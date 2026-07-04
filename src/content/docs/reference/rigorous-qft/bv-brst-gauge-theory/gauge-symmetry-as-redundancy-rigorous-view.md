---
title: "Gauge Symmetry as Redundancy: A Rigorous View"
description: "Explains gauge symmetry as a quotient problem for fields, observables, Noether identities, gauge fixing, and boundary caveats."
sidebar:
  label: "Gauge Redundancy"
  order: 1
level: Advanced
status: "Polished draft"
source: "Faddeev–Popov; Henneaux–Teitelboim; Barnich–Brandt–Henneaux; modern BV-BRST treatments"
topics:
  - gauge symmetry
  - gauge redundancy
  - observables
  - quotient spaces
  - Noether identities
canonicalTopics:
  - gauge-redundancy
  - gauge-orbits
  - physical-observables
  - noether-identities
researchStatus:
  established:
    - "For local gauge theories, gauge transformations identify redundant descriptions; physical observables must be insensitive to gauge orbits, up to boundary and global caveats."
  active:
    - "Global quotient geometry, Gribov problems, boundary charges, and nonperturbative measures require additional structure beyond the local infinitesimal quotient picture."
---

## Summary

Gauge symmetry is not an ordinary symmetry of physical alternatives. It is a redundancy in how the same physical configuration is described. If $\Phi$ is a space of fields and $\mathcal G$ is a gauge group acting on it, then the physical configuration space is not literally $\Phi$ but something like

$$
\Phi/\mathcal G,
$$

or, more carefully, a quotient groupoid or quotient stack that remembers stabilizers and singular orbits.

The basic operational rule is:

$$
O(g\cdot\phi)=O(\phi)
\qquad
(g\in\mathcal G),
$$

for every genuine gauge-invariant observable $O$. Local gauge potentials, ghosts, gauge-fixing functions, and Faddeev–Popov determinants are useful coordinates and tools. They are not themselves the final physical content.

This page explains the quotient problem behind gauge theory, the role of observables, the meaning of Noether identities, why gauge fixing is subtle, and why BRST/BV methods are not optional philosophical decoration but a practical way to resolve the quotient algebraically.

## Prerequisites

You should know the status conventions in [Conventions](/rigorous-qft/conventions/) and the basic distinction between a formal perturbative construction and a nonperturbative theory from [Perturbative QFT as Formal Power Series](/rigorous-qft/perturbative-algebraic-qft/perturbative-qft-as-formal-power-series/). Familiarity with [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/) helps explain why observables, rather than fields alone, are central.

## Core idea

The shortest reliable slogan is:

$$
\text{gauge symmetry} = \text{redundancy of description}.
$$

The mathematical problem is that many field configurations represent the same physical point. Choosing a gauge is like choosing coordinates on a quotient. Such coordinates can be excellent locally and disastrous globally. BRST and BV replace the naive quotient by a cohomological object that is easier to quantize and renormalize.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Gauge orbits, quotient, and observables](/figures/rigorous-qft/gauge-redundancy-quotient.svg)

<figcaption>

Gauge theory starts with a field space $\Phi$ and a gauge action of $\mathcal G$. Gauge-invariant observables are constant along orbits. Gauge fixing tries to choose representatives, while BRST/BV replaces the quotient by a cohomological resolution.

</figcaption>
</figure>

## Setup and conventions

Let $M$ be a spacetime manifold and let $\Phi$ denote a space of classical fields on $M$. In a Yang–Mills example, $\Phi$ may be the affine space of connections $A$ on a principal $G$-bundle, possibly together with matter fields. The gauge group $\mathcal G$ is a group of bundle automorphisms covering the identity on $M$, or equivalently maps $M\to G$ after a trivialization.

For a connection $A$, an infinitesimal gauge parameter $\epsilon$ acts as

$$
\delta_\epsilon A_\mu = D_\mu\epsilon,
$$

with sign conventions depending on whether the action is written on the left or right. The point of this page is not the sign; it is the geometry. The vector field $\delta_\epsilon\phi$ on $\Phi$ is tangent to the gauge orbit through $\phi$.

We call transformations **pure gauge** when they are treated as redundancy. Transformations that do not die at a boundary, at infinity, or at a defect may carry charges. Those are not automatically pure gauge; they may become global, asymptotic, or higher-form symmetries.

