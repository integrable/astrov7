---
title: "Center Symmetry"
description: "Explains center symmetry as a one-form global symmetry of gauge theories, its action on Wilson lines, its dependence on matter and global form, and its role in confinement diagnostics."
sidebar:
  label: "Center Symmetry"
  order: 5
level: Advanced
status: "Polished draft"
source: "Gaiotto–Kapustin–Seiberg–Willett; Aharony–Seiberg–Tachikawa; Polyakov Chs. 3, 5, 7; Srednicki §82; Schwartz §25.2."
topics:
  - center symmetry
  - one-form symmetry
  - Wilson lines
  - confinement
  - Polyakov loop
  - global form of gauge group
canonicalTopics:
  - center-symmetry
  - electric-one-form-symmetry
  - wilson-line-n-ality
  - confinement-order-parameter
  - global-form-of-gauge-group
researchStatus:
  established:
    - "Pure Yang–Mills theory with simply connected gauge group has an electric one-form symmetry given by the center of the gauge group, acting on Wilson lines by their center charge."
    - "The realization of center symmetry is a sharp diagnostic of confinement in pure gauge theory and a structural ingredient in the global definition of gauge theories."
  active:
    - "Center symmetry remains central in modern work on line-operator lattices, mixed anomalies, deconfinement, adjoint QCD, compactification, semiclassics, and generalized symmetry constraints."
---

## Summary

**Center symmetry** is the higher-form symmetry associated with the center of a gauge group. In pure $SU(N)$ Yang–Mills theory, the center is

$$
Z(SU(N))\cong \mathbb Z_N.
$$

Because the gauge bosons transform in the adjoint representation, they are neutral under this center. Wilson lines in representations with nonzero $N$-ality are charged. Thus pure $SU(N)$ Yang–Mills has an electric $\mathbb Z_N$ **one-form** global symmetry.

If $W_R(C)$ is a Wilson line in representation $R$ along a closed curve $C$, and $n_R\in\mathbb Z_N$ is its $N$-ality, then a center-symmetry surface operator $U_k(\Sigma)$ linked with $C$ acts as

$$
U_k(\Sigma)W_R(C)
=
\exp\!\left(\frac{2\pi i\,k\,n_R}{N}\operatorname{Link}(\Sigma,C)\right)
W_R(C).
$$

This is the one-form version of saying that a local operator of charge $q$ transforms by a phase under an ordinary $U(1)$ symmetry.

<figure class="doc-figure" style="--figure-width: 50rem;">

![A surface operator for center symmetry links a Wilson loop and multiplies it by a phase determined by N-ality.](/figures/symmetry-anomalies-topology/center-symmetry-wilson-loop.svg)

<figcaption>

The center one-form symmetry is measured by a topological surface operator $U_k(\Sigma)$. When $\Sigma$ links a Wilson loop $W_R(C)$, the correlator is multiplied by a phase determined by the $N$-ality of $R$.

</figcaption>
</figure>

Center symmetry is important because it detects global data that the local Yang–Mills Lagrangian does not. It controls which Wilson lines are genuine, how the global form of the gauge group is specified, whether fundamental matter explicitly breaks the symmetry, and how confinement is diagnosed in pure gauge theory.

## Prerequisites

Read [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/), [Charged Extended Operators](/symmetry-anomalies-topology/higher-form-generalized-symmetries/charged-extended-operators/), and [Gauging Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/gauging-higher-form-symmetries/) first. You should also know Wilson lines from [Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/) and the idea that line operators can carry one-form charge.

The mathematical prerequisite is elementary representation theory: the center $Z(G)$ of a group $G$, representations, and the fact that central elements act by phases in irreducible representations.

## Core idea

The center of a gauge group is invisible to adjoint fields but visible to Wilson lines.

Let $G=SU(N)$. Its center consists of matrices

$$
z_m=e^{2\pi i m/N}\,1_N,
\qquad m=0,1,\ldots,N-1.
$$

A field in the adjoint representation transforms by conjugation,

$$
X\mapsto z_m X z_m^{-1}=X,
$$

so gauge bosons and other adjoint fields are neutral. A field or Wilson line in the fundamental representation transforms as

$$
\psi\mapsto e^{2\pi i m/N}\psi.
$$

In a theory with no dynamical fundamental matter, this phase cannot be screened by local particles. The charge is carried by line operators. That is why center symmetry is a one-form symmetry, not an ordinary zero-form symmetry: it acts on lines rather than local gauge-invariant operators.

