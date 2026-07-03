---
title: "Cohomological TQFT"
description: "Explains cohomological topological quantum field theories, Q-exact metric dependence, topological twisting, descent, localization, and Donaldson–Witten-type examples."
sidebar:
  label: "Cohomological TQFT"
  order: 3
level: Advanced
status: "Polished draft"
source: "Witten; Atiyah; Schwarz; Donaldson–Witten; Pestun et al.; Nakahara; Frankel; Altland–Simons."
topics:
  - cohomological TQFT
  - topological twist
  - BRST cohomology
  - localization
  - descent equations
  - Donaldson-Witten theory
canonicalTopics:
  - cohomological-tqft
  - topological-twist
  - q-exact-metric-dependence
  - descent-observables
  - localization
researchStatus:
  established:
    - "Cohomological TQFTs are a standard class of topological field theories in which protected observables live in the cohomology of a nilpotent scalar charge."
    - "Metric independence often follows when the stress tensor is Q-exact, modulo boundary, anomaly, compactness, and contact-term caveats."
  active:
    - "Modern uses include supersymmetric localization, enumerative geometry, boundary/defect refinements, and relations to extended TQFT and symmetry TFT."
---

## Summary

A **cohomological topological quantum field theory** is a QFT equipped with a nilpotent scalar charge $Q$ such that physical observables are $Q$-cohomology classes. The basic algebra is

$$
Q^2=0,
\qquad
\mathcal O\sim\mathcal O+\{Q,\Lambda\},
\qquad
\{Q,\mathcal O\}=0.
$$

Here $\mathcal O$ is a physical observable if it is $Q$-closed, and two observables are identified if they differ by a $Q$-exact operator. The reason this produces topology is that the stress tensor is often $Q$-exact,

$$
T_{\mu\nu}=\{Q,G_{\mu\nu}\},
$$

so metric variations of correlation functions of $Q$-closed observables vanish, up to important caveats.

The slogan is

$$
\text{cohomological TQFT}
=
\text{QFT whose protected sector is }Q\text{-cohomology}.
$$

<figure class="doc-figure" style="--figure-width: 52rem;">

![A diagram showing the cohomological TQFT mechanism: a nilpotent scalar Q defines observables in Q-cohomology, Q-exact stress tensor gives metric independence, and Q-exact deformation gives localization.](/figures/symmetry-anomalies-topology/cohomological-tqft-mechanism.svg)

<figcaption>

The cohomological mechanism. A nilpotent scalar $Q$ defines physical observables by cohomology. If metric dependence and deformation terms are $Q$-exact, protected correlation functions are independent of the metric and often localize to fixed points or classical moduli spaces.

</figcaption>
</figure>

Cohomological TQFTs are not merely formal tricks. They connect QFT to geometry: Donaldson invariants, Gromov–Witten-type counts, supersymmetric localization, equivariant cohomology, moduli spaces, and index theory all appear naturally in this language.

## Prerequisites

You should know [What Is a TQFT?](/symmetry-anomalies-topology/topological-qft/what-is-a-tqft/) and [Metric Independence](/symmetry-anomalies-topology/topological-qft/metric-independence/). You should also be comfortable with BRST-like cohomology, path integrals, differential forms, gauge fixing, and the idea that a symmetry charge can act as a differential.

The page uses graded commutators schematically. For a fermionic charge $Q$ and an operator $\mathcal O$, write $\{Q,\mathcal O\}$ when $\mathcal O$ is fermionic and $[Q,\mathcal O]$ when $\mathcal O$ is bosonic. Most formulas below use $\{Q,\cdot\}$ as a compact notation for the appropriate graded bracket.

## Core idea

A cohomological TQFT turns the usual question

$$
\text{What is the full local quantum dynamics?}
$$

into the protected question

$$
\text{What survives in }Q\text{-cohomology?}
$$

The nilpotent charge $Q$ plays the role of a differential. Operators are sorted into three classes:

| Type | Condition | Physical role |
|---|---|---|
| $Q$-closed | $\{Q,\mathcal O\}=0$ | Candidate protected observable |
| $Q$-exact | $\mathcal O=\{Q,\Lambda\}$ | Trivial inside protected correlators |
| Non-closed | $\{Q,\mathcal O\}\neq0$ | Not a protected observable |

If the vacuum or path-integral measure is $Q$-invariant, then inserting a $Q$-exact operator into a correlator of $Q$-closed operators gives zero:

$$
\left\langle \{Q,\Lambda\}\,\mathcal O_1\cdots\mathcal O_n\right\rangle=0.
$$

This identity is the engine behind both topological invariance and localization.

## Setup and conventions

