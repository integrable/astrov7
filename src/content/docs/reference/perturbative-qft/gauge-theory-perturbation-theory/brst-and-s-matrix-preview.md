---
title: "BRST and the S-Matrix Preview"
description: "A first perturbative guide to how BRST symmetry identifies physical states, removes unphysical gauge modes, and makes the gauge-fixed S-matrix unitary on the physical Hilbert space."
sidebar:
  label: "BRST and S-Matrix"
  order: 8
level: Graduate
status: "Polished draft"
source: "Becchi–Rouet–Stora; Tyutin; Kugo–Ojima; Faddeev–Popov; Slavnov–Taylor; Srednicki §§71–74; Weinberg Vol. II ch. 15; Schwartz chs. 25–26"
topics:
  - BRST symmetry
  - gauge fixing
  - S-matrix
  - physical states
  - ghosts
canonicalTopics:
  - brst-symmetry
  - brst-cohomology
  - physical-state-space
  - gauge-fixed-s-matrix
  - ghost-decoupling
researchStatus:
  established:
    - "Perturbative BRST symmetry is the standard cohomological structure that organizes gauge-fixed path integrals, Slavnov–Taylor identities, unphysical-state cancellation, and gauge-independent S-matrix elements."
  active:
    - "Nonperturbative BRST, Gribov ambiguities, gauge fixing beyond perturbation theory, and BRST-compatible resummations remain subtle in many gauge theories."
---

## Summary

BRST symmetry is the symmetry that remains after gauge fixing, once the Faddeev–Popov ghosts are included. It is not an ordinary spacetime or internal symmetry acting on physical particles. It is a cohomological symmetry that keeps track of gauge redundancy inside a gauge-fixed description.

In perturbative Yang–Mills theory, one introduces a nilpotent operation $s$ with

$$
s^2=0.
$$

One convenient convention is

$$
sA_\mu^a=(D_\mu c)^a,
\qquad
sc^a=\frac{g}{2}f^{abc}c^b c^c,
\qquad
s\bar c^a=B^a,
\qquad
sB^a=0.
$$

Here $c^a$ is the ghost, $\bar c^a$ is the antighost, and $B^a$ is an auxiliary field. The signs in $sc^a$ vary across books with the sign convention for gauge transformations and structure constants. The essential invariant statement is nilpotency: applying $s$ twice gives zero.

The physical-state rule is

$$
Q_{\rm BRST}|\psi_{\rm phys}\rangle=0,
\qquad
|\psi\rangle\sim |\psi\rangle+Q_{\rm BRST}|\chi\rangle.
$$

Thus physical states are BRST cohomology classes: closed states modulo exact states. The S-matrix is physical because it commutes with the BRST charge,

$$
{[Q_{\rm BRST},S]=0,}
$$

so it maps physical cohomology classes to physical cohomology classes. This is the perturbative explanation of ghost decoupling, longitudinal-polarization cancellation, gauge-parameter independence, and unitarity of the physical S-matrix.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![BRST symmetry turns gauge-fixed perturbation theory into a cohomological construction of the physical S-matrix](/figures/perturbative-qft/brst-and-s-matrix-preview.svg)

<figcaption>

BRST symmetry is the bridge from gauge-fixed fields to physical scattering. Gauge fixing introduces ghosts and unphysical polarizations; BRST cohomology removes the unphysical sector; the S-matrix descends to a unitary map on physical cohomology classes.

</figcaption>
</figure>

## Prerequisites

You should know [Gauge Fixing for Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/gauge-fixing-for-perturbation-theory/), [Faddeev–Popov Ghosts in Diagrams](/perturbative-qft/gauge-theory-perturbation-theory/faddeev-popov-ghosts-in-diagrams/), [Gauge-Parameter Independence](/perturbative-qft/gauge-theory-perturbation-theory/gauge-parameter-independence/), [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/), and [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/). For the S-matrix side, review [Asymptotic States](/perturbative-qft/from-correlators-to-s-matrix/asymptotic-states/), [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), and [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/).

