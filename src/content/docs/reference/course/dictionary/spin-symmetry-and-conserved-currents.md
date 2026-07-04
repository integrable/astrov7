---
title: "Spin, Symmetry, and Conserved Currents"
description: "How bulk fields of different spin encode scalar operators, fermionic operators, conserved currents, stress tensors, and boundary symmetries."
sidebar:
  order: 70
---

The scalar dictionary is the training ground, but AdS/CFT is not a dictionary only for scalar operators. A realistic holographic theory contains gauge fields, gravitons, spinors, $p$-forms, Kaluza–Klein modes, and sometimes higher-spin fields. Each bulk field is paired with boundary operator data: spin, scaling dimension, global-symmetry representation, and conservation laws.

The guiding rule is:

$$
\boxed{
\text{bulk field with specified boundary behavior}
\quad\longleftrightarrow\quad
\text{boundary operator with matching quantum numbers}.
}
$$

The most important entries are:

| Bulk object | Boundary object |
|---|---|
| scalar field $\phi$ | scalar operator $\mathcal O$ |
| Dirac spinor $\psi$ | fermionic operator $\mathcal O_\psi$ |
| gauge field $A_M$ | conserved current $J^i$ |
| metric $g_{MN}$ | stress tensor $T^{ij}$ |
| internal isometry gauge field | global-symmetry current |
| $p$-form gauge field | higher-form current or extended-object source |
| gravitino | supersymmetry current |
| massless higher-spin field | conserved higher-spin current |

This page explains why these pairings are natural, how dimensions are read off, and how bulk gauge redundancies become boundary Ward identities.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Bulk fields of different spin are mapped to boundary operators with matching quantum numbers: scalar to scalar operator, spinor to fermionic operator, gauge field to conserved current, and metric to stress tensor.](/figures/course/spin-symmetry-conserved-currents.svg)

<figcaption>

The spin and symmetry dictionary. The boundary value of a bulk scalar sources a scalar operator. A bulk spinor sources a fermionic operator. A bulk gauge field sources a conserved current associated with a boundary global symmetry. The bulk metric sources the stress tensor. Gauge invariance and diffeomorphism invariance are not optional decorations: they enforce the corresponding Ward identities.

</figcaption>
</figure>

## Why this matters

The scalar field teaches the source-response logic, but most of the physics in AdS/CFT comes from symmetry.

A thermal black brane is important because its metric response gives $\langle T^{ij}\rangle$. A finite-density state is described by a bulk gauge field because the boundary theory has a conserved current $J^i$. Holographic superconductors use charged bulk fields because the boundary operator transforms under a global symmetry. Supersymmetric examples organize fields into representations of spacetime symmetry, R-symmetry, and supersymmetry. Kaluza–Klein modes on $S^5$ remember the $SO(6)_R$ quantum numbers of $\mathcal N=4$ SYM operators.

So the dictionary is not just

$$
\phi \leftrightarrow \mathcal O.
$$

It is a matching of representation theory, boundary conditions, and variational principles.

## Boundary quantum numbers from bulk quantum numbers

A local operator in a $d$-dimensional CFT is labeled by several kinds of data:

$$
\mathcal O:
\qquad
(\Delta,\;\text{Lorentz spin},\;\text{global-symmetry representation},\;\text{conservation or shortening conditions}).
$$

A bulk field carries the same information in geometric form:

- its mass controls the boundary scaling dimension;
- its tangent-space indices control the Lorentz spin of the boundary operator;
- its charge under bulk gauge fields controls global-symmetry quantum numbers;
- its transformation under internal compact-space isometries controls R-symmetry or flavor representations;
- gauge invariance or diffeomorphism invariance imposes conservation laws.

The near-boundary limit turns bulk tangent indices parallel to the boundary into boundary Lorentz indices. For example, a bulk vector $A_M$ has boundary components $A_i$ and radial component $A_z$. In radial gauge, $A_z=0$, the leading boundary value of $A_i$ is the source for a vector operator $J^i$.

A bulk symmetric tensor fluctuation $h_{MN}$ has boundary components $h_{ij}$. These perturb the boundary metric and therefore source $T^{ij}$. A bulk Dirac spinor has boundary spinor components; because the Dirac equation is first order, only half of those components are independent sources.

## Scalar fields: the baseline

For a scalar field,

$$
(\nabla^2-m^2)\phi=0,
$$

the near-boundary powers are

$$
\phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)
+
z^\Delta A(x),
$$

