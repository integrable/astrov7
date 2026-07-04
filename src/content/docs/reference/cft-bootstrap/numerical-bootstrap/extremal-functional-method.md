---
title: "Extremal Functional Method"
description: "How optimal bootstrap functionals at the boundary of allowed regions can be used to estimate operator spectra and OPE coefficients."
sidebar:
  label: "Extremal Functional Method"
  order: 10
level: Graduate
status: "Polished draft"
source: "El-Showk and Paulos; Poland, Rychkov, and Vichi 2019; Simmons-Duffin TASI lectures; numerical bootstrap spectrum-extraction literature."
topics:
  - extremal functional method
  - spectrum extraction
  - numerical conformal bootstrap
  - bootstrap bounds
  - OPE coefficients
canonicalTopics:
  - extremal-functional-method
  - spectrum-extraction
  - bootstrap-boundary-spectra
researchStatus:
  established:
    - "Extremal functionals at optimal bootstrap boundaries often encode approximate spectra and OPE coefficients of the corresponding extremal crossing solution."
  active:
    - "Current work refines spectrum extraction in mixed systems, islands, degenerate spectra, finite-cutoff extrapolation, navigator workflows, and rigorous reliability estimates."
---

## Summary

The **extremal functional method** extracts approximate CFT data from a bootstrap bound. At an optimal boundary, the excluding functional is just barely positive on the allowed spectrum. Its zeros often occur at the dimensions of operators in the extremal solution.

For a one-correlator scalar bootstrap, suppose crossing is

$$
\vec F_{\mathbf1}+\sum_i p_i\vec F_i=0,
\qquad
p_i=\lambda_i^2\ge0.
$$

An excluding functional satisfies

$$
\alpha(\vec F_{\mathbf1})>0,
\qquad
\alpha(\vec F_i)\ge0.
$$

At an optimal boundary, the solution must use operators whose contributions are not strictly positive under $\alpha$. Therefore many operators in the extremal spectrum satisfy

$$
\alpha(\vec F_{\Delta_i,\ell_i})=0.
$$

These zeros are the first hint of the spectrum. After locating them, one solves the truncated crossing equations to estimate OPE coefficients.

The method is powerful because it turns a bound into spectroscopy. It is delicate because it relies on finite-cutoff data, numerical zeros, assumptions, and the hypothesis that the boundary solution approximates a real CFT.

## Prerequisites

Read [Linear Functionals](/cft-bootstrap/numerical-bootstrap/linear-functionals/), [Identical Scalar Bounds](/cft-bootstrap/numerical-bootstrap/identical-scalar-bounds/), [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/), and [Mixed-Correlator Systems](/cft-bootstrap/numerical-bootstrap/mixed-correlator-systems/) first.

You should know the cone picture of crossing, the meaning of a boundary of an allowed region, and why a functional excluding a proposed spectrum must be nonnegative on allowed conformal block vectors.

## Core idea

A functional that proves exclusion is a separating hyperplane. At a boundary, the hyperplane touches the allowed cone. The block vectors where it touches are candidates for operators in an extremal crossing solution.

Geometrically:

$$
\text{boundary point}
\quad\Longrightarrow\quad
\text{supporting hyperplane}
\quad\Longrightarrow\quad
\text{contact points with the cone}.
$$

Physically, the contact points are operator dimensions and spins.

The slogan is

$$
\text{zeros of the extremal functional reveal the extremal spectrum}.
$$

This turns the bootstrap from a tool for ruling things out into a tool for estimating CFT data. It is one of the reasons numerical bootstrap became a precision method rather than only an exclusion machine.

## Setup and conventions

Consider an identical scalar four-point function. The truncated crossing equation is

$$
\vec F_{\mathbf1}+\sum_{\mathcal O\ne\mathbf1}
\lambda_{\mathcal O}^2\vec F_{\Delta,\ell}=0.
$$

Suppose a bound is optimized at fixed external dimension $\Delta_\phi$. The optimal functional $\alpha_*$ is normalized, for example, by

$$
\alpha_*(\vec F_{\mathbf1})=1.
$$

It satisfies positivity conditions on the assumed allowed spectrum. At the optimal boundary, one expects an extremal solution of the form

$$
\vec F_{\mathbf1}+\sum_{a=1}^{K}p_a\vec F_{\Delta_a,\ell_a}=0,
\qquad
p_a>0,
$$

using a finite or effectively finite set of operators at the chosen cutoff.

Applying $\alpha_*$ gives

$$
0=1+\sum_a p_a\alpha_*(\vec F_{\Delta_a,\ell_a}).
$$

