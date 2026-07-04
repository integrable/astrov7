---
title: "Why Fields Are Distributions"
description: "Explains why pointlike quantum fields are too singular to be operators and why smearing against test functions is part of the definition."
sidebar:
  label: "Why Fields Are Distributions"
  order: 1
level: Graduate
status: "Polished draft"
source: "Wightman; Streater–Wightman; Haag; Reed–Simon; Glimm–Jaffe; Hollands–Wald."
topics:
  - operator-valued distributions
  - smearing
  - Wightman fields
  - ultraviolet singularities
  - free scalar field
canonicalTopics:
  - operator-valued-distribution
  - rigorous-quantum-field-theory
  - axiomatic-quantum-field-theory
researchStatus:
  established:
    - "In Wightman-style axiomatic QFT, fields are operator-valued distributions; smeared fields are the primary operator objects."
    - "Free scalar fields give explicit examples where pointlike notation is distributional and smearing produces well-defined operators on a dense domain."
  active:
    - "For interacting and gauge theories, the construction of fields, composite fields, and local observables is framework-dependent and often requires renormalization, algebraic methods, or cohomological tools."
---

## Summary

A quantum field is usually not an operator-valued function $x\mapsto\phi(x)$. In rigorous Lorentzian QFT, the basic object is an **operator-valued distribution**: a rule that assigns an operator to a test function,

$$
f\longmapsto \phi(f),
\qquad
\phi(f)=\int d^dx\,\phi(x)f(x),
$$

where the integral is notation for distributional pairing. The smeared operator $\phi(f)$ is meaningful on a suitable dense domain; the point symbol $\phi(x)$ is usually a kernel notation, not an operator defined at the point $x$.

This is not a minor technicality. The two-point functions of QFT are singular distributions, equal-time commutators contain delta functions, and products of fields at the same point are generally ill-defined before renormalization. Smearing is the first repair that turns formal field notation into a mathematical object.

The slogan is:

$$
\text{quantum field}
\ne
\text{operator at every point},
\qquad
\text{quantum field}
=
\text{operator-valued distribution}.
$$

<figure class="doc-figure" style="--figure-width: 42rem;">

![Smearing a field against a test function](/figures/rigorous-qft/field-smearing.svg)

<figcaption>

The point notation $\phi(x)$ is a distributional kernel. A test function $f$ with controlled support and smoothness produces the operator $\phi(f)$ by smearing.

</figcaption>
</figure>

## Prerequisites

You should know the distribution notation from [Conventions and Logical Status](/rigorous-qft/conventions/), especially $C_c^\infty(M)$, $\mathcal S(\mathbb R^d)$, $\mathcal D'(M)$, $\mathcal S'(\mathbb R^d)$, and the pairing $\langle T,f\rangle$.

It helps to have seen the free scalar field in ordinary QFT and to know that the Feynman propagator and Wightman two-point function are singular at short distances. The detailed rules for choosing test functions are developed in [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/).

## Core idea

Classical field theory often begins with a function $x\mapsto\phi(x)$ satisfying an equation such as

$$
(\Box+m^2)\phi=0.
$$

Quantum field theory keeps the same notation but changes the mathematical type of the object. The value $\phi(x)$ fluctuates too violently at arbitrarily short distances to be an ordinary operator. What is well-defined is its average against a smooth probe $f$:

$$
\phi(f)
=
\langle \phi,f\rangle.
$$

A useful physical picture is that no actual detector measures a field at an infinitely sharp spacetime point. It has finite resolution, finite duration, and a response profile. A test function is the mathematical idealization of such a smooth, localized probe.

The deeper mathematical reason is that QFT correlators are distributions. If $\phi(x)$ were an honest operator-valued function with sufficiently nice vacuum matrix elements, then

$$
(x,y)\longmapsto
\langle\Omega,\phi(x)\phi(y)\Omega\rangle
$$

would be an ordinary function. In actual relativistic QFT, even the free field gives singular kernels. These kernels become legitimate after pairing with test functions.

## Setup and conventions

Work first on Minkowski space $\mathbb R^d$ with the mostly-minus convention from [Conventions and Logical Status](/rigorous-qft/conventions/). Let $\mathcal H$ be a Hilbert space, let $\mathcal D\subset\mathcal H$ be a dense domain, and let $\mathcal S(\mathbb R^d)$ denote the Schwartz test-function space.

