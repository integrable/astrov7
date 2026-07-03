---
title: "Metric Independence"
description: "Explains metric independence in TQFT through stress tensors, Schwarz-type actions, cohomological Q-exactness, contact terms, framing, and boundary subtleties."
sidebar:
  label: "Metric Independence"
  order: 2
level: Advanced
status: "Polished draft"
source: "Schwarz; Witten; Atiyah; Chern–Simons and BF theory references; Nakahara; Frankel; Altland–Simons."
topics:
  - metric independence
  - topological quantum field theory
  - stress tensor
  - Schwarz-type TQFT
  - cohomological TQFT
  - framing anomaly
canonicalTopics:
  - metric-independence
  - topological-stress-tensor
  - schwarz-type-tqft
  - cohomological-tqft
researchStatus:
  established:
    - "Metric independence is the central diagnostic of topological behavior, but it can arise by different mechanisms and may be modified by contact terms, boundary terms, anomalies, or framing dependence."
  active:
    - "Modern extended, fermionic, non-semisimple, and defect-rich TQFTs require refined versions of metric independence involving tangential structures, stratified spaces, and boundary-defect data."
---

## Summary

Metric independence is the first diagnostic of a topological quantum field theory. Roughly, a protected TQFT observable should not change when the spacetime metric is smoothly deformed:

$$
\frac{\delta}{\delta g_{\mu\nu}(x)}
\langle \mathcal O_1\cdots\mathcal O_n\rangle=0.
$$

The precise statement depends on what is being held fixed: topology, orientation, framing, spin structure, background bundles, boundary conditions, defect positions, and operator insertions.

There are two standard mechanisms.

In a **Schwarz-type** TQFT, the action itself is written without a metric. Chern–Simons and BF theory are the canonical examples.

In a **cohomological** or **Witten-type** TQFT, the action may use a metric, but changes of the metric are $Q$-exact. For $Q$-closed observables, $Q$-exact deformations do not change correlation functions:

$$
T_{\mu\nu}=\{Q,G_{\mu\nu}\}.
$$

<figure class="doc-figure" style="--figure-width: 54rem;">

![Two mechanisms for metric independence: metric-free Schwarz-type actions and Q-exact cohomological metric dependence.](/figures/symmetry-anomalies-topology/metric-independence-mechanisms.svg)

<figcaption>

Two common mechanisms for metric independence. Schwarz-type theories use actions and observables that do not require a metric. Cohomological theories may use a metric, but metric variation is $Q$-exact, so $Q$-closed observables are deformation-invariant up to anomalies, boundaries, and contact terms.

</figcaption>
</figure>

The slogan “TQFT does not depend on the metric” is right, but only after these qualifications are understood.

## Prerequisites

Read [What Is a TQFT?](/symmetry-anomalies-topology/topological-qft/what-is-a-tqft/) first. You should also know the stress tensor as the response to metric variation, differential forms, gauge fields, Wilson lines, and basic BRST-like cohomology.

The page uses Lorentzian and Euclidean notation schematically. Most TQFT path integrals are cleanest in Euclidean signature on closed manifolds, while Hamiltonian interpretations depend on slicing a spacetime manifold as an evolution bordism.

## Core idea

In an ordinary QFT, the metric appears everywhere. It defines distances, volume elements, kinetic operators, propagators, energy, and causal structure. Varying the metric inserts the stress tensor. Schematically,

$$
\delta_g \log Z[g]
=
\frac{i}{2}\int d^dx\,\sqrt{|g|}\,
\langle T^{\mu\nu}(x)\rangle\,\delta g_{\mu\nu}(x)
$$

in Lorentzian conventions, with corresponding Euclidean sign changes.

Thus, if a theory has no physical dependence on $g_{\mu\nu}$, its stress-tensor response must vanish in the appropriate sense.

The naive criterion is

$$
T_{\mu\nu}=0.
$$

The more flexible cohomological criterion is

