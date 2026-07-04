---
title: "Recursion Relations for Conformal Blocks"
description: "Explains the Casimir and dimension-recursion methods used to compute conformal blocks accurately for conformal bootstrap applications."
sidebar:
  label: "Recursion Relations"
  order: 5
level: Graduate
status: "Polished draft"
source: "Dolan–Osborn 2001; Hogervorst–Rychkov 2013; Kos–Poland–Simmons-Duffin 2014; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019"
topics:
  - conformal block recursion
  - conformal blocks
  - Casimir equation
  - null descendants
  - rational approximation
  - numerical bootstrap
canonicalTopics:
  - recursion-relations
  - conformal-blocks
  - block-computation
  - radial-coordinates
  - numerical-bootstrap
researchStatus:
  established:
    - "Scalar conformal blocks can be computed efficiently using recursions from the Casimir equation, radial expansions, and meromorphic structure in the exchanged dimension."
    - "Recursion methods underlie many practical numerical bootstrap implementations because they turn conformal block derivatives into controlled finite computations."
  active:
    - "Modern bootstrap software continues to improve block generation for spinning systems, mixed correlators, defects, supersymmetry, and high-precision semidefinite programs."
---

## Summary

A **recursion relation for conformal blocks** is a rule that computes complicated blocks from simpler data. There are two common meanings.

First, one may expand a scalar block in radial coordinates,

$$
g_{\Delta,\ell}(r,\eta)
=
(4r)^\Delta
\sum_{n=0}^{\infty} r^n
\sum_j
B_{n,j}(\Delta,\ell) C_j^{(\nu)}(\eta),
\qquad
\nu=\frac d2-1,
$$

and use the Casimir equation to determine the coefficients $B_{n,j}$ level by level.

Second, one may view the block as a meromorphic function of the exchanged dimension $\Delta$. At special values of $\Delta$, a descendant becomes primary and the block has a simple pole. The residue is proportional to a lower or shifted block. Schematically, after removing the leading factor $(4r)^\Delta$,

$$
h_{\Delta,\ell}(r,\eta)
=
h_{\infty,\ell}(r,\eta)
+
\sum_A
\frac{R_A(\ell)}{\Delta-\Delta_A^*}
(4r)^{n_A}
h_{\Delta_A^*+n_A,\ell_A}(r,\eta).
$$

This page explains what those statements mean, why they are true, and how they feed numerical bootstrap calculations.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Conformal block recursion from null descendant poles in the exchanged dimension.](/figures/cft-bootstrap/conformal-block-recursion-poles.svg)

<figcaption>

Dimension recursion treats the block as a meromorphic function of $\Delta$. At special dimensions $\Delta_A^*$, a descendant becomes primary, producing a simple pole whose residue is another conformal block with shifted dimension and spin.

</figcaption>
</figure>

## Prerequisites

You should know [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), [Casimir Equation](/cft-bootstrap/conformal-blocks/casimir-equation/), [Radial Coordinates](/cft-bootstrap/conformal-blocks/radial-coordinates/), [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/), and [Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/). The notation follows [Conventions and Notation](/cft-bootstrap/conventions/).

## Core idea

A conformal block is fixed by symmetry, but “fixed by symmetry” does not mean “easy to write in one line.” A block packages infinitely many descendants. Recursion relations organize that infinite sum in a way that is computable.

The radial expansion gives the first mental model. A primary creates the bottom state of a conformal multiplet. Acting with translations creates descendants. In radial quantization, a descendant at level $n$ costs $n$ extra units of radial energy, so it contributes $r^{\Delta+n}$. The Casimir equation relates neighboring levels. Starting from the leading primary term, one can climb the tower.

The meromorphic recursion gives the second mental model. The representation theory of the conformal algebra changes at special values of $\Delta$. A descendant can become null and itself behave like a new primary. Near such a reducibility point, the projector onto the conformal multiplet develops a pole. The residue is the block associated with the descendant multiplet. This is the conformal-block analogue of using singularities to reconstruct a function.

## Setup and conventions

We focus on scalar external operators and symmetric-traceless exchange in the $12\to34$ channel. Write

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z),
\qquad
z=\frac{4\rho}{(1+\rho)^2},
\qquad
\rho=re^{i\theta},
\qquad
\eta=\cos\theta.
$$

The block is denoted

$$
g_{\Delta,\ell}^{\Delta_{12},\Delta_{34}}(r,\eta).
$$

When the external dimensions are not all equal, the residues and seed functions depend on the two external-dimension differences. Many references package these as parameters such as $a=-\Delta_{12}/2$ and $b=\Delta_{34}/2$, or slight variants. This page keeps the external-dimension dependence visible but does not choose a residue-table convention.

The quadratic Casimir eigenvalue of the exchanged primary is

