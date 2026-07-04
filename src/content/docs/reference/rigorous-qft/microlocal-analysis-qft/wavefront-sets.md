---
title: "Wavefront Sets"
description: "Defines wavefront sets, explains the product and pullback criteria for distributions, and shows why microlocal singularities are central in rigorous QFT."
sidebar:
  label: "Wavefront Sets"
  order: 1
level: Advanced
status: "Polished draft"
source: "Hörmander; Radzikowski; Brunetti–Fredenhagen–Köhler; Brunetti–Fredenhagen; Hollands–Wald; Rejzner."
topics:
  - microlocal analysis
  - wavefront sets
  - distributions
  - Hadamard states
  - perturbative renormalization
canonicalTopics:
  - microlocal-analysis
  - wavefront-set
  - rigorous-quantum-field-theory
researchStatus:
  established:
    - "Wavefront sets give a coordinate-invariant description of the location and cotangent directions of distributional singularities."
    - "Hörmander's criteria give standard sufficient conditions for products and pullbacks of distributions, and Radzikowski's theorem characterizes Hadamard two-point functions microlocally."
  active:
    - "Microlocal methods continue to organize perturbative QFT on curved spacetimes, gauge theories, boundary problems, and local covariance questions."
---

## Summary

A wavefront set is the part of a distribution that says not only **where** the distribution is singular, but also **in which cotangent directions** it is singular. For a distribution $u$ on a smooth manifold $X$,

$$
\operatorname{WF}(u)\subset T^*X\setminus 0.
$$

The base point $x$ records the location of a singularity. The nonzero covector $\xi\in T_x^*X$ records a direction in which the localized Fourier transform of $u$ fails to decay rapidly.

This extra directional information is exactly what QFT needs. Quantum fields and propagators are distributions. Products such as composite fields, time-ordered products, and powers of propagators are not automatically defined. The basic product test is:

$$
\nexists\,(x,\xi)\in \operatorname{WF}(u)
\quad\text{with}\quad
(x,-\xi)\in \operatorname{WF}(v)
\quad\Longrightarrow\quad
uv\ \text{is defined}.
$$

Microlocal analysis is therefore a bridge between the physicist's singular formulas and rigorous operations on distributions.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Wavefront set directions and product obstruction](/figures/rigorous-qft/wavefront-set.svg)

<figcaption>

Singular support remembers only the bad base point $x_0$. The wavefront set remembers the bad cotangent directions. The product criterion forbids multiplying two distributions when opposite singular covectors occur at the same point.

</figcaption>
</figure>

## Prerequisites

You should know the distributional conventions from [Conventions and Logical Status](/rigorous-qft/conventions/): test functions, distribution pairings, and smearing. You should also be comfortable with Fourier transforms and the cotangent bundle of a smooth manifold.

No deep PDE background is required for the first pass. The point of this page is to make the QFT use of wavefront sets readable before the full machinery of pseudodifferential operators and Fourier integral operators appears.

## Core idea

The singular support of a distribution detects where the distribution is not smooth. That is useful but too crude. A distribution can be singular at a point while being singular only in some directions.

Wavefront sets refine singular support by asking a Fourier question after localizing near a point. If $\chi$ is a smooth cutoff near $x_0$, the Fourier transform $\widehat{\chi u}(\xi)$ tests high-frequency behavior near $x_0$. Smoothness near $x_0$ is equivalent to rapid decay in every direction. Microlocal smoothness in a direction $\xi_0$ means rapid decay in a conic neighborhood of $\xi_0$.

Thus

$$
(x_0,\xi_0)\notin \operatorname{WF}(u)
$$

means: after localizing near $x_0$, the distribution has no high-frequency singularity in the cotangent direction $\xi_0$.

## Setup and conventions

Let $U\subset \mathbb R^n$ be open and let $u\in \mathcal D'(U)$. A subset $\Gamma\subset \mathbb R^n\setminus 0$ is **conic** if $\lambda \Gamma=\Gamma$ for all $\lambda>0$.