## Core idea

Gauge-fixed perturbation theory contains more states than the physical theory. In a covariant gauge, the gauge field has components that are not physical polarizations. The ghost and antighost fields are not physical particles either, but they must appear in loops to cancel the overcounting of gauge degrees of freedom.

BRST symmetry is the structure that tells us which part of this enlarged theory is physical. It does three things at once:

1. it packages infinitesimal gauge transformations with the ghost as the gauge parameter;
2. it makes the gauge-fixing and ghost action a controlled BRST variation;
3. it defines the physical Hilbert space as cohomology.

The cohomology statement is the key. A BRST-closed state satisfies

$$
Q_{\rm BRST}|\psi\rangle=0.
$$

A BRST-exact state has the form

$$
|\psi\rangle=Q_{\rm BRST}|\chi\rangle.
$$

Exact states are treated as null physical information. They are changes of representative inside a gauge orbit. The physical state is therefore not a particular vector in the enlarged gauge-fixed space, but an equivalence class

$$
|\psi_{\rm phys}\rangle
\in
\frac{\ker Q_{\rm BRST}}{\operatorname{im} Q_{\rm BRST}}.
$$

That quotient is the algebraic reason unphysical polarizations and ghosts can be present in the calculation without appearing in physical scattering.

## Setup and conventions

We use the qft.org non-Abelian conventions

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c.
$$

For an adjoint field $X^a$, the covariant derivative is

$$
(D_\mu X)^a
=
\partial_\mu X^a-gf^{abc}A_\mu^bX^c.
$$

A convenient BRST differential is

$$
sA_\mu^a=(D_\mu c)^a,
$$

$$
sc^a=\frac{g}{2}f^{abc}c^b c^c,
$$

$$
s\bar c^a=B^a,
\qquad
sB^a=0.
$$

The ghost field $c^a$ is Grassmann odd and has ghost number $+1$. The antighost $\bar c^a$ is Grassmann odd and has ghost number $-1$. The auxiliary field $B^a$ is Grassmann even and has ghost number $0$.

| Field | Grassmann parity | Ghost number | Role |
|---|---:|---:|---|
| $A_\mu^a$ | even | $0$ | gauge field |
| $c^a$ | odd | $+1$ | ghost, replaces gauge parameter |
| $\bar c^a$ | odd | $-1$ | antighost, appears in gauge-fixing fermion |
| $B^a$ | even | $0$ | auxiliary field enforcing gauge condition |

With these assignments, $s$ raises ghost number by one.

The signs above are one consistent convention. If a source uses the opposite sign for the gauge transformation or defines the adjoint covariant derivative differently, the sign in $sc^a$ may flip. Nilpotency and the cohomology construction are the convention-independent content.

## Gauge fixing as a BRST variation

Let

$$
G^a[A]=\partial^\mu A_\mu^a
$$

be the covariant-gauge condition. Introduce the gauge-fixing fermion

$$
\Psi
=
\bar c^a
\left(G^a[A]+\frac{\xi}{2}B^a\right).
$$

The gauge-fixing plus ghost Lagrangian is written as

$$
\mathcal L_{\rm gf+gh}=s\Psi.
$$

Using the BRST rules,

$$
s\Psi
=
B^aG^a+\frac{\xi}{2}B^aB^a
-\bar c^a\,sG^a,
$$

where the minus sign comes from the Grassmann parity of $\bar c^a$. Since

$$
sG^a
=
\partial^\mu(D_\mu c)^a,
$$

we get

$$
\mathcal L_{\rm gf+gh}
=
B^a\partial^\mu A_\mu^a
+\frac{\xi}{2}B^aB^a
-\bar c^a\partial^\mu(D_\mu c)^a.
$$

The auxiliary field has no kinetic term. Its equation of motion is

