---
title: "Time-Slice Axiom"
description: "State and interpret the locally covariant time-slice axiom, which sends Cauchy morphisms to algebra isomorphisms."
sidebar:
  label: "Time-Slice Axiom"
  order: 3
level: Advanced
status: "Polished draft"
source: "Haag–Kastler primitive causality; Brunetti–Fredenhagen–Verch local covariance; Fewster–Verch curved-spacetime AQFT."
topics:
  - time-slice axiom
  - Cauchy morphisms
  - locally covariant QFT
  - hyperbolic dynamics
canonicalTopics:
  - time-slice-axiom
  - cauchy-morphism
  - locally-covariant-quantum-field-theory
researchStatus:
  established:
    - "In locally covariant QFT, the time-slice axiom is the standard algebraic expression of hyperbolic dynamics: Cauchy morphisms are mapped to isomorphisms."
  active:
    - "Gauge constraints, topological sectors, boundaries, and perturbative BV formulations require careful versions of the time-slice idea."
---

## Summary

The **time-slice axiom** says that a locally covariant QFT does not lose information when one restricts to a spacetime region containing a Cauchy surface. If

$$
\psi:M\to N
$$

is a Cauchy morphism, meaning that $\psi(M)$ contains a Cauchy surface of $N$, then a theory

$$
\mathcal A:\mathsf{Loc}\to\mathsf{Alg}
$$

satisfies the time-slice axiom if

$$
\mathcal A(\psi):\mathcal A(M)
\xrightarrow{\ \simeq\ }
\mathcal A(N)
$$

is an algebra isomorphism.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A diagram of a Cauchy neighborhood embedded into a globally hyperbolic spacetime and sent by a locally covariant QFT functor to an algebra isomorphism.](/figures/rigorous-qft/time-slice-cauchy-morphism.svg)

<figcaption>

The time-slice axiom sends a Cauchy morphism to an isomorphism. A neighborhood containing a Cauchy surface carries enough algebraic information to generate the observables of its causal development.

</figcaption>
</figure>

This is the locally covariant version of **primitive causality** in algebraic QFT. It is not a statement about doing finitely many measurements. It is an algebraic expression of the fact that hyperbolic field equations propagate data from Cauchy surfaces.

## Prerequisites

You should know [QFT as a Functor on Spacetimes](/rigorous-qft/locally-covariant-qft/qft-as-functor-on-spacetimes/) and [Globally Hyperbolic Spacetimes](/rigorous-qft/locally-covariant-qft/globally-hyperbolic-spacetimes/). The fixed-spacetime version is explained in [Additivity and the Time-Slice Axiom](/rigorous-qft/algebraic-qft/additivity-and-time-slice-axiom/).

The main geometric words are Cauchy surface, domain of dependence, causally convex embedding, and globally hyperbolic spacetime.

## Core idea

A hyperbolic field theory has equations of motion. Those equations should imply that observables in a small time-slab around a Cauchy surface generate all observables in the spacetime determined by that Cauchy surface.

In a fixed spacetime, the slogan is

$$
\mathcal A(\text{Cauchy neighborhood})
=\mathcal A(\text{causal development}).
$$

In locally covariant QFT, the same idea becomes functorial:

$$
\psi\text{ contains a Cauchy surface}
\quad\Longrightarrow\quad
\mathcal A(\psi)\text{ is an isomorphism}.
$$

The word **isomorphism** matters. It says not only that observables in the smaller spacetime can be embedded into the larger one, but also that every observable of the larger spacetime can be represented algebraically using observables localized in the Cauchy region.

## Setup and conventions

Let $\mathsf{Loc}$ be the category whose objects are globally hyperbolic spacetimes with orientation and time orientation, and whose morphisms are admissible causally convex isometric embeddings.

A morphism

$$
\psi:M\to N
$$

is called a **Cauchy morphism** if its image contains a Cauchy surface of $N$:

$$
\exists\,\Sigma\subset \psi(M)
\quad\text{such that}\quad
\Sigma\text{ is a Cauchy surface of }N.
$$

A locally covariant QFT is a functor

$$
\mathcal A:\mathsf{Loc}\to\mathsf{Alg}.
$$

The time-slice axiom is the condition

$$
\psi\text{ Cauchy}
\quad\Rightarrow\quad
\mathcal A(\psi)\text{ is an isomorphism in }\mathsf{Alg}.
$$

