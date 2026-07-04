---
title: "Integrable Highest Weights"
description: "Which affine highest-weight representations are allowed in compact WZW models at positive integer level, and how the integrability condition makes the spectrum finite."
sidebar:
  label: "Integrable Highest Weights"
  order: 7
level: Graduate
status: "Polished draft"
source: "Kac; Di Francesco, Mathieu, and Senechal chs. 14–15; standard affine Lie algebra and WZW representation theory."
topics:
  - integrable highest weights
  - affine Lie algebras
  - WZW models
  - representation theory
  - rational CFT
canonicalTopics:
  - integrable-highest-weights
  - affine-representation-theory
  - wzw-primary-spectrum
researchStatus:
  established:
    - "Compact simple WZW models at positive integer level have finitely many affine primary families labeled by integrable highest weights satisfying (lambda, theta) <= k."
  active:
    - "Extensions to noncompact groups, supergroups, admissible fractional levels, logarithmic theories, and boundary or defect sectors require additional representation-theoretic care."
---

## Summary

An **integrable highest weight** is an affine highest weight that gives a well-behaved unitary representation of a compact WZW current algebra at positive integer level. For a compact simple Lie algebra $\mathfrak g$ at level $k$, the allowed WZW primary labels are finite highest weights $\lambda$ satisfying

$$
(\lambda,\theta)\le k,
$$

where $\theta$ is the highest root and long roots have length squared $2$.

The set of allowed weights is usually denoted

$$
P_k^+.
$$

It is finite. This finiteness is the representation-theoretic reason compact WZW models are rational CFTs.

For $SU(2)_k$, the condition becomes

$$
2j\le k,
$$

so

$$
j=0,\frac12,1,\ldots,\frac{k}{2}.
$$

For $SU(N)_k$, if $\lambda_i$ are Dynkin labels, integrability is

$$
\sum_{i=1}^{N-1}\lambda_i\le k.
$$

This page explains the condition, how to use it, why it truncates the spectrum, and how it feeds into WZW characters, fusion rules, and modular data.

## Prerequisites

Read [Affine Lie Algebras](/cft-bootstrap/current-algebras-wzw/affine-lie-algebras/), [Level and Normalization](/cft-bootstrap/current-algebras-wzw/level-and-normalization/), [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/), and [WZW Primary Fields](/cft-bootstrap/current-algebras-wzw/wzw-primary-fields/) first.

You should know the language of finite highest weights, roots, fundamental weights, Dynkin labels, and the highest root. The page reviews the needed formulas but does not replace a full course in Lie algebra representation theory.

## Core idea

A finite compact Lie algebra $\mathfrak g$ has infinitely many irreducible finite-dimensional representations. A WZW model at fixed positive integer level $k$ does not use all of them. It uses only those that fit below the affine level cutoff.

The cutoff is

$$
(\lambda,\theta)\le k.
$$

This inequality says that the highest weight $\lambda$ is not too large in the direction of the highest root. Geometrically, it cuts a finite simplex out of the dominant Weyl chamber.

The slogan is

$$
\text{dominant finite weight}
+\text{level bound}
\quad\Longrightarrow\quad
\text{integrable affine primary}.
$$

Without the level bound, the spectrum would not be finite. With it, the WZW model has finitely many primary families and finite fusion rules.

## Setup and conventions

Let $\mathfrak g$ be compact and simple. Let $\alpha_i$ be simple roots and $\omega_i$ fundamental weights. A dominant finite highest weight is

$$
\lambda=\sum_i \lambda_i\omega_i,
\qquad
\lambda_i\in\mathbb Z_{\ge0}.
$$

The integers $\lambda_i$ are Dynkin labels. Let $\theta$ be the highest root. We normalize long roots by

$$
(\theta,\theta)=2.
$$

The affine level is the integer $k$ appearing in the current algebra

$$
[J^a_m,J^b_n]
=i f^{ab}{}_cJ^c_{m+n}+k m\kappa^{ab}\delta_{m+n,0}.
$$

The integrable highest weights at level $k$ are

$$
P_k^+=\{\lambda\in P^+:(\lambda,\theta)\le k\}.
$$

Here $P^+$ is the set of dominant integral finite weights.

For non-simply-laced algebras, the condition can be written using the highest coroot or comarks depending on the normalization convention. In this chapter, the simple examples are simply laced unless stated otherwise.

