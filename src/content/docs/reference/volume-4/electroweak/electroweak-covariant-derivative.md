---
title: "Electroweak Covariant Derivative"
description: "Builds the electroweak covariant derivative for quarks, leptons, and the Higgs doublet, and rewrites it in charged-current, neutral-current, photon, and Z-boson form."
sidebar:
  label: "Electroweak Covariant Derivative"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–89; Schwartz Ch. 29; Weinberg Vol. II electroweak chapters."
topics:
  - electroweak covariant derivative
  - weak charged current
  - weak neutral current
  - photon Z mixing
  - Standard Model interactions
canonicalTopics:
  - electroweak-covariant-derivative
  - charged-current
  - neutral-current
  - photon-z-mixing
  - standard-model-gauge-couplings
researchStatus:
  established:
    - "The electroweak covariant derivative fixes the gauge interactions of Standard Model quarks, leptons, and the Higgs doublet before electroweak symmetry breaking."
  active:
    - "Precision tests often parameterize possible deviations from the Standard Model by modifying electroweak gauge couplings through higher-dimensional operators or extended field content."
---

## Summary

The electroweak covariant derivative is the compact object from which the gauge interactions of leptons, quarks, and the Higgs field are read. For a field in an $SU(2)_L$ representation with generators $T^a$ and hypercharge $Y$, this volume uses

$$
D_\mu
=
\partial_\mu
+igW_\mu^aT^a
+ig'YB_\mu.
$$

For quarks, the full Standard Model derivative also includes color:

$$
D_\mu
=
\partial_\mu
+ig_sG_\mu^AT_c^A
+igW_\mu^aT_L^a
+ig'YB_\mu.
$$

The derivative is not the same operator on every field. It depends on the field's representation. A lepton doublet, a right-handed charged lepton, a quark doublet, a right-handed up quark, and the Higgs doublet all see different matrices and different hypercharges.

After electroweak symmetry breaking, the neutral part can be rewritten as

$$
igW_\mu^3T^3+ig'YB_\mu
=
ieQA_\mu
+i\frac{g}{c_W}(T^3-s_W^2Q)Z_\mu,
$$

where $s_W=\sin\theta_W$, $c_W=\cos\theta_W$, and $Q=T^3+Y$. This formula is the seed of electromagnetic universality and weak neutral-current structure.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Electroweak covariant derivative decomposition](/figures/gauge-theories-standard-model/electroweak-covariant-derivative-flow.svg)

<figcaption>

The covariant derivative first acts in the gauge basis through $W_\mu^a$ and $B_\mu$. After the Higgs vacuum selects $Q=T^3+Y$, its neutral part reorganizes into the photon coupling $eQ$ and the $Z$ coupling $\frac{g}{c_W}(T^3-s_W^2Q)$, while $W^\pm$ couple through $T^\pm$.

</figcaption>
</figure>

## Prerequisites

You should know [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/) and the convention

$$
Q=T^3+Y.
$$

You should also know [Covariant Derivative in Representations](/gauge-theories-standard-model/yang-mills/covariant-derivative-in-representations/), because this page is an applied representation-by-representation version of the same idea.

The page [QCD Lagrangian](/gauge-theories-standard-model/qcd/qcd-lagrangian/) fixes the color part of the derivative for quarks. The page [SU(2)L × U(1)Y Gauge Structure](/gauge-theories-standard-model/electroweak/su2-u1-gauge-structure/) fixes the electroweak gauge fields and field strengths.

## Core idea

The covariant derivative is the local instruction for comparing field values at neighboring spacetime points while respecting gauge redundancy. In the Standard Model, the instruction depends on the representation of the field:

$$
\text{field } \Phi
\quad\leadsto\quad
D_\mu\Phi
=
\left[
\partial_\mu
+i(\text{color connection})
+i(\text{weak connection})
+i(\text{hypercharge connection})
\right]\Phi.
$$

For a generic field with Standard Model representation data

$$
(R_c,R_L)_Y,
$$

the derivative is

$$
D_\mu
=
\partial_\mu
+ig_sG_\mu^AT_{R_c}^A
+igW_\mu^aT_{R_L}^a
+ig'YB_\mu.
$$

Here

- $T_{R_c}^A$ are $SU(3)_c$ generators in the color representation $R_c$;
- $T_{R_L}^a$ are $SU(2)_L$ generators in the weak representation $R_L$;
- $Y$ is a number multiplying the identity on the field;
- missing factors vanish because singlet generators are zero.

