---
title: "Large-N Methods"
description: "Chapter overview for large-N limits, vector models, sigma models, matrix models, planar diagrams, factorization, and saddle-point methods in nonperturbative QFT."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Polyakov; Shifman; Mariño; Coleman; Zinn-Justin; large-N gauge-theory, sigma-model, and matrix-model literature."
topics:
  - large-N methods
  - vector models
  - sigma models
  - matrix models
  - planar expansion
  - saddle points
  - gap equations
  - factorization
  - eigenvalue density
  - master fields
  - CP N minus one model
  - double scaling
canonicalTopics:
  - nonperturbative-qft
  - large-n-methods
  - large-n-vector-models
  - large-n-sigma-models
  - matrix-models
  - planar-diagrams
  - large-n-factorization
  - master-field
  - large-n-yang-mills
  - saddle-points
researchStatus:
  established:
    - "Large-N limits provide controlled nonperturbative expansions in many vector, sigma, matrix, and gauge theories by making collective variables or single-trace sectors behave classically."
  active:
    - "Which large-N limits faithfully approximate a desired finite-N theory, and how large-N saddle data reorganize into strings, geometry, or dual variables, remains model-dependent and often research-level."
---

Large-N Methods is the chapter in the Nonperturbative QFT volume where $N$ itself becomes the control parameter. Instead of expanding in a small coupling, one studies a family of theories labeled by an integer $N$ and asks whether the limit $N\to\infty$ has a simpler organization.

The surprise is that this can be a genuinely nonperturbative approximation. In vector and sigma models, the theory becomes a saddle-point problem for collective fields such as Hubbard–Stratonovich fields, Lagrange multipliers, and gap variables. In matrix and gauge theories, the diagrams reorganize by topology, and planar graphs dominate. In both cases, the large-$N$ limit can turn a strongly interacting quantum field theory into a new kind of classical system.

Large $N$ is not one method. It is a family of methods whose meaning depends on how the degrees of freedom scale with $N$: $O(N)$ vector fields, constrained sigma-model variables, $N\times N$ matrices, gauge fields in the adjoint representation, fundamental matter, or mixed systems. This chapter teaches the common logic and then separates the cases carefully.

<figure class="doc-figure" style="--figure-width: 55rem;">

![Map of large-N methods, from N-indexed degrees of freedom to collective saddles, planar diagrams, factorization, matrix eigenvalues, gauge/string intuition, and finite-N corrections.](/figures/nonperturbative-qft/large-n-methods-map.svg)

<figcaption>

Large $N$ creates a new classical limit. Vector and sigma models become saddle-point problems for collective singlet fields; matrix and gauge theories organize by planar diagrams, eigenvalue densities, and factorization. The expansion parameter is typically $1/N$ or $1/N^2$, but the physical meaning of that expansion is different in different theories.

</figcaption>
</figure>

## Prerequisites

You should know [Beyond Perturbation Theory](/nonperturbative-qft/what-is-nonperturbative-qft/beyond-perturbation-theory/), [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/), [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/), [Mass Gap in Gauge Theory](/nonperturbative-qft/confinement-screening-mass-gap/mass-gap/), [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/), and [QCD as a Strongly Coupled QFT](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-as-strongly-coupled-qft/).

For this chapter, the most important background is not complicated algebra; it is the ability to track powers of $N$. You should be comfortable with Gaussian functional integrals, determinants such as $\operatorname{Tr}\log K$, and the idea that an action of the form

$$
S_{\rm eff}[\sigma]=N\,s_{\rm eff}[\sigma]
$$

is dominated by a saddle point as $N\to\infty$.

## Reading path

Read these pages in order on a first pass. The full first-pass Large-N Methods path is now available, ending with eigenvalue-density methods and double-scaling limits.

