---
title: "Witten Diagrams"
description: "How tree-level bulk perturbation theory in AdS computes boundary CFT correlation functions through contact and exchange diagrams."
sidebar:
  order: 10
---

## Why this matters

The GKP/Witten prescription tells us that CFT correlation functions are obtained by differentiating a bulk partition function with respect to boundary sources. In the classical gravity limit this becomes a variational problem for an on-shell action. Witten diagrams are the next step: they are the diagrammatic expansion of that on-shell action around an AdS saddle.

They are the AdS analogues of Feynman diagrams, but with an important twist. In ordinary flat-space perturbation theory, external legs usually represent asymptotic particles. In Euclidean AdS/CFT, the external legs end on boundary points and represent insertions of CFT operators. A Witten diagram is therefore not primarily a scattering diagram. It is a way to compute the position-space correlation function

$$
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle
$$

from a bulk integral over AdS.

This page introduces the basic rules. The next page applies them to the most important first example: a cubic bulk coupling and the CFT three-point coefficient $C_{123}$.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Contact and exchange Witten diagrams](/figures/course/witten-diagrams.svg)

<figcaption>

Witten diagrams organize the saddle expansion of $S_{\rm bulk}$ around AdS. Boundary-to-bulk propagators attach CFT sources to bulk vertices; bulk-to-bulk propagators carry exchanged fields through the interior.

</figcaption>
</figure>

## Setup: a scalar bulk theory

Work in Euclidean Poincare AdS$_{d+1}$,

$$
ds^2
=
\frac{L^2}{z^2}
\left(dz^2+d x^i d x^i\right),
\qquad
z>0,
$$

with boundary at $z=0$. For most of this page, set $L=1$ to reduce clutter. Consider a collection of scalar fields $\phi_a$ dual to scalar primary operators $\mathcal O_a$ of dimensions $\Delta_a$. A useful toy action is

$$
S[\phi]
=
\int_{\mathrm{AdS}} d^{d+1}X\sqrt g
\left[
\frac12 \sum_a
\left(
 g^{MN}\partial_M\phi_a\partial_N\phi_a
 +m_a^2\phi_a^2
\right)
+
V_{\rm int}(\phi)
\right]
+
S_{\rm bdy},
$$

where $X=(z,x)$ and $S_{\rm bdy}$ includes the boundary terms and counterterms needed to make the variational problem and the on-shell action well-defined.

The scalar masses determine the CFT dimensions by

$$
m_a^2L^2=\Delta_a(\Delta_a-d).
$$

For standard quantization, the near-boundary behavior is

$$
\phi_a(z,x)
\sim
z^{d-\Delta_a}J_a(x)
+
z^{\Delta_a}A_a(x)+\cdots,
$$

where $J_a$ is the source for $\mathcal O_a$, while $A_a$ is related to $\langle \mathcal O_a\rangle$ after holographic renormalization.

The Euclidean generating functional is

$$
Z_{\rm CFT}[J]
=
\left\langle
\exp\left(\sum_a\int d^d x\,J_a\mathcal O_a\right)
\right\rangle,
\qquad
W_{\rm CFT}[J]=\log Z_{\rm CFT}[J].
$$

In the classical bulk approximation,

$$
W_{\rm CFT}[J]
\approx
-S_{\text{ren,on-shell}}[J].
$$

Witten diagrams are the perturbative expansion of the right-hand side.

## Boundary-to-bulk propagators

The linearized equation for a scalar field is

$$
\left(-\nabla^2+m^2\right)\phi=0.
$$

Given a boundary source $J(x)$, the regular Euclidean solution can be written as

$$
\phi^{(1)}(z,x)
=
\int d^d y\,K_\Delta(z,x;y)J(y),
$$

where $K_\Delta$ is the boundary-to-bulk propagator. In Poincare AdS, a standard normalization is

$$
K_\Delta(z,x;y)
=
C_\Delta
\left(
\frac{z}{z^2+|x-y|^2}
\right)^\Delta,
\qquad
C_\Delta
=
\frac{\Gamma(\Delta)}{\pi^{d/2}\Gamma(\Delta-d/2)}.
$$

