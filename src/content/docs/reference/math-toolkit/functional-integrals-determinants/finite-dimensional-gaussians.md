---
title: "Finite-Dimensional Gaussians"
description: "Finite-dimensional Gaussian integrals as the exact algebraic prototype for free path integrals, propagators, determinants, sources, zero modes, and Wick contractions."
sidebar:
  label: "Finite-Dimensional Gaussians"
  order: 1
level: Graduate
status: "Polished draft"
source: "Standard linear algebra, probability, and QFT functional-method references; finite-dimensional prototypes for bosonic path integrals and one-loop determinants."
topics:
  - Gaussian integrals
  - determinants
  - covariance matrices
  - Wick contractions
  - path integral prototypes
canonicalTopics:
  - finite-dimensional-gaussians
  - gaussian-normalization
  - covariance-matrices
  - determinant-factors
researchStatus:
  established:
    - "Finite-dimensional Gaussian formulas are exact, elementary, and form the algebraic prototype for free bosonic functional integrals."
  active:
    - "Their infinite-dimensional analogues require regulators, domains, boundary conditions, and renormalization before determinant and measure factors become meaningful."
---

## Summary

A finite-dimensional Gaussian integral is the safest place to learn the algebra of path integrals. The basic formula is

$$
\int_{\mathbb R^n} d^n x\,
\exp\!\left(-\frac12 x^T A x+J^T x\right)
=(2\pi)^{n/2}(\det A)^{-1/2}
\exp\!\left(\frac12 J^T A^{-1}J\right),
$$

where $A$ is a real symmetric positive-definite matrix. This one identity contains the main structural ingredients of a free bosonic field theory:

$$
\text{quadratic form}\quad A,
\qquad
\text{propagator}\quad A^{-1},
\qquad
\text{one-loop factor}\quad (\det A)^{-1/2}.
$$

The point of this page is not merely to memorize the formula. The point is to understand what every symbol is doing before the same notation is promoted to fields, kernels, differential operators, and functional determinants.

<figure class="doc-figure" style="--figure-width: 39rem;">

![Geometry of a finite-dimensional Gaussian: contours, eigen-directions, covariance, and source shift.](/figures/math-toolkit/finite-gaussian-geometry.svg)

<figcaption>

A positive quadratic form $A$ defines ellipsoidal Gaussian contours. The covariance is $C=A^{-1}$, so narrow directions of $e^{-x^T A x/2}$ become small fluctuations. A source $J$ shifts the mean to $\mu=CJ$ without changing the covariance.

</figcaption>
</figure>

Finite-dimensional Gaussians are also an honesty device. They show exactly which steps are harmless in finite dimension and which become dangerous in QFT: determinant products, zero modes, indefinite quadratic forms, normalization constants, and changes of variables.

## Prerequisites

You should be comfortable with determinants, traces, transposes, Hermitian conjugates, eigenvalues, changes of variables, and positive-definite matrices. The notation follows [Mathematical Conventions](/math-toolkit/conventions/).

For later field-theory interpretation, it helps to know that distributions and Fourier transforms turn differential operators into kernels and multiplication operators; the relevant background is in [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/) and [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/). This page is the first ordinary page in [Functional Integrals and Determinants](/math-toolkit/functional-integrals-determinants/).

## Core idea

A Gaussian integral is an integral whose exponent is at most quadratic in the variables. In Euclidean signature, the quadratic part must damp the integral. In finite dimension this means that the real part of the quadratic form is positive in the directions being integrated over.

The standard real case is

$$
Q(x)=\frac12 x^T A x-J^T x,
$$

with $A=A^T>0$ and $J\in\mathbb R^n$. The integral is controlled by two operations:

$$
\text{diagonalize the quadratic form},
\qquad
\text{complete the square}.
$$

The inverse matrix $A^{-1}$ appears because the stationary point solves

$$
\nabla_x Q(x)=Ax-J=0,
\qquad
x=A^{-1}J.
$$

The determinant appears because the volume element changes when the ellipsoid defined by $A$ is turned into a round sphere.

In field theory, this same story becomes

$$
A\to K,
\qquad
A^{-1}\to G(x,y),
\qquad
\det A\to \det K,
$$

where $K$ is a kinetic operator and $G$ is a Green function. The finite-dimensional result is exact; the field-theory result is a regulated analogy unless a precise construction is supplied.