$$
B^a=-\frac{1}{\xi}\partial^\mu A_\mu^a.
$$

Substituting back gives

$$
\mathcal L_{\rm gf+gh}
=
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2
-\bar c^a\partial^\mu(D_\mu c)^a.
$$

This is the usual covariant gauge-fixing and ghost Lagrangian. The advantage of the BRST form is that it makes the hidden structure visible:

$$
\mathcal L_{\rm inv}+s\Psi
$$

is BRST invariant because $\mathcal L_{\rm inv}$ is gauge invariant and $s^2\Psi=0$.

## Nilpotency

Nilpotency means

$$
s^2=0.
$$

For the antighost and auxiliary field it is immediate:

$$
s^2\bar c^a=sB^a=0,
\qquad
s^2B^a=0.
$$

For $A_\mu^a$ and $c^a$, nilpotency is the infinitesimal form of the closure of the gauge algebra. In algebra-valued notation, $sA_\mu=D_\mu c$, and $sc$ is the ghost version of the Lie bracket of two gauge transformations. The Jacobi identity for $f^{abc}$ is exactly what is needed for

$$
s^2A_\mu^a=0,
\qquad
s^2c^a=0.
$$

This is why BRST is more than a mnemonic. It is the gauge algebra rewritten with Grassmann-odd parameters.

At the quantum level, nilpotency can fail if the gauge symmetry is anomalous. In that case the theory does not merely have a technical problem; the physical-state construction and unitarity of the gauge theory are obstructed.

## The BRST charge

A continuous BRST symmetry has a conserved current $j_{\rm BRST}^\mu$ and charge

$$
Q_{\rm BRST}=\int d^3\mathbf x\,j_{\rm BRST}^0(t,\mathbf x).
$$

The charge is Grassmann odd and carries ghost number $+1$. It generates BRST transformations by a graded commutator,

$$
s\mathcal O
=
i[Q_{\rm BRST},\mathcal O\}_{\rm gr},
$$

where the bracket is a commutator for even $\mathcal O$ and an anticommutator for odd $\mathcal O$, up to convention-dependent signs.

Nilpotency becomes

$$
Q_{\rm BRST}^2=0.
$$

The gauge-fixed Hamiltonian or action is BRST invariant, so the BRST charge is conserved. In scattering language this implies

$$
[Q_{\rm BRST},S]=0.
$$

Thus if an incoming state is BRST closed,

$$
Q_{\rm BRST}|i\rangle=0,
$$

then the outgoing state is also BRST closed:

$$
Q_{\rm BRST}S|i\rangle
=
SQ_{\rm BRST}|i\rangle
=0.
$$

The S-matrix therefore maps closed states to closed states.

It also maps exact changes of representative to exact changes of representative:

$$
S\left(|i\rangle+Q_{\rm BRST}|\chi\rangle\right)
=
S|i\rangle
+
Q_{\rm BRST}S|\chi\rangle.
$$

Therefore $S$ descends to an operator on BRST cohomology.

## Physical states as cohomology

The physical Hilbert space in covariant gauge is not the full gauge-fixed state space. It is the cohomology

$$
\mathcal H_{\rm phys}
=
\frac{\ker Q_{\rm BRST}}{\operatorname{im}Q_{\rm BRST}}.
$$

This quotient has two pieces:

1. **Closedness:** $Q_{\rm BRST}|\psi\rangle=0$ imposes the gauge constraint in the enlarged space.
2. **Exact equivalence:** $|\psi\rangle\sim|\psi\rangle+Q_{\rm BRST}|\chi\rangle$ removes pure-gauge representatives.

In a free gauge theory, this cohomology keeps the transverse photon polarizations, and in perturbative partonic gauge-theory calculations it keeps the transverse external gauge-boson representatives. It removes longitudinal, timelike, ghost, and antighost excitations. In confining theories such as QCD, isolated colored gluons are not physical asymptotic hadrons nonperturbatively, but the same perturbative BRST organization is still what makes partonic amplitudes and factorized calculations consistent.