## Why integrability appears

Affine Lie algebras contain copies of $\mathfrak{su}(2)$ associated with roots, including the affine root. In a unitary highest-weight representation, these $\mathfrak{su}(2)$ subalgebras must act in finite-dimensional unitary ways.

For the ordinary simple roots, this requires ordinary dominance:

$$
\lambda_i\ge0.
$$

For the affine simple root, the condition becomes the level bound:

$$
(\lambda,\theta)\le k.
$$

Equivalently, the affine Dynkin label associated with the extra node is

$$
\lambda_0=k-(\lambda,\theta),
$$

and integrability requires

$$
\lambda_0\in\mathbb Z_{\ge0}.
$$

Thus an integrable affine highest weight has affine Dynkin labels

$$
(\lambda_0,\lambda_1,\ldots,\lambda_r)
$$

all nonnegative integers, with total level fixed by $k$.

This is not an arbitrary truncation. It is a positivity and representation-theory condition.

## SU(2) example

For $SU(2)$, finite representations are labeled by spin $j$ or by the Dynkin label

$$
\lambda_1=2j.
$$

The highest root is the single root, so

$$
(\lambda,\theta)=2j.
$$

The integrability condition is therefore

$$
2j\le k.
$$

The allowed primaries are

$$
j=0,\frac12,1,\ldots,\frac{k}{2}.
$$

At small levels:

| Level | Allowed spins |
|---:|---|
| $k=1$ | $0,\frac12$ |
| $k=2$ | $0,\frac12,1$ |
| $k=3$ | $0,\frac12,1,\frac32$ |
| $k=4$ | $0,\frac12,1,\frac32,2$ |

The number of primary families is

$$
k+1.
$$

Their conformal weights are

$$
h_j=\frac{j(j+1)}{k+2}.
$$

## SU(N) example

For $SU(N)$, write a dominant highest weight as

$$
\lambda=\sum_{i=1}^{N-1}\lambda_i\omega_i.
$$

The highest root is

$$
\theta=\alpha_1+\alpha_2+\cdots+\alpha_{N-1},
$$

and the integrability condition is

$$
\sum_{i=1}^{N-1}\lambda_i\le k.
$$

Thus $SU(N)_1$ has the integrable weights

$$
0,\ \omega_1,\ \omega_2,\ \ldots,\ \omega_{N-1}.
$$

These correspond to the antisymmetric tensor representations. For example, $SU(3)_1$ has

$$
0,\ \omega_1,\ \omega_2,
$$

which are the singlet, fundamental, and antifundamental sectors.

At level $k=2$, one also allows weights with two boxes in Young-diagram language, such as

$$
2\omega_1,\quad \omega_1+\omega_2,\quad 2\omega_{N-1},
$$

subject to the same total Dynkin-label bound.

For $SU(N)_k$, the condition is equivalent to saying that the associated Young diagram has at most $k$ columns, or equivalently first row length at most $k$ in the usual affine convention. Be explicit about the convention when translating between Dynkin labels and Young diagrams.

## Geometry of the level-k alcove

The dominant Weyl chamber contains all dominant weights:

$$
\lambda_i\ge0.
$$

The level condition adds one more wall:

$$
(\lambda,\theta)=k.
$$

The finite region

$$
\lambda_i\ge0,
\qquad
(\lambda,\theta)\le k
$$

is called the **level-$k$ alcove**. The integrable weights are the lattice points in this alcove.

This picture is useful for remembering WZW fusion. Ordinary tensor products can produce weights outside the alcove. WZW fusion reflects them back or truncates them according to affine Weyl symmetry. The result is a finite fusion algebra.

In this sense, integrability is not merely a list of allowed labels. It is the geometric origin of level-truncated representation theory.

## Conformal weights

Once $\lambda$ is integrable, the Sugawara construction gives the conformal weight

$$
h_\lambda=\frac{C_2(\lambda)}{2(k+h^\vee)}.
$$

With long roots normalized to length squared $2$,

$$
C_2(\lambda)=(\lambda,\lambda+2\rho),
$$

so

$$
h_\lambda=\frac{(\lambda,\lambda+2\rho)}{2(k+h^\vee)}.
$$

The integrability condition determines which $\lambda$ are allowed. The Sugawara formula then determines their weights.

For $SU(2)_k$,

$$
h_j=\frac{j(j+1)}{k+2}.
$$

