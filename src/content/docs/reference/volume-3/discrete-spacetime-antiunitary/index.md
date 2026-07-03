---
title: "Discrete, Spacetime, and Antiunitary Symmetries"
description: "Chapter overview for parity, time reversal, charge conjugation, CPT, antiunitary symmetries, reflection positivity, spin structures, and discrete-symmetry anomalies."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki §§23, 40; Weinberg Vol. I Chs. 2–3; Coleman lectures on CPT and discrete symmetries; standard treatments of spin structures, reflection positivity, and discrete anomalies."
topics:
  - parity
  - time reversal
  - charge conjugation
  - CPT theorem
  - antiunitary symmetry
  - reflection positivity
  - spin structures
  - fermion parity
  - crystalline symmetry
  - discrete anomalies
canonicalTopics:
  - parity
  - time-reversal
  - charge-conjugation
  - cpt-theorem
  - antiunitary-symmetry
  - reflection-positivity
  - spin-structure
  - fermion-parity
researchStatus:
  established:
    - "Parity, charge conjugation, time reversal, and CPT are standard discrete operations in relativistic QFT, with time reversal represented antiunitarily in Lorentzian quantum theory."
    - "The CPT theorem is a structural result of local relativistic QFT under appropriate assumptions, not a model-by-model accident."
  active:
    - "Discrete symmetries with spin, spacetime reflection, boundaries, crystalline actions, higher-form backgrounds, and non-invertible defects remain active in anomaly, phase, and symmetry-TFT research."
---

Discrete, Spacetime, and Antiunitary Symmetries is the chapter in the Symmetry, Anomalies, and Topology volume where symmetries are allowed to do more than rotate internal labels. They may reverse spatial orientation, reverse time orientation, exchange particles with antiparticles, conjugate complex phases, or depend on the spin structure of spacetime.

This chapter exists because $P$, $T$, $C$, and $CPT$ are not decorative symbols attached to old particle-physics tables. They are tests of how a QFT is glued to spacetime, how its Hilbert space realizes quantum symmetries, and how locality constrains possible violations.

The guiding slogan is:

$$
\text{discrete symmetry is where spacetime, conjugation, and topology meet.}
$$

Parity and time reversal act on spacetime arguments. Charge conjugation acts on internal charge assignments. Time reversal is antiunitary in Lorentzian quantum theory. CPT combines all three into a theorem-level constraint in local relativistic QFT.

<figure class="doc-figure" style="--figure-width: 56rem;">

![A roadmap diagram for the Discrete, Spacetime, and Antiunitary Symmetries chapter. It separates unitary spacetime reflections, antiunitary time reversal, charge conjugation, CPT, and the geometric data needed for spin, reflection positivity, crystalline symmetry, and discrete anomalies.](/figures/symmetry-anomalies-topology/discrete-spacetime-antiunitary-roadmap.svg)

<figcaption>

Discrete symmetries are not all the same kind of operation. Parity is usually unitary and reverses spatial orientation. Time reversal is antiunitary and reverses the sign of $i$. Charge conjugation exchanges charges and representations. CPT is a structural combination tied to locality, spin, and Lorentzian QFT. Spin structures, reflection positivity, crystalline symmetries, and discrete anomalies refine the story.

</figcaption>
</figure>

The chapter is deliberately conservative at the beginning. It starts with the textbook $P$, $T$, and $C$ transformations of scalar, spinor, vector, and current operators. Later pages explain why the same symbols become subtler in chiral gauge theories, Euclidean path integrals, systems with boundaries, condensed-matter phases, and modern anomaly classification.

## Prerequisites

You should know the volume [Conventions and Notation](/symmetry-anomalies-topology/conventions/), especially the mostly-minus metric, gamma-matrix convention, and current-source signs.

From earlier chapters, the most useful pages are [Internal versus Spacetime Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/internal-versus-spacetime-symmetries/), [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/), [Projective Representations Preview](/symmetry-anomalies-topology/ordinary-global-symmetries/projective-representations-preview/), and [Charges Acting on Local Operators](/symmetry-anomalies-topology/noether-currents-ward-identities/charges-acting-on-local-operators/).

