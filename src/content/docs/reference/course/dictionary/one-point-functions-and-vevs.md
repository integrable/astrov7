---
title: "One-Point Functions and VEVs"
description: "How holographic renormalization turns the normalizable part of a bulk field into a boundary expectation value."
sidebar:
  order: 60
---

The previous pages established the source side of the scalar dictionary. A bulk scalar of mass $m$ has two independent near-boundary behaviors,

$$
\phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)
+
z^\Delta A(x),
\qquad
m^2L^2=\Delta(\Delta-d),
$$

and in standard quantization the leading coefficient $\phi_{(0)}$ is the source for a boundary operator $\mathcal O$.

This page explains the response side of the same statement. The coefficient $A(x)$ is not just a decorative subleading term. After the correct counterterms are added, it determines the expectation value $\langle \mathcal O(x)\rangle$. The precise rule is not “read off the subleading coefficient by eye.” The precise rule is:

$$
\boxed{
\langle \mathcal O(x)\rangle_{\phi_{(0)}}
=
-\frac{1}{\sqrt{g_{(0)}(x)}}
\frac{\delta S_{\text{ren,on-shell}}}{\delta \phi_{(0)}(x)}
}
$$

with the Euclidean source convention used in this course. The minus sign follows from

$$
W_{\rm CFT}[\phi_{(0)}]
=
\log Z_{\rm CFT}[\phi_{(0)}]
\approx
-S_{\text{ren,on-shell}}[\phi_{(0)}].
$$

The short slogan is useful:

$$
\text{source}
\quad\longleftrightarrow\quad
\text{leading asymptotic coefficient},
$$

$$
\text{expectation value}
\quad\longleftrightarrow\quad
\text{renormalized radial canonical momentum}.
$$

The radial canonical momentum is the safer concept. The subleading coefficient $A(x)$ is often proportional to it, but local terms, logarithms, anomalies, and scheme choices can modify the naive relation.

<figure class="doc-figure" style="--figure-width: 56rem;">

![A boundary source fixes the leading mode of a bulk field. The regular bulk solution has a subleading response. After counterterms are added, varying the renormalized on-shell action gives the one-point function.](/figures/course/one-point-functions-and-vevs.svg)

<figcaption>

The one-point-function workflow. The source $\phi_{(0)}$ fixes the leading near-boundary behavior of a bulk field. The bulk equations plus an interior condition determine the response coefficient $A$. The finite, renormalized variation of the on-shell action gives $\langle\mathcal O\rangle$. The response is therefore a variational object, not merely a raw coefficient in the cutoff expansion.

</figcaption>
</figure>

## Why this matters

Correlation functions are obtained by differentiating the generating functional. But the first derivative is already extremely important. It tells us the expectation value of an operator in the state or ensemble being described.

In holography, one-point functions answer questions such as:

- What is the energy density of a black brane?
- What charge density is produced by a bulk electric field?
- Which scalar condensate is present in a deformed or symmetry-breaking state?
- Which Ward identities does the bulk solution obey?
- Which boundary state corresponds to a particular normalizable bulk deformation?

A two-point function tells us about linear response. A one-point function tells us what background we are responding around.

This is especially important because the same source can produce different expectation values in different states. The boundary condition at the AdS boundary specifies the QFT source. The interior condition specifies the state, saddle, ensemble, or real-time prescription. The vev is the response of that chosen state to the chosen source.

## The QFT definition

Let $M_d$ be the boundary spacetime with metric representative $g_{(0)ij}$. Suppose a source $J(x)$ couples to an operator $\mathcal O(x)$ through the Euclidean convention

$$
S_E
\to
S_E-
\int_{M_d} d^d x\sqrt{g_{(0)}}\,J(x)\mathcal O(x).
$$

Then

$$
Z_{\rm CFT}[J]
=
\left\langle
\exp\!\left(
\int d^d x\sqrt{g_{(0)}}\,J\mathcal O
\right)
\right\rangle,
\qquad
W_{\rm CFT}[J]=\log Z_{\rm CFT}[J].
$$

The one-point function in the presence of the source is

$$
\langle \mathcal O(x)\rangle_J
=
\frac{1}{\sqrt{g_{(0)}(x)}}
\frac{\delta W_{\rm CFT}}{\delta J(x)}.
$$

For the metric source,