| Step | Page | Status | What it gives you |
|---:|---|---|---|
| 1 | [Large-N Vector Models](/nonperturbative-qft/large-n-methods/large-n-vector-models/) | Available | The basic mechanism: $O(N)$ singlet collective fields, Hubbard–Stratonovich variables, gap equations, critical exponents, and $1/N$ corrections. |
| 2 | [Large-N Sigma Models](/nonperturbative-qft/large-n-methods/large-n-sigma-models/) | Available | The constrained-field version of the large-$N$ saddle, including the two-dimensional $O(N)$ model, mass generation, and the $CP^{N-1}$ model. |
| 3 | [Matrix Large-N Limits](/nonperturbative-qft/large-n-methods/matrix-large-n-limits/) | Available | Matrix integrals, eigenvalue repulsion, resolvents, saddle equations, planar free energy, and double-scaling intuition. |
| 4 | [Planar Diagrams](/nonperturbative-qft/large-n-methods/planar-diagrams/) | Available | ’t Hooft double-line notation, Euler-characteristic counting, planar dominance, handles, and quark-loop boundaries. |
| 5 | [Large-N Factorization](/nonperturbative-qft/large-n-methods/large-n-factorization/) | Available | Why connected correlators of normalized single-trace or singlet operators are suppressed and how this produces a classical limit. |
| 6 | [Master Field Preview](/nonperturbative-qft/large-n-methods/master-field-preview/) | Available | What a master field tries to encode, why factorization motivates it, and why four-dimensional Yang–Mills remains difficult. |
| 7 | [Large-N Yang–Mills](/nonperturbative-qft/large-n-methods/large-n-yang-mills/) | Available | Glueballs, mesons, baryons, string tension, theta dependence, and the controlled-but-not-solved large-$N$ picture of confinement. |
| 8 | [CP N-Minus-One Model](/nonperturbative-qft/large-n-methods/cp-n-minus-one-model/) | Available | A deeper model page for the two-dimensional large-$N$ theory with asymptotic freedom, mass generation, confinement-like behavior, and theta dependence. |
| 9 | [Saddle Points at Large N](/nonperturbative-qft/large-n-methods/saddle-points-at-large-n/) | Available | The general steepest-descent anatomy behind collective-field, density, and gauge-invariant large-$N$ limits. |
| 10 | [Eigenvalue-Density Methods](/nonperturbative-qft/large-n-methods/eigenvalue-density-methods/) | Available | Continuum eigenvalue densities, support intervals, saddle kernels, resolvents, and large-$N$ matrix-model observables. |
| 11 | [Double-Scaling Limits Preview](/nonperturbative-qft/large-n-methods/double-scaling-limits-preview/) | Available | How $N\to\infty$ can be combined with critical tuning so infinitely many genera, diagrams, or edge excitations survive. |

The chapter deliberately begins with vector and sigma models before matrix and gauge theories. They teach the most important lesson with the least notation: at large $N$, invariant collective variables have small fluctuations, and the path integral often becomes a saddle-point problem.

## Landmarks

| Landmark | Meaning | Why it matters |
|---|---|---|
| Large-N family | A sequence of theories indexed by $N$. | The approximation is meaningful only after saying what is held fixed as $N\to\infty$. |
| Vector model | $N$ fields $\phi_i$ with $O(N)$ symmetry. | The simplest nontrivial large-$N$ saddle and gap equation. |
| Nonlinear sigma model | Fields constrained to a target space such as $S^{N-1}$ or $CP^{N-1}$. | Shows how constraints and Lagrange multipliers generate masses and effective gauge fields. |
| Hubbard–Stratonovich field | Auxiliary singlet field replacing quartic interactions. | Turns the problem into an effective action proportional to $N$. |
| Gap equation | Saddle equation determining a dynamically generated mass or order parameter. | The basic nonperturbative result in vector and sigma models. |
| Large-N saddle | An effective exponent of the form $N s_{\rm eff}$ or $N^2 f$ dominated by stationary collective data. | Explains why large $N$ behaves like a classical limit for invariant observables. |
| Eigenvalue density | Continuum distribution of matrix eigenvalues. | The classical variable of many matrix-model large-$N$ limits. |
| Planar expansion | Matrix/gauge diagrams ordered by genus. | Explains why surfaces, strings, and topology enter large-$N$ gauge theories. |
| ’t Hooft coupling | $\lambda=g^2N$ held fixed in many gauge-theory limits. | Keeps planar gauge dynamics finite as $N\to\infty$. |
| Factorization | Connected correlators of normalized singlet operators are suppressed. | Large $N$ behaves like a classical limit for invariant observables. |
| Master field | A proposed object or state encoding all planar invariant observables. | Names what it would mean to solve the large-$N$ theory at leading order. |
| Large-N Yang–Mills | The ’t Hooft limit of non-Abelian gauge theory. | Organizes glueballs, mesons, baryons, flux tubes, and theta dependence by powers of $N$. |
| Double scaling | $N\to\infty$ while tuning to a critical point. | Allows infinitely many topologies or continuum surfaces to survive. |

## Common confusions

**Large $N$ is not automatically weak coupling.** A large-$N$ saddle may describe a strongly coupled theory. The small parameter is $1/N$, not necessarily the microscopic coupling.

**Large $N$ is not unique.** Vector, sigma, matrix, and gauge large-$N$ limits have different degrees of freedom, different scalings, and different correction parameters. A formula from an $O(N)$ vector model should not be blindly imported into large-$N$ Yang–Mills.

**The large-$N$ limit is not the same as the physical theory.** Real systems have finite $N$. Large $N$ is useful when corrections are small, when the qualitative mechanism survives, or when it provides a controlled starting point. It can also fail if the finite-$N$ theory has effects that are invisible or singular at $N=\infty$.

**The saddle point is not necessarily a classical field configuration of the original microscopic fields.** In vector and sigma models, the saddle is usually a collective singlet field or Lagrange multiplier. It is classical because its effective action is proportional to $N$, not because the original scalar field has a classical profile.

**Planar dominance is not the same as vector-model dominance.** Vector models have $O(N)$ degrees of freedom and bubble-chain large-$N$ diagrams. Matrix and adjoint gauge theories have $O(N^2)$ degrees of freedom and a topological expansion in surfaces.