Choose $x_0\in U$ and $\xi_0\in \mathbb R^n\setminus 0$. We say that $u$ is microlocally smooth at $(x_0,\xi_0)$ if there exist

$$
\chi\in C_c^\infty(U),
\qquad
\chi(x_0)\ne 0,
$$

and an open conic neighborhood $\Gamma$ of $\xi_0$ such that, for every $N\ge 0$,

$$
\sup_{\xi\in\Gamma}
(1+|\xi|)^N\,
|\widehat{\chi u}(\xi)|
<\infty.
$$

The **wavefront set** $\operatorname{WF}(u)$ is the complement of the set of microlocally smooth pairs:

$$
\operatorname{WF}(u)
=
\{(x,\xi):
 u\ \text{is not microlocally smooth at}\ (x,\xi)\}.
$$

On a smooth manifold $X$, this definition is made in coordinate charts and gives a coordinate-invariant closed conic subset of $T^*X\setminus 0$.

The projection of $\operatorname{WF}(u)$ to the base is the singular support:

$$
\operatorname{sing\,supp}(u)
=
\pi(\operatorname{WF}(u)),
\qquad
\pi:T^*X\to X.
$$

The wavefront set is therefore never smaller in information than the singular support; it is the singular support with directions attached.

## First examples

### Smooth functions

If $f\in C^\infty(X)$, then

$$
\operatorname{WF}(f)=\varnothing.
$$

This is the Fourier version of smoothness: local Fourier transforms of smooth compactly supported functions decay faster than any inverse power.

### Delta function at a point

On $\mathbb R^n$,

$$
\operatorname{WF}(\delta_0)
=
\{(0,\xi):\xi\ne 0\}.
$$

The delta distribution is singular only at the origin, but at that point it is singular in every cotangent direction. Indeed, for a cutoff $\chi$ with $\chi(0)\ne0$,

$$
\widehat{\chi\delta_0}(\xi)=\chi(0),
$$

which does not decay in any direction.

### Jump discontinuity

For the Heaviside distribution $H$ on $\mathbb R$,

$$
\operatorname{WF}(H)=\{(0,\xi):\xi\ne0\}.
$$

The singularity is the jump at $0$. In one dimension there are only two nonzero cotangent directions, and both occur.

### Delta distribution on a submanifold

Let $S\subset X$ be a smooth embedded submanifold. The delta distribution supported on $S$ has wavefront set contained in the conormal bundle,

$$
\operatorname{WF}(\delta_S)\subset N^*S\setminus 0,
$$

and in the basic clean cases equality holds. Here

$$
N^*_xS
=
\{\xi\in T_x^*X:\xi(v)=0\ \text{for all}\ v\in T_xS\}.
$$

This example is the geometric reason wavefront sets live in cotangent space: singularities normal to a surface are covectors annihilating tangent directions.

## Products of distributions

The product of two distributions is not defined by default. Hörmander's product criterion gives a powerful sufficient condition.

Let $u,v\in\mathcal D'(X)$. If there is no point $x\in X$ and nonzero covector $\xi\in T_x^*X$ such that

$$
(x,\xi)\in \operatorname{WF}(u),
\qquad
(x,-\xi)\in \operatorname{WF}(v),
$$

then the product $uv$ is well-defined as a distribution.

When the product exists by this criterion, its wavefront set satisfies

$$
\begin{aligned}
\operatorname{WF}(uv)
\subset{}& \operatorname{WF}(u)\cup \operatorname{WF}(v) \\
&{}\cup
\{(x,\xi+\eta):
(x,\xi)\in \operatorname{WF}(u),\ (x,\eta)\in \operatorname{WF}(v)\}.
\end{aligned}
$$

The intuition is simple: multiplying distributions corresponds locally to convolving their Fourier transforms. If two singular directions can add to zero, high-frequency singularities can collide in an uncontrolled way.

### Why delta squared fails

For $\delta_0$ on $\mathbb R$,