A scalar Wightman field may be treated as a linear map

$$
\phi:\mathcal S(\mathbb R^d)\longrightarrow
\operatorname{End}(\mathcal D),
\qquad
f\longmapsto \phi(f),
$$

such that matrix elements are tempered distributions:

$$
f\longmapsto
\langle \Psi,\phi(f)\Phi\rangle
\quad\text{is in}\quad
\mathcal S'(\mathbb R^d),
\qquad
\Psi,\Phi\in\mathcal D.
$$

This is often the cleanest definition of an operator-valued distribution. It says that the field is distributional after taking matrix elements between domain vectors. In concrete models, $\phi(f)$ is usually unbounded, so one should not expect it to be defined on all of $\mathcal H$.

For a Hermitian real scalar field, the adjoint relation is expressed domain-wise as

$$
\phi(f)^\dagger \supset \phi(\overline f),
$$

and for real $f$ one expects $\phi(f)$ to be symmetric on the chosen domain. Self-adjointness is a further operator-theoretic question and is not automatic from the formal symbol $\phi(x)$.

## The free scalar field already forces smearing

For the free massive scalar field, the positive-frequency two-point distribution is

$$
\Delta_+(x-y)
=
\int \frac{d^3\mathbf p}{(2\pi)^3\,2E_{\mathbf p}}
\,e^{-ip\cdot(x-y)},
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2},
$$

where $p^0=E_{\mathbf p}$. This formula is standard physics notation, but it should be read as a distribution. The smeared two-point function is

$$
\begin{aligned}
W_2(f,g)
&=
\langle\Omega,\phi(f)\phi(g)\Omega\rangle \\
&=
\int \frac{d^3\mathbf p}{(2\pi)^3\,2E_{\mathbf p}}
\,\widetilde f(-E_{\mathbf p},-\mathbf p)
\,\widetilde g(E_{\mathbf p},\mathbf p),
\end{aligned}
$$

with the precise complex conjugations depending on whether one makes $f$ linear or antilinear in the first slot. The important point is not this convention; it is that the on-shell momentum integral is finite for Schwartz test functions.

By contrast, the formal point expression

$$
\langle\Omega,\phi(x)^2\Omega\rangle
\sim
\int \frac{d^3\mathbf p}{(2\pi)^3\,2E_{\mathbf p}}
$$

is ultraviolet divergent. The problem appears before any interaction is added. The free field is already distributional.

This is the best first lesson: smearing is not a patch for complicated theories. It is already required by the simplest relativistic quantum field.

## Three sources of singularity

### On-shell spectral measures

Relativistic particles live on mass shells. The one-particle measure

$$
\frac{d^3\mathbf p}{(2\pi)^3\,2E_{\mathbf p}}
$$

is Lorentz invariant but is supported on $p^2=m^2$, $p^0>0$. As a distribution on full momentum space, this is

$$
\theta(p^0)\delta(p^2-m^2).
$$

Fourier transforming such mass-shell distributions gives spacetime distributions, not smooth functions. The singular support and wavefront set encode propagation along the light cone and mass shell.

### Canonical commutators

The equal-time canonical commutation relation is written formally as

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

The right-hand side is already a distribution. A pointwise commutator of ordinary operator-valued functions would not naturally equal a Dirac delta. The rigorous statement is smeared:

$$
[\phi(t,f),\pi(t,g)]
=i\int d^3\mathbf x\,f(\mathbf x)g(\mathbf x),
$$

for suitable spatial test functions $f,g$. Equal-time fields require additional care in interacting theories, but this formula explains the distributional origin.

### Ultraviolet fluctuations

A scalar field has short-distance fluctuations at all momentum scales. In four dimensions, the massless two-point function behaves schematically as

$$
\Delta_+(x)
\sim
\frac{1}{x^2-i0x^0}
$$

near $x=0$. This is a distribution with a singularity at coincidence. The expression becomes meaningful after testing against a smooth function of $x$.

## Locality is also distributional

A pointlike locality formula is often written

$$
[\phi(x),\phi(y)]=0
\quad\text{for spacelike separated}\quad x,y.
$$

The rigorous smeared version is

$$
[\phi(f),\phi(g)]=0
$$

whenever $\operatorname{supp}f$ and $\operatorname{supp}g$ are spacelike separated. This is stronger and cleaner than the pointwise slogan because it is a statement about actual operators.

For the free scalar field,

