---
title: "Standard Model Fermion Representations"
description: "Lists and explains the chiral quark and lepton representation data of one Standard Model generation, including hypercharges, electric charges, all-left-handed notation, and basic consistency checks."
sidebar:
  label: "SM Fermion Representations"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–91; Schwartz Chs. 29–30; Burgess Ch. 9; Weinberg Vol. II electroweak chapters."
topics:
  - Standard Model fermions
  - chiral representations
  - hypercharge
  - weak isospin
  - anomaly cancellation preview
canonicalTopics:
  - standard-model-fermion-representations
  - chiral-gauge-theory
  - hypercharge-assignments
  - all-left-handed-weyl-notation
researchStatus:
  established:
    - "The minimal Standard Model fermion content consists of three copies of a chiral one-generation pattern transforming under SU(3)c × SU(2)L × U(1)Y."
  active:
    - "The observed repetition of three generations and the hierarchy of Yukawa matrices are empirical inputs, not consequences of the minimal Standard Model gauge group."
---

## Summary

The Standard Model fermions are not arranged as parity-symmetric pairs before electroweak symmetry breaking. For one generation, the chiral representation data are

| Field | Representation under $SU(3)_c\times SU(2)_L\times U(1)_Y$ | Electric charges |
|---|---:|---:|
| $Q_L=(u_L,d_L)^T$ | $(\mathbf3,\mathbf2)_{1/6}$ | $2/3,-1/3$ |
| $u_R$ | $(\mathbf3,\mathbf1)_{2/3}$ | $2/3$ |
| $d_R$ | $(\mathbf3,\mathbf1)_{-1/3}$ | $-1/3$ |
| $L_L=(\nu_L,e_L)^T$ | $(\mathbf1,\mathbf2)_{-1/2}$ | $0,-1$ |
| $e_R$ | $(\mathbf1,\mathbf1)_{-1}$ | $-1$ |

There are three copies of this pattern, usually labeled by a generation index $i=1,2,3$. The gauge interactions are generation universal; the Yukawa matrices are not. That is where flavor enters.

The convention in this volume is

$$
Q=T^3+Y.
$$

Thus a weak doublet with hypercharge $Y$ has component charges $Y+1/2$ and $Y-1/2$, while a weak singlet has $Q=Y$. The hypercharges above are exactly the values that reproduce the observed electric charges and make the Higgs Yukawa couplings gauge invariant.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Standard Model fermion representation ledger](/figures/gauge-theories-standard-model/sm-fermion-representation-ledger.svg)

<figcaption>

The same one-generation fermion content can be written in a four-component chirality ledger or in an all-left-handed Weyl ledger. The all-left-handed form is often cleaner for anomalies, because right-handed fields are replaced by charge-conjugate left-handed fields in conjugate representations.

</figcaption>
</figure>

This table is not just a particle list. It is the input data for electroweak currents, Yukawa couplings, anomaly cancellation, CKM mixing, PMNS mixing after neutrino masses, and the full Standard Model Lagrangian.

## Prerequisites

You should know the electroweak convention from [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/), especially

$$
D_\mu=\partial_\mu+igW_\mu^aT^a+ig'YB_\mu,
\qquad
Q=T^3+Y.
$$

You should also know [Electroweak Covariant Derivative](/gauge-theories-standard-model/electroweak/electroweak-covariant-derivative/) and [Color SU(3)](/gauge-theories-standard-model/qcd/color-su3/). This page uses the representation notation introduced in [Matter Representations](/gauge-theories-standard-model/gauge-principle/matter-representations/).

## Core idea

The Standard Model is a chiral gauge theory. Its elementary fermions are Weyl fields whose left-chiral and right-chiral components do not transform in the same way under $SU(2)_L\times U(1)_Y$.

For quarks, the left-chiral fields sit in weak doublets,

$$
Q_L^i=
\begin{pmatrix}u_L^i\\ d_L^i\end{pmatrix}.
$$

For leptons,

$$
L_L^i=
\begin{pmatrix}\nu_L^i\\ e_L^i\end{pmatrix}.
$$

The right-chiral charged fields $u_R^i,d_R^i,e_R^i$ are weak singlets. In the minimal renormalizable Standard Model there is no right-handed neutrino field $\nu_R^i$.

