---
title: "Color SU(3)"
description: "Explains the concrete SU(3)c representation data used in QCD: triplets, antitriplets, octets, triality, singlet contractions, Casimirs, and color identities."
sidebar:
  label: "Color SU(3)"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki §§69–70 and §81; Schwartz Chs. 25–26; Coleman, Aspects of Symmetry, Ch. 1."
topics:
  - color SU(3)
  - QCD representations
  - quark color
  - gluon octet
  - color singlets
  - Casimir operators
  - triality
canonicalTopics:
  - color-su3
  - qcd-representations
  - fundamental-representation
  - adjoint-representation
  - color-singlets
  - qcd-color-factors
researchStatus:
  established:
    - "The SU(3)c representation theory, color factors, and singlet contractions used in perturbative and hadronic QCD are standard group-theoretic data."
  active:
    - "The same color data feed nonperturbative questions about confinement, hadronization, large-N limits, and the infrared organization of QCD."
---

## Summary

Color is the $SU(3)_c$ gauge label of QCD. Quarks transform in the fundamental representation $\boldsymbol 3$, antiquarks in the conjugate representation $\bar{\boldsymbol 3}$, and gluons in the adjoint representation $\boldsymbol 8$. The familiar color names red, green, and blue are basis labels in a local gauge frame. They are useful bookkeeping devices, not gauge-invariant properties of isolated particles.

The basic QCD representation data are

$$
q^i\to (U^{-1})^i{}_j q^j,
\qquad
\bar q_i\to \bar q_j U^j{}_i,
\qquad
G_\mu=G_\mu^AT^A\to U^{-1}G_\mu U-\frac{i}{g_s}U^{-1}\partial_\mu U,
$$

with $U(x)\in SU(3)_c$. The field strength transforms homogeneously,

$$
G_{\mu\nu}\to U^{-1}G_{\mu\nu}U,
$$

so traces and singlet contractions are the natural gauge-invariant building blocks.

The local algebra is controlled by a small collection of constants:

$$
\operatorname{tr}(T^AT^B)=\frac12\delta^{AB},
\qquad
C_F=\frac43,
\qquad
C_A=3,
\qquad
T_F=\frac12.
$$

These numbers are why QCD loop calculations differ from QED loop calculations even before the coupling runs differently. They also explain the color factors in scattering, splitting functions, Wilson loops, and the one-loop beta function.

<figure class="doc-figure" style="--figure-width: 42rem;">

![The basic SU(3)c color data: quarks in the 3, antiquarks in the anti-3, gluons in the 8, singlet meson and baryon contractions, and standard QCD color factors.](/figures/gauge-theories-standard-model/color-su3-representation-data.svg)

<figcaption>

The essential $SU(3)_c$ data for QCD. Local color algebra controls perturbative factors, while singlet contractions such as $\bar q_iq^i$ and $\epsilon_{ijk}q^iq^jq^k$ build gauge-invariant hadronic operators.

</figcaption>
</figure>

## Prerequisites

You should know the volume [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/), the [QCD Lagrangian](/gauge-theories-standard-model/qcd/qcd-lagrangian/), and the Yang–Mills pages [Color and Representations](/gauge-theories-standard-model/yang-mills/color-and-representations/) and [Global Form and Center](/gauge-theories-standard-model/yang-mills/global-form-and-center/).

This page uses the QCD convention

$$
D_\mu q=(\partial_\mu+ig_sG_\mu^AT^A)q,
\qquad
[T^A,T^B]=if^{ABC}T^C,
\qquad
\operatorname{tr}(T^AT^B)=\frac12\delta^{AB}.
$$

The notation $\boldsymbol 3$, $\bar{\boldsymbol 3}$, and $\boldsymbol 8$ denotes representations of $SU(3)_c$, not particle multiplicities by themselves. A single Dirac quark field of one flavor has spinor, color, and spacetime degrees of freedom; saying it is in $\boldsymbol 3$ only describes its color transformation law.

## Core idea

QCD color has two complementary roles.

First, it is the gauge index that makes the local Lagrangian non-Abelian. It tells us how quarks couple to gluons, how gluons self-interact, and which group factors appear in perturbation theory.

Second, it is the index that must disappear from physical local operators and asymptotic states. Gauge-invariant operators cannot carry an exposed fundamental color index. Meson, baryon, and glueball-like operators are possible because their color indices are contracted into singlets.

