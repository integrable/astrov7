---
title: "Polymer Expansions"
description: "Explains polymer expansions as the constructive RG technology that turns local activities into convergent expansions for partition functions, connected correlations, and scale-by-scale remainders."
sidebar:
  label: "Polymer Expansions"
  order: 7
level: Advanced
status: "Polished draft"
source: "Brydges; Kotecký–Preiss; Rivasseau; constructive RG literature"
topics:
  - polymer expansions
  - cluster expansions
  - constructive RG
  - connected correlations
  - convergence estimates
canonicalTopics:
  - polymer-expansions
  - constructive-renormalization
  - rigorous-rg
researchStatus:
  established:
    - "Polymer and cluster expansions are standard rigorous tools for proving analyticity, connectedness, decay estimates, and control of nonlocal remainders in constructive QFT and statistical mechanics."
  active:
    - "In modern constructive RG, the main work is not the abstract polymer formula itself but the model-dependent norms, regulators, and scale estimates that make the activities small enough to expand."
---

## Summary

A polymer expansion is a rigorous way to organize a finite-volume partition function or effective interaction as a gas of extended local objects. A **polymer** is usually a finite connected union of blocks in a lattice or multiscale decomposition. It carries an **activity** $K(X)$, and incompatible polymers are not allowed to appear together.

The clean abstract form is

$$
Z=\sum_{\Gamma\ \mathrm{compatible}}
\prod_{X\in\Gamma} K(X),
$$

where compatibility means that distinct polymers in $\Gamma$ do not overlap, or do not interact according to a chosen incompatibility relation. Under a smallness condition on the activities, one obtains a convergent expansion of $\log Z$ in connected clusters:

$$
\log Z
=\sum_{n\geq 1}\frac{1}{n!}
\sum_{X_1,\ldots,X_n}
\varphi^T(X_1,\ldots,X_n)
\prod_{i=1}^n K(X_i).
$$

Here $\varphi^T$ is a truncated, or Ursell, coefficient: it vanishes unless the incompatibility graph on $X_1,\ldots,X_n$ is connected.

In constructive RG, polymer expansions are the technology that turns locality plus smallness into estimates. They separate connected from disconnected contributions, convert local decay into convergence of $\log Z$ and connected correlations, and keep nonlocal remainders under control after each RG step.

## Prerequisites

Read [Renormalization as a Map of Measures](/rigorous-qft/rigorous-renormalization-rg/renormalization-as-map-of-measures/), [Wilsonian RG: Rigorous View](/rigorous-qft/rigorous-renormalization-rg/wilsonian-rg-rigorous-view/), [Rigorous φ⁴ Renormalization](/rigorous-qft/rigorous-renormalization-rg/rigorous-phi-four-renormalization/), and [Cluster Expansions](/rigorous-qft/constructive-qft/cluster-expansions/). You should also know the role of finite-volume cutoff measures from [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/).

## Core idea

The central trick is to replace a global interacting object by local pieces plus a combinatorial rule for how the pieces may coexist. The logarithm of a partition function should count connected physics. Polymer expansions make that statement precise: disconnected polymer families exponentiate away, while connected clusters remain in $\log Z$ and in connected correlation functions.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Polymer gas and connected clusters](/figures/rigorous-qft/polymer-expansion-structure.svg)

<figcaption>

A polymer expansion replaces a complicated finite-volume interaction by activities $K(X)$ attached to connected block sets. Compatible families contribute to $Z$; connected incompatibility clusters contribute to $\log Z$ and connected correlations.

</figcaption>
</figure>

The method is powerful because it proves statements of the form:

$$
\text{small local activities}
\quad\Longrightarrow\quad
\text{convergent connected expansion}.
$$

The hard analysis in QFT is usually to prove the left side uniformly in volume and scale. Once that is done, the abstract polymer machinery supplies the connected expansion.

## Setup and conventions

