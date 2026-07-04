---
title: "Derivative Truncations"
description: "How numerical bootstrap computations replace infinite crossing equations by finite derivative systems at the crossing-symmetric point, and how to interpret the cutoff."
sidebar:
  label: "Derivative Truncations"
  order: 4
level: Graduate
status: "Polished draft"
source: "Poland, Rychkov, and Vichi 2019; Simmons-Duffin TASI lectures; SDPB and numerical bootstrap implementation literature."
topics:
  - derivative truncations
  - numerical conformal bootstrap
  - conformal blocks
  - crossing symmetry
  - cutoff convergence
canonicalTopics:
  - derivative-truncations
  - bootstrap-derivative-basis
  - numerical-bootstrap-cutoffs
researchStatus:
  established:
    - "Finite derivative truncations at the crossing-symmetric point are the standard way to approximate crossing equations in many numerical bootstrap computations."
  active:
    - "Current work improves derivative bases, radial-coordinate expansions, conformal block approximations, large-spin treatment, rigorous certification, and alternatives such as navigator and cutting-surface workflows."
---

## Summary

A **derivative truncation** turns the infinite crossing equation into a finite numerical problem. Crossing is originally an equality of functions, for example

$$
F_{\mathbf1}(z,\bar z)+
\sum_{\mathcal O\ne\mathbf1}\lambda_{\mathcal O}^2
F_{\Delta,\ell}(z,\bar z)=0.
$$

If this function vanishes identically, then all its derivatives vanish at the crossing-symmetric point

$$
z=\bar z=\frac12.
$$

A numerical bootstrap computation keeps only finitely many derivatives:

$$
\partial_z^m\partial_{\bar z}^nF(z,
\bar z)\bigg|_{z=\bar z=1/2},
\qquad
(m,n)\in\mathcal D_\Lambda.
$$

The finite set $\mathcal D_\Lambda$ is the derivative truncation, often labeled by a cutoff $\Lambda$. Each conformal block contribution becomes a finite vector

$$
\vec F_{\Delta,\ell}^{(\Lambda)}.
$$

The truncated crossing equation is

$$
\vec F_{\mathbf1}^{(\Lambda)}+\sum_{\mathcal O\ne\mathbf1}
\lambda_{\mathcal O}^2\vec F_{\Delta,\ell}^{(\Lambda)}=0.
$$

Increasing $\Lambda$ gives a stronger approximation to the full crossing equation. Bounds should therefore be studied as functions of $\Lambda$, not treated as exact after one run.

## Prerequisites

Read [Crossing as a Vector Equation](/cft-bootstrap/numerical-bootstrap/crossing-as-a-vector-equation/) and [Linear Functionals](/cft-bootstrap/numerical-bootstrap/linear-functionals/) first.

You should know that a linear functional in the simplest numerical bootstrap is a finite linear combination of derivatives at the crossing-symmetric point:

$$
\alpha(F)=\sum_{(m,n)\in\mathcal D_\Lambda}a_{m,n}
\partial_z^m\partial_{\bar z}^nF(z,\bar z)\bigg|_{z=\bar z=1/2}.
$$

## Core idea

The full crossing equation contains infinitely much information. It is an equality of analytic functions in a domain of cross-ratio space. The numerical bootstrap samples this information through a finite Taylor expansion around a symmetric point.

The conceptual chain is

$$
\text{function crossing}
\quad\Longrightarrow\quad
\text{all Taylor coefficients vanish}
\quad\Longrightarrow\quad
\text{finite derivative subset used numerically}.
$$

A larger derivative set gives the functional more ways to separate inconsistent spectra from the crossing cone. Therefore increasing the derivative cutoff usually makes bounds stronger or more stable.

The slogan is

$$
\Lambda\text{ is not a physical cutoff; it is a numerical search-space cutoff.}
$$

It controls how many crossing constraints the computation uses. It is not a UV regulator of the CFT, and it is not a truncation of the operator spectrum by itself.

## Setup and conventions

For identical scalar external operators, use cross-ratios

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

The crossing-symmetric point is

$$
z=\bar z=\frac12,
\qquad
u=v=\frac14.
$$

