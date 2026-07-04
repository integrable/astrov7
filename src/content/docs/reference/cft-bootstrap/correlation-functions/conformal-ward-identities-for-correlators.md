---
title: "Conformal Ward Identities for Correlators"
description: "Derives and organizes the global and local Ward identities that constrain CFT correlation functions through conserved currents and the stress tensor."
sidebar:
  label: "Ward Identities for Correlators"
  order: 9
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Osborn and Petkou 1994; Rychkov 2016; Simmons-Duffin 2017; Poland, Rychkov, and Vichi 2019"
topics:
  - conformal field theory
  - Ward identities
  - correlation functions
  - stress tensor
  - conserved currents
  - conformal symmetry
canonicalTopics:
  - conformal-ward-identities-for-correlators
  - global-conformal-ward-identities
  - local-stress-tensor-ward-identities
  - current-ward-identities
  - contact-terms
researchStatus:
  established:
    - "Global conformal Ward identities constrain correlators by requiring the sum of infinitesimal conformal actions on all insertions to vanish."
    - "Local Ward identities express conservation of currents and the stress tensor up to contact terms at operator insertions."
  active:
    - "Lorentzian Ward identities, anomalies, contact-term classifications, curved-space generating functionals, and stress-tensor/current bootstrap systems remain active technical interfaces."
---

## Summary

Ward identities are the equations that turn symmetry into constraints on correlation functions. In CFT, there are two closely related versions.

The **global Ward identity** says that a correlator is invariant when all insertions are transformed together. For scalar primaries,

$$
\sum_{i=1}^n \mathcal D_i^{(X)}
\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle=0,
$$

where $X$ is a generator of translations, rotations, dilatations, or special conformal transformations, and $\mathcal D_i^{(X)}$ is the corresponding differential operator acting on the $i$th insertion.

The **local Ward identity** says that conserved currents and the stress tensor have divergences supported at operator insertions. For an internal current,

$$
\partial_\mu\langle J^{a\mu}(x)\prod_i\mathcal O_i(x_i)\rangle
=
\sum_i\delta^{(d)}(x-x_i)
\langle \mathcal O_1\cdots(t_i^a\mathcal O_i)(x_i)\cdots\mathcal O_n\rangle.
$$

For the stress tensor, contracting with a conformal Killing vector $\xi^\nu(x)$ gives schematically

$$
\partial^\mu\left[\xi^\nu(x)\langle T_{\mu\nu}(x)\prod_i\mathcal O_i(x_i)\rangle\right]
=
\sum_i\delta^{(d)}(x-x_i)
\langle \mathcal O_1\cdots(\delta_\xi\mathcal O_i)(x_i)\cdots\mathcal O_n\rangle,
$$

with a sign determined by the convention for $\delta_\xi\mathcal O$. Integrating this equation over a region gives the global conformal Ward identities.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Deforming a Ward-identity charge surface through operator insertions](/figures/cft-bootstrap/correlator-ward-surface-deformation.svg)

<figcaption>

A Ward identity comes from deforming a charge surface through a correlator. Nothing changes while the surface crosses empty space; crossing an insertion produces the infinitesimal symmetry action on that operator.

</figcaption>
</figure>

:::note[One line to remember]
At separated points, Ward identities look like conservation equations. At coincident points, the contact terms remember what the symmetry does to the operators.
:::

## Prerequisites

You should know [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/), [Conformal Generators](/cft-bootstrap/conformal-symmetry/conformal-generators/), [Conformal Transformations](/cft-bootstrap/conformal-symmetry/conformal-transformations/), [Current Correlators](/cft-bootstrap/correlation-functions/current-correlators/), and [Stress-Tensor Correlators](/cft-bootstrap/correlation-functions/stress-tensor-correlators/).

For this page, a primary operator is a local operator transforming covariantly under the conformal group. Spinning operators require spin generators in the Ward identities; scalar formulas are shown first because they expose the logic with fewer moving parts.

## Core idea

A charge is an integral of a conserved current over a codimension-one surface. If the current is conserved away from insertions, the surface can be moved without changing the answer. If the surface crosses an operator insertion, the charge acts on that operator.

This is the same idea for internal and spacetime symmetries:

