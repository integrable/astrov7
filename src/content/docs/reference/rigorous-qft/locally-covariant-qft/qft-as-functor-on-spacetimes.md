---
title: "QFT as a Functor on Spacetimes"
description: "Define locally covariant quantum field theory as a functor from globally hyperbolic spacetimes to algebras of observables."
sidebar:
  label: "QFT as Functor"
  order: 1
level: Advanced
status: "Polished draft"
source: "Brunetti–Fredenhagen–Verch local covariance; Fewster–Verch curved-spacetime AQFT; Dimock local observables on manifolds."
topics:
  - locally covariant QFT
  - algebraic QFT
  - functoriality
  - curved spacetime
canonicalTopics:
  - locally-covariant-quantum-field-theory
  - functorial-qft
  - qft-on-curved-spacetimes
researchStatus:
  established:
    - "Locally covariant QFT gives a standard functorial formulation of algebraic QFT on globally hyperbolic spacetimes."
  active:
    - "The right functorial conditions for gauge theories, preferred state spaces, dynamical locality, boundaries, and quantum gravity-inspired settings remain active research topics."
---

## Summary

A **locally covariant quantum field theory** assigns algebras of observables to spacetimes in a way that is compatible with embeddings of spacetimes into larger spacetimes. In the standard formulation, the theory is a covariant functor

$$
\mathcal A:\mathsf{Loc}\longrightarrow\mathsf{Alg}.
$$

Here $\mathsf{Loc}$ is a category of globally hyperbolic spacetimes and causal embeddings, while $\mathsf{Alg}$ is a category of unital $*$-algebras or $C^*$-algebras and injective unit-preserving $*$-homomorphisms.

The functorial rules are

$$
\mathcal A(\operatorname{id}_M)=\operatorname{id}_{\mathcal A(M)},
\qquad
\mathcal A(\psi\circ\varphi)
=\mathcal A(\psi)\circ\mathcal A(\varphi).
$$

The first equation says that doing nothing to spacetime does nothing to observables. The second says that embedding spacetime regions in two steps gives the same algebra map as embedding them in one step.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A diagram of a functor from a category of globally hyperbolic spacetimes and causal embeddings to a category of observable algebras and injective star homomorphisms.](/figures/rigorous-qft/locally-covariant-functor.svg)

<figcaption>

A locally covariant QFT is a functor. Spacetimes and causal embeddings are mapped to observable algebras and injective $*$-homomorphisms, with identity and composition preserved.

</figcaption>
</figure>

This framework is the curved-spacetime successor of the Haag–Kastler net idea. On a fixed spacetime $M$, one recovers a local net by applying the functor to suitable subregions $\mathcal O\subset M$:

$$
\mathcal O\longmapsto \mathcal A(\mathcal O).
$$

The new feature is that the background spacetime is no longer fixed once and for all. The same theory must make sense on every admissible spacetime and must behave naturally under embeddings.

## Prerequisites

You should know [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/), [Haag–Kastler Axioms](/rigorous-qft/algebraic-qft/haag-kastler-axioms/), and [Additivity and the Time-Slice Axiom](/rigorous-qft/algebraic-qft/additivity-and-time-slice-axiom/). The page [Globally Hyperbolic Spacetimes](/rigorous-qft/locally-covariant-qft/globally-hyperbolic-spacetimes/) supplies the geometric details behind the objects and morphisms used here.

The categorical language needed here is minimal: a category has objects, morphisms, identity morphisms, and composition; a functor sends objects to objects and morphisms to morphisms while preserving identity and composition.

## Core idea

In ordinary algebraic QFT on Minkowski space, one fixes a spacetime and assigns algebras to its regions:

$$
\mathcal O\subset M
\quad\longmapsto\quad
\mathcal A_M(\mathcal O).
$$

Poincaré covariance then says that spacetime symmetries act compatibly on the net.

