---
title: "KLN Theorem"
description: "The cancellation of soft and collinear infrared divergences in sufficiently inclusive transition probabilities after summing over degenerate initial and final states."
sidebar:
  label: "KLN Theorem"
  order: 4
level: Graduate
status: "Polished draft"
source: "Kinoshita; Lee–Nauenberg; Weinberg Vol. I on infrared effects; Srednicki §26; Schwartz ch. 20"
topics:
  - infrared divergences
  - KLN theorem
  - degenerate states
  - inclusive observables
  - soft and collinear cancellation
canonicalTopics:
  - kln-theorem
  - kinoshita-lee-nauenberg-cancellation
  - infrared-safe-observables
  - degenerate-state-sums
researchStatus:
  established:
    - "The KLN theorem is the standard perturbative cancellation theorem for infrared singularities in inclusive probabilities when all degenerate initial and final states are treated consistently."
  active:
    - "Practical implementations in non-Abelian gauge theories, hadron-collider factorization, jet algorithms, Glauber regions, non-global observables, and finite-resolution measurements remain active precision topics."
---

## Summary

The **Kinoshita–Lee–Nauenberg theorem**, usually called the **KLN theorem**, is the general cancellation principle behind infrared-safe perturbative predictions. It says that infrared divergences cancel in sufficiently inclusive transition probabilities after summing over all physically degenerate initial and final states.

A useful schematic form is

$$
P_{\mathcal F\leftarrow\mathcal I}^{\rm incl}
=
\sum_{i\in\mathcal I}\rho_i
\sum_{f\in\mathcal F}
|S_{fi}|^2,
$$

where $\mathcal I$ and $\mathcal F$ are sets of states degenerate within the measurement resolution, and $\rho_i$ is the initial density matrix or averaging weight. The theorem is not a statement about a single amplitude $S_{fi}$. It is a statement about inclusive probabilities.

The Bloch–Nordsieck theorem handles soft-photon cancellation in QED by summing over unresolved soft photons in the final state. KLN is broader. It includes both soft and collinear degeneracies and, in its cleanest form, requires summing over degenerate initial states as well as final states.

<figure class="doc-figure" style="--figure-width: 42rem; --caption-width: 55rem;">

![The KLN theorem sums over degenerate initial and final states to cancel soft and collinear infrared singularities in inclusive probabilities](/figures/perturbative-qft/kln-theorem.svg)

<figcaption>

KLN cancellation is a statement about inclusive probabilities. One sums over states that the measurement cannot distinguish: soft radiation, collinear splittings, and other exactly or effectively degenerate configurations. Individual amplitudes and individual diagrams remain infrared singular.

</figcaption>
</figure>

## Prerequisites

You should know [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/), [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/), [Bloch–Nordsieck Theorem](/perturbative-qft/infrared-physics-factorization/bloch-nordsieck-theorem/), [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/), [Optical Theorem and Rates](/perturbative-qft/phase-space-cross-sections-decays/optical-theorem-and-rates/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), and [Gauge Parameter Independence](/perturbative-qft/gauge-theory-perturbation-theory/gauge-parameter-independence/).

## Core idea

Infrared divergences appear when the perturbative calculation tries to distinguish states that are physically degenerate. In a massless theory, the following configurations can have the same measured hard data:

- the hard state itself;
- the hard state plus arbitrarily soft massless radiation;
- the hard state with one massless particle replaced by two collinear particles;
- combinations of soft and collinear emissions.

A calculation that keeps only one representative of this degenerate family is not computing an observable. It is computing a basis-dependent component of a larger probability.

The KLN theorem says that after summing over the full degenerate set, infrared singularities cancel order by order in perturbation theory, once ultraviolet renormalization has already been performed. The slogan is

$$
\text{IR divergences cancel in inclusive probabilities over degenerate states.}
$$

There are three pieces hidden in that sentence:

1. **Inclusive:** the observable must not ask the theory to resolve infinitely soft or perfectly collinear details.
2. **Probabilities:** cancellation occurs in $|S|^2$-type quantities, not in individual amplitudes.
3. **Degenerate states:** the sum must include all states that become indistinguishable in the infrared limit, including initial-state degeneracies in the fully general theorem.

