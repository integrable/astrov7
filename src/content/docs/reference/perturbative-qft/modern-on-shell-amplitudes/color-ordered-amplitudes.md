---
title: "Color-Ordered Amplitudes"
description: "How fixed cyclic order turns non-Abelian tree amplitudes into planar, gauge-invariant partial amplitudes with simple poles and factorization."
sidebar:
  label: "Color-Ordered Amplitudes"
  order: 4
level: Advanced
status: "Polished draft"
source: "Mangano and Parke; Dixon; Elvang and Huang; Schwartz ch. 27; Srednicki §§72, 80–81."
topics:
  - color-ordered amplitudes
  - partial amplitudes
  - planar amplitudes
  - color decomposition
  - Yang-Mills amplitudes
canonicalTopics:
  - color-ordered-amplitudes
  - planar-partial-amplitudes
  - cyclic-ordering
  - ordered-factorization
  - color-stripped-feynman-rules
researchStatus:
  established:
    - "Tree-level color-ordered amplitudes are standard objects in perturbative Yang–Mills theory and are fixed by the chosen color decomposition convention."
  active:
    - "Modern amplitude research refines color-ordered methods using amplitude relations, color-kinematics duality, generalized unitarity, finite-field reconstruction, and positive-geometry formulations."
---

## Summary

Color-ordered amplitudes are the kinematic pieces that appear after the color algebra of a non-Abelian amplitude has been separated from the momentum and helicity dependence. They are not new observables by themselves. They are carefully normalized partial amplitudes that make cyclic order, planar poles, factorization, and helicity structure visible.

For tree-level pure Yang–Mills amplitudes, a standard trace decomposition is

$$
\mathcal A_n^{\rm tree}
=
g^{n-2}
\sum_{\sigma\in S_n/\mathbb Z_n}
\operatorname{Tr}
\!\left(T^{a_{\sigma(1)}}\cdots T^{a_{\sigma(n)}}\right)
A_n^{\rm tree}(\sigma(1),\ldots,\sigma(n)).
$$

The full amplitude $\mathcal A_n$ carries adjoint color labels. The partial amplitude $A_n(1,\ldots,n)$ has a fixed cyclic order. Its poles occur only when a consecutive set of momenta in that order goes on shell.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 55rem;">

![A color-ordered amplitude has cyclic order and only planar factorization channels](/figures/perturbative-qft/color-ordered-amplitudes.svg)

<figcaption>

A color-ordered amplitude remembers a cyclic ordering of external legs. The allowed poles are planar: they split the cyclic order into two consecutive arcs. Nonadjacent or crossing channels are absent from that particular ordering, though they appear in other partial amplitudes or in the color-dressed sum.

</figcaption>
</figure>

The practical gain is enormous. Instead of manipulating all color factors and all diagrams at once, one computes smaller planar objects and reconstructs the full amplitude afterward. This is the natural language for Parke–Taylor formulas, BCFW recursion, generalized unitarity, planar large-$N$ limits, and many modern gauge-theory amplitude relations.

## Prerequisites

You should know [Color Decomposition](/perturbative-qft/modern-on-shell-amplitudes/color-decomposition/), [Color Factors](/perturbative-qft/gauge-theory-perturbation-theory/color-factors/), [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/), [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/), and [Three-Point Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/three-point-amplitudes/).

## Core idea

A color-ordered amplitude is what remains after the non-Abelian color tensor has fixed a cyclic order. Once the cyclic order is fixed, the amplitude behaves like a planar scattering object drawn on the boundary of a disk:

```txt
full non-Abelian amplitude
  = sum over color tensors × ordered kinematic amplitudes.
```

For $A_n(1,2,\ldots,n)$, the external labels are not just a list. They specify which momenta are adjacent. This adjacency controls the allowed singularities. A factorization channel can occur only when the internal line separates the cyclic order into two consecutive arcs.

For example, in $A_6(1,2,3,4,5,6)$ the invariants

$$
s_{23}=(p_2+p_3)^2,
\qquad
s_{234}=(p_2+p_3+p_4)^2
$$

can appear as poles, while

$$
(p_2+p_4)^2
$$

is not a pole of this ordering. Legs $2$ and $4$ are not adjacent as a set; a pole involving them belongs to another ordering or to the color-dressed sum.

That one fact — poles know the cyclic order — is the heartbeat of color-ordered amplitudes.

## Setup and conventions

We use the scattering and spinor-helicity conventions of the previous pages. All momenta are outgoing. The color-dressed amplitude is denoted $\mathcal A_n$; the ordered partial amplitude is denoted $A_n$.

The precise normalization of $A_n$ depends on the color decomposition. On QFT.org, unless stated otherwise, the generators satisfy