| Symmetry | Conserved object | Charge insertion | Contact term |
|---|---|---|---|
| internal global symmetry | $J^a_\mu$ | $\int dS^\mu J^a_\mu$ | $t_i^a\mathcal O_i$ |
| translation | $T_{\mu\nu}$ | $\int dS_\mu a_\nu T^{\mu\nu}$ | $a^\nu\partial_{i\nu}\mathcal O_i$ |
| rotation | $T_{\mu\nu}$ | $\int dS_\mu \omega_\nu{}^\rho x_\rho T^{\mu\nu}$ | orbital plus spin rotation |
| dilatation | $T_{\mu\nu}$ | $\int dS_\mu x_\nu T^{\mu\nu}$ | $x_i\cdot\partial_i+\Delta_i$ |
| special conformal | $T_{\mu\nu}$ | $\int dS_\mu \xi_\nu^{(K)}T^{\mu\nu}$ | special conformal differential action |

The punchline is not that every correlator is determined. The punchline is that every correlator must transform correctly. This fixes two- and three-point scalar correlators up to constants and reduces four-point scalar correlators to functions of cross-ratios.

## Setup and conventions

We work in Euclidean $\mathbb R^d$ with metric $\delta_{\mu\nu}$. For a scalar primary $\mathcal O_i$ of dimension $\Delta_i$, an infinitesimal conformal transformation generated by a conformal Killing vector $\xi^\mu(x)$ acts as

$$
\delta_\xi\mathcal O_i(x_i)
=
-\left[\xi^\mu(x_i)\partial_{i\mu}+\Delta_i\sigma(x_i)\right]\mathcal O_i(x_i),
$$

where

$$
\sigma(x)=\frac1d\partial_\mu\xi^\mu(x).
$$

This sign convention treats the transformation actively. If another page uses the opposite convention for $\delta_\xi$, all Ward identities acquire a common sign change. The invariant content is the same.

For a spinning primary, add the spin action:

$$
\delta_\xi\mathcal O_i(x_i)
=
-\left[\xi\cdot\partial_i+\Delta_i\sigma(x_i)+\frac12\omega_{\mu\nu}(x_i)\Sigma_i^{\mu\nu}\right]\mathcal O_i(x_i),
$$

where $\Sigma_i^{\mu\nu}$ are the rotation generators in the operator's spin representation and $\omega_{\mu\nu}$ is the local antisymmetric rotation extracted from $\partial_\mu\xi_\nu$.

We write

$$
G_n(x_1,\ldots,x_n)=
\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle.
$$

## Global scalar Ward identities

The conformal algebra is generated by translations $P_\mu$, rotations $M_{\mu\nu}$, dilatations $D$, and special conformal transformations $K_\mu$. For scalar primaries, the corresponding differential operators can be chosen as

$$
\mathcal D_i^{(P_\mu)}=\partial_{i\mu},
$$

$$
\mathcal D_i^{(M_{\mu\nu})}=x_{i\mu}\partial_{i\nu}-x_{i\nu}\partial_{i\mu},
$$

$$
\mathcal D_i^{(D)}=x_i\cdot\partial_i+\Delta_i,
$$

and

$$
\mathcal D_i^{(K_\mu)}=
2x_{i\mu}(x_i\cdot\partial_i)-x_i^2\partial_{i\mu}+2\Delta_i x_{i\mu}.
$$

The global Ward identities are

$$
\sum_i\mathcal D_i^{(P_\mu)}G_n=0,
\qquad
\sum_i\mathcal D_i^{(M_{\mu\nu})}G_n=0,
$$

$$
\sum_i\mathcal D_i^{(D)}G_n=0,
\qquad
\sum_i\mathcal D_i^{(K_\mu)}G_n=0.
$$

Translations imply dependence only on separations. Rotations imply dependence only on scalar combinations of separations unless the operators carry spin. Dilatations fix overall homogeneity. Special conformal transformations impose the strongest constraint; they are what distinguish conformal covariance from scale-plus-Poincaré covariance.

For spinning primaries, add spin terms to $M$ and $K$. In a polarization-vector formalism, those spin terms become differential operators acting on the auxiliary polarizations.

