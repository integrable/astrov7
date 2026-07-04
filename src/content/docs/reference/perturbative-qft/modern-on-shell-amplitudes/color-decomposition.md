---
title: "Color Decomposition"
description: "How non-Abelian scattering amplitudes separate color algebra from ordered kinematic partial amplitudes."
sidebar:
  label: "Color Decomposition"
  order: 3
level: Advanced
status: "Polished draft"
source: "Mangano and Parke; Dixon; Elvang and Huang; Schwartz ch. 27; Srednicki §§72, 80–81."
topics:
  - color decomposition
  - color-ordered amplitudes
  - trace basis
  - Yang-Mills amplitudes
  - planar amplitudes
canonicalTopics:
  - color-decomposition
  - color-ordered-amplitudes
  - trace-basis
  - partial-amplitudes
  - planar-color-ordering
researchStatus:
  established:
    - "Tree-level color decomposition of Yang–Mills amplitudes into color factors and ordered partial amplitudes is standard perturbative QFT technology."
  active:
    - "Modern work uses refined color bases, color-kinematics duality, multi-loop integrand bases, and amplitude relations to simplify high-multiplicity gauge-theory calculations."
---

## Summary

Color decomposition separates a non-Abelian scattering amplitude into two parts:

```txt
color algebra   ×   ordered kinematics.
```

For a tree-level pure-gluon amplitude, a common trace decomposition is

$$
\mathcal A_n^{\rm tree}
=
g^{n-2}
\sum_{\sigma\in S_n/\mathbb Z_n}
\operatorname{Tr}
\left(T^{a_{\sigma(1)}}\cdots T^{a_{\sigma(n)}}\right)
A_n^{\rm tree}(\sigma(1),\ldots,\sigma(n)).
$$

The full amplitude $\mathcal A_n$ carries adjoint color labels $a_i$. The partial amplitude $A_n$ is a color-stripped object with a fixed cyclic ordering of external legs. It contains poles and factorization channels compatible with that ordering.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 55rem;">

![Color decomposition separates non-Abelian color algebra from ordered kinematics](/figures/perturbative-qft/color-decomposition.svg)

<figcaption>

Color decomposition turns one color-dressed Yang–Mills amplitude into a sum of color structures multiplying ordered partial amplitudes. In trace or quark-line bases, the color tensor fixes an ordering, while the partial amplitude contains the corresponding planar kinematics.

</figcaption>
</figure>

The payoff is conceptual and computational. Gauge-theory amplitudes become smaller, cyclic order becomes visible, spinor-helicity formulas become compact, and large-$N$ counting becomes almost pictorial. Color decomposition is the doorway to color-ordered Feynman rules, Parke–Taylor amplitudes, BCFW recursion, generalized unitarity, and color-kinematics duality.

## Prerequisites

You should know [Color Factors](/perturbative-qft/gauge-theory-perturbation-theory/color-factors/), [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/), [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/), [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/), and [Three-Point Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/three-point-amplitudes/).

## Core idea

Non-Abelian Feynman diagrams entangle two kinds of information:

```txt
1. color:      generators, traces, structure constants, representation indices;
2. kinematics: momenta, helicities, poles, factorization, spinor brackets.
```

Color decomposition untangles them. Instead of treating every diagram as a single object, we expand the full amplitude in a basis of color tensors:

$$
\mathcal A_n=\sum_I C_I A_I.
$$

The $C_I$ are color factors. The $A_I$ are kinematic coefficients, usually called partial amplitudes, primitive amplitudes, or color-ordered amplitudes depending on the basis and loop order.

The key point is not merely aesthetic. Once a cyclic ordering is fixed, the kinematic partial amplitude behaves like a planar amplitude. Its poles are ordered, its factorization channels are restricted, and its spinor-helicity expressions often become dramatically simpler.

## Setup and conventions

We use Hermitian generators $T^a$ in the fundamental representation of $SU(N)$, with the normalization used on the QFT.org color-factor pages:

$$
\operatorname{Tr}(T^aT^b)=\frac12\delta^{ab},
\qquad
[T^a,T^b]=if^{abc}T^c.
$$

Many amplitude papers use rescaled generators. That changes numerical factors in the decomposition but not the separation into color structures and partial amplitudes.

All external momenta are outgoing. The symbol $\mathcal A_n$ denotes a color-dressed amplitude. The symbol $A_n$ denotes a color-stripped ordered amplitude.

## Why color can be separated

The Yang–Mills interaction vertices carry color factors. The three-gluon vertex contains $f^{abc}$, and the four-gluon vertex contains products of structure constants. Matter-gluon vertices contain fundamental generators $T^a$.

