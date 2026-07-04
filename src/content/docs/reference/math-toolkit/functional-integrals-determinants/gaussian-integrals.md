---
title: "Gaussian Integrals"
description: "A working calculus of Gaussian integrals for QFT: source differentiation, Wick theorem, determinant identities, Schur complements, complex Gaussians, oscillatory prescriptions, and Gaussian perturbation theory."
sidebar:
  label: "Gaussian Integrals"
  order: 2
level: Graduate
status: "Polished draft"
source: "Standard QFT generating-functional and Gaussian-integration references, emphasizing source methods, Wick theorem, block integration, and determinant identities."
topics:
  - Gaussian integrals
  - generating functionals
  - Wick theorem
  - Schur complements
  - determinant identities
canonicalTopics:
  - gaussian-generating-functionals
  - wick-theorem
  - schur-complements
  - gaussian-perturbation-theory
researchStatus:
  established:
    - "Gaussian source methods, Wick theorem, determinant identities, and Schur complements are exact finite-dimensional tools and standard in perturbative QFT."
  active:
    - "In continuum QFT, the same formulas require regularization and renormalization when products, traces, determinants, or coincident-point contractions become singular."
---

## Summary

Gaussian integration is not one formula; it is a calculus. Once the finite-dimensional Gaussian is understood, one can compute moments, prove Wick theorem, integrate out variables, derive determinant identities, generate Feynman diagrams, and recognize where one-loop effective actions come from.

For a centered real Gaussian with covariance $C$, the master identity is

$$
\left\langle e^{J^T x}\right\rangle_C
=e^{\frac12 J^TCJ}.
$$

Every correlation function follows by differentiating with respect to $J$. For example,

$$
\langle x_i x_j\rangle_C=C_{ij},
$$

and

$$
\langle x_i x_j x_k x_l\rangle_C
=C_{ij}C_{kl}+C_{ik}C_{jl}+C_{il}C_{jk}.
$$

This is the finite-dimensional skeleton of Wick contractions in QFT.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Gaussian integration workflow: complete the square, get a determinant, source exponential, and Wick contractions.](/figures/math-toolkit/gaussian-integration-workflow.svg)

<figcaption>

The Gaussian workflow is algebraic: complete the square, extract the determinant normalization, keep the source exponential, and obtain correlators by differentiating. Wick pairings are the derivatives of $e^{J^TCJ/2}$.

</figcaption>
</figure>

The page [Finite-Dimensional Gaussians](/math-toolkit/functional-integrals-determinants/finite-dimensional-gaussians/) gave the exact formulas. This page teaches how to use them as a calculation engine.

## Prerequisites

You should know the finite-dimensional formulas in [Finite-Dimensional Gaussians](/math-toolkit/functional-integrals-determinants/finite-dimensional-gaussians/), especially the convention

$$
Z_A[J]=\int d^n x\,
\exp\!\left(-\frac12x^TAx+J^Tx\right)
=(2\pi)^{n/2}(\det A)^{-1/2}e^{\frac12J^TA^{-1}J}.
$$

We write

$$
C=A^{-1}
$$

for the covariance. For field-theory interpretation, the relevant background is [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/), [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/), and [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/).

## Core idea

A Gaussian is exactly solvable because a quadratic exponent can be shifted to remove the linear term. Everything else is differentiation and linear algebra.

The source $J$ is not decoration. It is a bookkeeper. Since

$$
\frac{\partial}{\partial J_i}e^{J^Tx}=x_i e^{J^Tx},
$$

moments are obtained by differentiating the source-dependent integral:

$$
\langle x_{i_1}\cdots x_{i_m}\rangle_C
=\left.
\frac{\partial}{\partial J_{i_1}}\cdots
\frac{\partial}{\partial J_{i_m}}
\left\langle e^{J^Tx}\right\rangle_C
\right|_{J=0}.
$$

Since the normalized generating function is

$$
\left\langle e^{J^Tx}\right\rangle_C=e^{\frac12J^TCJ},
$$

all Gaussian moments reduce to pairwise contractions. That is Wick theorem.

In QFT, the same calculation becomes

$$
Z_0[J]
=\exp\!\left(\frac12\int d^dx\,d^dy\,J(x)G(x,y)J(y)\right),
$$

where $G$ is the propagator. Functional derivatives with respect to $J(x)$ generate free-field correlation functions.

