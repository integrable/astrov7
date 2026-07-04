---
title: "Error Analysis"
description: "A QFT-oriented guide to numerical error, residuals, conditioning, discretization error, roundoff, Monte Carlo uncertainty, continuum extrapolation, and reproducibility checks."
sidebar:
  label: "Error Analysis"
  order: 7
level: Graduate
status: "Polished draft"
source: "Numerical analysis, statistical error estimation, lattice field theory, spectral discretization, Monte Carlo methods, finite-size scaling, and continuum extrapolation practice."
topics:
  - error analysis
  - residuals
  - conditioning
  - discretization error
  - roundoff error
  - Monte Carlo uncertainty
  - continuum extrapolation
  - reproducibility
canonicalTopics:
  - numerical-error-analysis
  - residual-and-condition-number
  - discretization-error
  - monte-carlo-error
  - continuum-extrapolation
researchStatus:
  established:
    - "Residuals, conditioning, truncation error, roundoff error, convergence studies, statistical error estimates, and extrapolation fits are standard parts of numerical analysis and computational physics."
  active:
    - "Error quantification for lattice QFT, tensor networks, conformal bootstrap computations, stochastic quantization, machine-learning-assisted solvers, and real-time simulations remains an active methodological area."
---

## Summary

A numerical result is not a number. It is a number together with a claim about how wrong it might be.

In QFT and statistical field theory, numerical error has many sources:

| Source | Typical symptom | QFT example |
|---|---|---|
| discretization error | answer changes with lattice spacing or basis size | $a\to0$ continuum extrapolation |
| finite-volume error | answer changes with box size | mass gap from a finite spatial torus |
| truncation error | answer changes with cutoff in modes or states | Hamiltonian truncation, spectral methods |
| iterative-solver error | residual has not converged | nonlinear saddle equation, linear solve |
| conditioning error | small input errors create large output errors | nearly singular Hessian, zero modes |
| roundoff error | loss of digits from floating-point arithmetic | subtracting nearly equal large numbers |
| Monte Carlo error | statistical fluctuations and autocorrelation | lattice expectation values |
| model or fit error | extrapolation depends on ansatz | fitting critical exponents or continuum limits |

The goal of error analysis is not to produce decorative error bars. The goal is to decide whether the computed quantity answers the physics question.

The basic workflow is:

$$
\text{define the exact quantity}
\longrightarrow
\text{regularize and discretize}
\longrightarrow
\text{solve approximately}
\longrightarrow
\text{estimate error}
\longrightarrow
\text{test convergence}
\longrightarrow
\text{quote a result honestly}.
$$

## Prerequisites

You should know basic numerical linear algebra, Taylor expansion, norms, eigenvalues, Gaussian error propagation, and the distinction between exact continuum quantities and regulated approximations. Helpful nearby pages include [Finite-Difference Methods](/math-toolkit/numerical-mathematics/finite-difference-methods/), [Spectral Methods](/math-toolkit/numerical-mathematics/spectral-methods/), [Monte Carlo Basics](/math-toolkit/numerical-mathematics/monte-carlo-basics/), [Nonlinear Solvers](/math-toolkit/numerical-mathematics/nonlinear-solvers/), and [Eigenvalue Problems](/math-toolkit/numerical-mathematics/eigenvalue-problems/).

We write $Q$ for an exact target quantity and $Q_h$ for an approximation controlled by a resolution parameter $h$, such as a lattice spacing, time step, mesh width, or inverse basis cutoff.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A flowchart showing exact quantity, regularization, discretization, solver error, statistical error, extrapolation, and quoted result.](/figures/math-toolkit/error-analysis-budget-flow.svg)

<figcaption>

A computational QFT number has an uncertainty budget. The total error is not usually one thing; it combines discretization, finite-volume, truncation, solver, conditioning, roundoff, Monte Carlo, and fit-systematic effects.

</figcaption>
</figure>

## Exact quantity versus computed quantity

Begin by naming the exact quantity. For example:

$$
Q=\langle \mathcal O\rangle_{\mathrm{continuum},\,L=\infty}
$$

might be an infinite-volume continuum expectation value. A calculation may instead produce

$$
\widehat Q_{a,L,N,\epsilon,M},
$$

where:

- $a$ is a lattice spacing,
- $L$ is a finite box size,
- $N$ is a basis or truncation size,
- $\epsilon$ is a solver tolerance,
- $M$ is the number of Monte Carlo samples.

The difference

