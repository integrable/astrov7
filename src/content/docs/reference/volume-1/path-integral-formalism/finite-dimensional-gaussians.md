---
title: "Finite-Dimensional Gaussians"
description: "Bosonic Gaussian integrals with sources, determinants, covariance matrices, Wick pairings, Lorentzian phases, and the finite-dimensional prototype of free path integrals."
sidebar:
  label: "Finite-Dimensional Gaussians"
  order: 1
---

## Summary

Almost every free path integral is an infinite-dimensional Gaussian. Before pretending to integrate over fields, it is worth mastering the finite-dimensional version.

If $A$ is a real symmetric positive-definite $N\times N$ matrix and $J\in\mathbb R^N$, then

$$
\boxed{
\int_{\mathbb R^N}d^Nx\,
\exp\left[-\frac12x^TAx+J^Tx\right]
=(2\pi)^{N/2}(\det A)^{-1/2}
\exp\left[\frac12J^TA^{-1}J\right].
}
$$

After normalizing by the source-free integral,

$$
\boxed{
Z[J]=\frac{I[J]}{I[0]}
=\exp\left[\frac12J^TA^{-1}J\right].
}
$$

The inverse matrix $A^{-1}$ is the covariance:

$$
\boxed{
\langle x_i x_j\rangle=(A^{-1})_{ij}.
}
$$

All higher Gaussian moments are sums over pairings. This is the finite-dimensional form of Wick's theorem. In field theory, the matrix $A$ becomes a differential operator or kernel, $A^{-1}$ becomes a propagator, and $(\det A)^{-1/2}$ becomes a fluctuation determinant. Zee calls this family of formulas the “central identity” behind QFT path integrals; Srednicki and Coleman use the same Gaussian machinery to derive the free-field generating functional and Wick contractions (Zee 2010, appendix A; Srednicki 2007, §§6–8; Coleman 2019, chs. 28 and 32).

## Prerequisites

You should know [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/), [Connected Correlators](/foundations/correlators-and-propagators/connected-correlators/), and [Linearization and Normal Modes](/foundations/classical-field-theory/linearization-and-normal-modes/). This page is the algebraic foundation for [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/) and [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/).

## Core idea

A Gaussian integral with a source is solved by shifting the integration variable. The source changes the center of the Gaussian; the quadratic form controls the width.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Finite-dimensional Gaussian source shift and output data](/figures/foundations/finite-gaussian-source-shift.svg)

<figcaption>

Completing the square shifts the saddle from $0$ to $A^{-1}J$. The Gaussian output has two pieces: a determinant from fluctuations and an inverse kernel $A^{-1}$ that becomes the covariance. Field theory repeats this calculation with infinitely many coupled variables.

</figcaption>
</figure>

The whole calculation is the identity

$$
-\frac12x^TAx+J^Tx
=-\frac12(x-A^{-1}J)^TA(x-A^{-1}J)
+\frac12J^TA^{-1}J.
$$

The shift

$$
y=x-A^{-1}J
$$

leaves the measure $d^Nx$ unchanged. The $y$ integral contributes the same determinant as the source-free Gaussian. The source dependence is exactly

$$
\exp\left[\frac12J^TA^{-1}J\right].
$$

That is the seed from which free propagators, Wick contractions, and one-loop determinants grow.

## One-dimensional warm-up

For $a>0$,

$$
\int_{-\infty}^{\infty}dx\,e^{-ax^2/2}
=\sqrt{\frac{2\pi}{a}}.
$$

With a source $J$,

$$
I(J)=\int_{-\infty}^{\infty}dx\,
\exp\left[-\frac12ax^2+Jx\right].
$$

Complete the square:

$$
-\frac12ax^2+Jx
=-\frac12a\left(x-\frac{J}{a}\right)^2+\frac{J^2}{2a}.
$$

Therefore

$$
\boxed{
I(J)=\sqrt{\frac{2\pi}{a}}\,e^{J^2/(2a)}.
}
$$

The normalized generating function is

$$
Z(J)=\frac{I(J)}{I(0)}=e^{J^2/(2a)}.
$$

