---
title: "Charged Extended Operators"
description: "Explains the extended operators charged under higher-form symmetries: Wilson lines, ’t Hooft lines, surface operators, strings, branes, endpoints, screening, and linking tests."
sidebar:
  label: "Charged Extended Operators"
  order: 2
level: Advanced
status: "Polished draft"
source: "Gaiotto–Kapustin–Seiberg–Willett; Aharony–Seiberg–Tachikawa; Kapustin–Seiberg; Polyakov Ch. 7; Srednicki §82; Schwartz §25.2."
topics:
  - higher-form symmetry
  - charged extended operators
  - Wilson lines
  - ’t Hooft lines
  - surface operators
  - screening
  - linking
canonicalTopics:
  - charged-extended-operator
  - genuine-line-operator
  - higher-form-charge
  - linking-ward-identity
researchStatus:
  established:
    - "Charged extended operators are the operational probes of higher-form global symmetry, especially in gauge theory, topological field theory, and theories with line and surface defects."
    - "Whether an extended operator is genuine, screened, or allowed to end is part of the symmetry data of the theory."
  active:
    - "In non-invertible, categorical, fermionic, and gravitational settings the notion of charge can require more refined defect and boundary-condition data."
---

## Summary

A **charged extended operator** is an operator supported on an extended submanifold that transforms under a higher-form global symmetry. For a $q$-form symmetry in $d$ spacetime dimensions, the charged operators are $q$-dimensional:

$$
\text{$q$-form symmetry}
\quad\text{acts on}\quad
W_q(M^q).
$$

The symmetry is measured by a topological operator on a closed manifold of complementary dimension,

$$
U_g(\Sigma^{d-q-1}).
$$

The action is detected when $\Sigma$ links or crosses $M$:

$$
U_g(\Sigma)\,W_q(M)
=
\chi_W(g;\operatorname{Link}(\Sigma,M))\,W_q(M),
$$

in simple Abelian examples. The character $\chi_W$ is the higher-form analogue of a phase $e^{iq\alpha}$ for an ordinary charged local operator.

The central lesson is that the charged objects of higher-form symmetry are usually **not particles**. They are Wilson lines, ’t Hooft lines, surface defects, strings, domain walls, branes, flux operators, or other extended insertions. They can carry conserved charges even when no local operator does.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A schematic showing a topological symmetry operator linking a charged extended operator, with examples of local, line, and surface charged operators.](/figures/symmetry-anomalies-topology/charged-extended-operators-linking.svg)

<figcaption>

A $q$-dimensional charged operator $W_q(M)$ is measured by a topological operator $U_g(\Sigma)$ on a closed codimension-$q+1$ manifold. The Ward identity is the statement that $U_g(\Sigma)$ can be deformed freely until it links or crosses $M$.

</figcaption>
</figure>

This page explains what counts as charged, why endpoints matter, how screening breaks or reduces higher-form symmetry, and how familiar line and surface operators fit into the general picture.

## Prerequisites

Read [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) first. You should also know the Defects and Extended Operators chapter, especially Wilson lines, ’t Hooft lines, surface operators, defect fusion, and line-operator algebras.

The only geometric idea needed here is **linking**. A closed symmetry operator detects an extended charged operator if it cannot be moved away without crossing it. In $d=4$, for example, a closed two-surface can link a line operator.

## Core idea

The ordinary charge of a local operator can be detected by surrounding it with a sphere or by moving a codimension-one symmetry defect past it. Higher-form charge works the same way, but the charged object has positive dimension.

For a one-form symmetry in four spacetime dimensions, the charged object is a line operator $W(C)$, and the symmetry operator is a closed surface $U(\Sigma)$. If $\Sigma$ links $C$ once, the line picks up its one-form charge.

For a two-form symmetry in four dimensions, the charged object is a surface operator $V(S)$, and the symmetry operator is a closed line $U(\gamma)$. Again the action is measured by linking.

This changes the grammar of symmetry. Instead of asking only

$$
\text{What local fields carry charge?}
$$

one must ask

$$
\text{What genuine extended operators carry charge, and what topological operators measure them?}
$$

That question is often the cleanest way to distinguish phases of gauge theories, global forms of gauge groups, and topological sectors.

## Setup and conventions

A charged extended operator will be denoted

$$
W_q(M^q),
$$

