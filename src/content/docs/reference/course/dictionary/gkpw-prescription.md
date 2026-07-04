---
title: "The GKP/Witten Prescription"
description: "How the AdS/CFT dictionary turns boundary sources into bulk boundary conditions, and CFT generating functionals into renormalized on-shell bulk actions."
sidebar:
  order: 20
---

The previous page stated AdS/CFT as an equality of quantum theories. This page turns that statement into the first working rule of the correspondence: the boundary generating functional of a CFT is computed by the bulk partition function with specified asymptotic boundary conditions.

In its most compact Euclidean form, the Gubser–Klebanov–Polyakov/Witten prescription is

$$
Z_{\text{CFT}}[\text{sources}]
=
Z_{\text{bulk}}[\text{asymptotic boundary data}].
$$

For a scalar operator $\mathcal O$ sourced by $\phi_{(0)}$, this becomes

$$
Z_{\text{CFT}}[\phi_{(0)}]
=
Z_{\text{bulk}}\!\left[\phi(z,x)\sim z^{d-\Delta}\phi_{(0)}(x)\right].
$$

In the classical gravity limit,

$$
Z_{\text{bulk}}\!\left[\phi_{(0)}\right]
\approx
\exp\!\left(-S_{\text{ren,on-shell}}[\phi_{(0)}]\right),
$$

so that

$$
W_{\text{CFT}}[\phi_{(0)}]
\equiv
\log Z_{\text{CFT}}[\phi_{(0)}]
\approx
-S_{\text{ren,on-shell}}[\phi_{(0)}].
$$

This is the formula that makes AdS/CFT computational. A strongly coupled, large-$N$ CFT generating functional is replaced by a classical boundary-value problem in one higher dimension.

<figure class="doc-figure" style="--figure-width: 58rem;">

![The GKP/Witten prescription: a CFT source fixes the asymptotic boundary value of a bulk field; the regular bulk solution determines the renormalized on-shell action; functional derivatives give CFT correlators.](/figures/course/gkpw-prescription.svg)

<figcaption>

The GKP/Witten prescription. A boundary source $\phi_{(0)}$ is imposed as the leading asymptotic behavior of a bulk field $\phi$. Solving the bulk equations with the appropriate interior condition gives a renormalized on-shell action $S_{\text{ren,on-shell}}[\phi_{(0)}]$. Functional derivatives of this action compute CFT one-point functions and connected correlators.

</figcaption>
</figure>

## Why this matters

In ordinary QFT, the generating functional is the machine that produces correlation functions. If a source $J(x)$ couples to an operator $\mathcal O(x)$, then

$$
Z_{\text{QFT}}[J]
=
\left\langle
\exp\!\left(
\int d^d x\, J(x)\mathcal O(x)
\right)
\right\rangle,
\qquad
W[J]=\log Z[J].
$$

Connected correlators are obtained by differentiating $W[J]$:

$$
\left\langle \mathcal O(x_1)\cdots \mathcal O(x_n)\right\rangle_c
=
\frac{\delta^n W[J]}{\delta J(x_1)\cdots \delta J(x_n)}
\bigg|_{J=0}.
$$

The hard part is computing $W[J]$ at strong coupling. The GKP/Witten prescription says that, in a holographic large-$N$ CFT, this hard field-theory object can be computed from a bulk action evaluated on a solution of classical equations of motion.

This is not merely an analogy. The boundary source is not represented by an arbitrary bulk insertion. It is represented by a boundary condition.

That is the first operational lesson of AdS/CFT:

$$
\boxed{
\text{CFT source}
\quad \longleftrightarrow \quad
\text{leading asymptotic boundary value of a bulk field}
}
$$

and

$$
\boxed{
\text{CFT generating functional}
\quad \longleftrightarrow \quad
\text{bulk partition function with that boundary condition}.
}
$$

The rest of the dictionary is built by taking this statement seriously.

## The QFT side: sources define observables

