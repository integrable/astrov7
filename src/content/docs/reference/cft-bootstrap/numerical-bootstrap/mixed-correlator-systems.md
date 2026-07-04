---
title: "Mixed-Correlator Systems"
description: "How numerical bootstrap computations combine several external operators, crossing equations, and matrix positivity to isolate CFT data more sharply than single-correlator bounds."
sidebar:
  label: "Mixed-Correlator Systems"
  order: 9
level: Graduate
status: "Polished draft"
source: "Kos, Poland, Simmons-Duffin, and Vichi; Poland, Rychkov, and Vichi 2019; Rychkov and Su 2024; standard mixed-correlator bootstrap literature."
topics:
  - mixed correlators
  - numerical conformal bootstrap
  - matrix positivity
  - bootstrap islands
  - global symmetry
canonicalTopics:
  - mixed-correlator-systems
  - matrix-positivity-bootstrap
  - multi-correlator-bootstrap
researchStatus:
  established:
    - "Mixed-correlator bootstrap systems are essential for precision islands, because they combine several crossing equations and impose positive semidefinite OPE-coefficient matrices."
  active:
    - "Current work improves large mixed systems with many external operators, spinning correlators, global symmetries, supersymmetry, gauge-theory targets, and navigator-based searches."
---

## Summary

A **mixed-correlator system** studies several four-point functions at once. Instead of using only

$$
\langle \phi\phi\phi\phi\rangle,
$$

one may study correlators built from two or more external primaries, such as

$$
\langle \sigma\sigma\sigma\sigma\rangle,
\qquad
\langle \sigma\sigma\epsilon\epsilon\rangle,
\qquad
\langle \epsilon\epsilon\epsilon\epsilon\rangle.
$$

This is the decisive improvement behind many high-precision bootstrap islands. A single correlator can reveal a kink; mixed correlators can isolate a theory.

The new feature is that an exchanged operator can couple to more than one pair of external operators. If an even operator $\mathcal O$ appears in both $\sigma\times\sigma$ and $\epsilon\times\epsilon$, it has two OPE coefficients:

$$
\lambda_{\sigma\sigma\mathcal O},
\qquad
\lambda_{\epsilon\epsilon\mathcal O}.
$$

Their products form a positive semidefinite matrix:

$$
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O}\\
\lambda_{\epsilon\epsilon\mathcal O}
\end{pmatrix}
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O}&
\lambda_{\epsilon\epsilon\mathcal O}
\end{pmatrix}
\succeq0.
$$

Thus mixed-correlator bootstrap is not merely “more equations.” It changes scalar positivity into matrix positivity, making the semidefinite-programming structure much stronger.

## Prerequisites

Read [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/), [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/), [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/), and [Identical Scalar Bounds](/cft-bootstrap/numerical-bootstrap/identical-scalar-bounds/) first.

You should know how a single identical-scalar crossing equation becomes

$$
\vec F_{\mathbf1}+\sum_{\mathcal O\ne\mathbf1}\lambda_{\phi\phi\mathcal O}^2\vec F_{\Delta,\ell}=0,
$$

and why $\lambda^2\ge0$ is replaced by positive semidefinite matrices when several OPE coefficients are present.

## Core idea

Single-correlator bootstrap sees one projection of a CFT. Mixed-correlator bootstrap forces several projections to agree.

A CFT has one operator algebra. If the same operator $\mathcal O$ appears in several OPEs, its dimension is the same in all of them, and its OPE coefficients are related through the same underlying CFT data. Mixed correlators exploit this shared structure.

The slogan is

$$
\text{one CFT data set}
\quad\Longrightarrow\quad
\text{many crossing equations that must be solved together}.
$$

This extra consistency is powerful. It can turn a broad allowed region into a small island because fake solutions that satisfy one correlator often fail to satisfy the full coupled system.

The price is computational. Mixed systems have more tensor structures, more sectors, larger matrices, more assumptions to track, and more expensive semidefinite programs. Precision islands are not free; they are artisanal little monsters.

## From one scalar to two scalars

Let $\phi_1$ and $\phi_2$ be two scalar primaries. A mixed system may include correlators

$$
\langle \phi_i\phi_j\phi_k\phi_l\rangle,
\qquad
 i,j,k,l\in\{1,2\}.
$$

Crossing relates different OPE channels. Operators appearing in $\phi_1\times\phi_1$, $\phi_1\times\phi_2$, and $\phi_2\times\phi_2$ contribute to different equations.