Since $p_a>0$ and the non-identity terms are nonnegative, the only way to cancel the positive identity term in the boundary convention is that the sign convention or normalization places the identity on the other side, or equivalently that the operators in the extremal solution sit at saturation of the relevant positivity inequalities. In the common zero-finding convention, one searches for

$$
\alpha_*(\vec F_{\Delta_a,\ell_a})=0
$$

in each spin sector after using a consistent sign convention.

Sign conventions vary across papers. The invariant statement is that extremal operators lie where the functional's positivity inequality is saturated.

## Boundary versus interior

The extremal functional method works at boundaries of allowed regions, not deep in the interior.

Inside an allowed region, there is no unique supporting hyperplane. Many spectra may be compatible with the truncated crossing equations. A functional optimized for exclusion does not have a reason to touch the physical spectrum.

At a boundary, an optimal functional just fails to exclude the point. The boundary solution is extremal: it uses just enough operators to satisfy the finite set of crossing constraints. This is why the functional's zeros become informative.

For an isolated island, one can apply related ideas near the island boundary or use more refined methods to extract spectra at points inside the island. But the cleanest picture is still boundary extraction.

The practical rule is:

$$
\text{use extremal functionals where the bootstrap problem is nearly saturated}.
$$

## Locating zeros

At fixed spin $\ell$, evaluate the functional on the block vector as a function of dimension:

$$
f_\ell(\Delta)=\alpha_*(\vec F_{\Delta,\ell}).
$$

The allowed region begins at the unitarity bound or at an assumed gap:

$$
\Delta\ge\Delta_{\min}(\ell).
$$

Zeros of

$$
f_\ell(\Delta)
$$

inside the allowed range are candidate operator dimensions. In a typical plot, $f_\ell(\Delta)$ is nonnegative and touches zero at isolated points.

A simple scalar example might yield zeros at

$$
\Delta_{0,0},\quad \Delta_{1,0},\quad\Delta_{0,2},\quad\Delta_{0,4},\ldots .
$$

These are interpreted as scalar, spin-two, spin-four, and higher-spin operators in the extremal spectrum.

In practice, one uses numerical root finding, checks stability with cutoff, and compares zeros across spin sectors. Not every tiny numerical dip is a physical operator. Some are gremlins wearing eigenvalue costumes.

## OPE coefficient extraction

After candidate dimensions and spins are identified, the OPE coefficients can be estimated by solving the truncated crossing equation:

$$
\vec F_{\mathbf1}+\sum_a p_a\vec F_{\Delta_a,\ell_a}=0.
$$

Here

$$
p_a=\lambda_a^2
$$

for an identical-scalar setup.

Since only finitely many derivative components are kept, one obtains a finite linear system. The number of operators included is chosen so that the system is not wildly underdetermined. In practice, one may solve a least-squares problem or use a subset of derivatives and check consistency with the rest.

The extracted coefficients should satisfy

$$
p_a\ge0.
$$

Negative or unstable coefficients are warning signs: the candidate zero may be spurious, the truncation may be too low, the operator list may be incomplete, or the point may not correspond to a clean extremal solution.

OPE extraction is more fragile than dimension extraction. Dimensions come from zeros; coefficients come from solving a numerically sensitive linear system.

## Why zeros appear

Suppose the extremal solution includes an operator with coefficient $p_a>0$. The crossing equation at the boundary is saturated by the optimal functional. If

$$
\alpha_*(\vec F_a)>0,
$$

then that operator contributes strictly in the positive direction after applying the functional. It cannot participate in a saturated cancellation. Therefore it must lie where the positivity inequality is saturated:

$$
\alpha_*(\vec F_a)=0.
$$

This is complementary slackness in convex optimization language. Variables that are active in the primal solution correspond to saturated constraints in the dual solution.

The bootstrap version is:

| Primal object | Dual signal |
|---|---|
| operator appears with positive OPE coefficient | functional has a zero at its dimension |
| operator absent | functional may be strictly positive there |
| degenerate active operators | multiple coefficients share one zero or matrix kernel |
| mixed OPE vector active | block matrix has a null vector |

This primal-dual relation is the mathematical backbone of the method.

## Example: scalar gap bound

Consider the bound on the first scalar dimension in $\phi\times\phi$. At the optimal gap, the extremal spectrum usually contains a scalar exactly at the gap:

$$
\Delta_{S,0}^{\rm first}=\Delta_{\rm gap}^{\rm opt}.
$$

The extremal functional has a zero at that scalar dimension:

$$
f_0(\Delta_{\rm gap}^{\rm opt})=0.
$$

It may also have zeros at higher scalar dimensions and at spin-two, spin-four, and higher-spin dimensions. The resulting list approximates the spectrum of the extremal solution saturating the bound.