The moments follow by differentiating:

$$
\langle x^n\rangle
=\left.\frac{1}{Z(0)}\frac{d^n Z(J)}{dJ^n}\right|_{J=0}
=\left.\frac{d^n Z(J)}{dJ^n}\right|_{J=0}.
$$

Thus

$$
\langle x\rangle=0,
\qquad
\langle x^2\rangle=\frac1a,
\qquad
\langle x^4\rangle=3\frac1{a^2}.
$$

The factor $3$ in the fourth moment is the number of pairings of four objects:

$$
(12)(34),\qquad(13)(24),\qquad(14)(23).
$$

That innocent combinatorics is Wick's theorem in miniature.

## N-dimensional Euclidean Gaussian

Let $A$ be real, symmetric, and positive definite. Diagonalize it by an orthogonal matrix:

$$
A=O^T\Lambda O,
\qquad
\Lambda=\operatorname{diag}(\lambda_1,\ldots,\lambda_N),
\qquad
\lambda_i>0.
$$

With $y=Ox$, the measure is unchanged:

$$
d^Nx=d^Ny,
$$

because $|\det O|=1$. Hence

$$
\int d^Nx\,e^{-x^TAx/2}
=\prod_{i=1}^N\int dy_i\,e^{-\lambda_i y_i^2/2}
=(2\pi)^{N/2}\prod_{i=1}^N\lambda_i^{-1/2}.
$$

Therefore

$$
\boxed{
\int d^Nx\,e^{-x^TAx/2}
=(2\pi)^{N/2}(\det A)^{-1/2}.
}
$$

Now include the source. Completing the square gives

$$
-\frac12x^TAx+J^Tx
=-\frac12(x-A^{-1}J)^TA(x-A^{-1}J)+\frac12J^TA^{-1}J.
$$

Thus

$$
\boxed{
I[J]=(2\pi)^{N/2}(\det A)^{-1/2}
\exp\left[\frac12J^TA^{-1}J\right].
}
$$

After normalization,

$$
\boxed{
Z[J]=\exp\left[\frac12J_i(A^{-1})_{ij}J_j\right].
}
$$

Repeated indices are summed in this finite-dimensional section.

:::note[Positive definiteness]
The Euclidean formula above converges because $A$ is positive definite. If $A$ has a zero eigenvalue, the determinant vanishes and the integral diverges along the zero mode. Gauge redundancies, collective coordinates, and spontaneous symmetry breaking all force us to confront such zero modes later.
:::

## Covariance and Wick pairings

Define Gaussian expectation values by

$$
\langle f(x)\rangle
=\frac{1}{I[0]}\int d^Nx\,f(x)e^{-x^TAx/2}.
$$

The normalized source functional is

$$
Z[J]=\langle e^{J^Tx}\rangle.
$$

Therefore

$$
\langle x_{i_1}\cdots x_{i_n}\rangle
=\left.\frac{\partial^n Z[J]}{\partial J_{i_1}\cdots\partial J_{i_n}}\right|_{J=0}.
$$

The two-point function is

$$
\boxed{
\langle x_i x_j\rangle=(A^{-1})_{ij}.
}
$$

Odd moments vanish. Even moments are sums over pairings. For four variables,

$$
\boxed{
\begin{aligned}
\langle x_i x_j x_k x_l\rangle
=&\,(A^{-1})_{ij}(A^{-1})_{kl}
+(A^{-1})_{ik}(A^{-1})_{jl} \\
&+(A^{-1})_{il}(A^{-1})_{jk}.
\end{aligned}
}
$$

For $2n$ variables,

$$
\boxed{
\langle x_{i_1}\cdots x_{i_{2n}}\rangle
=\sum_{\text{pairings}}
(A^{-1})_{i_{a_1}i_{b_1}}\cdots
(A^{-1})_{i_{a_n}i_{b_n}}.
}
$$

This is Wick's theorem for a bosonic Gaussian.

## Connected moments

Since

$$
Z[J]=\exp\left[\frac12JA^{-1}J\right],
$$

the logarithm is quadratic:

$$
\log Z[J]=\frac12JA^{-1}J.
$$

