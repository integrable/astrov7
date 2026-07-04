---
title: "Vacuum Bubbles"
description: "A careful explanation of vacuum bubble diagrams, their exponentiation in the vacuum functional, their cancellation from normalized correlators, and their role in vacuum energy and thermodynamics."
sidebar:
  label: "Vacuum Bubbles"
  order: 8
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§9, 19, and 21; Coleman 2019, chs. 8, 28, and 32; Weinberg 1995, Vol. I, chs. 6 and 9; Schwartz 2014, chs. 7 and 14; Zinn-Justin 2021, chs. 1 and 7"
topics:
  - vacuum bubbles
  - generating functionals
  - connected diagrams
  - vacuum energy
  - normalization
canonicalTopics:
  - vacuum-bubble
  - vacuum-functional
  - connected-vacuum-diagram
  - vacuum-energy
  - normalized-correlator
researchStatus:
  established:
    - "Vacuum bubbles exponentiate in the vacuum functional and cancel from normalized flat-space correlation functions, while connected vacuum diagrams determine vacuum energy and free energy when the normalization is not divided out."
  active:
    - "Vacuum energy becomes physically delicate in gravity, finite-temperature QFT, nonequilibrium real-time formalisms, cosmology, and effective-potential calculations."
---

## Summary

A **vacuum bubble** is a Feynman diagram with no external operator insertions and no external particles. It is a diagram for the vacuum functional, not for a scattering process.

For an interacting scalar theory, the unnormalized vacuum functional is

$$
Z[0]
=
\int\mathcal D\phi\,e^{iS[\phi]}.
$$

Vacuum bubbles are the diagrams in the perturbative expansion of $Z[0]$. Connected vacuum bubbles exponentiate:

$$
Z[0]=Z_0[0]\exp\left(\sum_{\Gamma\,\in\,\text{connected vacuum diagrams}}
\mathcal A_\Gamma\right).
$$

In normalized correlators,

$$
\langle T\mathcal O\rangle
=
\frac{\langle T\mathcal O\,e^{iS_I}\rangle_0}
{\langle e^{iS_I}\rangle_0},
$$

vacuum bubbles disconnected from the operator insertions cancel between numerator and denominator.

That cancellation does **not** mean vacuum bubbles are meaningless. They contribute to vacuum energy, free energy, effective potentials, Casimir energies, and gravitationally coupled cosmological-constant terms. They cancel from ordinary normalized flat-space S-matrix elements because those observables are conditioned on the vacuum normalization.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![Vacuum bubble examples, factorization into source-connected diagrams times vacuum factors, and cancellation in normalized correlators](/figures/perturbative-qft/vacuum-bubbles.svg)

<figcaption>

Vacuum bubbles are diagrams with no external insertions. Connected vacuum bubbles exponentiate in $Z[0]$. Vacuum components factor out of correlators and cancel after division by $Z[0]$, but the same diagrams encode vacuum energy when the normalization is retained.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Generating-Functional Diagrams](/perturbative-qft/diagrammatics-feynman-rules/generating-functional-diagrams/), [Connected and Disconnected Diagrams](/perturbative-qft/diagrammatics-feynman-rules/connected-and-disconnected-diagrams/), [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/), [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), and [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/).

For later uses, review [Narrow-Width Approximation](/perturbative-qft/phase-space-cross-sections-decays/narrow-width-approximation/) and [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) only after the phase-space chapter is familiar.

## Core idea

Vacuum bubbles are the diagrams that happen even when no external source asks the field to do anything.

In a source expansion, diagrams fall into two classes:

| Diagram class | Meaning |
|---|---|
| Source-connected diagrams | At least one path connects the diagram to an external insertion or source. |
| Vacuum diagrams | No path connects the diagram to any external insertion or source. |

If a diagram has a vacuum component and a source-connected component, its value factorizes. The vacuum part does not know where the external insertions are. Therefore the numerator of a normalized correlator contains a common multiplicative vacuum factor, and the denominator contains exactly the same factor.

The practical slogan is

$$
\text{vacuum bubbles cancel from normalized correlators, but not from }\log Z[0].
$$

This is one of those statements that is both boring and load-bearing. If you forget it, you will either keep many irrelevant diagrams in scattering calculations or incorrectly throw away vacuum energy in contexts where it matters.

## Setup and conventions

Write the Lorentzian generating functional as

$$
Z[J]
=
\int\mathcal D\phi\,
\exp\left\{iS[\phi]+i\int d^dx\,J(x)\phi(x)\right\}.
$$

The normalized generating functional is

$$
Z_N[J]\equiv\frac{Z[J]}{Z[0]},
\qquad
Z_N[0]=1.
$$