A crossing function is

$$
F_{\Delta,\ell}(z,\bar z)
=v^{\Delta_\phi}G_{\Delta,\ell}(z,
\bar z)
-u^{\Delta_\phi}G_{\Delta,\ell}(1-z,1-\bar z),
$$

where the second term implements $u\leftrightarrow v$ in the chosen variables. Equivalent conventions are common.

Choose a finite derivative set

$$
\mathcal D_\Lambda=\{(m,n):m,n\ge0,\text{ chosen by cutoff and crossing parity}\}.
$$

The truncated block vector is

$$
\vec F_{\Delta,\ell}^{(\Lambda)}
=\left(
\partial_z^m\partial_{\bar z}^nF_{\Delta,\ell}(z,\bar z)
\bigg|_{z=\bar z=1/2}
\right)_{(m,n)\in\mathcal D_\Lambda}.
$$

The number of components is

$$
K_\Lambda=|\mathcal D_\Lambda|.
$$

This $K_\Lambda$ is the dimension of the finite vector space in which linear functionals live.

## Why derivatives at one point can work

A natural question is why derivatives at a single point know so much. The reason is analyticity. In a suitable Euclidean domain, conformal block expansions are analytic functions of the cross-ratios away from singular configurations. If an analytic function vanishes in a neighborhood, its Taylor coefficients at an interior point vanish.

The full infinite list of derivatives at the symmetric point is therefore equivalent, morally, to the function equation near that point. The finite numerical bootstrap keeps only a finite part of this infinite list.

This does not mean that a finite derivative truncation is exact. It means it is a systematic projection of crossing onto a finite-dimensional space.

The practical hope is that low and moderate derivatives already capture enough information to produce useful bounds. Experience shows that they often do, especially in unitary scalar and mixed-correlator systems.

## Choice of variables

Different variables can be used for the Taylor expansion. Common choices include:

| Variables | Use |
|---|---|
| $z,\bar z$ | Directly related to cross-ratios and conformal blocks. |
| $a,b$ around $z=\bar z=1/2$ | Useful for crossing parity and real derivative bases. |
| radial variables $r,\eta$ or $\rho,\bar\rho$ | Useful for convergence and block expansions. |

A typical real parametrization near the symmetric point is

$$
z=\frac12+a+b,
\qquad
\bar z=\frac12+a-b.
$$

The crossing exchange $z\to1-z$, $\bar z\to1-\bar z$ sends

$$
a\to -a,
\qquad
b\to -b
$$

or a related parity action depending on the exact coordinates. One then keeps derivative combinations with the parity appropriate to the crossing equation.

The variable choice affects numerical conditioning and implementation details. It does not change the underlying crossing equation.

## Crossing parity and independent derivatives

For identical scalars, the crossing function is antisymmetric under channel exchange:

$$
F(v,u)=-F(u,v).
$$

At the crossing-symmetric point, many derivatives are automatically zero or redundant because of this antisymmetry. A well-chosen derivative basis keeps only independent derivatives.

Schematically, if a coordinate $a$ changes sign under crossing while another coordinate is invariant, an antisymmetric crossing function has only odd powers of $a$ in its Taylor expansion:

$$
F(a,b)=aF_1(b)+a^3F_3(b)+\cdots .
$$

Then derivatives with the wrong parity vanish at the symmetric point and need not be included.

In practice, bootstrap codes choose derivative sets adapted to these parity rules. This improves efficiency and avoids wasting vector components on identically zero constraints.

## The cutoff Λ

The symbol $\Lambda$ is commonly used for the derivative cutoff. Its precise definition varies by code and paper. A simple version is

$$
\mathcal D_\Lambda=\{(m,n):m+n\le\Lambda,\text{ correct parity}\}.
$$

Other conventions use a maximum order in one coordinate, weighted derivative counts, or derivative sets tuned to the variables used.

Therefore, when comparing computations, always ask:

| Question | Why it matters |
|---|---|
| What derivative set defines $\Lambda$? | Different papers may use different counts. |
| Are only parity-allowed derivatives kept? | Affects vector dimension. |
| What conformal block normalization is used? | Affects numerical values and conditioning. |
| Are spins truncated or treated asymptotically? | Affects positivity constraints. |
| What precision and solver tolerances are used? | Affects reliability. |