If an exchanged operator $\mathcal O$ appears in both diagonal OPEs, define an OPE vector

$$
\lambda_{\mathcal O}
=
\begin{pmatrix}
\lambda_{11\mathcal O}\\
\lambda_{22\mathcal O}
\end{pmatrix}.
$$

The contribution to crossing involves the outer product

$$
\lambda_{\mathcal O}\lambda_{\mathcal O}^T.
$$

Since this matrix is positive semidefinite, a linear functional must make the corresponding block matrix positive semidefinite:

$$
\alpha(\vec V_{\Delta,\ell})\succeq0.
$$

Here $\vec V_{\Delta,\ell}$ denotes the matrix-valued conformal-block vector for that exchanged representation. The details of $\vec V$ depend on the correlator system and conventions, but the positivity logic is universal.

## Matrix positivity

For a real vector of OPE coefficients

$$
\lambda=
\begin{pmatrix}
\lambda_1\\
\lambda_2\\
\vdots\\
\lambda_n
\end{pmatrix},
$$

the outer product

$$
\lambda\lambda^T
$$

is positive semidefinite because

$$
w^T(\lambda\lambda^T)w=(w\cdot\lambda)^2\ge0.
$$

This is the Hilbert-space positivity statement behind mixed-correlator bootstrap.

The functional condition is no longer merely

$$
\alpha(\vec F_{\Delta,\ell})\ge0.
$$

It is

$$
\alpha(\vec V_{\Delta,\ell})\succeq0,
$$

meaning

$$
w^T\alpha(\vec V_{\Delta,\ell})w\ge0
$$

for every real vector $w$ of OPE-coefficient directions.

This matrix condition captures all possible relative signs and magnitudes of the OPE coefficients to the chosen external pairs. It is why mixed correlators can be dramatically stronger than several unrelated single-correlator bounds.

## Selection rules and sectors

Mixed systems are organized by all available symmetries. These include:

| Structure | Effect |
|---|---|
| spacetime spin | determines conformal blocks and unitarity bounds |
| identical versus non-identical external operators | controls spin selection rules |
| global symmetry | decomposes OPEs into representation sectors |
| parity or discrete symmetry | separates even and odd sectors |
| conservation | fixes dimensions of currents and stress tensors |
| supersymmetry | packages operators into supermultiplets |

In an Ising-like $\mathbb Z_2$ system, the leading operators are

$$
\sigma\quad\text{odd},
\qquad
\epsilon\quad\text{even}.
$$

The selection rules are

$$
\sigma\times\sigma=\text{even},
\qquad
\epsilon\times\epsilon=\text{even},
\qquad
\sigma\times\epsilon=\text{odd}.
$$

Thus even operators can appear in both diagonal OPEs and generate OPE matrices, while odd operators appear in mixed OPEs with their own positivity structure.

In an $O(N)$ model, the vector four-point function decomposes into singlet, traceless symmetric, and antisymmetric sectors. Mixed systems involving the leading singlet and traceless symmetric scalars introduce additional sector bookkeeping.

## The Ising mixed system

The classic example uses the 3D Ising operators $\sigma$ and $\epsilon$. The correlators are

$$
\langle\sigma\sigma\sigma\sigma\rangle,
\qquad
\langle\sigma\sigma\epsilon\epsilon\rangle,
\qquad
\langle\epsilon\epsilon\epsilon\epsilon\rangle.
$$

The even sector includes operators appearing in both

$$
\sigma\times\sigma
$$

and

$$
\epsilon\times\epsilon.
$$

For an even operator $\mathcal O^+$, the OPE vector is

$$
\lambda_{\mathcal O^+}
=
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O^+}\\
\lambda_{\epsilon\epsilon\mathcal O^+}
\end{pmatrix}.
$$

The odd sector includes operators in

$$
\sigma\times\epsilon.
$$

The bootstrap assumptions usually include that $\sigma$ is the leading odd scalar and $\epsilon$ is the leading even scalar, plus gaps above the next odd and even scalars. Under these assumptions, the allowed region in

$$
(\Delta_\sigma,\Delta_\epsilon)
$$

shrinks to a small island.

This is the prototype of a precision island: one does not merely observe a kink; one uses a coupled system to corner the CFT.

## Why mixed correlators make islands

A one-correlator scalar bound asks whether one cone contains one vector. A mixed-correlator system asks whether a much richer cone of matrix-valued block contributions can satisfy several crossing equations simultaneously.

