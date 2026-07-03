---
title: "Boundaries and Interfaces"
description: "Boundaries and interfaces in QFT as codimension-one gluing data, including boundary conditions, folding, edge modes, displacement operators, symmetry, anomaly inflow, and conformal examples."
sidebar:
  label: "Boundaries and Interfaces"
  order: 8
level: Advanced
status: "Polished draft"
source: "Cardy boundary CFT; Coleman, Aspects of Symmetry; Srednicki §§22, 67–68, 82; Gaiotto–Kapustin–Seiberg–Willett; Kapustin–Saulina; Burgess Ch. 5; standard defect-QFT literature."
topics:
  - boundaries
  - interfaces
  - boundary conditions
  - folding trick
  - edge modes
  - boundary operators
  - anomaly inflow
canonicalTopics:
  - defects-extended-operators
  - boundary-qft
  - interfaces
  - anomaly-inflow
researchStatus:
  established:
    - "A boundary is an interface to the trivial theory, and a general interface is codimension-one local data coupling two QFTs."
    - "The variational principle fixes admissible boundary conditions and determines which charges and stress-tensor components are conserved."
  active:
    - "Classification of strongly coupled, anomalous, topological, and non-invertible interfaces remains an active research area."
---

## Summary

A **boundary** is where a QFT ends. An **interface** is where one QFT meets another. Both are codimension-one structures, and both are best treated as local QFT data living on a hypersurface.

The slogan is

$$
\text{boundary of }\mathcal T
=\text{interface }\mathcal T|\mathbf 1,
$$

where $\mathbf 1$ is the trivial theory.

An interface between $\mathcal T_L$ and $\mathcal T_R$ may reflect, transmit, absorb, or transform excitations. It may preserve some symmetries and break others. It may carry its own degrees of freedom. It may be topological, conformal, gapped, gapless, anomalous, invertible, or non-invertible.

This page gives the general language: variational principle, gluing conditions, boundary-local operators, displacement operators, folding, symmetry, anomaly inflow, and a few standard examples.

<figure class="doc-figure" style="--figure-width: 55rem;">

![Boundary conditions, interfaces, and the folding trick in QFT.](/figures/symmetry-anomalies-topology/boundary-interface-folding.svg)

<figcaption>

A boundary is codimension-one data for a QFT on a half-space. An interface couples two QFTs across a hypersurface. By the folding trick, an interface between $\mathcal T_L$ and $\mathcal T_R$ becomes a boundary condition for $\mathcal T_L\otimes\overline{\mathcal T_R}$, where the bar indicates orientation reversal.

</figcaption>
</figure>

## Prerequisites

You should know the previous pages on local versus extended operators, surface operators, disorder operators, twist operators, and domain walls as defects. The pages on Ward identities, background fields, anomaly inflow, and anomalies and boundaries are useful companions.

We write a codimension-one hypersurface as $\Sigma$. Local coordinates near it are

$$
x^\mu=(y,x^a),
$$

where $y$ is normal to $\Sigma$ and $x^a$ are tangential coordinates. For a boundary at $y=0$, take the bulk to be $y\ge 0$ unless stated otherwise.

## Boundary conditions are dynamical data

A boundary condition is not an afterthought. It is part of the definition of the QFT.

Take a real scalar field on the half-space $y\ge 0$ with action

$$
S_{\text{bulk}}=\int_{y\ge 0}d^dx\,
\left[
\frac12\partial_\mu\phi\partial^\mu\phi - V(\phi)
\right].
$$

Varying the action gives the bulk Euler–Lagrange equation plus a boundary term

$$
\delta S_{\text{bulk}}\supset
\int_{y=0}d^{d-1}x\,n_\mu\partial^\mu\phi\,\delta\phi.
$$

A well-posed variational principle requires this term to vanish after adding possible boundary terms and imposing allowed boundary variations.

For example:

$$
\begin{array}{ccl}
\text{Dirichlet} &:& \delta\phi|_{\partial M}=0,\\
\text{Neumann} &:& n_\mu\partial^\mu\phi|_{\partial M}=0,\\
\text{Robin} &:& n_\mu\partial^\mu\phi+\lambda_B\phi=0.
\end{array}
$$

Robin boundary conditions arise from adding

