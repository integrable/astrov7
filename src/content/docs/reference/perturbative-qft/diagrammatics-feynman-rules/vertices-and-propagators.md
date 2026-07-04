---
title: "Vertices and Propagators"
description: "How propagators and vertices are read from the quadratic and interaction terms of a QFT Lagrangian, including scalar, fermion, gauge-field, derivative, and counterterm examples."
sidebar:
  label: "Vertices and Propagators"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§9–10, §19, and §§42–45; Coleman 2019, chs. 8, 10, 21, and 28; Weinberg 1995, Vol. I, §§6.1–6.3 and ch. 9; Schwartz 2014, chs. 7 and 13–14; Zee 2010, app. C"
topics:
  - vertices
  - propagators
  - Feynman rules
  - scalar field theory
  - fermion propagators
  - derivative interactions
  - counterterm insertions
canonicalTopics:
  - vertices-and-propagators
  - feynman-rule-building-blocks
  - quadratic-kernel-inversion
researchStatus:
  established:
    - "The extraction of propagators from quadratic kernels and vertices from local interaction terms is textbook-standard perturbative QFT."
  active:
    - "Gauge-theory automation, higher-spin fields, derivative operator bases, effective-field-theory vertices, and multi-loop counterterm bookkeeping are active computational subjects developed later in the volume."
---

## Summary

Propagators and vertices are the two local building blocks of perturbative QFT.

A **propagator** is the inverse of the free quadratic operator, with the Feynman $i\epsilon$ prescription. For a real scalar field in qft.org conventions,

$$
\mathcal L_0
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2,
$$

so the momentum-space quadratic kernel is $p^2-m^2$, and the scalar propagator is

$$
\Delta_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

A **vertex** is the local factor obtained from the interaction action. For

$$
\mathcal L_{\mathrm{int}}
=
-\frac{g}{3!}\phi^3
-\frac{\lambda}{4!}\phi^4,
$$

the stripped scalar vertex factors are

$$
{\phi^3:\ -ig,}
\qquad
{\phi^4:\ -i\lambda.}
$$

The word **stripped** means that the vertex's own momentum-conservation delta function has been removed. In the unstripped convention, an $r$-point vertex also carries

$$
(2\pi)^4\delta^{(4)}\!\left(p_1+\cdots+p_r\right),
$$

with all momenta taken incoming. This page explains how these rules are extracted, how derivative interactions produce momentum factors, how indices and arrows enter, and how to avoid confusing internal propagators with external legs.

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Perturbative Expansion](/perturbative-qft/diagrammatics-feynman-rules/perturbative-expansion/), [Wick Theorem Recap](/perturbative-qft/diagrammatics-feynman-rules/wick-theorem-recap/), [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/), and [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/).

For background, the Foundations pages [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Feynman Diagrams](/foundations/interactions-and-wick-expansion/feynman-diagrams/), [Scalar Interactions](/foundations/interactions-and-wick-expansion/scalar-interactions/), and [Dirac Field](/foundations/free-fields/dirac-field/) give the earlier operator and path-integral construction.

## Core idea

A Feynman rule is not guessed from a picture. It is read from the action.

The free part of the action is quadratic in fields. It defines a kernel. Inverting that kernel gives the propagator. The interaction part of the action is cubic, quartic, or higher in fields. Differentiating it with respect to the fields gives the vertex.

A compact dictionary is:

| Action data | Diagrammatic data | Practical meaning |
|---|---|---|
| quadratic term | propagator | inverse free kinetic operator |
| local monomial | vertex | local interaction insertion |
| derivative in an interaction | momentum factor | $\partial_\mu\mapsto -ip_\mu$ for incoming momentum |
| field index | line or vertex index | Lorentz, spinor, flavor, color, or species label |
| counterterm | counterterm vertex | local correction inserted like any other vertex |

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![The Feynman-rule dictionary from quadratic kernels and local interactions to propagators, vertices, derivative momentum factors, and index flow](/figures/perturbative-qft/vertices-propagators-dictionary.svg)