## Setup and conventions

We use qft.org scattering conventions,

$$
S_{fi}
=
\delta_{fi}
+i(2\pi)^4\delta^{(4)}(p_f-p_i)\mathcal M_{fi},
$$

mostly-minus metric, and dimensional regularization when we write infrared poles schematically as $1/\epsilon_{\rm IR}$.

A state is **infrared-degenerate** with another state if the difference between them costs vanishing energy, vanishing invariant mass, or lies below the measurement resolution. The two most important examples are:

$$
\text{soft:}\qquad k^0\to0,
$$

and

$$
\text{collinear:}\qquad s_{ij}=2p_i\cdot p_j\to0
\quad\text{for massless }p_i,p_j.
$$

The theorem is often invoked for cross sections written with measurement functions,

$$
\sigma[F]
=
\sum_n \int d\Pi_n\,|\mathcal M_n|^2 F_n(p_1,\ldots,p_n),
$$

where $F_n$ defines what is being measured. An infrared-safe measurement function satisfies the limiting conditions

$$
F_{n+1}(p_1,
\ldots,p_n,k_{\rm soft})
\longrightarrow
F_n(p_1,\ldots,p_n),
$$

and

$$
F_{n+1}(p_1,\ldots,p_i,p_j,\ldots)
\longrightarrow
F_n(p_1,\ldots,p_i+p_j,\ldots)
$$

when $p_i$ and $p_j$ become unresolved and collinear. These conditions are the observable-level version of the KLN lesson.

## Degenerate subspaces

Let $\mathcal I$ be an initial degenerate subspace and $\mathcal F$ a final degenerate subspace. The inclusive transition probability is not a single matrix element. It is a trace-like object,

$$
P_{\mathcal F\leftarrow\mathcal I}^{\rm incl}
=
\sum_{i\in\mathcal I}\rho_i
\sum_{f\in\mathcal F}
|\langle f|S|i\rangle|^2.
$$

Here $\rho_i$ encodes how the initial degenerate states are prepared or averaged. For a pure idealized initial state, $\rho_i$ may select one state, but then the full KLN cancellation of initial-state collinear singularities may not occur. This is not a paradox. It means the observable has not included the full degenerate initial ensemble.

In many practical scattering problems, final-state sums are automatic because detectors are inclusive over unresolved radiation. Initial-state sums are more subtle. In lepton collisions, finite lepton masses often regulate initial-state collinear singularities, leaving large logarithms such as $\log(s/m_e^2)$. In hadron collisions, universal initial-state collinear singularities are absorbed into parton distribution functions. The hadronic cross section is finite, but the partonic hard cross section by itself is not a complete observable.

## Soft cancellation revisited

Soft cancellation is the easiest part of KLN to see. The amplitude with an extra soft photon or gluon factorizes as

$$
\mathcal M_{n+1}(k)
\simeq
S(k)\mathcal M_n,
$$

with

$$
S(k)
\sim
\sum_i\frac{p_i\cdot\varepsilon(k)}{p_i\cdot k}.
$$

Real emission produces an integral of the form

$$
\int \frac{d\omega}{\omega}.
$$

Virtual exchange produces the same soft integral inside a loop. The sign and phase-space placement differ, but in an inclusive probability the singular regulator dependence cancels:

$$
\left[\text{virtual soft pole}\right]
+
\left[\text{real soft pole}\right]
=0.
$$

Bloch–Nordsieck cancellation is this story in Abelian QED, most transparently with massive charged particles. KLN says that soft cancellation is one case of a broader degenerate-state principle.

## Collinear cancellation and why final states are easier

Collinear divergences occur when a massless particle splits into two massless particles with nearly parallel momenta. The squared amplitude factorizes schematically as

$$
|\mathcal M_{n+1}|^2
\simeq
\frac{2g^2}{s_{ij}}
P_{a\to bc}(z)
|\mathcal M_n|^2,
$$

and phase space supplies

$$
\frac{d\mathbf k_\perp^2}{\mathbf k_\perp^2}.
$$