The color algebra is independent of the momenta and polarizations. A typical diagram contributes

$$
\text{diagram}
= C_{\Gamma}\,K_{\Gamma},
$$

where $C_\Gamma$ is a product of $f^{abc}$ and generators, while $K_\Gamma$ is the Lorentz and momentum-dependent part. Summing diagrams gives

$$
\mathcal A_n
=\sum_{\Gamma}C_{\Gamma}K_{\Gamma}.
$$

The nontrivial step is choosing a useful color basis and collecting all diagrams with the same basis color tensor. That collection defines the partial amplitudes.

## Trace basis for gluon tree amplitudes

At tree level, pure-gluon amplitudes can be expanded in single traces. One common convention is

$$
\mathcal A_n^{\rm tree}(1,2,\ldots,n)
=
g^{n-2}
\sum_{\sigma\in S_n/\mathbb Z_n}
\operatorname{Tr}
\left(T^{a_{\sigma(1)}}\cdots T^{a_{\sigma(n)}}\right)
A_n^{\rm tree}(\sigma(1),\ldots,\sigma(n)).
$$

The quotient $S_n/\mathbb Z_n$ means that cyclic rotations of the same trace are not counted separately. The trace factor is cyclic:

$$
\operatorname{Tr}(T^{a_1}T^{a_2}\cdots T^{a_n})
=
\operatorname{Tr}(T^{a_2}\cdots T^{a_n}T^{a_1}).
$$

Therefore the corresponding partial amplitude is also cyclic:

$$
A_n(1,2,\ldots,n)=A_n(2,3,\ldots,n,1).
$$

For pure-gluon tree amplitudes, the ordered amplitude also obeys the reflection relation

$$
A_n(1,2,\ldots,n)=(-1)^n A_n(n,n-1,\ldots,1),
$$

in standard color-ordered conventions. This relation is a useful check on calculations.

## From structure constants to traces

The trace basis is closely related to the structure-constant basis. With the generator normalization above,

$$
f^{abc}=-2i\,\operatorname{Tr}([T^a,T^b]T^c).
$$

Thus every cubic-graph color factor built from $f^{abc}$ can be rewritten as a sum of traces. At tree level, the result reduces to single traces. At loop level, multi-trace structures can appear.

For example, the three-gluon color factor can be written as

$$
f^{a_1a_2a_3}
=-2i\left[
\operatorname{Tr}(T^{a_1}T^{a_2}T^{a_3})
-
\operatorname{Tr}(T^{a_2}T^{a_1}T^{a_3})
\right].
$$

The two traces correspond to the two cyclic orientations of the ordered three-point amplitude.

## Ordered poles and planar diagrams

A color-ordered amplitude $A_n(1,2,\ldots,n)$ only has poles in sums of adjacent momenta. For example, at four points,

$$
A_4(1,2,3,4)
$$

can have poles in

$$
s_{12}=(p_1+p_2)^2,
\qquad
s_{23}=(p_2+p_3)^2,
$$

but not in $s_{13}$ as an independent ordered channel. The missing channel appears in a different ordering.

This is the planar meaning of color ordering. If the external legs are placed around a circle in the order $(1,2,\ldots,n)$, the allowed factorization channels are those that split the circle into two consecutive arcs.

This ordered-pole property is why color-ordered amplitudes are so useful in recursion. Factorization becomes combinatorially cleaner.

## Color-ordered Feynman rules

Instead of computing the full color-dressed amplitude and decomposing it afterward, one can compute partial amplitudes directly using color-ordered Feynman rules.

For pure Yang–Mills, the rule of thumb is:

```txt
Draw only planar diagrams compatible with the chosen cyclic ordering.
Use color-stripped ordered vertices.
Sum only the ordered channels.
```

The resulting object is $A_n(1,2,\ldots,n)$. The color trace is attached later.

For example, the ordered four-gluon amplitude $A_4(1,2,3,4)$ receives contributions from the ordered $s_{12}$ and $s_{23}$ cubic channels, plus the ordered four-gluon contact term. The crossed channel belongs to another partial amplitude.

This is not a different theory. It is a basis choice in the same gauge theory.

## Quark amplitudes

With one quark-antiquark pair and $n-2$ gluons, the natural color basis is an open string of generators:

$$
\mathcal A_n^{\rm tree}(1_{\bar q},2_q,3,\ldots,n)
=
g^{n-2}
\sum_{\sigma\in S_{n-2}}
\left(T^{a_{\sigma(3)}}\cdots T^{a_{\sigma(n)}}\right)_{i_2}^{\ \bar i_1}
A_n^{\rm tree}(1_{\bar q},2_q,\sigma(3),\ldots,\sigma(n)).
$$

The color line begins on the quark, passes through the ordered gluon insertions, and ends on the antiquark. This is the open-string analogue of the cyclic trace used for gluons.

With multiple quark lines, the color basis becomes larger. One must track which gluons attach to which fundamental color line and how different quark lines are connected.

## Color-flow basis

The trace basis is not the only useful basis. In the color-flow basis, an adjoint gluon is represented as a pair of fundamental color lines. This uses the completeness identity

$$
\sum_a (T^a)_i^{\ j}(T^a)_k^{\ l}
=
\frac12\left(\delta_i^{\ l}\delta_k^{\ j}
-\frac1N\delta_i^{\ j}\delta_k^{\ l}\right).
$$

At large $N$, the first term dominates and gluons behave like double lines. This makes the topology of color factors visible: planar diagrams dominate, and nonplanar diagrams are suppressed by powers of $1/N$.

Color flow is especially useful in collider calculations and parton-shower algorithms, where color connections influence radiation patterns and hadronization models.

## DDM basis

Another important tree-level basis is the Del Duca–Dixon–Maltoni, or DDM, basis. It fixes two external legs, say $1$ and $n$, and expands the amplitude in chains of structure constants:

$$
\mathcal A_n^{\rm tree}
=
g^{n-2}
\sum_{\sigma\in S_{n-2}}
C(1,\sigma,n)
A_n^{\rm tree}(1,\sigma(2),\ldots,\sigma(n-1),n),
$$

where $C(1,\sigma,n)$ is a nested product of structure constants. Schematically,

$$
C(1,2,\ldots,n)
\sim
f^{a_1a_2b_1}f^{b_1a_3b_2}\cdots f^{b_{n-3}a_{n-1}a_n}.
$$

This basis makes the Jacobi identity central and reduces redundancy compared with the full trace basis. It is a natural bridge to color-kinematics duality.

## Amplitude relations

Color decomposition reveals relations among partial amplitudes. The simplest are cyclicity and reflection. Less trivial are photon-decoupling and Kleiss–Kuijf relations.

The photon-decoupling identity follows from replacing one generator by the identity in a $U(N)$-style trace decomposition. Since a colorless photon has no non-Abelian self-interaction, the sum of ordered amplitudes with that leg inserted in all cyclic positions vanishes. A typical form is

$$
\sum_{i=2}^{n}
A_n(2,3,\ldots,i-1,1,i,\ldots,n)=0.
$$

Kleiss–Kuijf relations reduce the number of independent tree-level partial amplitudes further. BCJ relations, which use color-kinematics duality, reduce the basis even more.

The hierarchy is often summarized as:

| Level | Number of independent tree partial amplitudes |
|---|---:|
| cyclic and reflection | roughly $(n-1)!/2$ |
| Kleiss–Kuijf | $(n-2)!$ |
| BCJ | $(n-3)!$ |

The last step uses more than color algebra; it uses a kinematic counterpart of the Jacobi identity.

## Loops and multi-trace structures

At loop level, color decomposition remains useful but becomes richer. Pure-gluon loop amplitudes contain single-trace and multi-trace structures:

$$
\operatorname{Tr}(T^{a_1}\cdots T^{a_n}),
\qquad
\operatorname{Tr}(T^{a_1}\cdots T^{a_r})
\operatorname{Tr}(T^{a_{r+1}}\cdots T^{a_n}),
\qquad \ldots
$$

The leading-color terms at large $N$ are single-trace planar contributions. Subleading-color terms involve multi-trace or nonplanar structures.

Loop-level partial amplitudes also depend on which particles circulate in the loop and on the chosen primitive-amplitude basis. The clean tree-level story survives, but the bookkeeping becomes more delicate.

## Example: the four-gluon MHV amplitude

In color-ordered Yang–Mills, the four-gluon MHV amplitude is

$$
A_4(1^-,2^-,3^+,4^+)
=
\frac{\langle12\rangle^4}
{\langle12\rangle\langle23\rangle\langle34\rangle\langle41\rangle},
$$

up to the convention-dependent overall factor. The corresponding color-dressed contribution is obtained by summing this partial amplitude over cyclic orderings with trace factors:

$$
\mathcal A_4^{\rm tree}
=
g^2\sum_{\sigma\in S_4/\mathbb Z_4}
\operatorname{Tr}(T^{a_{\sigma(1)}}T^{a_{\sigma(2)}}T^{a_{\sigma(3)}}T^{a_{\sigma(4)}})
A_4(\sigma(1),\sigma(2),\sigma(3),\sigma(4)).
$$

The compact Parke–Taylor denominator is not an accident. It knows the cyclic order. If you change the order, you change which adjacent brackets appear.

## Why color decomposition matters

Color decomposition is useful because it turns a large non-Abelian problem into smaller structured problems.

| Use | What color decomposition buys |
|---|---|
| spinor-helicity formulas | compact color-ordered expressions |
| recursion | ordered factorization channels |
| unitarity cuts | simpler sewing of partial amplitudes |
| large-$N$ expansion | planar topology becomes visible |
| collider calculations | color-summed squared amplitudes can be organized systematically |
| double copy | color factors can be compared with kinematic numerators |

The moral is simple: non-Abelian color is not just an extra index. It reorganizes the geometry of perturbation theory.

## Common pitfalls

**Calling a partial amplitude the full amplitude.** A color-ordered amplitude is only the kinematic coefficient of a color tensor. The full color-dressed amplitude requires the sum over color structures.

**Forgetting generator normalization.** Trace decompositions differ by factors of $2$, $\sqrt2$, or $i$ across the literature. Always check $\operatorname{Tr}(T^aT^b)$.

**Adding forbidden ordered channels.** $A_n(1,2,\ldots,n)$ only has poles compatible with the cyclic order. Nonadjacent channels belong to other orderings.

**Assuming the trace basis is minimal.** It is convenient but redundant. DDM and BCJ bases are smaller at tree level.

**Using tree-level intuition at loops without modification.** Loops introduce multi-trace structures, primitive amplitudes, and subtleties involving particles in the loop.

**Confusing color ordering with physical time ordering.** The cyclic order is an ordering of external color insertions in a planar diagram, not an ordering in time.

## Relations to other pages

- [Color Factors](/perturbative-qft/gauge-theory-perturbation-theory/color-factors/) gives the group-theory identities used here.
- [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/) shows where $f^{abc}$ and generator factors enter diagrammatic perturbation theory.
- [Three-Point Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/three-point-amplitudes/) gives the color-stripped three-point kinematic seeds.
- [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/) explains the bracket notation used in compact partial amplitudes.
- [Non-Abelian Tree Amplitudes](/perturbative-qft/tree-level-scattering/non-abelian-tree-amplitudes/) gives the traditional color-dressed perspective.
- Later pages on color-ordered amplitudes, BCFW recursion, generalized unitarity, and double copy build directly on this separation of color and kinematics.

## Research status

- **Established:** Trace, color-flow, and structure-constant decompositions are standard tools for tree-level and loop-level gauge-theory amplitudes. Color-ordered partial amplitudes are central in analytic and numerical perturbative QCD.
- **Active:** Efficient color bases, loop-level primitive amplitudes, color-kinematics duality, finite-field reconstruction, and high-multiplicity QCD calculations remain active research and software-development areas.
- **Speculative:** Basic color decomposition is not speculative. Some broader conjectures relating color and kinematics, especially beyond standard perturbative settings, remain active research topics.

## Exercises

### Exercise 1: Rewrite a structure constant as traces

Using

$$
[T^a,T^b]=if^{abc}T^c,
\qquad
\operatorname{Tr}(T^aT^b)=\frac12\delta^{ab},
$$

show that

$$
f^{abc}=-2i\operatorname{Tr}([T^a,T^b]T^c).
$$

<details>
<summary><strong>Solution</strong></summary>

Start from the commutator:

$$
[T^a,T^b]=if^{abd}T^d.
$$

Multiply by $T^c$ and take the trace:

$$
\operatorname{Tr}([T^a,T^b]T^c)
=if^{abd}\operatorname{Tr}(T^dT^c).
$$

Using the normalization,

$$
\operatorname{Tr}(T^dT^c)=\frac12\delta^{dc},
$$

so

$$
\operatorname{Tr}([T^a,T^b]T^c)=\frac{i}{2}f^{abc}.
$$

Multiplying by $-2i$ gives

$$
-2i\operatorname{Tr}([T^a,T^b]T^c)=f^{abc}.
$$

</details>

### Exercise 2: Cyclicity of partial amplitudes

Explain why the trace decomposition naturally pairs cyclic trace factors with cyclic partial amplitudes.

<details>
<summary><strong>Solution</strong></summary>

The trace satisfies