$$
C_{\Delta,\ell}
=
\Delta(\Delta-d)+\ell(\ell+d-2).
$$

The Casimir equation says that the differential operator acting on the two points being fused satisfies

$$
\mathcal C_{12}\,g_{\Delta,\ell}
=
C_{\Delta,\ell}\,g_{\Delta,\ell},
$$

with the OPE-limit boundary condition selecting the physical block rather than its shadow.

## Level recursion from the Casimir equation

Insert the radial ansatz

$$
g_{\Delta,\ell}(r,\eta)
=
(4r)^\Delta
\sum_{n=0}^{\infty} r^n
\sum_j
B_{n,j} C_j^{(\nu)}(\eta)
$$

into the Casimir equation. The leading coefficient is fixed by normalization; in a common convention,

$$
B_{0,j}=0\quad(j\neq \ell),
\qquad
B_{0,\ell}\neq0.
$$

The Casimir operator is second order in the cross-ratios. In radial variables it relates coefficients at level $n$ to coefficients at lower levels. The recursion has the schematic form

$$
\bigl(C_{\Delta+n,j}-C_{\Delta,\ell}\bigr)B_{n,j}
=
\text{known expression built from lower levels}.
$$

Here

$$
C_{\Delta+n,j}
=
(\Delta+n)(\Delta+n-d)+j(j+d-2)
$$

is the Casimir eigenvalue one would associate with a state of dimension $\Delta+n$ and spin $j$. The exact right-hand side depends on external dimensions and normalization conventions, but the structure is universal: once the lower levels are known, the next level is determined unless a denominator vanishes.

Those exceptional denominators are not a computational accident. They signal reducible conformal representations, exactly the same phenomenon that appears as poles in the dimension-recursion method.

## Null descendants and pole families

For generic $\Delta$, the descendant tower of a spin-$\ell$ primary is irreducible. At special values $\Delta=\Delta_A^*$, a descendant becomes null and transforms as a primary. There are three standard families for symmetric-traceless representations in $d$ dimensions.

| Family | Pole location | Level | Shifted spin | Interpretation |
|---|---:|---:|---:|---|
| I | $\Delta_A^*=1-\ell-n$ | $n$ | $\ell+n$ | Symmetric-gradient descendant becomes primary. |
| II | $\Delta_A^*=\ell+d-1-n$ | $n$ | $\ell-n$ | Divergence-type descendant becomes primary. |
| III | $\Delta_A^*=d/2-n$ | $2n$ | $\ell$ | Laplacian-type descendant becomes primary. |

For family II, $n=1,\ldots,\ell$. For the other two families, $n=1,2,\ldots$ within the range where the representation exists and the shifted spin is meaningful.

The most familiar example is family II with $n=1$:

$$
\Delta_A^*=\ell+d-2.
$$

This is the conserved-current value for a spin-$\ell$ operator. The level-one descendant is the divergence. When the primary saturates the unitarity bound, that divergence is null, giving a short multiplet.

## Dimension recursion

Define a reduced block $h_{\Delta,\ell}$ by factoring out the leading radial behavior,

$$
g_{\Delta,\ell}(r,\eta)=(4r)^\Delta h_{\Delta,\ell}(r,\eta).
$$

The block $h_{\Delta,\ell}$ is meromorphic in $\Delta$. Its poles occur at the reducibility points $\Delta_A^*$. Near such a pole,

$$
h_{\Delta,\ell}(r,\eta)
\sim
\frac{R_A}{\Delta-\Delta_A^*}
(4r)^{n_A}
h_{\Delta_A^*+n_A,\ell_A}(r,\eta)
+
\text{regular}.
$$

The factor $(4r)^{n_A}$ records that the null primary is a level-$n_A$ descendant of the original primary. The shifted block has dimension $\Delta_A^*+n_A$ and spin $\ell_A$.

Putting all poles together gives the recursion

$$
h_{\Delta,\ell}(r,\eta)
=
h_{\infty,\ell}(r,\eta)
+
\sum_A
\frac{R_A}{\Delta-\Delta_A^*}
(4r)^{n_A}
h_{\Delta_A^*+n_A,\ell_A}(r,\eta).
$$

The seed $h_{\infty,\ell}$ is the large-$\Delta$ block, which is much simpler than a general block and is known explicitly in standard conventions. The coefficients $R_A$ are residue factors determined by conformal representation theory and by external dimensions.

This formula is powerful because each residue term points to another block with shifted parameters. Truncating the sum over poles and solving recursively gives accurate block values and derivatives.

:::note[What this page does not tabulate]
The explicit residue factors $R_A$ are convention-sensitive. They depend on block normalization, two-point normalization, and the external-dimension-difference parameters. For implementation, use a single standard reference or codebase and do not mix residue tables across conventions.
:::

