---
title: "Symmetry Factors"
description: "How to compute graph symmetry factors in perturbative QFT from Wick contractions, automorphisms, scalar examples, and practical counting checks."
sidebar:
  label: "Symmetry Factors"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§9–10 and §19; Coleman 2019, chs. 8 and 10; Weinberg 1995, Vol. I, §6.1; Schwartz 2014, ch. 7; Zee 2010, app. C; Zinn-Justin 2021, ch. 7"
topics:
  - symmetry factors
  - Wick contractions
  - Feynman diagrams
  - scalar perturbation theory
  - graph automorphisms
  - vacuum bubbles
canonicalTopics:
  - symmetry-factors
  - diagram-automorphisms
  - wick-counting
researchStatus:
  established:
    - "Symmetry factors for perturbative diagrams are standard combinatorial factors obtained by grouping Wick contractions into unlabeled Feynman graphs."
  active:
    - "Automated diagram generation, graph isomorphism, gauge-theory bookkeeping, and multi-loop integral organization are active computational subjects, but the basic combinatorics explained here is settled."
---

## Summary

A symmetry factor is the leftover combinatorial divisor attached to a Feynman diagram after the factorials in the Dyson expansion and the interaction Lagrangian have canceled most Wick-contraction overcounting.

For a scalar theory with interactions written as

$$
\mathcal L_{\mathrm{int}}
=-\sum_r \frac{g_r}{r!}\phi^r,
$$

the standard position-space contribution of a diagram $\Gamma$ has the schematic form

$$
G_\Gamma
=
\frac{1}{S_\Gamma}
\left(\prod_{v\in\Gamma}-ig_{r_v}\int d^4z_v\right)
\left(\prod_{\ell\in\Gamma}D_F(x_{\ell,1}-x_{\ell,2})\right),
$$

where $S_\Gamma$ is the symmetry factor. With labeled external insertions fixed, $S_\Gamma$ is the order of the graph automorphism group:

$$
S_\Gamma=|\operatorname{Aut}(\Gamma)|.
$$

This page explains what that statement means, how to compute $S_\Gamma$ by Wick counting or by graph symmetries, and how to avoid confusing graph symmetry factors with identical-particle factors, fermion signs, or loop-integration conventions.

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Perturbative Expansion](/perturbative-qft/diagrammatics-feynman-rules/perturbative-expansion/), [Wick Theorem Recap](/perturbative-qft/diagrammatics-feynman-rules/wick-theorem-recap/), and [Generating Functional Diagrams](/perturbative-qft/diagrammatics-feynman-rules/generating-functional-diagrams/). The Foundations page [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) gives the first diagrammatic examples.

## Core idea

The Dyson–Wick expansion labels too much. It labels the order of identical interaction insertions, the individual fields inside each interaction monomial, and the individual contractions. A drawn Feynman graph forgets those artificial labels. The symmetry factor divides by the number of artificial relabelings that produce the same drawn graph.

A good mental model is:

| Object | What is overcounted? | What fixes it? |
|---|---|---|
| Dyson expansion | identical vertex insertion order | $1/V!$ |
| Interaction $\phi^r/r!$ | identical fields at one vertex | $1/r!$ |
| Unlabeled graph | relabelings that leave the graph unchanged | $1/S_\Gamma$ |

The first two factorials are already built into the usual vertex rule. The symmetry factor is whatever remains after those cancellations.

<figure class="doc-figure" style="--figure-width: 44rem; --caption-width: 52rem;">

![Four scalar diagrams with symmetry factors: contact, tadpole, one-loop four-point bubble, and vacuum figure-eight](/figures/perturbative-qft/symmetry-factor-examples.svg)

<figcaption>

Some basic scalar symmetry factors with labeled external insertions fixed. The contact graph has no nontrivial graph symmetry, the tadpole and one-loop four-point bubble each have a factor $2$, and the one-vertex vacuum figure-eight has factor $8$.

</figcaption>
</figure>

## Setup and conventions

We work in flat four-dimensional Minkowski spacetime with qft.org conventions. The main examples use real scalar $\phi^4$ theory,

$$
\mathcal L
=
\frac12\partial_\mu\phi\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\lambda}{4!}\phi^4.
$$

At order $V$ in $\lambda$, the Dyson expansion contributes

$$
\frac{1}{V!}\left(-\frac{i\lambda}{4!}\right)^V
\int d^4z_1\cdots d^4z_V\,
T\{\phi(z_1)^4\cdots\phi(z_V)^4\}.
$$

