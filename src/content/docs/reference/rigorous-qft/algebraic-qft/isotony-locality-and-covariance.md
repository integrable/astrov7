---
title: "Isotony, Locality, and Covariance"
description: "Explain the three structural axioms that make a local net into a relativistic algebraic QFT: inclusion, spacelike commutation, and symmetry covariance."
sidebar:
  label: "Isotony, Locality, Covariance"
  order: 3
level: Graduate
status: "Polished draft"
source: "Haag–Kastler algebraic QFT; Haag, Local Quantum Physics; Fewster–Rejzner AQFT introduction."
topics:
  - algebraic QFT
  - Haag–Kastler axioms
  - local nets
canonicalTopics:
  - isotony
  - locality
  - covariance
researchStatus:
  established:
    - "Isotony, locality, and covariance are core structural axioms of algebraic QFT on a fixed spacetime background."
  active:
    - "Their strongest consequences depend on representation choice, additivity, duality, split inclusions, and phase-space assumptions."
---

## Summary

The three most basic structural axioms of algebraic QFT are **isotony**, **locality**, and **covariance**. For a local net

$$
\mathcal O\longmapsto \mathcal A(\mathcal O),
$$

they say, schematically,

$$
\begin{aligned}
\mathcal O_1\subset \mathcal O_2
&\quad\Longrightarrow\quad
\mathcal A(\mathcal O_1)\subset \mathcal A(\mathcal O_2),\\
\mathcal O_1\perp \mathcal O_2
&\quad\Longrightarrow\quad
[A,B]=0
\quad
(A\in\mathcal A(\mathcal O_1),\,B\in\mathcal A(\mathcal O_2)),\\
\alpha_g(\mathcal A(\mathcal O))
&=\mathcal A(g\mathcal O).
\end{aligned}
$$

Isotony says that enlarging the spacetime region can only enlarge the observable algebra. Locality says that spacelike separated observations are compatible. Covariance says that the localization assignment respects spacetime symmetries.

These axioms are easy to state but highly constraining. They are the algebraic counterpart of three physical principles: experiments in a smaller laboratory are still available in a larger laboratory; operations at spacelike separation do not disturb one another at the level of observable algebras; and the theory does not depend on a preferred inertial coordinate system.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A diagram showing isotony, locality, and covariance as three structural constraints on a local net.](/figures/rigorous-qft/isotony-locality-covariance.svg)

<figcaption>

The three structural constraints on a local net. Isotony controls nested regions, locality controls spacelike separated regions, and covariance controls the action of spacetime symmetries.

</figcaption>
</figure>

## Prerequisites

You should have read [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/) and [Haag–Kastler Axioms](/rigorous-qft/algebraic-qft/haag-kastler-axioms/). It is also useful to know [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/) and [Poincaré Covariance](/rigorous-qft/wightman-axiomatic-qft/poincare-covariance/) in the Wightman setting.

## Core idea

The algebraic formulation replaces pointwise field variables by a localization map. Once localization becomes part of the mathematical data, the first question is not “what is the field equation?” but “how do the algebras assigned to different regions fit together?”

Isotony, locality, and covariance are the minimal compatibility rules for this fit. They do not specify a Hamiltonian, Lagrangian, particle spectrum, or vacuum state. Instead, they define what it means for observable algebras to be organized as a relativistic local theory on spacetime.

This makes them both modest and powerful. They are modest because many different theories can satisfy the same structural axioms. They are powerful because any claim about local physics that violates one of them is not a candidate for an ordinary relativistic QFT in the Haag–Kastler sense.

## Setup and conventions

Work on Minkowski spacetime $M=\mathbb R^{1,d-1}$ with the mostly-minus convention fixed in [Conventions](/rigorous-qft/conventions/). Let $\mathcal K$ be a collection of admissible open regions, often double cones or relatively compact causally complete regions.

A local net assigns to each region $\mathcal O\in\mathcal K$ a unital $C^*$-algebra $\mathcal A(\mathcal O)$, or after choosing a representation, a von Neumann algebra $\mathcal M(\mathcal O)\subset B(\mathcal H)$. This page writes $\mathcal A(\mathcal O)$ for the local algebra unless the distinction matters.

The causal complement of $\mathcal O$ is denoted $\mathcal O'$. Two regions are spacelike separated, written $\mathcal O_1\perp\mathcal O_2$, when every point of one is spacelike separated from every point of the other.