The simplest summary is

$$
\text{center one-form symmetry}
\quad\text{acts on Wilson lines by center charge}.
$$

## Setup and conventions

For a gauge theory with connection $A$, a Wilson line in representation $R$ is

$$
W_R(C)=\operatorname{Tr}_R\,P\exp\!\left(i\oint_C A\right).
$$

For $SU(N)$, the center element $z=e^{2\pi i/N}1_N$ acts on an irreducible representation $R$ by

$$
R(z)=e^{2\pi i n_R/N}\,1_R,
$$

where

$$
n_R\in\mathbb Z_N
$$

is the $N$-ality of $R$. The fundamental representation has $n_R=1$, the antifundamental has $n_R=-1$, and the adjoint has $n_R=0$.

The center one-form topological operator is supported on a closed codimension-two surface $\Sigma$ in four-dimensional spacetime. Its action on a Wilson loop $C$ is determined by the linking number:

$$
U_k(\Sigma)W_R(C)
=
e^{2\pi i k n_R \operatorname{Link}(\Sigma,C)/N}
W_R(C).
$$

:::note[Convention-sensitive normalization]
The sign of the phase depends on orientation conventions for $\Sigma$, $C$, and $\operatorname{Link}(\Sigma,C)$. The invariant statement is that linking with a generator of the center-symmetry surface multiplies a Wilson line by its center character.
:::

## Why it is a one-form symmetry

An ordinary zero-form symmetry acts on local operators. Center symmetry in pure Yang–Mills does not act faithfully on local gauge-invariant operators made from adjoint fields. Those local operators are neutral.

Instead, it acts on Wilson loops. A Wilson loop is one-dimensional, so the symmetry is a one-form symmetry. The associated symmetry operator is codimension two in four dimensions, hence a surface.

This is a perfect example of why higher-form symmetry was introduced. Before the higher-form language, center symmetry was often discussed as a special property of Wilson loops and confinement. The modern language says: it is a global symmetry, but a one-form global symmetry.

This point clarifies an old puzzle. Pure Yang–Mills seems to have a global $\mathbb Z_N$ structure even though all local adjoint fields are neutral. The answer is that the charged objects are not local fields; they are line operators.

## Matter can break center symmetry

Center symmetry exists only if all dynamical matter is neutral under the relevant center subgroup.

In pure $SU(N)$ Yang–Mills, all dynamical fields are adjoint, so the full $\mathbb Z_N$ one-form center symmetry is present.

If fundamental matter is added, the fundamental Wilson line can end on a dynamical fundamental particle. Then the center charge of the line is not conserved. The one-form center symmetry is explicitly broken.

More generally, suppose the dynamical matter representations have center charges contained in a subgroup. The unbroken center one-form symmetry is the subgroup of $Z(G)$ that acts trivially on all dynamical matter fields.

For $SU(N)$ with matter of $N$-ality $m$, the unbroken center subgroup consists of center elements whose phase is trivial on charge $m$. If the matter includes fundamentals, the unbroken subgroup is trivial. If the matter is adjoint, the full $\mathbb Z_N$ survives.

This is the higher-form analogue of explicit symmetry breaking by charged matter.

## Genuine lines and screening

A Wilson line is **genuine** if it can be inserted on a closed curve without being attached to a higher-dimensional surface or endpoint data. Center symmetry acts on genuine Wilson lines.

Screening changes which line charges are conserved. If dynamical matter of the same center charge exists, a Wilson line can end on it or be screened by pair creation. Then the asymptotic line charge is not conserved.

In pure Yang–Mills, adjoint gluons can screen representations that differ by adjoint tensor products. They cannot screen $N$-ality. Thus the conserved electric one-form charge is precisely $N$-ality.

This is why large Wilson loops in different representations are often organized by $N$-ality at long distances rather than by the full highest weight of the representation.

## Global form of the gauge group

The local Lie algebra does not determine center symmetry. The global form of the gauge group matters.

Pure gauge theories locally based on $\mathfrak{su}(N)$ can have gauge group

$$
SU(N)
$$

or

$$
PSU(N)=SU(N)/\mathbb Z_N,
$$

and there are intermediate quotients for groups with suitable centers. The local gluon dynamics is the same, but the set of genuine line operators and one-form symmetries is different.

In the simply connected $SU(N)$ theory, fundamental Wilson lines are genuine and charged under the electric $\mathbb Z_N$ one-form symmetry.

