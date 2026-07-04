---
title: "Generating Functional Diagrams"
description: "How source functionals generate full, connected, and one-particle-irreducible diagrams, with scalar examples and vacuum-bubble cancellation made explicit."
sidebar:
  label: "Generating Functional Diagrams"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§9–10, §19, and §21; Coleman 2019, chs. 28 and 32; Weinberg 1995, Vol. I, ch. 9; Schwartz 2014, ch. 14; Zinn-Justin 2021, ch. 7"
topics:
  - generating functionals
  - source methods
  - connected diagrams
  - vacuum bubbles
  - effective action
  - scalar perturbation theory
canonicalTopics:
  - generating-functional-diagrams
  - source-functional-diagrammatics
  - connected-diagram-generator
researchStatus:
  established:
    - "The source-functional derivation of perturbative diagrams, the relation between logarithms and connected diagrams, and the Legendre transform to one-particle-irreducible vertices are textbook-standard."
  active:
    - "Convergence, nonperturbative definitions of functional integrals, real-time contours, gauge fixing, and constructive meanings of interacting measures require later pages and depend on the theory."
---

## Summary

Generating functionals turn diagrammatic perturbation theory into a differentiation problem. For a real scalar field coupled to a source $J$, the normalized functional

$$
Z[J]
=
\langle\Omega|T\exp\left(i\int d^4x\,J(x)\phi(x)\right)|\Omega\rangle
$$

generates time-ordered Green functions by

$$
G_n(x_1,\ldots,x_n)
=
\left.\frac{1}{i^n}\frac{\delta^n Z[J]}{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}
$$

when $Z[0]=1$. The logarithm generates connected Green functions,

$$
Z[J]=e^{iW[J]},
\qquad
G_{n,c}(x_1,\ldots,x_n)
=
\left.\frac{1}{i^{n-1}}\frac{\delta^n W[J]}{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}.
$$

The Legendre transform of $W[J]$ produces the effective action $\Gamma[\varphi]$, whose functional derivatives generate one-particle-irreducible vertices. Thus the source formalism organizes the hierarchy

$$
Z[J]\quad\longrightarrow\quad W[J]\quad\longrightarrow\quad \Gamma[\varphi]
$$

as full diagrams, connected diagrams, and one-particle-irreducible diagrams. This page explains how that hierarchy works and how it reproduces the familiar Feynman diagrams of scalar perturbation theory.

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Perturbative Expansion](/perturbative-qft/diagrammatics-feynman-rules/perturbative-expansion/), and [Wick Theorem Recap](/perturbative-qft/diagrammatics-feynman-rules/wick-theorem-recap/). The Foundations pages [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/), [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/), and [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/) provide the underlying path-integral and correlator language.

## Core idea

A source $J(x)$ is a temporary bookkeeping field. Differentiating with respect to $J(x)$ inserts a field $\phi(x)$. The free theory is Gaussian, so its source functional already knows Wick's theorem. The interaction is then represented by replacing each field in $S_{\mathrm{int}}[\phi]$ with a functional derivative with respect to $J$.

The resulting machine has three levels:

| Functional | Generates | Diagrammatic meaning |
|---|---|---|
| $Z[J]$ | full time-ordered correlators | all diagrams, including disconnected products |
| $W[J]=-i\log Z[J]$ | connected correlators | connected diagrams only |
| $\Gamma[\varphi]$ | one-particle-irreducible vertices | building blocks for connected diagrams |

The logarithm is not a decorative change of notation. It is the cumulant operation: it removes products of independent connected pieces. The Legendre transform goes one step further and extracts the vertices from which connected diagrams can be rebuilt by tree graphs using full propagators.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Hierarchy of source functionals from unnormalized diagrams to full, connected, and one-particle-irreducible generators](/figures/perturbative-qft/generating-functional-hierarchy.svg)

<figcaption>

The source-functional hierarchy. Normalization removes vacuum bubbles from ordinary correlators, the logarithm selects connected diagrams, and the Legendre transform produces one-particle-irreducible vertices.

</figcaption>
</figure>

## Setup and conventions

