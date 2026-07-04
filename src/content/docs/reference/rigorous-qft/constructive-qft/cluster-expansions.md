---
title: "Cluster Expansions"
description: "A practical guide to cluster and polymer expansions as convergence tools in constructive quantum field theory."
sidebar:
  label: "Cluster Expansions"
  order: 9
level: Advanced
status: "Polished draft"
source: "Glimm–Jaffe–Spencer cluster expansions; Ruelle statistical mechanics; Kotecký–Preiss polymer expansions; Brydges–Kennedy forest formulas."
topics:
  - constructive QFT
  - cluster expansions
  - polymer expansions
  - analyticity
  - exponential clustering
canonicalTopics:
  - constructive-quantum-field-theory
  - cluster-expansion
  - polymer-expansion
  - euclidean-quantum-field-theory
researchStatus:
  established:
    - "Cluster and polymer expansions are standard rigorous tools for proving convergence, analyticity, thermodynamic limits, and exponential clustering in suitable constructive and statistical-mechanical regimes."
  active:
    - "The difficult part in modern constructive QFT is often not the abstract expansion theorem itself, but finding a representation whose polymer activities obey the required smallness estimates uniformly in the relevant cutoff or scale."
---

## Summary

A cluster expansion is a way to turn a complicated partition function into a convergent sum over connected objects. In constructive QFT, it is one of the main technologies that turns a regularized Euclidean model into theorems about infinite-volume limits, analyticity in parameters, exponential decay of connected correlations, and sometimes particle structure.

The most common abstract form is a polymer gas. There is a set of finite objects $\mathcal P$ called polymers, an incompatibility relation $\not\sim$, and activities $w(\gamma)$. The partition function is

$$
Z
=
\sum_{\Gamma\text{ compatible}}
\prod_{\gamma\in\Gamma} w(\gamma),
$$

where compatible means that every pair of distinct polymers in $\Gamma$ is mutually compatible. The cluster expansion is the corresponding expansion of $\log Z$:

$$
\log Z
=
\sum_{n\geq 1}\frac{1}{n!}
\sum_{\gamma_1,\ldots,\gamma_n}
\Phi^T(\gamma_1,\ldots,\gamma_n)
\prod_{j=1}^n w(\gamma_j).
$$

Here $\Phi^T$ is a truncated or connected coefficient. It vanishes unless the incompatibility graph on $\{\gamma_1,\ldots,\gamma_n\}$ is connected. That single word, connected, is the whole reason cluster expansions are useful.

This page explains the method at the level needed for constructive QFT: what the polymers are, why connected clusters appear in logarithms and connected correlators, what convergence estimates look like, and what such estimates do and do not prove.

## Prerequisites

You should know [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/), [Euclidean Measures](/rigorous-qft/constructive-qft/euclidean-measures/), [Gaussian Measures](/rigorous-qft/constructive-qft/gaussian-measures/), [P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/), and [φ⁴₃ Theory](/rigorous-qft/constructive-qft/phi-four-three/). The page also uses the language of connected correlations from [Schwinger Functions](/rigorous-qft/osterwalder-schrader-euclidean-qft/schwinger-functions/).

## Core idea

The mental model is simple: after regularization, a QFT has many local degrees of freedom. One tries to rewrite the measure so that most of spacetime is boring and the nontrivial behavior is carried by sparse finite regions. Those regions are the polymers.

The expansion then separates two questions:

1. **Combinatorics:** if polymers are sufficiently small in weight, a general theorem turns the partition function into a convergent connected-cluster series.
2. **Analysis:** for the specific QFT, prove that the polymer weights are actually small enough, uniformly in the regulators being removed.

The combinatorics is universal. The analysis is where QFT enters.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Cluster expansion as a map from local polymers to connected clusters and logarithms.](/figures/rigorous-qft/cluster-expansion-polymer-gas.svg)

<figcaption>

A cluster expansion rewrites a dilute gas of local polymers as a connected-cluster expansion for $\log Z$ and connected Schwinger functions. The same schematic applies to high-temperature expansions, phase-cell expansions, and many constructive RG decompositions.

</figcaption>
</figure>

## Setup and conventions

Take a finite Euclidean volume $\Lambda$, usually divided into unit cubes or scale-dependent blocks. A polymer is a finite connected union of blocks together with whatever local data the representation keeps: fields above a threshold, contours between phases, local interaction insertions, fermion lines, or multiscale fluctuation data.

Write $\gamma\subset\Lambda$ for a polymer and $|\gamma|$ for its size. Two polymers are incompatible, written

$$
\gamma\not\sim\gamma',
$$

when they overlap or violate a required separation rule. A compatible family is a finite set $\Gamma$ of polymers satisfying $\gamma\sim\gamma'$ for all distinct $\gamma,\gamma'\in\Gamma$.