<figcaption>

Propagators come from inverting the quadratic kernel. Vertices come from differentiating the local interaction action. Derivative interactions give momentum factors, and fields with spin, charge, flavor, or color carry indices and arrows that must be contracted consistently.

</figcaption>
</figure>

This dictionary is the same in operator perturbation theory and in the path integral. Wick contractions supply propagators; expanded interaction insertions supply vertices. The only difference between position-space and momentum-space rules is whether one keeps vertex positions and propagators $D_F(x-y)$, or Fourier transforms everything into momentum conservation, propagator denominators, and loop integrals.

## Setup and conventions

We use the qft.org mostly-minus metric,

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
$$

and Fourier transform

$$
f(x)=\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot x}\widetilde f(p).
$$

Thus a derivative acting on a field with incoming momentum $p$ gives

$$
\partial_\mu e^{-ip\cdot x}=-ip_\mu e^{-ip\cdot x}.
$$

All momenta at a vertex are incoming unless explicitly stated otherwise. A physical outgoing external particle of momentum $k$ is often represented in an all-incoming amplitude by an incoming momentum $p=-k$. That convention is bookkeeping, not physics.

The scalar Feynman propagator is

$$
D_F(x-y)
=
\int\frac{d^4p}{(2\pi)^4}
\frac{i e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

A connected momentum-space diagram usually has one overall conservation law stripped off:

$$
(2\pi)^4\delta^{(4)}\!\left(\sum_{a}p_a\right).
$$

When this page quotes a vertex factor such as $-i\lambda$, it is quoting the stripped factor.

## Propagators from quadratic kernels

For a real scalar field, integrate the free action by parts:

$$
S_0
=
\int d^4x\left(\frac12\partial_\mu\phi\partial^\mu\phi-\frac12m^2\phi^2\right)
=
-\frac12\int d^4x\,\phi(\Box+m^2)\phi.
$$

In momentum space, $\Box e^{-ip\cdot x}=-p^2e^{-ip\cdot x}$, so

$$
S_0
=
\frac12\int\frac{d^4p}{(2\pi)^4}\,
\widetilde\phi(-p)(p^2-m^2)\widetilde\phi(p).
$$

The quadratic kernel is therefore

$$
K(p)=p^2-m^2.
$$

The Feynman propagator is the inverse kernel multiplied by $i$ and supplied with the pole prescription:

$$
\Delta_F(p)=\frac{i}{K(p)+i\epsilon}
=\frac{i}{p^2-m^2+i\epsilon}.
$$

For several bosonic fields $\Phi^A$, the quadratic action has the form

$$
S_0
=
\frac12\int\frac{d^4p}{(2\pi)^4}\,
\Phi^A(-p)K_{AB}(p)\Phi^B(p),
$$

and the propagator is the matrix inverse

$$
\Delta^{AB}(p)=i\,\bigl([K(p)+i\epsilon]^{-1}\bigr)^{AB}.
$$

This matrix form is not fancy notation for its own sake. It is what one needs for fields with Lorentz indices, flavor mixing, gauge fixing, Goldstone–gauge mixing, ghosts, and effective field theories with several operators.

## Fermion propagators and arrows

For a Dirac field,

$$
\mathcal L_0
=
\overline\psi(i\gamma^\mu\partial_\mu-m)\psi.
$$

With the same Fourier convention,

$$
i\gamma^\mu\partial_\mu e^{-ip\cdot x}
=
\gamma^\mu p_\mu e^{-ip\cdot x}
=
p\!\!\!/\,e^{-ip\cdot x},
$$

where

$$
p\!\!\!/\equiv\gamma^\mu p_\mu.
$$

The free Dirac operator is $p\!\!\!/-m$. Its inverse is

$$
(p\!\!\!/-m)^{-1}
=
\frac{p\!\!\!/+m}{p^2-m^2},
$$

because

$$
(p\!\!\!/-m)(p\!\!\!/+m)=p^2-m^2.
$$

Thus the fermion propagator is

$$
S_F(p)
=
\frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon}.
$$