If $\mathsf{Alg}$ is a category of unital $*$-algebras, this means that $\mathcal A(\psi)$ has an inverse unital $*$-homomorphism.

## Fixed-spacetime form

Fix a globally hyperbolic spacetime $M$ and let $O\subset M$ be an admissible globally hyperbolic open region. Suppose $O$ contains a Cauchy surface for $M$. The inclusion

$$
\iota_O:O\hookrightarrow M
$$

is then a Cauchy morphism. The time-slice axiom gives

$$
\mathcal A(\iota_O):\mathcal A(O)
\to \mathcal A(M)
$$

as an isomorphism.

In the language of local nets, one often phrases this by saying that the algebra associated with any neighborhood of a Cauchy surface is the algebra of the full spacetime, after identifying it with its image:

$$
\mathcal A_M(O)=\mathcal A(M).
$$

More generally, if $O$ contains a Cauchy surface for a globally hyperbolic region $D$, then the algebra of $O$ generates the algebra of $D$.

This is the sharpened form of the idea that QFT is local and dynamical. Isotony says smaller regions give subalgebras. Additivity says local pieces generate larger regions. The time-slice axiom says that a thin enough but Cauchy-complete time slab already generates the whole causal development.

## What the axiom does

The time-slice axiom does four important jobs.

First, it encodes equations of motion algebraically. A theory that assigns independent new observables at every time, unconstrained by dynamics, would generally fail the axiom.

Second, it lets one compare algebras on different spacetimes by moving through Cauchy morphisms. This is essential for relative Cauchy evolution, where one compares the theory before and after a compactly supported metric perturbation.

Third, it makes local covariance more than coordinate-free bookkeeping. The functor does not merely assign algebras to backgrounds; it knows which embeddings contain enough Cauchy data to determine the whole algebra.

Fourth, it lets curved-spacetime QFT avoid choosing a preferred global time evolution. Different Cauchy neighborhoods can be used, and the functorial isomorphisms express the independence of arbitrary slicing choices.

## What the axiom does not say

The time-slice axiom is easy to overread.

It does not say that a finite set of measurements determines the future. Local algebras are infinite-dimensional mathematical objects, not finite measurement records.

It does not pick a preferred Hamiltonian. On a general curved spacetime there may be no time-translation symmetry, hence no canonical Hamiltonian generating a one-parameter group of time translations.

It does not choose a preferred state. Even if the observable algebra is determined by a Cauchy slab, a state on the algebra is additional data. Curved-spacetime QFT generally has no natural vacuum state on every background.

It does not mean the theory is insensitive to geometry. Relative Cauchy evolution uses the time-slice axiom precisely to measure how the theory responds to changes in the metric.

## Free scalar example

For the free Klein–Gordon field on a globally hyperbolic spacetime $M$, write

$$
P_M=\Box_g+m^2+\xi R.
$$

One algebraic construction starts with smeared field generators $\Phi_M(f)$ for test functions $f\in C_0^\infty(M)$ and imposes the equation-of-motion relation

$$
\Phi_M(P_M f)=0.
$$

Equivalently, test functions are considered modulo the image of $P_M$:

$$
C_0^\infty(M)/P_M C_0^\infty(M).
$$

The commutator is controlled by the causal propagator $E_M=G^-_M-G^+_M$:

$$
[\Phi_M(f),\Phi_M(h)]
=iE_M(f,h)\mathbf 1.
$$

Now let $O\subset M$ be a Cauchy neighborhood. The key classical fact is that every compactly supported source $f$ is equivalent, modulo the equation of motion, to a compactly supported source $f_O$ supported in $O$:

$$
[f]=[f_O]
\quad\text{in}\quad
C_0^\infty(M)/P_M C_0^\infty(M).
$$

The proof uses advanced and retarded Green operators plus a smooth cutoff between two Cauchy surfaces surrounding $O$. The support estimates ensure that the new representative $f_O$ really lies in the Cauchy neighborhood.

Therefore every field generator $\Phi_M(f)$ can be represented by a generator smeared inside $O$. This is the time-slice property for the free scalar field.

## Relation to relative Cauchy evolution

Relative Cauchy evolution is one of the main reasons the time-slice axiom is so useful.