We work in flat four-dimensional Minkowski spacetime with qft.org mostly-minus conventions. The running example is real scalar $\phi^4$ theory,

$$
\mathcal L
=
\frac12\partial_\mu\phi\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\lambda}{4!}\phi^4.
$$

The free scalar propagator is

$$
D_F(x-y)
=
\int\frac{d^4p}{(2\pi)^4}
\frac{i\,e^{-ip\cdot(x-y)}}{p^2-m^2+i\epsilon}.
$$

We use the shorthand

$$
\int J D_F J
\equiv
\int d^4x\,d^4y\,J(x)D_F(x-y)J(y).
$$

The normalized Lorentzian free generating functional is

$$
Z_0[J]
=
\exp\left[-\frac12\int J D_F J\right].
$$

This sign is tied to the convention that correlators are generated by $(1/i)\delta/\delta J$. In particular,

$$
\left.\frac{1}{i^2}\frac{\delta^2 Z_0[J]}{\delta J(x)\delta J(y)}\right|_{J=0}
=D_F(x-y).
$$

## Free theory as Wick's theorem

The free functional already contains all Wick pairings. Expanding $Z_0[J]$ gives

$$
Z_0[J]
=
1
-
\frac12\int J D_F J
+
\frac{1}{8}\left(\int J D_F J\right)^2
-\cdots.
$$

Every factor $D_F(x-y)$ is a contraction. Functional derivatives with respect to $J$ pick out the endpoints of those contractions.

For example,

$$
\frac{1}{i^2}\left.\frac{\delta^2Z_0}{\delta J(x_1)\delta J(x_2)}\right|_{J=0}
=D_F(x_1-x_2),
$$

and four derivatives give

$$
\begin{aligned}
&\frac{1}{i^4}\left.\frac{\delta^4Z_0}{\delta J(x_1)\delta J(x_2)\delta J(x_3)\delta J(x_4)}\right|_{J=0} \\
&\qquad =
D_F(x_1-x_2)D_F(x_3-x_4)
+D_F(x_1-x_3)D_F(x_2-x_4) \\
&\qquad\quad
+D_F(x_1-x_4)D_F(x_2-x_3).
\end{aligned}
$$

This is exactly the free four-point Wick theorem. The source formalism has simply hidden the pairing combinatorics inside Gaussian differentiation.

## Interactions as differential operators

For an interacting scalar theory, the path integral says schematically

$$
Z_{\mathrm{un}}[J]
=
\int\mathcal D\phi\,
\exp\left\{iS_0[\phi]+iS_{\mathrm{int}}[\phi]+i\int J\phi\right\}.
$$

Because insertion of a field is represented by

$$
\phi(x)
\quad\longleftrightarrow\quad
\frac{1}{i}\frac{\delta}{\delta J(x)},
$$

the interacting functional can be written as

$$
Z_{\mathrm{un}}[J]
=
\exp\left\{iS_{\mathrm{int}}\!\left[\frac{1}{i}\frac{\delta}{\delta J}\right]\right\}Z_0[J].
$$

The subscript means "unnormalized." Ordinary normalized correlators use

$$
Z[J]
=
\frac{Z_{\mathrm{un}}[J]}{Z_{\mathrm{un}}[0]},
\qquad Z[0]=1.
$$

For $\phi^4$ theory,

$$
S_{\mathrm{int}}[\phi]
=
-\frac{\lambda}{4!}\int d^4z\,\phi(z)^4,
$$

so

$$
Z_{\mathrm{un}}[J]
=
\exp\left[-\frac{i\lambda}{4!}\int d^4z\,
\left(\frac{1}{i}\frac{\delta}{\delta J(z)}\right)^4
\right]Z_0[J].
$$

The diagrammatic translation is immediate: each power of the interaction creates a vertex, each functional derivative at a vertex must be paired by differentiating the Gaussian, and each source derivative used to compute a correlator attaches an external insertion.

## First-order scalar example

Let

$$
A(z;J)\equiv\int d^4y\,D_F(z-y)J(y).
$$