If the observable treats two collinear particles as one unresolved jet-like object, then the real collinear singularity cancels the corresponding virtual collinear singularity. This is why infrared-safe jet algorithms are designed to be insensitive to soft emissions and collinear splittings.

For final-state radiation in an inclusive observable, the measurement function can often be chosen so that

$$
F_{n+1}(\ldots,p_i,p_j,\ldots)
\to
F_n(\ldots,p_i+p_j,\ldots)
$$

in the collinear limit. Then the unresolved real-emission region and the virtual loop region contribute to the same measured bin.

For initial-state collinear radiation, the situation is less automatic. If a massless incoming parton splits collinearly before the hard scattering, the momentum fraction entering the hard process changes. The singularity is universal, but it is not usually canceled within a fixed partonic initial state. Instead, it is absorbed into the definition and scale dependence of a parton distribution function. This is mass factorization, not a violation of KLN.

## Infrared-safe observables

For practical calculations, the KLN theorem becomes a design principle for observables.

An observable is **infrared safe** if adding an unresolved soft particle or replacing one massless particle by a collinear pair does not change the measured value. In measurement-function language,

$$
F_{n+1}(\ldots,k_{\rm soft})
=
F_n(\ldots)
+O(k_{\rm soft}),
$$

and

$$
F_{n+1}(\ldots,zp,(1-z)p,\ldots)
=
F_n(\ldots,p,\ldots)
$$

at leading power.

Examples of infrared-safe observables include:

| Observable type | Why it is safe |
|---|---|
| total $e^+e^-\to$ hadrons rate | sums inclusively over unresolved hadronic radiation |
| suitably defined jet rates | soft particles and collinear splittings do not change the jet classification discontinuously |
| event shapes such as thrust | defined by continuous weights over final-state momenta |
| inclusive decay widths | sum over unresolved photons or gluons in the final state |

Examples of unsafe or incomplete quantities include:

| Quantity | Problem |
|---|---|
| amplitude for a fixed finite number of soft photons | not inclusive over degenerate soft states |
| bare quark or gluon energy fraction | changes under collinear splitting |
| partonic hadron-collider cross section before PDF factorization | misses initial-state long-distance physics |
| detector definition with a sharp sensitivity to one infinitely soft particle | violates soft safety |

The phrase “infrared safe” therefore belongs to observables, not to diagrams.

## KLN versus Bloch–Nordsieck

The two theorems are closely related but not identical.

| Feature | Bloch–Nordsieck | KLN |
|---|---|---|
| Original setting | Abelian QED soft photons | General infrared cancellation in perturbation theory |
| Main degeneracy | extra soft photons | soft and collinear degenerate states |
| Sum required | usually final soft radiation | final and, in full generality, initial degenerate states |
| Natural output | inclusive soft-photon rate and exponentiation | finite inclusive probabilities or IR-safe observables |
| Common use | QED soft radiation below energy resolution | gauge-theory infrared safety, jets, PDFs, inclusive rates |

A safe mental model is:

$$
\text{Bloch–Nordsieck is the Abelian soft prototype; KLN is the general degenerate-state cancellation principle.}
$$

## Role of unitarity

The cancellation is deeply tied to unitarity. Since

$$
S^\dagger S=1,
$$

probability cannot leak into unobserved states. The optical theorem expresses this as a relation between virtual corrections and sums over real intermediate states:

$$
2\operatorname{Im}\mathcal M_{i\to i}
=
\sum_X\int d\Pi_X\,|\mathcal M_{i\to X}|^2,
$$

with the usual convention-dependent normalization suppressed. The virtual loop knows about the same on-shell soft or collinear states that appear as real emissions in the inclusive sum.

This is why cut diagrams are so useful in infrared physics. A loop singularity is not mysterious once its cut reveals the real degenerate states that can go on shell.

## What the theorem does not say

The KLN theorem is powerful, but it is often overquoted. It does not say that every quantity in a gauge theory is finite. It does not say that every partonic cross section is a physical observable. It does not eliminate the need for factorization, PDFs, fragmentation functions, jet functions, or resummation.