where $M^q$ is its $q$-dimensional support in spacetime. The letter $W$ is suggestive of Wilson operators, but the notation is generic.

A topological symmetry operator for a $q$-form symmetry is denoted

$$
U_g(\Sigma^{d-q-1}),
$$

where $\Sigma$ is closed unless a boundary condition or endpoint is explicitly part of the construction.

For an Abelian group-like symmetry, a common model action is

$$
U_\alpha(\Sigma)W_n(M)
=
e^{i\alpha n\,\operatorname{Link}(\Sigma,M)}W_n(M),
$$

inside correlation functions. Here $n$ is the higher-form charge of $W_n$, and $\operatorname{Link}(\Sigma,M)$ is an integer linking number when the dimensions and topology allow it.

For a finite $\mathbb Z_N$ one-form symmetry, the same formula is often written as

$$
U_k(\Sigma)W_n(M)
=
\exp\!\left(\frac{2\pi i kn}{N}\operatorname{Link}(\Sigma,M)\right)W_n(M),
$$

with charges understood modulo $N$.

:::note[Source note]
The modern generalized-symmetry convention is that a $q$-form symmetry acts on $q$-dimensional operators. The original generalized-global-symmetry paper emphasizes Wilson lines, surface defects, strings, membranes, Ward identities, background fields, gauging, and ’t Hooft anomalies as parallel to the ordinary $q=0$ story.
:::

## Genuine extended operators

Not every formal line or surface written in a Lagrangian is a genuine operator of the QFT.

A **genuine operator** can be inserted on a closed support without requiring an arbitrary auxiliary surface, branch cut, or choice of endpoint. Equivalently, its definition is intrinsic once its support is specified.

A Wilson loop in a pure gauge theory is a genuine line operator:

$$
W_R(C)=\operatorname{Tr}_R\,P\exp\!\left(i\oint_C A\right),
$$

assuming $C$ is closed and $R$ is an allowed representation. In a theory with dynamical matter, some Wilson lines can end on dynamical charged fields. Those lines are no longer conserved probes of a one-form symmetry in the same way.

A line operator with an endpoint is still a useful object, but its endpoint data is part of the operator. For example, a Wilson line ending on a charged field is a composite object: the line plus endpoint insertion. If all lines carrying a proposed charge can end on dynamical objects, the corresponding one-form symmetry is explicitly broken or screened.

The slogan is:

$$
\text{one-form charge is conserved only for genuine unscreened line operators}.
$$

The same principle applies to surface operators and higher-dimensional charged objects.

## Wilson lines as charged objects

Wilson lines are the canonical charged operators for electric one-form symmetries. In a gauge theory with connection $A$, a Wilson line along a closed curve $C$ in representation $R$ is

$$
W_R(C)=\operatorname{Tr}_R\,P\exp\!\left(i\oint_C A\right).
$$

A center one-form symmetry acts on Wilson lines by their center charge. For $SU(N)$ pure Yang–Mills, the center is $\mathbb Z_N$. If $R$ has $N$-ality $n_R$, then a generator of the center one-form symmetry acts as

$$
W_R(C)\mapsto e^{2\pi i n_R/N}W_R(C).
$$

Equivalently, a topological surface operator $U_k(\Sigma)$ linked with $C$ gives

$$
U_k(\Sigma)W_R(C)
=
e^{2\pi i k n_R\,\operatorname{Link}(\Sigma,C)/N}W_R(C).
$$

This is a higher-form selection rule in its simplest gauge-theory form.

If fundamental dynamical matter is present, a fundamental Wilson line can end on matter. The center one-form symmetry is then explicitly broken: the line charge is no longer conserved because the endpoint can absorb it.

:::caution[Wilson lines and global form]
The allowed set of Wilson lines depends on the global form of the gauge group, not only on the Lie algebra. The theories often called $SU(N)$ and $PSU(N)=SU(N)/\mathbb Z_N$ have the same local gauge algebra but different genuine line operators and different one-form symmetry data.
:::

## ’t Hooft lines and magnetic charge

An ’t Hooft line is a magnetic disorder line. It is not defined by a polynomial in fields along the line. Instead, it specifies a singular boundary condition for gauge fields near the line. Around a small linking two-sphere, the field has prescribed magnetic flux.