The polymer partition function is

$$
Z_\Lambda
=
\sum_{\Gamma\subset\mathcal P(\Lambda)\text{ compatible}}
\prod_{\gamma\in\Gamma}w(\gamma).
$$

The activity $w(\gamma)$ contains all analytic information: couplings, Gaussian integrals, determinant estimates, boundary conditions, and scale factors. The cluster expansion is useful only if these activities decay quickly enough with size and interaction range.

## Connected clusters from logarithms

For a hard-core polymer gas, define the incompatibility graph of an ordered list $(\gamma_1,\ldots,\gamma_n)$ to have vertices $1,\ldots,n$ and an edge $ij$ when $\gamma_i\not\sim\gamma_j$. The truncated coefficient is

$$
\Phi^T(\gamma_1,\ldots,\gamma_n)
=
\sum_{G\in\mathcal G_c(n)}
\prod_{ij\in E(G)}
\left(-\mathbf 1_{\gamma_i\not\sim\gamma_j}\right),
$$

where $\mathcal G_c(n)$ is the set of connected graphs on $n$ labeled vertices. For $n=1$, set $\Phi^T(\gamma_1)=1$.

The formal identity is

$$
\log Z_\Lambda
=
\sum_{n\geq1}\frac{1}{n!}
\sum_{\gamma_1,\ldots,\gamma_n}
\Phi^T(\gamma_1,\ldots,\gamma_n)
\prod_{j=1}^n w(\gamma_j).
$$

This is the polymer analogue of the linked-cluster theorem in perturbative QFT: vacuum diagrams exponentiate, and the logarithm keeps only connected diagrams. The difference is that a constructive cluster expansion is not merely formal. It comes with absolute convergence estimates.

A typical convergence criterion is the Kotecký–Preiss condition. Choose a nonnegative size function $a(\gamma)$. If, for every polymer $\gamma$,

$$
\sum_{\gamma'\not\sim\gamma}
|w(\gamma')|e^{a(\gamma')}
\leq a(\gamma),
$$

then the cluster expansion for $\log Z_\Lambda$ converges absolutely, and the total contribution of clusters touching a fixed polymer is controlled. More refined versions include additional weights for diameter, scale, boundary distance, or source insertions.

## Where the polymers come from in QFT

The abstract polymer gas is rarely visible in the original Lagrangian. One has to manufacture it.

In high-temperature or large-mass regimes, the covariance is short-ranged, and local interaction terms can be expanded into connected chunks. In weakly coupled $P(\phi)_2$ models, phase-cell and cluster expansions isolate rare large-field regions and show that the rest behaves perturbatively around a controlled background. In $\phi^4_3$, multiscale decompositions create scale-indexed polymers whose activities include counterterms and fluctuation integrals. In fermionic models such as Gross–Neveu, the smallness often comes from determinant bounds and the anticommuting nature of the fields.

The pattern is always the same:

| Step | Constructive meaning |
|---:|---|
| 1 | Regularize the model in volume, lattice spacing, field cutoff, or momentum scale. |
| 2 | Decompose spacetime into blocks and classify local behavior. |
| 3 | Rewrite the partition function as a sum over finite connected objects. |
| 4 | Prove bounds on the activity $w(\gamma)$. |
| 5 | Apply an abstract convergence theorem. |
| 6 | Extract limits, analyticity, and connected correlation estimates. |

This is why cluster expansions are often hidden behind phrases like phase-cell expansion, polymer expansion, contour expansion, Mayer expansion, or constructive RG expansion. These are different machines, but they share the same connected-cluster backbone.

## Correlations and exponential decay

Partition functions are only the beginning. QFT cares about correlation functions. Suppose $A$ and $B$ are local observables supported near regions $X$ and $Y$. A polymer expansion with insertions rewrites

$$
\langle A B\rangle_\Lambda-
\langle A\rangle_\Lambda\langle B\rangle_\Lambda
$$

as a sum over connected clusters linking $X$ to $Y$. If the activity estimates include an exponential diameter weight, then clusters spanning a distance $R=\operatorname{dist}(X,Y)$ are exponentially suppressed:

$$
\left|
\langle A B\rangle_\Lambda-
\langle A\rangle_\Lambda\langle B\rangle_\Lambda
\right|
\leq C_{A,B} e^{-mR}.
$$

Such estimates are the constructive form of clustering. In an OS-positive Euclidean theory, sufficiently strong exponential clustering of Schwinger functions is closely tied to a mass gap in the reconstructed Lorentzian theory, though the exact spectral conclusion depends on the hypotheses and on which functions are controlled.

