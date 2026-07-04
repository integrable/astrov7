---
title: "Stress Tensor and the Metric"
description: "How the boundary metric acts as the source for the CFT stress tensor, and how the holographic stress tensor is extracted from the renormalized gravitational action."
sidebar:
  order: 80
---

The metric is the source for the stress tensor. This is one of the most important entries in the AdS/CFT dictionary because it is where ordinary geometry becomes the generator of energy, momentum, pressure, trace anomalies, and gravitational response in the boundary theory.

For a scalar operator, the source is a scalar function $J(x)$. For a conserved current, the source is a background gauge field $A_i(x)$. For the stress tensor, the source is the background metric $g_{(0)ij}(x)$ on which the boundary QFT is placed:

$$
\boxed{
\text{boundary metric } g_{(0)ij}
\quad \longleftrightarrow \quad
\text{bulk metric } G_{MN}
}
$$

and

$$
\boxed{
\text{bulk graviton}
\quad \longleftrightarrow \quad
\text{CFT stress tensor } T_{ij}
}
$$

This page explains the metric/stress-tensor dictionary at the first working level. The full machinery is holographic renormalization, which begins in the next unit. Here the aim is to understand what is being varied, what is held fixed, why counterterms are necessary, and what information in the near-boundary metric becomes $\langle T_{ij}\rangle$.

<figure class="doc-figure" style="--figure-width: 54rem;">

![The boundary metric sources the CFT stress tensor, while the same boundary metric is Dirichlet data for the bulk metric. Varying the renormalized on-shell action gives the holographic stress tensor.](/figures/course/stress-tensor-metric.svg)

<figcaption>

The metric/stress-tensor dictionary. The boundary metric $g_{(0)ij}$ is a source in the CFT and a Dirichlet boundary condition for the bulk metric. The renormalized Brown–York tensor, including counterterms, computes $\langle T_{ij}\rangle$.

</figcaption>
</figure>

## Why this matters

The stress tensor is not just another operator. It is the operator associated with spacetime symmetries. It measures local energy density, momentum density, pressure, and stress. Its correlation functions encode transport, sound modes, viscosity, central charges, conformal anomalies, and the response of the theory to changes in geometry.

On the gravity side, the metric is not just another field either. It is the field that defines distances, horizons, causal structure, and black-hole thermodynamics. Thus the entry

$$
g_{(0)ij}
\quad \longleftrightarrow \quad
T_{ij}
$$

is the part of the dictionary that turns gravitational geometry into QFT energy-momentum data.

Three later topics depend directly on this page:

1. **Holographic renormalization.** The stress tensor is the cleanest place to see why the Brown–York tensor must be supplemented by counterterms.
2. **Thermal holography.** Black-brane metrics encode the energy density and pressure of thermal CFT states.
3. **Hydrodynamics.** Retarded correlators $G^R_{T_{ij}T_{kl}}$ are obtained by solving linearized gravitational perturbations.

The metric dictionary is also the reason why the spin-two bulk graviton is dual to the boundary stress tensor.

## Setup: QFT on a background metric

A local QFT can be coupled to nondynamical background sources. For the operators relevant here, the generating functional has the schematic form

$$
Z_{\mathrm{CFT}}[g_{(0)},A,J]
=
\int [D\Phi]\,\exp\!
\left(
-S_{\mathrm{CFT}}[\Phi;g_{(0)}]
-\int d^d x\sqrt{|g_{(0)}|}\,J\mathcal O
-\int d^d x\sqrt{|g_{(0)}|}\,A_iJ^i
\right),
$$

in Euclidean signature. We write

$$
W_{\mathrm{CFT}}[g_{(0)},A,J]=\log Z_{\mathrm{CFT}}[g_{(0)},A,J].
$$

The boundary metric $g_{(0)ij}$ is not integrated over in ordinary AdS/CFT with Dirichlet boundary conditions. It is a source. Varying it defines the stress tensor.

In this course we use the convention

$$
\delta W_{\mathrm{CFT}}
=
\frac12\int d^d x\sqrt{|g_{(0)}|}\,
\langle T^{ij}\rangle\,\delta g_{(0)ij}
+
\int d^d x\sqrt{|g_{(0)}|}\,
\langle J^i\rangle\delta A_i
+
\int d^d x\sqrt{|g_{(0)}|}\,
\langle \mathcal O\rangle\delta J
+
\cdots .
$$

