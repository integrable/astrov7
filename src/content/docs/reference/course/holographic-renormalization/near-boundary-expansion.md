---
title: "Near-Boundary Expansion"
description: "How asymptotic expansions of bulk fields near the AdS boundary separate sources, local counterterm data, and state-dependent expectation values."
sidebar:
  order: 20
---

Holographic renormalization works because the near-boundary behavior of asymptotically AdS fields is highly constrained. Once the sources are specified, the equations of motion determine a tower of local terms near $z=0$. The undetermined terms are the normalizable data, and these are precisely where one-point functions and state dependence enter.

This page is the technical bridge between the statement

$$
S_{\rm ren}
=
\lim_{\epsilon\to0}
\left(S_{\rm reg}+S_{\rm ct}\right)
$$

and actual holographic computations. We will learn how to expand scalars, gauge fields, and metrics near the boundary, which coefficients are sources, which coefficients are fixed locally, and which coefficients encode vevs.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Near the AdS boundary, a bulk field expansion separates source data, locally determined coefficients, possible logarithmic anomaly terms, and state-dependent normalizable data.](/figures/course/near-boundary-expansion.svg)

<figcaption>

Near-boundary data split into three kinds of information: sources such as $\phi_{(0)}$ and $g_{(0)ij}$, local coefficients fixed recursively by the equations of motion, and normalizable data such as $A(x)$ or $g_{(d)ij}$ that encode expectation values. Logarithmic terms appear in special dimensions and are tied to anomalies.

</figcaption>
</figure>

## Why this matters

Near-boundary expansions answer three questions that recur throughout AdS/CFT:

1. **What is the source?** The source is the leading asymptotic coefficient after the correct rescaling, not the raw cutoff value of the bulk field.
2. **What counterterms are needed?** Divergences are determined by local terms in the asymptotic expansion.
3. **What is the vev?** The one-point function is associated with the normalizable response, corrected by local terms required by renormalization.

The expansion is also the place where the radial-coordinate/RG-scale intuition becomes concrete. Solving the bulk equations from small $z$ inward resembles evolving from UV data toward the IR. The UV data are the sources. The IR condition selects the state.

## Fefferman–Graham gauge

For asymptotically locally AdS$_{d+1}$ geometries, a standard near-boundary coordinate choice is Fefferman–Graham gauge:

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+g_{ij}(z,x)dx^i dx^j\right),
\qquad z\to0.
$$

The boundary is at $z=0$. The cutoff surface is $z=\epsilon$. The induced metric on the cutoff surface is

$$
\gamma_{ij}(\epsilon,x)
=
\frac{L^2}{\epsilon^2}g_{ij}(\epsilon,x).
$$

The finite boundary metric source is

$$
g_{(0)ij}(x)
=
\lim_{z\to0}g_{ij}(z,x),
$$

up to the choice of conformal frame. A different defining function $z$ can Weyl-rescale $g_{(0)ij}$.

Fefferman–Graham gauge is not always the best coordinate system globally. It often breaks down at horizons or caustics. But near the conformal boundary it is the cleanest coordinate system for holographic renormalization.

## Scalar fields: indicial exponents

Consider a scalar field in fixed Euclidean Poincaré AdS$_{d+1}$:

$$
ds^2
=
\frac{L^2}{z^2}\left(dz^2+d\vec x^{\,2}\right).
$$

The scalar wave equation is

$$
\left(\nabla^2-m^2\right)\phi=0.
$$

Near $z=0$, the radial derivative terms dominate over boundary derivatives. If

$$
\phi(z,x)\sim z^\alpha f(x),
$$

then the leading equation gives

$$
\alpha(\alpha-d)=m^2L^2.
$$

Thus

$$
\alpha=\Delta_-
\quad\text{or}\quad
\alpha=\Delta_+,
$$

where

$$
\Delta_\pm
=
\frac d2\pm\nu,
\qquad
\nu=\sqrt{\frac{d^2}{4}+m^2L^2}\,.
$$

In standard quantization,

$$
\Delta=\Delta_+,
\qquad
\Delta_-=d-\Delta.
$$

The near-boundary expansion begins as

$$
\phi(z,x)
=
z^{d-\Delta}
\left(\phi_{(0)}(x)+z^2\phi_{(2)}(x)+z^4\phi_{(4)}(x)+\cdots\right)
+
z^\Delta
\left(A(x)+\cdots\right).
$$

