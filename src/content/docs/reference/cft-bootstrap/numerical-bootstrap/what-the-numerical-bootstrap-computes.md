---
title: "What the Numerical Bootstrap Computes"
description: "What numerical conformal bootstrap calculations take as input, what they return, and how to interpret bounds, islands, functionals, and extracted spectra."
sidebar:
  label: "What It Computes"
  order: 1
level: Graduate
status: "Polished draft"
source: "Poland, Rychkov, and Vichi 2019; Rychkov and Su 2024; Simmons-Duffin TASI lectures; standard numerical bootstrap literature."
topics:
  - numerical conformal bootstrap
  - bootstrap bounds
  - bootstrap islands
  - spectrum extraction
  - crossing symmetry
canonicalTopics:
  - what-the-numerical-bootstrap-computes
  - bootstrap-input-output-map
  - numerical-bootstrap-interpretation
researchStatus:
  established:
    - "Numerical bootstrap computations turn crossing, unitarity, and explicit spectral assumptions into exclusion certificates, allowed regions, bounds, islands, and approximate CFT data."
  active:
    - "Current work improves reliability, algorithms, spectrum extraction, mixed-correlator systems, spinning correlators, and applications to gauge theories, defects, and supersymmetric CFTs."
---

## Summary

The **numerical conformal bootstrap** computes consequences of CFT consistency. It does not simulate a lattice Hamiltonian, integrate a path integral directly, or solve a Lagrangian equation of motion. Its basic input is a set of crossing equations plus assumptions such as unitarity, global symmetry, operator gaps, spacetime dimension, and sometimes the existence of special operators like currents or stress tensors.

The output is usually one of the following:

| Output | Meaning |
|---|---|
| bound | A rigorous-looking upper or lower limit on a dimension, OPE coefficient, or normalization under stated assumptions. |
| excluded region | A set of hypothetical CFT data proven inconsistent at a chosen numerical cutoff. |
| allowed region | The complement of what the computation could exclude, not automatically a set of real CFTs. |
| kink | A sharp feature in a bound, often but not always associated with an actual CFT. |
| island | A small allowed region obtained after adding physically motivated assumptions. |
| extremal spectrum | Approximate operator data inferred from a functional saturating an optimal bound. |
| navigator value | A diagnostic number used to search high-dimensional parameter spaces. |

The simplest schematic crossing equation is

$$
\sum_{\mathcal O}\lambda_{\phi\phi\mathcal O}^2 F_{\Delta,\ell}=0,
$$

with

$$
\lambda_{\phi\phi\mathcal O}^2\ge0
$$

in a unitary identical-scalar setup. Numerical bootstrap asks whether such an equation can be solved with an assumed spectrum. If not, the assumed spectrum is excluded.

The central warning is:

$$
\text{allowed by a finite bootstrap run}\ne\text{known to exist as a CFT}.
$$

A numerical bootstrap result is a conditional consistency statement. Its power comes from making the conditions explicit.

## Prerequisites

Read the [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) overview, [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/), [Identical Scalar Bootstrap](/cft-bootstrap/crossing-bootstrap-logic/identical-scalar-bootstrap/), [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/), and [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) first.

You should know that CFT data consist of operator dimensions, spins, global-symmetry representations, and OPE coefficients. You do not need to know semidefinite programming yet; this page explains what is being computed before explaining how.

## Core idea

A CFT four-point function can be expanded using the OPE in different channels. Crossing symmetry says these expansions describe the same function. In a unitary theory, many OPE coefficients enter as nonnegative squares. This converts consistency into a positivity problem.

A numerical bootstrap computation usually starts with a proposed statement such as:

> Suppose a unitary 3D CFT has a scalar $\phi$ of dimension $\Delta_\phi$, and suppose the first scalar in $\phi\times\phi$ after the identity has dimension at least $\Delta_{\rm gap}$. Can crossing be satisfied?

The computer does not search directly over all CFTs. Instead, it searches for a **certificate of impossibility**. If it finds a linear functional $\alpha$ such that all possible exchanged operators contribute with the same sign while the identity contributes with the opposite sign, then the assumed spectrum cannot solve crossing.

The slogan is