This is not enough for QFT on a general curved spacetime. A curved spacetime may have no nontrivial global symmetries at all. If covariance only means covariance under symmetry groups, then a generic curved background has almost no covariance left to express.

The locally covariant idea is to replace symmetry under automorphisms by functoriality under embeddings:

$$
\text{symmetry group action on one spacetime}
\quad\leadsto\quad
\text{functorial assignment over all spacetimes}.
$$

A symmetry is just a special case of an embedding from a spacetime to itself. Local covariance therefore contains ordinary covariance but is not limited to symmetric backgrounds.

This page introduces the basic functorial framework. The following pages add globally hyperbolic geometry, the time-slice axiom, relative Cauchy evolution, locally covariant fields, Hadamard states, and renormalization in curved spacetime.

## Setup and conventions

The standard source category is denoted here by $\mathsf{Loc}$. Its objects are globally hyperbolic spacetimes $M$ of fixed dimension $d$, equipped with orientation and time orientation. Concretely, an object is a tuple such as

$$
M=(\mathcal M,g,\mathfrak o,\mathfrak t),
$$

where $\mathcal M$ is a smooth manifold, $g$ is a Lorentzian metric, $\mathfrak o$ is an orientation, and $\mathfrak t$ is a time orientation.

A morphism

$$
\psi:M\to N
$$

is usually taken to be a smooth isometric embedding preserving orientation and time orientation, with causally convex image. Causal convexity means that any causal curve in $N$ whose endpoints lie in $\psi(M)$ is entirely contained in $\psi(M)$. This condition prevents an embedded spacetime from missing causal shortcuts through the ambient spacetime.

The target category $\mathsf{Alg}$ has algebras as objects. Depending on the version, these can be unital topological $*$-algebras, unital $C^*$-algebras, or more elaborate algebraic objects such as differential graded algebras. In the simplest $C^*$-algebraic version, morphisms are injective unit-preserving $*$-homomorphisms:

$$
\alpha:\mathcal A\to\mathcal B.
$$

The injectivity requirement means that observables in the smaller spacetime are faithfully represented as observables in the larger spacetime.

## The functorial definition

A locally covariant QFT is a covariant functor

$$
\mathcal A:\mathsf{Loc}\to\mathsf{Alg}.
$$

This consists of two assignments.

First, each spacetime $M$ is assigned an algebra

$$
M\longmapsto \mathcal A(M).
$$

This algebra represents the observables available in the theory on the spacetime $M$.

Second, each admissible embedding $\psi:M\to N$ is assigned an algebra homomorphism

$$
\mathcal A(\psi):\mathcal A(M)\to\mathcal A(N).
$$

This map tells us how to regard an observable of the theory on the smaller spacetime $M$ as an observable of the theory on the larger spacetime $N$.

Functoriality imposes the identity and composition laws:

$$
\mathcal A(\operatorname{id}_M)
=\operatorname{id}_{\mathcal A(M)},
$$

and, for composable spacetime morphisms

$$
M\xrightarrow{\ \varphi\ }N
\xrightarrow{\ \psi\ }P,
$$

one has

$$
\mathcal A(\psi\circ\varphi)
=\mathcal A(\psi)\circ\mathcal A(\varphi).
$$

This second equation is the heart of the definition. It says that the algebraic localization of observables is independent of how one factors a geometric embedding into intermediate embeddings.

## Recovering a Haag–Kastler net

Fix a spacetime $M$. Let $\mathsf{Reg}(M)$ be the category whose objects are suitable causally convex open subregions $\mathcal O\subset M$ and whose morphisms are inclusions.

Each region $\mathcal O$ can itself be regarded as a globally hyperbolic spacetime with the induced metric, orientation, and time orientation, when the region is chosen appropriately. The inclusion

$$
\iota_{\mathcal O}:\mathcal O\hookrightarrow M
$$

gives an algebra homomorphism