A fermion line carries spinor indices. In index notation,

$$
(S_F)^\alpha{}_{\beta}(p)
=
\left[\frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon}\right]^\alpha{}_{\beta}.
$$

Fermion arrows are not decorative. They track the order of spinor-index contractions and, in charged theories, charge flow. Closed fermion loops also contribute an extra factor of $-1$, coming from the cyclic permutation of Grassmann fields. The sign is not visible in the scalar-looking denominator; it comes from statistics.

## Gauge-field propagators depend on gauge fixing

For a massless Abelian gauge field, the kinetic operator is not invertible until one fixes gauge redundancy. In Feynman gauge, qft.org conventions give

$$
D_F^{\mu\nu}(p)
=
\frac{-i\eta^{\mu\nu}}{p^2+i\epsilon}.
$$

In a general covariant gauge one often writes

$$
D_F^{\mu\nu}(p)
=
\frac{-i}{p^2+i\epsilon}
\left[\eta^{\mu\nu}-(1-\xi)\frac{p^\mu p^\nu}{p^2+i\epsilon}\right].
$$

The propagator is gauge-dependent. Physical observables are not. This is why gauge-theory pages must keep track of Ward identities, Slavnov–Taylor identities, ghosts, and external polarization choices. In this chapter, the lesson is simply: for constrained or gauge-redundant fields, fix the quadratic operator before trying to invert it.

## Vertices from interaction terms

The cleanest definition of a stripped vertex is:

$$
V_{A_1\cdots A_r}(p_1,
\ldots,p_r)
=
i\,\frac{\delta^r S_{\mathrm{int}}}{\delta\Phi^{A_1}(p_1)\cdots\delta\Phi^{A_r}(p_r)}\bigg|_{\Phi=0}
\quad\text{with }(2\pi)^4\delta^{(4)}\!\left(\sum_i p_i\right)\text{ stripped.}
$$

This formula is schematic for fermions, where one must use consistent left and right functional derivatives and keep the chosen field order. For ordinary scalar interactions it is literal and painless.

For example,

$$
S_{\mathrm{int}}
=
-\int d^4x\,\frac{\lambda}{4!}\phi^4(x).
$$

In momentum space,

$$
S_{\mathrm{int}}
=
-\frac{\lambda}{4!}
\int\prod_{a=1}^4\frac{d^4p_a}{(2\pi)^4}
(2\pi)^4\delta^{(4)}\!\left(p_1+p_2+p_3+p_4\right)
\widetilde\phi(p_1)\widetilde\phi(p_2)\widetilde\phi(p_3)\widetilde\phi(p_4).
$$

Four functional derivatives produce a factor $4!$, canceling the $1/4!$. Multiplication by $i$ gives

$$
\phi^4\text{ vertex}:\quad -i\lambda.
$$

Similarly,

$$
\mathcal L_{\mathrm{int}}=-\frac{g}{3!}\phi^3
\quad\Longrightarrow\quad
\phi^3\text{ vertex}:\ -ig.
$$

The factorials in the Lagrangian are conventional but useful. They make the vertex rule equal to the coupling times $-i$ rather than a coupling multiplied by a combinatorial factor.

## Derivative interactions

Derivative interactions are not harder; they are easier to get wrong.

Suppose

$$
\mathcal L_{\mathrm{int}}
=
-\frac{g}{2}\chi\,\partial_\mu\phi\,\partial^\mu\phi.
$$

The factor $1/2$ compensates for the two identical $\phi$ fields. With all momenta incoming, let $p_1$ and $p_2$ be the momenta on the two $\phi$ legs, and $p_3$ the momentum on the $\chi$ leg. Each derivative contributes $-ip_\mu$. Therefore

$$
\partial_\mu\phi(p_1)\partial^\mu\phi(p_2)
\quad\longrightarrow\quad
(-ip_{1\mu})(-ip_2^\mu)
=
-p_1\cdot p_2.
$$

