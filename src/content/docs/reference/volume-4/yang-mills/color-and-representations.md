---
title: "Color and Representations"
description: "Explains the SU(3) color representations used in QCD, including triplets, antitriplets, octets, singlet contractions, tensor products, Casimirs, Dynkin indices, and color-flow notation."
sidebar:
  label: "Color and Representations"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki §§69–70, 72–73, 80–81; Schwartz Chs. 25–27, 32; Weinberg Vol. II Ch. 15; Coleman, Aspects of Symmetry, unitary symmetry lectures."
topics:
  - color SU(3)
  - group representations
  - QCD
  - Casimir operators
  - color flow
canonicalTopics:
  - color-and-representations
  - su3-color
  - qcd-representations
  - color-singlets
  - color-factors
researchStatus:
  established:
    - "The SU(3) color representation data used in perturbative QCD and the Standard Model are standard consequences of compact Lie-group representation theory."
  active:
    - "How color representation data reorganize nonperturbatively is tied to confinement, center symmetry, hadronization, large-N limits, and line-operator physics."
---

## Summary

Color is the gauge representation label of $SU(3)_c$. It is not a new kind of ordinary color, not a directly observable charge like electric charge, and not a global flavor label. It is the internal gauge index carried by quarks and gluons in quantum chromodynamics.

In the Standard Model, quarks transform in the fundamental representation of the color gauge group,

$$
q^i,
\qquad i=1,2,3,
\qquad q\in \mathbf 3 \text{ of } SU(3)_c,
$$

antiquark states transform in the conjugate representation $\bar{\mathbf 3}$, and gluons transform in the adjoint representation,

$$
A_\mu=A_\mu^aT^a,
\qquad a=1,\ldots,8,
\qquad A_\mu\in \mathbf 8.
$$

The main representation-theory facts behind QCD are compact:

$$
\mathbf 3\otimes\bar{\mathbf 3}=\mathbf 1\oplus\mathbf 8,
\qquad
\mathbf 3\otimes\mathbf 3=\bar{\mathbf 3}\oplus\mathbf 6,
\qquad
\mathbf 3\otimes\mathbf 3\otimes\mathbf 3
=\mathbf 1\oplus\mathbf 8\oplus\mathbf 8\oplus\mathbf{10}.
$$

They explain why mesons can be color singlets of the form $\bar q_iq^i$, why baryons can be color singlets of the form $\epsilon_{ijk}q^iq^jq^k$, and why gluons can be represented as traceless color matrices $A^i{}_j$.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Map of SU(3) color representation data: quark triplets, antiquark antitriplets, gluon octets, tensor-product channels, Casimirs, Dynkin indices, and N-ality.](/figures/gauge-theories-standard-model/color-representation-data.svg)

<figcaption>

The elementary color representations of QCD. Quarks carry $\mathbf 3$, antiquarks carry $\bar{\mathbf 3}$, gluons carry the adjoint $\mathbf 8$, and physical finite-energy particles in confining QCD are built from gauge-invariant color-singlet contractions.

</figcaption>
</figure>

## Prerequisites

You should have read [Covariant Derivative in Representations](/gauge-theories-standard-model/yang-mills/covariant-derivative-in-representations/) and [Gauge-Boson Self-Interactions](/gauge-theories-standard-model/yang-mills/gauge-boson-self-interactions/). This page uses the same normalization

$$
\operatorname{tr}(T_F^aT_F^b)=\frac12\delta^{ab}
$$

for the fundamental generators of $SU(N)$. It also uses the volume convention

$$
D_\mu=\partial_\mu+igA_\mu^aT_R^a.
$$

The representation theory here is deliberately minimal. You only need to know that a representation assigns matrices $T_R^a$ to the same abstract generators, and that tensor products describe objects with several color indices.

## Core idea

The clean way to think about color is this:

$$
\text{color} = \text{representation data for the gauge group } SU(3)_c.
$$

The group $SU(3)_c$ has eight generators. A quark field does not carry an adjoint index $a=1,\ldots,8$; it carries a fundamental index $i=1,2,3$. The gluon field carries the adjoint index $a$ because the connection is Lie-algebra valued. When the gluon is written as a matrix,

$$
(A_\mu)^i{}_{j}=A_\mu^a(T_F^a)^i{}_{j},
$$

