---
title: "Background Fields for Higher-Form Symmetries"
description: "Explains how higher-form global symmetries couple to background gauge fields, how Ward identities become background gauge invariance, and how charged extended operators transform."
sidebar:
  label: "Background Fields"
  order: 3
level: Advanced
status: "Polished draft"
source: "Gaiotto–Kapustin–Seiberg–Willett; Kapustin–Seiberg; Freed–Hopkins; Nakahara; Frankel; standard differential-form conventions."
topics:
  - higher-form symmetry
  - background fields
  - higher-form gauge fields
  - Ward identities
  - anomalies
  - charged extended operators
canonicalTopics:
  - higher-form-background-field
  - background-gauge-invariance
  - higher-form-current
  - higher-form-ward-identity
  - anomaly-obstruction
researchStatus:
  established:
    - "For Abelian higher-form symmetries, background gauge fields provide the standard source-field formulation of Ward identities, gauging, and ’t Hooft anomalies."
    - "A $q$-form symmetry couples to a background $(q+1)$-form gauge field, generalizing the ordinary coupling of a zero-form current to a background one-form gauge field."
  active:
    - "Global, discrete, fermionic, higher-group, non-invertible, and symmetry-TFT refinements require cocycle, differential-cohomology, or categorical background data beyond a single differential form."
---

## Summary

A higher-form global symmetry can be probed by a higher-form background gauge field. For an ordinary zero-form symmetry, the background is a one-form gauge field $A_1$. For a $q$-form symmetry, the background is a $(q+1)$-form gauge field:

$$
\text{$q$-form symmetry}
\quad\longrightarrow\quad
B_{q+1}.
$$

For a continuous Abelian $q$-form symmetry with current $J_{q+1}$, the schematic source coupling is

$$
S\mapsto S+\int_{X_d}B_{q+1}\wedge {*J}_{q+1}.
$$

Background gauge invariance

$$
B_{q+1}\mapsto B_{q+1}+d\Lambda_q
$$

is the higher-form version of the Ward identity. If the symmetry is exact and non-anomalous, the generating functional is invariant:

$$
Z[B+d\Lambda]=Z[B].
$$

If charged operators are inserted, the Ward identity includes their transformation. For a charged $q$-dimensional operator $W_n(M^q)$,

$$
W_n(M)\mapsto
\exp\!\left(i n\int_M\Lambda_q\right)W_n(M).
$$

Thus background fields do for higher-form symmetries exactly what ordinary sources do for zero-form symmetries: they make conservation, charge, gauging, contact terms, and anomalies precise.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Schematic showing a q-form current coupled to a background B field, the gauge transformation B to B+d Lambda, and a charged extended operator transforming by the integral of Lambda over its support.](/figures/symmetry-anomalies-topology/higher-form-background-fields.svg)

<figcaption>

A continuous Abelian $q$-form current $J_{q+1}$ couples to a background $(q+1)$-form field $B_{q+1}$. Background gauge transformations encode the Ward identity. Charged $q$-dimensional operators transform by the holonomy of the $q$-form gauge parameter over their support.

</figcaption>
</figure>

This page explains the differential-form version. Later pages refine it for finite groups, large gauge transformations, nontrivial bundles, gauging, and anomalies.

## Prerequisites

Read [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) and [Charged Extended Operators](/symmetry-anomalies-topology/higher-form-generalized-symmetries/charged-extended-operators/) first. You should also know the basic background-field idea from [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/): a background field is an external source, not a dynamical field integrated over in the path integral.

The mathematical prerequisites are differential forms, exterior derivative $d$, Stokes’ theorem, and the idea that a $p$-form can be integrated over a $p$-dimensional submanifold.

## Core idea

A background field turns a symmetry into a family of partition functions.

For an ordinary global symmetry with current $j^\mu$, one introduces a background gauge field $A_\mu$ and studies

$$
Z[A].
$$

Gauge invariance of $Z[A]$ under

$$
A\mapsto A+d\lambda
$$

encodes current conservation and Ward identities.

For a $q$-form symmetry, the same idea becomes

$$
Z[B_{q+1}],
$$

with background gauge invariance

$$
B_{q+1}\mapsto B_{q+1}+d\Lambda_q.
$$

The parameter is a $q$-form because the background is a $(q+1)$-form. Charged operators are $q$-dimensional, so $\Lambda_q$ can be integrated over their supports. This is the geometric reason the formula

$$
W_n(M^q)\mapsto e^{in\int_M\Lambda_q}W_n(M^q)
$$