The two identical $\phi$ derivatives cancel the factor $1/2$, and the stripped vertex factor is

$$
\chi\phi\phi\text{ derivative vertex}:
\quad i g\,p_1\cdot p_2.
$$

The sign comes from three sources at once: the sign in $\mathcal L_{\mathrm{int}}$, the factor of $i$ from $e^{iS_{\mathrm{int}}}$, and the two factors $-ip$ from the derivatives. This is why derivative vertices should be derived once rather than memorized from vibes. Vibes are not a regulator.

For more complicated derivative interactions, the safe algorithm is:

1. write the interaction in momentum space using $\partial_\mu\mapsto -ip_\mu$;
2. include all symmetry factors for identical fields in the Lagrangian;
3. functionally differentiate with respect to the external fields;
4. multiply the stripped coefficient by $i$;
5. keep all free indices and momentum labels until the end.

## Common building blocks

Here is a compact table of frequently used stripped factors in qft.org conventions.

| Theory ingredient | Stripped factor | Comments |
|---|---:|---|
| real scalar internal line | $\displaystyle \frac{i}{p^2-m^2+i\epsilon}$ | momentum $p$ flows along the line |
| complex scalar $\phi\phi^\dagger$ line | $\displaystyle \frac{i}{p^2-m^2+i\epsilon}$ | arrow often tracks charge flow |
| Dirac fermion line | $\displaystyle \frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon}$ | spinor indices and arrow order matter |
| Feynman-gauge photon line | $\displaystyle \frac{-i\eta^{\mu\nu}}{p^2+i\epsilon}$ | gauge-dependent propagator |
| $-g\phi^3/3!$ | $-ig$ | scalar cubic vertex |
| $-\lambda\phi^4/4!$ | $-i\lambda$ | scalar quartic vertex |
| $-y\phi\overline\psi\psi$ | $-iy$ | Yukawa vertex, spinor indices contracted |
| charge-$q$ Dirac–photon vertex | $-iq\gamma^\mu$ | with $D_\mu=\partial_\mu+iqA_\mu$; for the electron $q=-e$ gives $+ie\gamma^\mu$ |
| $-g\chi\partial\phi\partial\phi/2$ | $ig\,p_1\cdot p_2$ | $p_1,p_2$ on the differentiated $\phi$ legs |

This table is a lookup aid, not a substitute for the derivation. Whenever signs differ across sources, check metric signature, Fourier phase, charge convention, and whether the source quotes $i\mathcal M$ or $\mathcal M$.

## Counterterm vertices

Counterterms are local interactions and therefore have vertices.

For scalar $\phi^4$ theory, a common counterterm Lagrangian is

$$
\mathcal L_{\mathrm{ct}}
=
\frac12\delta Z\,\partial_\mu\phi\partial^\mu\phi
-
\frac12\delta m^2\phi^2
-
\frac{\delta\lambda}{4!}\phi^4.
$$

The two-point counterterm vertex has incoming momentum $p$ on one leg and $-p$ on the other. The quadratic momentum-space coefficient is

$$
\delta Z\,p^2-\delta m^2,
$$

so the two-point insertion is

$$
\text{scalar two-point counterterm}:
\quad i(\delta Z\,p^2-\delta m^2).
$$

The quartic counterterm vertex is

$$
\text{scalar quartic counterterm}:
\quad -i\delta\lambda.
$$

Counterterm diagrams look like ordinary diagrams with special local vertices. Their job is not to represent a new microscopic force. Their job is to implement a renormalization prescription, absorb regulator dependence, and express predictions in terms of renormalized parameters.

## External legs are not internal propagators

Internal lines are Wick contractions whose momenta are integrated or fixed by momentum conservation. External legs depend on what object is being computed.

| Object being computed | What happens to external legs? |
|---|---|
| full Green function | external insertions include external propagators |
| connected Green function | still includes external propagators |
| amputated Green function | external propagators are removed |
| S-matrix element | LSZ amputates, takes on-shell limits, and inserts residues and wavefunctions |

