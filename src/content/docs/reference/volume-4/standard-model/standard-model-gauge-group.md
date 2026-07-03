---
title: "Standard Model Gauge Group"
description: "Explains the Standard Model gauge algebra, conventional product group, hypercharge convention, gauge bosons, covariant derivative, and global-form caveat."
sidebar:
  label: "Standard Model Gauge Group"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–89; Schwartz Chs. 25 and 29–30; Burgess Ch. 9; Weinberg Vol. II electroweak chapters."
topics:
  - Standard Model gauge group
  - hypercharge
  - electroweak gauge group
  - color gauge group
  - global form
canonicalTopics:
  - standard-model-gauge-group
  - standard-model-gauge-algebra
  - weak-hypercharge
  - electric-charge-generator
  - standard-model-global-form
researchStatus:
  established:
    - "The local Standard Model gauge algebra and its action on the known fields are textbook-standard and experimentally successful."
  active:
    - "The global form of the gauge group and its line-operator and topological-sector consequences are established structural questions, but they are usually invisible in first-pass perturbation theory."
---

## Summary

The Standard Model gauge algebra is

$$
\mathfrak g_{\rm SM}
=
\mathfrak{su}(3)_c\oplus\mathfrak{su}(2)_L\oplus\mathfrak u(1)_Y.
$$

On a first perturbative pass, physicists usually write the corresponding gauge group as

$$
G_{\rm SM}^{\rm prod}=SU(3)_c\times SU(2)_L\times U(1)_Y.
$$

The three factors describe color, weak isospin, and weak hypercharge. The gauge fields are

$$
G_\mu^A,
\qquad
W_\mu^I,
\qquad
B_\mu,
$$

with couplings $g_s$, $g$, and $g'$. Electric charge is not $Y$ by itself. In this volume's convention,

$$
Q=T^3+Y.
$$

After electroweak symmetry breaking, the Higgs vacuum leaves $SU(3)_c\times U(1)_{\rm em}$ unbroken.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Standard Model gauge group map](/figures/gauge-theories-standard-model/standard-model-gauge-group-map.svg)

<figcaption>

The local Standard Model gauge structure has three factors before electroweak symmetry breaking. The Higgs vacuum leaves color unbroken and selects the electromagnetic generator $Q=T^3+Y$ inside $SU(2)_L\times U(1)_Y$.

</figcaption>
</figure>

There is a subtle global caveat. The local formulas only see the Lie algebra. The full gauge group can be a quotient of the product group, with the common choice

$$
G_{\rm SM}
=
\frac{SU(3)_c\times SU(2)_L\times U(1)_Y}{\mathbb Z_6}.
$$

The quotient does not change ordinary tree-level Feynman rules, but it matters for allowed representations, line operators, bundles, magnetic charges, and topological sectors. This page explains the local structure and flags the global-form issue; the next page treats the quotient carefully.

## Prerequisites

You should know [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/), [Electroweak Covariant Derivative](/gauge-theories-standard-model/electroweak/electroweak-covariant-derivative/), [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/), [Color SU(3)](/gauge-theories-standard-model/qcd/color-su3/), and [Standard Model Fermion Representations](/gauge-theories-standard-model/flavor-neutrinos/standard-model-fermion-representations/).

The only convention to tattoo on the inside of your eyelids is

$$
Q=T^3+Y,
$$

not $Q=T^3+Y/2$. Many books use the latter with a different normalization of hypercharge. Same physics; different bookkeeping gremlin.

## Core idea

A gauge group does two jobs at once.

First, it tells you which local frame rotations are redundancies. Color, weak isospin, and hypercharge frames can be chosen independently at each spacetime point, so the theory needs gauge fields that transform as connections.

Second, it tells you which matter representations are allowed. Once a field is assigned a representation of $SU(3)_c\times SU(2)_L$ and a hypercharge $Y$, its gauge interactions are fixed by the covariant derivative. The Standard Model is astonishingly constrained because the same representation assignments must also permit Yukawa couplings, give the observed electric charges, and cancel gauge anomalies.

The story is therefore not

$$
\text{choose particles}\quad\Longrightarrow\quad\text{decorate with forces}.
$$

It is closer to

$$
\text{choose gauge structure and representations}
\quad\Longrightarrow\quad
\text{allowed fields, interactions, charges, and consistency checks}.
$$

## Setup and conventions

We use the volume convention

$$
D_\mu=\partial_\mu+i g A_\mu^aT^a,
$$