$$
\widehat Q_{a,L,N,\epsilon,M}-Q
$$

is the total error. Error analysis decomposes this into pieces that can be estimated, bounded, or at least stress-tested.

A useful schematic decomposition is

$$
\widehat Q-Q
=
(\widehat Q-Q_{a,L,N})
+(Q_{a,L,N}-Q_{0,L,N})
+(Q_{0,L,N}-Q_{0,\infty,N})
+(Q_{0,\infty,N}-Q).
$$

The first term contains solver, floating-point, and statistical error. The second is discretization error. The third is finite-volume error. The fourth is truncation or modeling error. In real calculations the split is not always clean, but writing it down prevents category mistakes.

## Absolute and relative error

If $q$ approximates $Q$, the absolute error is

$$
|q-Q|.
$$

The relative error is

$$
\frac{|q-Q|}{|Q|},
$$

when $Q\ne0$.

Relative error is often more meaningful for nonzero masses, energies, dimensions, or matrix elements. Absolute error is safer when the exact value may vanish because of symmetry or subtraction.

For example, if a Ward identity predicts

$$
\partial_\mu J^\mu=0,
$$

then the absolute size of the violation is meaningful. A relative error with denominator zero is just a little trap wearing a fake mustache.

## Residual error

For a linear system

$$
Ax=b,
$$

the residual of an approximate solution $\widehat x$ is

$$
r=b-A\widehat x.
$$

A small residual means $\widehat x$ almost solves the discrete equation. It does **not** automatically mean $\widehat x$ is close to the exact solution.

Let $x$ be the exact solution of the discrete system. Then

$$
A(x-\widehat x)=r,
$$

so

$$
\|x-\widehat x\|\le \|A^{-1}\|\,\|r\|.
$$

The inverse norm matters. If $A$ is nearly singular, a tiny residual can still hide a large solution error.

For a nonlinear equation

$$
F(u)=0,
$$

the residual is

$$
r=F(\widehat u).
$$

Near a regular solution $u_*$,

$$
F(\widehat u)\approx J(u_*)(\widehat u-u_*),
$$

where

$$
J_{ij}=\frac{\partial F_i}{\partial u_j}.
$$

Again, the conditioning of the Jacobian controls the relation between residual and actual error.

## Conditioning

A problem is well-conditioned if small changes in input produce small changes in output. It is ill-conditioned if small perturbations get amplified.

For an invertible matrix $A$, the condition number in a norm is

$$
\kappa(A)=\|A\|\,\|A^{-1}\|.
$$

For the Euclidean norm and a Hermitian positive matrix,

$$
\kappa(A)=\frac{\lambda_{\max}}{\lambda_{\min}}.
$$

If $A$ has a small eigenvalue, the problem is sensitive. In QFT this often has physical meaning: a near-zero mode may signal a symmetry, collective coordinate, critical slowing down, gauge redundancy, Goldstone mode, or instability.

Ill-conditioning is not always a numerical defect. Sometimes it is the physics waving a tiny red flag.

## Stability, consistency, and convergence

Three words organize many discretization arguments.

A discretization is **consistent** if the discrete equations approach the continuum equations as the resolution is refined. For a differential operator $L$ and discrete operator $L_h$, consistency means

$$
L_h f_h = Lf + O(h^p)
$$

for smooth test functions, after identifying continuum functions with grid values.

A scheme is **stable** if errors do not grow uncontrollably under the numerical evolution or solve.

A scheme is **convergent** if the numerical solution approaches the exact continuum solution:

$$
\|u_h-u\|\to0
\qquad
\text{as }h\to0.
$$

For many linear initial-value problems, the moral is:

$$
\text{consistency} + \text{stability} \Rightarrow \text{convergence}.
$$

That slogan is not a license to skip checks. It tells you what to check.

## Truncation and discretization error

Suppose a method has order $p$:

$$
Q_h=Q+c h^p+O(h^{p+1}).
$$

If you compute at two resolutions $h$ and $h/2$, then

$$
Q_{h/2}-Q_h
= c\left(\frac{h^p}{2^p}-h^p\right)+O(h^{p+1}).
$$

A simple Richardson extrapolation gives

$$
Q\approx Q_{h/2}+\frac{Q_{h/2}-Q_h}{2^p-1}.
$$

This is useful only if the calculation is in the asymptotic regime where the leading $h^p$ behavior dominates. If not, Richardson extrapolation turns optimism into arithmetic.

In lattice QFT, one often writes the continuum extrapolation as

