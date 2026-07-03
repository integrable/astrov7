---
title: "Multiparticle States"
description: "Tensor-product multiparticle states, identical particles, exchange symmetry, symmetrization, antisymmetrization, normalization, and the bridge to Fock space."
sidebar:
  label: "Multiparticle States"
  order: 4
level: Graduate
status: "Polished draft"
topics:
  - multiparticle states
  - identical particles
  - symmetrization
  - antisymmetrization
  - phase space
canonicalTopics:
  - multiparticle-state
  - identical-particles
  - symmetrization
  - antisymmetrization
---

## Summary

A one-particle state describes one excitation. A multiparticle state describes several excitations at once. For distinguishable particles, the first construction is an ordinary tensor product. For identical particles, that tensor product has too much labeling information: exchanging two identical particles does not produce a new physical configuration.

For one identical species, the physical $N$-particle Hilbert space is therefore either

$$
\mathcal H_N^{(+)}=\operatorname{Sym}^N\mathcal H_1
$$

for bosons, or

$$
\mathcal H_N^{(-)}=\wedge^N\mathcal H_1
$$

for fermions. In words, identical-boson states are symmetric; identical-fermion states are antisymmetric.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Symmetric and antisymmetric projections of a two-particle tensor product](/figures/foundations/multiparticle-symmetrization.svg)

<figcaption>

The ordered tensor product remembers slot labels that identical-particle physics does not. Symmetric and antisymmetric projectors remove the redundant label information in the bosonic and fermionic ways.

</figcaption>
</figure>

## Prerequisites

You should have read [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/) and [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/). The required quantum mechanics is tensor products, Dirac notation, and the exchange rule for identical particles.

## One-particle labels

Bundle momentum and discrete labels into

$$
q=(\boldsymbol p,\alpha),
$$

where $\alpha$ may include spin, helicity, species, charge, flavor, or other internal data. Use the shorthand

$$
\delta(q',q)
=(2\pi)^3 2E_{\boldsymbol p}\delta^{(3)}(\boldsymbol p'-\boldsymbol p)\delta_{\alpha'\alpha},
$$

and

$$
\int d\mu(q)
=\sum_\alpha\int\frac{d^3\boldsymbol p}{(2\pi)^3 2E_{\boldsymbol p}}.
$$

Then

$$
\langle q'\mid q\rangle=\delta(q',q),
\qquad
\mathbf1_1=\int d\mu(q)\,\lvert q\rangle\langle q\rvert.
$$

## Distinguishable particles

For two distinguishable particles $A$ and $B$,

$$
\mathcal H_{A,B}=\mathcal H_A\otimes\mathcal H_B.
$$

A basis state is

$$
\lvert q_A;q_B\rangle
=\lvert q_A\rangle\otimes\lvert q_B\rangle.
$$

The semicolon is a reminder that the two slots refer to different species or different Hilbert spaces. The inner product factorizes:

$$
\langle q_A';q_B'\mid q_A;q_B\rangle
=\delta_A(q_A',q_A)\delta_B(q_B',q_B).
$$

An electron-proton state is not symmetrized under exchanging the electron with the proton. A state with two electrons and one proton is antisymmetric under exchange of the two electrons only.

## Identical particles

For two identical particles, the ordered tensor-product states

$$
\lvert q_1\rangle\otimes\lvert q_2\rangle,
\qquad
\lvert q_2\rangle\otimes\lvert q_1\rangle
$$

contain redundant slot labels. In ordinary relativistic QFT in three spatial dimensions, the physical exchange choices are bosonic and fermionic.

For two identical bosons,

$$
\lvert q_1,q_2\rangle_+
=\lvert q_2,q_1\rangle_+.
$$

For two identical fermions,

$$
\lvert q_1,q_2\rangle_-
=-\lvert q_2,q_1\rangle_-.
$$

A projector construction makes this precise. If $P_{12}$ exchanges the two tensor slots, then

$$
P_+=\frac12(1+P_{12}),
\qquad
P_-=\frac12(1-P_{12}).
$$

The symmetric and antisymmetric sectors are the images of these projectors.

## The $N$-particle sector

For $N$ identical particles, permutations act on tensor slots. The bosonic and fermionic projectors are

$$
\mathcal P_+
=\frac1{N!}\sum_{\pi\in S_N}U(\pi),
$$

and

$$
\mathcal P_-
=\frac1{N!}\sum_{\pi\in S_N}\operatorname{sgn}(\pi)U(\pi).
$$

Thus

$$
\mathcal H_N^{(+)}=\operatorname{Sym}^N\mathcal H_1,
\qquad
\mathcal H_N^{(-)}=\wedge^N\mathcal H_1.
$$

Equivalently,

$$
\lvert q_{\pi(1)},\ldots,q_{\pi(N)}\rangle_+
=
\lvert q_1,\ldots,q_N\rangle_+,
$$

while

$$
\lvert q_{\pi(1)},\ldots,q_{\pi(N)}\rangle_-
=
\operatorname{sgn}(\pi)\lvert q_1,\ldots,q_N\rangle_-.
$$