In the $PSU(N)$ theory, fundamental Wilson lines are not genuine Wilson lines of the gauge group. Instead, magnetic line operators and discrete theta choices become essential. The theory has different one-form symmetry data, often described as magnetic rather than electric.

This is why one-form symmetries are part of the global definition of a gauge theory. They are not optional decorations added after the Lagrangian.

:::note[Source note: reading between the lines]
The modern line-operator viewpoint emphasizes that theories with the same gauge algebra can differ by their allowed line operators, mutual locality conditions, and discrete theta angles. Center symmetry is the simplest door into that global classification.
:::

## Confinement and Wilson-loop behavior

In pure Yang–Mills, center symmetry gives a sharp language for confinement.

A large Wilson loop in representation $R$ has expectation value

$$
\langle W_R(C)\rangle.
$$

For a large rectangular loop of spatial size $L$ and time size $T$, its behavior extracts the potential between external probe charges. If

$$
\langle W_R(C)\rangle\sim e^{-\sigma\,\operatorname{Area}(C)},
$$

then the potential grows linearly with separation, and one says the theory has an **area law** for that line. If instead

$$
\langle W_R(C)\rangle\sim e^{-\mu\,\operatorname{Perimeter}(C)},
$$

the line has a **perimeter law**.

For a one-form symmetry, the rough diagnostic is:

| Realization of one-form symmetry | Behavior of charged Wilson loops |
|---|---|
| Unbroken | Area law |
| Spontaneously broken | Perimeter law |

Thus an unbroken electric center one-form symmetry is associated with confinement of external fundamental probes in pure Yang–Mills. A broken electric one-form symmetry is associated with a deconfined or Higgs-like phase for those probes.

This statement is most precise in pure gauge theories and in infinite volume. With dynamical fundamental matter, the center symmetry is explicitly broken, and the Wilson loop can show string breaking rather than a true asymptotic area law.

## Finite temperature and the Polyakov loop

At finite temperature, Euclidean time is compact:

$$
S^1_\beta\times \mathbb R^{d-1},
\qquad
\beta=\frac{1}{T}.
$$

The **Polyakov loop** is the Wilson line wrapping the thermal circle:

$$
P_R(\mathbf x)
=
\operatorname{Tr}_R\,P\exp\!\left(i\int_{S^1_\beta} A_0\,d\tau\right).
$$

In the spatial theory, this object behaves like a local order parameter for the center symmetry obtained by wrapping the one-form symmetry on the thermal circle.

In pure Yang–Mills,

$$
\langle P_{\mathbf N}\rangle=0
$$

in the center-symmetric confined phase, while

$$
\langle P_{\mathbf N}\rangle\ne0
$$

signals center breaking and deconfinement in the infinite-volume limit.

This is one of the most useful practical roles of center symmetry: it turns a thermal confinement question into a symmetry-realization question.

:::caution[Finite-temperature caveat]
The Polyakov loop is a sharp order parameter only when the center symmetry is exact. Dynamical fundamental matter explicitly breaks center symmetry, so $\langle P\rangle$ is no longer protected to vanish, though it can still be a useful diagnostic.
:::

## Center symmetry and higher-form backgrounds

A one-form center symmetry can be coupled to a background two-form gauge field

$$
B_2.
$$

For a finite center symmetry such as $\mathbb Z_N$, this background is globally a discrete two-form gauge field, often represented by cohomological data rather than an ordinary real differential form. Turning on $B_2$ changes which bundles and line operators are allowed and can reveal mixed anomalies.

For $SU(N)$ Yang–Mills, coupling the $\mathbb Z_N$ one-form symmetry to $B_2$ is closely related to allowing $PSU(N)$ bundles with nontrivial obstruction class. This is where center symmetry meets global topology: the background field records the failure of an $SU(N)$ bundle to lift globally in the presence of quotient data.

The theta angle can interact nontrivially with this background. In some theories, shifts of $\theta$ by $2\pi$ combine with transformations of discrete counterterms for $B_2$. This is the source of important mixed anomalies involving center symmetry, time reversal, and CP at special theta angles.

This page only sets the stage; the anomaly pages develop those constraints.

## Center symmetry in common gauge groups

For simply connected compact simple groups, the electric one-form symmetry of pure gauge theory is the center:

| Gauge group | Center | Electric one-form symmetry in pure gauge theory |
|---|---:|---|
| $SU(N)$ | $\mathbb Z_N$ | $\mathbb Z_N$ |
| $Sp(N)$ | $\mathbb Z_2$ | $\mathbb Z_2$ |
| $Spin(2N+1)$ | $\mathbb Z_2$ | $\mathbb Z_2$ |
| $Spin(4N)$ | $\mathbb Z_2\times\mathbb Z_2$ | $\mathbb Z_2\times\mathbb Z_2$ |
| $Spin(4N+2)$ | $\mathbb Z_4$ | $\mathbb Z_4$ |
| $E_6$ | $\mathbb Z_3$ | $\mathbb Z_3$ |
| $E_7$ | $\mathbb Z_2$ | $\mathbb Z_2$ |
| $E_8$, $F_4$, $G_2$ | trivial | none |

This table assumes pure gauge theory with no dynamical matter charged under the center. Matter representations can explicitly break these symmetries to subgroups or eliminate them.

## Center symmetry versus gauge transformations

Center symmetry is not the same as an ordinary local gauge transformation.

Gauge transformations are redundancies. They do not act on physical operators as global symmetries. Center one-form symmetry is a global symmetry because it acts nontrivially on genuine Wilson lines.

A useful mental picture is to think of center symmetry as being generated by a topological surface operator. It is invisible to small local gauge-invariant operators but visible when linked with a line. That linking action is physical.

This resolves the common confusion: “If the center is part of the gauge group, how can it be a global symmetry?” The answer is that the one-form global symmetry is not a constant gauge transformation acting on local fields. It is a topological operation acting on extended operators.

## Example: SU(2)

For $SU(2)$, the center is

$$
Z(SU(2))=\{\pm 1\}\cong \mathbb Z_2.
$$

Representations are labeled by spin $j$. The center element $-1$ acts as

$$
(-1)^{2j}.
$$

Integer-spin representations have trivial center charge. Half-integer representations have nontrivial center charge. In pure $SU(2)$ Yang–Mills, a Wilson loop in the fundamental representation $j=1/2$ is charged under the $\mathbb Z_2$ one-form symmetry.

Adjoint gluons have $j=1$ and cannot screen the fundamental center charge. Therefore the fundamental Wilson line carries the nontrivial one-form charge.

## Example: SU(3)

For $SU(3)$, the center is

$$
Z(SU(3))\cong \mathbb Z_3.
$$

The fundamental representation $\mathbf 3$ has $N$-ality $1$, the antifundamental $\overline{\mathbf 3}$ has $N$-ality $-1$, and the adjoint $\mathbf 8$ has $N$-ality $0$.

In pure $SU(3)$ Yang–Mills, fundamental Wilson loops are charged under the $\mathbb Z_3$ one-form symmetry. Adding dynamical quarks in the fundamental representation explicitly breaks the center symmetry. That is why center symmetry is an exact order parameter in pure Yang–Mills but not in full QCD with dynamical fundamental quarks.

## Common pitfalls

**“The center acts trivially, so it is unphysical.”** It acts trivially on adjoint local fields, but not on Wilson lines. The charged objects are extended.

**“Center symmetry is an ordinary zero-form symmetry.”** In pure gauge theory it is naturally a one-form symmetry because it acts on line operators.

**“Fundamental matter preserves center symmetry.”** Dynamical fundamental matter explicitly breaks the electric center one-form symmetry because fundamental Wilson lines can end on matter.

**“The Lie algebra determines center symmetry.”** It does not. The global form of the gauge group controls the allowed line operators and one-form symmetry data.

**“Area law equals confinement in every theory.”** The Wilson-loop area law is a sharp confinement diagnostic for external probes in pure gauge theory. With dynamical fundamentals, string breaking and explicit center breaking require more careful language.

**“The Polyakov loop is always an exact order parameter.”** It is exact when the relevant center symmetry is exact, such as in pure Yang–Mills. With dynamical fundamental matter, it is still useful but not protected.

## Relations to other pages

[Charged Extended Operators](/symmetry-anomalies-topology/higher-form-generalized-symmetries/charged-extended-operators/) explains why Wilson lines are charged objects for one-form symmetries.

[Gauging Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/gauging-higher-form-symmetries/) explains how gauging center symmetry changes the global form and line-operator spectrum.

[Electric and Magnetic One-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/electric-and-magnetic-one-form-symmetries/) generalizes this page to Maxwell theory, Abelian gauge theory, magnetic symmetries, and Wilson–’t Hooft charge lattices.