has exactly the right dimensions.

The lesson is:

$$
\text{background gauge invariance}
\quad=\quad
\text{Ward identity in source language}.
$$

When background gauge invariance fails in a way that cannot be removed by local counterterms, the higher-form symmetry has a ’t Hooft anomaly.

## Setup and conventions

Let $X_d$ be the $d$-dimensional spacetime manifold. A continuous Abelian $q$-form symmetry has a current written as a $(q+1)$-form

$$
J_{q+1}.
$$

The conservation law is

$$
d{*J}_{q+1}=0.
$$

The background field is a $(q+1)$-form

$$
B_{q+1}.
$$

The schematic coupling is

$$
S[\Phi;B]=S[\Phi]+\int_{X_d}B_{q+1}\wedge {*J}_{q+1}.
$$

With Lorentzian path-integral weight $e^{iS}$, the generating functional is

$$
Z[B]=\int\mathcal D\Phi\,e^{iS[\Phi;B]}.
$$

The expectation value of the current is obtained by varying $W[B]$ with respect to $B$, with $Z[B]=e^{iW[B]}$. Suppressing component combinatorial factors,

$$
\frac{\delta W[B]}{\delta B_{q+1}}\sim \langle {*J}_{q+1}\rangle_B.
$$

:::note[Convention-sensitive normalization]
Some authors define the current as the dual form ${*J}_{q+1}$ rather than $J_{q+1}$. This volume uses $J_{q+1}$ for the form that has degree $q+1$ and couples as $B_{q+1}\wedge {*J}_{q+1}$. The conserved charge is $\int_\Sigma {*J}_{q+1}$.
:::

## Background gauge transformations

The background gauge transformation is

$$
B_{q+1}\mapsto B_{q+1}+d\Lambda_q.
$$

If no charged operators are inserted, the variation of the source term is

$$
\delta_\Lambda S
=
\int_{X_d}d\Lambda_q\wedge {*J}_{q+1}.
$$

Using integration by parts on a closed spacetime,

$$
\delta_\Lambda S
=
(-1)^{q+1}\int_{X_d}\Lambda_q\wedge d{*J}_{q+1}.
$$

Thus background gauge invariance is equivalent to

$$
d{*J}_{q+1}=0,
$$

up to boundary terms, contact terms, and anomalies.

This is the higher-form analogue of the elementary zero-form fact that ordinary background gauge invariance implies current conservation.

## Charged insertions and contact terms

Now insert charged extended operators

$$
W_{n_i}(M_i^q).
$$

Under a background gauge transformation, they transform as

$$
W_{n_i}(M_i)\mapsto
\exp\!\left(i n_i\int_{M_i}\Lambda_q\right)W_{n_i}(M_i).
$$

Therefore the correct Ward identity for a correlator is not simply $Z[B+d\Lambda]=Z[B]$. It is the covariance statement

$$
\left\langle\prod_i W_{n_i}(M_i)\right\rangle_{B+d\Lambda}
=
\exp\!\left(i\sum_i n_i\int_{M_i}\Lambda_q\right)
\left\langle\prod_i W_{n_i}(M_i)\right\rangle_B,
$$

with signs depending on whether the transformation is written actively or passively.

Infinitesimally, this says that $d{*J}$ has delta-function support on charged operator worldvolumes. Schematically,

$$
d{*J}_{q+1}
=
\sum_i n_i\,\delta_{M_i},
$$

where $\delta_{M_i}$ is the Poincaré-dual distributional form to $M_i$. This is the local background-field version of the linking Ward identity.

:::note[Source note]
The statement “charged insertions create contact terms in Ward identities” is the higher-form version of the ordinary current-divergence Ward identity for charged local operators. The only new ingredient is that the delta function is supported on an extended submanifold rather than at a point.
:::

## Gauge-invariant dressed operators

A charged operator is not invariant under background gauge transformations by itself. That is not a bug; it is what it means to be charged.

In a fixed background $B$, one can often make a gauge-invariant composite by attaching a filling manifold. Let $M^q=\partial N^{q+1}$. Define

$$
\widehat W_n(M,N)
=
W_n(M)\,
\exp\!\left(-in\int_N B_{q+1}\right).
$$

Under

$$
B_{q+1}\mapsto B_{q+1}+d\Lambda_q,
$$

the exponential changes by

$$
\exp\!\left(-in\int_N d\Lambda_q\right)
=
\exp\!\left(-in\int_M \Lambda_q\right),
$$

