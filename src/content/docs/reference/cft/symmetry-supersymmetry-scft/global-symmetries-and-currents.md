---
title: "Global Symmetries and Currents"
description: "Flavor symmetries, conserved currents, Ward identities, background gauge fields, anomalies, and the holographic gauge-field dictionary."
sidebar:
  order: 1
---

We now begin the part of the course where ordinary conformal symmetry is enlarged by internal symmetry, supersymmetry, and eventually superconformal symmetry. This page is about the first step: **global symmetries** and their **conserved currents**.

In an AdS/CFT course, this topic is not optional background. A global symmetry of the boundary CFT is one of the cleanest ways to see how a bulk gauge field emerges. The basic dictionary is

$$
\boxed{
\text{CFT global current } J_\mu^a
\quad \longleftrightarrow \quad
\text{bulk gauge field } A_M^a
}
$$

and the source relation is

$$
\boxed{
A_\mu^{a(0)}(x)
\equiv
\lim_{z\to 0} A_\mu^a(z,x)
\quad \text{sources} \quad
J_a^\mu(x) .
}
$$

Here $a$ is an adjoint index of the global symmetry group $G$, while $M$ is a bulk index in $\mathrm{AdS}_{d+1}$. The boundary value of the bulk field is not a dynamical gauge field in the original CFT; it is a background source for a conserved current.

<figure class="doc-figure" style="--figure-width: 42rem; --caption-width: 54rem;">

![The global symmetry current dictionary](/figures/cft/global-symmetry-current-dictionary.svg)

<figcaption>

A CFT global symmetry gives a conserved current $J_\mu^a$. Coupling the CFT to a background field $A_\mu^a$ produces the generating functional $W[A]$. In AdS/CFT, $A_\mu^a$ is the boundary value of a bulk gauge field $A_M^a$. An anomaly $\mathcal A_a$ means that the background gauge Ward identity is modified.

</figcaption>
</figure>

The slogan is simple, but it hides several important distinctions. A **global symmetry** acts on physical operators. A **gauge symmetry** is a redundancy of description. AdS/CFT relates these two notions in a subtle way:

$$
\text{global symmetry on the boundary}
\quad \leftrightarrow \quad
\text{gauge redundancy in the bulk}.
$$

This is one of the earliest signs that bulk locality and bulk gauge invariance are not put in by hand. They are reconstructed from the structure of the CFT operator algebra.

## Global symmetry versus gauge symmetry

Let $G$ be an internal global symmetry group. Its Lie algebra has generators $T^a$ satisfying

$$
[T^a,T^b]=i f^{ab}{}_c T^c .
$$

An operator $\mathcal O_i(x)$ transforms in some representation $R_i$ of $G$. For an infinitesimal transformation with constant parameter $\alpha^a$, we write

$$
\delta_\alpha \mathcal O_i(x)
=
\alpha^a (\delta_a \mathcal O_i)(x),
\qquad
\delta_a \mathcal O_i = i (t_a)_i{}^j \mathcal O_j .
$$

The matrices $t_a$ obey the same Lie algebra in the representation carried by $\mathcal O_i$:

$$
[t_a,t_b]=i f_{ab}{}^c t_c .
$$

The important point is that $G$ acts on gauge-invariant local operators. For example, in a CFT with a flavor symmetry $SU(N_f)$, the transformation rotates fields or composite operators carrying flavor indices. It changes physical charged operators into physical charged operators.

A gauge symmetry is different. Gauge transformations do not map one physical state to a different physical state. They identify different descriptions of the same state. In a gauge theory such as $\mathcal N=4$ SYM, the gauge group $SU(N)$ is not a global symmetry of the CFT. Local gauge-charged fields are not physical local operators. Gauge-invariant single-trace operators such as

$$
\operatorname{Tr}(\Phi^I\Phi^J),
\qquad
\operatorname{Tr}(F_{\mu\nu}F^{\mu\nu}),
\qquad
\operatorname{Tr}(\bar\lambda\lambda)
$$