That asymmetry is the seed of almost everything that feels distinctive about the Standard Model: parity violation in weak interactions, the absence of gauge-invariant bare fermion masses, the need for the Higgs doublet in Yukawa couplings, anomaly constraints on hypercharges, and the nontrivial flavor structure that appears after diagonalizing Yukawa matrices.

## Setup and conventions

The local gauge algebra is

$$
\mathfrak{su}(3)_c\oplus\mathfrak{su}(2)_L\oplus\mathfrak{u}(1)_Y.
$$

For most local calculations we write the corresponding group as

$$
SU(3)_c\times SU(2)_L\times U(1)_Y.
$$

The global form of the Standard Model gauge group is a subtler question and is treated later in the Standard Model Architecture chapter. On this page, the representation label

$$
(R_c,R_L)_Y
$$

means:

- $R_c$ is the color representation;
- $R_L$ is the weak-isospin representation;
- $Y$ is the hypercharge in the convention $Q=T^3+Y$.

The color triplet representation is denoted $\mathbf3$, its conjugate by $\bar{\mathbf3}$, the weak doublet by $\mathbf2$, and a singlet by $\mathbf1$.

For a weak doublet

$$
\Psi=\begin{pmatrix}\psi_+\\ \psi_-\end{pmatrix},
\qquad
T^3=\frac12
\begin{pmatrix}
1&0\\
0&-1
\end{pmatrix},
$$

the component charges are

$$
Q(\psi_+)=Y+\frac12,
\qquad
Q(\psi_-)=Y-\frac12.
$$

For a weak singlet, $T^3=0$, so $Q=Y$.

:::note[Hypercharge convention]
Some books write $Q=T^3+Y_{\rm old}/2$. Their listed hypercharges are twice the hypercharges used here:

$$
Y_{\rm old}=2Y.
$$

Do not mix the two ledgers. Hypercharge mistakes are the Standard Model’s favorite little banana peel.
:::

## One-generation representation table

For one generation, the minimal Standard Model fermion content is

| Field | Meaning | $SU(3)_c$ | $SU(2)_L$ | $Y$ | Charges |
|---|---|---:|---:|---:|---:|
| $Q_L=(u_L,d_L)^T$ | left-chiral quark doublet | $\mathbf3$ | $\mathbf2$ | $1/6$ | $2/3,-1/3$ |
| $u_R$ | right-chiral up-type quark | $\mathbf3$ | $\mathbf1$ | $2/3$ | $2/3$ |
| $d_R$ | right-chiral down-type quark | $\mathbf3$ | $\mathbf1$ | $-1/3$ | $-1/3$ |
| $L_L=(\nu_L,e_L)^T$ | left-chiral lepton doublet | $\mathbf1$ | $\mathbf2$ | $-1/2$ | $0,-1$ |
| $e_R$ | right-chiral charged lepton | $\mathbf1$ | $\mathbf1$ | $-1$ | $-1$ |

The Higgs doublet is not a fermion, but it belongs beside this table because it is the field that makes the Yukawa couplings possible:

$$
H=\begin{pmatrix}H^+\\ H^0\end{pmatrix}
\sim (\mathbf1,\mathbf2)_{1/2}.
$$

Its conjugate doublet is

$$
\tilde H=i\sigma^2H^*
\sim (\mathbf1,\mathbf2)_{-1/2}.
$$

The component charges follow from the same rule:

$$
Q(H^+)=\frac12+\frac12=1,
\qquad
Q(H^0)=-\frac12+\frac12=0.
$$

The neutral component can therefore acquire a vacuum expectation value without breaking electromagnetism.

## Why these hypercharges

The doublet hypercharges are fixed by the average electric charge inside each doublet. For quarks,

$$
Y(Q_L)=\frac12\left(\frac23-\frac13\right)=\frac16,
$$

and for leptons,

$$
Y(L_L)=\frac12(0-1)=-\frac12.
$$

For weak singlets, $T^3=0$, so hypercharge equals electric charge:

$$
Y(u_R)=\frac23,
\qquad
Y(d_R)=-\frac13,
\qquad
Y(e_R)=-1.
$$