## Two-point functions from Ward identities

Let

$$
G_2=\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\rangle
$$

for scalar primaries. Translation and rotation invariance give

$$
G_2=F(x_{12}^2).
$$

Dilatation invariance gives

$$
\left(x_{12}\cdot\partial_{x_{12}}+\Delta_1+\Delta_2\right)F=0,
$$

so

$$
F(x_{12}^2)=\frac{C_{12}}{(x_{12}^2)^{(\Delta_1+\Delta_2)/2}}.
$$

The special conformal Ward identity then forces

$$
(\Delta_1-\Delta_2)C_{12}=0.
$$

Thus the separated-point scalar two-point function is

$$
\langle \mathcal O_i(x_1)\mathcal O_j(x_2)\rangle
=
\frac{C_{ij}\,\delta_{\Delta_i,\Delta_j}}{(x_{12}^2)^{\Delta_i}},
$$

with the understanding that one can diagonalize the coefficient matrix in a unitary theory. For spin, the same Ward identities fix the inversion-tensor structure.

## Three-point functions from Ward identities

For scalar primaries, conformal Ward identities fix the three-point function up to one constant:

$$
\langle \mathcal O_1(x_1)\mathcal O_2(x_2)\mathcal O_3(x_3)\rangle
=
\frac{\lambda_{123}}
{(x_{12}^2)^{\alpha_{12}}(x_{23}^2)^{\alpha_{23}}(x_{31}^2)^{\alpha_{31}}},
$$

where

$$
\alpha_{12}=\frac{\Delta_1+\Delta_2-\Delta_3}{2},
\qquad
\alpha_{23}=\frac{\Delta_2+\Delta_3-\Delta_1}{2},
\qquad
\alpha_{31}=\frac{\Delta_3+\Delta_1-\Delta_2}{2}.
$$

The exponents are fixed by requiring the correlator to have weight $\Delta_i$ at each point. Special conformal invariance confirms that this scale-covariant answer is genuinely conformal.

For spinning operators, the same reasoning fixes the coordinate weights and leaves a finite set of tensor structures:

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\rangle
=
\sum_a\lambda_{123}^{(a)}\,\text{structure}_a(x_i,s_i).
$$

The Ward identities do not determine the constants $\lambda_{123}^{(a)}$. Those constants are CFT data.

## Four-point functions and cross-ratios

For four scalar primaries, the global Ward identities no longer fix the correlator up to constants. They reduce it to a function of conformal cross-ratios. For identical scalars of dimension $\Delta_\phi$,

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}\mathcal G(u,v),
$$

where

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The function $\mathcal G(u,v)$ is dynamical. Symmetry alone does not determine it. The OPE and crossing symmetry constrain it further.

For nonidentical scalars, one factors out a conventional coordinate prefactor and leaves a reduced correlator depending on $u$ and $v$. For spinning four-point functions, there are several tensor structures, each with its own function of $u$ and $v$.

## Local current Ward identity

The local Ward identity for an internal current is

$$
\partial_\mu\langle J^{a\mu}(x)\mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle
=
\sum_i\delta^{(d)}(x-x_i)
\langle \mathcal O_1\cdots(t_i^a\mathcal O_i)(x_i)\cdots\mathcal O_n\rangle.
$$

At separated points, the divergence vanishes:

$$
\partial_\mu\langle J^{a\mu}(x)\prod_i\mathcal O_i(x_i)\rangle=0,
\qquad x\neq x_i.
$$

At coincident points, the delta functions are essential. They encode charge conservation, selection rules, and the current–operator OPE.

For a $U(1)$ current acting on operators of charges $q_i$,

$$
(t_i\mathcal O_i)=q_i\mathcal O_i.
$$

Integrating over a region containing all insertions gives the neutrality condition

$$
\left(\sum_i q_i\right)
\langle \mathcal O_1\cdots\mathcal O_n\rangle=0.
$$

For a non-Abelian current, the same formula says that the correlator must be an invariant tensor in the product of representations.

## Local stress-tensor Ward identity

The stress tensor generates spacetime transformations. Translation Ward identities can be written schematically as

