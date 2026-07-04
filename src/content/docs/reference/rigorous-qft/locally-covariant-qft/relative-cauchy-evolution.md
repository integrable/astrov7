---
title: "Relative Cauchy Evolution"
description: "Defines relative Cauchy evolution as the automorphism measuring how a locally covariant QFT responds to compact metric perturbations."
sidebar:
  label: "Relative Cauchy Evolution"
  order: 4
level: Advanced
status: "Polished draft"
source: "Brunetti–Fredenhagen–Verch local covariance; Fewster–Verch dynamical locality."
topics:
  - relative Cauchy evolution
  - locally covariant QFT
  - time-slice axiom
  - metric perturbations
canonicalTopics:
  - relative-cauchy-evolution
  - locally-covariant-quantum-field-theory
  - qft-on-curved-spacetimes
researchStatus:
  established:
    - "For time-slice locally covariant theories, relative Cauchy evolution is the standard algebraic construction encoding response to compact metric perturbations."
  active:
    - "Gauge theories, higher categorical AQFT, boundaries, and perturbative quantum gravity require refined versions of relative Cauchy evolution."
---

## Summary

Relative Cauchy evolution is the automorphism of the observable algebra that compares a locally covariant QFT on a spacetime $M$ with the same theory on a compactly perturbed metric $M[h]$. It is the curved-spacetime replacement for asking how observables respond when the background geometry is changed in a bounded region.

Let $M=(\mathcal M,g)$ be a globally hyperbolic spacetime and let $h$ be a compactly supported smooth symmetric tensor such that $g+h$ is again a globally hyperbolic Lorentzian metric with the same orientation and time orientation. Write $M[h]=(\mathcal M,g+h)$. Choose past and future Cauchy regions $M^-$ and $M^+$ outside the support of $h$, and let

$$
i^\pm:M^\pm\to M,
\qquad
j^\pm:M^\pm\to M[h]
$$

be the natural embeddings. If the theory $\mathcal A:\mathsf{Loc}\to\mathsf{Alg}$ satisfies the time-slice axiom, then all four algebra maps are isomorphisms and one defines

$$
\operatorname{rce}_M[h]
=
\mathcal A(i^+)\,\mathcal A(j^+)^{-1}\,
\mathcal A(j^-)\,\mathcal A(i^-)^{-1}
\in \operatorname{Aut}(\mathcal A(M)).
$$

The construction uses no preferred vacuum, no Killing symmetry, and no Hamiltonian. It uses only local covariance, global hyperbolicity, compact support of the perturbation, and the time-slice axiom.

:::caution[Conventions]
Some papers use the inverse automorphism because they order the past-to-future comparison oppositely. This page uses the convention displayed above. With this convention the infinitesimal generator is chosen in the next page so that, when a stress tensor exists,

$$
\left.\frac{d}{ds}\right|_{s=0}\operatorname{rce}_M[sh](A)
=\frac{i}{2}[T_M(h),A].
$$
:::

## Prerequisites

You should know [QFT as a Functor on Spacetimes](/rigorous-qft/locally-covariant-qft/qft-as-functor-on-spacetimes/), [Globally Hyperbolic Spacetimes](/rigorous-qft/locally-covariant-qft/globally-hyperbolic-spacetimes/), and the [Time-Slice Axiom](/rigorous-qft/locally-covariant-qft/time-slice-axiom/). The algebraic fixed-spacetime version is reviewed in [Additivity and the Time-Slice Axiom](/rigorous-qft/algebraic-qft/additivity-and-time-slice-axiom/).

## Core idea

A compact metric perturbation changes the spacetime only in a bounded region. Far enough in the past and far enough in the future, the original spacetime $M$ and the perturbed spacetime $M[h]$ are literally the same manifold with the same metric. The time-slice axiom says that a Cauchy region in the past already determines the full algebra, and the same is true for a Cauchy region in the future.

Relative Cauchy evolution compares two ways to transport an observable from the past to the future:

1. propagate it through the unperturbed spacetime $M$;
2. propagate it through the perturbed spacetime $M[h]$.

The mismatch is an automorphism of $\mathcal A(M)$. This automorphism is not ordinary time evolution inside one spacetime. It is the response of the theory to a local change of the background geometry.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Relative Cauchy evolution as a comparison between an unperturbed spacetime and a compactly perturbed spacetime](/figures/rigorous-qft/relative-cauchy-evolution.svg)