$$
T_{\mu\nu}=\{Q,G_{\mu\nu}\},
$$

because $Q$-exact insertions vanish in correlators of $Q$-closed observables, assuming the measure is $Q$-invariant and there are no boundary or contact obstructions.

## Setup and conventions

Let

$$
Z[M,g]=\int \mathcal D\Phi\,e^{iS[\Phi;g]}
$$

be a QFT on a $d$-manifold $M$ with metric $g$. The stress tensor is defined, up to conventional signs, by variation with respect to the metric:

$$
\delta S
=
\frac12\int_M d^dx\,\sqrt{|g|}\,T^{\mu\nu}\delta g_{\mu\nu}.
$$

In Euclidean signature, many authors define

$$
T^{\mu\nu}
=
\frac{2}{\sqrt g}\frac{\delta S_E}{\delta g_{\mu\nu}},
$$

or with a minus sign depending on whether $S_E$ appears as $e^{-S_E}$. This page uses stress-tensor formulas schematically and flags sign-sensitive statements.

A **topological observable** is an observable whose correlation functions are invariant under smooth deformations of the metric and, often, under smooth deformations of the observable’s support avoiding other insertions.

:::note[Source note]
Metric independence should be compared only after checking signature, stress-tensor sign, and path-integral convention. The criterion “metric variation inserts $T_{\mu\nu}$” is universal; the prefactor is convention-dependent.
:::

## Stress tensor criterion

Suppose $\mathcal O_i$ are metric-independent insertions away from coincident points. Then formally,

$$
\frac{\delta}{\delta g_{\mu\nu}(x)}
\langle \mathcal O_1\cdots\mathcal O_n\rangle
\sim
\langle T^{\mu\nu}(x)\mathcal O_1\cdots\mathcal O_n\rangle
+\text{contact terms}.
$$

If the right-hand side vanishes, the correlator is locally metric-independent.

This is the cleanest physical diagnostic:

$$
\text{metric independence}
\quad\Longleftrightarrow\quad
\text{stress-tensor insertion is trivial}
$$

for the relevant observables.

But “trivial” can mean several things:

| Mechanism | Meaning |
|---|---|
| Zero stress tensor | $T_{\mu\nu}$ vanishes as an operator or constraint. |
| Q-exact stress tensor | $T_{\mu\nu}=\{Q,G_{\mu\nu}\}$, so it vanishes in $Q$-cohomology. |
| Infrared topological sector | Metric-dependent massive modes decouple from protected observables. |
| Anomalous/framed case | Metric dependence reduces to dependence on extra topological or tangential structure. |

The rest of the page unpacks these mechanisms.

## Schwarz-type metric independence

A Schwarz-type TQFT is written using an action that does not need a metric.

The abelian BF action in $d$ dimensions is schematically

$$
S_{\mathrm{BF}}=\frac{N}{2\pi}\int_M B_{d-p-1}\wedge dA_p.
$$

This uses the wedge product and orientation of $M$, not a Hodge star. Since no metric is used, classical metric variation gives

$$
T_{\mu\nu}=0
$$

before gauge fixing and regularization subtleties.

Similarly, three-dimensional Chern–Simons theory has action

$$
S_{\mathrm{CS}}
=
\frac{k}{4\pi}\int_M
\operatorname{tr}\left(A\wedge dA+\frac{2i}{3}A\wedge A\wedge A\right),
$$

using Hermitian gauge fields. The action uses a connection, orientation, and trace pairing, but not a metric.

:::caution[Gauge fixing can introduce a metric]
Even if the classical action is metric-free, gauge fixing may introduce a metric. A good quantization must show that metric dependence cancels in gauge-invariant observables, or account for the remaining anomaly or framing dependence.
:::

Schwarz-type metric independence is the most direct. It is also less automatic than it looks: determinants, regularization, zero modes, and measure choices can reintroduce dependence on auxiliary structures.

## Cohomological metric independence

