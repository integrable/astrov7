---
title: "Planar Diagrams"
description: "Explains ’t Hooft double-line notation, Euler-characteristic counting, and why planar ribbon graphs dominate large-N matrix and gauge theories."
sidebar:
  label: "Planar Diagrams"
  order: 4
level: Advanced
status: "Polished draft"
source: "’t Hooft; Coleman; Polyakov; Mariño; Shifman; standard large-N matrix and gauge-theory literature."
topics:
  - planar diagrams
  - double-line notation
  - ribbon graphs
  - large-N gauge theory
  - matrix models
  - "’t Hooft coupling"
  - genus expansion
  - quark-loop suppression
canonicalTopics:
  - nonperturbative-qft
  - large-n-methods
  - planar-diagrams
  - double-line-notation
  - large-n-gauge-theory
  - matrix-models
researchStatus:
  established:
    - "The large-N expansion of adjoint matrix and gauge theories is organized by ribbon-graph topology, with planar graphs dominating when the ’t Hooft coupling is held fixed."
  active:
    - "Turning planar dominance into a complete solution of four-dimensional confining gauge theories is still model-dependent and generally unsolved."
---

## Summary

A **planar diagram** in large-$N$ matrix or gauge theory is a Feynman diagram that can be drawn as a ribbon graph on a sphere without crossings. In ordinary perturbation theory, diagrams are organized by loop order. In the large-$N$ expansion of adjoint theories, they are also organized by topology.

For a connected ribbon graph with $V$ vertices, $E$ propagators, and $F$ closed index loops,

$$
\text{amplitude}\sim N^{F-E+V}.
$$

The combination

$$
\chi=F-E+V
$$

is the Euler characteristic of the surface on which the ribbon graph can be drawn. For an orientable connected surface of genus $h$ with $b$ boundaries,

$$
\chi=2-2h-b,
$$

so the large-$N$ expansion becomes

$$
\text{amplitude}\sim N^{2-2h-b}\,f(\lambda),
$$

where $\lambda=g^2N$ is the ’t Hooft coupling in gauge theory. Planar diagrams have $h=0$ and dominate. Each handle costs a factor of $1/N^2$, and each boundary costs a factor of $1/N$.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Double-line notation and planar versus nonplanar large-N counting.](/figures/nonperturbative-qft/planar-diagrams-topology.svg)

<figcaption>

Double-line notation replaces an adjoint propagator by two oriented fundamental index lines. Closed index faces give powers of $N$. The resulting ribbon graph has a topological weight $N^\chi=N^{2-2h-b}$, so planar graphs dominate and nonplanar handles are suppressed by $1/N^2$.

</figcaption>
</figure>

This page explains the counting, why it is the natural language of large-$N$ gauge theory, and what it does **not** prove by itself.

## Prerequisites

Read [Large-N Methods](/nonperturbative-qft/large-n-methods/), [Matrix Large-N Limits](/nonperturbative-qft/large-n-methods/matrix-large-n-limits/), and [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) first. You should also be comfortable with traces, index notation, and ordinary Feynman-diagram counting.

The most important habit is to write matrix indices explicitly. A field in the adjoint of $U(N)$ or $SU(N)$ is matrix-valued,

$$
X^i{}_j(x),
\qquad i,j=1,\ldots,N,
$$

and each repeated color index is summed.

## Core idea

In an adjoint theory, a propagator does not carry one color line. It carries two. Schematically,

$$
\langle X^i{}_j X^k{}_\ell\rangle
\propto
\delta^i{}_\ell\,\delta^k{}_j.
$$

This is the double-line propagator. It says that an adjoint particle behaves, for color bookkeeping, like a fundamental index and an antifundamental index traveling together. Interactions built from traces preserve cyclic order at each vertex. Therefore the diagram is not merely a graph; it is a **fat graph** or **ribbon graph**.

The punchline is beautifully geometric:

$$
\text{powers of }N
\quad\longleftrightarrow\quad
\text{Euler characteristic of a surface}.
$$

That is why large-$N$ matrix and gauge theories smell like string theory. Their perturbative expansion is not just a sum over particle graphs; it is a sum over discretized two-dimensional surfaces.

## Setup and conventions

We use Euclidean path-integral conventions. For a simple Hermitian matrix field or matrix integral, take an action normalized as

$$
S=N\operatorname{Tr}\left[\frac12 X K X+\sum_{r\ge3}\frac{g_r}{r}X^r\right].
$$

The conventional large-$N$ normalization gives the schematic rules

$$
\text{propagator}\sim \frac1N,
\qquad
\text{single-trace vertex}\sim N,
\qquad
\text{closed index face}\sim N.
$$

For non-Abelian gauge theory, the corresponding large-$N$ normalization holds the ’t Hooft coupling

$$
\lambda=g^2N
$$

fixed as $N\to\infty$. In a pure adjoint theory, the free energy scales as

$$
\log Z\sim N^2.
$$

This $N^2$ is not accidental: an adjoint gauge field has $O(N^2)$ color degrees of freedom.

Most formulas on this page are cleanest for $U(N)$. For $SU(N)$, the tracelessness projection changes subleading terms but not the leading planar counting. The difference between $U(N)$ and $SU(N)$ is usually invisible at leading large $N$ for single-trace adjoint observables.

## Double-line counting

Take a connected vacuum ribbon graph. It has

- $V$ single-trace vertices, each contributing $N$;
- $E$ propagators, each contributing $1/N$;
- $F$ closed index faces, each contributing $N$.

The net power is therefore

$$
N^V N^{-E} N^F=N^{F-E+V}.
$$

But a ribbon graph defines a cell decomposition of an orientable surface: vertices are zero-cells, propagator ribbons are one-cells, and index loops are faces. Thus

$$
F-E+V=\chi.
$$

For a connected closed orientable surface of genus $h$,

$$
\chi=2-2h.
$$

Hence a vacuum graph contributes as

$$
N^{2-2h}.
$$

The leading vacuum graphs are planar graphs with $h=0$, scaling as $N^2$. A torus graph has $h=1$ and scales as $N^0$. Each additional handle suppresses the graph by another $1/N^2$.

This is the **genus expansion**:

$$
\log Z=N^2F_0(\lambda)+F_1(\lambda)+\frac{1}{N^2}F_2(\lambda)+\cdots.
$$

The subscript $h$ labels the genus of the ribbon surface, not the ordinary loop order.

## Boundaries and single-trace insertions

A gauge-invariant single-trace operator such as

$$
\operatorname{Tr}X^k
$$

creates a boundary in the ribbon graph. With $b$ such boundaries, the surface has

$$
\chi=2-2h-b,
$$

so an unnormalized connected correlator behaves as

$$
\left\langle \operatorname{Tr}X^{k_1}\cdots \operatorname{Tr}X^{k_b}\right\rangle_c
\sim N^{2-2h-b}
$$

at genus $h$. The leading connected term has $h=0$:

$$
\left\langle \operatorname{Tr}X^{k_1}\cdots \operatorname{Tr}X^{k_b}\right\rangle_c
\sim N^{2-b}.
$$

For normalized operators

$$
\mathcal O_k=\frac1N\operatorname{Tr}X^k,
$$

this becomes

$$
\left\langle \mathcal O_{k_1}\cdots\mathcal O_{k_b}\right\rangle_c
\sim N^{2-2b}.
$$

In particular,

$$
\left\langle \mathcal O_1\mathcal O_2\right\rangle_c\sim \frac1{N^2}.
$$

This is the diagrammatic origin of [Large-N Factorization](/nonperturbative-qft/large-n-methods/large-n-factorization/).

## Fundamental matter and quark loops

Fundamental fields carry only one color line. A closed fundamental loop is a boundary rather than a face, so it reduces the power of $N$ by one relative to an adjoint face. In large-$N$ QCD with fixed number of flavors $N_f$,

