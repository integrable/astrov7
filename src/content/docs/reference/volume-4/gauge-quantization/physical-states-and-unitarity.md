---
title: "Physical States and Unitarity"
description: "Explains how BRST cohomology removes unphysical gauge modes and why the physical S-matrix remains unitary in covariant gauges."
sidebar:
  label: "Physical States and Unitarity"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §74; Weinberg Vol. II §§15.7–15.8; Coleman lectures on gauge-field Feynman rules; Schwartz Chs. 25–30; standard Gupta–Bleuler and Kugo–Ojima perspective."
topics:
  - BRST cohomology
  - physical Hilbert space
  - unitarity
  - gauge fixing
  - ghost cancellations
  - Gupta–Bleuler condition
canonicalTopics:
  - physical-states-in-gauge-theory
  - brst-cohomology
  - gauge-theory-unitarity
  - unphysical-polarizations
  - ghost-cancellations
  - gupta-bleuler-quantization
researchStatus:
  established:
    - "In perturbative anomaly-free gauge theories, BRST cohomology gives the physical state space and the S-matrix descends to a unitary operator on that space."
  active:
    - "Nonperturbative physical Hilbert spaces, confinement, Gribov copies, boundary charges, and gauge theories with anomalies require refinements beyond this perturbative cohomological argument."
---

## Summary

Covariant gauge fixing is deliberately extravagant. It keeps Lorentz covariance manifest by integrating over field components that are not physical particles: time-like and longitudinal gauge-field modes, ghosts, antighosts, and sometimes auxiliary fields. This is wonderful for Feynman rules and dangerous for interpretation.

The cure is not to pretend that every state in the gauge-fixed state space is physical. The physical state space is selected by the BRST charge $Q_{\rm B}$:

$$
Q_{\rm B}^2=0,
\qquad
Q_{\rm B}|\Psi\rangle=0,
$$

with the equivalence relation

$$
|\Psi\rangle\sim |\Psi\rangle+Q_{\rm B}|\Lambda\rangle.
$$

Thus the physical Hilbert space is the ghost-number-zero BRST cohomology,

$$
\boxed{
\mathcal H_{\rm phys}
=
H^0(Q_{\rm B})
=
\frac{\ker Q_{\rm B}\text{ at ghost number }0}
{\operatorname{im}Q_{\rm B}\text{ from ghost number }-1}.
}
$$

This quotient does two jobs at once. It imposes the gauge constraint and removes the null or negative-norm baggage introduced by covariant quantization. The unphysical modes organize into BRST doublets or quartets, while transverse gauge bosons and gauge-invariant matter states survive in cohomology.

<figure class="doc-figure" style="--figure-width: 43rem;">

![BRST-closed states modulo BRST-exact states define the physical Hilbert space, and the S-matrix descends to that quotient.](/figures/gauge-theories-standard-model/physical-state-cohomology.svg)

<figcaption>

The gauge-fixed state space is larger than the physical state space. BRST-closed states obey $Q_{\rm B}|\Psi\rangle=0$, BRST-exact states are null representatives $Q_{\rm B}|\Lambda\rangle$, and physical states are cohomology classes. BRST invariance, $[Q_{\rm B},S]=0$, makes the S-matrix act on the quotient rather than on arbitrary gauge-fixed representatives.

</figcaption>
</figure>

The unitarity statement is then precise:

$$
\boxed{
S_{\rm phys}^\dagger S_{\rm phys}=1
\quad\text{on}\quad
\mathcal H_{\rm phys},
}
$$

provided BRST symmetry is not anomalous and the asymptotic states are appropriate for the theory. In QED this statement must be paired with the usual infrared care for charged states. In confining QCD it is not a claim that isolated gluons are physical asymptotic particles; it is the perturbative gauge-theory statement that unphysical polarizations and ghosts cancel from gauge-invariant amplitudes.

## Prerequisites