$$
\operatorname{WF}(\delta_0)=\{(0,\xi):\xi\ne0\}.
$$

Both $\xi$ and $-\xi$ occur. Therefore the criterion forbids $\delta_0^2$. This agrees with the usual fact that the square of a delta distribution is not canonically defined.

### Why separated singularities are harmless

If $u$ is singular only near $x=0$ and $v$ is singular only near $x=1$, then no base point carries singular covectors from both distributions. Their product is defined. The obstruction is local in phase space: the same point and opposite directions must occur.

### Sufficient, not necessary

The criterion is sufficient, not logically necessary. When it fails, a product may still be definable after extra choices or by a special structure. In QFT those extra choices are often precisely renormalization choices. The failure of the criterion is a warning that a product is not canonical from distribution theory alone.

## Pullbacks and restrictions

Wavefront sets also control whether a distribution can be pulled back along a smooth map.

Let $f:Y\to X$ be smooth. Define the normal set of $f$ by

$$
N_f
=
\{(f(y),\xi)\in T^*X:
(df_y)^T\xi=0\}.
$$

If

$$
\operatorname{WF}(u)\cap N_f=\varnothing,
$$

then the pullback $f^*u$ is defined as a distribution on $Y$.

Restriction to a submanifold is the special case in which $f$ is an inclusion $i:S\hookrightarrow X$. The obstruction is then the conormal bundle $N^*S$. A distribution can be restricted to $S$ if its wavefront set has no covectors normal to $S$.

This matters in QFT because many tempting operations are restrictions to diagonals. For example, trying to define a composite field by setting two arguments equal is a pullback problem along the diagonal map.

## Why QFT needs wavefront sets

In QFT, the basic objects are rarely honest functions. Wightman functions, Schwinger functions, commutator functions, Feynman propagators, retarded propagators, and time-ordered products are distributions. A product such as

$$
G_F(x,y)^2
$$

is not automatically meaningful near $x=y$. The singularity on the diagonal must be controlled.

Wavefront sets answer three recurring QFT questions:

| QFT operation | Microlocal question |
|---|---|
| Multiply propagators | Do opposite singular covectors occur at the same point? |
| Restrict a correlator to coincident points | Does the wavefront set avoid the conormal bundle of the diagonal? |
| Define time-ordered products | Can the distribution be extended from configuration space without diagonals to the full space? |
| Form Wick powers | Can singular two-point functions be subtracted so the remaining distributional product is defined? |
| Work on curved spacetime | Can the state condition be stated without global Fourier transform? |

The last question is especially important. In Minkowski space, the spectral condition can be stated using energy-momentum support. On a general curved spacetime there is no global translation symmetry and no global momentum space. Wavefront sets provide the replacement: they describe local covector directions of singularities.

## Hadamard states and the microlocal spectrum condition

For a free scalar field on a globally hyperbolic curved spacetime, physical states must have the right short-distance singularity structure. The old Hadamard condition states this using a local parametrix. Radzikowski's microlocal theorem reformulates it as a wavefront-set condition on the two-point function.

Let $\omega_2(x,y)$ be the two-point distribution of a quasifree scalar state. The Hadamard wavefront-set condition is

$$
\operatorname{WF}(\omega_2)
=
\{(x,k_x;y,-k_y):
(x,k_x)\sim(y,k_y),\ k_x\triangleright 0\}.
$$

Here $(x,k_x)\sim(y,k_y)$ means that $x$ and $y$ are connected by a null geodesic and that the covectors are cotangent to that geodesic and parallel transported along it. The notation $k_x\triangleright0$ means future-directed. The minus sign on the $y$ covector reflects that $\omega_2$ is a distribution on $M\times M$.

This formula is one of the key bridges from functional analysis to QFT in curved spacetime. It says that the two-point function has exactly the positive-frequency lightlike singularities expected from the vacuum, but it says so without using a global Fourier transform.

## Renormalization as extension from diagonals