<figcaption>

Relative Cauchy evolution compares $M$ and $M[h]$ by using past and future Cauchy regions where the two metrics agree. The two time-slice identifications differ by an automorphism of $\mathcal A(M)$.

</figcaption>
</figure>

## Setup and conventions

Let $\mathsf{Loc}$ be the spacetime category used in this chapter: objects are oriented and time-oriented globally hyperbolic Lorentzian spacetimes, and morphisms are causal, orientation-preserving, time-orientation-preserving isometric embeddings. Let

$$
\mathcal A:\mathsf{Loc}\longrightarrow \mathsf{Alg}
$$

be a locally covariant theory satisfying the time-slice axiom.

A metric perturbation on $M=(\mathcal M,g)$ is a compactly supported smooth symmetric covariant tensor

$$
h\in C_c^\infty(S^2T^*\mathcal M)
$$

such that $g+h$ is again a globally hyperbolic Lorentzian metric with the same orientation and time orientation. The perturbed spacetime is denoted

$$
M[h]=(\mathcal M,g+h).
$$

Let $K=\operatorname{supp}h$. Choose open globally hyperbolic subspacetimes $M^-$ and $M^+$ satisfying the following conditions:

- $M^-$ lies to the past of $K$ and contains a Cauchy surface for both $M$ and $M[h]$;
- $M^+$ lies to the future of $K$ and contains a Cauchy surface for both $M$ and $M[h]$;
- the metrics $g$ and $g+h$ agree on $M^-$ and $M^+$.

One standard choice is to take suitable globally hyperbolic subregions of

$$
M^-\subset M\setminus J_M^+(K),
\qquad
M^+\subset M\setminus J_M^-(K),
$$

where $J_M^+(K)$ and $J_M^-(K)$ are the causal future and past of $K$ in $M$. The exact choice is not part of the observable physics; the construction below is independent of the chosen cuts.

There are four natural embeddings:

$$
i^-:M^-\to M,
\qquad
j^-:M^-\to M[h],
$$

and

$$
i^+:M^+\to M,
\qquad
j^+:M^+\to M[h].
$$

Because each image contains a Cauchy surface of the target, each of these morphisms is a Cauchy morphism. By the time-slice axiom, the induced algebra maps

$$
\mathcal A(i^-),\ \mathcal A(j^-),\
\mathcal A(i^+),\ \mathcal A(j^+)
$$

are isomorphisms.

## The definition

The relative Cauchy evolution induced by $h$ is

$$
\boxed{
\operatorname{rce}_M[h]
=
\mathcal A(i^+)\,\mathcal A(j^+)^{-1}\,
\mathcal A(j^-)\,\mathcal A(i^-)^{-1}.
}
$$

Read the formula from right to left:

$$
\mathcal A(M)
\xrightarrow{\ \mathcal A(i^-)^{-1}\ }
\mathcal A(M^-)
\xrightarrow{\ \mathcal A(j^-)\ }
\mathcal A(M[h])
\xrightarrow{\ \mathcal A(j^+)^{-1}\ }
\mathcal A(M^+)
\xrightarrow{\ \mathcal A(i^+)\ }
\mathcal A(M).
$$

Thus $\operatorname{rce}_M[h]$ is an automorphism of $\mathcal A(M)$.

This definition is deliberately algebraic. It does not say that states evolve unitarily on a preferred Hilbert space. A state $\omega$ on $\mathcal A(M)$ can be pulled back along the automorphism,

$$
\omega\longmapsto \omega\circ \operatorname{rce}_M[h],
$$

but the basic object is the algebra automorphism, not a Hilbert-space operator.

## Independence of the past and future cuts

The formula appears to depend on the chosen subspacetimes $M^-$ and $M^+$. It does not.

Suppose one chooses smaller or larger past and future Cauchy regions satisfying the same support conditions. The inclusions between these choices are themselves Cauchy morphisms, hence induce isomorphisms by the time-slice axiom. Naturality of the functor $\mathcal A$ then makes the corresponding comparison diagram commute.

The result is that $\operatorname{rce}_M[h]$ depends on the perturbation $h$ and the background theory, not on an auxiliary choice of Cauchy cuts. This is the same structural reason that time evolution for a hyperbolic equation is independent of the particular Cauchy surface used to compute it.

## Basic properties

The most important formal properties are the following.