## Setup and conventions

Let $A=A^T>0$ and $C=A^{-1}$. The unnormalized integral is

$$
Z_A[J]
=\int d^n x\,e^{-\frac12x^TAx+J^Tx}.
$$

The normalized source-dependent generating function is

$$
W_C[J]
=\frac{Z_A[J]}{Z_A[0]}
=e^{\frac12J^TCJ}.
$$

The centered Gaussian expectation value is

$$
\langle F(x)\rangle_C
=\frac{1}{Z_A[0]}
\int d^n x\,F(x)e^{-x^TAx/2}.
$$

Thus

$$
W_C[J]=\langle e^{J^Tx}\rangle_C.
$$

This page uses ordinary derivatives for finite-dimensional sources. In field theory these become functional derivatives:

$$
\frac{\partial}{\partial J_i}
\quad\leadsto\quad
\frac{\delta}{\delta J(x)}.
$$

## Sources and moment generation

The source generating function gives moments by differentiation:

$$
\langle x_{i_1}\cdots x_{i_m}\rangle_C
=\left.
\partial_{i_1}\cdots\partial_{i_m}W_C[J]
\right|_{J=0},
\qquad
\partial_i\equiv\frac{\partial}{\partial J_i}.
$$

For the first two derivatives,

$$
\partial_i W_C[J]
=(CJ)_i W_C[J],
$$

and

$$
\partial_i\partial_j W_C[J]
=\left(C_{ij}+(CJ)_i(CJ)_j\right)W_C[J].
$$

Setting $J=0$ gives

$$
\langle x_i\rangle_C=0,
\qquad
\langle x_i x_j\rangle_C=C_{ij}.
$$

For four derivatives,

$$
\left.\partial_i\partial_j\partial_k\partial_l e^{\frac12J^TCJ}\right|_{J=0}
=C_{ij}C_{kl}+C_{ik}C_{jl}+C_{il}C_{jk}.
$$

The terms are exactly the possible pairings of four variables.

This is why the free propagator is represented by a line in Feynman diagrams: every Gaussian moment decomposes into products of two-point functions.

## Wick theorem

For a centered Gaussian, Wick theorem states

$$
\langle x_{i_1}\cdots x_{i_m}\rangle_C=0
\quad\text{if }m\text{ is odd},
$$

and

$$
\langle x_{i_1}\cdots x_{i_{2r}}\rangle_C
=\sum_{\text{pairings }P}
\prod_{(a,b)\in P}C_{i_a i_b}
$$

if $m=2r$ is even.

A pairing is a partition of the labels $\{1,\ldots,2r\}$ into unordered pairs. The number of pairings is

$$
(2r-1)!!=\frac{(2r)!}{2^r r!}.
$$

The proof from sources is short. The exponential

$$
e^{\frac12J^TCJ}
=\sum_{r=0}^{\infty}\frac{1}{r!}
\left(\frac12\sum_{a,b}J_aC_{ab}J_b\right)^r
$$

contains only even powers of $J$. To compute a $2r$-point function, only the term of degree $2r$ contributes. Differentiating picks out all ways to assign the $2r$ derivatives to the $r$ quadratic source factors. Each assignment is a pairing, and the factors $2^r r!$ cancel the denominator.

The theorem is exact because the action is quadratic. Interactions spoil Gaussianity, and Wick theorem then becomes a perturbative rule after expanding the non-Gaussian part.

## Connected generating function

The logarithm of the generating function is the connected generating function. In finite dimension, define

$$
\mathcal W_C[J]=\log W_C[J]=\frac12J^TCJ.
$$

Connected correlators are derivatives of $\mathcal W_C[J]$:

$$
\langle x_{i_1}\cdots x_{i_m}\rangle_{C,\mathrm{conn}}
=\left.
\partial_{i_1}\cdots\partial_{i_m}\mathcal W_C[J]
\right|_{J=0}.
$$

For a Gaussian,

$$
\langle x_i x_j\rangle_{C,\mathrm{conn}}=C_{ij},
$$

and all connected correlators of order $m\neq2$ vanish:

$$
\langle x_{i_1}\cdots x_{i_m}\rangle_{C,\mathrm{conn}}=0,
\qquad m\geq3.
$$

This is the finite-dimensional version of the statement that a free field theory has only a connected two-point function; higher full correlators are products of two-point functions.

## Determinant identities

