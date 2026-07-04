---
title: "Haag–Kastler Axioms"
description: "State the standard Haag–Kastler axioms for algebraic QFT and explain what each assumption contributes."
sidebar:
  label: "Haag–Kastler Axioms"
  order: 2
level: Graduate
status: "Polished draft"
source: "Haag–Kastler 1964; Haag, Local Quantum Physics; Araki, Mathematical Theory of Quantum Fields."
topics:
  - Haag–Kastler axioms
  - algebraic QFT
  - locality
canonicalTopics:
  - haag-kastler-axioms
  - local-quantum-physics
  - algebraic-quantum-field-theory
researchStatus:
  established:
    - "The Haag–Kastler framework is a standard axiomatic formulation of local relativistic quantum theory in terms of observable algebras."
  active:
    - "Different authors use slightly different axiom lists and strengthenings, especially for additivity, duality, phase-space conditions, and curved-spacetime generalizations."
---

## Summary

The **Haag–Kastler axioms** describe a relativistic QFT by a local net of observable algebras satisfying structural conditions such as isotony, locality, covariance, and positive-energy vacuum representation. In a fixed Minkowski spacetime setting, the core data are

$$
\mathcal O\longmapsto\mathcal A(\mathcal O),
\qquad
\alpha_g\big(\mathcal A(\mathcal O)\big)=\mathcal A(g\mathcal O),
$$

where $\mathcal O$ ranges over suitable bounded open regions and $g$ is a Poincaré transformation.

The framework is sometimes called **local quantum physics**. Its main philosophical move is to formulate locality and covariance directly in terms of observable algebras, not in terms of a chosen set of pointlike fields. The result is a precise way to discuss states, representations, superselection sectors, thermal equilibrium, modular theory, and curved-spacetime generalizations.

There is no universally identical finite list called "the" Haag–Kastler axioms. The minimal core is stable, but authors differ on whether additivity, irreducibility, Haag duality, the time-slice axiom, or phase-space/nuclearity conditions are axioms, derived properties, or additional hypotheses for special theorems.

<figure class="doc-figure" style="--figure-width: 44rem;">

![A map of the Haag–Kastler axioms around a local net.](/figures/rigorous-qft/haag-kastler-axioms-map.svg)

<figcaption>

The Haag–Kastler framework starts with a local net and adds compatibility with inclusion, causality, spacetime symmetry, and physical representations.

</figcaption>
</figure>

## Prerequisites

You should know [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/), especially isotony and spacelike commutativity. It is also useful to compare the field-based assumptions in [Poincaré Covariance](/rigorous-qft/wightman-axiomatic-qft/poincare-covariance/), [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/), and [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/).

## Core idea

The Haag–Kastler axioms say that relativistic quantum theory is local before it is expressed in fields. Each spacetime region $\mathcal O$ has an algebra $\mathcal A(\mathcal O)$ of observables. The physical content of the theory lies in how these algebras fit together as regions are enlarged, moved by symmetries, or placed at spacelike separation.

The axioms are deliberately structural. They do not tell you which Lagrangian to quantize. They tell you what any successful local relativistic quantum theory should provide after quantization: a coherent system of local observables, compatible with causality, spacetime symmetry, and positive energy.

This makes the framework both powerful and unforgiving. It is powerful because many consequences can be stated without choosing coordinates on field space. It is unforgiving because writing down a classical action does not automatically produce a net satisfying these axioms.

## Setup and conventions

Let $M=\mathbb R^{1,d-1}$ be Minkowski spacetime. Let $\mathcal K$ be a directed collection of admissible open regions, often bounded double cones. Directed means that for $\mathcal O_1,\mathcal O_2\in\mathcal K$ there is a region $\mathcal O_3\in\mathcal K$ containing both.

A Haag–Kastler theory is usually presented as a net

$$
\mathcal K\ni\mathcal O\longmapsto\mathcal A(\mathcal O)
$$

of unital $C^*$-algebras, or as a net of von Neumann algebras acting on a Hilbert space $\mathcal H$. The $C^*$-algebraic version is more representation-independent. The von Neumann version is natural once a vacuum or thermal representation has been chosen.

For a region $\mathcal O$, its causal complement is $\mathcal O'$. The commutant of a von Neumann algebra $\mathcal M\subset B(\mathcal H)$ is denoted $\mathcal M'$:

$$
\mathcal M'=\{B\in B(\mathcal H): BA=AB\text{ for all }A\in\mathcal M\}.
$$

Do not confuse the spacetime causal complement $\mathcal O'$ with the algebraic commutant $\mathcal M'$; the same prime notation is conventional but context-sensitive.

## The core axioms

A common fixed-background version of the Haag–Kastler axioms is the following.