$$
\langle T^{ij}(x)\rangle
=
\frac{2}{\sqrt{g_{(0)}(x)}}
\frac{\delta W_{\rm CFT}}{\delta g_{(0)ij}(x)},
$$

up to the usual Euclidean sign convention. For a background gauge field $A_{(0)i}$ coupled as

$$
\int d^d x\sqrt{g_{(0)}}\,A_{(0)i}J^i,
$$

the current is

$$
\langle J^i(x)\rangle
=
\frac{1}{\sqrt{g_{(0)}(x)}}
\frac{\delta W_{\rm CFT}}{\delta A_{(0)i}(x)}.
$$

These are field-theory definitions. Holography gives a way to compute the same derivatives from the bulk.

## The bulk variational principle

Consider a scalar field in Euclidean asymptotically AdS$_{d+1}$ with action

$$
S_\phi
=
\frac{\mathcal N}{2}
\int d^{d+1}x\sqrt{g}\,
\left(g^{MN}\partial_M\phi\partial_N\phi+m^2\phi^2\right),
$$

where $\mathcal N$ is an overall normalization. For a canonically normalized supergravity field, $\mathcal N$ typically contains a factor such as $L^{d-1}/G_{d+1}$ and therefore scales like a power of $N$.

Varying the action gives

$$
\delta S_\phi
=
\mathcal N
\int d^{d+1}x\sqrt{g}\,
(-\nabla^2\phi+m^2\phi)\delta\phi
+
\mathcal N
\int_{z=\epsilon} d^d x\sqrt{\gamma}\,n^M\partial_M\phi\,\delta\phi.
$$

Here $\gamma_{ij}$ is the induced metric on the cutoff surface $z=\epsilon$, and $n^M$ is the outward-pointing unit normal. On shell, the bulk term vanishes. The variation is a boundary term:

$$
\delta S_{\text{reg,on-shell}}
=
\int_{z=\epsilon} d^d x\sqrt{\gamma}\,\Pi_\epsilon\,\delta\phi_\epsilon,
$$

where

$$
\Pi_\epsilon
=
\mathcal N n^M\partial_M\phi
$$

is the regulated radial canonical momentum. This object diverges as $\epsilon\to0$. The divergence is expected: the boundary is at infinite proper distance, and the dual QFT has UV divergences.

The renormalized action is

$$
S_{\rm ren}
=
\lim_{\epsilon\to0}
\left(
S_{\rm reg}^{z\ge\epsilon}
+
S_{{\rm ct},\epsilon}
\right),
$$

where $S_{{\rm ct},\epsilon}$ is a local functional on the cutoff surface. After counterterms are included, the finite variation has the form

$$
\delta S_{\text{ren,on-shell}}
=
\int d^d x\sqrt{g_{(0)}}\,\Pi_{\rm ren}(x)\,\delta\phi_{(0)}(x).
$$

Using $W_{\rm CFT}=-S_{\text{ren,on-shell}}$ gives

$$
\boxed{
\langle \mathcal O(x)\rangle
=
-\Pi_{\rm ren}(x)
}
$$

with the source convention above.

Many authors absorb this sign by defining the source deformation with the opposite sign or by writing the Euclidean generating functional differently. The invariant statement is: the one-point function is the renormalized canonical momentum conjugate to the source, with the sign fixed by the chosen QFT convention.

## Reading the scalar vev from the near-boundary expansion

In Poincaré coordinates,

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+g_{(0)ij}dx^i dx^j+\cdots\right),
\qquad
z\to0,
$$

a scalar solution has the schematic expansion

$$
\phi(z,x)
=
z^{d-\Delta}
\left(
\phi_{(0)}(x)+z^2\phi_{(2)}(x)+\cdots
\right)
+
z^\Delta
\left(
\phi_{(2\Delta-d)}(x)+\cdots
\right).
$$

The notation $\phi_{(2\Delta-d)}$ is conventional: it labels the coefficient by its relative power compared with the source branch. In simple non-resonant cases, the coefficients $\phi_{(2)}$, $\phi_{(4)}$, and so on are determined locally by the source and the boundary metric. The coefficient $\phi_{(2\Delta-d)}$ is the first genuinely response-like datum.

If there are no logarithmic terms and no subtle mixing with other fields, the scalar one-point function takes the form

