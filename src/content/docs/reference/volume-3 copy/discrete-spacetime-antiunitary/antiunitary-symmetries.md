---
title: "Antiunitary Symmetries"
description: "Explains antiunitary symmetries in quantum theory and QFT, including Wigner's theorem, conjugate-linearity, time reversal, squares, Kramers degeneracy, fields, backgrounds, and Euclidean reflection."
sidebar:
  label: "Antiunitary Symmetries"
  order: 5
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. I §§2.2, 2.6; Srednicki §§23, 40; Coleman, Lectures on QFT ch. 22; standard Wigner theorem and time-reversal treatments."
topics:
  - antiunitary symmetry
  - Wigner theorem
  - time reversal
  - Kramers degeneracy
  - projective representation
  - Hilbert space
  - background fields
  - reflection positivity
canonicalTopics:
  - antiunitary-symmetry
  - wigner-theorem
  - kramers-degeneracy
  - antiunitary-square
  - time-reversal
  - reflection-positivity
researchStatus:
  established:
    - "Quantum symmetries preserving transition probabilities are represented by unitary or antiunitary transformations; antiunitary symmetries are conjugate-linear and complex-conjugate phases."
    - "Kramers degeneracy follows from an antiunitary symmetry commuting with the Hamiltonian and squaring to minus one on a state sector."
  active:
    - "Antiunitary symmetries remain central in modern QFT through time-reversal anomalies, Pin structures, reflection positivity, topological phases, lattice systems, and antiunitary duality actions."
---

## Summary

An antiunitary symmetry is a symmetry represented on Hilbert space by a conjugate-linear norm-preserving operator. If $\Theta$ is antiunitary, then

$$
\Theta(c_1|\psi_1\rangle+c_2|\psi_2\rangle)
=c_1^*\Theta|\psi_1\rangle+c_2^*\Theta|\psi_2\rangle,
$$

and

$$
\langle\Theta\psi|\Theta\phi\rangle
=\langle\phi|\psi\rangle.
$$

That single complex conjugation is the difference between antiunitary symmetries and ordinary unitary symmetries. It implies

$$
\Theta i\Theta^{-1}=-i,
$$

which is why antiunitary symmetries can reverse time evolution without sending positive energy to negative energy.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Antiunitary symmetry data map: a symmetry preserving transition probabilities may be unitary or antiunitary; antiunitary symmetries are written as U K after choosing a basis, square to U U star, reverse i, and can imply Kramers pairs.](/figures/symmetry-anomalies-topology/antiunitary-symmetry-data.svg)

<figcaption>

An antiunitary symmetry is locally “a unitary matrix times complex conjugation,” $\Theta=UK$, after choosing a basis. The basis-dependent symbol $K$ should not be confused with a physical operator by itself. The invariant data include conjugate-linearity, the transformed Hamiltonian, the square $\Theta^2$, and the induced action on operators, backgrounds, and sectors.

</figcaption>
</figure>

Antiunitary symmetry is not a decorative technicality attached to time reversal. It is one of the two possible ways a quantum symmetry can preserve transition probabilities. Wigner's theorem says that a symmetry of rays preserving probabilities is implemented by either a unitary or an antiunitary transformation. Continuous symmetries connected to the identity are unitary. Disconnected symmetries, especially time reversal and CPT, can be antiunitary.

## Prerequisites

Read [Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/time-reversal/) before this page. [CPT Theorem Perspective](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/cpt-theorem-perspective/) uses antiunitarity in a relativistic setting. The pages [Projective Representations Preview](/symmetry-anomalies-topology/ordinary-global-symmetries/projective-representations-preview/) and [Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/) supply the Hilbert-space background.

We write antiunitary operators as $\Theta$, $\mathsf T$, or $\mathsf A$ depending on context. The symbol $T$ is avoided for the operator when it could be confused with time-ordering, temperature, or the stress tensor.

## Core idea

A quantum state is a ray, not a vector. A physical symmetry must preserve transition probabilities,

$$
|\langle\psi|\phi\rangle|^2.
$$

Wigner's theorem says that such a symmetry is represented on Hilbert space by either a unitary or an antiunitary transformation. The unitary case is linear:

$$
U(c_1|\psi_1\rangle+c_2|\psi_2\rangle)
=c_1U|\psi_1\rangle+c_2U|\psi_2\rangle.
$$

The antiunitary case is conjugate-linear:

$$
\Theta(c_1|\psi_1\rangle+c_2|\psi_2\rangle)
=c_1^*\Theta|\psi_1\rangle+c_2^*\Theta|\psi_2\rangle.
$$