Gaussian calculations constantly produce determinants. The following identities are used everywhere in one-loop QFT.

For an invertible matrix $A(t)$,

$$
\frac{d}{dt}\log\det A(t)
=\operatorname{Tr}\!\left(A^{-1}(t)\frac{dA}{dt}\right).
$$

Equivalently,

$$
\delta\log\det A=\operatorname{Tr}(A^{-1}\delta A).
$$

Since

$$
\log\det A=\operatorname{Tr}\log A,
$$

one often writes determinant factors as traces of logarithms:

$$
(\det A)^{-1/2}
=\exp\!\left[-\frac12\operatorname{Tr}\log A\right].
$$

This is the finite-dimensional ancestor of the one-loop effective action term

$$
\Gamma_{\text{1-loop}}\sim \frac12\operatorname{Tr}\log K,
$$

for a bosonic fluctuation operator $K$. The sign and factor depend on whether the fluctuation is real bosonic, complex bosonic, fermionic, or constrained by gauge redundancy.

The inverse matrix varies as

$$
\delta A^{-1}=-A^{-1}(\delta A)A^{-1}.
$$

This identity is the algebraic reason perturbing a propagator produces insertions:

$$
(A+V)^{-1}=A^{-1}-A^{-1}VA^{-1}+A^{-1}VA^{-1}VA^{-1}-\cdots,
$$

when the series is meaningful.

## Integrating out variables

One of the most important Gaussian operations is integrating out a subset of variables. This is the finite-dimensional model for effective actions and EFT matching.

Split the variables into

$$
x\in\mathbb R^p,
\qquad
y\in\mathbb R^q,
$$

and write the quadratic form as

$$
\frac12
\begin{pmatrix}x\\y\end{pmatrix}^T
\begin{pmatrix}
A_{xx}&A_{xy}\\
A_{yx}&A_{yy}
\end{pmatrix}
\begin{pmatrix}x\\y\end{pmatrix},
$$

where $A_{yx}=A_{xy}^T$ and $A_{yy}>0$.

For fixed $x$, the $y$-dependent part is

$$
\frac12y^TA_{yy}y+y^TA_{yx}x.
$$

Complete the square:

$$
\frac12y^TA_{yy}y+y^TA_{yx}x
=\frac12(y+A_{yy}^{-1}A_{yx}x)^TA_{yy}(y+A_{yy}^{-1}A_{yx}x)
-\frac12x^TA_{xy}A_{yy}^{-1}A_{yx}x.
$$

Therefore

$$
\int d^qy\,
\exp\!\left[-\frac12
\begin{pmatrix}x\\y\end{pmatrix}^T
\begin{pmatrix}
A_{xx}&A_{xy}\\
A_{yx}&A_{yy}
\end{pmatrix}
\begin{pmatrix}x\\y\end{pmatrix}\right]
$$

equals

$$
(2\pi)^{q/2}(\det A_{yy})^{-1/2}
\exp\!\left[-\frac12x^T
\left(A_{xx}-A_{xy}A_{yy}^{-1}A_{yx}\right)x\right].
$$

The effective quadratic form for $x$ is the Schur complement

$$
A_{\mathrm{eff}}
=A_{xx}-A_{xy}A_{yy}^{-1}A_{yx}.
$$

The determinant factor is

$$
(\det A_{yy})^{-1/2}.
$$

In physics language, integrating out $y$ changes the $x$ action and contributes a determinant normalization. If $y$ is heavy and $x$ is light, this is the algebraic seed of an effective field theory.

## Schur complements and propagators

The same block decomposition explains how propagators change after eliminating variables. If

$$
A=\begin{pmatrix}
A_{xx}&A_{xy}\\
A_{yx}&A_{yy}
\end{pmatrix},
$$

with $A_{yy}$ invertible, then

$$
\det A=\det A_{yy}\,\det(A_{xx}-A_{xy}A_{yy}^{-1}A_{yx}).
$$

The inverse block relevant for the remaining $x$ variables is

$$
(A^{-1})_{xx}=A_{\mathrm{eff}}^{-1}.
$$

Thus the covariance of $x$ after allowing $y$ to fluctuate is not $A_{xx}^{-1}$; it is the inverse Schur complement.

This distinction is crucial. Setting $y=0$ gives the quadratic form $A_{xx}$. Integrating out $y$ gives

