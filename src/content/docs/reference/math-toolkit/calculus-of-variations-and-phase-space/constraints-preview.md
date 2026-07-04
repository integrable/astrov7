---
title: "Constraints Preview"
description: "A QFT-oriented preview of constrained Hamiltonian systems, weak equality, first-class and second-class constraints, Dirac brackets, gauge generators, and reduced phase space."
sidebar:
  label: "Constraints Preview"
  order: 7
level: Graduate
status: "Polished draft"
source: "Standard constrained Hamiltonian dynamics and gauge-theory references, including Dirac, Bergmann, Henneaux–Teitelboim, Gotay–Nester, Arnold, Frankel, Nakahara, Coleman, Srednicki, Weinberg, Schwartz, and Zee."
topics:
  - constraints
  - Dirac brackets
  - gauge generators
  - first-class constraints
  - second-class constraints
  - reduced phase space
canonicalTopics:
  - constrained-hamiltonian-systems
  - dirac-bracket
  - first-class-constraint
  - second-class-constraint
  - gauge-redundancy
researchStatus:
  established:
    - "The Dirac–Bergmann analysis of constrained Hamiltonian systems is the standard local framework behind canonical gauge theory, gauge fixing, and the transition from singular Lagrangians to reduced phase space."
  active:
    - "Constraints in field theories with boundaries, edge modes, asymptotic symmetries, gravity, irregular constraint surfaces, and BV-BRST formulations require additional geometric and functional-analytic care."
---

## Summary

A **constraint** is a relation among phase-space variables that holds because the Legendre transform is not freely invertible, because a gauge condition has been imposed, or because a theory has redundant variables. In canonical language, constraints are functions

$$
\phi_a(q,p)\approx 0
$$

on phase space. The symbol $\approx$ means **weak equality**: the equation is true after restricting to the constraint surface, but it should not be used inside Poisson brackets until the bracket has been computed.

The basic constrained Hamiltonian story is:

$$
L(q,\dot q)
\quad\longrightarrow\quad
p_i=\frac{\partial L}{\partial\dot q^i}
\quad\longrightarrow\quad
\phi_a(q,p)\approx0.
$$

If the Hessian

$$
W_{ij}=\frac{\partial^2L}{\partial\dot q^i\partial\dot q^j}
$$

is singular, not all velocities can be solved in terms of $(q,p)$. The image of the Legendre map is then a subspace of phase space rather than all of phase space. That subspace is cut out by **primary constraints**.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Flow diagram for the Dirac constraint algorithm: singular Legendre map, primary constraints, total Hamiltonian, consistency conditions, first-class and second-class split, and reduced phase space.](/figures/math-toolkit/constraints-dirac-algorithm.svg)

<figcaption>

The local Dirac–Bergmann workflow. A singular Legendre map gives primary constraints. Preserving constraints under Hamiltonian evolution can produce secondary constraints or determine multipliers. First-class constraints generate degeneracies of the presymplectic form; second-class constraints are removed by restriction or by the Dirac bracket.

</figcaption>
</figure>

The total Hamiltonian has the form

$$
H_T=H_c+u^a\phi_a,
$$

where $H_c$ is the canonical Hamiltonian and the functions $u^a(t)$ are Lagrange multipliers. Consistency requires

$$
\dot\phi_a\approx \{\phi_a,H_T\}\approx0.
$$

These equations may determine some multipliers, produce new constraints, or hold automatically.

A constraint is **first-class** if its Poisson bracket with every constraint vanishes weakly:

$$
\{\phi_a,\phi_b\}\approx0.
$$

A first-class constraint signals a degeneracy direction of the presymplectic form and, in gauge theories, is tied to gauge redundancy.

A set of constraints $\chi_a$ is **second-class** if the constraint matrix

$$
C_{ab}=\{\chi_a,\chi_b\}
$$

is invertible on the constraint surface. Second-class constraints are handled by replacing the Poisson bracket with the **Dirac bracket**

$$
\{F,G\}_D
=
\{F,G\}
-
\{F,\chi_a\}C^{ab}\{\chi_b,G\},
$$

where $C^{ab}$ is the inverse matrix, $C^{ab}C_{bc}=\delta^a{}_c$.