Applying four source derivatives at the same point $z$ to the free Gaussian gives

$$
\left(\frac{1}{i}\frac{\delta}{\delta J(z)}\right)^4Z_0[J]
=
\left\{\left[ iA(z;J)\right]^4
+6D_F(0)\left[iA(z;J)\right]^2
+3D_F(0)^2\right\}Z_0[J].
$$

Therefore the unnormalized functional to first order in $\lambda$ is

$$
\begin{aligned}
Z_{\mathrm{un}}[J]
&=
Z_0[J]
-\frac{i\lambda}{4!}\int d^4z\,
\Big\{\left[iA(z;J)\right]^4 \\
&\qquad\qquad
+6D_F(0)\left[iA(z;J)\right]^2
+3D_F(0)^2\Big\}Z_0[J]
+O(\lambda^2).
\end{aligned}
$$

There are three terms, with three diagrammatic meanings.

| Term | Diagrammatic meaning |
|---|---|
| $\left[iA(z;J)\right]^4$ | one quartic vertex connected to four source insertions |
| $6D_F(0)\left[iA(z;J)\right]^2$ | a two-point tadpole correction with two source insertions |
| $3D_F(0)^2$ | a vacuum bubble with no source insertions |

The normalized functional divides by $Z_{\mathrm{un}}[0]$. To first order, this cancels the constant vacuum-bubble term $3D_F(0)^2$. This is the functional version of the diagrammatic statement that vacuum bubbles cancel in normalized correlation functions.

:::caution[The $D_F(0)$ warning]
The expression $D_F(0)$ is ultraviolet divergent in four-dimensional continuum QFT. On this page it is a formal diagrammatic placeholder. A regulator and renormalization prescription are needed before such loop expressions become meaningful numbers.
:::

## Connected diagrams from the logarithm

Disconnected diagrams factor. If a full correlator has two connected components, its contribution is a product of two connected contributions. The exponential is exactly the combinatorial structure that turns sums of connected pieces into sums over arbitrary products of connected pieces.

This is why

$$
Z[J]=e^{iW[J]}
$$

means that $W[J]$ generates connected diagrams. Equivalently, $W[J]$ is the field-theory analogue of a cumulant generating function in probability theory.

For instance, differentiating $Z=e^{iW}$ twice gives

$$
\frac{1}{i^2}\frac{\delta^2 Z}{\delta J_1\delta J_2}
=
\frac{\delta W}{\delta J_1}\frac{\delta W}{\delta J_2}
+
\frac{1}{i}\frac{\delta^2 W}{\delta J_1\delta J_2}.
$$

At $J=0$, this says

$$
G_2(x_1,x_2)
=
G_1(x_1)G_1(x_2)+G_{2,c}(x_1,x_2).
$$

Similarly, the full four-point function is a connected four-point function plus products of connected two-point functions and one-point functions. The logarithm performs these subtractions automatically.

## From connected diagrams to one-particle-irreducible vertices

The classical field in the presence of a source is

$$
\varphi_J(x)
\equiv
\frac{\delta W[J]}{\delta J(x)}.
$$

The effective action is the Legendre transform

$$
\Gamma[\varphi]
=
W[J]-\int d^4x\,J(x)\varphi(x),
\qquad
\frac{\delta\Gamma}{\delta\varphi(x)}=-J(x).
$$

Functional derivatives of $\Gamma$ generate one-particle-irreducible vertices. A one-particle-irreducible diagram is a connected diagram that cannot be disconnected by cutting a single internal line.

The relation between $W$ and $\Gamma$ is useful because connected diagrams can be built from one-particle-irreducible vertices joined by full propagators. In practical scattering calculations, this is the reason self-energies, vertex functions, and counterterm insertions become reusable building blocks rather than separate Wick-counting exercises every time.

## Diagrammatic dictionary

The source-functional method has a compact dictionary.