Let $\mathcal P$ be a finite or countable set of polymers. A symmetric relation $X\nsim Y$ says that $X$ and $Y$ are incompatible. Typically, $X\nsim Y$ means $X\cap Y\neq\varnothing$ or that the two polymers are too close to each other.

A finite compatible family $\Gamma\subset\mathcal P$ is a set such that no two distinct elements are incompatible. The polymer partition function is

$$
Z(\Lambda)
=\sum_{\Gamma\subset\mathcal P(\Lambda)\ \mathrm{compatible}}
\prod_{X\in\Gamma} K(X),
$$

with the convention that the empty family contributes $1$. In constructive field theory, $K(X)$ can be a number, but it is often a functional of a background field:

$$
K(X)=K(X,\phi).
$$

Then the expansion is performed in a Banach norm adapted to the field dependence, not merely in absolute value.

The truncated coefficient in the logarithm is most compactly described by the incompatibility graph. Given $X_1,\ldots,X_n$, form a graph with vertices $1,\ldots,n$ and an edge $ij$ when $X_i\nsim X_j$. Then $\varphi^T(X_1,\ldots,X_n)=0$ unless this graph is connected. One common normalization is

$$
\varphi^T(X_1,\ldots,X_n)
=\sum_{G\ \mathrm{connected}}
\prod_{ij\in E(G)} f_{ij},
$$

where the sum is over connected graphs on $\{1,\ldots,n\}$ and

$$
f_{ij}=\begin{cases}
-1, & X_i\nsim X_j,\\
0, & X_i\sim X_j.
\end{cases}
$$

Different authors shift signs or normalizations, but the invariant content is the same: $\log Z$ sees only connected incompatibility clusters.

## Abstract convergence criterion

A typical convergence theorem says that the cluster expansion converges if incompatible neighbors of every polymer are sufficiently small. A useful schematic version is the Kotecký–Preiss condition: choose a nonnegative size function $a(X)$ such that

$$
\sum_{Y\nsim X} |K(Y)|e^{a(Y)}\leq a(X)
\qquad\text{for every }X.
$$

Then the expansion for $\log Z$ converges absolutely and uniformly in finite volume, with bounds controlled by $a(X)$. More refined versions add a second weight $b(X)$, improve constants, or use tree-graph estimates.

The criterion should be read as a locality–smallness statement. The activity of a polymer must decay fast enough with its size and with the number of incompatible neighbors. In a block lattice, a common target bound is

$$
\|K(X)\|\leq C\epsilon^{|X|}e^{-\kappa |X|}
$$

for small $\epsilon$ and positive $\kappa$, although real constructive RG norms are more delicate because fields can be large and derivatives matter.

## Polymer activities in constructive RG

In a scale-by-scale RG proof, the effective object at scale $j$ is often split into a local factor and a polymer remainder. A schematic finite-volume form is

$$
Z_j(\phi)
=\sum_{\{X_1,\ldots,X_n\}\ \mathrm{compatible}}
\prod_i K_j(X_i,\phi)
\prod_{B\notin X_1\cup\cdots\cup X_n} I_j(B,\phi),
$$

where $B$ ranges over scale-$j$ blocks. The factor $I_j$ contains the local part of the interaction on a single block, while $K_j$ contains nonlocal remainders, irrelevant interactions, or errors generated by previous RG steps.

One often writes this symbolically with a circle product,

$$
Z_j=I_j\circ K_j.
$$

The RG step integrates a fluctuation field and then rewrites the result in the same form:

$$
\mathbb E_{C_{j+1}}(I_j\circ K_j)(\phi+\zeta)
= I_{j+1}\circ K_{j+1}(\phi).
$$

This formula is not a formal decoration. It is a bookkeeping device for a proof. The local extraction sends the dangerous relevant and marginal parts into $I_{j+1}$, while the norm estimates show that $K_{j+1}$ remains small.

A useful mental model is:

| Object | Role in RG |
|---|---|
| $I_j(B)$ | Local coupling coordinates on a block. |
| $K_j(X)$ | Polymer activity containing controlled nonlocal remainder. |
| extraction | Moves local relevant/marginal pieces from $K_j$ into $I_j$. |
| norm on $K_j$ | Quantifies smallness, field growth, derivatives, and decay. |
| cluster expansion | Converts polymer smallness into connected estimates. |

## Connected correlations

Polymer expansions do not only compute free energy. If source insertions or observables are added to the activities, derivatives of $\log Z[J]$ generate connected correlations. The connectedness of the incompatibility graph then becomes the analytic origin of clustering estimates.

For example, if a source-supported polymer activity records insertions near regions $A$ and $B$, a connected two-point function requires a connected polymer cluster joining the two regions. If activities have exponential size or distance decay, the connected clusters are suppressed at large separation. This is one rigorous route from local smallness to exponential clustering in massive phases.

The same idea underlies many high-temperature expansions, low-temperature contour expansions, and constructive estimates in massive Euclidean field theories. The details differ, but the slogan is stable:

$$
\text{connected observable}
=\text{sum over connected polymer clusters touching it}.
$$

## What polymer expansions prove

A successful polymer expansion can prove several types of statements.

| Output | What must be controlled |
|---|---|
| Existence of thermodynamic limit | Uniform convergence of $\log Z(\Lambda)/|\Lambda|$. |
| Analyticity in couplings | Uniform analytic bounds on activities. |
| Exponential clustering | Distance decay of connected polymer clusters. |
| RG stability | Smallness of $K_j$ after each scale integration. |
| Locality of effective action | Extraction bounds and decay of polymer tails. |

The theorem usually does not say that the original path integral was easy. It says that, after a clever decomposition, all dangerous pieces have been put into finitely many local coordinates and the remaining gas of polymers is small enough to control.

## Common pitfalls

**Thinking a polymer is a physical polymer.** The word is borrowed from statistical mechanics. In constructive RG, a polymer is usually a connected set of blocks carrying a local activity, not necessarily a molecule or stringlike excitation.

**Expanding before proving smallness.** A formal sum over connected clusters is cheap. The theorem begins when one proves a criterion such as Kotecký–Preiss or a model-specific norm bound uniformly in volume and scale.

**Confusing compatibility with independence.** Compatible polymers need not be probabilistically independent. Compatibility is a combinatorial rule for which activities may appear together in the representation.

**Ignoring field dependence.** In QFT, activities are often functions of a background field. Bounds must control large fields, derivatives, and covariance integration, not only numerical polymer weights.

**Forgetting the local extraction.** In constructive RG, polymer expansions are paired with a projection onto local relevant and marginal terms. Without extraction, the remainder generally will not stay small under iteration.

## Relations to other pages

- [Wilsonian RG: Rigorous View](/rigorous-qft/rigorous-renormalization-rg/wilsonian-rg-rigorous-view/) explains the scale-by-scale RG map whose remainders are represented by polymer activities.
- [Rigorous φ⁴ Renormalization](/rigorous-qft/rigorous-renormalization-rg/rigorous-phi-four-renormalization/) uses scalar models as the standard testing ground for local counterterms plus polymer remainders.
- [Multiscale Analysis](/rigorous-qft/rigorous-renormalization-rg/multiscale-analysis/) explains the covariance and momentum/position-scale decompositions that produce the block structure.
- [Cluster Expansions](/rigorous-qft/constructive-qft/cluster-expansions/) gives the broader constructive-QFT and statistical-mechanics context for connected expansions.
- [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/) explains why uniform estimates are needed before cutoff removal.

## Research status

The abstract theory of polymer and cluster expansions is mature. It is a standard part of rigorous statistical mechanics and constructive QFT, with many versions adapted to high-temperature expansions, contour models, Mayer expansions, Euclidean field theory, fermionic systems, and multiscale RG.

The active part is model-dependent implementation. For a hard QFT, one must choose the blocks, regulators, norms, covariance decomposition, extraction map, and large-field controls so that the polymer activities obey the required smallness bounds. That is why polymer expansions are best understood as a technology inside a proof, not as a standalone magic formula.

