---
title: "Blocking and Coarse Graining"
description: "Explains Kadanoff blocking, real-space coarse graining, exact blocking kernels, rescaling, and their relation to Wilsonian RG and universality."
sidebar:
  label: "Blocking and Coarse Graining"
  order: 7
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Zinn-Justin 2021; Kadanoff scaling ideas; Polyakov 1987; Schwartz ch. 23; Burgess chs. 2–3; Altland and Simons ch. 6."
topics:
  - blocking
  - coarse graining
  - Kadanoff blocks
  - Wilsonian RG
  - real-space RG
  - lattice field theory
canonicalTopics:
  - blocking-transformation
  - coarse-graining
  - real-space-renormalization-group
  - kadanoff-blocking
  - wilsonian-rg-map
researchStatus:
  established:
    - "Blocking and coarse graining are standard real-space formulations of Wilsonian RG: short-distance degrees of freedom are integrated out, new effective interactions are generated, and the result is rescaled for comparison."
  active:
    - "Exact real-space RG transformations, tensor-network coarse graining, gauge-invariant blocking, Monte Carlo RG, and continuum definitions of coarse graining remain important research tools."
---

## Summary

**Blocking** is the real-space version of Wilsonian renormalization. Instead of integrating out a thin shell of high momenta, one groups nearby microscopic degrees of freedom into blocks, defines a coarser variable for each block, and computes the effective action for the block variables.

For a lattice system with microscopic variables $s$ and coarse variables $S$, an exact blocking transformation can be written schematically as