Let $M_d$ be the boundary spacetime and let $g_{(0)ij}$ be its metric representative. Suppose a scalar primary operator $\mathcal O$ has scaling dimension $\Delta$. A source $\phi_{(0)}$ for $\mathcal O$ has dimension

$$
[\phi_{(0)}]=d-\Delta,
$$

because the source term must be dimensionless:

$$
\int_{M_d} d^d x\sqrt{|g_{(0)}|}\,\phi_{(0)}(x)\mathcal O(x).
$$

With the Euclidean convention used in this course,

$$
Z_{\text{CFT}}[\phi_{(0)}]
=
\left\langle
\exp\!\left(
\int d^d x\sqrt{g_{(0)}}\,\phi_{(0)}(x)\mathcal O(x)
\right)
\right\rangle.
$$

Equivalently, the source appears in the Euclidean action as

$$
S_E
\to
S_E-\int d^d x\sqrt{g_{(0)}}\,\phi_{(0)}\mathcal O.
$$

Then

$$
\langle \mathcal O(x)\rangle_{\phi_{(0)}}
=
\frac{1}{\sqrt{g_{(0)}(x)}}
\frac{\delta W_{\text{CFT}}}{\delta \phi_{(0)}(x)}.
$$

This sign convention will be important below. Some books put the source in the Euclidean action with the opposite sign. That changes the sign of formulas for one-point functions, but it does not change the physics once the convention is used consistently.

The metric itself is also a source. Varying $g_{(0)ij}$ gives the stress tensor:

$$
\langle T^{ij}(x)\rangle
=
\frac{2}{\sqrt{g_{(0)}}}
\frac{\delta W_{\text{CFT}}}{\delta g_{(0)ij}(x)},
$$

up to the sign convention for Euclidean metric variation. Similarly, background gauge fields source conserved currents, spinor sources source fermionic operators, and higher-spin or Kaluza–Klein boundary data source the corresponding single-trace operators.

## The bulk side: sources are boundary conditions

Work first in Euclidean Poincaré AdS$_{d+1}$,

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+\delta_{ij}dx^i dx^j\right),
\qquad
z>0,
$$

with the conformal boundary at $z=0$. Let $\phi$ be a bulk scalar of mass $m$. Near the boundary, solutions of the scalar equation have the asymptotic form

$$
\phi(z,x)
\sim
z^{d-\Delta}\left(\phi_{(0)}(x)+\cdots\right)
+
z^\Delta\left(A(x)+\cdots\right),
$$

where

$$
m^2L^2=\Delta(\Delta-d).
$$

In standard quantization, $\phi_{(0)}(x)$ is the CFT source. The coefficient $A(x)$ is related to the expectation value $\langle \mathcal O(x)\rangle$, after holographic renormalization.

The notation hides a few subtleties:

- the dots include terms determined locally by $\phi_{(0)}$ and the boundary metric;
- when $2\Delta-d$ is an integer, logarithmic terms may appear;
- the coefficient $A(x)$ is not always equal to the renormalized one-point function by itself;
- if the mass lies in the alternate-quantization window, the source/response interpretation can be changed.

For the moment, keep the standard case in mind: the leading non-normalizable coefficient is the source, and the subleading normalizable coefficient is the response.

## The prescription as a path integral equality

The exact bulk object is not a classical action but a partition function. Schematically,

$$
Z_{\text{bulk}}[\phi_{(0)}]
=
\int_{\phi \sim z^{d-\Delta}\phi_{(0)}}
\mathcal D\phi\,\mathcal Dg\,\mathcal D(\text{other fields})
\,\exp(-S_{\text{bulk}}).
$$

The GKP/Witten prescription says

$$
Z_{\text{CFT}}[\phi_{(0)}]
=
Z_{\text{bulk}}[\phi_{(0)}].
$$

This is the clean conceptual statement. The classical formula follows when the bulk path integral is dominated by a saddle:

$$
Z_{\text{bulk}}[\phi_{(0)}]
\approx
\exp\!\left(-S_{\text{ren,on-shell}}[\phi_{(0)}]\right).
$$

Thus

$$
W_{\text{CFT}}[\phi_{(0)}]
\approx
-S_{\text{ren,on-shell}}[\phi_{(0)}].
$$

At this leading order, CFT correlators are obtained by differentiating the renormalized on-shell action:

$$
\langle \mathcal O(x)\rangle_{\phi_{(0)}}
=
-\frac{1}{\sqrt{g_{(0)}(x)}}
\frac{\delta S_{\text{ren,on-shell}}}{\delta \phi_{(0)}(x)}.
$$

The minus sign follows from $W_{\text{CFT}}=-S_{\text{ren,on-shell}}$ and from the source convention above. If one defines the source deformation with the opposite sign, this formula changes sign.

Connected two-point functions are then

$$
\langle \mathcal O(x)\mathcal O(y)\rangle_c
=
-\frac{1}{\sqrt{g_{(0)}(x)}\sqrt{g_{(0)}(y)}}
\frac{\delta^2 S_{\text{ren,on-shell}}}
{\delta \phi_{(0)}(x)\delta \phi_{(0)}(y)}
\bigg|_{\phi_{(0)}=0}.
$$

Higher connected correlators are obtained by higher functional derivatives. In a large-$N$ theory with a classical bulk, the tree-level bulk action computes leading connected correlators; bulk loops give $1/N$ corrections.

## The classical algorithm

For a single scalar source, the practical calculation proceeds as follows.

### Step 1: Choose the boundary source

Specify $\phi_{(0)}(x)$ and the boundary metric $g_{(0)ij}$. In Poincaré AdS, one often chooses $g_{(0)ij}=\delta_{ij}$ or $\eta_{ij}$.

### Step 2: Solve the bulk equation

Solve

$$
(\nabla^2-m^2)\phi=0
$$

with the near-boundary condition

$$
\phi(z,x)
=
z^{d-\Delta}\phi_{(0)}(x)+\cdots.
$$

This boundary condition alone does not always determine the solution. One also needs an interior condition. In Euclidean AdS, the standard condition is regularity in the interior. In Lorentzian black-hole backgrounds, retarded correlators require incoming-wave boundary conditions at the horizon.

### Step 3: Evaluate the on-shell action

Insert the solution back into the bulk action. For a free scalar, the bulk term reduces on shell to a boundary term. For interacting fields, the on-shell action includes Witten diagrams built from bulk propagators and interaction vertices.

At this stage the result is usually divergent because the AdS boundary is at infinite proper distance.

### Step 4: Regulate and renormalize

Introduce a cutoff surface $z=\epsilon$ and define

$$
S_{\epsilon}
=
S_{\text{bulk}}^{z\ge \epsilon}+S_{\text{boundary}}^{z=\epsilon}.
$$

Then add local counterterms on the cutoff surface:

$$
S_{\text{ren}}
=
\lim_{\epsilon\to0}
\left(
S_{\epsilon}+S_{\text{ct},\epsilon}
\right).
$$

The counterterms are local functionals of the induced fields at $z=\epsilon$. They remove divergences but may leave finite scheme-dependent contact terms. Nonlocal terms are the physical correlators at separated points.

### Step 5: Differentiate

Use

$$
W_{\text{CFT}}[\phi_{(0)}]
=
-S_{\text{ren,on-shell}}[\phi_{(0)}]
$$

to obtain one-point functions and connected correlators.

The next page performs this procedure explicitly for a scalar two-point function.

## Boundary conditions, states, and saddles

The GKP/Witten formula has two kinds of data that students often mix up.

The first kind is source data. These are fixed at the AdS boundary: $\phi_{(0)}$, $g_{(0)ij}$, background gauge fields, and so on. They define the QFT problem.

The second kind is state or contour data. These choose which state, ensemble, or real-time Green's function one computes. Examples include:

- regularity in Euclidean AdS for the vacuum correlator;
- smoothness of the Euclidean black-hole cigar for a thermal partition function;
- incoming-wave horizon conditions for retarded Lorentzian correlators;
- a Schwinger–Keldysh contour for real-time expectation values;
- normalizable modes specifying excited states.

The source is not the state. The same source can be studied in different states. Conversely, different sources can be applied to the same state.

## The metric/source dictionary

The scalar example generalizes to all bulk fields. The most important entries are:

| Bulk boundary data | Boundary interpretation |
|---|---|
| scalar leading coefficient $\phi_{(0)}$ | source for scalar operator $\mathcal O$ |
| boundary metric $g_{(0)ij}$ | source for stress tensor $T^{ij}$ |
| boundary gauge field $A_{(0)i}$ | source for conserved current $J^i$ |
| boundary value of a spinor component | source for a fermionic operator |
| boundary values of higher Kaluza–Klein fields | sources for single-trace operators |

The corresponding one-point functions are obtained by varying the renormalized on-shell action:

$$
\langle \mathcal O_I(x)\rangle
=
-\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta S_{\text{ren}}}{\delta J_I(x)},
$$

with sign changes depending on the source convention and on whether the field is bosonic, fermionic, Euclidean, or Lorentzian.

For the stress tensor, a common convention is

$$
\langle T^{ij}\rangle
=
\frac{2}{\sqrt{g_{(0)}}}
\frac{\delta S_{\text{ren}}}{\delta g_{(0)ij}},
$$

again with Euclidean sign conventions to be tracked carefully. In later pages we will connect this formula to the Brown–York stress tensor plus counterterms.

## What is actually classical?

The classical on-shell action is not the exact bulk answer. It is the leading term in a semiclassical expansion.

For a bulk effective action of the form

$$
S_{\text{bulk}}
\sim
\frac{L^{d-1}}{G_{d+1}}
\int d^{d+1}x\sqrt{g}\,\mathcal L,
$$

the prefactor scales like the number of boundary degrees of freedom. In AdS$_5$/CFT$_4$,

$$
\frac{L^3}{G_5}
\sim
N^2.
$$

Therefore the classical on-shell action is of order $N^2$ for stress-tensor-sector quantities. Bulk loops are suppressed by powers of $G_{d+1}/L^{d-1}$, which are boundary $1/N$ corrections.

Stringy corrections are separate. They are controlled by the ratio $\alpha'/L^2$. In the canonical AdS$_5$/CFT$_4$ example,