$$
\operatorname{Tr}(T^aT^b)=\frac12\delta^{ab},
\qquad
[T^a,T^b]=if^{abc}T^c.
$$

The coupling $g^{n-2}$ and the overall momentum-conserving delta function are usually stripped from $A_n$. When comparing formulas across books and papers, check whether the author has stripped $i$, $g$, trace-normalization factors, or the delta function. Tiny convention goblins live exactly there.

## Cyclic order and planar poles

The ordered amplitude $A_n(1,2,\ldots,n)$ is associated with a cyclic order, not a linear order. Therefore

$$
A_n(1,2,\ldots,n)=A_n(2,3,\ldots,n,1).
$$

At tree level, the poles of a color-ordered Yang–Mills amplitude are of the form

$$
P_{i\cdots j}^2
=\left(p_i+p_{i+1}+\cdots+p_j\right)^2,
$$

where the labels are consecutive in the chosen cyclic order. The factorization at such a pole is

$$
A_n(1,\ldots,n)
\xrightarrow{P_{i\cdots j}^2\to0}
\sum_h
A_L(\ldots,\widehat P^{-h})
\frac{i}{P_{i\cdots j}^2}
A_R(\widehat P^h,\ldots),
$$

where the two lower-point amplitudes inherit the orderings of the two arcs. The sum runs over physical helicities of the intermediate state.

For instance, in $A_5(1,2,3,4,5)$ a pole in $s_{12}$ has the schematic factorization

$$
A_5(1,2,3,4,5)
\sim
\sum_h
A_3(1,2,-P_{12}^{-h})
\frac{i}{s_{12}}
A_4(P_{12}^h,3,4,5).
$$

There is no pole that would split the ordering into a tangled, crossing diagram. Color ordering has turned general non-Abelian tree diagrams into planar pieces.

## Ordered Feynman rules

Color-ordered amplitudes can be computed using color-stripped Feynman rules. One way to get them is to start from the color-dressed Yang–Mills rules, decompose all products of structure constants into traces, and collect the terms multiplying a chosen cyclic trace.

The result is a planar set of rules:

| Ingredient | Color-ordered interpretation |
|---|---|
| external legs | placed in a fixed cyclic order |
| propagator | ordinary gluon propagator with color removed |
| three-gluon vertex | cyclically ordered Lorentz vertex |
| four-gluon vertex | ordered contact term compatible with the cyclic order |
| internal sums | only planar attachments compatible with the ordering |

Schematic ordered vertices have the same Lorentz structures as the color-dressed vertices but no $f^{abc}$. For a three-gluon ordered vertex, the Lorentz tensor is proportional to

$$
\eta^{\mu_1\mu_2}(p_1-p_2)^{\mu_3}
+
\eta^{\mu_2\mu_3}(p_2-p_3)^{\mu_1}
+
\eta^{\mu_3\mu_1}(p_3-p_1)^{\mu_2},
$$

with all momenta outgoing and with the overall normalization fixed by the trace convention. The point of the ordered rule is not to invent a new theory. It is to compute the coefficient of one chosen color structure directly.

## Four-point example

The ordered amplitude $A_4(1,2,3,4)$ has only the planar channels compatible with the ordering:

$$
A_4(1,2,3,4)
\quad\text{has poles in}\quad
s_{12}\text{ and }s_{23},
$$

but not in

$$
s_{13}=(p_1+p_3)^2.
$$

The $s_{13}$ channel is nonplanar with respect to the order $(1,2,3,4)$. It appears in amplitudes with different cyclic order, such as $A_4(1,3,2,4)$.

This is why color-ordered amplitudes are smaller than color-dressed amplitudes. They do not contain all channels at once. They contain exactly the channels compatible with their ordering.

## Gauge invariance of partial amplitudes

For tree-level pure-gluon amplitudes, the partial amplitudes are gauge invariant in the following practical sense: replacing an external polarization vector by its momentum gives zero,

$$
A_n(\ldots,\varepsilon_i\mapsto p_i,\ldots)=0.
$$

This statement is inherited from gauge invariance of the full color-dressed amplitude, together with the independence of the tree-level color basis. It is one reason color-ordered amplitudes are physically useful objects rather than merely algebraic scraps.

At loop level, the story becomes basis-dependent. Partial amplitudes remain extremely useful, but the precise statement of gauge invariance, primitive amplitudes, trace structures, and color bases requires more care. The safe rule is simple: tree-level color-ordered amplitudes are clean; loop-level color decomposition is still powerful but less innocent.

## Symmetries of ordered amplitudes

Color-ordered tree amplitudes satisfy basic ordering symmetries. Cyclicity gives

