---
title: "Distributions in QFT"
description: "A QFT-focused guide to operator-valued distributions, smeared fields, propagators, contact terms, spectral densities, and the distributional meaning of local quantum fields."
sidebar:
  label: "Distributions in QFT"
  order: 7
level: Graduate
status: "Polished draft"
source: "Standard distribution theory, Wightman-style field theory, and graduate QFT treatments of propagators, time ordering, canonical commutators, Ward identities, and renormalized composite operators."
topics:
  - operator-valued distributions
  - propagators
  - contact terms
  - Wightman functions
  - QFT smearing
canonicalTopics:
  - operator-valued-distributions
  - qft-propagators-as-distributions
  - contact-terms
  - qft-distribution-theory
researchStatus:
  established:
    - "Local quantum fields and their correlation functions are naturally treated as distributions, with smearing providing the mathematically meaningful operation."
  active:
    - "The rigorous construction of interacting fields, gauge-theory observables, renormalized products, and distributional products at coincident points remains a central theme in mathematical and constructive QFT."
---

## Summary

The most important distributional lesson in QFT is simple and slightly brutal:

$$
\text{a local quantum field is not usually an operator at a point.}
$$

It is an operator-valued distribution. The expression $\phi(x)$ is shorthand for the object that becomes an operator only after smearing against a smooth test function:

$$
\phi(f)=\int d^dx\,f(x)\phi(x).
$$

Correlation functions are distributions for the same reason. The two-point function $\langle 0|T\phi(x)\phi(y)|0\rangle$ is not merely a function with a singularity at $x=y$. It is a distribution on spacetime pairs, with a specified boundary condition, a pole prescription, and contact terms.

This viewpoint is not mathematical ornamentation. It is how equal-time commutators, propagator equations, Ward identities, spectral representations, anomalies, and renormalized composite operators actually make sense.

:::note[The practical rule]
When a QFT formula contains coincident points, delta functions, time ordering, propagator denominators, or local operator products, read it first as a distributional identity. Only then ask whether it has a pointwise interpretation.
:::

## Prerequisites

You should know the [Mathematical Conventions](/math-toolkit/conventions/), especially the metric and Fourier conventions. The pages on [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/), [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/), [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/), [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/), and [Principal Values](/math-toolkit/analysis-distributions-fourier/principal-values/) are the immediate background.

You do not need axiomatic QFT for a first pass. The goal here is operational: to make the distributional content of standard graduate-QFT formulas explicit enough that the formulas stop lying to you.

## Core idea

A classical smooth field assigns a number, vector, spinor, or tensor to each point. A quantum field is more singular. The point $x$ is too sharp a probe; it asks for arbitrarily high momentum information. The physically and mathematically meaningful object is a smeared field

$$
\phi(f)=\int d^dx\,f(x)\phi(x),
$$

where $f$ is smooth and controlled.

The same idea applies to correlation functions. Instead of treating

$$
W_2(x,y)=\langle \Omega|\phi(x)\phi(y)|\Omega\rangle
$$

as an ordinary function, treat it as the bilinear pairing

$$
W_2(f,g)=\int d^dx\,d^dy\,f(x)g(y)W_2(x,y).
$$

In free theories this can often be computed explicitly. In interacting theories it is the correct conceptual starting point, even when the exact distribution is not known.

The price of locality is singularity. The reward is that the singularities are highly structured.

## Setup and conventions

Unless stated otherwise, this page uses Minkowski spacetime with mostly-minus metric

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
\qquad
p^2=(p^0)^2-\mathbf p^2.
$$

The Lorentzian Fourier convention is

$$
f(x)=\int_p e^{-ip\cdot x}\widetilde f(p),
\qquad
\widetilde f(p)=\int d^4x\,e^{ip\cdot x}f(x),
\qquad
\int_p=\int\frac{d^4p}{(2\pi)^4}.
$$

The Klein–Gordon operator is

$$
\Box+m^2,
\qquad
\Box=\partial_\mu\partial^\mu=\partial_t^2-\nabla^2.
$$

With the inverse transform $e^{-ip\cdot x}$,

$$
(\Box+m^2)e^{-ip\cdot x}=-(p^2-m^2)e^{-ip\cdot x}.
$$

This sign is responsible for the common identity