This derivation uses the observed electric charges as input. A deeper structural check comes from gauge invariance of the Yukawa couplings and cancellation of gauge anomalies. Those checks are not independent miracles; they are part of the same tight representation puzzle.

## Three generations

The Standard Model contains three copies of the one-generation pattern. The full minimal fermion list is

$$
Q_L^i,
\quad u_R^i,
\quad d_R^i,
\quad L_L^i,
\quad e_R^i,
\qquad i=1,2,3.
$$

The left-handed neutrino $\nu_L^i$ is not a separate gauge multiplet; it is the upper component of $L_L^i$. A right-handed neutrino $\nu_R^i$ is not included in the minimal renormalizable Standard Model.

Gauge interactions do not distinguish the generation label $i$. In the absence of Yukawa couplings, the kinetic terms have a large flavor-basis freedom: independent unitary rotations may be made on the five species $Q_L,u_R,d_R,L_L,e_R$. The Yukawa matrices break this freedom and leave behind physical masses, mixing angles, and CP phases.

This is why generation is not the same thing as gauge representation. Generation labels are copied representation data. Flavor physics begins when the copies are coupled by matrices.

## All-left-handed Weyl notation

Anomaly calculations, supersymmetric model building, and many modern QFT discussions use only left-handed Weyl fields. In that notation, the left-handed doublets remain as they are, while right-handed charged fields are replaced by their charge-conjugate left-handed fields. The useful one-generation all-left-handed list is

| Left-handed Weyl field | Four-component name it replaces | Representation |
|---|---|---:|
| $Q$ | $Q_L$ | $(\mathbf3,\mathbf2)_{1/6}$ |
| $u^c$ | charge conjugate of $u_R$ | $(\bar{\mathbf3},\mathbf1)_{-2/3}$ |
| $d^c$ | charge conjugate of $d_R$ | $(\bar{\mathbf3},\mathbf1)_{1/3}$ |
| $L$ | $L_L$ | $(\mathbf1,\mathbf2)_{-1/2}$ |
| $e^c$ | charge conjugate of $e_R$ | $(\mathbf1,\mathbf1)_1$ |

The superscript $c$ is part of the field name here. It reminds you that the field has conjugate gauge quantum numbers. For example,

$$
Y(u_R)=\frac23,
\qquad
Y(u^c)=-\frac23.
$$

The same physical content is being described in two ledgers. The four-component chirality ledger is convenient for phenomenology after masses are generated. The all-left-handed Weyl ledger is convenient for anomalies and gauge-invariant operator counting.

## Gauge-invariant Yukawa check

The renormalizable Standard Model Yukawa terms are

$$
\mathcal L_Y
=
-\bar Q_LY_dHd_R
-\bar Q_LY_u\tilde H u_R
-\bar L_LY_eHe_R
+\text{h.c.},
$$

where generation indices are suppressed. Each term is a gauge singlet.

Hypercharge neutrality is a quick check. Since $\bar Q_L$ has hypercharge $-1/6$,

$$
Y(\bar Q_L)+Y(H)+Y(d_R)
= -\frac16+\frac12-\frac13=0.
$$

Similarly,

$$
Y(\bar Q_L)+Y(\tilde H)+Y(u_R)
= -\frac16-\frac12+\frac23=0,
$$

and

$$
Y(\bar L_L)+Y(H)+Y(e_R)
= \frac12+\frac12-1=0.
$$

The $SU(2)_L$ contractions use the doublet structure. The down-type and charged-lepton terms use $H$, while the up-type term uses $\tilde H$. This is why the conjugate Higgs doublet is not a random trick: it is forced by hypercharge.

## Why bare fermion masses are absent

A Dirac mass term pairs a left-chiral and right-chiral fermion:

$$
-m\bar\psi\psi=-m(\bar\psi_L\psi_R+\bar\psi_R\psi_L).
$$

Before electroweak symmetry breaking, the Standard Model left- and right-chiral fermions do not generally have the same electroweak representation. For the electron, $e_L$ lives inside

$$
L_L\sim(\mathbf1,\mathbf2)_{-1/2},
$$

while

$$
e_R\sim(\mathbf1,\mathbf1)_{-1}.
$$