You should also be comfortable with Lorentz transformations, spinor chirality, the distinction between unitary and antiunitary operators in quantum mechanics, and the idea that fermionic QFTs require spin-structure data.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | Parity | Spatial orientation reversal, intrinsic parity, scalar/vector/axial transformations, spinor parity, and parity-odd terms. |
| 2 | Time Reversal | Antiunitarity, reversal of momenta and angular momenta, Kramers structure, time-reversal signs of fields and response coefficients. |
| 3 | Charge Conjugation | Particle–antiparticle exchange, conjugate representations, vector and axial currents, Majorana subtleties, and neutral-field conventions. |
| 4 | CPT Theorem Perspective | Why local Lorentzian QFT strongly constrains the combined operation $CPT$, and what assumptions enter the theorem. |
| 5 | Antiunitary Symmetries | Wigner’s theorem, complex conjugation, Kramers degeneracy, antiunitary internal symmetries, and reality structures. |
| 6 | Reflection Positivity and Time Reversal | The Euclidean version of time-reflection positivity and how it reconstructs Lorentzian unitarity. |
| 7 | Crystalline and Spacetime Symmetries Preview | Discrete translations, rotations, reflections, glide/screw operations, and the warning that spacetime symmetries can mix with internal data. |
| 8 | Spin Structures and Fermion Parity | Why fermions require extra global geometric data and why $(-1)^F$ is more fundamental than many optional symmetries. |
| 9 | Anomalies of Discrete Symmetries Preview | How a discrete symmetry can fail to be consistently gauged or coupled to background fields. |

The first four pages are the core. The last five pages are bridges to generalized symmetry, anomalies, topology, Euclidean QFT, and phases of matter.

## Landmarks

A parity transformation is not merely the instruction “replace $\mathbf x$ by $-\mathbf x$.” It is a candidate quantum symmetry operator, usually denoted $\mathsf P$, together with transformation laws for every field, source, state, and operator in the theory. A Lagrangian density may look spatially reflected and still fail to be parity invariant if the field transformations are inconsistent.

Time reversal is antiunitary in Lorentzian quantum mechanics. This is not a technical footnote. If time reversal were unitary while reversing the sign of energy as a four-vector component, the Hamiltonian invariance condition would be wrong. Antiunitarity gives

$$
\mathsf T i\mathsf T^{-1}=-i,
$$

which is why time reversal can reverse momenta and angular momenta while preserving positive energy.

Charge conjugation is not spacetime reflection. It changes internal representation data: charges, gauge representations, and sometimes complex structures. A theory only has charge conjugation if its spectrum and interactions admit such a conjugation operation. A complex scalar with a $U(1)$ charge can be charge-conjugated; a chiral gauge theory may not possess a standalone $C$ symmetry.

Parity flips chirality. In four-dimensional Dirac notation, parity exchanges left- and right-handed Weyl components because

$$
\gamma^0\gamma^5\gamma^0=-\gamma^5.
$$

This is one reason chiral weak interactions violate parity so dramatically: a theory containing only a left-handed current is not mapped to itself by ordinary parity.

CPT is stronger than the empirical statement that many observed interactions respect a combined transformation. Under the usual assumptions of local relativistic QFT, $CPT$ is forced even when $C$, $P$, and $T$ are separately violated. The theorem is sensitive to assumptions: locality, Lorentz invariance, a stable vacuum, spin-statistics, and analytic continuation all matter in different formulations.

Discrete symmetries can be anomalous. For continuous symmetries, anomalies often first appear as nonconservation of a current. For finite or spacetime-reflection symmetries, there may be no current at all. The modern diagnostic is whether the theory can be consistently coupled to suitable background fields, bundles, spin structures, or reflection structures and whether gauging is obstructed.

## Common confusions