This normalization is chosen so that, distributionally,

$$
K_\Delta(z,x;y)
\sim
z^{d-\Delta}\delta^{(d)}(x-y)
\qquad
\text{as }z\to0,
$$

up to the usual conventions and contact-term subtleties.

In a diagram, a boundary-to-bulk propagator is drawn as a line from a boundary point $x_i$ to a bulk point $X$. It is the AdS version of an external leg. The leg does not represent a particle coming in from infinity. It represents the response of the bulk field to a boundary source.

## Bulk-to-bulk propagators

When an interaction creates a field that propagates through the interior before interacting again, one needs a bulk-to-bulk propagator. For a scalar field of dimension $\Delta$, it satisfies

$$
\left(-\nabla_X^2+m^2\right)G_\Delta(X,Y)
=
\frac{1}{\sqrt{g}}\delta^{(d+1)}(X-Y),
$$

with boundary conditions appropriate to the chosen quantization and interior regularity. In Euclidean AdS, this means regularity in the interior and the appropriate normalizable behavior near the boundary.

A bulk-to-bulk propagator is drawn as an internal line between two bulk points $X$ and $Y$. In a boundary four-point function, such an internal line corresponds to the exchange of a single-trace operator and its descendants in the CFT OPE.

## The tree-level rules

For a weakly coupled bulk effective theory in Euclidean AdS, the leading large-$N$ connected correlators are computed by tree-level Witten diagrams. The rules are:

1. Put each operator insertion $\mathcal O_i(x_i)$ on the boundary.
2. Attach a boundary-to-bulk propagator $K_{\Delta_i}(X;x_i)$ to each external insertion.
3. Integrate each bulk interaction vertex over AdS with measure $d^{d+1}X\sqrt g$.
4. Include the coupling constants and derivative operators from the bulk action.
5. Connect bulk vertices with bulk-to-bulk propagators $G_\Delta(X,Y)$.
6. Add all diagrams of the required order in the bulk interactions.
7. Include signs, symmetry factors, field normalizations, and counterterm contributions according to the precise action convention.

For example, a cubic interaction

$$
S_{\rm int}
=
\frac{g_{123}}{3!}
\int d^{d+1}X\sqrt g\,\phi_1\phi_2\phi_3
$$

gives a three-point contact diagram. If the three fields are distinct, one often writes the same term without the $3!$ and absorbs the combinatorics into the definition of $g_{123}$.

An $n$-point contact interaction schematically contributes

$$
\mathcal A_{\rm contact}(x_1,\ldots,x_n)
\sim
-g_{1\cdots n}
\int_{\mathrm{AdS}}d^{d+1}X\sqrt g\,
K_{\Delta_1}(X;x_1)\cdots K_{\Delta_n}(X;x_n).
$$

The minus sign is the Euclidean convention coming from $W=-S_{\text{on-shell}}$. Depending on whether one defines $S_{\rm int}$ with additional signs, the displayed sign may change. The physical OPE data are of course convention-independent once operator and coupling normalizations are fixed.

A scalar exchange contribution to a four-point function has the schematic form

$$
\mathcal A_{\rm exchange}(x_1,x_2,x_3,x_4)
\sim
 g_{12\chi}g_{34\chi}
\int dX\sqrt g\int dY\sqrt g\,
K_1(X;x_1)K_2(X;x_2)
G_\chi(X,Y)
K_3(Y;x_3)K_4(Y;x_4),
$$

again up to a convention-dependent sign and symmetry factor.

## Where the diagrams come from

The diagrammatic expansion is not an extra postulate. It follows from solving the classical equations of motion perturbatively in the sources and couplings.

For one scalar field with a cubic interaction,

$$
S
=
\int dX\sqrt g
\left[
\frac12\phi\left(-\nabla^2+m^2\right)\phi
+
\frac{g}{3!}\phi^3
\right]
+
S_{\rm bdy},
$$

the equation of motion is

$$
\left(-\nabla^2+m^2\right)\phi
+
\frac{g}{2}\phi^2=0.
$$

Expand the classical solution as

$$
\phi_{\rm cl}
=
\phi^{(1)}+\phi^{(2)}+\cdots,
$$