The common phrase “ghosts cancel unphysical polarizations” is true but compressed. A more precise statement is:

```txt
Unphysical gauge and ghost excitations form BRST-exact or BRST-paired sectors.
Physical amplitudes are computed on the BRST cohomology.
```

This is the covariant-gauge version of saying that only gauge-invariant degrees of freedom are physical.

## S-matrix on cohomology

The physical S-matrix is well-defined on equivalence classes if two conditions hold:

$$
Q_{\rm BRST}^2=0,
\qquad
[Q_{\rm BRST},S]=0.
$$

Let $|i\rangle$ and $|i\rangle+Q_{\rm BRST}|\chi\rangle$ represent the same physical incoming state. For a physical outgoing state $\langle f|$ satisfying the corresponding closedness condition, the difference in amplitudes is

$$
\langle f|S Q_{\rm BRST}|\chi\rangle.
$$

Using $[Q_{\rm BRST},S]=0$,

$$
\langle f|S Q_{\rm BRST}|\chi\rangle
=
\langle f|Q_{\rm BRST}S|\chi\rangle.
$$

For a physical bra, this vanishes. Thus

$$
\langle f|S|i+Q_{\rm BRST}\chi\rangle
=
\langle f|S|i\rangle.
$$

The amplitude depends only on the cohomology class, not on the representative. This is the precise version of “gauge choices do not affect physical scattering.”

## Decoupling of BRST-exact insertions

Let $\mathcal O=sX$ be a BRST-exact operator. In charge language,

$$
\mathcal O=i[Q_{\rm BRST},X\}_{\rm gr}.
$$

Between physical states,

$$
\langle f,{\rm phys}|\mathcal O|i,{\rm phys}\rangle=0,
$$

again up to the graded sign conventions. This decoupling statement is the engine behind several familiar results:

| BRST-exact structure | Physical consequence |
|---|---|
| change of gauge-fixing fermion | gauge-choice independence |
| change of gauge parameter $\xi$ | gauge-parameter independence |
| longitudinal external gauge-boson replacement | Ward or Slavnov–Taylor identity |
| unphysical polarization sector | no physical external ghosts or longitudinal gauge particles |
| BRST-exact counterterm | no change in physical S-matrix data |

This does not say that every BRST-exact expression is literally zero as an operator. It says its physical matrix elements vanish between cohomology classes.

## Ghosts and unitarity

Covariant gauge fixing seems to create a paradox. The gauge-fixed theory contains negative-norm or unphysical modes, but the physical S-matrix must be unitary.

BRST resolves the paradox by changing the statement of unitarity. The full gauge-fixed space is not the physical Hilbert space. The physical Hilbert space is the BRST cohomology. The S-matrix is unitary on that cohomology.

Schematically,

$$
S^\dagger S=1
\quad\text{on}\quad
\mathcal H_{\rm phys}.
$$

The cancellation mechanism is often called the quartet mechanism: unphysical gauge modes and ghost modes are paired into BRST multiplets whose contributions cancel from physical quantities. The details depend on the gauge and on the representation of the state space, but the cohomological idea is stable.

This is why ghosts can run in loops but cannot appear as external observed particles. Internal ghost lines are part of the algebraic repair that makes covariant gauge calculations equivalent to the physical gauge-invariant theory.

## Relation to Ward and Slavnov–Taylor identities

Ward identities in QED and Slavnov–Taylor identities in Yang–Mills theory are functional forms of BRST invariance.

In the path integral, a BRST change of variables gives

$$
0=
\int\mathcal D\Phi\,s\left[
\mathcal O[\Phi]\,e^{iS_{\rm gf}[\Phi]}
\right],
$$

assuming the measure and action are BRST invariant. Expanding this gives identities among correlation functions.

