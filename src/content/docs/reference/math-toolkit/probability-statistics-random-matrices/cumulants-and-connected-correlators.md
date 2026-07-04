---
title: "Cumulants and Connected Correlators"
description: "A QFT-oriented guide to cumulants, connected correlation functions, generating functionals, the linked-cluster theorem, and diagrammatic connectedness."
sidebar:
  label: "Cumulants and Connected Correlators"
  order: 3
level: Graduate
status: "Polished draft"
source: "Probability cumulants, statistical mechanics, Euclidean generating functionals, connected Feynman diagrams, and linked-cluster expansions."
topics:
  - cumulants
  - connected correlators
  - generating functionals
  - linked-cluster theorem
  - Wick theorem
  - cluster decomposition
  - effective action
canonicalTopics:
  - cumulants
  - connected-correlation-functions
  - moment-cumulant-relations
  - generating-functional
  - linked-cluster-theorem
researchStatus:
  established:
    - "Cumulants are the connected parts of moments, and in QFT the logarithm of the generating functional generates connected correlation functions and connected vacuum diagrams."
  active:
    - "In gauge theories, finite-temperature systems, non-equilibrium QFT, and theories with defects or boundaries, defining and interpreting connectedness can require careful choices of state, algebra, regulator, and observable class."
---

## Summary

Cumulants are the pieces of correlation functions that do **not** factor into lower pieces. In probability, they measure the failure of random variables to behave independently. In QFT, they are the connected correlators.

For random variables $X_1,\ldots,X_n$, define the moment-generating function

$$
M(J)=\mathbb E\!\left[\exp\!\left(\sum_iJ_iX_i\right)\right]
$$

and the cumulant-generating function

$$
K(J)=\log M(J).
$$

The cumulant is

$$
\kappa(X_1,\ldots,X_n)
=\left.\frac{\partial^nK}{\partial J_1\cdots \partial J_n}\right|_{J=0}.
$$

In QFT, the same construction is written

$$
Z[J]=\left\langle \exp\!\left(\int d^dx\,J(x)\phi(x)\right)\right\rangle,
\qquad
W[J]=\log Z[J],
$$

and

$$
\langle \phi(x_1)\cdots \phi(x_n)\rangle_c
=\left.\frac{\delta^n W[J]}{\delta J(x_1)\cdots \delta J(x_n)}\right|_{J=0}.
$$

That logarithm is the whole trick. It removes disconnected pieces, removes vacuum bubbles, and turns the generating functional into the right object for physical response, cluster decomposition, and the effective action.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A flowchart showing moments, logarithms, cumulants, connected correlators, and the effective action.](/figures/math-toolkit/cumulant-connected-correlator-flow.svg)

<figcaption>

Moments come from $Z[J]$; connected correlators come from $W[J]=\log Z[J]$. The logarithm implements the same combinatorics as selecting connected diagrams from all diagrams.

</figcaption>
</figure>

## Prerequisites

You should know [Probability Measures](/math-toolkit/probability-statistics-random-matrices/probability-measures/) and the Gaussian generating function from [Gaussian Measures](/math-toolkit/probability-statistics-random-matrices/gaussian-measures/). Familiarity with Wick contractions from [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/) is helpful.

The page uses ordinary finite-dimensional random variables first, then translates the formulas to QFT sources. All functional derivatives are formal unless a regulator or class of smeared test functions has been specified.

## Moments versus cumulants

Moments are ordinary expectation values:

$$
\mu_{i_1\cdots i_n}
=\mathbb E[X_{i_1}\cdots X_{i_n}].
$$

Cumulants are the connected combinations of moments. The first few are:

$$
\kappa(X)=\mathbb E[X],
$$

$$
\kappa(X,Y)=\mathbb E[XY]-\mathbb E[X]\mathbb E[Y],
$$

and

