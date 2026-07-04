---
title: "Vacuum Expectation Values"
description: "Defines vacuum expectation values as state-dependent one-point functions and explains how sources, limits, renormalization, and gauge invariance affect their use as nonperturbative diagnostics."
sidebar:
  label: "Vacuum Expectation Values"
  order: 1
level: Graduate
status: "Polished draft"
source: "Coleman, Aspects of Symmetry, Secret Symmetry; Srednicki §§21,30–31; Schwartz §§18.1,28; Zinn-Justin."
topics:
  - vacuum expectation values
  - order parameters
  - spontaneous symmetry breaking
  - source selection
  - effective potential
  - condensates
  - gauge invariance
canonicalTopics:
  - nonperturbative-qft
  - vacuum-structure
  - vacuum-expectation-values
  - spontaneous-symmetry-breaking
  - order-parameters
  - effective-potential
researchStatus:
  established:
    - "A vacuum expectation value is a one-point function in a specified state; as a phase diagnostic it must be defined with the correct source, volume, renormalization, and gauge-invariance data."
  active:
    - "In strongly coupled gauge theories, condensates and local VEVs are often insufficient by themselves; robust phase identification may require spectra, extended operators, anomalies, and lattice or dual evidence."
---

## Summary

A vacuum expectation value, or VEV, is a one-point function in a specified vacuum state:

$$
\langle\mathcal O\rangle_\Omega
=\frac{\langle\Omega|\mathcal O|\Omega\rangle}{\langle\Omega|\Omega\rangle}.
$$

This formula looks harmless, but the notation hides almost everything that matters nonperturbatively: which vacuum $|\Omega\rangle$ is chosen, whether the theory is in finite or infinite volume, whether a source or boundary condition selected the state, whether $\mathcal O$ is a renormalized operator, and whether $\mathcal O$ is gauge invariant.

VEVs are among the most useful diagnostics of phases. They detect symmetry breaking, condensates, density, background response, and vacuum selection. They are also among the easiest diagnostics to misuse. A nonzero VEV can be a physical order parameter, a scheme-dependent condensate, a gauge-fixed artifact, or merely a statement about a source-deformed state.

The cleanest nonperturbative definition uses a finite-volume generating functional with a source:

$$
Z_V[J]=\int\mathcal D\Phi\,
\exp\left[-S_E[\Phi]+J\int_V d^dx\,\mathcal O(x)\right],
$$

and then defines the source-selected one-point function by

$$
m_V(J)=\frac{1}{V}\frac{\partial}{\partial J}\log Z_V[J].
$$

When spontaneous symmetry breaking is involved, the order of limits is part of the definition:

$$
\langle\mathcal O\rangle_{\pm}
=\lim_{J\to0^{\pm}}\lim_{V\to\infty}m_V(J).
$$

Taking $J\to0$ before $V\to\infty$ can give a different answer.

## Prerequisites

You should know [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/), [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/), and [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/). The conventions for Euclidean path integrals, sources, and expectation values are fixed in [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/).

This page assumes the basic idea of a global symmetry and of spontaneous symmetry breaking. It does not assume a prior study of the effective potential, lattice simulations, or gauge-theory phase diagrams.

## Core idea

A VEV is not just “the value of a field in the vacuum.” It is the expectation value of an operator in a state. That state may be a unique symmetric vacuum, one of several pure broken vacua, a finite-volume ground state, a thermal state, a metastable state, or a gauge-fixed representative.

The useful mental model is:

| Question | Why it matters |
|---|---|
| Which operator? | Elementary fields, composite operators, charges, densities, and disorder operators behave differently. |
| Which state? | A symmetric finite-volume state and a pure broken infinite-volume state can give different one-point functions. |
| Which limits? | Source, volume, continuum, long-time, and zero-temperature limits need not commute. |
| Which renormalization? | Composite VEVs can mix with the identity or with lower-dimension operators. |
| Which symmetry? | A VEV charged under an unbroken global symmetry vanishes; a gauge-variant VEV is not a physical observable by itself. |

Used well, VEVs are a sharp way to identify phases. Used carelessly, they are a factory for fake conclusions. The VEV gremlin is small, but it steals minus signs, limits, and entire phases.

## Setup and conventions

Work first in Euclidean signature and finite spacetime volume $V$. Couple a spacetime-independent source $J$ to a local scalar operator $\mathcal O(x)$ by

