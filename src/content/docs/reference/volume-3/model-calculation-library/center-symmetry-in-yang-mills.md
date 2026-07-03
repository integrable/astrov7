---
title: "Center Symmetry in Yang–Mills"
description: "A model calculation deriving the electric center one-form symmetry of pure Yang–Mills theory, its action on Wilson loops, N-ality, screening, and confinement diagnostics."
sidebar:
  label: "Center Symmetry in Yang–Mills"
  order: 13
level: Graduate
status: "Polished draft"
source: "Gaiotto–Kapustin–Seiberg–Willett 2015; Srednicki §§69–70 and §82; Polyakov Chs. 3, 5, and 7; Schwartz Ch. 25."
topics:
  - center symmetry
  - Yang–Mills theory
  - Wilson loops
  - one-form symmetry
  - confinement
  - N-ality
canonicalTopics:
  - center-symmetry
  - yang-mills-theory
  - wilson-loop
  - one-form-symmetry
  - n-ality
  - model-calculation
researchStatus:
  established:
    - "Pure Yang–Mills theory with simply connected gauge group SU(N) has a Z_N electric one-form center symmetry acting on Wilson loops by their N-ality."
    - "The area law for fundamental Wilson loops is the standard confinement diagnostic associated with an unbroken electric center one-form symmetry."
  active:
    - "Precise symmetry data depend on the global form of the gauge group, allowed line operators, theta angles, matter content, finite-temperature boundary conditions, and possible mixed anomalies."
---

## Summary

Pure $SU(N)$ Yang–Mills theory has a discrete electric one-form global symmetry,

$$
\mathbb Z_N^{(1)}.
$$

It is called **center symmetry** because it comes from the center of the gauge group,

$$
Z(SU(N))=\{e^{2\pi i m/N}1_N\mid m=0,\ldots,N-1\}\cong\mathbb Z_N.
$$

Its charged operators are Wilson loops. A Wilson loop in representation $R$,

$$
W_R(C)=\operatorname{tr}_R\,\mathcal P\exp\left(i\oint_C A\right),
$$

has a charge called its **N-ality**. If a representation has $k_R$ boxes modulo $N$ in its Young tableau, then the center acts by

$$
z\cdot W_R(C)=z^{k_R}W_R(C),
\qquad z=e^{2\pi i/N}.
$$

The one-form symmetry operator is supported on a closed two-surface $\Sigma$ in four spacetime dimensions. If $\Sigma$ links the loop $C$, then

$$
U_z(\Sigma)W_R(C)=z^{k_R\,\operatorname{Link}(\Sigma,C)}W_R(C).
$$

This is the cleanest model calculation showing how a generalized global symmetry acts on extended operators.

<figure class="doc-figure" style="--figure-width: 42rem;">

![A closed center-symmetry surface linking a Wilson loop and multiplying it by a phase determined by N-ality.](/figures/symmetry-anomalies-topology/center-symmetry-yang-mills.svg)

<figcaption>

The center one-form symmetry in pure $SU(N)$ Yang–Mills is measured by a topological surface operator $U_z(\Sigma)$. When $\Sigma$ links a Wilson loop $W_R(C)$, the loop picks up the phase $z^{k_R}$, where $k_R$ is the N-ality of the representation.

</figcaption>
</figure>

The same symmetry is also a precise way to say why adjoint gluons cannot screen a fundamental Wilson loop, why fundamental matter explicitly breaks the center symmetry, and why the Wilson-loop area law is an order parameter for confinement in pure Yang–Mills theory.

## Prerequisites

You should know the pages on Wilson loops, one-form symmetry in Maxwell theory, center symmetry, and Wilson-loop area laws. You should also know the basic Yang–Mills connection

$$
A=A_\mu dx^\mu=A_\mu^aT_a dx^\mu
$$

and Wilson loops in representation $R$.

We use compact gauge group $SU(N)$ unless stated otherwise. The distinction between the Lie algebra $\mathfrak{su}(N)$ and the global group $SU(N)$, $PSU(N)=SU(N)/\mathbb Z_N$, or other quotients is not decorative here; it changes the line operators and the one-form symmetry.

## Setup

Pure Yang–Mills theory has action

$$
S_{\rm YM}
=
-\frac{1}{2g^2}\int \operatorname{tr}(F\wedge {*F})
$$

in Lorentzian signature, up to the convention-dependent theta term. The field strength is

$$
F=dA+iA\wedge A
$$

for Hermitian gauge fields in the convention used in this volume.

The Wilson loop in representation $R$ is

$$
W_R(C)=\operatorname{tr}_R\,\mathcal P\exp\left(i\oint_C A\right).
$$