it looks like a color–anticolor object. The trace part is absent because $SU(3)$ generators are traceless. This is the representation-theory origin of the slogan “a gluon carries color and anticolor,” with the important caveat that the adjoint is the traceless part of $\mathbf 3\otimes\bar{\mathbf 3}$, not all of it.

The same representation data appear in three different places:

| Place | Representation data | Why it matters |
|---|---|---|
| Matter coupling | $D_\mu=\partial_\mu+igA_\mu^aT_R^a$ | Determines the quark–gluon vertex and gauge covariance. |
| Color factors | $\operatorname{tr}(T_R^aT_R^b)$ and $T_R^aT_R^a$ | Determines group factors in loop diagrams and scattering amplitudes. |
| Gauge-invariant states/operators | invariant tensors such as $\delta^i{}_j$ and $\epsilon_{ijk}$ | Determines which color contractions are singlets. |

Color is therefore not an extra decoration on QCD. It is the representation theory through which the gauge principle becomes a physical interaction.

## Setup and conventions

For $SU(N)$, let $T_F^a$ denote the fundamental generators. We often write

$$
t^a\equiv T_F^a.
$$

They obey

$$
[t^a,t^b]=if^{abc}t^c,
\qquad
\operatorname{tr}(t^at^b)=\frac12\delta^{ab}.
$$

The number of generators of $SU(N)$ is

$$
D(A)=N^2-1,
$$

so $SU(3)$ has $8$ gauge bosons. The fundamental quadratic Casimir and adjoint quadratic Casimir are

$$
C_F=\frac{N^2-1}{2N},
\qquad
C_A=N.
$$

For $SU(3)$,

$$
C_F=\frac43,
\qquad
C_A=3,
\qquad
D(A)=8.
$$

The Dynkin index $T(R)$ is defined by

$$
\operatorname{tr}(T_R^aT_R^b)=T(R)\delta^{ab},
$$

so

$$
T(F)=\frac12,
\qquad
T(A)=N.
$$

The relation between the index and the quadratic Casimir is

$$
T(R)D(A)=C_R D(R),
$$

where $D(R)$ is the dimension of representation $R$ and $C_R$ is defined by

$$
T_R^aT_R^a=C_R\mathbf 1_R.
$$

This identity is a workhorse: it lets you move between trace normalizations and Casimir factors without recomputing matrices.

## Triplets and antitriplets

A quark field in QCD is a color triplet,

$$
q^i(x),\qquad i=1,2,3.
$$

For one quark flavor, the color part of the covariant derivative is

$$
(D_\mu q)^i
=
\partial_\mu q^i+ig_sA_\mu^a(t^a)^i{}_{j}q^j.
$$

Here $g_s$ is the strong coupling. The subscript $s$ is often used to distinguish it from the electric coupling $e$ and weak couplings $g,g'$.

The conjugate color index appears on the Dirac adjoint field,

$$
\bar q_i=q_i^\dagger\gamma^0,
$$

which transforms as a dual color vector. The singlet contraction

$$
\bar q_iq^i
$$

is invariant under local $SU(3)_c$ transformations. This is the color part of an ordinary quark mass term.

Antiquark one-particle states are naturally labeled by the conjugate representation $\bar{\mathbf 3}$. This statement belongs to the representation theory of the Hilbert space. The field-level statement is that conjugate or dual color indices transform oppositely from fundamental color indices, allowing contractions such as $\bar q_iq^i$.

For $SU(3)$, the fundamental and antifundamental are inequivalent complex representations:

$$
\mathbf 3\not\simeq\bar{\mathbf 3}.
$$

This is unlike the fundamental of $SU(2)$, which is pseudoreal. That difference matters whenever one builds chiral theories or tracks representation conjugation.

## The adjoint representation and gluons

The gluon field is a connection,

$$
A_\mu=A_\mu^aT^a,
$$

so it is Lie-algebra valued. The adjoint representation has dimension equal to the number of generators:

$$
D(A)=8\quad\text{for }SU(3)_c.
$$

In components, the adjoint generators are

$$
(T_A^a)_{bc}=-if^{abc}.
$$

The field strength is also adjoint-valued:

$$
F_{\mu\nu}=F_{\mu\nu}^aT^a,
\qquad
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U.
$$

In the fundamental matrix notation,