For the $SU(N)_k$ fundamental,

$$
h_{\rm fund}=\frac{N^2-1}{2N(k+N)}.
$$

These weights are generally rational numbers at integer $k$, as expected in rational CFT.

## Characters and modular data

Each integrable highest weight $\lambda\in P_k^+$ has an affine character

$$
\chi_\lambda(\tau)=\operatorname{Tr}_{\mathcal V_\lambda}q^{L_0-c/24}.
$$

A refined character also includes Cartan fugacities:

$$
\chi_\lambda(\tau,z)=\operatorname{Tr}_{\mathcal V_\lambda}q^{L_0-c/24}e^{2\pi i z\cdot H_0}.
$$

The finite vector of integrable characters transforms under the modular group:

$$
\chi_\lambda(-1/\tau)=\sum_{\mu\in P_k^+}S_{\lambda\mu}\chi_\mu(\tau).
$$

The modular $S$ matrix then computes fusion through the Verlinde formula:

$$
N_{\lambda\mu}{}^\nu
=\sum_{\rho\in P_k^+}
\frac{S_{\lambda\rho}S_{\mu\rho}S^*_{\nu\rho}}{S_{0\rho}}.
$$

The same finite set $P_k^+$ therefore controls primary fields, characters, modular transformations, and fusion rules.

## Fusion truncation

For $SU(2)_k$, fusion is the clearest example. It resembles spin addition but is truncated by the level:

$$
j_1\times j_2
=\sum_j j,
$$

where $j$ runs in integer steps from

$$
|j_1-j_2|
$$

to

$$
\min(j_1+j_2,k-j_1-j_2).
$$

If

$$
j_1+j_2\le\frac{k}{2},
$$

then the level cutoff is invisible and fusion matches the ordinary $SU(2)$ tensor product. If

$$
j_1+j_2>\frac{k}{2},
$$

then the affine cutoff removes the would-be high-spin channels.

For example, in $SU(2)_1$,

$$
\frac12\times\frac12=0,
$$

not

$$
0+1,
$$

because the spin-$1$ representation is not integrable at level one.

This example captures the heart of WZW rationality: ordinary representation theory is present, but it is cut down by the affine level.

## Diagonal WZW Hilbert space

The diagonal compact WZW model has Hilbert space

$$
\mathcal H_{\rm diag}
=\bigoplus_{\lambda\in P_k^+}
\mathcal V_\lambda\otimes\overline{\mathcal V}_\lambda.
$$

Its torus partition function is

$$
Z_{\rm diag}(\tau,\bar\tau)=
\sum_{\lambda\in P_k^+}|\chi_\lambda(	au)|^2.
$$

This is the WZW analogue of a diagonal minimal-model modular invariant. Other modular invariants can pair left and right labels differently, but the chiral building blocks are still integrable affine representations at the chosen level.

The word “integrable” is therefore doing a lot of work. It specifies the chiral spectrum from which local theories are assembled.

## Beyond compact positive integer level

This page focuses on compact simple WZW models at positive integer level. Other cases are important but require more care.

| Setting | What changes |
|---|---|
| Noncompact groups | Spectra may be continuous, and unitarity conditions are different. |
| Fractional admissible level | Some rational structures survive, but the representation category is subtler. |
| Supergroups | The Killing form may vanish or be indefinite, and logarithmic behavior can occur. |
| Logarithmic current algebras | Indecomposable modules replace a purely semisimple primary list. |
| Boundary and defect sectors | Allowed labels can be constrained by boundary conditions or defect gluing. |

So the compact theorem should not be overextended. The safe statement is: for compact simple $G$ at positive integer level $k$, the WZW chiral primaries are labeled by integrable highest weights in $P_k^+$.

## Common pitfalls

**Do not use all finite-dimensional representations.** Only weights satisfying $(\lambda,\theta)\le k$ label compact WZW primaries at level $k$.

**Do not confuse the level bound with a dimension bound.** It bounds the highest-root component of the weight, not the dimension of the finite representation directly.

**Do not forget long-root normalization.** The simple inequality assumes $(\theta,	heta)=2$. Translate carefully for other conventions.

**Do not confuse ordinary tensor products with WZW fusion.** WZW fusion is level truncated. At small level, ordinary tensor-product channels can be absent.

**Do not confuse chiral integrable representations with a full local modular invariant.** The full CFT still needs a left-right pairing.