**A large-$N$ solution can miss instantons or nonperturbative-in-N sectors.** Effects scaling like $e^{-cN}$ are invisible to every order in the $1/N$ expansion. This is the large-$N$ analogue of effects like $e^{-1/g^2}$ in weak-coupling semiclassics.

## Boundaries

This chapter does:

- explain large $N$ as a controlled nonperturbative limit;
- derive saddle-point and gap-equation methods in vector and sigma models;
- develop matrix-model eigenvalue methods, planar counting, factorization, and large-$N$ gauge-theory intuition;
- emphasize the difference between $1/N$ and $1/N^2$ expansions;
- connect large $N$ to confinement, mass gaps, topological susceptibility, effective strings, and holographic or geometric intuition.

This chapter does not try to do:

- a full course on random matrix theory;
- the full AdS/CFT correspondence;
- a complete treatment of supersymmetric localization;
- lattice large-$N$ numerical methods;
- rigorous constructive large-$N$ analysis.

Large $N$ belongs here because it is a nonperturbative method. The holographic interpretation of large-$N$ gauge theory belongs in Spacetime, Gravity, and Holography. Supersymmetric exact large-$N$ results belong in Supersymmetry, Duality, and Integrability, with cross-links back to this chapter.

## Where to go next

Begin with [Large-N Vector Models](/nonperturbative-qft/large-n-methods/large-n-vector-models/), then read [Large-N Sigma Models](/nonperturbative-qft/large-n-methods/large-n-sigma-models/) for constrained fields and mass generation. Continue to [Matrix Large-N Limits](/nonperturbative-qft/large-n-methods/matrix-large-n-limits/) for eigenvalue-density saddles, [Planar Diagrams](/nonperturbative-qft/large-n-methods/planar-diagrams/) for ribbon-graph topology, [Large-N Factorization](/nonperturbative-qft/large-n-methods/large-n-factorization/) for the classical limit of normalized invariant observables, [Master Field Preview](/nonperturbative-qft/large-n-methods/master-field-preview/) for the object factorization suggests, [Large-N Yang–Mills](/nonperturbative-qft/large-n-methods/large-n-yang-mills/) for the gauge-theory physics of the ’t Hooft limit, [CP N-Minus-One Model](/nonperturbative-qft/large-n-methods/cp-n-minus-one-model/) for a solvable theta-dependent sigma model, and [Saddle Points at Large N](/nonperturbative-qft/large-n-methods/saddle-points-at-large-n/) for the general steepest-descent logic.

For earlier motivation from confinement, read [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/), [Flux Tubes](/nonperturbative-qft/confinement-screening-mass-gap/flux-tubes/), and [QCD String Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-string-preview/). Finish the chapter with [Eigenvalue-Density Methods](/nonperturbative-qft/large-n-methods/eigenvalue-density-methods/) and [Double-Scaling Limits Preview](/nonperturbative-qft/large-n-methods/double-scaling-limits-preview/). For the next nonperturbative method, continue to [Lattice Field Theory](/nonperturbative-qft/lattice-field-theory/), beginning with [Euclidean Lattice](/nonperturbative-qft/lattice-field-theory/euclidean-lattice/).

## References

### Standard first pass

- M. Mariño, *Instantons and Large N*, especially the large-$N$ chapters on sigma models, QCD, matrix models, two-dimensional QCD, and large-$N$ instantons.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on strong coupling, instantons, loop dynamics, large $N$, and random surfaces.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapters on confinement, the ’t Hooft limit, $CP(N-1)$, the ’t Hooft model, and the large-$N$ solution of the $O(N)$ model.

### Deeper references

- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for vector models, critical phenomena, saddle methods, and $1/N$ expansions.
- S. Coleman, *Aspects of Symmetry*, especially the lecture “1/N.”
- G. ’t Hooft, “A Planar Diagram Theory for Strong Interactions,” for the original planar expansion of non-Abelian gauge theory.
- E. Brézin, C. Itzykson, G. Parisi, and J.-B. Zuber, “Planar Diagrams,” for classic matrix-model large-$N$ methods.
- E. Witten, “Baryons in the 1/N Expansion,” and related large-$N$ QCD papers for physical consequences of the gauge-theory limit.

## Version history

- **2026-06-28:** Linked forward to the new Lattice Field Theory chapter after completing the first-pass large-$N$ methods path.
- **2026-06-28:** Added eigenvalue-density methods and double-scaling limits, completing the first-pass Large-N Methods reading path.
- **2026-06-27:** Updated reading path after adding the CP N-minus-one model and saddle-points-at-large-N.
- **2026-06-27:** Updated reading path after adding the master-field preview and large-N Yang–Mills.
- **2026-06-27:** Updated reading path after adding planar diagrams and large-N factorization.
- **2026-06-27:** Updated reading path after adding large-N sigma models and matrix large-N limits.
- **2026-06-27:** Initial polished chapter overview, added after the Strongly Coupled Gauge Theories chapter arc to begin the large-$N$ methods block.