Cluster expansions also prove analyticity. If $w(\gamma)$ depends analytically on a coupling $g$ and the convergence criterion is uniform for $g$ in a complex neighborhood, then $\log Z$ and local correlation functions are analytic in $g$ in that neighborhood. This is one reason cluster expansions are so powerful in weak-coupling, high-temperature, and strong-field regimes.

## What the method proves

A good cluster expansion can prove several different kinds of statement.

| Output | Typical meaning |
|---|---|
| Thermodynamic limit | $|\Lambda|^{-1}\log Z_\Lambda$ and local correlations converge as $\Lambda\nearrow\mathbb R^d$. |
| Boundary insensitivity | Local correlations far from the boundary have limits independent of many boundary conditions. |
| Analyticity | Pressure and correlations are analytic in a coupling, field, activity, or inverse temperature. |
| Exponential clustering | Truncated correlations decay like $e^{-m|x-y|}$ in a phase. |
| Phase selection | Different boundary conditions select distinct pure phases in a multiphase region. |
| Error control | Truncated cluster sums come with explicit tails and uniform estimates. |

The method does not automatically prove critical behavior. Near a second-order phase transition, correlation lengths diverge and ordinary small-polymer estimates fail. One then needs renormalization-group methods, lace expansions, infrared bounds, conformal methods, or model-specific exact techniques.

## A minimal worked example

Let there be two polymers $\gamma_1$ and $\gamma_2$ with activities $u$ and $v$. If they are compatible, then

$$
Z=(1+u)(1+v),
\qquad
\log Z=\log(1+u)+\log(1+v).
$$

There is no connected contribution linking them. If they are incompatible, the simultaneous configuration is forbidden, so

$$
Z=1+u+v.
$$

Expanding the logarithm gives

$$
\log(1+u+v)
=
\log(1+u)+\log(1+v)-uv+O(u^2v,uv^2).
$$

The mixed term is precisely the connected correction caused by incompatibility. A full cluster expansion is the systematic, convergent version of this observation for arbitrarily many polymers.

## Common pitfalls

**Confusing cluster expansion with cluster decomposition.** A cluster expansion is a proof method. Cluster decomposition is a physical or axiomatic property of correlations at large separation. A cluster expansion can prove cluster decomposition in suitable regimes, but the words do not mean the same thing.

**Expanding without a small parameter.** The small parameter may be a coupling, an activity, a large mass, a high temperature, a large field, or a scale-dependent RG norm. If no norm makes the activities small enough, the formal expansion is just formal.

**Ignoring connectedness.** The logarithm of the partition function and connected correlations keep connected clusters. Forgetting this is the most common way to lose volume factors and get false divergent estimates.

**Treating the abstract criterion as the hard theorem.** Kotecký–Preiss-type theorems are powerful, but the model-specific burden is proving their hypotheses uniformly in the cutoffs. In QFT, that is usually the main work.

**Expecting one expansion to cover all phases.** A cluster expansion is usually adapted to a phase or a parameter regime. A low-temperature contour expansion, a high-temperature expansion, and a critical RG analysis are different tools.

## Relations to other pages

- [Constructive Program](/rigorous-qft/constructive-qft/constructive-program/) explains why cutoff removal and uniform estimates are the central tasks.
- [P(φ)₂ Models](/rigorous-qft/constructive-qft/p-phi-two-models/) and [φ⁴₂ Theory](/rigorous-qft/constructive-qft/phi-four-two/) are the scalar examples where cluster expansions help control infinite-volume and particle-structure questions.
- [φ⁴₃ Theory](/rigorous-qft/constructive-qft/phi-four-three/) explains why multiscale estimates and counterterms become more demanding in three dimensions.
- [Gross–Neveu Model: Preview](/rigorous-qft/constructive-qft/gross-neveu-model-preview/) points toward fermionic expansions, determinant bounds, and constructive RG.
- [Correlation Inequalities](/rigorous-qft/constructive-qft/correlation-inequalities/) gives a complementary nonperturbative tool: inequalities rather than convergent series.

## Research status

Cluster expansions are established mathematics in statistical mechanics and constructive QFT. They have rigorous abstract convergence theorems, many model-specific implementations, and a long record of applications to low-dimensional constructive field theory.

Their limitation is equally important: they are not a universal solution to continuum QFT. Critical theories, massless fields, gauge theories, and four-dimensional interacting continuum limits usually require additional structure. Modern constructive RG can be viewed as a scale-by-scale descendant of the same philosophy, but its estimates are more subtle than a single polymer-gas criterion.

## Exercises

### Exercise 1: Two polymers

Let two polymers have activities $u$ and $v$. Compute $\log Z$ through order $uv$ when they are compatible and when they are incompatible.

<details>
<summary><strong>Solution</strong></summary>

If compatible,

$$
Z=1+u+v+uv=(1+u)(1+v),
$$

