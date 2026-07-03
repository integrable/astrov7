---
title: "Projective Representations Preview"
description: "Explains why quantum symmetries may close only up to phases, how projective representations become central extensions or covering groups, and why this preview matters for spin, anomalies, and generalized symmetry."
sidebar:
  label: "Projective Representations"
  order: 10
level: Advanced
status: "Polished draft"
source: "Weinberg Vol. I §2.7; Wigner theorem; Bargmann central extensions; standard QFT symmetry and anomaly lore."
topics:
  - projective representations
  - Wigner theorem
  - quantum symmetry
  - central extensions
  - covering groups
  - anomalies
canonicalTopics:
  - projective-representation
  - central-extension
  - quantum-symmetry-phase
  - covering-group
researchStatus:
  established:
    - "Quantum symmetries act on rays, so their Hilbert-space implementations can form projective representations whose phases are classified up to redefinition."
  active:
    - "Projective phases reappear in modern QFT through anomalies, boundary degrees of freedom, symmetry defects, higher groups, and categorical symmetry data."
---

## Summary

Quantum states are rays, not preferred vectors. Multiplying a state vector by a phase does not change the physical state:

$$
|\psi\rangle\sim e^{i\lambda}|\psi\rangle.
$$

Because of this, a symmetry action on physical states need not lift to Hilbert-space operators that multiply exactly as the abstract group does. One may have

$$
U_gU_h=e^{i\omega(g,h)}U_{gh},
$$

where $\omega(g,h)$ is a phase. This is a **projective representation**.

The phase is not automatically physical. If we rephase the chosen operators by

$$
U_g\mapsto U'_g=e^{i\beta(g)}U_g,
$$

then $\omega$ changes. Only the part of $\omega$ that cannot be removed this way is meaningful. Equivalently, a projective representation of $G$ can often be viewed as an ordinary representation of a larger group $\widehat G$ fitting into a central extension,

$$
1\longrightarrow U(1)\longrightarrow \widehat G\longrightarrow G\longrightarrow 1.
$$

Infinitesimally, a projective phase may appear as a central term in the charge algebra,

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c+i\kappa_{ab}\mathbf 1.
$$

Topologically, it may appear because the physically convenient group is not simply connected. Spin-$1/2$ states, for example, are projective representations of $SO(3)$ but ordinary representations of its double cover $SU(2)$.

This page is a preview because projective representation theory is not needed for the first pass through ordinary global symmetry. But it is the first hint of a bigger theme: in quantum field theory, symmetry can carry phase data beyond the naive group action. Later this becomes central extensions, Schwinger terms, spin structures, anomalies, symmetry-protected boundary states, and symmetry defects.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A schematic showing a symmetry action on rays lifting to Hilbert-space operators that close up to a phase, and then being repaired either by rephasing, a central extension, or a covering group.](/figures/symmetry-anomalies-topology/projective-representation-lift.svg)

<figcaption>

A physical symmetry acts on rays. A choice of Hilbert-space lifts $U_g$ may close only up to a phase $e^{i\omega(g,h)}$. Trivial phases can be removed by rephasing; nontrivial phases are encoded by central extensions, covering groups, or, in QFT, anomaly-like data.

</figcaption>
</figure>

## Prerequisites

You should know [What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/), [Symmetry Groups and Representations](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-groups-and-representations/), [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/), [Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/), and [Symmetry Algebras](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-algebras/).

The mathematical prerequisites are modest: Hilbert-space rays, group multiplication, and commutators. The page uses some cohomology words, but only in their most basic role: distinguishing a removable phase from a nonremovable one.

## Core idea

The core idea is almost embarrassingly simple.

A symmetry of quantum mechanics maps physical states to physical states while preserving transition probabilities. Physical states are rays in Hilbert space, so the symmetry is really a map

$$
\mathbb P(\mathcal H)\longrightarrow\mathbb P(\mathcal H),
$$

not first of all a map $\mathcal H\to\mathcal H$.