$$
\partial^\mu\langle T_{\mu\nu}(x)\prod_i\mathcal O_i(x_i)\rangle
=
\sum_i\delta^{(d)}(x-x_i)\partial_{i\nu}
\langle \prod_i\mathcal O_i(x_i)\rangle
+
\text{spin/contact refinements}.
$$

This formula is schematic because spinning operators and coincident composite definitions require additional contact terms. The clean conformal version contracts with a conformal Killing vector $\xi^\nu$:

$$
\partial^\mu\left[\xi^\nu(x)\langle T_{\mu\nu}(x)\prod_i\mathcal O_i(x_i)\rangle\right]
=
\sum_i\delta^{(d)}(x-x_i)
\langle \mathcal O_1\cdots(\delta_\xi\mathcal O_i)(x_i)\cdots\mathcal O_n\rangle.
$$

This follows from conservation and tracelessness at separated points:

$$
\partial^\mu T_{\mu\nu}=0,
\qquad
T^\mu_{\ \mu}=0.
$$

Indeed,

$$
\partial^\mu(\xi^\nu T_{\mu\nu})
=(\partial^\mu\xi^\nu)T_{\mu\nu}+\xi^\nu\partial^\mu T_{\mu\nu}.
$$

For a conformal Killing vector,

$$
\partial_\mu\xi_\nu+\partial_\nu\xi_\mu=2\sigma(x)\delta_{\mu\nu},
$$

so the symmetric part gives $\sigma T^\mu_{\ \mu}$ and vanishes at separated points in a flat-space CFT without anomaly. The antisymmetric part drops out because $T_{\mu\nu}$ is symmetric.

## From local to global

Integrating the stress-tensor Ward identity over a region $B$ gives

$$
\int_{\partial B}dS_\mu\,\xi^\nu
\langle T^{\mu}{}_{\nu}(x)\prod_i\mathcal O_i(x_i)\rangle
=
\sum_{x_i\in B}
\langle \mathcal O_1\cdots(\delta_\xi\mathcal O_i)(x_i)\cdots\mathcal O_n\rangle.
$$

If the boundary is pushed to infinity and the flux at infinity vanishes, the sum of variations of all insertions is zero:

$$
\sum_i
\langle \mathcal O_1\cdots(\delta_\xi\mathcal O_i)(x_i)\cdots\mathcal O_n\rangle=0.
$$

This is the global Ward identity. The same reasoning works for internal currents. Local conservation plus contact terms implies global charge invariance. Conversely, the local Ward identity is the distributional version of the statement that charge surfaces can be deformed.

## Ward identities and OPE coefficients

Ward identities fix special OPE coefficients involving conserved currents.

For an ordinary current,

$$
J^a_\mu(x)\mathcal O_i(0)
\sim
\frac{x_\mu}{S_d(x^2)^{d/2}}(t^a\mathcal O)_i(0)+\cdots.
$$

For the stress tensor and a scalar primary, the leading singular terms are fixed by the dimension and translation action. Schematically,

$$
T_{\mu\nu}(x)\mathcal O(0)
\sim
\text{universal singular tensor depending on }\Delta_\mathcal O
+\text{terms generating }\partial_\mu\mathcal O
+\cdots.
$$

In three-point language, this says that $\langle J\mathcal O\mathcal O\rangle$ and $\langle T\mathcal O\mathcal O\rangle$ are not arbitrary once the physical $J$ and $T$ are normalized by charges. In unit-normalized operator conventions, the same statements become relations involving $C_J$ and $C_T$:

$$
\lambda_{\widehat J\mathcal O\mathcal O}\propto \frac{1}{\sqrt{C_J}},
\qquad
\lambda_{\widehat T\mathcal O\mathcal O}\propto \frac{\Delta_\mathcal O}{\sqrt{C_T}}.
$$

The proportionality constants are convention-dependent tensor-structure normalizations; the dependence on $C_J$, $C_T$, and $\Delta_\mathcal O$ is the invariant lesson.

## Contact terms, anomalies, and separated points

Many formulas in CFT are stated at separated points. Ward identities force us to care about coincident points.

A contact term is a distribution supported when two or more insertion points coincide. For example,

$$
\delta^{(d)}(x-x_i)
$$