This is why one should not write “the Standard Model covariant derivative” as though it were one universal matrix. There is one formula, but its concrete matrix content changes from field to field.

## Setup and conventions

The weak charged fields are

$$
W_\mu^\pm=\frac{1}{\sqrt2}(W_\mu^1\mp iW_\mu^2),
$$

and the weak ladder generators are

$$
T^\pm=T^1\pm iT^2.
$$

Then

$$
W_\mu^1T^1+W_\mu^2T^2
=
\frac{1}{\sqrt2}
\left(W_\mu^+T^+ + W_\mu^-T^-\right).
$$

So the electroweak derivative may be written in the gauge basis as

$$
D_\mu
=
\partial_\mu
+\frac{ig}{\sqrt2}
\left(W_\mu^+T^+ + W_\mu^-T^-\right)
+igW_\mu^3T^3
+ig'YB_\mu.
$$

The neutral physical fields are defined by

$$
A_\mu=s_WW_\mu^3+c_WB_\mu,
\qquad
Z_\mu=c_WW_\mu^3-s_WB_\mu,
$$

where

$$
\tan\theta_W=\frac{g'}{g},
\qquad
s_W=\sin\theta_W,
\qquad
c_W=\cos\theta_W.
$$

Equivalently,

$$
W_\mu^3=c_WZ_\mu+s_WA_\mu,
\qquad
B_\mu=c_WA_\mu-s_WZ_\mu.
$$

The electric charge is

$$
e=gs_W=g'c_W.
$$

Using $Q=T^3+Y$, the neutral derivative becomes

$$
igW_\mu^3T^3+ig'YB_\mu
=
ieQA_\mu
+i\frac{g}{c_W}(T^3-s_W^2Q)Z_\mu.
$$

This identity is worth memorizing. It is the one-line bridge from electroweak gauge eigenstates to electromagnetic and neutral weak interactions.

## Field-by-field derivatives

The following list uses one fermion generation. Generation labels are suppressed. Quark fields are color triplets, so their derivatives include the gluon connection. Leptons and the Higgs are color singlets.

### Lepton doublet

The left-handed lepton doublet is

$$
L_L=
\binom{\nu_L}{e_L},
\qquad
L_L\sim(\mathbf 1,\mathbf 2)_{-1/2}.
$$

Therefore

$$
D_\mu L_L
=
\left[
\partial_\mu
+igW_\mu^a\frac{\sigma^a}{2}
-\frac{i}{2}g'B_\mu
\right]L_L.
$$

In charged and neutral gauge-basis form,

$$
D_\mu L_L
=
\left[
\partial_\mu
+\frac{ig}{\sqrt2}(W_\mu^+T^+ + W_\mu^-T^-)
+igW_\mu^3T^3
-\frac{i}{2}g'B_\mu
\right]L_L.
$$

The charged terms connect $\nu_L$ and $e_L$. The neutral terms distinguish them through $T^3$ and $Q$ after the $A$–$Z$ rotation.

### Right-handed charged lepton

The right-handed charged lepton is

$$
e_R\sim(\mathbf 1,\mathbf 1)_{-1}.
$$

It is a weak singlet, so $T^a=0$. Therefore

$$
D_\mu e_R
=
(\partial_\mu-ig'B_\mu)e_R.
$$

After the neutral rotation,

$$
D_\mu e_R
=
\left[
\partial_\mu
-ieA_\mu
+i\frac{g}{c_W}s_W^2Z_\mu
\right]e_R.
$$

This follows from $T^3=0$ and $Q=-1$ in

$$
i\frac{g}{c_W}(T^3-s_W^2Q)Z_\mu.
$$

The right-handed electron couples electromagnetically and to the $Z$, but not to $W^\pm$.

### Quark doublet

The left-handed quark doublet is

$$
Q_L=
\binom{u_L}{d_L},
\qquad
Q_L\sim(\mathbf 3,\mathbf 2)_{1/6}.
$$

Let $t^A=\lambda^A/2$ be the fundamental $SU(3)_c$ generators. Then

$$
D_\mu Q_L
=
\left[
\partial_\mu
+ig_sG_\mu^At^A
+igW_\mu^a\frac{\sigma^a}{2}
+\frac{i}{6}g'B_\mu
\right]Q_L.
$$

The color generators act on the suppressed color index, while the Pauli matrices act on the weak-isospin index. These are different vector spaces, so the actions commute.

The charged weak part connects the two weak components,

$$
u_L
\longleftrightarrow
d_L,
$$

while color leaves the weak component unchanged and rotates the color index.

### Right-handed up quark

The right-handed up quark is

$$
u_R\sim(\mathbf 3,\mathbf 1)_{2/3}.
$$

Therefore

$$
D_\mu u_R
=
\left[
\partial_\mu
+ig_sG_\mu^At^A
+\frac{2i}{3}g'B_\mu
\right]u_R.
$$

In the physical neutral basis,

$$
D_\mu u_R
=
\left[
\partial_\mu
+ig_sG_\mu^At^A
+\frac{2i}{3}eA_\mu
-\frac{2i}{3}\frac{g}{c_W}s_W^2Z_\mu
\right]u_R.
$$

Again, $u_R$ has no $W^\pm$ coupling because it is an $SU(2)_L$ singlet.

### Right-handed down quark

The right-handed down quark is

$$
d_R\sim(\mathbf 3,\mathbf 1)_{-1/3}.
$$

Therefore

$$
D_\mu d_R
=
\left[
\partial_\mu
+ig_sG_\mu^At^A
-\frac{i}{3}g'B_\mu
\right]d_R.
$$

In the physical neutral basis,

$$
D_\mu d_R
=
\left[
\partial_\mu
+ig_sG_\mu^At^A
-\frac{i}{3}eA_\mu
+\frac{i}{3}\frac{g}{c_W}s_W^2Z_\mu
\right]d_R.
$$

### Higgs doublet

The Higgs doublet is

$$
H=
\binom{H^+}{H^0},
\qquad
H\sim(\mathbf 1,\mathbf 2)_{1/2}.
$$

Thus

$$
D_\mu H
=
\left[
\partial_\mu
+igW_\mu^a\frac{\sigma^a}{2}
+\frac{i}{2}g'B_\mu
\right]H.
$$

This is the derivative that produces the gauge-boson mass matrix after $H$ develops a vacuum expectation value. If

$$
\langle H\rangle=\frac{1}{\sqrt2}\binom{0}{v},
$$

then

$$
(D_\mu\langle H\rangle)^\dagger(D^\mu\langle H\rangle)
=
\frac{v^2}{8}
\left[
g^2(W_\mu^1W^{1\mu}+W_\mu^2W^{2\mu})
+(gW_\mu^3-g'B_\mu)(gW^{3\mu}-g'B^\mu)
\right].
$$

So the charged combination $W^\pm$ becomes massive, the neutral combination proportional to $gW^3-g'B$ becomes the $Z$, and the orthogonal combination remains the photon. The full mass derivation belongs to the electroweak symmetry breaking page, but its origin is already visible in $D_\mu H$.

## A compact Standard Model table

The derivative for one generation can be summarized as follows.

| Field | Representation | Covariant derivative |
|---|---|---|
| $Q_L$ | $(\mathbf 3,\mathbf 2)_{1/6}$ | $\partial_\mu+ig_sG_\mu^At^A+igW_\mu^a\sigma^a/2+i g'B_\mu/6$ |
| $u_R$ | $(\mathbf 3,\mathbf 1)_{2/3}$ | $\partial_\mu+ig_sG_\mu^At^A+2ig'B_\mu/3$ |
| $d_R$ | $(\mathbf 3,\mathbf 1)_{-1/3}$ | $\partial_\mu+ig_sG_\mu^At^A-ig'B_\mu/3$ |
| $L_L$ | $(\mathbf 1,\mathbf 2)_{-1/2}$ | $\partial_\mu+igW_\mu^a\sigma^a/2-ig'B_\mu/2$ |
| $e_R$ | $(\mathbf 1,\mathbf 1)_{-1}$ | $\partial_\mu-ig'B_\mu$ |
| $H$ | $(\mathbf 1,\mathbf 2)_{1/2}$ | $\partial_\mu+igW_\mu^a\sigma^a/2+ig'B_\mu/2$ |

The table is deliberately written before electroweak symmetry breaking. It is the cleanest way to see the gauge structure. The physical-basis couplings to $A_\mu$, $Z_\mu$, and $W^\pm_\mu$ are derived from this table, not postulated separately.

## Four-component notation and chiral projectors

Many particle-physics formulas use four-component Dirac spinors. For a charged lepton one writes

$$
e=e_L+e_R,
\qquad
e_L=P_Le,
\qquad
e_R=P_Re,
$$

with

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2}.
$$

The electroweak derivative does not act on $e_L$ and $e_R$ in the same way. One can package the neutral couplings after symmetry breaking as

$$
\bar e\,i\gamma^\mu D_\mu e
=
\bar e i\gamma^\mu(\partial_\mu-ieA_\mu)e
-\frac{g}{c_W}Z_\mu
\bar e\gamma^\mu
\left[
(T^3_e-s_W^2Q_e)P_L
+
(-s_W^2Q_e)P_R
\right]e,
$$

where $T^3_e=-1/2$ for the left-handed electron and $Q_e=-1$. The sign in the interaction term comes from inserting $D_\mu=\partial_\mu+i(\cdots)$ into $\bar e\,i\gamma^\mu D_\mu e$.

It is often cleaner to keep the chiral fields separate until the end. That avoids pretending that a single weak-isospin matrix acts on both $e_L$ and $e_R$.

## Charged currents from the derivative

The charged part of the derivative is

$$
D_\mu\supset
\frac{ig}{\sqrt2}
\left(W_\mu^+T^+ + W_\mu^-T^-\right).
$$

For lepton doublets this gives charged-current interactions of the form

$$
\mathcal L_{\rm cc}^{\ell}
=
-\frac{g}{\sqrt2}
\left[
W_\mu^+\,\bar\nu_L\gamma^\mu e_L
+
W_\mu^-\,\bar e_L\gamma^\mu\nu_L
\right],
$$

where the overall minus sign follows from $\bar\psi i\gamma^\mu D_\mu\psi$ with our $D_\mu$ convention.

For quark doublets in the weak-interaction basis,

$$
\mathcal L_{\rm cc}^{q}
=
-\frac{g}{\sqrt2}
\left[
W_\mu^+\,\bar u_L\gamma^\mu d_L
+
W_\mu^-\,\bar d_L\gamma^\mu u_L
\right].
$$

After quark mass matrices are diagonalized, the charged current contains the CKM matrix. That flavor structure belongs to the Flavor and Neutrinos chapter. The key point here is representation-theoretic: charged currents come from $T^\pm$ acting on left-handed weak doublets.

## Neutral currents from the derivative

The neutral physical-basis derivative is

$$
D_\mu\supset
ieQA_\mu
+i\frac{g}{c_W}(T^3-s_W^2Q)Z_\mu.
$$

The photon coupling is universal: it depends only on $Q$. Thus both $e_L$ and $e_R$ have the same electromagnetic charge $-1$, even though they have different electroweak representations before symmetry breaking.

The $Z$ coupling is not universal in the same way. It depends on

$$
T^3-s_W^2Q.
$$

For left-handed fermions in doublets, $T^3=\pm1/2$. For right-handed singlets, $T^3=0$. This gives the characteristic chiral structure of neutral weak interactions.

For example, the $Z$ charges in the derivative are

| Field | $T^3$ | $Q$ | $T^3-s_W^2Q$ |
|---|---:|---:|---:|
| $\nu_L$ | $1/2$ | $0$ | $1/2$ |
| $e_L$ | $-1/2$ | $-1$ | $-1/2+s_W^2$ |
| $e_R$ | $0$ | $-1$ | $s_W^2$ |
| $u_L$ | $1/2$ | $2/3$ | $1/2-\frac23s_W^2$ |
| $u_R$ | $0$ | $2/3$ | $-\frac23s_W^2$ |
| $d_L$ | $-1/2$ | $-1/3$ | $-1/2+\frac13s_W^2$ |
| $d_R$ | $0$ | $-1/3$ | $\frac13s_W^2$ |

This table is the compact origin of vector and axial $Z$ couplings. Later pages will translate it into weak neutral currents.

## Why the derivative knows the high-energy theory

At low energies, weak interactions are often summarized by four-fermion operators. At high energies, that is not enough. The electroweak covariant derivative encodes relations among all of the following:

- charged-current couplings;
- neutral-current couplings;
- photon couplings;
- $W$ and $Z$ interactions with the Higgs;
- gauge-boson self-interactions;
- the pattern of gauge-boson masses;
- the relation $e=gs_W=g'c_W$.

These relations are what make the electroweak theory a gauge theory rather than a pile of vertices. Changing one coupling without changing the others usually breaks gauge invariance, unitarity, or renormalizability unless the change comes from a consistent EFT operator or an extended ultraviolet theory.

## Common pitfalls

**Using the same weak generator for left- and right-handed fields.** Right-handed charged fermions are weak singlets in the minimal Standard Model. Their $T^a$ matrices are zero.

**Forgetting color in quark derivatives.** Electroweak pages often suppress color, but the full derivative on quarks contains $ig_sG_\mu^At^A$.

**Calling $W^3_\mu$ the $Z$ boson.** The $Z$ is $c_WW_\mu^3-s_WB_\mu$ after symmetry breaking. The orthogonal combination is the photon.

**Dropping the factor $1/\sqrt2$ in the charged-current derivative.** With $W^\pm=(W^1\mp iW^2)/\sqrt2$ and $T^\pm=T^1\pm iT^2$, the charged part is $\frac{g}{\sqrt2}(W^+T^+ + W^-T^-)$ inside the connection.

**Confusing derivative signs with vertex signs.** This volume uses $D_\mu=\partial_\mu+i(\cdots)$. In the fermion Lagrangian $\bar\psi i\gamma^\mu D_\mu\psi$, gauge interactions appear with an extra minus sign. A different derivative convention moves that sign elsewhere.

**Treating $Q$ as an input generator before the Higgs vacuum.** Before symmetry breaking, the gauge-basis generators are $T^a$ and $Y$. The generator $Q=T^3+Y$ becomes the unbroken electromagnetic generator because of the Higgs vacuum direction.

**Forgetting that $Y$ multiplies the identity.** Hypercharge does not mix doublet components. Weak isospin matrices do.

**Writing a bare fermion mass term too early.** Since left- and right-handed fermions have different electroweak representations, masses must arise through Higgs Yukawa couplings in the minimal theory.

## Relations to other pages

This page turns [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/) into an operator. The next pages use it to derive [Electroweak Symmetry Breaking](/gauge-theories-standard-model/electroweak/electroweak-symmetry-breaking/), [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/), [Weak Charged Current](/gauge-theories-standard-model/electroweak/weak-charged-current/), and [Weak Neutral Current](/gauge-theories-standard-model/electroweak/weak-neutral-current/).

The same derivative appears in the Higgs Sector chapter, where $(D_\mu H)^\dagger D^\mu H$ produces gauge-boson masses and Higgs–gauge interactions. It also appears in the Standard Model Architecture chapter, where color, electroweak theory, Yukawa terms, the Higgs potential, and anomaly cancellation are assembled into the full Lagrangian.

## Research status

The electroweak covariant derivative of the minimal Standard Model is established. Its representation-by-representation structure is fixed by the gauge group, the observed electroweak field content, and the hypercharge assignments.

Active work concerns possible deformations and extensions: SMEFT operators that modify gauge and Higgs couplings, extra gauge bosons, extended Higgs sectors, vectorlike fermions, sterile neutrinos, composite Higgs models, and precision tests of charged and neutral currents. In all such cases, the Standard Model covariant derivative is the reference point.

## Exercises

### Exercise 1: Derive the photon and Z couplings

Starting from

$$
igW_\mu^3T^3+ig'YB_\mu,
$$

use

$$
W_\mu^3=c_WZ_\mu+s_WA_\mu,
\qquad
B_\mu=c_WA_\mu-s_WZ_\mu,
$$

and $e=gs_W=g'c_W$ to show that

$$
igW_\mu^3T^3+ig'YB_\mu
=
ieQA_\mu
+i\frac{g}{c_W}(T^3-s_W^2Q)Z_\mu.
$$

<details><summary><strong>Solution</strong></summary>

Substitute the rotation:

$$
igT^3(c_WZ_\mu+s_WA_\mu)
+
ig'Y(c_WA_\mu-s_WZ_\mu).
$$

The coefficient of $A_\mu$ is

$$
i(gs_WT^3+g'c_WY)=ie(T^3+Y)=ieQ.
$$

The coefficient of $Z_\mu$ is

$$
i(gc_WT^3-g's_WY).
$$

Using $g'=g\,s_W/c_W$ gives

$$
i\frac{g}{c_W}(c_W^2T^3-s_W^2Y).
$$

Since $c_W^2=1-s_W^2$,

$$
c_W^2T^3-s_W^2Y
=
T^3-s_W^2(T^3+Y)
=
T^3-s_W^2Q.
$$

Therefore

$$
igW_\mu^3T^3+ig'YB_\mu
=
ieQA_\mu
+i\frac{g}{c_W}(T^3-s_W^2Q)Z_\mu.
$$

</details>

### Exercise 2: Charged weak action on a lepton doublet

For

$$
L_L=\binom{\nu_L}{e_L},
$$

compute $T^+L_L$ and $T^-L_L$ using

$$
T^+=
\begin{pmatrix}
0&1\\
0&0
\end{pmatrix},
\qquad
T^-=
\begin{pmatrix}
0&0\\
1&0
\end{pmatrix}.
$$

Explain which $W$ field couples to $\bar\nu_L\gamma^\mu e_L$.

<details><summary><strong>Solution</strong></summary>

Acting on the doublet,

$$
T^+L_L=
\binom{e_L}{0},
\qquad
T^-L_L=
\binom{0}{\nu_L}.
$$

The charged part of the derivative is

$$
D_\mu\supset
\frac{ig}{\sqrt2}(W_\mu^+T^+ + W_\mu^-T^-).
$$

In the fermion Lagrangian, this produces

$$
-\frac{g}{\sqrt2}
W_\mu^+\bar L_L\gamma^\mu T^+L_L
=
-\frac{g}{\sqrt2}
W_\mu^+\bar\nu_L\gamma^\mu e_L.
$$

Thus $W^+$ couples to the current $\bar\nu_L\gamma^\mu e_L$, while $W^-$ couples to its Hermitian conjugate.

</details>

### Exercise 3: Higgs mass matrix from the derivative

Use

$$
D_\mu H=
\left(
\partial_\mu
+igW_\mu^a\frac{\sigma^a}{2}
+\frac{i}{2}g'B_\mu
\right)H
$$

and

$$
\langle H\rangle=\frac{1}{\sqrt2}\binom{0}{v}
$$

to derive

$$
(D_\mu\langle H\rangle)^\dagger(D^\mu\langle H\rangle)
=
\frac{v^2}{8}
\left[
g^2(W_\mu^1W^{1\mu}+W_\mu^2W^{2\mu})
+(gW_\mu^3-g'B_\mu)^2
\right].
$$

<details><summary><strong>Solution</strong></summary>

Since the vacuum is constant, only the gauge connection acts. Using Pauli matrices,

$$
\frac{\sigma^1}{2}\binom{0}{v/\sqrt2}
=
\frac{v}{2\sqrt2}\binom{1}{0},
\qquad
\frac{\sigma^2}{2}\binom{0}{v/\sqrt2}
=
-\frac{iv}{2\sqrt2}\binom{1}{0},
$$

and

$$
\frac{\sigma^3}{2}\binom{0}{v/\sqrt2}
=
-\frac{v}{2\sqrt2}\binom{0}{1}.
$$

Also

$$
Y_H\binom{0}{v/\sqrt2}
=
\frac12\binom{0}{v/\sqrt2}.
$$

Therefore

$$
D_\mu\langle H\rangle
=
\frac{iv}{2\sqrt2}
\binom{
g(W_\mu^1-iW_\mu^2)
}{
-gW_\mu^3+g'B_\mu
}.
$$

Taking the norm gives

$$
(D_\mu\langle H\rangle)^\dagger(D^\mu\langle H\rangle)
=
\frac{v^2}{8}
\left[
g^2((W_\mu^1)^2+(W_\mu^2)^2)
+(gW_\mu^3-g'B_\mu)^2
\right],
$$

with Lorentz indices contracted in the usual way.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§87–89, for the Standard Model gauge, lepton, and quark sectors.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 29, for weak interactions and electroweak symmetry breaking.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the general treatment of spontaneously broken gauge theories and electroweak interactions.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for the conceptual role of gauge fields and the Higgs phenomenon.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*, for standard electroweak Feynman rules and tree-level weak processes.

## Version history

- **2026-06-18:** Initial polished draft. Wrote the field-by-field Standard Model covariant derivatives and derived the photon and $Z$ couplings in the convention $D_\mu=\partial_\mu+igW_\mu^aT^a+ig'YB_\mu$.