Near a kink, the extracted extremal spectrum can resemble a known CFT. For the 3D Ising kink, early extremal functional studies found spectra consistent with an interacting Ising-like CFT. Later mixed-correlator islands made the identification much sharper.

The moral is:

$$
\text{a bound gives a curve; an extremal functional gives a candidate spectrum on the curve}.
$$

## Mixed-correlator extremality

In mixed systems, positivity is matrix-valued. For an exchanged operator, the functional produces a matrix

$$
M_{\Delta,\ell}(\alpha_*)\succeq0.
$$

An active operator appears when this matrix has a null direction:

$$
M_{\Delta_i,\ell_i}(\alpha_*)\,\lambda_i=0,
$$

where $\lambda_i$ is the vector of OPE coefficients to the external operator pairs.

Thus the zero condition becomes a determinant or kernel condition:

$$
\det M_{\Delta_i,\ell_i}(\alpha_*)=0
$$

in simple cases, together with the extraction of the null vector. The null vector estimates ratios such as

$$
\frac{\lambda_{\epsilon\epsilon\mathcal O}}{\lambda_{\sigma\sigma\mathcal O}}.
$$

This is one reason mixed correlators are rich: the extremal functional can reveal not only dimensions but also OPE-vector directions.

The cost is that degeneracies, matrix kernels, and numerical conditioning become more subtle than in one-correlator scalar bootstrap.

## Degeneracies and multiple operators

If two or more operators have the same spin and nearly the same dimension, the extremal functional may show one zero where several operators are hiding. This is common in theories with global symmetry, large-$N$ double-trace spectra, or accidental degeneracies.

A single zero can correspond to:

- one operator;
- several degenerate operators;
- a mixture of operators in the same quantum-number sector;
- a finite-cutoff approximation to a cluster of nearby dimensions.

OPE coefficient extraction may reveal the problem if one coefficient seems too large, unstable, or inconsistent across derivative subsets.

In mixed systems, degeneracy is even subtler because the null space of a positive semidefinite matrix can have dimension greater than one. Then one must reconstruct a subspace of OPE vectors rather than a single vector.

The safe statement is:

$$
\text{extremal zeros identify active spectral locations, not always individual operators one by one.}
$$

## Cutoff dependence

At finite derivative cutoff $\Lambda$, the extremal spectrum is an approximation. As $\Lambda$ increases, good spectral estimates should stabilize:

$$
\Delta_i^{(\Lambda)}\to\Delta_i.
$$

In practice, convergence can be uneven. Low-lying operators often converge faster than high-dimension operators. Operators near imposed gaps may be stable by construction. Weakly coupled or nearly degenerate operators may converge slowly.

A responsible extraction reports:

| Check | Purpose |
|---|---|
| several $\Lambda$ values | test convergence |
| several derivative subsets | test linear-system stability |
| positivity of OPE coefficients | check unitarity consistency |
| Ward identities | check stress-tensor and current normalization |
| comparison with other methods | validate interpretation |
| sensitivity to gap assumptions | identify assumption-driven data |

An extremal spectrum without cutoff checks is a sketch, not a measurement.

## Relation to truncation methods

The extremal functional method should not be confused with arbitrary spectrum truncation. It does produce a finite list of operators at finite cutoff, but that list is inferred from a functional optimizing a rigorous-looking exclusion problem.

A naive truncation method might assume a finite set of operators and solve crossing approximately. The extremal method instead starts from a bound, finds the supporting functional, and reads off which operators are active in the extremal solution.

The two approaches can interact. Extremal spectra can suggest good truncation ansätze. Truncation methods can refine or test extracted data. But their logic is different:

$$
\text{extremal method}:\quad \text{functional first, spectrum second}.
$$

$$
\text{truncation method}:\quad \text{spectrum ansatz first, crossing fit second}.
$$

## When the method works best

The method is most reliable when:

1. the point is on a sharp, stable boundary;
2. the functional is well conditioned;
3. the relevant zeros are isolated;
4. the low-lying spectrum is sparse;
5. the same data appear across increasing cutoffs;
6. gap assumptions are physically motivated;
7. mixed-correlator data support the same interpretation.

It is less reliable when:

1. the allowed region is broad;
2. the point lies deep in the interior;
3. many operators are nearly degenerate;
4. the functional has noisy near-zeros;
5. the theory has dense spectra or large operator mixing;
6. the solver precision is marginal;
7. the imposed gaps force an artificial extremal solution.

The method is a microscope. It still needs focus, calibration, and someone not bumping the table.

## Common pitfalls

**Do not treat every zero as a physical operator.** Numerical artifacts, accidental zeros, and finite-cutoff effects exist.

**Do not use the method deep inside an allowed region without extra structure.** Extremal functionals are boundary tools.

