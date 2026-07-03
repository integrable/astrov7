---
title: "Connected Diagrams"
description: "Connected and disconnected diagrams in perturbation theory: vacuum-bubble cancellation, diagram exponentiation, W[J] as the connected generator, and the bridge to 1PI effective actions."
sidebar:
  label: "Connected Diagrams"
  order: 6
---

## Summary

Perturbation theory produces many diagrams that factor into independent pieces. Some pieces are completely disconnected from the operator insertions; these are **vacuum bubbles**. Other pieces attach to external insertions but split into several independent components. Both kinds are important, but they are removed in different ways.

The normalized time-ordered Green function is schematically

$$
G_n(x_1,\ldots,x_n)
=
\frac{
\langle0|T\{\phi_I(x_1)\cdots\phi_I(x_n)\exp[-i\int d^4x\,\mathcal H_I(x)]\}|0\rangle
}{
\langle0|T\{\exp[-i\int d^4x\,\mathcal H_I(x)]\}|0\rangle
}.
$$

The denominator cancels vacuum bubbles: diagrams with no connection to the external insertions. The logarithm of the source functional removes the remaining factorization among source-attached components. With qft.org's Lorentzian convention,

$$
\boxed{Z[J]=e^{iW[J]},}
$$

and $W[J]$ generates connected correlators.

This page is the diagrammatic counterpart of [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/). There, connectedness was defined algebraically by cumulants. Here, connectedness is visible in diagrams. Coleman is especially explicit about the denominator that cancels disconnected vacuum bubbles in Feynman-graph calculations, and about the role of $Z[J]$ and $W[J]$ in generating full and connected Green functions; Weinberg and Srednicki present the same linked-cluster structure in the general Feynman-rule and path-integral formalisms (Coleman 2019, §§8.4, 13.2–13.4, and 32.1; Weinberg 1995, Vol. I, §§4.3, 6.1, and 9.4; Srednicki 2007, §§9 and 19).

## Prerequisites

You should know [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/), [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/), [Wick's Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/), [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/), and [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/).

## Core idea

Every diagram decomposes uniquely into connected components. Summing over arbitrary products of connected components exponentiates. Taking a logarithm extracts the connected pieces.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Connected diagrams exponentiate and vacuum bubbles cancel](/figures/foundations/connected-diagram-exponentiation.svg)

<figcaption>

Diagrammatic linked-cluster structure. The displayed exponentiation is schematic: the connected components include the usual factors of $i$, propagators, vertices, integrals, and symmetry factors. Dividing by $\mathcal Z[0]$ removes source-free vacuum bubbles; taking $W[J]=-i\log Z[J]$ keeps connected source-attached diagrams.

</figcaption>
</figure>

This is the reason $W[J]$ is more than notation. It is the object that stores the genuinely connected response of the vacuum to sources.

:::note[Assumptions]
The diagrammatic exponentiation statements are perturbative statements. They follow from the combinatorics of Wick contractions and the fact that disconnected components multiply. As usual, loop integrals and coincident-point products require a regulator before they are honest numbers.
:::

## Two meanings of disconnected

There are two related but distinct issues.

First, a diagram may contain a vacuum component disconnected from all external insertions:

```txt
external connected graph × vacuum bubble.
```

These vacuum bubbles cancel between numerator and denominator in normalized Green functions.

Second, a diagram may be disconnected but still have external insertions on every component:

```txt
(two-point graph connecting x₁,x₂) × (two-point graph connecting x₃,x₄).
```

These do not cancel by dividing by the vacuum functional. They are real contributions to the full four-point function. They disappear only when one passes from full correlators to connected correlators, equivalently from $Z[J]$ to $W[J]$.

So the hierarchy is

```txt
unnormalized vacuum functional:
  contains everything, including pure vacuum bubbles;

normalized Z[J]:
  removes pure vacuum bubbles but still contains products of source-connected pieces;

connected generator W[J]:
  keeps only connected source-attached pieces.
```

This distinction is small on the page and huge in calculations.

## Vacuum bubbles and normalization

In the interaction picture, the unnormalized numerator for an $n$-point function is

$$
N_n
=
\langle0|T\{\phi_1\cdots\phi_n S_I\}|0\rangle,
\qquad
S_I=T\exp\left[-i\int d^4x\,\mathcal H_I(x)\right].
$$

Here $\phi_a\equiv\phi_I(x_a)$. Wick's theorem expands $N_n$ into diagrams. Some diagrams have a component with no external insertion. Such a component is a vacuum bubble.

