---
title: "Weak Isospin and Hypercharge"
description: "Explains weak isospin, hypercharge, the convention Q = T³ + Y, and the chiral electroweak representation assignments of Standard Model matter and the Higgs doublet."
sidebar:
  label: "Weak Isospin and Hypercharge"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–89; Schwartz Ch. 29; Weinberg Vol. II electroweak chapters."
topics:
  - weak isospin
  - hypercharge
  - electroweak charges
  - chiral gauge theory
  - Standard Model representations
canonicalTopics:
  - weak-isospin
  - hypercharge
  - electric-charge-generator
  - electroweak-representation-data
  - standard-model-fermion-representations
researchStatus:
  established:
    - "The Standard Model electroweak charge assignments are fixed by the local SU(2)L × U(1)Y gauge structure, observed electric charges, the Higgs representation, Yukawa gauge invariance, and anomaly cancellation."
  active:
    - "The minimal electroweak assignments are established, while neutrino-mass extensions, flavor structure, anomaly-free BSM representations, and global-form questions remain active research interfaces."
---

## Summary

Weak isospin and hypercharge are the two electroweak charge labels before electroweak symmetry breaking. A field carries an $SU(2)_L$ representation, acted on by generators $T^a$, and a $U(1)_Y$ charge $Y$. In this volume the electric charge generator is

$$
Q=T^3+Y.
$$

This convention is common in modern Standard Model treatments. Some books instead write $Q=T^3+Y_{\rm old}/2$; their hypercharge is $Y_{\rm old}=2Y$.

The essential fact is that weak isospin is chiral. In the minimal Standard Model, left-handed quarks and leptons sit in weak doublets, while right-handed charged fermions are weak singlets. The Higgs field is also a weak doublet. The charge assignments are not a decorative table to memorize; they are the representation data that make electroweak gauge invariance, electromagnetism, fermion masses, and anomaly cancellation fit together.

<figure class="doc-figure" style="--figure-width: 45rem;">

![Weak isospin and hypercharge assignments](/figures/gauge-theories-standard-model/weak-isospin-hypercharge-map.svg)

<figcaption>

Electroweak charge bookkeeping in the convention $Q=T^3+Y$. Weak doublets occupy two levels with $T^3=\frac12$ and $T^3=-\frac12$ at fixed hypercharge $Y$; weak singlets have $T^3=0$, so their hypercharge equals their electric charge.

</figcaption>
</figure>

## Prerequisites

You should know [SU(2)L × U(1)Y Gauge Structure](/gauge-theories-standard-model/electroweak/su2-u1-gauge-structure/) and the representation language from [Matter Representations](/gauge-theories-standard-model/gauge-principle/matter-representations/). The page [Color SU(3)](/gauge-theories-standard-model/qcd/color-su3/) is useful for contrast: color is vectorlike and unbroken, while weak isospin is chiral and Higgsed.

The only convention you must keep pinned to the wall is

$$
D_\mu=\partial_\mu+igW_\mu^aT^a+ig'YB_\mu,
\qquad
Q=T^3+Y.
$$

If you compare with a source using $Q=T^3+Y/2$, divide that source's listed hypercharges by two before using formulas in this chapter.

## Core idea

Electroweak representation data answer two different questions.

The $SU(2)_L$ representation answers: **which fields are connected by charged weak interactions?** If a field is a weak doublet, the generators $T^1$ and $T^2$ connect its upper and lower components. If it is a weak singlet, $T^a=0$ and it does not couple to $W_\mu^1$, $W_\mu^2$, or $W_\mu^3$ directly.

The hypercharge $Y$ answers: **how does the field couple to the Abelian gauge boson $B_\mu$ before symmetry breaking?** Because $Y$ commutes with $SU(2)_L$, every component inside a weak multiplet has the same hypercharge.

Electric charge is then the derived quantity

$$
Q=T^3+Y.
$$

For a weak doublet

$$
\binom{\psi_+}{\psi_-},
\qquad
T^3=\frac12
\begin{pmatrix}
1&0\\
0&-1
\end{pmatrix},
$$

the electric charges are

$$
Q(\psi_+)=Y+\frac12,
\qquad
Q(\psi_-)=Y-\frac12.
$$

