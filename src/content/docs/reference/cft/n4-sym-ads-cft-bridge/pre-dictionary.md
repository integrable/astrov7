---
title: "The Pre-AdS/CFT Dictionary"
description: "The CFT data-to-bulk data map: sources, operators, fields, symmetries, large N, and the first holographic rules."
sidebar:
  order: 4
---

## Goal

This page closes the CFT preparation course by assembling the **pre-AdS/CFT dictionary**. The word “pre” is important. We are not yet deriving holographic renormalization, computing Witten diagrams, or proving a duality. Instead, we are identifying the CFT structures that are about to become bulk structures.

The basic claim of AdS/CFT is not merely that two theories have the same symmetry group. It is that the complete quantum theory of gravity on an asymptotically AdS spacetime is encoded in the CFT generating functional. In its most compressed form, the dictionary says

$$
Z_{\mathrm{CFT}}[J_i]
=
Z_{\mathrm{bulk}}\big[\phi_i\to J_i\big].
$$

The left-hand side is the generating functional of CFT correlators in the presence of sources $J_i(x)$ for local operators $\mathcal O_i(x)$. The right-hand side is the bulk string/gravity path integral with boundary conditions fixed by those same functions $J_i(x)$. In the semiclassical limit,

$$
Z_{\mathrm{bulk}}\big[\phi_i\to J_i\big]
\approx
\exp\big(-S_{\mathrm{bulk,on\ shell}}[J_i]\big),
$$

so CFT correlators are obtained by differentiating the renormalized on-shell bulk action with respect to boundary data.

The most important moral is this:

$$
\boxed{
\text{The bulk is not added to the CFT. The bulk is a reorganization of CFT data.}
}
$$

<figure class="doc-figure" style="--figure-width: 44rem; --caption-width: 55rem;">

![The pre-AdS/CFT dictionary](/figures/cft/pre-dictionary-map.svg)

<figcaption>

The pre-AdS/CFT dictionary identifies CFT sources, operators, symmetries, and large-$N$ structures with bulk fields, boundary conditions, gauge redundancies, and particle states. The central relation is the equality of generating functionals $Z_{\rm CFT}[J]=Z_{\rm bulk}[\phi\to z^{d-\Delta}J]$.

</figcaption>
</figure>

## The generating-functional statement

Start with a CFT deformed by sources:

$$
S_{\mathrm{CFT}}
\longrightarrow
S_{\mathrm{CFT}}+
\int d^dx\,J_i(x)\mathcal O_i(x).
$$

The Euclidean generating functional is

$$
Z_{\mathrm{CFT}}[J_i]
=
\left\langle
\exp\left[-\int d^dx\,J_i(x)\mathcal O_i(x)\right]
\right\rangle_{\mathrm{CFT}},
$$

up to the sign convention chosen for source couplings. Functional derivatives generate correlation functions:

$$
\left\langle \mathcal O_{i_1}(x_1)\cdots \mathcal O_{i_n}(x_n)\right\rangle
=
(-1)^n
\frac{1}{Z_{\mathrm{CFT}}[0]}
\frac{\delta^n Z_{\mathrm{CFT}}[J]}{\delta J_{i_1}(x_1)\cdots \delta J_{i_n}(x_n)}
\bigg|_{J=0}.
$$

AdS/CFT interprets $J_i(x)$ as the boundary value of a bulk field $\phi_i$. Schematically,

$$
J_i(x)
\quad\longleftrightarrow\quad
\phi_i\big|_{\partial \mathrm{AdS}}.
$$

Thus the CFT operation “turn on a source for $\mathcal O_i$” becomes the bulk operation “solve the bulk equations with a prescribed boundary condition for $\phi_i$.” This is the cleanest way to remember the dictionary: **sources are boundary conditions, operators are responses**.

More precisely, for Euclidean $\mathrm{AdS}_{d+1}$ in Poincare coordinates,

$$
ds^2
=
\frac{L^2}{z^2}\left(dz^2+d x^\mu d x_\mu\right),
\qquad z>0,
$$

the boundary is at $z=0$. A scalar field of mass $m$ behaves near the boundary as

$$
\phi(z,x)
\sim
z^{d-\Delta}J(x)+z^\Delta A(x)+\cdots.
$$