The vacuum-to-vacuum factor is

$$
N_0=\langle0|S_I|0\rangle.
$$

The normalized Green function is

$$
\boxed{
G_n(x_1,\ldots,x_n)
=\frac{N_n}{N_0}.
}
$$

Every diagram in $N_n$ can be written as

$$
(\text{diagram attached to external insertions})
\times
(\text{product of vacuum bubbles}).
$$

The product of vacuum bubbles is exactly the same factor that appears in $N_0$. Dividing by $N_0$ removes it.

In path-integral language the same normalization is

$$
Z[J]
=\frac{\mathcal Z[J]}{\mathcal Z[0]},
\qquad
\mathcal Z[J]
=\int\mathcal D\phi\,
\exp\left(iS[\phi]+i\int d^4x\,J\phi\right).
$$

Then

$$
Z[0]=1.
$$

That one-line condition is the practical statement that pure vacuum bubbles have been normalized away.

## Why disconnected diagrams exponentiate

Suppose the connected vacuum diagrams of a source theory are denoted by $C_1[J],C_2[J],\ldots$, including their numerical factors. A general disconnected diagram is a product of connected components:

$$
C_1[J]^{n_1}C_2[J]^{n_2}\cdots.
$$

If a component appears $n_I$ times, the expansion includes a factor $1/n_I!$ because identical connected components are indistinguishable. Therefore the sum over all disconnected products gives

$$
\sum_{n_1,n_2,\ldots\ge0}
\prod_I\frac{C_I[J]^{n_I}}{n_I!}
=\prod_I e^{C_I[J]}
=\exp\left(\sum_I C_I[J]\right).
$$

This is the linked-cluster theorem in its most elementary form:

$$
\boxed{
\text{sum of all diagrams}
=\exp(\text{sum of connected diagrams}).
}
$$

The exact factors of $i$ depend on whether one says that $C_I$ is the diagram itself, or that $iW$ is the sum of connected diagrams. With qft.org's Lorentzian convention, the clean statement is

$$
\boxed{
Z[J]=e^{iW[J]},
\qquad
W[J]=-i\log Z[J].
}
$$

Thus $iW[J]$ is the sum of connected source-attached diagrams in the normalized theory.

## Why W generates connected correlators

The full source functional expands as

$$
Z[J]
=1+
\sum_{n=1}^{\infty}\frac{i^n}{n!}
\int d^4x_1\cdots d^4x_n\,
J(x_1)\cdots J(x_n)G_n(x_1,\ldots,x_n).
$$

The connected generator expands as

$$
W[J]
=\sum_{n=1}^{\infty}\frac{i^{n-1}}{n!}
\int d^4x_1\cdots d^4x_n\,
J(x_1)\cdots J(x_n)G_n^{\rm c}(x_1,\ldots,x_n).
$$

Therefore

$$
\boxed{
G_n^{\rm c}(x_1,\ldots,x_n)
=\left.\frac{1}{i^{n-1}}
\frac{\delta^n W[J]}{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}.
}
$$

For example, if $\langle\phi\rangle=0$, then

$$
G_4(x_1,x_2,x_3,x_4)
=G_4^{\rm c}(x_1,x_2,x_3,x_4)
+G_2(x_1,x_2)G_2(x_3,x_4)
$$

$$
\quad
+G_2(x_1,x_3)G_2(x_2,x_4)
+G_2(x_1,x_4)G_2(x_2,x_3).
$$

The three products are disconnected source-attached diagrams. They are present in $Z[J]$ and absent from $W[J]$.

## Diagrammatic example in scalar theory

In $\phi^4$ theory, the first-order contribution to the four-point function contains the connected contact diagram

$$
G_{4,{\rm conn}}^{(1)}(x_1,x_2,x_3,x_4)
=(-i\lambda)\int d^4z\,
\prod_{a=1}^4D_F(x_a-z).
$$

The full four-point function also contains disconnected pieces such as

$$
D_F(x_1-x_2)D_F(x_3-x_4).
$$

The first term is generated by differentiating $W[J]$. The product term is generated by differentiating $Z[J]$, because $Z[J]$ contains products of connected pieces.

Now consider a diagram that equals

$$
\left[(-i\lambda)\int d^4z\,\prod_{a=1}^4D_F(x_a-z)\right]
\times
\left[\frac{-i\lambda}{8}\int d^4w\,D_F(w-w)^2\right].
$$

The second bracket is a vacuum bubble. It is disconnected from the external points. It is canceled by the denominator $Z[0]$ and does not appear in the normalized four-point Green function.

