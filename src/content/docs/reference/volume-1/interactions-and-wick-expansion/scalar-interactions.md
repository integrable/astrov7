---
title: "Scalar Interactions"
description: "The first concrete interacting QFT examples: cubic and quartic scalar interactions, vertex factors, tree diagrams, symmetry factors, source-functional rules, and the first glimpse of loops."
sidebar:
  label: "Scalar Interactions"
  order: 5
---

## Summary

Scalar interactions are the simplest laboratory for perturbative QFT. A real scalar field can be given local polynomial interactions such as

$$
\mathcal L_{\rm int}
=-\frac{g}{3!}\phi^3-\frac{\lambda}{4!}\phi^4.
$$

With the qft.org mostly-minus convention and the scalar propagator

$$
D_F(p)=\frac{i}{p^2-m^2+i\epsilon},
$$

the corresponding momentum-space vertex factors are

$$
\boxed{\phi^3\text{ vertex: }-ig},
\qquad
\boxed{\phi^4\text{ vertex: }-i\lambda}.
$$

The factorials in the Lagrangian are not decoration. They cancel the number of Wick contractions among identical fields, leaving clean vertex factors. In $\phi^3$ theory, the first four-point scattering contribution comes from two cubic vertices joined by an internal propagator. In $\phi^4$ theory, there is already a four-point contact diagram at first order.

This page is the first place where the formal machinery from the previous pages becomes a working calculational language. The interaction picture supplies the Dyson expansion, Wick's theorem turns products of free fields into propagators, and Feynman diagrams package the resulting combinatorics. Coleman introduces perturbation theory through simple model field theories before deriving Wick and Feynman diagrams; Srednicki develops the early Feynman rules in scalar theories; Zee uses scalar fields as the cleanest first diagrammatic example; Weinberg gives the general covariant rule-making framework (Coleman 2019, chs. 8 and 10; Srednicki 2007, §§9–10; Zee 2010, ch. I.7; Weinberg 1995, Vol. I, ch. 6).

## Prerequisites

You should know [Interaction Picture](/foundations/interactions-and-wick-expansion/interaction-picture/), [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/), [Wick's Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/), [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/), [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/), and [Free Field Summary](/foundations/free-fields/free-field-summary/).

## Core idea

A local interaction term is a local vertex. Propagators connect vertices. External lines attach operator insertions or asymptotic particles.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Scalar cubic and quartic interaction vertices](/figures/foundations/scalar-interaction-vertices.svg)

<figcaption>

Cubic and quartic scalar interactions produce local vertices. The factors $1/3!$ and $1/4!$ in the Lagrangian cancel the Wick-contraction multiplicities for identical scalar fields, giving the simple vertex factors $-ig$ and $-i\lambda$.

</figcaption>
</figure>

The simplest dictionary is

```txt
local monomial in ℒ_int     → vertex;
coefficient in ℒ_int        → vertex factor after multiplying by i;
free two-point contraction  → propagator;
spacetime integral          → momentum-conserving delta function;
unfixed internal momentum   → loop integral.
```

For non-derivative scalar interactions, that dictionary is almost embarrassingly efficient. It is also where one learns the good habits that later prevent disasters in spinor and gauge theories.

:::note[Assumptions]
This page uses ordinary perturbation theory around the free scalar vacuum. The interaction is treated as small, fields are interaction-picture free fields inside the Dyson expansion, and all formal products are assumed to be regulated when ultraviolet singularities appear. Nonperturbative questions such as vacuum stability, triviality, and exact existence are outside the scope of this foundations page.
:::

## The interaction Hamiltonian sign

For a real scalar field with no derivative interactions,

$$
\mathcal L=\mathcal L_0+\mathcal L_{\rm int},
\qquad
\mathcal L_0
=\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2,
$$

the interaction Hamiltonian density is

$$
\mathcal H_I=-\mathcal L_{\rm int}.
$$

The Dyson factor is therefore