$$
\mathcal A(\iota_{\mathcal O}):
\mathcal A(\mathcal O)\to\mathcal A(M).
$$

The image

$$
\mathcal A_M(\mathcal O)
:=
\mathcal A(\iota_{\mathcal O})\bigl(\mathcal A(\mathcal O)\bigr)
\subset \mathcal A(M)
$$

is the local algebra of $\mathcal O$ inside the global algebra of $M$.

If $\mathcal O_1\subset\mathcal O_2\subset M$, functoriality gives

$$
\mathcal A_M(\mathcal O_1)
\subset
\mathcal A_M(\mathcal O_2),
$$

which is isotony. Thus a locally covariant theory automatically gives a local net on each fixed spacetime.

If $M$ has an isometry $\kappa:M\to M$, functoriality gives an automorphism

$$
\mathcal A(\kappa):\mathcal A(M)\to\mathcal A(M).
$$

In Minkowski space, the Poincaré group appears this way. Ordinary covariance is recovered as a special case of local covariance.

## Einstein causality

The functorial definition by itself is not enough. One normally imposes **Einstein causality** as an additional axiom.

Let

$$
\psi_1:M_1\to N,
\qquad
\psi_2:M_2\to N
$$

be two spacetime embeddings whose images are causally disjoint in $N$. Then the corresponding subalgebras of $\mathcal A(N)$ should commute:

$$
\bigl[
\mathcal A(\psi_1)(A_1),
\mathcal A(\psi_2)(A_2)
\bigr]=0
$$

for all

$$
A_1\in\mathcal A(M_1),
\qquad
A_2\in\mathcal A(M_2).
$$

This is the locally covariant version of Haag–Kastler locality. Instead of saying that two subregions of one fixed spacetime have commuting algebras, it says that two spacetime embeddings with causally disjoint images have commuting images in the target algebra.

The condition is sometimes written as a property of the diagram

$$
M_1\xrightarrow{\psi_1}N\xleftarrow{\psi_2}M_2.
$$

If the images of the two arrows are causally separated, then the two induced algebra maps have commuting ranges.

## The time-slice axiom

The second major supplementary condition is the **time-slice axiom**, developed in [Time-Slice Axiom](/rigorous-qft/locally-covariant-qft/time-slice-axiom/).

A morphism

$$
\psi:M\to N
$$

is a **Cauchy morphism** if $\psi(M)$ contains a Cauchy surface of $N$. The time-slice axiom says

$$
\psi\text{ Cauchy}
\quad\Longrightarrow\quad
\mathcal A(\psi):\mathcal A(M)\xrightarrow{\ \simeq\ }\mathcal A(N).
$$

Thus Cauchy morphisms become algebra isomorphisms.

This expresses the equation-of-motion content of the theory. If the image of $M$ contains enough spacetime to determine all of $N$ by hyperbolic evolution, then the observables assigned to $M$ and $N$ should be algebraically equivalent.

In a fixed-spacetime net, this becomes the statement that the algebra in a neighborhood of a Cauchy surface generates the algebra of the corresponding domain of dependence. The previous page [Additivity and the Time-Slice Axiom](/rigorous-qft/algebraic-qft/additivity-and-time-slice-axiom/) explains this in the Haag–Kastler language.

## The functor is not just notation

It is tempting to treat the functorial definition as a fancy way to restate local nets. It is more than that.

First, it compares different spacetimes without choosing coordinates or embeddings into a universal background. The theory is defined on all objects of $\mathsf{Loc}$ at once.

Second, it gives a precise meaning to local general covariance: the assignment of observables should be natural with respect to all admissible spacetime embeddings, not only with respect to global symmetry groups.

Third, it makes relative Cauchy evolution possible. If two metrics differ only in a compact region between Cauchy surfaces, the time-slice axiom lets one compare the corresponding algebras by moving through Cauchy neighborhoods. The resulting automorphism measures the response of the theory to a local change in the metric. In suitable theories, its functional derivative is related to the stress tensor.