Therefore

$$
\boxed{
\langle T^{ij}(x)\rangle
=
\frac{2}{\sqrt{|g_{(0)}|}}
\frac{\delta W_{\mathrm{CFT}}}{\delta g_{(0)ij}(x)}
}
$$

with this sign convention. In the classical Euclidean gravity saddle,

$$
W_{\mathrm{CFT}}[g_{(0)},A,J]
\simeq
-S_{\text{ren,on-shell}}[g_{(0)},A,J],
$$

so

$$
\boxed{
\langle T^{ij}(x)\rangle
\simeq
-\frac{2}{\sqrt{|g_{(0)}|}}
\frac{\delta S_{\text{ren,on-shell}}}{\delta g_{(0)ij}(x)}
}
$$

in Euclidean signature. In Lorentzian signature the factors of $i$ and signs are convention-dependent. The invariant lesson is simple: **the one-point function of the stress tensor is the response of the renormalized on-shell action to a change of boundary metric.**

## Boundary metric as bulk Dirichlet data

Near the conformal boundary, an asymptotically locally AdS metric can be written in Fefferman–Graham gauge:

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2+g_{ij}(z,x)dx^i dx^j
\right),
\qquad z\to0.
$$

The leading term in the expansion of $g_{ij}(z,x)$ defines the boundary metric:

$$
g_{ij}(z,x)
=
g_{(0)ij}(x)+\cdots .
$$

More precisely, AdS/CFT fixes a boundary **conformal class** $[g_{(0)}]$, because a different choice of defining function near the boundary can Weyl-rescale $g_{(0)}$. Choosing a representative $g_{(0)ij}$ is like choosing a conformal frame for the CFT.

For a small perturbation around flat space,

$$
g_{(0)ij}(x)=\eta_{ij}+h_{(0)ij}(x),
$$

the CFT source term is, to first order,

$$
\delta W_{\mathrm{CFT}}
=
\frac12\int d^d x\,\langle T^{ij}(x)\rangle h_{(0)ij}(x).
$$

Thus $h_{(0)ij}$ is the source for $T^{ij}$. The corresponding bulk field is the metric perturbation $h_{MN}$, usually called the graviton. This is the spin-two version of the scalar dictionary:

$$
\phi_{(0)} \leftrightarrow \mathcal O,
\qquad
A_{(0)i} \leftrightarrow J^i,
\qquad
g_{(0)ij} \leftrightarrow T^{ij}.
$$

## The gravitational action and the Brown–York tensor

For Dirichlet boundary conditions on the metric, the gravitational action is not just the Einstein–Hilbert action. One must include the Gibbons–Hawking–York boundary term:

$$
S_{\mathrm{grav}}
=
\frac{1}{16\pi G_{d+1}}
\int_M d^{d+1}x\sqrt{|G|}\,(R-2\Lambda)
+
\frac{1}{8\pi G_{d+1}}
\int_{\partial M}d^d x\sqrt{|\gamma|}\,K
+S_{\mathrm{ct}}.
$$

Here

$$
\Lambda=-\frac{d(d-1)}{2L^2},
$$

$\gamma_{ij}$ is the induced metric on a cutoff surface $z=\epsilon$, and $K_{ij}$ is its extrinsic curvature. The term $S_{\mathrm{ct}}$ is a sum of local counterterms built from $\gamma_{ij}$ and boundary values of matter fields.

Before adding counterterms, the variation of the Einstein–Hilbert plus Gibbons–Hawking–York action gives the Brown–York tensor on the cutoff surface:

$$
T^{\mathrm{BY}}_{ij}
=
\frac{1}{8\pi G_{d+1}}
\left(K_{ij}-K\gamma_{ij}\right),
$$

up to the sign determined by the orientation convention for the outward normal. This tensor is natural, but it is not yet the CFT stress tensor. It diverges as the cutoff surface is taken to the AdS boundary.

The renormalized cutoff stress tensor is instead