$$
T\exp\left[-i\int d^4x\,\mathcal H_I(x)\right]
=
T\exp\left[i\int d^4x\,\mathcal L_{\rm int}(x)\right].
$$

This is why a term

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4
$$

produces the vertex factor

$$
i\left(-\lambda\right)=-i\lambda.
$$

The same logic gives $-ig$ for $\mathcal L_{\rm int}=-g\phi^3/3!$.

The sign rule is easy to remember but easy to misuse. For derivative interactions, constrained systems, and gauge-fixed theories, the interaction Hamiltonian need not be just minus the interaction Lagrangian. In those cases, the path-integral derivation is often cleaner, and the canonical derivation must be handled with more care.

## Cubic scalar interaction

Take

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{g}{3!}\phi^3.
$$

The cubic vertex has three scalar legs and vertex factor

$$
\boxed{-ig}.
$$

At second order in perturbation theory, cubic interactions produce four-point processes by joining two cubic vertices with one internal propagator. For four external scalar particles with all momenta taken incoming, define

$$
s=(p_1+p_2)^2,
\qquad
 t=(p_1+p_3)^2,
\qquad
 u=(p_1+p_4)^2,
$$

where the precise signs in $t$ and $u$ depend on whether one uses the all-incoming convention or the incoming/outgoing convention. The three tree exchange diagrams give

$$
i\mathcal M_{\phi^3}^{\rm tree}
=(-ig)^2\left[
\frac{i}{s-m^2+i\epsilon}
+\frac{i}{t-m^2+i\epsilon}
+\frac{i}{u-m^2+i\epsilon}
\right].
$$

Equivalently,

$$
\boxed{
\mathcal M_{\phi^3}^{\rm tree}
=-g^2\left[
\frac{1}{s-m^2+i\epsilon}
+\frac{1}{t-m^2+i\epsilon}
+\frac{1}{u-m^2+i\epsilon}
\right].
}
$$

This expression is more important pedagogically than phenomenologically. It shows how an internal line carries momentum that is not independently observed. It also shows how different channels arise from different pairings of the same external legs.

A pure real $\phi^3$ potential is not bounded below. That does not stop it from being useful as a perturbative toy model, especially in dimensions where it has convenient power counting, but it is not a stable standalone classical potential in four dimensions. Stability is not a cosmetic issue; it is part of what it means for a QFT to define a sensible vacuum.

## Quartic scalar interaction

The standard first interacting scalar example in four spacetime dimensions is

$$
\mathcal L
=\frac12\partial_\mu\phi\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4.
$$

The quartic vertex has four scalar legs and vertex factor

$$
\boxed{-i\lambda}.
$$

At tree level, the four-point scattering amplitude is simply

$$
i\mathcal M_{\phi^4}^{\rm tree}=-i\lambda,
\qquad
\boxed{\mathcal M_{\phi^4}^{\rm tree}=-\lambda.}
$$

This is the contact diagram: all four external scalar lines meet at one spacetime point. In position space, the first connected contribution to the four-point Green function is

$$
G^{(1)}_{4,{\rm conn}}(x_1,x_2,x_3,x_4)
=(-i\lambda)\int d^4z\,
\prod_{a=1}^4 D_F(x_a-z).
$$

The contact term is local in the vertex position $z$, but the external points are connected to $z$ by propagators. Locality of the interaction does not mean the correlator vanishes unless all external points coincide. It means the fundamental interaction insertion is local.

## Why the factorials are there

For identical fields, the convenient convention is

$$
\mathcal L_{\rm int}
=-\sum_{n\ge 3}\frac{g_n}{n!}\phi^n.
$$

The $n!$ cancels the number of ways to contract $n$ identical fields at the vertex with $n$ labeled external or internal half-edges. Then the $n$-point scalar vertex is simply

$$
\boxed{-ig_n.}
$$

If instead one writes

$$
\mathcal L_{\rm int}=-a\phi^4,
$$

then the quartic vertex factor is

$$
\boxed{-i(4!)a.}
$$

This is not a different physics convention; it is a different definition of the coupling. The safest habit is to define the coupling with the factorial included when the fields are identical.