with

$$
m^2L^2=\Delta(\Delta-d).
$$

The boundary source $\phi_{(0)}$ couples to a scalar primary:

$$
\int d^d x\sqrt{g_{(0)}}\,\phi_{(0)}\mathcal O.
$$

A scalar is simple because there is no gauge redundancy and no tensor constraint. Its conservation law is trivial. This is why scalar fields are the natural first example, but they hide some of the most important structure of holography.

## Spinors: first-order equations and half the boundary data

A bulk Dirac spinor satisfies

$$
(\Gamma^M D_M-m)\psi=0.
$$

Near the boundary, the two independent spinor components scale schematically as

$$
\psi(z,x)
\sim
z^{\frac d2-mL}\psi_{(0)}(x)
+
z^{\frac d2+mL}\psi_{(2mL)}(x),
$$

for $mL>0$ in standard quantization. The dual fermionic operator has dimension

$$
\boxed{
\Delta_\psi=\frac d2+|m|L
}
$$

in the standard quantization.

The important difference from scalars is that the Dirac equation is first order. One cannot fix all boundary components of $\psi$ independently. In a convenient convention, the radial gamma matrix $\Gamma^z$ splits the spinor into projected components,

$$
\psi_\pm
=
\frac12(1\pm\Gamma^z)\psi.
$$

One component is the source, and the conjugate component is the response. The precise assignment depends on the sign of $m$ and on gamma-matrix conventions.

The fermionic source term is schematically

$$
\int d^d x\sqrt{g_{(0)}}\,
\left(\bar\eta\,\mathcal O_\psi+\bar{\mathcal O}_\psi\eta\right),
$$

where $\eta$ is the boundary spinor source. In Lorentzian signature, careful treatment of reality conditions, boundary terms, and retarded versus Euclidean prescriptions is essential.

For this foundations course, the key lesson is:

$$
\text{bulk spinor mass}
\quad\longleftrightarrow\quad
\text{fermionic operator dimension},
$$

and

$$
\text{only half of the spinor boundary data are sources}.
$$

## Gauge fields and conserved currents

A bulk gauge field $A_M$ is dual to a conserved current $J^i$ in the boundary theory. The source coupling is

$$
\int d^d x\sqrt{g_{(0)}}\,A_{(0)i}J^i.
$$

For a massless Maxwell field,

$$
S_A
=
\frac{1}{4g_{d+1}^2}
\int d^{d+1}x\sqrt{g}\,F_{MN}F^{MN},
$$

the near-boundary expansion in radial gauge $A_z=0$ is schematically

$$
A_i(z,x)
=
A_{(0)i}(x)
+
\cdots
+
z^{d-2}A_{(d-2)i}(x)
+
\cdots.
$$

The leading coefficient $A_{(0)i}$ is a background gauge field for a global symmetry of the boundary theory. The response is the current expectation value:

$$
\langle J^i\rangle
=
-\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta S_{\rm ren}}{\delta A_{(0)i}}.
$$

Up to normalization and local terms,

$$
\langle J^i\rangle
\propto
A_{(d-2)}^i.
$$

The dual operator has protected dimension

$$
\boxed{
\Delta_J=d-1}
$$

because it is conserved:

$$
\nabla_iJ^i=0.
$$

This conservation law is the boundary imprint of bulk gauge invariance.

## Bulk gauge symmetry versus boundary global symmetry

A subtle but essential slogan is:

$$
\boxed{
\text{bulk gauge symmetry}
\quad\longleftrightarrow\quad
\text{boundary global symmetry}.
}
$$

At first this sounds backwards. Should a gauge field not mean a gauge symmetry on both sides?

The point is that $A_{(0)i}$ is normally a nondynamical background source in the boundary CFT. It lets us probe a global current. We are not, by default, integrating over $A_{(0)i}$ as a dynamical boundary gauge field. Boundary gauge transformations of $A_{(0)i}$ are redundancies of the background-field description, and they imply the Ward identity for the global current.

For an infinitesimal boundary gauge transformation,

$$
\delta A_{(0)i}=\partial_i\lambda,
$$

invariance of the generating functional gives

$$
0=\delta W
=
\int d^d x\sqrt{g_{(0)}}\,\langle J^i\rangle\partial_i\lambda
=
-
\int d^d x\sqrt{g_{(0)}}\,\lambda\nabla_i\langle J^i\rangle,
$$

so

$$
\nabla_i\langle J^i\rangle=0,
$$