$$
T^{\mathrm{BY+ct}}_{ij}
=
\frac{2}{\sqrt{|\gamma|}}
\frac{\delta}{\delta \gamma^{ij}}
\left(S_{\mathrm{bulk}}+S_{\mathrm{GHY}}+S_{\mathrm{ct}}\right),
$$

again with sign depending on whether one varies with respect to $\gamma_{ij}$ or $\gamma^{ij}$. A standard first part of the counterterm contribution is

$$
T^{\mathrm{BY+ct}}_{ij}
=
\frac{1}{8\pi G_{d+1}}
\left(
K_{ij}-K\gamma_{ij}
-\frac{d-1}{L}\gamma_{ij}
+\frac{L}{d-2}G_{ij}[\gamma]
+\cdots
\right),
$$

for $d>2$, where $G_{ij}[\gamma]$ is the Einstein tensor of the cutoff metric and the ellipsis denotes higher-curvature and matter counterterms. This formula is meant as a representative convention, not as a universal sign oracle. The next unit will give the systematic prescription.

The CFT stress tensor is obtained by rescaling from the cutoff metric to the boundary metric and removing the cutoff:

$$
\boxed{
\langle T_{ij}\rangle
=
\lim_{\epsilon\to0}
\left(\frac{L}{\epsilon}\right)^{d-2}
T^{\mathrm{BY+ct}}_{ij}(\epsilon)
}
$$

for covariant components in Fefferman–Graham coordinates. The power is fixed by the fact that $T_{ij}$ has scaling dimension $d$ but carries two lower metric indices.

## Fefferman–Graham expansion and the stress tensor

The most useful way to see where $\langle T_{ij}\rangle$ lives is the Fefferman–Graham expansion. For pure gravity, the near-boundary metric takes the form

$$
g_{ij}(z,x)
=
g_{(0)ij}(x)
+z^2g_{(2)ij}(x)
+\cdots
+z^d g_{(d)ij}(x)
+z^d\log z^2\,h_{(d)ij}(x)
+\cdots .
$$

The logarithmic term is present only in special cases, especially when the boundary dimension $d$ is even. It is tied to the conformal anomaly.

The Einstein equations determine the coefficients $g_{(2)},g_{(4)},\ldots,g_{(d-2)}$ locally from the source metric $g_{(0)}$. They also determine the trace and divergence of $g_{(d)}$. But the transverse-traceless part of $g_{(d)}$ is not fixed locally by $g_{(0)}$. It is state data.

Schematically,

$$
\boxed{
\langle T_{ij}\rangle
=
\frac{dL^{d-1}}{16\pi G_{d+1}}g_{(d)ij}
+X_{ij}[g_{(0)}]
}
$$

where $X_{ij}[g_{(0)}]$ is a local functional of the source metric. It is nonzero when curvature counterterms, logarithmic terms, or conformal anomalies contribute.

For a flat boundary metric and no extra sources, the local term often vanishes, and the formula simplifies to

$$
\langle T_{ij}\rangle
=
\frac{dL^{d-1}}{16\pi G_{d+1}}g_{(d)ij}.
$$

In AdS$_5$/CFT$_4$, this becomes

$$
\langle T_{ij}\rangle
=
\frac{L^3}{4\pi G_5}g_{(4)ij}
+X_{ij}[g_{(0)}].
$$

This is one of the most useful practical formulas in classical holography.

## Constraints become Ward identities

The radial components of Einstein's equations are constraints rather than dynamical radial evolution equations. Holographically, these constraints become Ward identities for the boundary stress tensor.

If the CFT is coupled to a background gauge field $A_i$ and scalar sources $J^I$, diffeomorphism invariance gives

$$
\boxed{
\nabla_i\langle T^{ij}\rangle
=
F^j{}_{i}\langle J^i\rangle
+\sum_I \langle \mathcal O_I\rangle \nabla^j J^I
}
$$

with the sign depending on the source convention used in the definition of $W$. The meaning is physical: stress-tensor conservation is modified when background sources inject momentum into the system.

If all sources are constant and the background is flat, this reduces to ordinary conservation:

$$
\partial_i\langle T^{ij}\rangle=0.
$$

The trace Ward identity has the schematic form

$$
\boxed{
\langle T^i{}_i\rangle
=
\mathcal A[g_{(0)},A,J]
+\sum_I (d-\Delta_I)J^I\langle \mathcal O_I\rangle
}
$$