$$
Q(a)=Q(0)+c_1 a^p+c_2 a^{p+1}+\cdots,
$$

or, if symmetries remove odd powers,

$$
Q(a)=Q(0)+c_1 a^2+c_2 a^4+\cdots.
$$

The power $p$ is determined by the action, operators, symmetries, and improvement scheme.

## Finite-volume error

A finite box changes the spectrum and long-distance correlations. If the theory has a mass gap $m$, finite-volume corrections often scale like

$$
e^{-mL}
$$

up to powers of $L$. If the theory is critical or massless, finite-size corrections are typically power laws:

$$
L^{-\Delta}.
$$

This distinction matters. Extrapolating a massless system with an exponential ansatz is not conservative; it is just wrong in a polished outfit.

A good finite-volume study computes at several $L$ and asks whether the chosen scaling form is physically justified.

## Statistical error

For independent samples $X_1,\ldots,X_M$ with mean $\mu$ and variance $\sigma^2$, the sample mean

$$
\overline X=\frac1M\sum_{i=1}^M X_i
$$

has variance

$$
\operatorname{Var}(\overline X)=\frac{\sigma^2}{M}.
$$

The standard error is

$$
\operatorname{SE}(\overline X)=\frac{s}{\sqrt M},
$$

where $s^2$ is the sample variance.

Monte Carlo estimates therefore converge like

$$
M^{-1/2}.
$$

That slow square-root law is why a factor of $100$ more samples buys only a factor of $10$ smaller statistical error. Monte Carlo is honest but not especially generous.

## Autocorrelation

Markov-chain Monte Carlo samples are not independent. If $X_t$ is measured along a chain, the normalized autocorrelation function is

$$
\rho(k)=\frac{\operatorname{Cov}(X_t,X_{t+k})}{\operatorname{Var}(X_t)}.
$$

The integrated autocorrelation time is

$$
\tau_{\mathrm{int}}
=\frac12+\sum_{k=1}^{\infty}\rho(k).
$$

The variance of the sample mean is approximately

$$
\operatorname{Var}(\overline X)
\approx
\frac{2\tau_{\mathrm{int}}\sigma^2}{M}.
$$

Thus the effective number of independent samples is

$$
M_{\mathrm{eff}}\approx \frac{M}{2\tau_{\mathrm{int}}}.
$$

Near a critical point, $\tau_{\mathrm{int}}$ can grow dramatically. This is critical slowing down. Ignoring it makes error bars look heroic and fake.

## Bias and variance

An estimator $\widehat Q$ has bias

$$
\operatorname{Bias}(\widehat Q)=\mathbb E[\widehat Q]-Q.
$$

Its mean-square error is

$$
\mathbb E[(\widehat Q-Q)^2]
=
\operatorname{Var}(\widehat Q)+\operatorname{Bias}(\widehat Q)^2.
$$

Monte Carlo error bars usually estimate variance. They do not automatically estimate bias from thermalization, finite volume, discretization, truncation, an imperfect ansatz, or a failed solver.

This is one of the most important distinctions in computational QFT:

$$
\text{small statistical error} \ne \text{small total error}.
$$

## Roundoff and floating-point error

Floating-point arithmetic represents numbers with finite precision. In double precision, the machine epsilon is roughly

$$
\epsilon_{\mathrm{mach}}\sim 10^{-16}.
$$

A stable computation may accumulate errors of order a modest multiple of $\epsilon_{\mathrm{mach}}$. An unstable or ill-conditioned computation can amplify roundoff dramatically.

The classic danger is subtractive cancellation. If two nearly equal numbers are subtracted,

$$
A-B,
\qquad
A\approx B,
$$

then leading digits cancel and relative precision can be lost. In QFT calculations, this appears in vacuum subtractions, determinant ratios, nearly degenerate eigenvalues, Ward-identity checks, and difference estimators.

Sometimes the cure is algebraic reformulation. Sometimes it is higher precision. Sometimes it is not doing the subtraction in that form at all.

## Error propagation

Suppose $Q=f(x_1,\ldots,x_n)$ and the inputs have covariance matrix

$$
\Sigma_{ij}=\operatorname{Cov}(x_i,x_j).
$$

For small uncertainties, linear propagation gives

$$
\operatorname{Var}(Q)
\approx
\sum_{i,j}\frac{\partial f}{\partial x_i}\Sigma_{ij}\frac{\partial f}{\partial x_j}.
$$

If the inputs are independent, this reduces to

