---
title: "Reflection Positivity and Time Reversal"
description: "Explains how Euclidean reflection positivity encodes Hilbert-space positivity, how it differs from time-reversal symmetry, and how antiunitary time reversal appears after analytic continuation."
sidebar:
  label: "Reflection Positivity"
  order: 6
level: Advanced
status: "Polished draft"
source: "Osterwalder–Schrader reconstruction; Glimm–Jaffe constructive QFT; Weinberg Vol. I on symmetries and analytic structure; Srednicki and Schwartz on Wick rotation; Jaffe–Ritter on Euclidean functional integrals."
topics:
  - reflection positivity
  - time reversal
  - antiunitary symmetry
  - Euclidean QFT
  - Wick rotation
  - Osterwalder–Schrader reconstruction
  - Hilbert-space positivity
  - topological terms
canonicalTopics:
  - reflection-positivity
  - euclidean-qft
  - antiunitary-time-reversal
  - osterwalder-schrader-positivity
  - wick-rotation
  - unitary-lorentzian-qft
researchStatus:
  established:
    - "Reflection positivity is the Euclidean positivity condition that lets Euclidean correlation functions reconstruct a positive-norm Lorentzian Hilbert space with a positive Hamiltonian."
    - "Lorentzian time reversal, when it is a symmetry, is represented by an antiunitary operator; its Euclidean shadow is a suitable reflection symmetry of the Euclidean theory."
  active:
    - "Reflection positivity remains delicate in gauge-fixed theories, fermionic theories, theories with topological terms, finite-density systems, nonlocal effective actions, lattice discretizations, and curved-space generalizations."
---

## Summary

Reflection positivity is the Euclidean condition that remembers a very Lorentzian fact: the physical Hilbert space must have positive norm.

In a Euclidean path integral, choose a coordinate $\tau$ to play the role of Euclidean time and define the reflection

$$
\theta:(\tau,\mathbf x)\mapsto(-\tau,\mathbf x).
$$

For any functional $F$ of fields supported only in the positive half-space $\tau>0$, reflection positivity says schematically

$$
\langle (\theta F)F\rangle_E\ge 0.
$$

The symbol $\theta F$ is not just $F$ evaluated at $-\tau$. It includes the correct reflection action on field components, complex conjugation of coefficients, and possible spinor or tensor matrices. The inequality says that Euclidean correlation functions define a positive inner product on states created by insertions in the half-space $\tau>0$.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Euclidean reflection positivity map: operators in the positive time half-space are reflected, producing a positive inner product and, after reconstruction, a Hilbert space, positive Hamiltonian, and Lorentzian unitary theory.](/figures/symmetry-anomalies-topology/reflection-positivity-time-reflection.svg)

<figcaption>

Reflection positivity is the Euclidean replacement for Hilbert-space positivity. Operators inserted at $\tau>0$ create candidate states. Reflecting them through $\tau=0$ gives the bra. The inequality $\langle(\theta F)F\rangle_E\ge0$ lets one quotient null states and reconstruct a Hilbert space. A separate reflection invariance of the Euclidean action is what becomes Lorentzian time-reversal symmetry.

</figcaption>
</figure>

The crucial distinction is this:

$$
\text{reflection positivity}\neq\text{time-reversal symmetry}.
$$

Reflection positivity is a consistency condition needed to reconstruct a unitary Lorentzian theory from Euclidean data. Time-reversal symmetry is an additional physical symmetry, represented in Lorentzian signature by an antiunitary operator $\mathsf T$. A Euclidean theory can fail to be invariant under reflection even when its correlators are arranged so that some unitary Lorentzian theory exists, and a Lorentzian theory can be perfectly unitary without having time reversal as a symmetry.

## Prerequisites

Read [Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/time-reversal/), [Antiunitary Symmetries](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/antiunitary-symmetries/), and [CPT Theorem Perspective](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/cpt-theorem-perspective/) first. You should also know the path-integral Ward-identity viewpoint from [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/) and the background-field language from [Sources and Background Fields](/symmetry-anomalies-topology/background-fields-and-gauging/sources-and-background-fields/).

This page assumes the volume convention

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1)
$$

in Lorentzian signature. Euclidean time is written $\tau$. With the common continuation $t=-i\tau$, Lorentzian time evolution $e^{-iHt}$ becomes Euclidean time evolution $e^{-H\tau}$ for $\tau>0$.

