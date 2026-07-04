---
title: "Perturbative Expansion"
description: "How interactions are expanded around a free QFT, producing Dyson series, source-functional diagrams, vacuum-bubble cancellation, and the first scalar diagrammatic terms."
sidebar:
  label: "Perturbative Expansion"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§9–10 and §19; Coleman 2019, chs. 7–8 and 28; Weinberg 1995, Vol. I, chs. 6 and 9; Schwartz 2014, ch. 7; Zinn-Justin 2021, ch. 7"
topics:
  - perturbative expansion
  - Dyson series
  - Wick theorem
  - source functional
  - Feynman diagrams
  - vacuum bubbles
  - scalar field theory
canonicalTopics:
  - perturbative-expansion
  - dyson-wick-expansion
  - interaction-expansion
researchStatus:
  established:
    - "The Dyson expansion, source-functional interaction expansion, Wick contraction rules, vacuum-bubble cancellation in normalized correlators, and scalar diagrammatic examples are textbook-standard perturbative QFT."
  active:
    - "The convergence, summability, resurgence, renormalon structure, and nonperturbative completion of perturbative series are active topics beyond this introductory page."
---

## Summary

The perturbative expansion is the method of computing an interacting QFT by expanding around a solvable free QFT. In the operator language, the interaction-picture scattering operator is formally

$$
S
=
T\exp\left[-i\int_{-\infty}^{\infty}dt\,H_I(t)\right],
$$

and normalized time-ordered correlators are computed as

$$
\langle T\mathcal O\rangle
=
\frac{
\langle0|T\{\mathcal O S\}|0\rangle_0
}{
\langle0|S|0\rangle_0
}.
$$

Here $\langle\cdots\rangle_0$ means expectation value in the free theory. Expanding $S$ gives powers of the interaction. Wick's theorem then reduces each free-theory time-ordered product to contractions, and each contraction is a Feynman propagator.

In the path-integral language, the same idea is packaged as

$$
Z[J]
=
\frac{
\exp\left\{iS_{\mathrm{int}}\!\left[\frac{1}{i}\frac{\delta}{\delta J}\right]\right\}Z_0[J]
}{
\left.\exp\left\{iS_{\mathrm{int}}\!\left[\frac{1}{i}\frac{\delta}{\delta J}\right]\right\}Z_0[J]\right|_{J=0}
}.
$$

This page explains what this formula means, why diagrams appear, how vacuum bubbles cancel, and how the first nontrivial scalar terms are checked by explicit Wick counting.

:::note[Main lesson]
Perturbation theory is not “particles doing things in a diagram.” It is organized Gaussian bookkeeping. Vertices come from expanding the interaction; internal lines come from free contractions; loop integrals come from momenta not fixed by conservation laws.
:::

## Prerequisites

You should know the scattering conventions in [Conventions and Notation](/perturbative-qft/conventions/), the interaction-picture [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/), [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/), the [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), and the Foundations page [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/).

The path-integral version uses [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/) and [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/). Those pages are useful but not required for the operator-first route.

## Core idea

A perturbative QFT calculation begins by splitting the action into a free part and an interaction part,

$$
S[\phi]=S_0[\phi]+S_{\mathrm{int}}[\phi].
$$

The free part is chosen because we can compute its propagators exactly. The interaction part is treated as a formal expansion. A term with $V$ interaction insertions becomes a term with $V$ vertices. Wick contractions of the free fields connect those vertices and external insertions by propagators.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Flowchart of the perturbative expansion from action splitting to observables](/figures/perturbative-qft/perturbative-expansion-flow.svg)

<figcaption>

The perturbative expansion splits the action into a free Gaussian part and an interaction, expands the interaction, evaluates free contractions, removes vacuum bubbles by normalization, and then interprets the resulting diagrams as correlators, amputated objects, or on-shell amplitudes depending on the calculation.

</figcaption>
</figure>

The key dictionary is:

| Algebraic object | Diagrammatic object | Check |
|---|---|---|
| Free two-point function $D_F(x-y)$ | Propagator line | Does it invert the free kinetic operator with the chosen $i\epsilon$ prescription? |
| Interaction insertion $iS_{\mathrm{int}}$ | Vertex | Does its factor match the sign and factorials in the Lagrangian? |
| Repeated integration over insertion points | Vertex-position integral | Does translation invariance later give momentum conservation? |
| Wick-contraction multiplicity | Symmetry factor | Does the diagram overcount identical contractions? |
| Denominator $\langle0|S|0\rangle_0$ or $Z[0]$ | Vacuum-bubble cancellation | Do disconnected vacuum diagrams cancel from normalized correlators? |
| Unfixed internal momentum | Loop integral | Does the loop count agree with topology? |

The same diagram can mean different things in different contexts. For a Green function, external lines are propagators attached to operator insertions. For an amputated correlator, those external propagators are removed. For an S-matrix element, external particles are placed on shell and normalized according to LSZ.

## Setup and conventions

We work in flat four-dimensional Minkowski spacetime with the qft.org mostly-minus metric. Plane waves are written as $e^{-ip\cdot x}$, and the scalar Feynman propagator is

$$
D_F(x-y)
=
\int\frac{d^4p}{(2\pi)^4}
\frac{i\,e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

The running example is real scalar $\phi^4$ theory,

$$
\mathcal L
=
\frac12\partial_\mu\phi\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\lambda}{4!}\phi^4.
$$

Thus

$$
\mathcal L_0
=
\frac12\partial_\mu\phi\partial^\mu\phi
-
\frac12m^2\phi^2,
\qquad
\mathcal L_{\mathrm{int}}
=-\frac{\lambda}{4!}\phi^4.
$$

For this non-derivative scalar interaction, the interaction Hamiltonian density is

$$
\mathcal H_I=\frac{\lambda}{4!}\phi^4=-\mathcal L_{\mathrm{int}}.
$$

For derivative interactions, constrained systems, and gauge theories, $\mathcal H_I=-\mathcal L_{\mathrm{int}}$ can fail or require care. The safe statement is always the one derived from the chosen operator or path-integral formulation.

## Operator form: the Dyson expansion

The interaction-picture evolution operator obeys

$$
i\frac{\partial}{\partial t}U_I(t,t_0)=H_I(t)U_I(t,t_0),
\qquad
U_I(t_0,t_0)=1.
$$

Its formal solution is the time-ordered exponential

$$
U_I(t,t_0)
=
T\exp\left[-i\int_{t_0}^{t}dt'\,H_I(t')\right].
$$

Taking $t_0\to-\infty$ and $t\to+\infty$ gives the formal scattering operator

$$
S
=
T\exp\left[-i\int_{-\infty}^{\infty}dt\,H_I(t)\right].
$$

In a local theory, this can be written as

$$
S
=
T\exp\left[-i\int d^4z\,\mathcal H_I(z)\right].
$$

For $\phi^4$ theory,

$$
S
=
T\exp\left[-i\frac{\lambda}{4!}\int d^4z\,\phi(z)^4\right].
$$

Expanding the exponential gives

$$
S
=
\sum_{V=0}^\infty
\frac{1}{V!}
\left(-i\frac{\lambda}{4!}\right)^V
\int d^4z_1\cdots d^4z_V\,
T\{\phi(z_1)^4\cdots\phi(z_V)^4\}.
$$

The integer $V$ counts interaction insertions. In diagram language, it counts quartic vertices.

For a time-ordered operator product $\mathcal O$, the normalized interacting correlator is

$$
\langle T\mathcal O\rangle
=
\frac{
\langle0|T\{\mathcal O S\}|0\rangle_0
}{
\langle0|S|0\rangle_0
}.
$$

The denominator is essential. It removes vacuum bubbles that are disconnected from the operator insertions. Dropping it too early is one of the classic ways to manufacture fake disconnected terms.