where $\phi^{(n)}$ is order $J^n$. The first term is sourced linearly by the boundary value:

$$
\phi^{(1)}(X)=\int d^d x\,K_\Delta(X;x)J(x).
$$

The next correction is obtained by inverting the wave operator with the bulk-to-bulk propagator:

$$
\phi^{(2)}(X)
=
-\frac{g}{2}
\int dY\sqrt{g(Y)}\,G_\Delta(X,Y)\left[\phi^{(1)}(Y)\right]^2.
$$

Substituting the solution into $S_{\text{on-shell}}$ and expanding in powers of $J$ produces precisely the Witten diagrams. The quadratic part gives the two-point function, the cubic interaction gives the three-point contact diagram, and higher orders generate contact and exchange diagrams.

This derivation also explains why there is no integration over the boundary insertion points $x_i$ after differentiation with respect to sources. The boundary points are fixed by the functional derivatives. Only interior vertices are integrated over.

## Contact diagrams

A contact Witten diagram has a single bulk vertex. For scalar external operators it has the universal form

$$
D_{\Delta_1\cdots\Delta_n}(x_1,\ldots,x_n)
=
\int_{\mathrm{AdS}}dX\sqrt g\,
K_{\Delta_1}(X;x_1)\cdots K_{\Delta_n}(X;x_n),
$$

up to normalization constants. These integrals are often called $D$-functions.

For $n=3$, conformal symmetry fixes the full position dependence, so the contact integral can only determine the overall three-point coefficient. For $n=4$, conformal symmetry leaves two independent cross ratios, so a contact integral gives a nontrivial function of those cross ratios. Four-point contact diagrams are therefore the first place where dynamical bulk locality becomes visible in a way not fixed by conformal symmetry alone.

Derivative interactions modify the integrand. For instance,

$$
S_{\rm int}
\supset
\int dX\sqrt g\,h_{123}\,\phi_1\nabla_M\phi_2\nabla^M\phi_3
$$

contributes an integral of the form

$$
-h_{123}\int dX\sqrt g\,
K_1(X;x_1)
\nabla_M K_2(X;x_2)
\nabla^M K_3(X;x_3).
$$

By integration by parts and the equations of motion, derivative cubic couplings among scalars can often be rewritten as non-derivative couplings plus boundary/contact terms. At four points and beyond, derivative interactions carry more dynamical information.

## Exchange diagrams

Exchange diagrams have at least two bulk vertices connected by an internal bulk propagator. They encode the contribution of an intermediate bulk particle. In CFT language, this corresponds to the contribution of the dual single-trace operator and its conformal descendants to an OPE channel.

For example, in a four-point function of scalar operators,

$$
\mathcal O_1(x_1)\mathcal O_2(x_2)
\sim
\sum_{\chi} C_{12\chi}\,|x_{12}|^{\Delta_\chi-\Delta_1-\Delta_2}
\left[\mathcal O_\chi(x_2)+\text{descendants}\right]+
\cdots,
$$

and the exchange of the bulk field $\chi$ gives the single-trace conformal block of $\mathcal O_\chi$, mixed with contact-term ambiguities depending on how the exchange diagram is represented.

At large $N$, four-point functions also contain double-trace operators schematically of the form

$$
[\mathcal O_1\mathcal O_2]_{n,\ell},
$$

whose leading dimensions are

$$
\Delta_1+\Delta_2+2n+\ell+O(1/N^2).
$$

Contact diagrams and exchange diagrams determine the anomalous dimensions and OPE coefficients of these double-trace operators at subleading order in $1/N$.

## Large $N$ counting

For normalized single-trace operators, connected correlators in a large-$N$ gauge theory scale schematically as

$$
\langle \mathcal O_1\cdots\mathcal O_n\rangle_{\rm conn}
\sim
N^{2-n}.
$$

In a weakly coupled bulk theory, this appears because canonically normalized bulk interactions are suppressed by powers of the gravitational coupling. In AdS$_5$/CFT$_4$,

$$
\frac{L^3}{G_5}\sim N^2.
$$

After canonical normalization of bulk fields, a cubic vertex scales like $1/N$, a quartic vertex scales like $1/N^2$, and each bulk loop brings further suppression. Thus:

$$
\begin{array}{ccl}
\text{tree-level three-point diagram} &\sim& 1/N,\\
\text{tree-level connected four-point diagram} &\sim& 1/N^2,\\
\text{one-loop correction to a two-point function} &\sim& 1/N^2.
\end{array}
$$

This is the diagrammatic form of large-$N$ factorization.

Be careful: different communities normalize operators differently. If operators are not normalized to have $O(N^0)$ two-point functions, these powers of $N$ shift. The invariant statement is the relative suppression of connected correlators and bulk loops.

## Relation to flat-space Feynman diagrams

Witten diagrams resemble Feynman diagrams because they are built from propagators and vertices. But the interpretation differs in several ways.

First, AdS has a timelike boundary, so the natural observables are boundary correlators, not an ordinary S-matrix. Boundary-to-bulk legs attach to operator insertions rather than asymptotic scattering states.

Second, AdS curvature matters. A bulk vertex is integrated over a curved spacetime, and the propagators know about the boundary conditions at infinity. The result is constrained by conformal symmetry rather than by Poincare momentum conservation alone.

Third, an AdS diagram automatically packages infinitely many boundary descendants. A single bulk exchange field corresponds not just to a primary operator, but to the primary plus all descendants in the relevant conformal block decomposition.

There is nevertheless a deep relation to flat-space scattering. In a large-radius limit, or through Mellin-space representations, Witten diagrams can make contact with flat-space amplitudes. That viewpoint is powerful, but it is not needed for the first pass through the dictionary.

## Euclidean versus Lorentzian diagrams

The cleanest introductory setting is Euclidean AdS. The Euclidean prescription chooses the regular solution in the interior and produces Euclidean CFT correlators.

Lorentzian AdS/CFT requires extra choices. Depending on the desired correlator, one must impose different boundary and horizon conditions. For example, retarded finite-temperature correlators are obtained by imposing incoming-wave conditions at a black-hole horizon. Real-time Witten diagrams can be formulated carefully using Schwinger–Keldysh contours, but the diagrams are no longer just the naive Euclidean pictures with $t\to -it$.

A safe rule is:

$$
\text{Euclidean Witten diagrams are boundary-value problems;}
$$

$$
\text{Lorentzian Witten diagrams are boundary-value problems plus causal prescriptions.}
$$

This course first develops the Euclidean technology, then returns to real-time correlators in the thermal unit.

## Spin, gauge fields, and gravitons

The scalar diagrams are the cleanest starting point, but the same idea applies to fields with spin.

A bulk gauge field $A_M$ is dual to a conserved current $J^i$. Its boundary-to-bulk propagator carries a boundary vector index and a bulk vector index. Gauge redundancy forces one to fix a gauge or work with gauge-invariant objects, and the resulting correlators satisfy current Ward identities.

A metric perturbation $h_{MN}$ is dual to the stress tensor $T^{ij}$. Graviton Witten diagrams compute stress-tensor correlators and mixed correlators involving $T^{ij}$. They are more technically involved because of diffeomorphism invariance, gauge fixing, ghost terms in loops, and tensor structures.

Spinor fields are dual to fermionic operators. Their boundary conditions are first order, so the source/response split differs from the scalar case, but the diagrammatic principle remains the same.

The abstract rule is:

$$
\text{bulk representation data}
\quad\longleftrightarrow\quad
\text{boundary conformal tensor structures}.
$$

## A practical workflow

When computing a tree-level Witten diagram, proceed as follows.

### Step 1: Identify the fields and operators

For each boundary operator $\mathcal O_i$, identify the dual bulk field $\phi_i$, its mass, spin, and normalization. For a scalar, this means fixing $m_i^2L^2=\Delta_i(\Delta_i-d)$.

### Step 2: Normalize the two-point functions

OPE coefficients are meaningful only after choosing two-point-function normalizations. If

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{\mathcal N_i\delta_{ij}}{|x|^{2\Delta_i}},
$$

then the normalized operators are

$$
\widehat{\mathcal O}_i=\frac{\mathcal O_i}{\sqrt{\mathcal N_i}}.
$$

