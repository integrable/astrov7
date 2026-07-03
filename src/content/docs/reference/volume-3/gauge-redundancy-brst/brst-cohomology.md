---
title: "BRST Cohomology"
description: "Explains how BRST cohomology identifies the physical states, observables, counterterms, and anomaly classes of a gauge-fixed theory."
sidebar:
  label: "BRST Cohomology"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki §§71–74; Weinberg Vol. II §§15.7–15.9; Zinn-Justin, BRST/Zinn-Justin equation; Henneaux–Teitelboim; Barnich–Brandt–Henneaux local BRST cohomology."
topics:
  - BRST cohomology
  - physical states
  - gauge-invariant observables
  - ghost number
  - anomalies
  - local BRST cohomology
canonicalTopics:
  - brst-cohomology
  - physical-state-cohomology
  - local-brst-cohomology
  - gauge-anomaly
  - brst-exact
researchStatus:
  established:
    - "In perturbatively gauge-fixed anomaly-free gauge theories, physical states and gauge-invariant observables are represented by BRST cohomology classes."
    - "Local BRST cohomology organizes consistent interactions, invariant counterterms, conserved currents, and gauge anomalies."
  active:
    - "Global, boundary, nonperturbative, and higher-categorical generalizations of BRST cohomology remain subtle and context-dependent."
---

## Summary

BRST symmetry gives a nilpotent operator. Nilpotent operators create cohomology. In gauge theory, this cohomology is not decorative mathematics; it is the rule that tells us which objects in the gauge-fixed description are physical.

Let $Q_{\rm B}$ be the BRST charge in canonical language, or $s$ the BRST differential in Lagrangian language. Nilpotence means

$$
Q_{\rm B}^2=0,
\qquad
s^2=0.
$$

A state is BRST-closed if

$$
Q_{\rm B}|\psi\rangle=0,
$$

and BRST-exact if

$$
|\psi\rangle=Q_{\rm B}|\chi\rangle.
$$

The physical state space is the quotient

$$
\mathcal H_{\rm phys}
=\frac{\ker Q_{\rm B}}{\operatorname{im}Q_{\rm B}}.
$$

Likewise, a physical operator is represented by a BRST-closed operator modulo BRST-exact operators:

$$
s\mathcal O=0,
\qquad
\mathcal O\sim\mathcal O+s\Lambda.
$$

This quotient is the point. The physical content is not every BRST-closed object; it is every BRST-closed object after declaring BRST-exact clutter to be zero.

<figure class="doc-figure" style="--figure-width: 52rem;">

![BRST cohomology as the quotient of closed states or operators by exact states or operators, with ghost-number grading and BRST doublets.](/figures/symmetry-anomalies-topology/brst-cohomology-quotient.svg)

<figcaption>

BRST cohomology keeps the closed objects and quotients out the exact ones. At ghost number $0$ it gives physical observables or states. At ghost number $1$ the same logic detects possible gauge anomalies. BRST doublets contribute no cohomology.

</figcaption>
</figure>

The phrase “modulo BRST-exact terms” sounds modest, but it is doing serious work. It removes gauge artifacts, longitudinal modes, timelike modes, auxiliary fields, ghosts, and gauge-fixing choices from the physical answer.

## Prerequisites

Read [BRST Symmetry](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-symmetry/) first. You should know the transformations

$$
sA_\mu=\mathcal D_\mu c,
\qquad
sc=-igc^2,
\qquad
s\bar c=B,
\qquad
sB=0,
$$

and why the gauge-fixed action can be written as $S_{\rm YM}+s\Psi$.

It is also useful to know [Charges Acting on Local Operators](/symmetry-anomalies-topology/noether-currents-ward-identities/charges-acting-on-local-operators/) and [Ward Identities: Operator Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-operator-form/), because $Q_{\rm B}$ is a conserved charge in the gauge-fixed theory.

## Core idea

A cohomology is built from a nilpotent map.

Suppose a vector space $\mathcal V$ has a map

$$
s:\mathcal V\to\mathcal V,
\qquad
s^2=0.
$$

Then every exact element is closed:

$$
X=sY
\quad\Rightarrow\quad
sX=s^2Y=0.
$$

So

$$
\operatorname{im}s\subset\ker s.
$$

The cohomology is

$$
H(s)=\frac{\ker s}{\operatorname{im}s}.
$$

For BRST, $\mathcal V$ might be a space of states, local operators, local functionals, counterterms, currents, or possible anomalies. The interpretation depends on the ghost number.