$$
\text{closed quark loop}\sim \frac{N_f}{N}
$$

relative to the leading gluonic planar diagrams.

This is why the simplest ’t Hooft large-$N$ limit is often described as a **quenched** or **planar** approximation for quark loops: gluons remain fully dynamical at leading order, while closed fundamental loops are suppressed.

There is a different and important limit, the **Veneziano limit**, in which

$$
N\to\infty,
\qquad
\frac{N_f}{N}\quad\text{fixed}.
$$

Then quark-loop boundaries are not suppressed in the same way. Whenever a large-$N$ statement involves flavor dynamics, it matters which limit is being taken.

## Relation to strings

The topological expansion

$$
N^{2-2h-b}
$$

has the same structure as a closed-string perturbation expansion with string coupling

$$
g_s\sim \frac1N.
$$

A planar vacuum diagram is sphere-like; a one-handle correction is torus-like; operator insertions or quark loops act like boundaries. This is the deep reason large-$N$ gauge theories are natural ancestors of gauge/string duality.

Still, ribbon-graph topology is not yet a full string theory. To obtain an actual string description one needs a continuum worldsheet interpretation, a set of worldsheet fields, a rule for observables, and control over the sum over diagrams. Matrix models provide controlled examples in low-dimensional settings. Four-dimensional Yang–Mills theory is far harder.

## Checks and diagnostics

A quick way to check the counting is to ask three questions.

First, did every propagator contribute its $1/N$? If the action is normalized as $N\operatorname{Tr}(\cdots)$, the inverse quadratic form carries $1/N$.

Second, did every single-trace vertex contribute $N$? The trace contracts indices cyclically and the action normalization supplies the factor.

Third, did every closed index loop get counted? The most common error is to count ordinary momentum loops instead of color-index faces. Large-$N$ topology is color topology, not momentum topology.

A useful summary is