## Core idea

A state in Lorentzian QFT can be created from the vacuum by acting with local operators in the past. Its norm is an expectation value of a bra times a ket. In Euclidean signature, “past” and “future” are replaced by the two half-spaces separated by $\tau=0$.

A Euclidean insertion $F$ supported at positive Euclidean time creates a candidate ket,

$$
|F\rangle.
$$

The corresponding bra is created by reflecting the insertion across $\tau=0$:

$$
\langle F|\quad\leftrightarrow\quad \theta F.
$$

Therefore the norm should be

$$
\langle F|F\rangle=\langle(\theta F)F\rangle_E.
$$

Reflection positivity demands that this norm be nonnegative for all $F$. After quotienting out the zero-norm states and completing the space, one gets the physical Hilbert space.

This turns a Euclidean correlation-function condition into the Lorentzian requirement

$$
\|\psi\|^2\ge0.
$$

That is the whole conceptual engine. The formal Osterwalder–Schrader reconstruction theorem adds the analytic, covariance, growth, and clustering assumptions needed to turn this engine into a precise theorem.

## Setup and conventions

Let $E_d$ denote Euclidean spacetime with coordinates

$$
x_E=(\tau,\mathbf x).
$$

The basic reflection is

$$
\theta x_E=(-\tau,\mathbf x).
$$

For a real scalar field,

$$
(\theta\phi)(\tau,\mathbf x)=\phi(-\tau,\mathbf x).
$$

For a complex scalar with charge conjugation not included,

$$
(\theta\phi)(\tau,\mathbf x)=\phi^*(-\tau,\mathbf x),
$$

when acting on the functional coefficients and the field configuration in the Euclidean measure. If the physical reflection includes an internal unitary transformation $R$, then one writes schematically

$$
(\theta_R\phi)_a(\tau,\mathbf x)=R_a{}^b\phi_b^*(-\tau,\mathbf x).
$$

For spinors and tensor fields, $\theta$ also acts on the spin or vector indices. For example, the component normal to the reflecting plane and the components tangent to the plane need not transform in the same way. This is exactly where sign errors like to breed in the plumbing.

:::note[Convention-sensitive source note]
The reflection operator used in Osterwalder–Schrader positivity is not a universal one-line formula for every field. It depends on the Euclidean continuation, the representation of the fields, and the chosen reflecting hyperplane. Scalar formulas are clean; spinor formulas require gamma-matrix and reflection-matrix conventions. The invariant statement is the positivity of the reflected two-sided Euclidean correlation functional.
:::

A general functional supported at positive Euclidean time has the form

$$
F=\sum_i c_i\mathcal O_i,
$$

where each $\mathcal O_i$ is a product or smeared product of fields with all insertions at $\tau>0$. Reflection acts anti-linearly:

$$
\theta F=\sum_i c_i^*\theta\mathcal O_i.
$$

Reflection positivity is

$$
\sum_{i,j}c_i^*c_j\langle(\theta\mathcal O_i)\mathcal O_j\rangle_E\ge0.
$$

Equivalently, the matrix

$$
M_{ij}=\langle(\theta\mathcal O_i)\mathcal O_j\rangle_E
$$

is positive semidefinite for every finite collection of positive-time insertions.

## The reflected inner product

The Euclidean path integral computes correlation functions

$$
\langle \mathcal O_1\cdots\mathcal O_n\rangle_E
=\frac{1}{Z}\int\mathcal D\Phi\,\mathcal O_1\cdots\mathcal O_n\,e^{-S_E[\Phi]}.
$$

If $F$ is supported at $\tau>0$, define

$$
(F,G)_E\equiv\langle(\theta F)G\rangle_E.
$$

Reflection positivity says

$$
(F,F)_E\ge0.
$$

This is not ordinary positivity of the Euclidean Boltzmann weight $e^{-S_E}$. The two ideas are related in simple bosonic theories, but they are not the same. A real positive measure can still fail reflection positivity if the kinetic operator or nonlocal couplings have the wrong spectral structure. Conversely, fermionic path integrals and gauge-fixed path integrals often do not have a naive positive measure over all variables, yet the gauge-invariant physical sector can still have the right positivity.

Once $(F,F)_E\ge0$ is available, the reconstructed Hilbert space is formed in three steps:

1. take the vector space of positive-time functionals $F$;
2. quotient by null functionals satisfying $(F,F)_E=0$;
3. complete the resulting pre-Hilbert space.

The zero-time surface $\tau=0$ becomes the quantization surface, and Euclidean time translations become a contraction semigroup,

$$
T(a):F(\tau,\mathbf x)\mapsto F(\tau+a,\mathbf x),
\qquad a>0.
$$

After reconstruction,

$$
T(a)=e^{-aH},
\qquad H\ge0.
$$

The positivity of the Hamiltonian is not an extra decorative property. It is encoded in the fact that Euclidean time translations move insertions deeper into the positive half-space and act as a semigroup with positive generator.

## Free scalar check

The free scalar field is the cleanest test case. In $d$ Euclidean dimensions, the massive scalar two-point function has the spectral representation

$$
C_E(\tau,\mathbf x)
=\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}\frac{1}{2E_{\mathbf p}}
\exp\left[-E_{\mathbf p}|\tau|+i\mathbf p\cdot\mathbf x\right],
$$

where

$$
E_{\mathbf p}=\sqrt{\mathbf p^2+m^2}.
$$

Take a positive-time one-particle functional

$$
F=\sum_j c_j\phi(\tau_j,\mathbf x_j),
\qquad \tau_j>0.
$$

Then

$$
\langle(\theta F)F\rangle_E
=\sum_{i,j}c_i^*c_j C_E(\tau_i+\tau_j,\mathbf x_j-\mathbf x_i).
$$

Using the spectral form,

$$
\langle(\theta F)F\rangle_E
=\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}\frac{1}{2E_{\mathbf p}}
\left|\sum_j c_j e^{-E_{\mathbf p}\tau_j+i\mathbf p\cdot\mathbf x_j}\right|^2\ge0.
$$

The absolute square is the whole story. The positive energy $E_{\mathbf p}>0$ in Lorentzian signature becomes exponential decay $e^{-E_{\mathbf p}\tau}$ in Euclidean signature, and that decay kernel makes the reflected inner product positive.

This also explains why reflection positivity is so sensitive to the pole structure of propagators. If a Euclidean propagator decomposes into a difference of positive kernels, has complex poles, or comes from higher-derivative ghosts, reflection positivity can fail even when the Euclidean expression looks perfectly rotationally invariant.

## Relation to Wightman positivity

In Lorentzian QFT, one formulation of positivity is that smeared fields create positive-norm states:

$$
\left\|\sum_i c_i\mathcal O_i|0\rangle\right\|^2\ge0.
$$

Equivalently,

$$
\sum_{i,j}c_i^*c_j\langle0|\mathcal O_i^\dagger\mathcal O_j|0\rangle\ge0.
$$

Reflection positivity is the Euclidean continuation of this statement. The reflected insertion $\theta\mathcal O_i$ plays the role of the adjoint operator in the bra.

This is why Euclidean correlation functions are not just ordinary functions on $\mathbb R^d$ with rotation symmetry. To be the Euclidean shadows of a unitary Lorentzian theory, they must satisfy a special positivity property tied to a choice of Euclidean time reflection.

Put differently:

$$
\text{Euclidean invariance alone does not imply Lorentzian unitarity.}
$$

Reflection positivity is the missing bridge.

## Time reversal as an extra symmetry

A Lorentzian time-reversal symmetry $\mathsf T$ is antiunitary and satisfies, for a time-independent Hamiltonian,

$$
\mathsf T H\mathsf T^{-1}=H.
$$

Because $\mathsf T$ is antiunitary,

$$
\mathsf T e^{-iHt}\mathsf T^{-1}=e^{+iHt}=e^{-iH(-t)}.
$$

This is why time reversal can reverse time without sending $H$ to $-H$.

In Euclidean language, Lorentzian time reversal is related to reflection across a Euclidean time slice. But there are two logically different questions:

$$
\begin{array}{ccl}
\text{Reflection positivity} &:& \langle(\theta F)F\rangle_E\ge0,\\[4pt]
\text{Time-reversal invariance} &:& S_E[\theta\Phi]=S_E[\Phi]\text{, with all backgrounds transformed.}
\end{array}
$$

The first is a positivity axiom. The second is a symmetry statement.

