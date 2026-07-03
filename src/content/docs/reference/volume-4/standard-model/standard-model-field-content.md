---
title: "Standard Model Field Content"
description: "Records the gauge representations of the Standard Model gauge bosons, chiral fermions, Higgs doublet, and optional singlet neutrinos in the convention Q = T3 + Y."
sidebar:
  label: "Standard Model Field Content"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–91; Schwartz Chs. 29–31; Burgess Ch. 9; Weinberg Vol. II electroweak and Standard Model material."
topics:
  - Standard Model field content
  - fermion representations
  - Higgs doublet
  - gauge bosons
  - hypercharge
canonicalTopics:
  - standard-model-field-content
  - standard-model-fermion-representations
  - standard-model-higgs-representation
  - standard-model-gauge-bosons
  - standard-model-generations
researchStatus:
  established:
    - "The minimal renormalizable Standard Model field content and its gauge representations are textbook-standard and strongly constrained by observed charges, weak interactions, Yukawa couplings, and anomaly cancellation."
  active:
    - "Observed neutrino masses require either effective operators or additional fields beyond the minimal renormalizable field content; dark matter and other open problems likewise require extensions or new sectors."
---

## Summary

The Standard Model field content is a short representation table with an unreasonable amount of physics packed inside it. Before electroweak symmetry breaking, the gauge algebra is

$$
\mathfrak{su}(3)_c\oplus\mathfrak{su}(2)_L\oplus\mathfrak u(1)_Y,
$$

and the fields are:

- gauge bosons for the three gauge factors;
- three replicated generations of chiral fermions;
- one complex Higgs doublet.

In this volume's convention,

$$
Q=T^3+Y.
$$

The one-generation matter table, together with the Higgs representation, is

| Field | Representation | Components | Electric charges |
|---|---:|---|---:|
| $Q_L$ | $(\mathbf3,\mathbf2)_{1/6}$ | $(u_L,d_L)$ with three colors | $2/3,-1/3$ |
| $u_R$ | $(\mathbf3,\mathbf1)_{2/3}$ | right-handed up-type quark | $2/3$ |
| $d_R$ | $(\mathbf3,\mathbf1)_{-1/3}$ | right-handed down-type quark | $-1/3$ |
| $L_L$ | $(\mathbf1,\mathbf2)_{-1/2}$ | $(\nu_L,e_L)$ | $0,-1$ |
| $e_R$ | $(\mathbf1,\mathbf1)_{-1}$ | right-handed charged lepton | $-1$ |
| $H$ | $(\mathbf1,\mathbf2)_{1/2}$ | $(H^+,H^0)$ | $1,0$ |

<figure class="doc-figure" style="--figure-width: 58rem;">

![Standard Model field-content ledger](/figures/gauge-theories-standard-model/standard-model-field-content-ledger.svg)

<figcaption>

The Standard Model fields before electroweak symmetry breaking: gauge bosons in adjoint representations, three generations of chiral matter, and one Higgs doublet. The representation labels use $(SU(3)_c,SU(2)_L)_Y$ with $Q=T^3+Y$.

</figcaption>
</figure>

The punchline is not merely “these are the particles.” The punchline is

$$
\text{field content}
=
\text{representation data that makes the gauge theory possible}.
$$

## Prerequisites

You should know the [Standard Model Gauge Group](/gauge-theories-standard-model/standard-model/standard-model-gauge-group/), [Global Form of the Standard Model Gauge Group](/gauge-theories-standard-model/standard-model/global-form-of-standard-model-gauge-group/), [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/), [Yukawa Couplings](/gauge-theories-standard-model/flavor-neutrinos/yukawa-couplings/), and [Fermion Mass Matrices](/gauge-theories-standard-model/flavor-neutrinos/fermion-mass-matrices/).

The page uses mostly Standard Model phenomenology notation with left-handed doublets and right-handed singlets. When discussing anomalies, it switches to the all-left-handed Weyl notation because gauge anomalies are most cleanly counted using left-handed Weyl fields.

## Core idea

A field in a gauge theory is not specified only by its spin and name. It must carry a representation of the gauge group. The Standard Model representation labels are usually written

$$
(R_3,R_2)_Y,
$$

where $R_3$ is the color representation, $R_2$ is the weak-isospin representation, and $Y$ is weak hypercharge.

Once the representation is fixed, the gauge interactions are fixed. For a field $\Psi\sim(R_3,R_2)_Y$,

$$
D_\mu\Psi
=
\left(
\partial_\mu
+i g_sG_\mu^AT_{R_3}^A
+i gW_\mu^It_{R_2}^I
+i g'YB_\mu
\right)\Psi.
$$

