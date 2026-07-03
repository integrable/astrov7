---
title: "Fock Space"
description: "The direct sum of particle-number sectors, the vacuum, creation and annihilation operators, occupation-number basis, number operators, and the role of Fock space in QFT."
sidebar:
  label: "Fock Space"
  order: 5
level: Graduate
status: "Polished draft"
topics:
  - Fock space
  - creation operators
  - annihilation operators
  - occupation numbers
  - number operator
canonicalTopics:
  - fock-space
  - creation-annihilation-operators
  - occupation-number-basis
---

## Summary

Fock space is the Hilbert space that contains states with zero, one, two, three, and arbitrarily many quanta:

$$
\boxed{
\mathcal F=\bigoplus_{N=0}^{\infty}\mathcal H_N.
}
$$

For identical bosons,

$$
\mathcal H_N=\operatorname{Sym}^N\mathcal H_1,
$$

while for identical fermions,

$$
\mathcal H_N=\wedge^N\mathcal H_1.
$$

Creation operators move states to higher particle-number sectors. Annihilation operators move them to lower sectors. This is the operator language behind occupation numbers, field mode expansions, particle-number-changing interactions, and Wick contractions.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Fock space as a ladder of particle-number sectors connected by creation and annihilation operators](/figures/foundations/fock-space-ladder.svg)

<figcaption>

Fock space is the direct sum of all particle-number sectors. A creation operator raises particle number by one; an annihilation operator lowers it by one. In a discrete mode basis, the same information is stored in occupation numbers.

</figcaption>
</figure>

## Prerequisites

You should have read [Multiparticle States](/foundations/relativistic-particles-and-fields/multiparticle-states/) and [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/). The harmonic oscillator viewpoint continues in [Harmonic Oscillator Modes](/foundations/canonical-quantization/harmonic-oscillator-modes/).

## The direct sum of sectors

Let $\mathcal H_1$ be the one-particle Hilbert space for one species. The bosonic Fock space is

$$
\mathcal F_+(\mathcal H_1)
=\bigoplus_{N=0}^{\infty}\operatorname{Sym}^N\mathcal H_1.
$$

The fermionic Fock space is

$$
\mathcal F_-(\mathcal H_1)
=\bigoplus_{N=0}^{\infty}\wedge^N\mathcal H_1.
$$

The zero-particle sector is

$$
\mathcal H_0\cong\mathbb C\lvert0\rangle.
$$

Here $\lvert0\rangle$ is the vacuum for the Fock-space species under discussion. In an interacting QFT, the physical vacuum may have nontrivial correlations, degeneracy, condensates, or topology. “Vacuum” does not mean a classical empty room.

A general Fock-space state has components in many sectors:

$$
\lvert\Psi\rangle
=\psi_0\lvert0\rangle+
\lvert\Psi_1\rangle+
\lvert\Psi_2\rangle+
\cdots.
$$

This is the infinite list of wavefunctions that occupation-number language compresses.

## Creation and annihilation operators

Let

$$
q=(\boldsymbol p,\alpha)
$$

collect momentum and discrete labels. Define