$$
S_{\partial}=\frac12\int_{\partial M}d^{d-1}x\,\lambda_B\phi^2,
$$

up to sign conventions for the normal and Lorentzian versus Euclidean action.

:::caution[Source note]
Boundary-condition signs depend on whether the outward normal is used and whether the action is Lorentzian $e^{iS}$ or Euclidean $e^{-S_E}$. The physical condition is not the sign in isolation, but the vanishing of the full boundary variation.
:::

This elementary example already contains the general lesson. A boundary condition specifies which variations are allowed, which boundary terms are present, and which boundary-local degrees of freedom are included.

## Interfaces as gluing conditions

An interface between two QFTs $\mathcal T_L$ and $\mathcal T_R$ is local data on $\Sigma$ coupling fields on the two sides:

$$
S=S_L[\Phi_L]+S_R[\Phi_R]
+\int_\Sigma d^{d-1}x\,
\mathcal L_\Sigma(\Phi_L|_\Sigma,\Phi_R|_\Sigma,\chi).
$$

Here $\chi$ denotes possible interface degrees of freedom.

The variational principle gives gluing conditions. For scalar fields with interface potential $U(\phi_L,\phi_R)$, one gets schematic conditions of the form

$$
n_\mu\partial^\mu\phi_L+\frac{\partial U}{\partial \phi_L}=0,
\qquad
- n_\mu\partial^\mu\phi_R+\frac{\partial U}{\partial \phi_R}=0,
$$

where $n$ points from left to right. The relative sign appears because the same normal points outward for one side and inward for the other.

An interface can impose continuity,

$$
\phi_L|_\Sigma=\phi_R|_\Sigma,
$$

but it need not. It can identify fields by a symmetry, impose a duality map, couple only certain sectors, or carry an independent lower-dimensional QFT.

## Boundary-local operators

Once a boundary or interface is present, there are new local operators supported on $\Sigma$. We denote them by

$$
\widehat{\mathcal O}(x^a).
$$

These are not the same as restrictions of bulk operators. Some boundary operators are limits of bulk fields; others are genuine boundary degrees of freedom.

A bulk operator approaching a boundary often admits a **boundary operator expansion**:

$$
\mathcal O(y,x^a)
\sim
\sum_{\widehat{\mathcal O}}
C_{\mathcal O\widehat{\mathcal O}}
(2y)^{\widehat\Delta-\Delta}
\widehat{\mathcal O}(x^a),
\qquad y\to 0,
$$

in a scale-invariant or conformal setting. This is the boundary analogue of the ordinary OPE.

For a general nonconformal boundary, the expansion is less constrained, but the conceptual point remains: the boundary has its own operator algebra.

## The folding trick

The **folding trick** turns an interface problem into a boundary problem.

An interface between $\mathcal T_L$ on $y<0$ and $\mathcal T_R$ on $y>0$ can be folded by reflecting the right theory across $\Sigma$. The result is a boundary condition for

$$
\mathcal T_L\otimes \overline{\mathcal T_R}
$$

on a half-space. The bar means orientation reversal. In Lorentzian language this reversal is tied to how the stress tensor, currents, spin structures, and anomaly terms transform.

The folding trick is especially powerful in two-dimensional CFT, where conformal interfaces can be studied using boundary-state technology. But the idea is more general: an interface is boundary data for a product theory with one side reversed.

:::note[What folding does not do]
Folding does not make a hard problem easy by magic. It changes the bookkeeping. The boundary condition for the folded product theory can still be strongly coupled, anomalous, or nonlocal-looking in microscopic variables.
:::

## Stress tensor, displacement, and momentum flow

A boundary or interface breaks translations normal to $\Sigma$. The corresponding Ward identity contains a displacement operator.

For a boundary at $y=0$,

$$
\partial_\mu T^{\mu y}=\delta(y)\,\mathcal D.
$$

The operator $\mathcal D$ measures the force density exerted on the boundary by the bulk. It is the generator of normal deformations of the boundary.

Tangential translations may still be preserved. If so, the combined bulk-plus-boundary stress tensor obeys

$$
\partial_\mu T^{\mu a}_{\text{bulk}}
+\delta(y)\partial_b\widehat T^{ba}=0,
$$