assuming no charged sources are turned on.

If one changes the boundary conditions and integrates over the boundary gauge field, one can sometimes gauge the boundary symmetry. That is a different holographic theory or a different ensemble. It is not the default Dirichlet dictionary.

## Massive vectors and non-conserved vector operators

A massive bulk vector is not gauge redundant. Its dual is a vector operator that is generally not conserved. For a transverse vector operator, the mass-dimension relation is

$$
\boxed{
m^2L^2=(\Delta-1)(\Delta-d+1).
}
$$

If $m=0$, this relation allows

$$
\Delta=d-1
\qquad\text{or}\qquad
\Delta=1.
$$

For the ordinary conserved current in standard quantization, the physical choice is

$$
\Delta=d-1.
$$

The other root is related to alternate boundary conditions and special low-dimensional possibilities. For a standard unitary CFT in $d>2$, a conserved vector current saturates the spin-one unitarity bound and has $\Delta=d-1$.

Thus a massless bulk gauge field is not merely a vector field with $m=0$. The gauge invariance is what enforces the current conservation and protects the dimension.

## The metric and the stress tensor

The bulk metric is dual to the boundary stress tensor. The source is the boundary metric representative $g_{(0)ij}$:

$$
Z_{\rm CFT}[g_{(0)}]
=
Z_{\rm bulk}[g_{MN}\to g_{(0)ij}].
$$

The coupling is

$$
\frac12
\int d^d x\sqrt{g_{(0)}}\,g_{(0)ij}T^{ij}
$$

at the level of variations. More precisely,

$$
\delta W
=
\frac12
\int d^d x\sqrt{g_{(0)}}\,\langle T^{ij}\rangle\delta g_{(0)ij}.
$$

Therefore

$$
\langle T^{ij}\rangle
=
\frac{2}{\sqrt{g_{(0)}}}
\frac{\delta W}{\delta g_{(0)ij}}
=
-\frac{2}{\sqrt{g_{(0)}}}
\frac{\delta S_{\rm ren}}{\delta g_{(0)ij}},
$$

with our Euclidean source convention.

The stress tensor has protected dimension

$$
\boxed{\Delta_T=d}
$$

and obeys

$$
\nabla_iT^{ij}=0
$$

when no external sources are turned on.

In the bulk, the corresponding field is the graviton: a fluctuation of the metric. Diffeomorphism invariance is responsible for the stress-tensor Ward identities, just as gauge invariance is responsible for current conservation.

The full stress-tensor dictionary is important enough to deserve its own page. The present page gives the conceptual map; the next metric-focused pages will explain Brown–York tensors, counterterms, trace anomalies, and thermodynamic stress tensors.

## Diffeomorphisms and Ward identities

Boundary diffeomorphism invariance gives the stress-tensor Ward identity. If the only source is the metric, then

$$
\nabla_i\langle T^{ij}\rangle=0.
$$

If scalar and gauge sources are present, the Ward identity becomes schematically

$$
\nabla_i\langle T^{ij}\rangle
=
F_{(0)}^{ji}\langle J_i\rangle
+
\langle\mathcal O\rangle\nabla^j\phi_{(0)}
+
\cdots.
$$

The interpretation is ordinary field theory. External fields can exchange momentum with the system. The term $F^{ji}J_i$ is a Lorentz force density. The term involving $\nabla^j\phi_{(0)}$ says that a spatially varying scalar coupling can inject or remove momentum.

Boundary Weyl transformations give a trace Ward identity:

$$
\langle T^i_{\ i}\rangle
=
(d-\Delta)\phi_{(0)}\langle\mathcal O\rangle
+
\mathcal A.
$$

Here $\mathcal A$ is the conformal anomaly. In the bulk, this identity is encoded in radial diffeomorphisms and the logarithmic terms of the Fefferman–Graham expansion.

## Internal symmetries and compact dimensions

In the canonical example,

$$
\mathcal N=4\;\text{SYM}
\quad\longleftrightarrow\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5,
$$

the compact sphere has isometry group

$$
SO(6)\simeq SU(4)_R.
$$

This is the R-symmetry group of the boundary theory. Fluctuations of the metric and form fields along the $S^5$ directions produce five-dimensional gauge fields and other Kaluza–Klein modes. Their quantum numbers under $SO(6)$ match the R-symmetry representations of boundary operators.

This is a general lesson. Internal bulk geometry encodes internal boundary symmetries. A bulk gauge field may come from:

- an explicit gauge field in the lower-dimensional effective action;
- an isometry of a compact internal space;
- a higher-dimensional form field reduced on cycles of the compact space;
- flavor branes, which add global flavor symmetries in the probe approximation.

The boundary symmetry is usually global because the corresponding boundary gauge field is a source, not a dynamical variable.

## $p$-form fields and generalized global symmetries

Bulk $p$-form gauge fields couple naturally to extended objects. Near the boundary, their leading values source antisymmetric tensor operators or higher-form currents. Schematically,

$$
\int_{M_d} B_{(0),i_1\cdots i_p}J^{i_1\cdots i_p}.
$$

Modern language often describes these as generalized global symmetries. A conserved $q$-form current is associated with charged extended operators rather than charged local operators.

For a first AdS/CFT course, one does not need the full generalized-symmetry formalism. The useful lesson is that the scalar/vector/metric dictionary is part of a larger pattern:

$$
\text{bulk gauge redundancy of a field}
\quad\longrightarrow\quad
\text{boundary Ward identity for the dual current-like operator}.
$$

## Higher-spin fields and why they are special

A massless spin-$s$ field in AdS is dual to a conserved spin-$s$ current in the CFT. For example, a massless spin-two field is the graviton, dual to the stress tensor. A massless spin-one field is a gauge field, dual to a conserved current.

For $s>2$, the presence of massless higher-spin fields is highly constraining. A CFT with many exactly conserved higher-spin currents is typically close to a free or integrable theory. The bulk dual is not ordinary Einstein gravity; it is a higher-spin theory.

This is one reason the “large gap” condition matters. A CFT with a simple local Einstein-like bulk should have:

- a stress tensor;
- perhaps a small number of conserved currents;
- no infinite tower of low-dimension higher-spin conserved currents;
- a large gap before stringy or higher-spin single-trace operators appear.

In the canonical AdS$_5$/CFT$_4$ example, strong 't Hooft coupling makes many stringy operators heavy in AdS units. This is part of why a low-energy supergravity description emerges.

## Symmetry matching in one table

| Boundary structure | Bulk structure |
|---|---|
| conformal group $SO(2,d)$ | AdS$_{d+1}$ isometry group |
| global $U(1)$ or nonabelian symmetry | bulk gauge field |
| conserved current $J^i$ | massless vector field $A_M$ |
| stress tensor $T^{ij}$ | metric/graviton $g_{MN}$ |
| R-symmetry representation | internal-space quantum numbers |
| fermionic operator | bulk spinor |
| supersymmetry current | gravitino |
| Ward identity | bulk constraint equation or gauge redundancy |
| anomaly | logarithmic term or Chern–Simons/boundary contribution |

This table is not just mnemonic. It is a consistency condition. If a proposed bulk field has the wrong spin, wrong charge, wrong mass, or wrong boundary behavior, it cannot be dual to the claimed operator.

## Boundary conditions and ensembles

The same bulk field can define different boundary theories if different boundary conditions are chosen. This is especially important for gauge fields and gravity.

For a bulk scalar in the alternate-quantization window, either coefficient can be treated as the source. For a bulk gauge field in certain low-dimensional cases, one may choose boundary conditions that make the boundary gauge field dynamical. For gravity, changing boundary conditions for the metric can couple the CFT to dynamical gravity or alter the ensemble.

The default AdS/CFT dictionary used in this course is Dirichlet for sources:

$$
\text{fix }g_{(0)ij},\quad
\text{fix }A_{(0)i},\quad
\text{fix scalar sources},
$$

and vary the renormalized action with respect to those sources. This computes expectation values in a QFT placed on specified background fields.

Whenever a paper uses Neumann, mixed, transparent, or alternate boundary conditions, it is changing this variational problem. The resulting dictionary must be stated explicitly.

## Operator normalization

The dictionary identifies which bulk field is dual to which operator, but it does not automatically fix every normalization in a universal way. Normalizations depend on the bulk action.

For example, the Maxwell action contains

$$
\frac{1}{4g_{d+1}^2}\int F^2.
$$

Changing $g_{d+1}$ rescales the current two-point function and the current expectation value. Similarly, the gravitational action contains

$$
\frac{1}{16\pi G_{d+1}}\int d^{d+1}x\sqrt{g}\,(R-2\Lambda),
$$

so stress-tensor correlators scale with $L^{d-1}/G_{d+1}$. In AdS$_5$/CFT$_4$, this quantity scales like $N^2$.

