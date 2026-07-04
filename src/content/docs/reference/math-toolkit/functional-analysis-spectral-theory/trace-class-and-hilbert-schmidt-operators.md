---
title: "Trace-Class and Hilbert–Schmidt Operators"
description: "Explains Hilbert–Schmidt and trace-class operators, singular values, Schatten ideals, kernel criteria, traces, Fredholm determinants, and why QFT traces and determinants require more than compactness."
sidebar:
  label: "Trace-Class and Hilbert–Schmidt"
  order: 7
level: Graduate
status: "Polished draft"
source: "Standard functional-analysis and mathematical-physics references, including Reed–Simon, Simon, Teschl, Hall, Moretti, Conway, Kato, and QFT treatments of functional determinants, density matrices, heat kernels, and Fredholm determinants."
topics:
  - trace-class operators
  - Hilbert–Schmidt operators
  - Schatten ideals
  - singular values
  - trace ideals
  - Fredholm determinants
  - integral kernels
  - density matrices
  - heat kernels
  - functional determinants
canonicalTopics:
  - trace-class-operator
  - hilbert-schmidt-operator
  - schatten-ideal
  - singular-value
  - trace-ideal
  - fredholm-determinant
  - integral-kernel
  - density-matrix
  - heat-kernel
  - functional-determinant
researchStatus:
  established:
    - "Trace-class and Hilbert–Schmidt operators are standard Schatten ideals that refine compactness by imposing summability conditions on singular values."
  active:
    - "In continuum QFT, most formal traces and determinants are not automatically trace class; one must specify the regulator, subtraction, volume normalization, or operator ideal being used."
---

## Summary

Compact operators recover part of the finite-dimensional spectral picture: their nonzero singular values tend to zero. That is not enough to make traces, determinants, partition functions, or density matrices finite. Trace-class and Hilbert–Schmidt operators add the missing summability.

For a compact operator $T$ on a Hilbert space, its singular values are the eigenvalues of

$$
|T|=(T^*T)^{1/2},
$$

listed with multiplicity and in decreasing order:

$$
s_1(T)\ge s_2(T)\ge\cdots\ge0.
$$

Then

$$
T\text{ is Hilbert–Schmidt}
\quad\Longleftrightarrow\quad
\sum_n s_n(T)^2<\infty,
$$

while

$$
T\text{ is trace class}
\quad\Longleftrightarrow\quad
\sum_n s_n(T)<\infty.
$$

<figure class="doc-figure" style="--figure-width: 56rem;">

![Flow diagram showing compact operators, Schatten classes, Hilbert–Schmidt operators, trace-class operators, Fredholm data, kernel tests, product rules, and the warning that discrete spectrum does not by itself imply a finite determinant.](/figures/math-toolkit/trace-ideals-schatten-hierarchy.svg)

<figcaption>

Trace ideals refine compactness by summability of singular values. Hilbert–Schmidt operators have $\sum_n s_n(T)^2<\infty$, trace-class operators have $\sum_n s_n(T)<\infty$, and trace class is the natural setting for honest traces and Fredholm determinants. Compactness alone is not enough to make $\operatorname{Tr}T$ or $\det(1+T)$ finite.

</figcaption>
</figure>

The hierarchy is

$$
\text{trace class}
\quad\Rightarrow\quad
\text{Hilbert–Schmidt}
\quad\Rightarrow\quad
\text{compact}
\quad\Rightarrow\quad
\text{bounded},
$$

and every reverse implication is false in infinite dimensions.

This page is the repair kit for a common QFT mistake: replacing an infinite determinant by a product of eigenvalues just because the spectrum is discrete. Discreteness is a start, not a license. To take traces and determinants honestly, one needs summability, subtraction, regularization, or a statement about which trace ideal is being used.

## Prerequisites