For a weak singlet, $T^3=0$, so

$$
Q=Y.
$$

That one line explains why the left-handed electron belongs with the neutrino in a doublet, while the right-handed electron is a singlet; why the Higgs doublet has one charged and one neutral component; and why the neutral Higgs vacuum preserves electromagnetism.

## Setup and conventions

The local electroweak gauge group is

$$
SU(2)_L\times U(1)_Y.
$$

For a field in an $SU(2)_L$ representation $R_L$ and hypercharge $Y$, the electroweak covariant derivative is

$$
D_\mu=\partial_\mu+igW_\mu^aT^a_{R_L}+ig'YB_\mu.
$$

The weak generators satisfy

$$
[T^a,T^b]=i\epsilon^{abc}T^c.
$$

For a doublet,

$$
T^a=\frac{\sigma^a}{2},
$$

and for a singlet,

$$
T^a=0.
$$

The useful ladder operators are

$$
T^+=T^1+iT^2,
\qquad
T^-=T^1-iT^2.
$$

On a doublet $(\psi_+,\psi_-)^T$, they act as

$$
T^+\binom{\psi_+}{\psi_-}
=
\binom{\psi_-}{0},
\qquad
T^-\binom{\psi_+}{\psi_-}
=
\binom{0}{\psi_+}.
$$

So $T^+$ raises $T^3$ and $T^-$ lowers $T^3$. The corresponding gauge fields are

$$
W_\mu^\pm=\frac{1}{\sqrt2}(W_\mu^1\mp iW_\mu^2).
$$

The charged weak gauge bosons therefore know about the off-diagonal $SU(2)_L$ generators, not about hypercharge alone.

## One-generation electroweak representation table

For one generation of minimal Standard Model fermions, plus the Higgs doublet, the electroweak data are

| Field | $SU(2)_L$ | $Y$ | Electric charges from $Q=T^3+Y$ |
|---|---:|---:|---:|
| $Q_L=(u_L,d_L)^T$ | $\mathbf 2$ | $1/6$ | $2/3,-1/3$ |
| $u_R$ | $\mathbf 1$ | $2/3$ | $2/3$ |
| $d_R$ | $\mathbf 1$ | $-1/3$ | $-1/3$ |
| $L_L=(\nu_L,e_L)^T$ | $\mathbf 2$ | $-1/2$ | $0,-1$ |
| $e_R$ | $\mathbf 1$ | $-1$ | $-1$ |
| $H=(H^+,H^0)^T$ | $\mathbf 2$ | $1/2$ | $1,0$ |

The quark fields also carry color:

$$
Q_L,u_R,d_R\in \mathbf 3\text{ of }SU(3)_c,
$$

while $L_L,e_R,H$ are color singlets.

The table is written in the common four-component/chirality language: $u_R$, $d_R$, and $e_R$ denote right-handed fermion fields. Anomaly calculations often rewrite all fermions as left-handed Weyl fields. Then a right-handed field is replaced by its charge-conjugate left-handed field, for example $u_R$ becomes $u_L^c$, and the gauge representation is conjugated. Thus

$$
Y(u_R)=\frac23
\quad\text{but}\quad
Y(u_L^c)=-\frac23.
$$

Both notations are correct. They are different ledgers for the same physics.

## Weak isospin

Weak isospin is an internal $SU(2)$ gauge quantum number. It is not spatial spin. It does not say that a particle is rotating in ordinary space, and it does not use the Lorentz generators.

A weak doublet has two components with

$$
T^3=+\frac12
\quad\text{and}\quad
T^3=-\frac12.
$$

For the lepton doublet,

$$
L_L=
\binom{\nu_L}{e_L},
\qquad
Y(L_L)=-\frac12.
$$

Therefore

$$
Q(\nu_L)=+\frac12-\frac12=0,
\qquad
Q(e_L)=-\frac12-\frac12=-1.
$$

For the quark doublet,

$$
Q_L=
\binom{u_L}{d_L},
\qquad
Y(Q_L)=\frac16,
$$

so

$$
Q(u_L)=+\frac12+\frac16=\frac23,
\qquad
Q(d_L)=-\frac12+\frac16=-\frac13.
$$

The charged weak generators connect the members of each doublet. Schematically,