## Setup and conventions

Throughout this page, $x$ is a column vector in $\mathbb R^n$ and

$$
d^n x=dx_1\cdots dx_n.
$$

For a real symmetric positive-definite matrix $A$, define the unnormalized Gaussian integral

$$
Z_A[J]
=\int_{\mathbb R^n} d^n x\,
\exp\!\left(-\frac12 x^T A x+J^T x\right).
$$

The source-free integral is

$$
Z_A[0]
=\int_{\mathbb R^n} d^n x\,
\exp\!\left(-\frac12 x^T A x\right).
$$

The normalized expectation value of a function $F$ is

$$
\langle F(x)\rangle_A
=\frac{1}{Z_A[0]}
\int_{\mathbb R^n} d^n x\,F(x)
\exp\!\left(-\frac12 x^T A x\right).
$$

The covariance matrix is

$$
C=A^{-1}.
$$

This notation deliberately uses $A$ for the quadratic form and $C$ for its inverse. In QFT language, $A$ is the finite-dimensional kinetic operator and $C$ is the finite-dimensional propagator.

## The one-dimensional prototype

The one-dimensional Gaussian integral is

$$
\int_{-\infty}^{\infty} dx\,e^{-a x^2/2}
=\sqrt{\frac{2\pi}{a}},
\qquad a>0.
$$

With a source,

$$
\int_{-\infty}^{\infty} dx\,e^{-a x^2/2+Jx}
=\sqrt{\frac{2\pi}{a}}\,e^{J^2/(2a)}.
$$

The proof is the completion of the square:

$$
-\frac12 a x^2+Jx
=-\frac12 a\left(x-\frac{J}{a}\right)^2
+\frac{J^2}{2a}.
$$

Three pieces of QFT intuition are already visible.

First, the inverse of the quadratic coefficient appears in the source term:

$$
\frac{J^2}{2a}.
$$

Second, the determinant factor in one dimension is just $a^{-1/2}$.

Third, the source shifts the mean but not the width:

$$
\langle x\rangle_J=\frac{J}{a},
\qquad
\langle (x-\langle x\rangle_J)^2\rangle_J=\frac1a.
$$

The inverse quadratic coefficient is the variance. This is the finite-dimensional ancestor of the statement that the propagator is the inverse kinetic operator.

## Diagonalization and determinant

Let $A=A^T>0$. The spectral theorem gives an orthogonal matrix $O$ such that

$$
A=O^T\Lambda O,
\qquad
\Lambda=\operatorname{diag}(\lambda_1,\ldots,\lambda_n),
\qquad
\lambda_i>0.
$$

Set $y=Ox$. Since $O$ is orthogonal,

$$
d^n x=d^n y,
\qquad
x^TAx=y^T\Lambda y=\sum_{i=1}^n \lambda_i y_i^2.
$$

Therefore

$$
Z_A[0]
=\prod_{i=1}^n\int_{-\infty}^{\infty}dy_i\,e^{-\lambda_i y_i^2/2}
=(2\pi)^{n/2}\prod_{i=1}^n\lambda_i^{-1/2}.
$$

Since

$$
\det A=\prod_{i=1}^n\lambda_i,
$$

we get

$$
Z_A[0]=(2\pi)^{n/2}(\det A)^{-1/2}.
$$

This is the origin of the bosonic square-root determinant. Each normal mode contributes one factor $\lambda_i^{-1/2}$.

A useful geometric interpretation is this: the set

$$
\{x:x^TAx\leq 1\}
$$

is an ellipsoid. Its volume is smaller than the unit ball by a factor $(\det A)^{-1/2}$. A large eigenvalue means a narrow direction and a small fluctuation. A small eigenvalue means a broad direction and a large fluctuation.

## Completing the square in matrix form

With a source, write $C=A^{-1}$ and shift

$$
x=y+CJ.
$$

Then

$$
-\frac12 x^T A x+J^T x
=-\frac12 (x-CJ)^T A(x-CJ)
+\frac12 J^T C J.
$$

The Lebesgue measure is translation invariant in finite dimension, so $d^n x=d^n y$. Therefore

$$
Z_A[J]=Z_A[0]\,e^{\frac12 J^TCJ}
=(2\pi)^{n/2}(\det A)^{-1/2}e^{\frac12 J^TA^{-1}J}.
$$

The stationary point of the exponent is