The theorem says that infrared divergences cancel after summing over complete degenerate sets. If the observable is not inclusive enough, singularities remain. If the observable is inclusive but contains large hierarchies of scales, large logarithms remain and may need resummation. Finiteness and numerical stability are different things.

Thus, after KLN cancellation, one often still has finite logarithms such as

$$
\log\frac{Q}{\Delta E},
\qquad
\log\frac{Q}{m},
\qquad
\log\frac{Q}{p_T^{\rm cut}}.
$$

These are physical logarithms of measurement scales or masses, not uncanceled infrared regulators.

## Common pitfalls

**Thinking KLN makes amplitudes finite.** It does not. It applies to probabilities summed over degenerate states.

**Forgetting initial-state degeneracy.** Final-state inclusiveness is often enough for lepton-collider final-state observables, but initial-state collinear singularities require more care. In hadron collisions they are absorbed into PDFs.

**Confusing regulator cancellation with cut independence.** The artificial regulator cancels. Physical cuts and resolutions remain.

**Calling a parton-level object an observable too soon.** Bare quarks and gluons are not directly measured. A finite hadronic prediction usually requires PDFs, fragmentation functions, or jet definitions.

**Assuming every finite observable is numerically well behaved.** KLN cancellation can leave large logarithms. Resummation may be needed even when the fixed-order result is finite.

**Ignoring measurement functions.** The cancellation is controlled by how the observable treats unresolved soft and collinear limits. Without the measurement definition, the statement “the cross section is finite” is incomplete.

## Relations to other pages

- [Bloch–Nordsieck Theorem](/perturbative-qft/infrared-physics-factorization/bloch-nordsieck-theorem/) gives the Abelian soft-photon prototype of inclusive cancellation.
- [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) derives the leading soft factor and soft logarithm.
- [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/) derives the leading splitting picture and collinear logarithm.
- [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) explains measurement functions and infrared safety from the rate side.
- [Optical Theorem and Rates](/perturbative-qft/phase-space-cross-sections-decays/optical-theorem-and-rates/) explains the unitarity relation between virtual corrections and real sums.
- Later factorization pages will explain how long-distance singularities are separated into hard, soft, jet, and PDF factors.
- Later resummation pages will explain why finite large logarithms often need all-order organization.

## Research status

**Established.** KLN cancellation is a standard theorem of perturbative QFT. Its practical lesson — define infrared-safe observables and sum over unresolved degenerate states — is foundational in precision QED, QCD, and collider physics.

**Active.** The boundaries of factorization, especially in non-Abelian gauge theory with hadronic initial states, jet vetoes, non-global observables, Glauber exchange, small transverse momentum, heavy-quark thresholds, and real detector definitions, remain active research areas.

**Subtle.** The theorem is often stated more simply than it is used. Initial-state degeneracy, confinement, PDFs, and experimental cuts mean that practical calculations require factorization theorems in addition to KLN logic.

**Convention-dependent.** The normalization of $S$, $\mathcal M$, phase space, and dimensional-regularization poles varies by source. The degenerate-state cancellation statement is invariant.

## Exercises

### Exercise 1: Check soft safety of a measurement function

Suppose an observable is defined by measurement functions $F_n$ satisfying

$$
F_{n+1}(p_1,\ldots,p_n,k)
\to
F_n(p_1,\ldots,p_n)
$$

as $k^0\to0$. Explain why this condition is needed for soft real–virtual cancellation.

<details>
<summary><strong>Solution</strong></summary>

The real-emission contribution in the soft region has the form

$$
\int d\Pi_k\,|S(k)|^2 |\mathcal M_n|^2
F_{n+1}(p_1,\ldots,p_n,k).
$$

The virtual soft correction multiplies the lower-multiplicity contribution,

$$
|\mathcal M_n|^2F_n(p_1,\ldots,p_n),
$$

with the opposite infrared pole or logarithm. For the singular parts to cancel, the real-emission measurement weight must approach the same value as the virtual contribution in the soft limit. That is precisely

$$
F_{n+1}\to F_n.
$$

If the observable changes discontinuously when an arbitrarily soft particle is added, the real soft singularity is weighted differently from the virtual one and the cancellation fails.