A theory can be unitary without being time-reversal invariant. Weak interactions violate time reversal in the appropriate sense, but that is not a failure of Hilbert-space positivity. Conversely, a Euclidean action can be formally invariant under a reflection operation while the theory fails reflection positivity because the kinetic operator has ghostlike spectral data.

## Background fields and reflected couplings

Symmetry statements always require transforming backgrounds. If a theory is coupled to a background magnetic field, time reversal sends

$$
\mathbf B\mapsto-\mathbf B,
\qquad
\mathbf E\mapsto\mathbf E.
$$

Therefore a fixed-background partition function should obey a relation of the form

$$
Z[\mathbf E,\mathbf B]=Z[\mathbf E,-\mathbf B]^*
$$

for a time-reversal-invariant system, not necessarily $Z[\mathbf E,\mathbf B]=Z[\mathbf E,\mathbf B]^*$ at the same background.

The same warning applies to curved backgrounds, spin structures, gauge fields, chemical potentials, theta angles, and boundary conditions. Reflection positivity is a statement about the full background-decorated Euclidean theory, not just a line in the Lagrangian with all external data frozen.

Chemical potential is a famous trap. A real Lorentzian chemical potential for a charge often appears as an imaginary Euclidean background gauge field. The resulting Euclidean weight can become complex and may fail reflection positivity in the naive form. This is one face of the finite-density sign problem.

## Topological terms and time reversal

Topological terms are where reflection and time reversal become especially unforgiving.

Consider a four-dimensional gauge theory with Lorentzian theta term

$$
S_\theta=\frac{\theta}{8\pi^2}\int\operatorname{tr}(F\wedge F),
$$

up to trace-normalization conventions. In Euclidean signature this typically contributes a phase

$$
e^{-S_E}\supset \exp(i\theta Q),
\qquad
Q\in\mathbb Z
$$

for suitably normalized instanton number $Q$.

Orientation reversal sends

$$
Q\mapsto -Q.
$$

Therefore time reversal requires

$$
\theta\equiv-\theta\pmod{2\pi},
$$

so the special values are

$$
\theta=0,\pi\pmod{2\pi}.
$$

At $\theta=0$, reflection invariance is straightforward. At $\theta=\pi$, the phase is also invariant because $e^{i\pi Q}=e^{-i\pi Q}$ for integer $Q$, but the theory can have subtle mixed anomalies, degenerate vacua, or symmetry-enforced boundary phenomena depending on the gauge group and matter content.

:::note[Convention-sensitive source note]
The numerical coefficient of $\int\operatorname{tr}(F\wedge F)$ depends on the trace convention and on whether the gauge field is written Hermitian or anti-Hermitian. The symmetry statement is convention-independent: an orientation-reversing or time-reversing operation flips the topological charge $Q$, so a periodic theta angle must obey $\theta\equiv-\theta$ for the operation to be a symmetry.
:::

## Fermions and reflection

For fermions, reflection positivity is not captured by replacing $\phi(\tau)$ with $\phi(-\tau)$. A Euclidean spinor reflection must also act on spinor indices. The details depend on Euclidean gamma-matrix conventions, but the structure is always the same:

$$
\theta\psi(\tau,\mathbf x)
=R\,\bar\psi(-\tau,\mathbf x)^T
$$

or an equivalent convention-dependent formula involving a reflection matrix $R$.

The important points are:

- the reflected field is the correct adjoint partner for building the bra;
- the reflection may depend on spin or Pin structure;
- fermionic signs enter because the functional algebra is graded;
- gauge-invariant fermion bilinears may have cleaner reflection properties than elementary Grassmann variables.

A useful sanity check is the free Dirac two-point function. The Euclidean propagator must reconstruct a positive-energy Lorentzian fermion theory with positive norms for physical one-particle states. If a regulator or lattice discretization breaks reflection positivity, the continuum limit must repair it or the candidate theory is not a standard unitary Lorentzian QFT.

## Gauge theories and ghosts

Gauge theories add another layer. In a covariantly gauge-fixed path integral, the elementary gauge field, ghost, and antighost variables live in an enlarged space with unphysical polarizations and negative-metric-looking ingredients. Reflection positivity for every gauge-fixed field correlator is too strong and generally false.

The physical requirement is reflection positivity for the reconstructed **gauge-invariant physical sector**, or equivalently positivity after imposing the BRST or Gauss-law constraints in a correct formulation.