At ghost number $0$, BRST cohomology describes physical observables and physical states. At ghost number $1$, local BRST cohomology describes possible anomalies. At other ghost numbers it can encode global symmetries, deformations, reducibility identities, or higher structures depending on the formalism.

## Setup and conventions

We use the BRST transformations from the previous page:

$$
sA_\mu=\mathcal D_\mu c,
\qquad
sc=-igc^2,
\qquad
s\bar c=B,
\qquad
sB=0.
$$

The ghost number assignments are

$$
\operatorname{gh}(A_\mu)=0,
\qquad
\operatorname{gh}(c)=1,
\qquad
\operatorname{gh}(\bar c)=-1,
\qquad
\operatorname{gh}(B)=0,
$$

and

$$
\operatorname{gh}(s)=1.
$$

The BRST charge satisfies

$$
[Q_{\rm gh},Q_{\rm B}]=Q_{\rm B},
$$

where $Q_{\rm gh}$ is the ghost-number charge. Thus BRST maps ghost-number $n$ objects to ghost-number $n+1$ objects.

For an operator $\mathcal O$, the relation between the charge and the differential is schematically

$$
s\mathcal O=i[Q_{\rm B},\mathcal O\}_{\pm},
$$

where $[\cdot,\cdot\}_{\pm}$ is the graded commutator. Sign conventions for the factor of $i$ vary; the cohomology does not.

:::note[Convention-sensitive source note]
Some sources write the BRST charge as $Q$, $Q_{\rm BRST}$, $Q_B$, or $\Omega$. Some absorb factors of $i$ into the definition of $s$. The stable statements are $Q_{\rm B}^2=0$, $s^2=0$, and physical equivalence by quotienting exact states or operators.
:::

## Why exact states are unphysical

The quotient by exact states is not arbitrary. If $|\phi\rangle$ is BRST-closed and $|\psi\rangle=Q_{\rm B}|\chi\rangle$ is BRST-exact, then formally

$$
\langle\phi|\psi\rangle
=\langle\phi|Q_{\rm B}|\chi\rangle.
$$

If the BRST charge has the appropriate adjointness property on the indefinite gauge-fixed state space, then

$$
\langle\phi|Q_{\rm B}|\chi\rangle
=\langle Q_{\rm B}\phi|\chi\rangle=0.
$$

So exact states have zero overlap with closed physical states. They are null directions in the physical pairing. Quotienting by them removes redundant gauge-fixing degrees of freedom.

This is the BRST version of a familiar idea: a pure-gauge excitation should not be counted as a physical photon or gluon state.

## Why closed is not enough

BRST-closed means invariant under the BRST differential. But an exact object is automatically closed:

$$
X=sY
\quad\Rightarrow\quad
sX=0.
$$

If we kept every closed object, we would still keep pure-gauge garbage. The cohomology quotient removes it.

A useful analogy is de Rham cohomology. A closed differential form satisfies $d\omega=0$. An exact form is $\omega=d\lambda$. Exact forms are closed, but they do not represent nontrivial topology. The cohomology keeps closed forms modulo exact forms:

$$
H_{\rm dR}=\frac{\ker d}{\operatorname{im}d}.
$$

BRST cohomology is the gauge-theory cousin:

$$
H_{\rm BRST}=\frac{\ker s}{\operatorname{im}s}.
$$

The analogy is not just poetic. In geometric treatments, BRST is literally a differential on the space of gauge orbits, with ghosts playing the role of odd coordinates along gauge directions.

## Operators at ghost number zero

For local gauge-invariant operators, BRST closure is usually straightforward. Since $s$ acts like an infinitesimal gauge transformation with parameter $c$, a gauge-invariant operator $\mathcal O$ satisfies

$$
s\mathcal O=0.
$$

Examples include

$$
\operatorname{tr}F_{\mu\nu}F^{\mu\nu},
\qquad
\operatorname{tr}F_{\mu\nu}\widetilde F^{\mu\nu},
\qquad
\bar\psi\psi
$$

when the matter indices are contracted gauge-invariantly. Wilson loops are nonlocal examples:

$$
W_R(C)=\operatorname{tr}_R\,P\exp\left(ig\oint_C A\right).
$$

Gauge-variant quantities are generally not BRST cohomology classes. For example, $A_\mu^a$ itself is not BRST-closed:

$$
sA_\mu^a=\mathcal D_\mu^{ab}c^b.
$$

The gauge-fixing term is also not physical data. It is BRST-exact:

$$
S_{\rm gf}+S_{\rm gh}=s\Psi.
$$

Therefore changing the gauge-fixing fermion changes the representative of the gauge-fixed path integral, not the cohomology class of a physical observable.