where $\widehat T^{ab}$ is the boundary stress tensor.

For an interface, energy and momentum can be transmitted, reflected, or stored on the wall. A transparent interface has no reflection. A totally reflecting boundary has no transmission because there is no second side. A topological interface has vanishing displacement in correlators and can be moved freely.

## Symmetries with boundaries

A boundary condition may preserve, break, or modify a global symmetry.

For a conserved bulk current,

$$
\partial_\mu j^\mu=0,
$$

the charge in a region with boundary changes by the flux through the boundary:

$$
\frac{dQ}{dt}=-\int_{\partial \text{space}} dS_i\,j^i.
$$

A boundary preserves the symmetry if the normal flux either vanishes or is absorbed into boundary degrees of freedom. In local form one may have

$$
n_\mu j^\mu + \partial_a \widehat j^a=0
\quad \text{on }\partial M,
$$

where $\widehat j^a$ is a boundary current.

Thus symmetry preservation is not always $n_\mu j^\mu=0$. A boundary can carry charge, and charge can flow between bulk and boundary while the total charge remains conserved.

For an interface between two theories, the preserved current may be a diagonal combination:

$$
j_L^\mu n_\mu-j_R^\mu n_\mu+\partial_a\widehat j^a=0.
$$

The signs again reflect normal-orientation conventions.

## Gauge fields and edge modes

Gauge theories make boundaries more subtle. Gauge redundancy itself is not a physical global symmetry, but gauge transformations that do not vanish at a boundary can act nontrivially on boundary data.

There are several common possibilities:

- impose boundary conditions that remove the would-be boundary variation;
- add boundary degrees of freedom that restore gauge invariance;
- allow edge modes carrying a physical global symmetry inherited from boundary gauge transformations;
- couple the boundary to a lower-dimensional anomalous theory whose anomaly is canceled by bulk inflow.

For Maxwell theory, electric and magnetic boundary conditions lead to different boundary operator algebras. In nonabelian gauge theory, choices of boundary condition can preserve different subgroups, support boundary matter, or change the spectrum of allowed line operators ending on the boundary.

This is one reason boundaries are not merely “spacetime with an edge.” They can change the physical Hilbert space.

## Anomaly inflow and anomalous boundaries

A standalone anomalous theory cannot be consistently defined as an ordinary QFT with the anomalous symmetry gauged. But it can appear at the boundary of a higher-dimensional bulk whose variation cancels the anomaly.

Schematically,

$$
\delta_\alpha S_{\text{bulk}}=-\delta_\alpha W_{\partial}.
$$

The combined system is gauge invariant or symmetry consistent even though neither part is separately invariant.

This has two important consequences.

First, a boundary of an SPT phase often realizes an anomalous symmetry action. The boundary cannot be trivially gapped while preserving all symmetries, unless it develops topological order or other nontrivial infrared structure.

Second, if a QFT has an ’t Hooft anomaly, it can be viewed as living naturally on the boundary of an invertible anomaly theory in one higher dimension.

Interfaces have the same logic. An interface can carry the difference between anomaly theories on the two sides. If $\mathcal T_L$ and $\mathcal T_R$ have different anomaly classes, an interface preserving the symmetry must supply the mismatch.

## Conformal boundaries and interfaces

At a conformal fixed point, a boundary condition is **conformal** if it preserves the subgroup of the conformal group that maps the boundary to itself. For a flat boundary in $d$ dimensions, this subgroup is

$$
SO(d-1,2)
$$

in Lorentzian signature.

Conformal boundaries and defects have special constraints:

- one-point functions of bulk operators can be nonzero;
- bulk two-point functions depend on a conformal cross-ratio involving the distance to the boundary;
- boundary operators have their own scaling dimensions;
- the displacement operator has protected dimension $d$ for a codimension-one conformal defect;
- boundary RG flows can have monotonicity theorems in special dimensions.

In two dimensions, boundary CFT is especially powerful. Boundaries can be described by boundary states, Cardy conditions, and open-channel/closed-channel consistency. Interfaces can often be analyzed by folding.

This page only sets the language. The CFT and Bootstrap volume is the canonical home for the full conformal machinery.

## Topological interfaces

A topological interface is an interface whose position can be deformed without changing correlators, away from contact terms. It behaves like a generalized symmetry operation.