Correlators are generated from $Z_N[J]$, not from the unnormalized $Z[J]$, when the vacuum-to-vacuum normalization has been divided out:

$$
\langle T\phi(x_1)\cdots\phi(x_n)\rangle
=
\left.
\frac{1}{i^n}
\frac{\delta^n Z_N[J]}{\delta J(x_1)\cdots\delta J(x_n)}
\right|_{J=0}.
$$

The connected generating functional is defined by

$$
Z[J]=e^{iW[J]}.
$$

Then $W[J]$ is the generator of connected diagrams, including connected vacuum diagrams at $J=0$. For the normalized functional,

$$
Z_N[J]
=e^{i(W[J]-W[0])}.
$$

Thus normalized connected correlators are generated by

$$
W_N[J]=W[J]-W[0].
$$

The subtraction of $W[0]$ is the algebraic version of canceling vacuum bubbles.

## Exponentiation of connected vacuum diagrams

The reason connected vacuum bubbles exponentiate is the same combinatorial reason that connected diagrams are generated by the logarithm of $Z$.

Suppose the possible connected vacuum components have amplitudes

$$
\mathcal A_1,\mathcal A_2,\mathcal A_3,\ldots.
$$

A disconnected vacuum diagram is a multiset of connected vacuum components. If component $j$ appears $n_j$ times, its contribution includes the factor

$$
\frac{\mathcal A_j^{n_j}}{n_j!},
$$

because identical connected components can be permuted without producing a new diagram. Summing over all multiplicities gives

$$
\prod_j\left(\sum_{n_j=0}^{\infty}\frac{\mathcal A_j^{n_j}}{n_j!}\right)
=
\prod_j e^{\mathcal A_j}
=
\exp\left(\sum_j\mathcal A_j\right).
$$

Therefore

$$
\frac{Z[0]}{Z_0[0]}
=
\exp\left(\sum_{\Gamma\,\in\,\text{connected vacuum}}
\mathcal A_\Gamma\right).
$$

This is the vacuum version of the linked-cluster theorem.

## Cancellation in normalized correlators

Consider a normalized expectation value in the interaction picture:

$$
\langle T\mathcal O\rangle
=
\frac{\langle0|T\{\mathcal O e^{iS_I}\}|0\rangle_0}
{\langle0|T\{e^{iS_I}\}|0\rangle_0}.
$$

Every numerator diagram can be decomposed into a source-connected part touching $\mathcal O$ multiplied by a vacuum-bubble factor disconnected from $\mathcal O$.

The sum over all vacuum-bubble factors is precisely

$$
\langle0|T\{e^{iS_I}\}|0\rangle_0,
$$

which appears in the denominator. Therefore the denominator cancels the disconnected vacuum factor.

Equivalently,

$$
\langle T\mathcal O\rangle
=
\left[\text{sum of diagrams connected to at least one insertion in }\mathcal O\right].
$$

For scattering amplitudes, one usually goes further: disconnected pieces that describe no interaction between external particles are also separated from the connected, amputated part. But vacuum-bubble cancellation is the first step.

:::note[Connected to at least one insertion]
After dividing by $Z[0]$, a correlator can still contain diagrams disconnected from each other if each component touches at least one external insertion. For example, a four-point correlator can contain a product of two connected two-point diagrams. These are not vacuum bubbles. They are disconnected correlator pieces.
:::

## Example: the first φ⁴ vacuum bubble

Take

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4.
$$

At first order in $\lambda$, the vacuum contribution is

$$
-\frac{i\lambda}{4!}\int d^dx\,
\langle0|T\phi(x)^4|0\rangle_0.
$$

Wick's theorem gives

$$
\langle0|T\phi(x)^4|0\rangle_0
=3D_F(0)^2,
$$

because the four fields can be paired in three ways. Therefore the first connected $\phi^4$ vacuum bubble is

$$
\mathcal A^{(1)}_{\rm vac,\phi^4}
=
-\frac{i\lambda}{8}\int d^dx\,D_F(0)^2.
$$

The graph has one vertex and two internal lines that begin and end at the same vertex. Its symmetry factor is $8$:

$$
{S_\Gamma=8.}
$$

Since

$$
D_F(0)=\int\frac{d^dp}{(2\pi)^d}\frac{i}{p^2-m^2+i\epsilon},
$$

this vacuum bubble is ultraviolet divergent in ordinary four-dimensional perturbation theory. In dimensional regularization, a massless scaleless version of this integral vanishes, but that is a regulator statement, not a proof that vacuum energy is physically absent.

## Example: the θ bubble in φ³ theory

For

$$
\mathcal L_{\rm int}=-\frac{g}{3!}\phi^3,
$$