## The BRST doublet lemma

A pair of variables $(u,v)$ is a BRST doublet if

$$
su=v,
\qquad
sv=0.
$$

The pair contributes no cohomology. Intuitively, $v$ is exact, and $u$ is not closed unless it appears in a combination that can be removed by a homotopy. More precisely, for polynomial functions of a doublet, every closed dependence on the pair is exact up to a part independent of the pair.

The antighost and auxiliary field form the basic example:

$$
s\bar c=B,
\qquad
sB=0.
$$

This is why $\bar c$ and $B$ do not create physical observables. They are gauge-fixing scaffolding.

In the state space, a similar mechanism removes unphysical modes. Longitudinal gauge modes, timelike gauge modes, ghosts, and antighosts organize into BRST doublets or quartets. The surviving cohomology is built from transverse physical polarizations and gauge-invariant composite data.

## Free Maxwell theory as a guide

In covariantly gauge-fixed Maxwell theory, the vector field has four components. A massless physical photon has only two polarizations. The mismatch is not a paradox; it is the reason gauge redundancy was present in the first place.

BRST quantization handles the mismatch as follows:

1. The BRST-closed condition removes states that are not compatible with the constraint structure.
2. The quotient by BRST-exact states identifies states that differ by a pure-gauge excitation.
3. Ghost and longitudinal/timelike sectors cancel in the cohomology.

The final physical one-particle state space contains the two transverse photon polarizations. In non-Abelian perturbation theory, the same logic applies around the perturbative vacuum, although interactions make the bookkeeping more intricate.

The important lesson is that the gauge-fixed Fock space is larger than the physical Hilbert space. BRST cohomology is the projection method that does not ruin Lorentz covariance.

## Local BRST cohomology

For renormalization, anomalies, and deformations, one usually studies **local** BRST cohomology. The objects are local functionals or local differential forms built from fields and finitely many derivatives.

A local functional is an integral

$$
I=\int d^dx\,a(x),
$$

where $a(x)$ is a local density. Since total derivatives do not affect the integrated functional on a compact spacetime without boundary, the relevant equivalence often becomes cohomology modulo $d$:

$$
sa+db=0,
\qquad
 a\sim a+s\lambda+d\mu.
$$

This is written as

$$
H(s|d).
$$

This notation means: BRST cohomology of local densities, with total derivatives treated as trivial.

The ghost number determines the physical use:

| Ghost number | Typical meaning |
|---:|---|
| $0$ | gauge-invariant actions, observables, counterterms |
| $1$ | candidate gauge anomalies |
| $-1$ | global symmetries and conserved currents in some formulations |
| higher | higher consistency data, reducibility, or BV structures |

This table is a map, not a substitute for theorems. The exact classification depends on dimension, field content, locality assumptions, and whether one works on shell or off shell.

## Anomalies as cohomology classes

A gauge anomaly is a failure of BRST symmetry at the quantum level. Suppose the quantum effective action satisfies

$$
s\Gamma=\mathcal A.
$$

Nilpotence implies

$$
s\mathcal A=0.
$$

This is the Wess–Zumino consistency condition in BRST language. If the anomaly can be written as

$$
\mathcal A=s\mathcal B,
$$

then it can be removed by adding the local counterterm $-\mathcal B$ to the effective action. Such an anomaly is cohomologically trivial.

A genuine anomaly is therefore a nontrivial class:

$$
[\mathcal A]\in H^1(s|d).
$$

This is one of the cleanest uses of BRST cohomology. Gauge anomalies are not just “nonconservation of a current.” They are obstructions to solving the quantum BRST identity.

This also explains why anomaly cancellation is a consistency condition for gauge theories. If the nontrivial ghost-number-one class vanishes after summing over all matter fields, the BRST identity can be maintained. If it does not vanish, the theory cannot be quantized as a theory with that gauge redundancy.

## Counterterms and deformations

BRST cohomology at ghost number $0$ controls possible counterterms. A counterterm added to the action must preserve BRST symmetry, at least up to a BRST-exact or total-derivative term:

$$
s\Delta S=0.
$$

If

$$
\Delta S=sX,
$$

then it is a BRST-exact change of gauge-fixing data or field-redefinition type information, not a new physical coupling. Nontrivial classes at ghost number $0$ correspond to genuine invariant deformations.

For Yang–Mills theory, examples include gauge-invariant local terms such as

$$
\int d^4x\,\operatorname{tr}F_{\mu\nu}F^{\mu\nu}
$$

and, depending on dimension and symmetry assumptions,

$$
\int \operatorname{tr}F\wedge F.
$$