Therefore the connected Gaussian moments are

$$
\langle x_i x_j\rangle_{\mathrm c}=(A^{-1})_{ij},
$$

and

$$
\boxed{
\langle x_{i_1}\cdots x_{i_n}\rangle_{\mathrm c}=0
\qquad(n>2).
}
$$

This is the finite-dimensional prototype of the free-field statement

$$
G_{0,n}^{\mathrm c}=0\qquad(n>2).
$$

A non-Gaussian interaction produces connected higher cumulants. Perturbative QFT is, in large part, the art of expanding around a Gaussian and organizing the non-Gaussian corrections.

## Nonzero mean

A shifted Gaussian has the form

$$
I[J]=\int d^Nx\,
\exp\left[-\frac12(x-\mu)^TA(x-\mu)+J^Tx\right].
$$

Completing the square or shifting $y=x-\mu$ gives

$$
Z[J]=\exp\left[J^T\mu+\frac12J^TA^{-1}J\right].
$$

Hence

$$
\langle x_i\rangle=\mu_i,
$$

and

$$
\langle x_i x_j\rangle_{\mathrm c}
=\langle x_i x_j\rangle-\langle x_i\rangle\langle x_j\rangle
=(A^{-1})_{ij}.
$$

This is why connected correlators subtract one-point functions. In QFT, the analogue is expanding around a background field or vacuum expectation value.

## Lorentzian Gaussian and iε

Path integrals in real time are oscillatory rather than absolutely convergent. A finite-dimensional Lorentzian Gaussian has the schematic form

$$
I_L[J]=\int d^Nx\,
\exp\left[-\frac{i}{2}x^TKx+iJ^Tx\right].
$$

Completing the square gives the source dependence

$$
\boxed{
I_L[J]\propto
\exp\left[\frac{i}{2}J^TK^{-1}J\right].
}
$$

The proportionality constant includes a phase and a determinant. To make the integral well-defined, one must specify a contour or add an $i\epsilon$ prescription. In finite dimensions this is a convergence prescription; in QFT it also encodes boundary conditions for propagators.

For the free real scalar field in qft.org conventions,

$$
S_0[\phi]
=-\frac12\int d^4x\,\phi(x)(\Box+m^2)\phi(x).
$$

The source term is

$$
\int d^4x\,J(x)\phi(x).
$$

The Lorentzian Gaussian analogy says

$$
Z_0[J]
\propto
\exp\left[\frac{i}{2}\int J K^{-1}J\right],
\qquad
K=\Box+m^2.
$$

But the Feynman propagator satisfies

$$
K D_F(x-y)=-i\delta^{(4)}(x-y),
$$

so

$$
K^{-1}=iD_F.
$$

Therefore

$$
\boxed{
Z_0[J]
=\exp\left[-\frac12\int d^4x\,d^4y\,J(x)D_F(x-y)J(y)\right]
}
$$

after normalizing $Z_0[0]=1$. This is exactly the source formula used in the Feynman-propagator page.

## From matrices to kernels

A field is an infinite collection of degrees of freedom, so the formal replacements are

$$
x_i\longrightarrow \phi(x),
\qquad
A_{ij}\longrightarrow K(x,y),
\qquad
(A^{-1})_{ij}\longrightarrow K^{-1}(x,y).
$$

The finite-dimensional quadratic form

$$
\frac12x_iA_{ij}x_j
$$

becomes a double integral

$$
\frac12\int d^dx\,d^dy\,\phi(x)K(x,y)\phi(y),
$$

or, for a local differential operator,

$$
\frac12\int d^dx\,\phi(x)K\phi(x).
$$

The finite-dimensional source term

$$
J_ix_i
$$

becomes

$$
\int d^dx\,J(x)\phi(x).
$$

The inverse matrix becomes the Green function:

$$
\int d^dz\,K(x,z)K^{-1}(z,y)=\delta^{(d)}(x-y).
$$

In Lorentzian QFT, the inverse must also know which boundary condition is intended: Feynman, retarded, advanced, or something else. The $i\epsilon$ prescription is what turns a formal inverse into a particular propagator.