$$
A_n(1,2,\ldots,n)=A_n(2,3,\ldots,n,1).
$$

With common Yang–Mills conventions, reflection gives

$$
A_n(1,2,\ldots,n)=(-1)^n A_n(n,n-1,\ldots,1).
$$

There are also deeper linear relations among partial amplitudes. The Kleiss–Kuijf relations reduce the number of independent tree-level partial amplitudes from $(n-1)!$ to $(n-2)!$. The Bern–Carrasco–Johansson relations reduce the independent set further to $(n-3)!$ when the amplitudes can be arranged to satisfy color-kinematics duality.

Those identities are not needed for the first use of color ordering, but they explain why modern amplitude calculations can be shockingly compact. The redundancy is not a bug; it is structure trying to get our attention.

## Parke–Taylor amplitudes

The most famous color-ordered gluon amplitude is the maximally helicity-violating tree amplitude. With two negative-helicity gluons $i,j$ and the rest positive,

$$
A_n^{\rm tree}(1^+,\ldots,i^-,\ldots,j^-,\ldots,n^+)
=
i\frac{\langle ij\rangle^4}
{\langle12\rangle\langle23\rangle\cdots\langle n1\rangle},
$$

up to the overall convention used for $A_n$. The denominator is cyclic. The formula knows the ordering. A different cyclic order has a different denominator.

Several lessons are packed into this one line:

| Feature | Meaning |
|---|---|
| only adjacent brackets in the denominator | planar cyclic order |
| fourth power $\langle ij\rangle^4$ | little-group weights for two negative helicities |
| no reference vectors | gauge-invariant final result |
| compact rational function | huge diagrammatic cancellations have occurred |

The Parke–Taylor formula is often the first moment when students realize that Feynman diagrams are not the only natural language for scattering. A long sum of diagrams can secretly be one small rational function wearing a trench coat.

## Relation to large-N counting

Color ordering is closely related to the large-$N$ expansion. In the trace basis, a single-trace term corresponds to a planar ordering of external gluons. In the ’t Hooft large-$N$ limit with $g^2N$ held fixed, planar contributions dominate many observables.

This is not merely a combinatorial trick. The same planar organization appears in matrix models, Wilson loops, AdS/CFT, integrability, and positive-geometry approaches to amplitudes. Color-ordered amplitudes are one of the most useful entrances into that world because they are still concrete tree-level scattering functions.

## Common pitfalls

**Treating ordered amplitudes as separately measured cross sections.** A detector does not measure $A_n(1,2,\ldots,n)$. Physical probabilities use the color-dressed amplitude, summed and averaged over colors as appropriate.

**Forgetting that the order matters.** $A_5(1,2,3,4,5)$ and $A_5(1,3,2,4,5)$ are different functions. They have different planar poles.

**Putting every Mandelstam pole into one partial amplitude.** A partial amplitude contains only cyclically consecutive channels. The full amplitude contains all channels after all orderings are summed.

**Mixing trace normalizations.** Different papers normalize $T^a$, $g$, and $A_n$ differently. Parke–Taylor-type formulas are stable, but overall factors move around.

**Assuming loop color decomposition is just the tree story again.** At loop level, multi-trace structures, primitive amplitudes, rational terms, and regularization schemes enter. The planar idea survives, but the bookkeeping grows teeth.

## Relations to other pages

- [Color Decomposition](/perturbative-qft/modern-on-shell-amplitudes/color-decomposition/) explains how full amplitudes are expanded into color tensors and partial amplitudes.
- [Color Factors](/perturbative-qft/gauge-theory-perturbation-theory/color-factors/) fixes the group-theory conventions used here.
- [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/) gives the color-dressed vertices that color ordering strips apart.
- [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/) supplies the variables used in compact formulas such as Parke–Taylor.
- [Three-Point Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/three-point-amplitudes/) gives the elementary on-shell building blocks used in factorization and recursion.
- [BCFW Recursion](/perturbative-qft/modern-on-shell-amplitudes/bcfw-recursion/) uses color-ordered amplitudes because their planar pole structure makes the recursion clean.

## Research status

**Established:** Tree-level color ordering, trace decompositions, cyclic partial amplitudes, ordered factorization, and Parke–Taylor amplitudes are standard and heavily checked parts of perturbative gauge theory.

**Active:** Efficient color bases, color-kinematics duality, multi-loop primitive amplitudes, finite-field reconstruction, and planar positive-geometry structures remain active research and computational tools.

**Speculative:** The basic color-ordered tree technology is not speculative. Speculation enters when planar amplitude structures are interpreted as hints of deeper formulations of quantum field theory.

## Exercises

### Exercise 1: Cyclic orderings