Fourth, it provides a clean language for no-go theorems about preferred states. A generic curved spacetime has no distinguished vacuum. The locally covariant framework makes precise why a natural choice of one preferred state in every spacetime is too much to ask under physically reasonable assumptions.

## Locally covariant fields as natural transformations

The functorial viewpoint also gives a precise definition of a field that is local and covariant.

Let $\mathcal D$ be a test-function functor assigning to each spacetime $M$ a space of compactly supported test functions $\mathcal D(M)$, with pushforward maps induced by embeddings. Let $\mathcal A$ be the observable-algebra functor.

A locally covariant scalar field is, schematically, a natural transformation

$$
\Phi:\mathcal D\Longrightarrow\mathcal A.
$$

For each spacetime $M$, this gives a map

$$
\Phi_M:\mathcal D(M)\to\mathcal A(M),
\qquad
f\mapsto \Phi_M(f).
$$

Naturality says that for every embedding $\psi:M\to N$,

$$
\mathcal A(\psi)\bigl(\Phi_M(f)\bigr)
=
\Phi_N(\psi_*f).
$$

In words: first form the field observable in $M$ and embed it into $N$, or first push the test function forward to $N$ and then form the field observable there. The result is the same.

This equation is the curved-spacetime replacement for the familiar covariance law of fields under Poincaré transformations. It is also more general, because $\psi$ need not be a symmetry.

## State spaces are contravariant

The functor $\mathcal A$ assigns algebras covariantly: embeddings of spacetimes give embeddings of algebras. States go the other way.

If

$$
\alpha:\mathcal A(M)\to\mathcal A(N)
$$

is a $*$-homomorphism and $\omega_N$ is a state on $\mathcal A(N)$, then restriction gives a state on $\mathcal A(M)$:

$$
\omega_M=\omega_N\circ\alpha.
$$

Thus state spaces naturally form a contravariant assignment:

$$
\mathcal S(N)\to\mathcal S(M).
$$

This asymmetry is physically important. Observables localized in a smaller spacetime can be embedded into a larger spacetime, but a state on the larger spacetime restricts to a state on the smaller one. There is generally no canonical way to extend an arbitrary state from a subspacetime to a larger spacetime.

In curved-spacetime QFT this is one reason the notion of a vacuum is subtle. A natural state prescription would have to be compatible with all embeddings, and broad no-go results show that such prescriptions are usually impossible for physically reasonable theories.

## Example: the free scalar field

The free Klein–Gordon field is the guiding example. On each globally hyperbolic spacetime $M$, let

$$
P_M=\Box_{g_M}+m^2+\xi R_M.
$$

One constructs a symplectic space of solutions or, equivalently, a quotient of test functions by the equation of motion. The causal propagator $E_M$ gives the commutator structure. Quantization produces a CCR algebra $\mathcal A(M)$ generated by smeared fields with relations

$$
\Phi_M(P_M f)=0,
$$

and

$$
[\Phi_M(f),\Phi_M(h)]
=iE_M(f,h)\mathbf 1.
$$

If $\psi:M\to N$ is an admissible embedding, the pushforward of test functions gives a homomorphism satisfying

$$
\mathcal A(\psi)\bigl(\Phi_M(f)\bigr)
=
\Phi_N(\psi_*f).
$$

The causally convex nature of the embedding ensures that the causal propagators behave compatibly. Hyperbolicity gives the time-slice property.

This example shows why the functorial language is not abstract decoration. It exactly captures the natural behavior expected of a wave equation and its quantization on all backgrounds.

## Common pitfalls

**Thinking local covariance means diffeomorphism invariance of one spacetime.** Local covariance is a functorial statement over a category of spacetimes. Diffeomorphisms or isometries of one spacetime are only special morphisms.