## Gauge orbits and the quotient problem

A gauge transformation sends a field configuration $\phi$ to another configuration $g\cdot\phi$. The gauge orbit through $\phi$ is

$$
\mathcal O_\phi=
\{g\cdot\phi\mid g\in\mathcal G\}.
$$

The naive physical configuration space is the set of orbits. This sentence is useful, but it hides several difficulties.

First, the action of $\mathcal G$ need not be free. A field may have a stabilizer: a nontrivial gauge transformation that leaves it fixed. For example, special backgrounds can have residual gauge symmetry. Quotients with stabilizers are naturally groupoids or stacks rather than ordinary smooth manifolds.

Second, the orbit space need not be globally smooth. Gauge conditions can fail to intersect every orbit, or can intersect an orbit more than once. This is the geometric origin of Gribov-type problems.

Third, the quotient depends on which transformations are declared redundant. Compactly supported gauge transformations are normally redundancies. Transformations with nontrivial behavior at infinity, boundaries, or defects may act nontrivially on physical sectors.

The rigorous habit is therefore to avoid saying “divide by the gauge group” without stating the domain, boundary conditions, stabilizers, and intended level of analysis.

## Observables are constant along gauge directions

A classical observable is a function or functional $O$ on field space. It is gauge invariant if

$$
O(g\cdot\phi)=O(\phi).
$$

Infinitesimally, if $R_\epsilon$ is the vector field on $\Phi$ generated by the gauge parameter $\epsilon$, then

$$
R_\epsilon O=0.
$$

For electromagnetism, $A_\mu$ is not gauge invariant under

$$
A_\mu\mapsto A_\mu+\partial_\mu\epsilon,
$$

but the field strength

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu
$$

is invariant. Wilson loops are also gauge-invariant in appropriate representations after taking the trace, subject to the usual global and bundle-theoretic qualifications.

This is the first conceptual repair: do not ask first which field is “real.” Ask which quantities descend to the quotient.

## Noether identities, not Noether charges

Gauge redundancy implies relations among the Euler–Lagrange equations. Let $S[\phi]$ be a gauge-invariant action and write

$$
E_i(S)=\frac{\delta S}{\delta\phi^i}
$$

for the Euler–Lagrange expressions. If an infinitesimal gauge transformation has the schematic form

$$
\delta_\epsilon\phi^i=R^i_\alpha(\phi)\epsilon^\alpha,
$$

then gauge invariance gives, after integration by parts and ignoring boundary terms,

$$
R_\alpha^{\dagger i}(\phi)E_i(S)=0.
$$

This is a Noether identity. It says that the equations of motion are not independent. It is different from the Noether theorem for a global symmetry, which produces a conserved current acting on physical states.

For Maxwell theory, the equation of motion is

$$
\partial_\mu F^{\mu\nu}=j^\nu.
$$

The identity $\partial_\nu\partial_\mu F^{\mu\nu}=0$ implies current conservation $\partial_\nu j^\nu=0$ as a consistency condition. The antisymmetry of $F^{\mu\nu}$ is doing the work.

This distinction is essential for BRST and BV. Gauge symmetry produces constraints and identities. The BV antifields and Koszul–Tate differential later encode exactly those identities.

## Gauge fixing is a local coordinate choice

A gauge condition is a proposed slice through the gauge orbits. For example, in Yang–Mills theory one may impose a Lorenz-type condition

$$
\partial^\mu A_\mu=0.
$$

Perturbatively, one often inserts a Faddeev–Popov determinant and integrates over a gauge-fixed representative. Formally, the idea is

$$
\int_\Phi \frac{\mathcal D\phi}{\operatorname{Vol}\mathcal G}\,e^{iS[\phi]}
\quad\rightsquigarrow\quad
\int_{\chi(\phi)=0}\mathcal D\phi\,
\Delta_{\mathrm{FP}}[\phi]e^{iS[\phi]}.
$$

This formula is useful only after its status is understood. The left-hand side is not generally a measure. The right-hand side depends on a gauge condition, a determinant, boundary conditions, and a perturbative or regularized interpretation.

Gauge fixing is a coordinate choice on the quotient. It is not a proof that the quotient is globally well behaved.