There is no independent knob for “how much a quark couples to gluons” after choosing $g_s$ and the representation $\mathbf3$. There is no independent knob for “which charged weak current exists” after choosing left-handed doublets and right-handed singlets. The representation table is the skeleton; the Lagrangian is the muscle.

## Setup and conventions

We use

$$
Q=T^3+Y,
\qquad
\mathsf y=6Y
$$

when integral hypercharge is convenient. The Higgs doublet is

$$
H=
\begin{pmatrix}H^+\\ H^0\end{pmatrix},
\qquad
H\sim(\mathbf1,\mathbf2)_{1/2},
$$

and

$$
\tilde H=i\sigma^2H^*
\sim(\mathbf1,\mathbf2)_{-1/2}.
$$

Generation indices are denoted by

$$
i,j=1,2,3.
$$

Color indices are denoted by

$$
a,b=1,2,3,
$$

and weak doublet indices by

$$
\alpha,\beta=1,2.
$$

The phrase “minimal renormalizable Standard Model” means the theory with no right-handed neutrino field and no higher-dimensional Weinberg operator. The modern effective-field-theory viewpoint allows higher-dimensional operators, and neutrino data force some extension of the minimal neutrino sector.

## Gauge fields

The gauge fields are connections for the three gauge factors.

| Field | Representation as gauge boson | Number | Coupling | Field strength |
|---|---:|---:|---:|---:|
| $G_\mu^A$ | adjoint of $SU(3)_c$ | $8$ | $g_s$ | $G_{\mu\nu}^A$ |
| $W_\mu^I$ | adjoint of $SU(2)_L$ | $3$ | $g$ | $W_{\mu\nu}^I$ |
| $B_\mu$ | gauge field of $U(1)_Y$ | $1$ | $g'$ | $B_{\mu\nu}$ |

The local gauge-boson sector is

$$
\mathcal L_{\rm gauge}
=
-\frac14G_{\mu\nu}^AG^{A\mu\nu}
-\frac14W_{\mu\nu}^IW^{I\mu\nu}
-\frac14B_{\mu\nu}B^{\mu\nu}.
$$

After electroweak symmetry breaking, the electroweak gauge bosons reorganize as

$$
W_\mu^\pm=\frac{1}{\sqrt2}(W_\mu^1\mp iW_\mu^2),
$$

and

$$
A_\mu=s_WW_\mu^3+c_WB_\mu,
\qquad
Z_\mu=c_WW_\mu^3-s_WB_\mu.
$$

The eight gluons remain color gauge bosons. The photon remains massless. The $W^\pm$ and $Z$ become massive by eating the Higgs doublet's three Goldstone modes.

## One-generation fermion table

One generation of Standard Model fermions in conventional notation is

| Field | Components | Representation | Electric charges |
|---|---|---:|---:|
| $Q_L$ | $(u_L,d_L)^T$ | $(\mathbf3,\mathbf2)_{1/6}$ | $2/3,-1/3$ |
| $u_R$ | $u_R$ | $(\mathbf3,\mathbf1)_{2/3}$ | $2/3$ |
| $d_R$ | $d_R$ | $(\mathbf3,\mathbf1)_{-1/3}$ | $-1/3$ |
| $L_L$ | $(\nu_L,e_L)^T$ | $(\mathbf1,\mathbf2)_{-1/2}$ | $0,-1$ |
| $e_R$ | $e_R$ | $(\mathbf1,\mathbf1)_{-1}$ | $-1$ |

The Standard Model has three copies of this table:

$$
(Q_L^i,u_R^i,d_R^i,L_L^i,e_R^i),
\qquad i=1,2,3.
$$

The gauge interactions are generation-universal. Flavor enters through the Yukawa matrices, not through different gauge representations for $e,\mu,\tau$ or for the three quark generations.

The electric-charge check is immediate. For $Q_L\sim(\mathbf3,\mathbf2)_{1/6}$,

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

This is why hypercharge is not an afterthought. It is the ingredient that makes the weak doublets contain the observed electric charges.

## All-left-handed Weyl ledger

For anomaly calculations and many formal discussions, it is better to write every independent fermion as a left-handed Weyl field. The right-handed fields are replaced by their left-handed charge conjugates.

The one-generation all-left table is

| Left-handed Weyl field | Representation | $\mathsf y=6Y$ | Comment |
|---|---:|---:|---|
| $Q$ | $(\mathbf3,\mathbf2)_{1/6}$ | $1$ | left-handed quark doublet |
| $u^c$ | $(\bar{\mathbf3},\mathbf1)_{-2/3}$ | $-4$ | left-handed anti-up field |
| $d^c$ | $(\bar{\mathbf3},\mathbf1)_{1/3}$ | $2$ | left-handed anti-down field |
| $L$ | $(\mathbf1,\mathbf2)_{-1/2}$ | $-3$ | left-handed lepton doublet |
| $e^c$ | $(\mathbf1,\mathbf1)_{1}$ | $6$ | left-handed positron field |