Perturbative QFT often starts with distributions defined away from coincident points. For example, products of propagators are usually well-defined on the configuration space

$$
M^n\setminus\{\text{partial diagonals}\},
$$

where no two problematic points coincide. Renormalization asks whether and how these distributions extend across the diagonals.

Microlocal analysis separates two issues:

1. **Away from diagonals:** Hörmander's product criterion controls whether products are already defined.
2. **At diagonals:** extension theorems and scaling degree control the local ambiguity of extending singular distributions.

This is the rigorous version of the physics statement that counterterms are local. The ambiguity lives where points collide, so it is supported on diagonals and is expressed by local distributions such as derivatives of delta functions.

## Common pitfalls

**Confusing vectors and covectors.** Wavefront directions are covectors. This is not cosmetic: phase functions and Fourier variables naturally live in cotangent space.

**Thinking singular support is enough.** Singular support records where a distribution is singular. It cannot tell whether two singularities have compatible or incompatible directions for multiplication.

**Thinking the product criterion is an if-and-only-if theorem.** The criterion gives a standard sufficient condition. Failure means the product is not canonical from this criterion; it does not prove that no extension or renormalized product can ever be chosen.

**Ignoring the zero section.** Wavefront sets exclude the zero covector. The zero covector carries no direction and is removed from $T^*X$ in the definition.

**Using flat-space momentum intuition on curved spacetime.** A curved spacetime generally lacks global momentum. The wavefront set is local and geometric, which is why it can replace the spectral condition in curved-spacetime QFT.

## Relations to other pages

- [Conventions and Logical Status](/rigorous-qft/conventions/) fixes the distribution notation used here.
- [Physics QFT versus Mathematical QFT](/rigorous-qft/what-is-rigorous-qft/physics-qft-versus-mathematical-qft/) explains why singular physics formulas need a precise mathematical interpretation.
- Later pages on products of distributions, the microlocal spectrum condition, Hadamard two-point functions, and Epstein–Glaser renormalization will use the criteria stated here.
- Later pages on perturbative algebraic QFT will use wavefront sets to control time-ordered products and local covariance.

## Research status

The definition of wavefront sets and the basic product and pullback criteria are standard results in microlocal analysis. Their use in QFT on curved spacetime is also established, especially through the microlocal characterization of Hadamard states and the construction of Wick polynomials and time-ordered products.

Active work continues around gauge theories, boundary conditions, interacting models, local covariance, and refined microlocal tools for perturbative and nonperturbative problems. The main lesson for this volume is settled: singularity directions are part of the data of a quantum field, not a technical afterthought.

## Exercises

### Exercise 1: Delta function

Show that $\operatorname{WF}(\delta_0)=\{(0,\xi):\xi\ne0\}$ on $\mathbb R^n$.

<details>
<summary><strong>Solution</strong></summary>

Choose $\chi\in C_c^\infty(\mathbb R^n)$ with $\chi(0)\ne0$. Then $\chi\delta_0=\chi(0)\delta_0$, so

$$
\widehat{\chi\delta_0}(\xi)=\chi(0)
$$

up to the Fourier normalization convention. This does not decay rapidly in any conic direction. Away from $0$, choose $\chi$ supported away from $0$, and then $\chi\delta_0=0$. Therefore the only base point is $0$, and all nonzero covectors occur there.

</details>

### Exercise 2: Delta squared

Use Hörmander's product criterion to explain why $\delta_0^2$ is not canonically defined on $\mathbb R$.

<details>
<summary><strong>Solution</strong></summary>

On $\mathbb R$,

$$
\operatorname{WF}(\delta_0)=\{(0,\xi):\xi\ne0\}.
$$

For every $\xi\ne0$, both $(0,\xi)$ and $(0,-\xi)$ lie in the same wavefront set. Thus the product criterion fails for $u=v=\delta_0$. The attempted product has opposite singular covectors at the same base point, so distribution theory gives no canonical product.

</details>

### Exercise 3: Restriction to a hypersurface