Wigner's theorem says that such a probability-preserving map is implemented on Hilbert space by either a unitary linear operator or an antiunitary antilinear operator. Continuous internal symmetries are represented by unitary operators connected to the identity; antiunitary symmetries such as time reversal are treated later in the discrete and antiunitary chapter.

But Wigner's theorem gives the operator only up to a phase. If $U_g$ implements $g$, then so does $e^{i\beta(g)}U_g$. Therefore the equation

$$
gh\mapsto U_gU_h
$$

can differ from the chosen representative $U_{gh}$ by a phase.

The slogan is

$$
\text{symmetry on rays}
\quad\leadsto\quad
\text{operator representation up to phase}.
$$

This is not a flaw in quantum theory. It is one of the places where quantum mechanics is more subtle than classical mechanics.

## Setup and conventions

Let $G$ be a symmetry group. For now assume its elements are represented by unitary operators $U_g$ on Hilbert space. Since $U_g$ is only defined up to a phase, a consistent choice of lifts may satisfy

$$
U_gU_h=e^{i\omega(g,h)}U_{gh},
$$

where $\omega(g,h)$ is real and defined modulo $2\pi$.

Associativity of operator multiplication requires

$$
U_g(U_hU_k)=(U_gU_h)U_k.
$$

Substituting the projective multiplication law gives

$$
\omega(h,k)+\omega(g,hk)
=
\omega(g,h)+\omega(gh,k)
\quad \mathrm{mod}\,2\pi.
$$

This is the **two-cocycle condition**.

Now rephase the lifts:

$$
U_g\mapsto U'_g=e^{i\beta(g)}U_g.
$$

Then