$$
\mu=CJ,
$$

and the fluctuations around it still have covariance $C$.

This is the finite-dimensional version of the free generating functional

$$
Z_0[J]\sim e^{\frac12\langle J,K^{-1}J\rangle},
$$

up to normalization and sign conventions.

## Normalized Gaussian measure

It is often cleaner to absorb the determinant normalization into the measure. Define

$$
d\mu_C(x)
=\frac{d^n x}{(2\pi)^{n/2}(\det C)^{1/2}}
\exp\!\left(-\frac12 x^T C^{-1}x\right),
$$

where $C=C^T>0$. Then

$$
\int_{\mathbb R^n}d\mu_C(x)=1.
$$

With this normalization,

$$
\left\langle e^{J^Tx}\right\rangle_C
=\int d\mu_C(x)\,e^{J^Tx}
=e^{\frac12 J^TCJ}.
$$

The matrix $C$ is the covariance because

$$
\langle x_i x_j\rangle_C=C_{ij}.
$$

In probability theory this is the centered normal distribution with covariance $C$. In Euclidean free-field theory, this is the finite-dimensional shadow of the Gaussian measure whose covariance is the Green function.

There is a useful warning hiding here. The normalized measure uses $(\det C)^{1/2}$, while the unnormalized action uses $(\det A)^{-1/2}$. Since $C=A^{-1}$, these are the same statement. Confusion often starts when one switches between the $A$ and $C$ descriptions without saying so.

## Moments and Wick contractions

Moments are obtained by differentiating the source formula. Since

$$
\left\langle e^{J^Tx}\right\rangle_C=e^{\frac12J^TCJ},
$$

we have

$$
\langle x_{i_1}\cdots x_{i_m}\rangle_C
=\left.
\frac{\partial}{\partial J_{i_1}}\cdots
\frac{\partial}{\partial J_{i_m}}
 e^{\frac12J^TCJ}
\right|_{J=0}.
$$

Odd moments vanish:

$$
\langle x_{i_1}\cdots x_{i_{2r+1}}\rangle_C=0.
$$

Even moments are sums over pairings:

$$
\langle x_{i_1}\cdots x_{i_{2r}}\rangle_C
=\sum_{\text{pairings }P}
\prod_{(a,b)\in P} C_{i_a i_b}.
$$

For example,

$$
\langle x_i x_j x_k x_l\rangle_C
=C_{ij}C_{kl}+C_{ik}C_{jl}+C_{il}C_{jk}.
$$

This is Wick theorem in finite dimension. Nothing quantum has happened yet. Wick contractions are a property of Gaussian integration.

## Affine Gaussians: mean and covariance

A Gaussian with source can be regarded as a Gaussian with nonzero mean. The normalized source-dependent measure is

$$
d\mu_{C,\mu}(x)
=\frac{d^n x}{(2\pi)^{n/2}(\det C)^{1/2}}
\exp\!\left[-\frac12(x-\mu)^T C^{-1}(x-\mu)\right],
$$

with

$$
\mu=CJ.
$$

Then

$$
\langle x_i\rangle_{C,\mu}=\mu_i,
\qquad
\langle (x_i-\mu_i)(x_j-\mu_j)\rangle_{C,\mu}=C_{ij}.
$$

Equivalently,

$$
\langle x_i x_j\rangle_{C,\mu}=C_{ij}+\mu_i\mu_j.
$$

This decomposition matters in field theory because a saddle point or background field gives the mean, while the inverse fluctuation operator gives the covariance.

## Complex Gaussian variables

Complex bosonic fields require a closely related formula. Let $z\in\mathbb C^n$ and let $A$ be Hermitian positive definite. With

$$
d^{2n}z=\prod_{i=1}^n d(\operatorname{Re} z_i)\,d(\operatorname{Im} z_i),
$$

one has

$$
\int_{\mathbb C^n} d^{2n}z\,e^{-z^\dagger A z}
=\frac{\pi^n}{\det A}.
$$

With complex sources,

$$
\int_{\mathbb C^n} d^{2n}z\,
\exp\!\left(-z^\dagger A z+\eta^\dagger z+z^\dagger\eta\right)
=\frac{\pi^n}{\det A}\,
\exp\!\left(\eta^\dagger A^{-1}\eta\right).
$$