Let $S$ be an action invariant under a fermionic scalar charge $Q$,

$$
\{Q,S\}=0.
$$

The protected observables obey

$$
\{Q,\mathcal O_i\}=0.
$$

If the path-integral measure is also $Q$-invariant, then for any $\Lambda$,

$$
\left\langle \{Q,\Lambda\}\right\rangle=0
$$

inside correlators of $Q$-closed insertions, assuming no boundary contribution from field space.

A deformation of the action by a $Q$-exact term,

$$
S_t=S+t\{Q,V\},
$$

does not change protected correlators:

$$
\frac{d}{dt}
\left\langle \mathcal O_1\cdots\mathcal O_n\right\rangle_t
=
i\left\langle \{Q,V\}\mathcal O_1\cdots\mathcal O_n\right\rangle_t
=0
$$

in Lorentzian notation, with the analogous sign in Euclidean signature. This is the localization principle in its cohomological form.

:::note[Source note]
This page uses the physicist’s cohomological convention common in BRST and topological twisting. Mathematically, the same structure is often phrased as a cochain complex, with $Q$ acting as a differential and observables represented by cohomology classes.
:::

## Metric independence from a Q-exact stress tensor

The stress tensor measures metric dependence:

$$
T_{\mu\nu}(x)=\frac{2}{\sqrt{|g|}}\frac{\delta S}{\delta g^{\mu\nu}(x)}
$$

up to the sign convention for Lorentzian versus Euclidean signature. If

$$
T_{\mu\nu}=\{Q,G_{\mu\nu}\},
$$

then changing the metric inserts a $Q$-exact operator. For $Q$-closed observables,

$$
\frac{\delta}{\delta g^{\mu\nu}(x)}
\left\langle \mathcal O_1\cdots\mathcal O_n\right\rangle
\propto
\left\langle \{Q,G_{\mu\nu}(x)\}\mathcal O_1\cdots\mathcal O_n\right\rangle
=0.
$$

Therefore protected correlators do not depend on the metric. They may depend on topology, smooth structure, choice of bundle, cohomology class, framing, spin structure, or boundary condition, but not on local distances.

This is the cohomological analogue of a familiar BRST statement: unphysical variations are exact and decouple from physical observables.

:::caution[Metric independence has hypotheses]
The argument assumes no anomaly in the $Q$ symmetry, no boundary contribution in spacetime or field space, no contact-term collision with other insertions, and no failure of compactness. In many important applications, exactly these caveats carry the interesting geometry.
:::

## Topological twisting

Many cohomological TQFTs arise from supersymmetric QFT by **topological twisting**. The problem is that ordinary supercharges transform as spinors under the Lorentz group. A scalar topological charge does not exist in the untwisted theory. A twist modifies the Lorentz group by mixing it with an internal R-symmetry so that some supercharge becomes a scalar.

Schematically, one replaces

$$
G_{\mathrm{Lorentz}}
$$

by a diagonal subgroup of

$$
G_{\mathrm{Lorentz}}\times G_R.
$$

After the twist, a component of the supersymmetry generator becomes a scalar $Q$. If it squares to zero, or to a gauge transformation on gauge-invariant operators,

$$
Q^2=0
$$

in the physical sector, then one can form a cohomological TQFT.

Donaldson–Witten theory is the standard four-dimensional example. It is obtained by twisting four-dimensional $\mathcal N=2$ supersymmetric Yang–Mills theory. Its protected observables compute smooth four-manifold invariants.

The twist is not cosmetic. It changes how fields transform under rotations. Fermions can become differential forms, spinor indices can be reinterpreted as form indices, and the resulting theory can be placed naturally on curved manifolds without requiring covariantly constant spinors.

## Descent observables

Cohomological TQFTs often produce families of observables by **descent**. Suppose $\mathcal O^{(0)}$ is a $Q$-closed local operator. A descent tower is a sequence of differential-form operators $\mathcal O^{(p)}$ obeying

$$
d\mathcal O^{(p)}=\{Q,\mathcal O^{(p+1)}\}.
$$

If $\gamma_p$ is a closed $p$-cycle, then

$$
\mathcal O(\gamma_p)=\int_{\gamma_p}\mathcal O^{(p)}
$$

is $Q$-closed:

$$
\{Q,\mathcal O(\gamma_p)\}
=
\int_{\gamma_p}\{Q,\mathcal O^{(p)}\}
=
\int_{\gamma_p}d\mathcal O^{(p-1)}
=0.
$$

The observable depends only on the homology class of $\gamma_p$, because deforming the cycle changes the integral by a $Q$-exact term.

This is one of the cleanest bridges between local QFT and topology. A local operator generates observables attached to cycles of different dimensions.