the first connected vacuum bubble with no one-point tadpole structure appears at second order. It has two cubic vertices connected by three propagators. Its position-space amplitude is

$$
\mathcal A^{(2)}_{\theta}
=
\frac{(-ig)^2}{12}
\int d^dx\,d^dy\,D_F(x-y)^3.
$$

The factor $12$ is the symmetry factor. One way to see it is to start from the expansion coefficient and vertex factorials,

$$
\frac{(-ig)^2}{2!(3!)^2},
$$

and count the $3!$ ways to pair the three fields at $x$ with the three fields at $y$. Thus the net coefficient is

$$
\frac{(-ig)^2}{2!(3!)^2}\,3!
=
\frac{(-ig)^2}{12}.
$$

The loop count for this connected vacuum graph is

$$
L=I-V+1=3-2+1=2.
$$

So even simple vacuum bubbles can be multi-loop diagrams.

## Vacuum energy and constant counterterms

Vacuum bubbles cancel from normalized flat-space correlators, but $Z[0]$ itself contains vacuum-energy information.

In a spatial box of volume $V$ over a long time interval $T$,

$$
Z[0]
\sim
e^{-iE_0T}
=
e^{-i\mathcal E_0VT},
$$

where $\mathcal E_0$ is the vacuum energy density. Thus connected vacuum diagrams contribute to

$$
\log Z[0]
\sim
-i\mathcal E_0VT.
$$

A constant shift of the Lagrangian density,

$$
\mathcal L\mapsto\mathcal L-C,
$$

changes the action by

$$
S\mapsto S-C\int d^dx,
$$

and therefore multiplies the vacuum functional by

$$
Z[0]\mapsto e^{-iC\int d^dx}Z[0].
$$

In nongravitational flat-space scattering, this overall phase cancels from normalized observables. In gravity, a constant term in the matter Lagrangian acts like a cosmological-constant contribution, so it cannot be dismissed so casually.

:::tip[When to keep vacuum bubbles]
Drop vacuum bubbles for ordinary normalized correlators and S-matrix elements in flat spacetime. Keep them when computing vacuum energy, free energy, effective potentials, thermal partition functions, Casimir energies, or gravitationally coupled observables.
:::

## Relation to the effective action

The effective action $\Gamma[\varphi]$ is obtained by a Legendre transform of $W[J]$. At a constant field $\varphi$, it defines the effective potential by

$$
\Gamma[\varphi]
=-\int d^dx\,V_{\rm eff}(\varphi)
$$

in Lorentzian conventions for constant configurations.

Vacuum diagrams are the $\varphi=0$ part of this story. More generally, vacuum diagrams in a background field determine the loop expansion of $V_{\rm eff}(\varphi)$. This is why vacuum bubbles are not just clutter: in the right problem, they are exactly the diagrams you want.

At finite temperature, the Euclidean partition function satisfies

$$
Z_E=\operatorname{Tr}e^{-\beta H}
=e^{-\beta F},
$$

so connected vacuum diagrams compute the free energy $F$. The same diagrams that cancel from zero-temperature normalized correlators become thermodynamic data.

## Common pitfalls

**Saying vacuum bubbles are always zero.** They cancel from normalized flat-space correlators. They do not vanish as contributions to $Z[0]$, vacuum energy, or free energy.

**Confusing vacuum bubbles with disconnected correlator pieces.** A disconnected four-point correlator made from two two-point functions is not a vacuum bubble, because each component touches external insertions.

**Forgetting exponentiation.** Connected vacuum diagrams contribute to $\log Z[0]$, not linearly to $Z[0]$ without combinatorial exponentiation.

**Dropping vacuum energy in gravity.** A constant shift of the Lagrangian is invisible to nongravitational normalized scattering, but it gravitates.

**Overinterpreting dimensional-regularization zeros.** Scaleless vacuum integrals vanish in dimensional regularization. That is a useful regulator property, not a universal physical statement about the vacuum.

**Using normalized and unnormalized generating functionals interchangeably.** If $Z[0]=1$ has been imposed, vacuum bubbles have already been divided out. Do not then try to extract vacuum energy from the same normalized functional.

## Relations to other pages

- [Generating-Functional Diagrams](/perturbative-qft/diagrammatics-feynman-rules/generating-functional-diagrams/) explains how $Z[J]$, $W[J]$, and diagram exponentiation are related.
- [Connected and Disconnected Diagrams](/perturbative-qft/diagrammatics-feynman-rules/connected-and-disconnected-diagrams/) distinguishes connected correlators from disconnected products.
- [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/) gives the counting rules used in the $\phi^4$ and $\phi^3$ vacuum examples.
- [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/) explains the 1PI language behind the effective action.
- [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/) introduces local counterterms, including constant vacuum-energy counterterms.
- [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/) explains loop counting, including vacuum diagrams.
- [Renormalization, RG, and EFT](/renormalization-rg-eft/) is the conceptual home for vacuum-energy counterterms and effective potentials.
- [Spacetime, Gravity, and Holography](/spacetime-gravity-holography/) discusses why vacuum energy becomes gravitationally significant.