:::caution[Gauge fixing is not physics]
Changing gauge should not change gauge-invariant observables. But this statement is itself nontrivial: it is enforced perturbatively by Ward, Slavnov–Taylor, BRST, or BV identities and can fail in the presence of anomalies or boundary effects.
:::

## Boundary and global caveats

The phrase “gauge symmetry is redundancy” is correct only after specifying which transformations are counted as gauge. In a spacetime region with boundary, an infinitesimal transformation may produce a boundary term in the variation of the action or symplectic form. Such a transformation can carry a charge.

The practical rule is:

| Transformation type | Typical status |
|---|---|
| compactly supported gauge transformation | pure redundancy |
| transformation trivial at boundary | usually pure redundancy |
| transformation nontrivial at infinity | possible global or asymptotic symmetry |
| transformation ending on a defect | possible defect action or charge |
| large gauge transformation | may identify sectors or act nontrivially, depending on the theory |

This is why gauge theory, generalized symmetries, edge modes, anomalies, and boundary conditions are entangled. The local BRST complex is a starting point, not the whole global story.

## Why cohomology enters

The quotient $\Phi/\mathcal G$ is often too singular or infinite-dimensional to use directly. BRST replaces the infinitesimal quotient by a differential. The ghost $c$ is the odd replacement for the gauge parameter $\epsilon$, and the BRST differential $s$ moves along gauge directions:

$$
s\phi^i=R^i_\alpha(\phi)c^\alpha+\cdots.
$$

Gauge-invariant functions become degree-zero cohomology classes:

$$
\text{physical observables}
\approx H^0(s).
$$

The dots matter in general gauge theories. If the gauge algebra closes only on shell, or if there are relations among gauge transformations, the simple BRST differential is not enough. BV adds antifields and a master equation to make the resolution systematic.

## This is the most important part of this page

Gauge symmetry is a statement about description, not about extra physical motion. The mathematical object behind a gauge theory is not merely a set of fields plus an invariant action. It is a quotient problem together with a prescription for observables, identities, boundary conditions, and quantization.

The three levels are:

| Level | Object | Main warning |
|---|---|---|
| classical fields | $\Phi$ with a $\mathcal G$-action | Fields contain redundant directions. |
| physical configurations | quotient of $\Phi$ by $\mathcal G$ | The quotient may be singular or global. |
| observables | invariant functions or cohomology classes | Gauge-fixed variables need not be physical. |

BRST and BV exist because the quotient must be handled algebraically in perturbation theory, renormalization, and curved-spacetime constructions.

## Common pitfalls

**Treating gauge transformations as ordinary global symmetries.** A global symmetry maps one physical state to another. A pure gauge transformation changes only the description of the same state.

**Calling every transformation with a gauge parameter redundant.** Boundary behavior matters. A transformation that is not trivial at infinity may carry electric charge, color-superselection information in restricted contexts, or an asymptotic symmetry charge.

**Assuming a gauge potential is never useful because it is not invariant.** Gauge potentials are indispensable local coordinates and enter Wilson lines, covariant derivatives, and perturbation theory. They are not themselves the final gauge-invariant content.

**Believing a gauge condition defines the quotient globally.** Gauge slices can miss or multiply intersect orbits. Perturbation theory often works in a local neighborhood of a background; global quotient geometry is harder.

**Thinking ghosts are optional computational artifacts.** Ghosts encode the gauge directions and the Faddeev–Popov determinant or, in BRST language, the cohomological resolution of the quotient.

## Relations to other pages

- [BRST Complex](/rigorous-qft/bv-brst-gauge-theory/brst-complex/) turns the infinitesimal quotient into a differential graded algebra.
- [Perturbative QFT as Formal Power Series](/rigorous-qft/perturbative-algebraic-qft/perturbative-qft-as-formal-power-series/) explains the formal perturbative status of many gauge-theory constructions.
- [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/) explains the local-covariant renormalization requirements that gauge theories must satisfy perturbatively.
- [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/) is the curved-spacetime bridge toward BRST and BV renormalization.

## Research status

The local infinitesimal picture of gauge redundancy is standard and mathematically well developed. BRST and BV give precise tools for perturbative quantization, local cohomology, anomalies, and deformation theory.