$$
[\phi(x),\phi(y)]=i\Delta(x-y),
$$

where $\Delta$ is the Pauli–Jordan distribution. Its support lies in the causal cone. Thus if the supports of $f$ and $g$ are spacelike separated, the distributional pairing of $\Delta$ with $f(x)g(y)$ vanishes.

This is a recurring pattern in rigorous QFT: the formal point formula is a compact mnemonic for a support statement about distributions.

## Point notation is still useful

The conclusion is not that one must ban $\phi(x)$ from physics. Point notation is efficient and often harmless when used as kernel notation. One writes

$$
\phi(f)=\int d^dx\,\phi(x)f(x)
$$

just as one writes a distribution $T$ as if it had a kernel $T(x)$. The danger is only to forget the interpretation.

A good rule is:

| Expression | Safe reading |
|---|---|
| $\phi(x)$ | Distributional kernel for smeared fields. |
| $\langle\Omega,\phi(x)\phi(y)\Omega\rangle$ | Distributional kernel of a two-point function. |
| $\phi(f)$ | Actual smeared field operator on a specified domain. |
| $\phi(x)^2$ | Usually undefined until a renormalized composite field is specified. |
| $[\phi(x),\phi(y)]$ | Kernel notation for a distributional commutator. |

## What smearing does not solve

Smearing a single field makes $\phi(f)$ meaningful, but it does not automatically define every expression in a QFT.

Products at the same point remain singular. The expression $\phi(x)^2$ is not obtained merely by declaring $x$ to be a point. One must define a composite field, for example by normal ordering in a free theory or by renormalization in an interacting theory.

Time-ordered products require further choices. Even if $\phi(f)$ and $\phi(g)$ are meaningful, the distributional kernels entering $T\{\phi(x)\phi(y)\}$ have singularities on diagonals such as $x=y$. Renormalization can be understood as a controlled extension of distributions to these diagonals.

Gauge theory adds another layer. Gauge-variant fields may be useful coordinatizations, but the physical observable algebra may be built from gauge-invariant or BRST/BV-cohomological objects. The statement "fields are distributions" remains true for many gauge-fixed fields, but it is not the whole definition of the theory.

## Common pitfalls

**Saying that smearing is only experimental resolution.** Physical detectors motivate smearing, but the mathematical reason is sharper: the field is not defined pointwise as an operator.

**Thinking distributions are less real than functions.** A distribution is a precise mathematical object. The Dirac delta, mass-shell measure, Feynman propagator, and Wightman functions are not informal because they are distributions.

**Confusing a finite cutoff with the continuum theory.** With a lattice or momentum cutoff, fields may become honest finite-dimensional variables. The distributional issue reappears in the continuum limit.

**Assuming that $\phi(f)$ is bounded.** Smeared fields are usually unbounded operators. Smearing fixes the point singularity, not every operator-domain issue.

**Squaring distributions naively.** Defining $\phi(f)$ does not define $\phi(x)^2$. Composite fields and time-ordered products require additional construction.

## Relations to other pages

- [Test Functions and Smearing](/rigorous-qft/operator-valued-distributions/test-functions-and-smearing/) explains the allowed test-function spaces, support language, adjoints, derivatives, and locality statements.
- [Conventions and Logical Status](/rigorous-qft/conventions/) fixes the distribution notation used here.
- [Physics QFT versus Mathematical QFT](/rigorous-qft/what-is-rigorous-qft/physics-qft-versus-mathematical-qft/) explains why the symbol $\phi(x)$ changes meaning when a physics formula is upgraded to a theorem-level claim.
- [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) explains how directional singularities decide when products of distributions are allowed.

Later pages in this chapter discuss domains of unbounded operators, equal-time fields, two-point functions as distributions, Wick products, time-ordered products, and renormalization of singular products.

## Research status

The distributional nature of Wightman fields is an established part of axiomatic QFT. It is also central in algebraic QFT, perturbative algebraic QFT, and QFT on curved spacetimes.

The active frontier is not whether fields are distributional; it is how to construct and compare the relevant distributional objects in interacting theories, gauge theories, curved spacetimes, conformal theories, and scaling limits. In perturbative settings, microlocal analysis and Epstein–Glaser methods give precise control over singular products. In nonperturbative constructive settings, proving the existence of the limiting distributional fields remains highly model-dependent.

## Exercises

### Exercise 1: Smearing the two-point function