In QFT, constraints are everywhere: Maxwell theory, Yang–Mills theory, general relativity, Chern–Simons theory, fermionic systems, gauge-fixed path integrals, and any canonical treatment of redundant variables. This page is only a preview, but it gives the vocabulary needed to read those later pages without getting eaten by notation goblins.

## Prerequisites

You should know [Legendre Transforms](/math-toolkit/calculus-of-variations-and-phase-space/legendre-transforms/), [Symplectic Forms](/math-toolkit/calculus-of-variations-and-phase-space/symplectic-forms/), and [Poisson Brackets](/math-toolkit/calculus-of-variations-and-phase-space/poisson-brackets/). You should also know [Boundary Terms and Functional Differentiability](/math-toolkit/calculus-of-variations-and-phase-space/boundary-terms-and-functional-differentiability/), because in field theory a would-be constraint or Hamiltonian generator is not meaningful until its boundary variation is controlled.

The distributional normalization used for field-theory constraints follows [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/) and [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/). The path-integral cousin of this page is [Faddeev–Popov Determinants Preview](/math-toolkit/functional-integrals-determinants/faddeev-popov-determinants-preview/).

This page uses the Poisson-bracket convention

$$
\{q^i,p_j\}=\delta^i{}_j,
\qquad
\dot F=\{F,H\}+\frac{\partial F}{\partial t}.
$$

## Core idea

Ordinary Hamiltonian mechanics assumes that the Legendre map

$$
(q,\dot q)\mapsto(q,p),
\qquad
p_i=\frac{\partial L}{\partial\dot q^i},
$$

can be inverted for the velocities $\dot q^i$. Then one can define

$$
H(q,p)=p_i\dot q^i-L(q,\dot q)
$$

with all velocities written in terms of $(q,p)$.

Gauge theories break this assumption in the most productive possible way. Some velocities either do not appear in the Lagrangian or appear only through combinations. Then the momenta satisfy relations. Those relations are constraints.

For example, in Maxwell theory with Lagrangian density

$$
\mathcal L=-\frac14 F_{\mu\nu}F^{\mu\nu},
$$

the time derivative $\dot A_0$ does not appear. Therefore

$$
\pi^0=\frac{\partial\mathcal L}{\partial\dot A_0}=0
$$

is a primary constraint. Preserving it in time gives Gauss's law,

$$
\partial_i\pi^i\approx0
$$

in the absence of charged matter. The pair is not an accident of electromagnetism. It is the canonical trace left by gauge redundancy.

The geometric picture is this:

$$
\text{phase space }\mathcal P
\supset
\text{constraint surface }\mathcal C
\longrightarrow
\text{physical phase space }\mathcal P_{\rm phys}.
$$

On $\mathcal P$ the symplectic form is nondegenerate. When pulled back to $\mathcal C$, it may acquire null directions. Those null directions are gauge directions. The physical phase space is obtained, locally and when all goes well, by quotienting the constraint surface by the gauge orbits:

$$
\mathcal P_{\rm phys}\simeq \mathcal C/\mathcal G.
$$

The phrase “when all goes well” is doing work. Global gauge slices may fail to exist; constraint surfaces can be singular; boundaries can turn gauge transformations into physical symmetries; and field spaces are infinite-dimensional. The local finite-dimensional picture is still the right starting point.

## Setup and conventions

Let $\mathcal P$ be a phase space with coordinates $(q^i,p_i)$ and Poisson bracket $\{\cdot,\cdot\}$. A constraint is a function $\phi_a\in C^\infty(\mathcal P)$ whose vanishing defines a surface

$$
\mathcal C=\{z\in\mathcal P\mid \phi_a(z)=0\text{ for all }a\}.
$$

One writes

$$
\phi_a\approx0
$$

rather than $\phi_a=0$ to remind oneself that the equation holds only after restriction to $\mathcal C$.

A function $F$ is **weakly zero** if

$$
F|_{\mathcal C}=0.
$$

A function $F$ is **strongly zero** if it is zero as a function on the original phase space.

The distinction matters because Poisson brackets differentiate functions away from $\mathcal C$. If $F\approx0$, it does not follow that

$$
\{F,G\}\approx0
$$

for arbitrary $G$. A one-line example is