$$
\begin{aligned}
\kappa(X,Y,Z)
={}&\mathbb E[XYZ]
-\mathbb E[XY]\mathbb E[Z]
-\mathbb E[XZ]\mathbb E[Y]
-\mathbb E[YZ]\mathbb E[X] \\
&+2\mathbb E[X]\mathbb E[Y]\mathbb E[Z].
\end{aligned}
$$

For one variable $X$, the first cumulants are

$$
\kappa_1=\mathbb E[X],
$$

$$
\kappa_2=\mathbb E[X^2]-\mathbb E[X]^2,
$$

$$
\kappa_3=\mathbb E[(X-\mathbb E X)^3],
$$

and

$$
\kappa_4=\mathbb E[(X-\mathbb E X)^4]-3\mathbb E[(X-\mathbb E X)^2]^2.
$$

The subtraction in $\kappa_4$ is exactly the removal of the three pairwise disconnected products.

## The partition formula

Let $[n]=\{1,2,\ldots,n\}$. A partition $\pi$ of $[n]$ is a decomposition into disjoint nonempty blocks $B$. The moment-cumulant relation is

$$
\mathbb E[X_1\cdots X_n]
=
\sum_{\pi\in\Pi_n}
\prod_{B\in\pi} \kappa(X_i:i\in B).
$$

Here $\Pi_n$ is the set of all partitions of $[n]$.

For $n=4$, this says

$$
\begin{aligned}
\mathbb E[X_1X_2X_3X_4]
={}&\kappa_{1234}
+\kappa_{123}\kappa_4+\kappa_{124}\kappa_3+\kappa_{134}\kappa_2+\kappa_{234}\kappa_1 \\
&+\kappa_{12}\kappa_{34}+\kappa_{13}\kappa_{24}+\kappa_{14}\kappa_{23} \\
&+\kappa_{12}\kappa_3\kappa_4+\kappa_{13}\kappa_2\kappa_4+\kappa_{14}\kappa_2\kappa_3 \\
&+\kappa_{23}\kappa_1\kappa_4+\kappa_{24}\kappa_1\kappa_3+\kappa_{34}\kappa_1\kappa_2 \\
&+\kappa_1\kappa_2\kappa_3\kappa_4.
\end{aligned}
$$

When all one-point functions vanish, this simplifies to

$$
\mathbb E[X_1X_2X_3X_4]
=\kappa_{1234}+\kappa_{12}\kappa_{34}+\kappa_{13}\kappa_{24}+\kappa_{14}\kappa_{23}.
$$

So the four-point connected correlator is

$$
\kappa_{1234}
=\mathbb E[X_1X_2X_3X_4]
-\mathbb E[X_1X_2]\mathbb E[X_3X_4]
-\mathbb E[X_1X_3]\mathbb E[X_2X_4]
-\mathbb E[X_1X_4]\mathbb E[X_2X_3],
$$

provided all one-point functions vanish.

## Why the logarithm selects connected pieces

The exponential of a sum generates arbitrary collections of objects. The logarithm extracts the connected objects.

This is the same combinatorial fact behind many formulas:

| All objects | Connected objects |
|---|---|
| moments | cumulants |
| $Z[J]$ | $W[J]=\log Z[J]$ |
| all vacuum diagrams | connected vacuum diagrams |
| all correlator diagrams | connected correlator diagrams, after normalization |
| partition function | free energy |

The finite-dimensional proof is short. Suppose

$$
M(J)=\exp K(J).
$$

Derivatives of $M$ distribute among derivatives of $K$ in every possible partition. Therefore moments are sums over products of cumulants. Inverting the relation says cumulants are the connected parts of moments.

In QFT, the same combinatorics appears diagrammatically: disconnected diagrams are unordered products of connected diagrams, so exponentiating connected diagrams gives all diagrams.

## QFT generating functionals

Let $Z[J]$ be the normalized source functional

$$
Z[J]=\left\langle \exp\!\left(\int d^dx\,J(x)\phi(x)\right)\right\rangle,
\qquad
Z[0]=1.
$$