$$
(F_{\mu\nu})^i{}_{j}=F_{\mu\nu}^a(t^a)^i{}_{j},
\qquad
(F_{\mu\nu})^i{}_{i}=0.
$$

This is why an adjoint color line can be drawn as a pair of fundamental-index lines with the trace part removed. Algebraically,

$$
\mathbf 3\otimes\bar{\mathbf 3}=\mathbf 1\oplus\mathbf 8.
$$

The singlet is the trace part, proportional to $\delta^i{}_j$. The octet is the traceless part. The physical gluon lives in the traceless part.

## Color singlets

Gauge-invariant local operators must have all color indices contracted into singlets. For $SU(3)$, the two basic invariant tensors are

$$
\delta^i{}_{j},
\qquad
\epsilon_{ijk},
$$

together with their raised-index versions. They produce the familiar color structures of hadrons.

A meson-like color singlet has color contraction

$$
\bar q_i q^i.
$$

A baryon-like color singlet has color contraction

$$
\epsilon_{ijk}q^iq^jq^k.
$$

A glueball-like local singlet can be built from traces of field strengths, for example

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
=
\frac12F_{\mu\nu}^aF^{a\mu\nu}.
$$

These formulas are not yet a theory of hadron spectroscopy. They are representation-theory constraints on gauge-invariant operators. Dynamics decides which states exist, their masses, their widths, and how they mix.

:::note[Color singlet versus physical particle]
In a confining theory such as low-energy QCD, finite-energy asymptotic particles are color singlets. But not every gauge-invariant local operator creates a narrow stable particle. Operators can mix, create multiparticle continua, or couple weakly to the lightest state in a channel.
:::

## Tensor products you actually use

The most useful $SU(3)$ tensor products for QCD are

$$
\mathbf 3\otimes\bar{\mathbf 3}=\mathbf 1\oplus\mathbf 8,
$$

$$
\mathbf 3\otimes\mathbf 3=\bar{\mathbf 3}\oplus\mathbf 6,
$$

$$
\bar{\mathbf 3}\otimes\bar{\mathbf 3}=\mathbf 3\oplus\bar{\mathbf 6},
$$

and

$$
\mathbf 8\otimes\mathbf 8
=
\mathbf 1\oplus\mathbf 8_S\oplus\mathbf 8_A\oplus\mathbf{10}\oplus\bar{\mathbf{10}}\oplus\mathbf{27}.
$$

The subscripts $S$ and $A$ distinguish symmetric and antisymmetric octet channels.

For three quarks,

$$
\mathbf 3\otimes\mathbf 3\otimes\mathbf 3
=
\mathbf 1\oplus\mathbf 8\oplus\mathbf 8\oplus\mathbf {10}.
$$

The color-singlet baryon channel is the totally antisymmetric one, extracted with $\epsilon_{ijk}$. This color antisymmetry is one ingredient in the spin–flavor structure of baryons.

These decompositions also explain why a single isolated quark operator is not gauge invariant, why a quark–antiquark bilinear can be, and why a three-quark operator can be.

## Casimirs and color factors

Perturbative QCD amplitudes are full of color factors. The most common ones are

$$
t^at^a=C_F\mathbf 1_F,
\qquad
C_F=\frac{N^2-1}{2N},
$$

and

$$
f^{acd}f^{bcd}=C_A\delta^{ab},
\qquad
C_A=N.
$$

For $SU(3)$, these become

$$
C_F=\frac43,
\qquad
C_A=3.
$$

The trace normalization is

$$
\operatorname{tr}(t^at^b)=T_F\delta^{ab},
\qquad
T_F=\frac12.
$$

These constants appear in different places:

| Constant | For $SU(N)$ | For $SU(3)$ | Typical role |
|---|---:|---:|---|
| $D(A)$ | $N^2-1$ | $8$ | Number of gluons. |
| $T_F$ | $1/2$ | $1/2$ | Trace of a fundamental fermion loop. |
| $C_F$ | $(N^2-1)/(2N)$ | $4/3$ | Quark self-energy and quark color charge factor. |
| $C_A$ | $N$ | $3$ | Gluon self-interactions, ghost loops, Yang–Mills beta function. |

A particularly useful identity in the fundamental representation of $SU(N)$ is

$$
(t^a)^i{}_{j}(t^a)^k{}_{l}
=
\frac12
\left(
\delta^i{}_{l}\delta^k{}_{j}
-
\frac1N\delta^i{}_{j}\delta^k{}_{l}
\right).
$$