In four-dimensional Maxwell theory, a magnetic line of charge $m$ can be detected by an electric or magnetic higher-form symmetry operator depending on the convention and choice of duality frame. In non-Abelian gauge theory, ’t Hooft lines are labeled by magnetic weights subject to identifications by the Weyl group and by the allowed global form of the gauge group.

The important structural point is this:

$$
\text{Wilson lines measure electric data},\qquad
\text{’t Hooft lines impose magnetic data}.
$$

Both can be charged under one-form symmetries. Wilson–’t Hooft lines carry both electric and magnetic labels,

$$
(e,m).
$$

Their mutual locality, braiding phases, and allowed charge lattice are part of the line-operator algebra of the theory.

This is why line operators remember global information invisible in the local Lagrangian density.

## Surface operators and higher-dimensional charges

A two-form symmetry acts on surface operators. In four spacetime dimensions, the charged operator is supported on a two-dimensional surface $S$ and the topological symmetry operator is supported on a closed line $\gamma$.

Surface operators arise in several ways:

- as exponentials of integrals of two-form gauge fields,
- as defects imposing monodromy or flux singularities,
- as worldsheet insertions for stringlike charged objects,
- as symmetry defects in lower-dimensional theories,
- as topological surface observables in TQFTs.

For an Abelian two-form symmetry with surface charge $n$, one may have a schematic action

$$
U_\alpha(\gamma)V_n(S)
=
e^{i\alpha n\,\operatorname{Link}(\gamma,S)}V_n(S).
$$

The linking number is now between a closed line and a closed surface in four dimensions.

The same pattern extends to higher dimensions. A $q$-form symmetry acts on $q$-dimensional operators, and the measuring operator has support dimension $d-q-1$.

## Charged excitations versus charged operators

The generalized-symmetry literature distinguishes charged **operators** from charged **excitations**.

A charged operator is an insertion in a correlation function. A charged excitation is a state or object in the spectrum. For ordinary zero-form symmetry, a charged local operator may create a charged particle. For higher-form symmetry, a charged line operator may represent the worldline of an external probe particle, while a charged excitation may be a string, brane, flux tube, or domain-wall object.

This distinction matters because a probe operator need not correspond to a dynamical object in the spectrum. A Wilson line in a pure gauge theory can be an external probe even if there is no dynamical fundamental quark. Conversely, a dynamical string can appear in the spectrum and be charged under a two-form symmetry.

A safe rule:

$$
\text{operators probe symmetry; dynamical excitations populate the theory}.
$$

Both can carry higher-form charges, but they play different roles.

## Endpoints, screening, and explicit breaking

A higher-form charge is conserved only if charged extended operators cannot simply end on allowed dynamical objects.

For a one-form symmetry, a charged line cannot end in the vacuum. If it can end on a local operator $\mathcal O(x)$, then the endpoint absorbs the line’s charge. The symmetry is explicitly broken or reduced.

For example, in pure $SU(N)$ Yang–Mills, fundamental Wilson lines are genuine probe lines and carry $\mathbb Z_N$ center charge. With dynamical fundamental quarks, the fundamental Wilson line can end on a quark field. The center one-form symmetry is then broken by the matter content.

Screening can also reduce a symmetry rather than destroy it completely. If dynamical matter has charge $k$ under a putative $U(1)$ or $\mathbb Z_N$ one-form symmetry, then only charges modulo the screened subgroup remain conserved.

The same logic applies to magnetic lines. Dynamical monopoles can screen magnetic one-form charges. Dynamical strings can screen two-form charges.

:::note[Endpoint diagnostic]
To test whether a line operator carries a conserved one-form charge, ask whether there exists a genuine endpoint operator allowed by the theory. If yes, the charge is not conserved. If no, the line may be charged under an exact one-form symmetry.
:::

## Selection rules for extended operators

Higher-form symmetry gives selection rules for extended-operator correlators.

Consider line operators $W_{n_i}(C_i)$ charged under a finite $\mathbb Z_N$ one-form symmetry. Insert a topological surface $U_k(\Sigma)$. If $\Sigma$ can be moved away and removed, then

$$
\left\langle \prod_i W_{n_i}(C_i)\right\rangle
=
\exp\!\left(\frac{2\pi i k}{N}\sum_i n_i\,\operatorname{Link}(\Sigma,C_i)\right)
\left\langle \prod_i W_{n_i}(C_i)\right\rangle.
$$