so for a field $\Psi$ in representation $R_3$ of color, representation $R_2$ of weak isospin, and hypercharge $Y$, the Standard Model covariant derivative is

$$
D_\mu\Psi
=
\left(
\partial_\mu
+i g_sG_\mu^AT_{R_3}^A
+i g W_\mu^It_{R_2}^I
+i g'YB_\mu
\right)\Psi.
$$

For singlet representations, the corresponding generators vanish. For example, a right-handed charged lepton has no color and no weak-isospin generator, so only the hypercharge piece acts on it.

The non-Abelian field strengths follow the same sign convention:

$$
G_{\mu\nu}^A
=
\partial_\mu G_\nu^A-\partial_\nu G_\mu^A
-g_sf^{ABC}G_\mu^BG_\nu^C,
$$

$$
W_{\mu\nu}^I
=
\partial_\mu W_\nu^I-\partial_\nu W_\mu^I
-g\epsilon^{IJK}W_\mu^JW_\nu^K,
$$

and

$$
B_{\mu\nu}=\partial_\mu B_\nu-\partial_\nu B_\mu.
$$

The gauge kinetic terms are

$$
\mathcal L_{\rm gauge}
=
-\frac14G_{\mu\nu}^AG^{A\mu\nu}
-\frac14W_{\mu\nu}^IW^{I\mu\nu}
-\frac14B_{\mu\nu}B^{\mu\nu}.
$$

## The three factors

The Standard Model gauge factors have very different personalities.

| Factor | Gauge bosons | Coupling | Acts nontrivially on | Physical role |
|---|---:|---:|---|---|
| $SU(3)_c$ | $G_\mu^A$, $A=1,\ldots,8$ | $g_s$ | quarks and gluons | strong interaction, color confinement, asymptotic freedom |
| $SU(2)_L$ | $W_\mu^I$, $I=1,2,3$ | $g$ | left-handed doublets and Higgs | charged weak currents, neutral weak current, Higgs mechanism |
| $U(1)_Y$ | $B_\mu$ | $g'$ | all fields with hypercharge | weak hypercharge, mixes with $W^3$ to make $A$ and $Z$ |

The subscript $L$ in $SU(2)_L$ is not decorative. It means that the weak-isospin doublets are left-handed fermions:

$$
Q_L=\begin{pmatrix}u_L\\ d_L\end{pmatrix},
\qquad
L_L=\begin{pmatrix}\nu_L\\ e_L\end{pmatrix}.
$$

The corresponding right-handed charged fermions $u_R$, $d_R$, and $e_R$ are weak singlets. A right-handed neutrino $\nu_R$ does not appear in the minimal renormalizable Standard Model, while $\nu_L$ is locked inside the lepton doublet $L_L$. This is the representation-theoretic seed of weak parity violation and of the special status of neutrino masses.

## Electric charge from weak isospin and hypercharge

The Higgs doublet has

$$
H=\begin{pmatrix}H^+\\ H^0\end{pmatrix},
\qquad
H\sim(\mathbf1,\mathbf2)_{1/2}.
$$

The upper component has $T^3=+1/2$ and the lower component has $T^3=-1/2$, so

$$
Q(H^+)=\frac12+\frac12=1,
\qquad
Q(H^0)=-\frac12+\frac12=0.
$$

The neutral component can therefore take a vacuum expectation value without breaking electromagnetism:

$$
\langle H\rangle
=\frac{1}{\sqrt2}\begin{pmatrix}0\\ v\end{pmatrix},
\qquad
Q\langle H\rangle=0.
$$

This leaves the unbroken gauge symmetry

$$
SU(3)_c\times U(1)_{\rm em}.
$$

The neutral electroweak gauge bosons rotate into the photon and $Z$ boson:

$$
A_\mu=s_W W_\mu^3+c_WB_\mu,
\qquad
Z_\mu=c_W W_\mu^3-s_WB_\mu,
$$

with