The normalized three-point coefficient differs from the raw Witten-diagram coefficient by the corresponding factors of $\mathcal N_i^{-1/2}$.

### Step 3: Write the relevant bulk interaction

Read off the vertex from the bulk action. For scalar contact diagrams, this may be as simple as

$$
S_{\rm int}=g_{123}\int dX\sqrt g\,\phi_1\phi_2\phi_3.
$$

For spinning fields or derivative interactions, include the appropriate covariant derivatives, index contractions, and possible boundary terms.

### Step 4: Build the diagram

Replace each external field by a boundary-to-bulk propagator and integrate over all interior vertices. For a three-point contact diagram,

$$
W^{(3)}[J]
=
-g_{123}
\int dX\sqrt g
\prod_{i=1}^3
\left[
\int d^d x_i\,K_{\Delta_i}(X;x_i)J_i(x_i)
\right].
$$

Differentiate with respect to $J_i(x_i)$ and set $J=0$.

### Step 5: Renormalize and interpret

Some diagrams are finite as written. Others require holographic counterterms, especially when there are derivative interactions, coincident points, logarithmic divergences, or special relations among dimensions. Separate universal nonlocal data from scheme-dependent contact terms.

## Dictionary checkpoint

The Witten-diagram dictionary is:

| Bulk object | Boundary meaning |
|---|---|
| boundary-to-bulk propagator $K_\Delta(X;x)$ | insertion/source for $\mathcal O(x)$ |
| bulk-to-bulk propagator $G_\Delta(X,Y)$ | exchange of a single-trace primary and descendants |
| local bulk vertex | CFT interaction/OPE data |
| tree diagram | leading connected large-$N$ correlator |
| bulk loop | $1/N$ correction |
| derivative vertex | momentum/position dependence and tensor-structure data |
| boundary counterterm | contact term or scheme choice |

The short version is:

$$
\text{Witten diagrams compute CFT correlators by integrating bulk interactions over AdS.}
$$

## Common confusions

### “A Witten diagram is a scattering amplitude.”

Not directly. It is a boundary correlation function. In special limits one can extract flat-space scattering information, but the basic object is a CFT correlator with boundary insertions.

### “External legs are particles entering AdS.”

In Euclidean AdS/CFT, external legs are boundary-to-bulk propagators sourced by boundary data. They are not normalizable wave packets unless one builds a Lorentzian state with the appropriate source profile.

### “Only contact diagrams matter for CFT data.”

No. Three-point functions of scalar primaries are fixed in position dependence by conformal symmetry, so a single cubic contact diagram is enough to extract one coefficient. Four-point functions are far richer: exchange diagrams, contact diagrams, and loops all contribute to functions of cross ratios.

### “The diagram automatically gives the physical OPE coefficient.”

It gives a coefficient in a chosen normalization. To get the OPE coefficient used in CFT conventions, normalize the two-point functions of the external operators and track all factors in the bulk kinetic terms.

### “Counterterms are only for two-point functions.”

No. Interacting on-shell actions can produce divergences and contact-term ambiguities at higher points. Holographic renormalization applies to the full generating functional.

## Exercises

### Exercise 1: Scaling of a contact diagram

Consider the three-point scalar contact integral

$$
I_3(x_1,x_2,x_3)
=
\int_{\mathrm{AdS}}dX\sqrt g\,
K_{\Delta_1}(X;x_1)K_{\Delta_2}(X;x_2)K_{\Delta_3}(X;x_3).
$$

Use the Poincare AdS scaling symmetry

$$
z\to \lambda z,
\qquad
x\to \lambda x
$$

to show that

$$
I_3(\lambda x_1,\lambda x_2,\lambda x_3)
=
\lambda^{-(\Delta_1+\Delta_2+\Delta_3)}I_3(x_1,x_2,x_3).
$$

<details>
<summary><strong>Solution</strong></summary>

Under the simultaneous scaling $z\to\lambda z$ and $x\to\lambda x$, the AdS measure is invariant:

$$
d^{d+1}X\sqrt g
=
\frac{dz\,d^dx}{z^{d+1}}
\quad\longrightarrow\quad
\frac{\lambda dz\,\lambda^d d^dx}{(\lambda z)^{d+1}}
=
\frac{dz\,d^dx}{z^{d+1}}.
$$

The boundary-to-bulk propagator obeys

$$
K_\Delta(\lambda z,\lambda x;\lambda x_i)
=
\lambda^{-\Delta}K_\Delta(z,x;x_i).
$$

Multiplying the three propagators gives the scaling factor

$$
\lambda^{-\Delta_1}\lambda^{-\Delta_2}\lambda^{-\Delta_3}.
$$

Therefore

$$
I_3(\lambda x_1,\lambda x_2,\lambda x_3)
=
\lambda^{-(\Delta_1+\Delta_2+\Delta_3)}I_3(x_1,x_2,x_3).
$$

This is exactly the scaling expected of a CFT three-point function.

</details>

### Exercise 2: Why a cubic vertex gives a three-point function

Let

$$
S_{\rm int}=\frac{g}{3!}\int dX\sqrt g\,\phi^3.
$$

Using

$$
\phi^{(1)}(X)=\int d^dx\,K_\Delta(X;x)J(x),
$$

show that the order-$J^3$ contribution to $W[J]$ is

$$
W^{(3)}[J]
=
-\frac{g}{3!}
\int dX\sqrt g
\prod_{a=1}^3
\left[\int d^dx_a\,K_\Delta(X;x_a)J(x_a)\right].
$$

Then explain why differentiating three times with respect to $J$ removes the factor $3!$.

<details>
<summary><strong>Solution</strong></summary>

At leading order in the interaction, one substitutes the linear solution into the interaction term. Since $W[J]\approx -S_{\text{on-shell}}[J]$, the cubic contribution is

$$
W^{(3)}[J]
=
-\frac{g}{3!}
\int dX\sqrt g\,\left[\phi^{(1)}(X)\right]^3.
$$

Inserting

$$
\phi^{(1)}(X)=\int d^dx\,K_\Delta(X;x)J(x)
$$

gives the stated expression.

The connected three-point function is

$$
\frac{\delta^3 W[J]}{\delta J(y_1)\delta J(y_2)\delta J(y_3)}\bigg|_{J=0}.
$$

The three functional derivatives can act on the three identical source factors in $3!$ equivalent ways. This cancels the explicit $1/3!$, leaving

$$
-g\int dX\sqrt g\,
K_\Delta(X;y_1)K_\Delta(X;y_2)K_\Delta(X;y_3).
$$

</details>

### Exercise 3: Exchange diagrams and OPE channels

Consider the four-point exchange diagram

$$
\int dX\sqrt g\int dY\sqrt g\,
K_1(X;x_1)K_2(X;x_2)G_\chi(X,Y)K_3(Y;x_3)K_4(Y;x_4).
$$

Which OPE channel is naturally associated with this drawing, and what single-trace operator appears in that channel?

<details>
<summary><strong>Solution</strong></summary>

The drawing groups $x_1,x_2$ at one vertex and $x_3,x_4$ at the other. It is therefore naturally associated with the $12\to34$ channel, or equivalently the OPE limit $x_1\to x_2$ and $x_3\to x_4$.

The internal bulk propagator $G_\chi(X,Y)$ belongs to a bulk field $\chi$. The dual boundary primary $\mathcal O_\chi$ appears as the exchanged single-trace operator in the $\mathcal O_1\times\mathcal O_2$ OPE. The exchange diagram includes the contribution of $\mathcal O_\chi$ and its conformal descendants. In the full four-point function, there are also double-trace contributions and possibly exchange diagrams in other channels.

</details>

## Further reading

- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).
- D. Z. Freedman, S. D. Mathur, A. Matusis, and L. Rastelli, [Correlation Functions in the CFT$_d$/AdS$_{d+1}$ Correspondence](https://arxiv.org/abs/hep-th/9804058).
- E. D'Hoker and D. Z. Freedman, [General Scalar Exchange in AdS$_{d+1}$](https://arxiv.org/abs/hep-th/9811257).
- J. Penedones, [TASI Lectures on AdS/CFT](https://arxiv.org/abs/1608.04948).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151).