The expression $\bar e_Le_R$ alone is not an electroweak gauge singlet. It becomes allowed only as part of

$$
\bar L_LHe_R.
$$

The same logic holds for quarks. The Higgs field supplies the missing weak-isospin and hypercharge quantum numbers. After

$$
H\to\frac{1}{\sqrt2}\begin{pmatrix}0\\ v+h\end{pmatrix},
$$

the Yukawa terms become mass terms plus Higgs couplings.

This is the sharpest practical meaning of “chiral Standard Model”: gauge symmetry forbids elementary fermion masses until the Higgs field participates.

## Anomaly checks in one generation

The representation table is also tuned so that gauge anomalies cancel. The full anomaly story belongs in the consistency chapter, but the one-generation arithmetic is short enough to record here.

Use the all-left-handed fields

$$
Q,
\quad u^c,
\quad d^c,
\quad L,
\quad e^c.
$$

The $SU(2)_L^2U(1)_Y$ anomaly is proportional to the sum of hypercharges over weak doublets, with color multiplicity included:

$$
3\left(\frac16\right)+1\left(-\frac12\right)=0.
$$

The $SU(3)_c^2U(1)_Y$ anomaly is proportional to

$$
2\left(\frac16\right)-\frac23+\frac13=0,
$$

where the factor $2$ comes from the two weak components of $Q$.

The mixed gravitational-$U(1)_Y$ anomaly is proportional to the sum of hypercharges over all left-handed Weyl components:

$$
6\left(\frac16\right)
+3\left(-\frac23\right)
+3\left(\frac13\right)
+2\left(-\frac12\right)
+1(1)=0.
$$

The cubic Abelian anomaly also cancels:

$$
6\left(\frac16\right)^3
+3\left(-\frac23\right)^3
+3\left(\frac13\right)^3
+2\left(-\frac12\right)^3
+1^3=0.
$$

Finally, each generation contains four left-handed $SU(2)_L$ doublets: three colored quark doublets plus one lepton doublet. The number is even, so the global $SU(2)$ anomaly is absent generation by generation.

The cancellations are not optional. A chiral gauge theory with uncanceled gauge anomalies is not a consistent quantum gauge theory.

## Neutrinos in the minimal representation table

The left-handed neutrino $\nu_L$ is present because it is the upper component of $L_L$. A right-handed neutrino $\nu_R$ is not part of the minimal renormalizable Standard Model field content.

That single absence has a large consequence: there is no renormalizable Dirac neutrino Yukawa term

$$
\bar L_L\tilde H\nu_R
$$

unless $\nu_R$ is added. There is also no gauge-invariant dimension-three Majorana mass term for $\nu_L$ alone. The leading Standard-Model-only neutrino mass operator is instead the dimension-five Weinberg operator, discussed later in this chapter.

## Common pitfalls

**Using two hypercharge conventions at once.** If a source writes $Q=T^3+Y/2$, divide its listed hypercharges by two before using formulas on this site.

**Forgetting that $u^c$ is not $u_R$.** The field $u^c$ is a left-handed Weyl field with conjugate gauge quantum numbers. It is the left-handed charge conjugate of the right-handed up quark.

**Counting generations as gauge indices.** Gauge bosons do not carry generation labels. Generation space is where Yukawa matrices live.

**Putting $\nu_R$ into the minimal table.** A right-handed neutrino is a perfectly reasonable extension, but it is not part of the minimal renormalizable Standard Model.

**Trying to write bare fermion masses before the Higgs vacuum.** Electroweak gauge invariance forbids those mass terms. Yukawa couplings plus the Higgs vacuum generate them.

**Dropping multiplicities in anomaly sums.** Color and weak-isospin multiplicities matter. The sums cancel only when every Weyl component is counted.

## Relations to other pages

This page supplies the representation data used in [Chirality and Gauge Interactions](/gauge-theories-standard-model/flavor-neutrinos/chirality-and-gauge-interactions/). The pages on Yukawa Couplings and Fermion Mass Matrices then explain how these chiral fields acquire masses after electroweak symmetry breaking.

The Electroweak Theory chapter develops the gauge interactions associated with these fields. The Standard Model Architecture chapter later assembles the complete field content and Lagrangian. The consistency chapter proves anomaly cancellation in a more systematic way.