The proper orthochronous Poincaré group is written $\mathcal P_+^\uparrow$. Its elements $g=(a,\Lambda)$ act on spacetime by

$$
gx=\Lambda x+a.
$$

In the algebraic setting this geometric action is accompanied by automorphisms $\alpha_g$ of the quasi-local algebra.

## Isotony

Isotony is the axiom

$$
\mathcal O_1\subset\mathcal O_2
\quad\Longrightarrow\quad
\mathcal A(\mathcal O_1)\subset\mathcal A(\mathcal O_2).
$$

It says that an observable measurable in a smaller spacetime region is also measurable in any larger region containing it. If a detector, preparation procedure, or bounded measurement can be localized in $\mathcal O_1$, then it can also be regarded as localized in $\mathcal O_2$.

This is why algebraic QFT uses a **net**, not merely a list of independent algebras. The inclusion maps carry physical information. They tell us how local algebras are nested and allow one to form the quasi-local algebra generated by all bounded local observables.

A typical construction first defines algebras on small regions and then builds larger algebras by inclusion and completion. Isotony is the condition that makes this local-to-global construction coherent.

### What isotony does not say

Isotony does not say that $\mathcal A(\mathcal O_2)$ is a tensor product of $\mathcal A(\mathcal O_1)$ with “the degrees of freedom in the rest of $\mathcal O_2$.” In continuum QFT, local von Neumann algebras are usually type III factors, and naive Hilbert-space tensor factorization across sharp spatial boundaries is not available.

Isotony also does not say that the inclusion is proper. Some pathological or overly small nets can have equal algebras for many regions. To rule out nets with too little localization information, one adds further assumptions such as additivity, weak additivity, or local definiteness.

## Locality

Locality, also called Einstein causality in this context, is the axiom

$$
\mathcal O_1\perp\mathcal O_2
\quad\Longrightarrow\quad
[A,B]=0
$$

for all $A\in\mathcal A(\mathcal O_1)$ and $B\in\mathcal A(\mathcal O_2)$.

Equivalently, in a Hilbert-space representation,

$$
\mathcal A(\mathcal O_1)
\subset
\mathcal A(\mathcal O_2)'
\qquad
(\mathcal O_1\perp\mathcal O_2),
$$

where the prime on the algebra denotes the commutant. If $\mathcal O_1\subset\mathcal O_2'$, locality gives

