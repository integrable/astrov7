---
title: "Antiparticles"
description: "Negative-frequency modes, complex fields, particle and antiparticle creation operators, charge conjugation, neutral self-conjugate fields, and why antiparticles are not optional bookkeeping."
sidebar:
  label: "Antiparticles"
  order: 7
level: Graduate
status: "Polished draft"
topics:
  - antiparticles
  - complex scalar field
  - charge conjugation
  - particle–antiparticle sectors
  - negative-frequency modes
canonicalTopics:
  - antiparticles
  - complex-field-mode-expansion
  - charge-conjugation-preview
---

## Summary

A relativistic charged field does not describe only one kind of particle. Its local mode expansion contains two positive-energy sectors: particles and antiparticles.

For a free complex scalar field,

$$
\boxed{
\phi(x)=\int d\Pi_p
\left[a(\boldsymbol p)e^{-ip\cdot x}+b^\dagger(\boldsymbol p)e^{ip\cdot x}\right],
}
$$

and

$$
\boxed{
\phi^\dagger(x)=\int d\Pi_p
\left[a^\dagger(\boldsymbol p)e^{ip\cdot x}+b(\boldsymbol p)e^{-ip\cdot x}\right].
}
$$

The operator $a^\dagger$ creates a particle, while $b^\dagger$ creates its antiparticle. Both excitations have positive energy

$$
E_{\boldsymbol p}=\sqrt{\boldsymbol p^2+m^2}.
$$

The phrase “negative-frequency mode” does not mean “negative-energy particle.” In the quantum field, the negative-frequency branch is reinterpreted as creation of a positive-energy antiparticle.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Complex scalar field modes and antiparticles](/figures/foundations/antiparticle-modes.svg)

<figcaption>

The complex scalar field $\phi$ annihilates a particle through the $a e^{-ip\cdot x}$ term and creates an antiparticle through the $b^\dagger e^{ip\cdot x}$ term. Its adjoint performs the conjugate operations.

</figcaption>
</figure>

## Prerequisites

You should know [Why Fields?](/foundations/relativistic-particles-and-fields/why-fields/), [Relativistic Normalization](/foundations/relativistic-particles-and-fields/relativistic-normalization/), [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/), and the real and complex scalar fields from [Scalar Fields](/foundations/classical-field-theory/scalar-fields/). The full derivation appears in [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/).

## The core idea

The classical Klein–Gordon equation has two frequency branches,

$$
p^0=+E_{\boldsymbol p},
\qquad
p^0=-E_{\boldsymbol p}.
$$

A one-particle interpretation struggles with this. QFT changes the interpretation: the field is an operator, and the two branches become different operator actions.

For a charged scalar field,

$$
\phi\sim a e^{-ip\cdot x}+b^\dagger e^{ip\cdot x}.
$$

The positive-frequency term annihilates a particle. The negative-frequency term creates an antiparticle. Locality, positive energy, and charge conservation are then compatible.

## Real scalar versus complex scalar

A real scalar field satisfies

$$
\phi^\dagger=\phi.
$$

Its expansion has one oscillator species:

$$
\phi(x)=\int d\Pi_p\left[a(\boldsymbol p)e^{-ip\cdot x}+a^\dagger(\boldsymbol p)e^{ip\cdot x}\right].
$$

The quantum created by $a^\dagger$ is neutral and self-conjugate.

A complex scalar field has independent $\phi$ and $\phi^\dagger$. Its expansion needs two oscillator species:

$$
\phi(x)=\int d\Pi_p
\left[a(\boldsymbol p)e^{-ip\cdot x}+b^\dagger(\boldsymbol p)e^{ip\cdot x}\right],
$$

$$
\phi^\dagger(x)=\int d\Pi_p
\left[a^\dagger(\boldsymbol p)e^{ip\cdot x}+b(\boldsymbol p)e^{-ip\cdot x}\right].
$$

The two species have equal mass because both use the same on-shell energy. They differ by additive internal charges.

## Charge counting

Use the phase convention

$$
\phi\mapsto e^{-iq\alpha}\phi,
\qquad
\phi^\dagger\mapsto e^{iq\alpha}\phi^\dagger.
$$

The normal-ordered charge operator is

$$
\boxed{
Q=q\int d\Pi_p
\left[a^\dagger(\boldsymbol p)a(\boldsymbol p)-b^\dagger(\boldsymbol p)b(\boldsymbol p)\right].
}
$$

Therefore

$$
Q\,a^\dagger(\boldsymbol p)\lvert0\rangle
=+q\,a^\dagger(\boldsymbol p)\lvert0\rangle,
$$

while

$$
Q\,b^\dagger(\boldsymbol p)\lvert0\rangle
=-q\,b^\dagger(\boldsymbol p)\lvert0\rangle.
$$

The particle has charge $+q$ and the antiparticle has charge $-q$. The sign of $q$ depends on the convention for the phase rotation; the invariant statement is that particle and antiparticle carry opposite additive charges.

## Positive energy

The Hamiltonian has the schematic form

$$
H=\int d\Pi_p\,E_{\boldsymbol p}
\left[a^\dagger(\boldsymbol p)a(\boldsymbol p)+b^\dagger(\boldsymbol p)b(\boldsymbol p)\right]
$$

up to the vacuum-energy convention. Thus

$$
H\,a^\dagger(\boldsymbol p)\lvert0\rangle
=E_{\boldsymbol p}\,a^\dagger(\boldsymbol p)\lvert0\rangle,
$$

and