## Research status

The representation table is established physics. It is fixed by the observed Standard Model fermions and by decades of precision tests of electromagnetic, weak, and strong interactions.

What remains unexplained inside the minimal Standard Model is why this table appears in three copies, why the Yukawa matrices have their observed hierarchical structure, why CP violation has its observed size, and how neutrino masses arise. Those are not mistakes in the representation table; they are its most interesting unanswered questions.

## Exercises

### Exercise 1: Recover the doublet hypercharges

Use $Q=T^3+Y$ to derive $Y(Q_L)=1/6$ and $Y(L_L)=-1/2$ from the component electric charges.

<details><summary><strong>Solution</strong></summary>

For a doublet, the upper and lower charges are $Y+1/2$ and $Y-1/2$. For $Q_L=(u_L,d_L)^T$,

$$
Y+\frac12=\frac23,
\qquad
Y-\frac12=-\frac13,
$$

so $Y=1/6$. For $L_L=(\nu_L,e_L)^T$,

$$
Y+\frac12=0,
\qquad
Y-\frac12=-1,
$$

so $Y=-1/2$.

</details>

### Exercise 2: Convert to all-left-handed notation

Starting from $u_R\sim(\mathbf3,\mathbf1)_{2/3}$ and $d_R\sim(\mathbf3,\mathbf1)_{-1/3}$, find the representations of $u^c$ and $d^c$.

<details><summary><strong>Solution</strong></summary>

Charge conjugation reverses the Abelian charge and conjugates the non-Abelian representation. Therefore

$$
 u^c\sim(\bar{\mathbf3},\mathbf1)_{-2/3},
\qquad
 d^c\sim(\bar{\mathbf3},\mathbf1)_{1/3}.
$$

The weak representation remains a singlet because the conjugate of an $SU(2)$ singlet is still a singlet.

</details>

### Exercise 3: Check a Yukawa hypercharge sum

Show that $\bar Q_L\tilde H u_R$ is hypercharge neutral.

<details><summary><strong>Solution</strong></summary>

The hypercharges are

$$
Y(\bar Q_L)=-\frac16,
\qquad
Y(\tilde H)=-\frac12,
\qquad
Y(u_R)=\frac23.
$$

Thus

$$
-\frac16-\frac12+\frac23
= -\frac16-\frac36+\frac46
=0.
$$

So the operator is neutral under $U(1)_Y$. It is also an $SU(2)_L$ singlet because $\bar Q_L$ and $\tilde H$ are contracted as doublets, and it is a color singlet because $\bar Q_L$ and $u_R$ are in conjugate color representations.

</details>

### Exercise 4: Check the cubic hypercharge anomaly

Verify that

$$
6\left(\frac16\right)^3
+3\left(-\frac23\right)^3
+3\left(\frac13\right)^3
+2\left(-\frac12\right)^3
+1^3=0.
$$

<details><summary><strong>Solution</strong></summary>

Compute each term:

$$
6\left(\frac16\right)^3=\frac1{36},
\qquad
3\left(-\frac23\right)^3=-\frac89,
\qquad
3\left(\frac13\right)^3=\frac19,
$$

and

$$
2\left(-\frac12\right)^3=-\frac14,
\qquad
1^3=1.
$$

With denominator $36$,

$$
\frac1{36}-\frac{32}{36}+\frac4{36}-\frac9{36}+\frac{36}{36}=0.
$$

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§87–91, for the Standard Model gauge/Higgs, lepton, quark, and neutrino-mass sectors.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 29–30, for weak interactions, the fermion sector, and anomaly cancellation.
- Burgess, *Introduction to Effective Field Theory*, Ch. 9, for the Standard Model as an effective theory and the role of higher-dimensional operators.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for a systematic treatment of electroweak theory and fermion mixing.
- Georgi, *Lie Algebras in Particle Physics*, for representation-theory bookkeeping in particle physics.
- Slansky, “Group Theory for Unified Model Building,” for a broad reference on group representations used in model building.

## Version history

- **2026-06-18:** Initial page. Added the one-generation representation table, all-left-handed Weyl ledger, Yukawa checks, anomaly-preview arithmetic, exercises, and representation-ledger figure.