That tension is the whole mood of QCD: color is indispensable in the microscopic description and absent from isolated macroscopic particles.

## Setup and conventions

Let $N_c=3$. Fundamental color indices are written as

$$
i,j,k,\ell=1,2,3,
$$

and adjoint color indices as

$$
A,B,C=1,\ldots,8.
$$

A quark of flavor $f$ is a color triplet,

$$
q_f(x)=
\begin{pmatrix}
q_f^1(x)\\
q_f^2(x)\\
q_f^3(x)
\end{pmatrix},
$$

while an antiquark transforms in the conjugate representation. In index notation,

$$
q^i\mapsto (U^{-1})^i{}_j q^j,
\qquad
\bar q_i\mapsto \bar q_jU^j{}_i.
$$

The gluon field is an adjoint-valued connection,

$$
G_\mu=G_\mu^AT^A,
$$

where $T^A$ are the fundamental generators. A standard explicit choice is

$$
T^A=\frac{\lambda^A}{2},
$$

with $\lambda^A$ the Gell-Mann matrices, but almost no physical formula depends on choosing this particular basis. What matters are the algebra and normalization.

The generators are Hermitian and traceless:

$$
(T^A)^\dagger=T^A,
\qquad
\operatorname{tr}T^A=0.
$$

They obey

$$
[T^A,T^B]=if^{ABC}T^C,
$$

and

$$
\{T^A,T^B\}=\frac13\delta^{AB}\mathbf 1+d^{ABC}T^C.
$$

The constants $f^{ABC}$ are totally antisymmetric and appear in the non-Abelian field strength and gluon self-interactions. The constants $d^{ABC}$ are totally symmetric and appear in many color decompositions and higher invariant tensors.

## The triplet, antitriplet, and octet

The fundamental representation $\boldsymbol 3$ is the color representation of quarks. The conjugate representation $\bar{\boldsymbol 3}$ is the color representation of antiquarks.

The tensor product

$$
\boldsymbol 3\otimes\bar{\boldsymbol 3}
$$

is naturally the space of $3\times 3$ matrices. It decomposes into trace and traceless parts:

$$
\boldsymbol 3\otimes\bar{\boldsymbol 3}
=
\boldsymbol 1\oplus\boldsymbol 8.
$$

In matrix language,

$$
M^i{}_j
=
\frac13\delta^i{}_j M^k{}_k
+
\left(M^i{}_j-\frac13\delta^i{}_jM^k{}_k\right).
$$

The trace is the singlet $\boldsymbol 1$; the traceless part is the adjoint $\boldsymbol 8$. This is the precise meaning behind the informal statement that a gluon carries a color–anticolor label with the singlet removed.

Do not take that phrase too literally. Gluons are not nine color–anticolor particles minus a forbidden one. They are gauge bosons valued in the Lie algebra $\mathfrak{su}(3)$, an eight-dimensional space of traceless Hermitian generators. The color–anticolor picture is a helpful basis-dependent mnemonic.

The tensor product of two quark triplets decomposes as

$$
\boldsymbol 3\otimes\boldsymbol 3
=
\boldsymbol 6\oplus\bar{\boldsymbol 3}.
$$

The symmetric part is $\boldsymbol 6$, and the antisymmetric part is $\bar{\boldsymbol 3}$. With three triplets,

$$
\boldsymbol 3\otimes\boldsymbol 3\otimes\boldsymbol 3
=
\boldsymbol 1\oplus\boldsymbol 8\oplus\boldsymbol 8\oplus\boldsymbol {10}.
$$

The singlet is built using the invariant tensor $\epsilon_{ijk}$:

$$
\epsilon_{ijk}q^iq^jq^k.
$$

This is the color skeleton of a baryon operator.

## Triality and the center

The center of $SU(3)$ is

$$
Z(SU(3))\simeq \mathbb Z_3,
\qquad
z_n=e^{2\pi in/3}\mathbf 1,
\qquad
n=0,1,2.
$$

A representation has a center charge, often called triality. Under $z_n$,

$$
\boldsymbol 3\mapsto e^{2\pi in/3}\boldsymbol 3,
\qquad
\bar{\boldsymbol 3}\mapsto e^{-2\pi in/3}\bar{\boldsymbol 3},
\qquad
\boldsymbol 8\mapsto \boldsymbol 8.
$$