Suppose two metrics agree outside a compact time strip. Choose an early Cauchy region before the perturbation and a late Cauchy region after the perturbation. Because the embeddings of these Cauchy regions are mapped to algebra isomorphisms, one can compare the algebras of the two metric backgrounds by composing inverse and direct time-slice maps.

Schematically, one obtains an automorphism

$$
\operatorname{rce}_M[h]:\mathcal A(M)\to\mathcal A(M),
$$

where $h$ is the compactly supported metric perturbation. In suitable theories, the first variation of this automorphism with respect to $h$ is generated by the stress tensor.

This is a remarkable payoff: an apparently abstract categorical axiom makes it possible to define the response of a quantum field theory to local changes of geometry.

## Gauge theories and constraints

The time-slice axiom is cleanest for unconstrained hyperbolic systems such as the scalar field. Gauge theories require more care.

Classically, gauge fields have constraints and redundancies. Quantization may use BRST or BV complexes, quotient algebras, gauge-invariant observables, or enriched algebraic targets. In these settings, the time-slice statement often survives, but its precise formulation may involve cohomology rather than ordinary algebras.

There is also a global issue. Gauge theories can have topological charges, edge-sensitive data, or Gauss-law constraints that are not localized in a naive time slab unless the observable category and region choices are chosen carefully.

Thus the correct lesson is not that gauge theories violate causality. The lesson is that the phrase "the algebra generated by a Cauchy neighborhood" must be interpreted in a formulation that has already handled gauge redundancy and constraints correctly.

## Common pitfalls

**Confusing the time-slice axiom with determinism of states.** The axiom is about observable algebras. It does not say that one state is dynamically selected from another without specifying state data.

**Thinking it follows from isotony.** Isotony gives an embedding

$$
\mathcal A(O)\subset\mathcal A(M).
$$

The time-slice axiom says that this embedding is onto when $O$ contains a Cauchy surface. That is much stronger.

**Using arbitrary time slabs.** A slab must contain a Cauchy surface for the relevant spacetime or region. A short coordinate-time interval is not enough if it misses causal curves.

**Forgetting equations of motion.** A kinematic algebra of off-shell fields usually does not satisfy the time-slice property until equations of motion are imposed.

**Expecting a Hamiltonian on every background.** Time-slice is an algebraic replacement for global Hamiltonian evolution, not a proof that a preferred Hamiltonian exists.

**Ignoring gauge subtleties.** Gauge theory may require a cohomological or constraint-aware formulation before the time-slice axiom has the right meaning.

## Relations to other pages

[Globally Hyperbolic Spacetimes](/rigorous-qft/locally-covariant-qft/globally-hyperbolic-spacetimes/) supplies the geometric definition of Cauchy surfaces and Cauchy morphisms.

[QFT as a Functor on Spacetimes](/rigorous-qft/locally-covariant-qft/qft-as-functor-on-spacetimes/) introduces the functor $\mathcal A:\mathsf{Loc}\to\mathsf{Alg}$ to which the time-slice axiom is added.

[Additivity and the Time-Slice Axiom](/rigorous-qft/algebraic-qft/additivity-and-time-slice-axiom/) gives the fixed-spacetime Haag–Kastler counterpart.

[Haag–Kastler Axioms](/rigorous-qft/algebraic-qft/haag-kastler-axioms/) explains how time-slice fits among isotony, locality, covariance, and additivity.

[Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) prepares the analytic language needed later for Hadamard states and perturbative renormalization on curved backgrounds.

## Research status

**Established.** The time-slice axiom is a standard supplementary axiom in algebraic and locally covariant QFT. For free normally hyperbolic fields, it can be verified directly from the Cauchy problem and Green-operator support properties.

**Structural.** The axiom is not merely a technical convenience. It is what allows relative Cauchy evolution, metric response, and many rigidity arguments in locally covariant QFT.

**Active.** Gauge theories, topological sectors, boundaries, perturbative BV-BRST theories, and quantum-gravity inspired settings require refined versions. The main issue is not whether hyperbolic propagation exists, but what algebraic or cohomological object is the correct carrier of the propagated observables.

## Exercises

1. **Cauchy morphisms become isomorphisms.** Let $\mathcal A$ satisfy the time-slice axiom and let $\psi:M\to N$ be a Cauchy morphism. What extra algebraic fact does the axiom give beyond injectivity of $\mathcal A(\psi)$?