Wick's theorem then pairs fields. Several different Wick pairings can produce the same drawn graph. The coefficient of the graph is found by multiplying the expansion factor above by the number of Wick contractions that produce that graph.

Equivalently, once the ordinary vertex factor $-i\lambda$ has been adopted, the remaining coefficient is $1/S_\Gamma$.

## Two equivalent definitions

There are two reliable definitions of the symmetry factor.

### Wick-counting definition

For a fixed diagram $\Gamma$, compute

$$
\text{coefficient of }\Gamma
=
\frac{1}{V!}\prod_v\frac{1}{r_v!}\times
N_{\mathrm{Wick}}(\Gamma),
$$

where $N_{\mathrm{Wick}}(\Gamma)$ is the number of Wick contractions producing that graph with the chosen external labels. If the vertex factors are written as $-ig_{r_v}$, the remaining coefficient is $1/S_\Gamma$.

This definition is slow but nearly foolproof. When a diagram is confusing, go back to Wick counting. It is the source code.

### Automorphism definition

With standard $\phi^r/r!$ interaction normalizations, $S_\Gamma$ is the number of graph automorphisms that leave the diagram unchanged while keeping external labels fixed and preserving vertex types.

An automorphism may include:

1. permutations of identical internal vertices;
2. swaps of identical internal lines connecting the same vertices;
3. flips of tadpole lines whose two ends meet the same vertex;
4. permutations of identical disconnected vacuum components.

External labels are not moved when computing a Green-function symmetry factor. If the external points are $x_1,x_2,x_3,x_4$, then exchanging $x_1$ with $x_2$ is not a graph automorphism unless the calculation has explicitly declared those labels indistinguishable.

## Scalar examples

### Four-point contact graph

At first order in $\lambda$, the connected four-point function contains

$$
\frac{-i\lambda}{4!}\int d^4z\,
\langle0|T\{\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\phi(z)^4\}|0\rangle_0.
$$

For the contact graph, the four fields at $z$ are contracted with the four external insertions. There are $4!$ such contractions, so

$$
\frac{-i\lambda}{4!}\times4!=-i\lambda.
$$

Thus

$$
S_\Gamma=1.
$$

No nontrivial relabeling of the internal graph leaves all four external labels fixed.

### Two-point tadpole graph

At first order, the tadpole contribution to the two-point function is

$$
\frac{-i\lambda}{4!}\int d^4z\,
\langle0|T\{\phi(x)\phi(y)\phi(z)^4\}|0\rangle_0.
$$

Choose a field at $z$ to contract with $\phi(x)$: $4$ choices. Choose a field at $z$ to contract with $\phi(y)$: $3$ choices. The two remaining fields at $z$ contract with each other. Hence

$$
N_{\mathrm{Wick}}=4\cdot3=12.
$$

Therefore

$$
\frac{-i\lambda}{4!}\times12=\frac{-i\lambda}{2},
$$

and

$$
G_2^{\mathrm{tad}}(x,y)
=
\frac{-i\lambda}{2}\int d^4z\,
D_F(x-z)D_F(y-z)D_F(0).
$$

The symmetry factor is

$$
S_\Gamma=2.
$$

In the automorphism language, the factor $2$ is the flip of the tadpole line: its two ends are attached to the same vertex, so interchanging those two half-edges changes no drawn graph.

### One-loop four-point bubble

At second order in $\phi^4$ theory, one connected four-point graph has two quartic vertices connected by two internal lines. One channel has the position-space structure

$$
D_F(x_1-z)D_F(x_2-z)D_F(z-w)^2D_F(w-x_3)D_F(w-x_4),
$$

plus the other assignments of the external points.

For this channel, the coefficient is

$$
\frac{(-i\lambda)^2}{2}
\int d^4z\,d^4w\,
D_F(x_1-z)D_F(x_2-z)D_F(z-w)^2D_F(w-x_3)D_F(w-x_4).
$$

Thus $S_\Gamma=2$. In the automorphism language, the two internal lines connecting $z$ and $w$ can be swapped. The external labels prevent a further exchange of the two vertices in this particular labeled channel.

A fast Wick-count check gives the same answer. The two external points on the left can be attached to one vertex and the two on the right to the other vertex, with either assignment of the two integration variables $z,w$. For each such assignment there are $4\cdot3$ choices at one vertex, $4\cdot3$ choices at the other, and $2!$ ways to pair the remaining fields across the two vertices. Hence