$$
\boxed{
\text{ribbon graph power}=N^{\#\text{faces}-\#\text{edges}+\#\text{vertices}}
}
$$

with boundaries included by the topology of the resulting surface.

## Common pitfalls

**Confusing planar order with low loop order.** A planar diagram can contain arbitrarily many ordinary loops. The planar limit still requires summing infinitely many diagrams at fixed $\lambda$.

**Holding the wrong coupling fixed.** In gauge theory, the useful large-$N$ limit keeps $\lambda=g^2N$ fixed. If $g$ is held fixed instead, the interaction strength does not have a finite large-$N$ limit.

**Counting lines but not faces.** The factor $N^F$ comes from closed index loops. A drawing that looks complicated may still be planar if its ribbons can be rearranged on the sphere without crossings.

**Treating quarks as adjoint fields.** Fundamental matter changes the topology by introducing boundaries. Whether those boundaries are suppressed depends on the flavor scaling.

**Equating planar dominance with confinement.** Planar diagrams organize the expansion. They do not by themselves prove an area law, a mass gap, or flux-tube formation.

## Relations to other pages

[Matrix Large-N Limits](/nonperturbative-qft/large-n-methods/matrix-large-n-limits/) introduced the planar free-energy expansion from matrix integrals. This page explains the same topology directly from double-line Feynman diagrams.

[Large-N Factorization](/nonperturbative-qft/large-n-methods/large-n-factorization/) uses the boundary counting above to show why connected correlators of normalized single-trace observables are suppressed.

[Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) and [QCD String Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-string-preview/) explain why planar topology suggests string-like physics in confining gauge theories.

[Master Field Preview](/nonperturbative-qft/large-n-methods/master-field-preview/) and [Large-N Yang–Mills](/nonperturbative-qft/large-n-methods/large-n-yang-mills/) use this counting for loop-space classicality, glueballs, mesons, baryons, theta dependence, and confinement expectations.


## Research status

**Established.** Double-line notation, genus counting, planar dominance, quark-loop suppression at fixed $N_f$, and the $1/N^2$ topological expansion are standard results of large-$N$ matrix and gauge theory.

**Established with caveats.** The string-like interpretation of planar diagrams is structurally robust, but an explicit continuum string dual is known only in special cases or with additional structure. For ordinary four-dimensional Yang–Mills theory, planar dominance is an organizing principle, not a solution.

**Active.** Determining nonperturbative planar spectra, understanding finite-$N$ corrections, controlling nonplanar effects, and relating diagrammatic surfaces to emergent geometry remain active across gauge theory, holography, matrix models, and conformal field theory.

## Exercises

### Exercise 1: Euler-characteristic counting

A connected ribbon vacuum graph has $V=4$, $E=6$, and $F=4$. What is its large-$N$ scaling? What genus does it have if it is orientable and closed?

<details>
<summary><strong>Solution</strong></summary>

The power of $N$ is

$$
N^{F-E+V}=N^{4-6+4}=N^2.
$$

For a closed orientable surface,

$$
\chi=2-2h.
$$

Since $\chi=2$, we get $h=0$. The graph is planar.

</details>

### Exercise 2: One handle

A connected vacuum ribbon graph has genus $h=1$. By what power of $N$ is it suppressed relative to a planar vacuum graph?

<details>
<summary><strong>Solution</strong></summary>

A planar vacuum graph has $h=0$ and scales as $N^2$. A genus-one graph scales as

$$
N^{2-2h}=N^0.
$$

Therefore it is suppressed by

$$
\frac{N^0}{N^2}=\frac1{N^2}.
$$

</details>

### Exercise 3: Boundaries from operator insertions

Let

$$
\mathcal O_k=\frac1N\operatorname{Tr}X^k.
$$

Use planar boundary counting to show that

$$
\langle \mathcal O_{k_1}\mathcal O_{k_2}\rangle_c\sim \frac1{N^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

The unnormalized connected correlator with two single-trace insertions has $b=2$ and $h=0$, so it scales as

$$
N^{2-b}=N^0.
$$

Each normalized operator contributes an extra factor $1/N$. Therefore

$$
\langle \mathcal O_{k_1}\mathcal O_{k_2}\rangle_c
\sim
\frac{1}{N^2}N^0
=\frac1{N^2}.
$$

</details>

### Exercise 4: Fixed flavor versus Veneziano scaling

Explain why a closed quark loop is suppressed in the ’t Hooft limit with fixed $N_f$, but not necessarily in the Veneziano limit.

<details>
<summary><strong>Solution</strong></summary>

A closed fundamental loop introduces a boundary, costing one power of $N$ compared with an adjoint face. It also carries a flavor sum, producing $N_f$. Thus its relative weight is roughly

$$
\frac{N_f}{N}.
$$

In the ’t Hooft limit with fixed $N_f$, this goes to zero. In the Veneziano limit, $N_f/N$ is held fixed, so quark-loop boundaries can survive at leading order.

</details>

## References

### Standard first pass

- M. Mariño, *Instantons and Large N*, especially the chapters on fatgraphs, large-$N$ QCD, matrix models, and large-$N$ instantons.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the large-$N$ and random-surface chapters.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the sections on the ’t Hooft limit and confinement.

### Deeper references

- G. ’t Hooft, “A Planar Diagram Theory for Strong Interactions,” for the original double-line expansion.
- E. Brézin, C. Itzykson, G. Parisi, and J.-B. Zuber, “Planar Diagrams,” for classic matrix-model large-$N$ diagrammatics.
- E. Witten, “Baryons in the 1/N Expansion,” for physical large-$N$ QCD consequences beyond the pure-glue sector.

## Version history

- **2026-06-27:** Added links to master-field preview and Large-N Yang–Mills.
- **2026-06-27:** Initial polished page deriving double-line notation, Euler-characteristic counting, planar dominance, boundary counting, and quark-loop suppression.