The difference is easy to say:

```txt
Products of source-attached components belong to full correlators.
Pure vacuum components do not belong to normalized correlators.
Connected correlators keep only one source-attached component.
```

## Vacuum diagrams and vacuum energy

If vacuum bubbles cancel, why care about them at all?

Because they encode the vacuum energy. In a finite spacetime volume, the vacuum-to-vacuum amplitude behaves schematically as

$$
\langle0|S_I|0\rangle
\sim e^{-iE_0T}
$$

in Lorentzian signature. Vacuum diagrams contribute to $E_0$. In most scattering and normalized-correlation calculations, this overall phase or normalization cancels. In effective-potential calculations, Casimir-energy calculations, finite-temperature field theory, and semiclassical tunneling, vacuum diagrams can become the thing one wants.

So the rule is not “vacuum diagrams are meaningless.” The rule is:

```txt
For normalized correlators and S-matrix elements, pure vacuum bubbles cancel.
For vacuum energy and effective actions, vacuum diagrams carry physical information.
```

## Connected versus one-particle irreducible

A connected diagram is a diagram that cannot be split into two pieces by cutting no lines. More precisely, any two vertices or external insertions are joined by some path through the graph.

A one-particle-irreducible diagram, or 1PI diagram, is stronger: it cannot be disconnected by cutting one internal line.

Thus

```txt
1PI ⇒ connected,
connected ⇏ 1PI.
```

For example, in $\phi^3$ theory the tree-level exchange diagram for four-point scattering is connected, but it is not 1PI: cutting the internal exchange line separates the graph into two pieces. The $\phi^4$ contact diagram is 1PI at tree level.

This distinction matters because

```txt
W[J] generates connected diagrams;
Γ[φ] generates 1PI diagrams.
```

The next page on the effective action develops this second reorganization.

## Cluster decomposition

Connected diagrams are also tied to the physical idea that distant experiments become independent. If two groups of insertions are separated by a large spacelike distance, the full correlator should factorize into a product of correlators for the two groups, provided the vacuum is unique and the theory has suitable locality and spectral properties.

The connected correlator is the part that should decay in this limit:

$$
G_{A\cup B}^{\rm c}\longrightarrow 0
\qquad
\text{as the separation between }A\text{ and }B\text{ becomes large.}
$$

This is why connected correlators are the natural input for scattering and response. They remove the parts that say only that two independent experiments were performed in the same universe.

## Common pitfalls

### Saying the denominator removes every disconnected diagram

The denominator removes vacuum bubbles only. It does not remove products of lower-point correlators that still contain source or external insertions. To remove those, use $W[J]=-i\log Z[J]$.

### Confusing connected and 1PI

Connected diagrams can fall apart when one internal line is cut. Such diagrams are not 1PI. The connected generator is $W[J]$; the 1PI generator is the effective action $\Gamma[\varphi]$.

### Forgetting normalization conventions

Some books use $Z=e^W$, especially in Euclidean signature. qft.org uses $Z=e^{iW}$ in Lorentzian signature. Factors of $i$ in derivative formulas follow from this choice.

### Throwing away vacuum diagrams everywhere

Vacuum bubbles cancel in normalized correlators, but vacuum diagrams are central in vacuum energy, effective potentials, finite-temperature free energies, and tunneling rates.

### Mistaking diagrammatic connectedness for causal connectedness

A connected Feynman diagram is a combinatorial object. It does not mean that an on-shell particle literally travels along each internal line, nor does it by itself define a causal response function. Retarded functions, commutators, and support properties are separate structures.

## Relations to nearby pages

- [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/) defines connected functions algebraically as cumulants.
- [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) develops the $Z[J]$, $W[J]$, and $\Gamma[\varphi]$ hierarchy.
- [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/) gives the first concrete vertices used in the examples here.
- [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/) explains the 1PI generator.
- [Cluster Decomposition](/foundations/structural-principles/cluster-decomposition/) will give the structural version of the long-distance factorization principle.

## Research status

The linked-cluster and connected-diagram structure is textbook-standard perturbative QFT. Nonperturbatively, the exact meaning of $Z[J]$, $W[J]$, and their differentiability can be subtle, especially in gauge theories, theories with multiple vacua, and theories requiring infrared regulation. The perturbative statements here are stable within a regulated expansion.

## Exercises

### Exercise 1: Vacuum-bubble cancellation

Suppose the unnormalized numerator of a two-point function factors as

$$
N_2=A_2\,B,
$$