A cohomological TQFT has a nilpotent scalar operator $Q$,

$$
Q^2=0
$$

up to gauge transformations or other harmless symmetries, and physical observables are $Q$-closed modulo $Q$-exact operators:

$$
Q\mathcal O=0,\qquad
\mathcal O\sim \mathcal O+\{Q,\Lambda\}.
$$

Metric independence follows if the stress tensor is $Q$-exact:

$$
T_{\mu\nu}=\{Q,G_{\mu\nu}\}.
$$

Then

$$
\frac{\delta}{\delta g_{\mu\nu}(x)}
\langle \mathcal O_1\cdots\mathcal O_n\rangle
\sim
\langle \{Q,G_{\mu\nu}(x)\}\mathcal O_1\cdots\mathcal O_n\rangle=0
$$

for $Q$-closed insertions, assuming the path-integral measure is $Q$-invariant and no boundary terms appear.

This is the mechanism behind Witten-type cohomological field theories. The action may be full of metric-dependent terms, but those terms are cohomologically invisible to protected observables.

## Q-exact deformations

A useful generalization is the statement that adding a $Q$-exact term does not change $Q$-closed correlators:

$$
S\mapsto S+t\{Q,V\}.
$$

Differentiate with respect to $t$:

$$
\frac{d}{dt}\langle \mathcal O\rangle_t
=
-\langle \{Q,V\}\mathcal O\rangle_t.
$$

If $Q\mathcal O=0$ and the measure is $Q$-invariant, the right-hand side vanishes. Therefore

$$
\frac{d}{dt}\langle \mathcal O\rangle_t=0.
$$

This is also the intuition behind localization: if a deformation is $Q$-exact, one can take $t$ to a convenient limit without changing protected observables.

Metric independence is the special case where changing $g_{\mu\nu}$ changes the action by a $Q$-exact deformation.

## Topological observables and contact terms

Metric independence is rarely a statement about every possible quantity. It is a statement about protected observables.

A Wilson loop in Chern–Simons theory is topological, but its expectation value can depend on framing. Local gauge-variant expressions are not observables. Operators that are not $Q$-closed in a cohomological TQFT need not have metric-independent correlators.

Contact terms require care. The formula

$$
\frac{\delta}{\delta g_{\mu\nu}(x)}
\langle \mathcal O_1\cdots\mathcal O_n\rangle
\sim
\langle T^{\mu\nu}(x)\mathcal O_1\cdots\mathcal O_n\rangle
$$

can receive contact terms when $x$ hits an operator insertion or defect. If the observables themselves depend on the metric, their metric variation contributes too.

Thus a precise topological statement should specify:

1. which observables are allowed;
2. what structures are held fixed;
3. whether supports of defects are allowed to move;
4. what happens at boundaries and corners;
5. whether there are anomalies or framing dependencies.

## Framing and anomalies

Chern–Simons theory is the classic warning. Classically its action is metric-independent. Quantum mechanically, regularization of Wilson loops and determinants can introduce **framing dependence**. A framed knot is not merely an embedded loop; it is a loop together with a choice of nonzero normal vector field, or equivalently a small ribbon thickening.

The theory is still topological, but not purely invariant under all choices one might have expected. The invariant is naturally an invariant of framed links and framed three-manifolds, or it must be corrected by additional data.

This is not a failure of TQFT. It is a lesson: quantum TQFTs often depend on refined topological or tangential structures. Orientation, spin structure, Pin structure, framing, and background bundles can all be part of the definition.

An anomaly is precisely the obstruction to making a symmetry or structure independence exact without adding extra data or a bulk inflow theory.

## Boundaries and metric independence

On a closed manifold, metric independence can be stated cleanly. On a manifold with boundary, variations can produce boundary terms.

For example, a total derivative in the metric variation may vanish on a closed manifold but survive on a boundary:

$$
\int_M d(\cdots)=\int_{\partial M}(\cdots).
$$