where $\mathcal A$ is the conformal anomaly. If the boundary dimension $d$ is odd and the theory is placed on a smooth background without explicit scale-breaking sources, there is no local Weyl anomaly. If $d$ is even, a Weyl anomaly can appear on curved backgrounds.

For a pure CFT on flat space with no sources,

$$
\langle T^i{}_i\rangle=0.
$$

This is the field-theory reason why the thermal stress tensor of a CFT must obey an equation of state such as

$$
\epsilon=(d-1)p
$$

in a homogeneous isotropic state.

## Example 1: pure Poincare AdS

Consider pure AdS in Poincare coordinates:

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+\eta_{ij}dx^i dx^j\right).
$$

Here

$$
g_{(0)ij}=\eta_{ij},
\qquad
 g_{(d)ij}=0,
$$

and all local curvature terms vanish. Therefore

$$
\langle T_{ij}\rangle=0.
$$

This is the vacuum of the CFT on flat space. It is important that this statement depends on the conformal frame. The same physical bulk spacetime written with a boundary cylinder rather than a flat boundary can have a nonzero Casimir energy.

## Example 2: global AdS and Casimir energy

Global AdS has boundary geometry

$$
\mathbb R_t\times S^{d-1}.
$$

For even-dimensional boundary CFTs, the vacuum stress tensor on the cylinder can contain a Casimir energy. In AdS$_5$/CFT$_4$, global AdS gives the vacuum energy of $\mathcal N=4$ SYM on $S^3$.

The result in standard normalization is

$$
E_{\mathrm{vac}}
=
\frac{3\pi L^2}{32G_5}
=
\frac{3N^2}{16L}
$$

at large $N$, using

$$
\frac{L^3}{G_5}=\frac{2N^2}{\pi}.
$$

This is not an excitation above the cylinder vacuum. It is the vacuum stress tensor in a curved conformal frame.

## Example 3: planar black brane stress tensor

The planar AdS black brane is dual to a thermal CFT state on flat space. Its metric can be written as

$$
ds^2
=
\frac{L^2}{z^2}
\left(
-f(z)dt^2+d\vec x^{\,2}+\frac{dz^2}{f(z)}
\right),
\qquad
f(z)=1-\left(\frac{z}{z_h}\right)^d.
$$

This is not in Fefferman–Graham gauge, but one can transform it near the boundary and extract $g_{(d)ij}$. The resulting stress tensor has the perfect-fluid form

$$
\langle T_{\mu\nu}\rangle
=
\operatorname{diag}(\epsilon,p,p,\ldots,p),
$$

with

$$
p
=
\frac{L^{d-1}}{16\pi G_{d+1}}\frac{1}{z_h^d},
\qquad
\epsilon
=
(d-1)p.
$$

The trace vanishes:

$$
\langle T^\mu{}_{\mu}\rangle
=-\epsilon+(d-1)p=0,
$$

as required for a CFT in flat space. The horizon temperature is

$$
T=\frac{d}{4\pi z_h},
$$

so the energy density scales as

$$
\epsilon\propto T^d.
$$

That is exactly what dimensional analysis predicts for a $d$-dimensional conformal theory.

## Stress-tensor two-point functions

The one-point function comes from the first variation of the renormalized on-shell action. The two-point function comes from the second variation:

$$
\langle T^{ij}(x)T^{kl}(y)\rangle_c
=
\frac{4}{\sqrt{|g_{(0)}(x)|}\sqrt{|g_{(0)}(y)|}}
\frac{\delta^2 W_{\mathrm{CFT}}}
{\delta g_{(0)ij}(x)\delta g_{(0)kl}(y)}.
$$

In the gravity approximation this means solving the linearized Einstein equations for metric perturbations with boundary value $h_{(0)ij}$ and expanding the on-shell action to quadratic order:

$$
S_{\mathrm{ren}}[g_{(0)}+h_{(0)}]
=
S_{\mathrm{ren}}[g_{(0)}]
+S^{(1)}_{\mathrm{ren}}[h_{(0)}]
+S^{(2)}_{\mathrm{ren}}[h_{(0)}]
+\cdots .
$$