You should have read [Ghosts and Gauge-Fixed Action](/gauge-theories-standard-model/gauge-quantization/ghosts-and-gauge-fixed-action/) and [BRST Symmetry in Gauge Theory](/gauge-theories-standard-model/gauge-quantization/brst-symmetry-in-gauge-theory/). We will use the auxiliary-field covariant gauge-fixed Yang–Mills Lagrangian

$$
\mathcal L
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
+B^a\partial^\mu A_\mu^a
+\frac{\xi}{2}B^aB^a
-\bar c^a\partial^\mu D_\mu^{ab}c^b
+\mathcal L_{\rm matter},
$$

and the BRST transformations

$$
\begin{aligned}
sA_\mu^a&=(D_\mu c)^a,\\
sc^a&=\frac{g}{2}f^{abc}c^b c^c,\\
s\bar c^a&=B^a,\\
sB^a&=0.
\end{aligned}
$$

The corresponding conserved charge is denoted $Q_{\rm B}$. On operators, schematically,

$$
s\mathcal O=i[Q_{\rm B},\mathcal O\}_{\rm gr},
$$

where $[\,,\}_{\rm gr}$ is the graded commutator. The precise factor of $i$ is conventional; the structural facts are nilpotence, ghost-number grading, and conservation.

## Core idea

The gauge-fixed theory has too many states, but the BRST complex knows which states are fake.

This is the same logic as a quotient space in linear algebra. If a vector space contains redundant directions, one can either choose coordinates that avoid them or keep them and quotient at the end. Covariant gauge theory chooses the second strategy. It keeps all four components of $A_\mu^a$ and adds ghosts so that Lorentz covariance and locality are manifest. Then BRST cohomology performs the quotient.

The slogan is

$$
\text{physical states}
=
\frac{\text{BRST-closed states}}{\text{BRST-exact states}}.
$$

A BRST-closed state satisfies the quantum gauge constraint. A BRST-exact state is pure gauge in the enlarged state space. Exact states do not contribute to physical matrix elements, so they must be identified with zero.

This is why ghost fields can appear in loops but not as external particles. They are variables in a representation of the quotient, not particles in the quotient itself.

## Why the gauge-fixed state space is too large

A massless spin-one particle has two physical helicities. A covariant vector field $A_\mu$ has four components. Gauge invariance removes the mismatch, but gauge fixing reintroduces a larger intermediate space so that the propagator exists.

In Feynman gauge, for example, the gauge-boson propagator has the simple numerator $\eta_{\mu\nu}$:

$$
D_{\mu\nu}^{ab}(k)
=
\frac{-i\delta^{ab}\eta_{\mu\nu}}{k^2+i\epsilon}.
$$

This numerator is computationally convenient, but it does not project onto the two transverse physical polarizations. It includes time-like and longitudinal directions. If these directions were allowed as independent physical states, probabilities would not have a positive interpretation.

There are two ways to say the problem.

Classically, gauge fields have constraints. Not every component of $A_\mu^a$ is an independent degree of freedom.

Quantum mechanically, a manifestly covariant gauge-fixed state space has an indefinite or enlarged inner product structure. The physical Hilbert space must be a subquotient, not the whole auxiliary space.

BRST symmetry is the efficient modern language for that subquotient.

## The BRST charge

A continuous symmetry has a conserved charge. BRST symmetry is odd, but the same idea applies. The gauge-fixed action is invariant under $s$, so there is a conserved BRST current $j_{\rm B}^\mu$ and a conserved charge

$$
Q_{\rm B}=\int d^3\mathbf x\,j_{\rm B}^0.
$$

The defining properties are

$$
Q_{\rm B}^2=0,
\qquad
[Q_{\rm B},H]=0,
$$

where $H$ is the gauge-fixed Hamiltonian. In scattering language this implies

$$
[Q_{\rm B},S]=0.
$$

Nilpotence is the quantum version of the statement that gauge transformations have already been quotiented once; applying the BRST constraint twice gives no new constraint.

The physical-state condition is

$$
\boxed{
Q_{\rm B}|\Psi\rangle=0.
}
$$