$$
H\,b^\dagger(\boldsymbol p)\lvert0\rangle
=E_{\boldsymbol p}\,b^\dagger(\boldsymbol p)\lvert0\rangle.
$$

Both excitations have positive energy. The sign in $e^{ip\cdot x}$ is a sign in the spacetime dependence of a creation term, not a sign of physical energy.

:::caution[Do not quantize the negative branch as negative energy]
A stable relativistic quantum theory needs energy bounded below. Antiparticle creation operators are how the negative-frequency branch is included without introducing physical negative-energy particles.
:::

## Why locality wants the conjugate sector

A neutral scalar can combine annihilation and creation of the same particle:

$$
\phi\sim a e^{-ip\cdot x}+a^\dagger e^{ip\cdot x}.
$$

For a charged scalar, the field should transform with a definite charge. The creation term in $\phi$ cannot be $a^\dagger$, because $a^\dagger$ creates the same charge that $\phi$ annihilates. The field must instead contain

$$
b^\dagger e^{ip\cdot x},
$$

which creates a state of the opposite charge. That state is the antiparticle.

This is the local-field version of a broad rule: charged sectors in relativistic QFT come with conjugate sectors. In full generality, CPT symmetry guarantees corresponding antiparticle states under the usual locality, Lorentz-invariance, and positivity assumptions.

## Charge conjugation is a separate question

Charge conjugation exchanges particles and antiparticles. For the free complex scalar,

$$
C a(\boldsymbol p)C^{-1}=b(\boldsymbol p),
\qquad
C b(\boldsymbol p)C^{-1}=a(\boldsymbol p),
$$

and, up to phases,

$$
C\phi(x)C^{-1}=\phi^\dagger(x).
$$

If the Hamiltonian is invariant under this operation, then $C$ is a symmetry. But antiparticles can exist even when charge conjugation is not an exact symmetry. The weak interaction violates $C$; positrons still exist.

:::note[Two different claims]
“Antiparticles exist” means the theory contains conjugate particle states with opposite additive charges. “Charge conjugation is a symmetry” means the dynamics are invariant when particles and antiparticles are exchanged.
:::

## Self-conjugate particles

A particle can be its own antiparticle if all relevant additive charges vanish and the representation admits an appropriate reality condition.

Examples:

| Field or particle type | Antiparticle relation |
|---|---|
| real scalar field | self-conjugate |
| complex charged scalar field | distinct antiparticle |
| photon | self-conjugate |
| electron | positron is distinct |
| charged pion $\pi^+$ | $\pi^-$ is distinct |
| neutral pion $\pi^0$ | self-conjugate |
| Dirac fermion | distinct antiparticle |
| Majorana fermion | self-conjugate if allowed by charges |

The table is conceptual. In interacting theories, physical particles may be composite excitations rather than elementary fields appearing directly in the Lagrangian.

## Dirac-field preview

A free Dirac field has the same structure with spinor wavefunctions:

$$
\psi(x)=\sum_s\int d\Pi_p
\left[
 a_s(\boldsymbol p)u_s(p)e^{-ip\cdot x}
+b_s^\dagger(\boldsymbol p)v_s(p)e^{ip\cdot x}
\right].
$$

The $a_s^\dagger$ operators create fermions, while the $b_s^\dagger$ operators create antifermions. The spinors $u_s(p)$ and $v_s(p)$ carry the Lorentz transformation information needed for $\psi$ to transform as a spinor.

The scalar case is presented first because it contains the essential particle–antiparticle logic without gamma matrices.

## Common pitfalls

**Calling antiparticles negative-energy particles.** Physical antiparticle states have positive energy.

**Thinking every neutral particle is self-conjugate.** A particle with zero electric charge may carry another additive charge. Self-conjugacy requires all relevant additive charges to vanish.

**Confusing charge conjugation with complex conjugation.** For simple scalars they look close. For spinors, gauge multiplets, and interacting theories, charge conjugation includes representation data and phase conventions.

**Assuming $C$ symmetry is required for antiparticles.** Antiparticles are state content. Charge conjugation symmetry is an additional dynamical statement.

**Treating the field as the particle.** The field is an operator. It may annihilate a particle or create an antiparticle.

## Relation to other topics

- [Why Fields?](/foundations/relativistic-particles-and-fields/why-fields/) explains why field language replaces fixed-particle wave mechanics.
- [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/) supplies the creation and annihilation language.
- [Complex Scalar Field](/foundations/canonical-quantization/complex-scalar-field/) derives the expansion and charge operator.
- [Dirac Field](/foundations/free-fields/dirac-field/) develops the spinor version.
- [Discrete Symmetries](/foundations/symmetry-and-spacetime/discrete-symmetries/) treats $C$, $P$, and $T$ systematically.
- [CPT Theorem](/foundations/symmetry-and-spacetime/cpt-theorem/) states the structural theorem relating particles and antiparticles.

## Research status

- **Established:** Relativistic local QFT contains positive-energy antiparticle sectors for charged fields under the standard assumptions.
- **Active:** In curved spacetime, time-dependent backgrounds, condensed-matter systems, and strongly coupled theories, the particle–antiparticle language may require careful reinterpretation.

## References

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 6.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §5.2.
- M. Srednicki, *Quantum Field Theory*, §§1 and 3.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed., Parts I.4 and II.1–II.2.

## Version history

- **2026-06-08:** Revised for chapter terminology, clearer positive-energy language, leaner charge-conjugation discussion, and tighter handoff to complex scalar and Dirac-field pages.