The coefficient $\phi_{(0)}$ is the source for the dual operator $\mathcal O$. The coefficient $A(x)$ is the first state-dependent response coefficient. The renormalized one-point function has the schematic form

$$
\langle\mathcal O(x)\rangle
=(2\Delta-d)A(x)+\text{local terms in sources},
$$

with the overall normalization depending on the normalization of the scalar action.

## The first local scalar coefficient

For a scalar in flat-boundary Poincaré AdS, the full equation is

$$
\left[
z^2\partial_z^2-(d-1)z\partial_z+z^2\Box_x-m^2L^2
\right]\phi=0.
$$

Let

$$
\alpha=d-\Delta
$$

and insert

$$
\phi(z,x)=z^\alpha\left(\phi_{(0)}(x)+z^2\phi_{(2)}(x)+\cdots\right).
$$

The $z^{\alpha}$ term gives the indicial equation. The $z^{\alpha+2}$ term gives

$$
\left[(\alpha+2)(\alpha+2-d)-m^2L^2\right]\phi_{(2)}+
\Box_x\phi_{(0)}=0.
$$

Using $m^2L^2=\alpha(\alpha-d)$, this becomes

$$
\phi_{(2)}
=
\frac{1}{2(2\Delta-d-2)}\Box_x\phi_{(0)}
$$

for $2\Delta-d-2\ne0$, with the sign convention for $\Box_x$ inherited from the metric signature. This coefficient is local in the source. Higher coefficients are similarly local until one reaches the normalizable order or a logarithmic resonance.

This recursive structure is the reason counterterms are local.

## Normalizable data and interior boundary conditions

The asymptotic expansion alone does not determine $A(x)$. To determine it, one must solve the bulk equation with an interior condition. Examples include:

- regularity in Euclidean AdS;
- normalizability in global AdS;
- incoming-wave conditions at a Lorentzian black-hole horizon;
- smoothness at the end of a soliton geometry.

Thus the source $\phi_{(0)}$ specifies the external deformation of the CFT, while $A(x)$ depends on the state or saddle selected by the interior.

In momentum space for Euclidean Poincaré AdS, regularity at $z\to\infty$ selects the Bessel $K_\nu$ solution. Expanding that solution near $z=0$ relates $A(k)$ nonlocally to $\phi_{(0)}(k)$, producing the two-point function. In a black-hole background, the corresponding relation gives thermal Green's functions.

## Logarithmic scalar terms

If the two roots differ by an integer in a way that creates a resonance in the recursion, logarithmic terms can appear. A common case is

$$
2\nu=2\Delta-d\in\mathbb Z_{\ge0}.
$$

Then the expansion can contain terms such as

$$
\phi(z,x)
=
z^{d-\Delta}
\left(
\phi_{(0)}+\cdots+z^{2\nu}\log z^2\,\psi_{(2\nu)}+\cdots
\right)
+
z^\Delta\left(A+\cdots\right).
$$

The logarithmic coefficient $\psi_{(2\nu)}$ is local in the source and is tied to scale dependence in the renormalized generating functional. In even boundary dimensions, similar logarithms in the metric expansion encode the Weyl anomaly.

Logs are not a sign that the expansion has failed. They are the expansion's way of remembering anomalies and renormalization-scale dependence.

## Metric expansion

In Fefferman–Graham gauge, the metric has an expansion of the form

$$
g_{ij}(z,x)
=
g_{(0)ij}(x)
+z^2g_{(2)ij}(x)
+z^4g_{(4)ij}(x)
+\cdots
+z^d g_{(d)ij}(x)
+z^d\log z^2\,h_{(d)ij}(x)
+\cdots .
$$

The logarithmic term $h_{(d)ij}$ appears for even $d$ in pure gravity and is related to the conformal anomaly. For odd $d$, there is no gravitational Weyl anomaly of this type.

The leading coefficient is the boundary metric source:

$$
g_{(0)ij}
\quad\longleftrightarrow\quad
\text{source for }T^{ij}.
$$

The coefficients $g_{(2)ij},g_{(4)ij},\ldots$ below order $z^d$ are locally determined by $g_{(0)ij}$ through Einstein's equations. For example, for pure gravity and $d\ne2$,