This condition alone is not quite enough, because it still includes states of the form

$$
|\Psi\rangle=Q_{\rm B}|\Lambda\rangle.
$$

Such states are automatically closed:

$$
Q_{\rm B}|\Psi\rangle
=
Q_{\rm B}^2|\Lambda\rangle
=0.
$$

But they are pure-gauge representatives. They must be quotiented out.

## Exact states decouple

Assume $Q_{\rm B}$ is self-adjoint with respect to the BRST-compatible inner product. If $|\Phi\rangle$ is BRST closed and $|\Psi\rangle=Q_{\rm B}|\Lambda\rangle$ is BRST exact, then

$$
\langle\Phi|\Psi\rangle
=
\langle\Phi|Q_{\rm B}|\Lambda\rangle
=
\langle Q_{\rm B}\Phi|\Lambda\rangle
=0.
$$

So exact states have zero overlap with every closed state. In particular, exact states have zero norm when paired with themselves:

$$
\langle Q_{\rm B}\Lambda|Q_{\rm B}\Lambda\rangle
=
\langle\Lambda|Q_{\rm B}^2|\Lambda\rangle
=0.
$$

This is the linear-algebra heart of the construction. A physical state is not a single vector in the gauge-fixed space; it is an equivalence class

$$
[\Psi]=\{|\Psi\rangle+Q_{\rm B}|\Lambda\rangle\}.
$$

Physical matrix elements cannot depend on the representative chosen inside the class.

For a BRST-closed observable $\mathcal O$, meaning

$$
[Q_{\rm B},\mathcal O\}_{\rm gr}=0,
$$

we have

$$
\langle\Phi|\mathcal O\,Q_{\rm B}|\Lambda\rangle
=
\langle\Phi|Q_{\rm B}\mathcal O|\Lambda\rangle
=0
$$

when $|\Phi\rangle$ is also BRST closed. Thus exact changes of the external state are invisible to physical observables.

## The quartet mechanism

A useful theorem in BRST cohomology is that BRST doublets do not contribute to cohomology. If two variables satisfy

$$
sX=Y,
\qquad
sY=0,
$$

then the pair $(X,Y)$ is cohomologically trivial. Any dependence on the pair is either not closed or is exact, up to harmless constants.

In gauge theory the unphysical sector is built from such pairs. At the level of states, the time-like and longitudinal gauge modes combine with ghost and antighost excitations into BRST quartets. The detailed oscillator construction depends on the chosen gauge and normalization, but the conclusion is robust:

$$
\text{BRST quartets do not survive in }H^0(Q_{\rm B}).
$$

The physical one-particle gauge-boson states are represented by transverse polarizations. In a weakly coupled non-Abelian theory, one may use these transverse gluon states as perturbative external states. In QCD as a real infrared theory, confinement replaces them by color-singlet hadronic states, but the perturbative cancellation of unphysical modes remains essential inside short-distance calculations.

The quartet mechanism is also why ghosts are allowed internally but forbidden externally. Internal ghost lines are part of the determinant representation. External ghost states would live in the auxiliary complex, not in ghost-number-zero physical cohomology.

## The S-matrix descends to cohomology

Now suppose the gauge-fixed theory has a BRST-invariant S-matrix,

$$
[Q_{\rm B},S]=0.
$$

If $|\Psi\rangle$ is closed, then $S|\Psi\rangle$ is closed:

$$
Q_{\rm B}S|\Psi\rangle
=SQ_{\rm B}|\Psi\rangle
=0.
$$

If $|\Psi\rangle$ is changed by an exact state, then

$$
S(|\Psi\rangle+Q_{\rm B}|\Lambda\rangle)
=S|\Psi\rangle+Q_{\rm B}S|\Lambda\rangle.
$$

The change is still exact. Therefore $S$ acts on equivalence classes:

$$
S:[\Psi]\mapsto[S\Psi].
$$

This is what it means for the S-matrix to descend to BRST cohomology. The physical amplitudes are not matrix elements between arbitrary gauge-fixed states. They are matrix elements between cohomology classes.