so

$$
\log Z=\log(1+u)+\log(1+v),
$$

and there is no mixed connected term. If incompatible,

$$
Z=1+u+v,
$$

so

$$
\log Z=u+v-\frac12(u+v)^2+O(3)
=u+v-\frac12u^2-uv-\frac12v^2+O(3).
$$

The mixed term is $-uv$, the first connected incompatibility correction.

</details>

### Exercise 2: Why disconnected graphs do not contribute

For three polymers, suppose the incompatibility graph has one edge between $1$ and $2$ and polymer $3$ is compatible with both. Explain why there is no contribution to $\Phi^T(\gamma_1,\gamma_2,\gamma_3)$.

<details>
<summary><strong>Solution</strong></summary>

The coefficient $\Phi^T$ sums only connected graphs on the vertex set $\{1,2,3\}$, with an edge allowed only where polymers are incompatible. Since vertex $3$ has no incompatibility edge to $1$ or $2$, no connected graph on all three vertices can be formed. Thus $\Phi^T(\gamma_1,\gamma_2,\gamma_3)=0$.

</details>

### Exercise 3: Exponential clustering from polymer size

Assume every connected cluster linking two regions $X$ and $Y$ has total size at least $c\,\operatorname{dist}(X,Y)$, and the sum of cluster weights of size $N$ is bounded by $C e^{-\alpha N}$. Show the connected correlation is exponentially decaying.

<details>
<summary><strong>Solution</strong></summary>

Let $R=\operatorname{dist}(X,Y)$. Only clusters of size $N\ge cR$ contribute. Therefore

$$
\sum_{N\ge cR} C e^{-\alpha N}
=
C\frac{e^{-\alpha cR}}{1-e^{-\alpha}}.
$$

This has the form $C' e^{-mR}$ with $m=\alpha c$ and $C'=C/(1-e^{-\alpha})$.

</details>

## References

### Standard first pass

- David Ruelle, *Statistical Mechanics: Rigorous Results*, W. A. Benjamin, 1969; World Scientific reprint, 1999. DOI: [10.1142/4090](https://doi.org/10.1142/4090).
- James Glimm and Arthur Jaffe, *Quantum Physics: A Functional Integral Point of View*, second edition, Springer, 1987. DOI: [10.1007/978-1-4612-4728-9](https://doi.org/10.1007/978-1-4612-4728-9).
- Vincent Rivasseau, *From Perturbative to Constructive Renormalization*, Princeton University Press, 1991. DOI: [10.1515/9781400862085](https://doi.org/10.1515/9781400862085).

### Deeper references

- James Glimm, Arthur Jaffe, and Thomas Spencer, "The Particle Structure of the Weakly Coupled $P(\phi)_2$ Model and Other Applications of High Temperature Expansions, Part II: The Cluster Expansion," in *Constructive Quantum Field Theory*, Lecture Notes in Physics 25, Springer, 1973. DOI for volume: [10.1007/BFb0113079](https://doi.org/10.1007/BFb0113079).
- James Glimm, Arthur Jaffe, and Thomas Spencer, "The Wightman Axioms and Particle Structure in the $P(\phi)_2$ Quantum Field Model," *Annals of Mathematics* **100** (1974), 585–632. DOI: [10.2307/1970959](https://doi.org/10.2307/1970959).
- James Glimm, Arthur Jaffe, and Thomas Spencer, "A Convergent Expansion about Mean Field Theory. I. The Expansion," *Annals of Physics* **101** (1976), 610–630. DOI: [10.1016/0003-4916(76)90026-9](https://doi.org/10.1016/0003-4916(76)90026-9).
- James Glimm, Arthur Jaffe, and Thomas Spencer, "A Convergent Expansion about Mean Field Theory. II. Convergence of the Expansion," *Annals of Physics* **101** (1976), 631–669.
- Roman Kotecký and David Preiss, "Cluster Expansion for Abstract Polymer Models," *Communications in Mathematical Physics* **103** (1986), 491–498. DOI: [10.1007/BF01211762](https://doi.org/10.1007/BF01211762).
- David C. Brydges and Tom Kennedy, "Mayer Expansions and the Hamilton–Jacobi Equation," *Journal of Statistical Physics* **48** (1987), 19–49. DOI: [10.1007/BF01010398](https://doi.org/10.1007/BF01010398).
- Roberto Fernández and Aldo Procacci, "Cluster Expansion for Abstract Polymer Models. New Bounds from an Old Approach," *Communications in Mathematical Physics* **274** (2007), 123–140. arXiv: [math-ph/0605041](https://arxiv.org/abs/math-ph/0605041).

## Version history

- **2026-06-29:** Initial page on cluster expansions in constructive QFT.