The extra power comes from several sources:

1. The same operator dimensions must work in several OPE channels.
2. Relative OPE coefficients are constrained by positive semidefinite matrices.
3. Global-symmetry and parity sectors are tied together.
4. Gap assumptions can be imposed in multiple sectors.
5. Conserved currents and the stress tensor can be placed in the correct sectors.

A fake solution may satisfy

$$
\langle\sigma\sigma\sigma\sigma\rangle
$$

alone but fail once

$$
\langle\sigma\sigma\epsilon\epsilon\rangle
$$

and

$$
\langle\epsilon\epsilon\epsilon\epsilon\rangle
$$

are included. Mixed correlators are the consistency cross-examination. Very courtroom, but with more Gamma functions.

## OPE coefficient signs

For one identical scalar, changing the sign of an exchanged operator flips

$$
\lambda_{\phi\phi\mathcal O}\mapsto-\lambda_{\phi\phi\mathcal O},
$$

but the four-point function only sees

$$
\lambda_{\phi\phi\mathcal O}^2.
$$

In a mixed system, relative signs become meaningful. If an operator couples to two pairs, then the product

$$
\lambda_{11\mathcal O}\lambda_{22\mathcal O}
$$

appears. Flipping the sign of $\mathcal O$ changes both coefficients and leaves the product invariant, but the relative sign between different external-pair couplings is physical once operator conventions are fixed.

This is why mixed systems can determine OPE coefficient ratios and signs that are invisible to one-correlator bootstrap.

However, signs are convention-dependent under redefinitions of external operators. What is physical is the set of correlators and invariant products, not an isolated sign quoted without conventions.

## Gaps in mixed systems

Gap assumptions must specify the sector. For example, in the Ising mixed system one might assume gaps for:

| Sector | Example statement |
|---|---|
| even scalar | no even scalar after $\epsilon$ below some dimension |
| odd scalar | no odd scalar after $\sigma$ below some dimension |
| even spin two | unique stress tensor and a gap above it |
| odd spin | lower bounds in $\sigma\times\epsilon$ sectors |

The more sectors a system has, the more carefully gaps must be documented.

A gap in the wrong sector does not mean what one wants. For example, saying “the next scalar is irrelevant” is incomplete if the theory has several scalar sectors. One must say whether the gap is singlet, non-singlet, even, odd, traceless symmetric, antisymmetric, or something else.

Good mixed-correlator papers are basically gap-accounting documents with physics attached.

## Global-symmetry mixed systems

For $O(N)$ models, one may combine external operators such as the vector $\phi_i$, the leading singlet scalar $s$, and the leading traceless symmetric scalar $t_{ij}$. The crossing equations know about the tensor product rules of $O(N)$.

The vector OPE decomposes as

$$
\phi_i\times\phi_j=S+T+A,
$$

where $S$ is the singlet, $T$ is traceless symmetric, and $A$ is antisymmetric.

Including $s$ and $t_{ij}$ adds correlators such as

$$
\langle\phi\phi ss\rangle,
\qquad
\langle ssss\rangle,
\qquad
\langle\phi\phi tt\rangle,
\qquad
\langle tttt\rangle,
$$

with many group-theory tensor structures.

Such systems can isolate $O(N)$ islands and test stability questions such as cubic anisotropy. They are also substantially more expensive than the Ising mixed system. The matrices get bigger, the sectors multiply, and the scan dimension grows. The reward is much sharper physics.

## Computational cost

Mixed-correlator systems are expensive because several quantities grow at once:

| Quantity | Why it grows |
|---|---|
| number of crossing equations | more external operator orderings |
| matrix size | more OPE coefficient vectors |
| number of sectors | global symmetry and parity decompositions |
| derivative vector size | same cutoff applied to more structures |
| scan dimension | more external dimensions and gaps |
| solver precision | islands become thin and high-dimensional |

A single-correlator run may be feasible on modest hardware. A serious mixed-correlator island can require large memory, high precision, many solver runs, and careful workflow automation.

This is why modern algorithms such as navigator functions, Delaunay triangulation, and cutting-surface methods matter. They reduce the number of expensive SDP solves needed to map an allowed region.

## Common pitfalls

**Do not treat mixed correlators as independent single-correlator problems.** The power comes from solving the coupled system with shared operator data.