$$
\mathcal A(\mathcal O_1)
\subset
\mathcal A(\mathcal O_2')
\subset
\mathcal A(\mathcal O_2)'.
$$

This is the algebraic version of microcausality. In a field-generated example, one expects smeared bosonic observables supported in spacelike separated regions to commute. But the algebraic axiom does not require pointlike fields to exist as primary objects.

### Observables versus charged fields

For observable algebras, locality is ordinary commutativity at spacelike separation. If one works with charged fields or fermionic field algebras, the corresponding condition can be graded locality: odd fermionic fields anticommute at spacelike separation while even observables commute. The Haag–Kastler net of observables is usually built so that the local observable algebras satisfy ordinary locality.

This distinction is not cosmetic. In gauge theory, charged fields may not be genuine local observables, while gauge-invariant local observables can still form a local net. Algebraic QFT is deliberately formulated so that the primary object is the observable content.

## Covariance

Covariance says that spacetime symmetries act compatibly on regions and algebras. Abstractly, there is a group homomorphism

$$
g\longmapsto\alpha_g
$$

from $\mathcal P_+^\uparrow$ into automorphisms of the quasi-local algebra such that

$$
\alpha_g(\mathcal A(\mathcal O))=\mathcal A(g\mathcal O).
$$

Thus a transformed observable is localized in the transformed region. If $A$ is localized in $\mathcal O$, then $\alpha_g(A)$ is localized in $g\mathcal O$.

After choosing a covariant Hilbert-space representation $\pi$ on $\mathcal H$, covariance is often implemented by unitaries $U(g)$ satisfying

$$
U(g)\,\pi(A)\,U(g)^{-1}=\pi(\alpha_g(A)).
$$

This unitary implementation is representation-dependent. The abstract net may have automorphic covariance even before a particular Hilbert space is chosen. In a vacuum representation one usually adds strong continuity of $U$ and the spectrum condition for translations.

### Why covariance is more than notation

Covariance ties algebraic localization to the geometry of spacetime. It implies, for example, that if two regions are related by a Poincaré transformation, their algebras are isomorphic in the physically prescribed way. It also ensures that isotony and locality are not artifacts of one coordinate system.

Because Poincaré transformations preserve inclusions and spacelike separation, the three axioms are compatible:

$$
\mathcal O_1\subset\mathcal O_2
\Longrightarrow
 g\mathcal O_1\subset g\mathcal O_2,
$$

and

$$
\mathcal O_1\perp\mathcal O_2
\Longrightarrow
 g\mathcal O_1\perp g\mathcal O_2.
$$

The corresponding algebraic statements follow from the covariance of the net.

## The three axioms as a package

The package can be summarized as follows.

| Axiom | Geometric input | Algebraic output | Physical reading |
|---|---|---|---|
| Isotony | $\mathcal O_1\subset\mathcal O_2$ | $\mathcal A(\mathcal O_1)\subset\mathcal A(\mathcal O_2)$ | A larger laboratory contains the smaller one. |
| Locality | $\mathcal O_1\perp\mathcal O_2$ | $[\mathcal A(\mathcal O_1),\mathcal A(\mathcal O_2)]=0$ | Spacelike separated observations are compatible. |
| Covariance | $\mathcal O\mapsto g\mathcal O$ | $\mathcal A(\mathcal O)\mapsto\mathcal A(g\mathcal O)$ | Symmetries move regions and observables together. |

Here $[\mathcal A(\mathcal O_1),\mathcal A(\mathcal O_2)]=0$ is shorthand for $[A,B]=0$ for all local observables $A$ and $B$ in the indicated algebras.

The package is structural rather than dynamical. The dynamics enters through translations, the spectrum condition, the time-slice axiom, Hamiltonians in representations, or relative Cauchy evolution in the locally covariant framework.

## Checks

Given a proposed algebraic model, the first checks are mechanical.

Check isotony by verifying that the construction of $\mathcal A(\mathcal O)$ is monotone in $\mathcal O$. For a field-generated net, this usually follows because test functions supported in $\mathcal O_1$ are also supported in $\mathcal O_2$ when $\mathcal O_1\subset\mathcal O_2$.

Check locality by proving commutation for spacelike separated generators and then extending to the generated algebras. For free scalar fields this reduces to the vanishing of the Pauli–Jordan commutator at spacelike separation.

Check covariance by verifying that the automorphism sends each generator localized in $\mathcal O$ to the corresponding transformed generator localized in $g\mathcal O$. In a Hilbert-space representation, check that the implementing unitaries form a strongly continuous representation if later spectral statements are needed.

Finally, check that the chosen region class is stable under the spacetime symmetries being used. Otherwise the covariance axiom is not even well-typed.

## Common pitfalls

**Confusing isotony with additivity.** Isotony says smaller-region algebras include into larger-region algebras. Additivity says larger algebras are generated by algebras of smaller regions covering them. Additivity is stronger.

**Confusing locality with Haag duality.** Locality gives $\mathcal A(\mathcal O)\subset\mathcal A(\mathcal O')'$. Haag duality asks for equality, under suitable hypotheses. Equality is an additional completeness property, not the locality axiom itself.

**Treating covariance as automatic.** A formula may be Lorentz covariant while a cutoff, domain choice, boundary condition, or representation breaks covariance. The algebraic axiom requires an actual action on the net.

**Forgetting that observables commute, not necessarily all fields.** Fermionic and charged field algebras require care. The observable net is built to satisfy ordinary locality; field algebras may satisfy graded variants.

**Assuming locality implies tensor factorization.** Spacelike commuting algebras are not the same thing as tensor factors of the Hilbert space. The split property is the refined statement that gives approximate tensor-product behavior under additional hypotheses.

## Relations to other pages

- [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/) defines the net language used here.
- [Haag–Kastler Axioms](/rigorous-qft/algebraic-qft/haag-kastler-axioms/) places these three axioms alongside vacuum, spectrum, additivity, and other standard assumptions.
- [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/) gives the field-based version of the same causal idea.
- [Poincaré Covariance](/rigorous-qft/wightman-axiomatic-qft/poincare-covariance/) explains unitary spacetime symmetry in the Wightman framework.

## Research status

The three axioms on this page are established structural assumptions of algebraic QFT. They are not controversial as a fixed-background formalization of relativistic locality for observables.

The research frontier lies in what can be proved from them after adding further physically motivated hypotheses. Haag duality, the split property, modular nuclearity, sector classification, thermodynamic behavior, and locally covariant generalizations are not automatic consequences of this minimal package. They require additional assumptions or constructions.

## Exercises

### Exercise 1: Locality implies an inclusion into the commutant

Assume locality. Show that if $\mathcal O_1\subset\mathcal O_2'$, then

$$
\mathcal A(\mathcal O_1)\subset\mathcal A(\mathcal O_2)'.
$$

<details>
<summary><strong>Solution</strong></summary>

If $\mathcal O_1\subset\mathcal O_2'$, then every point of $\mathcal O_1$ is spacelike separated from every point of $\mathcal O_2$. Hence locality gives $[A,B]=0$ for all $A\in\mathcal A(\mathcal O_1)$ and $B\in\mathcal A(\mathcal O_2)$. This is exactly the statement that every $A\in\mathcal A(\mathcal O_1)$ belongs to the commutant of $\mathcal A(\mathcal O_2)$.

</details>

### Exercise 2: Covariance preserves isotony

Suppose the net is covariant and isotone. Show that if $\mathcal O_1\subset\mathcal O_2$, then

$$
\mathcal A(g\mathcal O_1)\subset\mathcal A(g\mathcal O_2).
$$

<details>
<summary><strong>Solution</strong></summary>

By isotony, $\mathcal A(\mathcal O_1)\subset\mathcal A(\mathcal O_2)$. Apply the automorphism $\alpha_g$ to both sides. Since automorphisms preserve inclusions,

$$
\alpha_g(\mathcal A(\mathcal O_1))
\subset
\alpha_g(\mathcal A(\mathcal O_2)).
$$

Using covariance, this becomes $\mathcal A(g\mathcal O_1)\subset\mathcal A(g\mathcal O_2)$.

</details>

### Exercise 3: Why locality is not duality

Locality gives $\mathcal A(\mathcal O)\subset\mathcal A(\mathcal O')'$. Explain in words why the reverse inclusion is a stronger condition.

<details>
<summary><strong>Solution</strong></summary>

The reverse inclusion says that every bounded operator commuting with all observables in the causal complement is already generated by observables localized in $\mathcal O$. That is not just causal compatibility; it is a completeness claim about the observable content of $\mathcal O$. Locality tells us that observables in $\mathcal O$ cannot disturb spacelike separated observables. Haag duality says there are no additional operators compatible with the complement except those belonging to $\mathcal O$ itself.

</details>

## References

### Standard first pass

- Rudolf Haag and Daniel Kastler, "An Algebraic Approach to Quantum Field Theory," *Journal of Mathematical Physics* **5** (1964), 848–861. [doi:10.1063/1.1704187](https://doi.org/10.1063/1.1704187).
- Rudolf Haag, *Local Quantum Physics: Fields, Particles, Algebras*, 2nd ed., Springer, 1996. [doi:10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- Huzihiro Araki, *Mathematical Theory of Quantum Fields*, Oxford University Press, 1999. Oxford Academic: [Mathematical Theory of Quantum Fields](https://academic.oup.com/book/54810).

### Deeper references

- Christopher J. Fewster and Kasia Rejzner, "Algebraic Quantum Field Theory – an introduction," arXiv: [1904.04051](https://arxiv.org/abs/1904.04051).
- Detlev Buchholz and Klaus Fredenhagen, "Algebraic Quantum Field Theory: Objectives, Methods, and Results," arXiv: [2305.12923](https://arxiv.org/abs/2305.12923).
- Romeo Brunetti, Klaus Fredenhagen, and Rainer Verch, "The generally covariant locality principle – A new paradigm for local quantum physics," *Communications in Mathematical Physics* **237** (2003), 31–68. [doi:10.1007/s00220-003-0815-7](https://doi.org/10.1007/s00220-003-0815-7), arXiv: [math-ph/0112041](https://arxiv.org/abs/math-ph/0112041).

## Version history

- **2026-06-28:** Initial page on the three core structural axioms of local nets.