which cancels the transformation of $W_n(M)$.

This construction is the higher-form analogue of attaching a Wilson line to charged local operators in an ordinary background gauge field.

It also reveals an important subtlety. The dressed operator depends on the choice of $N$. Changing $N$ by a closed $(q+1)$-cycle changes the result by a background holonomy:

$$
\exp\!\left(-in\int_{\Gamma^{q+1}}B_{q+1}\right).
$$

Thus in nontrivial backgrounds, charged operators are not merely local objects; they know about global topology.

## Large gauge transformations and quantization

For noncompact real-valued forms, $B\mapsto B+d\Lambda$ is the whole local story. For compact $U(1)$ higher-form gauge fields, there are also large gauge transformations and quantization conditions.

A $U(1)$ $(q+1)$-form background has field strength

$$
H_{q+2}=dB_{q+1}
$$

locally, but globally it is better regarded as a differential-cohomology object. Its periods obey

$$
\frac{1}{2\pi}\int_{\Gamma^{q+2}}H_{q+2}\in\mathbb Z
$$

on closed $(q+2)$-cycles, when the usual compact normalization is used.

Large gauge transformations can shift

$$
\int_{C^{q+1}}B_{q+1}
$$

by integer multiples of $2\pi$ on closed cycles. Charge quantization is what makes

$$
\exp\!\left(in\int_C B_{q+1}\right)
$$

well-defined for integer charge $n$.

This is the higher-form version of the familiar statement that a compact $U(1)$ background gauge field has quantized flux and charged particles have quantized charges.

## Discrete higher-form backgrounds

For a finite higher-form symmetry such as $\mathbb Z_N^{(q)}$, a smooth real-valued differential form is not the right global object. The background is a discrete $(q+1)$-form gauge field, often represented on a triangulated spacetime by a cocycle

$$
B_{q+1}\in Z^{q+1}(X,\mathbb Z_N).
$$

Gauge transformations are cochain shifts

$$
B_{q+1}\mapsto B_{q+1}+\delta\Lambda_q.
$$

A charged operator of charge $n\in\mathbb Z_N$ transforms by the discrete analogue of the continuum phase,

$$
W_n(M)\mapsto
\exp\!\left(\frac{2\pi i n}{N}\int_M\Lambda_q\right)W_n(M).
$$

The integrals here mean evaluation of cochains on chains. This language is often the cleanest way to describe finite higher-form backgrounds, Dijkgraaf–Witten-type terms, and discrete ’t Hooft anomalies.

The continuous-form formulas on this page should therefore be understood as the differential-form model of a more general background-field idea.

## Relation to topological symmetry operators

Background fields and topological charge operators are two views of the same symmetry.

The topological-operator view says that a symmetry operator $U_g(\Sigma)$ can be inserted and deformed. When it links a charged operator, the charged operator transforms.

The background-field view says that one may turn on a background $B_{q+1}$ whose holonomy or flux through a linking cycle represents the same operation.

For finite or compact symmetries, a flat background can implement a symmetry twist. For example, a $\mathbb Z_N$ one-form background can be understood as prescribing phases for line operators when they link certain surfaces. In a path integral, this is often represented by summing over fields with twisted patching data.

The topological operator is local in the sense of being an insertion. The background field is global in the sense of modifying the source data on spacetime. They are complementary languages.

## Example: ordinary symmetry as q equals zero

For $q=0$, the background is a one-form

$$
B_{q+1}=A_1.
$$

The gauge parameter is a zero-form function $\lambda$,

$$
A\mapsto A+d\lambda.
$$

A charged local operator at a point $x$ transforms as

$$
\mathcal O_n(x)\mapsto e^{in\lambda(x)}\mathcal O_n(x).
$$

If $x$ and $y$ are endpoints of a path $\gamma$, the dressed two-point insertion

$$
\mathcal O_n(x)\,
\exp\!\left(-in\int_\gamma A\right)
\mathcal O_{-n}(y)
$$

is gauge invariant under the background transformation.

This is exactly the $q=0$ version of the filling-manifold construction: the charged support is a zero-dimensional boundary, and the dressing is an integral over a one-dimensional chain.

## Example: one-form symmetry in four dimensions

For a one-form symmetry in four dimensions, the background is a two-form

$$
B_2.
$$

The gauge parameter is a one-form

$$
\Lambda_1,
$$

and

$$
B_2\mapsto B_2+d\Lambda_1.
$$