This is why BRST cohomology appears in algebraic proofs of renormalizability: it classifies which divergences can appear consistently with gauge symmetry.

## On-shell versus off-shell cohomology

There are two common versions of BRST cohomology.

In off-shell BRST, auxiliary fields such as $B^a$ are kept, and nilpotence holds without using equations of motion:

$$
s^2=0
\quad\text{off shell}.
$$

In on-shell BRST, some auxiliary fields are eliminated, or the algebra closes only after imposing equations of motion. Then nilpotence may hold only modulo equations of motion.

For elementary Faddeev–Popov Yang–Mills theory, the auxiliary field makes the off-shell story simple. For more complicated gauge systems, especially those with open gauge algebras or reducible gauge symmetries, the BV formalism is the natural framework. BV enlarges the field space further by introducing antifields and encodes the whole structure in the master equation.

For this page, the practical rule is:

$$
\text{keep }B\text{ when explaining cohomology; eliminate it when convenient for propagators.}
$$

## Boundaries and global issues

BRST-exact terms are often treated as physically trivial. That statement has assumptions.

On a spacetime with boundary,

$$
\int d^dx\,\partial_\mu j^\mu
$$

need not vanish. Thus cohomology modulo total derivatives must be handled with boundary conditions included.

Similarly, a gauge transformation that is pure redundancy in the bulk may act nontrivially on boundary data. Then the corresponding would-be exact direction can carry physical charge. This is why edge modes in gauge theory, Chern–Simons boundary degrees of freedom, and asymptotic symmetries require more care than the flat-space perturbative BRST story suggests.

Gribov copies introduce another global issue. The perturbative BRST complex describes a local patch of gauge orbit space. Globally, the gauge-fixing slice may not exist as a single smooth object. This does not spoil the standard perturbative use of BRST, but it warns against careless nonperturbative extrapolation.

## BRST cohomology and BV preview

BRST cohomology is the visible entrance to the larger BV-BRST framework. BV becomes necessary when gauge algebras are open, reducible, or field-dependent in a way that the elementary Faddeev–Popov construction does not handle cleanly.

BV introduces antifields $\Phi^*$ paired with fields $\Phi$ and an antibracket $(\cdot,\cdot)$. The classical master equation is

$$
(S,S)=0.
$$

This single equation packages the action, gauge transformations, closure relations, equations-of-motion identities, ghosts, ghosts-for-ghosts, and higher consistency conditions.

In that language, BRST cohomology is not an add-on. It is the cohomology of the differential generated by the BV master action. The page [BV Formalism Preview](/symmetry-anomalies-topology/gauge-redundancy-brst/bv-formalism-preview/) will give the careful first pass.

## Common pitfalls

**Pitfall: identifying physical objects with all closed objects.** Physical objects are closed modulo exact. Forgetting the quotient keeps pure-gauge data.

**Pitfall: treating exact terms as zero without checking boundaries.** Exact terms are trivial only under assumptions about boundary conditions, zero modes, and the functional measure.

**Pitfall: thinking BRST cohomology is only for states.** It also classifies observables, counterterms, anomalies, consistent deformations, and conservation laws.

**Pitfall: saying ghosts disappear because they are unphysical.** Ghosts are unphysical external states, but they are essential internal fields in covariant gauge-fixed perturbation theory.

**Pitfall: ignoring ghost number.** The same cohomological machinery means different things at different ghost numbers. Ghost number $0$ and ghost number $1$ are especially important.

**Pitfall: assuming perturbative BRST automatically solves nonperturbative gauge fixing.** Gribov copies and global orbit-space issues are not removed by writing $s^2=0$ in a local patch.

## Relations to other pages

This page follows [BRST Symmetry](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-symmetry/) and prepares [Physical State Space](/symmetry-anomalies-topology/gauge-redundancy-brst/physical-state-space/). It also feeds directly into [BV Formalism Preview](/symmetry-anomalies-topology/gauge-redundancy-brst/bv-formalism-preview/), [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), [Wess–Zumino Consistency Condition](/symmetry-anomalies-topology/anomalies/wess-zumino-consistency-condition/), and [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/).

In the gauge-theory volume, BRST cohomology reappears in the proof of Slavnov–Taylor identities, the classification of allowed counterterms, and the unitarity of gauge-fixed perturbation theory.

## Research status

The perturbative BRST cohomology of Yang–Mills-type gauge theories is a mature part of quantum field theory. It is used in renormalization, anomaly classification, deformation theory, and the proof that covariant gauge-fixed calculations have a physical gauge-invariant content.

