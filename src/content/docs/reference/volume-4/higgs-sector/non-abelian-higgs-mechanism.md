---
title: "Non-Abelian Higgs Mechanism"
description: "Explains how a scalar vacuum in a non-Abelian gauge theory splits generators into unbroken and broken directions, producing massive gauge bosons and would-be Goldstone modes."
sidebar:
  label: "Non-Abelian Higgs Mechanism"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki §§84 and 86–87; Schwartz Chs. 28–29; Coleman, Aspects of Symmetry, Ch. 5; Weinberg Vol. II spontaneously broken gauge theory chapters."
topics:
  - non-Abelian Higgs mechanism
  - gauge boson mass matrix
  - broken generators
  - Goldstone modes
  - unbroken subgroup
canonicalTopics:
  - non-abelian-higgs-mechanism
  - gauge-boson-mass-matrix
  - broken-gauge-generator
  - unbroken-gauge-subgroup
  - goldstone-counting
researchStatus:
  established:
    - "Perturbatively, every broken gauge generator supplies one would-be Goldstone mode that becomes the longitudinal polarization of a massive gauge boson."
  active:
    - "The global and nonperturbative distinction between Higgs, confinement, Coulomb, and topological phases depends on gauge-group global form, matter representations, line operators, and boundary conditions."
---

## Summary

The non-Abelian Higgs mechanism is the general version of the Abelian story. A scalar field $\phi$ transforms in a representation of a gauge group $G$. A vacuum configuration $\phi_0$ selects an unbroken subgroup

$$
H=\{h\in G\mid h^{-1}\phi_0=\phi_0\}.
$$

The gauge bosons associated with the unbroken generators of $H$ remain massless, while the gauge bosons associated with broken directions in $G/H$ become massive by absorbing would-be Goldstone modes.

In the simple case of one gauge coupling $g$ and Hermitian generators $T^a$ acting on $\phi$, the covariant derivative is

$$
D_\mu\phi=\partial_\mu\phi+igA_\mu^aT^a\phi.
$$

Expanding the scalar kinetic term around a constant vacuum $\phi_0$ gives the gauge-boson mass matrix

$$
(M^2)_{ab}
=
2g^2\,\operatorname{Re}\left[(T^a\phi_0)^\dagger(T^b\phi_0)\right].
$$

Generators satisfying

$$
T^a\phi_0=0
$$

produce zero rows and columns in this matrix. They generate the unbroken gauge algebra $\mathfrak h$. Generators satisfying

$$
T^a\phi_0\neq0
$$

are broken directions and generally produce massive vector bosons after diagonalizing $M^2$.

<figure class="doc-figure" style="--figure-width: 47rem;">

![Non-Abelian Higgs mechanism: a vacuum splits the gauge algebra into unbroken and broken directions, and the broken directions become massive vector bosons.](/figures/gauge-theories-standard-model/non-abelian-higgs-counting.svg)

<figcaption>

A scalar vacuum $\phi_0$ splits the Lie algebra into unbroken generators that annihilate $\phi_0$ and broken generators that move it. The mass matrix from $|D_\mu\phi|^2$ is zero along unbroken directions and nonzero along broken directions. The would-be Goldstone modes in $G/H$ become longitudinal vector polarizations.

</figcaption>
</figure>

The counting is the main idea:

$$
\text{number of eaten Goldstones}=\dim G-\dim H.
$$

This page explains the mechanism before applying it to the Standard Model Higgs doublet. The electroweak case is special because the gauge group is a product, the vacuum preserves $Q=T^3+Y$, and the neutral gauge bosons mix.

## Prerequisites

You should know [Abelian Higgs Model](/gauge-theories-standard-model/higgs-sector/abelian-higgs-model/), especially the idea that the angular scalar variable becomes part of a massive vector field. You should also know [Matter Representations](/gauge-theories-standard-model/gauge-principle/matter-representations/), [Covariant Derivative in Representations](/gauge-theories-standard-model/yang-mills/covariant-derivative-in-representations/), and [Gauge Boson Self-Interactions](/gauge-theories-standard-model/yang-mills/gauge-boson-self-interactions/).