| Axiom | Statement | Meaning |
|---|---|---|
| Isotony | If $\mathcal O_1\subset\mathcal O_2$, then $\mathcal A(\mathcal O_1)\subset\mathcal A(\mathcal O_2)$. | Larger regions contain the measurements of smaller regions. |
| Locality | If $\mathcal O_1\subset\mathcal O_2'$, then $[A,B]=0$ for $A\in\mathcal A(\mathcal O_1)$ and $B\in\mathcal A(\mathcal O_2)$. | Spacelike separated observations are compatible. |
| Covariance | There is an action $\alpha_g$ of the Poincaré group with $\alpha_g(\mathcal A(\mathcal O))=\mathcal A(g\mathcal O)$. | Localization respects spacetime symmetry. |
| Vacuum representation | There is a representation with a Poincaré-invariant vacuum vector $\Omega$. | The theory has a distinguished empty state in Minkowski space. |
| Spectrum condition | The joint spectrum of energy–momentum lies in the closed forward light cone. | Energy is positive and momentum is relativistically causal. |
| Additivity, often included | $\mathcal A(\mathcal O)$ is generated by algebras of smaller regions covering $\mathcal O$. | Local data generate larger local data. |

The first three axioms are net-structural. The vacuum and spectrum assumptions refer to a physical representation. Additivity controls whether the net has enough small-region observables to reconstruct larger regions.

## Vacuum representation

In a vacuum representation, the quasi-local algebra $\mathcal A$ acts on a Hilbert space $\mathcal H$ through a representation $\pi$. There is a strongly continuous unitary representation $U$ of the proper orthochronous Poincaré group such that

$$
U(g)\,\pi(A)\,U(g)^{-1}=\pi(\alpha_g(A)).
$$

A vacuum vector $\Omega\in\mathcal H$ satisfies

$$
U(g)\Omega=\Omega,
$$

and the joint spectrum of the translation generators $P^\mu$ obeys

$$
\operatorname{sp}(P)\subset \overline V_+.
$$

Often one also assumes that $\Omega$ is cyclic for the quasi-local algebra, meaning that $\pi(\mathcal A)\Omega$ is dense in $\mathcal H$. Under additional locality and spectrum assumptions, cyclicity for local algebras is related to Reeh–Schlieder-type phenomena. The algebraic formulation thus recovers a central Wightman lesson: the vacuum is highly entangled across spacetime regions.

## Optional strengthenings

Several important conditions are often taught near the Haag–Kastler axioms but should be kept conceptually separate.

**Haag duality** says, roughly, that the algebra of a region is the full commutant of the algebra of its causal complement:

$$
\mathcal A(\mathcal O)=\mathcal A(\mathcal O')'.
$$

This is stronger than locality, which only gives $\mathcal A(\mathcal O)\subset\mathcal A(\mathcal O')'$.

**The split property** says that for suitable nested regions with $\overline{\mathcal O_1}\subset\mathcal O_2$, there is a type I factor $\mathcal N$ with

$$
\mathcal A(\mathcal O_1)\subset\mathcal N\subset\mathcal A(\mathcal O_2).
$$

It is a precise substitute for approximate tensor factorization with a collar between the regions.

**The time-slice axiom** says that an algebra associated with a neighborhood of a Cauchy surface generates the algebra of the causal development. This axiom becomes especially important in locally covariant QFT.

**Phase-space or nuclearity conditions** control how many local degrees of freedom exist below a given energy. They are often needed to prove thermodynamic or structural results.

## Relation to Wightman axioms

The Wightman framework starts from operator-valued distributions on a Hilbert space. The Haag–Kastler framework starts from local observable algebras. The two are not enemies. In favorable situations, Wightman fields generate a Haag–Kastler net by assigning to $\mathcal O$ the algebra generated by smeared fields supported in $\mathcal O$.

The algebraic framework is more flexible in several ways. It can compare inequivalent Hilbert-space representations of the same observable algebra. It can describe thermal states without pretending they are vectors in the vacuum Hilbert space. It can focus on gauge-invariant observables rather than gauge-dependent field variables. It also gives the natural language for superselection sectors: different charged sectors can be represented as inequivalent representations of the same observable net.

The cost is that the framework is abstract. To use it for physics, one must still construct examples, identify physically meaningful states, and connect observables to measurements or calculations.

## Checks

A proposed Haag–Kastler model should be tested in layers.

First, check the net axioms: isotony, locality, and covariance. These are usually visible from the construction.

Second, check representation-theoretic physics: strong continuity of translations, existence of energy–momentum generators, spectrum condition, and vacuum invariance.

Third, check generation properties such as additivity or weak additivity. A net that has too few local observables may satisfy locality but fail to capture the intended field theory.

Fourth, mark optional structural features honestly. Haag duality, the split property, modular nuclearity, type III local factors, and asymptotic completeness are major properties, not harmless decorations.

## Common pitfalls

**Using locality when only isotony was stated.** Isotony concerns nested regions. Locality concerns spacelike separated regions. They are independent structural ideas.

**Mistaking locality for Haag duality.** Locality gives an inclusion into the commutant of the causal complement. Haag duality says this inclusion is equality. Equality can fail and is often physically informative.

**Assuming every axiom list is identical.** Some presentations include additivity or irreducibility in the basic axioms; others treat them as extra assumptions. Always check which version a theorem uses.

**Forgetting states.** A net of algebras is not yet a prediction machine. States turn algebra elements into expectation values, and different physically relevant states can define inequivalent Hilbert-space representations.

## Relations to other pages

- [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/) defines the underlying net language used here.
- [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/) gives the field-based framework that motivates many algebraic examples.
- [Poincaré Covariance](/rigorous-qft/wightman-axiomatic-qft/poincare-covariance/) and [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/) explain the same physical requirements in the Wightman setting.
- [Reflection Positivity](/rigorous-qft/osterwalder-schrader-euclidean-qft/reflection-positivity/) is the Euclidean positivity condition that can lead, after reconstruction, to a Lorentzian Hilbert-space theory.

## Research status

The Haag–Kastler framework is established mathematical physics. It is one of the cleanest languages for local relativistic quantum theory, especially when fields are not the right primitive objects.

The active frontier is not whether the framework is meaningful, but how far it can be pushed: constructing physically central interacting four-dimensional examples, incorporating gauge theories and constraints, understanding local covariance in curved spacetime, classifying sectors and defects, and relating operator-algebraic structures to modern categorical and factorization-algebraic frameworks.

## Exercises

### Exercise 1: Locality as an inclusion

Let $\mathcal A(\mathcal O')'$ denote the commutant of the algebra assigned to the causal complement of $\mathcal O$. Show that locality implies

$$
\mathcal A(\mathcal O)\subset \mathcal A(\mathcal O')'.
$$

<details>
<summary><strong>Solution</strong></summary>

If $A\in\mathcal A(\mathcal O)$ and $B\in\mathcal A(\mathcal O')$, then the regions $\mathcal O$ and $\mathcal O'$ are spacelike separated by definition of causal complement. Locality gives $AB=BA$ for every such $B$. Therefore $A$ lies in the commutant of $\mathcal A(\mathcal O')$, so $A\in\mathcal A(\mathcal O')'$.

</details>

### Exercise 2: Covariance preserves isotony

Suppose $\mathcal O_1\subset\mathcal O_2$ and $\alpha_g(\mathcal A(\mathcal O))=\mathcal A(g\mathcal O)$. Show that isotony for $\mathcal O_1\subset\mathcal O_2$ implies isotony for $g\mathcal O_1\subset g\mathcal O_2$.

<details>
<summary><strong>Solution</strong></summary>

From isotony, $\mathcal A(\mathcal O_1)\subset\mathcal A(\mathcal O_2)$. Applying the automorphism $\alpha_g$ gives

$$
\alpha_g(\mathcal A(\mathcal O_1))
\subset
\alpha_g(\mathcal A(\mathcal O_2)).
$$

Using covariance, this becomes $\mathcal A(g\mathcal O_1)\subset\mathcal A(g\mathcal O_2)$.

</details>

### Exercise 3: Locality versus Haag duality

Explain why locality does not by itself prove Haag duality.

<details>
<summary><strong>Solution</strong></summary>

Locality proves only that every observable localized in $\mathcal O$ commutes with every observable localized in $\mathcal O'$, hence $\mathcal A(\mathcal O)\subset\mathcal A(\mathcal O')'$. Haag duality asserts that every operator commuting with $\mathcal A(\mathcal O')$ is already generated by observables in $\mathcal O$. That reverse inclusion is a stronger completeness statement about the net and can fail.

</details>

## References

### Standard first pass

- Rudolf Haag and Daniel Kastler, "An Algebraic Approach to Quantum Field Theory," *Journal of Mathematical Physics* **5** (1964), 848–861. [doi:10.1063/1.1704187](https://doi.org/10.1063/1.1704187).
- Rudolf Haag, *Local Quantum Physics: Fields, Particles, Algebras*, 2nd ed., Springer, 1996. [doi:10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- Huzihiro Araki, *Mathematical Theory of Quantum Fields*, Oxford University Press, 1999. Oxford Academic: [Mathematical Theory of Quantum Fields](https://academic.oup.com/book/54810).

### Deeper references

- Christopher J. Fewster and Kasia Rejzner, "Algebraic Quantum Field Theory – an introduction," arXiv: [1904.04051](https://arxiv.org/abs/1904.04051).
- Sergio Doplicher, Rudolf Haag, and John E. Roberts, "Local Observables and Particle Statistics I," *Communications in Mathematical Physics* **23** (1971), 199–230. [doi:10.1007/BF01877742](https://doi.org/10.1007/BF01877742).
- Sergio Doplicher, Rudolf Haag, and John E. Roberts, "Local Observables and Particle Statistics II," *Communications in Mathematical Physics* **35** (1974), 49–85. [doi:10.1007/BF01646454](https://doi.org/10.1007/BF01646454).
- Christopher J. Fewster and Rainer Verch, "Algebraic Quantum Field Theory in Curved Spacetimes," in *Advances in Algebraic Quantum Field Theory*, 2015. [doi:10.1007/978-3-319-21353-8_4](https://doi.org/10.1007/978-3-319-21353-8_4), [arXiv:1504.00586](https://arxiv.org/abs/1504.00586).

- Detlev Buchholz and Klaus Fredenhagen, "Algebraic Quantum Field Theory: Objectives, Methods, and Results," arXiv: [2305.12923](https://arxiv.org/abs/2305.12923).

## Version history

- **2026-06-28:** Initial page on the Haag–Kastler axioms.