$$
\boxed{
\langle \mathcal O(x)\rangle
=
(2\Delta-d)\mathcal N\,\phi_{(2\Delta-d)}(x)
+
\text{local terms in sources}.
}
$$

The local terms are fixed by counterterms and finite scheme choices. They matter for Ward identities and contact terms. At separated points, the nonlocal dependence of $\phi_{(2\Delta-d)}$ on $\phi_{(0)}$ is the physical part that gives ordinary correlators.

A useful special case is a flat boundary, no source derivatives, no logarithmic terms, and vanishing source. Then the local terms often vanish, and one can simply say

$$
\langle \mathcal O\rangle
\propto
\phi_{(2\Delta-d)}.
$$

But this is a special simplification, not the definition.

## Source, response, and state

The source and the vev play different roles.

A source deforms the QFT action or background:

$$
S_{\rm CFT}
\to
S_{\rm CFT}-\int \phi_{(0)}\mathcal O.
$$

A vev is an expectation value in a chosen state or ensemble:

$$
\langle\mathcal O\rangle
=
\langle\Psi|\mathcal O|\Psi\rangle
\quad
\text{or}
\quad
\langle\mathcal O\rangle_\rho
=
{\rm Tr}(\rho\mathcal O).
$$

In the bulk, the source is fixed at the conformal boundary. The state is encoded by normalizable data and by the interior condition. For example:

| Boundary situation | Bulk description |
|---|---|
| vacuum CFT on flat space | pure Poincaré AdS with regular Euclidean continuation |
| CFT on $\mathbb R\times S^{d-1}$ in the vacuum | global AdS with appropriate regularity |
| thermal state | Euclidean black-hole saddle or Lorentzian black brane |
| finite charge density | bulk gauge field with electric flux |
| scalar condensate | normalizable scalar response, possibly with vanishing source |

This distinction prevents a common mistake. A normalizable mode is not automatically a source. It can describe a state-dependent expectation value. Conversely, a source is not automatically a vev. It is a deformation or background field.

## A simple scalar example

Suppose $\phi_{(0)}=0$ and the scalar expansion is

$$
\phi(z,x)=z^\Delta A(x)+\cdots.
$$

If standard quantization is used and no local source terms contribute, then

$$
\langle\mathcal O(x)\rangle
=(2\Delta-d)\mathcal N A(x).
$$

This is how spontaneous or state-induced expectation values appear in many holographic solutions. A bulk field can be normalizable at the boundary while still being nonzero in the interior. In the boundary theory this corresponds to a state with a nonzero operator expectation value but no explicit source for that operator.

However, the phrase “spontaneous” requires care. To claim spontaneous symmetry breaking, the operator must be charged under a symmetry, the source for the charged operator must be set to zero, and the solution must choose a nonzero vev. Merely finding a subleading scalar coefficient is not enough.

## Current expectation values

For a bulk Maxwell field,

$$
S_A
=
\frac{1}{4g_{d+1}^2}
\int d^{d+1}x\sqrt{g}\,F_{MN}F^{MN},
$$

the boundary value $A_{(0)i}$ sources a conserved current $J^i$:

$$
\int d^d x\sqrt{g_{(0)}}\,A_{(0)i}J^i.
$$

In radial gauge $A_z=0$, a massless gauge field often has the near-boundary expansion

$$
A_i(z,x)
=
A_{(0)i}(x)
+
\cdots
+
z^{d-2}A_{(d-2)i}(x)
+
\cdots,
$$

with possible logarithms in special dimensions. The current expectation value is obtained from the renormalized electric flux:

$$
\langle J^i(x)\rangle
=
\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta W}{\delta A_{(0)i}(x)}
=
-\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta S_{\rm ren}}{\delta A_{(0)i}(x)}.
$$

For a static finite-density solution, one often writes near the boundary

$$
A_t(z)=\mu-\rho z^{d-2}+\cdots.
$$

Then $\mu$ is the chemical potential and $\rho$ is proportional to the charge density $\langle J^t\rangle$, with the proportionality fixed by the Maxwell normalization and by counterterms.

The phrase “proportional to” is doing real work. If the action normalization changes, the numerical value of $\langle J^t\rangle$ changes. The boundary current normalization is part of the dictionary.

## The stress tensor as a one-point function

