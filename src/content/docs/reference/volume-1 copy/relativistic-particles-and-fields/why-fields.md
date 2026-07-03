---
title: "Why Fields?"
description: "Why local relativistic quantum theory is organized by fields rather than fixed-particle-number wavefunctions."
sidebar:
  label: "Why Fields?"
  order: 1
level: Graduate
status: "Polished draft"
topics:
  - why fields
  - locality
  - relativistic quantum mechanics
  - variable particle number
  - Klein–Gordon equation
canonicalTopics:
  - why-quantum-fields
  - fixed-particle-number-limits
  - relativistic-locality
---

## Summary

Relativistic one-particle quantum mechanics is a useful kinematic subject. A stable free particle can be described by a positive-energy representation of the Poincaré group. That is not the problem.

The problem appears when we ask for **locality**, **relativity**, **quantum mechanics**, and **interactions** at the same time. Fixed-particle-number wavefunctions are then the wrong basic language. They do not naturally describe particle creation, antiparticles, local observables, or spacelike separation.

QFT changes the starting point. Spacetime points label local operators,

$$
\phi(x),\qquad \psi(x),\qquad A_\mu(x),
$$

not particle positions. Particles are states or excitations of the theory. Fields are the local objects whose correlations, commutators, and matrix elements encode the physics.

<figure class="doc-figure" style="--figure-width: 48rem;">

![From fixed-particle wave mechanics to local quantum fields](/figures/foundations/why-fields-flow.svg)

<figcaption>

A fixed-particle wavefunction can be a good approximation in low-energy sectors. A local relativistic quantum theory needs a state space with variable particle number and local field operators acting on that space.

</figcaption>
</figure>

:::tip[The slogan]
Do not promote spacetime coordinates to particle-position operators. Attach operators to spacetime points and let particles appear as states, excitations, or poles of correlation functions.
:::

## What fixed-particle quantum mechanics does well

For one nonrelativistic particle, a wavefunction

$$
\psi(t,\boldsymbol x)
$$

is often ideal. For $N$ particles, one uses

$$
\psi(t,\boldsymbol x_1,\ldots,\boldsymbol x_N).
$$

This works beautifully when the number and species of particles are fixed. Even in nonrelativistic many-body physics, it is often convenient to rewrite the same theory using creation and annihilation operators. There, field language may be a useful reformulation.

In relativistic local quantum theory, the pressure is stronger. Interactions can turn energy into particles and antiparticles. Local measurements should commute at spacelike separation. A description based on one fixed $N$-particle wavefunction is no longer the natural home.

## The square-root Hamiltonian warning

A free relativistic particle has energy

$$
E_{\boldsymbol p}=\sqrt{\boldsymbol p^2+m^2}.
$$

A direct positive-energy one-particle equation would be

$$
i\frac{\partial}{\partial t}\psi(t,\boldsymbol x)
=\sqrt{-\nabla^2+m^2}\,\psi(t,\boldsymbol x).
$$

This equation keeps positive energy and is first order in time, but the square-root operator is nonlocal in space. Formally,

$$
\sqrt{m^2-\nabla^2}
=m-\frac{\nabla^2}{2m}-\frac{(\nabla^2)^2}{8m^3}-\cdots,
$$

an infinite derivative expansion. That is not the local relativistic structure we want for interactions.

Squaring the equation gives the local Lorentz-covariant Klein–Gordon equation,

$$
(\Box+m^2)\psi=0.
$$

But as a one-particle wave equation it has another problem: the natural conserved current is not positive definite.

## The Klein–Gordon current problem

For a complex solution of

$$
(\Box+m^2)\psi=0,
$$

the current

$$
j^\mu=i\left(\psi^*\partial^\mu\psi-(\partial^\mu\psi^*)\psi\right)
$$

obeys $\partial_\mu j^\mu=0$. For a plane wave $\psi=Ae^{-ip\cdot x}$,

$$
j^0=2p^0|A|^2.
$$

Positive-frequency modes have positive $j^0$; negative-frequency modes have negative $j^0$. Thus $j^0$ is not a probability density for one particle.

The right conclusion is not that the Klein–Gordon equation is bad. The right conclusion is that it should be interpreted as a **field equation**. In a complex scalar field, the same current becomes a charge current, and the two frequency branches become particle and antiparticle operator sectors.

## The Dirac equation does not make fields optional

The Dirac equation is first order in time and gives a positive probability density in a one-particle reading. It is a major improvement over the Klein–Gordon equation as a relativistic wave equation.

But the field-theory lesson remains. The Dirac spectrum still forces a particle–antiparticle interpretation, and a local interacting theory still needs variable particle number. Modern QFT does not keep a filled sea of negative-energy electrons as the basic object. It quantizes a local spinor field whose mode expansion contains fermion and antifermion creation operators.

So the lesson is not

$$
\text{Klein–Gordon bad, Dirac good, fields optional.}
$$

It is

$$
\text{relativistic wave equations become field equations in local QFT.}
$$

## Variable particle number

Relativity relates energy and mass. With enough energy and the right quantum numbers, reactions can change particle number, for example