Thus two statements must be kept separate:

1. the representation-theoretic pairing, such as $A_M\leftrightarrow J^i$;
2. the normalization of the correlators, fixed by the coefficient of the bulk kinetic term.

The first is structural. The second is quantitative.

## Common dimensions

The following formulas are useful first-pass guides in AdS$_{d+1}$:

| Bulk field | Standard boundary dimension |
|---|---|
| scalar mass $m$ | $m^2L^2=\Delta(\Delta-d)$ |
| Dirac spinor mass $m$ | $\Delta=\frac d2+|m|L$ |
| conserved current | $\Delta=d-1$ |
| stress tensor | $\Delta=d$ |
| transverse vector mass $m$ | $m^2L^2=(\Delta-1)(\Delta-d+1)$ |

These formulas come with qualifications. Alternate quantization can modify scalar and spinor assignments in allowed mass windows. Gauge constraints remove unphysical components. Mixing among fields can complicate the extraction of operator dimensions. In a compactification, Kaluza–Klein masses determine dimensions after diagonalizing the fluctuation spectrum.

But as a first dictionary, the table is indispensable.

## Dictionary checkpoint

The central lesson of this page is:

$$
\boxed{
\text{spin, mass, charge, and gauge redundancy in the bulk}
\quad
\longleftrightarrow
\quad
\text{dimension, spin, symmetry representation, and Ward identity in the CFT}.
}
$$

More concretely:

| Bulk data | Boundary data |
|---|---|
| scalar field $\phi$ | scalar primary $\mathcal O$ |
| scalar mass $m$ | scaling dimension $\Delta$ |
| spinor $\psi$ | fermionic operator $\mathcal O_\psi$ |
| gauge field $A_M$ | conserved current $J^i$ |
| boundary value $A_{(0)i}$ | background source for global symmetry |
| radial electric flux | current expectation value $\langle J^i\rangle$ |
| metric $g_{MN}$ | stress tensor $T^{ij}$ |
| boundary metric $g_{(0)ij}$ | spacetime/background source |
| normalizable metric response | $\langle T^{ij}\rangle$ |
| bulk gauge invariance | current Ward identity |
| bulk diffeomorphism invariance | stress-tensor Ward identity |
| internal isometry | boundary global/R symmetry |

The source-response dictionary is therefore also a symmetry dictionary.

## Common confusions

### “A bulk gauge symmetry means the boundary symmetry is gauged.”

Usually no. With standard Dirichlet boundary conditions, the boundary value of the bulk gauge field is a nondynamical source. The boundary symmetry is global. To gauge it, one must change the boundary conditions or integrate over the boundary gauge field.

### “The radial component of a vector field sources an extra scalar operator.”

Not in the standard Maxwell dictionary. The radial component is gauge-dependent and is often set to zero by radial gauge. Physical source data come from the boundary components $A_{(0)i}$, subject to gauge redundancy.

### “A massless vector is dual to any vector operator of dimension $d-1$.”

The operator is a conserved current associated with a global symmetry. Conservation and gauge invariance are essential. A generic vector operator need not be conserved and is dual to a massive vector or to a more complicated bulk fluctuation.

### “The graviton is dual to a spin-two operator other than the stress tensor.”

The massless graviton is dual to the conserved stress tensor. Additional massive spin-two fields, if present, can be dual to other spin-two operators, but the universal massless spin-two field is paired with $T^{ij}$.

### “All operator dimensions are fixed by spin.”

Only conserved currents and the stress tensor have protected dimensions fixed by conservation. Generic scalar, spinor, and tensor operators have dimensions determined by bulk masses, interactions, and compactification data.

### “Internal dimensions are irrelevant to the boundary theory.”

Internal spaces encode global-symmetry quantum numbers and Kaluza–Klein towers. In AdS$_5\times S^5$, the $S^5$ is not optional decoration; it carries the $SO(6)_R$ structure of $\mathcal N=4$ SYM.

## Exercises

### Exercise 1: Gauge invariance and current conservation

Assume the CFT generating functional depends on a background gauge field $A_{(0)i}$ through

$$
\delta W
=
\int d^d x\sqrt{g_{(0)}}\,\langle J^i\rangle\delta A_{(0)i}.
$$

Show that invariance under $\delta A_{(0)i}=\partial_i\lambda$ implies $\nabla_i\langle J^i\rangle=0$.

<details>
<summary><strong>Solution</strong></summary>

Gauge invariance gives