The global and nonperturbative picture is more delicate. Orbit spaces may be singular, gauge fixing may have Gribov obstructions, large gauge transformations can affect sectors, and continuum interacting gauge theories in four dimensions remain a major mathematical challenge. Boundary and asymptotic symmetries also require care: not every “gauge” transformation is physically trivial once boundary data are part of the problem.

## Exercises

### Exercise 1: Maxwell observables

Let $A_\mu\mapsto A_\mu+\partial_\mu\epsilon$. Show that $F_{\mu\nu}$ is gauge invariant, but $A_\mu A^\mu$ is not.

<details>
<summary><strong>Solution</strong></summary>

The field strength changes by

$$
\delta F_{\mu\nu}
=\partial_\mu\partial_\nu\epsilon-\partial_\nu\partial_\mu\epsilon=0,
$$

assuming ordinary smooth functions. By contrast,

$$
\delta(A_\mu A^\mu)
=2A^\mu\partial_\mu\epsilon+\partial_\mu\epsilon\,\partial^\mu\epsilon,
$$

for a finite transformation, so it is not invariant for a general $\epsilon$.

</details>

### Exercise 2: Noether identity in Maxwell theory

Starting from $E^\nu=\partial_\mu F^{\mu\nu}-j^\nu$, show that the identity associated with gauge invariance implies charge conservation.

<details>
<summary><strong>Solution</strong></summary>

Take the divergence:

$$
\partial_\nu E^\nu
=\partial_\nu\partial_\mu F^{\mu\nu}-\partial_\nu j^\nu.
$$

The first term vanishes because $F^{\mu\nu}$ is antisymmetric while $\partial_\nu\partial_\mu$ is symmetric. Thus $\partial_\nu E^\nu=-\partial_\nu j^\nu$. On shell, $E^\nu=0$, so consistency requires $\partial_\nu j^\nu=0$.

</details>

### Exercise 3: A boundary warning

On a region $M$ with boundary, consider an Abelian gauge transformation $A\mapsto A+d\epsilon$. Explain why requiring $\epsilon|_{\partial M}=0$ and allowing arbitrary $\epsilon|_{\partial M}$ can lead to different notions of redundancy.

<details>
<summary><strong>Solution</strong></summary>

If $\epsilon$ vanishes at the boundary, the transformation normally acts only inside the region and is treated as pure redundancy. If $\epsilon$ is nonzero at the boundary, variations of the action or symplectic form can produce boundary terms. Such transformations may act on boundary data and can carry charges. The correct choice depends on what boundary conditions and boundary observables are included in the theory.

</details>

## References

### Standard first pass

- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* **25** (1967), 29–30. [doi:10.1016/0370-2693(67)90067-6](https://doi.org/10.1016/0370-2693(67)90067-6).
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*, Princeton University Press, 1992. [doi:10.1515/9780691213866](https://doi.org/10.1515/9780691213866).
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, fifth edition, Oxford University Press, 2021. [doi:10.1093/oso/9780198834625.001.0001](https://doi.org/10.1093/oso/9780198834625.001.0001).

### Deeper references

- C. Becchi, A. Rouet, and R. Stora, “Renormalization of Gauge Theories,” *Annals of Physics* **98** (1976), 287–321. [doi:10.1016/0003-4916(76)90156-1](https://doi.org/10.1016/0003-4916(76)90156-1).
- I. V. Tyutin, “Gauge Invariance in Field Theory and Statistical Physics in Operator Formalism,” Lebedev preprint (1975). [arXiv:0812.0580](https://arxiv.org/abs/0812.0580).
- G. Barnich, F. Brandt, and M. Henneaux, “Local BRST Cohomology in Gauge Theories,” *Physics Reports* **338** (2000), 439–569. [arXiv:hep-th/0002245](https://arxiv.org/abs/hep-th/0002245), [doi:10.1016/S0370-1573(00)00049-1](https://doi.org/10.1016/S0370-1573(00)00049-1).
- A. S. Cattaneo, P. Mnev, and N. Reshetikhin, “Classical BV Theories on Manifolds with Boundary,” *Communications in Mathematical Physics* **332** (2014), 535–603. [arXiv:1201.0290](https://arxiv.org/abs/1201.0290), [doi:10.1007/s00220-014-2145-3](https://doi.org/10.1007/s00220-014-2145-3).

## Version history

- **2026-07-01:** Initial polished draft.