| Source-functional object | Diagrammatic object |
|---|---|
| $J(x)$ | external source endpoint |
| $\delta/\delta J(x)$ | field insertion at $x$ |
| $D_F(x-y)$ | free contraction or propagator line |
| $iS_{\mathrm{int}}[(1/i)\delta/\delta J]$ | interaction vertex generator |
| $Z_{\mathrm{un}}[0]$ | vacuum-bubble factor |
| $Z[J]$ with $Z[0]=1$ | normalized full correlators |
| $W[J]=-i\log Z[J]$ | connected diagrams |
| $\Gamma[\varphi]$ | one-particle-irreducible vertices |

The dictionary is the cleanest way to remember why diagrams exponentiate, why disconnected diagrams appear in full correlators, and why vacuum diagrams cancel from normalized flat-space correlators.

## Common pitfalls

**Forgetting the normalization by $Z_{\mathrm{un}}[0]$.** The unnormalized functional contains vacuum bubbles. Normalized correlation functions divide them out, which is why vacuum bubbles do not appear in ordinary connected scattering calculations.

**Confusing full and connected correlators.** $Z[J]$ generates full correlators, not connected ones. The connected generator is $W[J]=-i\log Z[J]$, with factors of $i$ fixed by Lorentzian conventions.

**Treating $D_F(0)$ as a number too early.** Tadpoles and vacuum bubbles often contain coincident-point propagators. In continuum QFT these are divergent until a regulator and renormalization prescription are specified.

**Thinking source endpoints are external particles.** A source derivative inserts a field in a Green function. External particles require amputation, on-shell limits, and state normalizations supplied by LSZ reduction.

**Comparing Euclidean and Lorentzian formulas without translating factors of $i$.** The compact formulas above are Lorentzian. Euclidean generating functionals have different signs in the Gaussian and no identical pattern of explicit $i$ factors.

## Relations to other pages

- [Perturbative Expansion](/perturbative-qft/diagrammatics-feynman-rules/perturbative-expansion/) explains the operator and path-integral expansion that this page packages into source derivatives.
- [Wick Theorem Recap](/perturbative-qft/diagrammatics-feynman-rules/wick-theorem-recap/) gives the pairing formula hidden inside the free Gaussian $Z_0[J]$.
- [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/) explains the remaining overcounting factors after functional derivatives are grouped into diagrams.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) Fourier transforms the position-space diagrams generated here.
- [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/) introduces the Legendre-transform viewpoint behind one-particle-irreducible vertices.
- [LSZ Preview](/foundations/interactions-and-wick-expansion/lsz-preview/) explains why Green functions are not yet scattering amplitudes.

## Research status

The source-functional construction is textbook-standard as a formal perturbative method. Its rigorous status depends on the theory, regulator, spacetime signature, and choice of contour. In perturbative flat-space scalar QFT, it is best understood as a compact generator of formal power series. Nonperturbative measures, gauge fixing, real-time Schwinger–Keldysh contours, and constructive definitions require later volumes.

## Exercises

### Exercise 1: Recover the free two-point function

Starting from

$$
Z_0[J]=\exp\left[-\frac12\int J D_F J\right],
$$

show that

$$
\left.\frac{1}{i^2}\frac{\delta^2 Z_0}{\delta J(x)\delta J(y)}\right|_{J=0}=D_F(x-y).
$$

<details>
<summary><strong>Solution</strong></summary>

Define

$$
A(x;J)=\int d^4z\,D_F(x-z)J(z).
$$

Then

$$
\frac{\delta Z_0}{\delta J(x)}=-A(x;J)Z_0[J].
$$

A second derivative gives

$$
\frac{\delta^2 Z_0}{\delta J(x)\delta J(y)}
=
\left[-D_F(x-y)+A(x;J)A(y;J)\right]Z_0[J].
$$

At $J=0$, $A=0$ and $Z_0[0]=1$. Since $1/i^2=-1$,

$$
\left.\frac{1}{i^2}\frac{\delta^2 Z_0}{\delta J(x)\delta J(y)}\right|_{J=0}
=D_F(x-y).
$$

</details>

### Exercise 2: Four derivatives and Wick pairings

Use four functional derivatives of $Z_0[J]$ to recover the three terms in the free scalar four-point function.

<details>
<summary><strong>Solution</strong></summary>