**Do not replace matrix positivity by entrywise positivity.** Positive semidefinite means all quadratic forms are nonnegative, not that every matrix entry is positive.

**Do not hide sector labels on gaps.** A gap must specify representation, spin, parity, and whether it is above a protected operator.

**Do not assume OPE coefficient signs are convention-free.** Relative signs matter inside a fixed convention, but isolated signs can change under operator redefinitions.

**Do not expect islands without assumptions.** Mixed correlators are stronger, but precision islands usually still require physically motivated gaps.

**Do not forget computational conditioning.** Larger matrices and higher derivative cutoffs often require higher precision.

**Do not compare mixed-system results unless external operators and normalizations match.** Different choices of external basis can change how data are quoted.

## Relations to other pages

This page follows [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/) and prepares [Extremal Functional Method](/cft-bootstrap/numerical-bootstrap/extremal-functional-method/), where boundary spectra are extracted.

It also connects to [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/) because mixed systems require positive semidefinite matrix constraints. [Navigator and Modern Search Algorithms](/cft-bootstrap/numerical-bootstrap/navigator-and-modern-search-algorithms/) explains how high-dimensional mixed-correlator island searches are made practical.

For examples, see [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/) and [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/).

## Research status

Mixed-correlator bootstrap is established and is the standard route to precision islands in many nontrivial CFTs. The 3D Ising and $O(N)$ systems are benchmark examples.

Active research extends mixed systems to more external operators, spinning operators, fermions, supersymmetric multiplets, boundary and defect CFTs, gauge-theory CFTs, and high-dimensional navigator searches. A major practical frontier is making these computations scalable, reproducible, and interpretable.

## Exercises

### Exercise 1

Show that an outer product $\lambda\lambda^T$ is positive semidefinite.

<details><summary><strong>Solution</strong></summary>

For any real vector $w$,

$$
w^T(\lambda\lambda^T)w=(w^T\lambda)(\lambda^Tw)=(w\cdot\lambda)^2\ge0.
$$

Therefore $\lambda\lambda^T\succeq0$.

</details>

### Exercise 2

In the Ising mixed system, why do even operators produce OPE vectors with two entries?

<details><summary><strong>Solution</strong></summary>

Even operators can appear in both

$$
\sigma\times\sigma
$$

and

$$
\epsilon\times\epsilon,
$$

because odd times odd is even and even times even is even. Therefore an even exchanged operator $\mathcal O^+$ can have two OPE coefficients:

$$
\lambda_{\sigma\sigma\mathcal O^+},
\qquad
\lambda_{\epsilon\epsilon\mathcal O^+}.
$$

These form the OPE vector used in the matrix-positivity condition.

</details>

### Exercise 3

Why can mixed correlators produce islands when a single correlator only gives a kink?

<details><summary><strong>Solution</strong></summary>

A single correlator imposes one set of crossing constraints. It may produce a boundary with a kink, but many possible spectra can still project to the same region. Mixed correlators impose several crossing equations with shared operator dimensions and positive semidefinite OPE matrices. This removes many fake solutions and can shrink a broad region into a small allowed island under appropriate gap assumptions.

</details>

### Exercise 4

What is incomplete about the statement “we impose a gap above the next scalar” in a theory with global symmetry?

<details><summary><strong>Solution</strong></summary>

With global symmetry, scalar operators occur in different representation sectors. A gap must say which sector it applies to: singlet, vector, traceless symmetric, antisymmetric, odd, even, and so on. The statement “next scalar” is ambiguous unless the representation and parity are specified.

</details>

### Exercise 5

Why is entrywise positivity not enough for a mixed-correlator block matrix?

<details><summary><strong>Solution</strong></summary>

A matrix can have all entries nonnegative but still have a negative eigenvalue. The required condition is positive semidefiniteness:

$$
w^TMw\ge0
$$

for every vector $w$. This guarantees positivity for every possible OPE-coefficient direction. Entrywise positivity checks only a much weaker condition.

</details>

## References

- F. Kos, D. Poland, and D. Simmons-Duffin, “Bootstrapping mixed correlators in the 3D Ising model,” *Journal of High Energy Physics* **2014**.
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Precision islands in the Ising and $O(N)$ models,” *Journal of High Energy Physics* **2016**.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.

## Version history

- 2026-07-01: First polished draft. Added mixed-correlator motivation, matrix positivity, Ising and $O(N)$ examples, gap-sector bookkeeping, computational-cost discussion, exercises, and references.