Thus quarks have triality $1$, antiquarks have triality $-1$, and gluons have triality $0$ modulo $3$.

Triality gives a quick singlet test: a color singlet must have total triality zero. A meson has

$$
1+(-1)=0\quad \text{mod }3,
$$

and a baryon has

$$
1+1+1=0\quad \text{mod }3.
$$

This is necessary but not sufficient: triality zero says a singlet is allowed by center charge, not that a particular tensor is already projected onto the singlet.

There is one subtle but important point. Pure $SU(3)$ Yang–Mills theory has a genuine $\mathbb Z_3$ one-form center symmetry acting on Wilson loops. QCD with dynamical fundamental quarks does not have that same exact one-form symmetry, because fundamental Wilson lines can end on dynamical quark fields. Triality remains a useful representation label, but the infrared confinement diagnostic is less sharp than in pure Yang–Mills theory.

## Color singlet operators

Gauge-invariant local operators must have all color indices contracted. The simplest examples are meson-like bilinears,

$$
\bar q_{f i}\Gamma q_g^i,
$$

where $\Gamma$ is a spinor matrix such as $\mathbf 1$, $\gamma^5$, $\gamma^\mu$, $\gamma^\mu\gamma^5$, or $\sigma^{\mu\nu}$. The color contraction is the same for all of these; the spin and flavor choices determine the operator's quantum numbers.

Baryon-like color structures use the invariant tensor $\epsilon_{ijk}$:

$$
\epsilon_{ijk}q_f^iq_g^jq_h^k.
$$

A complete baryon operator also needs spinor contractions and, for identical fermions, the total wavefunction must obey Fermi statistics. The color part above is antisymmetric.

Gluonic singlets are built from traces, for example

$$
\operatorname{tr}(G_{\mu\nu}G^{\mu\nu})
=
\frac12G_{\mu\nu}^AG^{A\mu\nu},
$$

and

$$
\operatorname{tr}(G_{\mu\nu}\widetilde G^{\mu\nu})
=
\frac12G_{\mu\nu}^A\widetilde G^{A\mu\nu}.
$$

In pure Yang–Mills theory, such operators create glueball-like states. In full QCD, gluonic operators can mix with quark operators that have the same quantum numbers.

## Casimirs and Dynkin index

For a representation $R$, define the generators $T_R^A$ by

$$
[T_R^A,T_R^B]=if^{ABC}T_R^C.
$$

The quadratic Casimir $C_R$ is defined by

$$
T_R^AT_R^A=C_R\mathbf 1_R,
$$

and the Dynkin index $T_R$ by

$$
\operatorname{tr}_R(T_R^AT_R^B)=T_R\delta^{AB}.
$$

For the fundamental representation of $SU(N_c)$ with our normalization,

$$
T_F=\frac12,
\qquad
C_F=\frac{N_c^2-1}{2N_c}.
$$

For the adjoint representation,

$$
C_A=N_c.
$$

Therefore, for QCD with $N_c=3$,

$$
C_F=\frac43,
\qquad
C_A=3,
\qquad
T_F=\frac12.
$$

These numbers appear everywhere. Examples include

$$
\mu\frac{dg_s}{d\mu}
=
-\frac{g_s^3}{16\pi^2}
\left(\frac{11}{3}C_A-\frac{4}{3}T_Fn_f\right)+\cdots,
$$

and the fundamental Wilson-loop short-distance potential,

$$
V(r)\sim -\frac{C_F\alpha_s}{r}
\qquad
(r\ll \Lambda_{\rm QCD}^{-1}).
$$

The first formula says gluons and quarks pull the running coupling in opposite directions. The second says the Coulombic short-distance attraction between a heavy quark and antiquark carries the fundamental Casimir $C_F$.

## Completeness identity

The fundamental generators form an orthonormal basis for traceless Hermitian matrices. Their completeness relation is

$$
\sum_{A=1}^{8}(T^A)^i{}_j(T^A)^k{}_{\ell}
=
\frac12\left(
\delta^i{}_{\ell}\delta^k{}_j
-
\frac13\delta^i{}_j\delta^k{}_{\ell}
\right).
$$

This identity is the color analogue of a projection formula. The first term is what one would get from a complete basis of all $3\times 3$ matrices; the second subtracts the trace, because the $SU(3)$ generators are traceless.