**Allowing arbitrary embeddings.** Morphisms are restricted. They preserve the metric, orientation, and time orientation, and their images are causally well behaved. Without such restrictions, the algebraic maps would not respect causal structure.

**Forgetting that $\mathcal A(M)$ is not a Hilbert space.** The basic functor assigns algebras, not Hilbert spaces. Hilbert-space representations arise after choosing states, typically through GNS constructions.

**Confusing covariance with a preferred state.** The functorial theory may be locally covariant even though there is no natural vacuum state in each spacetime.

**Ignoring the time-slice axiom.** A functor without the time-slice property may assign algebras to spacetimes, but it may not encode hyperbolic dynamics in the desired way.

**Assuming the framework solves quantum gravity.** Locally covariant QFT treats quantum fields on classical background spacetimes. It is useful for perturbative and conceptual approaches to gravity, but it is not by itself a nonperturbative theory of quantum spacetime.

**Assuming all physically important theories fit the simple $C^*$-algebra target.** Gauge theories, perturbative theories, fermions, BV complexes, and renormalized local fields may require enriched target categories.

## Relations to other pages

[Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/) is the fixed-spacetime precursor. A locally covariant functor restricts to a Haag–Kastler-type net on every spacetime.

[Globally Hyperbolic Spacetimes](/rigorous-qft/locally-covariant-qft/globally-hyperbolic-spacetimes/) defines the background category used here: Cauchy surfaces, causal diamonds, causal convexity, and smooth splittings.

[Time-Slice Axiom](/rigorous-qft/locally-covariant-qft/time-slice-axiom/) develops the locally covariant version of the time-slice condition: Cauchy morphisms are mapped to isomorphisms.

[Additivity and the Time-Slice Axiom](/rigorous-qft/algebraic-qft/additivity-and-time-slice-axiom/) explains the fixed-spacetime version of the same idea in Haag–Kastler language.

[States and GNS Representation](/rigorous-qft/algebraic-qft/states-and-gns-representation/) explains how states on algebras produce Hilbert spaces. This matters because locally covariant QFT is usually formulated at the algebraic level before choosing representations.

[Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) gives one of the key analytic tools behind modern curved-spacetime QFT, especially Hadamard states and perturbative renormalization.

## Research status

**Established.** The functorial framework of locally covariant QFT is a standard mathematical formulation of algebraic QFT on curved spacetimes. It cleanly captures local covariance, Einstein causality, the time-slice axiom, locally covariant fields, and relative Cauchy evolution.

**Subtle.** Local covariance alone is not the whole story. Further conditions are needed to express that a theory represents "the same physics" in all spacetimes. This motivates dynamical locality and related criteria.

**Active.** Important ongoing directions include gauge theories and constraints, locally covariant renormalization, state-space selection, Hadamard conditions, boundaries and defects, theories with topological charges, perturbative quantum gravity, and comparisons with factorization-algebra or BV-BRST formulations.

## Exercises

1. **Functorial isotony.** Let $\mathcal O_1\subset\mathcal O_2\subset M$ be admissible regions. Use functoriality to show that the local algebra of $\mathcal O_1$ embeds into the local algebra of $\mathcal O_2$.

<details><summary><strong>Solution</strong></summary>

Let $j:\mathcal O_1\hookrightarrow\mathcal O_2$ and $i:\mathcal O_2\hookrightarrow M$ be inclusions. Then $i\circ j:\mathcal O_1\hookrightarrow M$. Functoriality gives

$$
\mathcal A(i\circ j)=\mathcal A(i)\circ\mathcal A(j).
$$

The image of $\mathcal A(\mathcal O_1)$ in $\mathcal A(M)$ is therefore contained in the image of $\mathcal A(\mathcal O_2)$ in $\mathcal A(M)$, because it first lands in $\mathcal A(\mathcal O_2)$ and then embeds into $\mathcal A(M)$. This is isotony.

</details>