$$
S_E\longmapsto S_E-J\int_V d^dx\,\mathcal O(x),
$$

so that

$$
Z_V[J]=\int\mathcal D\Phi\,
\exp\left[-S_E[\Phi]+J\int_V d^dx\,\mathcal O(x)\right].
$$

The finite-volume source-dependent expectation value is

$$
\langle\mathcal O\rangle_{V,J}
=\frac{1}{V}\frac{\partial}{\partial J}\log Z_V[J].
$$

Equivalently,

$$
\langle\mathcal O\rangle_{V,J}
=\frac{1}{V}\int_V d^dx\,\langle\mathcal O(x)\rangle_{V,J}.
$$

If translation invariance is unbroken and boundary effects are negligible, this equals the local one-point function away from the boundary.

The connected susceptibility is the second derivative:

$$
\chi_V(J)
=\frac{\partial}{\partial J}\langle\mathcal O\rangle_{V,J}
=\frac{1}{V}\left\langle
\left(\int_V d^dx\,[\mathcal O(x)-\langle\mathcal O\rangle_{V,J}]\right)^2
\right\rangle_{V,J}.
$$

A growing susceptibility is often the finite-volume warning sign that the infinite-volume limit is reorganizing the vacuum.

## One-point functions are state data

The symbol $\langle\mathcal O\rangle$ is incomplete until the state is known. In canonical language, the vacuum expectation value is

$$
\langle\mathcal O\rangle_\Omega
=\langle\Omega|\mathcal O|\Omega\rangle,
$$

after whatever normalization convention is being used for $|\Omega\rangle$. In Euclidean language, the same object is extracted from a path integral with boundary conditions or large Euclidean time projection onto a state.

For a unique translationally invariant vacuum, a scalar local operator has a constant one-point function:

$$
\langle\Omega|\mathcal O(x)|\Omega\rangle=\text{constant}.
$$

If $\mathcal O$ carries nonzero spin or momentum, its one-point function vanishes in a Poincaré-invariant vacuum. If $\mathcal O$ is charged under an unbroken internal global symmetry, its one-point function also vanishes.

More generally, a nonzero one-point function says that the state carries the corresponding quantum numbers or background response. It does not automatically say that a symmetry is spontaneously broken. For example, a finite density state has a nonzero charge-density expectation value, but that is a statement about the chosen state or ensemble, not necessarily about vacuum degeneracy.

## Sources and the order of limits

The simplest diagnostic of spontaneous breaking of a discrete symmetry is a scalar operator $\mathcal O$ that changes sign under a $\mathbb Z_2$ symmetry. At finite volume and zero source, if the symmetry is exact and the integration measure respects it, then

$$
\langle\mathcal O\rangle_{V,0}=0.
$$

This is true even when the infinite-volume theory has two broken phases with

$$
\langle\mathcal O\rangle_+=+v,
\qquad
\langle\mathcal O\rangle_-=-v.
$$

The source $J$ selects one side before the thermodynamic limit suppresses tunneling between the two phases:

$$
\langle\mathcal O\rangle_+
=\lim_{J\to0^+}\lim_{V\to\infty}\langle\mathcal O\rangle_{V,J},
$$

and similarly for $J\to0^-$. If the limits are reversed,

$$
\lim_{V\to\infty}\lim_{J\to0}\langle\mathcal O\rangle_{V,J}=0
$$

in the symmetric finite-volume ensemble.

<figure class="doc-figure" style="--figure-width: 54rem;">

![Diagram of source selection and noncommuting limits for a vacuum expectation value](/figures/nonperturbative-qft/vev-source-selection-limits.svg)

<figcaption>

A source $J$ selects a phase before the infinite-volume limit suppresses tunneling. Taking $J\to0$ first keeps the finite-volume symmetric state and gives a vanishing VEV for a symmetry-odd operator.

</figcaption>
</figure>

The noncommuting limits are not a technicality. They are the mathematical expression of phase selection. In finite-dimensional quantum mechanics, tunneling usually produces a unique ground state. In infinite-volume QFT, the tunneling amplitude between macroscopically different vacua can vanish, leaving distinct pure phases.

## Pure phases and mixed states

A pure broken phase and a symmetric mixture can have the same short-distance Lagrangian but different long-distance clustering.

For a symmetry-odd scalar $\phi$, a pure broken phase may have

$$
\langle\phi\rangle_+=v.
$$