$$
U'_gU'_h
=e^{i\omega'(g,h)}U'_{gh},
$$

with

$$
\omega'(g,h)=\omega(g,h)+\beta(g)+\beta(h)-\beta(gh).
$$

A phase of this form is called a **coboundary**. It is a bookkeeping artifact of the choice of representatives $U_g$. A genuinely projective representation is one for which no choice of phases removes $\omega$ everywhere.

:::note[Convention-sensitive source note]
The displayed law uses $U_gU_h=e^{i\omega(g,h)}U_{gh}$. Some references reverse the order because they define group actions on functions by pullback, or use $U(g)^{-1}\mathcal O U(g)$ rather than $U(g)\mathcal O U(g)^{-1}$. The invariant content is the same: associativity gives a two-cocycle, and rephasing gives a coboundary.
:::

## Rays, phases, and observables

Why are phases allowed at all? Because observables are insensitive to the overall phase of a state.

If

$$
|\psi\rangle\mapsto e^{i\lambda}|\psi\rangle,
$$

then for any ordinary expectation value,

$$
\langle\psi|\mathcal O|\psi\rangle
\mapsto
\langle\psi|e^{-i\lambda}\mathcal O e^{i\lambda}|\psi\rangle
=
\langle\psi|\mathcal O|\psi\rangle.
$$

Transition probabilities are also unchanged:

$$
|\langle\phi|\psi\rangle|^2
=
|\langle e^{i\mu}\phi|e^{i\lambda}\psi\rangle|^2.
$$

Therefore a map of physical states cannot distinguish $U_g$ from $e^{i\beta(g)}U_g$.

This does **not** mean all relative phases are unphysical. Phases in interference experiments matter. The point is narrower: the implementation of a symmetry on rays is only defined up to an overall phase for each group element. Projective representation theory asks which leftover phases survive all such choices.

## Ordinary, projective, and central-extension representations

An ordinary representation obeys

$$
U_gU_h=U_{gh}.
$$

A projective representation obeys

$$
U_gU_h=e^{i\omega(g,h)}U_{gh}.
$$

One way to remove the projective law is to enlarge the group. Define a group $\widehat G$ whose elements are pairs $(e^{i\lambda},g)$ with multiplication

$$
(e^{i\lambda},g)(e^{i\mu},h)
=
(e^{i(\lambda+\mu+\omega(g,h))},gh).
$$

Then $U_g$ becomes an ordinary representation of $\widehat G$:

$$
(e^{i\lambda},g)\mapsto e^{i\lambda}U_g.
$$

The extra $U(1)$ factor is central: it commutes with everything. This is why projective representations are often described by central extensions.

The extension viewpoint is useful because it shifts the question from “Why does the representation fail?” to “What is the correct group acting on Hilbert space?” Sometimes the answer is a central extension. Sometimes it is a covering group. Sometimes, especially in field theory, the answer involves background fields, defects, or anomaly inflow.

## Infinitesimal projectivity and central charges

For a connected continuous symmetry, a projective phase can show up in the Lie algebra. With the convention

$$
U(\alpha)=e^{-i\alpha^aQ_a},
$$

an ordinary representation has

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c.
$$

A central extension allows

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c+i\kappa_{ab}\mathbf 1,
$$

where $\kappa_{ab}=-\kappa_{ba}$ is real.

Because $\mathbf 1$ commutes with everything, the Jacobi identity does not create new generators, but it does constrain $\kappa_{ab}$. A shift of generators by constants,

$$
Q_a\mapsto Q_a+c_a\mathbf 1,
$$

changes the central term by a piece proportional to $f_{ab}{}^c c_c$. Such pieces are convention-dependent and can be removed. Nonremovable pieces are genuine central extensions.

A standard nonrelativistic example is the Galilei algebra. Boosts $K_i$ and spatial translations $P_j$ obey

$$
[K_i,P_j]=iM\delta_{ij},
$$

where $M$ is the mass operator. For a single particle, $M=m\mathbf 1$. The mass acts as a central charge. This is not a relativistic QFT example, but it is a clean laboratory for seeing why a central term can be physical.

In QFT, infinite-dimensional symmetry algebras provide especially important examples. Two-dimensional current algebras can have levels, and the Virasoro algebra has central charge $c$. These are not cosmetic constants; they control correlation functions, anomaly coefficients, and universality classes.

## Topological projectivity and covering groups

Not all projective representations come from a central term visible near the identity. Some are global and topological.

The textbook example is rotation symmetry. Integer-spin states give ordinary representations of $SO(3)$. Half-integer-spin states do not. A $2\pi$ rotation is the identity element of $SO(3)$, but on a spin-$1/2$ vector it acts as

$$
U(2\pi)=-1.
$$

As a representation of $SO(3)$ this is projective. As a representation of the double cover

$$
SU(2)\longrightarrow SO(3),
$$

it is ordinary.

This distinction teaches two lessons.

First, the Lie algebra is not enough. The Lie algebras of $SU(2)$ and $SO(3)$ are the same:

$$
\mathfrak{su}(2)\simeq\mathfrak{so}(3).
$$

But the allowed representations are different.

Second, the phrase “the symmetry group is $G$” is physical data, not decoration. Choosing $SU(2)$ rather than $SO(3)$ changes which representations are allowed, which background bundles can be coupled, and which line or defect operators are genuine.

This is one reason the global form of symmetry groups becomes so important in the chapters on background fields, anomalies, gauge theory, and higher-form symmetry.

## Projective representations versus anomalies

Projective representations and anomalies are related, but they are not the same statement.

A projective representation says that the symmetry acts on a Hilbert space up to phases:

$$
U_gU_h=e^{i\omega(g,h)}U_{gh}.
$$

An anomaly says that a symmetry cannot be consistently gauged, or equivalently cannot be coupled to background fields with all the desired consistency conditions. In modern language, an anomaly is often encoded by an invertible theory in one higher dimension whose boundary variation cancels the anomalous variation of the theory of interest.

The relation is clearest in low dimensions and on boundaries. A quantum-mechanical boundary degree of freedom may carry a projective representation of $G$. That projective phase can be the boundary shadow of a higher-dimensional symmetry-protected topological phase. More generally, anomalous symmetry defects may fail to compose like ordinary group elements without extra topological phases.

So the safe rule is:

$$
\text{projective phase}
\neq
\text{anomaly by itself},
$$

but projective phases are one of the simplest ways anomaly data can become visible.

## Superselection caveat

There is a mild but important caveat. The usual argument that the phase $\omega(g,h)$ is independent of the state assumes that arbitrary superpositions of the states under discussion are physically allowed.

If the Hilbert space splits into superselection sectors,

$$
\mathcal H=\bigoplus_s\mathcal H_s,
$$

and states in different sectors cannot be coherently superposed by physical operations, then the projective phase can depend on the sector. This is not a paradox. It means the symmetry data must be specified sector by sector, or the symmetry group must be enlarged to include the central labels.

In QFT, superselection sectors can arise from charges, boundary conditions, topological sectors, gauge constraints, or infinite-volume limits. This is another reason that a slogan like “the symmetry group is $G$” often hides real structure.

## What this preview is preparing you for

Projective representations are the first place where ordinary representation theory becomes quantum representation theory.

They prepare the reader for several later ideas:

| Later idea | Projective preview |
|---|---|
| Spin and spin structures | Spinor fields are ordinary representations of a covering group, not of the naive rotation group. |
| Current algebra | Commutators of current modes can contain central terms. |
| Virasoro symmetry | The central charge $c$ is a central extension of the conformal algebra in two dimensions. |
| ’t Hooft anomalies | Symmetry may compose with extra phase data when background fields or defects are included. |
| SPT boundaries | Boundary degrees of freedom can transform projectively under a symmetry. |
| Higher groups | Symmetry composition may involve lower-form symmetries as extension data. |
| Non-invertible symmetry | Symmetry defects can have fusion data richer than group multiplication. |

The moral is not that every symmetry is projective. The moral is that **symmetry is not merely a set of labels**. It includes how transformations compose on the actual quantum objects of the theory.

## Common pitfalls

**“A projective representation is just an approximate representation.”** No. It is exact on rays. The phase is part of the exact quantum implementation.

**“Overall phases never matter, so projective phases never matter.”** A single overall phase of one state vector is unobservable. A coherent system of phases in the multiplication law of all symmetry operators can be invariant under redefinitions and physically meaningful.

**“Every projective representation signals an anomaly.”** No. A projective representation may simply mean that the honest Hilbert-space symmetry is a central extension or covering group. An anomaly is an obstruction to gauging or background-field consistency.

**“Spinors are ordinary representations of $SO(3)$.”** They are ordinary representations of $SU(2)$, the double cover of $SO(3)$. Treating them as representations of $SO(3)$ makes the representation projective.

**“The Lie algebra determines the symmetry.”** It does not. The Lie algebra misses global form, covering groups, disconnected components, allowed representations, and many anomaly questions.

**“Central terms can always be shifted away.”** Some can. A generator shift $Q_a\mapsto Q_a+c_a\mathbf 1$ removes exact central terms. Nontrivial central extensions remain.

## Relations to other pages

This page closes the Ordinary Global Symmetries chapter by pointing beyond ordinary representation theory.

The next chapter, Noether Currents and Ward Identities, studies how continuous symmetries are represented locally by currents and contact terms. The central-extension viewpoint reappears there in current algebra and Schwinger terms.

Background Fields and Gauging explains the more robust modern diagnostic: couple the symmetry to a background field and ask whether the coupling is consistent. Many anomaly statements are best formulated in that language rather than as mysterious current nonconservation.

Discrete, Spacetime, and Antiunitary Symmetries returns to Wigner's theorem for antiunitary symmetries such as time reversal, where projective actions such as $T^2=\pm1$ become physically important.

CFT and Bootstrap develops the most famous central extension in QFT, the Virasoro algebra, while the low-dimensional symmetry chapter returns to projective and anomalous actions in two-dimensional examples.

## Research status

The basic mathematics of projective representations, central extensions, and covering groups is established.

In modern QFT, the surrounding landscape is active. Projective symmetry actions appear in anomaly inflow, symmetry-protected and symmetry-enriched phases, higher-group symmetries, non-invertible defects, categorical symmetry, and boundary/defect Hilbert spaces. The elementary formulas on this page are therefore not obsolete graduate-course trivia. They are the baby version of a much larger modern story.

## Exercises

### Exercise 1: Associativity and the cocycle condition

Starting from

$$
U_gU_h=e^{i\omega(g,h)}U_{gh},
$$

show that associativity implies

$$
\omega(h,k)+\omega(g,hk)
=
\omega(g,h)+\omega(gh,k)
\quad \mathrm{mod}\,2\pi.
$$

<details><summary><strong>Solution</strong></summary>

Compute the product in two ways:

$$
U_g(U_hU_k)
=U_g(e^{i\omega(h,k)}U_{hk})
=e^{i\omega(h,k)}e^{i\omega(g,hk)}U_{ghk},
$$

while

$$
(U_gU_h)U_k
=(e^{i\omega(g,h)}U_{gh})U_k
=e^{i\omega(g,h)}e^{i\omega(gh,k)}U_{ghk}.
$$

Associativity says the two phases agree modulo $2\pi$.

</details>

### Exercise 2: Rephasing and coboundaries

Let $U'_g=e^{i\beta(g)}U_g$. Derive the transformation law

$$
\omega'(g,h)=\omega(g,h)+\beta(g)+\beta(h)-\beta(gh).
$$

<details><summary><strong>Solution</strong></summary>

Use

$$
U'_gU'_h=e^{i\beta(g)}e^{i\beta(h)}U_gU_h
=e^{i[\beta(g)+\beta(h)+\omega(g,h)]}U_{gh}.
$$

Since $U'_{gh}=e^{i\beta(gh)}U_{gh}$, we have

$$
U_{gh}=e^{-i\beta(gh)}U'_{gh}.
$$

Therefore

$$
U'_gU'_h
=e^{i[\omega(g,h)+\beta(g)+\beta(h)-\beta(gh)]}U'_{gh}.
$$

</details>

### Exercise 3: Spin one-half as a projective representation of rotations

Explain why a spin-$1/2$ state defines a projective representation of $SO(3)$ but an ordinary representation of $SU(2)$.

<details><summary><strong>Solution</strong></summary>

In $SO(3)$, a $2\pi$ rotation is the identity group element. In a spin-$1/2$ representation, the corresponding operator is $-1$, not $+1$. Since $-1$ acts on an isolated ray as the same physical ray, this can be interpreted as a projective representation of $SO(3)$.

The group $SU(2)$ double-covers $SO(3)$. The two elements $+1$ and $-1$ in $SU(2)$ map to the same $SO(3)$ rotation. In $SU(2)$, the element corresponding to a $2\pi$ rotation is not identified with the identity; it is the central element $-1$. The spin-$1/2$ representation is therefore an ordinary linear representation of $SU(2)$.

</details>

### Exercise 4: Removing an exact central term

Suppose

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c+i f_{ab}{}^c c_c\mathbf 1.
$$

Show that the shifted generators

$$
Q'_a=Q_a+c_a\mathbf 1
$$

obey the ordinary algebra

$$
[Q'_a,Q'_b]=if_{ab}{}^cQ'_c.
$$

<details><summary><strong>Solution</strong></summary>

Since $\mathbf 1$ commutes with everything,

$$
[Q'_a,Q'_b]=[Q_a,Q_b].
$$

Using the assumed algebra,

$$
[Q'_a,Q'_b]=if_{ab}{}^cQ_c+i f_{ab}{}^c c_c\mathbf 1
=if_{ab}{}^c(Q_c+c_c\mathbf 1)
=if_{ab}{}^cQ'_c.
$$

So this central term was removable by a constant shift of the generators.

</details>

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, §2.2 and §2.7. The clean graduate-level source for Wigner's theorem, ray representations, projective phases, central terms, and covering groups.
- E. P. Wigner, *Group Theory and Its Application to the Quantum Mechanics of Atomic Spectra*. The foundational source for quantum symmetries as transformations preserving transition probabilities.
- V. Bargmann, “On Unitary Ray Representations of Continuous Groups.” Classic treatment of projective unitary representations and central extensions.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chapters 5–6. Useful for the surrounding operator and symmetry viewpoint, even though the projective-representation formalism is not the main emphasis.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.” Useful later for seeing how ordinary group multiplication is generalized by topological symmetry operators and their fusion.

## Version history

- **2026-06-17:** Initial polished advanced preview for projective representations in the Ordinary Global Symmetries chapter.