For QED, these identities reduce to Ward–Takahashi identities. For Yang–Mills theory, they include ghost terms and become Slavnov–Taylor identities. For the effective action, the same structure is often summarized by a functional equation

$$
\mathcal S(\Gamma)=0,
$$

where $\mathcal S$ is the Slavnov–Taylor operator.

The details of $\mathcal S(\Gamma)$ require antifields or external sources for BRST variations, and belong in a full BRST or BV treatment. For this page, the important point is:

```txt
BRST symmetry is the compact principle.
Ward and Slavnov–Taylor identities are its consequences for Green functions.
Gauge-parameter independence is its consequence for physical observables.
```

## Broken gauge theories

In spontaneously broken gauge theories, covariant gauges usually introduce both ghosts and would-be Goldstone fields. In an $R_\xi$ gauge, the gauge-fixing condition is chosen to cancel gauge-boson–Goldstone mixing. A schematic Abelian example is

$$
G=\partial^\mu A_\mu+\xi m\chi,
$$

where $\chi$ is the would-be Goldstone field. The corresponding gauge-fixing term is

$$
-\frac{1}{2\xi}G^2.
$$

Then Goldstone and ghost masses often depend on $\xi$:

$$
m_\chi^2=\xi m^2,
\qquad
m_c^2=\xi m^2.
$$

Those masses are not physical particle masses. They are gauge-fixing artifacts. BRST symmetry is what guarantees that the $\xi$-dependent Goldstone and ghost contributions cancel appropriately in physical observables.

This is why electroweak calculations are especially unforgiving. Leaving out a Goldstone diagram, ghost diagram, or counterterm can produce gauge-parameter dependence even if the final observable should be independent.

## BRST versus gauge symmetry

BRST symmetry is sometimes described as “the quantum version of gauge symmetry.” That phrase is useful, but it can also mislead.

Gauge redundancy is a redundancy of description. It relates field configurations that represent the same physical situation. BRST symmetry is a global Grassmann-odd symmetry of the gauge-fixed action that remembers this redundancy after gauge fixing.

The relationship is:

| Structure | Meaning |
|---|---|
| gauge transformation | changes representative on a gauge orbit |
| gauge fixing | chooses a slice through gauge orbits |
| Faddeev–Popov determinant | corrects the path-integral measure |
| ghosts | represent the determinant and gauge-orbit Jacobian |
| BRST symmetry | cohomological remnant of gauge redundancy after gauge fixing |
| BRST cohomology | physical state or operator content |

Thus BRST is not an extra physical symmetry producing new conserved particle quantum numbers. It is a bookkeeping symmetry whose cohomology defines the physical content.

## Where the preview stops

This page is a perturbative scattering preview. A full BRST treatment goes further:

- construction of the BRST current and charge in detail;
- proof of nilpotency at the quantum level;
- Slavnov–Taylor identities with antifields or external sources;
- algebraic renormalization;
- Kugo–Ojima physical-state formalism;
- Batalin–Vilkovisky formalism for general gauge systems;
- Gribov copies and nonperturbative gauge fixing;
- BRST cohomology of local operators and anomalies.

Those topics belong mainly to the Symmetry, Anomalies, and Topology volume, the Gauge Theories and Standard Model volume, and the Mathematical and Rigorous QFT volume. Here the goal is narrower: understand why the gauge-fixed perturbative S-matrix is a physical object.

## Common pitfalls

**Thinking ghosts are physical particles.** Ghosts are Grassmann scalar fields used inside gauge-fixed perturbation theory. They do not appear as external states in the physical S-matrix.

**Thinking BRST is an optional trick.** In covariant perturbation theory, BRST is the organizing principle behind physical-state projection, Slavnov–Taylor identities, gauge-parameter independence, and unitarity.

**Ignoring the quotient by exact states.** The physical condition is not only $Q_{\rm BRST}|\psi\rangle=0$. One must also identify states that differ by $Q_{\rm BRST}|\chi\rangle$.