A very common use is to simplify color factors in quark scattering. For example, a single gluon exchanged between two quark lines carries a factor

$$
(T^A)^i{}_j(T^A)^k{}_{\ell},
$$

which can be rewritten as singlet-exchange and color-rearrangement pieces by the completeness identity above.

## Color flow intuition

At large $N_c$, it is often useful to draw gluons using double-line notation, because the adjoint representation sits inside

$$
\boldsymbol N\otimes\bar{\boldsymbol N}
=
\boldsymbol 1\oplus\operatorname{Adj}.
$$

For $SU(3)$ this says $\boldsymbol 3\otimes\bar{\boldsymbol 3}=\boldsymbol 1\oplus\boldsymbol 8$. In color-flow language, a gluon carries one fundamental and one antifundamental line, with the singlet part removed.

This notation is excellent for organizing color factors in amplitudes and for seeing why planar diagrams dominate in certain large-$N_c$ limits. But it is still a computational representation. It does not mean that an observed gluon literally consists of two smaller colored particles.

## Common pitfalls

**Color labels are not observables.** A statement like “this quark is red” means “this component is chosen in a local color basis.” A gauge transformation can rotate the label.

**The gluon octet is not an ordinary flavor octet.** Flavor $SU(3)$ classifies approximate global multiplets involving $u,d,s$ quarks. Color $SU(3)_c$ is a gauge redundancy. Mixing these two $SU(3)$ groups is a reliable way to manufacture confusion and probably a small pedagogical fire.

**A triality-zero object is not automatically a singlet.** For example, $\boldsymbol 3\otimes\bar{\boldsymbol 3}$ has triality zero, but it contains both $\boldsymbol 1$ and $\boldsymbol 8$. One still has to project onto the singlet.

**The ninth color–anticolor state is not a QCD gluon.** The trace part of $\boldsymbol 3\otimes\bar{\boldsymbol 3}$ is a singlet. QCD gluons live in the traceless adjoint $\boldsymbol 8$ of $SU(3)$.

**Color factors are normalization-dependent until conventions are fixed.** The values $C_F=4/3$, $C_A=3$, and $T_F=1/2$ assume $\operatorname{tr}(T^AT^B)=\frac12\delta^{AB}$. Change the generator normalization and intermediate formulas change, though physical predictions do not.

## Relations to other pages

The [QCD Lagrangian](/gauge-theories-standard-model/qcd/qcd-lagrangian/) page uses this color data to write the quark–gluon coupling and the gluon field strength. [Quarks and Gluons](/gauge-theories-standard-model/qcd/quarks-and-gluons/) explains how these colored fields function as perturbative partons even though physical isolated states are color singlets.

The Yang–Mills page [Color and Representations](/gauge-theories-standard-model/yang-mills/color-and-representations/) gives the more general $SU(N)$ version. [Global Form and Center](/gauge-theories-standard-model/yang-mills/global-form-and-center/) explains the center-symmetry language that becomes important for pure Yang–Mills confinement and for distinguishing $SU(N)$ from quotient gauge groups.

Later QCD pages use the same data in different ways: [QCD Beta Function](/gauge-theories-standard-model/qcd/qcd-beta-function/) uses $C_A$ and $T_F$, [Chiral Symmetry in QCD](/gauge-theories-standard-model/qcd/chiral-symmetry-in-qcd/) separates color from flavor, and [Confinement in QCD](/gauge-theories-standard-model/qcd/confinement-in-qcd/) studies why exposed color does not appear in the spectrum.

## Research status

The finite-dimensional $SU(3)$ group theory on this page is settled. The active physics lies in how this local color structure reorganizes in the infrared: confinement with dynamical quarks, hadronization, glueball–meson mixing, large-$N_c$ expansions, finite-density phases, and lattice determinations of color-singlet spectra.

There is also ongoing use of color decompositions in high-multiplicity perturbative QCD, where choosing the right color basis can make the difference between an impossible calculation and one that merely ruins your afternoon.

## Exercises

### Exercise 1: Trace and traceless parts

Show explicitly that a matrix $M^i{}_j$ in $\boldsymbol 3\otimes\bar{\boldsymbol 3}$ decomposes into a singlet and an adjoint part.

<details><summary><strong>Solution</strong></summary>

Define