A TQFT with boundary therefore needs boundary conditions, boundary degrees of freedom, or boundary counterterms. Chern–Simons theory on a manifold with boundary is tied to chiral boundary dynamics. SymTFT uses topological boundary conditions to encode choices of global form, gauging, or physical QFT boundary.

Metric independence must then include the boundary data:

$$
\text{bulk TQFT}+\text{boundary condition}
$$

rather than the bulk action alone.

## Examples

### BF theory

The BF action

$$
S=\frac{N}{2\pi}\int B\wedge dA
$$

does not use a Hodge star. Its equations of motion impose flatness-type constraints:

$$
dA=0,\qquad dB=0
$$

in the abelian case. Observables are controlled by holonomy and linking, not local wave propagation.

### Chern–Simons theory

Chern–Simons theory is metric-independent at the classical level, but its quantum definition requires care with framing and level quantization. Wilson-loop correlators are topological link invariants once the correct framing data are included.

### Donaldson–Witten theory

Donaldson–Witten theory is a cohomological TQFT obtained by twisting supersymmetric Yang–Mills theory. The action uses a metric, but protected observables are metric-independent because stress-tensor insertions are $Q$-exact. The theory computes smooth four-manifold invariants rather than ordinary scattering amplitudes.

### Finite gauge theory

A finite gauge theory such as Dijkgraaf–Witten theory sums over flat finite-group bundles. There is no local metric-dependent kinetic term. The partition function depends on topology of the manifold and on cohomological action data.

## Metric independence versus diffeomorphism invariance

Diffeomorphism invariance and metric independence are related but not identical.

A generally covariant ordinary QFT can be diffeomorphism-invariant while still depending on the metric. For example, a scalar field action

$$
S=\frac12\int d^dx\,\sqrt g\,g^{\mu\nu}\partial_\mu\phi\,\partial_\nu\phi
$$

is diffeomorphism-invariant, but it certainly depends on $g_{\mu\nu}$.

Metric independence is stronger. It says that changing the metric without changing topology does not affect protected data. In stress-tensor language, diffeomorphism invariance gives conservation laws, while metric independence says the stress-tensor insertion is trivial in the relevant sense.

## Common pitfalls

**“Diffeomorphism-invariant” means “topological.”** No. General relativity and scalar field theory can be diffeomorphism-invariant but metric-dependent.

**“The classical action has no metric, so the quantum theory is automatically metric-independent.”** Gauge fixing, regularization, determinants, and anomalies can introduce dependence on auxiliary structures.

**“Metric independence means no dependence on framing or spin structure.”** No. Framing and spin structure are not metrics, but they are extra geometric/topological structures.

**“Q-exact means zero.”** A $Q$-exact operator has vanishing correlators with $Q$-closed insertions only under assumptions: $Q$-invariant measure, no boundary obstruction, and no anomaly.

**“All observables are topological.”** Usually only a protected subsector is topological. Nonprotected insertions can have metric dependence even inside a cohomological theory.

## Relations to other pages

[What Is a TQFT?](/symmetry-anomalies-topology/topological-qft/what-is-a-tqft/) gives the broad definition. This page supplies the diagnostic.

[Cohomological TQFT](/symmetry-anomalies-topology/topological-qft/cohomological-tqft/) develops the $Q$-exact mechanism more deeply. [Chern–Simons Theory](/symmetry-anomalies-topology/topological-qft/chern-simons-theory/) and [BF Theory](/symmetry-anomalies-topology/topological-qft/bf-theory/) give the key Schwarz-type examples.

[Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/anomaly-inflow/) explains what happens when metric or background independence fails on a boundary and is restored by a bulk theory.

## Research status

The basic stress-tensor and $Q$-exact criteria are standard. The subtle parts are not whether metric independence matters, but what extra structures a given theory requires and how fully extended boundary/defect data should be encoded.

Active research directions include framed and spin refinements, non-semisimple TQFTs, relative and anomalous theories, metric independence on stratified manifolds with defects, and the precise relation between topological phases, SymTFT, and extended TQFT.