Only the quadratic source term in the Gaussian can contribute after setting $J=0$. Equivalently, the fourth derivative must split the four labels into two pairs. The possible pairings are

$$
(12)(34),\qquad (13)(24),\qquad (14)(23).
$$

Thus

$$
\begin{aligned}
G_4^{(0)}(x_1,x_2,x_3,x_4)
&=D_F(x_1-x_2)D_F(x_3-x_4)\\
&\quad+D_F(x_1-x_3)D_F(x_2-x_4)\\
&\quad+D_F(x_1-x_4)D_F(x_2-x_3).
\end{aligned}
$$

This is Wick's theorem in source-functional form.

</details>

### Exercise 3: Vacuum-bubble cancellation at first order

In $\phi^4$ theory, show that the $3D_F(0)^2$ term in $Z_{\mathrm{un}}[J]$ cancels from the normalized $Z[J]$ at order $\lambda$.

<details>
<summary><strong>Solution</strong></summary>

To first order,

$$
Z_{\mathrm{un}}[J]=Z_0[J]+\lambda A[J]+O(\lambda^2),
$$

where $A[J]$ includes a constant vacuum term $A[0]$. Since $Z_0[0]=1$,

$$
Z_{\mathrm{un}}[0]=1+\lambda A[0]+O(\lambda^2).
$$

Therefore

$$
Z[J]=\frac{Z_{\mathrm{un}}[J]}{Z_{\mathrm{un}}[0]}
=\left(Z_0[J]+\lambda A[J]\right)\left(1-\lambda A[0]\right)+O(\lambda^2).
$$

The constant part of $A[J]$ is $A[0]Z_0[J]$ at this order. It cancels against $-A[0]Z_0[J]$, leaving only the terms connected to source insertions.

</details>

### Exercise 4: Connected two-point formula

Starting from $Z[J]=e^{iW[J]}$, derive

$$
G_2(x,y)=G_1(x)G_1(y)+G_{2,c}(x,y),
$$

with

$$
G_{2,c}(x,y)=\left.\frac{1}{i}\frac{\delta^2W}{\delta J(x)\delta J(y)}\right|_{J=0}.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate once:

$$
\frac{1}{i}\frac{\delta Z}{\delta J(x)}
=Z\frac{\delta W}{\delta J(x)}.
$$

Differentiate again and divide by $i$ in the same convention:

$$
\frac{1}{i^2}\frac{\delta^2Z}{\delta J(x)\delta J(y)}
=Z\frac{\delta W}{\delta J(x)}\frac{\delta W}{\delta J(y)}
+Z\frac{1}{i}\frac{\delta^2W}{\delta J(x)\delta J(y)}.
$$

At $J=0$, $Z[0]=1$. The first term is $G_1(x)G_1(y)$, and the second term is the connected two-point function.

</details>

### Exercise 5: Source insertions versus external particles

Explain why differentiating $Z[J]$ four times does not by itself give a $2\to2$ scattering amplitude.

<details>
<summary><strong>Solution</strong></summary>

Four derivatives of $Z[J]$ produce a time-ordered four-point Green function. Its external legs are field insertions and are generally off shell. A scattering amplitude requires the connected part, amputation of external propagators, on-shell limits, wavefunction residues, and relativistic state normalization. Those extra steps are supplied by LSZ reduction, not by source differentiation alone.

</details>

## References

### Standard first pass

- Mark Srednicki, *Quantum Field Theory*, especially the path-integral derivation of interacting scalar perturbation theory and the discussion of all-order perturbation theory.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 28 and 32, for functional integration, generating functionals, and connected versus one-particle-irreducible diagrams.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 14, for generating functionals and path-integral derivations of Feynman rules.

### Deeper references

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 9, for the path-integral formulation and its connection to Feynman rules.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, ch. 7, for generating functionals, connected functions, vertex functionals, and loop expansions.
- A. Zee, *Quantum Field Theory in a Nutshell*, app. A and app. C, for Gaussian integration and compact Feynman-rule summaries.

## Version history

- **2026-06-11:** Initial standardized page.
