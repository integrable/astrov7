---
title: "One-Point Functions from Variation"
description: "A practical guide to obtaining holographic one-point functions by varying the renormalized on-shell action."
sidebar:
  order: 40
---

The renormalized on-shell action is useful because it is a generating functional. Once the divergent terms have been subtracted, one-point functions are obtained by variation with respect to sources.

This page gives the practical variational dictionary. The main idea is:

$$
\text{holographic vev}
\quad\longleftrightarrow\quad
\text{renormalized radial canonical momentum}.
$$

The word “renormalized” is essential. The raw canonical momentum at the cutoff surface diverges. Counterterms supply local subtraction terms. The finite limit is the one-point function, with a sign fixed by the source convention.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Sources are fixed at the conformal boundary. The bulk solution and interior condition determine the response. The regulated canonical momentum plus counterterm contribution has a finite limit, which gives the vev.](/figures/course/one-point-functions-variation.svg)

<figcaption>

One-point functions are obtained from finite variations of $S_{\rm ren}$. The boundary source fixes the leading asymptotic data. The interior condition selects the response. The raw cutoff momentum $\Pi_{\rm reg}$ is divergent, but $\Pi_{\rm reg}+\Pi_{\rm ct}$ has a finite limit. That finite renormalized momentum is the holographic vev, up to the sign convention relating $W_{\rm CFT}$ to $S_{\rm ren}$.

</figcaption>
</figure>

## Why this matters

Most holographic computations eventually ask for one of the following quantities:

- the scalar condensate $\langle\mathcal O\rangle$;
- the charge density or current $\langle J^i\rangle$;
- the energy density, pressure, or stress tensor $\langle T^{ij}\rangle$;
- the response of a state to a deformation;
- the Ward identities obeyed by a background solution.

All of these come from varying $S_{\rm ren}$. This is the safe rule. Reading off a subleading coefficient is a useful shortcut only after the variational normalization and counterterms are understood.

The computation has two layers:

$$
\delta S_{\text{ren,on-shell}}
\quad\Rightarrow\quad
\text{renormalized canonical momenta},
$$

and

$$
W_{\rm CFT}\approx -S_{\text{ren,on-shell}}
\quad\Rightarrow\quad
\text{CFT one-point functions}.
$$

The first layer is bulk mechanics. The second layer is the AdS/CFT sign and source convention.

## QFT variational definitions

Let the boundary theory live on a metric representative $g_{(0)ij}$. Let a scalar source $\phi_{(0)}$ couple to $\mathcal O$, a background gauge field $A_{(0)i}$ couple to $J^i$, and the metric source the stress tensor.

With the Euclidean convention

$$
S_E
\to
S_E-
\int d^d x\sqrt{g_{(0)}}\,\phi_{(0)}\mathcal O
-
\int d^d x\sqrt{g_{(0)}}\,A_{(0)i}J^i+
\cdots,
$$

the generating functional is

$$
W_{\rm CFT}=\log Z_{\rm CFT}.
$$

Its variation is

$$
\delta W_{\rm CFT}
=
\int d^d x\sqrt{g_{(0)}}
\left[
\langle\mathcal O\rangle\delta\phi_{(0)}
+
\langle J^i\rangle\delta A_{(0)i}
+
\frac12\langle T^{ij}\rangle\delta g_{(0)ij}
+\cdots
\right].
$$

Equivalently,

$$
\langle\mathcal O(x)\rangle
=
\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta W_{\rm CFT}}{\delta\phi_{(0)}(x)},
$$

$$
\langle J^i(x)\rangle
=
\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta W_{\rm CFT}}{\delta A_{(0)i}(x)},
$$

and

$$
\langle T^{ij}(x)\rangle
=
\frac{2}{\sqrt{g_{(0)}}}
\frac{\delta W_{\rm CFT}}{\delta g_{(0)ij}(x)}.
$$

In the classical Euclidean holographic limit used here,

$$
W_{\rm CFT}
\approx
-S_{\text{ren,on-shell}}.
$$

Therefore

$$
\boxed{
\langle\mathcal O\rangle
=
-
\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta S_{\text{ren,on-shell}}}{\delta\phi_{(0)}}
}
$$

and similarly for currents and the stress tensor. Many papers use different Euclidean source signs or Lorentzian conventions. The invariant statement is that one-point functions are finite renormalized momenta conjugate to sources.

## Bulk variation and canonical momenta

Let $\Psi$ denote a bulk field. On a classical solution, the variation of the regulated action reduces to a cutoff-surface term:

$$
\delta S_{\text{reg,on-shell}}
=
\int_{\Sigma_\epsilon}d^d x\sqrt\gamma\,\Pi_{\rm reg}^{\Psi}\delta\Psi.
$$

The regulated momentum $\Pi_{\rm reg}^{\Psi}$ is the radial canonical momentum conjugate to $\Psi$. It usually diverges as $\epsilon\to0$. The counterterm action contributes

$$
\delta S_{{\rm ct},\epsilon}
=
\int_{\Sigma_\epsilon}d^d x\sqrt\gamma\,\Pi_{\rm ct}^{\Psi}\delta\Psi.
$$

Thus

$$
\Pi_{\rm ren}^{\Psi}
=
\lim_{\epsilon\to0}
\left(
\text{appropriate rescaling of }
\Pi_{\rm reg}^{\Psi}+\Pi_{\rm ct}^{\Psi}
\right)
$$

is finite. The “appropriate rescaling” converts variations of cutoff fields into variations of finite sources. For a scalar,

$$
\phi(\epsilon,x)
\sim
\epsilon^{d-\Delta}\phi_{(0)}(x),
$$

so

$$
\delta\phi(\epsilon,x)
\sim
\epsilon^{d-\Delta}\delta\phi_{(0)}(x).
$$

For the metric,

$$
\gamma_{ij}(\epsilon,x)
\sim
\frac{L^2}{\epsilon^2}g_{(0)ij}(x),
$$

so one must rescale the Brown–York tensor before taking the boundary limit.

## Scalar one-point function

Take again the scalar action

$$
S_\phi
=
\frac{\mathcal N_\phi}{2}
\int d^{d+1}x\sqrt g
\left(
 g^{MN}\partial_M\phi\partial_N\phi+m^2\phi^2
\right).
$$

The regulated radial momentum is

$$
\Pi_{\rm reg}
=
\mathcal N_\phi n^M\partial_M\phi.
$$

The near-boundary expansion in standard quantization is

$$
\phi(z,x)
=
z^{d-\Delta}
\left(
\phi_{(0)}+z^2\phi_{(2)}+\cdots
\right)
+
z^\Delta
\left(A+\cdots\right).
$$

After adding the scalar counterterms and varying with respect to the finite source, one obtains the schematic but very useful result

$$
\boxed{
\langle\mathcal O(x)\rangle
=
\mathcal N_\phi(2\Delta-d)A(x)
+
\text{local terms in sources}
}
$$

with the Euclidean source convention used in this course.

The local terms are determined by counterterms and possible logarithms. They vanish in many simple flat-boundary examples with constant or zero sources, but they are not optional in general.

A useful mnemonic is:

$$
2\Delta-d
=
\Delta_+-\Delta_-.
$$

The factor multiplying $A$ is the difference between the two radial exponents. It comes from the radial derivative in the canonical momentum.

## Source-free vevs

A particularly important case is a normalizable scalar profile with no source:

$$
\phi_{(0)}=0,
\qquad
\phi(z,x)=z^\Delta A(x)+\cdots.
$$

Then, if no local source terms contribute,

$$
\langle\mathcal O(x)\rangle
=
\mathcal N_\phi(2\Delta-d)A(x).
$$

This is how many holographic condensates are identified. However, “source-free” must be checked in the correct quantization and scheme. In alternate quantization, or in the presence of mixed boundary conditions, the meaning of source and vev changes.

## Gauge fields and currents

For a bulk Maxwell field,

$$
S_A
=
\frac{1}{4g_{d+1}^2}
\int d^{d+1}x\sqrt g\,F_{MN}F^{MN}
$$

in Euclidean signature. On shell, the variation contains

$$
\delta S_A
=
\frac{1}{g_{d+1}^2}
\int_{\Sigma_\epsilon}d^d x\sqrt\gamma\,
 n_M F^{Mi}\delta A_i
$$

up to signs fixed by the orientation convention. Counterterms may contribute local pieces, especially in special dimensions.

The boundary source is

$$
A_i(z,x)=A_{(0)i}(x)+\cdots.
$$

The current expectation value is

$$
\boxed{
\langle J^i(x)\rangle
=
-
\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta S_{\rm ren}}{\delta A_{(0)i}(x)}
}
$$

with the Euclidean convention $W=-S_{\rm ren}$.

In many finite-density solutions one writes

$$
A_t(z)=\mu-\rho z^{d-2}+\cdots.
$$

Then $\mu$ is the chemical potential and $\rho$ is proportional to the charge density. The proportionality depends on the Maxwell normalization, the dimension, and counterterm conventions. The variational formula is what fixes it.