## From recursion to derivatives

Numerical bootstrap calculations do not usually need the whole function $g_{\Delta,\ell}(z,\bar z)$. They need derivatives at the crossing-symmetric point:

$$
\left.
\partial_z^m\partial_{\bar z}^n
g_{\Delta,\ell}(z,\bar z)
\right|_{z=\bar z=1/2}.
$$

Radial coordinates and recursion relations make these derivatives computable. A typical workflow is:

1. rewrite the block in $\rho,\bar\rho$ or $r,\eta$;
2. generate a radial expansion or use dimension recursion;
3. evaluate derivatives at the symmetric point;
4. approximate the result as a rational function of $\Delta$;
5. pass polynomial data to a semidefinite program.

The rational-approximation step is what turns a continuous positivity problem into the kind of polynomial matrix positivity problem that bootstrap solvers can handle. Schematically,

$$
\left.
\partial_z^m\partial_{\bar z}^n
g_{\Delta,\ell}
\right|_{1/2}
\approx
\chi_\ell(\Delta)\,
P_{m,n,\ell}(\Delta),
$$

where $\chi_\ell(\Delta)$ is a positive prefactor on the allowed unitary range and $P_{m,n,\ell}$ is a polynomial or polynomial matrix after truncation. The exact form depends on the chosen bootstrap package and approximation scheme.

## Checks

**OPE normalization.** The recursion must reproduce the leading $r^\Delta C_\ell^{(\nu)}(\eta)$ behavior. A recursion that gets many higher terms right but misses the leading normalization is still incompatible with the OPE coefficient convention.

**Casimir eigenvalue.** Substituting the generated block back into the Casimir equation should reproduce $C_{\Delta,\ell}=\Delta(\Delta-d)+\ell(\ell+d-2)$ to the intended truncation order.

**Conservation pole.** For spin $\ell\ge1$, the family-II pole at $\Delta=\ell+d-2$ should be visible in the long-multiplet block. Physical conserved-current blocks require quotienting by the null descendant, not blindly treating the long block as generic.

**Crossing derivatives.** Derivative tables should respect the exchange symmetries of the external operators. Odd or even derivative patterns often provide a quick way to catch channel or normalization mistakes.

## Bootstrap role

Conformal blocks are the expensive special functions inside the bootstrap. Recursion relations are the reason high-precision bootstrap calculations are possible rather than heroic hand tabulations.

For the identical-scalar bootstrap, one builds crossing vectors

$$
F_{\Delta,\ell}(u,v)
=
v^{\Delta_\phi}
g_{\Delta,\ell}(u,v)
-
u^{\Delta_\phi}
g_{\Delta,\ell}(v,u).
$$

A linear functional acts on derivatives of these vectors at the symmetric point. To test positivity for all $\Delta$ above a gap, the computation needs reliable functions of $\Delta$ for each spin $\ell$. Recursion relations supply those functions.

For mixed correlators and spinning operators, the same logic survives but the objects become matrices of tensor structures. The computational problem is larger, but the organizing principle is unchanged: symmetry fixes the blocks; recursion computes them.

## Assumptions and status

- **Exact:** The Casimir equation, reducibility points of conformal multiplets, and pole structure of blocks are exact representation-theoretic facts.
- **Numerical:** Practical implementations truncate pole sums, radial series, spin ranges, derivative orders, or polynomial approximations.
- **Assumption-dependent:** Positivity of the resulting bootstrap problem depends on unitarity, operator reality conditions, global-symmetry decomposition, and tensor-structure normalization.
- **Open:** For complicated spinning, defect, supersymmetric, and Lorentzian setups, the best block basis and recursion strategy can be a serious research-level choice.

## Common pitfalls

**Thinking recursion changes the definition of the block.** Recursion is a computation method. The block is still defined by the OPE contribution of one conformal multiplet.

**Mixing conventions for residues.** The pole locations are universal; the residues are not. If $R_A$ is copied from a source with different block normalization, the resulting block will be wrong.

**Confusing null descendants with missing operators.** A null descendant is a zero-norm state inside a representation at a special value of $\Delta$. It is not an additional independent primary in the CFT spectrum.

**Ignoring short multiplets.** Conserved currents and stress tensors sit at unitarity bounds. Their conformal blocks must respect shortening conditions.

**Overtrusting a truncation.** A recursion truncated at finite order is a numerical approximation. Bootstrap claims should state derivative order, spin cutoff, precision, gaps, and convergence checks where relevant.

## Relations to other pages