$$
F=p,
\qquad
G=q,
\qquad
p\approx0.
$$

On the surface $p=0$, $F$ vanishes, but

$$
\{p,q\}=-1.
$$

So constraints can vanish while their Hamiltonian vector fields do not.

The canonical Hamiltonian is obtained from the Legendre transform where possible:

$$
H_c=p_i\dot q^i-L.
$$

The total Hamiltonian is

$$
H_T=H_c+u^a\phi_a,
$$

where the $u^a$ are multipliers. They are not arbitrary decorations. They encode the unresolved velocities associated with the singular Legendre map.

## Primary and secondary constraints

A **primary constraint** appears directly from the definition of the momenta. If

$$
\operatorname{rank}\frac{\partial^2L}{\partial\dot q^i\partial\dot q^j}<n,
$$

then the momenta cannot be independent. The image of the Legendre map is locally described by equations

$$
\phi_a(q,p)=0.
$$

These are primary constraints.

A **secondary constraint** appears by demanding time preservation of a primary constraint. Since a constraint must remain true along the motion,

$$
\dot\phi_a\approx0.
$$

Using Hamiltonian evolution,

$$
\dot\phi_a\approx \{\phi_a,H_T\}
=\{\phi_a,H_c\}+u^b\{\phi_a,\phi_b\}\approx0.
$$

This condition has three possible outcomes.

First, it may hold automatically. Then it gives no new information.

Second, it may determine one or more multipliers $u^b$. Then those directions were not gauge freedom; the equations of motion fix them.

Third, it may impose a new condition

$$
\psi(q,p)\approx0.
$$

Then $\psi$ is a secondary constraint. It must also be preserved in time, so the algorithm continues.

The terminology “primary,” “secondary,” “tertiary,” and so on records where the constraint appeared in the algorithm, not its physical importance. Gauss's law in Maxwell theory is secondary in this sense, but physically it is hardly second-tier. Tiny terminology trap. Classic.

## The Dirac–Bergmann algorithm

The local algorithm is:

1. Compute the canonical momenta.
2. Identify primary constraints $\phi_a\approx0$.
3. Form the total Hamiltonian $H_T=H_c+u^a\phi_a$.
4. Demand time preservation of the constraints.
5. Add any new constraints.
6. Repeat until no new constraints appear.
7. Classify the final constraints into first-class and second-class constraints.
8. Reduce the phase space, impose gauge fixing, or introduce Dirac brackets as appropriate.

Written in equations, the stability condition at each stage is

$$
\dot\Phi_A
\approx
\{\Phi_A,H_T\}
\approx0,
$$

where $\Phi_A$ denotes all constraints found so far.

The algorithm is local. It assumes that the constraint surface is reasonably smooth, that the rank of the constraint matrix is stable, and that the Hamiltonian vector fields exist with suitable boundary conditions. Field theory can violate any of these assumptions. This is why canonical gauge theory is both powerful and occasionally spicy.

## First-class constraints

A constraint $\phi_a$ is **first-class** if its Poisson bracket with every constraint vanishes weakly:

$$
\{\phi_a,\Phi_A\}\approx0
$$

for all constraints $\Phi_A$ in the final constraint set.

Equivalently, the Hamiltonian vector field generated by $\phi_a$ is tangent to the constraint surface. In geometric language, first-class constraints generate null directions of the presymplectic form pulled back to the constraint surface.

Let $\iota:\mathcal C\hookrightarrow\mathcal P$ be the inclusion. If $\Omega$ is the symplectic form on $\mathcal P$, then

$$
\Omega_{\mathcal C}=\iota^*\Omega
$$

is closed but may be degenerate. Its kernel consists of vectors $Y$ tangent to $\mathcal C$ such that

$$
\iota_Y\Omega_{\mathcal C}=0.
$$

These are the infinitesimal gauge directions in the clean case.

A first-class constraint generates a transformation

$$
\delta_\epsilon F=\epsilon^a\{F,\phi_a\}.
$$

For a gauge theory, these transformations move along gauge orbits rather than changing the physical state.

There is a caveat worth stating early. In realistic field theories, the actual generator of a gauge transformation is often a tuned combination of primary and secondary first-class constraints, sometimes plus boundary terms. It is safer to say:

:::note[First-class constraints and gauge transformations]
First-class constraints signal gauge degeneracy. The full gauge generator is constructed from the first-class constraint chain and must be functionally differentiable, including boundary terms when present.
:::

This caveat prevents many canonical-gravity headaches from metastasizing.

## Second-class constraints

A set of constraints $\chi_a$ is **second-class** if the matrix

$$
C_{ab}=\{\chi_a,\chi_b\}
$$

is invertible on the constraint surface.

Second-class constraints do not generate gauge redundancy. They remove degrees of freedom directly. The standard ways to handle them are:

- solve them explicitly and restrict to the reduced surface;
- or keep the original variables and replace the Poisson bracket by the Dirac bracket.

The Dirac bracket is

$$
\{F,G\}_D
=
\{F,G\}
-
\{F,\chi_a\}C^{ab}\{\chi_b,G\},
$$

where

$$
C^{ab}C_{bc}=\delta^a{}_c.
$$

Its defining magic trick is

$$
\{F,\chi_a\}_D=0
$$

for every $F$. Therefore second-class constraints can be set strongly to zero after replacing $\{\cdot,\cdot\}$ by $\{\cdot,\cdot\}_D$.

This is not cosmetic. If one imposes second-class constraints by hand while continuing to use the original Poisson bracket, the bracket may push observables away from the constraint surface. The Dirac bracket corrects the bracket so that the constrained surface is respected.

## Degree-of-freedom counting

For a finite-dimensional phase space of dimension $2N$, suppose there are $F$ independent first-class constraints and $S$ independent second-class constraints. Under the usual regularity assumptions, the physical phase-space dimension is

$$
\dim\mathcal P_{\rm phys}=2N-2F-S.
$$

The number of physical configuration-space degrees of freedom is therefore

$$
N_{\rm phys}=N-F-\frac{S}{2}.
$$

Why does a first-class constraint remove two phase-space dimensions? One dimension is removed by the constraint equation itself; the other is removed by quotienting along the gauge orbit it generates. A second-class constraint removes only one phase-space dimension, but second-class constraints come in even-dimensional symplectic pairs under good regularity assumptions.

For field theory, the same counting is applied mode-by-mode or per spatial point, but constraints, boundary conditions, zero modes, and global sectors can modify the naive answer.

## Maxwell theory as the canonical example

Use mostly-minus metric conventions and write the Maxwell action as

$$
S=-\frac14\int d^4x\,F_{\mu\nu}F^{\mu\nu}.
$$

The canonical momenta are

$$
\pi^\mu=\frac{\partial\mathcal L}{\partial\dot A_\mu}.
$$

Since $F_{00}=0$ and $\dot A_0$ does not appear,

$$
\pi^0\approx0
$$

is a primary constraint.

The spatial momenta are essentially the electric field, up to convention-dependent signs tied to whether one works with $A_i$ or $A^i$. The canonical Hamiltonian has the schematic form

$$
H_c=\int d^3\mathbf x\,
\left[\frac12\mathbf E^2+\frac12\mathbf B^2-A_0\,\partial_i\pi^i\right],
$$

for the no-charge case, with signs fixed by the precise canonical variables. Preserving the primary constraint gives

$$
\dot\pi^0(\mathbf x)
\approx
\{\pi^0(\mathbf x),H_T\}
\approx
\partial_i\pi^i(\mathbf x)
\approx0.
$$

Thus Gauss's law appears as a secondary constraint:

$$
\mathcal G(\mathbf x)=\partial_i\pi^i(\mathbf x)\approx0.
$$

The smeared Gauss constraint

$$
G[\lambda]
=
\int d^3\mathbf x\,\lambda(\mathbf x)\partial_i\pi^i(\mathbf x)
$$

generates gauge transformations of the spatial potential. If boundary terms vanish, integration by parts gives

$$
G[\lambda]
= -\int d^3\mathbf x\,\partial_i\lambda\,\pi^i.
$$

Then

$$
\delta_\lambda A_i(\mathbf x)
=
\{A_i(\mathbf x),G[\lambda]\}
=-\partial_i\lambda(\mathbf x),
$$

with the sign depending on the convention for $G[\lambda]$. The content is invariant: Gauss's law generates $U(1)$ gauge transformations.