$$
N_{\mathrm{Wick}}
=2\,(4\cdot3)(4\cdot3)2!=576.
$$

The expansion denominator is

$$
2!(4!)^2=1152,
$$

so the leftover coefficient is $576/1152=1/2$.

### Vacuum figure-eight graph

The first-order vacuum bubble in $\phi^4$ theory is

$$
\frac{-i\lambda}{4!}\int d^4z\,
\langle0|T\{\phi(z)^4\}|0\rangle_0.
$$

The four fields can be paired in three ways, so

$$
\frac{-i\lambda}{4!}\times3
=
\frac{-i\lambda}{8}.
$$

Thus the one-vertex figure-eight vacuum graph has

$$
S_\Gamma=8.
$$

The automorphism group has order $8$: each of the two tadpole loops can be flipped, and the two identical loops can be exchanged.

## Practical counting workflow

For scalar diagrams with interactions normalized as $\phi^r/r!$, use this workflow.

1. **Fix what is labeled.** External operator insertions in a Green function are labeled. External particles in an amplitude are usually labeled by momenta and species until phase-space symmetrization is performed.
2. **Draw one graph topology.** Keep vertex types and field species visible.
3. **Find automorphisms.** Count relabelings of internal vertices, internal lines, and half-edges that leave the graph unchanged with external labels fixed.
4. **Separate other factors.** Fermion-loop signs, color factors, spin sums, counterterms, and identical-particle phase-space factors are not graph symmetry factors.
5. **Check with Wick counting when unsure.** The expansion coefficient times the number of Wick contractions must match $1/S_\Gamma$ times the ordinary product of vertex factors.

A compact reference table for common $\phi^4$ diagrams is:

| Diagram | External labels fixed? | Symmetry factor |
|---|---:|---:|
| four-point contact | yes | $1$ |
| two-point tadpole | yes | $2$ |
| one-loop four-point bubble, one channel | yes | $2$ |
| one-vertex vacuum figure-eight | no external labels | $8$ |
| disconnected product of two identical vacuum bubbles | no external labels | extra $2!$ for exchanging components |

## What symmetry factors are not

A graph symmetry factor is not the same as an identical-particle factor in a cross section. If a final state contains two identical particles, the phase-space integral may include a factor $1/2!$ to avoid double-counting the same final state. That is a property of final-state counting, not of Wick contractions inside a diagram.

A symmetry factor is also not a fermion sign. Closed fermion loops produce a factor of $-1$, and reordering external fermion operators can produce additional signs. Those signs multiply the graph contribution separately.

A symmetry factor is also not a gauge factor. Color traces, group generators, Lorentz-index contractions, ghost signs, and gauge-parameter dependence belong to the field content and vertices. They do not replace the graph automorphism count.

## Common pitfalls

**Moving external labels.** In ordinary Green functions, $x_1,x_2,\ldots$ are labels. A permutation that swaps external labels is not part of the symmetry factor unless the observable explicitly identifies those labels.

**Counting identical final-state factors as graph symmetry factors.** A factor such as $1/2!$ in phase space for two identical final particles is not a diagram symmetry factor. It belongs to the observable definition, not the perturbative Wick expansion.

**Forgetting tadpole flips.** A line that begins and ends at the same vertex often contributes a factor of $2$ to the automorphism group. This is why the $\phi^4$ two-point tadpole has $S_\Gamma=2$.

**Dropping the Dyson factor.** At order $V$, the expansion contains $1/V!$. If you do Wick counting directly, include this factor before comparing with the diagrammatic symmetry factor.

**Mixing up connectedness and symmetry.** A disconnected diagram may have a symmetry factor, but connectedness is a different question. The logarithm of the generating functional removes disconnected products; it does not change the automorphism factor of a connected component.

## Relations to other pages

- [Wick Theorem Recap](/perturbative-qft/diagrammatics-feynman-rules/wick-theorem-recap/) gives the pairing formula whose overcounting produces symmetry factors.
- [Generating Functional Diagrams](/perturbative-qft/diagrammatics-feynman-rules/generating-functional-diagrams/) explains how the same combinatorics is packaged by source derivatives.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) uses symmetry factors as part of the final momentum-space diagram value.
- [Connected Diagrams](/foundations/interactions-and-wick-expansion/connected-diagrams/) explains the connected-disconnected distinction that is separate from graph automorphisms.
- [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/) introduces one-particle-irreducible diagrams, where symmetry factors remain essential.
- [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/) gives the first scalar vertices from which these examples are built.