Let $i:S\hookrightarrow X$ be an embedded hypersurface. State the wavefront-set condition that allows a distribution $u\in\mathcal D'(X)$ to be restricted to $S$.

<details>
<summary><strong>Solution</strong></summary>

The restriction $i^*u$ is defined if

$$
\operatorname{WF}(u)\cap N^*S=\varnothing,
$$

where $N^*S$ is the conormal bundle of $S$. Equivalently, $u$ must not have singular covectors normal to the hypersurface along which one wants to restrict it.

</details>

### Exercise 4: Why Hadamard is directional

Why is it not enough to say that the two-point function of a curved-spacetime state is singular on the light cone?

<details>
<summary><strong>Solution</strong></summary>

Many distributions can be singular on the light cone. A physical two-point function must have the correct positive-frequency singular directions. The Hadamard wavefront-set condition specifies not only that singularities propagate along null geodesics, but also which future-directed covectors occur. This directional information replaces the flat-space positive-energy condition when there is no global Fourier transform.

</details>

## References

### Microlocal analysis

- L. Hörmander, *The Analysis of Linear Partial Differential Operators I: Distribution Theory and Fourier Analysis*, Springer. DOI: [10.1007/978-3-642-61497-2](https://doi.org/10.1007/978-3-642-61497-2).
- M. E. Taylor, *Pseudodifferential Operators*, Princeton University Press. DOI: [10.1515/9781400886104](https://doi.org/10.1515/9781400886104).
- J. J. Duistermaat, *Fourier Integral Operators*, Birkhäuser. DOI: [10.1007/978-0-8176-8108-1](https://doi.org/10.1007/978-0-8176-8108-1).
- L. Hörmander, "Fourier Integral Operators. I," *Acta Mathematica* **127** (1971), 79–183. DOI: [10.1007/BF02392052](https://doi.org/10.1007/BF02392052).
- J. J. Duistermaat and L. Hörmander, "Fourier Integral Operators. II," *Acta Mathematica* **128** (1972), 183–269. DOI: [10.1007/BF02392165](https://doi.org/10.1007/BF02392165).

### Microlocal analysis in QFT

- M. J. Radzikowski, "Micro-Local Approach to the Hadamard Condition in Quantum Field Theory on Curved Space-Time," *Communications in Mathematical Physics* **179** (1996), 529–553. DOI: [10.1007/BF02100096](https://doi.org/10.1007/BF02100096).
- R. Brunetti, K. Fredenhagen, and M. Köhler, "The Microlocal Spectrum Condition and Wick Polynomials of Free Fields on Curved Spacetimes," *Communications in Mathematical Physics* **180** (1996), 633–652. arXiv: [gr-qc/9510056](https://arxiv.org/abs/gr-qc/9510056), DOI: [10.1007/BF02099626](https://doi.org/10.1007/BF02099626).
- R. Brunetti and K. Fredenhagen, "Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds," *Communications in Mathematical Physics* **208** (2000), 623–661. arXiv: [math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), DOI: [10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- S. Hollands and R. M. Wald, "Local Wick Polynomials and Time Ordered Products of Quantum Fields in Curved Spacetime," *Communications in Mathematical Physics* **223** (2001), 289–326. arXiv: [gr-qc/0103074](https://arxiv.org/abs/gr-qc/0103074), DOI: [10.1007/s002200100540](https://doi.org/10.1007/s002200100540).
- H. Sahlmann and R. Verch, "Microlocal Spectrum Condition and Hadamard Form for Vector-Valued Quantum Fields in Curved Spacetime," *Reviews in Mathematical Physics* **13** (2001), 1203–1246. arXiv: [math-ph/0008029](https://arxiv.org/abs/math-ph/0008029), DOI: [10.1142/S0129055X01001010](https://doi.org/10.1142/S0129055X01001010).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory*, Springer. DOI: [10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).

## Version history

- **2026-06-27:** Initial polished draft for the Microlocal Analysis in QFT chapter.