**Do not apply compact-unitary conclusions to noncompact or logarithmic theories without checking assumptions.** The representation theory can change dramatically.

## Relations to other pages

This page follows [WZW Primary Fields](/cft-bootstrap/current-algebras-wzw/wzw-primary-fields/) by making the allowed label set explicit. It relies on [Level and Normalization](/cft-bootstrap/current-algebras-wzw/level-and-normalization/) for the meaning of $k$ and on [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/) for conformal weights.

The next pages use this finite set repeatedly. [WZW Fusion Rules](/cft-bootstrap/current-algebras-wzw/wzw-fusion-rules/) explains level-truncated products. [Knizhnik–Zamolodchikov Equations](/cft-bootstrap/current-algebras-wzw/knizhnik-zamolodchikov-equations/) studies correlators of fields labeled by these weights. [Cosets and GKO Construction](/cft-bootstrap/current-algebras-wzw/cosets-gko-construction/) uses integrable labels of numerator and denominator current algebras.

The rational-CFT background is developed in [Rational CFT](/cft-bootstrap/minimal-models-rational-cft/rational-cft/), [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), and [Verlinde Formula Preview](/cft-bootstrap/minimal-models-rational-cft/verlinde-formula-preview/).

## Research status

The integrable highest-weight classification for compact affine Lie algebras at positive integer level is established. It is a standard part of WZW model representation theory and rational CFT.

Active work uses these ideas in generalized settings: admissible fractional levels, logarithmic current algebras, supergroup WZW models, nonsemisimple tensor categories, boundary and defect WZW theories, and chiral algebras arising from supersymmetric or higher-dimensional QFT.

## Exercises

### Exercise 1

List the integrable highest weights of $SU(3)_2$ in Dynkin labels.

<details><summary><strong>Solution</strong></summary>

For $SU(3)_k$, the condition is

$$
\lambda_1+\lambda_2\le k.
$$

At $k=2$, the allowed Dynkin labels are

$$
(0,0),\quad(1,0),\quad(0,1),\quad(2,0),\quad(1,1),\quad(0,2).
$$

There are six integrable highest weights.

</details>

### Exercise 2

Why is the spin-$1$ representation absent from $SU(2)_1$ fusion?

<details><summary><strong>Solution</strong></summary>

For $SU(2)_k$, the integrability condition is

$$
2j\le k.
$$

At $k=1$, the allowed spins are only

$$
j=0,\frac12.
$$

The spin-$1$ representation would require $2j=2>1$, so it is not an integrable primary at level one. Therefore the WZW fusion rule is

$$
\frac12\times\frac12=0
$$

rather than the ordinary finite $SU(2)$ tensor product $0+1$.

</details>

### Exercise 3

Compute the number of integrable highest weights of $SU(2)_k$.

<details><summary><strong>Solution</strong></summary>

The allowed spins are

$$
j=0,\frac12,1,\ldots,\frac{k}{2}.
$$

Equivalently, the Dynkin label $\lambda_1=2j$ can be any integer

$$
\lambda_1=0,1,2,\ldots,k.
$$

There are therefore

$$
k+1
$$

integrable highest weights.

</details>

### Exercise 4

For $SU(N)_1$, identify the allowed highest weights.

<details><summary><strong>Solution</strong></summary>

For $SU(N)_k$, the condition is

$$
\sum_{i=1}^{N-1}\lambda_i\le k.
$$

At $k=1$, either all Dynkin labels vanish or exactly one of them is $1$. Thus the allowed weights are

$$
0,\ \omega_1,\ \omega_2,\ldots,\omega_{N-1}.
$$

These correspond to the antisymmetric tensor representations, including the singlet and the conjugate fundamentals.

</details>

## References

- V. Kac, *Infinite-Dimensional Lie Algebras*, Cambridge University Press.
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- P. Goddard, A. Kent, and D. Olive, “Virasoro algebras and coset space models,” *Physics Letters B* **152** (1985).
- E. Verlinde, “Fusion rules and modular transformations in 2D conformal field theory,” *Nuclear Physics B* **300** (1988).
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.

## Version history

- 2026-06-30: First polished draft. Added integrability condition, affine Dynkin-label interpretation, $SU(2)_k$ and $SU(N)_k$ examples, alcove picture, conformal weights, fusion truncation, exercises, and references.