If it is invertible, it often implements an equivalence or duality between theories. If it is non-invertible, its fusion may take the form

$$
\mathcal N\times \mathcal N
=\sum_i N_i\mathcal D_i,
$$

rather than the identity.

Topological interfaces are central in two-dimensional CFT, TQFT, lattice dualities, and modern generalized symmetry. They are also the cleanest way to say that a duality is not merely an equality of partition functions but a map between operator sectors, defects, and boundary conditions.

## Interfaces and RG flow

Not every interface is conformal or topological. An interface can itself undergo RG flow. Starting from microscopic interface data, the bulk theories may flow to fixed points while the interface flows to a conformal boundary condition or defect.

This is common in condensed matter: an impurity, junction, or material boundary may be irrelevant, relevant, or exactly marginal at a bulk critical point.

A useful diagnostic is whether the interface introduces relevant boundary operators. If so, the infrared boundary condition may differ from the ultraviolet one even when the bulk fixed point is unchanged.

The same idea appears in high-energy language as a brane, wall, or boundary RG flow.

## Examples

### Free scalar on a half-space

Dirichlet and Neumann boundary conditions are the simplest examples:

$$
\phi|_{y=0}=0,
\qquad
\partial_y\phi|_{y=0}=0.
$$

In Euclidean correlators, the method of images gives the Green function on the half-space as