are physical local operators. By contrast, the $SU(4)_R$ symmetry of $\mathcal N=4$ SYM is a true global symmetry of the CFT. Its current is dual to bulk gauge fields in type IIB string theory on $\mathrm{AdS}_5\times S^5$.

So one must keep three things apart:

| Concept | Meaning | Example in AdS/CFT |
|---|---|---|
| CFT gauge redundancy | Not a physical global symmetry | $SU(N)$ gauge redundancy of $\mathcal N=4$ SYM |
| CFT global symmetry | Acts on physical local operators | $SU(4)_R$ symmetry of $\mathcal N=4$ SYM |
| Bulk gauge redundancy | Redundancy of the emergent bulk description | Gauge field dual to a CFT global current |

The paradoxical-sounding statement “global symmetries become gauge symmetries in the bulk” means precisely this: a genuine CFT global symmetry gives rise to a bulk gauge field, but the bulk gauge transformation is a redundancy of the gravitational description.

## Noether currents

Suppose the CFT has a continuous global symmetry. In a Lagrangian description, Noether's theorem associates to it a current $J_a^\mu$.

Let the dynamical fields be collectively denoted by $\Phi$. A constant transformation is

$$
\delta_\alpha \Phi = \alpha^a \delta_a \Phi,
$$

where $\alpha^a$ is constant. The action is invariant:

$$
\delta_\alpha S = 0.
$$

To find the current, promote $\alpha^a$ to a function of spacetime. With a convenient convention, the variation of the Euclidean action takes the form

$$
\delta_\alpha S
=
-
\int d^d x\, \partial_\mu \alpha^a(x) J_a^\mu(x).
$$

If $\alpha^a$ has compact support, integration by parts gives

$$
\delta_\alpha S
=
\int d^d x\, \alpha^a(x)\partial_\mu J_a^\mu(x).
$$

The original transformation is a symmetry for constant $\alpha^a$, so the local variation identifies the current. The classical equation of motion then implies

$$
\partial_\mu J_a^\mu=0.
$$

This equation should be read carefully. In quantum field theory, the current conservation law is not merely an equation for classical field configurations. Its precise meaning is a Ward identity inside correlation functions, with contact terms when the current insertion approaches charged operators.

## Current conservation as a shortening condition

In a CFT, the current $J_\mu^a$ is a local operator. For an ordinary internal symmetry, it is a Lorentz vector and a scalar under dilatations. The corresponding charge is

$$
Q^a(\Sigma)=\int_\Sigma d\Sigma_\mu\, J_a^\mu,
$$

where $\Sigma$ is a codimension-one surface. If the current is conserved, $Q^a(\Sigma)$ is independent of small deformations of $\Sigma$, as long as no charged operator crosses the surface.

The scaling dimension of a conserved current in a unitary CFT is fixed:

$$
\boxed{\Delta_J=d-1.}
$$

There are two complementary ways to understand this.

First, current conservation says

$$
\partial^\mu J_\mu^a=0.
$$

The derivative has dimension $1$, so $\partial^\mu J_\mu^a$ would be a descendant of dimension $\Delta_J+1$. For a generic vector primary, this descendant is present. For a conserved current, it vanishes. In representation-theoretic language, the current multiplet is **short**.

Second, the spin-one unitarity bound in $d\geq 3$ is

$$
\Delta \geq d-1.
$$

Saturation occurs precisely when the vector is conserved. Thus a conserved current lies at the unitarity bound. A non-conserved vector primary has

$$
\Delta>d-1.
$$

This fact has a direct holographic interpretation. A spin-one primary with dimension $\Delta$ is dual to a bulk vector field whose mass obeys

$$
\boxed{
 m^2L^2=(\Delta-1)(\Delta-d+1).
}
$$

For a conserved current, $\Delta=d-1$, hence

$$
 m^2=0.
$$

So current conservation in the CFT is the boundary reason for the existence of a massless gauge field in AdS.

## Ward identity with charged operators

Let

$$
X=\mathcal O_1(x_1)\mathcal O_2(x_2)\cdots \mathcal O_n(x_n).
$$