The holonomy

$$
\mathcal P\exp\left(i\oint_C A\right)
$$

is an element of $SU(N)$ in representation $R$. A center element $z1_N$ commutes with all group elements, so in an irreducible representation $R$ it acts as a scalar by Schur’s lemma:

$$
R(z1_N)=z^{k_R}1_R.
$$

The integer

$$
k_R\in\mathbb Z_N
$$

is the N-ality of $R$.

For the fundamental representation,

$$
k_{\mathbf N}=1.
$$

For the antifundamental,

$$
k_{\overline{\mathbf N}}=-1\mod N.
$$

For the adjoint,

$$
k_{\operatorname{Adj}}=0.
$$

This last fact is the reason gluons do not screen N-ality.

:::note[Source note]
In ordinary particle-physics language, center symmetry is often introduced as a transformation of temporal Wilson lines at finite temperature. In generalized-symmetry language, it is an electric one-form symmetry acting on Wilson lines in spacetime. The finite-temperature center symmetry is the dimensional reduction of this one-form symmetry along the thermal circle.
:::

## The one-form symmetry action

For a $q$-form symmetry in $d$ spacetime dimensions, the symmetry operator is supported on a codimension-$q+1$ manifold. Here $q=1$ and $d=4$, so the center-symmetry operator is supported on a closed two-surface,

$$
U_z(\Sigma_2).
$$

The operator is topological: moving $\Sigma_2$ without crossing charged line operators does not change correlation functions. If it crosses or links a Wilson line, it acts by a center phase.

The defining Ward identity is

$$
U_z(\Sigma_2)W_R(C)
=
z^{k_R\,\operatorname{Link}(\Sigma_2,C)}
W_R(C)U_z(\Sigma_2).
$$

Here

$$
\operatorname{Link}(\Sigma_2,C)\in\mathbb Z
$$

is the linking number in four-dimensional spacetime. This equation is the higher-form analogue of

$$
U_g\mathcal O_qU_g^{-1}=e^{iq\alpha}\mathcal O_q
$$

for an ordinary $U(1)$ symmetry acting on a local charged operator.

The phase depends only on topology, not on a metric or local shape. That is why the surface operator is a symmetry operator.

## N-ality and tensor products

The N-ality is additive under tensor products. If $R$ and $S$ have N-alities $k_R$ and $k_S$, then

$$
k_{R\otimes S}=k_R+k_S\mod N.
$$

A Wilson loop in $R\otimes S$ therefore has center charge

$$
z^{k_R+k_S}.
$$

Representations built from $n$ fundamental indices and $\bar n$ antifundamental indices have

$$
k_R=n-\bar n\mod N.
$$

For example, for $SU(3)$:

| Representation | Common name | N-ality |
|---|---|---:|
| $\mathbf 1$ | singlet | $0$ |
| $\mathbf 3$ | fundamental | $1$ |
| $\overline{\mathbf 3}$ | antifundamental | $2$ |
| $\mathbf 8$ | adjoint | $0$ |
| $\mathbf 6$ | symmetric two-index | $2$ |
| $\mathbf{10}$ | symmetric three-index | $0$ |

An operator with zero N-ality is neutral under the center one-form symmetry. An operator with nonzero N-ality is charged.

## Screening

Screening means that a line operator can be modified or neutralized by attaching dynamical charged particles.

In pure Yang–Mills theory, the dynamical fields are gluons. They transform in the adjoint representation, so they have N-ality zero. Gluons can screen Wilson lines within the same N-ality class, but they cannot change N-ality.

For example, in pure $SU(N)$ Yang–Mills, a Wilson loop in a complicated representation $R$ can mix at long distance with the lowest-tension string carrying the same N-ality $k_R$. But it cannot be screened all the way to the vacuum unless

$$
k_R=0.
$$

If we add dynamical fundamental quarks, the situation changes. Fundamental matter has N-ality one. Then a fundamental Wilson line can end on a dynamical quark worldline. The center one-form symmetry is explicitly broken:

$$
\mathbb Z_N^{(1)}\quad\text{is absent with dynamical fundamentals.}
$$

This is a good test of the definition. A one-form symmetry exists only when charged lines cannot end on dynamical local operators.

:::caution[Gauge group versus matter content]
The phrase “Yang–Mills with gauge algebra $\mathfrak{su}(N)$” is not enough to determine the one-form symmetry. You must specify the global gauge group and which dynamical matter representations are present.
:::

## Area law and confinement

For a large rectangular Wilson loop $C_{R,T}$ of spatial size $R$ and time size $T$,