This is why the following statements are compatible:

$$
\text{Faddeev–Popov ghosts violate naive positivity,}
$$

but

$$
\text{a healthy gauge theory can still have a positive physical Hilbert space.}
$$

Reflection positivity is most transparent in lattice gauge theory with a Wilson action and gauge-invariant observables. Gauge fixing is useful for perturbation theory, but it is often a bad place to look for positivity with the naked eye.

## Boundaries, defects, and reflection planes

Reflection positivity requires a reflection plane. If a theory has a boundary, interface, defect, or nontrivial background, the reflection must map the setup to itself or to a conjugate setup.

For example, if a boundary condition is placed at $\tau=0$, the reflected inner product involves a boundary Hilbert space. If a line defect crosses the reflection plane, the reflection may turn it into an adjoint line defect. If a defect lies entirely in $\tau>0$, its reflected partner lies in $\tau<0$.

This is one reason reflection positivity is a useful diagnostic for defect QFTs: it asks whether defect insertions really define states of nonnegative norm. In conformal field theory, this becomes tightly related to radial quantization and unitarity bounds. In topological phases, it connects to reflection, orientation reversal, and Pin-structure data.

## Common pitfalls

**Mistaking Wick rotation for a proof of unitarity.** Replacing $t$ by $-i\tau$ can make formulas converge, but convergence is not the same as Hilbert-space positivity. Reflection positivity is the extra condition that makes Euclidean data reconstruct a unitary Lorentzian theory.

**Confusing reflection positivity with time-reversal invariance.** Reflection positivity is a consistency condition. Time reversal is a symmetry. The former can hold without the latter.

**Checking positivity only for elementary fields.** In gauge-fixed theories, elementary variables may live in an enlarged unphysical space. The physical positivity question is about gauge-invariant or BRST-cohomological observables.

**Ignoring background transformations.** A theory in a fixed magnetic field is not time-reversal invariant at that fixed background. Time reversal relates the background to the reversed background.

**Treating topological terms as harmless total derivatives.** A total derivative can affect reflection and time reversal through global topological sectors. Theta terms are the standard example.

**Forgetting null states.** Reflection positivity gives a positive semidefinite form. Zero-norm states must be quotiented out before constructing the physical Hilbert space.

## Relations to other pages

[Antiunitary Symmetries](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/antiunitary-symmetries/) explains why Lorentzian time reversal must be antiunitary. This page explains how its Euclidean shadow is organized.

[Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/time-reversal/) gives the operator transformations for fields and backgrounds. Reflection positivity supplies the Euclidean Hilbert-space test behind those transformations.

[CPT Theorem Perspective](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/cpt-theorem-perspective/) uses antiunitarity and locality in Lorentzian signature. Reflection positivity is one Euclidean route to the same kind of structural control.

[Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/) is the right place to check which external sources must be transformed under reflection or time reversal.

[Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/) explains why theta angles and topological sectors are periodic and why orientation reversal can act nontrivially on them.

## Research status

The basic Osterwalder–Schrader idea is established: reflection-positive Euclidean correlation functions, together with the other reconstruction assumptions, define a positive-energy Lorentzian QFT.

Several frontiers remain subtle rather than mysterious. Reflection positivity in gauge theories requires care about gauge-invariant sectors and BRST cohomology. Reflection positivity with fermions requires spin and reflection data. Topological terms can make Euclidean weights complex and can force time reversal to act projectively or anomalously. Finite-density theories may fail naive reflection positivity, which is closely related to sign problems.

In modern QFT, reflection positivity also functions as a diagnostic in conformal bootstrap, lattice field theory, curved-space QFT, topological phases with reflection or time reversal, and rigorous reconstruction programs. The phrase is old-school; the tool is very much alive.

## Exercises

### Exercise 1: The free scalar positivity kernel

Let

$$
F=\sum_j c_j\phi(\tau_j,\mathbf x_j),
\qquad \tau_j>0,
$$

in a free massive Euclidean scalar theory. Use the spectral representation of $C_E$ to show that $\langle(\theta F)F\rangle_E\ge0$.

<details><summary><strong>Solution</strong></summary>

Reflection gives insertions at $-\tau_i$, so the Euclidean time separation between the reflected $i$ insertion and the $j$ insertion is $\tau_i+\tau_j$. Thus

