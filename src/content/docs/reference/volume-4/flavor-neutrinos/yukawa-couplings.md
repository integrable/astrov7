---
title: "Yukawa Couplings"
description: "Derives the gauge-invariant Standard Model Yukawa operators and explains how their generation-space matrices become fermion masses and Higgs couplings after electroweak symmetry breaking."
sidebar:
  label: "Yukawa Couplings"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–91; Schwartz Ch. 29; Burgess Ch. 9; Weinberg Vol. II electroweak chapters."
topics:
  - Yukawa couplings
  - Standard Model fermion masses
  - Higgs doublet
  - flavor matrices
  - electroweak symmetry breaking
canonicalTopics:
  - standard-model-yukawa-sector
  - higgs-fermion-couplings
  - flavor-spurions
  - charged-fermion-masses
researchStatus:
  established:
    - "Gauge invariance fixes the renormalizable Standard Model Yukawa operators to use H for down-type quarks and charged leptons and the conjugate doublet H̃ for up-type quarks."
  active:
    - "The values and hierarchies of the Yukawa matrices are empirical inputs in the minimal Standard Model and remain a central flavor problem."
---

## Summary

The Standard Model has no gauge-invariant bare mass term for its charged fermions before electroweak symmetry breaking. The left-chiral fields and right-chiral fields transform differently under $SU(2)_L\times U(1)_Y$, so terms such as $\bar e_Le_R$ and $\bar u_Lu_R$ are not electroweak singlets.

The Higgs doublet repairs this. With three generations, the renormalizable Yukawa Lagrangian is

$$
\mathcal L_Y
=
-\bar Q_LY_dHd_R
-\bar Q_LY_u\widetilde H u_R
-\bar L_LY_eHe_R
+\mathrm{h.c.},
$$

where

$$
H\sim(\mathbf1,\mathbf2)_{1/2},
\qquad
\widetilde H\equiv i\sigma^2H^*\sim(\mathbf1,\mathbf2)_{-1/2}.
$$

The matrices $Y_u,Y_d,Y_e$ act in generation space. After

$$
H\to\frac1{\sqrt2}\begin{pmatrix}0\\ v+h\end{pmatrix},
\qquad
\widetilde H\to\frac1{\sqrt2}\begin{pmatrix}v+h\\0\end{pmatrix},
$$

they become mass matrices and aligned Higgs couplings:

$$
M_u=\frac{v}{\sqrt2}Y_u,
\qquad
M_d=\frac{v}{\sqrt2}Y_d,
\qquad
M_e=\frac{v}{\sqrt2}Y_e.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![Yukawa operators become masses and Higgs couplings](/figures/gauge-theories-standard-model/yukawa-operator-to-mass-map.svg)

<figcaption>

Gauge invariance filters the allowed renormalizable fermion bilinears. The Higgs doublet $H$ supplies the weak and hypercharge quantum numbers needed for down-type quarks and charged leptons, while $\widetilde H=i\sigma^2H^*$ supplies the conjugate quantum numbers needed for up-type quarks. The same matrices that generate masses also generate tree-level Higgs–fermion couplings.

</figcaption>
</figure>

The Yukawa sector is therefore both elegant and suspicious. It is elegant because gauge invariance fixes the operator architecture. It is suspicious because the entries of the three complex matrices are not explained by the minimal Standard Model.

## Prerequisites

You should know [Standard Model Fermion Representations](/gauge-theories-standard-model/flavor-neutrinos/standard-model-fermion-representations/) and [Chirality and Gauge Interactions](/gauge-theories-standard-model/flavor-neutrinos/chirality-and-gauge-interactions/). You should also know the Higgs-doublet convention from [Standard Model Higgs Doublet](/gauge-theories-standard-model/higgs-sector/standard-model-higgs-doublet/) and the vacuum expansion from [Higgs Potential](/gauge-theories-standard-model/higgs-sector/higgs-potential/).

We use

$$
Q=T^3+Y,
\qquad
H=\begin{pmatrix}H^+\\H^0\end{pmatrix}\sim(\mathbf1,\mathbf2)_{1/2},
\qquad
\widetilde H=i\sigma^2H^*.
$$

Generation indices are usually suppressed. When they are shown, $i,j=1,2,3$ label generations, $a=1,2$ labels weak components, and $\alpha=1,2,3$ labels color.

## Core idea

A Yukawa coupling is a scalar–fermion–fermion interaction. In the Standard Model it has a sharper meaning: it is the only renormalizable, gauge-invariant way to connect a left-chiral weak doublet to a right-chiral weak singlet.

For a generic Dirac fermion in a vectorlike theory, one might write a mass term directly:

$$
\mathcal L_m=-m\bar\psi\psi
=-m(\bar\psi_L\psi_R+\bar\psi_R\psi_L).
$$

In the electroweak theory this is not allowed for charged fermions. For example,

$$
L_L\sim(\mathbf1,\mathbf2)_{-1/2},
\qquad
e_R\sim(\mathbf1,\mathbf1)_{-1}.
$$

The bilinear $\bar L_Le_R$ is still a weak doublet and has hypercharge

$$
Y(\bar L_Le_R)=+\frac12-1=-\frac12.
$$

It is not a singlet. Multiplying by the Higgs doublet gives

$$
Y(\bar L_LHe_R)=+\frac12+\frac12-1=0,
$$

and the weak indices can be contracted. The operator $\bar L_LHe_R$ is gauge invariant. When $H$ develops a neutral vacuum expectation value, it becomes the charged-lepton mass term.

This is the Higgs mechanism in the fermion sector: **fermion masses are not inserted directly; they arise from gauge-invariant Yukawa operators evaluated in the Higgs vacuum.**

## Setup and conventions

The left-chiral doublets are

$$
Q_L^i=\begin{pmatrix}u_L^i\\d_L^i\end{pmatrix}\sim(\mathbf3,\mathbf2)_{1/6},
\qquad
L_L^i=\begin{pmatrix}\nu_L^i\\e_L^i\end{pmatrix}\sim(\mathbf1,\mathbf2)_{-1/2}.
$$

The right-chiral charged singlets are

$$
u_R^i\sim(\mathbf3,\mathbf1)_{2/3},
\qquad
d_R^i\sim(\mathbf3,\mathbf1)_{-1/3},
\qquad
e_R^i\sim(\mathbf1,\mathbf1)_{-1}.
$$

The minimal renormalizable Standard Model has no right-handed neutrino field. Therefore this page only constructs charged-fermion Yukawa couplings. Neutrino masses are treated later, where either a dimension-five operator or additional fields must be introduced.

The Higgs doublet and its conjugate are

$$
H=\begin{pmatrix}H^+\\H^0\end{pmatrix}\sim(\mathbf1,\mathbf2)_{1/2},
\qquad
\widetilde H=i\sigma^2H^*=\begin{pmatrix}H^{0*}\\-H^-\end{pmatrix}\sim(\mathbf1,\mathbf2)_{-1/2}.
$$

The definition of $\widetilde H$ is not decorative. It is forced by hypercharge. Up-type quarks need a doublet with $Y=-1/2$, while down-type quarks and charged leptons need a doublet with $Y=+1/2$.

## Gauge-invariant operators

With generation indices exposed, the charged-fermion Yukawa terms are

$$
\mathcal L_Y=
-\bar Q_{Li}^{\alpha a}(Y_d)_{ij}H_a d_{Rj}^{\alpha}
-\bar Q_{Li}^{\alpha a}(Y_u)_{ij}\widetilde H_a u_{Rj}^{\alpha}
-\bar L_{Li}^{a}(Y_e)_{ij}H_a e_{Rj}
+\mathrm{h.c.}
$$

The color index $\alpha$ is contracted between $\bar Q_L$ and the right-handed quark singlet. The weak index $a$ is contracted between the anti-doublet $\bar Q_L$ or $\bar L_L$ and the Higgs doublet. The generation labels are tied together by arbitrary complex $3\times3$ matrices $Y_f$.

Each term is neutral under hypercharge:

| Operator | Hypercharge sum | Result |
|---|---:|---:|
| $\bar Q_LH d_R$ | $-1/6+1/2-1/3$ | $0$ |
| $\bar Q_L\widetilde H u_R$ | $-1/6-1/2+2/3$ | $0$ |
| $\bar L_LH e_R$ | $+1/2+1/2-1$ | $0$ |

This table is the quickest way to remember why $\widetilde H$ appears in the up-type Yukawa coupling. If one used $H$ instead, the hypercharge sum would be $-1/6+1/2+2/3=1$, not zero.

## Component form

Writing

$$
Q_L=\begin{pmatrix}u_L\\d_L\end{pmatrix},
\qquad
L_L=\begin{pmatrix}\nu_L\\e_L\end{pmatrix},
\qquad
H=\begin{pmatrix}H^+\\H^0\end{pmatrix},
\qquad
\widetilde H=\begin{pmatrix}H^{0*}\\-H^-\end{pmatrix},
$$

the Yukawa terms contain

$$
-\bar Q_LY_dHd_R
=
-\bar u_LY_dH^+d_R
-\bar d_LY_dH^0d_R,
$$