**Assuming nilpotency is automatic quantum mechanically.** Gauge anomalies can obstruct BRST nilpotency. An anomalous gauge theory is not a consistent perturbative quantum gauge theory.

**Forgetting Goldstone fields in broken gauges.** In $R_\xi$ gauges, Goldstone and ghost contributions are part of the BRST cancellation pattern.

**Using BRST language nonperturbatively without caveats.** Perturbative BRST around a fixed gauge patch is standard. Global gauge fixing, Gribov copies, confinement, and physical state spaces in non-Abelian gauge theories require more care.

## Relations to other pages

- [Gauge Fixing for Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/gauge-fixing-for-perturbation-theory/) explains why gauge-fixed propagators are needed.
- [Faddeev–Popov Ghosts in Diagrams](/perturbative-qft/gauge-theory-perturbation-theory/faddeev-popov-ghosts-in-diagrams/) gives the determinant and ghost-line origin of the BRST ghost fields.
- [Gauge-Parameter Independence](/perturbative-qft/gauge-theory-perturbation-theory/gauge-parameter-independence/) explains how BRST-exact gauge variations decouple from physical amplitudes.
- [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/) gives the Abelian ancestor of the Slavnov–Taylor identities.
- [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/) gives the non-Abelian vertices whose consistency is organized by BRST.
- [Background Field Method Preview](/perturbative-qft/gauge-theory-perturbation-theory/background-field-method-preview/) explains a complementary way to preserve manifest background gauge invariance.
- [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/) fixes the scattering normalization that the physical BRST cohomology acts on.

## Research status

- **Established:** Perturbative BRST symmetry, Faddeev–Popov ghosts, and Slavnov–Taylor identities are standard tools for quantizing anomaly-free gauge theories and proving gauge-independent physical S-matrix elements.
- **Subtle:** The connection between BRST cohomology and a nonperturbative physical Hilbert space is harder than the perturbative story, especially in confining non-Abelian gauge theories.
- **Active:** BRST-compatible resummation, gauge-invariant definitions of unstable-particle observables, algebraic renormalization, BV methods, and nonperturbative gauge fixing remain important research and precision-calculation topics.

## Exercises

### Exercise 1: Ghost numbers

Using the assignments

$$
{\rm gh}(A_\mu)=0,
\qquad
{\rm gh}(c)=1,
\qquad
{\rm gh}(\bar c)=-1,
\qquad
{\rm gh}(B)=0,
$$

show that the BRST differential $s$ raises ghost number by one.

<details>
<summary><strong>Solution</strong></summary>

The BRST variations are

$$
sA_\mu^a=(D_\mu c)^a,
\qquad
sc^a=\frac{g}{2}f^{abc}c^b c^c,
\qquad
s\bar c^a=B^a,
\qquad
sB^a=0.
$$

The right-hand side of $sA_\mu$ contains one ghost, so it has ghost number $1$, while $A_\mu$ has ghost number $0$.

The right-hand side of $sc$ contains two ghosts, so it has ghost number $2$, while $c$ has ghost number $1$.

The right-hand side of $s\bar c$ is $B$, which has ghost number $0$, while $\bar c$ has ghost number $-1$.

Thus in every nonzero case,

$$
{\rm gh}(s\Phi)={\rm gh}(\Phi)+1.
$$

</details>

### Exercise 2: Eliminating the auxiliary field

Start from

$$
\mathcal L_{\rm gf}
=
B^aG^a+\frac{\xi}{2}B^aB^a.
$$

Eliminate $B^a$ and show that the usual gauge-fixing term is recovered.

<details>
<summary><strong>Solution</strong></summary>

The equation of motion for $B^a$ is

$$
0=\frac{\partial \mathcal L_{\rm gf}}{\partial B^a}
=
G^a+\xi B^a.
$$

Therefore

$$
B^a=-\frac{1}{\xi}G^a.
$$