If $\lambda$ does not vanish at the boundary, the integration by parts produces a boundary term. Then the generator must be improved, and the boundary value of $\lambda$ may act as a physical global symmetry rather than a pure gauge redundancy. This is the seed of charges at infinity and edge-mode stories.

## Gauge fixing and second-class pairs

Gauge fixing turns first-class redundancy into second-class constraints. In Maxwell theory, a common gauge condition is Coulomb gauge,

$$
\partial_i A^i\approx0.
$$

Together with Gauss's law,

$$
\partial_i\pi^i\approx0,
$$

it forms a second-class pair, because their bracket gives an elliptic operator:

$$
\{\partial_i A^i(\mathbf x),\partial_j\pi^j(\mathbf y)\}
=
\nabla^2\delta^{(3)}(\mathbf x-\mathbf y),
$$

up to sign conventions. Inverting this operator produces the transverse projector. The Dirac bracket then keeps only transverse photon degrees of freedom.

This is the canonical version of a familiar statement: gauge fixing chooses one representative from each gauge orbit. But it works only where the gauge condition is good and where the relevant differential operator has no problematic zero modes. On compact spaces, with boundaries, or in non-Abelian gauge theory, this warning becomes essential.

## Field-theory constraints are distributions

In field theory, constraints are usually local densities. A constraint such as

$$
\mathcal G(\mathbf x)=\partial_i\pi^i(\mathbf x)\approx0
$$

is not best understood as uncountably many independent ordinary equations. It should be smeared against a test function:

$$
G[\lambda]
=
\int_\Sigma d^{d-1}\mathbf x\,\lambda(\mathbf x)\mathcal G(\mathbf x).
$$

The Poisson bracket of local constraints is then defined distributionally. For example,

$$
\{\mathcal G(\mathbf x),\mathcal G(\mathbf y)\}=0
$$

in Abelian gauge theory, while non-Abelian Yang–Mills theory has schematically

$$
\{G[\alpha],G[\beta]\}=G([\alpha,\beta]),
$$

where $[\alpha,\beta]^a=f^a{}_{bc}\alpha^b\beta^c$.

A local expression involving derivatives of delta functions should normally be checked by smearing. The smeared form reveals boundary terms, differentiability conditions, and whether an apparently zero expression hides a surface charge.

## Constraints and the path integral

The canonical and path-integral languages handle the same redundancy differently.

In canonical language, first-class constraints are imposed on states or used to reduce phase space. In a schematic quantum theory one might write

$$
\widehat\phi_a|\psi_{\rm phys}\rangle=0,
$$

with serious domain, ordering, anomaly, and regularization caveats.

In path-integral language, gauge redundancy is usually handled by gauge fixing and a Faddeev–Popov determinant:

$$
\frac{1}{\operatorname{Vol}\mathcal G}
\int\mathcal D A
\quad\leadsto\quad
\int\mathcal D A\,\delta(G[A])\Delta_{\rm FP}[A].
$$

The two languages meet because gauge fixing a first-class constrained system produces second-class constraints, whose determinant is the canonical cousin of the Faddeev–Popov determinant.

For many practical calculations, the path-integral route is faster. The canonical route explains what the redundancy is doing to phase space and Hilbert space. Both are useful; neither is allowed to bully the other at lunch.

## Boundaries and differentiability

A constraint generator must be functionally differentiable. Suppose a smeared generator has variation

$$
\delta G[\lambda]
=\int_\Sigma \text{bulk terms}+\int_{\partial\Sigma}\text{boundary terms}.
$$

If the boundary term does not vanish under the allowed boundary conditions, then $G[\lambda]$ is not a well-defined Hamiltonian generator. One must either restrict $\lambda$, change boundary conditions, or add a boundary charge $Q[\lambda]$ so that

$$
\widetilde G[\lambda]=G[\lambda]+Q[\lambda]
$$

has a clean variation.

This is more than bookkeeping. Transformations that look like gauge transformations in the bulk can become physical symmetries at the boundary. In electrodynamics they give electric charges. In gravity they lead to ADM charges, BMS charges, and related asymptotic symmetry structures. In Chern–Simons theory, boundary degrees of freedom can become a full lower-dimensional theory.