**Do not ignore degeneracies.** One zero may represent multiple operators or a mixed subspace.

**Do not trust OPE coefficients without stability checks.** Coefficient extraction is sensitive to the chosen operator list and derivative components.

**Do not forget sign conventions.** Different papers put the identity on different sides of crossing, so the positivity and zero conditions may look sign-flipped.

**Do not overinterpret high-dimension zeros.** Low-lying operators usually converge more reliably.

**Do not confuse extremal spectra with exact CFT spectra.** They are finite-cutoff estimates that require extrapolation and corroboration.

## Relations to other pages

This page follows [Mixed-Correlator Systems](/cft-bootstrap/numerical-bootstrap/mixed-correlator-systems/) and prepares [Navigator and Modern Search Algorithms](/cft-bootstrap/numerical-bootstrap/navigator-and-modern-search-algorithms/) and [Error Bars and Reliability](/cft-bootstrap/numerical-bootstrap/error-bars-and-reliability/).

It also connects to [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/) because extremal functionals explain why boundary features can carry spectral information.

For physics examples, see [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/) and [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/). For the optimization background, see [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/).

## Research status

The extremal functional method is established as a standard spectrum-extraction tool in numerical bootstrap. It has been used to interpret kinks, boundary spectra, and precision CFT data in benchmark models.

Active research concerns reliability and generalization: mixed-correlator spectra, degenerate operators, matrix-kernel extraction, interior points of islands, navigator-compatible extraction, rigorous error estimates, and hybrid methods combining extremal functionals with analytic bootstrap and truncation approaches.

## Exercises

### Exercise 1

Explain why an active operator in an extremal solution should sit at a zero of the extremal functional.

<details><summary><strong>Solution</strong></summary>

At the boundary, the extremal solution saturates the positivity constraints. If an operator appears with positive coefficient $p_i>0$ and the functional were strictly positive on its block vector, then after applying the functional to crossing it would contribute a strictly positive amount. In a saturated solution, active operators must instead lie where the positivity inequality is saturated:

$$
\alpha_*(\vec F_i)=0.
$$

This is the bootstrap version of complementary slackness.

</details>

### Exercise 2

Why is the extremal functional method more reliable on a boundary than in the interior of an allowed region?

<details><summary><strong>Solution</strong></summary>

At a boundary, there is a supporting functional that just touches the allowed cone. Its contact points carry spectral information. In the interior, there is no unique supporting hyperplane and no reason for an optimized exclusion functional to touch the physical spectrum. Many spectra may satisfy the truncated crossing equations there.

</details>

### Exercise 3

After locating candidate dimensions $\Delta_a$, how can one estimate OPE coefficients in an identical-scalar setup?

<details><summary><strong>Solution</strong></summary>

One substitutes the candidate operators into the truncated crossing equation:

$$
\vec F_{\mathbf1}+\sum_a p_a\vec F_{\Delta_a,\ell_a}=0.
$$

Then one solves the resulting finite linear system or least-squares problem for

$$
p_a=\lambda_a^2.
$$

The coefficients should be nonnegative and stable under changes of derivative subset and cutoff.

</details>

### Exercise 4

What replaces the scalar zero condition in a mixed-correlator system?

<details><summary><strong>Solution</strong></summary>

In a mixed system, applying the functional gives a positive semidefinite matrix

$$
M_{\Delta,\ell}(\alpha_*)\succeq0.
$$

An active operator appears when this matrix has a null direction corresponding to its OPE coefficient vector:

$$
M_{\Delta_i,\ell_i}(\alpha_*)\lambda_i=0.
$$

Thus one looks for matrix kernels or determinant zeros rather than zeros of a scalar function alone.

</details>

### Exercise 5

List three reasons an extremal-functional zero might not correspond to a trustworthy physical operator.

<details><summary><strong>Solution</strong></summary>

Possible reasons include finite-cutoff artifacts, insufficient numerical precision, accidental near-zeros, degenerate operators hiding at one zero, an incomplete operator list in coefficient extraction, unstable gap assumptions, and poor convergence with increasing $\Lambda$. Any three of these are enough.

</details>

## References

- S. El-Showk and M. F. Paulos, “Bootstrapping conformal field theories with the extremal functional method,” *Physical Review Letters* **111** (2013).
- S. El-Showk, M. F. Paulos, D. Poland, S. Rychkov, D. Simmons-Duffin, and A. Vichi, “Solving the 3D Ising Model with the Conformal Bootstrap II,” *Journal of Statistical Physics* **157** (2014).
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.

## Version history

- 2026-07-01: First polished draft. Added boundary-supporting-functional picture, zero-finding logic, OPE coefficient extraction, mixed-correlator matrix-kernel version, degeneracy and cutoff caveats, exercises, and references.