$$
T^+d_L=u_L,
\qquad
T^-u_L=d_L,
$$

and similarly

$$
T^+e_L=\nu_L,
\qquad
T^-\nu_L=e_L.
$$

This is the representation-theory origin of charged weak transitions. The $W^\pm$ interactions do not merely attach to particles with electric charge. They act through the weak-isospin ladder operators.

## Hypercharge

Hypercharge is the $U(1)_Y$ gauge charge. It is assigned to entire weak multiplets, so both components of $L_L$ have the same $Y=-1/2$, and both components of $Q_L$ have the same $Y=1/6$.

A good way to remember hypercharge is:

$$
Y=Q-T^3.
$$

For a weak singlet, $T^3=0$, so the hypercharge is just the electric charge. That gives

$$
Y(e_R)=-1,
\qquad
Y(u_R)=\frac23,
\qquad
Y(d_R)=-\frac13.
$$

For a doublet, $Y$ is the common offset that shifts the two $T^3$ eigenvalues into the observed electric charges. In other words, weak isospin supplies the splitting inside the doublet, while hypercharge supplies the midpoint:

$$
Y=\frac{Q_{\rm upper}+Q_{\rm lower}}{2}.
$$

For $Q_L$, the midpoint of $2/3$ and $-1/3$ is $1/6$. For $L_L$, the midpoint of $0$ and $-1$ is $-1/2$. For the Higgs doublet, the midpoint of $1$ and $0$ is $1/2$.

## The Higgs doublet and the unbroken generator

The Higgs doublet has

$$
H=
\binom{H^+}{H^0},
\qquad
Y_H=\frac12.
$$

Its component charges are

$$
Q(H^+)=+\frac12+\frac12=1,
\qquad
Q(H^0)=-\frac12+\frac12=0.
$$

The neutral component can acquire a vacuum expectation value,

$$
\langle H\rangle
=\frac{1}{\sqrt2}
\binom{0}{v}.
$$

This vacuum is not invariant under $T^3$ alone, because the lower component has $T^3=-1/2$. It is not invariant under $Y$ alone, because the whole doublet has $Y=1/2$. But it is invariant under their sum:

$$
Q\langle H\rangle=(T^3+Y)\langle H\rangle=0.
$$

That is why the unbroken gauge group is electromagnetic $U(1)_{\rm em}$ and why the photon couples to $Q$. The neutral Higgs vacuum is the quiet little line of algebra from which the whole $W$–$Z$–photon story grows.

## Why left and right fields differ

The weak interaction violates parity because the Standard Model assigns different electroweak representations to left-handed and right-handed fermions.

For charged leptons,

$$
L_L=\binom{\nu_L}{e_L}\sim (\mathbf 2,-\tfrac12),
\qquad
e_R\sim (\mathbf 1,-1)
$$

under $SU(2)_L\times U(1)_Y$. Thus $e_L$ participates in charged weak interactions because it is part of $L_L$, while $e_R$ is an $SU(2)_L$ singlet.

For quarks,

$$
Q_L=\binom{u_L}{d_L}\sim(\mathbf 2,\tfrac16),
\qquad
u_R\sim(\mathbf 1,\tfrac23),
\qquad
d_R\sim(\mathbf 1,-\tfrac13).
$$

A gauge-singlet right-handed neutrino $\nu_R\sim(\mathbf 1,0)$ can be added consistently, but it is not part of the minimal Standard Model field content used in this chapter.

The chiral assignments also explain why bare Dirac mass terms are not electroweak gauge invariant. For example, a naive electron mass term would couple $e_L$ and $e_R$,

$$
-m_e\bar e e=-m_e(\bar e_Le_R+\bar e_Re_L),
$$

but $e_L$ sits inside a weak doublet and $e_R$ is a weak singlet. Their electroweak representations do not match. The Higgs doublet supplies the missing representation data through a Yukawa interaction. Fermion masses therefore come after electroweak symmetry breaking, not before it.

## Yukawa gauge invariance as a consistency check

The hypercharge assignments are constrained by the requirement that Yukawa interactions be gauge invariant.

For the charged lepton Yukawa coupling, the gauge-invariant structure is

$$
-y_e\bar L_LHe_R+\text{h.c.}
$$