is invisible in an ordinary separated-point correlator but essential when integrating a current divergence. Derivatives of delta functions also appear in stress-tensor Ward identities and in correlators of composite operators.

In curved space and in even dimensions, the trace of the stress tensor can have an anomaly:

$$
\langle T^\mu_{\ \mu}\rangle_g=\text{local curvature invariants}.
$$

In flat space at separated points this usually vanishes, but metric variations of the anomaly can leave contact terms in stress-tensor correlators. Similarly, background gauge anomalies modify current Ward identities.

For this chapter, the default assumption is: flat space, separated-point formulas unless contact terms are explicitly displayed, and no anomaly unless stated. Later pages on anomalies, two-dimensional CFT, and curved-space methods relax these assumptions.

## Worked example: why four points have two invariants

For $n$ scalar insertions in $d\geq2$, a rough dimension count says the number of coordinates is $nd$, while the conformal group has dimension

$$
\frac{(d+1)(d+2)}2.
$$

For $n=2$ and $n=3$, the conformal group is powerful enough to fix all point dependence up to constants. For $n=4$, two invariant combinations remain. These are the cross-ratios $u$ and $v$.

The Ward identities are the differential version of this counting. They say that $G_4$ is constant along conformal orbits in configuration space. The reduced correlator therefore lives on the quotient of four-point configurations by conformal transformations. For scalar four-point functions, this quotient is two-dimensional and can be coordinatized by $u,v$ or by $z,\bar z$.

This is why the bootstrap begins at four points. At two and three points, symmetry leaves constants. At four points, symmetry leaves functions, and consistency of the OPE becomes a nontrivial dynamical constraint.

## Common pitfalls

**Do not confuse separated-point conservation with the full Ward identity.** The equation $\partial\cdot J=0$ at $x\neq x_i$ is not the full statement. The delta functions at insertions are what encode charges.

**Do not forget spin terms.** Scalar Ward identities are clean, but spinning operators transform with additional rotation generators. Omitting these terms gives wrong tensor-structure constraints.

**Do not treat contact terms as unphysical.** Some contact terms are convention-dependent, but Ward-identity contact terms are required. Anomalies and central charges often reveal themselves precisely through contact terms or singular OPE terms.

**Do not expect conformal symmetry to determine four-point functions.** It reduces them to functions of cross-ratios. The OPE and crossing symmetry do the next job.

**Do not compare Ward-identity normalizations after rescaling currents.** Physical currents and stress tensors are normalized by charges. Unit-normalized operators are convenient in bootstrap, but their OPE coefficients contain $1/\sqrt{C_J}$ or $1/\sqrt{C_T}$ factors.

## Relations to other pages

[Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/) introduces Ward identities as symmetry statements. This page specializes them to correlation functions and contact terms.

[Current Correlators](/cft-bootstrap/correlation-functions/current-correlators/) gives the internal-symmetry example in detail. [Stress-Tensor Correlators](/cft-bootstrap/correlation-functions/stress-tensor-correlators/) gives the spacetime-symmetry example and explains $C_T$.

[Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/), [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/), and [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/) are the low-point outputs of the global Ward identities.

[Operator Product Expansion](/cft-bootstrap/operator-product-expansion/) turns Ward identities into singular OPE statements. [Crossing Symmetry and Bootstrap Logic](/cft-bootstrap/crossing-bootstrap-logic/) uses these constraints inside four-point consistency equations.

## Research status

The global conformal Ward identities and the local current/stress-tensor Ward identities are standard. Their use in fixing low-point correlators, normalizing currents, and deriving selection rules is part of the established CFT toolkit.

More technical questions remain active: classifying contact terms in general dimensions, organizing curved-space generating functionals, treating anomalies and boundaries, translating Euclidean Ward identities into Lorentzian ordered correlators, and implementing current/stress-tensor Ward constraints efficiently in large spinning bootstrap systems.

## Exercises

### Exercise 1: Scalar two-point function

Use translation, rotation, dilatation, and special conformal Ward identities to show that scalar primaries with unequal dimensions have vanishing two-point function.

<details><summary><strong>Solution</strong></summary>

Translation and rotation invariance give

$$
G_2=F(x_{12}^2).
$$

Dilatation invariance gives