The determinant power differs from the real formula because one complex variable contains two real variables. A complex bosonic Gaussian gives $(\det A)^{-1}$, while a real bosonic Gaussian gives $(\det A)^{-1/2}$.

A common QFT convention absorbs the factor $\pi^n$ into the measure:

$$
\int \prod_i\frac{d(\operatorname{Re}z_i)d(\operatorname{Im}z_i)}{\pi}\,
 e^{-z^\dagger A z}
=(\det A)^{-1}.
$$

Both conventions are fine, but the measure must be stated.

## Parameters, units, and normalization

The variable $x_i$ may have physical dimensions. Then $A_{ij}$ has the inverse dimensions needed to make $x^TAx$ dimensionless, and $d^n x$ carries dimensions. Consequently, the bare number $Z_A[0]$ is not always physically meaningful by itself.

In QFT this issue is amplified. A path integral normalization may contain powers of a lattice spacing, volume factors, cutoff-dependent constants, and arbitrary reference scales. Many normalized quantities are independent of these choices, but vacuum energies, determinants, and effective actions are not automatically so.

The practical rule is

$$
\text{normalize ratios and expectation values carefully; treat absolute determinants as convention-dependent until regulated.}
$$

For example, the ratio

$$
\frac{Z_A[J]}{Z_A[0]}=e^{\frac12J^TA^{-1}J}
$$

is independent of the overall measure normalization. The absolute value of $Z_A[0]$ is not.

## Zero modes

The positive-definite assumption is essential. If $A$ has a zero eigenvalue, then

$$
\det A=0,
$$

and the source-free integral over $\mathbb R^n$ diverges in that flat direction. If $A$ is positive semidefinite, diagonalization gives an integral of the form

$$
\int_{-\infty}^{\infty}dy\,e^0,
$$

for each zero mode.

In field theory, zero modes are not a nuisance to be swept away. They usually mean something physical or geometric:

| Zero-mode origin | What it means |
|---|---|
| Translation symmetry of a soliton | Collective coordinate for position. |
| Gauge redundancy | Overcounting of gauge-equivalent configurations. |
| Moduli space of solutions | Flat directions requiring separate integration. |
| Spontaneous symmetry breaking | Massless Goldstone directions or volume of a group orbit. |
| Negative or zero Hessian at a saddle | Instability or marginal direction. |

The finite-dimensional instruction is simple: split the variables into zero and nonzero modes before using the determinant formula. If $A$ is nonzero only on a subspace $V_\perp$, then the Gaussian determinant belongs only to $A|_{V_\perp}$. The remaining variables need a separate measure, constraint, gauge fixing, collective-coordinate treatment, or physical boundary condition.

## Indefinite quadratic forms and oscillatory Gaussians

If $A$ has negative eigenvalues, the Euclidean integral

$$
\int d^n x\,e^{-x^TAx/2}
$$

diverges along those directions. In saddle-point problems, an indefinite Hessian signals that the saddle is not a local minimum of the Euclidean action.

Lorentzian path integrals are different. They involve oscillatory factors such as

$$
e^{iS[x]},
$$

not damping factors. A finite-dimensional oscillatory Gaussian has the schematic form

$$
\int_{\mathbb R^n}d^n x\,
\exp\!\left(\frac{i}{2}x^T Mx+iJ^Tx\right).
$$

This integral is not absolutely convergent. It is defined by a contour prescription, an $i\epsilon$ prescription, analytic continuation, or distributional interpretation. Formally, if $M$ is real symmetric and nondegenerate, one gets

$$
\int d^n x\,
\exp\!\left(\frac{i}{2}x^T Mx+iJ^Tx\right)
\propto
|\det M|^{-1/2}
\exp\!\left(-\frac{i}{2}J^TM^{-1}J\right),
$$

with a phase determined by the signature of $M$ and the chosen contour.

The Euclidean Gaussian is the clean algebraic prototype. The Lorentzian Gaussian is the same algebra plus analytic and boundary-condition data. Tiny phrase, enormous caveat.

## The finite-dimensional QFT dictionary

A regulated free scalar field theory is a large finite-dimensional Gaussian. For example, on a lattice with $N$ sites, a real field is a vector

$$
\phi=(\phi_1,\ldots,\phi_N),
$$

and a quadratic Euclidean action has the form

$$
S_0[\phi]=\frac12\phi^T K\phi.
$$

The source-coupled generating integral is

