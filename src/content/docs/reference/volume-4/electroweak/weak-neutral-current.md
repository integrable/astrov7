---
title: "Weak Neutral Current"
description: "Derives the Z-boson neutral-current interaction, its vector and axial couplings, weak-mixing-angle dependence, parity violation, and flavor structure."
sidebar:
  label: "Weak Neutral Current"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–90; Schwartz Chs. 29 and 31; Weinberg Vol. II electroweak chapters."
topics:
  - weak neutral current
  - Z boson
  - weak mixing angle
  - vector and axial couplings
  - parity violation
canonicalTopics:
  - neutral-current
  - z-boson-coupling
  - weak-mixing-angle
  - vector-axial-couplings
  - electroweak-parity-violation
researchStatus:
  established:
    - "The Standard Model neutral current is mediated by the Z boson and couples to fermions through T3PL − sin²θW Q, producing both vector and axial interactions."
  active:
    - "Precision neutral-current measurements, weak mixing angle determinations, parity-violation experiments, neutrino scattering, and SMEFT fits remain active tests of electroweak theory."
---

## Summary

The weak neutral current is the part of the electroweak interaction mediated by the $Z$ boson. Unlike the charged current, it does not change electric charge. Unlike QED, it is not purely vectorlike: the $Z$ coupling distinguishes left- and right-handed fermions.

After electroweak symmetry breaking, the neutral electroweak interaction can be written as

$$
\mathcal L_{\rm neutral}
=
-eA_\mu J_{\rm em}^\mu
-
\frac{g}{c_W}Z_\mu J_Z^\mu,
$$

where

$$
J_{\rm em}^\mu
=
\sum_f Q_f\bar f\gamma^\mu f,
\qquad
J_Z^\mu
=
\sum_f\bar f\gamma^\mu(T_f^3P_L-s_W^2Q_f)f.
$$

Here

$$
s_W=\sin\theta_W,
\qquad
c_W=\cos\theta_W,
\qquad
Q=T^3+Y.
$$

The photon couples to electric charge $Q$. The $Z$ couples to the different combination $T^3P_L-s_W^2Q$. That small-looking difference is the source of weak neutral currents, parity violation, and the distinctive pattern of $Z$ couplings measured in precision electroweak physics.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Weak neutral current map](/figures/gauge-theories-standard-model/weak-neutral-current-map.svg)

<figcaption>

The neutral electroweak current after the weak mixing rotation. The photon couples to the vectorlike electromagnetic current, while the $Z$ couples to $T^3P_L-s_W^2Q$. In Dirac notation this becomes a vector–axial coupling with $g_V^f=T_f^3-2Q_fs_W^2$ and $g_A^f=T_f^3$.

</figcaption>
</figure>

Historically, weak neutral currents were a major prediction of the electroweak theory: if the weak and electromagnetic forces really come from $SU(2)_L\times U(1)_Y$, there must be a neutral weak interaction in addition to charged $W$ exchange.

## Prerequisites

You should know [Weak Isospin and Hypercharge](/gauge-theories-standard-model/electroweak/weak-isospin-and-hypercharge/), [Electroweak Covariant Derivative](/gauge-theories-standard-model/electroweak/electroweak-covariant-derivative/), [Electroweak Symmetry Breaking](/gauge-theories-standard-model/electroweak/electroweak-symmetry-breaking/), [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/), and [Weak Charged Current](/gauge-theories-standard-model/electroweak/weak-charged-current/).

You should also be comfortable with chiral projectors,

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2},
$$

and with the convention $Q=T^3+Y$.

## Core idea

Before electroweak symmetry breaking, the neutral gauge fields are $W_\mu^3$ and $B_\mu$. Their couplings to a fermion are determined by weak isospin and hypercharge:

$$
\mathcal L_{\rm neutral}^{\rm gauge}
=
-gW_\mu^3\bar f_L\gamma^\mu T^3f_L
-g'B_\mu\bar f\gamma^\mu Yf.
$$

After the Higgs vacuum chooses the unbroken generator $Q=T^3+Y$, the neutral gauge fields rotate to

$$
A_\mu=s_WW_\mu^3+c_WB_\mu,
\qquad
Z_\mu=c_WW_\mu^3-s_WB_\mu.
$$

The inverse relations are

$$
W_\mu^3=s_WA_\mu+c_WZ_\mu,
\qquad
B_\mu=c_WA_\mu-s_WZ_\mu.
$$

Using

$$
e=gs_W=g'c_W,
$$

the photon part becomes

$$
-eA_\mu\bar f\gamma^\mu Qf,
$$

which is ordinary QED. The orthogonal neutral field is the $Z$ boson, and its coupling is

$$
-\frac{g}{c_W}Z_\mu\bar f\gamma^\mu(T^3P_L-s_W^2Q)f.
$$

Thus the neutral current is not guessed. It is forced by the same weak mixing rotation that produces the massless photon.

## Setup and conventions

We use

$$
A_\mu=s_WW_\mu^3+c_WB_\mu,
\qquad
Z_\mu=c_WW_\mu^3-s_WB_\mu,
$$