## Unitarity on the physical sector

The full gauge-fixed formalism is not a positive Hilbert-space theory in the naive sense. It is an auxiliary construction with an indefinite metric or with ghost variables in the path integral. The claim of unitarity is therefore not

$$
\text{all auxiliary states have positive probability}.
$$

That statement is false. The correct claim is

$$
\text{the induced S-matrix on }H^0(Q_{\rm B})\text{ is unitary}.
$$

One way to see the logic is:

1. The gauge-fixed action is BRST invariant.
2. BRST invariance gives a conserved nilpotent charge $Q_{\rm B}$.
3. The S-matrix commutes with $Q_{\rm B}$.
4. Exact states decouple from closed states.
5. The S-matrix is therefore well-defined on cohomology.
6. The negative-norm and null parts of the auxiliary space are absent after the cohomological quotient.

Equivalently, in perturbative diagrammatics, the optical theorem for physical amplitudes can be checked using covariant propagators. Unphysical gauge polarizations and ghost contributions cancel in the sum over intermediate states. The cancellation is not usually visible diagram by diagram; it appears in complete gauge-invariant sets of diagrams and is enforced by Ward or Slavnov–Taylor identities.

For external physical states $i$ and $f$, the optical theorem has the physical form

$$
2\operatorname{Im}\mathcal M_{i\to f}
=
\sum_{n\in\mathcal H_{\rm phys}}
\mathcal M_{i\to n}\mathcal M^*_{f\to n},
$$

with the usual phase-space integrations understood. In a covariant calculation, intermediate algebra may contain longitudinal gauge bosons and ghosts. The theorem says that the final physical cut can be organized in terms of physical states.

## Abelian warm-up: Gupta–Bleuler

In free QED, the older Gupta–Bleuler condition is a useful warm-up. One does not impose the Lorenz condition $\partial_\mu A^\mu=0$ as a strong operator equation, because that is incompatible with covariant quantization. Instead one imposes its positive-frequency part on physical states:

$$
(\partial_\mu A^\mu)^{(+)}|\Psi\rangle=0.
$$

This removes the scalar-longitudinal unphysical sector while preserving Lorentz covariance. States differing by null photon states are identified.

BRST quantization is the non-Abelian, path-integral-friendly, cohomological generalization of this idea. In Abelian theory, ghosts decouple in Lorenz gauge, so one can often avoid mentioning them. In non-Abelian theory, ghosts interact and the BRST formulation becomes the cleanest way to state the physical-state condition.

## What is actually checked in calculations?

In practical perturbation theory, one rarely constructs $Q_{\rm B}$ explicitly. Instead one checks its consequences.

For a tree-level amplitude with external gauge bosons, replacing a physical polarization vector by a pure-gauge momentum should give zero after summing all contributing diagrams:

$$
\varepsilon_\mu(k)\to k_\mu
\quad\Longrightarrow\quad
\mathcal M=0
$$

for appropriate on-shell external states and conserved sources. In non-Abelian theory this statement is generalized by Slavnov–Taylor identities, where ghost Green functions can appear in intermediate identities.

For loop calculations, one checks that gauge-parameter dependence cancels from physical quantities. A single self-energy graph, vertex graph, or box graph may depend on $\xi$. A properly defined physical observable must not.

For renormalization, one checks that counterterms can be chosen in a BRST-consistent way. If a regulator or counterterm scheme breaks BRST in a way that cannot be repaired, the quantum theory is inconsistent. Gauge anomalies are exactly of this dangerous kind.

## Anomalies and the failure mode

BRST symmetry can fail quantum mechanically. If the functional measure and regularization cannot preserve BRST symmetry, then the would-be conservation law becomes anomalous:

$$
Q_{\rm B}^2\neq0
\quad\text{or}\quad
[Q_{\rm B},S]\neq0
$$

in the quantum theory.