| Property | Statement | Meaning |
|---|---|---|
| Identity at zero | $\operatorname{rce}_M[0]=\operatorname{id}_{\mathcal A(M)}$ | No metric perturbation means no response. |
| Automorphism | $\operatorname{rce}_M[h]\in\operatorname{Aut}(\mathcal A(M))$ | The comparison is invertible because all four maps are time-slice isomorphisms. |
| Local dependence | Only the causal influence of $\operatorname{supp}h$ can matter. | Observables causally disjoint from the perturbation are unaffected. |
| Covariance | Embeddings intertwine relative Cauchy evolution on compatible perturbations. | Metric response is itself locally covariant. |
| Infinitesimal derivation | Differentiating at $h=0$ gives a derivation of $\mathcal A(M)$ when the derivative exists. | The derivative is the algebraic form of stress-energy response. |

For the local-dependence statement, suppose an observable is localized in a region $O$ that is causally disjoint from $\operatorname{supp}h$. Then one can choose the comparison regions so that the relevant local embedding of $O$ factors through a part of spacetime on which the two metrics agree. By functoriality and Einstein causality, the relative Cauchy evolution acts trivially on that localized observable.

## Why this is dynamics

In a fixed stationary spacetime, dynamics is often described by a one-parameter group of time translations. In a generic curved spacetime, there is no preferred time-translation symmetry. Relative Cauchy evolution replaces the question

$$
\text{How does an observable evolve under time translation?}
$$

by the more generally covariant question

$$
\text{How does an observable respond to a compact change of geometry?}
$$

This is why the construction is central in locally covariant QFT. It gives a model-independent meaning to the dynamics of the theory even when no Hamiltonian has been chosen.

The analogy with scattering is useful. A compact metric perturbation is like a finite-duration disturbance of the background. The past region supplies incoming data, the future region supplies outgoing data, and relative Cauchy evolution is the scattering automorphism induced by the disturbance.

The analogy should not be overread. No particle interpretation is required, no asymptotic flatness is assumed, and the construction applies to local observable algebras rather than to an S-matrix between Fock spaces.

## Infinitesimal relative Cauchy evolution

If the map

$$
s\longmapsto \operatorname{rce}_M[sh](A)
$$

is differentiable at $s=0$, define

$$
\delta_M[h](A)
=
\left.\frac{d}{ds}\right|_{s=0}\operatorname{rce}_M[sh](A).
$$

Because $\operatorname{rce}_M[sh]$ is an algebra automorphism for each small $s$, its derivative satisfies the Leibniz rule

$$
\delta_M[h](AB)
=
\delta_M[h](A)B+A\delta_M[h](B).
$$

Thus infinitesimal relative Cauchy evolution is a derivation of the algebra whenever it exists. In many standard quantum field theories, this derivation is implemented by the smeared stress tensor:

$$
\delta_M[h](A)
=
\frac{i}{2}[T_M(h),A],
\qquad
T_M(h)=\int_M T_M^{\mu\nu}h_{\mu\nu}\,d\operatorname{vol}_g.
$$

This formula is a theorem in important free-field examples and a guiding structural principle in perturbative algebraic QFT. It is not part of the bare definition of locally covariant QFT, because an arbitrary functor need not come equipped with a differentiable metric dependence or a stress tensor inside the algebra.

## Example: the linear scalar field

For the classical Klein–Gordon operator on a curved spacetime,

$$
P_g=\Box_g+m^2+\xi R_g,
$$

a metric perturbation changes the differential operator to $P_{g+h}$. The retarded and advanced Green operators, the solution space, and the symplectic form can all be compared using Cauchy evolution. The classical relative Cauchy evolution is a symplectic transformation of the space of solutions.

After CCR quantization, the same comparison induces an automorphism of the Weyl algebra. Infinitesimally, it is generated by the stress-energy tensor of the scalar field, with the expected curvature-coupling dependence. This example is valuable because every step can be made explicit, but the abstract construction does not depend on having a Lagrangian scalar field.

## Relation to dynamical locality

Relative Cauchy evolution also gives a way to define what part of the algebra is dynamically associated with a spacetime region. Roughly, an observable is dynamically localized in a region $O$ if it is insensitive to all metric perturbations supported outside $O$.

This can be compared with the kinematic local algebra assigned directly to $O$ by functoriality. A theory is called dynamically local when these two notions of local physics agree under suitable hypotheses.