The cutoff $\Lambda$ is a label for a finite search space, not a universal physical quantity.

## Increasing Λ

Suppose a functional exists at cutoff $\Lambda$. If the derivative set at cutoff $\Lambda'$ contains all derivatives used at cutoff $\Lambda$, with $\Lambda'>\Lambda$, then the same functional can be embedded into the larger space by setting the new coefficients to zero.

Thus a larger derivative space can reproduce all exclusions found at smaller cutoff and may find stronger exclusions. In this nested setup, bounds are expected to improve monotonically or at least not weaken in exact arithmetic.

In practice, small nonmonotonicities can appear because of numerical precision, different approximations, or changes in spin treatment. Still, convergence with increasing $\Lambda$ is one of the central reliability checks.

A typical bootstrap plot should be read as a sequence:

$$
\Lambda=11,\quad 19,\quad 27,\quad 35,\quad\ldots
$$

not as a single final curve without context.

## Derivative truncation versus spectrum truncation

A derivative truncation is not the same as a spectrum truncation.

Derivative truncation keeps finitely many crossing constraints:

$$
\text{finite number of equations or functional components.}
$$

The operator spectrum remains infinite in principle. Positivity constraints are still imposed for all allowed operator dimensions and spins, up to whatever spin-handling method the computation uses.

A spectrum truncation would instead keep only finitely many operators and try to solve crossing approximately. That is a different method, sometimes useful, but logically distinct from the rigorous exclusion approach.

The difference is crucial:

$$
\text{derivative-truncated bootstrap can still exclude infinite spectral families.}
$$

It does this because a single functional positivity condition can hold for a continuum of dimensions and infinitely many spins.

## Spin treatment

Even after choosing a derivative basis, the crossing equation includes infinitely many spins. For identical scalar external operators, these are even spins:

$$
\ell=0,2,4,\ldots .
$$

In a numerical implementation, one must handle spin carefully. Common strategies include:

1. include low spins explicitly;
2. impose positivity for a finite list of spins up to $\ell_{\max}$;
3. use analytic or numerical arguments to control spins above $\ell_{\max}$;
4. choose conformal block approximations that make large-spin positivity tractable.

A derivative cutoff alone does not specify the spin treatment. Two computations with the same $\Lambda$ can differ if their spin ranges or large-spin methods differ.

For scalar bootstrap in common dimensions, high-spin behavior is well understood enough to make robust computations possible. For spinning and mixed systems, spin management can become a major technical part of the calculation.

## Rational approximations to blocks

To enforce positivity for continuous $\Delta$, modern bootstrap codes often approximate derivatives of conformal blocks by rational functions of $\Delta$:

$$
\partial^kG_{\Delta,\ell}\big|_{\rm sym}
\approx
\chi_{\ell}(\Delta)
\frac{P_{k,\ell}(\Delta)}{Q_{\ell}(\Delta)},
$$

where $P_{k,\ell}$ and $Q_{\ell}$ are polynomials and $\chi_\ell$ is a positive prefactor in the relevant range.

After multiplying by a positive denominator, functional positivity becomes a polynomial positivity condition:

$$
P(\Delta)\ge0
\qquad
\Delta\ge\Delta_{\rm min}(\ell).
$$

Polynomial positivity on a half-line can be represented by sums of squares and encoded as semidefinite constraints.

This is one reason derivative truncations and SDPB-style semidefinite programming fit together so well.

## Conditioning and normalization

Higher derivatives can become numerically large or small. Blocks for different spins and dimensions can vary across many orders of magnitude. Poor normalization can make the optimization problem ill-conditioned.

Practical computations therefore rescale vectors, choose stable coordinates, use high-precision arithmetic, and normalize functionals carefully. These choices do not change the mathematical crossing equation, but they can determine whether the numerical solver succeeds.

Common symptoms of conditioning problems include:

- solver failure at high precision;
- unstable bounds as $\Lambda$ changes;
- apparent violations of expected monotonicity;
- sensitivity to small changes in block approximation;
- spurious zeros in extremal functional spectra.