This is the color Fierz identity. It says that the adjoint exchange is the full color-line exchange minus its singlet trace. It is the algebraic backbone of double-line notation and large-$N$ color-flow diagrams.

## Color flow

The adjoint representation of $SU(N)$ can be represented by a pair of fundamental color lines with the trace removed. This gives a powerful diagrammatic language.

A gluon with adjoint index $a$ can be written as a matrix

$$
A^i{}_{j}=A^a(t^a)^i{}_{j}.
$$

The completeness relation above tells us that when we sum over adjoint indices, we get

$$
\sum_a(t^a)^i{}_{j}(t^a)^k{}_{l}
=
\frac12\delta^i{}_{l}\delta^k{}_{j}
-
\frac{1}{2N}\delta^i{}_{j}\delta^k{}_{l}.
$$

The first term is the color-flow line. The second subtracts the unwanted singlet. In the large-$N$ limit, the first term dominates many counting arguments, while the trace-subtraction term is suppressed by $1/N$ in suitable normalizations.

This is the beginning of the double-line notation used in large-$N$ Yang–Mills theory. The same idea is also practical in ordinary $N=3$ QCD calculations: it organizes complicated color sums into trace structures and color-ordered partial amplitudes.

## How color enters QCD

With $n_f$ quark flavors, the QCD part of the Lagrangian can be written schematically as

$$
\mathcal L_{\mathrm{QCD}}
=
-\frac14G_{\mu\nu}^aG^{a\mu\nu}
+
\sum_{I=1}^{n_f}\bar q_{I i}
\left(i\gamma^\mu D_\mu-m_I\right)^i{}_{j}
q_I^j.
$$

Here $I$ is flavor and $i,j$ are color. The covariant derivative is

$$
(D_\mu)^i{}_{j}
=
\delta^i{}_{j}\partial_\mu+ig_sG_\mu^a(t^a)^i{}_{j}.
$$

The flavor label $I$ does not participate in the color gauge transformation. The color label $i$ does. This separation is the first step toward understanding QCD's approximate flavor symmetries, chiral symmetry, and the difference between quarks as fundamental fields and hadrons as color-singlet states.

## Common pitfalls

**Thinking color is observable like electric charge.** Electric charge labels genuine charged states in QED. Color labels gauge representation. In confining QCD, isolated finite-energy color-triplet particles are not observed as asymptotic states.

**Confusing color with flavor.** Up, down, strange, charm, bottom, and top are flavors. Red, green, and blue are mnemonic names for the three components of the $SU(3)_c$ fundamental representation.

**Forgetting the trace subtraction in gluon color flow.** A gluon is not a full $\mathbf 3\otimes\bar{\mathbf 3}$ object. It is the traceless octet part. The singlet trace would behave like an extra $U(1)$ gauge boson, which QCD does not contain.

**Replacing all representation theory by slogans.** “Mesons are quark–antiquark” and “baryons are three quarks” are useful first-pass pictures, but the gauge-invariant statement is about color-singlet operator contractions. Real QCD states can mix with gluonic and sea-quark components.

**Using $C_F$, $C_A$, and $T_F$ interchangeably.** They are related but not the same. $C_R$ comes from $T_R^aT_R^a$; $T(R)$ comes from a trace; $C_A$ is the adjoint Casimir.

**Assuming local representation data settle global questions.** The $SU(3)$ Lie algebra tells you the local gluon interactions. The global form of the gauge group and its center determine additional facts about genuine representations, line operators, and one-form symmetries. That is the next page.

## Relations to other pages

This page builds on [Covariant Derivative in Representations](/gauge-theories-standard-model/yang-mills/covariant-derivative-in-representations/) by specializing the representation language to $SU(3)_c$ and QCD. It prepares the QCD chapter, where $g_s$, $\alpha_s$, confinement, chiral symmetry, and hadron physics become the central story.

The next page, [Global Form and Center](/gauge-theories-standard-model/yang-mills/global-form-and-center/), explains why $SU(N)$ and $SU(N)/\mathbb Z_N$ can share the same local Lie algebra while defining different quantum gauge theories.

The color-flow material connects later to perturbative QCD, large-$N$ Yang–Mills theory, color ordering, and the scattering-amplitudes pages.