Both preserve probabilities. They differ in what they do to phases. Since interference is made of phases, antiunitarity is physically meaningful.

The practical slogan is

$$
\text{antiunitary symmetry preserves probabilities while complex-conjugating amplitudes.}
$$

That is why antiunitary symmetries are everywhere in questions involving time reversal, CPT, real structures, Kramers degeneracy, reflection positivity, and topological phases with time-reversal symmetry.

## Setup and conventions

An antiunitary operator $\Theta$ obeys

$$
\langle\Theta\psi|\Theta\phi\rangle=\langle\phi|\psi\rangle.
$$

Equivalently,

$$
\langle\Theta\psi|\Theta\phi\rangle
=\langle\psi|\phi\rangle^*.
$$

For an ordinary operator $\mathcal O$, conjugation by $\Theta$ is defined by

$$
\mathcal O\mapsto \Theta\mathcal O\Theta^{-1}.
$$

This operation preserves products in the same order:

$$
\Theta(\mathcal O_1\mathcal O_2)\Theta^{-1}
=(\Theta\mathcal O_1\Theta^{-1})
(\Theta\mathcal O_2\Theta^{-1}).
$$

It does not behave like Hermitian conjugation, which reverses order. The anti-linearity is in the numerical coefficients:

$$
\Theta(c_1\mathcal O_1+c_2\mathcal O_2)\Theta^{-1}
=c_1^*\Theta\mathcal O_1\Theta^{-1}
+c_2^*\Theta\mathcal O_2\Theta^{-1}.
$$

After choosing a basis, any antiunitary operator can be written as

$$
\Theta=UK,
$$

where $U$ is unitary and $K$ complex-conjugates components in that basis. This decomposition is useful but not invariant. Under a change of basis, $K$ and $U$ both change. The antiunitary operator $\Theta$ is the physical object.

:::note[Convention-sensitive source note]
Many texts write antiunitary transformations as $UK$, where $K$ is “complex conjugation.” This statement is always basis-relative. Treat $K$ as a bookkeeping device, not as a canonical symmetry. The invariant statements are conjugate-linearity, preservation of transition probabilities, and the square $\Theta^2$ on physical sectors.
:::

## Why time reversal is antiunitary

Time evolution is

$$
U(t)=e^{-iHt}.
$$

A time-reversal symmetry should satisfy

$$
\Theta U(t)\Theta^{-1}=U(-t).
$$

If $\Theta$ commutes with the Hamiltonian,

$$
\Theta H\Theta^{-1}=H,
$$

then antiunitarity gives

$$
\Theta e^{-iHt}\Theta^{-1}
=e^{+iHt}
=U(-t).
$$

A unitary operator commuting with $H$ would instead leave $e^{-iHt}$ unchanged. This is the clean reason that time reversal is antiunitary.

Notice what did not happen: the Hamiltonian did not transform as $H\mapsto -H$. Time reversal reverses motion, not energy.

## Antiunitary symmetries and Hamiltonians

An antiunitary operator $\Theta$ is a symmetry of a time-independent Hamiltonian if

$$
\Theta H\Theta^{-1}=H.
$$

Then energy eigenstates are mapped to energy eigenstates with the same energy:

$$
H|\psi\rangle=E|\psi\rangle
\quad\Longrightarrow\quad
H\Theta|\psi\rangle=E\Theta|\psi\rangle.
$$

This follows because $E$ is real. If one writes a formal eigenvalue equation with complex numbers, antiunitarity would complex-conjugate the eigenvalue. Hermiticity saves the usual energy-spectrum statement.

For a time-dependent Hamiltonian, the condition is instead

$$
\Theta H(t)\Theta^{-1}=H(-t),
$$

possibly also transforming external backgrounds. A magnetic field, for example, is time-reversal odd. A Hamiltonian in a fixed external magnetic field need not be time-reversal invariant unless the background is transformed too.

In generating-functional language, an antiunitary symmetry often means

$$
Z[B]=Z[\Theta B]^*,
$$

where $B$ denotes background fields and sources. In Euclidean signature the complex conjugation and reflection of the path-integral weight require special care.

## Squares and projective data

The square of an antiunitary symmetry is unitary:

$$
\Theta^2\quad\text{is unitary}.
$$

If $\Theta=UK$ in some basis, then

$$
\Theta^2=UKUK=UU^*.
$$

Thus the square is not $U^2$ but $UU^*$. This tiny distinction is responsible for many sign mistakes.