You should know Hilbert spaces, linear operators, compact operators, and the spectral theorem from [Hilbert Spaces](/math-toolkit/functional-analysis-spectral-theory/hilbert-spaces/), [Linear Operators](/math-toolkit/functional-analysis-spectral-theory/linear-operators/), [Compact Operators](/math-toolkit/functional-analysis-spectral-theory/compact-operators/), and [Spectral Theorem](/math-toolkit/functional-analysis-spectral-theory/spectral-theorem/). Kernel examples use [Convolution](/math-toolkit/analysis-distributions-fourier/convolution/) and [Distributions in QFT](/math-toolkit/analysis-distributions-fourier/distributions-in-qft/). Determinant examples connect to [Functional Determinants](/math-toolkit/functional-integrals-determinants/functional-determinants/), [Zeta Regularization](/math-toolkit/functional-integrals-determinants/zeta-regularization/), and [Heat Kernel Expansion](/math-toolkit/functional-integrals-determinants/heat-kernel-expansion/).

## Core idea

In finite dimensions, every operator has finitely many singular values. Therefore every matrix has a finite Hilbert–Schmidt norm,

$$
\|A\|_2^2=\operatorname{Tr}(A^*A),
$$

and a finite trace norm,

$$
\|A\|_1=\operatorname{Tr}|A|.
$$

Infinite dimensions split these properties apart. A compact operator can have singular values tending to zero so slowly that neither

$$
\sum_ns_n(T)^2
$$

nor

$$
\sum_ns_n(T)
$$

converges. So compactness answers a qualitative question — do the singular values vanish? — while trace ideals answer quantitative questions — how fast do they vanish?

The physics translation is sharp. Compactness often gives a countable mode expansion. Hilbert–Schmidt summability often gives a finite quadratic norm or a square-integrable kernel. Trace class gives a finite ordinary trace. Determinants require at least trace-class perturbations of the identity, or a specified regularization scheme.

That is why the symbolic step

$$
\operatorname{Tr}f(A)=\sum_nf(\lambda_n)
$$

is not just notation. It asserts that the right-hand side converges in an appropriate sense. If it does not, the trace may still have a regulated meaning, but the regulator is part of the answer.

## Singular values

Let $T:\mathcal H\to\mathcal K$ be a compact operator between Hilbert spaces. The positive operator

$$
|T|=(T^*T)^{1/2}
$$

is compact and self-adjoint. Its nonzero eigenvalues are called the singular values of $T$:

$$
s_1(T)\ge s_2(T)\ge\cdots\ge0.
$$

The singular values measure the lengths of the principal axes of the image of the unit ball under $T$. For a diagonal operator on $\ell^2$,

$$
(Te_n)=a_ne_n,
\qquad
a_n\to0,
$$

the singular values are the decreasing rearrangement of $|a_n|$.

For a finite matrix, singular values are what one obtains from the singular-value decomposition. In infinite dimensions, compactness is the condition that makes the singular-value sequence tend to zero. It does not say the sequence is summable.

The operator norm is the largest singular value:

$$
\|T\|=s_1(T).
$$

The Hilbert–Schmidt and trace norms are

$$
\|T\|_2=\left(\sum_ns_n(T)^2\right)^{1/2},
$$

and

$$
\|T\|_1=\sum_ns_n(T).
$$

These are stronger than the operator norm. For trace-class $T$,

$$
\|T\|\le \|T\|_2\le\|T\|_1.
$$

## Schatten ideals

For $1\le p<\infty$, the Schatten class $\mathcal S_p$ consists of compact operators satisfying

$$
\sum_ns_n(T)^p<\infty.
$$

The norm is

$$
\|T\|_p=\left(\sum_ns_n(T)^p\right)^{1/p}.
$$

The two most important cases for QFT are

$$
\mathcal S_2=\text{Hilbert–Schmidt operators},
$$

and

$$
\mathcal S_1=\text{trace-class operators}.
$$

The word “ideal” means these classes are stable under multiplication by bounded operators. If $A$ and $B$ are bounded and $T\in\mathcal S_p$, then

$$
ATB\in\mathcal S_p,
$$

and

$$
\|ATB\|_p\le \|A\|\,\|T\|_p\,\|B\|.
$$

This stability is why trace ideals are useful in perturbation theory. If the dangerous part of an expression belongs to a trace ideal, multiplying it by bounded insertions does not immediately destroy the summability.