The Ward identity for the global current is

$$
\boxed{
\partial_\mu\langle J_a^\mu(x)X\rangle
=
\sum_{i=1}^n \delta^{(d)}(x-x_i)
\langle
\mathcal O_1(x_1)\cdots (\delta_a\mathcal O_i)(x_i)\cdots \mathcal O_n(x_n)
\rangle.
}
$$

This equation is the quantum version of current conservation. Away from operator insertions, the current is conserved:

$$
\partial_\mu\langle J_a^\mu(x)X\rangle=0,
\qquad
x\neq x_i.
$$

At $x=x_i$, there is a contact term because the charge generated by the current acts on the operator $\mathcal O_i$.

Integrating the Ward identity over a small ball $B_i$ surrounding $x_i$ gives

$$
\int_{\partial B_i} dS_\mu\,
\langle J_a^\mu(x)X\rangle
=
\langle
\mathcal O_1(x_1)\cdots (\delta_a\mathcal O_i)(x_i)\cdots \mathcal O_n(x_n)
\rangle.
$$

This is the cleanest way to remember the current OPE. If $\mathcal O_i$ transforms in representation $R_i$, then at short distance

$$
\boxed{
J_a^\mu(x)\mathcal O_i(0)
\sim
\frac{1}{S_{d-1}}\frac{x^\mu}{|x|^d}
(\delta_a\mathcal O_i)(0)
+
\text{less singular terms},
}
$$

where

$$
S_{d-1}=\frac{2\pi^{d/2}}{\Gamma(d/2)}
$$

is the area of the unit sphere $S^{d-1}$. The normalization is chosen so that

$$
\int_{S^{d-1}_r} dS_\mu\,
\frac{1}{S_{d-1}}\frac{x^\mu}{|x|^d}=1.
$$

This OPE is extremely useful. It says that the leading singularity of the current near a charged operator is fixed by the representation matrix of the symmetry.

For a $U(1)$ symmetry with charge $q_i$, the transformation is

$$
\delta \mathcal O_i=i q_i \mathcal O_i,
$$

so the current OPE becomes

$$
J^\mu(x)\mathcal O_i(0)
\sim
\frac{i q_i}{S_{d-1}}\frac{x^\mu}{|x|^d}\mathcal O_i(0)+\cdots.
$$

Depending on whether one uses Hermitian or anti-Hermitian symmetry generators, the factor of $i$ may be moved into the definition of $\delta_a$. The physics is the integrated statement: the flux of the current through a small sphere measures the charge of the operator.

## Selection rules

The Ward identity immediately implies selection rules. Consider a correlation function of charged scalar primaries in a theory with a $U(1)$ global symmetry:

$$
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle.
$$

Under a constant symmetry transformation,

$$
\mathcal O_i\mapsto e^{i q_i\alpha}\mathcal O_i.
$$

If the vacuum is invariant, the correlator can be nonzero only if

$$
\boxed{\sum_{i=1}^n q_i=0.}
$$

For a non-abelian symmetry, the analogous statement is that the tensor product of the external representations must contain a singlet. For example, in an $SU(2)$-invariant CFT, a two-point function between operators in representations $j_1$ and $j_2$ can be nonzero only if the representations can pair to a singlet. For irreducible $SU(2)$ representations this requires $j_1=j_2$.

These are not dynamical accidents. They follow from the identity of the vacuum representation under the global symmetry.

## The current two-point function

For a conserved spin-one primary, conformal symmetry fixes the current two-point function up to an overall coefficient. In flat Euclidean space,

$$
\boxed{
\langle J_\mu^a(x)J_\nu^b(0)\rangle
=
\frac{C_J\delta^{ab}}{(x^2)^{d-1}}
I_{\mu\nu}(x),
\qquad
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2}.
}
$$

Here $C_J$ is called a **flavor central charge** or **current central charge**. It is positive in a unitary theory once the generator normalization is fixed.

There is a subtle normalization issue. If we rescale the generators by

$$
T^a\to \lambda T^a,
$$