On a sector of Hilbert space, $\Theta^2$ can be

$$
\Theta^2=1,
\qquad
\Theta^2=-1,
\qquad
\Theta^2=(-1)^F,
$$

or another internal symmetry. For a single spin-$s$ quantum-mechanical multiplet with ordinary rotation symmetry,

$$
\Theta^2=(-1)^{2s}.
$$

For fermionic many-body and QFT systems, the statement is often organized as a relation involving fermion parity,

$$
(-1)^F.
$$

The square of an antiunitary symmetry is part of the symmetry data. Two theories can have the same abstract time-reversal label but different $\Theta^2$ on local operators, line operators, or Hilbert-space sectors. In modern language this difference can be tied to global form, anomalies, Pin structures, or symmetry-protected phases.

## Kramers degeneracy

Kramers degeneracy is the basic payoff of antiunitarity.

Suppose

$$
\Theta H\Theta^{-1}=H,
\qquad
\Theta^2=-1
$$

on a Hilbert-space sector. If $|\psi\rangle$ is an energy eigenstate, then $\Theta|\psi\rangle$ has the same energy. They cannot be proportional. If they were,

$$
\Theta|\psi\rangle=\lambda|\psi\rangle,
$$

then applying $\Theta$ again would give

$$
\Theta^2|\psi\rangle
=\lambda^*\Theta|\psi\rangle
=|\lambda|^2|\psi\rangle,
$$

contradicting $\Theta^2|\psi\rangle=-|\psi\rangle$.

Therefore every energy level in that sector is at least twofold degenerate.

The key assumptions are all necessary:

| Assumption | Why it matters |
|---|---|
| $\Theta$ antiunitary | Gives the conjugation in the square and protects the orthogonal partner. |
| $\Theta H\Theta^{-1}=H$ | Ensures $\Theta|\psi\rangle$ has the same energy. |
| $\Theta^2=-1$ on the sector | Forbids $\Theta|\psi\rangle$ from being proportional to $|\psi\rangle$. |
| No symmetry-breaking background | A fixed time-reversal-odd background can remove the degeneracy. |

In QFT, Kramers degeneracy can apply to finite-volume Hilbert spaces, boundary states, defect Hilbert spaces, or charged sectors, depending on how the antiunitary symmetry is realized.

## Fields and local operators

For a local operator multiplet $\mathcal O_a(x)$, an antiunitary symmetry acts as

$$
\Theta\mathcal O_a(t,\mathbf x)\Theta^{-1}
=R_a{}^b\mathcal O_b(\tau t,\rho\mathbf x),
$$

where $\tau=\pm1$ and $\rho$ may include a spatial reflection or rotation. The antiunitarity is not visible in the spacetime arguments; it is visible in coefficients and matrix elements.

For example, if

$$
\Theta\mathcal O\Theta^{-1}=\eta_\mathcal O\mathcal O,
$$

then

$$
\Theta(i\mathcal O)\Theta^{-1}
=-i\eta_\mathcal O\mathcal O.
$$

So $i\mathcal O$ has the opposite antiunitary parity from $\mathcal O$. This is a common trap in tables of fermion bilinears and topological terms.

For a conserved current, time reversal typically acts as

$$
j^0(t,\mathbf x)\mapsto j^0(-t,\mathbf x),
\qquad
j^i(t,\mathbf x)\mapsto -j^i(-t,\mathbf x).
$$

The charge

$$
Q=\int d^3\mathbf x\,j^0(t,\mathbf x)
$$

may be even or odd depending on whether the antiunitary symmetry also conjugates the internal charge. Time reversal itself leaves electric charge unchanged. CPT changes electric charge because it includes charge conjugation.

## Antiunitary symmetries are not generated by ordinary charges

A continuous internal symmetry connected to the identity has unitary transformations

$$
U(\alpha)=e^{i\alpha Q}
$$

with a Hermitian charge $Q$. Antiunitary symmetries are disconnected from the identity component of the symmetry group. There is no continuous path of antiunitary transformations starting at the identity, because the identity is linear while antiunitary maps are conjugate-linear.

This is why antiunitary symmetries do not usually have Noether currents. Time reversal is a symmetry, but there is no local Noether current whose integral generates a continuous time-reversal rotation. One studies it through its action on operators, states, correlation functions, backgrounds, and defects.

There can still be conserved quantities associated with spacetime symmetries that appear near time reversal. For example, time translations are unitary and generated by the Hamiltonian. Time reversal is the disconnected operation that sends $t\to -t$ and conjugates $i$.