Then ordinary correlators are

$$
G_n(x_1,\ldots,x_n)
=\langle \phi(x_1)\cdots\phi(x_n)\rangle
=\left.\frac{\delta^n Z[J]}{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0}.
$$

Connected correlators are

$$
G_n^c(x_1,\ldots,x_n)
=\langle \phi(x_1)\cdots\phi(x_n)\rangle_c
=\left.\frac{\delta^n W[J]}{\delta J(x_1)\cdots\delta J(x_n)}\right|_{J=0},
$$

where

$$
W[J]=\log Z[J].
$$

Some books use $Z[J]=e^{iW[J]}$ in Lorentzian signature. In Euclidean probability notation, $W=\log Z$ is cleaner. The physics is the same after tracking factors of $i$.

## Two-point and four-point examples

For a scalar field, define

$$
G_1(x)=\langle \phi(x)\rangle.
$$

The connected two-point function is

$$
G_2^c(x,y)
=\langle \phi(x)\phi(y)\rangle
-\langle \phi(x)\rangle\langle\phi(y)\rangle.
$$

If the one-point function vanishes, then

$$
G_2^c(x,y)=G_2(x,y).
$$

The connected four-point function, assuming vanishing one-point functions, is

$$
\begin{aligned}
G_4^c(x_1,x_2,x_3,x_4)
={}&G_4(x_1,x_2,x_3,x_4)
-G_2(x_1,x_2)G_2(x_3,x_4)\\
&-G_2(x_1,x_3)G_2(x_2,x_4)
-G_2(x_1,x_4)G_2(x_2,x_3).
\end{aligned}
$$

This formula is one of the most useful diagnostics of interactions. In a free centered Gaussian scalar theory,

$$
G_4^c=0.
$$

In an interacting theory, $G_4^c$ is generally nonzero.

## Gaussian cumulants

A centered Gaussian has

$$
K(J)=\log M(J)=\frac12J_iC^{ij}J_j.
$$

Since $K$ is quadratic, every cumulant beyond order two vanishes:

$$
\kappa(X_{i_1},\ldots,X_{i_n})=0
\qquad
\text{for }n\ge3.
$$

Thus Wick’s theorem can be rephrased as:

$$
\text{a Gaussian is the distribution with only one- and two-point connected data.}
$$

For a centered free field,

$$
W_0[J]=\frac12\int d^dx\,d^dy\,J(x)G(x,y)J(y),
$$

so

$$
G_2^c(x,y)=G(x,y),
$$

and

$$
G_n^c=0
\qquad
\text{for }n\ge3.
$$

This is why nonzero connected higher-point functions are a clean signal of non-Gaussianity or interaction.

## The linked-cluster theorem

Consider an interacting Euclidean scalar theory written relative to a Gaussian expectation:

$$
Z[J]
=\frac{\mathbb E_0\!\left[\exp\!\left(-S_{\mathrm{int}}[\phi]+\int J\phi\right)\right]}
{\mathbb E_0\!\left[\exp\!\left(-S_{\mathrm{int}}[\phi]\right)\right]}.
$$

The numerator generates diagrams with sources. The denominator cancels disconnected vacuum bubbles. Taking

$$
W[J]=\log Z[J]
$$

then keeps only connected diagrams with external source insertions.

This is the linked-cluster theorem in path-integral language. Its practical consequence is enormous: physical response functions come from connected diagrams, while disconnected vacuum factors exponentiate and cancel in normalized expectation values.

## Free energy as a connected generator

In statistical mechanics, the partition function is

$$
Z=\operatorname{Tr}e^{-\beta H}.
$$

The free energy is

$$
F=-\frac1\beta \log Z.
$$

So the free energy, not the partition function itself, is the connected extensive object. If two systems are independent,

$$
Z_{A\cup B}=Z_AZ_B,
$$

but

$$
F_{A\cup B}=F_A+F_B.
$$