then the current and $C_J$ rescale. Therefore $C_J$ is meaningful only after choosing a convention for the Lie algebra metric, usually

$$
\operatorname{tr}_R(T^aT^b)=T_R\delta^{ab}
$$

in a chosen representation.

The tensor structure $I_{\mu\nu}(x)$ is the same inversion tensor that appeared in spinning correlators. The power $(x^2)^{d-1}$ follows from $\Delta_J=d-1$. Conservation fixes the dimension but also imposes transversality away from $x=0$:

$$
\partial^\mu
\left[\frac{I_{\mu\nu}(x)}{(x^2)^{d-1}}\right]=0,
\qquad x\neq 0.
$$

The phrase “away from $x=0$” matters. At coincident points there can be contact terms. In momentum space, those contact terms are polynomial ambiguities. In holography, the same ambiguities appear as local boundary counterterms in holographic renormalization.

## Current three-point functions

The three-point function

$$
\langle J_\mu^a(x_1)\mathcal O_i(x_2)\mathcal O_j(x_3)\rangle
$$

is constrained by conformal symmetry and by the Ward identity. If $\mathcal O_i$ and $\mathcal O_j$ are scalar primaries in representations related by conjugation, the coefficient is fixed by the charge matrices once the scalar two-point function is normalized. Schematically,

$$
\partial_{x_1}^\mu
\langle J_\mu^a(x_1)\mathcal O_i(x_2)\mathcal O_j(x_3)\rangle
=
\delta(x_{12})\langle (\delta_a\mathcal O_i)(x_2)\mathcal O_j(x_3)\rangle
+
\delta(x_{13})\langle \mathcal O_i(x_2)(\delta_a\mathcal O_j)(x_3)\rangle.
$$

This is one of the simplest examples of how a three-point coefficient is not arbitrary. It is fixed by a symmetry representation and a two-point normalization.

The three-current correlator

$$
\langle J_\mu^a(x_1)J_\nu^b(x_2)J_\rho^c(x_3)\rangle
$$

contains group theory tensors. In a parity-even theory, the antisymmetric structure constants $f^{abc}$ encode the non-abelian Ward identity. In some dimensions and for some groups, symmetric tensors such as $d^{abc}$ can also appear, often tied to anomaly data. The precise decomposition depends on spacetime dimension, parity, and the symmetry group.

The lesson for AdS/CFT is direct: current correlators become boundary correlators of bulk gauge fields. The coefficient $C_J$ controls the bulk gauge coupling, while higher-point structures encode bulk gauge interactions and possible Chern-Simons terms.

## Background gauge fields as sources

To systematically define current correlators, couple the CFT to a nondynamical background gauge field $A_\mu^a(x)$. Use the convention

$$
e^{W[A]}
=
Z[A]
=
\left\langle
\exp\left(\int d^d x\, A_\mu^a J_a^\mu\right)
\right\rangle_{A=0}.
$$

Then current correlators are functional derivatives:

$$
\langle J_a^\mu(x)\rangle_A
=
\frac{\delta W[A]}{\delta A_\mu^a(x)},
$$

and at $A=0$,

$$
\langle J_a^\mu(x)J_b^\nu(y)\rangle_{\mathrm{conn}}
=
\left.\frac{\delta^2 W[A]}{\delta A_\mu^a(x)\delta A_\nu^b(y)}\right|_{A=0}.
$$

For a non-abelian symmetry, the background field transforms as

$$
\delta_\alpha A_\mu^a
=
D_\mu\alpha^a
=
\partial_\mu\alpha^a+f^a{}_{bc}A_\mu^b\alpha^c.
$$

If the symmetry has no anomaly, the generating functional is invariant:

$$
W[A+D\alpha]=W[A].
$$

Taking the infinitesimal variation gives

$$
0
=
\int d^d x\,
\frac{\delta W}{\delta A_\mu^a}D_\mu\alpha^a
=
-
\int d^d x\,
\alpha^a D_\mu\langle J_a^\mu\rangle_A,
$$

so

$$
\boxed{D_\mu\langle J_a^\mu\rangle_A=0.}
$$