## Metric variation and the stress tensor

The boundary metric is the source for the stress tensor. The holographic stress tensor is

$$
\boxed{
\langle T^{ij}\rangle
=
-
\frac{2}{\sqrt{g_{(0)}}}
\frac{\delta S_{\rm ren}}{\delta g_{(0)ij}}
}
$$

in the same Euclidean convention. In Lorentzian conventions many authors absorb the sign into the definition of the Brown–York tensor.

At the cutoff surface, the regulated Brown–York tensor is built from the extrinsic curvature:

$$
T_{{\rm BY},\epsilon}^{ij}
\sim
\frac{1}{\kappa_{d+1}^2}
\left(
K^{ij}-K\gamma^{ij}
\right),
$$

with signs depending on the convention for the gravitational action and the normal vector. The counterterms contribute local curvature terms. The renormalized stress tensor is obtained by adding these terms and rescaling to the finite boundary metric.

For asymptotically AdS solutions in Fefferman–Graham gauge,

$$
g_{ij}(z,x)
=
g_{(0)ij}+\cdots+z^d g_{(d)ij}+z^d\log z^2\,h_{(d)ij}+\cdots.
$$

The expectation value has the schematic form

$$
\langle T_{ij}\rangle
=
\frac{dL^{d-1}}{2\kappa_{d+1}^2}g_{(d)ij}
+
\text{local curvature and source terms}.
$$

The local terms include anomaly contributions in even boundary dimension. For flat-boundary black branes, they are often absent or simple, so $g_{(d)ij}$ directly gives energy density and pressure.

## Ward identities from variations

One-point functions are not arbitrary. Symmetries of the renormalized action imply Ward identities.

### Gauge Ward identity

If $S_{\rm ren}$ is invariant under boundary gauge transformations

$$
\delta A_{(0)i}=\nabla_i\alpha,
$$

then

$$
\nabla_i\langle J^i\rangle=0
$$

when there are no charged scalar sources. With charged sources, the right-hand side contains the explicit symmetry-breaking terms produced by those sources.

### Diffeomorphism Ward identity

Under a boundary diffeomorphism generated by $\xi^i$,

$$
\delta g_{(0)ij}=\nabla_i\xi_j+\nabla_j\xi_i,
\qquad
\delta\phi_{(0)}=\xi^i\partial_i\phi_{(0)},
\qquad
\delta A_{(0)i}=\mathcal L_\xi A_{(0)i}.
$$

Invariance gives the schematic identity

$$
\nabla_i\langle T^i_{\ j}\rangle
=
\langle\mathcal O\rangle\partial_j\phi_{(0)}
+
F_{(0)ji}\langle J^i\rangle
+
\cdots.
$$

The stress tensor is conserved only when external sources do not inject momentum.

### Weyl Ward identity

Under a boundary Weyl transformation,

$$
\delta g_{(0)ij}=2\sigma g_{(0)ij},
\qquad
\delta\phi_{(0)}=(\Delta-d)\sigma\phi_{(0)},
$$

one obtains

$$
\langle T^i_{\ i}\rangle
=
(d-\Delta)\phi_{(0)}\langle\mathcal O\rangle
+\mathcal A
+
\cdots.
$$

Here $\mathcal A$ is the conformal anomaly. In odd boundary dimensions and without anomaly-generating sources, $\mathcal A$ is often zero.

These Ward identities are among the best checks of a holographic computation. If your counterterms or normalizations are wrong, the Ward identities usually know before you do.

## A practical algorithm for vevs

For a classical solution, use the following workflow:

1. **Choose the sources.** Identify $g_{(0)ij}$, $\phi_{(0)}$, $A_{(0)i}$, and any other boundary data.
2. **Solve the bulk equations.** Impose the correct interior condition: regularity, incoming waves, horizon smoothness, or another state/ensemble condition.
3. **Expand near the boundary.** Determine the coefficients through the order that contributes to the desired vev.
4. **Write the regulated variation.** Compute the radial canonical momentum at $z=\epsilon$.
5. **Add counterterm variations.** Include $\Pi_{\rm ct}$, not only $S_{\rm ct}$.
6. **Convert to source variations.** Replace variations of cutoff fields by variations of finite sources.
7. **Take $\epsilon\to0$.** Extract the finite renormalized momentum.
8. **Apply the $W=-S_{\rm ren}$ sign.** Translate the bulk variation into the CFT one-point function.
9. **Check Ward identities.** Conservation, trace, and gauge identities are strong consistency tests.