Dynamical locality is not needed to define relative Cauchy evolution. It is a stronger condition used to sharpen the phrase "the same physics in all spacetimes." Some locally covariant functors satisfy it; some artificial examples do not. Gauge theories require care because gauge redundancy and topological sectors can blur the naive comparison between kinematic and dynamical localization.

## Common pitfalls

**Relative Cauchy evolution is not ordinary time evolution.** It compares two background metrics. It does not require a time-translation Killing vector or a preferred Hamiltonian.

**The perturbation must be compactly supported.** The past and future comparison regions exist because the metrics agree outside a bounded causal disturbance. Global changes of metric require additional choices and are not what this construction defines.

**The time-slice axiom is essential.** Without it, the maps from Cauchy neighborhoods to full spacetimes need not be isomorphisms, and the displayed formula cannot be formed.

**The construction is algebraic before it is Hilbert-space-theoretic.** A particular state may or may not implement $\operatorname{rce}_M[h]$ by a unitary operator in its GNS representation.

**The infinitesimal generator is not automatically an element of the original algebra.** In many theories, the stress tensor is an operator-valued distribution in an extended algebra or appears as a derivation rather than a bounded observable.

**Sign conventions vary.** If another source defines the past-to-future comparison in the opposite order, its relative Cauchy evolution is the inverse of the one used here, and the sign in the stress-tensor formula changes accordingly.

## Relations to other pages

Relative Cauchy evolution uses the [Time-Slice Axiom](/rigorous-qft/locally-covariant-qft/time-slice-axiom/) in an essential way. It is the bridge from functorial kinematics to the [Stress Tensor from Local Covariance](/rigorous-qft/locally-covariant-qft/stress-tensor-from-local-covariance/) and to later pages on locally covariant fields, Hadamard states, and algebraic renormalization in curved spacetime.

It also refines the fixed-spacetime discussion of [Haag–Kastler Axioms](/rigorous-qft/algebraic-qft/haag-kastler-axioms/) by replacing a preferred spacetime symmetry group with covariance over a category of spacetimes.

## Research status

Relative Cauchy evolution is an established tool in locally covariant algebraic QFT. It is part of the original Brunetti–Fredenhagen–Verch formulation and is central in later work on dynamical locality and curved-spacetime QFT.

For free scalar, Dirac, and several other linear fields, the construction can be carried out explicitly and its infinitesimal form is related to the stress-energy tensor. In perturbative algebraic QFT, relative Cauchy evolution is connected to the dependence of interacting fields on the background metric and to conservation of the stress tensor under suitable renormalization conditions.

Active directions include gauge theories, theories with boundaries, homotopy AQFT, perturbative quantum gravity, and the precise relationship between relative Cauchy evolution and background independence. In these settings, the words "metric perturbation," "observable algebra," and "time-slice isomorphism" may require enriched or derived versions.

## Exercises

1. **Check the types in the definition.** Starting with $A\in\mathcal A(M)$, verify that each factor in

   $$
   \mathcal A(i^+)\,\mathcal A(j^+)^{-1}\,
   \mathcal A(j^-)\,\mathcal A(i^-)^{-1}(A)
   $$

   has the correct domain and codomain.

   <details><summary><strong>Solution</strong></summary>

   Since $i^-:M^-\to M$ is a Cauchy morphism, $\mathcal A(i^-):\mathcal A(M^-)\to\mathcal A(M)$ is an isomorphism. Hence $\mathcal A(i^-)^{-1}$ maps $\mathcal A(M)$ to $\mathcal A(M^-)$. Then $\mathcal A(j^-)$ maps $\mathcal A(M^-)$ to $\mathcal A(M[h])$. Since $j^+:M^+\to M[h]$ is also Cauchy, $\mathcal A(j^+)^{-1}$ maps $\mathcal A(M[h])$ to $\mathcal A(M^+)$. Finally $\mathcal A(i^+)$ maps $\mathcal A(M^+)$ to $\mathcal A(M)$. The composite is therefore an endomorphism of $\mathcal A(M)$, and because all factors are isomorphisms it is an automorphism.

   </details>