$$
e^{-S'[S]}
=
\sum_s K[S,s]e^{-S[s]},
$$

where $K[S,s]$ is a blocking kernel. In a continuum Euclidean path integral, the analogous expression is

$$
e^{-S'[\Phi]}
=
\int\mathcal D\phi\,K[\Phi,\phi]e^{-S[\phi]}.
$$

After blocking, the lattice spacing has increased from $a$ to $a'=ba$. To compare with the original description, one rescales coordinates and fields. Blocking plus rescaling defines an RG map on theory space.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![A real-space blocking transformation: microscopic lattice variables are grouped into blocks, replaced by coarse variables, then rescaled to produce a new effective action](/figures/renormalization-rg-eft/blocking-coarse-graining-map.svg)

<figcaption>

A blocking step replaces microscopic variables at lattice spacing $a$ by block variables at spacing $a'=ba$. The effective action for the block variables contains every interaction allowed by symmetry. After rescaling lengths and fields, the result is another point in theory space.

</figcaption>
</figure>

:::note[Not just averaging]
Coarse graining is not merely drawing a blurry picture. It is a change of description that preserves long-distance observables by integrating over the microscopic variables inside each block. The price is that the effective action becomes more complicated.
:::

## Prerequisites

You should know [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/), and [Momentum-Shell RG](/renormalization-rg-eft/wilsonian-renormalization/momentum-shell-rg/). The geometric interpretation is developed in [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/), and the reason blocking leads to universal behavior is explained in [Universality](/renormalization-rg-eft/wilsonian-renormalization/universality/).

No lattice field theory background is required. The lattice here is mainly a clean way to say what coarse graining means.

## Core idea

A long-distance observer does not need to know every microscopic variable separately. If a spin system has lattice spacing $a$, one can group spins into blocks of linear size $ba$ and describe the system using one effective variable per block. If the correlation length $\xi$ is much larger than $a$, there can be a wide window

$$
a\ll ba\ll \xi
$$

where the block variables still resolve the long-distance physics but no longer track microscopic detail.

Kadanoff's physical picture is that critical systems look statistically similar after blocking and rescaling. Wilson's upgrade is that the blocking operation should be treated as a map on the whole action, not just as a hand-wavy picture of larger spins. The map generates new couplings, changes old couplings, and flows through theory space.

The essential cycle is

$$
\text{block}
\longrightarrow
\text{integrate internal variables}
\longrightarrow
\text{generate a new action}
\longrightarrow
\text{rescale}
\longrightarrow
\text{repeat}.
$$

At a fixed point, this cycle returns the same statistical theory after rescaling.

## Setup and conventions

This page uses Euclidean statistical-field-theory notation. A microscopic lattice has spacing $a$ and variables $s_x$. A block transformation with scale factor $b>1$ partitions the lattice into blocks $B_X$, labelled by coarse sites $X$, with new spacing

$$
a'=ba.
$$

A block variable $S_X$ is a chosen function, or probabilistic function, of the microscopic variables in $B_X$. Examples include

$$
S_X=\operatorname{sign}\left(\sum_{x\in B_X}s_x\right)
$$

for majority-rule Ising blocking, or

$$
\Phi_X=\frac{1}{|B_X|}\sum_{x\in B_X}\phi_x
$$

for a simple scalar-field average. The normalization may be modified by powers of $b$ so that the blocked field has convenient scaling dimension.

The Wilsonian infrared RG time is

$$
\ell=\log b
$$

for one blocking step, or $\ell=n\log b$ after $n$ identical steps.

## Blocking kernels

The most flexible way to define blocking is with a kernel $K[S,s]$. For a spin system,

$$
e^{-S'[S]}
=
\sum_{\{s_x\}}K[S,s]e^{-S[s]}.
$$

The kernel specifies how coarse configurations are related to microscopic configurations. It may be sharp, as in a delta-function constraint, or probabilistic, as in a noisy majority rule.

A useful normalization condition is

$$
\sum_{\{S_X\}}K[S,s]=1.
$$

Then the partition function is preserved up to a possible constant normalization:

$$
Z'=
\sum_{\{S_X\}}e^{-S'[S]}
=
\sum_{\{s_x\}}e^{-S[s]}
=Z.
$$

In continuum notation one writes

$$
e^{-S'[\Phi]}
=
\int\mathcal D\phi\,K[\Phi,\phi]e^{-S[\phi]},
$$

with

$$
\int\mathcal D\Phi\,K[\Phi,\phi]=1.
$$

The blocking kernel is part of the RG scheme. Different kernels define different coordinates and different trajectories in theory space, but they should give the same universal fixed-point data when used consistently.

## The new action contains everything

After blocking, the action is usually not of the same simple form as the microscopic action.

Start with a nearest-neighbor Ising Hamiltonian,

$$
H[s]=-K\sum_{\langle xy\rangle}s_xs_y.
$$

A blocking step generally generates

$$
H'[S]
=
-K_1'\sum_{\langle XY\rangle}S_XS_Y
-K_2'\sum_{\langle\langle XY\rangle\rangle}S_XS_Y
-K_4'\sum_{\square}S_XS_YS_ZS_W
-\cdots.
$$

The dots are not a failure of the method. They are the method. Integrating out variables generates every interaction allowed by the symmetries. A truncation to a small number of couplings is an approximation, not an exact RG transformation.

The same lesson holds in continuum field theory. A blocked scalar action may include

$$
\phi^2,
\quad
(\partial\phi)^2,
\quad
\phi^4,
\quad
\phi^6,
\quad
\phi^2(\partial\phi)^2,
\quad
(\partial^2\phi)^2,
\quad
\ldots
$$

even if the microscopic action started with only the first few terms. Wilsonian RG lives naturally in infinite-dimensional theory space.

:::tip[Truncations need humility]
A two-coupling recursion relation can be useful, but it is not the exact RG unless the omitted couplings are known to be irrelevant or absent by symmetry. The RG does not promise that your favorite finite-dimensional ansatz is closed.
:::

## Blocking plus rescaling

Blocking alone increases the lattice spacing:

$$
a\longrightarrow a'=ba.
$$

To compare the blocked theory to the original theory, one rescales coordinates:

$$
x'=\frac{x}{b}.
$$

One also rescales fields. If a field has scaling dimension $\Delta_\phi$, then near a fixed point one writes schematically

$$
\phi'(x')=b^{\Delta_\phi}\Phi(x).
$$

The precise normalization convention depends on the field and on the RG scheme. The point is that blocking without rescaling changes the resolution, while blocking plus rescaling returns the system to the same cutoff scale so that couplings can be compared.

Thus an RG step has two logically distinct parts:

| Step | What it does | Why it matters |
|---|---|---|
| Coarse grain | integrates microscopic variables into block variables | removes short-distance detail |
| Rescale | restores the cutoff or lattice spacing | allows comparison with the original action |

A fixed point is fixed under the combined operation, not under ordinary averaging alone.

## Example: exact decimation in the one-dimensional Ising model

The simplest exact real-space RG example is the one-dimensional Ising model with no magnetic field:

$$
H[s]=-K\sum_i s_i s_{i+1},
\qquad s_i=\pm1.
$$

Decimate the odd spins. For two neighboring even spins $s_i$ and $s_{i+2}$,

$$
\sum_{s_{i+1}=\pm1}
\exp\left[Ks_i s_{i+1}+Ks_{i+1}s_{i+2}\right]
=
2\cosh\left(K(s_i+s_{i+2})\right).
$$

If $s_i=s_{i+2}$, this is $2\cosh(2K)$. If $s_i=-s_{i+2}$, this is $2$. Write the result as

$$
A\exp\left(K' s_i s_{i+2}\right).
$$

Then

$$
A e^{K'}=2\cosh(2K),
\qquad
A e^{-K'}=2.
$$

Dividing gives

$$
e^{2K'}=\cosh(2K),
\qquad
K'=\frac12\log\cosh(2K).
$$

For small $K$,

$$
K'=K^2+O(K^4),
$$

so high temperature flows toward $K=0$. For any finite temperature in one dimension, repeated decimation eventually flows to the disordered fixed point. Only $K=\infty$, the zero-temperature point, avoids this fate.

This example is pedagogically useful because the blocking can be done exactly. It is also a warning: exact blocking is rare, and low-dimensional examples can have special features.

## Momentum-shell RG versus real-space blocking

Momentum-shell RG and real-space blocking are two languages for the same Wilsonian idea.

| Momentum-shell RG | Real-space blocking |
|---|---|
| splits fields into slow and fast Fourier modes | groups nearby degrees of freedom into blocks |
| integrates $\Lambda/b<|p|<\Lambda$ | integrates microscopic variables inside blocks |
| natural for perturbation theory | natural for statistical systems and numerical coarse graining |
| keeps translation invariance manifest | keeps locality and physical averaging vivid |
| can be awkward with sharp cutoffs and gauge symmetry | can be awkward to make exact or analytically tractable |

In a continuum weak-coupling calculation, momentum-shell RG is often easier. In lattice statistical mechanics, tensor networks, Monte Carlo RG, and conceptual discussions of universality, blocking is often clearer.

A good physicist should be bilingual. The slogan

$$
\text{integrate out high momenta}
$$

and the slogan

$$
\text{average over short-distance blocks}
$$

are not identical operations in every regulator, but they express the same principle: remove short-distance information while preserving the long-distance questions one cares about.

## Locality after coarse graining

A common worry is that integrating out variables might make the effective action nonlocal. In principle it can. In the situations where Wilsonian RG works cleanly, locality survives in a controlled form.

If the microscopic theory is local and the blocking scale is finite, then the blocked action is usually **quasi-local**: interactions can extend over several blocks, but their range and derivative expansion are controlled. In continuum language, this means that the effective action can be organized as

$$
S_\Lambda=\sum_i g_i(\Lambda)\int d^d x\,\mathcal O_i(x),
$$

with local operators ordered by scaling dimension, derivative count, or another power-counting scheme.

At a critical point, the correlation length is infinite. That does not mean the Wilsonian action becomes nonlocal. Rather, the action sits near a scale-invariant fixed point. Correlation functions are long-range because the theory is critical, not because the action has become a random nonlocal functional.

There are exceptions and caveats: long-range microscopic interactions, gapless modes that have been integrated out incorrectly, Fermi surfaces, gauge constraints, and real-time open systems can all complicate the locality story. The local Wilsonian expansion is powerful precisely because one learns when it applies.

## Gauge fields and constrained systems

Blocking spin or scalar variables is conceptually straightforward. Gauge fields require more care.

The microscopic gauge potential $A_\mu$ is not itself gauge invariant. On a lattice, the natural variables are link variables or Wilson lines. A gauge-invariant blocking rule should build coarse link variables out of products and averages of fine link variables along paths. Schematically,

$$
U_{X,\mu}^{\text{coarse}}
\sim
\text{blocked product of fine links from }X\text{ to }X+b\hat\mu.
$$

The details matter. A poor blocking rule can obscure gauge redundancy, generate awkward constraints, or make locality hard to see. This is why lattice gauge theory and numerical RG use specialized blocking transformations.

The principle, however, is the same: the coarse variables must be the correct long-distance variables. For gauge theories, that often means Wilson loops, gauge-covariant blocked links, gauge-fixed fields with care, or gauge-invariant operator data.

## Coarse graining observables

Blocking transforms actions, but it also transforms observables. If $\mathcal O[s]$ is a microscopic observable, its blocked version is defined by inserting it into the same conditional average:

$$
\mathcal O'[S]e^{-S'[S]}
=
\sum_s K[S,s]\mathcal O[s]e^{-S[s]}.
$$

This equation is a little masterpiece of bookkeeping. It says that an observable is not automatically the same function of the new variables. It must be matched under the blocking transformation.

This is the real-space version of operator renormalization. Local microscopic operators become linear combinations of scaling operators near a fixed point:

$$
\mathcal O_{\text{micro}}
=
\sum_a c_a\mathcal O_a^{\text{scaling}}.
$$

At long distances, the term with the smallest scaling dimension allowed by the symmetries usually dominates. This is why different microscopic order parameters can have the same critical exponent once they overlap with the same leading scaling operator.

## Coarse graining and information loss

Blocking seems to throw information away. That is true, but it throws away information in a controlled direction.

The partition function and long-distance observables can be preserved if the effective action and blocked observables are defined exactly. What is lost is not physics but microscopic resolution. The exact blocked action stores the effects of eliminated variables in new interactions among block variables.

The practical difficulty is that exact blocked actions are complicated. If one truncates the action to a small set of couplings, information is genuinely discarded. The art is to discard information only in irrelevant directions, or at least to know the error being made.

This is the Wilsonian version of a familiar scientific discipline: model only the variables needed at the scale and accuracy of interest.

## Common pitfalls

**Thinking blocking is just averaging.** Averaging defines candidate coarse variables. The RG step also integrates over microscopic variables and produces a new effective action.

**Forgetting induced interactions.** Blocking almost always generates new couplings. Keeping only the original coupling form is an approximation.

**Skipping the rescaling step.** Without rescaling, one has merely changed the lattice spacing. RG flow is usually the combined operation of coarse graining and rescaling.

**Treating the blocking rule as unique.** Different kernels are different schemes. Universal data should not depend on this choice, but intermediate couplings do.

**Blocking observables incorrectly.** Operators renormalize too. A microscopic spin, density, current, or Wilson loop may map to a combination of scaling operators.

**Assuming locality without checking assumptions.** Locality after coarse graining depends on the microscopic locality, the degrees of freedom retained, and the presence or absence of long-range modes or constraints.

## Relations to other pages

[Momentum-Shell RG](/renormalization-rg-eft/wilsonian-renormalization/momentum-shell-rg/) gives the complementary Fourier-space version of the same idea. [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/) explains why the blocked action should be treated as a point in an infinite-dimensional space. [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/) explains why many induced couplings become unimportant near a fixed point. [Universality](/renormalization-rg-eft/wilsonian-renormalization/universality/) explains how repeated blocking leads to common long-distance behavior.

Later pages on [Exact Renormalization Group](/renormalization-rg-eft/wilsonian-renormalization/exact-renormalization-group/) and [Functional Renormalization Group Preview](/renormalization-rg-eft/wilsonian-renormalization/functional-renormalization-group-preview/) will give continuum versions of exact coarse-graining equations. The later chapters on critical phenomena, EFT, lattice regularization, and nonperturbative QFT all use this logic.

## Research status

The conceptual role of blocking and coarse graining in Wilsonian RG is established. It is one of the standard explanations of universality, critical phenomena, and effective field theory.

The practical implementation remains an active area. Exact real-space RG is difficult because blocking generates infinitely many couplings. Tensor-network RG, Monte Carlo RG, multigrid methods, functional RG, gradient-flow-based smoothing, and gauge-invariant blocking transformations are modern descendants of the same idea. In quantum many-body systems, quantum circuits and entanglement renormalization give a closely related but Hilbert-space-centered view of coarse graining.

The frontier is not whether coarse graining is useful. The frontier is how to choose variables and truncations that preserve the right long-distance structures in strongly coupled, constrained, topological, real-time, or sign-problem-limited systems.

## Exercises

### Exercise 1: One-dimensional Ising decimation

Derive the exact decimation rule

$$
K'=\frac12\log\cosh(2K)
$$

for the one-dimensional nearest-neighbor Ising model with no magnetic field.

<details><summary><strong>Solution</strong></summary>

For two neighboring even spins $s_i$ and $s_{i+2}$, sum over the odd spin $s_{i+1}$:

$$
\sum_{s_{i+1}=\pm1}
\exp\left[Ks_i s_{i+1}+Ks_{i+1}s_{i+2}\right]
=
2\cosh\left(K(s_i+s_{i+2})\right).
$$

If $s_i=s_{i+2}$, this equals $2\cosh(2K)$. If $s_i=-s_{i+2}$, this equals $2$. Match it to

$$
A\exp(K's_i s_{i+2}).
$$

Then

$$
A e^{K'}=2\cosh(2K),
\qquad
A e^{-K'}=2.
$$

Dividing gives

$$
e^{2K'}=\cosh(2K),
$$

so

$$
K'=\frac12\log\cosh(2K).
$$

</details>

### Exercise 2: Partition function preservation

Assume a discrete blocking kernel satisfies

$$
\sum_S K[S,s]=1
$$

for every microscopic configuration $s$. Show that the blocked action defined by

$$
e^{-S'[S]}=\sum_sK[S,s]e^{-S[s]}
$$

has the same partition function as the original action.

<details><summary><strong>Solution</strong></summary>

The blocked partition function is

$$
Z'=\sum_S e^{-S'[S]}
=\sum_S\sum_sK[S,s]e^{-S[s]}.
$$

Exchange the sums:

$$
Z'=\sum_s e^{-S[s]}\sum_S K[S,s].
$$

Using the normalization condition gives

$$
Z'=\sum_s e^{-S[s]}=Z.
$$

Thus the partition function is preserved exactly.

</details>

### Exercise 3: Why rescaling is needed

A blocking step maps a lattice spacing $a$ to $a'=ba$. Explain why this alone is not yet an RG flow on the same theory space chart.

<details><summary><strong>Solution</strong></summary>

After blocking, the theory is written with a different lattice spacing. Its couplings are attached to variables living on a coarser lattice. To compare the blocked theory with the original theory as another point in the same coordinate system, one rescales lengths by $x'=x/b$ so that the cutoff or lattice spacing is restored. One also rescales fields according to their scaling dimensions. The RG map is the combined operation: coarse grain, then rescale.

</details>

### Exercise 4: Operator blocking

Let $\mathcal O[s]$ be a microscopic observable. Define $\mathcal O'[S]$ by

$$
\mathcal O'[S]e^{-S'[S]}
=
\sum_sK[S,s]\mathcal O[s]e^{-S[s]}.
$$

Show that expectation values of $\mathcal O$ in the original theory equal expectation values of $\mathcal O'$ in the blocked theory.

<details><summary><strong>Solution</strong></summary>

The blocked expectation value is

$$
\langle\mathcal O'\rangle'
=\frac{1}{Z'}\sum_S\mathcal O'[S]e^{-S'[S]}.
$$

Using the definition of $\mathcal O'$ gives

$$
\langle\mathcal O'\rangle'
=\frac{1}{Z'}\sum_S\sum_sK[S,s]\mathcal O[s]e^{-S[s]}.
$$

Exchange the sums and use $\sum_S K[S,s]=1$:

$$
\langle\mathcal O'\rangle'
=\frac{1}{Z'}\sum_s\mathcal O[s]e^{-S[s]}.
$$

Since $Z'=Z$, this is

$$
\langle\mathcal O'\rangle'=\langle\mathcal O\rangle.
$$

Thus exact blocking preserves expectation values if observables are blocked along with the action.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Leo P. Kadanoff, scaling and block-spin ideas in critical phenomena.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on RG and critical behavior.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the discussion of statistical systems, continuum limits, and RG ideas.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter 23.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapters 2–3.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, chapter 6.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for a compact introduction to real-space RG intuition.

## Version history

- 2026-06-17: First polished draft. Introduced blocking kernels, exact partition-function preservation, induced interactions, rescaling, Ising decimation, observable blocking, and links to Wilsonian universality.