## Determinants

The factor

$$
(\det A)^{-1/2}
$$

is independent of the source $J$, so it cancels in normalized correlators. That is why early correlator calculations can hide it inside the normalization.

But the determinant is not meaningless. It contributes to quantities that care about the normalization of the path integral, such as

```txt
vacuum energy,
free energy,
one-loop effective actions,
semiclassical fluctuation prefactors,
anomaly-related Jacobians.
```

In field theory, determinants are infinite products over modes and require regularization. The harmless-looking finite-dimensional factor becomes serious mathematical business.

## Common pitfalls

### Forgetting convergence

The Euclidean formula requires positive definiteness. Lorentzian integrals require a contour or $i\epsilon$ prescription. A formal Gaussian without a convergence prescription is not yet an integral.

### Dropping determinants everywhere

Determinants cancel in normalized correlation functions, but not in vacuum energies, partition functions, or effective actions.

### Confusing the kernel with its inverse

The quadratic operator $A$ or $K$ appears in the action. The propagator is its inverse, with boundary conditions.

### Missing zero modes

If $A$ has zero modes, $A^{-1}$ does not exist. Gauge fixing, collective coordinates, and constrained systems are sophisticated ways of handling this basic problem.

### Assuming every theory is Gaussian

Free theories are Gaussian. Interacting theories are not. Perturbation theory works by treating the non-Gaussian part as an expansion around the Gaussian core.

## Exercises

### Exercise 1: Complete the square

Show that

$$
-\frac12x^TAx+J^Tx
=-\frac12(x-A^{-1}J)^TA(x-A^{-1}J)+\frac12J^TA^{-1}J
$$

for symmetric invertible $A$.

<details>
<summary><strong>Solution</strong></summary>

Expand the shifted term:

$$
(x-A^{-1}J)^TA(x-A^{-1}J)
=x^TAx-x^TJ-J^Tx+J^TA^{-1}J.
$$

Since $x^TJ=J^Tx$,

$$
-\frac12(x-A^{-1}J)^TA(x-A^{-1}J)
=-\frac12x^TAx+J^Tx-\frac12J^TA^{-1}J.
$$

Adding $\frac12J^TA^{-1}J$ gives the desired identity.

</details>

### Exercise 2: Two-point function from sources

For

$$
Z[J]=\exp\left[\frac12J_iC_{ij}J_j\right],
$$

where $C_{ij}=C_{ji}$, show that

$$
\langle x_i x_j\rangle=C_{ij}.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate once:

$$
\frac{\partial Z}{\partial J_i}=C_{ij}J_jZ.
$$

Differentiate again:

$$
\frac{\partial^2Z}{\partial J_i\partial J_j}
=C_{ij}Z+C_{ik}J_kC_{jl}J_lZ.
$$

Setting $J=0$ and using $Z[0]=1$ gives

$$
\langle x_i x_j\rangle
=\left.\frac{\partial^2Z}{\partial J_i\partial J_j}\right|_{J=0}
=C_{ij}.
$$

For the Gaussian above, $C=A^{-1}$.

</details>

### Exercise 3: Four-point Wick pairing

Use the same $Z[J]$ to show that

$$
\langle x_i x_j x_k x_l\rangle
=C_{ij}C_{kl}+C_{ik}C_{jl}+C_{il}C_{jk}.
$$

<details>
<summary><strong>Solution</strong></summary>

Only terms quartic in $J$ contribute after four derivatives and setting $J=0$. Expanding

$$
Z[J]=1+\frac12J_aC_{ab}J_b+\frac{1}{8}(J_aC_{ab}J_b)^2+\cdots,
$$

the four derivatives act on the square of the quadratic term. The possible pairings of the labels $(i,j,k,l)$ are

$$
(ij)(kl),\qquad(ik)(jl),\qquad(il)(jk).
$$

Each pairing contributes the product of the corresponding covariance entries, giving

$$
\langle x_i x_j x_k x_l\rangle
=C_{ij}C_{kl}+C_{ik}C_{jl}+C_{il}C_{jk}.
$$

</details>