For the Standard Model application, it helps to have read [SU(2)L × U(1)Y Gauge Structure](/gauge-theories-standard-model/electroweak/su2-u1-gauge-structure/) and [Electroweak Symmetry Breaking](/gauge-theories-standard-model/electroweak/electroweak-symmetry-breaking/).

## Core idea

A non-Abelian scalar vacuum does two jobs at once.

First, it identifies which gauge transformations leave the vacuum unchanged. These form the unbroken subgroup $H\subset G$.

Second, it gives masses to gauge bosons in directions that move the vacuum. Those directions are the broken generators. Their would-be Goldstone fields are not physical massless particles in the gauge theory; they become the longitudinal polarizations of massive vector bosons.

The conceptual slogan is

$$
G\longrightarrow H,
\qquad
\text{broken directions }G/H\text{ are eaten.}
$$

This notation is useful, but it should not be read as literal destruction of gauge redundancy. Gauge transformations remain redundancies of the description. The phrase $G\to H$ means that the perturbative spectrum around the chosen vacuum is organized as if the unbroken gauge fields are those of $H$, while the remaining gauge bosons are massive.

## Setup and conventions

Let $G$ be a compact gauge group with Lie algebra generators $T^a$ in the scalar representation $R$. We use Hermitian generators and the convention

$$
D_\mu=\partial_\mu+igA_\mu^aT^a.
$$

Matter fields transform as

$$
\phi\mapsto U_R^{-1}(x)\phi,
\qquad
U_R(x)=\exp\{ig\alpha^a(x)T_R^a\}.
$$

The scalar Lagrangian is

$$
\mathcal L_\phi=(D_\mu\phi)^\dagger(D^\mu\phi)-V(\phi),
$$

where $V$ is gauge invariant:

$$
V(U_R^{-1}\phi)=V(\phi).
$$

A vacuum is a constant field value $\phi_0$ minimizing $V$. The stabilizer of the vacuum is

$$
H=\{h\in G\mid h_R^{-1}\phi_0=\phi_0\}.
$$

At the Lie algebra level, an infinitesimal generator $T^a$ is unbroken if

$$
T^a\phi_0=0.
$$

The broken generators are those for which

$$
T^a\phi_0\neq0.
$$

Locally, one may split the algebra as a vector space,

$$
\mathfrak g=\mathfrak h\oplus\mathfrak k,
$$

where $\mathfrak h$ annihilates $\phi_0$ and $\mathfrak k$ moves it. The quotient $G/H$ is the vacuum manifold of the corresponding global symmetry problem; in the gauge theory, these directions become would-be Goldstone directions.

## Deriving the gauge-boson mass matrix

The gauge-boson masses come only from the scalar kinetic term. Expand around a constant vacuum,

$$
\phi(x)=\phi_0+\text{fluctuations}.
$$

Ignoring scalar fluctuations for the moment,

$$
D_\mu\phi_0=igA_\mu^aT^a\phi_0.
$$

Therefore

$$
(D_\mu\phi_0)^\dagger(D^\mu\phi_0)
=
g^2A_\mu^aA^{b\mu}(T^a\phi_0)^\dagger(T^b\phi_0).
$$

Since $A_\mu^aA^{b\mu}$ is symmetric under $a\leftrightarrow b$, only the real symmetric part contributes. Comparing with the standard vector mass term

$$
\mathcal L_{\rm mass}=\frac12A_\mu^a(M^2)_{ab}A^{b\mu},
$$

gives

$$
(M^2)_{ab}
=
2g^2\operatorname{Re}\left[(T^a\phi_0)^\dagger(T^b\phi_0)\right].
$$

This formula is worth remembering. It packages most of the perturbative Higgs mechanism into one line.

If $T^i\phi_0=0$, then

$$
(M^2)_{ib}=0
$$

for every $b$. Thus unbroken generators give massless gauge bosons. If $X^\alpha\phi_0\neq0$, the corresponding gauge bosons appear in the positive-semidefinite mass matrix. Diagonalizing $M^2$ gives the physical massive vector combinations.

For product gauge groups with different couplings, replace $gT^aA_\mu^a$ by the full sum of coupling-weighted generators. For example, in electroweak theory,