A charged line operator $W_n(C)$ transforms as

$$
W_n(C)\mapsto
\exp\!\left(in\oint_C\Lambda_1\right)W_n(C).
$$

If $C=\partial S$, the dressed line

$$
\widehat W_n(C,S)
=
W_n(C)\exp\!\left(-in\int_S B_2\right)
$$

is invariant under background gauge transformations.

This formula is one of the best ways to remember the degree rule:

$$
\text{line support }C^1,\qquad
\text{gauge parameter }\Lambda_1,\qquad
\text{background }B_2,\qquad
\text{filling }S^2.
$$

## Example: Maxwell theory

In four-dimensional Maxwell theory without charged matter, there are electric and magnetic one-form symmetries. Their conserved currents are two-forms built from $F$ and $*F$:

$$
J_e\sim F,\qquad
J_m\sim {*F},
$$

depending on convention and normalization.

One may couple corresponding two-form backgrounds to these currents. Turning on an electric one-form background can be described by replacing the field strength in the action by a gauge-invariant combination involving a background two-form. Turning on a magnetic one-form background modifies the Bianchi identity in a dual description.

Different normalizations are common, especially because electric-magnetic duality exchanges fields, couplings, and flux quantization. For conceptual purposes, the important point is stable:

$$
\text{one-form symmetry in }d=4
\quad\Longleftrightarrow\quad
\text{two-form background field}.
$$

The detailed Maxwell page will state its normalization separately.

## Boundary terms and anomaly inflow

On a spacetime with boundary, the integration-by-parts step that gave

$$
d{*J}=0
$$

also produces a boundary term. Background gauge invariance may then require boundary degrees of freedom, boundary conditions, or anomaly inflow from one higher dimension.

If

$$
Z[B+d\Lambda]\neq Z[B]
$$

by a phase that cannot be removed by a local counterterm in $d$ dimensions, the higher-form symmetry has a ’t Hooft anomaly. Often this anomalous variation can be represented as the boundary variation of a $(d+1)$-dimensional topological action

$$
\exp\!\left(iS_{\text{bulk}}[B]\right).
$$

This is the higher-form version of anomaly inflow. It is one of the bridges from this chapter to Symmetry TFT.

## Preparing for gauging

A background field is not integrated over. Gauging a higher-form symmetry means promoting the background to a dynamical field or, more generally, summing over the appropriate background gauge-equivalence classes.

Symbolically,

$$
Z_{\text{gauged}}
\sim
\sum_{[B]}\,Z[B],
$$

or

$$
Z_{\text{gauged}}
\sim
\int \frac{\mathcal D B}{\text{higher-form gauge redundancy}}\,Z[B],
$$

depending on whether the symmetry is finite or continuous.

This operation changes the theory. It changes which extended operators are genuine, which line or surface operators can end, and what dual symmetry remains. If $Z[B]$ is not background gauge invariant, the symmetry cannot be gauged by itself without adding extra bulk or boundary data.

The next page develops this operation carefully.

## Common pitfalls

**“A higher-form background is always an ordinary differential form.”** Locally, yes for continuous Abelian symmetries. Globally, compact and finite higher-form backgrounds are better described using bundles, cocycles, or differential cohomology.

**“The background field is dynamical.”** No. A background field is a source. It becomes dynamical only after gauging or after explicitly adding an integration/sum over it.

**“Gauge invariance of $Z[B]$ means charged operators are invariant.”** Charged operators transform covariantly. Their correlators are invariant only after including the transformation of the insertions or after dressing them.

**“The field strength is always just $dB$.”** Locally this is true. Globally, flux quantization, torsion, patching, and discrete cocycles can carry information not visible in a single global form.

**“If an operator needs a filling surface, it is unphysical.”** Not necessarily. It may be a charged operator in a background field. The filling dependence records the background holonomy and is the analogue of dressing charged local operators with Wilson lines.

**“Every failure of background gauge invariance is explicit breaking.”** A removable failure can be a counterterm convention. A non-removable failure is a ’t Hooft anomaly. Explicit breaking means the background gauge transformation is not a symmetry requirement of the theory.

## Relations to other pages

[Charged Extended Operators](/symmetry-anomalies-topology/higher-form-generalized-symmetries/charged-extended-operators/) explains the objects that transform under higher-form background gauge transformations. [Gauging Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/gauging-higher-form-symmetries/) explains what happens when $B_{q+1}$ is summed over. [Center Symmetry](/symmetry-anomalies-topology/higher-form-generalized-symmetries/center-symmetry/) gives the most important non-Abelian gauge-theory example.