Under $U(1)_Y$, a barred field carries the opposite hypercharge. The total hypercharge is

$$
Y(\bar L_L)+Y(H)+Y(e_R)
=
+\frac12+\frac12-1=0.
$$

For down-type quarks,

$$
-y_d\bar Q_LHd_R+\text{h.c.},
$$

and the hypercharge sum is

$$
Y(\bar Q_L)+Y(H)+Y(d_R)
=
-\frac16+\frac12-\frac13=0.
$$

For up-type quarks one uses the conjugate Higgs doublet

$$
\widetilde H=i\sigma^2H^*,
\qquad
Y(\widetilde H)=-\frac12,
$$

so

$$
-y_u\bar Q_L\widetilde H u_R+\text{h.c.}
$$

has total hypercharge

$$
Y(\bar Q_L)+Y(\widetilde H)+Y(u_R)
=
-\frac16-\frac12+\frac23=0.
$$

This is a wonderfully efficient sanity check. Hypercharge assignments that reproduce electric charges but fail Yukawa gauge invariance would not give the observed charged-fermion masses through a single Higgs doublet.

## Anomaly cancellation preview

There is one more consistency condition: gauge anomalies must cancel. An anomaly is a quantum obstruction to gauging a classical symmetry. Since electroweak theory is chiral, this is not automatic.

The full anomaly calculation is done later, but it is useful to know what is being checked. In one generation, with every fermion written as a left-handed Weyl field, the anomaly ledger is

| Four-component field language | All-left-handed anomaly language | Hypercharge in anomaly sum |
|---|---|---:|
| $Q_L$ | $Q_L$ | $1/6$ |
| $u_R$ | $u_L^c$ | $-2/3$ |
| $d_R$ | $d_L^c$ | $1/3$ |
| $L_L$ | $L_L$ | $-1/2$ |
| $e_R$ | $e_L^c$ | $1$ |

In this notation the quark and lepton contributions cancel the dangerous gauge anomalies generation by generation. This includes the $SU(2)_L^2U(1)_Y$, $SU(3)_c^2U(1)_Y$, $U(1)_Y^3$, and mixed gauge–gravitational anomalies. The full computation belongs in the Standard Model anomalies chapter.

For now, the moral is enough:

$$
\text{electric charges}
+\text{Yukawa invariance}
+\text{anomaly cancellation}
\quad\Rightarrow\quad
\text{the Standard Model hypercharge pattern}.
$$

The table is not numerology. It is a consistency mechanism.

## Common pitfalls

**Using two hypercharge conventions at once.** This volume uses $Q=T^3+Y$. If a book lists $Y(Q_L)=1/3$ and $Y(H)=1$, it is using $Q=T^3+Y/2$. Divide those hypercharges by two here.

**Thinking weak isospin is ordinary spin.** Weak isospin is an internal gauge representation label. It is unrelated to Lorentz spin, helicity, or Pauli spin in ordinary space.

**Forgetting that $Y$ is constant across a doublet.** The upper and lower members of a weak doublet have different $T^3$ and different $Q$, but the same $Y$.

**Calling $Y$ the electric charge of a doublet.** Hypercharge equals electric charge only for weak singlets. For doublets, $Q$ also includes $T^3$.

**Putting $e_R$ into the lepton doublet.** The doublet is $(\nu_L,e_L)^T$. The field $e_R$ is a weak singlet.

**Adding a right-handed neutrino without saying so.** A gauge-singlet $\nu_R$ can be added and is important in many neutrino-mass models, but it is not part of the minimal Standard Model field table used here.

**Ignoring color in anomaly checks.** Color is irrelevant for computing a particle's electric charge, but it is crucial in anomaly cancellation because quark fields come in three colors.

**Using right-handed notation in anomaly sums without conjugating.** Gauge anomalies are usually summed over left-handed Weyl fields. A right-handed field of charge $Y$ becomes a left-handed conjugate field of charge $-Y$.

## Relations to other pages

This page is the charge-bookkeeping companion to [SU(2)L × U(1)Y Gauge Structure](/gauge-theories-standard-model/electroweak/su2-u1-gauge-structure/). The next page, [Electroweak Covariant Derivative](/gauge-theories-standard-model/electroweak/electroweak-covariant-derivative/), turns the representation table into explicit differential operators on quarks, leptons, and the Higgs field.