For a nonzero correlator, the phase must be one for every allowed $k$ and every allowed $\Sigma$:

$$
\sum_i n_i\,\operatorname{Link}(\Sigma,C_i)=0\mod N.
$$

This is not ordinary charge conservation in space. It is conservation tested by linking. It constrains which networks of lines and surfaces can have nonzero expectation values and which endpoints or junctions are allowed.

In topological theories, these selection rules become algebraic constraints on fusion and braiding. In ordinary QFT, they are often used as robust diagnostics of phases and of explicit symmetry breaking.

## Generalized order parameters

Charged extended operators often serve as generalized order parameters.

For ordinary zero-form symmetry, an order parameter is often a local operator $\mathcal O(x)$ whose expectation value distinguishes phases. For one-form symmetry, an order parameter is often a line operator. Its large-size expectation value can obey perimeter, area, or volume laws.

For a Wilson loop $W(C)$, one often studies

$$
\langle W(C)\rangle
$$

for a large loop $C$. In gauge theory, area-law or perimeter-law behavior diagnoses confinement, screening, and one-form symmetry realization. The precise interpretation depends on dimension, matter content, and which line is being tested.

For a one-form symmetry:

- unbroken one-form symmetry often corresponds to an area law for charged lines in appropriate settings,
- broken one-form symmetry often corresponds to a perimeter law,
- explicit breaking occurs if charged lines can end.

This is a useful analogy, not a universal theorem without assumptions. The Generalized Symmetry Breaking page treats the phase diagnostics more carefully.

## Examples

### Maxwell theory in four dimensions

Free Maxwell theory in four dimensions has electric and magnetic one-form symmetries in the absence of electric and magnetic charges. The field strength $F$ and its Hodge dual $*F$ define conserved two-form currents:

$$
dF=0,\qquad d{*F}=0.
$$

Wilson lines are electrically charged, and ’t Hooft lines are magnetically charged. The symmetry operators can be written as flux operators on closed two-surfaces:

$$
U_e(\Sigma)=\exp\!\left(i\alpha\int_\Sigma {*F}\right),
\qquad
U_m(\Sigma)=\exp\!\left(i\beta\int_\Sigma F\right).
$$

Dynamical electric charges break or screen the electric one-form symmetry. Dynamical magnetic monopoles break or screen the magnetic one-form symmetry.

### Pure Yang–Mills theory

Pure $SU(N)$ Yang–Mills has a $\mathbb Z_N$ center one-form symmetry acting on Wilson lines by their $N$-ality. The fundamental Wilson line is charged. Adjoint Wilson lines are neutral because their $N$-ality is zero.

This symmetry is central to confinement diagnostics: a charged Wilson loop can distinguish phases through its large-loop behavior.

### Gauge theory with matter

If matter fields transform in the fundamental representation, the fundamental Wilson line can end on a dynamical field. The center one-form symmetry is explicitly broken. If matter only transforms in representations of $N$-ality divisible by $k$, a subgroup of the center one-form symmetry may remain.

This shows that higher-form symmetry depends on the spectrum of genuine charged operators, not merely on the gauge algebra.

## Common pitfalls

**“Every Wilson line is charged.”** Only Wilson lines with nontrivial charge under the relevant one-form symmetry are charged. Adjoint Wilson lines may be neutral under center symmetry.

**“A line that can end still carries conserved one-form charge.”** If the endpoint is a genuine allowed operator, the line charge is not conserved as a standalone one-form charge.

**“Higher-form charged objects must be dynamical branes.”** Probe operators and dynamical excitations are different. Both can carry charges, but a symmetry can be detected using external probe operators.

**“The local Lagrangian determines all higher-form charges.”** It often does not. The global form of the gauge group, allowed line operators, matter content, spin structure, and boundary conditions can change the answer.

**“Linking formulas are always just phases.”** Simple Abelian group-like symmetries act by phases. Non-Abelian, non-invertible, and categorical generalizations can act on vector spaces of defect states or fuse into sums of defects.

**“A charged extended operator is the same as a topological operator.”** Not necessarily. Charged operators need not be topological. Symmetry operators are topological; charged probes may have metric-dependent expectation values.

## Relations to other pages

[Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) gives the general definition. This page explains the charged objects that appear in that definition.