$$
\text{bootstrap computation}
=\text{search for consistency or a certificate of inconsistency}.
$$

This perspective explains why the method is powerful. One can rule out infinitely many hypothetical spectra using finitely many numerical inequalities.

## Setup and conventions

Consider a scalar primary $\phi$ in a unitary CFT. Normalize the two-point function as

$$
\langle\phi(x)\phi(0)\rangle=\frac{1}{(x^2)^{\Delta_\phi}}.
$$

The four-point function can be written as

$$
\langle\phi_1\phi_2\phi_3\phi_4\rangle
=\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}\mathcal G(u,v),
$$

where

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

The OPE expansion is

$$
\mathcal G(u,v)
=\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2G_{\Delta,\ell}(u,v).
$$

Crossing gives a vector equation of the schematic form

$$
\sum_{\mathcal O}\lambda_{\phi\phi\mathcal O}^2F_{\Delta,\ell}=0.
$$

The identity operator is included as one term, usually separated because its coefficient is fixed:

$$
\lambda_{\phi\phi\mathbf 1}^2=1
$$

in the unit-normalized convention.

A numerical computation replaces the infinite-dimensional crossing equation by a finite problem: derivatives up to some order, spins up to some effective treatment, and rational or polynomial approximations to conformal blocks.

## What goes in

A bootstrap run has explicit inputs. They are not optional background philosophy; they define the problem being solved.