Active subtleties live at the boundaries: nonperturbative gauge fixing, Gribov regions, edge modes, asymptotic symmetries, non-Lagrangian theories, higher-form gauge fields, and categorical or derived versions of gauge structure. In these settings, the BRST idea remains powerful, but the correct complex may be larger or more global than the elementary Faddeev–Popov one.

## Exercises

### Exercise 1. Exact states have zero overlap with closed states

Assume $Q_{\rm B}^2=0$ and that the adjointness properties allow moving $Q_{\rm B}$ from ket to bra without extra anomaly terms. Show that a BRST-exact state has zero inner product with any BRST-closed state.

<details><summary><strong>Solution</strong></summary>

Let

$$
|\psi\rangle=Q_{\rm B}|\chi\rangle,
\qquad
Q_{\rm B}|\phi\rangle=0.
$$

Then

$$
\langle\phi|\psi\rangle
=\langle\phi|Q_{\rm B}|\chi\rangle.
$$

Moving $Q_{\rm B}$ to the bra gives

$$
\langle\phi|Q_{\rm B}|\chi\rangle
=\langle Q_{\rm B}\phi|\chi\rangle=0.
$$

Thus exact states are null against closed states and should be quotiented out of the physical pairing.

</details>

### Exercise 2. Field strength is BRST covariant

For Yang–Mills theory, show that

$$
sF_{\mu\nu}=ig[F_{\mu\nu},c].
$$

Conclude that $\operatorname{tr}F_{\mu\nu}F^{\mu\nu}$ is BRST-closed.

<details><summary><strong>Solution</strong></summary>

The gauge field transforms under BRST like an infinitesimal gauge transformation with parameter $c$:

$$
sA_\mu=\mathcal D_\mu c.
$$

The field strength transforms covariantly under an infinitesimal gauge transformation, so

$$
sF_{\mu\nu}=ig[F_{\mu\nu},c].
$$

Then

$$
s\operatorname{tr}F_{\mu\nu}F^{\mu\nu}
=2\operatorname{tr}(sF_{\mu\nu})F^{\mu\nu}
=2ig\operatorname{tr}[F_{\mu\nu},c]F^{\mu\nu}.
$$

Using cyclicity of the trace,

$$
\operatorname{tr}[F_{\mu\nu},c]F^{\mu\nu}=0.
$$

Therefore

$$
s\operatorname{tr}F_{\mu\nu}F^{\mu\nu}=0.
$$

</details>

### Exercise 3. A BRST doublet has no cohomology

Let $su=v$ and $sv=0$. Explain why $v$ is not a nontrivial cohomology class.

<details><summary><strong>Solution</strong></summary>

The element $v$ is closed because

$$
sv=0.
$$

But it is also exact because

$$
v=su.
$$

A cohomology class is closed modulo exact elements. Since $v$ is exact, it represents the zero class:

$$
[v]=0\in H(s).
$$

The full doublet lemma says that polynomial dependence on such a pair contributes no nontrivial cohomology, up to dependence independent of the doublet.

</details>

### Exercise 4. Anomaly consistency

Suppose the effective action obeys $s\Gamma=\mathcal A$. Use $s^2=0$ to show that $s\mathcal A=0$.

<details><summary><strong>Solution</strong></summary>

Apply $s$ to both sides:

$$
s^2\Gamma=s\mathcal A.
$$

Since $s^2=0$,

$$
s\mathcal A=0.
$$

Thus any anomaly must be BRST-closed. A trivial anomaly has the form $\mathcal A=s\mathcal B$ and can be removed by a local counterterm. A genuine anomaly is a nontrivial BRST cohomology class at ghost number $1$.

</details>

## References

- Becchi, Rouet, Stora, and Tyutin, original BRST papers.
- Faddeev and Popov, “Feynman Diagrams for the Yang–Mills Field,” 1967.
- Srednicki, *Quantum Field Theory*, BRST and non-Abelian gauge theory sections.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Chapter 15.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chapters on BRST symmetry, the Zinn-Justin equation, and gauge theory renormalization.
- Henneaux and Teitelboim, *Quantization of Gauge Systems*, for canonical BRST and constrained systems.
- Barnich, Brandt, and Henneaux, “Local BRST cohomology in gauge theories,” for local cohomology, anomalies, and deformations.
- Gomis, Paris, and Samuel, “Antibracket, antifields and gauge-theory quantization,” for a bridge to BV.

## Version history

- 2026-06-17: First polished draft. Added state and operator cohomology, ghost-number grading, local BRST cohomology, anomaly interpretation, counterterm classification, boundary caveats, and exercises.