Schatten classes also satisfy Hölder-type inequalities. The case to remember is

$$
\mathcal S_2\cdot\mathcal S_2\subseteq\mathcal S_1.
$$

Two Hilbert–Schmidt factors can make a trace-class product. This is a small miracle that appears repeatedly in scattering theory, covariance estimates, and determinant formulas.

## Hilbert–Schmidt operators

An operator $T:\mathcal H\to\mathcal K$ is Hilbert–Schmidt if

$$
\sum_n\|Te_n\|_{\mathcal K}^2<\infty
$$

for one, and hence every, orthonormal basis $\{e_n\}$ of $\mathcal H$. The Hilbert–Schmidt norm is

$$
\|T\|_{\mathrm{HS}}^2
=\sum_n\|Te_n\|^2.
$$

This agrees with the singular-value definition:

$$
\|T\|_{\mathrm{HS}}^2=\sum_ns_n(T)^2.
$$

If $\mathcal H=\mathcal K$ and $T$ is Hilbert–Schmidt, then

$$
T^*T
$$

is trace class, and

$$
\|T\|_{\mathrm{HS}}^2=\operatorname{Tr}(T^*T).
$$

The Hilbert–Schmidt class itself is a Hilbert space with inner product

$$
\langle S,T\rangle_{\mathrm{HS}}=\operatorname{Tr}(S^*T).
$$

This is the infinite-dimensional analog of the Frobenius inner product for matrices.

Hilbert–Schmidt is often the right notion for square-integrable kernels, covariance differences, and quadratic error estimates. But Hilbert–Schmidt is still not enough for an ordinary trace of $T$ itself. For that, one needs trace class.

## Integral kernels

Let $(X,\mu)$ and $(Y,\nu)$ be measure spaces, and define

$$
(Tf)(x)=\int_YK(x,y)f(y)\,d\nu(y)
$$

as an operator

$$
T:L^2(Y,d\nu)\to L^2(X,d\mu).
$$

If

$$
\int_Xd\mu(x)\int_Yd\nu(y)\,|K(x,y)|^2<\infty,
$$

then $T$ is Hilbert–Schmidt and

$$
\|T\|_{\mathrm{HS}}^2
=\int_Xd\mu(x)\int_Yd\nu(y)\,|K(x,y)|^2.
$$

This is the continuum version of saying that a matrix is Hilbert–Schmidt when its entries are square-summable:

$$
\sum_{m,n}|K_{mn}|^2<\infty.
$$

For QFT this criterion is useful but also sobering. Many kernels that physicists call propagators are not square-integrable. They can fail at short distance, at long distance, or both. A local propagator usually has ultraviolet singularities near coincident points; a massless infinite-volume propagator may also have infrared trouble.

Adding a cutoff, putting the theory in finite volume, composing with a smoothing operator, smearing with test functions, or taking a sufficiently decaying difference can turn a formal kernel into a Hilbert–Schmidt operator. The operation that does this is part of the mathematical statement.

## Trace-class operators

An operator $T$ is trace class if

$$
\|T\|_1=\operatorname{Tr}|T|=\sum_ns_n(T)<\infty.
$$

For trace-class $T$, the trace

$$
\operatorname{Tr}T=\sum_n\langle e_n,Te_n\rangle
$$

is absolutely convergent and independent of the orthonormal basis $\{e_n\}$.

If $T\ge0$, then trace class means

$$
\operatorname{Tr}T<\infty,
$$

and the trace is the sum of the eigenvalues, counted with multiplicity:

$$
\operatorname{Tr}T=\sum_n\lambda_n(T).
$$

For a general trace-class operator, eigenvalues can be complex. The singular-value definition is the safer definition; eigenvalue sums are more delicate for non-normal operators.

Trace class is the natural home of density matrices. A quantum state represented by a density operator $\rho$ must satisfy

$$
\rho\ge0,
\qquad
\operatorname{Tr}\rho=1.
$$

Thus $\rho$ is positive trace class. A positive compact operator with eigenvalues tending to zero is not necessarily a density matrix; its eigenvalues must also be summable.

