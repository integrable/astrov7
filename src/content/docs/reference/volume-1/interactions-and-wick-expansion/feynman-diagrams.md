---
title: "Feynman Diagrams"
description: "Feynman diagrams as compact bookkeeping for Dyson expansion and Wick contractions: propagators, vertices, loop integrals, symmetry factors, fermion signs, and external lines."
sidebar:
  label: "Feynman Diagrams"
  order: 4
---

## Summary

Feynman diagrams are compact notation for terms in perturbation theory. They are not an additional physical postulate. In the operator derivation, they come from applying Wick's theorem to the Dyson expansion. In the path-integral derivation, they come from differentiating Gaussian source functionals and expanding interaction terms.

For a scalar theory with

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4,
$$

the basic momentum-space ingredients are

$$
\boxed{\text{internal line: }\frac{i}{p^2-m^2+i\epsilon}},
\qquad
\boxed{\text{quartic vertex: }-i\lambda(2\pi)^4\delta^{(4)}\!\left(\sum p\right)},
$$

and each independent loop momentum is integrated with

$$
\boxed{\int\frac{d^4\ell}{(2\pi)^4}.}
$$

The full contribution of a diagram is the product of its vertex factors, propagators, external factors if appropriate, loop integrals, signs, and symmetry factor. Coleman emphasizes that Feynman diagrams represent matrix elements, while the preceding Wick diagrams represent operator terms; Weinberg gives the general covariant algorithm for drawing diagrams, assigning factors, integrating over internal variables, and summing diagrams (Coleman 2019, chs. 8 and 10; Weinberg 1995, Vol. I, §§6.1 and 6.3).

## Prerequisites

You should know [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/), [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/), [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/), [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/), and [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/).

## Core idea

A Feynman diagram records a Wick-contraction pattern in a way that makes the corresponding integral easy to write down.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Feynman diagrams as bookkeeping for Dyson and Wick expansion](/figures/foundations/feynman-diagram-bookkeeping.svg)

<figcaption>

A diagram is a compact label for a term in the Dyson–Wick expansion. Vertices come from interaction terms, internal lines come from contractions, loop momenta are integrated, and the whole graph is multiplied by its symmetry factor and any fermion signs.

</figcaption>
</figure>

The important dictionary is

```txt
interaction term     → vertex;
Wick contraction     → propagator line;
uncontracted field   → external insertion or external particle factor;
unfixed momentum     → loop integral;
overcounting         → symmetry factor;
fermion permutation  → sign.
```

Once this dictionary is set, drawing diagrams is just a humane way of managing the combinatorics.

## Diagrams are not literal particle histories

It is tempting to say that a diagram shows particles moving, meeting, and splitting. That language can be useful, but it is not fundamental.

A Feynman diagram is primarily a term in an expansion. Internal lines are propagators, not observed particles. Vertices are local interaction insertions, not little spacetime explosions. Loop momenta are integration variables, not measured momenta.

The literal object being computed depends on context:

```txt
Green function:
  external legs are operator insertions and may be off shell;

S-matrix element:
  external particles are asymptotic states and are on shell;

amputated amplitude:
  external propagators are removed, usually through LSZ reduction.
```

This distinction prevents a lot of folk-physics headaches. Diagrams are wonderful bookkeeping. They are not microscopic security-camera footage.

## Position-space viewpoint

Start with the interaction-picture expansion

$$
S
=\sum_{V=0}^{\infty}\frac{(-i)^V}{V!}
\int d^4x_1\cdots d^4x_V\,
T\{\mathcal H_I(x_1)\cdots\mathcal H_I(x_V)\}.
$$

For a scalar interaction $\lambda\phi^4/4!$, each interaction point $x_a$ carries four scalar fields. Wick's theorem pairs fields. A pair between $x$ and $y$ gives

$$
D_F(x-y)=\langle0|T\{\phi(x)\phi(y)\}|0\rangle.
$$

Thus position-space diagrams are made of vertices at spacetime points and propagators connecting them. A typical position-space contribution has the form

$$
\frac{1}{S_\Gamma}
\left(\prod_{v\in\Gamma} -i\lambda_v\int d^4x_v\right)
\left(\prod_{\ell\in\Gamma}D_F(x_{\ell,1}-x_{\ell,2})\right),
$$