$$
A_{xx}-A_{xy}A_{yy}^{-1}A_{yx}.
$$

Those are different operations. In QFT language, dropping a field and integrating out a field are not the same thing.

## Complex bosonic Gaussians

For complex variables, the standard formula is

$$
\int_{\mathbb C^n}d^{2n}z\,
\exp\!\left(-z^\dagger A z+\eta^\dagger z+z^\dagger\eta\right)
=\frac{\pi^n}{\det A}e^{\eta^\dagger A^{-1}\eta},
$$

where $A=A^\dagger>0$.

With the normalized measure

$$
\prod_{i=1}^n\frac{d(\operatorname{Re}z_i)d(\operatorname{Im}z_i)}{\pi},
$$

the factor becomes $(\det A)^{-1}$.

The basic contraction is

$$
\langle z_i z_j^*\rangle=(A^{-1})_{ij},
$$

while

$$
\langle z_i z_j\rangle=0,
\qquad
\langle z_i^*z_j^*\rangle=0
$$

for the centered Gaussian with action $z^\dagger A z$.

Complex scalar fields in QFT behave like this rather than like one real scalar. A complex bosonic determinant is the square of the real-boson answer in the corresponding doubled real-variable representation.

## Oscillatory Gaussians and the iε idea

Euclidean Gaussian integrals converge because the exponent is damped. Lorentzian Gaussian integrals are oscillatory. In finite dimension, a typical Lorentzian formula is

$$
\int d^n x\,
\exp\!\left(\frac{i}{2}x^TMx+iJ^Tx\right)
\propto
|\det M|^{-1/2}
\exp\!\left(-\frac{i}{2}J^TM^{-1}J\right),
$$

where $M$ is real symmetric and nondegenerate. The missing proportionality factor contains a signature-dependent phase and depends on the contour prescription.

The $i\epsilon$ idea is to deform the quadratic form slightly so that the integral is damped in the correct directions. Schematically,

$$
M\to M+i\epsilon I
$$

or, in field theory, the kinetic operator is modified so that poles are displaced consistently with time ordering and boundary conditions.

The practical lesson is this:

$$
\text{Euclidean Gaussian algebra gives the inverse operator; Lorentzian QFT also requires a prescription.}
$$

A propagator is not just $K^{-1}$. It is $K^{-1}$ with boundary conditions or pole data.

## Gaussian perturbation theory

Suppose the action is a Gaussian part plus an interaction:

$$
S(x)=\frac12x^TAx+V(x).
$$

The source-dependent integral is

$$
Z[J]=\int d^nx\,e^{-\frac12x^TAx - V(x)+J^Tx}.
$$

If $V$ is treated perturbatively, use the identity

$$
x_i e^{J^Tx}=\frac{\partial}{\partial J_i}e^{J^Tx}.
$$

Then

$$
Z[J]
=e^{-V(\partial_J)}Z_A[J],
$$

where $V(\partial_J)$ means replace each $x_i$ in $V(x)$ by $\partial/\partial J_i$ and let the derivatives act on the free Gaussian generating function.

For example, if

$$
V(x)=\frac{\lambda}{4!}x^4
$$

in one dimension, then

$$
Z[J]=\exp\!\left(-\frac{\lambda}{4!}\frac{d^4}{dJ^4}\right)
\left[\sqrt{\frac{2\pi}{a}}e^{J^2/(2a)}\right].
$$

Expanding in $\lambda$ gives a finite-dimensional version of perturbation theory. The derivatives generate pairings. The coefficients become symmetry factors. In QFT, the same manipulation produces Feynman diagrams.

This is why Gaussian integration is the engine under perturbation theory: interactions are expanded, and the Gaussian part performs all contractions.

## Normal ordering as subtracting self-contractions

In a Gaussian theory, powers of fields contain self-contractions. In finite dimension,

$$
\langle x^2\rangle_C=C.
$$

Define the normal-ordered quadratic polynomial by

$$
:x^2:=x^2-C.
$$

Then

$$
\langle :x^2:\rangle_C=0.
$$

Similarly,

$$
:x^4:=x^4-6Cx^2+3C^2
$$

has zero Gaussian expectation. In many variables, normal ordering subtracts contractions among variables at the same vertex.

In continuum QFT this becomes more delicate because the self-contraction $G(x,x)$ is often singular. The finite-dimensional operation is harmless. The continuum operation requires a regulator or a renormalized definition of composite operators.