$$
(\Box+m^2)D_F(x)=-i\delta^{(4)}(x)
$$

when

$$
D_F(x)=\int_p \frac{i\,e^{-ip\cdot x}}{p^2-m^2+i0}.
$$

## Why point fields are too sharp

A free scalar field has the formal mode expansion

$$
\phi(x)=\int\frac{d^3\mathbf p}{(2\pi)^3}\frac{1}{\sqrt{2E_{\mathbf p}}}
\left(a_{\mathbf p}e^{-ip\cdot x}+a_{\mathbf p}^\dagger e^{ip\cdot x}\right),
\qquad
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

This is a superb physicist's formula and a dangerous operator formula. At fixed $x$, the integral samples all momenta. The result is generally not a well-defined operator on the Hilbert space in the same way that the harmonic-oscillator position operator is.

Smearing repairs the problem:

$$
\phi(f)=\int d^4x\,f(x)\phi(x).
$$

For good $f$, the Fourier transform $\widetilde f(p)$ suppresses high momenta, and the creation-annihilation expression becomes a controlled operator on a suitable dense domain.

A useful analogy is the delta function. The symbol $\delta(x)$ is not a number-valued function at $x=0$; it is defined by its action on test functions. Likewise, the symbol $\phi(x)$ is not usually a Hilbert-space operator at $x$; it is defined by smearing.

## Smeared fields

For a real scalar field, the smeared field is formally self-adjoint when the smearing function is real:

$$
\phi(f)^\dagger=\phi(\overline f).
$$

If $f$ and $g$ are spacetime test functions, the commutator of free fields is

$$
[\phi(f),\phi(g)]
=i\int d^4x\,d^4y\,f(x)g(y)\Delta(x-y),
$$

where $\Delta$ is the Pauli–Jordan commutator distribution.

At equal time, canonical quantization is written as

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

Distributionally, this means

$$
[\phi(t,f),\pi(t,g)]
=i\int d^3\mathbf x\,f(\mathbf x)g(\mathbf x),
$$

where

$$
\phi(t,f)=\int d^3\mathbf x\,f(\mathbf x)\phi(t,\mathbf x),
\qquad
\pi(t,g)=\int d^3\mathbf x\,g(\mathbf x)\pi(t,\mathbf x).
$$

No $\delta^{(3)}(0)$ appears. That symbol appears only when the smearing has been forgotten.

## Correlators as distributions

The $n$-point Wightman distribution of scalar fields is

$$
W_n(x_1,\ldots,x_n)
=\langle \Omega|\phi(x_1)\cdots\phi(x_n)|\Omega\rangle.
$$

Its smeared version is

$$
W_n(f_1,\ldots,f_n)
=\int \prod_{j=1}^n d^4x_j\,f_j(x_j)\,
W_n(x_1,\ldots,x_n).
$$

This is the object with direct distributional meaning.

If the vacuum is translation invariant, then

$$
W_n(x_1+a,\ldots,x_n+a)=W_n(x_1,\ldots,x_n).
$$

In momentum space this gives an overall conservation delta function:

$$
\widetilde W_n(p_1,\ldots,p_n)
=(2\pi)^4\delta^{(4)}\left(\sum_{j=1}^n p_j\right)
\widetilde W_n^{\operatorname{red}}(p_1,\ldots,p_n).
$$

The reduced distribution $\widetilde W_n^{\operatorname{red}}$ contains the nontrivial dependence. The overall delta function records translation invariance.

This is also the clean way to understand the notorious symbol $\delta^{(4)}(0)$. If one squares an amplitude before dividing by the spacetime volume, one can produce a formal $\delta^{(4)}(0)$. In a finite box it is a volume factor; in infinite volume it is a reminder that one has not yet formed a rate, density, or properly normalized observable.

## Free scalar two-point distributions

The positive-frequency two-point distribution is

$$
\Delta_+(x)
=\langle 0|\phi(x)\phi(0)|0\rangle
=\int\frac{d^3\mathbf p}{(2\pi)^3}\frac{1}{2E_{\mathbf p}}e^{-ip\cdot x},
\qquad p^0=E_{\mathbf p}.
$$

It solves the homogeneous Klein–Gordon equation distributionally:

$$
(\Box+m^2)\Delta_+(x)=0.
$$