| Input | Example | Why it matters |
|---|---|---|
| spacetime dimension | $d=3$ | Determines conformal blocks and unitarity bounds. |
| external operators | $\sigma$, $\epsilon$, $\phi_i$ | Determines which correlators and OPE channels appear. |
| global symmetry | $\mathbb Z_2$, $O(N)$, $SU(N)$ | Decomposes crossing into representation sectors. |
| unitarity | positive norms and OPE squares | Gives positivity constraints. |
| gaps | $\Delta_{\epsilon'}\ge3.8$ | Turns broad bounds into targeted islands. |
| protected operators | $T_{\mu\nu}$, $J_\mu$ | Inserts fixed-dimension conserved operators. |
| numerical cutoff | derivative order $\Lambda$ | Controls the finite approximation. |
| precision settings | arithmetic precision, tolerances | Affects reliability of solver output. |

The most important habit is to read a bootstrap result as a sentence beginning with “Assuming…” For example:

> Assuming unitarity, $d=3$, $\mathbb Z_2$ symmetry, one relevant odd scalar, one relevant even scalar, and a gap above the next even scalar, the allowed region for $(\Delta_\sigma,\Delta_\epsilon)$ is small.

Without the assumptions, the statement is meaningless.

## What comes out

The most common outputs are bounds. A bound may say, for example,

$$
\Delta_{\rm next\ scalar}\le B(\Delta_\phi)
$$

or

$$
C_T\ge C_T^{\rm min}(\Delta_\phi).
$$

A more targeted calculation can produce an island: a small region in a space of trial parameters, such as

$$
(\Delta_\sigma,\Delta_\epsilon).
$$

At an optimal point, the extremal functional method may extract approximate dimensions and OPE coefficients for the candidate CFT. This is how numerical bootstrap moves from exclusion to spectroscopy.

The output is best interpreted in layers:

1. **Exclusion:** the cleanest result; a region is inconsistent with the assumptions at the chosen cutoff.
2. **Bound:** a frontier between excluded and not-excluded regions.
3. **Kink:** a suggestive feature in the bound.
4. **Island:** a targeted allowed region after adding assumptions.
5. **Spectrum extraction:** approximate CFT data inferred near an optimal or isolated solution.

The further down this list one goes, the more interpretation is involved.

## Exclusion certificates

The basic exclusion logic is simple. Suppose crossing is

$$
F_{\mathbf1}+\sum_{\mathcal O\ne\mathbf1}\lambda_{\mathcal O}^2F_{\Delta,\ell}=0.
$$

Here $F_{\mathbf1}$ is the identity contribution and

$$
\lambda_{\mathcal O}^2\ge0.
$$

If one can find a linear functional $\alpha$ such that

$$
\alpha(F_{\mathbf1})>0
$$

and

$$
\alpha(F_{\Delta,\ell})\ge0
$$

for every non-identity operator allowed by the assumed spectrum, then applying $\alpha$ to crossing gives

$$
0=\alpha(F_{\mathbf1})+\sum_{\mathcal O\ne\mathbf1}\lambda_{\mathcal O}^2\alpha(F_{\Delta,\ell})>0,
$$

which is impossible.

Therefore the assumed spectrum is excluded.

This is the heart of the numerical bootstrap. The computer searches for $\alpha$. If it finds one, the proposed assumptions are inconsistent. If it does not find one, the assumptions are merely not excluded at that cutoff.

## Bounds

A typical scalar-dimension bound is found by scanning over a hypothetical gap. For each trial value $\Delta_{\rm gap}$, ask whether the spectrum with no scalar below that gap is excluded.

If gaps above a certain value are excluded, then crossing requires at least one scalar below that value. This gives an upper bound on the first scalar dimension in that sector.

For example, a schematic result might be:

$$
\Delta_{S,0}^{\rm first}\le B(\Delta_\phi).
$$

The curve $B(\Delta_\phi)$ is a bootstrap bound. It does not say that a CFT exists at every point below the curve. It says that points above the curve are inconsistent with the assumptions and truncation.

When a known or suspected CFT sits at a sharp feature of the curve, the feature is called a kink. Kinks are clues, not proofs.

## Islands

An island is a small allowed region in parameter space. Islands usually require more information than a single correlator and a single gap. For the 3D Ising CFT, the decisive step was to use mixed correlators involving the leading odd scalar $\sigma$ and leading even scalar $\epsilon$, together with assumptions about gaps in the odd and even scalar sectors.

A typical island statement looks like:

$$
(\Delta_\sigma,\Delta_\epsilon)
\in \text{small allowed region}
$$

under stated assumptions.

The strength of an island is that it can isolate candidate CFT data with high precision. The danger is that the result may be misquoted without the assumptions that made the island appear.

A responsible island claim includes:

- the external operators used;
- the global symmetry and spacetime dimension;
- the imposed gaps;
- the derivative cutoff and numerical precision;
- convergence checks as the cutoff increases;
- comparison with other methods when available.

## Spectrum extraction

Near an optimal bound, the extremal functional often has zeros at operator dimensions that appear in the putative extremal solution. These zeros can be used to estimate a spectrum:

$$
\{\Delta_i,\ell_i,\lambda_i^2\}.
$$

This procedure is powerful but delicate. Degenerate operators, nearly degenerate operators, finite-cutoff artifacts, and insufficient assumptions can all distort the extracted spectrum.

Spectrum extraction is most trustworthy when:

1. the point lies on a stable boundary or inside a well-isolated island;
2. results converge with increasing derivative cutoff;
3. extracted dimensions satisfy known Ward identities and symmetry constraints;
4. independent methods agree;
5. the same data appear consistently across different correlator systems.

The extremal functional method is a spectroscope, not a magic oracle. It turns consistency saturation into approximate CFT data.

## What the numerical bootstrap does not compute

The numerical bootstrap does **not** usually compute a path integral:

$$
\int \mathcal D\phi\,e^{-S[\phi]}.
$$

It also does not generally prove that a proposed microscopic Lagrangian flows to a given CFT. Instead, it constrains possible CFT data compatible with symmetry and consistency.

It does not automatically determine:

| Not directly computed | Why |
|---|---|
| microscopic Hamiltonian | Bootstrap works with continuum CFT data. |
| RG trajectory | Crossing describes fixed-point data, not the whole flow. |
| existence of every allowed point | Allowed means not excluded. |
| exact finite-$N$ spectrum from a finite run | Truncation and numerical precision remain. |
| nonlocal or nonunitary consistency | Standard positivity assumptions may fail. |
| all correlators | Only correlators included in the system are constrained directly. |

This is not a weakness. It is what makes the method so general. By avoiding microscopic details, the bootstrap can constrain non-Lagrangian and strongly coupled theories.

## Reliability and convergence

A numerical bootstrap result is more reliable when it is stable under increasing the numerical cutoff. If $\Lambda$ is the derivative order, then a typical sequence of bounds might be

$$
B_{\Lambda=19},\quad B_{\Lambda=27},\quad B_{\Lambda=35},\quad\ldots .
$$

One expects bounds to improve or stabilize as $\Lambda$ increases, though the details depend on the setup. If a claimed feature disappears when the cutoff changes, it should not be trusted.

Reliability also depends on solver precision, conformal block accuracy, spin truncation, assumptions about large spin, and whether the problem is well conditioned.

A good numerical bootstrap paper therefore reports enough information for readers to understand the computation:

- derivative order or truncation parameters;
- precision and solver tolerances;
- block-generation method;
- imposed gaps and assumptions;
- convergence behavior;
- code or input files when feasible.

The slogan is

$$
\text{numerical bootstrap result}=	ext{mathematical idea}+\text{computational implementation}+\text{interpretation}.
$$

All three parts matter.

## Example: the 3D Ising island

The 3D Ising CFT illustrates the input-output map perfectly.

The inputs include:

- $d=3$;
- unitarity;
- $\mathbb Z_2$ symmetry;
- external operators $\sigma$ and $\epsilon$;
- crossing equations for mixed correlators;
- assumptions that $\sigma$ and $\epsilon$ are the leading odd and even scalars;
- gaps to subleading operators in selected sectors.

The output is a small allowed island in the plane

$$
(\Delta_\sigma,\Delta_\epsilon).
$$

Inside or near this island, one can extract additional CFT data such as OPE coefficients, stress-tensor normalization, and subleading operator dimensions.

The computation does not simulate a cubic-lattice Ising model. It identifies the continuum CFT data compatible with crossing and the assumed Ising-like spectrum. Agreement with lattice simulations and experiments then supports the identification with the Ising universality class.

## Example: gauge-theory targets

Gauge-theory CFTs are harder bootstrap targets. The natural Lagrangian fields may not be gauge-invariant local operators. One must choose external operators such as bilinears, monopoles, conserved currents, or other gauge-invariant composites.

A bootstrap question might be:

> Is there a unitary 3D CFT with the global symmetry and low-lying monopole spectrum expected of QED3 with $N_f$ fermions?

The computation constrains the hypothetical CFT data. It does not by itself prove that a particular gauge-theory Lagrangian flows to that solution. The bridge from Lagrangian to CFT may require large-$N_f$ calculations, lattice simulations, dualities, supersymmetric analogues, or other evidence.

This distinction is essential for modern applications. Bootstrap is a consistency microscope. It sees CFT data, not gauge redundancy.

## Common pitfalls

**Do not confuse allowed with existing.** A finite bootstrap run can fail to exclude a point even if no CFT exists there.

**Do not quote islands without assumptions.** Islands are produced by crossing plus specific spectral assumptions.

**Do not treat a kink as proof.** Kinks are strong hints only when supported by spectrum extraction, mixed correlators, convergence, and independent evidence.

**Do not forget finite-cutoff effects.** A result at one derivative order is not the full infinite-dimensional bootstrap problem.

**Do not apply identical-scalar positivity blindly.** Non-identical, spinning, fermionic, and nonunitary systems require modified positivity structures.

**Do not confuse CFT data with microscopic fields.** Bootstrap computes dimensions and OPE data of local operators, not lattice spins or gauge-variant fields directly.

**Do not hide numerical choices.** Precision, block approximations, truncations, and solver settings are part of the result.

## Relations to other pages

This page is the conceptual entry point to the numerical bootstrap chapter. [Crossing as a Vector Equation](/cft-bootstrap/numerical-bootstrap/crossing-as-a-vector-equation/) explains how scalar crossing becomes the vector equation used in computations. [Linear Functionals](/cft-bootstrap/numerical-bootstrap/linear-functionals/) explains the exclusion certificate. [Derivative Truncations](/cft-bootstrap/numerical-bootstrap/derivative-truncations/) explains how the infinite equation becomes finite.

The physics examples connect to [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/), [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/), and [Gauge-Theory CFTs](/cft-bootstrap/higher-dimensional-cft/gauge-theory-cfts/).

For the conceptual foundations, see [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) and [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/).

## Research status

The input-output logic of numerical bootstrap is established. Exclusion via linear or semidefinite optimization, bounds, mixed-correlator islands, and extremal-functional spectrum extraction are standard parts of the field.

Active research improves the reach and reliability of the method: better algorithms, navigator and cutting-surface methods, more efficient conformal blocks, spinning systems, gauge-theory applications, defect and boundary bootstrap, rigorous error bars, and hybrid methods combining numerical and analytic bootstrap.

## Exercises

### Exercise 1

Explain why finding a functional with

$$
\alpha(F_{\mathbf1})>0,
\qquad
\alpha(F_{\Delta,\ell})\ge0
$$

for all assumed non-identity operators excludes the assumed spectrum.

<details><summary><strong>Solution</strong></summary>

Crossing has the schematic form

$$
F_{\mathbf1}+\sum_{\mathcal O\ne\mathbf1}\lambda_{\mathcal O}^2F_{\Delta,\ell}=0.
$$

Apply $\alpha$:

$$
\alpha(F_{\mathbf1})+\sum_{\mathcal O\ne\mathbf1}\lambda_{\mathcal O}^2\alpha(F_{\Delta,\ell})=0.
$$

In a unitary identical-scalar setup,

$$
\lambda_{\mathcal O}^2\ge0.
$$

By assumption, $\alpha(F_{\mathbf1})>0$ and every other term is nonnegative. Therefore the left-hand side is strictly positive, contradicting zero. The assumed spectrum is impossible.

</details>

### Exercise 2

Why does “not excluded” not mean “exists”?

<details><summary><strong>Solution</strong></summary>

A finite numerical bootstrap run searches for exclusion certificates in a truncated space of functionals and with finite numerical precision. If no certificate is found, the assumptions survive that particular test. There may still be a stronger functional at higher cutoff, another correlator system, or another consistency condition that excludes the point. Therefore “not excluded” means only “not ruled out by this computation.”

</details>

### Exercise 3

List three assumptions behind a typical 3D Ising bootstrap island.

<details><summary><strong>Solution</strong></summary>

Typical assumptions include:

1. the theory is a unitary CFT in $d=3$;
2. it has a $\mathbb Z_2$ global symmetry;
3. $\sigma$ is the leading $\mathbb Z_2$-odd scalar and $\epsilon$ is the leading $\mathbb Z_2$-even scalar;
4. gaps are imposed above the next odd or even scalar in selected sectors;
5. mixed correlators involving $\sigma$ and $\epsilon$ are included.

Any three of these answer the question.

</details>

### Exercise 4

What is the difference between a bound and an island?

<details><summary><strong>Solution</strong></summary>

A bound usually gives an excluded side and an allowed side for one quantity as a function of another, such as an upper bound on the first scalar dimension as a function of $\Delta_\phi$. An island is a small allowed region in a multi-dimensional parameter space, usually obtained by adding extra assumptions and using stronger correlator systems. A bound limits possibilities; an island aims to isolate a candidate CFT.

</details>

### Exercise 5

Why is spectrum extraction more interpretive than exclusion?

<details><summary><strong>Solution</strong></summary>

Exclusion follows from a direct contradiction: a functional with certain positivity properties makes crossing impossible. Spectrum extraction uses zeros or near-zeros of an extremal functional at a finite cutoff to infer which operators would appear in a putative extremal solution. Degeneracies, finite-cutoff artifacts, numerical precision, and missing correlators can affect the inferred spectrum. Therefore spectrum extraction is powerful but requires convergence checks and physical interpretation.

</details>

## References

- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.
- S. El-Showk, M. F. Paulos, D. Poland, S. Rychkov, D. Simmons-Duffin, and A. Vichi, “Solving the 3D Ising Model with the Conformal Bootstrap II,” *Journal of Statistical Physics* **157** (2014).
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Precision islands in the Ising and $O(N)$ models,” *Journal of High Energy Physics* **2016**.

## Version history

- 2026-07-01: First polished draft. Added numerical-bootstrap input-output map, exclusion certificates, bounds, islands, spectrum extraction, reliability caveats, examples, exercises, and references.