The boundary metric $g_{(0)ij}$ sources the stress tensor. The holographic stress tensor is therefore

$$
\boxed{
\langle T^{ij}\rangle
=
\frac{2}{\sqrt{g_{(0)}}}
\frac{\delta W}{\delta g_{(0)ij}}
=
-\frac{2}{\sqrt{g_{(0)}}}
\frac{\delta S_{\rm ren}}{\delta g_{(0)ij}}
}
$$

with our Euclidean convention. Many gravity references instead define a Brown–York tensor directly from $S_{\rm ren}$ with a sign chosen for Lorentzian signature. The next dedicated stress-tensor page will fix these conventions carefully.

The important conceptual point is simple:

$$
\text{normalizable metric coefficient}
\quad\longleftrightarrow\quad
\langle T_{ij}\rangle.
$$

For a planar AdS black brane, the normalizable part of the metric gives the thermal energy density and pressure of the boundary CFT. For global AdS, the holographic stress tensor gives the vacuum energy on $\mathbb R\times S^{d-1}$, including the Casimir-energy contribution in even boundary dimensions.

## Local terms, anomalies, and scheme dependence

A counterterm is local in the sources. For a scalar, examples include terms such as

$$
S_{\rm ct}
\supset
\int_{z=\epsilon} d^d x\sqrt{\gamma}\,
\phi^2,
\qquad
S_{\rm ct}
\supset
\int_{z=\epsilon} d^d x\sqrt{\gamma}\,\gamma^{ij}\partial_i\phi\partial_j\phi.
$$

When varied, these counterterms contribute local functions of the source to $\langle\mathcal O\rangle$. Finite local counterterms change these local terms without changing nonlocal separated-point correlators.

This is the holographic version of renormalization-scheme dependence. It is not a flaw. It is the same ambiguity present in ordinary QFT when one defines composite operators in the presence of background sources.

Logarithmic terms are especially important. When the near-boundary expansion contains

$$
z^\Delta\log z\,\widetilde\phi_{(2\Delta-d)}(x),
$$

the renormalized action depends on a scale, and Weyl transformations can produce anomalies. In the stress-tensor sector, this is the holographic Weyl anomaly.

Thus the full response is better written as

$$
\langle\mathcal O\rangle
=
(2\Delta-d)\mathcal N\phi_{(2\Delta-d)}
+
\mathcal F_{\rm local}[\phi_{(0)},g_{(0)}],
$$

where $\mathcal F_{\rm local}$ is fixed only after the renormalization scheme is specified.

## Ward identities from the renormalized action

The one-point functions are not independent. They obey Ward identities because $S_{\rm ren}$ is invariant under boundary gauge transformations, diffeomorphisms, and Weyl transformations, up to anomalies.

For a scalar source $\phi_{(0)}$ and background metric $g_{(0)ij}$, boundary diffeomorphism invariance gives schematically

$$
\nabla_i\langle T^{ij}\rangle
=
\langle\mathcal O\rangle\nabla^j\phi_{(0)}
+
\text{terms from other sources}.
$$

If a background gauge field is present, the stress tensor Ward identity includes the Lorentz-force term:

$$
\nabla_i\langle T^{ij}\rangle
=
F_{(0)}^{ji}\langle J_i\rangle
+
\langle\mathcal O\rangle\nabla^j\phi_{(0)}
+
\cdots.
$$

Gauge invariance gives

$$
\nabla_i\langle J^i\rangle=0
$$

when the charged-operator sources vanish. If charged scalar sources are present, the current Ward identity includes their variation under the symmetry.

Weyl transformations give the trace identity

$$
\langle T^i_{\ i}\rangle
=
(d-\Delta)\phi_{(0)}\langle\mathcal O\rangle
+
\mathcal A[g_{(0)},\phi_{(0)},\ldots],
$$

where $\mathcal A$ is the conformal anomaly, present in even boundary dimensions or in the presence of scale-dependent sources.

These identities are powerful checks on holographic calculations. If a proposed one-point function violates the correct Ward identity, either the counterterms, the signs, or the boundary conditions are wrong.

## Vevs and spontaneous symmetry breaking

A source explicitly breaks any symmetry under which it transforms. A vev can break the symmetry spontaneously if the source is absent.

Suppose $\mathcal O$ is charged under a global $U(1)$ symmetry and is dual to a charged bulk scalar $\Phi$. Near the boundary,