The commutator distribution is

$$
[\phi(x),\phi(y)]=i\Delta(x-y),
$$

with

$$
i\Delta(x)=\Delta_+(x)-\Delta_+(-x),
\qquad
\Delta(x)=-i\left(\Delta_+(x)-\Delta_+(-x)\right).
$$

With this convention, $\Delta(x)$ is the real Pauli–Jordan function. For a relativistic scalar field, $\Delta(x)$ vanishes at spacelike separation. This is the distributional form of microcausality:

$$
[\phi(x),\phi(y)]=0
\qquad \text{if }(x-y)^2<0.
$$

The Feynman two-point function is

$$
D_F(x-y)
=\langle 0|T\phi(x)\phi(y)|0\rangle
=\int_p \frac{i\,e^{-ip\cdot(x-y)}}{p^2-m^2+i0}.
$$

It is a Green distribution:

$$
(\Box_x+m^2)D_F(x-y)=-i\delta^{(4)}(x-y).
$$

This is not a pointwise differential equation at $x=y$. It is a distributional identity. Away from $x=y$, the Feynman propagator solves the homogeneous equation; the delta function is the contact source at coincidence.

## Retarded and advanced Green distributions

The retarded and advanced Green distributions are built from the commutator distribution:

$$
D_R(x)=\theta(x^0)\Delta(x),
\qquad
D_A(x)=-\theta(-x^0)\Delta(x).
$$

They obey the same inhomogeneous Klein–Gordon equation up to the conventional normalization chosen for $\Delta$:

$$
(\Box+m^2)D_R(x)=-\delta^{(4)}(x),
\qquad
(\Box+m^2)D_A(x)=-\delta^{(4)}(x)
$$

when $D_R$ and $D_A$ are defined without the extra factor of $i$ used in $D_F$.

Their support encodes causality:

$$
\operatorname{supp}D_R\subseteq \{x:x^0\ge0,\ x^2\ge0\},
\qquad
\operatorname{supp}D_A\subseteq \{x:x^0\le0,\ x^2\ge0\}.
$$

Momentum-space denominators remember this support through pole prescriptions. For example,

$$
\frac{1}{(p^0+i0)^2-E_{\mathbf p}^2}
$$

is the retarded denominator: both poles lie below the $p^0$ contour.

## Pole prescriptions as distributions

The scalar denominator is not an ordinary reciprocal on the mass shell. It is a boundary-value distribution:

$$
\frac{1}{p^2-m^2+i0}
=\operatorname{PV}\frac{1}{p^2-m^2}-i\pi\delta(p^2-m^2).
$$

Therefore

$$
\frac{i}{p^2-m^2+i0}
=i\operatorname{PV}\frac{1}{p^2-m^2}+\pi\delta(p^2-m^2).
$$

The delta term is supported on shell. The principal-value term is the off-shell boundary-value remnant. Their combination is the Feynman distribution.

This split is often useful, but the full $i0$ expression is usually safer. It knows how the poles move in the complex $p^0$ plane; the separated principal-value and delta pieces can obscure that causal information if handled carelessly.

## Contact terms

A contact term is a distribution supported on coincident points. In two variables, it is supported on the diagonal

$$
\Delta_2=\{(x_1,x_2):x_1=x_2\}.
$$

Typical examples are

$$
\delta^{(4)}(x-y),
\qquad
\partial_\mu\delta^{(4)}(x-y),
\qquad
P(\partial)\delta^{(4)}(x-y)
$$

for a polynomial differential operator $P(\partial)$.

<figure class="doc-figure" style="--figure-width: 38rem;">

![Contact terms supported on the coincidence diagonal](/figures/math-toolkit/contact-terms-diagonal.svg)

<figcaption>

A contact term is invisible at separated points but lives on the coincidence diagonal. Renormalizing products of local fields amounts to extending distributions from separated configurations to the diagonal, with local ambiguities supported there.

</figcaption>
</figure>

Contact terms are not disposable. They carry the local information in many identities.

For instance, differentiating a time-ordered product gives