For mixed fields, only identical repetitions get factorials. For example,

$$
\mathcal L_{\rm int}=-\frac{g}{2}\chi\phi^2
$$

has one $\chi$ leg and two identical $\phi$ legs. The vertex factor is

$$
\boxed{-ig.}
$$

The factor $1/2$ cancels the two possible contractions of the identical $\phi$ fields.

## Scalar interactions from the source functional

The path-integral generating functional gives the same rules in one line. For $\phi^4$ theory,

$$
Z[J]
=\frac{1}{\mathcal N}
\int\mathcal D\phi\,
\exp\left\{i\int d^4x\left[
\mathcal L_0-\frac{\lambda}{4!}\phi^4+J\phi
\right]\right\}.
$$

Formally replace each field in the interaction by a source derivative:

$$
\phi(x)\longrightarrow \frac{1}{i}\frac{\delta}{\delta J(x)}.
$$

Then

$$
Z[J]
=\exp\left[-i\frac{\lambda}{4!}\int d^4x
\left(\frac{1}{i}\frac{\delta}{\delta J(x)}\right)^4
\right]Z_0[J],
$$

where

$$
Z_0[J]
=\exp\left[-\frac12\int d^4x\,d^4y\,
J(x)D_F(x-y)J(y)\right]
$$

in the normalized free theory and qft.org's $D_F$ convention. Expanding the interaction exponential and differentiating $Z_0[J]$ reproduces exactly the same Wick contractions and Feynman diagrams.

This source-functional form is often the shortest way to derive scalar Feynman rules. The operator derivation explains what is being time-ordered. The path-integral derivation makes the combinatorics and covariance almost automatic.

## Tree diagrams and loops

For a connected scalar diagram, let

```txt
V = number of interaction vertices,
I = number of internal lines,
E = number of external lines,
L = number of independent loop momenta.
```

For a connected diagram,

$$
\boxed{L=I-V+1.}
$$

Tree diagrams have $L=0$. They contain no loop-momentum integration. In tree-level scalar theory, all internal momenta are fixed by momentum conservation and the external momenta.

Loop diagrams have $L>0$. Each loop brings an integration

$$
\int\frac{d^4\ell}{(2\pi)^4}.
$$

For example, the one-loop correction to the four-point function in $\phi^4$ theory has two quartic vertices and two internal lines connecting them, so

$$
L=2-2+1=1.
$$

The resulting loop integral is ultraviolet divergent in four dimensions. Foundations does not yet renormalize it. The point here is simply to see where loop integrals first enter.

## First look at mass dimensions

In four spacetime dimensions, the action is dimensionless in units $\hbar=c=1$, and the Lagrangian density has mass dimension four. Since

$$
\frac12\partial_\mu\phi\partial^\mu\phi
$$

has dimension four, the scalar field has dimension

$$
\boxed{[\phi]=1.}
$$

Therefore

$$
[g]=1,
\qquad
[\lambda]=0
$$

for $g\phi^3/3!$ and $\lambda\phi^4/4!$ in four dimensions.

This is the first hint of the renormalization-group classification:

```txt
φ³ in four dimensions: coupling has positive mass dimension;
φ⁴ in four dimensions: coupling is dimensionless;
φ⁶ in four dimensions: coupling has negative mass dimension.
```

Do not overread this yet. Power counting is not the full story, and the meaning of ultraviolet divergences belongs in the renormalization group section. But it is useful to notice early that different interactions have different dimensional status.

## Symmetries restrict interactions

A real scalar theory may have a $\mathbb Z_2$ symmetry

$$
\phi\mapsto -\phi.
$$

If this symmetry is imposed, odd powers are forbidden:

$$
\phi^3,\phi^5,\ldots \quad \text{not allowed.}
$$

The simplest interacting polynomial potential then begins with $\phi^4$.

For a complex scalar with global $U(1)$ symmetry

$$
\Phi\mapsto e^{i\alpha}\Phi,
$$