$$
G_{D/N}(x,x')=G_0(x-x')\mp G_0(x-\bar x'),
$$

where $\bar x'$ is the mirror point and the minus/plus sign gives Dirichlet/Neumann respectively.

### Interface between two scalar theories

Let two free scalar theories meet at $y=0$. One can impose

$$
\phi_L=\phi_R,
\qquad
\partial_y\phi_L=\kappa\,\partial_y\phi_R,
$$

with coefficients chosen so that energy flux is conserved. Such interfaces can transmit and reflect waves.

### Boundary of a topological phase

A bulk Chern–Simons term on a manifold with boundary is not gauge invariant by itself. Gauge invariance can be restored by boundary chiral modes or by suitable boundary conditions. This is the field-theoretic origin of edge modes in quantum Hall systems.

### Symmetry-breaking boundary

A boundary may explicitly break a bulk symmetry. For example, a spin system with a boundary magnetic field breaks spin-flip symmetry at the edge even if the bulk Hamiltonian preserves it.

## Common pitfalls

### Boundary condition does not mean “set the field to zero”

Dirichlet is one boundary condition, not the definition of a boundary. Neumann, Robin, mixed, dynamical, topological, and anomalous boundary conditions are equally legitimate when the variational principle and symmetries allow them.

### A boundary may carry its own QFT

Boundary-local degrees of freedom are not decorative. They can carry charge, cancel anomalies, change RG flows, and host independent operator algebras.

### Folding reverses orientation

The folded theory is $\mathcal T_L\otimes\overline{\mathcal T_R}$, not just $\mathcal T_L\otimes\mathcal T_R$. Orientation reversal matters for chiral theories, Chern–Simons terms, fermions, and anomalies.

### Gauge edge modes are physical only after the redundancy is handled correctly

Not every gauge parameter at the boundary is a new global symmetry. One must specify the phase space, boundary conditions, and allowed gauge transformations.

### Topological interfaces are not generic interfaces

Most material interfaces reflect or absorb energy. Topological interfaces are special objects with vanishing displacement operator and strong algebraic constraints.

## Relation to nearby pages

The previous page treats domain walls as codimension-one defects. This page generalizes that discussion to boundaries and interfaces. The next pages on defect fusion and defect correlation functions explain how interfaces compose and how local operators living on defects enter correlation functions.

The anomaly-inflow pages explain why some boundaries are not standalone QFTs. The CFT and Bootstrap volume develops BCFT and defect CFT. The Matter volume develops physical boundary and edge modes in topological phases.

## Research status

The variational and operator language of boundaries and interfaces is standard. Boundary CFT, TQFT boundary conditions, gauge-theory edge modes, and anomaly inflow are all mature subjects.

The active frontier concerns classification and dynamics: which strongly coupled boundaries exist, how interfaces compose, how anomalies constrain gapped boundaries, how non-invertible interfaces act, and how boundary RG flows are organized beyond perturbation theory.

## Exercises

### Exercise 1: Derive Robin boundary conditions

For a scalar field on $y\ge 0$, add

$$
S_\partial=\frac12\int_{y=0}d^{d-1}x\,\lambda_B\phi^2.
$$

Assuming the outward normal is $n=-\partial_y$, derive the boundary condition.

<details><summary><strong>Solution</strong></summary>

The bulk variation gives

$$
\delta S_{\text{bulk}}\supset
\int_{y=0}d^{d-1}x\,n_\mu\partial^\mu\phi\,\delta\phi.
$$

The boundary variation is

$$
\delta S_\partial
=\int_{y=0}d^{d-1}x\,\lambda_B\phi\,\delta\phi.
$$

For arbitrary boundary variation $\delta\phi$, the coefficient must vanish:

$$
n_\mu\partial^\mu\phi+\lambda_B\phi=0.
$$

With $n=-\partial_y$, this is

$$
-\partial_y\phi+\lambda_B\phi=0,
$$

up to the Lorentzian sign convention for the kinetic term.

</details>

### Exercise 2: Boundary as interface to the trivial theory

Explain why boundary-local operators are the same kind of data as interface-local operators when the right-hand theory is trivial.

<details><summary><strong>Solution</strong></summary>

An interface-local operator is supported on the hypersurface separating two theories. It can depend on fields restricted from the left, fields restricted from the right, and intrinsic interface fields. If the right-hand theory is trivial, there are no right bulk fields. What remains are operators depending on the left bulk fields restricted to the hypersurface and on intrinsic hypersurface degrees of freedom. Those are exactly boundary-local operators.

</details>

### Exercise 3: Charge conservation with a boundary current

Suppose

$$
\partial_\mu j^\mu=0
$$

in the bulk, but on the boundary

$$
n_\mu j^\mu+\partial_a\widehat j^a=0.
$$

Show that the total charge including the boundary contribution is conserved.

<details><summary><strong>Solution</strong></summary>

Let

$$
Q_{\text{bulk}}=\int_{\text{space}} d^{d-1}x\,j^0,
\qquad
Q_{\partial}=\int_{\partial\text{space}}d^{d-2}x\,\widehat j^0.
$$

Bulk current conservation gives

$$
\frac{dQ_{\text{bulk}}}{dt}=-\int_{\partial\text{space}}d^{d-2}x\,n_i j^i.
$$

The boundary equation gives

$$
\frac{dQ_{\partial}}{dt}=\int_{\partial\text{space}}d^{d-2}x\,n_i j^i,
$$

assuming no boundary-of-boundary flux. Therefore

$$
\frac{d}{dt}(Q_{\text{bulk}}+Q_{\partial})=0.
$$

</details>

### Exercise 4: Folding an interface

Let an interface separate $\mathcal T_L$ from $\mathcal T_R$. Why does folding produce $\mathcal T_L\otimes\overline{\mathcal T_R}$ rather than $\mathcal T_L\otimes\mathcal T_R$?

<details><summary><strong>Solution</strong></summary>

Folding reflects the right half-space across the interface. Reflection reverses orientation. Any term sensitive to orientation, such as a chiral current algebra, fermion spin structure, Chern–Simons term, or anomaly polynomial descendant, changes accordingly. The folded right theory must therefore be the orientation-reversed theory $\overline{\mathcal T_R}$. The interface condition becomes a boundary condition for the product theory on one side.

</details>

## References

- J. L. Cardy, “Boundary Conformal Field Theory,” arXiv:hep-th/0411189.
- M. Oshikawa and I. Affleck, “Boundary conformal field theory approach to the two-dimensional critical Ising model with a defect line,” arXiv:cond-mat/9612187.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” arXiv:1412.5148.
- J. Fuchs, C. Schweigert, and A. Valentino, “A geometric approach to boundaries and surface defects in Dijkgraaf–Witten theories,” arXiv:1307.3632.
- A. Kapustin and N. Saulina, “Topological boundary conditions in abelian Chern–Simons theory,” arXiv:1008.0654.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, Chs. 8–10, for topological field theory, anomalies, and gauge-theory boundary/response language.

## Version history

- 2026-06-19: Initial polished draft.