## Exercises

### Exercise 1: Stress tensor and partition function

Assume

$$
\delta \log Z[g]=\frac{i}{2}\int d^dx\,\sqrt{|g|}\,
\langle T^{\mu\nu}\rangle\delta g_{\mu\nu}.
$$

What condition on $\langle T^{\mu\nu}\rangle$ implies local metric independence of $Z[g]$?

<details><summary><strong>Solution</strong></summary>

If

$$
\langle T^{\mu\nu}(x)\rangle=0
$$

for all $x$, up to contact terms or anomalies, then the first variation of $\log Z[g]$ under arbitrary local metric deformations vanishes. This is the infinitesimal statement of metric independence.

</details>

### Exercise 2: Schwarz-type action

Explain why

$$
S=\frac{N}{2\pi}\int B\wedge dA
$$

is metric-independent, while

$$
S=\frac12\int d^dx\,\sqrt g\,g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi
$$

is not.

<details><summary><strong>Solution</strong></summary>

The BF action uses only differential forms, the wedge product, and orientation. It does not require $g_{\mu\nu}$ or the Hodge star. The scalar action explicitly contains $\sqrt g$ and $g^{\mu\nu}$, so varying the metric changes the action and inserts the scalar stress tensor.

</details>

### Exercise 3: Q-exact metric dependence

Suppose $T_{\mu\nu}=\{Q,G_{\mu\nu}\}$ and $Q\mathcal O_i=0$. Show why the metric derivative of $\langle\mathcal O_1\cdots\mathcal O_n\rangle$ vanishes formally.

<details><summary><strong>Solution</strong></summary>

The metric derivative inserts $T_{\mu\nu}$:

$$
\delta_g\langle\mathcal O_1\cdots\mathcal O_n\rangle
\sim
\langle \{Q,G_{\mu\nu}\}\mathcal O_1\cdots\mathcal O_n\rangle.
$$

If the measure is $Q$-invariant and the insertions are $Q$-closed, the expectation value of a $Q$-exact insertion vanishes. Therefore the protected correlator is metric-independent, modulo boundary terms, contact terms, and anomalies.

</details>

### Exercise 4: Diffeomorphism invariance is not enough

Give an example of a diffeomorphism-invariant theory that is not a TQFT.

<details><summary><strong>Solution</strong></summary>

A scalar field on a curved manifold has action

$$
S=\frac12\int d^dx\,\sqrt g\,g^{\mu\nu}\partial_\mu\phi\partial_\nu\phi.
$$

This action is diffeomorphism-invariant because it is written geometrically. But it depends explicitly on the metric. Its correlators depend on distances and eigenvalues of the Laplacian, so it is not topological.

</details>

## References

- Albert Schwarz, early work on metric-independent topological quantum field theories.
- Edward Witten, “Topological Quantum Field Theory.”
- Edward Witten, “Quantum Field Theory and the Jones Polynomial.”
- Michael Atiyah, “Topological Quantum Field Theories.”
- Daniel Birmingham, Matthias Blau, Mark Rakowski, and George Thompson, “Topological Field Theory.”
- Daniel S. Freed, “Remarks on Chern–Simons Theory.”
- A. M. Polyakov, *Gauge Fields and Strings*, especially topology of gauge fields and loop dynamics.
- Mikio Nakahara, *Geometry, Topology and Physics*, for differential forms, Chern classes, instantons, monopoles, and gauge bundles.
- Theodore Frankel, *The Geometry of Physics*, for stress-tensor geometry, forms, Chern forms, and gauge-field intuition.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, especially topological field theory, response terms, Wess–Zumino terms, Chern–Simons terms, and topological gauge theory.

## Version history

- 2026-06-22: Initial polished draft. Added stress-tensor criterion, Schwarz-type and cohomological mechanisms, framing and boundary caveats, examples, and exercises.