With charged operator insertions, this becomes the background-field version of the Ward identity:

$$
D_\mu\langle J_a^\mu(x)X\rangle_A
=
\sum_i \delta^{(d)}(x-x_i)
\langle \mathcal O_1\cdots (\delta_a\mathcal O_i)\cdots \mathcal O_n\rangle_A.
$$

This is the CFT side of the bulk statement that the on-shell action is invariant under gauge transformations that vanish appropriately at the boundary, while boundary gauge transformations act as global symmetry transformations on the dual CFT.

## Stress tensor in a background gauge field

When a CFT is coupled to both a background metric $g_{\mu\nu}$ and a background gauge field $A_\mu^a$, the generating functional is

$$
W[g,A].
$$

With the convention

$$
e^{W[g,A]}=Z[g,A],
$$

define one-point functions by

$$
\langle J_a^\mu\rangle
=
\frac{1}{\sqrt g}\frac{\delta W}{\delta A_\mu^a},
$$

and

$$
\langle T^{\mu\nu}\rangle
=
\frac{2}{\sqrt g}\frac{\delta W}{\delta g_{\mu\nu}}.
$$

The precise sign of the stress-tensor definition varies across the literature depending on whether one defines $W=\log Z$ or $W=-\log Z$, and whether one differentiates with respect to $g_{\mu\nu}$ or $g^{\mu\nu}$. The invariant content is the Ward identity.

Diffeomorphism invariance gives, schematically,

$$
\boxed{
\nabla_\mu \langle T^{\mu}{}_{\nu}\rangle
=
F_{\nu\mu}^a\langle J_a^\mu\rangle
+
\text{operator-source terms}
+
\text{anomalies}.
}
$$

The term $F_{\nu\mu}^a J_a^\mu$ is the curved-space version of the Lorentz force. It tells us that when the CFT is placed in a background gauge field, the stress tensor is not separately conserved in the ordinary sense; energy-momentum can be exchanged with the external source.

For a true CFT on a flat background with no sources and no anomaly, the familiar identities are recovered:

$$
\partial_\mu J_a^\mu=0,
\qquad
\partial_\mu T^{\mu}{}_{\nu}=0,
\qquad
T^\mu{}_{\mu}=0.
$$

## Anomalies and 't Hooft anomalies

A global symmetry can be exact as an operator statement and still have an obstruction to being coupled to a background gauge field in a gauge-invariant way. This obstruction is an **'t Hooft anomaly**.

In the background-field language, an anomaly means that $W[A]$ is not invariant under a background gauge transformation. Instead,

$$
\delta_\alpha W[A]
=
\int d^d x\, \alpha^a(x)\mathcal A_a(A,g).
$$

Then the Ward identity becomes

$$
\boxed{
D_\mu\langle J_a^\mu\rangle_A
=
\mathcal A_a(A,g).
}
$$

This does not mean the theory is inconsistent. It means the symmetry cannot be gauged as an ordinary dynamical gauge symmetry without adding extra degrees of freedom or anomaly inflow.

This distinction is central in holography. CFT anomalies are encoded by bulk topological terms. For example, a four-dimensional CFT flavor anomaly can be represented in an $\mathrm{AdS}_5$ bulk by a Chern-Simons coupling of schematic form

$$
S_{\rm CS}\sim k\int_{\mathrm{AdS}_5} A\wedge F\wedge F.
$$

Under a gauge transformation, this term changes by a boundary term. That boundary term reproduces the anomalous variation of the CFT generating functional. This is anomaly inflow in the AdS/CFT language.

## Flavor central charges and bulk gauge couplings

The current two-point coefficient $C_J$ is one of the most important pieces of CFT data attached to a global symmetry. In holography it determines the normalization of the bulk Maxwell action:

$$
S_{\rm bulk}
\supset
\frac{1}{4g_{d+1}^2}
\int d^{d+1}X\sqrt g\,
F_{MN}^aF^{aMN}.
$$

Up to convention-dependent numerical factors,