$$
g_{(2)ij}
=
-\frac{1}{d-2}
\left(
R_{ij}[g_{(0)}]
-
\frac{R[g_{(0)}]}{2(d-1)}g_{(0)ij}
\right).
$$

The coefficient $g_{(d)ij}$ contains the state-dependent information. Its trace and divergence are constrained by the equations of motion and by anomalies, while its transverse-traceless part is related to the expectation value of the stress tensor:

$$
\langle T_{ij}\rangle
\sim
\frac{dL^{d-1}}{16\pi G_{d+1}}g_{(d)ij}
+\text{local terms in }g_{(0)}.
$$

The symbol $\sim$ hides convention-dependent signs and local anomaly terms. The exact formula depends on the action normalization, dimension, and counterterm scheme.

## Gauge-field expansion

A bulk gauge field is dual to a conserved current. In radial gauge,

$$
A_z=0,
$$

its near-boundary expansion typically has the form

$$
A_i(z,x)
=
A_{(0)i}(x)
+z^{d-2}A_{(d-2)i}(x)
+\cdots,
$$

with logarithmic or derivative terms in special dimensions.

The leading coefficient $A_{(0)i}$ is the source for the conserved current $J^i$. The normalizable coefficient $A_{(d-2)i}$ is related to the current expectation value:

$$
\langle J^i\rangle
\sim
A_{(d-2)}^i+\text{local terms}.
$$

The radial Maxwell constraint gives the Ward identity. In the absence of charged operator sources,

$$
\nabla_i\langle J^i\rangle=0.
$$

This is the vector-field version of the same pattern: leading coefficient is source, subleading normalizable coefficient is response, and radial constraints become Ward identities.

## Spinors and other fields

Spinors have first-order radial equations, so their expansion is slightly different. Roughly, one half of the boundary spinor components are fixed as sources, while the conjugate half is determined as a response. A spinor of mass $m$ in AdS$_{d+1}$ is dual to a fermionic operator with dimension

$$
\Delta=\frac d2+|mL|
$$

in the standard quantization, with alternate choices possible in an allowed mass window.

For $p$-forms and higher-spin fields, the same organizing principle remains: specify the allowed asymptotic behavior, identify the source, solve the radial constraints, renormalize the canonical momentum, and read off the vev.

## Sources, local terms, vevs: the three-way split

For every field, the near-boundary expansion separates data into three classes.

| Coefficient type | Boundary meaning | Determination |
|---|---|---|
| leading non-normalizable data | source | chosen externally |
| local subleading data | counterterms, contact terms, anomalies | fixed recursively by equations of motion and sources |
| normalizable data | state-dependent vev | fixed by interior condition or full solution |

This split is one of the conceptual pillars of AdS/CFT. It explains why the UV divergences are local while expectation values are sensitive to the full bulk geometry.

## Radial canonical momenta

A useful way to package the response is through radial canonical momenta. For a scalar,

$$
\Pi_\phi(\epsilon,x)
=
\frac{\delta S_{\rm reg}}{\delta \phi(\epsilon,x)}
\sim
\sqrt{\gamma}\,n^M\partial_M\phi.
$$

The bare momentum diverges as $\epsilon\to0$. The renormalized momentum is obtained by adding the counterterm variation:

$$
\Pi_{\phi,{\rm ren}}
=
\lim_{\epsilon\to0}
\epsilon^{\Delta-d}
\left(
\Pi_\phi+
\frac{\delta S_{\rm ct}}{\delta\phi}
\right).
$$

Then

$$
\langle\mathcal O(x)\rangle
=
\Pi_{\phi,{\rm ren}}(x)
$$

up to the sign convention relating $W_{\rm CFT}$ to $S_{\rm ren}$. For the metric, the analogous canonical momentum is the extrinsic curvature combination that becomes the Brown–York tensor. For gauge fields, it is the radial electric field.

This viewpoint is especially powerful because the radial Hamiltonian constraints become CFT Ward identities.

## A practical near-boundary recipe

When solving a new holographic problem, proceed as follows:

1. **Choose Fefferman–Graham gauge near the boundary** if possible.
2. **Write the most general expansion** consistent with the expected weights.
3. **Insert into the equations of motion.** Solve recursively order by order in $z$.
4. **Separate local and normalizable data.** Do not confuse coefficients determined by sources with the independent response.
5. **Evaluate the divergent action.** Express divergences in terms of cutoff fields.
6. **Add local counterterms.** Use covariance with respect to the cutoff metric $\gamma_{ij}$.
7. **Compute renormalized canonical momenta.** These give one-point functions.
8. **Apply the interior condition.** This fixes the normalizable data as a functional of the sources and the state.

In many practical calculations, especially for two-point functions, one solves the full linearized equation rather than performing only the asymptotic recursion. But the near-boundary expansion is still required to identify sources, counterterms, and vevs.

## Example: flat-boundary massless scalar in AdS$_{d+1}$

For a massless scalar,

$$
m^2=0,
$$

the two roots are

$$
\Delta_-=0,
\qquad
\Delta_+=d.
$$

Thus the expansion begins as

$$
\phi(z,x)
=
\phi_{(0)}(x)
+z^2\phi_{(2)}(x)
+\cdots
+z^d A(x)
+\cdots.
$$

For $d>2$, the first local coefficient is

$$
\phi_{(2)}
=
\frac{1}{2(d-2)}\Box_x\phi_{(0)}.
$$

If the source is constant, then $\Box_x\phi_{(0)}=0$, so the derivative corrections vanish near the boundary. The normalizable coefficient $A$ is still not determined by near-boundary analysis alone. In pure Euclidean AdS, regularity may set it as a nonlocal functional of $\phi_{(0)}$; in a black-brane background, the horizon condition gives a different functional relation.

## Example: pure AdS metric

For pure Poincaré AdS with flat boundary,

$$
g_{(0)ij}=\delta_{ij},
$$

all curvature tensors of $g_{(0)}$ vanish. Hence

$$
g_{(2)ij}=0,
$$

and in fact

$$
g_{ij}(z,x)=\delta_{ij}
$$

in exact Poincaré AdS. The stress tensor in the flat-space vacuum vanishes in this conformal frame:

$$
\langle T_{ij}\rangle=0.
$$

By contrast, global AdS has boundary $\mathbb R\times S^{d-1}$. In even-dimensional CFTs on the cylinder, the vacuum stress tensor may have a Casimir contribution. This is not a contradiction; it reflects the choice of boundary conformal frame and anomaly structure.

## Dictionary checkpoint

The near-boundary expansion gives the following entries:

| Bulk coefficient | Boundary meaning |
|---|---|
| $\phi_{(0)}$ in $\phi=z^{d-\Delta}\phi_{(0)}+\cdots$ | source for scalar operator $\mathcal O$ |
| $A$ in $\phi=z^\Delta A+\cdots$ | normalizable response, related to $\langle\mathcal O\rangle$ |
| $g_{(0)ij}$ | source for $T^{ij}$, the boundary metric |
| $g_{(d)ij}$ | state-dependent metric coefficient, related to $\langle T_{ij}\rangle$ |
| $A_{(0)i}$ for a gauge field | source for current $J^i$ |
| $A_{(d-2)i}$ | response, related to $\langle J^i\rangle$ |
| logarithmic coefficients | anomalies and RG-scale dependence |
| radial constraints | Ward identities |

The recurring pattern is

$$
\boxed{
\text{source} + \text{interior condition}
\quad\Longrightarrow\quad
\text{response}
}
$$

after counterterms have been added.

## Common confusions

### “Every subleading coefficient is a vev.”

No. Many subleading coefficients are local functions of the source. The vev is associated with the independent normalizable data, plus local terms required by renormalization.

### “The near-boundary expansion determines the full bulk solution.”

No. It determines the asymptotic solution order by order. The normalizable data generally require an interior condition or a full solution.

### “Log terms are optional.”

No. When the recursion demands them, they are forced. They encode anomalies or scale dependence and are essential for correct Ward identities.

### “The boundary metric is the induced metric at $z=\epsilon$.”

The induced metric diverges as $\epsilon^{-2}$. The finite boundary metric source is the rescaled leading coefficient $g_{(0)ij}$.

### “Fefferman–Graham gauge is globally harmless.”

It is a near-boundary gauge. It can fail in the interior, especially near horizons. Real-time black-hole calculations often use ingoing Eddington–Finkelstein coordinates in the interior and translate to near-boundary data asymptotically.

## Exercises

### Exercise 1: Derive the scalar exponents