:::caution[Asymptotic caveat]
The expression with time limits $\pm\infty$ assumes that the scattering problem is well defined. A more careful treatment uses adiabatic switching, wave packets, stable asymptotic particles, and eventually LSZ reduction. This page focuses on the perturbative bookkeeping, not the full mathematical definition of scattering.
:::

## Path-integral form: expanding the interaction

The same expansion can be generated from sources. Define the normalized Lorentzian generating functional

$$
Z[J]
=
\frac{1}{\mathcal N}
\int\mathcal D\phi\,
\exp\left\{iS_0[\phi]+iS_{\mathrm{int}}[\phi]+i\int d^4x\,J(x)\phi(x)\right\},
\qquad
Z[0]=1.
$$

The free generating functional is

$$
Z_0[J]
=
\exp\left[-\frac12\int d^4x\,d^4y\,J(x)D_F(x-y)J(y)\right].
$$

Because

$$
\frac{1}{i}\frac{\delta}{\delta J(x)}
\exp\left[i\int d^4y\,J(y)\phi(y)\right]
=
\phi(x)
\exp\left[i\int d^4y\,J(y)\phi(y)\right],
$$

we can represent powers of $\phi$ by functional derivatives with respect to $J$. Therefore

$$
Z[J]
=
\frac{
\exp\left\{iS_{\mathrm{int}}\!\left[\frac{1}{i}\frac{\delta}{\delta J}\right]\right\}Z_0[J]
}{
\left.\exp\left\{iS_{\mathrm{int}}\!\left[\frac{1}{i}\frac{\delta}{\delta J}\right]\right\}Z_0[J]\right|_{J=0}
}.
$$

For $\phi^4$ theory,

$$
iS_{\mathrm{int}}\!\left[\frac{1}{i}\frac{\delta}{\delta J}\right]
=
-i\frac{\lambda}{4!}\int d^4z\,
\left(\frac{1}{i}\frac{\delta}{\delta J(z)}\right)^4.
$$

This expression is the source-functional version of the Dyson expansion. The Gaussian $Z_0[J]$ supplies propagators. The functional derivative operator supplies vertices. The denominator enforces $Z[0]=1$ and cancels vacuum bubbles.

## What an order means

Perturbation theory is an expansion in a chosen interaction parameter, not automatically an expansion in loops. In $\phi^4$ theory, a term of order $\lambda^V$ has $V$ quartic vertices, but its loop number depends on how the contractions connect those vertices.

For a connected graph,

$$
L=I-V+1,
$$

where $L$ is the number of independent loop momenta, $I$ is the number of internal lines, and $V$ is the number of vertices.

| Example in scalar theory | Coupling order | Loop order |
|---|---:|---:|
| Four-point contact diagram in $\phi^4$ | $\lambda$ | tree |
| Two-point tadpole in $\phi^4$ | $\lambda$ | one loop |
| Four-point fish diagram in $\phi^4$ | $\lambda^2$ | one loop |
| Four-point tree exchange in $\phi^3$ | $g^2$ | tree |
| Two-point sunset in $\phi^4$ | $\lambda^2$ | two loops |

So “first order in the coupling” and “tree level” are not synonyms. The interaction, external legs, and contraction topology decide the loop order.

## Worked example: the first scalar two-point correction

Consider the normalized two-point function in $\phi^4$ theory,

$$
G_2(x,y)=\langle T\phi(x)\phi(y)\rangle.
$$

Using the operator expansion,

$$
G_2(x,y)
=
\frac{
\left\langle0\left|T\left\{\phi(x)\phi(y)
\exp\left[-i\frac{\lambda}{4!}\int d^4z\,\phi(z)^4\right]
\right\}\right|0\right\rangle_0
}{
\left\langle0\left|T\exp\left[-i\frac{\lambda}{4!}\int d^4z\,\phi(z)^4\right]\right|0\right\rangle_0
}.
$$

Expand to first order in $\lambda$:

$$
\begin{aligned}
G_2(x,y)
&=D_F(x-y)\\
&\quad
-i\frac{\lambda}{4!}\int d^4z\,
\left[
\langle0|T\{\phi(x)\phi(y)\phi(z)^4\}|0\rangle_0
-D_F(x-y)\langle0|T\{\phi(z)^4\}|0\rangle_0
\right]
+O(\lambda^2).
\end{aligned}
$$

