---
title: "Bosons and Fermions"
description: "Commutation versus anticommutation, symmetric and antisymmetric states, occupation numbers, Pauli exclusion, graded signs, and the first structural view of the spin–statistics connection."
sidebar:
  label: "Bosons and Fermions"
  order: 6
level: Graduate
status: "Polished draft"
topics:
  - bosons
  - fermions
  - exchange statistics
  - Pauli exclusion
  - spin–statistics
canonicalTopics:
  - bosons-and-fermions
  - exchange-statistics
  - pauli-exclusion
  - spin-statistics-preview
---

## Summary

Bosons and fermions are distinguished by how identical-particle states behave under exchange. For identical bosons,

$$
\lvert q_1,q_2\rangle=\lvert q_2,q_1\rangle,
$$

while for identical fermions,

$$
\lvert q_1,q_2\rangle=-\lvert q_2,q_1\rangle.
$$

In Fock-space language, the same distinction is encoded in operator algebra. Bosonic modes satisfy commutation relations,

$$
[a_i,a_j^\dagger]=\delta_{ij},
$$

whereas fermionic modes satisfy anticommutation relations,

$$
\{a_i,a_j^\dagger\}=\delta_{ij}.
$$

The fermionic algebra implies

$$
(a_i^\dagger)^2=0,
$$

so one fermionic mode can be occupied at most once.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Bosonic and fermionic operator algebras](/figures/foundations/boson-fermion-algebra.svg)

<figcaption>

Bosonic creation operators commute, so arbitrary occupation is allowed. Fermionic creation operators anticommute, so a repeated creation operator vanishes.

</figcaption>
</figure>

## Prerequisites

You should have read [Multiparticle States](/foundations/relativistic-particles-and-fields/multiparticle-states/) and [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/). The full theorem connecting spin to statistics comes later in [Spin–Statistics](/foundations/symmetry-and-spacetime/spin-statistics/).

## Two languages for the same structure

In state language,

$$
\lvert q_{\pi(1)},\ldots,q_{\pi(N)}\rangle
=\eta(\pi)\lvert q_1,\ldots,q_N\rangle,
$$

where

$$
\eta(\pi)=1
$$

for bosons and

$$
\eta(\pi)=\operatorname{sgn}(\pi)
$$

for fermions.

In operator language,

$$
a_i^\dagger a_j^\dagger
=+a_j^\dagger a_i^\dagger
$$

for bosons, while

$$
a_i^\dagger a_j^\dagger
=-a_j^\dagger a_i^\dagger
$$

for fermions.

These are not separate ideas. Creation operators build the multiparticle states, so their exchange algebra determines the exchange property of the states.

## Bosonic modes

A single bosonic mode satisfies

$$
[a,a^\dagger]=1.
$$

The normalized occupation states are

$$
\lvert n\rangle=\frac{(a^\dagger)^n}{\sqrt{n!}}\lvert0\rangle,
\qquad
n=0,1,2,\ldots.
$$

The ladder operators act as

$$
a^\dagger\lvert n\rangle=\sqrt{n+1}\lvert n+1\rangle,
\qquad
 a\lvert n\rangle=\sqrt n\lvert n-1\rangle.
$$

There is no algebraic upper bound on $n$. This is the state-space reason bosons can pile into the same mode. It is not the same as saying all bosons attract each other; attraction and repulsion are determined by the interactions.

## Fermionic modes

A single fermionic mode satisfies

$$
\{a,a^\dagger\}=1,
\qquad
\{a^\dagger,a^\dagger\}=0.
$$

The second equation gives

$$
\boxed{(a^\dagger)^2=0.}
$$

Only two occupation states exist:

$$
\lvert0\rangle,
\qquad
\lvert1\rangle=a^\dagger\lvert0\rangle.
$$

Trying to create the same fermion twice gives zero. This is the Pauli exclusion principle in its leanest algebraic form. It is not a force; it is the absence of a state from Hilbert space.

For many fermionic modes, a canonical ordering of modes must be chosen. Reordering occupied fermionic modes changes the sign.

## Why fermionic signs matter

An overall sign of a state is not observable. Relative signs are. Fermionic exchange signs become relative signs whenever there are multiple ways to reach the same final state.

This is why the algebra later becomes calculation rules:

```txt
state-space rule:  no two identical fermions occupy the same mode;
operator rule:     reordering fermionic operators contributes minus signs;
diagram rule:      identical external fermions and closed fermion loops carry signs.
```

The first line is physical. The latter two are how the physical rule is implemented consistently.

## Mixed species and graded signs

For distinguishable particles, exchanging species is not an exchange of identical particles. An electron and a muon are not the same species.

Nevertheless, QFT usually uses a graded algebra:

- bosonic operators commute with bosonic and fermionic operators;
- fermionic operators anticommute with other fermionic operators.

For two different fermion species $a$ and $b$,

$$
a_i^\dagger b_j^\dagger=-b_j^\dagger a_i^\dagger.
$$

This sign is part of the consistent tensor-product convention for many-fermion Fock spaces. It is not saying that the two species are identical.

:::caution[Do not overread the convention]
The directly physical exchange rule applies to identical particles. The graded sign between different fermion species is a bookkeeping convention that becomes indispensable once one uses local fermion fields and path integrals.
:::

## Statistics and spin

In nonrelativistic quantum mechanics, one may impose bosonic or fermionic exchange symmetry by hand. Relativistic local QFT is stricter. In ordinary $3+1$-dimensional local QFT with positive energy and a suitable vacuum,

$$
\boxed{\text{integer spin}\quad\longleftrightarrow\quad\text{bosonic statistics},}
$$

and

$$
\boxed{\text{half-integer spin}\quad\longleftrightarrow\quad\text{fermionic statistics}.}
$$

This is the spin–statistics theorem. The assumptions matter. This page gives the operator and state-space language; the proof belongs later.

For intuition, the wrong algebra breaks the architecture. Quantizing a scalar field with anticommutators does not produce an ordinary local scalar particle. Quantizing a Dirac field with commutators spoils positivity and causal structure.

## Beyond the ordinary case

This page is about ordinary relativistic QFT in $3+1$ dimensions. In two spatial dimensions, particle paths can braid, and anyonic statistics can occur in suitable systems. These are not counterexamples to the ordinary spin–statistics theorem; they use different topology.

Gauge-fixed theories also contain ghost fields. Faddeev–Popov ghosts are Grassmann scalar fields, but they are not physical spin-zero particles in the Hilbert space. They are bookkeeping fields inside a gauge-fixed path integral.

## Common pitfalls

**Treating Pauli exclusion as a microscopic repulsive force.** The exclusion principle is a Hilbert-space statement. Degeneracy pressure is real, but it is not a fundamental Pauli force.

**Saying bosons attract and fermions repel.** Statistics controls occupation and exchange. Interactions control forces.

**Forgetting the full one-particle label.** Two electrons with the same momentum but opposite spin are not in the same mode.

**Reordering fermion operators casually.** Every swap of fermionic operators contributes a minus sign.

**Calling spin–statistics a convention.** Some operator-ordering choices are conventional. The relativistic spin–statistics relation is not merely conventional.

## Relation to other topics

- [Multiparticle States](/foundations/relativistic-particles-and-fields/multiparticle-states/) constructs the symmetric and antisymmetric Hilbert-space sectors.
- [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/) packages the sectors and introduces creation and annihilation operators.
- [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/) adds the particle–antiparticle distinction for charged relativistic fields.
- [Fermionic Canonical Quantization](/foundations/canonical-quantization/fermionic-canonical-quantization/) quantizes spinor fields using anticommutators.
- [Fermionic Path Integral](/foundations/path-integral-formalism/fermionic-path-integral/) introduces the path-integral algebra for fermions.
- [Spin–Statistics](/foundations/symmetry-and-spacetime/spin-statistics/) states the theorem and its assumptions.

## Research status

- **Established:** Bosonic and fermionic exchange statistics, together with the spin–statistics theorem in ordinary relativistic QFT, are textbook-standard.
- **Active:** Anyons, generalized statistics, defects, ghost sectors, and categorical symmetry require broader language outside the basic $3+1$-dimensional particle setting.

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§4.1–4.2 and ch. 5.
- M. Srednicki, *Quantum Field Theory*, §§1 and 4.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed., ch. II.4.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 2–4.

## Version history

- **2026-06-08:** Revised for shorter state/operator parallelism, cleaner warnings about graded signs, chapter terminology, and reduced overlap with the multiparticle and Fock-space pages.