2. **Automorphisms from spacetime symmetries.** Suppose $\kappa:M\to M$ is an isomorphism in $\mathsf{Loc}$. Show that $\mathcal A(\kappa)$ is an algebra automorphism.

<details><summary><strong>Solution</strong></summary>

Since $\kappa$ is an isomorphism, it has an inverse $\kappa^{-1}$ with

$$
\kappa^{-1}\circ\kappa=\operatorname{id}_M,
\qquad
\kappa\circ\kappa^{-1}=\operatorname{id}_M.
$$

Applying the functor gives

$$
\mathcal A(\kappa^{-1})\circ\mathcal A(\kappa)
=\operatorname{id}_{\mathcal A(M)},
$$

and

$$
\mathcal A(\kappa)\circ\mathcal A(\kappa^{-1})
=\operatorname{id}_{\mathcal A(M)}.
$$

Thus $\mathcal A(\kappa)$ is invertible, with inverse $\mathcal A(\kappa^{-1})$.

</details>

3. **Naturality of a field.** Explain in words the equation

$$
\mathcal A(\psi)\bigl(\Phi_M(f)\bigr)=\Phi_N(\psi_*f).
$$

<details><summary><strong>Solution</strong></summary>

The equation says that forming the field observable and then embedding it into the larger spacetime gives the same result as first pushing the test function forward and then forming the field observable in the larger spacetime. It is the functorial version of a covariance law for fields.

</details>

## References

### Standard first pass

- Romeo Brunetti, Klaus Fredenhagen, and Rainer Verch, "The generally covariant locality principle – A new paradigm for local quantum physics," *Communications in Mathematical Physics* **237** (2003), 31–68. [doi:10.1007/s00220-003-0815-7](https://doi.org/10.1007/s00220-003-0815-7), arXiv: [math-ph/0112041](https://arxiv.org/abs/math-ph/0112041).
- Christopher J. Fewster and Rainer Verch, "Algebraic Quantum Field Theory in Curved Spacetimes," in *Advances in Algebraic Quantum Field Theory*, Springer, 2015. [doi:10.1007/978-3-319-21353-8_4](https://doi.org/10.1007/978-3-319-21353-8_4), arXiv: [1504.00586](https://arxiv.org/abs/1504.00586).
- Klaus Fredenhagen, "Locally covariant quantum field theory," arXiv: [hep-th/0403007](https://arxiv.org/abs/hep-th/0403007).

### Background and advanced directions

- Jonathan Dimock, "Algebras of local observables on a manifold," *Communications in Mathematical Physics* **77** (1980), 219–228. [doi:10.1007/BF01269921](https://doi.org/10.1007/BF01269921).
- Romeo Brunetti and Klaus Fredenhagen, "Quantum Field Theory on Curved Backgrounds," arXiv: [0901.2063](https://arxiv.org/abs/0901.2063).
- Christopher J. Fewster and Rainer Verch, "Dynamical locality and covariance: What makes a physical theory the same in all spacetimes?" *Annales Henri Poincaré* **13** (2012), 1613–1674. [doi:10.1007/s00023-012-0165-0](https://doi.org/10.1007/s00023-012-0165-0), arXiv: [1106.4785](https://arxiv.org/abs/1106.4785).
- Romeo Brunetti, Klaus Fredenhagen, and Kasia Rejzner, "Quantum gravity from the point of view of locally covariant quantum field theory," *Communications in Mathematical Physics* **345** (2016), 741–779. [doi:10.1007/s00220-016-2676-x](https://doi.org/10.1007/s00220-016-2676-x), arXiv: [1306.1058](https://arxiv.org/abs/1306.1058).

## Version history

- **2026-06-29:** Lightly updated prerequisites and related links after adding globally hyperbolic spacetimes and the locally covariant time-slice page.
- **2026-06-29:** Initial polished draft. Introduced the functorial definition, Einstein causality, time-slice, recovery of fixed-spacetime nets, natural fields, state-space covariance, and the free scalar example.