The subtraction term comes from expanding the denominator. It cancels the part of the numerator in which $\phi(x)$ contracts with $\phi(y)$ while all four fields at $z$ contract among themselves. That disconnected piece is a vacuum bubble multiplying the free two-point function.

The connected first-order term contracts one field at $z$ with $\phi(x)$, one field at $z$ with $\phi(y)$, and the remaining two fields at $z$ with each other. There are

$$
4\times3=12
$$

such contractions. Therefore

$$
-i\frac{\lambda}{4!}\times 12=-\frac{i\lambda}{2},
$$

and the connected tadpole correction is

$$
G_{2,\mathrm{conn}}^{(1)}(x,y)
=
-\frac{i\lambda}{2}\int d^4z\,
D_F(x-z)D_F(y-z)D_F(0).
$$

The factor $D_F(0)$ is singular in the continuum theory. That is not a surprise; it is the first sign that loop diagrams need regularization and, in a renormalized theory, counterterms.

## From position space to momentum space

The position-space expression above still has explicit vertex integration. Momentum-space rules arise by Fourier transforming each propagator. For example,

$$
D_F(x-z)
=
\int\frac{d^4p}{(2\pi)^4}
\frac{i\,e^{-ip\cdot(x-z)}}{p^2-m^2+i\epsilon}.
$$

Integrating over the vertex position $z$ produces a momentum-conservation delta function. For a general vertex,

$$
\int d^4z\,
\exp\left[-iz\cdot(p_1+\cdots+p_r)\right]
=
(2\pi)^4\delta^{(4)}(p_1+\cdots+p_r).
$$

This is why momentum-space Feynman rules attach momentum conservation to vertices and leave an integral over each independent loop momentum.

In the tadpole correction, the internal contraction at the same point contributes a loop integral,

$$
D_F(0)
=
\int\frac{d^4\ell}{(2\pi)^4}
\frac{i}{\ell^2-m^2+i\epsilon}.
$$

This integral is ultraviolet divergent in four dimensions. The perturbative expansion tells us which integral occurs. Regularization and renormalization tell us how to define and interpret it.

## Connected diagrams and exponentiation

Full correlators include disconnected pieces. Connected correlators are generated by the logarithm of the source functional. With the qft.org convention

$$
Z[J]=e^{iW[J]},
$$

$W[J]$ generates connected correlators.

This is not merely a formal convenience. It expresses the linked-cluster structure of perturbation theory: disconnected diagrams exponentiate, and taking the logarithm keeps the connected part.

For ordinary normalized correlators in flat spacetime, vacuum bubbles cancel because the same vacuum factor multiplies numerator and denominator. For vacuum energy, finite-temperature partition functions, gravity, and effective actions, vacuum diagrams can become physically important again. “Vacuum bubbles cancel” is therefore a statement about a specific normalized observable, not a universal banishment spell.

## How to check a perturbative term

A reliable perturbative calculation should pass several cheap tests before any heroic algebra begins.

| Check | What it catches |
|---|---|
| Coupling order | Missing or extra vertices. |
| Field counting | Impossible Wick contractions. |
| Symmetry factor | Overcounting identical contractions. |
| Dimensions | Missing powers of momentum, mass, or coupling. |
| Momentum conservation | Wrong Fourier signs or vertex flow conventions. |
| Loop count | Missing integration variables or delta functions. |
| External-leg status | Confusion between correlators, amputated correlators, and amplitudes. |
| Vacuum normalization | Disconnected vacuum bubbles contaminating normalized correlators. |

These checks are not busywork. They are how professional calculations avoid becoming decorative nonsense.

## Common pitfalls

**Confusing the sign of the interaction.** For $\mathcal L_{\mathrm{int}}=-\lambda\phi^4/4!$, the vertex factor is $-i\lambda$. The sign comes from $iS_{\mathrm{int}}$, or equivalently from $-i\int H_I$ when $H_I=-L_{\mathrm{int}}$.