The logarithm turns multiplication of independent pieces into addition of connected thermodynamic pieces. That is the same cumulant mechanism again, now wearing a thermodynamics costume.

## Connectedness and cluster decomposition

Connected correlators are also the natural objects for long-distance physics. In a translationally invariant state, cluster decomposition says that distant experiments become independent in the connected sense:

$$
\langle \mathcal O_1(x)\mathcal O_2(y)\rangle_c
\to 0
\qquad
\text{as }|x-y|\to\infty,
$$

under suitable assumptions such as a unique vacuum and a mass gap.

For a massive theory, connected correlators often decay exponentially:

$$
G_2^c(x,y)\sim e^{-m|x-y|}.
$$

At a critical point, they may decay by a power law:

$$
G_2^c(x,y)\sim \frac1{|x-y|^{2\Delta}}.
$$

The connected correlator is what knows whether the system has long-range order, a mass gap, or critical scaling.

## Susceptibilities and integrated connected correlators

Suppose a source $h$ couples to an observable $M$:

$$
Z(h)=\left\langle e^{hM}\right\rangle.
$$

The susceptibility is the second derivative of $\log Z$:

$$
\chi=\left.\frac{\partial^2}{\partial h^2}\log Z(h)\right|_{h=0}
=\langle M^2\rangle-\langle M\rangle^2.
$$

If

$$
M=\int d^dx\,\mathcal O(x),
$$

then

$$
\chi=\int d^dx\,d^dy\,\langle \mathcal O(x)\mathcal O(y)\rangle_c.
$$

This is why connected correlators appear directly in response theory, critical exponents, and fluctuation-dissipation relations.

## Contact terms

Connected correlators are distributions. Functional derivatives at coincident points may produce contact terms supported on diagonals such as

$$
x_i=x_j.
$$

For example, differentiating composite operators or varying local sources can produce terms proportional to

$$
\delta^{(d)}(x-y).
$$

These terms are not mistakes. They encode short-distance definitions, Ward identities, improvement ambiguities, and renormalization choices. If a formula is meant only away from coincident points, say so. If it is a distributional identity, include the contact terms.

## Connected versus one-particle irreducible

Connected correlators are not the same as one-particle-irreducible vertices.

The connected generator is

$$
W[J]=\log Z[J].
$$

The classical field is

$$
\varphi(x)=\frac{\delta W}{\delta J(x)}.
$$

The 1PI effective action is the Legendre transform

$$
\Gamma[\varphi]=\int d^dx\,J(x)\varphi(x)-W[J],
$$

with $J$ eliminated in favor of $\varphi$.

Then:

| Object | Generated by | Diagram type |
|---|---|---|
| ordinary correlators | $Z[J]$ | all diagrams |
| connected correlators | $W[J]=\log Z[J]$ | connected diagrams |
| 1PI vertices | $\Gamma[\varphi]$ | one-particle-irreducible diagrams |

The two-point connected function and the 1PI two-point vertex are inverse kernels, up to convention-dependent signs and factors:

$$
\int d^dz\,G_c(x,z)\Gamma^{(2)}(z,y)=\delta^{(d)}(x-y).
$$

So connected and 1PI objects are related, but not identical.

## Normalized versus unnormalized functionals

There are two common definitions:

$$
Z_{\mathrm{un}}[J]=\int D\phi\,e^{-S[\phi]+\int J\phi},
$$

and

$$
Z[J]=\frac{Z_{\mathrm{un}}[J]}{Z_{\mathrm{un}}[0]}.
$$

The normalized functional satisfies

$$
Z[0]=1,
\qquad
W[0]=0.
$$

The unnormalized logarithm includes the vacuum free energy:

$$
W_{\mathrm{un}}[0]=\log Z_{\mathrm{un}}[0].
$$

Both conventions are useful. For ordinary correlators, normalization is usually cleaner. For thermodynamics, the absolute vacuum or free energy can be physical, so one keeps $\log Z_{\mathrm{un}}[0]$.