Starting from the near-boundary scalar equation

$$
\left[z^2\partial_z^2-(d-1)z\partial_z-m^2L^2\right]\phi=0,
$$

insert $\phi=z^\alpha f(x)$ and derive the two exponents.

<details>
<summary><strong>Solution</strong></summary>

With $\phi=z^\alpha f(x)$,

$$
z\partial_z\phi=\alpha z^\alpha f,
\qquad
z^2\partial_z^2\phi=\alpha(\alpha-1)z^\alpha f.
$$

The equation becomes

$$
\left[\alpha(\alpha-1)-(d-1)\alpha-m^2L^2\right]z^\alpha f=0.
$$

Thus

$$
\alpha(\alpha-d)=m^2L^2.
$$

The roots are

$$
\alpha=\frac d2\pm\sqrt{\frac{d^2}{4}+m^2L^2}
=\Delta_\pm.
$$

</details>

### Exercise 2: Compute $\phi_{(2)}$

For

$$
\phi=z^\alpha(\phi_{(0)}+z^2\phi_{(2)}+\cdots),
$$

show that

$$
\phi_{(2)}
=
\frac{1}{2(2\Delta-d-2)}\Box_x\phi_{(0)}
$$

in standard quantization, where $\alpha=d-\Delta$.

<details>
<summary><strong>Solution</strong></summary>

The $z^{\alpha+2}$ coefficient in

$$
\left[z^2\partial_z^2-(d-1)z\partial_z+z^2\Box_x-m^2L^2\right]\phi=0
$$

gives

$$
\left[(\alpha+2)(\alpha+2-d)-m^2L^2\right]\phi_{(2)}+
\Box_x\phi_{(0)}=0.
$$

Using $m^2L^2=\alpha(\alpha-d)$,

$$
(\alpha+2)(\alpha+2-d)-\alpha(\alpha-d)
=
2(2\alpha+2-d).
$$

Since $\alpha=d-\Delta$,

$$
2(2\alpha+2-d)
=-2(2\Delta-d-2).
$$

Therefore

$$
\phi_{(2)}
=
\frac{1}{2(2\Delta-d-2)}\Box_x\phi_{(0)}.
$$

</details>

### Exercise 3: The first metric coefficient for flat boundary

Use

$$
g_{(2)ij}
=
-\frac{1}{d-2}
\left(
R_{ij}[g_{(0)}]
-
\frac{R[g_{(0)}]}{2(d-1)}g_{(0)ij}
\right)
$$

to find $g_{(2)ij}$ when $g_{(0)ij}=\eta_{ij}$ or $\delta_{ij}$.

<details>
<summary><strong>Solution</strong></summary>

For a flat boundary metric,

$$
R_{ij}[g_{(0)}]=0,
\qquad
R[g_{(0)}]=0.
$$

Therefore

$$
g_{(2)ij}=0.
$$

This is consistent with exact Poincaré AdS, for which $g_{ij}(z,x)=g_{(0)ij}$ in Fefferman–Graham gauge.

</details>

### Exercise 4: Source versus response

For a scalar with $\Delta>d/2$ in standard quantization, explain why $\phi_{(0)}$ is interpreted as the source while $A$ is interpreted as response data.

<details>
<summary><strong>Solution</strong></summary>

Near the boundary,

$$
\phi=z^{d-\Delta}\phi_{(0)}+z^\Delta A+\cdots.
$$

For $\Delta>d/2$, the $z^{d-\Delta}$ term is the slower falloff. Fixing this coefficient specifies the asymptotic boundary condition for the bulk field. In the CFT, fixing a boundary condition is equivalent to turning on an external source for the dual operator.

The faster falloff is normalizable in the standard range and is not fixed by the source alone. It depends on the interior condition or state. Therefore it is response data and is related to $\langle\mathcal O\rangle$, after including local renormalization terms.

</details>

## Further reading

- Sebastian de Haro, Kostas Skenderis, and Sergey N. Solodukhin, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- Massimo Bianchi, Daniel Z. Freedman, and Kostas Skenderis, [Holographic Renormalization](https://arxiv.org/abs/hep-th/0112119).
- Kostas Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
- Ioannis Papadimitriou and Kostas Skenderis, [AdS/CFT Correspondence and Geometry](https://arxiv.org/abs/hep-th/0404176).
- Edward Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