For a scalar connected Green function near tree level,

$$
\widetilde G_{n,\mathrm{conn}}(p_1,\ldots,p_n)
=
\left[\prod_{a=1}^n\frac{i}{p_a^2-m^2+i\epsilon}\right]
 i\mathcal A_n(p_1,\ldots,p_n),
$$

with the overall momentum-conservation delta function stripped. The amputated object $i\mathcal A_n$ is what remains after removing the external propagators. In a properly normalized scattering amplitude, LSZ additionally accounts for one-particle residues and external spin or polarization wavefunctions.

A common beginner mistake is to draw four external lines attached to a vertex and then multiply by four extra propagators even though the target quantity is already an amputated amplitude. The diagram alone does not tell you the answer; the object being computed does.

## Worked example: scalar four-point contact term

In $\phi^4$ theory,

$$
\mathcal L_{\mathrm{int}}=-\frac{\lambda}{4!}\phi^4,
$$

the first-order connected four-point Green function is

$$
G_{4,\mathrm{conn}}^{(1)}(x_1,x_2,x_3,x_4)
=
(-i\lambda)\int d^4z\,
D_F(x_1-z)D_F(x_2-z)D_F(x_3-z)D_F(x_4-z).
$$

In momentum space this becomes

$$
\widetilde G_{4,\mathrm{conn}}^{(1)}(p_1,p_2,p_3,p_4)
=
(-i\lambda)
\prod_{a=1}^4\frac{i}{p_a^2-m^2+i\epsilon},
$$

with the overall $(2\pi)^4\delta^{(4)}(p_1+p_2+p_3+p_4)$ stripped. The amputated tree object is therefore

$$
i\mathcal A_4^{\mathrm{tree}}=-i\lambda.
$$

This is the same local factor one writes at the quartic vertex. The external propagators appear only because the first expression computed a Green function.

## Worked example: Yukawa exchange

For a real scalar $\phi$ coupled to a Dirac field by

$$
\mathcal L_{\mathrm{int}}=-y\phi\overline\psi\psi,
$$

the Yukawa vertex is

$$
{-iy.}
$$

Consider tree-level fermion–fermion scattering through scalar exchange. If the scalar carries momentum $q$, the internal scalar line contributes

$$
\frac{i}{q^2-m^2+i\epsilon},
$$

and the two vertices contribute $(-iy)^2$. The spinor wavefunctions and index contractions depend on the external fermion assignment, but the internal building block is

$$
(-iy)^2\frac{i}{q^2-m^2+i\epsilon}.
$$

The important lesson is modularity. The scalar propagator knows about the exchanged scalar; the Yukawa vertices know about the local coupling; the external spinors know about the asymptotic fermion states. Mixing these roles is how one loses signs and factors.

## Common pitfalls

**Using the wrong sign for the interaction.** If $\mathcal L_{\mathrm{int}}=-\lambda\phi^4/4!$, the vertex is $-i\lambda$. If a source writes the potential $V=+\lambda\phi^4/4!$, remember that $\mathcal L=T-V$.

**Forgetting the Fourier phase.** With $e^{-ip\cdot x}$, a derivative on an incoming field gives $-ip_\mu$. A different Fourier convention moves signs into derivative vertices.

**Inverting the wrong quadratic operator.** Gauge fields, mixed fields, constrained systems, and derivative couplings may require gauge fixing, field redefinitions, or matrix inversion before a propagator exists.

**Confusing external lines with internal lines.** Green functions include external propagators. Amplitudes do not. LSZ is the bridge.

**Dropping indices too early.** Lorentz, spinor, flavor, color, and gauge indices are part of the rule. A scalar-looking expression may hide a nontrivial matrix product.

**Treating counterterms as optional decorations.** In renormalized perturbation theory, counterterm vertices are part of the Feynman rules at the relevant order.

## Relations to other pages

- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) explains how these local building blocks assemble into full diagram integrals.
- [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/) explains the remaining combinatorial divisors after vertices and propagators are assigned.
- [Connected and Disconnected Diagrams](/perturbative-qft/diagrammatics-feynman-rules/connected-and-disconnected-diagrams/) separates full correlators, connected pieces, and vacuum bubbles.
- [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/) uses propagators and vertices to define the irreducible building blocks of the effective action.
- [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/) develops the counterterm vertices used in renormalized perturbation theory.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) derives the scalar propagator and its pole prescription.
- [Dirac Field](/foundations/free-fields/dirac-field/) gives the spinor conventions behind the fermion propagator.
- [Gauge Fixing for Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/gauge-fixing-for-perturbation-theory/) explains why gauge-field propagators require gauge fixing.

## Research status

**Established:** The vertex and propagator rules described here are standard consequences of perturbative expansion around a free quadratic theory. For ordinary scalar, spinor, and gauge theories, they are textbook material.

**Convention-dependent:** Signs depend on metric signature, Fourier phase, charge convention, and whether one reports the full matrix element, $i\mathcal M$, or $\mathcal M$.

**Subtle:** Gauge theories require gauge fixing and ghosts; derivative interactions can require careful treatment of field redefinitions and redundant operators; unstable particles and resummed propagators require a precise scheme.

**Active:** Automated Feynman-rule generation, effective-operator bases, multi-loop counterterm organization, gauge-invariant amplitude construction, and symbolic manipulation of large theories are active computational areas.

## Exercises

### Exercise 1: Scalar quadratic kernel

Starting from

$$
\mathcal L_0
=
\frac12\partial_\mu\phi\partial^\mu\phi
-
\frac12m^2\phi^2,
$$

show that the momentum-space quadratic kernel is $K(p)=p^2-m^2$ and hence the Feynman propagator is $i/(p^2-m^2+i\epsilon)$.

<details>
<summary><strong>Solution</strong></summary>

Integrate by parts:

$$
S_0
=
-\frac12\int d^4x\,\phi(\Box+m^2)\phi.
$$

With

$$
\phi(x)=\int\frac{d^4p}{(2\pi)^4}e^{-ip\cdot x}\widetilde\phi(p),
$$

we have

$$
\Box e^{-ip\cdot x}=-p^2e^{-ip\cdot x}.
$$

Therefore

$$
S_0
=
\frac12\int\frac{d^4p}{(2\pi)^4}\,
\widetilde\phi(-p)(p^2-m^2)\widetilde\phi(p).
$$

Thus $K(p)=p^2-m^2$. The Feynman propagator is the inverse kernel with the Lorentzian factor and pole prescription:

$$
\Delta_F(p)=\frac{i}{p^2-m^2+i\epsilon}.
$$

</details>

### Exercise 2: Quartic vertex by functional differentiation

Use

$$
S_{\mathrm{int}}
=
-\int d^4x\,\frac{\lambda}{4!}\phi^4(x)
$$

to derive the stripped $\phi^4$ vertex factor.

<details>
<summary><strong>Solution</strong></summary>

In momentum space,

$$
S_{\mathrm{int}}
=
-\frac{\lambda}{4!}
\int\prod_{a=1}^4\frac{d^4p_a}{(2\pi)^4}
(2\pi)^4\delta^{(4)}\!\left(\sum_{a=1}^4p_a\right)
\widetilde\phi(p_1)\widetilde\phi(p_2)\widetilde\phi(p_3)\widetilde\phi(p_4).
$$

Four functional derivatives with respect to the four scalar fields give a factor $4!$, which cancels $1/4!$. The stripped coefficient is $-\lambda$. Multiplying by $i$ from $e^{iS_{\mathrm{int}}}$ gives

$$
{-i\lambda.}
$$

</details>

### Exercise 3: Derivative vertex sign

For

$$
\mathcal L_{\mathrm{int}}
=
-\frac{g}{2}\chi\,\partial_\mu\phi\partial^\mu\phi,
$$