## Cumulants and independence

If two families of random variables $X$ and $Y$ are independent, every mixed cumulant vanishes:

$$
\kappa(X_{i_1},\ldots,X_{i_r},Y_{j_1},\ldots,Y_{j_s})=0
$$

whenever $r,s>0$.

The converse is also true under suitable conditions if all mixed cumulants vanish. This gives a clean interpretation: cumulants measure statistical dependence at a specified order.

In QFT, exact independence of spatial regions is usually too strong because local algebras and constraints can be subtle. Connected correlators instead measure failure of factorization in the chosen state.

## Diagrammatic meaning

In perturbation theory, a correlator can be represented as a sum of diagrams with external legs. A disconnected diagram is a product of connected components. Therefore the full generating functional has the schematic form

$$
Z[J]=\exp\!\left(\sum_{\text{connected diagrams}}\right).
$$

Taking the logarithm gives

$$
W[J]=\sum_{\text{connected diagrams}}.
$$

This is not just a pictorial slogan. It is the exponential formula for combinatorial species applied to Wick contractions. Feynman diagrams are a bookkeeping system for a moment-cumulant expansion.

## Common pitfalls

### Forgetting the logarithm

Derivatives of $Z[J]$ give all correlators. Derivatives of $\log Z[J]$ give connected correlators. This is the single most common source of wrong “connected” formulas.

### Dropping one-point functions silently

Many compact formulas assume $\langle\phi\rangle=0$. If the one-point function is nonzero, connected correlators require additional subtraction terms.

### Confusing connected with irreducible

Connected diagrams need not be one-particle irreducible. A connected diagram can fall apart after cutting one internal line.

### Treating contact terms as optional garbage

Contact terms can be essential for Ward identities, anomalies, and composite-operator renormalization. Ignoring them can break exact identities.

### Assuming Gaussianity from vanishing four-point connected function alone

A Gaussian has all cumulants above order two equal to zero. Vanishing of one higher cumulant is not enough to prove Gaussianity.

### Confusing cluster decomposition with independence

Cluster decomposition is a long-distance property of connected correlators. It is not literal independence of local field variables at finite separation.

## Exercises

### Exercise 1: Derive the two-variable cumulant

Let

$$
M(J_X,J_Y)=\mathbb E[e^{J_XX+J_YY}],
\qquad
K=\log M.
$$

Show that

$$
\left.\frac{\partial^2K}{\partial J_X\partial J_Y}\right|_0
=\mathbb E[XY]-\mathbb E[X]\mathbb E[Y].
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
\partial_X\partial_Y\log M
=\frac{\partial_X\partial_YM}{M}
-\frac{(\partial_XM)(\partial_YM)}{M^2}.
$$

At $J_X=J_Y=0$,

$$
M=1,
\qquad
\partial_XM=\mathbb E[X],
\qquad
\partial_YM=\mathbb E[Y],
$$

and

$$
\partial_X\partial_YM=\mathbb E[XY].
$$

Therefore

$$
\left.\partial_X\partial_YK\right|_0
=\mathbb E[XY]-\mathbb E[X]\mathbb E[Y].
$$

</details>

### Exercise 2: Fourth cumulant of a centered Gaussian

Let $X$ be centered Gaussian with variance $\sigma^2$. Show that

$$
\kappa_4=\mathbb E[X^4]-3\mathbb E[X^2]^2=0.
$$

<details><summary><strong>Solution</strong></summary>

For a centered Gaussian,

$$
\mathbb E[X^2]=\sigma^2.
$$

Wick’s theorem gives

$$
\mathbb E[X^4]=3\sigma^4,
$$

because there are three pairings of four identical variables. Hence

$$
\kappa_4=3\sigma^4-3(\sigma^2)^2=0.
$$

This is the one-variable version of the statement that all Gaussian cumulants beyond order two vanish.

</details>