interaction terms must have equal numbers of $\Phi$ and $\Phi^\dagger$. The basic quartic interaction is

$$
\mathcal L_{\rm int}=-\frac{\lambda}{2}(\Phi^\dagger\Phi)^2,
$$

where the factor convention varies by author. The associated diagrams carry charge-flow arrows: each vertex conserves the global charge.

This is the first gentle lesson of QFT model building: write every local term allowed by the symmetries and then ask which terms matter at the energy scale of interest.

## Position-space examples

The first-order correction to the two-point function in $\phi^4$ theory is

$$
\frac{-i\lambda}{4!}\int d^4z\,
\langle0|T\{\phi(x)\phi(y)\phi(z)^4\}|0\rangle_0.
$$

One connected contraction gives the tadpole correction:

$$
G_{2,{\rm tad}}(x,y)
=\frac{-i\lambda}{2}\int d^4z\,
D_F(x-z)D_F(y-z)D_F(0).
$$

The factor $1/2$ is a symmetry factor. It arises because the $12$ Wick contractions of the desired type do not fully cancel the $4!$ in the vertex.

At first order, the four-point contact correction is

$$
G_{4,{\rm conn}}^{(1)}(x_1,x_2,x_3,x_4)
=(-i\lambda)\int d^4z\,
D_F(x_1-z)D_F(x_2-z)D_F(x_3-z)D_F(x_4-z).
$$

At second order in $\phi^3$ theory, one four-point exchange channel is

$$
(-ig)^2\int d^4z\,d^4w\,
D_F(x_1-z)D_F(x_2-z)D_F(z-w)D_F(w-x_3)D_F(w-x_4),
$$

with the other channels obtained by distributing the external points differently.

These formulas are not usually the most compact way to compute scattering amplitudes, but they are the most honest way to see where the diagrams come from.

## Common pitfalls

### Confusing Lagrangian coefficients with vertex factors

The vertex factor is $i$ times the coefficient of the corresponding product of fields in $\mathcal L_{\rm int}$, after accounting for identical-field factorials. If the Lagrangian is written with nonstandard factorials, the vertex factor changes accordingly.

### Forgetting that diagrams compute different objects in different contexts

A tree diagram can contribute to a Green function, an amputated Green function, or an S-matrix element. The external-line treatment differs in these three cases. The scalar vertex factor is the same, but the object being computed is not.

### Treating internal lines as observed particles

An internal scalar line is a propagator. Its momentum is integrated over if it is part of a loop. It is not an on-shell observed particle unless a pole is isolated in a physical factorization limit.

### Hiding vacuum stability

A polynomial interaction may be useful perturbatively even if the corresponding classical potential is unbounded below. But a stable theory needs a stable vacuum or a carefully defined metastable setting.

### Assuming every allowed diagram is nonzero

Kinematics, symmetries, statistics, and conservation laws can make a diagram vanish. The diagrammatic topology is only the first filter.

## Relations to nearby pages

- [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) gives the general diagrammatic dictionary.
- [Connected Diagrams](/foundations/interactions-and-wick-expansion/connected-diagrams/) explains which diagrams survive after vacuum normalization and logarithms of source functionals.
- [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/) reorganizes diagrams into one-particle-irreducible building blocks.
- [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/) explains how scalar correlators become scattering amplitudes.
- [UV Divergences Preview](/foundations/interactions-and-wick-expansion/uv-divergences-preview/) explains what loop divergences are trying to tell us.

## Research status

Scalar perturbation theory is textbook-standard. The formulas here are formal until a regulator is supplied for coincident-point products and loop integrals. The interpretation of scalar interactions as effective interactions at a scale is stable modern QFT; the deeper questions of renormalization, continuum limits, and nonperturbative existence belong to later sections.

## Exercises

### Exercise 1: Vertex factor from a nonstandard quartic convention

Suppose

$$
\mathcal L_{\rm int}=-a\phi^4.
$$

What is the four-scalar vertex factor?

<details>
<summary><strong>Solution</strong></summary>