$$
\langle(\theta F)F\rangle_E
=\sum_{i,j}c_i^*c_j C_E(\tau_i+\tau_j,\mathbf x_j-\mathbf x_i).
$$

Using

$$
C_E(\tau,\mathbf x)=\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}\frac{e^{-E_{\mathbf p}|\tau|+i\mathbf p\cdot\mathbf x}}{2E_{\mathbf p}},
$$

we get

$$
\langle(\theta F)F\rangle_E
=\int\frac{d^{d-1}\mathbf p}{(2\pi)^{d-1}}\frac{1}{2E_{\mathbf p}}
\left|\sum_j c_j e^{-E_{\mathbf p}\tau_j+i\mathbf p\cdot\mathbf x_j}\right|^2\ge0.
$$

The result is nonnegative because the integrand is a positive measure times an absolute square.

</details>

### Exercise 2: Why a negative spectral weight is fatal

Suppose a Euclidean two-point function has a spectral representation like the free scalar, but with one contribution carrying coefficient $-1$ instead of $+1$. Explain why reflection positivity fails.

<details><summary><strong>Solution</strong></summary>

Reflection positivity requires the reflected two-point matrix

$$
M_{ij}=C_E(\tau_i+\tau_j,\mathbf x_j-\mathbf x_i)
$$

to be positive semidefinite for all choices of points and coefficients. A negative spectral contribution gives a term of the form

$$
-\int d\mu(\lambda)\left|\sum_j c_j f_\lambda(\tau_j,\mathbf x_j)\right|^2.
$$

By choosing $F$ to overlap dominantly with that spectral component, one can make the norm negative. In Lorentzian language, this corresponds to a negative-norm or ghostlike state, not a physical positive Hilbert space.

</details>

### Exercise 3: Theta angle and reflection

Assume the Euclidean path integral contains the phase $e^{i\theta Q}$ with $Q\in\mathbb Z$, and reflection sends $Q\mapsto -Q$. For which $\theta$ is the phase reflection invariant?

<details><summary><strong>Solution</strong></summary>

Reflection invariance requires

$$
e^{i\theta Q}=e^{-i\theta Q}
$$

for all integers $Q$. Equivalently,

$$
e^{2i\theta Q}=1
$$

for all $Q$, so $e^{2i\theta}=1$. Thus

$$
\theta=0\text{ or }\pi\pmod{2\pi}.
$$

At $\theta=\pi$, invariance of the phase does not guarantee a unique trivial vacuum; anomalies or spontaneous symmetry breaking can still occur depending on the theory.

</details>

### Exercise 4: Positivity versus symmetry

Give an example, in words, of a property that is required for reflection positivity but not for time-reversal invariance, and a property required for time-reversal invariance but not for reflection positivity.

<details><summary><strong>Solution</strong></summary>

Reflection positivity requires the reflected Euclidean correlation matrix $\langle(\theta F_i)F_j\rangle_E$ to be positive semidefinite. This is a Hilbert-space reconstruction requirement, not a symmetry of the action.

Time-reversal invariance requires the dynamics, including all background fields and couplings, to be invariant under the time-reversal transformation. A theory in a fixed magnetic field, for instance, may be perfectly unitary and reflection positive in the correct sense, but it is not invariant under time reversal unless the magnetic field is also reversed.

</details>

## References

- K. Osterwalder and R. Schrader, “Axioms for Euclidean Green's Functions,” *Communications in Mathematical Physics* **31** (1973) and “Axioms for Euclidean Green's Functions II,” **42** (1975).
- J. Glimm and A. Jaffe, *Quantum Physics: A Functional Integral Point of View*.
- A. Jaffe and G. Ritter, “Quantum Field Theory on Curved Backgrounds. I. The Euclidean Functional Integral,” arXiv:hep-th/0609003.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, especially the discussion of symmetries, antiunitary transformations, and analytic structure.
- M. Srednicki, *Quantum Field Theory*, especially the sections on discrete symmetries, Euclidean continuation, and gauge theory.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the discussion of path integrals, Wick rotation, discrete symmetries, and unitarity.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for Euclidean functional integral and statistical-field-theory conventions.

## Version history

- 2026-06-17: Initial polished draft for the Discrete, Spacetime, and Antiunitary Symmetries chapter.