- [Casimir Equation](/cft-bootstrap/conformal-blocks/casimir-equation/) gives the differential equation behind level recursion.
- [Radial Coordinates](/cft-bootstrap/conformal-blocks/radial-coordinates/) explains why the radial series converges rapidly.
- [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) defines the scalar blocks being computed here.
- [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/) explains descendants, null states, and shortening.
- [Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/) explains why the conservation pole is physically important.
- [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/) will explain how block derivative data become numerical bootstrap constraints.
- [Precision and Error Control](/cft-bootstrap/numerical-bootstrap/precision-and-error-control/) will discuss how truncation and arithmetic errors are reported.

## Research status

The scalar-block recursion technology is mature and standard. It is one of the hidden engines behind the numerical bootstrap’s success in three-dimensional Ising, $O(N)$, and related systems.

The frontier is broader block infrastructure: spinning external operators, mixed correlator systems, supersymmetric shortening, defects and boundaries, non-integer dimensions, Lorentzian continuations, and code-level reproducibility. In those applications, the same representation-theoretic ideas remain central, but implementation details matter enormously. Tiny normalization mistakes can look like physics until the solver catches fire. Sometimes the solver does not even have the courtesy to catch fire.

## Exercises

### Exercise 1: Identify the conservation pole

Use the family-II pole formula

$$
\Delta_A^*=\ell+d-1-n
$$

with $n=1$. Show that it gives the unitarity-bound value for a conserved spin-$\ell$ current.

<details>
<summary><strong>Solution</strong></summary>

For $n=1$,

$$
\Delta_A^*=\ell+d-2.
$$

A symmetric-traceless spin-$\ell$ conserved current in $d$ dimensions has dimension

$$
\Delta=\ell+d-2.
$$

At this value, the level-one divergence descendant is null:

$$
\partial^{\mu_1}J_{\mu_1\cdots\mu_\ell}=0.
$$

Thus the pole family correctly detects the shortening of a conserved-current multiplet.

</details>

### Exercise 2: Level suppression in radial recursion

Suppose a descendant at level $n$ contributes to a block in radial coordinates. What is its leading radial suppression relative to the primary?

<details>
<summary><strong>Solution</strong></summary>

The primary has radial energy $\Delta$ and contributes $r^\Delta$. A level-$n$ descendant has radial energy $\Delta+n$, so it contributes $r^{\Delta+n}$. Relative to the primary, it is suppressed by $r^n$. This is why the radial expansion is efficient when $r$ is small.

</details>

### Exercise 3: Why poles in delta do not mean physical divergences

The long-multiplet scalar block has poles at special $\Delta_A^*$. Explain why this does not mean that physical four-point functions generically diverge at those dimensions.

<details>
<summary><strong>Solution</strong></summary>

The pole is a feature of the long-multiplet block as a function of the formal parameter $\Delta$. At a reducibility point, the representation develops a null descendant and should be replaced by the appropriate shortened or quotient representation. In a physical correlator, OPE coefficients and the correct representation content combine so that the correlator is well-defined. The pole is a computational signal of shortening, not a generic physical singularity.

</details>

### Exercise 4: Rational approximation and positivity

Why is it useful to approximate block derivatives as

$$
\chi_\ell(\Delta)P_\ell(\Delta),
$$

where $\chi_\ell(\Delta)$ is positive on the allowed range and $P_\ell$ is polynomial?

<details>
<summary><strong>Solution</strong></summary>

Bootstrap solvers need to impose positivity for continuous ranges of $\Delta$. Polynomial positivity, or matrix polynomial positivity, can be encoded in semidefinite programming. If $\chi_\ell(\Delta)$ is positive on the range being tested, it does not affect the sign. The positivity problem can therefore be transferred to the polynomial part $P_\ell(\Delta)$, up to the accuracy of the approximation.

</details>

## References

### Standard first pass

- Slava Rychkov, *EPFL Lectures on Conformal Field Theory in D Greater Than or Equal to Three Dimensions*, 2016.
- David Simmons-Duffin, *The Conformal Bootstrap*, TASI lectures, 2017.
- David Poland, Slava Rychkov, and Alessandro Vichi, *The Conformal Bootstrap: Theory, Numerical Techniques, and Applications*, 2019.

### Deeper references

- Francis A. Dolan and Hugh Osborn, works on conformal partial waves and scalar conformal blocks.
- Matthijs Hogervorst and Slava Rychkov, *Radial Coordinates for Conformal Blocks*, 2013.
- Filip Kos, David Poland, and David Simmons-Duffin, work on bootstrap equations and rational approximations for conformal blocks.
- Miguel S. Costa, Joao Penedones, David Poland, and Slava Rychkov, work on spinning conformal correlators and blocks.
- Slava Rychkov and Ning Su, *New Developments in the Numerical Conformal Bootstrap*, 2024, for modern computational context.

## Version history

- **2026-06-27:** Initial polished draft for the Conformal Blocks chapter.