This is not a small cosmetic problem. Without nilpotence and conservation, the cohomological definition of physical states is not stable under time evolution. Negative-norm or gauge-dependent states can leak into physical amplitudes. This is why gauge anomalies are fatal for gauge symmetries.

The Standard Model avoids this failure because its chiral fermion representations satisfy anomaly-cancellation conditions. That story belongs later in the Anomalies and Consistency chapter, but the reason it matters is already visible here: anomaly cancellation is a unitarity condition for a chiral gauge theory, not merely an aesthetic pattern in hypercharges.

## Infrared and confinement caveats

The BRST argument is a statement about gauge redundancy and perturbative consistency. It is not a substitute for the infrared physics of a particular theory.

In QED, charged particles are accompanied by long-range electromagnetic fields and soft photons. The naive Fock-space S-matrix between bare charged states has infrared divergences. Physical inclusive rates or dressed asymptotic states are needed.

In QCD, colored gluons and quarks are not isolated asymptotic states in the real infrared theory. Perturbative quark and gluon amplitudes are still essential short-distance ingredients, but physical scattering states are color singlets.

Neither caveat weakens the BRST lesson. It only tells us that

$$
\text{BRST cohomology removes gauge redundancy,}
$$

while

$$
\text{the actual asymptotic particle spectrum is a dynamical question.}
$$

## Common pitfalls

**Pitfall 1: Saying ghosts restore unitarity because they are negative-probability particles.**

Ghosts are not particles. They are auxiliary Grassmann fields representing the Faddeev–Popov determinant. Their loops cancel unphysical contributions in covariant calculations, but they are not external states with negative probabilities.

**Pitfall 2: Treating $Q_{\rm B}|\Psi\rangle=0$ as the whole physical-state condition.**

Closed states still include exact states. The physical space is cohomology, not merely the kernel of $Q_{\rm B}$.

**Pitfall 3: Expecting every diagram to be unitary by itself.**

Gauge cancellations occur among complete sets of diagrams and after including ghosts. A single covariant-gauge diagram is usually not a physical object.

**Pitfall 4: Confusing gauge fixing with choosing a physical frame.**

Gauge fixing chooses representatives in redundant field space. It does not pick a physical medium, observer, or preferred Lorentz frame.

**Pitfall 5: Ignoring anomalies.**

BRST cohomology is powerful only if BRST symmetry survives quantization. A gauge anomaly breaks the mechanism that keeps the physical subspace stable.

## Relations to other pages

This page is the physical-state continuation of [BRST Symmetry in Gauge Theory](/gauge-theories-standard-model/gauge-quantization/brst-symmetry-in-gauge-theory/). It explains why the cohomology introduced there is not abstract algebra for its own sake; it is the physical Hilbert space of a gauge-fixed theory.

The next page, [Covariant Gauges](/gauge-theories-standard-model/gauge-quantization/covariant-gauges/), explains how the gauge parameter $\xi$ labels a family of equivalent gauge-fixed descriptions. Gauge-parameter independence of physical quantities is another expression of the same BRST logic.

Later pages on gauge renormalization use this material to explain Slavnov–Taylor identities, gauge-invariant counterterms, and asymptotic freedom. The Standard Model anomaly pages will explain why chiral gauge theories are consistent only when BRST-breaking gauge anomalies cancel.

## Research status

The perturbative BRST construction of the physical state space and the unitarity of anomaly-free covariant gauges are established parts of quantum gauge theory.

The global and nonperturbative picture is subtler. Gribov copies obstruct a simple global gauge slice. In confining theories, the physical color-singlet Hilbert space is not obtained by simply listing perturbative gluon states. Boundaries and asymptotic regions can turn would-be gauge transformations into physical charges. Modern work on generalized symmetries, edge modes, and nonperturbative gauge fixing refines the simple perturbative story.

For this volume, the working rule is: use BRST cohomology for perturbative gauge theory, remember the caveats, and do not confuse a covariant computational representation with the physical spectrum.

## Exercises

### Exercise 1: Exact states are invisible