where $S_\Gamma$ is the graph's symmetry factor. For derivative interactions, spinor fields, vector fields, or gauge fields, the line and vertex factors carry indices and momenta, but the same logic applies.

## Momentum-space viewpoint

The scalar Feynman propagator is

$$
D_F(x-y)=\int\frac{d^4p}{(2\pi)^4}\,
\frac{i e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

When every propagator is Fourier transformed, each vertex integral produces momentum conservation:

$$
\int d^4x\,e^{-ix\cdot(p_1+\cdots+p_r)}
=(2\pi)^4\delta^{(4)}(p_1+\cdots+p_r).
$$

For scalar $\phi^4$ theory the stripped momentum-space rules are:

$$
\boxed{\text{internal scalar line carrying }p:
\quad \frac{i}{p^2-m^2+i\epsilon},}
$$

$$
\boxed{\text{quartic scalar vertex:}
\quad -i\lambda,}
$$

with an overall factor

$$
(2\pi)^4\delta^{(4)}\!\left(\sum p_{\rm external}\right)
$$

for total momentum conservation. If there are independent loop momenta, integrate each one with

$$
\boxed{
\int\frac{d^4\ell}{(2\pi)^4}.
}
$$

## External lines

For correlation functions, external lines are contractions from the inserted operators to the rest of the graph. They are ordinary propagators unless one defines an amputated correlator.

For S-matrix elements, external lines are treated differently. LSZ reduction amputates external propagators and extracts residues at one-particle poles. In practical scattering rules, external scalar legs contribute simple normalization factors, external spinor legs contribute $u$, $v$, $\bar u$, or $\bar v$, and external vector legs contribute polarization vectors.

Foundations keeps this distinction visible:

```txt
correlator diagram:    computes a time-ordered Green function;
amputated diagram:    removes external propagators;
S-matrix diagram:      also places external states on shell.
```

The full LSZ story belongs to the scattering section. Here the key point is that Feynman diagrams are a shared notation used before and after amputation.

## Symmetry factors

The factorials in the Dyson expansion and in interaction terms are designed to cancel most of the Wick-contraction overcounting. But not always all of it.

A graph symmetry factor divides by the number of relabelings of internal vertices and lines that leave the graph unchanged while keeping external labels fixed. Equivalently, it compensates for the fact that several Wick contractions may produce the same unlabeled graph.

For example, in scalar $\phi^4$ theory, the first-order connected four-point contact contribution has no remaining symmetry factor when the four external insertions are labeled. The $4!$ ways to attach the four external fields to the four fields at the vertex cancel the $1/4!$ in the interaction.

The one-loop tadpole correction to the two-point function is different. At first order,

$$
\frac{-i\lambda}{4!}\int d^4z\,
\langle0|T\{\phi(x)\phi(y)\phi(z)^4\}|0\rangle.
$$

Choose a field at $z$ to contract with $\phi(x)$: $4$ choices. Choose a field at $z$ to contract with $\phi(y)$: $3$ choices. The remaining two fields at $z$ contract with each other. Hence there are $12$ contractions, and

$$
\frac{-i\lambda}{4!}\times 12=\frac{-i\lambda}{2}.
$$

The tadpole contribution is

$$
\boxed{
G_2^{\rm tad}(x,y)
=\frac{-i\lambda}{2}\int d^4z\,
D_F(x-z)D_F(y-z)D_F(0).
}
$$

So this diagram has symmetry factor $2$.

When in doubt, return to Wick contractions. Feynman rules are compressed combinatorics; Wick's theorem is the source code.

## Fermion signs

Fermion diagrams include signs from anticommuting fields. There are two common bookkeeping rules:

```txt
1. A closed fermion loop contributes an extra factor of -1.
2. Reordering external fermions to a standard order may contribute extra signs.
```

For a Dirac field, the fermion propagator is

$$
S_F(p)=\frac{i(\slashed p+m)}{p^2-m^2+i\epsilon},
$$

with convention-dependent index placement. Fermion lines also carry arrows to track charge flow and spinor-index contractions. The detailed Dirac and gauge-theory rules belong in the perturbative QFT and QED sections, but the origin of the signs is already visible here.

## Vacuum bubbles

The numerator of an interacting correlator contains diagrams that are disconnected from all external insertions. These are vacuum bubbles. In a normalized correlator,

$$
\frac{\langle0|T\{\mathcal O_1\cdots\mathcal O_n S\}|0\rangle}
{\langle0|S|0\rangle},
$$

vacuum bubbles cancel between numerator and denominator. This is the diagrammatic version of writing

$$
Z[J]=e^{iW[J]}
$$

and using $W[J]$ to generate connected diagrams. Vacuum bubbles are not meaningless; they contribute to vacuum energy and to the effective action. But they cancel from normalized ordinary correlators in flat-space QFT without gravity.

## Loop counting

For a connected graph with $V$ vertices, $I$ internal lines, and $L$ independent loop momenta,

$$
\boxed{L=I-V+1.}
$$

Reason: assign one momentum to each internal line, giving $I$ variables. Momentum conservation at each vertex gives $V$ delta functions, but one of them enforces overall external momentum conservation rather than fixing an internal variable. Thus $V-1$ constraints reduce the number of independent internal momenta to

$$
I-(V-1)=I-V+1.
$$

Tree diagrams have $L=0$. Loop diagrams have $L\ge1$ and contain integrals over momenta not fixed by external kinematics. These loop integrals are where ultraviolet divergences first appear.

In four-dimensional $\phi^4$ theory, the one-loop correction to four-point scattering contains an integral of the schematic form

$$
\int\frac{d^4\ell}{(2\pi)^4}
\frac{i}{\ell^2-m^2+i\epsilon}
\frac{i}{(\ell+P)^2-m^2+i\epsilon},
$$

where $P$ is a combination of external momenta. Foundations introduces why this integral appears; renormalization explains how to interpret it.

## Connected and disconnected diagrams

A connected diagram is one graph: any point on it can be reached from any other point by following lines. A disconnected diagram is a product of connected components.

For correlators, disconnected diagrams are not automatically wrong. They are part of the full correlator. But connected correlators isolate the part that does not factor into lower-point functions. That is why the logarithm of the generating functional produces connected diagrams.

For scattering, disconnected diagrams often represent independent processes happening side by side. The physically interesting scattering amplitude is usually the connected, amputated part.

## Common pitfalls

**Mistaking diagrams for ontology.** Internal lines are propagators, not observed particles. Virtual particles are not asymptotic states.

**Forgetting what is being computed.** Correlators, amputated Green functions, and S-matrix elements have related but different diagrammatic rules.

**Dropping symmetry factors.** A clean-looking graph may represent many identical Wick contractions. The symmetry factor keeps the counting honest.

**Forgetting fermion signs.** Closed fermion loops and external fermion permutations produce signs.

**Ignoring gauge dependence.** In gauge theories, individual diagrams can depend on gauge choice even when the final observable does not.

**Assuming perturbation theory sees everything.** Solitons, instantons, confinement, and other nonperturbative phenomena are not generally visible in any finite set of ordinary Feynman diagrams.

## Relation to nearby pages

- [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) derives the contractions that diagrams encode.
- [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/) supplies the perturbative expansion.
- [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/) explains the logarithm of the generating functional and connected diagrams.
- [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/) gives the Gaussian path-integral derivation of the same rules.
- [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/) explains how source derivatives generate diagrams.
- [Semiclassical Expansion](/foundations/path-integral-formalism/semiclassical-expansion/) connects loop counting with expansion around a saddle.
- [Spectral Representation](/foundations/correlators-and-propagators/spectral-representation/) reminds us that exact propagators contain physical spectral data beyond a single free line.

## Research status

Feynman diagrams are textbook-standard as formal perturbative tools. Their precise meaning requires a regulator, a renormalization prescription, and a statement about the asymptotic or effective nature of the expansion. Individual diagrams are often not observables; properly summed and renormalized quantities are.

## Exercises

### Exercise 1: Quartic vertex factor

Starting from

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

show that the four-point contact vertex factor is $-i\lambda$ after the Wick-contraction combinatorics are included.

<details>
<summary><strong>Solution</strong></summary>

At first order in the Dyson expansion,

$$
\frac{-i\lambda}{4!}\int d^4z\,
\langle0|T\{\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\phi(z)^4\}|0\rangle.
$$

In a four-point correlator, the four fields at $z$ can be contracted with four external insertions in $4!$ ways. These contractions cancel the factor $1/4!$. The remaining local factor is

$$
-i\lambda.
$$

</details>

### Exercise 2: Four-point contact correlator

Write the first-order connected position-space contribution to the scalar four-point function in $\phi^4$ theory.

<details>
<summary><strong>Solution</strong></summary>

The connected contact term contracts each external field with one of the four fields at $z$. There are $4!$ such contractions, canceling $1/4!$. Hence

$$
\boxed{
G_{4,\rm conn}^{(1)}(x_1,x_2,x_3,x_4)
=(-i\lambda)\int d^4z\,
D_F(x_1-z)D_F(x_2-z)D_F(x_3-z)D_F(x_4-z).
}
$$

</details>

### Exercise 3: Tadpole symmetry factor

Compute the coefficient of the one-loop tadpole correction to the two-point function in $\phi^4$ theory.

<details>
<summary><strong>Solution</strong></summary>

The first-order term is

$$
\frac{-i\lambda}{4!}\int d^4z\,
\langle0|T\{\phi(x)\phi(y)\phi(z)^4\}|0\rangle.
$$

For the tadpole graph, one field at $z$ contracts with $\phi(x)$ and another with $\phi(y)$. There are $4$ choices for the first contraction and $3$ choices for the second, so $12$ choices. The two remaining $z$ fields contract with each other.

Thus

$$
\frac{-i\lambda}{4!}\times12=\frac{-i\lambda}{2},
$$

and

$$
G_2^{\rm tad}(x,y)
=\frac{-i\lambda}{2}\int d^4z\,D_F(x-z)D_F(y-z)D_F(0).
$$

</details>

### Exercise 4: Cubic tree counting

For a scalar theory with $\mathcal L_{\rm int}=-g\phi^3/3!$, draw the tree-level connected contribution to the four-point function at order $g^2$ and write its position-space expression for one channel.

<details>
<summary><strong>Solution</strong></summary>

At order $g^2$, two cubic vertices are needed. One channel connects $x_1,x_2$ to a vertex $z$ and $x_3,x_4$ to a vertex $w$, with one internal line between $z$ and $w$. Its position-space expression is

$$
(-ig)^2\int d^4z\,d^4w\,
D_F(x_1-z)D_F(x_2-z)D_F(z-w)D_F(w-x_3)D_F(w-x_4),
$$

plus the other channels obtained by assigning the external points differently. The $1/2!$ from the second-order Dyson term and the $1/(3!)^2$ from the vertices are canceled by the corresponding Wick-contraction multiplicities for the labeled tree diagram.

</details>

### Exercise 5: Loop count for the fish diagram

In $\phi^4$ theory, the one-loop correction to the four-point function has two quartic vertices connected by two internal lines. Use $L=I-V+1$ to compute the number of loop momenta.

<details>
<summary><strong>Solution</strong></summary>

For the fish diagram,

$$
V=2,
\qquad
I=2.
$$

Therefore

$$
L=I-V+1=2-2+1=1.
$$

There is one independent loop momentum. In momentum space, the diagram contains one integral of the form

$$
\int\frac{d^4\ell}{(2\pi)^4}
$$

multiplying two internal propagators.

</details>

### Exercise 6: Vacuum bubbles cancel in normalized correlators

Explain why vacuum bubbles cancel in

$$
\frac{\langle0|T\{\mathcal O_1\cdots\mathcal O_nS\}|0\rangle}
{\langle0|S|0\rangle}.
$$

<details>
<summary><strong>Solution</strong></summary>

The numerator contains diagrams connected to the operator insertions multiplied by diagrams completely disconnected from them. The disconnected vacuum diagrams are exactly the same vacuum-bubble factor that appears in the denominator $\langle0|S|0\rangle$. Dividing by the denominator cancels that common factor. What remains is the sum of diagrams connected to at least one external insertion.

</details>

## References

- R. P. Feynman, “Space-Time Approach to Quantum Electrodynamics,” *Physical Review* **76** (1949), 769–789.
- F. J. Dyson, “The S Matrix in Quantum Electrodynamics,” *Physical Review* **75** (1949), 1736–1755.
- G. C. Wick, “The Evaluation of the Collision Matrix,” *Physical Review* **80** (1950), 268–272.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 8 and 10, for Wick diagrams, the transition to Feynman diagrams, and early examples.
- Mark Srednicki, *Quantum Field Theory*, §§9–10 and §19, for interacting scalar field theory and perturbation theory to all orders.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 6, for the general covariant Feynman-rule derivation.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. I.7 and appendix C, for an accessible diagrammatic introduction and quick rule summary.