### Exercise 4: Connected four-point Gaussian moment

Show that the connected four-point moment of a centered Gaussian vanishes.

<details>
<summary><strong>Solution</strong></summary>

The connected moments are generated by $\log Z[J]$. For a centered Gaussian,

$$
\log Z[J]=\frac12J_iC_{ij}J_j,
$$

which is quadratic in $J$. Therefore

$$
\frac{\partial^4\log Z[J]}{\partial J_i\partial J_j\partial J_k\partial J_l}=0.
$$

Thus

$$
\langle x_i x_j x_k x_l\rangle_{\mathrm c}=0.
$$

Equivalently, the full four-point function is exactly the sum of products of two-point functions, so after subtracting those products nothing remains.

</details>

### Exercise 5: Lorentzian sign

Complete the square in

$$
I_L[J]=\int d^Nx\,\exp\left[-\frac{i}{2}x^TKx+iJ^Tx\right]
$$

and show that the source-dependent part is proportional to

$$
\exp\left[\frac{i}{2}J^TK^{-1}J\right].
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
x=y+K^{-1}J.
$$

Then

$$
-\frac{i}{2}x^TKx+iJ^Tx
=-\frac{i}{2}y^TKy+\frac{i}{2}J^TK^{-1}J.
$$

The $y$ integral is independent of $J$, so the source-dependent part is

$$
\exp\left[\frac{i}{2}J^TK^{-1}J\right].
$$

The remaining factor requires a contour or $i\epsilon$ prescription.

</details>

### Exercise 6: A zero mode

Let

$$
A=\begin{pmatrix}a&0\\0&0\end{pmatrix},
\qquad a>0.
$$

Explain why the Euclidean Gaussian integral over $\mathbb R^2$ diverges and why $A^{-1}$ does not exist.

<details>
<summary><strong>Solution</strong></summary>

The quadratic form is

$$
x^TAx=ax_1^2.
$$

It contains no $x_2$ dependence. Therefore

$$
\int_{\mathbb R^2}dx_1dx_2\,e^{-ax_1^2/2}
=\left(\int_{-\infty}^{\infty}dx_1\,e^{-ax_1^2/2}\right)
\left(\int_{-\infty}^{\infty}dx_2\right),
$$

and the second factor diverges. Since $\det A=0$, the matrix is not invertible and $A^{-1}$ does not exist. This is the finite-dimensional analogue of a field-theory zero mode.

</details>

## Sources and further reading

### Primary references

- P. A. M. Dirac, “The Lagrangian in Quantum Mechanics,” *Physikalische Zeitschrift der Sowjetunion* **3** (1933), for the early action-based viewpoint behind path integrals.
- R. P. Feynman, “Space-Time Approach to Non-Relativistic Quantum Mechanics,” *Reviews of Modern Physics* **20** (1948), for the path-integral formulation in quantum mechanics.

### Standard textbook treatments

- A. Zee, *Quantum Field Theory in a Nutshell*, appendix A, for Gaussian integration and the “central identity” of QFT.
- M. Srednicki, *Quantum Field Theory*, §§6–8, for path integrals in quantum mechanics, the harmonic oscillator, and free scalar field theory.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 28 and 32, for functional integrals and generating functionals.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§9.1–9.5 and appendix to ch. 9, for path-integral methods and Gaussian multiple integrals.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, §§9.1–9.2, for generating functionals and free Gaussian path integrals.

### For a first pass

- Zee, appendix A.
- Srednicki, §§6–8.
- Peskin and Schroeder, §9.1.

### For mathematical precision

- B. Simon, *Functional Integration and Quantum Physics*, for a more careful treatment of Gaussian measures and functional integrals.
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*, for constructive field theory and Euclidean functional integrals.
- M. Reed and B. Simon, *Methods of Modern Mathematical Physics*, Vol. II, for spectral theory and Gaussian-related functional-analytic tools.

## Version history

- **2026-05-23:** Initial qft.org page on finite-dimensional bosonic Gaussian integrals, sources, determinants, covariance matrices, Wick pairings, connected moments, Lorentzian phases, and the path-integral analogy.