$$
\langle W(C_{R,T})\rangle\sim e^{-T V(R)}
$$

defines the static potential $V(R)$. An area law

$$
\langle W(C_{R,T})\rangle\sim e^{-\sigma RT}
$$

implies

$$
V(R)\sim \sigma R.
$$

For a fundamental Wilson loop in pure Yang–Mills, this is the usual confinement diagnostic. In generalized-symmetry language, the area law is the diagnostic of an unbroken electric center one-form symmetry.

The rough dictionary is:

| Behavior of large Wilson loop | Static potential | Electric center one-form symmetry |
|---|---|---|
| Area law | $V(R)\sim \sigma R$ | unbroken |
| Perimeter law | screened or Coulombic behavior | broken or not a good exact symmetry diagnostic |
| String breaking | line can end on dynamical matter | center one-form explicitly broken |

The last row matters. In QCD with dynamical fundamental quarks, a fundamental Wilson loop can show string breaking rather than a strict asymptotic area law. That does not mean pure-glue confinement was fake. It means the exact one-form symmetry order parameter is gone.

## Finite temperature and the Polyakov loop

At finite temperature, Euclidean time is compact:

$$
\tau\sim \tau+\beta,\qquad \beta=\frac{1}{T}.
$$

The temporal Wilson line wrapping the thermal circle is the Polyakov loop,

$$
P(\mathbf x)=\operatorname{tr}_{\mathbf N}\,\mathcal P\exp\left(i\int_0^\beta A_\tau(\tau,\mathbf x)\,d\tau\right).
$$

It is charged under the center symmetry. At finite temperature, the center one-form symmetry can be viewed as producing an ordinary zero-form symmetry acting on wrapped line operators in the dimensionally reduced thermal theory.

In pure Yang–Mills, the expectation value

$$
\langle P\rangle
$$

is an order parameter for deconfinement:

| Phase | Center behavior | Polyakov loop |
|---|---|---|
| Confined low-temperature phase | unbroken center | $\langle P\rangle=0$ |
| Deconfined high-temperature phase | broken center | $\langle P\rangle\neq0$ |

This statement assumes pure gauge theory. With dynamical fundamental quarks, the center symmetry is explicitly broken and $\langle P\rangle$ is no longer an exact order parameter.

## Global form and magnetic one-form symmetry

So far we assumed the gauge group is $SU(N)$. If instead the gauge group is

$$
PSU(N)=SU(N)/\mathbb Z_N,
$$

then fundamental Wilson lines are not genuine Wilson lines of the gauge theory. The allowed line operators and the one-form symmetry change.

A useful slogan is:

$$
\text{global form of gauge group}
\quad\Longleftrightarrow\quad
\text{choice of genuine line operators}.
$$

The $SU(N)$ theory has an electric $\mathbb Z_N^{(1)}$ center symmetry acting on Wilson lines. The $PSU(N)$ theory instead has different electric/magnetic one-form symmetry data, often described in terms of magnetic lines and discrete theta choices.

This is why center symmetry is not just a cute observation about matrices. It is part of the global definition of the gauge theory.

## Relation to gauge transformations

A common confusion is to think that center symmetry is just a gauge transformation. It is not an ordinary gauge redundancy acting trivially on physical operators.

Gauge transformations that are single-valued and continuously connected to the identity act redundantly. Center one-form transformations are better understood as topological operations that act nontrivially on Wilson loops according to their linking number. Their action is physical because Wilson loops are genuine observables.

At finite temperature, one often describes center transformations as gauge transformations periodic only up to a center element around the thermal circle. This is a useful computational description, but the symmetry’s gauge-invariant meaning is its action on center-charged line operators.

## Worked examples

### SU(2)

For $SU(2)$,

$$
Z(SU(2))=\{\pm1\}\cong\mathbb Z_2.
$$

Representations are labeled by spin $j$. The center element $-1$ acts as

$$
(-1)^{2j}.
$$

Thus integer-spin representations have N-ality zero, while half-integer-spin representations have N-ality one. The fundamental doublet has center charge $-1$; the adjoint triplet is neutral.

Pure $SU(2)$ Yang–Mills has a $\mathbb Z_2^{(1)}$ electric center symmetry. A fundamental Wilson loop is charged and can show an area law in the confining phase.

### SU(3)

For $SU(3)$,

$$
Z(SU(3))\cong\mathbb Z_3.
$$

The fundamental $\mathbf 3$ has N-ality $1$, the antifundamental $\overline{\mathbf 3}$ has N-ality $2$, and the adjoint $\mathbf 8$ has N-ality $0$.