2. **Zero perturbation.** Show that $\operatorname{rce}_M[0]=\operatorname{id}_{\mathcal A(M)}$.

   <details><summary><strong>Solution</strong></summary>

   If $h=0$, then $M[h]=M$ and the embeddings $j^\pm$ are the same as $i^\pm$. The definition becomes

   $$
   \mathcal A(i^+)\,\mathcal A(i^+)^{-1}\,
   \mathcal A(i^-)\,\mathcal A(i^-)^{-1}
   =\operatorname{id}_{\mathcal A(M)}.
   $$

   </details>

3. **Derivation from differentiable automorphisms.** Suppose $\alpha_s$ is a differentiable family of algebra automorphisms with $\alpha_0=\operatorname{id}$. Define $\delta(A)=\left.d\alpha_s(A)/ds\right|_{s=0}$. Prove that $\delta(AB)=\delta(A)B+A\delta(B)$.

   <details><summary><strong>Solution</strong></summary>

   Because each $\alpha_s$ is an algebra homomorphism,

   $$
   \alpha_s(AB)=\alpha_s(A)\alpha_s(B).
   $$

   Differentiate at $s=0$ and use $\alpha_0(A)=A$ and $\alpha_0(B)=B$:

   $$
   \delta(AB)=\delta(A)B+A\delta(B).
   $$

   </details>

4. **Why compact support matters.** Explain why a metric perturbation that changes the metric forever into the future would not fit directly into the definition above.

   <details><summary><strong>Solution</strong></summary>

   The construction needs a future Cauchy region $M^+$ on which $M$ and $M[h]$ agree, so that the same spacetime region embeds into both targets as an isometric subspacetime. If the perturbation persists forever into the future, there may be no such common future Cauchy region. One would then need extra choices or a different comparison problem, rather than the canonical relative Cauchy evolution defined here.

   </details>

## References

### Core sources

- Romeo Brunetti, Klaus Fredenhagen, and Rainer Verch, "The Generally Covariant Locality Principle – A New Paradigm for Local Quantum Physics," *Communications in Mathematical Physics* **237** (2003), 31–68. DOI: [10.1007/s00220-003-0815-7](https://doi.org/10.1007/s00220-003-0815-7), arXiv: [math-ph/0112041](https://arxiv.org/abs/math-ph/0112041).
- Christopher J. Fewster and Rainer Verch, "Dynamical Locality and Covariance: What Makes a Physical Theory the Same in all Spacetimes?" *Annales Henri Poincaré* **13** (2012), 1613–1674. DOI: [10.1007/s00023-012-0165-0](https://doi.org/10.1007/s00023-012-0165-0), arXiv: [1106.4785](https://arxiv.org/abs/1106.4785).
- Christopher J. Fewster and Rainer Verch, "Algebraic Quantum Field Theory in Curved Spacetimes," in *Advances in Algebraic Quantum Field Theory*, Springer, 2015. DOI: [10.1007/978-3-319-21353-8_4](https://doi.org/10.1007/978-3-319-21353-8_4), arXiv: [1504.00586](https://arxiv.org/abs/1504.00586).

### Examples and extensions

- Christopher J. Fewster and Rainer Verch, "Dynamical Locality of the Free Scalar Field," *Annales Henri Poincaré* **13** (2012), 1675–1709. DOI: [10.1007/s00023-012-0166-z](https://doi.org/10.1007/s00023-012-0166-z), arXiv: [1109.6732](https://arxiv.org/abs/1109.6732).
- Ko Sanders, "The Locally Covariant Dirac Field," *Reviews in Mathematical Physics* **22** (2010), 381–430. DOI: [10.1142/S0129055X10003990](https://doi.org/10.1142/S0129055X10003990), arXiv: [0911.1304](https://arxiv.org/abs/0911.1304).
- Marco Benini, "Relative Cauchy Evolution for the Vector Potential on Globally Hyperbolic Spacetimes," *Mathematics and Mechanics of Complex Systems* **3** (2015), 177–210. DOI: [10.2140/memocs.2015.3.177](https://doi.org/10.2140/memocs.2015.3.177), arXiv: [1403.7043](https://arxiv.org/abs/1403.7043).
- Sil Bruinsma, "Relative Cauchy Evolution for Linear Homotopy AQFTs," *Communications in Mathematical Physics* **392** (2022), 621–657. DOI: [10.1007/s00220-022-04352-7](https://doi.org/10.1007/s00220-022-04352-7), arXiv: [2108.10592](https://arxiv.org/abs/2108.10592).

## Version history

- **2026-06-29:** Initial page created.