$$
e^-+e^+\to \mu^-+\mu^+,
$$

or

$$
\gamma+\gamma\to e^-+e^+.
$$

No fixed one-particle Hilbert space can describe such processes. The state space must allow sectors with different numbers of quanta:

$$
\mathcal F
=\mathcal H_0\oplus\mathcal H_1\oplus\mathcal H_2\oplus\cdots.
$$

Creation and annihilation operators move between these sectors:

$$
a^\dagger:\mathcal H_N\to\mathcal H_{N+1},
\qquad
 a:\mathcal H_N\to\mathcal H_{N-1}.
$$

A free scalar field is built from these operators:

$$
\phi(x)
=\int d\Pi_p\left[a(\boldsymbol p)e^{-ip\cdot x}+a^\dagger(\boldsymbol p)e^{ip\cdot x}\right].
$$

The local field contains an annihilation part and a creation part. That is the seed of perturbation theory, propagators, and Wick contractions.

## Locality and spacetime labels

In ordinary one-particle quantum mechanics, position is an operator while time is a parameter. Relativity mixes space and time, so this asymmetry is not a comfortable foundation for local relativistic physics.

QFT uses a different arrangement:

$$
\text{spacetime point }x \quad\longmapsto\quad \text{local operator }\mathcal O(x).
$$

The locality requirement is expressed by commutators or anticommutators. For bosonic local observables,

$$
[\mathcal O_1(x),\mathcal O_2(y)]=0
\qquad\text{when }(x-y)^2<0.
$$

This is microcausality. It says that operations in spacelike separated regions cannot be used for instantaneous signaling. In a field theory, locality is a structural condition on operators, not a property of one-particle position eigenstates.

Strictly, quantum fields are operator-valued distributions. The well-defined objects are smeared fields such as

$$
\phi(f)=\int d^4x\,f(x)\phi(x),
$$

where $f$ is a test function. The point notation is powerful and standard, but it should be read with this distributional caveat in mind.

## Particles are still real where they are well-defined

QFT does not say particles are fake. It says particles are not the primitive local variables.

A stable particle may appear as

- a one-particle state in Hilbert space;
- an asymptotic incoming or outgoing state in scattering;
- a pole in a two-point function;
- a quasiparticle excitation in an effective description.

These are physical notions, but they can fail or change in strongly coupled, confined, thermal, finite-volume, or curved-spacetime settings. Fields and local observables survive more generally.

## The low-energy limit

Ordinary fixed-particle quantum mechanics works because it is often a controlled approximation. At energies far below pair-production thresholds, and when number-changing processes are negligible or forbidden, one can restrict to a fixed-particle sector. Atomic quantum mechanics is not nonsense because it omits explicit electron–positron pairs; it is an excellent low-energy effective description.

A better hierarchy is therefore

$$
\boxed{\text{fixed-particle quantum mechanics is often a low-energy limit of QFT.}}
$$

## Common pitfalls

**Saying relativity alone forces particle creation.** A free stable relativistic one-particle representation is consistent. Particle creation enters when interactions and sufficient energy are present.

**Saying the Klein–Gordon equation is wrong.** The naive one-particle probability interpretation fails. As a field equation, the Klein–Gordon equation is the first scalar QFT example.

**Treating fields as wavefunctions.** A wavefunction is a state representative. A quantum field is an operator acting on states or a path-integral variable.

**Treating particles as the opposite of fields.** In QFT, particles are produced, detected, and classified using fields and their correlation functions.

**Forgetting the approximation.** A fixed-particle sector can be extremely accurate, but it is a sector or limit, not the whole relativistic local theory.

## Relation to other topics

- [Fields, Actions, and Equations](/foundations/classical-field-theory/fields-actions-equations/) and [Linearization and Normal Modes](/foundations/classical-field-theory/linearization-and-normal-modes/) supply the classical language that will be quantized.
- [Single-Particle States](/foundations/relativistic-particles-and-fields/single-particle-states/) gives the clean representation-theoretic meaning of a stable particle.
- [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/) builds the variable-particle-number Hilbert space.
- [Antiparticles](/foundations/relativistic-particles-and-fields/antiparticles/) explains how the negative-frequency branch becomes a positive-energy conjugate sector.
- [Scalar Field Quantization](/foundations/canonical-quantization/scalar-field-quantization/) turns the classical scalar field into operators.
- [Feynman Propagator](/foundations/correlators-and-propagators/feynman-propagator/) shows how particles appear in correlation functions.

## Research status

- **Established:** Local relativistic QFT uses fields or local operator algebras as the natural language for interactions, causality, and variable particle number.
- **Active:** The particle concept is subtle in curved spacetime, de Sitter settings, confining theories, finite-density systems, and general nonperturbative QFT.

## References

- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 1–4.
- M. Srednicki, *Quantum Field Theory*, §§1–3.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed., Parts I.1, I.3, I.4, and I.8.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 2–5.

## Version history

- **2026-06-08:** Revised for chapter terminology, reduced repetition, sharpened locality and approximation caveats, and connected the page more directly to the reader path.