$$
M_{\rm singlet}{}^i{}_j=\frac13\delta^i{}_jM^k{}_k,
$$

and

$$
M_{\rm adj}{}^i{}_j=M^i{}_j-\frac13\delta^i{}_jM^k{}_k.
$$

The first part is proportional to the identity, so it is invariant under conjugation by $SU(3)$. The second part is traceless:

$$
M_{\rm adj}{}^i{}_i
=
M^i{}_i-\frac13\delta^i{}_iM^k{}_k
=
M^i{}_i-M^k{}_k=0.
$$

Thus the $9$-dimensional tensor product splits into a $1$-dimensional trace part and an $8$-dimensional traceless part:

$$
\boldsymbol 3\otimes\bar{\boldsymbol 3}=\boldsymbol 1\oplus\boldsymbol 8.
$$

</details>

### Exercise 2: Fundamental Casimir

Using the completeness identity, show that

$$
(T^AT^A)^i{}_j=C_F\delta^i{}_j
$$

with $C_F=4/3$ for $SU(3)$.

<details><summary><strong>Solution</strong></summary>

Set $k=j$ and $\ell=m$ carefully by writing

$$
(T^AT^A)^i{}_j=(T^A)^i{}_{\ell}(T^A)^\ell{}_j.
$$

Use the completeness identity with $k=\ell$ and $\ell\to j$:

$$
(T^A)^i{}_{\ell}(T^A)^\ell{}_j
=
\frac12\left(\delta^i{}_j\delta^\ell{}_{\ell}-\frac13\delta^i{}_{\ell}\delta^\ell{}_j\right).
$$

Since $\delta^\ell{}_{\ell}=3$ and $\delta^i{}_{\ell}\delta^\ell{}_j=\delta^i{}_j$,

$$
(T^AT^A)^i{}_j
=
\frac12\left(3-\frac13\right)\delta^i{}_j
=
\frac43\delta^i{}_j.
$$

Therefore $C_F=4/3$.

</details>

### Exercise 3: Triality test

Compute the triality of $qq$, $q\bar q$, $qqq$, and $gg$.

<details><summary><strong>Solution</strong></summary>

Assign triality

$$
q:1,
\qquad
\bar q:-1,
\qquad
g:0
\qquad
\text{mod }3.
$$

Then

$$
qq:1+1=2,
$$

so two quarks alone cannot form a color singlet. Next,

$$
q\bar q:1-1=0,
$$

so a meson singlet is allowed. For three quarks,

$$
qqq:1+1+1=3=0\quad \text{mod }3,
$$

so a baryon singlet is allowed. For two gluons,

$$
gg:0+0=0,
$$

so color singlets can occur in gluonic products. Triality zero is necessary for a singlet, but the actual singlet projection still has to be performed.

</details>

### Exercise 4: Meson singlet invariance

Show that $\bar q_iq^i$ is invariant under $q^i\mapsto (U^{-1})^i{}_jq^j$ and $\bar q_i\mapsto \bar q_jU^j{}_i$.

<details><summary><strong>Solution</strong></summary>

Under the transformation,

$$
\bar q_iq^i
\mapsto
\bar q_jU^j{}_i(U^{-1})^i{}_kq^k.
$$

The adjacent matrices multiply to the identity:

$$
U^j{}_i(U^{-1})^i{}_k=\delta^j{}_k.
$$

Therefore

$$
\bar q_jU^j{}_i(U^{-1})^i{}_kq^k
=
\bar q_j\delta^j{}_kq^k
=
\bar q_kq^k.
$$

So $\bar q_iq^i$ is a color singlet.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§69–70 for non-Abelian gauge theory and group representations, and §81 for QCD scattering context.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–26, for Yang–Mills theory, Wilson lines, color factors, and QCD perturbation theory.
- Coleman, *Aspects of Symmetry*, Ch. 1, for $SU(3)$ representation technology and physical multiplet intuition.

### Deeper references

- Georgi, *Lie Algebras in Particle Physics*, for representation theory and particle-physics group data.
- Cvitanović, *Group Theory*, for birdtracks and color algebra methods.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Ch. 15, for non-Abelian gauge-theory conventions and group-theory normalization in a systematic setting.

## Version history

- **2026-06-18:** Initial polished draft. Added the $SU(3)_c$ representation map, singlet contractions, triality discussion, Casimirs, and completeness identity.