The quadratic term $S^{(2)}_{\mathrm{ren}}$ generates $\langle TT\rangle$. In a CFT, the normalization of the stress-tensor two-point function is often called $C_T$. In holographic CFTs with an Einstein gravity dual,

$$
C_T\propto \frac{L^{d-1}}{G_{d+1}},
$$

with a dimension-dependent numerical coefficient fixed by conventions. For AdS$_5$/CFT$_4$ Einstein gravity gives

$$
a=c=\frac{\pi L^3}{8G_5}
$$

at leading large $N$.

This is why the dimensionless combination $L^{d-1}/G_{d+1}$ counts the number of boundary degrees of freedom.

## Dictionary checkpoint

| Boundary statement | Bulk statement |
|---|---|
| Put the CFT on background metric $g_{(0)ij}$ | Impose asymptotic boundary metric $g_{(0)ij}$ for $G_{MN}$ |
| Source $h_{(0)ij}$ | Non-normalizable metric perturbation |
| Stress tensor $T_{ij}$ | Bulk graviton $h_{MN}$ |
| $\langle T_{ij}\rangle$ | Renormalized Brown–York tensor |
| Conservation of $T_{ij}$ | Momentum constraint of Einstein equations |
| Trace Ward identity | Radial/Weyl constraint plus anomaly terms |
| $TT$ correlator | Quadratic on-shell action for metric perturbations |
| Central charge or $C_T$ | AdS radius in Planck units, $L^{d-1}/G_{d+1}$ |
| Thermal energy density and pressure | Asymptotic data of an AdS black brane |

## Common confusions

### “The boundary metric is dynamical because the bulk metric is dynamical.”

Not in the standard Dirichlet formulation of AdS/CFT. The bulk metric is dynamical in the interior, but its leading boundary value $g_{(0)ij}$ is held fixed as a source. The CFT is usually defined on a fixed background spacetime. Making the boundary metric dynamical is a different problem with different boundary conditions.

### “The Brown–York tensor alone is the CFT stress tensor.”

Almost, but not quite. The Brown–York tensor on a cutoff surface diverges as the cutoff approaches the AdS boundary. The CFT stress tensor is the renormalized limit of Brown–York plus local counterterm contributions.

### “The coefficient $g_{(d)ij}$ is always exactly $\langle T_{ij}\rangle$.”

Only in simple cases. In general,

$$
\langle T_{ij}\rangle
=
\frac{dL^{d-1}}{16\pi G_{d+1}}g_{(d)ij}
+X_{ij}[g_{(0)}],
$$

where $X_{ij}$ contains local curvature, anomaly, and scheme-dependent contributions. Flat-boundary examples often hide this subtlety.

### “Tracelessness means the stress tensor always vanishes.”

No. Tracelessness is the condition

$$
\langle T^i{}_i\rangle=0,
$$

not $\langle T_{ij}\rangle=0$. A thermal CFT in flat space has nonzero energy density and pressure, but its stress tensor is traceless because $\epsilon=(d-1)p$.

### “A metric perturbation is always a state.”

The leading metric perturbation $h_{(0)ij}$ is a source. The normalizable part of the bulk metric perturbation is related to the response $\langle T_{ij}\rangle$ and to the state. Source and state are conceptually distinct, even though both appear in the asymptotic expansion of the same bulk field.

## Exercises

### Exercise 1: Derive the stress-tensor definition

Assume the generating functional satisfies

$$
\delta W[g]
=
\frac12\int d^d x\sqrt{|g|}\,\langle T^{ij}\rangle\delta g_{ij}.
$$

Show that

$$
\langle T^{ij}(x)\rangle
=
\frac{2}{\sqrt{|g(x)|}}\frac{\delta W}{\delta g_{ij}(x)}.
$$

<details>
<summary><strong>Solution</strong></summary>

By definition of the functional derivative,

$$
\delta W[g]
=
\int d^d x\,\frac{\delta W}{\delta g_{ij}(x)}\delta g_{ij}(x).
$$

Comparing this with

$$
\delta W[g]
=
\frac12\int d^d x\sqrt{|g|}\,\langle T^{ij}\rangle\delta g_{ij},
$$

we identify