Good numerical bootstrap practice treats conditioning as part of the physics pipeline, not as a mere software annoyance.

## Mixed correlators

In mixed-correlator systems, derivative truncations apply to each crossing equation and tensor structure. Instead of one scalar crossing function, one has a vector or matrix of crossing functions.

For example, in an Ising-like mixed system with $\sigma$ and $\epsilon$, one studies several correlators:

$$
\langle\sigma\sigma\sigma\sigma\rangle,
\qquad
\langle\sigma\sigma\epsilon\epsilon\rangle,
\qquad
\langle\epsilon\epsilon\epsilon\epsilon\rangle.
$$

Each equation is differentiated at the symmetric point. The resulting derivative components are assembled into a larger vector or matrix-valued object.

The cutoff $\Lambda$ now controls a larger finite-dimensional space, and the number of components grows quickly. This is one reason mixed-correlator computations are expensive. It is also why they are powerful: many more crossing constraints are being imposed simultaneously.

## Derivative truncations and islands

Islands become smaller as derivative information improves and assumptions sharpen. At low $\Lambda$, an allowed region may be broad or absent. At higher $\Lambda$, the same assumptions may produce a small island.

This behavior should be interpreted carefully.

If an island shrinks stably as $\Lambda$ increases, that is strong evidence that the computation is isolating a real solution or small family of solutions under the assumptions. If an island moves erratically or disappears, the assumptions, numerical precision, or interpretation need rechecking.

A responsible island result usually shows:

$$
\text{island at several }\Lambda\text{ values}
$$

and explains the imposed gaps and numerical settings.

The derivative cutoff is therefore part of the statement of the result, just like the spacetime dimension and global symmetry are.

## Truncation and rigor

A finite derivative truncation can produce rigorous-looking exclusion certificates for the finite problem, especially when rational arithmetic or certified positivity is used. But the relationship to the full CFT crossing problem still involves a limiting procedure.

There are two distinct questions:

1. **Finite problem:** Did the solver correctly find a functional satisfying the finite set of constraints?
2. **Full crossing problem:** What happens as $\Lambda\to\infty$, spin treatment is completed, and block approximations are controlled?

Both matter. A high-quality numerical bootstrap result is clear about which level is being claimed.

In practice, the field often relies on convergence, independent implementations, precision tests, and agreement with other methods. For many benchmark problems, this evidence is extremely strong. But the logical distinction should remain visible.

## Choosing a derivative basis in practice

A good derivative basis should balance several goals:

| Goal | Reason |
|---|---|
| capture strong crossing constraints | Improves bounds. |
| respect crossing parity | Avoids redundant zero components. |
| be numerically well conditioned | Helps solver stability. |
| interface with block approximations | Enables continuous positivity constraints. |
| scale reasonably with mixed systems | Keeps computations feasible. |

There is no single universally best basis. The best choice depends on dimension, external spins, global symmetry, desired precision, and available software.

For learners, the safest first picture is derivatives at $z=\bar z=1/2$ up to total order $\Lambda$. Later pages can refine this into the actual bases used by SDPB workflows.

## Common pitfalls

**Do not treat $\Lambda$ as a physical UV cutoff.** It is a numerical derivative cutoff, not a regulator of the CFT.

**Do not confuse derivative truncation with spectrum truncation.** The former keeps finitely many crossing constraints; the latter keeps finitely many operators.

**Do not compare $\Lambda$ across papers blindly.** Different derivative bases and parity conventions can give different vector dimensions for the same symbol.

**Do not trust a one-cutoff feature without convergence checks.** Kinks, islands, and extracted spectra should be tested as $\Lambda$ increases.

**Do not ignore spin treatment.** Derivative cutoff and spin cutoff are separate implementation choices.

**Do not include redundant parity-forbidden derivatives.** They waste resources and can worsen conditioning.

**Do not forget block approximation error.** The finite derivative vector must be computed accurately enough for the optimization result to mean what it claims.

## Relations to other pages

This page follows [Linear Functionals](/cft-bootstrap/numerical-bootstrap/linear-functionals/) by explaining the finite-dimensional space in which those functionals live.