## Why trace class is stronger

The implication

$$
\mathcal S_1\subseteq\mathcal S_2
$$

follows from the elementary fact that an absolutely summable nonnegative sequence is square-summable. If $\sum_ns_n<\infty$, then $s_n\to0$, so eventually $s_n\le1$, and hence $s_n^2\le s_n$ for all large $n$.

The reverse implication fails. The diagonal operator on $\ell^2$ defined by

$$
Te_n=\frac1n e_n
$$

has singular values

$$
s_n(T)=\frac1n.
$$

It is Hilbert–Schmidt because

$$
\sum_{n=1}^\infty\frac1{n^2}<\infty,
$$

but it is not trace class because

$$
\sum_{n=1}^\infty\frac1n=\infty.
$$

Likewise, the diagonal operator with singular values

$$
s_n=\frac1{\sqrt n}
$$

is compact but not Hilbert–Schmidt.

This hierarchy is the mode-sum lesson in its purest form. The fact that eigenvalues go to zero does not tell you which sums converge.

## Traces and cyclicity

In finite dimensions,

$$
\operatorname{Tr}(AB)=\operatorname{Tr}(BA)
$$

for all square matrices. In infinite dimensions, this formula needs hypotheses.

A useful safe statement is: if $T$ is trace class and $A$ is bounded, then both $AT$ and $TA$ are trace class, and

$$
\operatorname{Tr}(AT)=\operatorname{Tr}(TA).
$$

This is why trace-class hypotheses appear behind formal manipulations such as

$$
\delta\log\det A=\operatorname{Tr}(A^{-1}\delta A).
$$

The expression on the right is not automatically meaningful. One needs $A^{-1}\delta A$ to be trace class, or one needs a regulated trace with a specified anomaly or subtraction.

This is one of the quiet places where anomalies enter. A cyclic finite-dimensional trace would kill many commutators. A regulator that does not preserve a formal cyclic manipulation can leave behind a local anomaly. The issue is not that trace cyclicity “fails” for trace-class operators; it is that the original unregulated expression was never trace class.

## Fredholm determinants

If $T$ is trace class, then the Fredholm determinant

$$
\det(\mathbf 1+T)
$$

is defined by a convergent product over eigenvalues:

$$
\det(\mathbf 1+T)=\prod_n(1+\lambda_n(T)),
$$

with eigenvalues counted algebraically.

Near $T=0$, one may write the logarithm as

$$
\log\det(\mathbf 1+T)
=\sum_{k=1}^\infty\frac{(-1)^{k+1}}{k}\operatorname{Tr}(T^k),
$$

with the usual convergence conditions and analytic continuation beyond that region.

If $T$ is Hilbert–Schmidt but not trace class, the ordinary Fredholm determinant may fail. There is a modified determinant, often written $\det_2(\mathbf 1+T)$, that subtracts the linear trace term. Symbolically,

$$
\det_2(\mathbf 1+T)=\det\!\left((\mathbf 1+T)e^{-T}\right),
$$

when the expression is interpreted correctly. This is a useful reminder: Hilbert–Schmidt perturbations may allow determinant-like objects, but the determinant is not the same as the trace-class Fredholm determinant.

QFT one-loop determinants are even more singular in typical continuum problems. A Gaussian integral might formally produce

$$
(\det A)^{-1/2},
$$

but $A$ is usually unbounded and not a trace-class perturbation of the identity. Heat-kernel, zeta, Pauli–Villars, dimensional, lattice, or cutoff regularization supplies additional data.

## Heat kernels and trace class

For a positive elliptic operator $A$ on a compact Riemannian manifold, the heat operator

$$
e^{-sA}
$$

is often trace class for every $s>0$. Its trace is the heat trace

$$
K(s)=\operatorname{Tr}(e^{-sA})=\sum_ne^{-s\lambda_n}.
$$

The exponential damping makes the high eigenvalues summable. As $s\downarrow0$, the trace usually diverges with a local asymptotic expansion,

$$
K(s)\sim\frac1{(4\pi s)^{d/2}}\sum_{j\ge0}a_j s^j,
$$