$$
\Phi(z,x)
\sim
z^{d-\Delta}\Phi_{(0)}(x)
+
z^\Delta A_\Phi(x).
$$

If

$$
\Phi_{(0)}=0,
\qquad
A_\Phi\neq0,
$$

then the boundary source for $\mathcal O$ vanishes but the expectation value can be nonzero. This is the holographic pattern behind many superfluid and superconducting models.

If instead $\Phi_{(0)}\neq0$, then the symmetry is explicitly broken by the source. The response may still be interesting, but it is not purely spontaneous.

The same logic applies more broadly. To diagnose a phase, do not simply look for a nonzero field. Identify which coefficient is the source, which coefficient is the response, and which symmetries those coefficients transform under.

## Multi-trace deformations and mixed boundary conditions

The clean source-response split above is simplest for single-trace sources in standard quantization. If the boundary theory is deformed by a multi-trace term, such as

$$
\Delta S_{\rm CFT}
=
\frac f2\int d^d x\,\mathcal O^2,
$$

then the boundary condition is no longer simply “fix $\phi_{(0)}$.” Instead, the source and response are related by a mixed boundary condition. Schematically, if $\alpha$ and $\beta$ denote the two independent scalar coefficients, one finds a condition of the form

$$
\beta=f\alpha+J
$$

or the inverse relation, depending on the quantization convention.

This is another reason why the variational definition is fundamental. Boundary conditions define which quantity is held fixed, and the vev is obtained by varying the correctly renormalized action appropriate to that boundary condition.

## Practical recipe

For a scalar one-point function in standard quantization:

1. Solve the bulk equations near the boundary.
2. Identify the source coefficient $\phi_{(0)}$.
3. Keep the independent response coefficient $\phi_{(2\Delta-d)}$.
4. Regulate the on-shell action at $z=\epsilon$.
5. Add local counterterms.
6. Vary the renormalized action with respect to $\phi_{(0)}$.
7. Only then remove the cutoff and read off $\langle\mathcal O\rangle$.

When the simple formula applies,

$$
\langle\mathcal O\rangle
=(2\Delta-d)\mathcal N\phi_{(2\Delta-d)}+\text{local terms}.
$$

When it does not apply, the recipe still does.

## Dictionary checkpoint

| Boundary concept | Bulk concept |
|---|---|
| source $\phi_{(0)}$ | leading non-normalizable scalar coefficient |
| vev $\langle\mathcal O\rangle$ | renormalized radial canonical momentum |
| response coefficient $\phi_{(2\Delta-d)}$ | normalizable scalar datum |
| charge density $\langle J^t\rangle$ | renormalized electric flux through the boundary |
| stress tensor $\langle T^{ij}\rangle$ | renormalized Brown–York metric response |
| QFT Ward identities | radial constraint equations and boundary gauge/diffeomorphism invariance |
| scheme-dependent contact terms | finite local counterterms |
| anomaly | logarithmic divergence and scale dependence of $S_{\rm ren}$ |

The safest sentence is:

$$
\boxed{
\text{One-point functions are renormalized canonical momenta conjugate to boundary sources.}
}
$$

## Common confusions

### “The vev is always the coefficient of $z^\Delta$.”

Only in simple scalar examples, and only after a normalization choice. In general, the vev is obtained by varying $S_{\rm ren}$. The $z^\Delta$ coefficient contributes to it, but local counterterm pieces, logarithms, mixing with other fields, and finite scheme choices may also appear.

### “A nonzero normalizable mode always means a new source.”

No. In standard quantization, normalizable data usually describe state-dependent expectation values. The source is the non-normalizable coefficient. Mixed boundary conditions and alternate quantization change the story, but they do so by changing the variational problem.

### “If the source is zero, all one-point functions vanish.”

Not necessarily. A state can have nonzero expectation values even when sources vanish. Thermal states have nonzero stress tensors. Finite-density states have nonzero charge density. Symmetry-broken states can have condensates with zero explicit source.

### “Counterterms only remove infinities, so they cannot affect finite vevs.”

Divergent counterterms remove infinities, but finite local counterterms are also allowed. They change scheme-dependent local terms in one-point functions. Physical nonlocal data and properly formulated Ward identities remain meaningful.

### “The sign of the vev formula is universal.”