**Treating the denominator as optional.** The denominator in normalized correlators cancels vacuum bubbles. Omitting it changes the object being computed.

**Equating coupling order with loop order.** A term of first order in $\lambda$ can be a tree diagram or a one-loop diagram, depending on the contraction pattern.

**Forgetting that $D_F(0)$ is singular.** A loop that begins and ends at the same vertex is a real loop integral, not a harmless constant.

**Using Feynman rules without knowing the target.** Correlators include external propagators. Scattering amplitudes use amputated, on-shell external states. Same drawing style; different object.

**Assuming perturbation theory converges.** Perturbative QFT usually gives asymptotic series. A few terms can be extremely predictive, but the expansion is not generally a convergent Taylor series defining the full theory.

## Relations to other pages

- [Roadmap](/perturbative-qft/roadmap/) explains where this page sits in the first-pass route through the volume.
- [Conventions and Notation](/perturbative-qft/conventions/) fixes the signs, Fourier phases, propagator denominators, state normalization, and amplitude normalization used later.
- [Dyson Series](/foundations/interactions-and-wick-expansion/dyson-series/) derives the time-ordered exponential used here.
- [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) is the combinatorial engine that turns free-field products into contractions.
- [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/) gives the foundational diagrammatic dictionary that this page specializes for perturbative calculations.
- [Connected Diagrams](/foundations/interactions-and-wick-expansion/connected-diagrams/) develops the linked-cluster logic behind $Z[J]=e^{iW[J]}$.
- [UV Divergences Preview](/foundations/interactions-and-wick-expansion/uv-divergences-preview/) explains why loop integrals such as $D_F(0)$ need regularization.

## Research status

The perturbative expansion described here is textbook-standard. The main formulas are formal until a regulator, normalization prescription, and physical observable are specified. The deeper status of perturbation theory as an asymptotic expansion, its large-order behavior, Borel summability, renormalons, resurgence, and its relation to nonperturbative saddles are active research topics that belong to later advanced pages.

## Exercises

### Exercise 1: The quartic vertex sign

Starting from

$$
\mathcal L_{\mathrm{int}}=-\frac{\lambda}{4!}\phi^4,
$$

show that the first-order interaction factor in the path integral is

$$
-i\frac{\lambda}{4!}\int d^4z\,\phi(z)^4.
$$

Then explain why the four-point contact vertex factor is $-i\lambda$ for labeled external fields.

<details>
<summary><strong>Solution</strong></summary>

The interaction action is

$$
S_{\mathrm{int}}
=\int d^4z\,\mathcal L_{\mathrm{int}}
=-\frac{\lambda}{4!}\int d^4z\,\phi(z)^4.
$$

The Lorentzian path-integral weight contains $e^{iS}$, so the first-order interaction factor is

$$
iS_{\mathrm{int}}
=-i\frac{\lambda}{4!}\int d^4z\,\phi(z)^4.
$$

For a four-point contact term with labeled external insertions, the four fields at $z$ can be contracted with the four external fields in $4!$ ways. This cancels the $1/4!$ in the interaction, leaving the local vertex factor

$$
-i\lambda.
$$

</details>

### Exercise 2: Vacuum bubble cancellation at first order

In the two-point function of $\phi^4$ theory, show that the disconnected contribution

$$
D_F(x-y)\langle0|T\{\phi(z)^4\}|0\rangle_0
$$

is canceled by the denominator of the normalized correlator at order $\lambda$.

<details>
<summary><strong>Solution</strong></summary>

Write

$$
N=N_0+\lambda N_1+O(\lambda^2),
\qquad
D=1+\lambda D_1+O(\lambda^2),
$$

where $N$ is the numerator and $D$ is the denominator. Since

$$
\frac{N}{D}=N_0+\lambda(N_1-N_0D_1)+O(\lambda^2),
$$

any part of $N_1$ equal to $N_0D_1$ cancels.

Here