## Background fields and response terms

Antiunitary symmetries must act on background fields and couplings. A few useful examples:

| Object | Typical time-reversal behavior |
|---|---|
| Electric field $\mathbf E$ | even |
| Magnetic field $\mathbf B$ | odd |
| Charge density $j^0$ | even |
| Current $\mathbf j$ | odd |
| Chemical potential for charge | even |
| Angular velocity | odd |
| Theta angle in Yang–Mills | $\theta\mapsto -\theta$ under $T$ |
| Chern–Simons level in three dimensions | changes sign under orientation-reversing or time-reversal operations |

A theory with action $S[B]$ in background fields may satisfy an antiunitary symmetry condition of the form

$$
e^{iS[B]}\mapsto e^{-iS[\Theta B]}.
$$

Equivalently,

$$
S[B]\mapsto -S[\Theta B]
$$

inside the exponent, modulo $2\pi$. In Euclidean signature this is often rewritten as a reflection property of the Euclidean functional integral.

This is where many anomaly statements begin. If no local counterterm can make the background-field partition function transform consistently under an antiunitary symmetry, the symmetry has an anomaly.

## Euclidean reflection and reflection positivity

Antiunitary symmetries in Lorentzian signature are closely related to reflections in Euclidean signature. The basic Wick-rotation intuition is

$$
t=-i\tau,
$$

so reversing Lorentzian time becomes reflecting Euclidean time,

$$
\tau\mapsto -\tau,
$$

together with complex conjugation of the Euclidean weight.

Reflection positivity is the Euclidean condition that lets one reconstruct a Lorentzian Hilbert space with positive norm. Very schematically, if $\mathcal F$ is built from fields supported at positive Euclidean time, reflection positivity demands

$$
\langle \Theta_E\mathcal F\,\mathcal F\rangle_E\ge 0,
$$

where $\Theta_E$ reflects Euclidean time and conjugates fields appropriately.

Do not overread this formula. The precise definition depends on fields, spin, gauge redundancy, boundary conditions, and Osterwalder–Schrader conventions. The conceptual bridge is stable: **antiunitarity in Lorentzian Hilbert space becomes reflection plus conjugation in Euclidean correlation functions**.

:::note[Convention-sensitive source note]
Wick rotation changes the bookkeeping of antiunitary symmetries. A Lorentzian factor of $i$ may become part of the Euclidean action, a theta term may remain imaginary in Euclidean signature, and spinor reality conditions may not survive unchanged. For antiunitary symmetries, never translate by only replacing $t$ with $-i\tau$; translate the operator action, conjugation, and background fields together.
:::

## Antiunitary symmetries in QFT examples

### Time reversal

Time reversal is the canonical antiunitary symmetry. It reverses momenta, angular momenta, spin, currents, and magnetic fields, while preserving energy. The square of time reversal can be $1$, $-1$, $(-1)^F$, or an internal symmetry depending on the system.

### CPT

CPT is antiunitary because it contains time reversal. In local relativistic QFT, CPT is guaranteed under standard assumptions even when the separate $C$, $P$, and $T$ operations are not symmetries.

### Particle-hole and charge-conjugation-like operations

In condensed matter and nonrelativistic systems, one often meets antiunitary particle-hole symmetries. These are not always the same as relativistic charge conjugation. Some act on single-particle Hamiltonians as

$$
\mathcal C H(\mathbf k)\mathcal C^{-1}=-H(-\mathbf k),
$$

where $\mathcal C$ may be antiunitary in the single-particle Hilbert space. The minus sign reflects the particle-hole grading of the effective description, not an ordinary symmetry commuting with the many-body Hamiltonian in the same way as time reversal.

### CP times time reversal in chiral theories

In chiral theories, $C$ or $P$ may not be separately available. Antiunitary combinations involving charge conjugation, orientation reversal, and time reversal can still be meaningful. The right object is whatever acts consistently on the full operator algebra and background fields.

## Common pitfalls

**Mistake 1: Treating complex conjugation as basis-independent.**

Writing $\Theta=UK$ is useful only after choosing a basis. The physical antiunitary operator is $\Theta$, not $K$ alone.

**Mistake 2: Forgetting that antiunitary conjugation preserves operator order.**

$\Theta(\mathcal O_1\mathcal O_2)\Theta^{-1}$ keeps the product order. Hermitian conjugation reverses order; antiunitary symmetry conjugation does not.

**Mistake 3: Squaring $UK$ as if it were $U^2$.**

The square is $UU^*$, not $U^2$.