## Research status

- **Established:** Vacuum-bubble exponentiation, cancellation from normalized correlators, and the relation between $\log Z[0]$ and connected vacuum diagrams are standard perturbative QFT.
- **Active:** Vacuum energy is subtle in gravitational physics, cosmology, curved spacetime, nonequilibrium real-time formalisms, and finite-density systems.
- **Convention-dependent:** Signs in the relation between $\log Z[0]$ and vacuum energy depend on Lorentzian versus Euclidean conventions and on whether $Z[0]$ has already been normalized to one.
- **Speculative:** The elementary diagrammatic cancellation on this page is not speculative. The interpretation of observed cosmological vacuum energy belongs to a much deeper frontier.

## Exercises

### Exercise 1: First φ⁴ vacuum bubble coefficient

Starting from

$$
-\frac{i\lambda}{4!}\int d^dx\,\langle0|T\phi(x)^4|0\rangle_0,
$$

show that the first connected $\phi^4$ vacuum bubble has coefficient $-i\lambda/8$ times $\int d^dx\,D_F(0)^2$.

<details>
<summary><strong>Solution</strong></summary>

Wick's theorem gives

$$
\langle0|T\phi(x)^4|0\rangle_0=3D_F(0)^2,
$$

because there are three ways to pair four fields. Substituting this into the first-order term gives

$$
-\frac{i\lambda}{4!}\int d^dx\,3D_F(0)^2
=
-\frac{i\lambda}{8}\int d^dx\,D_F(0)^2.
$$

</details>

### Exercise 2: Symmetry factor of the θ bubble

In $\phi^3$ theory, two cubic vertices can be connected by three propagators to form a vacuum bubble. Show that its symmetry factor is $12$.

<details>
<summary><strong>Solution</strong></summary>

At second order in the interaction, the expansion gives

$$
\frac{(-ig)^2}{2!(3!)^2}\int d^dx\,d^dy\,
\langle T\phi(x)^3\phi(y)^3\rangle_0.
$$

To form the θ bubble, each of the three fields at $x$ is paired with one of the three fields at $y$. There are $3!$ such pairings. Thus the net coefficient is

$$
\frac{(-ig)^2}{2!(3!)^2}3!
=
\frac{(-ig)^2}{12}.
$$

The graph amplitude is therefore divided by $12$, so $S_\Gamma=12$.

</details>

### Exercise 3: Vacuum-bubble cancellation

Let $C$ denote the sum of connected vacuum bubbles and $A$ the sum of diagrams connected to an operator insertion $\mathcal O$. Show that vacuum bubbles cancel in the normalized correlator.

<details>
<summary><strong>Solution</strong></summary>

Disconnected vacuum components exponentiate, so the numerator has the schematic form

$$
A e^C,
$$

while the denominator is

$$
e^C.
$$

Therefore

$$
\frac{Ae^C}{e^C}=A.
$$

The normalized correlator contains only diagrams connected to at least one insertion in $\mathcal O$.

</details>

### Exercise 4: Constant Lagrangian shift

Show that shifting $\mathcal L\mapsto\mathcal L-C$ multiplies the vacuum functional by

$$
e^{-iC\int d^dx}.
$$

<details>
<summary><strong>Solution</strong></summary>

The action shifts as

$$
S=\int d^dx\,\mathcal L
\quad\longmapsto\quad
S'=\int d^dx\,(\mathcal L-C)
=S-C\int d^dx.
$$

The path-integral weight therefore becomes

$$
e^{iS'}=e^{iS}e^{-iC\int d^dx}.
$$

Since the extra factor is field independent, it factors out of the path integral:

$$
Z[0]\mapsto e^{-iC\int d^dx}Z[0].
$$

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§9, 19, and 21, for generating functionals, connected diagrams, all-order perturbation theory, and the quantum action.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 8, 28, and 32, for Wick diagrams, functional integration, and connected generating functionals.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 6 and 9, for Feynman rules and path-integral normalization.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 7 and 14, for Feynman rules and generating functionals.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 1 and 7, for Gaussian integrals, connected diagrams, and functional methods.

## Version history

- **2026-06-12:** Initial polished draft. Added vacuum-bubble exponentiation, cancellation in normalized correlators, $\phi^4$ and $\phi^3$ examples, vacuum-energy interpretation, solved exercises, and a compact vacuum-bubble figure.