<details><summary><strong>Solution</strong></summary>

The functorial framework usually takes morphisms in $\mathsf{Alg}$ to be injective algebra homomorphisms, so $\mathcal A(\psi)$ already embeds $\mathcal A(M)$ into $\mathcal A(N)$. The time-slice axiom says more: $\mathcal A(\psi)$ is onto and has an inverse morphism in $\mathsf{Alg}$. Thus every observable in $\mathcal A(N)$ can be represented using observables from the Cauchy subspacetime $M$.

</details>

2. **Fixed-spacetime version.** Suppose $O\subset M$ contains a Cauchy surface of $M$ and the inclusion $\iota:O\hookrightarrow M$ is a morphism in $\mathsf{Loc}$. Write the time-slice statement for $\iota$.

<details><summary><strong>Solution</strong></summary>

Since $O$ contains a Cauchy surface of $M$, the inclusion $\iota$ is a Cauchy morphism. The time-slice axiom gives an isomorphism

$$
\mathcal A(\iota):\mathcal A(O)\xrightarrow{\ \simeq\ }\mathcal A(M).
$$

Identifying $\mathcal A(O)$ with its image in $\mathcal A(M)$, one writes this informally as $\mathcal A_M(O)=\mathcal A(M)$.

</details>

3. **Why off-shell fields fail.** Consider a formal algebra generated by symbols $\Phi(f)$ for all test functions $f$, without imposing $\Phi(Pf)=0$. Why should one not expect the time-slice property?

<details><summary><strong>Solution</strong></summary>

Without the equation-of-motion relation, a test function supported far from a Cauchy neighborhood labels an independent generator. There is no algebraic mechanism that rewrites $\Phi(f)$ in terms of smearings inside the Cauchy region. The time-slice property becomes plausible only after imposing the field equation, which identifies smearings that differ by $P$ applied to a compactly supported test function.

</details>

## References

### Standard first pass

- Romeo Brunetti, Klaus Fredenhagen, and Rainer Verch, "The Generally Covariant Locality Principle – A New Paradigm for Local Quantum Physics," *Communications in Mathematical Physics* **237** (2003), 31–68. DOI: [10.1007/s00220-003-0815-7](https://doi.org/10.1007/s00220-003-0815-7), arXiv: [math-ph/0112041](https://arxiv.org/abs/math-ph/0112041).
- Christopher J. Fewster and Rainer Verch, "Algebraic Quantum Field Theory in Curved Spacetimes," in *Advances in Algebraic Quantum Field Theory*, Springer, 2015. DOI: [10.1007/978-3-319-21353-8_4](https://doi.org/10.1007/978-3-319-21353-8_4), arXiv: [1504.00586](https://arxiv.org/abs/1504.00586).
- Klaus Fredenhagen, "Locally Covariant Quantum Field Theory," arXiv: [hep-th/0403007](https://arxiv.org/abs/hep-th/0403007).

### Background and advanced directions

- Rudolf Haag and Daniel Kastler, "An Algebraic Approach to Quantum Field Theory," *Journal of Mathematical Physics* **5** (1964), 848–861. DOI: [10.1063/1.1704187](https://doi.org/10.1063/1.1704187).
- Jonathan Dimock, "Algebras of Local Observables on a Manifold," *Communications in Mathematical Physics* **77** (1980), 219–228. DOI: [10.1007/BF01269921](https://doi.org/10.1007/BF01269921).
- Christian Bär, Nicolas Ginoux, and Frank Pfäffle, *Wave Equations on Lorentzian Manifolds and Quantization*, European Mathematical Society, 2007. arXiv: [0806.1036](https://arxiv.org/abs/0806.1036).
- Romeo Brunetti, Klaus Fredenhagen, and Kasia Rejzner, "Quantum Gravity from the Point of View of Locally Covariant Quantum Field Theory," *Communications in Mathematical Physics* **345** (2016), 741–779. DOI: [10.1007/s00220-016-2676-x](https://doi.org/10.1007/s00220-016-2676-x), arXiv: [1306.1058](https://arxiv.org/abs/1306.1058).

## Version history

- **2026-06-29:** Initial polished draft. Stated the locally covariant time-slice axiom, related it to fixed-spacetime primitive causality, explained the free scalar example, and flagged gauge-theory subtleties.