where $A_2$ is the sum of diagrams attached to the two external insertions and $B$ is the sum of vacuum bubbles. If $N_0=B$, what is the normalized two-point function?

<details>
<summary><strong>Solution</strong></summary>

By definition,

$$
G_2=\frac{N_2}{N_0}=\frac{A_2B}{B}=A_2.
$$

The pure vacuum-bubble factor cancels.

</details>

### Exercise 2: Full versus connected four-point function

Assume $\langle\phi\rangle=0$. Express the full four-point function in terms of connected four-point and two-point functions.

<details>
<summary><strong>Solution</strong></summary>

The decomposition is

$$
\begin{aligned}
G_4(x_1,x_2,x_3,x_4)
&=G_4^{\rm c}(x_1,x_2,x_3,x_4)\\
&\quad+G_2(x_1,x_2)G_2(x_3,x_4)\\
&\quad+G_2(x_1,x_3)G_2(x_2,x_4)\\
&\quad+G_2(x_1,x_4)G_2(x_2,x_3).
\end{aligned}
$$

The three product terms are disconnected but still source-attached.

</details>

### Exercise 3: Exponentiation of one connected component

If the only connected diagram is $C[J]$, show that the sum over any number of disconnected copies is $e^{C[J]}$.

<details>
<summary><strong>Solution</strong></summary>

The contribution with $n$ identical copies is $C[J]^n/n!$. Summing over $n$ gives

$$
\sum_{n=0}^{\infty}\frac{C[J]^n}{n!}=e^{C[J]}.
$$

This is the simplest case of diagram exponentiation.

</details>

### Exercise 4: Connected but not 1PI

Explain why the tree-level exchange diagram in $\phi^3$ theory is connected but not 1PI.

<details>
<summary><strong>Solution</strong></summary>

The diagram has two cubic vertices joined by one internal line. Every external leg is connected to every other through the graph, so the diagram is connected. But cutting the internal exchange line separates the diagram into two disconnected pieces. Therefore it is not one-particle irreducible.

</details>

### Exercise 5: Which functional generates what?

State which functional generates full correlators, connected correlators, and 1PI vertices.

<details>
<summary><strong>Solution</strong></summary>

The hierarchy is

$$
\boxed{Z[J]\text{ generates full correlators},}
$$

$$
\boxed{W[J]=-i\log Z[J]\text{ generates connected correlators},}
$$

and

$$
\boxed{\Gamma[\varphi]\text{ generates 1PI vertices}.}
$$

Here $Z=e^{iW}$ is the qft.org Lorentzian convention.

</details>

### Exercise 6: Subtracting vacuum diagrams in W

Let the unnormalized functional be

$$
\mathcal Z[J]=e^{i\mathcal W[J]}.
$$

Define the normalized functional by $Z[J]=\mathcal Z[J]/\mathcal Z[0]$. Express $W[J]$ in terms of $\mathcal W[J]$ and $\mathcal W[0]$.

<details>
<summary><strong>Solution</strong></summary>

We have

$$
Z[J]
=\frac{e^{i\mathcal W[J]}}{e^{i\mathcal W[0]}}
=e^{i(\mathcal W[J]-\mathcal W[0])}.
$$

Since $Z[J]=e^{iW[J]}$,

$$
\boxed{W[J]=\mathcal W[J]-\mathcal W[0].}
$$

The subtraction removes connected vacuum diagrams with no source insertions.

</details>

## Sources and further reading

- G. C. Wick, “The Evaluation of the Collision Matrix,” *Physical Review* **80** (1950), 268–272.
- F. J. Dyson, “The S Matrix in Quantum Electrodynamics,” *Physical Review* **75** (1949), 1736–1755.
- Sidney Coleman, *Lectures on Quantum Field Theory*, §§8.4, 13.2–13.4, and 32.1, for connected and disconnected diagrams, vacuum-bubble cancellation, and the $Z[J]$, $W[J]$ hierarchy.
- Mark Srednicki, *Quantum Field Theory*, §§8–10 and §19, for source functionals and perturbation theory to all orders.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, §§4.3, 6.1, and 9.4, for cluster decomposition, Feynman-rule combinatorics, and path-integral diagrammatics.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. I.7 and appendix C, for diagrammatic exponentiation and scalar examples.


## Version history

- **2026-05-23:** Initial qft.org page on connected and disconnected diagrams, vacuum-bubble cancellation, linked-cluster exponentiation, W[J] as the connected generator, the distinction from 1PI diagrams, and the bridge toward the effective action.