## Research status

The finite-dimensional $SU(3)$ representation data on this page are established mathematics and standard perturbative-QCD technology.

The physical realization of color is more subtle. QCD is believed, and lattice calculations strongly support, that color is confined at low energies. A full analytic solution of four-dimensional QCD confinement and mass gap remains a major nonperturbative problem. Representation theory tells us which color-singlet operators can be written; dynamics tells us what the spectrum and long-distance physics actually are.

## Exercises

### Exercise 1: Casimir from index and dimensions

Use

$$
T(R)D(A)=C_R D(R)
$$

for the fundamental representation of $SU(N)$, with

$$
T(F)=\frac12,
\qquad
D(F)=N,
\qquad
D(A)=N^2-1,
$$

to derive $C_F$.

<details><summary><strong>Solution</strong></summary>

Insert the data:

$$
\frac12(N^2-1)=C_F N.
$$

Therefore

$$
C_F=\frac{N^2-1}{2N}.
$$

For $N=3$ this gives

$$
C_F=\frac{8}{6}=\frac43.
$$

</details>

### Exercise 2: Why mesons and baryons can be singlets

Show that $\bar q_iq^i$ and $\epsilon_{ijk}q^iq^jq^k$ are invariant under $SU(3)$ transformations, ignoring spacetime and spinor indices.

<details><summary><strong>Solution</strong></summary>

Let

$$
q^i\mapsto (U^{-1})^i{}_{j}q^j,
\qquad
\bar q_i\mapsto \bar q_jU^j{}_{i}.
$$

Then

$$
\bar q_iq^i
\mapsto
\bar q_jU^j{}_{i}(U^{-1})^i{}_{k}q^k
=
\bar q_j\delta^j{}_{k}q^k
=
\bar q_iq^i.
$$

For the three-quark contraction,

$$
\epsilon_{ijk}q^iq^jq^k
\mapsto
\epsilon_{ijk}(U^{-1})^i{}_{a}(U^{-1})^j{}_{b}(U^{-1})^k{}_{c}q^aq^bq^c.
$$

The determinant identity gives

$$
\epsilon_{ijk}(U^{-1})^i{}_{a}(U^{-1})^j{}_{b}(U^{-1})^k{}_{c}
=
\det(U^{-1})\epsilon_{abc}.
$$

For $U\in SU(3)$, $\det U=1$, so $\det(U^{-1})=1$. Hence the baryon color contraction is invariant.

</details>

### Exercise 3: The trace subtraction in color flow

Use the fundamental completeness relation

$$
(t^a)^i{}_{j}(t^a)^k{}_{l}
=
\frac12
\left(
\delta^i{}_{l}\delta^k{}_{j}
-
\frac1N\delta^i{}_{j}\delta^k{}_{l}
\right)
$$

to explain why an adjoint color line is not identical to a full pair of fundamental color lines.

<details><summary><strong>Solution</strong></summary>

The first term,

$$
\frac12\delta^i{}_{l}\delta^k{}_{j},
$$

exchanges fundamental color lines and is what is drawn in double-line notation. The second term,

$$
-\frac{1}{2N}\delta^i{}_{j}\delta^k{}_{l},
$$

subtracts the color singlet trace. Without this subtraction, the pair $i,j$ would describe all of $\mathbf N\otimes\bar{\mathbf N}$, whose dimension is $N^2$. The adjoint of $SU(N)$ has dimension $N^2-1$, so the singlet must be removed.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§69–70, for non-Abelian gauge theory, QCD fields, conjugate and adjoint representations, Casimirs, Dynkin indices, and tensor products.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 25, for Lie groups, $SU(N)$ representation conventions, Wilson lines, Yang–Mills theory, and color factors.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 26–27 and 32, for perturbative QCD, color factors, running coupling, gluon scattering, color ordering, and the parton model.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, Ch. 15, for a systematic treatment of non-Abelian gauge theories and representation constraints in gauge Lagrangians.
- Coleman, *Aspects of Symmetry*, “An Introduction to Unitary Symmetry,” for classic $SU(3)$ representation technology and physical applications.
- Polyakov, *Gauge Fields and Strings*, Chs. 7–8, for loop dynamics and large-$N$ viewpoints that reinterpret color-flow structure nonperturbatively.

## Version history

- **2026-06-17:** Initial polished draft.