$$
\partial_t T(A(t)B(t'))
=T((\partial_t A(t))B(t'))+\delta(t-t')[A(t),B(t')]
$$

for bosonic operators, with graded signs for fermionic operators. The derivative of the step function produces the delta function.

This mechanism explains the contact source in the Feynman propagator equation. Away from $x=y$, the propagator solves the homogeneous equation. At $x=y$, differentiating the time ordering produces the canonical commutator, hence the delta function.

## Ward identities and local insertions

Ward identities are distributional identities. A schematic current-conservation identity has the form

$$
\partial_\mu^x\langle Tj^\mu(x)O_1(x_1)\cdots O_n(x_n)\rangle
=-i\sum_{k=1}^n \delta^{(4)}(x-x_k)
\langle T O_1(x_1)\cdots \delta O_k(x_k)\cdots O_n(x_n)\rangle
+\mathcal A(x;x_1,\ldots,x_n),
$$

where $\delta O_k$ is the infinitesimal symmetry variation of $O_k$, and $\mathcal A$ denotes possible anomaly or improvement contact terms.

The separated-point equation may simply say

$$
\partial_\mu j^\mu=0.
$$

The full QFT statement is stronger and more singular: the current insertion has contact terms when it collides with charged operators. Those contact terms encode the charge action on the operators.

This is why a Ward identity cannot be checked only at separated points. The local terms are often the whole point.

## Composite operators and products

The product $\phi(x)^2$ is not automatically defined, even in a free theory. The two fields become singular as their points approach each other:

$$
\langle 0|\phi(x)\phi(y)|0\rangle
\quad \text{is singular as }x\to y.
$$

In a free scalar theory, one defines normal ordering by subtracting the vacuum contraction:

$$
:\phi^2:(x)
=\lim_{y\to x}\left(\phi(x)\phi(y)-\langle 0|\phi(x)\phi(y)|0\rangle\right),
$$

understood after smearing or as a distributional limiting operation.

In interacting QFT, composite operators require renormalization. Different renormalization prescriptions can differ by local terms:

$$
[O]_R\longrightarrow [O]_R+\sum_i c_i[O_i]_R,
$$

where the $O_i$ are operators with the same symmetries and appropriate dimension. In correlation functions, such changes appear as contact terms.

A useful mathematical phrase is: renormalization extends a distribution defined away from the coincidence diagonal to a distribution on the full configuration space. The extension is not always unique. The ambiguity is local, hence supported on the diagonal.

## Operator products and the OPE

The operator product expansion is a controlled way of describing the singularity as points approach:

$$
O_i(x)O_j(0)\sim \sum_k C_{ij}{}^k(x)O_k(0).
$$

The coefficient functions $C_{ij}{}^k(x)$ are themselves distributions or singular functions that require interpretation near $x=0$. The OPE does not say that the pointwise product is harmless. It says that the singular product can be expanded in a basis of local operators with distributional coefficients.

Contact terms are part of this story. They are invisible for $x\neq0$ but affect integrated identities, Ward identities, anomalies, and scheme dependence.

## Fermions and spinor distributions

Fermion fields are also operator-valued distributions, with anticommutators instead of commutators. For a Dirac field,

$$
\{\psi_\alpha(t,\mathbf x),\psi_\beta^\dagger(t,\mathbf y)\}
=\delta_{\alpha\beta}\delta^{(3)}(\mathbf x-\mathbf y)
$$

means that after smearing,

$$
\{\psi(f),\psi^\dagger(g)\}
=\int d^3\mathbf x\,f^\alpha(\mathbf x)\overline{g_\alpha(\mathbf x)}.
$$

The free Dirac Feynman propagator is

$$
S_F(x)=\int_p e^{-ip\cdot x}\,\frac{i(p\!\!\!/+m)}{p^2-m^2+i0},
\qquad
p\!\!\!/\equiv \gamma^\mu p_\mu.
$$

It satisfies

$$
(i\gamma^\mu\partial_\mu-m)S_F(x)=i\delta^{(4)}(x).
$$

Again, the equation is distributional. The numerator $p\!\!\!/+m$ does not remove the pole; it records the spinor structure of the same mass-shell distribution.

## Gauge fields and ghosts

Gauge potentials $A_\mu(x)$ are also distributions after quantization. In covariant gauges their propagators contain both pole prescriptions and gauge-parameter-dependent tensor structures. The gauge-dependent propagator is not itself a physical observable, but it is still a distribution that must be handled consistently.

Ghost fields in gauge-fixed path integrals are Grassmann-valued distributions. Their propagators are singular kernels, and their contact terms are part of BRST and Slavnov–Taylor identities.

Gauge-invariant extended operators, such as Wilson lines, bring additional distributional issues. A line operator samples the gauge field along a lower-dimensional submanifold, and products or self-intersections can require their own renormalization. This is one reason line and defect operators are mathematically more delicate than their compact notation suggests.

## Euclidean distributions

Euclidean correlation functions, or Schwinger functions, are also distributions. In a free scalar theory,

$$
G_E(x)=\int\frac{d^dp}{(2\pi)^d}\,\frac{e^{ip\cdot x}}{p^2+m^2}
$$

solves

$$
(-\partial^2+m^2)G_E(x)=\delta^{(d)}(x).
$$

Euclidean formulas often look more like ordinary integrals because the denominator has no real mass-shell pole. But short-distance singularities at $x=0$ remain. Composite operators, coincident limits, and contact terms still require distributional care.

Analytic continuation between Euclidean and Lorentzian correlators is also a statement about boundary values. The Lorentzian $i0$ prescription remembers from which side of complexified time or energy one approaches the real slice.

## Spectral representations

In a unitary Lorentz-invariant theory, scalar two-point functions admit spectral representations under suitable assumptions. A standard schematic form is

$$
D_F(p)=\int_0^\infty d\mu^2\,\rho(\mu^2)\frac{i}{p^2-\mu^2+i0}
+\text{local polynomial terms}.
$$

The spectral density $\rho(\mu^2)$ is nonnegative for a Hermitian scalar operator in a positive-norm Hilbert space. The local polynomial terms are contact terms in position space.

This representation shows how several distributional ideas fit together:

| Piece | Distributional meaning |
|---|---|
| $i/(p^2-\mu^2+i0)$ | Boundary-value distribution with Feynman prescription. |
| $\rho(\mu^2)$ | Positive measure over invariant masses. |
| Polynomial in $p$ | Derivatives of delta functions in position space. |
| Discontinuity across the cut | On-shell spectral support. |

The exact spectral density is dynamical. The distributional form is kinematical.

## How to read QFT formulas distributionally

Many standard formulas become safer if translated into distributional language.

| Physicist shorthand | Distributional reading |
|---|---|
| $\phi(x)$ | An operator-valued distribution to be smeared as $\phi(f)$. |
| $[\phi(\mathbf x),\pi(\mathbf y)]=i\delta^{(3)}(\mathbf x-\mathbf y)$ | Equality after smearing in $\mathbf x$ and $\mathbf y$. |
| $D_F(x)=\int_p i e^{-ipx}/(p^2-m^2+i0)$ | Boundary-value distribution with a specified pole prescription. |
| $(\Box+m^2)D_F=-i\delta$ | Green identity with a contact source. |
| $\partial_\mu j^\mu=0$ inside correlators | Conservation away from insertions, plus contact terms at charged insertions. |
| $O_i(x)O_j(0)$ | Singular product requiring OPE, normal ordering, or renormalization. |
| $\delta^{(4)}(0)$ | Unremoved volume factor or an ill-formed coincident distribution. |

This translation is not pedantry. It is the grammar of local QFT.

## Common pitfalls

**Treating fields as ordinary functions.** A local quantum field is generally not a pointwise function or a pointwise operator. Smearing is not optional cleanup; it is part of the definition.

**Forgetting that time ordering differentiates step functions.** Derivatives of time-ordered products produce contact terms. Many equations of motion and Ward identities are wrong without them.

**Dropping contact terms because they vanish at separated points.** Contact terms can determine charges, anomalies, Schwinger terms, operator mixing, and counterterms. Vanishing away from coincidence does not mean physically irrelevant.

**Writing $\delta(0)$ as though it were a large number.** The expression usually means that a distribution was evaluated at a point or that an infinite volume factor has not been divided out.

**Multiplying distributions without checking singularities.** Products like $D_F(x)^2$ at the same point are not automatically defined. They require regularization and renormalization.

**Confusing a Green function with a propagator.** A Green function is an inverse of a differential operator with boundary conditions. A QFT propagator also knows about vacuum choice, time ordering, causality, gauge fixing, or thermal state.

**Thinking Euclidean signature removes all distributional issues.** Euclidean propagators avoid real-time pole prescriptions but retain short-distance singularities and contact terms.

## Relations to other pages

[Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) gives the basic pairing language. [Delta Functions](/math-toolkit/analysis-distributions-fourier/delta-functions/) explains the delta sources and constraint distributions used here. [Test Functions and Tempered Distributions](/math-toolkit/analysis-distributions-fourier/test-functions-and-tempered-distributions/) explains why smearing is the natural operation. [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/) fixes the signs in the propagator formulas. [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/) explains Green functions as kernels. [Principal Values](/math-toolkit/analysis-distributions-fourier/principal-values/) derives the $i0$ identities used in propagator prescriptions.

This page is the bridge from the mathematical chapter to later physics pages on free fields, canonical quantization, path integrals, Ward identities, spectral representations, loop integrals, and renormalized composite operators.

## Research status

The distributional nature of local fields and correlators is established. It is central to Wightman QFT, perturbative QFT, constructive QFT, algebraic QFT, and practical calculations with propagators.

What remains subtle is not the slogan but the construction and manipulation of interacting examples. Products of fields at coincident points require renormalization. Gauge theories require quotienting or cohomological treatment of redundant degrees of freedom. Nonperturbative continuum limits may be hard to construct. In curved spacetime, even defining preferred states and renormalized stress tensors requires care.

The operational rule remains stable across these settings: local QFT identities should be read as identities of distributions, with contact terms and domains made explicit when they matter.

## Exercises

### Exercise 1: Smearing the canonical commutator

Start from the equal-time distributional relation

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(3)}(\mathbf x-\mathbf y).
$$

Show that

$$
[\phi(t,f),\pi(t,g)]=i\int d^3\mathbf x\,f(\mathbf x)g(\mathbf x).
$$

<details><summary><strong>Solution</strong></summary>

By definition,

$$
\phi(t,f)=\int d^3\mathbf x\,f(\mathbf x)\phi(t,\mathbf x),
\qquad
\pi(t,g)=\int d^3\mathbf y\,g(\mathbf y)\pi(t,\mathbf y).
$$

Therefore

$$
[\phi(t,f),\pi(t,g)]
=\int d^3\mathbf x\,d^3\mathbf y\,f(\mathbf x)g(\mathbf y)
[\phi(t,\mathbf x),\pi(t,\mathbf y)].
$$

Insert the canonical commutator:

$$
[\phi(t,f),\pi(t,g)]
=i\int d^3\mathbf x\,d^3\mathbf y\,f(\mathbf x)g(\mathbf y)
\delta^{(3)}(\mathbf x-\mathbf y).
$$

Using the delta distribution gives

$$
[\phi(t,f),\pi(t,g)]
=i\int d^3\mathbf x\,f(\mathbf x)g(\mathbf x).
$$

</details>

### Exercise 2: The scalar Feynman Green equation

Using

$$
D_F(x)=\int_p \frac{i\,e^{-ip\cdot x}}{p^2-m^2+i0},
$$

show that

$$
(\Box+m^2)D_F(x)=-i\delta^{(4)}(x).
$$

<details><summary><strong>Solution</strong></summary>

With the site convention $e^{-ip\cdot x}$,

$$
(\Box+m^2)e^{-ip\cdot x}=-(p^2-m^2)e^{-ip\cdot x}.
$$

Therefore

$$
(\Box+m^2)D_F(x)
=\int_p i\,\frac{-(p^2-m^2)}{p^2-m^2+i0}e^{-ip\cdot x}.
$$

As a distribution, the ratio is $1$ away from the pole and gives the identity after the boundary-value prescription is applied. Thus

$$
(\Box+m^2)D_F(x)
=-i\int_p e^{-ip\cdot x}
=-i\delta^{(4)}(x).
$$

</details>

### Exercise 3: Momentum conservation delta functions

Suppose a two-point function is translation invariant:

$$
W_2(x,y)=F(x-y).
$$

Show that its Fourier transform contains $\delta^{(4)}(p+q)$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\widetilde W_2(p,q)=\int d^4x\,d^4y\,e^{ip\cdot x+iq\cdot y}F(x-y).
$$

Set $u=x-y$ and $v=y$. Then $x=u+v$, so

$$
\widetilde W_2(p,q)
=\int d^4u\,d^4v\,e^{ip\cdot(u+v)+iq\cdot v}F(u).
$$

This becomes

$$
\widetilde W_2(p,q)
=\left(\int d^4v\,e^{i(p+q)\cdot v}\right)
\left(\int d^4u\,e^{ip\cdot u}F(u)\right).
$$

The $v$ integral is

$$
(2\pi)^4\delta^{(4)}(p+q),
$$

so translation invariance gives momentum conservation.

</details>

### Exercise 4: Contact term from time ordering

Let

$$
T(A(t)B(t'))=\theta(t-t')A(t)B(t')+\theta(t'-t)B(t')A(t)
$$

for bosonic operators. Differentiate with respect to $t$ and show that a commutator contact term appears.

<details><summary><strong>Solution</strong></summary>

Differentiate:

$$
\partial_t T(A(t)B(t'))
=\delta(t-t')A(t)B(t')+\theta(t-t')(\partial_tA(t))B(t')
$$

$$
-\delta(t'-t)B(t')A(t)+\theta(t'-t)B(t')(\partial_tA(t)).
$$

Since $\delta(t'-t)=\delta(t-t')$, the delta terms combine into

$$
\delta(t-t')\left(A(t)B(t')-B(t')A(t)\right)
=\delta(t-t')[A(t),B(t')].
$$

The remaining terms form

$$
T((\partial_tA(t))B(t')).
$$

Hence

$$
\partial_t T(A(t)B(t'))
=T((\partial_tA(t))B(t'))+\delta(t-t')[A(t),B(t')].
$$

</details>

### Exercise 5: Why normal ordering subtracts a distribution

In a free scalar theory, explain why the definition

$$
:\phi^2:(x)=\lim_{y\to x}\left(\phi(x)\phi(y)-\langle0|\phi(x)\phi(y)|0\rangle\right)
$$

should be understood distributionally rather than pointwise.

<details><summary><strong>Solution</strong></summary>

The contraction

$$
\langle0|\phi(x)\phi(y)|0\rangle
$$

is singular as $y\to x$. The product $\phi(x)\phi(y)$ is therefore also singular in matrix elements. The subtraction removes the singular vacuum part, but the limiting operation is still a limit of distributions, not ordinary pointwise functions.

A safe definition smears the expression against a test function or introduces a regulator, subtracts the singular term, and then removes the regulator. In interacting theories, additional local subtractions may be required.

</details>

### Exercise 6: Local polynomial terms

Why does a polynomial in momentum space correspond to a contact term in position space?

<details><summary><strong>Solution</strong></summary>

With the Lorentzian Fourier convention,

$$
\int_p e^{-ip\cdot x}=\delta^{(4)}(x).
$$

Multiplication by $p_\mu$ in momentum space corresponds to $i\partial_\mu$ acting on the position-space distribution, because

$$
i\partial_\mu e^{-ip\cdot x}=p_\mu e^{-ip\cdot x}.
$$

Therefore a polynomial $P(p)$ Fourier transforms to

$$
P(i\partial)\delta^{(4)}(x),
$$

up to the precise index convention in $P$. This is supported at $x=0$, so it is a contact term.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, for free fields, propagators, canonical commutators, path integrals, and practical distributional identities.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for propagators, time ordering, path integrals, Ward identities, and spectral decompositions.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for Wigner-particle foundations, fields, propagators, spectral representations, and scattering theory.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for field operators, Green functions, LSZ, functional methods, and the physics of contact terms.

### Deeper references

- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for the operator-valued distribution viewpoint in axiomatic QFT.
- R. Haag, *Local Quantum Physics*, for the algebraic perspective on local observables.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for constructive and Euclidean methods.
- L. Hörmander, *The Analysis of Linear Partial Differential Operators*, Vol. I, for the distributional and microlocal background behind singular products and wavefront sets.
- K. Fredenhagen and K. Rejzner, *Perturbative Algebraic Quantum Field Theory*, for a modern account of time-ordered products, renormalization, and local covariance.

## Version history

- **2026-06-24:** Initial polished draft. Explained smeared fields, correlators as distributions, free scalar and Dirac propagators, pole prescriptions, contact terms, Ward identities, composite operators, and spectral representations.