$$
\frac{\alpha'}{L^2}
=
\frac{1}{\sqrt{\lambda}}.
$$

Thus the classical two-derivative supergravity prescription is reliable only when the theory has both large $N$ and a large stringy gap. The exact GKP/Witten statement is broader than this approximation.

## Contact terms and scheme dependence

Functional derivatives of a local counterterm produce contact terms. For example, a counterterm of the schematic form

$$
S_{\text{ct}}
\supset
\int d^d x\sqrt{\gamma}\,\phi^2
$$

contributes to the two-point function only at coincident points. In momentum space, these are polynomial terms in $k^2$. In position space, they are derivatives of delta functions.

This is why many holographic correlator formulas are stated “up to contact terms.” The separated-point power law is universal; local contact terms depend on the renormalization scheme and on the choice of finite counterterms.

The distinction is not optional. If one compares holographic correlators to CFT Ward identities, anomalies, or stress-tensor one-point functions, contact terms must be handled carefully.

## A minimal derivation of the one-point formula

Suppose $\phi_{\text{cl}}[\phi_{(0)}]$ is the classical solution satisfying the boundary condition. The renormalized on-shell action is a functional of the source:

$$
S_{\text{ren,on-shell}}[\phi_{(0)}]
=
S_{\text{ren}}[\phi_{\text{cl}}[\phi_{(0)}]].
$$

Varying it gives only boundary terms, because the bulk equations of motion hold:

$$
\delta S_{\text{ren,on-shell}}
=
\int d^d x\sqrt{g_{(0)}}\,\Pi_{\text{ren}}(x)\,\delta \phi_{(0)}(x).
$$

The renormalized canonical momentum $\Pi_{\text{ren}}$ is the finite coefficient obtained after adding counterterms and removing the cutoff.

Using $W_{\text{CFT}}=-S_{\text{ren,on-shell}}$, we find

$$
\langle \mathcal O(x)\rangle
=
-\Pi_{\text{ren}}(x).
$$

In many standard scalar examples,

$$
\Pi_{\text{ren}}(x)
=-(2\Delta-d)\mathcal N A(x)+\text{local terms},
$$

so that

$$
\langle \mathcal O(x)\rangle
=
(2\Delta-d)\mathcal N A(x)+\text{local terms}.
$$

Here $\mathcal N$ is the overall normalization of the scalar action. This formula is a useful memory aid, but the safe procedure is always to vary the renormalized action.

## Lorentzian warning

The Euclidean prescription computes Euclidean correlators. Lorentzian correlators require more information.

In Lorentzian signature, one must specify a real-time contour and interior boundary conditions. For example, in a black-brane background, the retarded Green's function is computed by imposing incoming-wave boundary conditions at the horizon. Advanced, Feynman, and Schwinger–Keldysh correlators use different prescriptions.

This is not a minor technicality. The same differential equation and the same near-boundary source can lead to different Lorentzian Green's functions depending on the interior condition.

For now, the main lesson is simple:

$$
\text{Euclidean regularity}
\neq
\text{Lorentzian retarded condition},
$$

although analytic continuation often connects the two when no singularities are crossed.

## Dictionary checkpoint

The GKP/Witten prescription gives the first complete computational dictionary:

| CFT quantity | Bulk quantity |
|---|---|
| source $J(x)$ for $\mathcal O$ | leading asymptotic boundary coefficient of $\phi$ |
| $Z_{\text{CFT}}[J]$ | bulk partition function with boundary condition $J$ |
| $W_{\text{CFT}}[J]$ | $-S_{\text{ren,on-shell}}[J]$ at leading classical order |
| $\langle \mathcal O\rangle_J$ | renormalized radial canonical momentum of $\phi$ |
| connected $n$-point functions | $n$ functional derivatives of $-S_{\text{ren,on-shell}}$ |
| large-$N$ factorization | tree-level bulk saddle expansion |
| CFT UV divergences | bulk IR divergences near the AdS boundary |

The slogan “boundary value equals source” is only the first line. The complete prescription is a regulated variational principle.

## Common confusions

### “The source is the whole boundary value of the field.”

Near the boundary, a bulk field has an asymptotic expansion. In standard quantization, the source is the coefficient of the leading non-normalizable falloff, not the entire function $\phi(z,x)$ evaluated at some small cutoff.

At finite cutoff, the induced value $\phi(\epsilon,x)$ contains both source and response data. Holographic renormalization is the procedure that extracts the correct finite source-response relation.

### “The on-shell action is finite once we solve the equations.”

Usually not. The on-shell action diverges as the cutoff surface approaches the boundary. The renormalized on-shell action is obtained only after adding local counterterms and taking the cutoff to zero.

### “Normalizable modes are always vevs.”

Normalizable modes are related to state-dependent data, but the precise vev is the variation of the renormalized action. Local terms, anomalies, operator mixing, and alternate quantization can modify the naive relation.

### “Euclidean and Lorentzian prescriptions are the same.”

They are related but not identical. Euclidean regularity is a boundary condition in a smooth Euclidean geometry. Lorentzian real-time correlators require time contours and causal boundary conditions.

### “The GKP/Witten formula proves every bottom-up gravity model has a CFT dual.”

No. The formula is part of a consistent string-theory/QFT duality or a controlled effective limit of one. A bottom-up model can be useful, but writing down a bulk action does not automatically guarantee the existence of a healthy boundary CFT.

## Exercises

### Exercise 1: Sign of the one-point function

Use the convention

$$
Z_{\text{CFT}}[J]
=
\left\langle \exp\!\left(\int J\mathcal O\right)\right\rangle,
\qquad
Z_{\text{CFT}}[J]
\approx
\exp(-S_{\text{ren}}[J]).
$$

Show that

$$
\langle \mathcal O(x)\rangle_J
=
-\frac{\delta S_{\text{ren}}}{\delta J(x)}.
$$

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
W[J]=\log Z_{\text{CFT}}[J].
$$

The source convention gives

$$
\langle \mathcal O(x)\rangle_J
=
\frac{\delta W[J]}{\delta J(x)}.
$$

The classical holographic relation gives

$$
W[J]\approx -S_{\text{ren}}[J].
$$

Therefore

$$
\langle \mathcal O(x)\rangle_J
=
-\frac{\delta S_{\text{ren}}}{\delta J(x)}.
$$

If the source is instead introduced as $S_E\to S_E+\int J\mathcal O$, then the definition of the QFT generating functional changes and the sign changes.

</details>

### Exercise 2: On-shell scalar action as a boundary term

Consider a Euclidean scalar action

$$
S
=
\frac12\int d^{d+1}X\sqrt{g}
\left(g^{MN}\partial_M\phi\partial_N\phi+m^2\phi^2\right).
$$

Show that on solutions of $(\nabla^2-m^2)\phi=0$, the action reduces to a boundary term.

<details>
<summary><strong>Solution</strong></summary>

Integrate the kinetic term by parts:

$$
\int \sqrt{g}\,g^{MN}\partial_M\phi\partial_N\phi
=
-\int \sqrt{g}\,\phi\nabla^2\phi
+
\int_{\partial M}\sqrt{\gamma}\,\phi n^M\partial_M\phi.
$$

Thus

$$
S
=
\frac12\int \sqrt{g}\,\phi(-\nabla^2+m^2)\phi
+
\frac12\int_{\partial M}\sqrt{\gamma}\,\phi n^M\partial_M\phi.
$$

The bulk term vanishes on the equation of motion, so

$$
S_{\text{on-shell}}
=
\frac12\int_{\partial M}\sqrt{\gamma}\,\phi n^M\partial_M\phi.
$$

For AdS with a cutoff surface $z=\epsilon$, this boundary term is divergent and must be renormalized.

</details>

### Exercise 3: Why counterterms produce contact terms

Suppose the renormalized action is changed by a finite local counterterm

$$
S_{\text{ren}}
\to
S_{\text{ren}}+\frac{a}{2}\int d^d x\, J(x)^2.
$$

What is the resulting change in the two-point function?

<details>
<summary><strong>Solution</strong></summary>

Using

$$
\langle \mathcal O(x)\mathcal O(y)\rangle_c
=
-\frac{\delta^2 S_{\text{ren}}}{\delta J(x)\delta J(y)},
$$

the finite counterterm changes the correlator by

$$
\delta\langle \mathcal O(x)\mathcal O(y)\rangle_c
=
-a\,\delta^{(d)}(x-y).
$$

This is a contact term. It affects coincident-point correlators and polynomial terms in momentum space, but not the separated-point power law.

</details>

### Exercise 4: Source dimension

A scalar primary operator has dimension $\Delta$ in a $d$-dimensional CFT. Show that its source has dimension $d-\Delta$.

<details>
<summary><strong>Solution</strong></summary>

The source deformation is

$$
\int d^d x\, J(x)\mathcal O(x).
$$

The measure has dimension $-d$, while $\mathcal O$ has dimension $\Delta$. For the integral to be dimensionless,

$$
[J]+\Delta-d=0.
$$

Therefore

$$
[J]=d-\Delta.
$$

This matches the near-boundary behavior of the dual bulk field: in standard quantization the source multiplies $z^{d-\Delta}$.

</details>

## Further reading

- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- S. de Haro, K. Skenderis, and S. N. Solodukhin, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