for Laplace-type operators in $d$ dimensions, with boundary and half-integer modifications when appropriate.

The heat trace therefore illustrates the double life of trace class. For each fixed $s>0$, $e^{-sA}$ may be trace class. But the ultraviolet limit $s\downarrow0$ exposes the local divergences that QFT must renormalize.

Zeta regularization packages related spectral data into

$$
\zeta_A(z)=\operatorname{Tr}(A^{-z}),
$$

where the trace may converge only for $\operatorname{Re}z$ large and must then be analytically continued. Analytic continuation is not the same thing as ordinary trace-class summability at $z=0$.

## Density matrices and reduced states

In ordinary quantum mechanics, a mixed state is represented by a positive trace-class operator $\rho$ with trace one. Its spectral decomposition is

$$
\rho=\sum_np_n|n\rangle\langle n|,
$$

where

$$
p_n\ge0,
\qquad
\sum_np_n=1.
$$

The von Neumann entropy is

$$
S(\rho)=-\operatorname{Tr}(\rho\log\rho)
=-\sum_np_n\log p_n,
$$

provided the sum is finite or allowed to be $+\infty$.

In continuum QFT, reduced density matrices are subtle because local algebras in relativistic QFT are typically not ordinary finite-dimensional tensor factors. The finite-dimensional or lattice formula for $\rho_A$ is often a regulated approximation, not literally the operator-theoretic object associated with a continuum region. Still, trace-class language is indispensable when discussing regulated density matrices, thermal states in finite volume, trace formulas, and entanglement calculations with cutoffs.

## Trace ideals in perturbation theory

Trace ideals often appear through differences rather than through individual operators. For example, two resolvents may each fail to be trace class, but their difference may have better decay:

$$
(A-z)^{-1}-(A_0-z)^{-1}.
$$

In scattering theory and spectral shift theory, trace-class or Hilbert–Schmidt conditions on such differences control changes in spectral densities, phase shifts, and determinants.

This is also the moral behind many QFT subtractions. A bare expression may diverge, but a difference between two backgrounds, or a differentiated expression, can be trace class after enough cancellations. The finite observable is not “the trace” alone; it is the trace together with the prescription that removed the non-trace-class part.

For example, a one-loop effective action difference may be written formally as

$$
\frac12\operatorname{Tr}\log\frac{A}{A_0}.
$$

A mathematically meaningful version might require showing that a resolvent difference, heat-kernel difference, or relative determinant is trace class after subtracting local counterterms.

## Common QFT appearances

**Gaussian functional integrals.** Finite-dimensional Gaussian integrals produce determinants. Infinite-dimensional Gaussian path integrals require deciding whether the determinant is Fredholm, relative, zeta-regularized, heat-kernel regulated, or defined by another scheme.

**Fermion determinants.** Integrating out fermions formally gives $\det D$ or $\operatorname{Pf}(C D)$, depending on the reality structure. The trace-class issue is hidden in the definition of the regulated determinant and in possible phase anomalies.

**Covariance operators.** A Gaussian measure on an infinite-dimensional Hilbert space is controlled by a positive trace-class covariance operator. Continuum fields often live as distributions rather than Hilbert-space-valued random variables precisely because their formal covariance is too singular.

**Thermal traces.** A finite-volume quantum system may have

$$
Z(\beta)=\operatorname{Tr}(e^{-\beta H})<\infty
$$

for $\beta>0$. Infinite volume usually turns this into a free-energy density rather than a finite trace.

**Fredholm determinant formulas.** In integrable systems, random matrices, and some exact QFT calculations, determinants of $\mathbf 1+K$ are meaningful when $K$ is trace class, or after replacing the determinant by a modified determinant adapted to a weaker class.

## Common pitfalls

**Thinking compact means trace class.** Compactness only says $s_n\to0$. Trace class requires $\sum_ns_n<\infty$.

**Using eigenvalues when singular values are needed.** Trace-class and Hilbert–Schmidt definitions are based on singular values. Eigenvalues are safe for positive compact operators, but non-normal operators can be deceptive.