## Localization

A $Q$-exact deformation

$$
S_t=S+t\{Q,V\}
$$

does not change protected correlators. If the Euclidean bosonic part of $\{Q,V\}$ is nonnegative, one can take

$$
t\to\infty.
$$

The path integral then localizes onto the locus where the bosonic deformation vanishes:

$$
\{Q,V\}_{\mathrm{bos}}=0.
$$

The original infinite-dimensional integral becomes an integral over a finite-dimensional moduli space, times a one-loop determinant and possible instanton or fluctuation corrections. In words:

$$
\text{path integral}
\quad\longrightarrow\quad
\text{localized integral over }Q\text{-fixed configurations}.
$$

This is the same structural reason supersymmetric localization can compute exact partition functions, indices, Wilson-loop expectation values, and protected correlators in many supersymmetric QFTs.

:::note[Source note]
In the localization literature, the cohomological charge is often called $Q$ even when it arises from a chosen supercharge rather than from a topological twist. The shared logic is $Q$-exact deformation and $Q$-cohomology.
:::

## Donaldson–Witten theory as the model example

The classic cohomological TQFT is Donaldson–Witten theory. It arises from twisting four-dimensional $\mathcal N=2$ Yang–Mills theory. Its protected observables are related to Donaldson invariants of smooth four-manifolds.

Very schematically, the localization equations involve anti-self-dual connections,

$$
F_A^+=0,
$$

where $F_A^+$ is the self-dual part of the curvature. The path integral localizes on the moduli space of instantons. Correlation functions of descent observables become intersection-theoretic data on that moduli space.

The details are subtle: compactification of instanton moduli spaces, reducible connections, wall crossing, orientation choices, and later Seiberg–Witten refinements all matter. But the conceptual lesson is simple and profound:

$$
\text{topologically twisted QFT can compute invariants of smooth manifolds}.
$$

This is one of the clearest demonstrations that QFT is not merely a language for particles; it can produce deep geometric invariants.

## Relation to BRST and gauge fixing

Cohomological TQFTs resemble BRST gauge theory because both use a nilpotent fermionic charge. But the interpretation differs.

In ordinary gauge fixing, BRST cohomology removes gauge redundancy and identifies physical states or operators. The BRST symmetry is a bookkeeping device for a theory that may not be topological.

In a cohomological TQFT, the $Q$-cohomology is the protected topological sector itself. The exactness of the stress tensor or metric dependence is what makes the theory topological.

The two ideas often coexist. A cohomological gauge theory can have both gauge BRST structure and a topological scalar charge. In many formulations they are combined into one total differential.

## Boundaries and defects

On a manifold with boundary, the identity

$$
\int_M d(\cdots)=0
$$

is no longer automatic. Metric independence, descent, and localization can all acquire boundary terms. To preserve $Q$, one may need boundary degrees of freedom, boundary conditions, or boundary counterterms.

Similarly, defects can preserve only part of the cohomological structure. A defect may support its own defect-local $Q$-cohomology. Correlators can depend on how descent cycles intersect or end on defects.

This is not a nuisance. It is how cohomological TQFT connects to boundary TQFT, categories of branes, Floer theory, knot homology, and modern extended TQFT.

## Common pitfalls

**“Q-exact means zero as an operator.”** No. A $Q$-exact operator is trivial inside $Q$-closed correlators under the usual hypotheses. It need not vanish as an operator in the full theory.

**“Metric-independent means no stress tensor.”** The stress tensor may exist, but it is $Q$-exact. Its insertions vanish in protected correlators, not necessarily in all correlators.

**“Every supersymmetric theory is a cohomological TQFT.”** No. One needs a suitable scalar nilpotent charge, usually after a twist or in a protected subsector, and one needs the metric-dependence argument to work.

**“Localization is a saddle-point approximation.”** It is an exact deformation argument for protected quantities, followed by a semiclassical-looking evaluation in a limit where the deformation is large.

**“Topological twisting is just Wick rotation for supersymmetry.”** No. Twisting changes the Lorentz representation assignment of fields by combining spacetime symmetry with R-symmetry.

## Relations to other pages

[Metric Independence](/symmetry-anomalies-topology/topological-qft/metric-independence/) gives the stress-tensor criterion. [Chern–Simons Theory](/symmetry-anomalies-topology/topological-qft/chern-simons-theory/) gives the main Schwarz-type contrast: a metric-independent action rather than a $Q$-exact stress tensor. [Donaldson–Witten Theory Preview](/symmetry-anomalies-topology/topological-qft/donaldson-witten-theory-preview/) will develop the four-dimensional example.