This algorithm is more reliable than memorizing coefficient rules.

## Example: flat-boundary scalar with no source derivatives

Suppose the source is slowly varying or constant enough that derivative counterterms do not contribute, and ignore logarithmic cases. The scalar expansion is

$$
\phi(z,x)=z^{d-\Delta}\phi_{(0)}(x)+z^\Delta A(x)+\cdots.
$$

The renormalized variation has the finite form

$$
\delta S_{\text{ren,on-shell}}
=
-
\mathcal N_\phi(2\Delta-d)
\int d^d x\sqrt{g_{(0)}}\,A(x)\delta\phi_{(0)}(x)
+
\text{local source terms}.
$$

Therefore

$$
\langle\mathcal O(x)\rangle
=
\mathcal N_\phi(2\Delta-d)A(x)
+
\text{local source terms}.
$$

The sign in the first equation is compensated by $W=-S_{\rm ren}$.

## Example: black-brane stress tensor

For an asymptotically AdS black brane with flat boundary metric, the near-boundary metric contains a coefficient $g_{(d)ij}$ determined by the horizon scale. The holographic stress tensor is proportional to $g_{(d)ij}$:

$$
\langle T_{ij}\rangle
=
\frac{dL^{d-1}}{2\kappa_{d+1}^2}g_{(d)ij}
$$

up to signs and index placements fixed by the metric convention, and up to local terms that vanish for flat sources.

For a conformal plasma, the result must obey

$$
\langle T^i_{\ i}\rangle=0,
\qquad
\epsilon=(d-1)p,
$$

when no anomaly or deformation is present. This provides a quick check of the calculation.

## Example: chemical potential and charge density

For a finite-density state, the near-boundary Maxwell field is often written as

$$
A_t(z)=\mu-\rho z^{d-2}+\cdots.
$$

The source is $\mu$. The response is the electric flux. The current is not defined by the symbol $\rho$ alone; it is defined by

$$
\langle J^t\rangle
=
-
\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta S_{\rm ren}}{\delta A_{(0)t}}.
$$

For simple Maxwell normalizations and flat boundary sources, this is proportional to $\rho$. In complicated models with Chern–Simons terms, dilaton couplings, or finite counterterms, the flux formula must be modified accordingly.

## Dictionary checkpoint

The variational dictionary is:

| Source | Bulk field | Renormalized momentum | Boundary one-point function |
|---|---|---|---|
| scalar source $\phi_{(0)}$ | scalar $\phi$ | finite scalar radial momentum | $\langle\mathcal O\rangle$ |
| gauge field $A_{(0)i}$ | bulk gauge field $A_i$ | finite electric flux | $\langle J^i\rangle$ |
| metric $g_{(0)ij}$ | bulk metric $g_{MN}$ | renormalized Brown–York tensor | $\langle T^{ij}\rangle$ |

The most compact formula is

$$
\delta S_{\text{ren,on-shell}}
=
-
\delta W_{\rm CFT}
$$

in Euclidean signature with the source convention used here.

## Common confusions

### “The vev is always the coefficient of $z^\Delta$.”

Only after choosing standard quantization, fixing the normalization, adding counterterms, and accounting for local terms. The $z^\Delta$ coefficient is often the state-dependent part of the answer, but the actual definition is variational.

### “A nonzero normalizable mode always means spontaneous symmetry breaking.”

No. It means a nonzero expectation value for the dual operator, provided the source is zero in the chosen quantization. To call it spontaneous symmetry breaking, the operator must transform under a symmetry and the source must not explicitly break that symmetry.

### “The electric flux is automatically the charge density.”

It is the charge density after normalization and counterterm choices are accounted for. In the presence of Chern–Simons terms or higher-derivative interactions, the correct conserved current can differ from the naive Maxwell flux.

### “The stress tensor is just $g_{(d)ij}$.”

The coefficient $g_{(d)ij}$ is the nonlocal state-dependent part, but local curvature terms and anomaly terms can contribute. For flat boundary metrics these local terms often vanish, which is why the shortcut is so tempting.

### “Ward identities are extra assumptions.”

They are consequences of the invariance of $S_{\rm ren}$ under boundary gauge transformations, diffeomorphisms, and Weyl transformations. They are built into the bulk constraints.

## Exercises

### Exercise 1: Scalar momentum and the factor $2\Delta-d$

Assume

$$
\phi(z,x)=z^{d-\Delta}\phi_{(0)}(x)+z^\Delta A(x)+\cdots
$$