If connected correlations cluster, then

$$
\lim_{|x|\to\infty}\langle\phi(x)\phi(0)\rangle_+
=\langle\phi\rangle_+^2=v^2.
$$

The symmetric mixture of the two phases has

$$
\langle\phi\rangle_{\mathrm{mix}}=0,
$$

but still

$$
\lim_{|x|\to\infty}\langle\phi(x)\phi(0)\rangle_{\mathrm{mix}}=v^2.
$$

This is a common source of confusion. The vanishing one-point function in the symmetric mixture does not mean that long-range order disappeared. It means the state is not a single pure broken phase.

A practical lesson follows: when a one-point function vanishes by symmetry, inspect long-distance two-point functions, susceptibilities, boundary-condition dependence, and finite-volume scaling before concluding that the phase is symmetric.

## VEVs and the effective potential

For a scalar field or scalar composite operator, source dependence is closely related to the effective potential. Let

$$
\varphi_J=\langle\phi\rangle_J.
$$

The generating functional $W[J]=\log Z[J]$ and the 1PI effective action $\Gamma[\varphi]$ are related by a Legendre transform. For a constant field configuration in volume $V$, one writes

$$
\Gamma[\varphi]=V\,U_{\mathrm{eff}}(\varphi)+\cdots,
$$

where the omitted terms contain derivatives. The source equation is

$$
\frac{dU_{\mathrm{eff}}}{d\varphi}=J.
$$

At zero source, candidate vacua satisfy

$$
\left.\frac{dU_{\mathrm{eff}}}{d\varphi}\right|_{\varphi=v}=0.
$$

This relation is useful, but it comes with two caveats.

First, the exact infinite-volume effective potential is convex as a consequence of the Legendre transform. Perturbative or semiclassical potentials often show multiple wells because they are approximations to a branch or because they are computed before the full convexification implied by phase coexistence.

Second, a gauge-fixed effective potential can depend on gauge choices away from physical extrema. The value of the potential at a physical extremum and properly defined physical observables are the safer objects. The position of a gauge-variant field minimum is not, by itself, a gauge-invariant observable.

The effective potential gets its own page because it is useful enough to deserve respect and dangerous enough to deserve adult supervision.

## Renormalization of VEVs and condensates

The operator in a VEV must be a renormalized operator. For an elementary scalar field, the renormalized field may be written schematically as

$$
\phi_R=Z_\phi^{-1/2}\phi_0,
$$

so its VEV depends on the normalization of the field. For a composite operator, the issue is sharper. Operators with the same quantum numbers can mix under renormalization:

$$
[\mathcal O_i]_R=Z_i{}^j\mathcal O_j+\text{subtractions}.
$$

If the identity operator is allowed by symmetries, then additive mixing can occur. For example, the bare expectation value of $\phi^2$ is ultraviolet divergent in a continuum scalar theory. A statement such as

$$
\langle\phi^2\rangle
$$

is not a universal number until the regulator, subtraction, and renormalization scheme are specified.

This does not make condensates useless. It means one should separate:

| Object | Typical status |
|---|---|
| Whether a symmetry is broken | Often scheme-independent when expressed through physical observables and limits. |
| The numerical value of a local composite VEV | Usually scheme- and scale-dependent. |
| Differences or derivatives of free energies | Often more physical than an isolated additive condensate. |
| Long-distance scaling of correlators | Often universal near critical points. |

In gauge theories and QCD-like theories, condensates such as $\langle\bar\psi\psi\rangle$ can be extremely useful, but their precise normalization and scale dependence must be tracked.

## Gauge invariance and Elitzur-type warnings

In a gauge theory, a local gauge-variant operator is not an observable. If the path integral is defined without gauge fixing and the regulator respects gauge invariance, expectation values of gauge-variant local operators vanish. This is the content, in lattice language, of the Elitzur-type warning that local gauge symmetry cannot be spontaneously broken in the same sense as a global symmetry.

Therefore a statement like

$$
\langle\phi\rangle\neq0
$$

in a gauge theory needs interpretation. It may be a useful gauge-fixed diagnostic, a convenient parametrization of perturbation theory, or a shorthand for a phase with massive gauge bosons and particular spectra. But the physical statement should be phrased using gauge-invariant observables, global symmetry realization, line operators, response functions, or the spectrum.