Let $\Delta_+(x-y)$ be the positive-frequency two-point distribution of a free scalar field. For test functions $f,g$, define

$$
W_2(f,g)
=
\int d^dx\,d^dy\,f(x)g(y)\Delta_+(x-y).
$$

Explain why this expression is better defined than $\Delta_+(x-y)$ evaluated at $x=y$.

<details>
<summary><strong>Solution</strong></summary>

The distribution $\Delta_+(x-y)$ is singular near coincident points. It is not meant to be evaluated as an ordinary function at $x=y$. The smeared expression pairs the distribution with the smooth compactly supported or Schwartz test function $(x,y)\mapsto f(x)g(y)$. That pairing is part of the definition of a distribution and is therefore meaningful under the usual hypotheses.

</details>

### Exercise 2: Why the free field is not pointwise

Using the formal identity

$$
\langle\Omega,\phi(x)^2\Omega\rangle
\sim
\int \frac{d^3\mathbf p}{(2\pi)^3\,2E_{\mathbf p}},
$$

show that the point field of a free scalar in four-dimensional spacetime cannot be an ordinary operator on the vacuum with finite norm.

<details>
<summary><strong>Solution</strong></summary>

If $\phi(x)$ were an operator such that $\phi(x)\Omega$ were a Hilbert-space vector, its norm squared would be $\langle\Omega,\phi(x)^2\Omega\rangle$. The displayed integral behaves at large $|\mathbf p|$ like

$$
\int^\infty \frac{p^2\,dp}{p}
=
\int^\infty p\,dp,
$$

which diverges. Smearing inserts the rapidly decaying Fourier transform of a test function and makes the corresponding one-particle norm finite.

</details>

### Exercise 3: Locality with supports

Suppose $[\phi(x),\phi(y)]=i\Delta(x-y)$ in the distributional sense and $\operatorname{supp}\Delta$ is contained in the causal cone. Explain why $[\phi(f),\phi(g)]=0$ when $\operatorname{supp}f$ and $\operatorname{supp}g$ are spacelike separated.

<details>
<summary><strong>Solution</strong></summary>

The smeared commutator is the pairing of $\Delta(x-y)$ with $f(x)g(y)$. If every point in $\operatorname{supp}f$ is spacelike separated from every point in $\operatorname{supp}g$, then $x-y$ never lies in the causal cone on the support of $f(x)g(y)$. Since $\Delta$ is supported inside the causal cone, the pairing vanishes.

</details>

### Exercise 4: What smearing does not define

Does the existence of $\phi(f)$ for every test function $f$ automatically define a composite field $\phi^2(h)$? Explain.

<details>
<summary><strong>Solution</strong></summary>

No. The operator $\phi(f)$ is a smeared single field. A composite field $\phi^2(h)$ would require multiplying the distributional kernel $\phi(x)$ by itself at the same point before smearing with $h(x)$. Products of distributions at coincident points are not automatic. In free theories one can often define Wick powers such as $:\!\phi^2\!:(h)$; in interacting theories this becomes part of renormalization.

</details>

## References

- A. S. Wightman, "How It Was Learned that Quantized Fields Are Operator-Valued Distributions," *Fortschritte der Physik* **44** (1996), 143–178. DOI: [10.1002/prop.2190440204](https://doi.org/10.1002/prop.2190440204).
- L. Gårding and A. S. Wightman, "Fields as Operator-Valued Distributions in Relativistic Quantum Theory," *Arkiv för Fysik* **28** (1964/65), 129–184.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).
- R. Haag, *Local Quantum Physics: Fields, Particles, Algebras*, Springer. DOI: [10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics II: Fourier Analysis, Self-Adjointness*, Academic Press.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, Springer. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- S. Hollands and R. M. Wald, "Quantum Fields in Curved Spacetime," *Physics Reports* **574** (2015), 1–35. DOI: [10.1016/j.physrep.2015.02.001](https://doi.org/10.1016/j.physrep.2015.02.001), arXiv: [1401.2026](https://arxiv.org/abs/1401.2026).
- R. Brunetti and K. Fredenhagen, "Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds," *Communications in Mathematical Physics* **208** (2000), 623–661. arXiv: [math-ph/9903028](https://arxiv.org/abs/math-ph/9903028).

## Version history

- **2026-06-28:** Initial polished draft for the Operator-Valued Distributions chapter.