The antisymmetric rule immediately gives Pauli exclusion. If two fermionic labels are identical, the state equals its own negative, so it vanishes.

## Normalization

For one identical species, the natural $N$-particle basis normalization is

$$
\boxed{
\langle q'_1,\ldots,q'_N\mid q_1,\ldots,q_N\rangle_\eta
=\sum_{\pi\in S_N}\eta(\pi)
\prod_{i=1}^N\delta(q'_i,q_{\pi(i)}),
}
$$

where

$$
\eta(\pi)=
\begin{cases}
1, & \text{bosons},\\
\operatorname{sgn}(\pi), & \text{fermions}.
\end{cases}
$$

The sum over permutations is the mathematical trace of indistinguishability. The final labels can match the initial labels in any order, with the appropriate exchange sign.

## Wave packets and factorials

A normalizable $N$-particle state is

$$
\lvert\Psi_N\rangle
=\frac1{N!}
\int d\mu(q_1)\cdots d\mu(q_N)\,
\Psi_N(q_1,\ldots,q_N)
\lvert q_1,\ldots,q_N\rangle_\eta.
$$

The wavefunction obeys

$$
\Psi_N(q_{\pi(1)},\ldots,q_{\pi(N)})
=\eta(\pi)\Psi_N(q_1,\ldots,q_N).
$$

The factor $1/N!$ removes overcounting of the same unlabeled configuration. Without it, integrating over all ordered labels would count the same generic configuration $N!$ times.

:::tip[Projectors versus normalized states]
The $1/N!$ in a projector and the $1/\sqrt{N!}$ that often appears in normalized basis states have different jobs. One makes an operator idempotent; the other normalizes a state.
:::

## Additive observables

For a multiparticle momentum eigenstate,

$$
P^\mu\lvert q_1,\ldots,q_N\rangle
=\left(\sum_{i=1}^N p_i^\mu\right)
\lvert q_1,\ldots,q_N\rangle.
$$

Similarly, an additive conserved charge acts as

$$
Q\lvert q_1,\ldots,q_N\rangle
=\left(\sum_{i=1}^N Q_i\right)
\lvert q_1,\ldots,q_N\rangle.
$$

Interactions may mix particle-number sectors, but exact energy, momentum, and charges remain operators on the full Hilbert space.

## Several species

A realistic theory has many species. The exchange rule applies to identical quanta of the same species. Two photons are symmetrized. Two electrons are antisymmetrized. An electron-photon state is not symmetrized under exchanging the electron with the photon.

Operator formalisms often impose a graded algebra on all fermionic creation operators, even for different fermion species. That is a consistent bookkeeping convention for many-fermion Fock space; it should not be confused with saying different fermion species are identical.

## Relation to scattering

Scattering theory uses multiparticle states as asymptotic states. Final-state phase space for $N$ on-shell particles is

$$
d\Phi_N(P;p_1,\ldots,p_N)
=(2\pi)^4\delta^{(4)}\!\left(P-\sum_{i=1}^N p_i\right)
\prod_{i=1}^N d\Pi_{p_i}.
$$

When final particles are identical, observable formulas include symmetry factors. The reason is the same overcounting of unordered configurations discussed above.

## What Fock space adds

The sectors

$$
\mathcal H_0,
\mathcal H_1,
\mathcal H_2,
\ldots
$$

are not yet one Hilbert space. A variable-particle-number theory needs all of them and needs operators that move between them. That is the role of [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/):

$$
\mathcal F=\bigoplus_{N=0}^\infty\mathcal H_N.
$$

## Common pitfalls

**Labeling identical particles as if tags were physical.** The labels $1,2,\ldots,N$ are tensor slots, not little name tags attached to particles.

**Symmetrizing distinguishable particles.** Only identical particles are subject to the exchange rule.

**Forgetting symmetry factors.** Identical final particles require symmetry factors in phase-space integrals because ordered momentum labels overcount final configurations.

**Interpreting Pauli exclusion as a force.** The state with two identical fermions in the same one-particle label is absent from Hilbert space. That is not a new microscopic interaction.

## Relation to other topics

- [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/) fixes the one-particle measure and delta functions.
- [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/) packages all $N$-particle sectors.
- [Bosons and Fermions](/foundations/relativistic-particles-and-fields/bosons-and-fermions/) explains how exchange symmetry is encoded by operator algebras.
- [Spin–Statistics](/foundations/symmetry-and-spacetime/spin-statistics/) states the relativistic theorem tying spin to exchange statistics.
- The perturbative QFT scattering pages use multiparticle measures in observable formulas once the scattering section is filled in.

## Research status

- **Established:** Symmetric and antisymmetric Fock sectors are standard for ordinary bosons and fermions in $3+1$-dimensional relativistic QFT.
- **Active:** Low-dimensional systems, anyons, defects, generalized statistics, and nontrivial superselection sectors require broader language.

## References

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 2.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 4.
- M. Srednicki, *Quantum Field Theory*, §1.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed., Parts I.8 and II.4.

## Version history

- **2026-06-08:** Revised for clearer reader flow, chapter terminology, lighter repetition with the Fock-space page, and sharper treatment of identical-particle overcounting.