$$
D_\mu H
=
\left(\partial_\mu+igW_\mu^a\frac{\sigma^a}{2}+ig'YB_\mu\right)H,
$$

so the neutral mass matrix involves both $gT^3$ and $g'Y$.

## Goldstone modes and gauge choices

In the corresponding global symmetry problem, a vacuum with stabilizer $H$ produces

$$
\dim G-\dim H
$$

Goldstone modes. They are coordinates on $G/H$ near the chosen vacuum. A convenient parametrization is

$$
\phi(x)=\exp\left(\frac{i\pi^\alpha(x)X^\alpha}{v}\right)\bigl(\phi_0+\text{radial modes}\bigr),
$$

where $X^\alpha$ are broken generators and $\pi^\alpha$ are would-be Goldstone fields.

In a gauge theory, a local gauge transformation can remove the $\pi^\alpha$ fields from the scalar multiplet, at least perturbatively near a vacuum where the parametrization is nonsingular. This is unitary gauge. The same fields reappear as longitudinal polarizations of the massive gauge bosons.

In covariant $R_\xi$ gauges, the $\pi^\alpha$ fields remain explicit. They are assigned gauge-dependent masses proportional to $\xi$ times the corresponding vector masses, and they are accompanied by ghosts. This description is usually better for loop calculations and for proving gauge-parameter independence of physical observables.

The physics is independent of this choice:

| Description | What it shows clearly | What it hides |
|---|---|---|
| Unitary gauge | physical particle content | power counting and gauge identities |
| Covariant $R_\xi$ gauges | propagators, ghosts, BRST identities | simple physical spectrum |
| Gauge-invariant language | observables and phase diagnostics | elementary perturbative fields |

The same Higgs mechanism is being described in three different coordinate systems.

## Degree-of-freedom counting

Suppose $G$ has dimension $\dim G$, the unbroken subgroup has dimension $\dim H$, and the scalar sector has $N_{\rm real}$ real scalar components.

Before the Higgs reorganization, perturbatively one has

$$
2\dim G+N_{\rm real}
$$

physical modes: two polarizations for each massless gauge boson plus the scalar modes.

After the Higgs reorganization:

- $\dim H$ gauge bosons remain massless, giving $2\dim H$ modes;
- $\dim G-\dim H$ gauge bosons become massive, giving $3(\dim G-\dim H)$ modes;
- $\dim G-\dim H$ scalar modes are eaten;
- the remaining scalar modes are

$$
N_{\rm phys}=N_{\rm real}-(\dim G-\dim H),
$$

assuming the vacuum breaks independent directions and there are no additional flat directions.

The total after the reorganization is therefore

$$
2\dim H+3(\dim G-\dim H)+N_{\rm phys}
=
2\dim G+N_{\rm real}.
$$

The number of local perturbative degrees of freedom is unchanged. The representation of those degrees of freedom has changed.

## Example: SU(2) with an adjoint scalar

Let $G=SU(2)$ and take a real adjoint scalar $\phi^a$. It is convenient to write

$$
\Phi=\phi^aT^a,
$$

with gauge transformation by conjugation. Choose a vacuum in the third direction,

$$
\phi_0^a=v\delta^{a3}.
$$

The generator $T^3$ leaves the vacuum direction fixed, while $T^1$ and $T^2$ rotate it. The breaking pattern is

$$
SU(2)\longrightarrow U(1).
$$

There are two broken generators, so two gauge bosons become massive and one remains massless. In a standard normalization, the masses are

$$
m_{A^1}=m_{A^2}=gv,
\qquad
m_{A^3}=0.
$$

This example is the gauge-theory prototype behind the Georgi–Glashow model and magnetic monopoles. The unbroken $U(1)$ gauge field is the long-range photon-like field of the low-energy theory. The vacuum manifold of the global problem is $SU(2)/U(1)\simeq S^2$, which is why monopole topology appears in the gauged model.

## Example: SU(2) with a fundamental doublet

Now take $G=SU(2)$ and a complex scalar doublet

$$
\phi=\begin{pmatrix}\phi_1\\ \phi_2\end{pmatrix},
\qquad
T^a=\frac{\sigma^a}{2}.
$$

Choose

$$
\phi_0=\frac{1}{\sqrt2}\begin{pmatrix}0\\ v\end{pmatrix}.
$$

No nonzero $SU(2)$ generator annihilates this vector. Therefore the gauge group is completely broken:

$$
SU(2)\longrightarrow \{1\}.
$$

There are three broken generators, so all three gauge bosons become massive. Since

$$
(T^a\phi_0)^\dagger(T^b\phi_0)=\frac{v^2}{8}\delta^{ab}
$$

in the symmetric part, the mass matrix is

$$
(M^2)_{ab}=\frac{g^2v^2}{4}\delta^{ab}.
$$

Hence

$$
m_A=\frac{gv}{2}
$$

for all three gauge bosons.

This is close to the electroweak Higgs mechanism, but not identical. The Standard Model has $SU(2)_L\times U(1)_Y$, not just $SU(2)$. The extra $U(1)_Y$ factor combines with $T^3$ so that one generator remains unbroken: electric charge.

## Electroweak preview

For the Standard Model Higgs doublet,

$$
H_0=\frac{1}{\sqrt2}\begin{pmatrix}0\\ v\end{pmatrix},
\qquad
Y_H=\frac12.
$$

The neutral part of the covariant derivative acting on the vacuum is proportional to

$$
\left(-\frac{g}{2}W_\mu^3+\frac{g'}{2}B_\mu\right)H_0.
$$

Thus the neutral mass term is

$$
\frac{v^2}{8}(gW_\mu^3-g'B_\mu)^2.
$$

The orthogonal combination is massless and becomes the photon. The massive combination becomes the $Z$ boson. The charged combinations

$$
W_\mu^\pm=\frac{1}{\sqrt2}(W_\mu^1\mp iW_\mu^2)
$$

have mass

$$
m_W=\frac{gv}{2},
$$

while

$$
m_Z=\frac{\sqrt{g^2+g'^2}}{2}v.
$$

This is not a new mechanism. It is the non-Abelian Higgs mechanism applied to the representation

$$
H\sim(\mathbf 1,\mathbf 2)_{1/2}
$$

of $SU(3)_c\times SU(2)_L\times U(1)_Y$.

## Gauge-invariant interpretation

Perturbation theory around a chosen $\phi_0$ is powerful, but one should remember what is gauge invariant.

The field $\phi$ is generally gauge charged. Therefore $\langle\phi\rangle$ is not a gauge-invariant observable. Choosing $\phi_0$ is a way to pick convenient coordinates on field space after gauge fixing. Gauge-invariant statements include:

- the spectrum of physical excitations;
- the existence or absence of massless gauge bosons associated with unbroken gauge factors;
- correlation functions of gauge-invariant composite operators;
- line-operator behavior, such as Wilson and 't Hooft loop diagnostics;
- topological sectors and defects, when the vacuum manifold and gauge-group global form allow them.

This matters most beyond perturbation theory. In a weakly coupled continuum expansion, the statement “$G$ breaks to $H$” is a reliable shorthand. In lattice gauge theory or strongly coupled regimes, the distinction between Higgs-like and confinement-like behavior can depend on the matter representation and available line operators.

## Common pitfalls

**Counting all generators as broken because the scalar has a nonzero vacuum value.** A generator is unbroken if it annihilates the vacuum. Nonzero $\phi_0$ does not automatically break every generator.

**Forgetting to include gauge couplings in product groups.** The mass matrix is built from coupling-weighted generators. In $SU(2)_L\times U(1)_Y$, the neutral mass matrix involves both $gT^3$ and $g'Y$.

**Confusing the vacuum manifold of a global theory with physical Goldstone particles in a gauge theory.** The space $G/H$ still organizes the would-be Goldstone directions, but those modes are gauge variables in the Higgs phase.

**Using unitary gauge to do every calculation.** It is great for spectrum counting but often poor for loop power counting. Covariant gauges keep the Goldstone and ghost sectors visible.

**Assuming “broken gauge symmetry” is a gauge-invariant order parameter.** Gauge symmetry is redundancy. Physical phase distinctions require gauge-invariant observables.

**Ignoring representation dependence.** The same gauge group can have different Higgs patterns depending on whether the scalar is fundamental, adjoint, symmetric, antisymmetric, or a product representation.

**Ignoring the global form of the gauge group.** The local Lie algebra controls perturbative masses, but line operators, allowed charges, defects, and topological sectors can depend on whether the group is, for example, $SU(N)$ or $SU(N)/\mathbb Z_N$.

## Relations to other pages

This page follows [Abelian Higgs Model](/gauge-theories-standard-model/higgs-sector/abelian-higgs-model/) and prepares [Standard Model Higgs Doublet](/gauge-theories-standard-model/higgs-sector/standard-model-higgs-doublet/). The electroweak pages [Electroweak Symmetry Breaking](/gauge-theories-standard-model/electroweak/electroweak-symmetry-breaking/) and [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/) contain the same mechanism specialized to $SU(2)_L\times U(1)_Y$.

For the group-theory background, see [Matter Representations](/gauge-theories-standard-model/gauge-principle/matter-representations/) and [Color and Representations](/gauge-theories-standard-model/yang-mills/color-and-representations/). For the quantum gauge-fixing background, see [Ghosts and Gauge-Fixed Action](/gauge-theories-standard-model/gauge-quantization/ghosts-and-gauge-fixed-action/) and [BRST Symmetry in Gauge Theory](/gauge-theories-standard-model/gauge-quantization/brst-symmetry-in-gauge-theory/).

For nonperturbative phase diagnostics, return to [Wilson Loops](/gauge-theories-standard-model/wilson-loops-confinement/wilson-loops/), ['t Hooft Loops](/gauge-theories-standard-model/wilson-loops-confinement/thooft-loops/), and [Center Symmetry and Confinement](/gauge-theories-standard-model/wilson-loops-confinement/center-symmetry-and-confinement/).

## Research status

The perturbative non-Abelian Higgs mechanism is settled. It is the standard mechanism by which the Standard Model gives masses to $W^\pm$ and $Z$ while preserving the photon.

The active subtleties are global and nonperturbative. Gauge-group global form, matter representations, line operators, monopoles, vortices, confinement-like regimes, and boundary conditions can change the correct phase language. These questions are not contradictions of the perturbative Higgs mechanism; they are reminders that local mass matrices do not exhaust the global content of a gauge theory.

## Exercises

### Exercise 1: Show that unbroken generators give zero mass

Starting from

$$
(M^2)_{ab}=2g^2\operatorname{Re}\left[(T^a\phi_0)^\dagger(T^b\phi_0)\right],
$$

show that if $T^i\phi_0=0$, then $(M^2)_{ib}=0$ for every $b$.

<details><summary><strong>Solution</strong></summary>

If $T^i\phi_0=0$, then

$$
(T^i\phi_0)^\dagger(T^b\phi_0)=0
$$

for every $b$. Therefore

$$
(M^2)_{ib}=2g^2\operatorname{Re}(0)=0.
$$

By symmetry of the real mass matrix, $(M^2)_{bi}=0$ as well. Thus the gauge boson associated with $T^i$ has no mass term from the vacuum.

</details>

### Exercise 2: SU(2) adjoint breaking

Let $G=SU(2)$ and take an adjoint scalar with vacuum $\phi_0^a=v\delta^{a3}$. Show that the unbroken group is $U(1)$ and that two gauge bosons become massive.

<details><summary><strong>Solution</strong></summary>

In the adjoint representation, infinitesimal transformations rotate the vector $\phi^a$ in internal three-dimensional space. A vacuum pointing in the $a=3$ direction is invariant under rotations around the third axis, generated by $T^3$. The generators $T^1$ and $T^2$ move the vacuum direction.

Thus

$$
SU(2)\to U(1),
$$

with one unbroken generator and two broken generators. The gauge boson $A_\mu^3$ remains massless, while $A_\mu^1$ and $A_\mu^2$ become massive. In standard normalization their masses are $gv$.

</details>

### Exercise 3: SU(2) fundamental breaking

Let

$$
\phi_0=\frac{1}{\sqrt2}\begin{pmatrix}0\\v\end{pmatrix},
\qquad
T^a=\frac{\sigma^a}{2}.
$$

Show that all three $SU(2)$ gauge bosons acquire mass $gv/2$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
T^1\phi_0=\frac{v}{2\sqrt2}\begin{pmatrix}1\\0\end{pmatrix},
\qquad
T^2\phi_0=\frac{v}{2\sqrt2}\begin{pmatrix}-i\\0\end{pmatrix},
\qquad
T^3\phi_0=\frac{v}{2\sqrt2}\begin{pmatrix}0\\-1\end{pmatrix}.
$$

The real symmetric products satisfy

$$
\operatorname{Re}\left[(T^a\phi_0)^\dagger(T^b\phi_0)\right]
=\frac{v^2}{8}\delta^{ab}.
$$

Therefore

$$
(M^2)_{ab}=2g^2\frac{v^2}{8}\delta^{ab}
=\frac{g^2v^2}{4}\delta^{ab}.
$$

All three gauge bosons have

$$
m=\frac{gv}{2}.
$$

</details>

### Exercise 4: Electroweak neutral mass matrix

For

$$
H_0=\frac{1}{\sqrt2}\begin{pmatrix}0\\v\end{pmatrix},
\qquad
Y_H=\frac12,
$$

show that the neutral mass term is

$$
\frac{v^2}{8}(gW_\mu^3-g'B_\mu)^2.
$$

Find the nonzero mass eigenvalue.

<details><summary><strong>Solution</strong></summary>

The lower component of the Higgs doublet has

$$
T^3=-\frac12,
\qquad
Y=\frac12.
$$

Thus the neutral part of the covariant derivative acting on $H_0$ is

$$
i\left(gW_\mu^3T^3+g'B_\mu Y\right)H_0
=
\frac{i}{2}(-gW_\mu^3+g'B_\mu)H_0.
$$

Taking the norm gives

$$
|D_\mu H_0|^2_{\rm neutral}
=
\frac{v^2}{8}(gW_\mu^3-g'B_\mu)^2.
$$

Writing this as $\frac12 V_\mu^T M^2 V^\mu$ with $V_\mu=(W_\mu^3,B_\mu)$ gives

$$
M^2=\frac{v^2}{4}
\begin{pmatrix}
g^2 & -gg'\\
-gg' & g'^2
\end{pmatrix}.
$$

The eigenvalues are

$$
0,
\qquad
\frac{v^2}{4}(g^2+g'^2).
$$

The zero eigenvalue is the photon, and the nonzero eigenvalue gives

$$
m_Z=\frac{v}{2}\sqrt{g^2+g'^2}.
$$

</details>

### Exercise 5: Degree counting

Suppose $G$ has dimension $10$, the unbroken subgroup $H$ has dimension $4$, and the scalar multiplet has $14$ real components. How many massive vectors, massless vectors, and physical scalar modes are present after the Higgs reorganization?

<details><summary><strong>Solution</strong></summary>

The number of broken generators is

$$
\dim G-\dim H=10-4=6.
$$

So there are $6$ massive vector bosons and $4$ massless vector bosons. The $6$ broken directions eat $6$ scalar modes, leaving

$$
N_{\rm phys}=14-6=8
$$

physical scalar modes, assuming no additional constraints or flat-direction subtleties.

The mode count checks:

$$
2\dim G+N_{\rm real}=20+14=34,
$$

while after the reorganization

$$
2\dim H+3(\dim G-\dim H)+N_{\rm phys}
=8+18+8=34.
$$

</details>

## References

- Srednicki, *Quantum Field Theory*, §§84 and 86–87, for spontaneous breaking of gauge symmetries, non-Abelian Higgs mechanism, and the Standard Model gauge and Higgs sector.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 28–29, for the Higgs mechanism and weak interactions.
- Coleman, *Aspects of Symmetry*, Ch. 5, “Secret Symmetry,” for the classic explanation of Goldstone modes, Yang–Mills fields, and the Higgs phenomenon.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for spontaneously broken gauge theories and electroweak applications.

## Version history

- **2026-06-18:** Initial polished draft. Added the mass-matrix derivation, Goldstone counting, $SU(2)$ examples, electroweak preview, exercises, and non-Abelian Higgs figure.