[Line-Operator Algebras](/symmetry-anomalies-topology/defects-extended-operators/line-operator-algebras/) studies mutual locality, screening, line fusion, and charge lattices. [Background Fields for Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/background-fields-for-higher-form-symmetries/) explains the two-form backgrounds used to probe center symmetry. [Anomalies](/symmetry-anomalies-topology/anomalies/) and [’t Hooft Anomalies and Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/) develop mixed anomalies involving center symmetry.

## Research status

Center symmetry is established and central to modern gauge theory. Its interpretation as a one-form global symmetry gives a unified language for Wilson loops, confinement diagnostics, global forms, line operators, background two-form fields, and mixed anomalies.

Current research uses center symmetry in many directions: adjoint QCD, deformed Yang–Mills, compactifications, resurgence, semiclassical confinement, thermal deconfinement, lattice studies, generalized anomalies, and symmetry TFT descriptions of gauge-theory global structure.

## Exercises

### Exercise 1: N-ality of tensor powers

In $SU(N)$, the fundamental representation has $N$-ality $1$. What is the $N$-ality of the tensor product of $k$ fundamental representations?

<details><summary><strong>Solution</strong></summary>

The center acts on each fundamental representation by

$$
z=e^{2\pi i/N}.
$$

On a tensor product of $k$ fundamentals, it acts by

$$
z^k=e^{2\pi i k/N}.
$$

Therefore the $N$-ality is

$$
k\mod N.
$$

</details>

### Exercise 2: Adjoint neutrality

Show that the adjoint representation of $SU(N)$ has zero $N$-ality.

<details><summary><strong>Solution</strong></summary>

The adjoint action is by conjugation:

$$
X\mapsto gXg^{-1}.
$$

For a center element $z=e^{2\pi i m/N}1_N$,

$$
X\mapsto zXz^{-1}=X.
$$

Thus every center element acts trivially in the adjoint representation. The adjoint has $N$-ality zero.

</details>

### Exercise 3: Fundamental matter and broken center symmetry

Why does dynamical fundamental matter explicitly break the electric center one-form symmetry of pure $SU(N)$ Yang–Mills?

<details><summary><strong>Solution</strong></summary>

A fundamental Wilson line carries nontrivial center charge. If dynamical fundamental matter exists, the Wilson line can end on a dynamical particle in the fundamental representation. Then center charge can be absorbed at the endpoint, so the line charge is not conserved. A symmetry whose charged operators can end on dynamical objects is explicitly broken.

</details>

### Exercise 4: Polyakov-loop order parameter

In pure Yang–Mills at finite temperature, explain why $\langle P_{\mathbf N}\rangle=0$ in a center-symmetric phase.

<details><summary><strong>Solution</strong></summary>

The fundamental Polyakov loop transforms nontrivially under the center symmetry. If the thermal state is center-invariant, the expectation value must equal its transformed value:

$$
\langle P_{\mathbf N}\rangle
=
e^{2\pi i/N}\langle P_{\mathbf N}\rangle.
$$

For $e^{2\pi i/N}\ne1$, this implies

$$
\langle P_{\mathbf N}\rangle=0.
$$

A nonzero expectation value signals spontaneous breaking of center symmetry in the infinite-volume thermal system.

</details>

### Exercise 5: Center of SU(2)

Classify the $SU(2)$ representations of spin $j=0,\frac12,1,\frac32,2$ by their $\mathbb Z_2$ center charge.

<details><summary><strong>Solution</strong></summary>

The center element $-1$ acts on spin-$j$ by

$$
(-1)^{2j}.
$$

Thus integer spins $j=0,1,2$ have trivial center charge, while half-integer spins $j=\frac12,\frac32$ have nontrivial center charge.

</details>

## References

- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” for the modern one-form symmetry interpretation of center symmetry.
- Ofer Aharony, Nathan Seiberg, and Yuji Tachikawa, “Reading Between the Lines of Four-Dimensional Gauge Theories,” for global forms, line operators, and discrete theta choices.
- Anton Kapustin and Nathan Seiberg, “Coupling a QFT to a TQFT and Duality,” for center backgrounds, topological couplings, and duality.
- Mark Srednicki, *Quantum Field Theory*, §82, for Wilson loops, lattice gauge theory, and confinement orientation.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, §25.2, for gauge invariance and Wilson lines in Yang–Mills theory.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on strong coupling, compact gauge systems, confinement criteria, and loop dynamics.

## Version history

- **2026-06-20:** Initial polished draft. Added center one-form symmetry, Wilson-line $N$-ality, screening, global-form dependence, confinement diagnostics, Polyakov loops, backgrounds, examples, and exercises.