$$
-\bar Q_LY_u\widetilde H u_R
=
-\bar u_LY_uH^{0*}u_R
+\bar d_LY_uH^-u_R,
$$

and

$$
-\bar L_LY_eHe_R
=
-\bar\nu_LY_eH^+e_R
-\bar e_LY_eH^0e_R.
$$

This component form makes the charged scalar couplings visible. In unitary gauge the charged and neutral Goldstone fields are hidden, but in covariant gauges they are useful and their Yukawa couplings are fixed by the same matrices that fix the masses.

## After electroweak symmetry breaking

In unitary gauge,

$$
H=\frac1{\sqrt2}\begin{pmatrix}0\\v+h\end{pmatrix},
\qquad
\widetilde H=\frac1{\sqrt2}\begin{pmatrix}v+h\\0\end{pmatrix}.
$$

Substituting into $\mathcal L_Y$ gives

$$
\mathcal L_Y
=
-\bar u_L\left(\frac{v+h}{\sqrt2}Y_u\right)u_R
-\bar d_L\left(\frac{v+h}{\sqrt2}Y_d\right)d_R
-\bar e_L\left(\frac{v+h}{\sqrt2}Y_e\right)e_R
+\mathrm{h.c.}
$$

Thus

$$
M_f=\frac{v}{\sqrt2}Y_f,
\qquad
f=u,d,e.
$$

The same substitution also gives the Higgs interaction

$$
\mathcal L_{hff}
=
-\frac{h}{v}
\left(
\bar u_LM_uu_R+\bar d_LM_dd_R+\bar e_LM_ee_R
\right)
+\mathrm{h.c.}
$$

Before diagonalization this is a matrix equation in flavor space. After diagonalization, it becomes

$$
\mathcal L_{hff}=-\sum_f\frac{m_f}{v}h\bar f f,
$$

for the physical charged fermions. This is why the Standard Model tree-level Higgs coupling to a charged fermion is proportional to its mass.

## Flavor as matrices

The Yukawa matrices are dimensionless complex matrices. Gauge symmetry tells us that the three matrices may appear; it does not tell us their entries. If the Yukawas were absent, the fermion kinetic terms would have a large flavor-basis freedom, schematically

$$
U(3)_Q\times U(3)_u\times U(3)_d\times U(3)_L\times U(3)_e.
$$

The Yukawa matrices break this freedom. A clean way to track the breaking is to treat them as spurions: assign transformation laws

$$
Y_u\to V_QY_uV_u^\dagger,
\qquad
Y_d\to V_QY_dV_d^\dagger,
\qquad
Y_e\to V_LY_eV_e^\dagger,
$$

while the fermions transform as $Q_L\to V_QQ_L$, $u_R\to V_uu_R$, and so on. The Lagrangian is then formally invariant. Physical flavor observables are built from combinations that survive these allowed basis changes.

This spurion viewpoint is not just notation. It is the seed of minimal flavor violation, EFT flavor counting, and many model-building attempts to explain the observed hierarchy of masses and mixings.

## What happens to neutrinos

The minimal renormalizable Standard Model does not include a right-handed neutrino. Therefore there is no term

$$
-\bar L_LY_\nu\widetilde H\nu_R+\mathrm{h.c.}
$$

inside the minimal theory. If one adds gauge-singlet fields $\nu_R$, then this Dirac Yukawa term becomes allowed. Without adding new fields, the lowest-dimension Standard-Model operator that gives neutrino masses is the dimension-five Weinberg operator, discussed later in this chapter. This is the first major place where observed neutrino oscillations point beyond the minimal renormalizable Standard Model.

## Common pitfalls

**Using H instead of H̃ for up-type quarks.** The hypercharge sum fails. The conjugate Higgs doublet is not optional notation; it is the only renormalizable Standard Model doublet with the right electroweak quantum numbers for $u_R$.

**Thinking Yukawa couplings are masses before symmetry breaking.** The matrices $Y_f$ are dimensionless couplings in the unbroken theory. The mass matrices are $M_f=vY_f/\sqrt2$ after the Higgs vacuum is chosen.

**Forgetting that Yukawas are matrices.** With three generations, $Y_u,Y_d,Y_e$ are not three numbers. Their diagonalization and misalignment produce the physical flavor structure.

**Assuming the Higgs coupling is independently chosen.** In the renormalizable Standard Model with one Higgs doublet, the tree-level Higgs–fermion coupling is aligned with the mass matrix. This alignment is why there are no tree-level Higgs-mediated flavor-changing neutral currents in the minimal Standard Model.

## Relations to other pages