## From finite variables to field modes

A free field can be viewed as a Gaussian over modes. On a finite lattice or in a finite box with a mode cutoff, write

$$
\phi(x)=\sum_{a=1}^N q_a f_a(x).
$$

A quadratic Euclidean action becomes

$$
S_0[\phi]=\frac12\sum_{a,b=1}^N q_a K_{ab}q_b.
$$

The finite-dimensional Gaussian gives

$$
\langle q_a q_b\rangle=(K^{-1})_{ab}.
$$

Therefore

$$
\langle \phi(x)\phi(y)\rangle
=\sum_{a,b}f_a(x)(K^{-1})_{ab}f_b(y).
$$

In the continuum limit, the sum becomes a distributional kernel $G(x,y)$. Coincident limits such as $G(x,x)$, determinant products such as $\prod_a\lambda_a$, and traces such as $\sum_a \log\lambda_a$ may diverge. The finite-dimensional formula remains the map; the continuum limit supplies the terrain hazards.

## Common pitfalls

**Differentiating $Z[J]$ when you meant $Z[J]/Z[0]$.** Unnormalized and normalized correlators differ by the vacuum normalization. Always decide whether the normalization matters.

**Forgetting connected versus full correlators.** Derivatives of $Z[J]$ produce full correlators. Derivatives of $\log Z[J]$ produce connected correlators.

**Thinking Wick theorem is a quantum theorem.** Wick theorem is a Gaussian theorem. Its QFT use comes from the fact that free-field path integrals and free-field vacuum expectation values are Gaussian.

**Replacing integration out by setting fields to zero.** Setting $y=0$ gives $A_{xx}$. Integrating out $y$ gives the Schur complement $A_{xx}-A_{xy}A_{yy}^{-1}A_{yx}$.

**Dropping determinant factors from integrating out variables.** They may be independent of the remaining fields in simple examples, but in field theory they often depend on backgrounds and produce effective actions.

**Using determinant identities without checking invertibility.** Formulas such as $\delta\log\det A=\operatorname{Tr}(A^{-1}\delta A)$ assume $A$ is invertible. Zero modes need separate treatment.

**Treating $\operatorname{Tr}\log K$ as automatically meaningful.** In finite dimension it is meaningful. For differential operators, it is typically divergent and must be regulated.

**Ignoring pole prescriptions.** A Lorentzian inverse operator is not a propagator until its boundary condition or $i\epsilon$ prescription is specified.

## Relations to other pages

This page follows [Finite-Dimensional Gaussians](/math-toolkit/functional-integrals-determinants/finite-dimensional-gaussians/) and supplies the working formulas used later in [Functional Integrals and Determinants](/math-toolkit/functional-integrals-determinants/). The next natural topics are Grassmann Algebra and Berezin Integration, where analogous manipulations produce determinants in the numerator rather than denominator.

The source and kernel notation relies on [Mathematical Conventions](/math-toolkit/conventions/). The distributional interpretation of continuum propagators is developed in [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/). The momentum-space form of Gaussian kernels uses [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/).

## Research status

The finite-dimensional source calculus, Wick theorem, Schur complement formula, and determinant identities are settled linear algebra and analysis.

In continuum QFT, the same formulas remain central but become regulator-sensitive. Products of fields at the same point, traces of differential operators, determinant phases, and changes of variables in the measure can require renormalization, anomaly analysis, or rigorous reconstruction. The finite-dimensional formulas are the correct prototypes, not automatic continuum definitions.

## Exercises

### Exercise 1: Wick theorem for six variables

Use Wick theorem to write $\langle x_1x_2x_3x_4x_5x_6\rangle_C$ as a sum over pairings. How many terms are there?

<details><summary><strong>Solution</strong></summary>

There are

$$
(6-1)!!=15
$$

pairings. The result is

$$
\langle x_1x_2x_3x_4x_5x_6\rangle_C
=\sum_{\text{15 pairings }P}\prod_{(a,b)\in P}C_{ab}.
$$

Writing all terms explicitly:

$$
\begin{aligned}
& C_{12}C_{34}C_{56}+C_{12}C_{35}C_{46}+C_{12}C_{36}C_{45}\\
&+C_{13}C_{24}C_{56}+C_{13}C_{25}C_{46}+C_{13}C_{26}C_{45}\\
&+C_{14}C_{23}C_{56}+C_{14}C_{25}C_{36}+C_{14}C_{26}C_{35}\\
&+C_{15}C_{23}C_{46}+C_{15}C_{24}C_{36}+C_{15}C_{26}C_{34}\\
&+C_{16}C_{23}C_{45}+C_{16}C_{24}C_{35}+C_{16}C_{25}C_{34}.
\end{aligned}
$$

The compact pairing notation is usually better than the full expansion. The full expansion is useful once, mostly to convince yourself how quickly diagrams become good notation.

</details>

### Exercise 2: Schur complement in two variables

Let

$$
S(x,y)=\frac12 ax^2+gxy+\frac12by^2,
$$

with $b>0$ and $ab-g^2>0$. Integrate out $y$ and find the effective quadratic coefficient for $x$.

<details><summary><strong>Solution</strong></summary>

Complete the square in $y$:

$$
\frac12by^2+gxy
=\frac12b\left(y+\frac{g}{b}x\right)^2
-\frac{g^2}{2b}x^2.
$$

Therefore

$$
S(x,y)=\frac12\left(a-\frac{g^2}{b}\right)x^2
+\frac12b\left(y+\frac{g}{b}x\right)^2.
$$

The $y$ integral contributes a factor $\sqrt{2\pi/b}$ and leaves

$$
S_{\mathrm{eff}}(x)=\frac12\left(a-\frac{g^2}{b}\right)x^2.
$$

The effective coefficient is the Schur complement

$$
a_{\mathrm{eff}}=a-\frac{g^2}{b}.
$$

</details>

### Exercise 3: Determinant variation

Prove that

$$
\delta\log\det A=\operatorname{Tr}(A^{-1}\delta A)
$$

for an invertible finite-dimensional matrix $A$.

<details><summary><strong>Solution</strong></summary>

Use

$$
\det(A+\delta A)=\det A\,\det(I+A^{-1}\delta A).
$$

For small $B$,

$$
\det(I+B)=1+\operatorname{Tr}B+O(B^2),
$$

so

$$
\log\det(A+\delta A)
=\log\det A+\operatorname{Tr}(A^{-1}\delta A)+O((\delta A)^2).
$$

Keeping the first-order term gives the identity.

</details>

### Exercise 4: Normal ordering in one variable

Let $x$ be a centered Gaussian variable with variance $C$. Find constants $\alpha$ and $\beta$ such that

$$
:x^4:=x^4+\alpha Cx^2+\beta C^2
$$

has zero expectation and is orthogonal to $x^2$ in the sense that $\langle :x^4:x^2\rangle=0$.

<details><summary><strong>Solution</strong></summary>

Gaussian moments are

$$
\langle x^2\rangle=C,
\qquad
\langle x^4\rangle=3C^2,
\qquad
\langle x^6\rangle=15C^3.
$$

The condition $\langle :x^4:\rangle=0$ gives

$$
3C^2+\alpha C^2+\beta C^2=0,
$$

so

$$
3+\alpha+\beta=0.
$$

The condition $\langle :x^4:x^2\rangle=0$ gives

$$
15C^3+\alpha C\cdot 3C^2+\beta C^2\cdot C=0,
$$

so

$$
15+3\alpha+\beta=0.
$$

Subtracting the first equation from the second gives

$$
12+2\alpha=0,
$$

hence $\alpha=-6$. Then $3-6+\beta=0$, so $\beta=3$. Thus

$$
:x^4:=x^4-6Cx^2+3C^2.
$$

</details>

## References

- M. Srednicki, *Quantum Field Theory*. Generating functionals, Wick contractions, Gaussian path integrals, and determinant factors.
- A. Zee, *Quantum Field Theory in a Nutshell*. Gaussian integration identity and intuitive path-integral applications.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*. Wick diagrams, generating functionals, functional integration, and determinant reasoning.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Path-integral source methods, Schwinger–Dyson equations, and Wick expansion.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Functional methods, Gaussian perturbation theory, and renormalization.
- C. P. Burgess, *Introduction to Effective Field Theory*. Integrating out degrees of freedom, effective actions, and scale-separated Gaussian prototypes.

## Version history

- 2026-06-24: First polished draft. Developed source differentiation, Wick theorem, connected correlators, determinant identities, Schur complements, complex and oscillatory Gaussians, normal ordering, and the bridge to field modes.