Gluons are adjoint and cannot screen a single fundamental test quark in pure Yang–Mills. Dynamical fundamental quarks explicitly break the $\mathbb Z_3^{(1)}$ center symmetry, allowing string breaking.

## Common pitfalls

**“The center is just a subgroup of the gauge group, so it must be gauge redundancy.”** The one-form center symmetry is a global symmetry acting on line operators. Its gauge-invariant content is the linking action on Wilson loops.

**“Adjoint gluons screen everything.”** They screen only zero N-ality. They cannot change the center charge of a Wilson loop.

**“QCD has the same center symmetry as pure Yang–Mills.”** Dynamical fundamental quarks explicitly break the electric center one-form symmetry.

**“The Lie algebra determines the center symmetry.”** It does not. The global form of the gauge group and the allowed line operators are essential.

**“Area law means any Wilson loop has confinement forever.”** Zero N-ality Wilson loops can be screened by gluons. The robust asymptotic diagnostic uses nonzero N-ality lines in the pure theory.

## Relations to other pages

This page is the model calculation version of the more conceptual Center Symmetry page in the higher-form chapter. It uses the Wilson-loop area-law calculation, the Maxwell one-form symmetry example, and the line-operator algebra discussion.

It prepares for the later calculations of Kramers–Wannier duality, WZW anomaly inflow, and non-invertible defect examples, because all of them use the same basic logic: a symmetry is detected by how topological operators act on charged observables.

## Research status

The center one-form symmetry of pure Yang–Mills is established. It is now standard language for describing confinement diagnostics, finite-temperature deconfinement, line-operator spectra, and global forms of gauge theories.

Active refinements include mixed anomalies involving center symmetry, time reversal, flavor symmetries, and discrete theta angles; center symmetry in theories with matter of restricted N-ality; non-invertible remnants after gauging; and precise lattice/continuum matching of line-operator spectra.

## Exercises

### Exercise 1: N-ality of tensor products

In $SU(N)$, show that the tensor product of representations with N-alities $k_1$ and $k_2$ has N-ality $k_1+k_2\mod N$.

<details><summary><strong>Solution</strong></summary>

A center element $z1_N$ acts on the first representation as $z^{k_1}$ and on the second as $z^{k_2}$. On the tensor product it acts as

$$
z^{k_1}\otimes z^{k_2}=z^{k_1+k_2}.
$$

Therefore the N-ality is additive modulo $N$.

</details>

### Exercise 2: SU(2) center charge

For $SU(2)$, determine the center charge of spin-$j$ representations.

<details><summary><strong>Solution</strong></summary>

The center is $\{\pm1\}$. The element $-1$ acts on the spin-$j$ representation as a $2\pi$ rotation,

$$
(-1)^{2j}.
$$

Thus integer-spin representations are center-neutral and half-integer-spin representations are center-charged.

</details>

### Exercise 3: Fundamental matter

Explain why adding dynamical fundamental matter breaks the electric center one-form symmetry.

<details><summary><strong>Solution</strong></summary>

A one-form symmetry exists when charged line operators cannot end on dynamical local excitations. Fundamental matter has nonzero center charge. A fundamental Wilson line can end on the worldline of a dynamical fundamental particle. Therefore the would-be center-charged line is no longer a conserved extended charge, and the center one-form symmetry is explicitly broken.

</details>

### Exercise 4: Area law and potential

Use

$$
\langle W(C_{R,T})\rangle\sim e^{-T V(R)}
$$

to show that an area law

$$
\langle W(C_{R,T})\rangle\sim e^{-\sigma RT}
$$

implies a linear potential.

<details><summary><strong>Solution</strong></summary>

Equating exponents gives

$$
T V(R)=\sigma RT
$$

for large $T$, so

$$
V(R)=\sigma R.
$$

The coefficient $\sigma$ is the string tension.

</details>

## References

- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” especially the discussion of higher-form symmetries, Wilson lines, background fields, gauging, and anomalies.
- Mark Srednicki, *Quantum Field Theory*, §§69–70 for non-Abelian gauge theory and group representations, and §82 for Wilson loops, lattice theory, and confinement.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on strong coupling, confinement, loop dynamics, and topology of gauge fields.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 25 for Yang–Mills theory, Wilson lines, and gauge-theory structure.
- Ofer Aharony, Nathan Seiberg, and Yuji Tachikawa, “Reading Between the Lines of Four-Dimensional Gauge Theories,” for the modern line-operator/global-form viewpoint.

## Version history

- **2026-06-23:** Initial polished model-calculation page deriving the center one-form symmetry action on Wilson loops, N-ality, screening, area-law diagnostics, finite-temperature center symmetry, and global-form caveats.