Counting color and weak-isospin components,

$$
\dim Q+\dim u^c+\dim d^c+\dim L+\dim e^c
=6+3+3+2+1=15.
$$

Thus the minimal Standard Model has $15$ left-handed Weyl fermions per generation, or

$$
3\times15=45
$$

for three generations. Adding one sterile $\nu^c\sim(\mathbf1,\mathbf1)_0$ per generation gives $16$ Weyl fields per generation, which is natural in $SO(10)$ grand unification but is not part of the minimal renormalizable Standard Model.

## Higgs field and component charges

The Higgs doublet is

$$
H=
\begin{pmatrix}H^+\\ H^0\end{pmatrix}
\sim(\mathbf1,\mathbf2)_{1/2}.
$$

Its upper and lower components have $T^3=+1/2$ and $T^3=-1/2$, so

$$
Q(H^+)=\frac12+\frac12=1,
\qquad
Q(H^0)=-\frac12+\frac12=0.
$$

The neutral component can acquire a vacuum expectation value,

$$
\langle H\rangle
=
\frac1{\sqrt2}
\begin{pmatrix}0\\ v\end{pmatrix},
$$

without breaking electromagnetism. The four real scalar components of $H$ reorganize into one physical Higgs boson plus three Goldstone modes that become the longitudinal polarizations of $W^+$, $W^-$, and $Z$.

## Yukawa couplings allowed by the ledger

The renormalizable charged-fermion Yukawa couplings are

$$
\mathcal L_Y
=
-\bar Q_LY_dHd_R
-\bar Q_LY_u\tilde H u_R
-\bar L_LY_eHe_R
+\text{h.c.}
$$

Here $Y_u$, $Y_d$, and $Y_e$ are complex $3\times3$ matrices in generation space. Gauge invariance is a sharp filter. For example,

$$
Y(\bar Q_L)+Y(\tilde H)+Y(u_R)
=
-\frac16-\frac12+\frac23=0,
$$

and

$$
Y(\bar Q_L)+Y(H)+Y(d_R)=0,
\qquad
Y(\bar L_L)+Y(H)+Y(e_R)=0.
$$

The absence of a right-handed neutrino forbids a renormalizable neutrino Yukawa coupling in the minimal theory. If sterile fields $N_R$ are added, the gauge-invariant terms

$$
-\bar L_LY_\nu\tilde HN_R
-\frac12\overline{N_R^c}M_NN_R+\text{h.c.}
$$

are possible. Without light sterile fields, the leading neutrino-mass operator is the dimension-five Weinberg operator,

$$
\frac{c_{ij}}{\Lambda}(L_L^iH)(L_L^jH)+\text{h.c.}
$$

The detailed neutrino story belongs to [PMNS Matrix](/gauge-theories-standard-model/flavor-neutrinos/pmns-matrix/) and [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/).

## What is absent in the minimal theory

The minimal Standard Model does not contain every field we might want.

| Absent field or sector | Why it is absent from the minimal theory | Common extension |
|---|---|---|
| right-handed neutrino | gauge singlet not required by charged-fermion masses or gauge anomalies | Dirac neutrino masses, seesaw models |
| dark matter field | no Standard Model field has the right stability and abundance | hidden sectors, singlets, doublets, axions |
| axion | strong CP problem is not solved by the minimal field content | Peccei–Quinn symmetry and axion field |
| graviton | gravity is not part of the nongravitational Standard Model QFT | general relativity as EFT, quantum gravity |
| GUT gauge bosons | no grand-unified group is assumed | $SU(5)$, $SO(10)$, Pati–Salam |

Absence is part of the definition. The minimal Standard Model is the most economical renormalizable gauge theory matching known nongravitational particle interactions, not the final inventory of the universe.

## Compatibility with the global form

The field content is compatible with the global quotient

$$
G_{\rm SM}
=
\frac{SU(3)_c\times SU(2)_L\times U(1)_Y}{\mathbb Z_6}.
$$

With integral hypercharge $\mathsf y=6Y$, color triality $t$, and weak center parity $s$, the quotient condition is

$$
\mathsf y+2t+3s\equiv0\pmod6.
$$

Each minimal multiplet satisfies it. For example,

$$
Q_L:\quad \mathsf y+2t+3s=1+2+3=6,
$$

and

$$
L_L:\quad \mathsf y+2t+3s=-3+0+3=0.
$$

This is a compact way of saying that color, weak isospin, and hypercharge are not independent decorations. They fit together globally.

## Common pitfalls