The moral is simple:

$$
\text{gauge in the bulk} + \text{boundary conditions}
\neq
\text{always pure redundancy}.
$$

## Fermionic and graded constraints

Fermionic systems require graded Poisson brackets. For Grassmann-odd variables, signs depend on the parity of the variables being bracketed. The conceptual structure remains similar: constraints can be first-class or second-class, gauge generators can be graded, and second-class fermionic constraints lead to graded Dirac brackets.

A standard example is the passage from a first-order fermion action to canonical anticommutation relations. Because the fermion Lagrangian is first-order in time derivatives, the canonical momenta are not independent of the fermion variables. This produces second-class constraints. The corresponding Dirac bracket is the classical precursor of the fermionic anticommutator.

This page does not develop the graded formalism in detail. The important preview is that “constraint” is not only a gauge-boson phenomenon. First-order systems, spinors, ghosts, topological theories, and supersymmetric systems all use constrained phase-space geometry.

## Common pitfalls

### Setting constraints strongly to zero too early

If $\phi\approx0$, you may restrict final answers to $\phi=0$. But you should not replace $\phi$ by zero before taking Poisson brackets. The bracket differentiates away from the constraint surface.

Bad:

$$
\phi\approx0\quad\Rightarrow\quad \{\phi,G\}=0.
$$

Good:

$$
\text{compute }\{\phi,G\}\text{ first, then restrict to }\mathcal C.
$$

### Confusing primary with important

Primary means “appears directly from the momentum definition.” It does not mean “physically more fundamental.” Gauss's law is secondary in Maxwell theory but central to the physics.

### Saying every first-class constraint is automatically the gauge generator

First-class constraints signal gauge degeneracy, but the actual gauge generator can involve a chain of constraints and boundary improvements. This distinction is especially important in electromagnetism, Yang–Mills theory, and gravity.

### Treating gauge fixing as harmless

Gauge fixing can create second-class constraints and determinants. A bad gauge fixing can miss configurations, introduce zero modes, or encounter Gribov copies. Locally it may be fine; globally it may be a tiny haunted house.

### Forgetting boundaries

A generator that is not functionally differentiable is not a generator. Boundary terms decide which transformations are pure gauge and which carry charges.

### Thinking second-class means unphysical

Second-class constraints are not “fake constraints.” They are real restrictions on phase space. They often arise from gauge fixing or from first-order actions, and they directly determine the correct bracket structure.

## Relations to other pages

[Legendre Transforms](/math-toolkit/calculus-of-variations-and-phase-space/legendre-transforms/) explains how constraints first appear from a singular velocity–momentum map.

[Symplectic Forms](/math-toolkit/calculus-of-variations-and-phase-space/symplectic-forms/) explains the geometric structure that becomes degenerate on a first-class constraint surface.

[Poisson Brackets](/math-toolkit/calculus-of-variations-and-phase-space/poisson-brackets/) gives the bracket used throughout this page, including functional brackets for fields.

[Boundary Terms and Functional Differentiability](/math-toolkit/calculus-of-variations-and-phase-space/boundary-terms-and-functional-differentiability/) explains why generators need boundary terms before they define Hamiltonian flows.

[Faddeev–Popov Determinants Preview](/math-toolkit/functional-integrals-determinants/faddeev-popov-determinants-preview/) gives the path-integral companion to gauge fixing and constraint determinants.

## Research status

The local Dirac–Bergmann framework for regular finite-dimensional constrained systems is established. Its use in canonical gauge theory, Coulomb gauge, canonical electromagnetism, Yang–Mills theory, and the canonical route to quantization is standard.

The frontier begins when the assumptions become fragile: infinite-dimensional phase spaces, boundaries, asymptotic symmetries, edge modes, Gribov regions, singular constraint strata, anomalies in constraint algebras, and gravity. In these settings the slogan “first-class means gauge” must be refined using differentiability, boundary conditions, global topology, and sometimes BV-BRST language.

## Exercises

### Exercise 1: Weak equality is not strong equality

Let $\mathcal P=\mathbb R^2$ with coordinates $(q,p)$ and $\{q,p\}=1$. Consider the constraint

$$
\phi=p\approx0.
$$