This is especially important in Higgs phases. In weakly coupled calculations, shifting a scalar field by a VEV is the simplest way to expose masses and interactions. Nonperturbatively, the physical distinction between Higgs, confinement, and Coulomb-like behavior depends on the global structure of the theory, matter content, allowed line operators, and boundary conditions.

A good working rule is:

$$
\text{use gauge-fixed VEVs for calculations; use gauge-invariant diagnostics for conclusions.}
$$

## Examples

**Broken $\mathbb Z_2$ scalar theory.** A scalar theory with $\phi\mapsto-\phi$ can have two infinite-volume phases with $\langle\phi\rangle=\pm v$. At finite volume and zero source the symmetric expectation value vanishes. The order parameter is defined by the source-selected limit.

**Chiral condensate.** In a QCD-like theory, the condensate $\langle\bar\psi\psi\rangle$ diagnoses chiral symmetry breaking. The operator is gauge invariant, but its numerical value depends on renormalization scale and scheme. The associated physical claims are better phrased through symmetry realization, Goldstone bosons when applicable, Ward identities, and spectral information.

**Higgs field VEV.** In the perturbative electroweak theory, a nonzero Higgs VEV is a convenient gauge-fixed way to organize masses and interactions. Nonperturbatively, the physical statements concern gauge-invariant spectra and symmetries rather than the expectation value of a gauge-variant scalar field by itself.

**Topological phases.** Some phases have no local order parameter at all. A vanishing set of local VEVs does not imply a trivial phase. Degeneracies on nontrivial spatial manifolds, line and surface operators, boundary modes, or response terms may carry the distinguishing data.

## Common pitfalls

**Writing a VEV without the state.** The notation $\langle\mathcal O\rangle$ suppresses the vacuum, source, volume, temperature, and boundary conditions. For phase questions, restore that data before interpreting the answer.

**Taking the zero-source limit too early.** At finite volume, an exact symmetry usually forces a charged order parameter to vanish. To define a broken phase, take infinite volume before removing the source or phase-selecting boundary condition.

**Treating a gauge-fixed VEV as a physical observable.** Gauge-fixed VEVs are useful calculational tools. Physical conclusions require gauge-invariant statements.

**Ignoring operator renormalization.** Composite condensates can be divergent, scheme-dependent, and scale-dependent. Compare condensates only after matching definitions.

**Confusing a mixed state with a symmetric phase.** A symmetric mixture of broken vacua can have $\langle\phi\rangle=0$ while retaining long-distance order in $\langle\phi(x)\phi(0)\rangle$.

**Equating “nonzero VEV” with “phase fully identified.”** A VEV may distinguish two simple phases, but strongly coupled gauge theories often require spectra, line operators, anomalies, and response observables.

## Relations to other pages

- [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/) explains why VEVs are only one class of phase diagnostic.
- [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/) explains why the volume and boundary conditions used above are part of the definition.
- [Euclidean Path Integral](/nonperturbative-qft/nonperturbative-definitions/euclidean-path-integral/) gives the path-integral language for sources and correlation functions.
- Degenerate Vacua will explain how multiple infinite-volume vacua arise and how tunneling splittings behave.
- Superselection Sectors will explain why some vacua or sectors cannot be connected by local physical operators.
- Effective Potential and Convexity will develop the Legendre-transform viewpoint used here.
- [Order Parameters and Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/) will compare local VEVs with disorder operators, correlation lengths, spectra, Wilson loops, and topological probes.

## Research status

The basic role of VEVs, source selection, and order-of-limits issues is textbook-standard. These ideas are foundational in statistical field theory, spontaneous symmetry breaking, and lattice field theory.

The subtle part is not the definition of a VEV. The subtle part is deciding whether a proposed VEV is the right diagnostic for a strongly coupled system. In gauge theories, systems with topological order, theories with dynamical screening, and phases constrained by generalized symmetries or anomalies, local VEVs are often only part of the evidence.

For research use, a phase claim based on a VEV should usually be accompanied by at least one independent check: a spectrum, a long-distance correlator, a symmetry or anomaly argument, a finite-size scaling analysis, or an extended-operator diagnostic.

## Exercises

### Exercise 1: Symmetry forces the finite-volume VEV to vanish

Let a finite-volume Euclidean theory have an exact $\mathbb Z_2$ symmetry $\phi\mapsto-\phi$, invariant action, and invariant measure. Show that $\langle\phi(x)\rangle_{V,0}=0$.