**Mistake 4: Looking for a Noether current for time reversal.**

Antiunitary symmetries are disconnected symmetries. They constrain physics, but they are not generated by continuous Hermitian charges.

**Mistake 5: Ignoring background fields.**

A system in a fixed magnetic field is not time-reversal invariant unless the magnetic field is transformed. Symmetry of the theory with backgrounds is a statement about $Z[B]$ and $Z[\Theta B]$, not just about one chosen background.

## Relations to other pages

[Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/time-reversal/) is the main physical example. [CPT Theorem Perspective](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/cpt-theorem-perspective/) explains the relativistic structural theorem. [Projective Representations Preview](/symmetry-anomalies-topology/ordinary-global-symmetries/projective-representations-preview/) explains why phases and central extensions matter. Later pages on [Reflection Positivity and Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/reflection-positivity-and-time-reversal/) and [Spin Structures and Fermion Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/spin-structures-and-fermion-parity/) refine the Euclidean and fermionic parts of the story.

The anomaly chapters will use antiunitary background transformations to state time-reversal and parity anomalies. The matter and topology chapters use the same language for Kramers degeneracy, topological insulators, and symmetry-protected phases.

## Research status

The Hilbert-space theory of antiunitary symmetries is established. Wigner's theorem, time reversal, and Kramers degeneracy are standard.

The active frontier lies in global and field-theoretic refinements: antiunitary symmetries with boundaries and defects, Pin$^+$ versus Pin$^-$ structures, mixed anomalies involving time reversal, non-invertible or duality-twisted antiunitary actions, reflection positivity in gauge theories, and the classification of fermionic symmetry-protected phases.

## Exercises

### Exercise 1: Canonical commutators and antiunitarity

Let $\Theta$ be antiunitary and suppose

$$
\Theta X\Theta^{-1}=X,
\qquad
\Theta P\Theta^{-1}=-P.
$$

Show that this is compatible with $[X,P]=i$.

<details><summary><strong>Solution</strong></summary>

Acting with $\Theta$ on the commutator gives

$$
\Theta[X,P]\Theta^{-1}
=\Theta i\Theta^{-1}
=-i.
$$

On the other hand,

$$
[\Theta X\Theta^{-1},\Theta P\Theta^{-1}]
=[X,-P]
=-[X,P]
=-i.
$$

The two answers agree. If $\Theta$ were unitary, the left-hand side would have given $+i$, producing a contradiction.

</details>

### Exercise 2: Squaring an antiunitary operator

Let $\Theta=UK$, where $U$ is unitary and $K$ is complex conjugation in a chosen basis. Show that

$$
\Theta^2=UU^*.
$$

<details><summary><strong>Solution</strong></summary>

Using $KUK=U^*$, we find

$$
\Theta^2=(UK)(UK)=U(KU K)=UU^*.
$$

This is not generally $U^2$. The star is basis-dependent in notation, but the final operator $\Theta^2$ is invariantly defined.

</details>

### Exercise 3: Kramers degeneracy

Suppose $\Theta H\Theta^{-1}=H$ and $\Theta^2=-1$. Show that no nonzero energy eigenstate can be invariant under $\Theta$ up to a phase.

<details><summary><strong>Solution</strong></summary>

Assume $\Theta|\psi\rangle=\lambda|\psi\rangle$ for some complex $\lambda$. Applying $\Theta$ again gives

$$
\Theta^2|\psi\rangle
=\Theta(\lambda|\psi\rangle)
=\lambda^*\Theta|\psi\rangle
=|\lambda|^2|\psi\rangle.
$$

But $\Theta^2=-1$ implies

$$
\Theta^2|\psi\rangle=-|\psi\rangle.
$$

This would require $|\lambda|^2=-1$, impossible. Therefore $|\psi\rangle$ and $\Theta|\psi\rangle$ are linearly independent eigenstates with the same energy.

</details>

## References

- E. P. Wigner, foundational work on symmetries and antiunitary transformations in quantum mechanics.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, especially Wigner's theorem, projective representations, and inversions.
- Mark Srednicki, *Quantum Field Theory*, sections on discrete symmetries and spinor transformations.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chapter on CPT and Fermi fields.
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, for theorem-level antiunitary/CPT context.
- Standard treatments of reflection positivity and Osterwalder–Schrader reconstruction for Euclidean QFT.

## Version history

- 2026-06-17: First polished draft. Added Wigner theorem framing, antiunitary algebra, Hamiltonian and background-field criteria, Kramers degeneracy, Euclidean reflection bridge, and exercises.