### Exercise 3: Connected four-point function with zero mean

Assume $\langle\phi(x)\rangle=0$. Express $\langle\phi_1\phi_2\phi_3\phi_4\rangle_c$ in terms of ordinary two- and four-point functions, where $\phi_i=\phi(x_i)$.

<details><summary><strong>Solution</strong></summary>

With zero one-point functions, the partition formula gives

$$
\langle\phi_1\phi_2\phi_3\phi_4\rangle
=\langle\phi_1\phi_2\phi_3\phi_4\rangle_c
+\langle\phi_1\phi_2\rangle_c\langle\phi_3\phi_4\rangle_c
+\langle\phi_1\phi_3\rangle_c\langle\phi_2\phi_4\rangle_c
+\langle\phi_1\phi_4\rangle_c\langle\phi_2\phi_3\rangle_c.
$$

Since zero mean implies $\langle\phi_i\phi_j\rangle_c=\langle\phi_i\phi_j\rangle$, we get

$$
\begin{aligned}
\langle\phi_1\phi_2\phi_3\phi_4\rangle_c
={}&\langle\phi_1\phi_2\phi_3\phi_4\rangle
-\langle\phi_1\phi_2\rangle\langle\phi_3\phi_4\rangle\\
&-\langle\phi_1\phi_3\rangle\langle\phi_2\phi_4\rangle
-\langle\phi_1\phi_4\rangle\langle\phi_2\phi_3\rangle.
\end{aligned}
$$

</details>

### Exercise 4: Additivity of cumulants

Let $X$ and $Y$ be independent random variables. Show that the cumulant-generating function of $X+Y$ is the sum of the cumulant-generating functions of $X$ and $Y$.

<details><summary><strong>Solution</strong></summary>

The moment-generating function of $X+Y$ is

$$
M_{X+Y}(J)=\mathbb E[e^{J(X+Y)}].
$$

Independence gives

$$
M_{X+Y}(J)=\mathbb E[e^{JX}]\mathbb E[e^{JY}]=M_X(J)M_Y(J).
$$

Taking logarithms,

$$
K_{X+Y}(J)=\log M_{X+Y}(J)=\log M_X(J)+\log M_Y(J)=K_X(J)+K_Y(J).
$$

Thus cumulants add for independent sums.

</details>

### Exercise 5: Susceptibility as a connected correlator

Let

$$
Z(h)=\left\langle e^{hM}\right\rangle.
$$

Show that

$$
\left.\frac{d^2}{dh^2}\log Z(h)\right|_{h=0}
=\langle M^2\rangle-\langle M\rangle^2.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{d}{dh}\log Z=\frac{Z'}{Z},
$$

and

$$
\frac{d^2}{dh^2}\log Z=\frac{Z''}{Z}-\frac{(Z')^2}{Z^2}.
$$

At $h=0$,

$$
Z(0)=1,
\qquad
Z'(0)=\langle M\rangle,
\qquad
Z''(0)=\langle M^2\rangle.
$$

Therefore

$$
\left.\frac{d^2}{dh^2}\log Z(h)\right|_{h=0}
=\langle M^2\rangle-\langle M\rangle^2.
$$

</details>

## References

- Billingsley, *Probability and Measure*.
- Feller, *An Introduction to Probability Theory and Its Applications*.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.
- Glimm and Jaffe, *Quantum Physics: A Functional Integral Point of View*.
- Srednicki, *Quantum Field Theory*, chapters on path integrals, perturbation theory, and the quantum action.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*, sections on connected diagrams and effective actions.
- Altland and Simons, *Condensed Matter Field Theory*, sections on functional integration, response functions, and disorder methods.

## Version history

- **2026-06-27:** First polished draft. Introduces cumulants, moment-cumulant relations, generating functionals, connected correlators, Gaussian cumulants, linked-cluster logic, cluster decomposition, susceptibilities, contact terms, and the distinction from 1PI vertices.