Substituting back gives

$$
\mathcal L_{\rm gf}
=
-\frac{1}{\xi}G^aG^a
+
\frac{\xi}{2}\frac{1}{\xi^2}G^aG^a
=
-\frac{1}{2\xi}G^aG^a.
$$

Thus

$$
\mathcal L_{\rm gf}
=
-\frac{1}{2\xi}(G^a)^2.
$$

</details>

### Exercise 3: S-matrix on cohomology

Assume

$$
[Q_{\rm BRST},S]=0.
$$

Show that if $|i\rangle$ and $|i\rangle+Q_{\rm BRST}|\chi\rangle$ represent the same physical incoming state, then they give the same physical amplitude against a BRST-closed outgoing state.

<details>
<summary><strong>Solution</strong></summary>

The difference in amplitudes is

$$
\Delta\mathcal A
=
\langle f|S Q_{\rm BRST}|\chi\rangle.
$$

Using $[Q_{\rm BRST},S]=0$,

$$
\Delta\mathcal A
=
\langle f|Q_{\rm BRST}S|\chi\rangle.
$$

For a physical outgoing bra, the BRST charge annihilates it in the corresponding adjoint sense, so

$$
\langle f|Q_{\rm BRST}=0.
$$

Therefore

$$
\Delta\mathcal A=0.
$$

The amplitude depends only on the BRST cohomology class of the incoming state.

</details>

### Exercise 4: Gauge-parameter variation is BRST exact

Let

$$
\Psi(\xi)
=
\bar c^a\left(G^a+\frac{\xi}{2}B^a\right).
$$

Show that $\partial_\xi(s\Psi)$ is BRST exact.

<details>
<summary><strong>Solution</strong></summary>

Since $s$ does not depend on $\xi$ in this simple covariant gauge family,

$$
\frac{\partial}{\partial\xi}(s\Psi)
=
s\left(\frac{\partial\Psi}{\partial\xi}\right).
$$

But

$$
\frac{\partial\Psi}{\partial\xi}
=
\frac12\bar c^aB^a.
$$

Therefore

$$
\frac{\partial}{\partial\xi}(s\Psi)
=
s\left(\frac12\bar c^aB^a\right).
$$

So the gauge-parameter variation of the gauge-fixing and ghost Lagrangian is BRST exact.

</details>

### Exercise 5: Why ghosts cannot be external physical particles

Use the BRST-cohomology interpretation to explain why ghosts may appear in internal loops but not as observed external particles.

<details>
<summary><strong>Solution</strong></summary>

Ghost fields are part of the enlarged gauge-fixed field space. They represent the Faddeev–Popov determinant and are required for the Slavnov–Taylor identities that cancel unphysical gauge modes. Physical external states, however, are BRST cohomology classes: they are closed under $Q_{\rm BRST}$ and defined modulo exact states. Ghost excitations are not elements of the physical cohomology as asymptotic observed particles. They can appear internally because internal lines are bookkeeping devices in the gauge-fixed path integral, not observed asymptotic states. Their loop contributions are precisely what makes the physical cohomology amplitudes consistent.

</details>

## References

- C. Becchi, A. Rouet, and R. Stora, original papers introducing BRST symmetry in renormalized gauge theories.
- I. V. Tyutin, original work on gauge invariance in field theory and the symmetry now called BRST.
- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” for the determinant and ghost construction.
- T. Kugo and I. Ojima, classic work on BRST quantization and the physical state space.
- M. Srednicki, *Quantum Field Theory*, §§71–74, for non-Abelian gauge theory, Faddeev–Popov ghosts, and BRST symmetry.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, ch. 15, for gauge fixing, ghosts, BRST, and the gauge-theory path integral.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 25–26, for Yang–Mills theory and ghost contributions in perturbative calculations.

## Version history

- **2026-06-13:** Initial polished draft for the Perturbative QFT and Scattering volume.