The Background Fields and Gauging chapter gives the zero-form version of this source logic. The Anomalies and Symmetry TFT chapters explain what it means for $Z[B]$ to transform anomalously.

## Research status

The background-field formulation of Abelian higher-form symmetries is standard. It is the workhorse for deriving Ward identities, defining ’t Hooft anomalies, gauging higher-form symmetries, and relating QFTs to topological field theories.

The active frontier concerns refinements: higher-group backgrounds where zero-form and higher-form transformations mix, non-invertible “backgrounds” better described by topological interfaces or symmetry TFT boundary conditions, fermionic and spin-sensitive backgrounds, and global differential-cohomology data needed for precise anomaly formulas.

## Exercises

### Exercise 1: Degree counting

A two-form symmetry in $d=6$ couples to what degree background field? What is the degree of its gauge parameter?

<details><summary><strong>Solution</strong></summary>

A $q$-form symmetry couples to a $(q+1)$-form background. For $q=2$, the background is a three-form

$$
B_3.
$$

Its gauge transformation is

$$
B_3\mapsto B_3+d\Lambda_2,
$$

so the gauge parameter is a two-form $\Lambda_2$.

</details>

### Exercise 2: Ward identity from background gauge invariance

Starting from

$$
S_{\text{source}}=\int B_{q+1}\wedge {*J}_{q+1},
$$

show that invariance under $B_{q+1}\mapsto B_{q+1}+d\Lambda_q$ implies $d{*J}_{q+1}=0$ on a closed spacetime with no charged insertions.

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta S_{\text{source}}
=
\int d\Lambda_q\wedge {*J}_{q+1}.
$$

Integrating by parts on a closed spacetime gives

$$
\delta S_{\text{source}}
=
(-1)^{q+1}\int \Lambda_q\wedge d{*J}_{q+1}.
$$

For arbitrary $\Lambda_q$, invariance requires

$$
d{*J}_{q+1}=0.
$$

</details>

### Exercise 3: Dressed line operator

For a one-form symmetry with background $B_2$, a charged line $W_n(C)$ transforms as

$$
W_n(C)\mapsto e^{in\oint_C\Lambda_1}W_n(C).
$$

Show that if $C=\partial S$, then

$$
\widehat W_n(C,S)=W_n(C)e^{-in\int_S B_2}
$$

is background-gauge-invariant.

<details><summary><strong>Solution</strong></summary>

Under $B_2\mapsto B_2+d\Lambda_1$,

$$
e^{-in\int_S B_2}
\mapsto
e^{-in\int_S B_2}\,
e^{-in\int_S d\Lambda_1}.
$$

By Stokes’ theorem,

$$
\int_S d\Lambda_1=\oint_C\Lambda_1.
$$

So the exponential gains the factor

$$
e^{-in\oint_C\Lambda_1},
$$

which cancels the transformation of $W_n(C)$. Thus $\widehat W_n(C,S)$ is invariant.

</details>

### Exercise 4: Discrete analogue

For a $\mathbb Z_N$ one-form symmetry, what replaces the smooth two-form background $B_2$?

<details><summary><strong>Solution</strong></summary>

A finite $\mathbb Z_N$ one-form symmetry is coupled to a discrete two-form background. On a triangulated spacetime, this can be represented by a cocycle

$$
B_2\in Z^2(X,\mathbb Z_N).
$$

Gauge transformations are cochain shifts

$$
B_2\mapsto B_2+\delta\Lambda_1.
$$

This discrete cocycle data replaces the smooth real-valued two-form background used for continuous Abelian symmetries.

</details>

## References

- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for higher-form backgrounds, Ward identities, gauging, and anomalies.
- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality,” for background-field and global-form refinements.
- D. S. Freed and M. J. Hopkins, “Reflection Positivity and Invertible Topological Phases,” for invertible field theories and anomaly-background structure.
- M. Nakahara, *Geometry, Topology and Physics*, for differential forms, bundles, characteristic classes, monopoles, and gauge geometry.
- T. Frankel, *The Geometry of Physics*, for exterior forms, integration, Stokes’ theorem, and the geometric language of gauge fields.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 34, for background-field methods in standard QFT language.

## Version history

- 2026-06-20: Initial polished draft. Added higher-form background-field conventions, background gauge transformations, charged insertion covariance, filling-surface dressing, finite-background preview, anomaly preview, and exercises.