## Research status

The symmetry-factor rules on this page are settled textbook combinatorics for ordinary perturbative QFT. In practical research, the difficulty is rarely the definition; it is bookkeeping in large theories with many fields, counterterms, gauge redundancies, color structures, and multi-loop topologies. Automated diagram generators implement these same ideas together with graph-isomorphism algorithms and theory-specific algebra.

## Exercises

### Exercise 1: Contact graph

In $\phi^4$ theory, compute the symmetry factor for the first-order connected four-point contact graph with external labels $x_1,x_2,x_3,x_4$ fixed.

<details>
<summary><strong>Solution</strong></summary>

The first-order term is

$$
\frac{-i\lambda}{4!}\int d^4z\,
\langle0|T\{\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\phi(z)^4\}|0\rangle_0.
$$

The four fields at $z$ can be attached to the four labeled external insertions in $4!$ ways. This cancels the $1/4!$ in the interaction. The coefficient is $-i\lambda$, so $S_\Gamma=1$.

</details>

### Exercise 2: Tadpole factor

Derive the factor $1/2$ in the two-point tadpole graph of $\phi^4$ theory by explicit Wick counting.

<details>
<summary><strong>Solution</strong></summary>

Choose which field at the vertex contracts with $\phi(x)$: $4$ choices. Choose which remaining field contracts with $\phi(y)$: $3$ choices. The two leftover fields at the vertex contract with each other. Thus there are $12$ Wick contractions.

The expansion coefficient is $(-i\lambda)/4!$, so

$$
\frac{-i\lambda}{4!}\times12=\frac{-i\lambda}{2}.
$$

Therefore the symmetry factor is $S_\Gamma=2$.

</details>

### Exercise 3: One-loop four-point bubble

For the one-loop four-point bubble in $\phi^4$ theory, verify that a fixed channel has symmetry factor $2$.

<details>
<summary><strong>Solution</strong></summary>

At second order the expansion denominator is $2!(4!)^2$. For the fixed channel, either integration variable can be the vertex attached to $x_1,x_2$, giving a factor $2$. At that vertex there are $4\cdot3$ choices for the external attachments. At the other vertex there are also $4\cdot3$ choices. The remaining two fields at each vertex can be paired across the vertices in $2!$ ways.

Thus

$$
N_{\mathrm{Wick}}=2(4\cdot3)(4\cdot3)2!=576.
$$

Since

$$
2!(4!)^2=1152,
$$

the leftover coefficient is $576/1152=1/2$. Hence $S_\Gamma=2$.

</details>

### Exercise 4: Vacuum figure-eight

Compute the symmetry factor of the one-vertex vacuum bubble in $\phi^4$ theory.

<details>
<summary><strong>Solution</strong></summary>

The first-order vacuum term is

$$
\frac{-i\lambda}{4!}\int d^4z\,\langle0|T\{\phi(z)^4\}|0\rangle_0.
$$

The four fields at the vertex can be paired in

$$
3=(4-1)!!
$$

ways. Therefore the coefficient is

$$
\frac{-i\lambda}{4!}\times3=\frac{-i\lambda}{8}.
$$

The graph has symmetry factor $S_\Gamma=8$.

</details>

### Exercise 5: Identical final particles

Why is the $1/2!$ for two identical final-state particles in a cross section not the same thing as the symmetry factor of a Feynman diagram?

<details>
<summary><strong>Solution</strong></summary>

A diagram symmetry factor comes from grouping Wick contractions into one graph. It is determined before integrating over final-state phase space. The identical-particle factor in a cross section removes overcounting in the final-state phase-space integral, where swapping the two identical measured momenta labels the same physical final state. The two factors can both appear in one calculation, but they have different origins.

</details>

## References

### Standard first pass

- Mark Srednicki, *Quantum Field Theory*, especially the sections on interacting scalar field theory, scattering amplitudes, and perturbation theory to all orders.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 8 and 10, for Wick diagrams, Feynman diagrams, and diagrammatic counting in early perturbation theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 7, for Lagrangian and Hamiltonian derivations of Feynman rules and symmetry-factor examples.

### Deeper references

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, §6.1, for the general derivation of Feynman rules and combinatoric factors.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, ch. 7, for functional methods, connected diagrams, and vertex functionals.
- A. Zee, *Quantum Field Theory in a Nutshell*, app. C, for a compact diagrammatic rule summary.

## Version history

- **2026-06-11:** Initial standardized page.