$$
Z_0[J]=\int d^N\phi\,
\exp\!\left(-\frac12\phi^TK\phi+J^T\phi\right).
$$

If $K$ is positive definite, then

$$
Z_0[J]=(2\pi)^{N/2}(\det K)^{-1/2}
\exp\!\left(\frac12 J^TK^{-1}J\right).
$$

The two-point function is

$$
\langle \phi_i\phi_j\rangle=(K^{-1})_{ij}.
$$

In a continuum limit, the matrix index $i$ becomes a spacetime point $x$, the matrix $K_{ij}$ becomes a differential operator or distributional kernel $K(x,y)$, and the inverse matrix becomes a Green function:

$$
\sum_j K_{ij}(K^{-1})_{jk}=\delta_{ik}
\quad\leadsto\quad
\int d^dy\,K(x,y)G(y,z)=\delta^{(d)}(x-z).
$$

This is the correct mental bridge. First finite dimension. Then regulator. Then continuum interpretation.

## Common pitfalls

**Forgetting positivity.** The Euclidean formula with $(\det A)^{-1/2}$ assumes damping. If $A$ is not positive definite, the ordinary real integral may diverge.

**Treating zero modes as harmless.** A zero eigenvalue makes the determinant vanish and the Gaussian volume diverge. Zero modes need to be separated before applying the formula.

**Confusing $A$ and $C$.** The quadratic form is $A=C^{-1}$. The covariance is $C=A^{-1}$. A determinant may appear as $(\det A)^{-1/2}$ or $(\det C)^{1/2}$ depending on which object is being used.

**Dropping normalization without knowing whether it matters.** The ratio $Z[J]/Z[0]$ often removes overall constants. Effective actions, vacuum energies, anomalies, and determinant ratios may retain important normalization data.

**Using complex Gaussian formulas with real Gaussian factors.** A real Gaussian gives $(\det A)^{-1/2}$. A complex Gaussian with $z^\dagger A z$ gives $(\det A)^{-1}$, up to powers of $\pi$ fixed by the measure.

**Calling every inverse a propagator.** In field theory, the inverse of a kinetic operator becomes a propagator only after boundary conditions, pole prescriptions, and functional spaces are specified.

**Believing infinite-dimensional Lebesgue measure exists by analogy.** Finite-dimensional translation-invariant Lebesgue measure is real. A fully analogous infinite-dimensional measure is not available in the same way. Continuum path-integral notation must be interpreted through regulators or more refined constructions.

## Relations to other pages

This page supplies the finite-dimensional prototype used throughout [Functional Integrals and Determinants](/math-toolkit/functional-integrals-determinants/). The next page, [Gaussian Integrals](/math-toolkit/functional-integrals-determinants/gaussian-integrals/), turns the formulas here into a working calculus: source differentiation, Wick theorem, determinant identities, block integration, and Gaussian perturbation theory.

For the analytic meaning of delta functions, Green functions, and inverse kernels, see [Distributions](/math-toolkit/analysis-distributions-fourier/distributions/), [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/), and [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/). For the Fourier normalization of momentum-space quadratic forms, see [Fourier Transform Conventions](/math-toolkit/analysis-distributions-fourier/fourier-transform-conventions/).

Later pages in this chapter will replace ordinary commuting variables by Grassmann variables, turning the bosonic determinant denominator into fermionic determinants and Pfaffians.

## Research status

The finite-dimensional statements on this page are elementary theorems. They are exact under the stated positivity and convergence assumptions.

The research-level subtlety begins when the same symbols are used in infinite-dimensional settings. Then one must specify the regulator, function space, operator domain, boundary conditions, zero-mode treatment, contour, and renormalization prescription. Different choices can differ by local counterterms, phases, anomalies, or global sign data.

So the status is split:

$$
\text{finite-dimensional Gaussian algebra: settled}
$$

but

$$
\text{continuum functional-integral interpretation: construction-dependent.}
$$

## Exercises

### Exercise 1: Source shift in one dimension

Show that

$$
\frac{\int_{-\infty}^{\infty}dx\,x^2e^{-a x^2/2+Jx}}
{\int_{-\infty}^{\infty}dx\,e^{-a x^2/2+Jx}}
=\frac1a+\frac{J^2}{a^2},
\qquad a>0.
$$

<details><summary><strong>Solution</strong></summary>

The source-dependent generating integral is

