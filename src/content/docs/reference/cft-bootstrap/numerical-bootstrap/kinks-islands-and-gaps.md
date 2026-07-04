---
title: "Kinks, Islands, and Gaps"
description: "How numerical bootstrap bounds develop kinks, how spectral gap assumptions produce islands, and how to interpret these features responsibly."
sidebar:
  label: "Kinks, Islands, and Gaps"
  order: 8
level: Graduate
status: "Polished draft"
source: "Poland, Rychkov, and Vichi 2019; Rychkov and Su 2024; El-Showk et al.; Kos, Poland, Simmons-Duffin, and Vichi; numerical bootstrap literature."
topics:
  - bootstrap kinks
  - bootstrap islands
  - spectral gaps
  - numerical conformal bootstrap
  - 3D Ising CFT
canonicalTopics:
  - kinks-islands-and-gaps
  - bootstrap-islands
  - spectral-gap-assumptions
researchStatus:
  established:
    - "Kinks, islands, and gap assumptions are standard interpretive tools in numerical conformal bootstrap, especially in precision studies of the 3D Ising and O(N) models."
  active:
    - "Current work sharpens the interpretation of islands, isolated regions, kinks, spectral assumptions, navigator functions, and rigorous reliability for increasingly complex CFT targets."
---

## Summary

Numerical bootstrap plots have a distinctive visual vocabulary. A **kink** is a sharp feature in a bound curve. An **island** is a small allowed region in a parameter space. A **gap** is an assumption that no operator of a certain type appears below a chosen dimension.

These words are easy to say and easy to misuse. The precise meanings are:

| Term | Meaning | Caution |
|---|---|---|
| kink | sharp feature in an exclusion bound | not automatically a CFT |
| island | small not-excluded region after assumptions | not assumption-free |
| gap | lower bound imposed on the next operator in a sector | can overconstrain if unjustified |
| isolated region | allowed component separated from others | may depend on cutoff and assumptions |
| archipelago | family of islands across parameters or symmetry rank | cute name, serious bookkeeping |

The 3D Ising CFT is the flagship example. Single-correlator scalar bounds show a famous kink. Mixed-correlator bootstrap with $\sigma$ and $\epsilon$, together with physically motivated gap assumptions, isolates a tiny island in the $(\Delta_\sigma,\Delta_\epsilon)$ plane.

The conceptual lesson is

$$
\text{kinks suggest; gaps target; islands isolate}.
$$

None of them replaces the need to state assumptions, check convergence, and compare with independent evidence.

## Prerequisites

Read [Identical Scalar Bounds](/cft-bootstrap/numerical-bootstrap/identical-scalar-bounds/), [Linear Functionals](/cft-bootstrap/numerical-bootstrap/linear-functionals/), [Derivative Truncations](/cft-bootstrap/numerical-bootstrap/derivative-truncations/), and [SDPB Workflow](/cft-bootstrap/numerical-bootstrap/sdpb-workflow/) first.

For physics examples, read [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/) and [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/).

## Core idea

A bootstrap bound is an exclusion boundary. A kink is a place where the boundary changes direction sharply. This often happens because the extremal solution on one side has a different operator content from the extremal solution on the other side.

A gap assumption removes part of the allowed spectrum. For example,