$$
\boxed{
C_J\propto \frac{L^{d-3}}{g_{d+1}^2}.
}
$$

Here $L$ is the AdS radius. Thus a large current central charge corresponds to a weakly coupled bulk gauge field. This is analogous to the stress-tensor relation

$$
C_T\propto \frac{L^{d-1}}{G_N},
$$

where $C_T$ is the stress-tensor two-point coefficient and $G_N$ is the bulk Newton constant.

This comparison is worth remembering:

| CFT operator | Protected dimension | Bulk field | Bulk coupling data |
|---|---:|---|---|
| $T_{\mu\nu}$ | $d$ | metric $g_{MN}$ | $C_T\sim L^{d-1}/G_N$ |
| $J_\mu^a$ | $d-1$ | gauge field $A_M^a$ | $C_J\sim L^{d-3}/g_{d+1}^2$ |
| scalar primary $\mathcal O$ | $\Delta$ | scalar $\phi$ | $m^2L^2=\Delta(\Delta-d)$ |

The current is protected by conservation in the same way the stress tensor is protected by energy-momentum conservation.

## Gauging a global symmetry

Given a CFT with global symmetry $G$, one can sometimes form a new theory by gauging $G$:

$$
Z_{\rm gauged}
=
\int \mathcal D A\,
\exp\left(-S_{\rm gauge}[A]\right)Z_{\rm CFT}[A].
$$

This operation is not always allowed. The symmetry must have no gauge anomaly, and the gauge coupling must have appropriate RG behavior. In four dimensions, gauging a flavor symmetry introduces a marginal gauge coupling at the classical level, but quantum beta functions decide whether the gauged theory is conformal.

This is different from the AdS/CFT dictionary above. In the ordinary dictionary, $A_\mu^a$ is a source, not a dynamical CFT field. The CFT global symmetry remains global. The bulk field $A_M^a$ is dynamical because the bulk gravitational theory is dynamical. This is not the same as gauging the boundary global symmetry.

Boundary gauging is an operation that changes the CFT. Bulk gauging is part of the dual description of the original global symmetry.

## Two-dimensional chiral currents

In two-dimensional CFT, currents can be holomorphic or antiholomorphic. A holomorphic current has dimensions

$$
(h,\bar h)=(1,0),
$$

and obeys

$$
\bar\partial J^a(z)=0.
$$

Its OPE takes the affine-current form

$$
\boxed{
J^a(z)J^b(0)
\sim
\frac{k\delta^{ab}}{z^2}
+
\frac{i f^{ab}{}_c J^c(0)}{z}
+\cdots .
}
$$

The coefficient $k$ is the level. This is stronger than ordinary current conservation in higher-dimensional CFT. It is the starting point of WZW models, affine Lie algebras, the Sugawara construction, and current-algebra methods in worldsheet CFT.

For AdS$_3$/CFT$_2$, this current algebra is especially important. A CFT$_2$ affine symmetry is dual to Chern-Simons gauge theory in three-dimensional AdS. The level $k$ controls the Chern-Simons coefficient and therefore the boundary current algebra.

## Higher-form symmetries, briefly

Modern QFT also includes generalized global symmetries. A $p$-form global symmetry acts not on local point operators, but on $p$-dimensional extended operators. The associated conserved current is a $(p+1)$-form current, or equivalently a $(d-p-1)$-form after Hodge duality.

For example, a one-form symmetry acts on line operators. Its charged objects are Wilson lines or other line defects. In holography, generalized global symmetries are related to bulk higher-form gauge fields and to the spectrum of extended objects.

This course mostly focuses on ordinary zero-form symmetries because they are the symmetries that lead to ordinary spin-one currents and ordinary bulk gauge fields. But the general rule is useful:

$$
\text{CFT generalized global symmetry}
\quad \leftrightarrow \quad
\text{bulk higher-form gauge field or constraint}.
$$

The same conceptual warning applies: the boundary symmetry is physical; the bulk gauge invariance is a redundancy of the emergent bulk description.

## AdS/CFT checkpoint

For later use, the essential dictionary is this:

$$
\boxed{
\text{CFT global symmetry }G
\quad \longleftrightarrow \quad
\text{bulk gauge field }A_M^a.
}
$$

The operator-source relation is

$$
\boxed{
Z_{\rm CFT}[A_\mu^{a(0)}]
=
Z_{\rm bulk}[A_M^a\to A_\mu^{a(0)}].
}
$$

Functional differentiation gives current correlators:

$$
\langle J_a^\mu(x)\rangle
=
\frac{\delta W[A]}{\delta A_\mu^a(x)}.
$$

The protected dimension

$$
\Delta_J=d-1
$$

is equivalent to the statement that the dual vector field is massless:

$$
 m^2L^2=(\Delta-1)(\Delta-d+1)=0.
$$

The current two-point coefficient determines the gauge coupling:

$$
C_J\propto \frac{L^{d-3}}{g_{d+1}^2}.
$$

Anomalies are not small corrections. They are exact pieces of CFT data and are represented holographically by topological bulk terms such as Chern-Simons couplings.

## Common pitfalls

A boundary global symmetry is not a boundary gauge redundancy. It acts on physical operators.

A bulk gauge symmetry is not a new physical global symmetry. It is the redundant description required for a massless spin-one field.

The current $J_\mu^a$ is not just any vector primary. It is a shortened conformal multiplet with $\Delta=d-1$.

The normalization of $C_J$ depends on the normalization of Lie algebra generators. Always state the convention before comparing two papers.

Contact terms are not optional nuisances. They are part of the Ward identity and are needed for consistency of charge action, background fields, and anomalies.

## Exercises

### Exercise 1 — Ward identity from a local transformation

Let $X=\prod_i\mathcal O_i(x_i)$. Starting from a change of variables in the Euclidean path integral under a local symmetry transformation $\alpha^a(x)$, derive

$$
\partial_\mu\langle J_a^\mu(x)X\rangle
=
\sum_i\delta^{(d)}(x-x_i)
\langle \mathcal O_1\cdots(\delta_a\mathcal O_i)\cdots\mathcal O_n\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Use the convention

$$
\delta_\alpha S
=
\int d^d x\,\alpha^a(x)\partial_\mu J_a^\mu(x).
$$

The path integral is invariant under a change of integration variables, so to first order

$$
0
=
\langle \delta_\alpha X\rangle
-
\langle X\delta_\alpha S\rangle.
$$

The variation of the product is localized at the insertion points:

$$
\delta_\alpha X
=
\int d^d x\,\alpha^a(x)
\sum_i\delta^{(d)}(x-x_i)
\mathcal O_1\cdots(\delta_a\mathcal O_i)\cdots\mathcal O_n.
$$

Substitute both expressions into the path-integral identity:

$$
0
=
\int d^d x\,\alpha^a(x)
\left[
\sum_i\delta^{(d)}(x-x_i)
\langle\mathcal O_1\cdots(\delta_a\mathcal O_i)\cdots\mathcal O_n\rangle
-
\partial_\mu\langle J_a^\mu(x)X\rangle
\right].
$$

Since $\alpha^a(x)$ is arbitrary, the integrand vanishes. This gives the Ward identity.

</details>

### Exercise 2 — Current OPE from charge flux

Show that the leading OPE

$$
J_a^\mu(x)\mathcal O_i(0)
\sim
\frac{1}{S_{d-1}}\frac{x^\mu}{|x|^d}(\delta_a\mathcal O_i)(0)
$$

has the correct normalization to generate the symmetry action on $\mathcal O_i$.

<details><summary><strong>Solution</strong></summary>

Integrate the current over a small sphere $S_r^{d-1}$ surrounding the origin:

$$
\int_{S_r^{d-1}}dS_\mu\,J_a^\mu(x)\mathcal O_i(0).
$$

Using the proposed OPE gives

$$
\frac{1}{S_{d-1}}
\int_{S_r^{d-1}}dS_\mu\frac{x^\mu}{|x|^d}(\delta_a\mathcal O_i)(0).
$$