Show explicitly that $\phi\approx0$ but $\{\phi,q\}$ is not weakly zero.

<details><summary><strong>Solution</strong></summary>

On the constraint surface $p=0$, the function $\phi=p$ vanishes, so $\phi\approx0$.

However,

$$
\{\phi,q\}=\{p,q\}=-1.
$$

This is nonzero everywhere, including on the constraint surface. Therefore weakly zero functions cannot be set to zero before computing Poisson brackets.

</details>

### Exercise 2: A simple second-class pair

Let $\mathcal P=\mathbb R^2$ with $\{q,p\}=1$. Impose the two constraints

$$
\chi_1=q\approx0,
\qquad
\chi_2=p\approx0.
$$

Compute the constraint matrix $C_{ab}=\{\chi_a,\chi_b\}$ and show that the pair is second-class.

<details><summary><strong>Solution</strong></summary>

The matrix is

$$
C_{ab}
=
\begin{pmatrix}
\{q,q\} & \{q,p\}\\
\{p,q\} & \{p,p\}
\end{pmatrix}
=
\begin{pmatrix}
0 & 1\\
-1 & 0
\end{pmatrix}.
$$

Its determinant is

$$
\det C=1,
$$

so $C_{ab}$ is invertible. Therefore $q\approx0$ and $p\approx0$ form a second-class pair.

</details>

### Exercise 3: Degree-of-freedom counting for electromagnetism

In $3+1$ dimensions, the electromagnetic potential has four configuration variables $A_\mu$ per spatial point. Maxwell theory has two first-class constraints per spatial point: $\pi^0\approx0$ and Gauss's law. Use the finite-dimensional counting formula to find the number of physical configuration-space degrees of freedom per spatial point.

<details><summary><strong>Solution</strong></summary>

Here

$$
N=4,
\qquad
F=2,
\qquad
S=0.
$$

Thus

$$
N_{\rm phys}=N-F-\frac{S}{2}=4-2=2.
$$

These are the two transverse photon polarizations. This count is local and perturbative; global modes and boundary sectors require separate treatment.

</details>

### Exercise 4: Dirac bracket kills second-class constraints

Let $\chi_a$ be second-class constraints with invertible matrix $C_{ab}=\{\chi_a,\chi_b\}$. Prove that

$$
\{F,\chi_c\}_D=0
$$

for any phase-space function $F$.

<details><summary><strong>Solution</strong></summary>

By definition,

$$
\{F,\chi_c\}_D
=
\{F,\chi_c\}
-
\{F,\chi_a\}C^{ab}\{\chi_b,\chi_c\}.
$$

Since $\{\chi_b,\chi_c\}=C_{bc}$ and $C^{ab}C_{bc}=\delta^a{}_c$, this becomes

$$
\{F,\chi_c\}_D
=
\{F,\chi_c\}
-
\{F,\chi_a\}\delta^a{}_c
=0.
$$

Thus all second-class constraints have zero Dirac bracket with every function and may be imposed strongly after the bracket has been replaced.

</details>

## References

- P. A. M. Dirac, *Lectures on Quantum Mechanics*, the classic compact source for constrained Hamiltonian dynamics.
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*, the standard systematic treatment of constrained systems, gauge generators, ghosts, and BRST ideas.
- V. I. Arnold, *Mathematical Methods of Classical Mechanics*, for symplectic geometry and Hamiltonian mechanics.
- R. Abraham and J. E. Marsden, *Foundations of Mechanics*, for the geometric mechanics background.
- T. Frankel, *The Geometry of Physics*, for phase space, symplectic forms, Poisson brackets, and geometric mechanics.
- M. Nakahara, *Geometry, Topology and Physics*, for gauge fields, bundles, and geometric structures used in constrained gauge systems.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the functional-integral and Faddeev–Popov discussions.
- M. Srednicki, *Quantum Field Theory*, especially the sections on canonical quantization, gauge fields, fermionic path integrals, functional determinants, and BRST symmetry.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II, for quantum fields, gauge theory, constraints, Faddeev–Popov methods, and BRST symmetry.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for gauge fixing, constraints, Ward identities, path integrals, and Standard Model applications.

## Version history

- 2026-06-24: Initial polished draft for the Mathematical Toolkit volume.