derive the stripped vertex with incoming momenta $p_1,p_2$ on the two $\phi$ legs and $p_3$ on the $\chi$ leg.

<details>
<summary><strong>Solution</strong></summary>

Each derivative acting on an incoming field contributes

$$
\partial_\mu\phi(p)\mapsto -ip_\mu\phi(p).
$$

Thus

$$
\partial_\mu\phi(p_1)\partial^\mu\phi(p_2)
\mapsto
(-ip_{1\mu})(-ip_2^\mu)
=
-p_1\cdot p_2.
$$

The factor $1/2$ is canceled by the two identical ways of differentiating with respect to the two $\phi$ fields. The coefficient in $S_{\mathrm{int}}$ is therefore

$$
-g(-p_1\cdot p_2)=g p_1\cdot p_2.
$$

Multiplying by $i$ gives

$$
{ig\,p_1\cdot p_2.}
$$

</details>

### Exercise 4: Scalar counterterm insertion

For

$$
\mathcal L_{\mathrm{ct}}
=
\frac12\delta Z\,\partial_\mu\phi\partial^\mu\phi
-
\frac12\delta m^2\phi^2,
$$

show that the two-point counterterm insertion is $i(\delta Zp^2-\delta m^2)$.

<details>
<summary><strong>Solution</strong></summary>

The kinetic counterterm gives

$$
\frac12\delta Z\,\partial_\mu\phi\partial^\mu\phi
\mapsto
\frac12\delta Z\,p^2\,\widetilde\phi(-p)\widetilde\phi(p),
$$

after the same integration-by-parts or Fourier-space calculation as in the free action. The mass counterterm gives

$$
-\frac12\delta m^2\phi^2
\mapsto
-\frac12\delta m^2\widetilde\phi(-p)\widetilde\phi(p).
$$

The quadratic coefficient is

$$
\delta Zp^2-\delta m^2.
$$

Multiplication by $i$ gives the two-point insertion

$$
{i(\delta Zp^2-\delta m^2).}
$$

</details>

### Exercise 5: Dirac inverse

Verify that

$$
(p\!\!\!/-m)^{-1}=\frac{p\!\!\!/+m}{p^2-m^2}
$$

using the Clifford algebra $\{\gamma^\mu,\gamma^\nu\}=2\eta^{\mu\nu}$.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
(p\!\!\!/-m)(p\!\!\!/+m)
=(p\!\!\!/)^2-m^2.
$$

Now

$$
(p\!\!\!/)^2
=\gamma^\mu\gamma^\nu p_\mu p_\nu
=\frac12\{\gamma^\mu,\gamma^\nu\}p_\mu p_\nu
=\eta^{\mu\nu}p_\mu p_\nu
=p^2,
$$

because $p_\mu p_\nu$ is symmetric and the commutator part of $\gamma^\mu\gamma^\nu$ drops out. Therefore

$$
(p\!\!\!/-m)(p\!\!\!/+m)=p^2-m^2,
$$

which proves the inverse away from the pole. The Feynman prescription gives

$$
S_F(p)=\frac{i(p\!\!\!/+m)}{p^2-m^2+i\epsilon}.
$$

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§9–10 and §19 for scalar rules, §§42–45 for fermion propagators and Dirac-field rules.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 8 and 10 for the transition from Wick diagrams to Feynman diagrams, and chs. 21 and 28 for fermionic and functional-integral perspectives.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§6.1–6.3 and ch. 9 for covariant Feynman rules and path-integral derivations.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 7 and 13–14 for practical Lagrangian, Hamiltonian, and path-integral derivations of Feynman rules.
- A. Zee, *Quantum Field Theory in a Nutshell*, app. C for a compact Feynman-rule summary.

## Version history

- **2026-06-11:** Initial polished draft for the Perturbative QFT and Scattering volume. Includes scalar, fermion, gauge-field, derivative-interaction, and counterterm examples, plus a compact dictionary figure.