The next pages [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/) and [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/) explain how positivity over continuous dimensions is converted into an optimization problem and solved in practice.

It also connects to [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), [Radial Coordinates](/cft-bootstrap/conformal-blocks/radial-coordinates/), and [Conformal Blocks in Higher Dimensions](/cft-bootstrap/conformal-blocks/conformal-blocks-in-higher-dimensions/) because block evaluation controls the quality and efficiency of derivative vectors.

## Research status

Derivative truncations are established and standard in numerical bootstrap. They are one of the main bridges from exact crossing equations to finite optimization problems.

Active work improves derivative bases, block-generation algorithms, large-spin control, rational approximations, rigorous certificates, high-precision conditioning, and alternatives or complements to pure derivative truncation such as navigator functions, cutting-surface methods, and hybrid analytic-numerical approaches.

## Exercises

### Exercise 1

Explain why exact crossing implies that all derivatives of the crossing function vanish at the crossing-symmetric point.

<details><summary><strong>Solution</strong></summary>

If exact crossing holds, then the crossing function is identically zero in a domain:

$$
F(z,\bar z)=0.
$$

An identically zero analytic function has all Taylor coefficients equal to zero at any interior point of its domain. Therefore

$$
\partial_z^m\partial_{\bar z}^nF(z,\bar z)\bigg|_{z=\bar z=1/2}=0
$$

for all nonnegative integers $m,n$.

</details>

### Exercise 2

Why is a derivative truncation not the same as truncating the operator spectrum?

<details><summary><strong>Solution</strong></summary>

A derivative truncation keeps only finitely many derivative constraints from crossing. The sum over operators remains infinite in principle, and positivity constraints can still be imposed for a continuum of dimensions and infinitely many spins.

A spectrum truncation instead keeps only finitely many exchanged operators and attempts to solve crossing approximately. These are different approximations. The standard exclusion bootstrap usually truncates derivatives, not the spectrum.

</details>

### Exercise 3

Suppose $\mathcal D_\Lambda$ contains all derivative pairs $(m,n)$ with $m+n\le\Lambda$ and $m+n$ odd. How many such pairs are there for $\Lambda=3$?

<details><summary><strong>Solution</strong></summary>

List nonnegative pairs with odd total degree at most $3$.

For total degree $1$:

$$
(1,0),\quad(0,1).
$$

For total degree $3$:

$$
(3,0),\quad(2,1),\quad(1,2),\quad(0,3).
$$

There are therefore

$$
2+4=6
$$

pairs.

</details>

### Exercise 4

Why can increasing $\Lambda$ strengthen a bootstrap bound?

<details><summary><strong>Solution</strong></summary>

Increasing $\Lambda$ enlarges the space of linear functionals. A larger space contains the old functionals, plus new ones involving higher derivatives. Since exclusions are proved by finding functionals with certain positivity properties, a larger search space can find stronger exclusions. Therefore bounds often improve or stabilize as $\Lambda$ increases.

</details>

### Exercise 5

Why is continuous positivity in $\Delta$ harder than checking a finite list of dimensions?

<details><summary><strong>Solution</strong></summary>

The allowed spectrum condition usually says that an operator of spin $\ell$ may have any dimension in a continuous range:

$$
\Delta\ge\Delta_{\rm min}(\ell).
$$

A functional must satisfy

$$
\alpha(\vec F_{\Delta,\ell})\ge0
$$

for every $\Delta$ in that range, not just for a sample of values. This is infinitely many inequalities. Practical implementations use rational approximations and polynomial positivity methods, often encoded as semidefinite constraints, to enforce positivity on the whole interval.

</details>

## References

- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2016.
- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.
- M. Hogervorst and S. Rychkov, “Radial coordinates for conformal blocks,” *Physical Review D* **87** (2013).
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Bootstrapping mixed correlators in the 3D Ising model,” *Journal of High Energy Physics* **2014**.
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.

## Version history

- 2026-07-01: First polished draft. Added derivative-basis construction, symmetric-point expansion, cutoff interpretation, crossing parity, spin treatment, block approximations, convergence caveats, mixed-correlator comments, exercises, and references.