Let $Q_{\rm B}^2=0$ and suppose $Q_{\rm B}$ is self-adjoint. If $|\Phi\rangle$ is BRST closed and $|\Psi\rangle=Q_{\rm B}|\Lambda\rangle$, show that $\langle\Phi|\Psi\rangle=0$.

<details><summary><strong>Solution</strong></summary>

Since $Q_{\rm B}|\Phi\rangle=0$ and $Q_{\rm B}$ is self-adjoint,

$$
\langle\Phi|\Psi\rangle
=
\langle\Phi|Q_{\rm B}|\Lambda\rangle
=
\langle Q_{\rm B}\Phi|\Lambda\rangle
=0.
$$

Thus a BRST-exact state has zero inner product with every BRST-closed state. This is why exact states can be quotiented out of the physical state space.

</details>

### Exercise 2: The S-matrix acts on cohomology

Assume $[Q_{\rm B},S]=0$. Show that if $|\Psi\rangle\sim |\Psi\rangle+Q_{\rm B}|\Lambda\rangle$, then $S|\Psi\rangle\sim S|\Psi\rangle+Q_{\rm B}|\Lambda'\rangle$ for some $|\Lambda'\rangle$.

<details><summary><strong>Solution</strong></summary>

Act with $S$ on the shifted representative:

$$
S(|\Psi\rangle+Q_{\rm B}|\Lambda\rangle)
=S|\Psi\rangle+SQ_{\rm B}|\Lambda\rangle.
$$

Using $[Q_{\rm B},S]=0$ gives

$$
SQ_{\rm B}|\Lambda\rangle
=Q_{\rm B}S|\Lambda\rangle.
$$

Therefore the transformed representative differs from $S|\Psi\rangle$ by the exact state $Q_{\rm B}|\Lambda'\rangle$ with $|\Lambda'\rangle=S|\Lambda\rangle$. Hence $S$ is well-defined on cohomology classes.

</details>

### Exercise 3: BRST doublets have no cohomology

Suppose $sX=Y$ and $sY=0$. Explain why a physical observable should not depend nontrivially on the pair $(X,Y)$.

<details><summary><strong>Solution</strong></summary>

The pair $(X,Y)$ is a BRST doublet. Since $Y=sX$, any appearance of $Y$ is BRST exact. Dependence on $X$ is not BRST closed unless it occurs in a combination whose $s$-variation cancels. A standard contracting-homotopy argument shows that closed expressions involving only doublet variables are exact, up to constants independent of the doublet. Therefore doublets do not contribute to BRST cohomology.

In gauge theory this is the algebraic reason unphysical gauge modes and ghost partners do not survive as physical observables.

</details>

### Exercise 4: Why external ghosts are excluded

Ghosts appear on internal lines in non-Abelian Feynman diagrams. Why are they not allowed as external particles in physical scattering amplitudes?

<details><summary><strong>Solution</strong></summary>

Ghost fields are auxiliary Grassmann variables representing the Faddeev–Popov determinant. They carry nonzero ghost number and belong to the enlarged gauge-fixed state complex, not to ghost-number-zero BRST cohomology. Physical asymptotic states are BRST cohomology classes at ghost number zero. Therefore ghosts can contribute internally to enforce the correct quotient by gauge redundancy, but external ghost states are not physical states.

</details>

## References

- Srednicki, *Quantum Field Theory*, §74, for BRST symmetry and its role in non-Abelian gauge theory.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, §§15.7–15.8, for BRST symmetry, BRST cohomology, and extensions of the formalism.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, Chs. 30–31 and the gauge-field Feynman-rule lectures, for the physical logic of covariant gauge quantization.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–30, for gauge invariance, ghosts, Ward identities, and anomaly cancellation in Standard-Model-oriented language.
- Kugo and Ojima, *Local Covariant Operator Formalism of Non-Abelian Gauge Theories and Quark Confinement Problem*, for the classic quartet-mechanism viewpoint.

## Version history

- **2026-06-18:** Initial polished draft.