$$
\Delta_{\epsilon'}\ge \Delta_{\rm gap}
$$

removes candidate even scalars below $\Delta_{\rm gap}$ after the leading even scalar. Removing operators shrinks the allowed cone of conformal block vectors. Stronger assumptions can turn a broad allowed region into a small island.

The geometry is:

$$
\text{larger gaps}
\quad\Rightarrow\quad
\text{smaller allowed cone}
\quad\Rightarrow\quad
\text{stronger exclusions}.
$$

The art is choosing gaps that encode real physics rather than wishful thinking. The bootstrap is very good at enforcing assumptions. It is not responsible for deciding whether those assumptions were wise. Tiny dragon, huge sword.

## Kinks

A kink is a sharp feature in a numerical bound curve. A typical example is an upper bound on the first scalar dimension as a function of the external scalar dimension:

$$
\Delta_{S,0}^{\rm first}\le B(\Delta_\phi).
$$

A kink at

$$
\Delta_\phi=\Delta_\phi^*
$$

means that the optimal exclusion functional changes behavior near that point. Often the extremal spectrum extracted near the kink resembles the spectrum of a known or suspected CFT.

Kinks are exciting because they can reveal theories without putting them in by hand. Historically, this was one of the big surprises of the numerical bootstrap: interesting CFTs appeared as geometric features of allowed regions.

But a kink is not a theorem of existence. It is a clue. To interpret a kink as a CFT, one wants supporting evidence:

- stability as the derivative cutoff increases;
- sensible extremal spectrum;
- agreement with known symmetries and Ward identities;
- agreement with perturbative, lattice, Monte Carlo, or exact results when available;
- strengthening to an island in a larger correlator system.

## Why kinks happen

There is no single universal mechanism for every kink. Several common mechanisms are:

| Mechanism | Interpretation |
|---|---|
| change of extremal spectrum | different operators saturate the bound on different sides |
| decoupling of a free sector | a free-field point lies on a boundary |
| onset of a relevant operator | crossing forces a new low-lying operator |
| conservation or near-conservation | a current, stress tensor, or higher-spin structure shapes the boundary |
| hidden assumptions from a simple setup | the one-correlator problem projects complicated physics into one curve |

The 3D Ising kink is associated with an interacting solution whose low-lying spectrum has one relevant $\mathbb Z_2$-odd scalar and one relevant $\mathbb Z_2$-even scalar. Other kinks may correspond to free theories, generalized free solutions, nonunitary limits, multicritical points, or artifacts of a weak setup.

Thus the correct question is not “Is this kink real?” but

$$
\text{What CFT data, if any, are organizing this kink?}
$$

## Gaps

A spectral gap is an assumption of the form

$$
\Delta_{\rm next}\ge \Delta_{\rm gap}.
$$

The word “next” must be made precise. Examples include:

| Gap | Meaning |
|---|---|
| $\Delta_{\epsilon'}\ge 3.8$ | no second even scalar below $3.8$ |
| $\Delta_{\sigma'}\ge 5$ | no second odd scalar below $5$ |
| $\Delta_{S,2}^{\rm next}\ge 5$ | gap above the stress tensor in singlet spin two |
| $\Delta_{A,1}^{\rm next}\ge 4$ | gap above a conserved current in an antisymmetric sector |
| higher-spin gap | no low-twist higher-spin currents beyond expected ones |

A gap is not a numerical trick. It is a physical hypothesis about the spectrum.

Gaps are useful because many CFTs are characterized by a small number of relevant operators. For instance, an ordinary critical point may require tuning one parameter, while a multicritical point requires more. A gap above the leading relevant scalar can encode this distinction.

## Islands

An island is a small allowed region in a space of trial CFT data. For example, in the 3D Ising problem one studies

$$
(\Delta_\sigma,\Delta_\epsilon)
$$

using mixed correlators. Each point in this plane is tested by a bootstrap computation with specified assumptions. The excluded points are shaded away. The remaining component can be a small island.

An island is stronger evidence than a kink because it localizes several pieces of CFT data simultaneously. But it is still conditional.

A complete island statement includes:

1. the external operators;
2. the correlators used;
3. the global symmetry;
4. the assumed operator ordering;
5. the imposed gaps;
6. the derivative cutoff and spin treatment;
7. numerical precision and solver settings;
8. convergence behavior.

Without those details, the phrase “the island” is incomplete.

## The 3D Ising example

The 3D Ising CFT has a $\mathbb Z_2$ symmetry and two leading scalar primaries:

$$
\sigma\quad(\mathbb Z_2\text{-odd}),
\qquad
\epsilon\quad(\mathbb Z_2\text{-even}).
$$

The most important mixed-correlator system includes

$$
\langle\sigma\sigma\sigma\sigma\rangle,
\qquad
\langle\sigma\sigma\epsilon\epsilon\rangle,
\qquad
\langle\epsilon\epsilon\epsilon\epsilon\rangle.
$$

The assumptions are roughly:

- unitarity in $d=3$;
- $\mathbb Z_2$ symmetry;
- $\sigma$ is the leading odd scalar;
- $\epsilon$ is the leading even scalar;
- gaps exist above the next odd and even scalars in appropriate sectors.

Under such assumptions, the allowed region in

$$
(\Delta_\sigma,\Delta_\epsilon)
$$

shrinks to a small island. This island gives high-precision estimates of the leading dimensions and OPE coefficients.

The important point is that the island is not produced by the lattice Ising Hamiltonian directly. It is produced by CFT consistency plus Ising-like spectral assumptions.

## O(N) islands and archipelagos

For $O(N)$ models, the external scalar is a vector

$$
\phi_i.
$$

The four-point function decomposes into singlet, traceless symmetric, and antisymmetric sectors. Mixed-correlator systems can include the leading singlet scalar $s$ and traceless symmetric scalar $t_{ij}$.

As $N$ varies, allowed regions can form a family of islands. Recent literature sometimes calls this an archipelago. The word is playful, but the structure is serious: for each $N$, the bootstrap problem has different group theory, different operator dimensions, and different stability questions.

Gap assumptions may encode:

$$
\text{one relevant singlet},
$$

or a gap above the leading traceless symmetric scalar, or the presence of conserved $O(N)$ currents with

$$
\Delta_J=d-1.
$$

For $N=1$, the story reduces to the Ising case. For $N=2,3$, precision questions include experimental critical exponents, cubic anisotropy stability, and comparisons with Monte Carlo and RG estimates.

## Gap assumptions and physics

Good gap assumptions usually come from one of these sources:

| Source | Example |
|---|---|
| symmetry | $\mathbb Z_2$ parity forbids odd operators in $\sigma\times\sigma$ |
| unitarity | $\Delta\ge\ell+d-2$ for spin $\ell\ge1$ |
| Ward identities | stress tensor at $\Delta=d$, current at $\Delta=d-1$ |
| relevant-operator count | only one relevant singlet for an ordinary critical point |
| perturbation theory | epsilon expansion predicts approximate ordering |
| large-$N$ | $1/N$ expansion estimates gaps |
| previous bootstrap | lower-precision studies suggest a spectral window |
| lattice or Monte Carlo | independent numerical estimates support a gap |

Bad gap assumptions are arbitrary values chosen only because they make a pretty island.

A gap can be optimistic but still useful if clearly labeled as a hypothesis. The danger is when a conditional hypothesis is retold as an unconditional result.

## Relevant operator counting

Critical phenomena often care about the number of relevant scalar singlets. A scalar deformation

$$
S\to S+g\int d^d x\,\mathcal O(x)
$$

is relevant if

$$
\Delta_\mathcal O<d.
$$

If a CFT has one relevant singlet, it may describe an ordinary critical point reached by tuning one parameter, such as temperature. If it has two or more relevant singlets, it may describe a multicritical point or require additional microscopic tuning.

In the bootstrap, one may impose a gap saying that the second singlet scalar is irrelevant:

$$
\Delta_{S,0}^{\rm second}>d.
$$

This is a physically meaningful assumption when looking for ordinary critical points.

But relevant operator counting must respect the symmetry. A scalar in a non-singlet representation may be forbidden by microscopic symmetry or may correspond to an anisotropy. Stability depends on which perturbations are allowed.

## Gaps above conserved operators

Conserved currents and stress tensors sit at unitarity bounds:

$$
\Delta_J=d-1,
\qquad
\Delta_T=d.
$$

One can impose gaps above them. For example, if the stress tensor is the only conserved spin-two operator, then the next spin-two singlet should have dimension

$$
\Delta_{T'}>d.
$$

Similarly, in a theory with global symmetry, the conserved current lies in a specific representation, and the next spin-one operator in that sector may be assumed to have a gap.

These assumptions can encode uniqueness of the stress tensor or absence of extra conserved currents. They are especially important when excluding decoupled products of CFTs or theories with enlarged symmetry.

However, conserved-operator gaps must be formulated carefully. A decoupled product theory has multiple stress tensors. A theory with emergent symmetry may have more currents than the microscopic symmetry suggests.

## Islands versus exact solutions

An island is not an exact solution. It is a finite-cutoff allowed region. At higher cutoff, the island may shrink, move, split, or disappear.

A stable island gives strong evidence for a CFT, especially when:

- it persists as $\Lambda$ increases;
- it agrees with independent methods;
- extremal spectra look consistent;
- Ward identities are satisfied;
- OPE coefficients are positive and stable;
- assumptions are physically motivated.

But the logical status remains conditional:

$$
\text{CFT satisfying assumptions, if it exists, lies in this region.}
$$

This sentence is less punchy than “we solved the theory,” but it is the honest one. Weirdly, honesty ages better.

## Kinks without islands

Some kinks do not become islands when stronger systems are studied. Possible reasons include:

| Possibility | Meaning |
|---|---|
| projection effect | many solutions project to a sharp feature in one plot |
| generalized-free boundary | kink reflects mean-field-like data |
| free or decoupled sector | feature is real but not the desired interacting CFT |
| missing assumptions | more correlators needed to isolate it |
| numerical artifact | feature weakens at higher cutoff |
| nonunitary or complex nearby solution | unitary plot feels influence of nearby analytic structure |

This is why a kink is the beginning of a story, not the ending. A good bootstrap project often starts by noticing a kink and then asks what additional correlators or assumptions can test its meaning.

## How islands are found

The brute-force approach is to scan a grid in parameter space. For each trial point, run a feasibility problem. Points with excluding functionals are outside; points without them are inside or undecided.

For high-dimensional searches, grids become expensive. Modern methods include:

| Method | Purpose |
|---|---|
| bisection | locate one-dimensional bound curves |
| Delaunay triangulation | adaptively map allowed/excluded regions |
| cutting-surface methods | iteratively approximate boundaries |
| navigator functions | create smooth functions guiding searches toward islands |
| skydive-like methods | approach feasible regions efficiently in high dimension |

The algorithms differ, but the underlying logic remains the same: each excluded point has a functional certificate in the chosen bootstrap setup.

## Interpreting gap scans

A useful practice is to vary a gap and see when an island appears or disappears. Suppose one imposes

$$
\Delta_{\epsilon'}\ge g.
$$

For small $g$, the allowed region may be broad. As $g$ increases, it may shrink into an island. If $g$ is pushed too high, the island may disappear because the true theory violates the assumption.

This gives a diagnostic:

| Behavior | Interpretation |
|---|---|
| island stable over a range of gaps | robust spectral isolation |
| island only at extreme gap | assumption may be too strong |
| island disappears below expected gap | external assumptions may be insufficient |
| island moves with gap | target data correlated with spectral assumptions |

Gap scans are an antidote to overconfidence. They show which parts of the result are driven by crossing and which are driven by assumptions.

## Common pitfalls

**Do not say a kink is a CFT.** A kink is a feature in a bound. It may indicate a CFT, but it is not itself one.

**Do not quote an island without its gaps.** The gaps are part of the definition of the allowed region.

**Do not call an allowed region an existence proof.** Not excluded is not the same as constructed.

**Do not use arbitrary gaps just to make an island.** Gaps should be physically motivated, or clearly labeled exploratory assumptions.

**Do not ignore cutoff dependence.** Kinks and islands must be checked as $\Lambda$ increases.

**Do not forget representation sectors.** In global-symmetry bootstrap, gaps must specify the sector, spin, and parity.

**Do not assume microscopic symmetry equals emergent symmetry.** Emergent currents or symmetry enhancement can change the spectrum and the interpretation of gaps.

## Relations to other pages

This page follows [Identical Scalar Bounds](/cft-bootstrap/numerical-bootstrap/identical-scalar-bounds/). It prepares [Mixed-Correlator Systems](/cft-bootstrap/numerical-bootstrap/mixed-correlator-systems/), where islands become much more powerful, and [Extremal Functional Method](/cft-bootstrap/numerical-bootstrap/extremal-functional-method/), where boundary spectra are extracted.

It also connects to [Navigator and Modern Search Algorithms](/cft-bootstrap/numerical-bootstrap/navigator-and-modern-search-algorithms/) and [Error Bars and Reliability](/cft-bootstrap/numerical-bootstrap/error-bars-and-reliability/), because modern island searches require careful algorithms and sober interpretation.

For examples, see [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/), [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/), and [Gauge-Theory CFTs](/cft-bootstrap/higher-dimensional-cft/gauge-theory-cfts/).

## Research status

Kinks, islands, and gap assumptions are established tools in numerical conformal bootstrap. They are central to precision studies of the 3D Ising model, $O(N)$ models, supersymmetric systems, boundary CFTs, and modern searches for gauge-theory CFTs.

Active research focuses on making their interpretation sharper: distinguishing true isolated CFTs from projection effects, improving convergence and error estimates, developing navigator and cutting-surface algorithms, incorporating analytic bootstrap information, and applying island methods to more complicated theories.

## Exercises

### Exercise 1

What is the difference between a kink and an island?

<details><summary><strong>Solution</strong></summary>

A kink is a sharp feature in a bound curve, often in a one- or two-dimensional plot. It suggests a change in the extremal solution and may indicate a CFT. An island is a small allowed region in parameter space obtained after applying crossing, unitarity, and additional assumptions such as spectral gaps. A kink is a clue; an island is a targeted allowed region.

</details>

### Exercise 2

Why do gap assumptions make bootstrap bounds stronger?

<details><summary><strong>Solution</strong></summary>

A gap assumption removes possible low-dimension operator contributions from the allowed spectrum. Geometrically, it removes some conformal block vectors from the positive cone. A smaller cone is easier to separate from the identity vector using a linear functional, so more points can be excluded and allowed regions shrink.

</details>

### Exercise 3

Give a physically meaningful gap assumption for an ordinary critical point with one relevant singlet.

<details><summary><strong>Solution</strong></summary>

If $s$ is the leading relevant singlet scalar, a physically meaningful assumption is that the next singlet scalar $s'$ is irrelevant:

$$
\Delta_{s'}>d.
$$

This encodes the idea that only one singlet coupling must be tuned to reach the critical point.

</details>

### Exercise 4

Why is an island not an existence proof?

<details><summary><strong>Solution</strong></summary>

An island is the region not excluded by a finite numerical bootstrap computation under stated assumptions. The computation may use finite derivative cutoff, finite precision, approximate conformal blocks, and a limited correlator system. A point inside the island has survived those tests, but this does not construct a complete CFT or prove that all crossing equations are satisfied exactly.

</details>

### Exercise 5

Why can a decoupled product CFT complicate assumptions about the stress tensor?

<details><summary><strong>Solution</strong></summary>

A decoupled product CFT has one conserved stress tensor for each factor. The sum is the total stress tensor, but the orthogonal combinations are also conserved spin-two operators. Therefore the spectrum contains multiple spin-two conserved operators. If a bootstrap setup assumes a unique stress tensor or imposes a gap above the stress tensor, it may exclude decoupled product theories or require those sectors to be treated separately.

</details>

## References

- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- S. El-Showk, M. F. Paulos, D. Poland, S. Rychkov, D. Simmons-Duffin, and A. Vichi, “Solving the 3D Ising Model with the Conformal Bootstrap II,” *Journal of Statistical Physics* **157** (2014).
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Bootstrapping mixed correlators in the 3D Ising model,” *Journal of High Energy Physics* **2014**.
- F. Kos, D. Poland, D. Simmons-Duffin, and A. Vichi, “Precision islands in the Ising and $O(N)$ models,” *Journal of High Energy Physics* **2016**.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- D. Simmons-Duffin, “A semidefinite program solver for the conformal bootstrap,” *Journal of High Energy Physics* **2015**.

## Version history

- 2026-07-01: First polished draft. Added definitions of kinks, islands, and gaps; Ising and O(N) examples; gap-assumption logic; relevant-operator counting; algorithmic search overview; pitfalls; exercises; and references.