## Exercises

### Exercise 1: Why connected clusters appear in the logarithm

Let

$$
Z=\sum_{\Gamma\ \mathrm{compatible}}\prod_{X\in\Gamma}K(X)
$$

for a finite polymer set. Explain why disconnected families should exponentiate and why $\log Z$ should be built from connected incompatibility clusters.

<details>
<summary><strong>Solution</strong></summary>

If the incompatibility graph splits into two disconnected parts, the choices of polymers in the two parts factorize. The exponential formula in combinatorics says that a partition function built from arbitrary assemblies is the exponential of the generating function for connected assemblies. Here “connected” means connected in the incompatibility graph, not necessarily geometrically connected after taking the union.

</details>

### Exercise 2: Check a small polymer system

Suppose there are two incompatible polymers $X\nsim Y$ with activities $K(X)=a$ and $K(Y)=b$. Compute $Z$ and $\log Z$ through order $ab$.

<details>
<summary><strong>Solution</strong></summary>

The compatible families are $\varnothing$, $\{X\}$, and $\{Y\}$, but not $\{X,Y\}$. Therefore

$$
Z=1+a+b.
$$

Expanding the logarithm gives

$$
\log Z=a+b-\frac12(a+b)^2+O(K^3)
=a+b-\frac12a^2-ab-\frac12b^2+O(K^3).
$$

The mixed connected term is $-ab$, reflecting the incompatibility edge between $X$ and $Y$.

</details>

### Exercise 3: Interpret the Kotecký–Preiss condition

Assume all polymers have the same activity size $|K(X)|\leq \epsilon$ and every polymer is incompatible with at most $N$ others. What rough smallness condition follows from

$$
\sum_{Y\nsim X}|K(Y)|e^{a(Y)}\leq a(X)
$$

if $a(X)=1$?

<details>
<summary><strong>Solution</strong></summary>

The left side is bounded by $N\epsilon e$. Thus a sufficient rough condition is

$$
N\epsilon e\leq 1.
$$

Real polymer systems have polymers of many sizes and many incompatibilities, so one chooses $a(X)$ to grow with size. The exercise shows the basic idea: activity smallness must beat the number of possible incompatible neighbors.

</details>

## References

### Standard first pass

- D. C. Brydges, “A Short Course on Cluster Expansions,” in *Critical Phenomena, Random Systems, Gauge Theories*, Les Houches Session XLIII, Elsevier, 1986. [PDF](https://secure.math.ubc.ca/~db5d/Seminars/les_houches_84.pdf).
- R. Kotecký and D. Preiss, “Cluster Expansion for Abstract Polymer Models,” *Communications in Mathematical Physics* **103** (1986) 491–498. [doi:10.1007/BF01211762](https://doi.org/10.1007/BF01211762).
- V. Rivasseau, *From Perturbative to Constructive Renormalization*, Princeton University Press, 1991.

### Deeper references

- D. C. Brydges and T. Kennedy, “Mayer Expansions and the Hamilton–Jacobi Equation,” *Journal of Statistical Physics* **48** (1987) 19–49. [doi:10.1007/BF01010398](https://doi.org/10.1007/BF01010398).
- A. Abdesselam and V. Rivasseau, “Trees, Forests and Jungles: A Botanical Garden for Cluster Expansions,” 1994. [arXiv:hep-th/9409094](https://arxiv.org/abs/hep-th/9409094).
- R. Fernández and A. Procacci, “Cluster Expansion for Abstract Polymer Models. New Bounds from an Old Approach,” *Communications in Mathematical Physics* **274** (2007) 123–140. [arXiv:math-ph/0605041](https://arxiv.org/abs/math-ph/0605041).
- R. Bauerschmidt, D. C. Brydges, and G. Slade, *Introduction to a Renormalisation Group Method*. [arXiv:1907.05474](https://arxiv.org/abs/1907.05474).

## Version history

- **2026-07-01:** Initial polished draft.