The Gauge Redundancy and BRST chapter explains the gauge-fixing side of nilpotent cohomology. The Symmetry TFT and Anomaly Inflow chapter explains how topological bulk theories encode symmetry and anomaly data.

## Research status

The basic cohomological TQFT mechanism is established. Topological twisting, descent, localization, and Donaldson–Witten theory are standard parts of the interface between QFT and geometry.

Active directions include extended and boundary versions, relations to derived geometry, categorified invariants, noncompact moduli spaces, defects, equivariant refinements, and exact computations in supersymmetric QFT. The physics moral is stable: $Q$-cohomology turns a quantum field theory into a machine for protected topological data.

## Exercises

### Exercise 1: Q-exact insertions decouple

Assume the measure and action are $Q$-invariant, and $\{Q,\mathcal O_i\}=0$. Show that

$$
\left\langle \{Q,\Lambda\}\mathcal O_1\cdots\mathcal O_n\right\rangle=0.
$$

<details><summary><strong>Solution</strong></summary>

Use $Q$-invariance of the path integral:

$$
0=\left\langle \{Q,\Lambda\mathcal O_1\cdots\mathcal O_n\}\right\rangle.
$$

Expanding with the graded Leibniz rule gives

$$
0=
\left\langle \{Q,\Lambda\}\mathcal O_1\cdots\mathcal O_n\right\rangle
+\sum_i(\text{sign})\left\langle \Lambda\mathcal O_1\cdots\{Q,\mathcal O_i\}\cdots\mathcal O_n\right\rangle.
$$

The second term vanishes because each $\mathcal O_i$ is $Q$-closed. Thus the $Q$-exact insertion decouples.

</details>

### Exercise 2: Metric independence from a Q-exact stress tensor

Suppose

$$
T_{\mu\nu}=\{Q,G_{\mu\nu}\}.
$$

Explain why correlators of $Q$-closed observables are metric-independent, assuming no boundary or anomaly terms.

<details><summary><strong>Solution</strong></summary>

A variation of the metric inserts the stress tensor:

$$
\delta_g\langle\mathcal O_1\cdots\mathcal O_n\rangle
\propto
\int_M\delta g^{\mu\nu}
\langle T_{\mu\nu}\mathcal O_1\cdots\mathcal O_n\rangle.
$$

Using $T_{\mu\nu}=\{Q,G_{\mu\nu}\}$, the insertion is $Q$-exact. By Exercise 1, $Q$-exact insertions vanish inside correlators of $Q$-closed observables. Therefore the metric variation is zero.

</details>

### Exercise 3: Descent and homology

Let $d\mathcal O^{(p)}=\{Q,\mathcal O^{(p+1)}\}$. Show that $\int_{\gamma_p}\mathcal O^{(p)}$ depends only on the homology class of $\gamma_p$ in $Q$-cohomology.

<details><summary><strong>Solution</strong></summary>

If $\gamma_p$ is deformed by adding a boundary, $\gamma_p\mapsto\gamma_p+\partial C_{p+1}$, then

$$
\int_{\partial C_{p+1}}\mathcal O^{(p)}
=
\int_{C_{p+1}}d\mathcal O^{(p)}
=
\int_{C_{p+1}}\{Q,\mathcal O^{(p+1)}\}
=
\left\{Q,\int_{C_{p+1}}\mathcal O^{(p+1)}\right\}.
$$

The change is $Q$-exact, so the observable depends only on the homology class inside $Q$-cohomology.

</details>

## References

- E. Witten, “Topological Quantum Field Theory,” *Communications in Mathematical Physics* **117** (1988).
- E. Witten, “Mirror Manifolds and Topological Field Theory,” for A/B-model topological strings and descent examples.
- M. Atiyah, *The Geometry and Physics of Knots*, for the geometric viewpoint on topological field theory.
- A. Schwarz, “The Partition Function of Degenerate Quadratic Functional and Ray–Singer Invariants,” for Schwarz-type topological theories.
- V. Pestun et al., “Localization Techniques in Quantum Field Theories,” especially the review of equivariant cohomology and cohomological field theories.
- M. Nakahara, *Geometry, Topology and Physics*, for differential forms, bundles, characteristic classes, monopoles, and instantons.
- T. Frankel, *The Geometry of Physics*, for exterior forms, geometry, gauge fields, Chern forms, and index-theoretic background.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for topological field theory, Wess–Zumino terms, and Chern–Simons terms in quantum matter.

## Version history

- **2026-06-22:** Initial polished draft. Added the $Q$-cohomology mechanism, $Q$-exact stress tensor criterion, twisting, descent, localization, Donaldson–Witten orientation, boundary caveats, and exercises.