This page uses the chiral representation data from [Standard Model Fermion Representations](/gauge-theories-standard-model/flavor-neutrinos/standard-model-fermion-representations/) and [Chirality and Gauge Interactions](/gauge-theories-standard-model/flavor-neutrinos/chirality-and-gauge-interactions/). The next page, [Fermion Mass Matrices](/gauge-theories-standard-model/flavor-neutrinos/fermion-mass-matrices/), explains how the matrices $M_f$ are diagonalized and why their left-handed rotations matter for weak charged currents.

Later pages on the [CKM Matrix](/gauge-theories-standard-model/flavor-neutrinos/ckm-matrix/), [CP Violation](/gauge-theories-standard-model/flavor-neutrinos/cp-violation/), [PMNS Matrix](/gauge-theories-standard-model/flavor-neutrinos/pmns-matrix/), and [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/) build on the same Yukawa architecture.

## Research status

The existence and gauge structure of the Standard Model Yukawa operators are established. Their numerical pattern is not explained by the minimal theory. The observed charged-fermion masses span many orders of magnitude, and the CKM angles show a hierarchical structure. Whether these patterns come from flavor symmetries, geometry, compositeness, extra dimensions, radiative generation, environmental selection, or something less polite remains open.

In EFT language, the Yukawa matrices are spurions controlling flavor symmetry breaking. That viewpoint is settled and extremely useful, but it is not an explanation of the spurion values.

## Exercises

### Exercise 1: Check the three hypercharge sums

Using $Y(\bar\psi)=-Y(\psi)$, verify that $\bar Q_LHd_R$, $\bar Q_L\widetilde H u_R$, and $\bar L_LHe_R$ are neutral under $U(1)_Y$.

<details><summary><strong>Solution</strong></summary>

The hypercharges are $Y(Q_L)=1/6$, $Y(u_R)=2/3$, $Y(d_R)=-1/3$, $Y(L_L)=-1/2$, $Y(e_R)=-1$, $Y(H)=1/2$, and $Y(\widetilde H)=-1/2$. Therefore

$$
Y(\bar Q_LHd_R)=-\frac16+\frac12-\frac13=0,
$$

$$
Y(\bar Q_L\widetilde H u_R)=-\frac16-\frac12+\frac23=0,
$$

and

$$
Y(\bar L_LHe_R)=+\frac12+\frac12-1=0.
$$

</details>

### Exercise 2: Derive the mass matrix from the Higgs vacuum

Insert $H=(0,(v+h)/\sqrt2)^T$ into $-\bar L_LY_eHe_R+\mathrm{h.c.}$ and identify $M_e$.

<details><summary><strong>Solution</strong></summary>

Since $L_L=(\nu_L,e_L)^T$,

$$
-\bar L_LY_eHe_R
=
-\bar e_LY_e\frac{v+h}{\sqrt2}e_R.
$$

The mass part is

$$
-\bar e_L\left(\frac{v}{\sqrt2}Y_e\right)e_R+\mathrm{h.c.},
$$

so

$$
M_e=\frac{v}{\sqrt2}Y_e.
$$

The remaining term is the aligned Higgs coupling $-h\bar e_LM_ee_R/v+\mathrm{h.c.}$.

</details>

### Exercise 3: Show the spurion transformation law

Let $Q_L\to V_QQ_L$ and $u_R\to V_uu_R$. Find the transformation of $Y_u$ that keeps $\bar Q_LY_u\widetilde H u_R$ formally invariant.

<details><summary><strong>Solution</strong></summary>

The transformed term is

$$
\bar Q_LV_Q^\dagger Y_u^\prime\widetilde H V_uu_R.
$$

For this to equal $\bar Q_LY_u\widetilde H u_R$ for arbitrary fields, we need

$$
V_Q^\dagger Y_u^\prime V_u=Y_u,
$$

or

$$
Y_u^\prime=V_QY_uV_u^\dagger.
$$

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§87–91 for the Standard Model gauge, lepton, quark, and neutrino sectors.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 29 for weak interactions and the fermion sector, and Ch. 30 for anomaly context.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for the Higgs phenomenon as the organizing idea behind electroweak mass generation.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the electroweak theory and flavor structure in a systematic field-theoretic treatment.
- Burgess, *Introduction to Effective Field Theory*, Ch. 9, for the Standard Model as an effective theory and the role of higher-dimensional flavor and neutrino operators.
- Georgi, *Weak Interactions and Modern Particle Theory*, for a compact, symmetry-first path through weak interactions and Yukawa couplings.

## Version history

- **2026-06-19:** Initial page. Added the gauge-invariant Yukawa operators, hypercharge checks, component expansion, Higgs-vacuum mass relation, flavor-spurion viewpoint, exercises, and Yukawa-operator map figure.