The coefficient $J(x)$ is the source for the dual CFT operator $\mathcal O(x)$. The coefficient $A(x)$ is related, after holographic renormalization, to the one-point function $\langle \mathcal O(x)\rangle_J$ in the presence of the source.

The scaling dimension $\Delta$ is fixed by the bulk mass:

$$
m^2L^2=\Delta(\Delta-d).
$$

Equivalently,

$$
\Delta_\pm
=
\frac d2\pm\sqrt{\frac{d^2}{4}+m^2L^2}.
$$

The standard quantization usually takes $\Delta=\Delta_+$. In the Breitenlohner--Freedman window

$$
-\frac{d^2}{4}< m^2L^2< -\frac{d^2}{4}+1,
$$

there is also an alternate quantization in which the roles of the two asymptotic modes are exchanged. At the exact BF bound the two roots coincide and logarithmic boundary behavior requires separate treatment. For a first reading of AdS/CFT, one should master standard quantization first and treat alternate quantization as a controlled refinement.

## Operator versus source

A CFT operator and its source have complementary scaling dimensions. If

$$
\mathcal O(x)\mapsto \lambda^{-\Delta}\mathcal O(\lambda x),
$$

then the source term

$$
\int d^dx\,J(x)\mathcal O(x)
$$

is scale invariant when

$$
J(x)\mapsto \lambda^{\Delta-d}J(\lambda x).
$$

So the source $J$ has engineering dimension

$$
[J]=d-\Delta.
$$

This explains the boundary behavior

$$
\phi(z,x)\sim z^{d-\Delta}J(x)+z^\Delta A(x).
$$

The leading mode has precisely the scaling needed to represent a source. The subleading mode has precisely the scaling expected of a response controlled by an operator of dimension $\Delta$.

A useful slogan is

$$
\boxed{
\text{source mode } z^{d-\Delta}
\quad\leftrightarrow\quad
\text{deformation of the CFT action},
}
$$

while

$$
\boxed{
\text{response mode } z^\Delta
\quad\leftrightarrow\quad
\text{state-dependent expectation value}
}
$$

This distinction is everywhere in holography: scalar condensates, stress tensors, currents, black holes, entanglement, and double-trace deformations all depend on keeping source and response conceptually separate.

## Symmetry dictionary

The simplest entry is the symmetry match:

$$
\mathrm{Isom}(\mathrm{AdS}_{d+1})=SO(d,2)
=
\mathrm{Conf}(\mathbb R^{d-1,1}).
$$

This is why conformal symmetry was unavoidable in the first place. The CFT conformal group is the bulk AdS isometry group. In global AdS, radial quantization becomes especially transparent: the CFT cylinder Hamiltonian is the bulk global time generator, and a CFT primary of dimension $\Delta$ creates a bulk state of energy

$$
E L=\Delta.
$$

The descendants created by $P_\mu$ correspond to excitations carrying angular momentum and radial structure in global AdS. This is the same representation theory viewed from two sides.

The stress tensor and conserved currents are the next universal entries:

| CFT structure | Bulk structure | Reason |
|---|---|---|
| $T_{\mu\nu}$ | metric $g_{MN}$ | $T_{\mu\nu}$ couples to the boundary metric and generates spacetime symmetries |
| flavor current $J^a_\mu$ | gauge field $A^a_M$ | global CFT symmetry becomes bulk gauge redundancy |
| scalar primary $\mathcal O_\Delta$ | scalar field $\phi$ | source $J$ is boundary value of $\phi$ |
| exactly marginal operator | massless scalar modulus | changing the coupling moves along a conformal manifold |
| Wilson loop | string worldsheet or brane object | loop expectation values are computed by extended bulk saddles |

The stress tensor entry is especially important. The CFT source for $T_{\mu\nu}$ is the background metric $g^{(0)}_{\mu\nu}$:

$$
\delta S_{\mathrm{CFT}}
=
\frac12\int d^dx\sqrt{g^{(0)}}\,\delta g^{(0)}_{\mu\nu}T^{\mu\nu}.
$$

Therefore the bulk field whose boundary value is $g^{(0)}_{\mu\nu}$ must be the bulk metric. The graviton is not optional in an AdS dual of a local CFT with a stress tensor.