$$
\operatorname{Var}(Q)
\approx
\sum_i\left(\frac{\partial f}{\partial x_i}\right)^2\sigma_i^2.
$$

Do not drop correlations just because the formula looks nicer without them. Correlations are often large when quantities are measured on the same configurations, fitted from the same correlator matrix, or obtained from the same ensemble.

## Fits and covariance matrices

A least-squares fit minimizes

$$
\chi^2(\theta)
=
\sum_{i,j}(y_i-f_i(\theta))C^{-1}_{ij}(y_j-f_j(\theta)),
$$

where $C$ is the covariance matrix of the data. If data points are correlated, $C$ is not diagonal.

A fit result should report:

- the model or ansatz,
- the fit range,
- whether correlations were included,
- parameter uncertainties,
- goodness-of-fit diagnostics,
- stability under reasonable changes of fit range and ansatz.

In QFT, extracted masses, scaling dimensions, critical exponents, matrix elements, and continuum limits often depend more on fit-systematic uncertainty than on raw statistical error.

## Continuum extrapolation

A continuum extrapolation estimates

$$
Q(0)=\lim_{a\to0}Q(a).
$$

A common fit form is

$$
Q(a)=Q(0)+c a^p.
$$

More realistically one may need

$$
Q(a)=Q(0)+c_1a^p+c_2a^{p'}+\cdots.
$$

The danger is underfitting: too simple an ansatz can give a tiny error bar around a biased continuum value. The opposite danger is overfitting: too many parameters make the extrapolation meaningless.

A credible continuum extrapolation usually requires:

1. at least several lattice spacings,
2. a theoretically motivated leading power,
3. fit stability under excluding coarse data,
4. separate accounting of statistical and systematic errors,
5. checks against improved actions or independent discretizations when possible.

## Error bars versus intervals of trust

A statistical one-sigma error bar often means that, under a model, repeated experiments would fluctuate with standard deviation $\sigma$. It does not mean “the true answer is definitely inside this interval.”

A systematic uncertainty is different. It often represents a range obtained by varying reasonable analysis choices. Combining statistical and systematic errors requires judgment. One common report is

$$
Q=Q_*\pm \sigma_{\mathrm{stat}}\pm \sigma_{\mathrm{sys}}.
$$

Another is to add independent uncertainties in quadrature:

$$
\sigma_{\mathrm{tot}}
=\sqrt{\sigma_1^2+\sigma_2^2+\cdots}.
$$

But systematic errors are not always independent random variables. Do not hide judgment behind a square root.

## A practical validation checklist

Before trusting a numerical QFT result, ask:

| Check | Question |
|---|---|
| dimensional check | Does the answer have the right units or scaling dimension? |
| symmetry check | Are exact symmetries and Ward identities respected? |
| residual check | Does the computed solution solve the discrete equations? |
| refinement check | Does the result converge as resolution improves? |
| finite-volume check | Does the result stabilize as $L$ changes? |
| solver check | Is the result insensitive to tighter tolerances? |
| statistical check | Are autocorrelations and covariance included? |
| fit-stability check | Does the answer survive reasonable fit variations? |
| limiting-case check | Does the method reproduce solvable cases? |
| independent-method check | Does another discretization or algorithm agree? |

None of these checks proves correctness alone. Together they build a case.

## Common pitfalls

### Treating the residual as the error

A small residual means the discrete equation is nearly solved. It does not guarantee closeness to the exact solution unless the problem is well-conditioned.

### Quoting Monte Carlo error as total error

Monte Carlo error is statistical. It does not include continuum extrapolation, finite volume, thermalization, model bias, or solver tolerance.

### Extrapolating outside the asymptotic regime

A fit of the form $Q(a)=Q(0)+ca^p$ is meaningful only when the omitted terms are genuinely subleading over the fitted range.

### Ignoring correlations

Correlated data points can make diagonal least-squares fits overconfident. This is common in effective-mass fits, bootstrap bounds, spectral estimates, and ensemble averages.

### Hiding physical zero modes inside numerical regularization

Small eigenvalues can be gauge modes, collective coordinates, Goldstone modes, or instabilities. Simply increasing a regulator to remove them can erase the physics.

### Reporting too many digits

If the total uncertainty is $0.03$, the number $1.284739$ is performance art. Quote $1.28(3)$ or an equivalently honest form.

## Exercises

### Exercise 1: Richardson extrapolation

Suppose

$$
Q_h=Q+ch^2+O(h^3).
$$

Show that

$$
Q\approx Q_{h/2}+\frac{Q_{h/2}-Q_h}{3}
$$

up to higher-order corrections.

<details><summary><strong>Solution</strong></summary>

Using the leading error model,

$$
Q_h=Q+ch^2,
\qquad
Q_{h/2}=Q+c\frac{h^2}{4}.
$$

Then

$$
Q_{h/2}-Q_h
= -\frac34 ch^2.
$$

Therefore

$$
\frac{Q_{h/2}-Q_h}{3}=-\frac14 ch^2.
$$

Add this to $Q_{h/2}$:

$$
Q_{h/2}+\frac{Q_{h/2}-Q_h}{3}
=Q+\frac14 ch^2-\frac14 ch^2=Q.
$$

The equality is exact for the pure $ch^2$ model and receives corrections from omitted higher powers of $h$.

</details>

### Exercise 2: Residual and condition number

Let $Ax=b$ and $A\widehat x=b-r$. Show that

$$
\frac{\|x-\widehat x\|}{\|x\|}
\le
\kappa(A)\frac{\|r\|}{\|b\|}
$$

for an invertible matrix $A$, using a consistent matrix norm.

<details><summary><strong>Solution</strong></summary>

Since

$$
Ax=b,
\qquad
A\widehat x=b-r,
$$

we have

$$
A(x-\widehat x)=r.
$$

Thus

$$
\|x-\widehat x\|
\le \|A^{-1}\|\,\|r\|.
$$

Also

$$
\|b\|=\|Ax\|\le \|A\|\,\|x\|,
$$

so

$$
\frac1{\|x\|}\le \frac{\|A\|}{\|b\|}.
$$

Multiplying gives

$$
\frac{\|x-\widehat x\|}{\|x\|}
\le
\|A^{-1}\|\|r\|\frac{\|A\|}{\|b\|}
=
\kappa(A)\frac{\|r\|}{\|b\|}.
$$

</details>

### Exercise 3: Autocorrelation and effective samples

A Markov-chain observable has integrated autocorrelation time $\tau_{\mathrm{int}}=20$. You collect $M=10^5$ samples. Estimate the effective number of independent samples.

<details><summary><strong>Solution</strong></summary>

The effective sample size is approximately

$$
M_{\mathrm{eff}}
\approx \frac{M}{2\tau_{\mathrm{int}}}.
$$

Substituting the numbers,

$$
M_{\mathrm{eff}}
\approx \frac{10^5}{40}=2500.
$$

So the chain has the statistical power of only about $2500$ independent samples for this observable.

</details>

### Exercise 4: Bias–variance decomposition

Show that

$$
\mathbb E[(\widehat Q-Q)^2]
=
\operatorname{Var}(\widehat Q)+\operatorname{Bias}(\widehat Q)^2.
$$

<details><summary><strong>Solution</strong></summary>

Let

$$
\mu=\mathbb E[\widehat Q].
$$

Then

$$
\widehat Q-Q=(\widehat Q-\mu)+(\mu-Q).
$$

Squaring and taking expectation,

$$
\mathbb E[(\widehat Q-Q)^2]
=
\mathbb E[(\widehat Q-\mu)^2]
+2(\mu-Q)\mathbb E[\widehat Q-\mu]
+(\mu-Q)^2.
$$

The middle term vanishes because $\mathbb E[\widehat Q-\mu]=0$. Therefore

$$
\mathbb E[(\widehat Q-Q)^2]
=
\operatorname{Var}(\widehat Q)+\operatorname{Bias}(\widehat Q)^2.
$$

</details>

## References

- Higham, *Accuracy and Stability of Numerical Algorithms*.
- Trefethen and Bau, *Numerical Linear Algebra*.
- Quarteroni, Sacco, and Saleri, *Numerical Mathematics*.
- Deuflhard, *Newton Methods for Nonlinear Problems*.
- Gander, Gander, and Kwok, *Scientific Computing*.
- Newman and Barkema, *Monte Carlo Methods in Statistical Physics*.
- Sokal, “Monte Carlo Methods in Statistical Mechanics: Foundations and New Algorithms.”
- Gattringer and Lang, *Quantum Chromodynamics on the Lattice*.
- Rothe, *Lattice Gauge Theories: An Introduction*.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.

## Version history

- **2026-06-27:** First polished draft. Introduces error decomposition, residuals, conditioning, stability, discretization, finite-volume effects, Monte Carlo uncertainty, autocorrelation, fits, continuum extrapolation, and validation checks.