The Higgs-sector pages will use $Y_H=1/2$ and $QH_0=0$ to derive gauge-boson masses. The Flavor and Neutrinos chapter will use the same hypercharge assignments to build Yukawa matrices, CKM mixing, PMNS mixing, and neutrino-mass operators. The Standard Model anomaly chapter will turn the anomaly-cancellation preview into an actual calculation.

## Research status

The weak-isospin and hypercharge assignments of the minimal Standard Model are established. Their internal consistency is one of the theory's deepest clues: the assignments reproduce electric charge, make the observed Yukawa interactions gauge invariant, and cancel gauge anomalies.

Active research appears when one asks how this pattern is extended or explained. Grand unification, anomaly-free BSM sectors, neutrino-mass mechanisms, gauged flavor symmetries, dark-sector portals, and global-form questions all start by modifying or embedding the same electroweak charge ledger.

## Exercises

### Exercise 1: Reconstruct hypercharge from electric charge

A weak doublet has component charges $q_+$ and $q_-$. Show that gauge invariance under $SU(2)_L$ requires

$$
q_+-q_-=1,
$$

and that the common hypercharge is

$$
Y=\frac{q_++q_-}{2}.
$$

Apply this to $Q_L$, $L_L$, and $H$.

<details><summary><strong>Solution</strong></summary>

For a doublet,

$$
q_+=Y+\frac12,
\qquad
q_-=Y-\frac12.
$$

Therefore

$$
q_+-q_-=1,
\qquad
q_++q_-=2Y.
$$

So

$$
Y=\frac{q_++q_-}{2}.
$$

For $Q_L$, the charges are $2/3$ and $-1/3$, so

$$
Y(Q_L)=\frac{2/3-1/3}{2}=\frac16.
$$

For $L_L$, the charges are $0$ and $-1$, so

$$
Y(L_L)=-\frac12.
$$

For $H$, the charges are $1$ and $0$, so

$$
Y(H)=\frac12.
$$

</details>

### Exercise 2: Higgs neutrality

Let $H=(H^+,H^0)^T$ be a weak doublet with $Y=1/2$. Show that the vacuum direction $(0,v/\sqrt2)^T$ is neutral under $Q=T^3+Y$.

<details><summary><strong>Solution</strong></summary>

On the lower component of a doublet,

$$
T^3=-\frac12.
$$

Since $Y=1/2$ for the whole Higgs doublet,

$$
QH^0=(T^3+Y)H^0=
\left(-\frac12+\frac12\right)H^0=0.
$$

Therefore

$$
Q\binom{0}{v/\sqrt2}=0.
$$

The Higgs vacuum preserves the electromagnetic generator.

</details>

### Exercise 3: Yukawa hypercharge checks

Verify that the hypercharge sums vanish for

$$
\bar L_LHe_R,
\qquad
\bar Q_LHd_R,
\qquad
\bar Q_L\widetilde H u_R,
$$

where $Y(\widetilde H)=-1/2$.

<details><summary><strong>Solution</strong></summary>

The hypercharges of barred fields have the opposite sign. Therefore

$$
Y(\bar L_LHe_R)=+\frac12+\frac12-1=0,
$$

$$
Y(\bar Q_LHd_R)=-\frac16+\frac12-\frac13=0,
$$

and

$$
Y(\bar Q_L\widetilde H u_R)=-\frac16-\frac12+\frac23=0.
$$

All three interactions are hypercharge neutral.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§87–89, for Standard Model gauge, lepton, and quark sectors.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 29, for weak interactions, electroweak symmetry breaking, fermion assignments, and weak currents.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the electroweak theory as a spontaneously broken chiral gauge theory.
- Georgi, *Weak Interactions and Modern Particle Theory*, for a concise treatment of weak isospin, hypercharge, and weak currents.
- Burgess, *Introduction to Effective Field Theory*, Ch. 9, for the Standard Model field content and symmetries viewed through EFT.

## Version history

- **2026-06-18:** Initial polished draft. Fixed the convention $Q=T^3+Y$ and organized the Standard Model electroweak representation table around weak doublets, singlets, and the neutral Higgs direction.