$$
\delta(q,q')=(2\pi)^3 2E_{\boldsymbol p}\delta^{(3)}(\boldsymbol p-\boldsymbol p')\delta_{\alpha\alpha'},
$$

and

$$
\int d\mu(q)=\sum_\alpha\int\frac{d^3\boldsymbol p}{(2\pi)^3 2E_{\boldsymbol p}}.
$$

The vacuum is annihilated by all annihilation operators:

$$
a(q)\lvert0\rangle=0.
$$

A one-particle state is

$$
\lvert q\rangle=a^\dagger(q)\lvert0\rangle.
$$

An $N$-particle basis state is

$$
\lvert q_1,\ldots,q_N\rangle
=a^\dagger(q_1)\cdots a^\dagger(q_N)\lvert0\rangle.
$$

The exchange properties of the state are encoded in the algebra of the creation operators.

For bosons,

$$
[a(q),a^\dagger(q')]=\delta(q,q'),
\qquad
[a(q),a(q')]=0,
\qquad
[a^\dagger(q),a^\dagger(q')]=0.
$$

For fermions,

$$
\{a(q),a^\dagger(q')\}=\delta(q,q'),
\qquad
\{a(q),a(q')\}=0,
\qquad
\{a^\dagger(q),a^\dagger(q')\}=0.
$$

:::note[Notation]
This page uses $a,a^\dagger$ generically. The commutator or anticommutator tells you whether the mode is bosonic or fermionic.
:::

## How annihilation operators act

For bosons,

$$
a(q)\lvert q_1,\ldots,q_N\rangle
=\sum_{r=1}^N
\delta(q,q_r)
\lvert q_1,\ldots,\widehat q_r,\ldots,q_N\rangle.
$$

The hat means that the label is omitted.

For fermions,

$$
a(q)\lvert q_1,\ldots,q_N\rangle
=\sum_{r=1}^N
(-1)^{r-1}\delta(q,q_r)
\lvert q_1,\ldots,\widehat q_r,\ldots,q_N\rangle.
$$

The sign appears because the annihilation operator must pass through $r-1$ fermionic creation operators before reaching the matching one.

## Occupation numbers

In a discrete mode basis, bosonic modes satisfy

$$
[a_i,a_j^\dagger]=\delta_{ij}.
$$

A normalized occupation-number state is

$$
\lvert n_1,n_2,\ldots\rangle
=\prod_i\frac{(a_i^\dagger)^{n_i}}{\sqrt{n_i!}}\lvert0\rangle,
\qquad
n_i=0,1,2,\ldots.
$$

The ladder operators act as

$$
a_i^\dagger\lvert\ldots,n_i,\ldots\rangle
=\sqrt{n_i+1}\lvert\ldots,n_i+1,\ldots\rangle,
$$

and

$$
a_i\lvert\ldots,n_i,\ldots\rangle
=\sqrt{n_i}\lvert\ldots,n_i-1,\ldots\rangle.
$$

For fermions,

$$
\{a_i,a_j^\dagger\}=\delta_{ij},
$$

and each occupation number is only

$$
n_i=0\quad\text{or}\quad1.
$$

Indeed,

$$
(a_i^\dagger)^2=0.
$$

A fixed order of fermionic modes must be chosen; reordering occupied fermionic modes changes the sign of the state.

## Number operator and additive observables

The total number operator is

$$
\boxed{
\widehat N=\int d\mu(q)\,a^\dagger(q)a(q).
}
$$

It satisfies

$$
[\widehat N,a^\dagger(q)]=a^\dagger(q),
\qquad
[\widehat N,a(q)]=-a(q),
$$

for both bosons and fermions. Thus

$$
\widehat N\lvert q_1,\ldots,q_N\rangle
=N\lvert q_1,\ldots,q_N\rangle.
$$

Any additive one-particle quantity has a similar form. The free four-momentum is

$$
P^\mu=\int d\mu(q)\,p^\mu(q)a^\dagger(q)a(q),
$$

and a conserved additive charge is

$$
Q=\int d\mu(q)\,Q(q)a^\dagger(q)a(q).
$$

If an interaction does not commute with $\widehat N$, particle number is not conserved. Exact charges may still be conserved.

## Particle-number-changing operators

A schematic operator with $r$ creation operators and $s$ annihilation operators has the form

$$
\mathcal O_{r,s}
\sim
\int h(q'_1,\ldots,q'_r;q_1,\ldots,q_s)
\,a^\dagger(q'_1)\cdots a^\dagger(q'_r)a(q_s)\cdots a(q_1).
$$

It destroys $s$ quanta and creates $r$ quanta. Its commutator with number is

$$
[\widehat N,\mathcal O_{r,s}]=(r-s)\mathcal O_{r,s}.
$$

Local QFT interactions are more constrained than this schematic expression; they must respect locality, Lorentz covariance, and exact charges. But the Fock-space meaning is simple: interactions are made from operators that create and annihilate quanta.

## Preview: fields from ladder operators

A free real scalar field will later be written as

$$
\phi(x)
=\int d\Pi_p\left[a(\boldsymbol p)e^{-ip\cdot x}+a^\dagger(\boldsymbol p)e^{ip\cdot x}\right].
$$

Read this structurally before deriving it. The field is a local operator. Its annihilation part removes a quantum; its creation part adds one. Correlation functions, propagators, Wick contractions, and Feynman rules are built from these two halves.

## Free Fock space versus interacting Hilbert space

Fock space is exact for free fields and essential for perturbation theory around a chosen vacuum. It supplies the free states, free propagators, Wick expansion, and asymptotic in/out states used by LSZ.

But an interacting Hilbert space can be subtler. Bound states, confinement, massless long-range fields, degenerate vacua, thermal states, and curved spacetime can all weaken or change the particle interpretation. Treat Fock space as the indispensable local coordinate chart near a free or asymptotic-particle description, not as the final word on every QFT.

## Common pitfalls

**Thinking Fock space means particle number is conserved.** Fock space allows variable particle number. Conservation of a number operator is a separate dynamical question.

**Confusing vacuum with empty classical space.** The vacuum is the lowest-energy or reference state in a Hilbert space. It can have nontrivial correlations.

**Forgetting fermionic ordering.** The ordering of fermionic creation operators is part of the notation. Reordering changes signs.

**Treating free Fock space as universal.** It is central for perturbation theory and scattering, but not every QFT has a simple global particle basis.

## Relation to other topics

- [Multiparticle States](/foundations/relativistic-particles-and-fields/multiparticle-states/) constructs the sectors that Fock space sums over.
- [Bosons and Fermions](/foundations/relativistic-particles-and-fields/bosons-and-fermions/) explains the statistics encoded in the operator algebra.
- [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/) uses two oscillator species for charged fields.
- [Harmonic Oscillator Modes](/foundations/canonical-quantization/harmonic-oscillator-modes/) explains why free fields become oscillator towers.
- [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/) derives the scalar field expansion.
- [Wick Theorem](/foundations/interactions-and-wick-expansion/wick-theorem/) uses the creation-annihilation algebra to organize contractions.

## Research status

- **Established:** Bosonic and fermionic Fock spaces are the standard free-field and perturbative starting point.
- **Active:** Non-Fock representations, inequivalent vacua, infraparticles, curved-spacetime particle definitions, and algebraic QFT remain important structural topics.

## References

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 2–4.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 4.
- M. Srednicki, *Quantum Field Theory*, §§1–3.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed., Part I.8.

## Version history

- **2026-06-08:** Revised for chapter terminology, less repetition with the multiparticle and statistics pages, clearer caveats about interacting Hilbert spaces, and a more direct handoff to canonical quantization.