Similarly, if a CFT has a conserved current $J^a_\mu$, then the source is a background gauge field $A^{a(0)}_\mu$:

$$
\delta S_{\mathrm{CFT}}
=
\int d^dx\,A^{a(0)}_\mu J^{a\mu}.
$$

The dual bulk field is a gauge field $A^a_M$. The global symmetry is global on the boundary because the gauge parameter is fixed at the boundary; in the interior it is a gauge redundancy.

## Central charges and bulk couplings

The normalization of stress-tensor correlators measures the number of CFT degrees of freedom. In a holographic CFT this number is proportional to the inverse bulk Newton constant:

$$
C_T\sim \frac{L^{d-1}}{G_N}.
$$

The exact numerical coefficient depends on conventions for $C_T$ and the gravitational action, but the scaling is the invariant statement. Large $C_T$ means weak bulk quantum gravity:

$$
\frac{G_N}{L^{d-1}}\sim \frac{1}{C_T}\ll 1.
$$

For adjoint large-$N$ gauge theories,

$$
C_T\sim N^2,
$$

so the genus expansion of the bulk string theory is the $1/N$ expansion of the CFT. Connected correlators of canonically normalized single-trace operators obey

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_{\mathrm{conn}}
\sim
N^{2-n}.
$$

This is the CFT origin of weak bulk interactions. A three-point coefficient of order $1/N$ is a cubic coupling suppressed by the bulk Planck scale. A connected four-point function of order $1/N^2$ is a tree-level exchange or contact process in the bulk.

## Spectrum dictionary: single-trace and multi-trace

In a large-$N$ CFT, the most important structural distinction is

$$
\text{single-trace}
\quad\text{versus}\quad
\text{multi-trace}.
$$

For a matrix gauge theory, single-trace operators have the schematic form

$$
\mathcal O_{\mathrm{st}}(x)
=
\frac{1}{N}\operatorname{Tr}\big(X_1X_2\cdots X_L\big)(x),
$$

with normalization chosen so that their two-point functions are order one. These map to single-particle bulk states:

$$
\mathcal O_{\mathrm{st}}
\quad\leftrightarrow\quad
\text{one bulk particle or one string state}.
$$

Multi-trace operators, after subtracting descendants and lower-trace mixing, map to multi-particle states:

$$
[\mathcal O_1\mathcal O_2]_{n,\ell}
\quad\leftrightarrow\quad
\text{two-particle AdS state}.
$$

At leading order in large $N$, their dimensions are additive:

$$
\Delta_{12,n,\ell}^{(0)}
=
\Delta_1+\Delta_2+2n+\ell.
$$

At subleading order,

$$
\Delta_{12,n,\ell}
=
\Delta_1+\Delta_2+2n+\ell
+\gamma_{12,n,\ell},
$$

where $\gamma_{12,n,\ell}$ is the anomalous dimension. In the bulk, this is an interaction energy or binding energy. Thus large-$N$ CFT perturbation theory literally becomes perturbation theory for particles interacting in AdS.

The OPE coefficient dictionary is equally direct:

$$
C_{ijk}
\quad\leftrightarrow\quad
\text{bulk cubic coupling among }\phi_i,\phi_j,\phi_k.
$$

More generally, CFT four-point data encode exchange diagrams, contact interactions, loop corrections, and locality constraints.

## Local bulk physics is an extra condition

A large-$N$ CFT does not automatically have a weakly curved Einstein-gravity dual. Large $N$ gives a weakly coupled bulk in the sense of factorization, but the bulk may still be stringy or nonlocal at the AdS scale.

For an ordinary local effective field theory in AdS, one wants a large gap to higher-spin single-trace operators:

$$
\Delta_{\mathrm{gap}}\gg 1.
$$

Here $\Delta_{\mathrm{gap}}$ is the dimension of the lightest single-trace operator with spin greater than two, or more broadly the gap to genuinely stringy single-particle states. A sparse low-lying spectrum allows the low-energy bulk theory to be described by a small number of light fields.

The hierarchy is therefore:

$$
\begin{array}{ccl}
\text{large }C_T &\Longleftrightarrow& \text{weak bulk quantum gravity},\\
\text{sparse single-trace spectrum} &\Longleftrightarrow& \text{local bulk EFT},\\
\Delta_{\mathrm{gap}}\gg1 &\Longleftrightarrow& \text{Einstein-like gravity regime}.
\end{array}
$$

For $\mathcal N=4$ SYM, the role of this gap is controlled by the 't Hooft coupling

$$
\lambda=g_{\mathrm{YM}}^2N.
$$

In the standard normalization of the $\mathrm{AdS}_5\times S^5$ dual,

$$
\frac{L^4}{\alpha'^2}=\lambda,
$$

so strong coupling makes the AdS radius large compared with the string length:

$$
\frac{L^2}{\alpha'}=\sqrt{\lambda}\gg1.
$$

This is why classical supergravity requires both

$$
N\gg1,
\qquad
\lambda\gg1.
$$

Finite $N$ gives quantum gravity corrections. Finite $\lambda$ gives stringy $\alpha'$ corrections.

## The canonical $\mathcal N=4$ SYM parameter map

For the standard example,

$$
\mathcal N=4\ \mathrm{SYM\ with\ gauge\ group}\ SU(N)
\quad\longleftrightarrow\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5,
$$

the main parameter relations are

$$
\frac{L^4}{\alpha'^2}=\lambda,
\qquad
4\pi g_s=g_{\mathrm{YM}}^2,
\qquad
\lambda=4\pi g_s N.
$$

Conventions for factors of $2\pi$ vary, but the physical meanings are stable:

$$
\begin{array}{ccl}
N\to\infty &\Longleftrightarrow& g_s\to0\ \text{at fixed }\lambda,\\
\lambda\to\infty &\Longleftrightarrow& L\gg \ell_s,\\
N\gg1,\ \lambda\gg1 &\Longleftrightarrow& \text{classical type IIB supergravity}.
\end{array}
$$

The protected half-BPS chiral primaries discussed earlier map to Kaluza--Klein modes on $S^5$. Long unprotected single-trace operators map to massive string states. Wilson loops map to string worldsheets ending on boundary curves. The stress tensor maps to the graviton. The $SU(4)_R\simeq SO(6)_R$ currents map to gauge fields arising from the isometries of $S^5$.

## Thermal and Lorentzian entries

The Euclidean dictionary is often the first one learned, but real-time physics is equally central. Thermal CFT states correspond to asymptotically AdS black holes or black branes. For a planar thermal state,

$$
T\neq0
\quad\leftrightarrow\quad
\text{AdS black brane with Hawking temperature }T.
$$

Entropy density scales as

$$
s\sim C_T T^{d-1},
$$

which matches the area density of the black-brane horizon in Planck units. Retarded correlators are computed by imposing infalling boundary conditions at the horizon. The simple mnemonic is

$$
G_R(\omega,\mathbf k)
\quad\leftrightarrow\quad
\text{bulk wave equation with infalling horizon behavior}.
$$

Entanglement has its own geometric entry. For holographic CFT states with a classical bulk dual, the leading large-$N$ entanglement entropy of a spatial region $A$ is computed by an extremal surface $\gamma_A$:

$$
S_A
=
\frac{\operatorname{Area}(\gamma_A)}{4G_N}
+\cdots.
$$

The dots denote quantum bulk corrections and higher-derivative corrections. From the CFT side, this is a statement about the reduced density matrix and the modular structure of the state. From the bulk side, it is a statement about geometry emerging from entanglement data.

## What is and is not being claimed

The dictionary is powerful, but it is easy to overstate it. The safe statements are:

- every bulk field corresponds to a CFT operator,
- every boundary condition for that field corresponds to a CFT source,
- bulk symmetries act as CFT global or spacetime symmetries,
- bulk interactions are encoded in OPE coefficients and higher-point functions,
- weakly coupled bulk physics requires large-$N$ factorization,
- local Einstein gravity requires more than large $N$: it also requires a sparse spectrum and a large gap.

The unsafe statement is: “every CFT has a simple geometric bulk.” That is not true. A generic CFT may have a valid AdS representation only as a highly stringy, strongly quantum, non-geometric theory. Geometry is an emergent special regime, not an automatic consequence of conformal symmetry.

It is also misleading to imagine the dictionary as a one-to-one map between elementary CFT fields and elementary bulk fields. The CFT elementary variables may not be gauge invariant, may depend on a Lagrangian description, and may not exist in a non-Lagrangian CFT. The dictionary is formulated in terms of **gauge-invariant local operators and their correlation functions**.

## Minimal checklist before starting AdS/CFT

At this point, the essential CFT concepts are in place. Before reading a serious AdS/CFT paper, one should be comfortable with the following translations:

| CFT question | Bulk translation |
|---|---|
| What is the scaling dimension $\Delta$? | What is the bulk mass $m^2L^2$? |
| What is the source $J$? | What is the boundary value of $\phi$? |
| What is $\langle \mathcal O\rangle_J$? | What is the normalizable response mode? |
| What is $C_T$? | What is $L^{d-1}/G_N$? |
| Is there a conserved current? | Is there a bulk gauge field? |
| Is the operator single-trace? | Is the state single-particle? |
| Are correlators factorized? | Is the bulk weakly coupled? |
| Is there a large higher-spin gap? | Is the bulk local and weakly curved? |
| What is the thermal state? | What is the black hole or black brane? |
| What is the Wilson loop? | What string worldsheet ends on it? |

This is the conceptual bridge from modern CFT to AdS/CFT. The next step is to choose a bulk coordinate system, solve bulk equations near the boundary, renormalize the on-shell action, and compute correlators directly.

## Exercises

### Exercise 1: derive the scalar mass-dimension relation

Consider a scalar field in Euclidean $\mathrm{AdS}_{d+1}$ with metric

$$
ds^2=\frac{L^2}{z^2}\left(dz^2+dx^\mu dx_\mu\right).
$$

Near the boundary, ignore derivatives along $x^\mu$ and solve the massive wave equation

$$
(\nabla^2-m^2)\phi=0
$$

with the ansatz $\phi(z,x)\sim z^\alpha f(x)$. Show that

$$
\alpha(\alpha-d)=m^2L^2,
$$

and hence that $m^2L^2=\Delta(\Delta-d)$.

<details><summary><strong>Solution</strong></summary>

For the metric above,

$$
\sqrt g=\left(\frac Lz\right)^{d+1},
\qquad
 g^{zz}=\frac{z^2}{L^2}.
$$

Ignoring boundary derivatives, the Laplacian gives

$$
\nabla^2\phi
=
\frac1{\sqrt g}\partial_z\left(\sqrt g\,g^{zz}\partial_z\phi\right)
=
\frac{z^{d+1}}{L^{d+1}}\partial_z\left(L^{d-1}z^{1-d}\partial_z\phi\right).
$$

For $\phi=z^\alpha f(x)$,

$$
\nabla^2\phi
=
\frac{1}{L^2}\alpha(\alpha-d)z^\alpha f(x).
$$

The wave equation therefore requires

$$
\frac{1}{L^2}\alpha(\alpha-d)-m^2=0,
$$

or

$$
\alpha(\alpha-d)=m^2L^2.
$$

The two roots are $\alpha=d-\Delta$ and $\alpha=\Delta$, with

$$
m^2L^2=\Delta(\Delta-d).
$$

</details>

### Exercise 2: source dimension and boundary falloff

Suppose a scalar primary has scaling dimension $\Delta$. Show that its source has dimension $d-\Delta$. Explain why this is consistent with the leading near-boundary falloff $z^{d-\Delta}J(x)$ of the dual bulk field.

<details><summary><strong>Solution</strong></summary>

The source term is

$$
\int d^dx\,J(x)\mathcal O(x).
$$

Under $x\mapsto \lambda x$, the measure scales as $d^dx\mapsto \lambda^d d^dx$, while

$$
\mathcal O(x)\mapsto \lambda^{-\Delta}\mathcal O(\lambda x).
$$

For the deformation to be dimensionless, the source must scale as

$$
J(x)\mapsto \lambda^{\Delta-d}J(\lambda x),
$$

so its engineering dimension is $d-\Delta$.

In AdS, the radial coordinate $z$ scales like a boundary length. The near-boundary field

$$
\phi(z,x)\sim z^{d-\Delta}J(x)
$$

is invariant under the combined scaling $z\mapsto \lambda z$, $x\mapsto \lambda x$ if $J$ has dimension $d-\Delta$. Thus the source falloff is exactly what conformal covariance demands.

</details>

### Exercise 3: large-$N$ factorization and bulk interactions

Assume canonically normalized single-trace operators obey

$$
\langle \mathcal O_1\cdots \mathcal O_n\rangle_{\rm conn}\sim N^{2-n}.
$$

What does this imply for the scaling of bulk cubic and quartic interactions?

<details><summary><strong>Solution</strong></summary>

A CFT three-point coefficient of single-trace operators scales as

$$
C_{123}\sim \frac1N.
$$

In the bulk, a three-point function is computed at tree level by a cubic interaction, so the cubic coupling scales as

$$
g_3\sim \frac1N.
$$

Similarly, connected four-point functions scale as

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle_{\rm conn}
\sim
\frac1{N^2}.
$$

They can arise from two cubic vertices joined by an exchange propagator, giving $g_3^2\sim 1/N^2$, or from a quartic contact coupling with

$$
g_4\sim \frac1{N^2}.
$$

This is the CFT origin of weakly coupled bulk perturbation theory. In gravitational language,

$$
G_N/L^{d-1}\sim 1/N^2.
$$

</details>

### Exercise 4: why the stress tensor maps to the metric

Use source coupling to explain why the CFT stress tensor must be dual to the bulk metric rather than to an ordinary scalar or vector field.

<details><summary><strong>Solution</strong></summary>

The stress tensor is defined as the response of the CFT generating functional to a variation of the background metric:

$$
\delta W[g^{(0)}]
=
\frac12\int d^dx\sqrt{g^{(0)}}\,
\langle T^{\mu\nu}\rangle\delta g^{(0)}_{\mu\nu}.
$$

Thus the source for $T_{\mu\nu}$ is the boundary metric $g^{(0)}_{\mu\nu}$. In the bulk dictionary, sources are boundary values of bulk fields. Therefore the bulk field whose boundary value is $g^{(0)}_{\mu\nu}$ must be the bulk metric $g_{MN}$.

This also matches symmetry. The stress tensor generates spacetime transformations in the CFT. In the bulk, spacetime transformations are encoded by diffeomorphism invariance, whose gauge field is the metric. Hence

$$
T_{\mu\nu}\quad\leftrightarrow\quad g_{MN}.
$$

</details>

### Exercise 5: when does a large-$N$ CFT have an Einstein-like dual?

Explain why large $N$ is not enough to guarantee a weakly curved Einstein gravity dual. What extra spectral condition is needed?

<details><summary><strong>Solution</strong></summary>

Large $N$ gives factorization:

$$
\langle \mathcal O_1\cdots\mathcal O_n\rangle_{\rm conn}\sim N^{2-n}.
$$

This implies weak bulk interactions and a small bulk Newton constant. But weak coupling does not imply that the bulk is described by a local two-derivative gravity theory. The bulk may still contain stringy states with masses of order the AdS scale.

To obtain a local Einstein-like effective theory, the CFT should have a sparse low-lying single-trace spectrum and a large gap to higher-spin/stringy single-trace operators:

$$
\Delta_{\rm gap}\gg1.
$$

Then the low-energy bulk dynamics can be organized as an effective field theory with finitely many light fields. Without such a gap, the bulk description, if it exists, is stringy or nonlocal at the AdS scale.

</details>

## Takeaway

The whole course can be summarized as a single chain:

$$
\text{CFT data}
\quad\Rightarrow\quad
\text{large-}N\text{ organization}
\quad\Rightarrow\quad
\text{bulk fields and interactions}
\quad\Rightarrow\quad
\text{AdS geometry when the spectrum is sparse}.
$$

The first AdS/CFT computations will now look much less mysterious. A bulk scalar is not introduced out of nowhere: it is the representation-theoretic avatar of a scalar primary. A graviton is not optional: it is the source-response partner of $T_{\mu\nu}$. A Witten diagram is not a new kind of observable: it is a reorganization of CFT conformal blocks and OPE data. A black brane is not merely a geometry: it is a thermal large-$N$ CFT state.

This is the point at which modern CFT becomes holography.