</details>

### Exercise 2: Check collinear safety of a measurement function

Suppose two massless final-state particles become collinear with momenta $p_i=zp$ and $p_j=(1-z)p$. What condition should $F_{n+1}$ satisfy for final-state collinear safety?

<details>
<summary><strong>Solution</strong></summary>

The observable must treat the unresolved collinear pair as a single particle or jet carrying the total momentum $p$. Therefore the condition is

$$
F_{n+1}(\ldots,zp,(1-z)p,\ldots)
=
F_n(\ldots,p,\ldots)
$$

at leading power in the collinear limit. This ensures that the real collinear splitting and the corresponding virtual correction contribute to the same measured bin, allowing their singularities to cancel.

</details>

### Exercise 3: Why a bare quark energy fraction is unsafe

Explain why measuring the energy fraction of a single bare quark in a massless QCD final state is not collinear safe.

<details>
<summary><strong>Solution</strong></summary>

A massless quark can split collinearly,

$$
q\to qg,
$$

with no invariant-mass cost in the strict collinear limit. If the observable measures the energy fraction carried by the quark alone, then before splitting the quark carries energy $E$, while after splitting the quark may carry only $zE$ and the gluon carries $(1-z)E$.

The observable therefore distinguishes

$$
q(p)
$$

from the degenerate configuration

$$
q(zp)+g((1-z)p).
$$

That violates collinear safety. A jet energy, by contrast, can be collinear safe because it recombines the quark and gluon into the total momentum $p$.

</details>

### Exercise 4: Bloch–Nordsieck as a special case of KLN

State which degenerate states are summed over in the Bloch–Nordsieck soft-photon cancellation and explain why this is a special case of KLN logic.

<details>
<summary><strong>Solution</strong></summary>

In the Bloch–Nordsieck setup, one fixes the hard charged particles and sums over any number of photons whose energies are below the detector resolution $\Delta E$. These final states are degenerate with the hard final state because the extra photons can carry arbitrarily small energy.

Thus the inclusive probability has the schematic form

$$
\sum_{N=0}^{\infty}
P(\text{hard charged particles}+N\text{ unresolved soft photons}).
$$

This is a KLN-type sum over degenerate final states. It is a special case because it focuses on Abelian soft photons and does not by itself address all collinear or initial-state degeneracies.

</details>

### Exercise 5: Finite does not mean log-free

An inclusive observable after KLN cancellation contains a term

$$
\alpha\log\frac{Q}{E_{\rm cut}}.
$$

Is this a contradiction of KLN? Explain.

<details>
<summary><strong>Solution</strong></summary>

No. KLN cancellation removes dependence on artificial infrared regulators such as $\lambda$ or $1/\epsilon_{\rm IR}$. It does not remove dependence on physical measurement scales. If $E_{\rm cut}$ is part of the observable definition, then

$$
\log\frac{Q}{E_{\rm cut}}
$$

is a physical logarithm. If it is large, fixed-order perturbation theory may converge poorly and resummation may be needed, but the observable is still infrared finite.

</details>

## References

- T. Kinoshita, “Mass singularities of Feynman amplitudes,” *Journal of Mathematical Physics* **3** (1962), for the original mass-singularity cancellation theorem.
- T. D. Lee and M. Nauenberg, “Degenerate Systems and Mass Singularities,” *Physical Review* **133** (1964), for the degenerate-state formulation.
- F. Bloch and A. Nordsieck, “Note on the Radiation Field of the Electron,” *Physical Review* **52** (1937), for the Abelian soft prototype.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for infrared effects, soft radiation, and inclusive cancellation.
- M. Srednicki, *Quantum Field Theory*, §26, for a compact treatment of infrared divergences.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 20, for practical real–virtual cancellation, jets, and infrared-safe observables.
- G. Sterman, *An Introduction to Quantum Field Theory*, for a detailed perturbative-QCD and factorization-oriented discussion.

## Version history

- **2026-06-13:** Initial polished draft. Establishes KLN cancellation, degenerate initial and final state sums, infrared-safe measurement functions, and the relation to Bloch–Nordsieck cancellation and factorization.