How many distinct cyclic orderings of $n$ labeled external gluons appear in the single-trace tree decomposition before using reflection or amplitude relations?

<details>
<summary><strong>Solution</strong></summary>

A linear ordering has $n!$ permutations. A trace is invariant under cyclic rotations, so each cyclic ordering is counted $n$ times in the linear list. Therefore the number of cyclic orderings is

$$
\frac{n!}{n}=(n-1)!.
$$

This is the size of $S_n/\mathbb Z_n$.

</details>

### Exercise 2: Planar poles at four points

List the two-particle poles allowed in $A_4(1,2,3,4)$.

<details>
<summary><strong>Solution</strong></summary>

The cyclic order is

$$
1\to2\to3\to4\to1.
$$

The adjacent two-particle channels are

$$
s_{12}=(p_1+p_2)^2,
\qquad
s_{23}=(p_2+p_3)^2.
$$

Equivalently, $s_{34}=s_{12}$ and $s_{41}=s_{23}$ by momentum conservation for massless four-point kinematics. The nonadjacent pair $1,3$ gives

$$
s_{13}=(p_1+p_3)^2,
$$

which is not a planar pole of $A_4(1,2,3,4)$.

</details>

### Exercise 3: Little-group check of Parke–Taylor

Check the little-group scaling of

$$
A_n(1^-,2^-,3^+,\ldots,n^+)
=
i\frac{\langle12\rangle^4}
{\langle12\rangle\langle23\rangle\cdots\langle n1\rangle}.
$$

<details>
<summary><strong>Solution</strong></summary>

Under little-group scaling,

$$
\lambda_i\mapsto t_i\lambda_i,
\qquad
\tilde\lambda_i\mapsto t_i^{-1}\tilde\lambda_i,
$$

a helicity-$h_i$ amplitude must scale as $t_i^{-2h_i}$.

For leg $1$, the numerator contributes $t_1^4$ through $\langle12\rangle^4$. The denominator contains $\langle12\rangle$ and $\langle n1\rangle$, contributing $t_1^2$. Therefore the amplitude scales as $t_1^2$, which is correct for $h_1=-1$.

The same argument applies to leg $2$. For a positive-helicity leg $k$, the denominator contains two adjacent brackets involving $k$, so the amplitude scales as $t_k^{-2}$, correct for $h_k=+1$.

</details>

### Exercise 4: Reflection at four points

Using the reflection property, relate $A_4(1,2,3,4)$ and $A_4(4,3,2,1)$.

<details>
<summary><strong>Solution</strong></summary>

The reflection identity is

$$
A_n(1,2,\ldots,n)=(-1)^nA_n(n,\ldots,2,1).
$$

For $n=4$, the sign is positive. Hence

$$
A_4(1,2,3,4)=A_4(4,3,2,1).
$$

For odd multiplicity, the reversed ordering would differ by a minus sign in the same convention.

</details>

### Exercise 5: Which ordering contains a pole?

Does the channel $(p_1+p_3)^2=0$ appear as a planar pole of $A_5(1,2,3,4,5)$? Find an ordering where it is planar.

<details>
<summary><strong>Solution</strong></summary>

In $A_5(1,2,3,4,5)$, the set $\{1,3\}$ is not consecutive, so $(p_1+p_3)^2$ is not a planar pole.

One ordering where the channel is planar is

$$
A_5(1,3,2,4,5).
$$

In that ordering, legs $1$ and $3$ are adjacent, so the channel $(p_1+p_3)^2=0$ is compatible with planar factorization.

</details>

## References

- S. J. Parke and T. R. Taylor, “An Amplitude for $n$ Gluon Scattering,” *Physical Review Letters* **56** (1986), for the original compact MHV formula.
- F. A. Berends and W. T. Giele, “Recursive Calculations for Processes with $n$ Gluons,” *Nuclear Physics B* **306** (1988), for recursive ordered-amplitude technology.
- M. L. Mangano and S. J. Parke, “Multiparton Amplitudes in Gauge Theories,” *Physics Reports* **200** (1991), for classic color decomposition and helicity-amplitude methods.
- L. J. Dixon, “Calculating Scattering Amplitudes Efficiently,” in *QCD and Beyond*, for a widely used review of color-ordered amplitudes.
- H. Elvang and Y.-t. Huang, *Scattering Amplitudes in Gauge Theory and Gravity*, for modern spinor-helicity and color-ordered amplitude methods.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 27, for a graduate-level introduction to gluon amplitudes, color ordering, and on-shell recursion.

## Version history

- **2026-06-13:** Initial polished draft for QFT.org, emphasizing cyclic order, planar poles, ordered factorization, Parke–Taylor amplitudes, and links to BCFW recursion.