**Calling the field table a particle table.** Before electroweak symmetry breaking, $B_\mu$ and $W_\mu^3$ are gauge fields. The photon and $Z$ are later linear combinations.

**Treating $u_R$ and $u^c$ as the same representation.** They describe related particle content, but they transform in conjugate representations. Use $u_R\sim(\mathbf3,\mathbf1)_{2/3}$ in particle notation and $u^c\sim(\bar{\mathbf3},\mathbf1)_{-2/3}$ in all-left Weyl notation.

**Forgetting color multiplicity.** $Q_L$ contains six Weyl components per generation: two weak components times three colors.

**Saying the Higgs is just one scalar.** The Higgs field before symmetry breaking is one complex weak doublet: four real scalar components. Only one remains as a physical scalar after three are eaten.

**Putting neutrino masses inside the minimal renormalizable field table.** Observed neutrino masses require an extension: higher-dimensional operators, sterile neutrino fields, or something more exotic.

**Equating generations with representations.** The three generations have the same Standard Model gauge representations. Flavor lives in Yukawa matrices, not in new gauge quantum numbers.

## Relations to other pages

- [Standard Model Gauge Group](/gauge-theories-standard-model/standard-model/standard-model-gauge-group/) defines the representation notation and hypercharge convention used here.
- [Global Form of the Standard Model Gauge Group](/gauge-theories-standard-model/standard-model/global-form-of-standard-model-gauge-group/) explains why this field table descends to the $\mathbb Z_6$ quotient.
- [Yukawa Couplings](/gauge-theories-standard-model/flavor-neutrinos/yukawa-couplings/) derives the allowed Yukawa operators from these representations.
- [Fermion Mass Matrices](/gauge-theories-standard-model/flavor-neutrinos/fermion-mass-matrices/) explains how the Yukawa matrices become masses and mixing matrices.
- [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/) explains the leading minimal-field-content operator for neutrino masses.
- [Standard Model Lagrangian](/gauge-theories-standard-model/standard-model/standard-model-lagrangian/) assembles the gauge, Higgs, fermion, Yukawa, theta, gauge-fixing, and ghost pieces.

## Research status

The minimal Standard Model field content is established by a huge web of experiments: color, weak charged currents, neutral currents, electromagnetic charges, Higgs couplings, quark mixing, lepton universality tests, and anomaly-free gauge consistency all point to the same representation ledger.

What remains open is why this ledger has the form it does. The minimal theory does not explain why there are exactly three generations, why the Yukawa matrices have their observed pattern, why neutrino masses are tiny, why the Higgs mass is stable against high-scale sensitivity, or what field content accounts for dark matter.

## Exercises

### Exercise 1: Count Weyl fields in one generation

Using the all-left-handed Weyl ledger, count the number of independent Weyl fields in one generation before adding a sterile neutrino.

<details>
<summary><strong>Solution</strong></summary>

The field $Q$ has $3\times2=6$ components. The fields $u^c$ and $d^c$ each have $3$ color components. The field $L$ has $2$ weak components, and $e^c$ has $1$ component. Therefore

$$
6+3+3+2+1=15.
$$

With three generations, this becomes $45$ left-handed Weyl fields.

</details>

### Exercise 2: Translate right-handed to all-left notation

The right-handed up quark has $u_R\sim(\mathbf3,\mathbf1)_{2/3}$. What are the quantum numbers of the left-handed conjugate field $u^c$?

<details>
<summary><strong>Solution</strong></summary>

Charge conjugation complex-conjugates the non-Abelian representation and reverses the abelian charge. Therefore

$$
u^c\sim(\bar{\mathbf3},\mathbf1)_{-2/3}.
$$

The important rule is: non-Abelian representations are conjugated, and $U(1)$ charges change sign.

</details>

### Exercise 3: Check the charged-lepton Yukawa hypercharge

Show that $\bar L_LHe_R$ is neutral under $U(1)_Y$.

<details>
<summary><strong>Solution</strong></summary>

The conjugate $\bar L_L$ has hypercharge $+1/2$. Therefore

$$
Y(\bar L_L)+Y(H)+Y(e_R)
=
\frac12+\frac12-1=0.
$$

The operator is also an $SU(2)_L$ singlet after contracting the two doublets.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the Standard Model gauge/Higgs, lepton, quark, and neutrino-mass sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the weak-interaction, anomaly, and Standard Model chapters.
- Burgess, *Introduction to Effective Field Theory*, especially the Standard Model as an effective theory.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the electroweak theory and Standard Model structure.
- Coleman, *Aspects of Symmetry*, especially the Higgs-mechanism lectures for the spontaneous-breaking logic behind the field ledger.

## Version history

- **2026-06-19:** Initial page listing the minimal Standard Model field content, generation structure, Higgs doublet, and all-left-handed Weyl notation.