$$
N_0=D_F(x-y),
$$

and

$$
D_1=-\frac{i}{4!}\int d^4z\,\langle0|T\{\phi(z)^4\}|0\rangle_0
$$

after factoring out $\lambda$. The disconnected numerator term is exactly $N_0D_1$, so it is removed by the normalization. Only contractions connected to the external insertions remain.

</details>

### Exercise 3: Count the tadpole contractions

For the first-order correction to $G_2(x,y)$ in $\phi^4$ theory, count the contractions in which $\phi(x)$ and $\phi(y)$ each connect to the interaction point $z$, while the remaining two fields at $z$ contract with each other.

<details>
<summary><strong>Solution</strong></summary>

There are four choices for the field at $z$ contracted with $\phi(x)$. After that, there are three choices for the field at $z$ contracted with $\phi(y)$. The remaining two fields at $z$ must contract with each other. Thus there are

$$
4\times3=12
$$

contractions. Multiplying by the interaction coefficient gives

$$
-i\frac{\lambda}{4!}\times12
=-\frac{i\lambda}{2}.
$$

Therefore

$$
G_{2,\mathrm{conn}}^{(1)}(x,y)
=
-\frac{i\lambda}{2}\int d^4z\,
D_F(x-z)D_F(y-z)D_F(0).
$$

</details>

### Exercise 4: Coupling order versus loop order

In $\phi^4$ theory, the one-loop four-point fish diagram has two quartic vertices connected by two internal lines. Use

$$
L=I-V+1
$$

for a connected graph to find its loop order and coupling order.

<details>
<summary><strong>Solution</strong></summary>

The fish diagram has

$$
V=2,
\qquad
I=2.
$$

Therefore

$$
L=I-V+1=2-2+1=1.
$$

It is a one-loop diagram. Since each quartic vertex contributes one power of $\lambda$, its coupling order is

$$
\lambda^2.
$$

So this graph is order $\lambda^2$ but one loop.

</details>

### Exercise 5: Source derivatives generate fields

Verify that

$$
\frac{1}{i}\frac{\delta}{\delta J(x)}
\exp\left[i\int d^4y\,J(y)\phi(y)\right]
=
\phi(x)
\exp\left[i\int d^4y\,J(y)\phi(y)\right].
$$

Use this identity to explain the operator

$$
\exp\left[-i\frac{\lambda}{4!}\int d^4z\,
\left(\frac{1}{i}\frac{\delta}{\delta J(z)}\right)^4\right]
$$

in the $\phi^4$ generating functional.

<details>
<summary><strong>Solution</strong></summary>

The functional derivative brings down the variation of the exponent:

$$
\frac{\delta}{\delta J(x)}
\left[i\int d^4y\,J(y)\phi(y)\right]
=i\phi(x).
$$

Therefore

$$
\frac{\delta}{\delta J(x)}e^{i\int J\phi}
=i\phi(x)e^{i\int J\phi},
$$

and multiplying by $1/i$ gives the desired identity.

In $\phi^4$ theory, each factor

$$
\left(\frac{1}{i}\frac{\delta}{\delta J(z)}\right)^4
$$

inserts four fields $\phi(z)^4$. The exponential sums over any number of such interaction insertions, with the coefficient $-i\lambda/4!$ at each vertex.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, §§9–10 and §19, for path-integral perturbation theory, scattering amplitudes, Feynman rules, and perturbation theory to all orders.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 7–8, for the interaction picture, Dyson's formula, Wick diagrams, and connected/disconnected diagram logic.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 7, for Lagrangian, Hamiltonian, and momentum-space derivations of Feynman rules.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 6 and 9, for the covariant Feynman-rule derivation and path-integral formulation.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. I.7–I.9 and appendix C, for a compact diagrammatic introduction.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, ch. 7, for algebraic perturbation theory, connected functions, vertex functions, and loop expansion.

## Version history

- **2026-06-11:** Initial standardized page with scalar $\phi^4$ examples, source-functional form, vacuum-bubble cancellation, figure, and solved exercises.