[Background Fields for Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/background-fields-for-higher-form-symmetries/) explains how to couple these charges to $(q+1)$-form background gauge fields. [Gauging Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/gauging-higher-form-symmetries/) explains what changes when those backgrounds are summed over. [Center Symmetry](/symmetry-anomalies-topology/higher-form-generalized-symmetries/center-symmetry/) develops the most important gauge-theory example.

The Defects and Extended Operators chapter supplies the operator vocabulary. The Line-Operator Algebras page explains mutual locality, charge lattices, and electric/magnetic labeling in more detail.

## Research status

The role of Wilson lines, ’t Hooft lines, surface operators, and other extended insertions as charged objects under higher-form symmetries is now standard in modern QFT.

Active refinements include non-invertible actions on line and surface categories, higher-group mixing between ordinary and higher-form symmetries, fermionic higher-form symmetry, symmetry TFT descriptions, and the fate of generalized global symmetries in quantum gravity. In those settings, “charge” may no longer be just an additive label; it can be a representation of a fusion category, a boundary condition in a higher-dimensional topological theory, or a more subtle object.

## Exercises

### Exercise 1: Linking dimension

In $d=4$, what is the dimension of the topological symmetry operator that measures a one-form charge? What kind of charged operator does it act on?

<details><summary><strong>Solution</strong></summary>

For a $q$-form symmetry in $d$ dimensions, the topological symmetry operator has support dimension

$$
d-q-1.
$$

With $d=4$ and $q=1$, this is

$$
4-1-1=2.
$$

So a one-form symmetry in four dimensions is measured by a closed surface operator. It acts on one-dimensional charged operators, such as Wilson or ’t Hooft lines.

</details>

### Exercise 2: Center charge of products

In pure $SU(N)$ Yang–Mills, suppose $W_R$ has $N$-ality $n_R$ and $W_S$ has $N$-ality $n_S$. What is the center one-form charge of a product line behaving like $W_R W_S$?

<details><summary><strong>Solution</strong></summary>

Center charges add modulo $N$. If a generator of the center acts as

$$
W_R\mapsto e^{2\pi i n_R/N}W_R,
\qquad
W_S\mapsto e^{2\pi i n_S/N}W_S,
$$

then the product transforms as

$$
W_R W_S\mapsto e^{2\pi i(n_R+n_S)/N}W_R W_S.
$$

The charge is therefore

$$
n_R+n_S\mod N.
$$

</details>

### Exercise 3: Endpoint test

Explain why adding dynamical fundamental matter to pure $SU(N)$ Yang–Mills breaks the $\mathbb Z_N$ center one-form symmetry.

<details><summary><strong>Solution</strong></summary>

In the pure theory, a fundamental Wilson line is a genuine closed line operator carrying nontrivial center charge. With dynamical fundamental matter, an open fundamental Wilson line can end on a dynamical charged field. The endpoint absorbs the center charge. Therefore the charge of a fundamental line is no longer conserved as a one-form charge, and the center one-form symmetry is explicitly broken.

</details>

### Exercise 4: Charged versus topological

Can a Wilson loop be charged under a one-form symmetry without itself being topological?

<details><summary><strong>Solution</strong></summary>

Yes. The topological operator is the symmetry operator $U_g(\Sigma)$ that measures the one-form charge. The Wilson loop $W(C)$ is the charged operator. Its expectation value can depend on the size, shape, and metric properties of $C$, for example through an area law or perimeter law. It need not be topological to be charged.

</details>

## References

- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the modern definition of higher-form symmetry and charged extended operators.
- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality,” for global-form and background-field refinements.
- O. Aharony, N. Seiberg, and Y. Tachikawa, “Reading Between the Lines of Four-Dimensional Gauge Theories,” for line operators and global choices in four-dimensional gauge theories.
- A. M. Polyakov, *Gauge Fields and Strings*, especially Ch. 7 on non-Abelian phase factors and loop dynamics.
- M. Srednicki, *Quantum Field Theory*, §82, for Wilson loops and confinement orientation.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, §25.2, for Wilson lines in Yang–Mills theory.

## Version history

- 2026-06-20: Initial polished draft. Added charged extended operator definitions, genuine-operator diagnostics, Wilson/’t Hooft/surface examples, endpoint screening, linking selection rules, and exercises.