The coefficient of four identical fields is $-a$, but there is no $1/4!$ in the Lagrangian. The $4!$ contractions remain. Thus the vertex factor is

$$
\boxed{-i(4!)a=-24ia.}
$$

If one defines $\lambda=24a$, this becomes the standard $-i\lambda$.

</details>

### Exercise 2: Mixed cubic vertex

For

$$
\mathcal L_{\rm int}=-\frac{g}{2}\chi\phi^2,
$$

where $\phi$ and $\chi$ are real scalar fields, find the vertex factor.

<details>
<summary><strong>Solution</strong></summary>

There are two identical $\phi$ fields, so the conventional factor is $1/2!$. Wick contractions of the two $\phi$ fields cancel this factor. The vertex with one $\chi$ line and two $\phi$ lines has factor

$$
\boxed{-ig.}
$$

</details>

### Exercise 3: Tree-level φ⁴ scattering

Using the quartic interaction

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

write the tree-level contribution to $i\mathcal M$ for $2\to2$ scattering.

<details>
<summary><strong>Solution</strong></summary>

There is one contact diagram. The four-point vertex factor is $-i\lambda$, so

$$
\boxed{i\mathcal M=-i\lambda,\qquad \mathcal M=-\lambda.}
$$

</details>

### Exercise 4: Cubic exchange channels

In real scalar $\phi^3$ theory, why are there three tree-level four-point exchange channels?

<details>
<summary><strong>Solution</strong></summary>

Two cubic vertices joined by one internal line leave four external legs. To form an exchange graph, choose which two external legs attach to one vertex; the remaining two attach to the other vertex. For four identical external scalars, the inequivalent partitions into two pairs are

$$
(12|34),\qquad (13|24),\qquad (14|23).
$$

These are the $s$, $t$, and $u$ channels, up to the sign convention used for external momenta.

</details>

### Exercise 5: Loop number of a tadpole

The one-loop tadpole correction to the two-point function in $\phi^4$ theory has one quartic vertex and one internal line that begins and ends at that vertex. Use $L=I-V+1$ to find the number of loops.

<details>
<summary><strong>Solution</strong></summary>

For the connected tadpole graph,

$$
I=1,
\qquad
V=1.
$$

Therefore

$$
\boxed{L=I-V+1=1.}
$$

The loop integral is hidden in the factor

$$
D_F(0)=\int\frac{d^4\ell}{(2\pi)^4}\frac{i}{\ell^2-m^2+i\epsilon}.
$$

</details>

### Exercise 6: Symmetry forbids odd powers

Show that the symmetry $\phi\mapsto-\phi$ forbids $\phi^3$ but allows $\phi^4$.

<details>
<summary><strong>Solution</strong></summary>

Under $\phi\mapsto-\phi$,

$$
\phi^3\mapsto -\phi^3,
\qquad
\phi^4\mapsto \phi^4.
$$

A symmetric Lagrangian must be invariant, so $\phi^3$ is forbidden while $\phi^4$ is allowed.

</details>

## Sources and further reading

- G. C. Wick, “The Evaluation of the Collision Matrix,” *Physical Review* **80** (1950), 268–272.
- F. J. Dyson, “The S Matrix in Quantum Electrodynamics,” *Physical Review* **75** (1949), 1736–1755.
- R. P. Feynman, “Space-Time Approach to Quantum Electrodynamics,” *Physical Review* **76** (1949), 769–789.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 8 and 10, for model field theories, Wick diagrams, and the transition to Feynman diagrams.
- Mark Srednicki, *Quantum Field Theory*, §§9–10 and §19, for scalar path-integral perturbation theory and all-order diagrammatics.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 6, for the covariant derivation of Feynman rules.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. I.7 and appendix C, for a compact scalar-field introduction to diagrams and vertex rules.

## Version history

- **2026-05-23:** Initial qft.org page on cubic and quartic scalar interactions, vertex factors, tree-level diagrams, coupling dimensions, symmetry constraints, tadpoles, stability caveats, and the boundary with renormalization.