The physics is universal; the sign convention is not. The sign depends on whether the Euclidean source is written as $S_E-\int J\mathcal O$ or $S_E+\int J\mathcal O$, and on the convention for $W$ versus the on-shell action. This course uses $W\approx -S_{\text{ren,on-shell}}$.

## Exercises

### Exercise 1: Source dimension

A scalar primary $\mathcal O$ has scaling dimension $\Delta$ in a $d$-dimensional CFT. What is the scaling dimension of its source $\phi_{(0)}$?

<details>
<summary><strong>Solution</strong></summary>

The source term is

$$
\int d^d x\,\phi_{(0)}(x)\mathcal O(x).
$$

The measure has dimension $-d$, while $\mathcal O$ has dimension $\Delta$. For the action to be dimensionless,

$$
[\phi_{(0)}]+\Delta-d=0.
$$

Thus

$$
[\phi_{(0)}]=d-\Delta.
$$

This matches the near-boundary behavior $z^{d-\Delta}\phi_{(0)}$: the radial coordinate $z$ has length dimension, so the full bulk field has the appropriate scaling behavior under boundary dilatations.

</details>

### Exercise 2: Deriving the scalar response factor

Assume a scalar expansion of the form

$$
\phi(z,x)=z^{d-\Delta}\phi_{(0)}(x)+z^\Delta A(x)+\cdots
$$

in Poincaré AdS and ignore all derivative and local counterterm pieces. Why should the vev be proportional to $(2\Delta-d)A$ rather than simply to $A$?

<details>
<summary><strong>Solution</strong></summary>

The canonical momentum involves a radial derivative. The two independent powers differ by

$$
\Delta-(d-\Delta)=2\Delta-d.
$$

After subtracting the divergent piece associated with the source branch, the finite part of the radial canonical momentum is proportional to this difference of exponents. More explicitly, the renormalized variation of the scalar action gives

$$
\delta S_{\rm ren}
\sim
-\mathcal N(2\Delta-d)
\int d^d x\sqrt{g_{(0)}}\,A(x)\delta\phi_{(0)}(x),
$$

with the sign depending on the convention for the outward normal and for $W=-S_{\rm ren}$. Therefore

$$
\langle\mathcal O\rangle
\sim
(2\Delta-d)\mathcal N A.
$$

The factor is not a mysterious CFT normalization. It comes from the radial canonical momentum.

</details>

### Exercise 3: Chemical potential and charge density

For a massless bulk gauge field in an asymptotically AdS$_{d+1}$ black-brane geometry, suppose

$$
A_t(z)=\mu-\rho z^{d-2}+\cdots.
$$

Which coefficient is the source, and which coefficient is proportional to the charge density?

<details>
<summary><strong>Solution</strong></summary>

The leading boundary value $\mu$ is the source for the charge density operator $J^t$. In thermodynamic language it is the chemical potential.

The subleading coefficient $\rho$ is proportional to the expectation value $\langle J^t\rangle$. More precisely, $\langle J^t\rangle$ is the renormalized electric flux at the boundary, so the numerical proportionality factor depends on the Maxwell coupling and normalization conventions.

</details>

### Exercise 4: Trace Ward identity with a relevant scalar source

A CFT is deformed by a scalar source $\phi_{(0)}$ for an operator of dimension $\Delta$. Ignoring anomalies, what trace Ward identity should you expect?

<details>
<summary><strong>Solution</strong></summary>

The source has dimension $d-\Delta$. A nonzero source introduces a scale unless $\Delta=d$. The trace Ward identity is

$$
\langle T^i_{\ i}\rangle
=
(d-\Delta)\phi_{(0)}\langle\mathcal O\rangle,
$$

up to sign conventions and possible additional source terms. If $\Delta<d$, the deformation is relevant. If $\Delta=d$, the classical source term is marginal and this contribution vanishes, though anomalies or beta functions can still contribute in more general cases.

</details>

## Further reading

- S. de Haro, K. Skenderis, and S. N. Solodukhin, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
- M. Bianchi, D. Z. Freedman, and K. Skenderis, [Holographic Renormalization](https://arxiv.org/abs/hep-th/0112119).
- I. R. Klebanov and E. Witten, [AdS/CFT Correspondence and Symmetry Breaking](https://arxiv.org/abs/hep-th/9905104).
- V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).