$$
\operatorname{Tr}(T^{a_1}T^{a_2}\cdots T^{a_n})
=
\operatorname{Tr}(T^{a_2}\cdots T^{a_n}T^{a_1}).
$$

Therefore the color tensor does not distinguish cyclic rotations of the labels. To avoid overcounting the same color structure, the sum is over $S_n/\mathbb Z_n$ rather than all of $S_n$.

The kinematic coefficient multiplying that trace is correspondingly labeled by a cyclic order rather than by a linearly ordered list. Hence

$$
A_n(1,2,\ldots,n)=A_n(2,\ldots,n,1).
$$

</details>

### Exercise 3: Ordered channels at four points

For the partial amplitude $A_4(1,2,3,4)$, identify the adjacent two-particle channels.

<details>
<summary><strong>Solution</strong></summary>

Place the labels around a circle in the order $1,2,3,4$. The allowed two-particle factorization channels split the circle into consecutive arcs. The adjacent pairs are

$$
(1,2)
\qquad\text{and}\qquad
(2,3),
$$

up to the complementary pairs $(3,4)$ and $(4,1)$, which carry the same momentum invariants by momentum conservation. Thus the ordered amplitude has poles in

$$
s_{12}
\qquad\text{and}\qquad
s_{23},
$$

not an independent pole in $s_{13}$.

</details>

### Exercise 4: Color flow completeness relation

Use the completeness relation

$$
\sum_a (T^a)_i^{\ j}(T^a)_k^{\ l}
=
\frac12\left(\delta_i^{\ l}\delta_k^{\ j}
-\frac1N\delta_i^{\ j}\delta_k^{\ l}\right)
$$

to explain why planar color flow dominates at large $N$.

<details>
<summary><strong>Solution</strong></summary>

The first term,

$$
\frac12\delta_i^{\ l}\delta_k^{\ j},
$$

connects fundamental color lines across the propagator. This is the double-line color-flow term.

The second term,

$$
-\frac{1}{2N}\delta_i^{\ j}\delta_k^{\ l},
$$

is suppressed by $1/N$. Therefore, in the large-$N$ limit, the leading color structures are those obtained by keeping the double-line connections. Their topology is planar at leading order, while nonplanar or trace-splitting effects are suppressed by powers of $1/N$.

</details>

### Exercise 5: Color-dressed four-point MHV amplitude

Write the trace-decomposition expression for the color-dressed amplitude whose partial amplitude includes

$$
A_4(1^-,2^-,3^+,4^+)
=
\frac{\langle12\rangle^4}
{\langle12\rangle\langle23\rangle\langle34\rangle\langle41\rangle}.
$$

<details>
<summary><strong>Solution</strong></summary>

The color-dressed tree amplitude is obtained by summing the ordered partial amplitude over cyclically inequivalent permutations:

$$
\mathcal A_4^{\rm tree}
=
g^2
\sum_{\sigma\in S_4/\mathbb Z_4}
\operatorname{Tr}
\left(T^{a_{\sigma(1)}}T^{a_{\sigma(2)}}T^{a_{\sigma(3)}}T^{a_{\sigma(4)}}\right)
A_4^{\rm tree}
(\sigma(1),\sigma(2),\sigma(3),\sigma(4)).
$$

The helicities move with the labels. For each ordering, the corresponding Parke–Taylor denominator uses adjacent brackets in that ordering.

</details>

## References

- M. L. Mangano and S. J. Parke, “Multiparton Amplitudes in Gauge Theories,” for color decompositions, partial amplitudes, and spinor-helicity technology.
- L. J. Dixon, “Calculating Scattering Amplitudes Efficiently,” for a classic review of color ordering and amplitude methods.
- V. Del Duca, L. Dixon, and F. Maltoni, “New Color Decompositions for Gauge Amplitudes at Tree and Loop Level,” for the DDM basis.
- Z. Bern, J. J. Carrasco, and H. Johansson, “New Relations for Gauge-Theory Amplitudes,” for color-kinematics duality and BCJ relations.
- H. Elvang and Y.-t. Huang, *Scattering Amplitudes in Gauge Theory and Gravity*, for a modern on-shell treatment.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 27, especially the color-ordering discussion.
- M. Srednicki, *Quantum Field Theory*, §§72 and 80–81, for non-Abelian Feynman rules, matrix-field notation, and QCD scattering.

## Version history

- **2026-06-13:** Initial polished page. Introduces trace, color-flow, and DDM decompositions; explains color-ordered partial amplitudes, ordered poles, quark color strings, large-$N$ color flow, and basic amplitude relations.