$$
\frac{\delta W}{\delta g_{ij}(x)}
=
\frac12\sqrt{|g(x)|}\,\langle T^{ij}(x)\rangle.
$$

Therefore

$$
\langle T^{ij}(x)\rangle
=
\frac{2}{\sqrt{|g(x)|}}\frac{\delta W}{\delta g_{ij}(x)}.
$$

</details>

### Exercise 2: Diffeomorphism Ward identity with a scalar source

Let

$$
\delta W
=
\frac12\int \sqrt{|g|}\,T^{ij}\delta g_{ij}
+
\int \sqrt{|g|}\,\mathcal O\delta J.
$$

Under an infinitesimal diffeomorphism generated by $\xi^i$,

$$
\delta g_{ij}=\nabla_i\xi_j+\nabla_j\xi_i,
\qquad
\delta J=\xi^i\nabla_iJ.
$$

Assuming $\delta W=0$, derive the Ward identity.

<details>
<summary><strong>Solution</strong></summary>

Substitute the variations:

$$
\delta W
=
\int\sqrt{|g|}\,T^{ij}\nabla_i\xi_j
+
\int\sqrt{|g|}\,\mathcal O\xi^j\nabla_jJ.
$$

Integrating the first term by parts gives

$$
\int\sqrt{|g|}\,T^{ij}\nabla_i\xi_j
=
-\int\sqrt{|g|}\,(\nabla_iT^{ij})\xi_j,
$$

ignoring boundary terms. Therefore

$$
\delta W
=
-\int\sqrt{|g|}\,
\left(\nabla_iT^{ij}-\mathcal O\nabla^jJ\right)\xi_j.
$$

Since $\xi_j$ is arbitrary and $\delta W=0$,

$$
\nabla_iT^{ij}=\mathcal O\nabla^jJ.
$$

After taking expectation values,

$$
\nabla_i\langle T^{ij}\rangle
=\langle\mathcal O\rangle\nabla^jJ.
$$

</details>

### Exercise 3: CFT equation of state from tracelessness

A homogeneous isotropic thermal state in flat $d$-dimensional Minkowski space has

$$
\langle T^\mu{}_{\nu}\rangle
=
\operatorname{diag}(-\epsilon,p,p,\ldots,p).
$$

Use tracelessness to derive the relation between $\epsilon$ and $p$.

<details>
<summary><strong>Solution</strong></summary>

The trace is

$$
\langle T^\mu{}_{\mu}\rangle
=-\epsilon+(d-1)p.
$$

For a CFT in flat space with no sources and no anomaly,

$$
\langle T^\mu{}_{\mu}\rangle=0.
$$

Therefore

$$
-\epsilon+(d-1)p=0,
$$

so

$$
\epsilon=(d-1)p.
$$

This is exactly the equation of state obtained from the planar AdS black brane.

</details>

### Exercise 4: Identify source and response for the metric

In Fefferman–Graham gauge, suppose the near-boundary metric has the expansion

$$
g_{ij}(z,x)
=
g_{(0)ij}(x)+z^d g_{(d)ij}(x)+\cdots
$$

with a flat boundary metric and no anomaly terms. Which coefficient is the source, and which coefficient determines the stress-tensor expectation value?

<details>
<summary><strong>Solution</strong></summary>

The source is the leading coefficient $g_{(0)ij}(x)$. It specifies the background metric of the CFT, up to conformal frame.

For a flat boundary metric with no local anomaly terms, the response is determined by $g_{(d)ij}(x)$:

$$
\langle T_{ij}\rangle
=
\frac{dL^{d-1}}{16\pi G_{d+1}}g_{(d)ij}.
$$

In more general situations, this formula is corrected by local terms $X_{ij}[g_{(0)}]$.

</details>

## Further reading

- J. D. Brown and J. W. York, [Quasilocal Energy and Conserved Charges Derived from the Gravitational Action](https://arxiv.org/abs/gr-qc/9209012).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).
- S. de Haro, K. Skenderis, and S. N. Solodukhin, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
- M. Henningson and K. Skenderis, [The Holographic Weyl Anomaly](https://arxiv.org/abs/hep-th/9806087).

The next unit develops this page into a systematic algorithm: regulate the asymptotically AdS spacetime, add covariant counterterms, vary the renormalized action, and remove the cutoff.