and ignore derivative counterterms. Explain why the finite vev is proportional to $(2\Delta-d)A$ rather than simply to $A$.

<details>
<summary><strong>Solution</strong></summary>

The two independent exponents are

$$
\Delta_-=d-\Delta,
\qquad
\Delta_+=\Delta.
$$

The radial canonical momentum involves a radial derivative, so it distinguishes the two powers. After subtracting the divergent source-branch contribution, the finite cross-term in the variation is proportional to the difference

$$
\Delta_+-\Delta_-=\Delta-(d-\Delta)=2\Delta-d.
$$

Thus, with action normalization $\mathcal N_\phi$,

$$
\langle\mathcal O\rangle
=
\mathcal N_\phi(2\Delta-d)A
+
\text{local source terms}
$$

in the Euclidean convention of this course.

</details>

### Exercise 2: Current conservation from gauge invariance

Let

$$
\delta W=\int d^d x\sqrt{g_{(0)}}\,\langle J^i\rangle\delta A_{(0)i}.
$$

Assume $W$ is invariant under $\delta A_{(0)i}=\nabla_i\alpha$ for arbitrary $\alpha(x)$. Derive $\nabla_i\langle J^i\rangle=0$.

<details>
<summary><strong>Solution</strong></summary>

Gauge invariance gives

$$
0=\delta W
=\int d^d x\sqrt{g_{(0)}}\,\langle J^i\rangle\nabla_i\alpha.
$$

Integrating by parts and ignoring boundary terms on the boundary spacetime,

$$
0=
-
\int d^d x\sqrt{g_{(0)}}\,\alpha\nabla_i\langle J^i\rangle.
$$

Since $\alpha(x)$ is arbitrary,

$$
\nabla_i\langle J^i\rangle=0.
$$

</details>

### Exercise 3: Trace Ward identity with a scalar source

Suppose a scalar source has dimension $d-\Delta$. Under an infinitesimal Weyl transformation with the source treated as a spurion,

$$
\delta g_{(0)ij}=2\sigma g_{(0)ij},
\qquad
\delta\phi_{(0)}=(\Delta-d)\sigma\phi_{(0)}.
$$

Using the variation of $W$, derive the trace identity without an anomaly.

<details>
<summary><strong>Solution</strong></summary>

The Weyl variation of $W$ is

$$
\delta W
=
\int d^d x\sqrt{g_{(0)}}
\left[
\frac12\langle T^{ij}\rangle(2\sigma g_{(0)ij})
+
\langle\mathcal O\rangle(\Delta-d)\sigma\phi_{(0)}
\right].
$$

Therefore

$$
\delta W
=
\int d^d x\sqrt{g_{(0)}}\,\sigma
\left[
\langle T^i_{\ i}\rangle
+(\Delta-d)\phi_{(0)}\langle\mathcal O\rangle
\right].
$$

With the variation convention above, Weyl invariance gives

$$
\langle T^i_{\ i}\rangle
=(d-\Delta)\phi_{(0)}\langle\mathcal O\rangle.
$$

The important point is that a dimensionful source explicitly breaks Weyl invariance and appears in the trace Ward identity. An anomaly term should be added when logarithmic counterterms are present.

</details>

### Exercise 4: Why finite counterterms affect one-point functions

Let

$$
S_{\rm finite}=c\int d^d x\sqrt{g_{(0)}}\,\phi_{(0)}^2.
$$

How does this change $\langle\mathcal O\rangle$ in the convention $W=-S_{\rm ren}$?

<details>
<summary><strong>Solution</strong></summary>

The finite counterterm changes the renormalized action by

$$
\Delta S_{\rm ren}=c\int d^d x\sqrt{g_{(0)}}\,\phi_{(0)}^2.
$$

Thus

$$
\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta \Delta S_{\rm ren}}{\delta\phi_{(0)}}
=2c\phi_{(0)}.
$$

Since $W=-S_{\rm ren}$,

$$
\Delta\langle\mathcal O\rangle
=-2c\phi_{(0)}.
$$

This is a local scheme-dependent shift. It changes contact terms and local one-point-function pieces, not the nonlocal part of correlators at separated points.

</details>

## Further reading

- S. de Haro, S. N. Solodukhin, and K. Skenderis, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- M. Bianchi, D. Z. Freedman, and K. Skenderis, [Holographic Renormalization](https://arxiv.org/abs/hep-th/0112119).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
- V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).
- I. Papadimitriou and K. Skenderis, [AdS/CFT Correspondence and Geometry](https://arxiv.org/abs/hep-th/0404176).