On the sphere, $x^\mu=r n^\mu$ and $dS_\mu=n_\mu r^{d-1}d\Omega$, so

$$
dS_\mu\frac{x^\mu}{|x|^d}
=
(n_\mu r^{d-1}d\Omega)\frac{r n^\mu}{r^d}
=d\Omega.
$$

Therefore

$$
\frac{1}{S_{d-1}}\int_{S^{d-1}}d\Omega=1.
$$

The integrated current inserts $(\delta_a\mathcal O_i)(0)$, which is exactly the charge action required by the Ward identity.

</details>

### Exercise 3 — Current dimension from the two-point function

Assume a vector primary has a conformally invariant two-point function

$$
\langle V_\mu(x)V_\nu(0)\rangle
=
\frac{C}{(x^2)^\Delta}I_{\mu\nu}(x).
$$

Show that conservation away from $x=0$ implies $\Delta=d-1$.

<details><summary><strong>Solution</strong></summary>

Compute the divergence for $x\neq 0$:

$$
\partial^\mu\left[\frac{I_{\mu\nu}(x)}{(x^2)^\Delta}\right].
$$

Using

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2\frac{x_\mu x_\nu}{x^2},
$$

one finds

$$
\partial^\mu\left[\frac{I_{\mu\nu}(x)}{(x^2)^\Delta}\right]
=
2(\Delta-d+1)\frac{x_\nu}{(x^2)^{\Delta+1}}.
$$

For this to vanish away from contact terms, one needs

$$
\Delta=d-1.
$$

Thus a conserved vector primary has protected dimension $d-1$.

</details>

### Exercise 4 — Background gauge Ward identity

Let

$$
e^{W[A]}=\left\langle \exp\left(\int A_\mu^aJ_a^\mu\right)\right\rangle.
$$

Assume $W[A]$ is invariant under $\delta A_\mu^a=D_\mu\alpha^a$. Derive

$$
D_\mu\langle J_a^\mu\rangle_A=0.
$$

<details><summary><strong>Solution</strong></summary>

The infinitesimal variation is

$$
\delta W[A]
=
\int d^d x\,\frac{\delta W}{\delta A_\mu^a}\delta A_\mu^a
=
\int d^d x\,\langle J_a^\mu\rangle_A D_\mu\alpha^a.
$$

Integrating by parts covariantly gives

$$
\delta W[A]
=
-
\int d^d x\,\alpha^a D_\mu\langle J_a^\mu\rangle_A.
$$

If $W[A]$ is invariant and $\alpha^a(x)$ is arbitrary, then

$$
D_\mu\langle J_a^\mu\rangle_A=0.
$$

If the symmetry has an anomaly, the same derivation gives

$$
D_\mu\langle J_a^\mu\rangle_A=\mathcal A_a.
$$

</details>

### Exercise 5 — Conserved current and massless bulk vector

Use

$$
 m^2L^2=(\Delta-1)(\Delta-d+1)
$$

for a spin-one field in $\mathrm{AdS}_{d+1}$ to show that a conserved current is dual to a massless bulk gauge field.

<details><summary><strong>Solution</strong></summary>

A conserved current in a $d$-dimensional CFT has

$$
\Delta_J=d-1.
$$

Substitute this into the AdS mass-dimension relation:

$$
 m^2L^2=(d-2)((d-1)-d+1)=(d-2)\cdot 0=0.
$$

Therefore the dual vector field is massless. A massless spin-one field in AdS has a gauge redundancy, so the CFT conservation law is the boundary origin of the bulk gauge symmetry.

</details>

## Further reading

For QFT Ward identities, Noether currents, and the stress tensor, review the early QFT chapters of Di Francesco, Mathieu, and Sénéchal. For current algebra in two-dimensional CFT, see the WZW and affine Lie algebra chapters. For the modern higher-dimensional bootstrap viewpoint, combine these notes with standard reviews of conformal blocks, Ward identities, and current multiplets. For the AdS/CFT dictionary, the essential next step is to compute the on-shell Maxwell action in Euclidean AdS and extract the current two-point function.