$$
F(x_{12}^2)=\frac{C_{12}}{(x_{12}^2)^{(\Delta_1+\Delta_2)/2}}.
$$

Applying the special conformal Ward identity to this expression leaves a term proportional to

$$
(\Delta_1-\Delta_2)C_{12}.
$$

Thus $C_{12}=0$ unless $\Delta_1=\Delta_2$.

</details>

### Exercise 2: Three-point exponents

Assume a scalar three-point function has the form

$$
G_3=\frac{\lambda_{123}}
{(x_{12}^2)^{\alpha_{12}}(x_{23}^2)^{\alpha_{23}}(x_{31}^2)^{\alpha_{31}}}.
$$

Use scaling at each point to derive the exponents $\alpha_{ij}$.

<details><summary><strong>Solution</strong></summary>

The weight at point $x_1$ receives contributions from the factors involving $x_1$:

$$
\alpha_{12}+\alpha_{31}=\Delta_1.
$$

Similarly,

$$
\alpha_{12}+\alpha_{23}=\Delta_2,
\qquad
\alpha_{23}+\alpha_{31}=\Delta_3.
$$

Solving gives

$$
\alpha_{12}=\frac{\Delta_1+\Delta_2-\Delta_3}{2},
\qquad
\alpha_{23}=\frac{\Delta_2+\Delta_3-\Delta_1}{2},
\qquad
\alpha_{31}=\frac{\Delta_3+\Delta_1-\Delta_2}{2}.
$$

</details>

### Exercise 3: Integrated current Ward identity

Let $J_\mu$ be a $U(1)$ current and let $\mathcal O_i$ have charge $q_i$. Integrate the local Ward identity over a region containing a subset $B$ of insertions. What does the result say?

<details><summary><strong>Solution</strong></summary>

The local Ward identity is

$$
\partial_\mu\langle J^\mu(x)\prod_i\mathcal O_i(x_i)\rangle
=
\sum_i q_i\delta^{(d)}(x-x_i)
\langle\prod_i\mathcal O_i(x_i)\rangle.
$$

Integrating over a region $B$ and using the divergence theorem gives

$$
\int_{\partial B}dS_\mu\langle J^\mu(x)\prod_i\mathcal O_i(x_i)\rangle
=
\sum_{x_i\in B}q_i\langle\prod_i\mathcal O_i(x_i)\rangle.
$$

Thus the current flux through the boundary measures the total charge of the insertions inside the boundary, inside that correlator.

</details>

### Exercise 4: Why u and v are invariant

Show that

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}
$$

are invariant under translations, rotations, dilatations, and inversions. Conclude that they are invariant under the conformal group generated by these transformations.

<details><summary><strong>Solution</strong></summary>

Translations and rotations leave all squared distances $x_{ij}^2$ unchanged. Under a dilatation $x\mapsto\lambda x$, every squared distance picks up a factor $\lambda^2$, which cancels between numerator and denominator.

Under inversion $x^\mu\mapsto x^\mu/x^2$, squared distances transform as

$$
x_{ij}^2\mapsto\frac{x_{ij}^2}{x_i^2x_j^2}.
$$

In $u$, the numerator gains the factor

$$
\frac1{x_1^2x_2^2x_3^2x_4^2},
$$

and the denominator gains the same factor. Hence $u$ is invariant. The same argument applies to $v$. Since special conformal transformations are inversion–translation–inversion compositions, $u$ and $v$ are conformal invariants.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, especially the chapters on global conformal invariance, Ward identities, and the operator formalism.
- H. Osborn and A. Petkou, “Implications of conformal invariance in field theories for general dimensions,” *Annals of Physics* **231** (1994), for current and stress-tensor Ward identities in general-dimensional CFT.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, for conformal kinematics, Ward identities, and the route to bootstrap equations.
- D. Simmons-Duffin, *TASI Lectures on the Conformal Bootstrap*, for conformal Ward identities, reflection positivity, OPE, and numerical bootstrap setup.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), for the modern higher-dimensional CFT and bootstrap toolkit.

## Version history

- **2026-06-27:** Added a polished first version deriving global conformal Ward identities, local current and stress-tensor Ward identities, and their consequences for low-point correlators.