<details>
<summary><strong>Solution</strong></summary>

At zero source,

$$
\langle\phi(x)\rangle_{V,0}
=\frac{1}{Z}\int\mathcal D\phi\,\phi(x)e^{-S_E[\phi]}.
$$

Make the change of variables $\phi\mapsto-\phi$. The measure and action are invariant, while the insertion changes sign. Therefore the integral equals its negative, so it vanishes.

</details>

### Exercise 2: Susceptibility as an integrated connected correlator

Using

$$
Z_V[J]=\int\mathcal D\Phi\,e^{-S_E+J\int_V d^dx\,\mathcal O(x)},
$$

show that

$$
\chi_V(0)=\frac{1}{V}\int_V d^dx\,d^dy\,
\langle\mathcal O(x)\mathcal O(y)\rangle_c.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate twice:

$$
\frac{\partial^2}{\partial J^2}\log Z_V[J]
=\left\langle\left(\int_V d^dx\,\mathcal O(x)\right)^2\right\rangle_J
-\left\langle\int_V d^dx\,\mathcal O(x)\right\rangle_J^2.
$$

Dividing by $V$ gives

$$
\chi_V(J)=\frac{1}{V}\int_V d^dx\,d^dy\,
\langle\mathcal O(x)\mathcal O(y)\rangle_{c,J}.
$$

Setting $J=0$ gives the stated result.

</details>

### Exercise 3: Pure phase versus symmetric mixture

Suppose two pure broken phases have $\langle\phi\rangle_+=v$ and $\langle\phi\rangle_-=-v$, and suppose each clusters. Consider the mixed state

$$
\langle A\rangle_{\mathrm{mix}}=\frac12\langle A\rangle_++\frac12\langle A\rangle_-.
$$

Compute $\langle\phi\rangle_{\mathrm{mix}}$ and $\lim_{|x|\to\infty}\langle\phi(x)\phi(0)\rangle_{\mathrm{mix}}$.

<details>
<summary><strong>Solution</strong></summary>

The one-point function is

$$
\langle\phi\rangle_{\mathrm{mix}}
=\frac12 v+\frac12(-v)=0.
$$

By clustering inside each pure phase,

$$
\lim_{|x|\to\infty}\langle\phi(x)\phi(0)\rangle_+=v^2,
\qquad
\lim_{|x|\to\infty}\langle\phi(x)\phi(0)\rangle_-=(-v)^2=v^2.
$$

Therefore the mixed state also has

$$
\lim_{|x|\to\infty}\langle\phi(x)\phi(0)\rangle_{\mathrm{mix}}=v^2.
$$

The one-point function vanishes, but long-range order remains visible in the two-point function.

</details>

### Exercise 4: Additive renormalization of a composite VEV

Explain why a scalar composite operator $\mathcal O=\phi^2$ can mix with the identity, and why this affects the numerical value of $\langle\mathcal O\rangle$.

<details>
<summary><strong>Solution</strong></summary>

The operator $\phi^2$ is a scalar and is even under $\phi\mapsto-\phi$. The identity operator has the same spacetime and internal symmetry quantum numbers. Renormalization can therefore include a subtraction of the form

$$
[\phi^2]_R=Z_{\phi^2}\phi_0^2+c(a)\mathbf 1,
$$

where $a$ is a cutoff scale and $c(a)$ removes ultraviolet divergences. Taking the vacuum expectation value gives

$$
\langle[\phi^2]_R\rangle=Z_{\phi^2}\langle\phi_0^2\rangle+c(a).
$$

The additive term changes the numerical value. Only after specifying the subtraction scheme does the condensate become a defined quantity.

</details>

## References

### Standard first pass

- S. Coleman, *Aspects of Symmetry*, especially “Secret Symmetry” for spontaneous symmetry breaking, functional methods, and the effective potential.
- M. Srednicki, *Quantum Field Theory*, sections on the quantum action and spontaneous symmetry breaking, for the relation between sources, effective action, and VEVs.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, sections on vacuum expectation values and spontaneous symmetry breaking.

### Deeper references

- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the order-parameter and statistical-field-theory viewpoint.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, for phases of gauge theories, solitons, false vacua, and confinement examples.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for a modern condensed-matter perspective on broken symmetry, collective phenomena, and order parameters.

## Version history

- **2026-06-26:** Initial polished page.