$$
\tan\theta_W=\frac{g'}{g},
\qquad
s_W=\sin\theta_W,
\qquad
c_W=\cos\theta_W,
\qquad
e=gs_W=g'c_W.
$$

The photon couples to $Q$, while the $Z$ couples to the orthogonal neutral generator.

## Matter representations as a consistency ledger

For one generation, the minimal Standard Model fermions are

| Field | Representation under $SU(3)_c\times SU(2)_L\times U(1)_Y$ | Electric charges |
|---|---:|---:|
| $Q_L=(u_L,d_L)^T$ | $(\mathbf3,\mathbf2)_{1/6}$ | $2/3,-1/3$ |
| $u_R$ | $(\mathbf3,\mathbf1)_{2/3}$ | $2/3$ |
| $d_R$ | $(\mathbf3,\mathbf1)_{-1/3}$ | $-1/3$ |
| $L_L=(\nu_L,e_L)^T$ | $(\mathbf1,\mathbf2)_{-1/2}$ | $0,-1$ |
| $e_R$ | $(\mathbf1,\mathbf1)_{-1}$ | $-1$ |
| $H$ | $(\mathbf1,\mathbf2)_{1/2}$ | $1,0$ |

This table is doing a suspicious amount of work. It gives the observed electric charges. It permits the Yukawa couplings

$$
\bar Q_LY_dHd_R,
\qquad
\bar Q_LY_u\tilde H u_R,
\qquad
\bar L_LY_eHe_R.
$$

It also makes gauge anomalies cancel generation by generation once the fermion content is treated consistently as left-handed Weyl fields. That last fact is not aesthetic; without gauge-anomaly cancellation, the quantum theory would not have a well-defined gauge symmetry.

## Product group versus quotient group

For local perturbative calculations, the gauge algebra is often enough. That is why the product notation

$$
SU(3)_c\times SU(2)_L\times U(1)_Y
$$

is ubiquitous. It correctly gives gauge bosons, covariant derivatives, Feynman rules, Ward identities, and the usual renormalizable Lagrangian.

But a Lie algebra does not determine the global group. The Standard Model representation table is compatible with quotienting by a common subgroup of the centers. In an integral hypercharge normalization

$$
\mathsf y=6Y,
$$

the element

$$
\left(e^{2\pi i/3}\mathbf1_3,\,-\mathbf1_2,\,e^{i\pi/3}\right)
$$

acts trivially on every minimal Standard Model matter and Higgs multiplet. This is the origin of the frequently written global form

$$
\frac{SU(3)_c\times SU(2)_L\times U(1)_Y}{\mathbb Z_6}.
$$

One can also consider quotients by subgroups, depending on the spectrum of allowed line operators and global assumptions about the theory. The next page is devoted to this issue. For the present page, the main rule is simple: do not confuse the local algebra needed for Feynman rules with the full global gauge group needed for nonperturbative and topological questions.

## Checks

A good gauge-group assignment survives several basic checks.

**Charge check.** For every component of every weak doublet, compute $Q=T^3+Y$. The table above must reproduce $u,d,\nu,e,H^+,H^0$ charges.

**Yukawa check.** Each renormalizable Yukawa operator must be a singlet under $SU(3)_c\times SU(2)_L\times U(1)_Y$. Hypercharge cancellation is especially quick:

$$
Y(\bar Q_L)+Y(H)+Y(d_R)
=-\frac16+\frac12-\frac13=0,
$$

$$
Y(\bar Q_L)+Y(\tilde H)+Y(u_R)
=-\frac16-\frac12+\frac23=0,
$$

$$
Y(\bar L_L)+Y(H)+Y(e_R)
=\frac12+\frac12-1=0.
$$

**Higgs-vacuum check.** The lower component of $H$ has $Q=0$, so the vacuum can preserve electromagnetism while breaking $SU(2)_L\times U(1)_Y$.

**Anomaly check.** The chiral fermion representations must make all gauge anomalies cancel. The detailed proof belongs to the anomaly-cancellation page, but the gauge group already tells you which anomaly sums must vanish.

## Common pitfalls

**Using $Q=T^3+Y/2$ without changing $Y$.** Some books call twice our hypercharge “$Y$.” If you import a table from such a convention without rescaling, every charge looks wrong by committee.

**Saying the photon is the $U(1)_Y$ gauge boson.** Before symmetry breaking, $B_\mu$ is the hypercharge gauge field. The photon is the unbroken linear combination $A_\mu=s_WW_\mu^3+c_WB_\mu$.

**Forgetting that $SU(2)_L$ acts only on left-handed fermion doublets.** The right-handed charged fermions are weak singlets. This is why bare Dirac mass terms are forbidden before electroweak symmetry breaking.

**Treating global form as pedantry.** It is pedantry for a tree-level cross section, maybe. It is not pedantry for line operators, monopoles, bundles, higher-form symmetries, or questions about what gauge theory has actually been specified.

**Confusing a basis choice with new physics.** Gauge eigenstates, weak-interaction eigenstates, and mass eigenstates can be different bases for the same fields. CKM and PMNS matrices are physical only after accounting for which field rotations are allowed.

## Relations to other pages

- [Electroweak Covariant Derivative](/gauge-theories-standard-model/electroweak/electroweak-covariant-derivative/) derives the $SU(2)_L\times U(1)_Y$ part of the derivative used here.
- [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/) explains the neutral gauge-boson rotation after the Higgs vacuum appears.
- [Color SU(3)](/gauge-theories-standard-model/qcd/color-su3/) gives the concrete $SU(3)_c$ representation data behind the color factor.
- [Standard Model Fermion Representations](/gauge-theories-standard-model/flavor-neutrinos/standard-model-fermion-representations/) records the chiral matter table in more detail.
- [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/) explains the leading Standard-Model-gauge-invariant operator that gives Majorana neutrino masses.
- [Global Form of the Standard Model Gauge Group](/gauge-theories-standard-model/standard-model/global-form-of-standard-model-gauge-group/) continues from the global-form warning in this page.

## Research status

The local gauge algebra, field representations, and hypercharge assignments of the minimal Standard Model are settled textbook material. They are also experimentally overconstrained: color, charged weak currents, neutral currents, electromagnetic charges, and Higgs couplings all test different parts of the same architecture.

The global form of the Standard Model gauge group is a more structural question. It does not change ordinary perturbative vertices, but it changes what counts as an allowed bundle or line operator. This topic is established mathematics and physics, but its phenomenological role depends on what ultraviolet completion or nonperturbative definition one has in mind.

## Exercises

### Exercise 1: Reconstruct the electric charges

Using $Q=T^3+Y$, compute the electric charges of the components of $Q_L$, $L_L$, and $H$ from their hypercharges.

<details>
<summary><strong>Solution</strong></summary>

For $Q_L\sim(\mathbf3,\mathbf2)_{1/6}$, the upper component has $T^3=+1/2$ and the lower has $T^3=-1/2$, so

$$
Q(u_L)=\frac12+\frac16=\frac23,
\qquad
Q(d_L)=-\frac12+\frac16=-\frac13.
$$

For $L_L\sim(\mathbf1,\mathbf2)_{-1/2}$,

$$
Q(\nu_L)=\frac12-\frac12=0,
\qquad
Q(e_L)=-\frac12-\frac12=-1.
$$

For $H\sim(\mathbf1,\mathbf2)_{1/2}$,

$$
Q(H^+)=\frac12+\frac12=1,
\qquad
Q(H^0)=-\frac12+\frac12=0.
$$

</details>

### Exercise 2: Check the down-type Yukawa hypercharge

Show that $\bar Q_LHd_R$ is neutral under $U(1)_Y$.

<details>
<summary><strong>Solution</strong></summary>

The conjugate field $\bar Q_L$ carries hypercharge $-Y(Q_L)=-1/6$. Therefore

$$
Y(\bar Q_L)+Y(H)+Y(d_R)
=-\frac16+\frac12-\frac13
=\frac{-1+3-2}{6}=0.
$$

The operator is also a color singlet after contracting the $\bar{\mathbf3}$ from $\bar Q_L$ with the $\mathbf3$ from $d_R$, and an $SU(2)_L$ singlet after contracting the two doublets.

</details>

### Exercise 3: Identify the unbroken neutral generator

Use $H\to(0,v/\sqrt2)^T$ to show that the generator preserved by the Higgs vacuum is $Q=T^3+Y$.

<details>
<summary><strong>Solution</strong></summary>

The vacuum lies in the lower component of the Higgs doublet. For that component,

$$
T^3=-\frac12,
\qquad
Y=\frac12.
$$

Thus

$$
Q\langle H\rangle=(T^3+Y)\langle H\rangle=0.
$$

The orthogonal neutral generator does not annihilate the vacuum and is broken; its gauge field becomes the massive $Z$ boson.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the Standard Model gauge/Higgs, lepton, and quark sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the Yang–Mills, weak-interaction, and anomaly chapters.
- Burgess, *Introduction to Effective Field Theory*, especially the Standard Model as an effective theory.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for a comprehensive treatment of the electroweak theory and Standard Model structure.
- Coleman, *Aspects of Symmetry*, especially the lectures on unitary symmetry and spontaneous symmetry breaking with gauge fields.

## Version history

- **2026-06-19:** Initial page on the Standard Model gauge group and global-form caveat.