with

$$
\tan\theta_W=\frac{g'}{g},
\qquad
s_W=\frac{g'}{\sqrt{g^2+g'^2}},
\qquad
c_W=\frac{g}{\sqrt{g^2+g'^2}}.
$$

The neutral-current interaction is

$$
\mathcal L_{\rm neutral}
=
-eA_\mu J_{\rm em}^\mu
-
\frac{g}{c_W}Z_\mu J_Z^\mu,
$$

where

$$
J_Z^\mu
=
\sum_f\bar f\gamma^\mu(g_L^fP_L+g_R^fP_R)f
$$

with

$$
g_L^f=T_f^3-s_W^2Q_f,
\qquad
g_R^f=-s_W^2Q_f.
$$

Here $T_f^3$ means the weak isospin of the left-handed component of the Dirac fermion $f$. For right-handed charged fermions in the minimal Standard Model, $T^3=0$.

## Vector and axial couplings

It is often useful to write the $Z$ interaction as

$$
\mathcal L_Z
=
-\frac{g}{2c_W}Z_\mu
\sum_f\bar f\gamma^\mu(g_V^f-g_A^f\gamma^5)f.
$$

This is equivalent to the chiral form if

$$
g_V^f=g_L^f+g_R^f=T_f^3-2Q_fs_W^2,
\qquad
g_A^f=g_L^f-g_R^f=T_f^3.
$$

The axial coupling is exactly where parity violation enters. If $g_A^f=0$, the $Z$ coupling to $f$ would be vectorlike. In the Standard Model, $g_A^f$ is nonzero for fermions whose left-handed component belongs to a weak doublet.

For one generation, the standard tree-level couplings are:

| Fermion $f$ | $Q_f$ | $T_f^3$ | $g_L^f$ | $g_R^f$ | $g_V^f$ | $g_A^f$ |
|---|---:|---:|---:|---:|---:|---:|
| $\nu$ | $0$ | $+1/2$ | $+1/2$ | $0$ | $+1/2$ | $+1/2$ |
| $e$ | $-1$ | $-1/2$ | $-1/2+s_W^2$ | $s_W^2$ | $-1/2+2s_W^2$ | $-1/2$ |
| $u$ | $+2/3$ | $+1/2$ | $+1/2-(2/3)s_W^2$ | $-(2/3)s_W^2$ | $+1/2-(4/3)s_W^2$ | $+1/2$ |
| $d$ | $-1/3$ | $-1/2$ | $-1/2+(1/3)s_W^2$ | $(1/3)s_W^2$ | $-1/2+(2/3)s_W^2$ | $-1/2$ |

The table is often the most efficient way to check signs. Notice especially that neutrinos couple to the $Z$ but not to the photon.

## Left and right couplings

The chiral form

$$
J_Z^\mu
=
\sum_f\bar f\gamma^\mu(g_L^fP_L+g_R^fP_R)f
$$

makes the asymmetry between left and right transparent.

For a charged lepton,

$$
g_L^e=-\frac12+s_W^2,
\qquad
g_R^e=s_W^2.
$$

For a neutrino in the minimal Standard Model,

$$
g_L^\nu=\frac12,
\qquad
g_R^\nu=0.
$$

This is why neutrino neutral-current scattering exists even though neutrinos are electrically neutral. It is also why neutral-current measurements probe the weak mixing angle and the chiral structure of the Standard Model.

## Flavor structure

At tree level, Standard Model neutral currents are flavor diagonal. This is a crucial contrast with the charged current.

The reason is simple. In a given charge sector, the neutral-current generators are proportional to the identity in generation space. When one rotates from weak-basis fields to mass-basis fields, unitary matrices cancel:

$$
\bar f'_L\gamma^\mu f'_L
=
\bar f_L U_L^\dagger\gamma^\mu U_L f_L
=
\bar f_L\gamma^\mu f_L.
$$

The same happens for right-handed fields. Therefore, the $Z$ interaction does not contain a tree-level analogue of the CKM matrix.

This fact is often summarized as **no tree-level flavor-changing neutral currents** in the minimal Standard Model. Flavor-changing neutral-current processes can still occur through loops, but they are suppressed by the GIM mechanism and CKM factors.

## Why neutral currents are weak but not electromagnetic

The photon and the $Z$ both come from the neutral electroweak gauge fields, but they couple to different currents.

The photon sees

$$
J_{\rm em}^\mu=\sum_fQ_f\bar f\gamma^\mu f.
$$

This is vectorlike: left and right components with the same electric charge couple equally.

The $Z$ sees

$$
J_Z^\mu=\sum_f\bar f\gamma^\mu(T_f^3P_L-s_W^2Q_f)f.
$$

This contains a universal piece proportional to electric charge and a chiral piece proportional to $T^3P_L$. The first resembles QED in its charge dependence. The second remembers that only left-handed fermions are $SU(2)_L$ doublets.

So the neutral current is “neutral” in the sense that it does not change electric charge, not in the sense that it is the same as electromagnetism.

## Common pitfalls

**Thinking neutral means electromagnetic.** The $Z$ current is electrically neutral, but it is not the electromagnetic current. It contains $T^3P_L$ and is therefore chiral.

**Forgetting the factor of $1/(2c_W)$ in vector–axial notation.** The formula with $g_V$ and $g_A$ is usually written with $g/(2c_W)$. The formula with $T^3P_L-s_W^2Q$ is written with $g/c_W$. These are equivalent.

**Using $T^3$ for right-handed charged fermions.** In the minimal Standard Model, right-handed charged fermions are weak-isospin singlets. Their $Z$ coupling comes only from the $-s_W^2Q$ term.

**Expecting CKM factors in tree-level $Z$ couplings.** CKM mixing appears in charged currents. Neutral currents are flavor diagonal at tree level because unitary rotations cancel inside each charge sector.

**Calling neutrino neutral-current scattering electromagnetic.** Neutrinos have $Q=0$, so their photon coupling vanishes. Their neutral-current interaction is a $Z$ interaction through $T^3P_L$.

## Relations to other pages

- [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/) defines the weak mixing rotation and the $Z$ boson.
- [Weak Charged Current](/gauge-theories-standard-model/electroweak/weak-charged-current/) gives the companion $W^\pm$ interaction and CKM structure.
- Fermi Theory Limit explains how both $W$ and $Z$ exchange become local four-fermion interactions at low momentum transfer.
- The later Flavor and Neutrinos chapter records the full fermion representation data and explains how flavor bases enter charged and neutral currents.
- The later Standard Model anomalies chapter explains why the chiral electroweak assignments are quantum-mechanically consistent.

## Research status

The tree-level neutral-current structure is established and has been tested in neutrino scattering, parity-violating electron scattering, $Z$-pole observables, atomic parity violation, and many precision electroweak measurements.

Active work concerns precision: defining and extracting effective weak mixing angles, computing radiative corrections, combining neutral-current observables in global electroweak fits, and interpreting possible deviations using SMEFT or more specific extensions. This page gives the tree-level architecture; precision pages will add scheme dependence, loops, and experimental definitions.

## Exercises

### Exercise 1: Derive the photon coupling

Starting from

$$
-gW_\mu^3T^3-g'B_\mu Y,
$$

use

$$
W_\mu^3=s_WA_\mu+c_WZ_\mu,
\qquad
B_\mu=c_WA_\mu-s_WZ_\mu,
$$

and $e=gs_W=g'c_W$ to show that the $A_\mu$ coupling is $-eA_\mu Q$.

<details><summary><strong>Solution</strong></summary>

The $A_\mu$ coefficient is

$$
-gs_WT^3-g'c_WY.
$$

Using $gs_W=g'c_W=e$, this becomes

$$
-eT^3-eY=-e(T^3+Y)=-eQ.
$$

</details>

### Exercise 2: Convert chiral couplings to vector and axial couplings

Given

$$
g_L^f=T_f^3-s_W^2Q_f,
\qquad
g_R^f=-s_W^2Q_f,
$$

show that

$$
g_V^f=g_L^f+g_R^f=T_f^3-2Q_fs_W^2,
\qquad
g_A^f=g_L^f-g_R^f=T_f^3.
$$

<details><summary><strong>Solution</strong></summary>

Add and subtract the left and right couplings:

$$
g_L^f+g_R^f=(T_f^3-s_W^2Q_f)-s_W^2Q_f=T_f^3-2Q_fs_W^2,
$$

and

$$
g_L^f-g_R^f=(T_f^3-s_W^2Q_f)+s_W^2Q_f=T_f^3.
$$

</details>

### Exercise 3: No tree-level flavor-changing neutral currents

Let $f'_L=U_Lf_L$ with $U_L$ unitary. Show that $\bar f'_L\gamma^\mu f'_L=\bar f_L\gamma^\mu f_L$.

<details><summary><strong>Solution</strong></summary>

Using $f'_L=U_Lf_L$ and $\bar f'_L=\bar f_LU_L^\dagger$, one finds

$$
\bar f'_L\gamma^\mu f'_L
=
\bar f_LU_L^\dagger\gamma^\mu U_Lf_L.
$$

The matrix $U_L$ acts in generation space, while $\gamma^\mu$ acts on spinor indices, so they commute. Since $U_L^\dagger U_L=1$,

$$
\bar f'_L\gamma^\mu f'_L
=
\bar f_L\gamma^\mu f_L.
$$

This is the algebraic reason neutral currents remain flavor diagonal at tree level.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§87–90, for the Standard Model gauge and Higgs sector, lepton sector, quark sector, and electroweak interactions.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 29 and 31, for weak interactions and precision electroweak tests.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak gauge theory and neutral-current structure.
- Georgi, *Weak Interactions and Modern Particle Theory*, for a concise physical account of weak neutral currents and electroweak unification.

## Version history

- **2026-06-18:** Initial polished draft. Added the neutral-current derivation, vector–axial coupling table, flavor-diagonal argument, and neutral-current map figure.