**Assuming a discrete spectrum makes a determinant finite.** A discrete spectrum can still produce divergent sums such as $\sum_n\log\lambda_n$ or $\sum_n\lambda_n^{-1}$.

**Forgetting the volume limit.** Finite volume can make heat kernels trace class and spectra discrete. Infinite volume often replaces traces by trace densities and eigenvalue sums by spectral-density integrals.

**Applying cyclicity without hypotheses.** The identity $\operatorname{Tr}(AB)=\operatorname{Tr}(BA)$ requires trace-class control. Otherwise anomalous-looking terms may be artifacts of illegal trace manipulations — or real anomalies revealed by the regulator.

**Confusing Hilbert–Schmidt kernels with propagators.** A square-integrable kernel is Hilbert–Schmidt. Many QFT propagators are distributions, not square-integrable kernels.

**Treating regularized traces as ordinary traces.** A zeta-regularized or heat-kernel-subtracted trace is not an ordinary trace unless a theorem says so. It can have different cyclicity, locality, and anomaly properties.

## Worked examples

### Diagonal operators on sequences

Let $T_\alpha$ act on $\ell^2(\mathbb N)$ by

$$
T_\alpha e_n=\frac1{n^\alpha}e_n.
$$

Then $T_\alpha$ is compact exactly when $\alpha>0$, because the singular values tend to zero. It is Hilbert–Schmidt exactly when

$$
\sum_{n=1}^\infty \frac1{n^{2\alpha}}<\infty,
$$

which means $\alpha>1/2$. It is trace class exactly when

$$
\sum_{n=1}^\infty\frac1{n^\alpha}<\infty,
$$

which means $\alpha>1$.

This example shows all three thresholds at once:

$$
\alpha>0\quad\text{compact},
\qquad
\alpha>\frac12\quad\text{Hilbert–Schmidt},
\qquad
\alpha>1\quad\text{trace class}.
$$

### Heat trace on a circle

Let

$$
A=-\frac{d^2}{dx^2}
$$

on a circle of circumference $L$. Its eigenvalues are

$$
\lambda_n=\left(\frac{2\pi n}{L}\right)^2,
\qquad n\in\mathbb Z.
$$

The operator $A$ is unbounded, but for $s>0$,

$$
e^{-sA}
$$

has eigenvalues

$$
e^{-s(2\pi n/L)^2}.
$$

The heat trace is

$$
\operatorname{Tr}(e^{-sA})
=\sum_{n\in\mathbb Z}e^{-s(2\pi n/L)^2},
$$

which converges for every $s>0$. As $s\downarrow0$, it diverges like

$$
\operatorname{Tr}(e^{-sA})\sim\frac{L}{\sqrt{4\pi s}}.
$$

So the heat operator is trace class for positive heat time, but the ultraviolet limit remembers the infinite number of local degrees of freedom.

## Exercises

### Exercise 1: Three thresholds for a diagonal operator

For $T_\alpha e_n=n^{-\alpha}e_n$ on $\ell^2(\mathbb N)$, determine for which $\alpha$ the operator is compact, Hilbert–Schmidt, and trace class.

<details><summary><strong>Solution</strong></summary>

The singular values are

$$
s_n(T_\alpha)=n^{-\alpha}.
$$

Compactness requires $s_n(T_\alpha)\to0$, so $\alpha>0$.

Hilbert–Schmidt requires

$$
\sum_n s_n(T_\alpha)^2
=\sum_{n=1}^\infty\frac1{n^{2\alpha}}<\infty,
$$

so $2\alpha>1$, or

$$
\alpha>\frac12.
$$

Trace class requires

$$
\sum_n s_n(T_\alpha)
=\sum_{n=1}^\infty\frac1{n^\alpha}<\infty,
$$

so

$$
\alpha>1.
$$

</details>

### Exercise 2: Square-summable kernels are Hilbert–Schmidt

Let

$$
(Tf)(x)=\int_YK(x,y)f(y)\,d\nu(y)
$$

with $K\in L^2(X\times Y)$. Show that $T$ is Hilbert–Schmidt and compute its Hilbert–Schmidt norm.