$$
0=\delta W
=
\int d^d x\sqrt{g_{(0)}}\,\langle J^i\rangle\partial_i\lambda.
$$

Integrating by parts and ignoring boundary terms on the boundary spacetime,

$$
0=
-
\int d^d x\sqrt{g_{(0)}}\,\lambda\nabla_i\langle J^i\rangle.
$$

Since $\lambda(x)$ is arbitrary,

$$
\nabla_i\langle J^i\rangle=0.
$$

In the bulk, this Ward identity is the boundary consequence of Maxwell gauge invariance and the radial constraint equation.

</details>

### Exercise 2: Massless vector dimension

Use

$$
m^2L^2=(\Delta-1)(\Delta-d+1)
$$

for a transverse vector. What are the two roots when $m=0$? Which root corresponds to an ordinary conserved current in standard quantization?

<details>
<summary><strong>Solution</strong></summary>

Setting $m=0$ gives

$$
(\Delta-1)(\Delta-d+1)=0.
$$

Therefore

$$
\Delta=1
\qquad\text{or}\qquad
\Delta=d-1.
$$

The ordinary conserved current in standard quantization has

$$
\Delta=d-1.
$$

This is the value required by current conservation in a unitary CFT. The other root is associated with alternate boundary-condition subtleties, especially in low dimensions, and is not the usual current dictionary.

</details>

### Exercise 3: Stress tensor as a metric response

Starting from

$$
\delta W
=
\frac12
\int d^d x\sqrt{g_{(0)}}\,\langle T^{ij}\rangle\delta g_{(0)ij},
$$

derive the variational formula for $\langle T^{ij}\rangle$.

<details>
<summary><strong>Solution</strong></summary>

By comparing the variation with the definition of a functional derivative,

$$
\delta W
=
\int d^d x\,
\frac{\delta W}{\delta g_{(0)ij}(x)}\delta g_{(0)ij}(x),
$$

we find

$$
\frac{\delta W}{\delta g_{(0)ij}(x)}
=
\frac12\sqrt{g_{(0)}}\,\langle T^{ij}(x)\rangle.
$$

Thus

$$
\langle T^{ij}(x)\rangle
=
\frac{2}{\sqrt{g_{(0)}}}
\frac{\delta W}{\delta g_{(0)ij}(x)}.
$$

In the classical holographic approximation $W=-S_{\text{ren,on-shell}}$, this becomes

$$
\langle T^{ij}\rangle
=
-
\frac{2}{\sqrt{g_{(0)}}}
\frac{\delta S_{\text{ren,on-shell}}}{\delta g_{(0)ij}},
$$

with the sign tied to the Euclidean convention.

</details>

### Exercise 4: Spinor source counting

Why can one not freely fix both independent near-boundary components of a bulk Dirac spinor?

<details>
<summary><strong>Solution</strong></summary>

The Dirac equation is first order in radial derivatives. For a second-order scalar equation, two independent radial coefficients appear, one of which may be fixed as a source while the other is determined dynamically as the response. For a first-order spinor equation, the two projected components are canonically conjugate rather than independently specifiable Dirichlet data.

A well-posed variational principle fixes only half of the spinor boundary data. The unfixed half is determined by the bulk solution and gives the fermionic response, analogous to the scalar normalizable coefficient.

</details>

### Exercise 5: Why does a large gap help Einstein gravity?

Explain why a holographic CFT with many light higher-spin single-trace operators is not expected to have a simple two-derivative Einstein-gravity dual.

<details>
<summary><strong>Solution</strong></summary>

Light higher-spin single-trace operators correspond to light higher-spin fields in AdS. A theory with many such fields cannot be approximated by a low-energy action containing only the metric, a few gauge fields, and a few scalars. The bulk effective theory must keep the higher-spin tower, and interactions are strongly constrained by higher-spin gauge symmetries.

A simple Einstein-gravity dual requires a large gap between the stress tensor and other low-spin protected fields on one hand, and stringy or higher-spin single-trace operators on the other. This gap allows a local low-energy bulk effective field theory with only finitely many light fields.

</details>

## Further reading

- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).
- W. Mueck and K. S. Viswanathan, [Conformal Field Theory Correlators from Classical Field Theory on Anti-de Sitter Space II: Vector and Spinor Fields](https://arxiv.org/abs/hep-th/9805145).
- V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).
- M. Henningson and K. Skenderis, [The Holographic Weyl Anomaly](https://arxiv.org/abs/hep-th/9806087).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