$$
Z[J]=\sqrt{\frac{2\pi}{a}}e^{J^2/(2a)}.
$$

Since differentiation brings down powers of $x$,

$$
\int dx\,x^2e^{-a x^2/2+Jx}=\frac{d^2Z}{dJ^2}.
$$

Now

$$
\frac{1}{Z}\frac{d^2Z}{dJ^2}
=\frac1a+\frac{J^2}{a^2}.
$$

The first term is the variance. The second is the square of the shifted mean $\mu=J/a$.

</details>

### Exercise 2: Two coupled variables

Let

$$
A=\begin{pmatrix}a&b\\ b&c\end{pmatrix},
$$

with $a>0$, $c>0$, and $ac-b^2>0$. Compute $\langle x_1x_2\rangle_A$ for the normalized centered Gaussian with quadratic form $A$.

<details><summary><strong>Solution</strong></summary>

The covariance is $C=A^{-1}$. For a $2\times2$ matrix,

$$
A^{-1}=\frac{1}{ac-b^2}
\begin{pmatrix}
c&-b\\
-b&a
\end{pmatrix}.
$$

Therefore

$$
\langle x_1x_2\rangle_A=C_{12}=-\frac{b}{ac-b^2}.
$$

The sign is worth noticing. A positive off-diagonal term $b$ in the quadratic form penalizes $x_1$ and $x_2$ having the same sign, so the covariance is negative.

</details>

### Exercise 3: Determinant from normal modes

Suppose $A$ has eigenvalues $\lambda_1,\ldots,\lambda_n>0$. Derive

$$
\int d^n x\,e^{-x^TAx/2}
=(2\pi)^{n/2}(\lambda_1\cdots\lambda_n)^{-1/2}.
$$

<details><summary><strong>Solution</strong></summary>

Choose an orthogonal matrix $O$ that diagonalizes $A$:

$$
A=O^T\operatorname{diag}(\lambda_1,\ldots,\lambda_n)O.
$$

Set $y=Ox$. The Jacobian has absolute value $1$, so $d^nx=d^ny$. The integral factorizes:

$$
\int d^ny\,\exp\!\left(-\frac12\sum_i\lambda_i y_i^2\right)
=\prod_i\sqrt{\frac{2\pi}{\lambda_i}}
=(2\pi)^{n/2}(\lambda_1\cdots\lambda_n)^{-1/2}.
$$

Since $\det A=\lambda_1\cdots\lambda_n$, this is the determinant formula.

</details>

### Exercise 4: A zero-mode warning

Let

$$
A=\begin{pmatrix}1&0\\0&0\end{pmatrix}.
$$

Evaluate formally what goes wrong with

$$
\int_{\mathbb R^2}dx\,dy\,e^{-\frac12(x,y)A(x,y)^T}.
$$

<details><summary><strong>Solution</strong></summary>

The exponent is just $-x^2/2$. Therefore

$$
\int_{\mathbb R^2}dx\,dy\,e^{-x^2/2}
=\left(\int_{-\infty}^{\infty}dx\,e^{-x^2/2}\right)
\left(\int_{-\infty}^{\infty}dy\right).
$$

The $x$ integral is $\sqrt{2\pi}$, but the $y$ integral diverges. The zero eigenvalue of $A$ is a flat direction. The determinant formula would produce $(\det A)^{-1/2}=\infty$, which is the same warning in compressed notation.

</details>

## References

- M. Srednicki, *Quantum Field Theory*. Path integrals, generating functionals, Gaussian functional integration, and functional determinants.
- A. Zee, *Quantum Field Theory in a Nutshell*. Appendix on Gaussian integration and the central identity of QFT; intuitive use of Gaussian methods throughout.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory* and *Aspects of Symmetry*. Functional integration, Wick contractions, determinants, and semiclassical Gaussian fluctuations.
- M. Schwartz, *Quantum Field Theory and the Standard Model*. Practical path-integral and generating-functional derivations.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Functional methods, Gaussian measures, perturbative expansions, and saddle points.
- B. Simon, *Functional Integration and Quantum Physics*. Mathematical treatment of Gaussian measures and functional integration.

## Version history

- 2026-06-24: First polished draft. Introduced real and complex finite-dimensional Gaussian formulas, determinant normalization, covariance, Wick contractions, zero modes, Lorentzian caveats, and the regulated QFT dictionary.