**Confusion 1: Parity is always full spatial inversion.** In $3+1$ dimensions, full inversion $\mathbf x\mapsto-\mathbf x$ reverses spatial orientation and is a standard parity choice. In $2+1$ dimensions, flipping both spatial coordinates is a rotation by $\pi$, so “parity” usually means reflecting one spatial coordinate. The word parity must be interpreted dimension by dimension.

**Confusion 2: Time reversal means playing a movie backward.** The symmetry operation is defined on states and operators. Its antiunitarity is essential. It reverses momenta, angular momenta, magnetic fields, and phases in a controlled way; it is not a naive operation on a recorded classical history.

**Confusion 3: Charge conjugation is complex conjugation of every formula.** Charge conjugation may involve complex conjugation of representation matrices, but as a quantum symmetry it is an operator acting on the Hilbert space and operator algebra. It is not the instruction “put a star on the equation.”

**Confusion 4: Intrinsic parity is directly observable for a single particle.** Overall phase choices in the definition of a symmetry operator can change individual intrinsic-parity assignments. Relative parity assignments and selection rules are physical.

**Confusion 5: If a classical Lagrangian has $P$, $T$, or $C$, the quantum theory automatically has it.** Regulators, measures, background fields, boundary conditions, and global topology can obstruct a classical discrete symmetry. This is one of the main reasons discrete anomalies belong in this volume.

**Confusion 6: Gauge transformations and discrete global symmetries are interchangeable.** A discrete gauge redundancy, a finite global symmetry, a spacetime reflection, and a quotient by a crystalline group are different structures. They may be related by gauging or orbifolding, but they should not be collapsed into one word.

## Boundaries

This chapter is not a full treatment of Lorentz representation theory. The representation-theory foundations live in the Mathematical Toolkit and Foundations volumes. Here the focus is on how discrete transformations act in QFT and how they constrain operators and interactions.

This chapter is not the canonical home of the full CPT theorem proof. The page on CPT gives assumptions, consequences, and proof strategy. A theorem-first treatment belongs in the Mathematical and Rigorous QFT volume.

This chapter is not a full catalog of crystalline groups, topological crystalline phases, or condensed-matter space groups. It gives QFT-facing principles and points to the Matter, Statistical Physics, and Quantum Information volume for detailed phases.

This chapter is not the full anomaly classification program. It introduces discrete anomalies and their diagnostics; the Anomalies, ’t Hooft Anomalies, Symmetry TFT, and Topological Terms chapters develop the general machinery.

## Where to go next

After this chapter, continue to [Anomalies](/symmetry-anomalies-topology/anomalies/) if your goal is chiral symmetry, parity-odd terms, $F\widetilde F$, and regulator obstructions.

Continue to [Topological Terms](/symmetry-anomalies-topology/topological-terms/) if your goal is theta terms, Chern–Simons terms, Wess–Zumino terms, and parity/time-reversal-odd actions.

Continue to [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) or [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) if you want the modern background-field and bulk-boundary language for discrete anomalies.

For Euclidean reconstruction and theorem-level assumptions, go to the Mathematical and Rigorous QFT volume after reading the reflection-positivity page.

## References

- M. Srednicki, *Quantum Field Theory*, §§23 and 40. A compact textbook treatment of $P$, $T$, $C$, scalar signs, spinor transformations, and bilinears.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, Chs. 2–3. Especially useful for Wigner’s theorem, space inversion, time reversal, projective representations, and symmetry constraints on the S-matrix.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chapters on symmetries, CPT, and Fermi fields.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 11 and 30. Useful for spinor solutions, CPT, and anomaly-facing examples.
- R. Streater and A. Wightman, *PCT, Spin and Statistics, and All That*. The classic theorem-level reference for the rigorous side.
- E. Witten, “Fermion Path Integrals and Topological Phases,” *Rev. Mod. Phys.* 88, 035001 (2016). A modern reference for fermion parity, spin structures, and reflection-related subtleties.

## Version history

- 2026-06-17: Initial polished draft. Added chapter roadmap, reading path, conceptual boundaries, and handoffs to anomalies, topology, and rigorous QFT.