<details><summary><strong>Solution</strong></summary>

Choose an orthonormal basis $\{e_n\}$ for $L^2(Y)$. For each $x$, Parseval's identity gives

$$
\sum_n\left|\int_YK(x,y)e_n(y)\,d\nu(y)\right|^2
=\int_Y|K(x,y)|^2\,d\nu(y),
$$

with the usual complex conjugation convention absorbed into the inner product. Integrating over $x$ gives

$$
\sum_n\|Te_n\|_{L^2(X)}^2
=\int_Xd\mu(x)\int_Yd\nu(y)\,|K(x,y)|^2.
$$

Therefore $T$ is Hilbert–Schmidt and

$$
\|T\|_{\mathrm{HS}}^2
=\int_Xd\mu(x)\int_Yd\nu(y)\,|K(x,y)|^2.
$$

</details>

### Exercise 3: Hilbert–Schmidt does not imply trace class

Show that the diagonal operator

$$
Te_n=\frac1n e_n
$$

on $\ell^2(\mathbb N)$ is Hilbert–Schmidt but not trace class.

<details><summary><strong>Solution</strong></summary>

The singular values are $s_n=1/n$. Then

$$
\sum_{n=1}^\infty s_n^2
=\sum_{n=1}^\infty\frac1{n^2}<\infty,
$$

so $T$ is Hilbert–Schmidt. But

$$
\sum_{n=1}^\infty s_n
=\sum_{n=1}^\infty\frac1n=\infty,
$$

so $T$ is not trace class.

</details>

### Exercise 4: Product of two diagonal Hilbert–Schmidt operators

Let $Ae_n=a_ne_n$ and $Be_n=b_ne_n$ on $\ell^2$, with $a_n,b_n\in\ell^2$. Show that $AB$ is trace class.

<details><summary><strong>Solution</strong></summary>

The product is diagonal:

$$
ABe_n=a_nb_ne_n.
$$

Its trace norm is

$$
\|AB\|_1=\sum_n|a_nb_n|.
$$

By Cauchy–Schwarz,

$$
\sum_n|a_nb_n|
\le\left(\sum_n|a_n|^2\right)^{1/2}
\left(\sum_n|b_n|^2\right)^{1/2}<\infty.
$$

Therefore $AB$ is trace class.

</details>

### Exercise 5: Heat-kernel damping on the circle

For the circle Laplacian with eigenvalues $\lambda_n=(2\pi n/L)^2$, show that $e^{-sA}$ is trace class for $s>0$.

<details><summary><strong>Solution</strong></summary>

The eigenvalues of $e^{-sA}$ are

$$
e^{-s(2\pi n/L)^2}.
$$

Since $e^{-c n^2}$ is summable for every $c>0$,

$$
\sum_{n\in\mathbb Z}e^{-s(2\pi n/L)^2}<\infty
$$

for $s>0$. The operator is positive, so summability of its eigenvalues is exactly trace class.

</details>

## References

- M. Reed and B. Simon, *Methods of Modern Mathematical Physics I: Functional Analysis*. Standard reference for trace ideals and compact operators.
- B. Simon, *Trace Ideals and Their Applications*. Classic reference for Schatten classes, trace-class perturbations, and determinants.
- G. Teschl, *Mathematical Methods in Quantum Mechanics*. Useful for trace ideals, compact resolvents, and Schrödinger operators.
- B. C. Hall, *Quantum Theory for Mathematicians*. Clear functional-analysis background for quantum theory.
- V. Moretti, *Spectral Theory and Quantum Mechanics*. Physics-oriented treatment of spectral theory, traces, and operator classes.
- T. Kato, *Perturbation Theory for Linear Operators*. Classic source on perturbations, compactness, and spectral stability.
- M. Srednicki, *Quantum Field Theory*. Useful for functional determinants and fermionic path integrals.
- M. Nakahara, *Geometry, Topology and Physics*. Useful for heat kernels, Dirac operators, and determinant-related geometric examples.

## Version history

- 2026-06-25: Initial polished draft.
