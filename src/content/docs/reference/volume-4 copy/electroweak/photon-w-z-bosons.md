---
title: "Photon, W, and Z Bosons"
description: "Defines the physical electroweak gauge bosons after symmetry breaking, derives their masses and couplings, and explains the weak mixing angle."
sidebar:
  label: "Photon, W, and Z Bosons"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–90; Schwartz Ch. 29; Weinberg Vol. II electroweak chapters."
topics:
  - photon
  - W boson
  - Z boson
  - weak mixing angle
  - electroweak currents
canonicalTopics:
  - photon-z-mixing
  - w-bosons
  - z-boson
  - weak-mixing-angle
  - electroweak-current-couplings
researchStatus:
  established:
    - "The physical electroweak gauge bosons are the charged W± fields, the massive neutral Z field, and the massless photon associated with unbroken U(1)em."
  active:
    - "Precision determinations of electroweak masses, widths, weak mixing parameters, and gauge-boson self-couplings remain central tests of the Standard Model and its effective extensions."
---

## Summary

After electroweak symmetry breaking, the four gauge-basis fields

$$
W_\mu^1,
\quad
W_\mu^2,
\quad
W_\mu^3,
\quad
B_\mu
$$

are more usefully described by

$$
W_\mu^+,
\quad
W_\mu^-,
\quad
Z_\mu,
\quad
A_\mu.
$$

The charged fields are

$$
W_\mu^\pm
=
\frac{1}{\sqrt2}(W_\mu^1\mp iW_\mu^2),
$$

and the neutral fields are

$$
A_\mu=s_WW_\mu^3+c_WB_\mu,
\qquad
Z_\mu=c_WW_\mu^3-s_WB_\mu.
$$

Here

$$
s_W=\sin\theta_W,
\qquad
c_W=\cos\theta_W,
\qquad
\tan\theta_W=\frac{g'}{g}.
$$

The photon $A_\mu$ is the gauge boson of the unbroken electromagnetic generator

$$
Q=T^3+Y,
$$

and remains massless. The $W^\pm$ and $Z$ bosons are massive:

$$
m_W=\frac{gv}{2},
\qquad
m_Z=\frac{v}{2}\sqrt{g^2+g'^2}=\frac{m_W}{c_W},
\qquad
m_A=0.
$$

<figure class="doc-figure" style="--figure-width: 44rem;">

![Photon, W, and Z boson map](/figures/gauge-theories-standard-model/photon-w-z-bosons-map.svg)

<figcaption>

The physical electroweak boson basis. $W^1$ and $W^2$ combine into charged $W^\pm$ bosons, while $W^3$ and $B$ rotate into the massless photon $A$ and the massive $Z$. The same weak mixing angle gives $e=gs_W=g'c_W$ and the neutral-current coupling $T^3-s_W^2Q$.

</figcaption>
</figure>

This page is mostly a translation dictionary. It tells you how to move from the gauge basis, which makes the symmetry simple, to the physical basis, which makes masses and low-energy interactions simple.

## Prerequisites

You should know [Electroweak Symmetry Breaking](/gauge-theories-standard-model/electroweak/electroweak-symmetry-breaking/), especially the mass terms

$$
\frac{g^2v^2}{4}W_\mu^+W^{-\mu}
+\frac{v^2}{8}(gW_\mu^3-g'B_\mu)^2.
$$

You should also know the [Electroweak Covariant Derivative](/gauge-theories-standard-model/electroweak/electroweak-covariant-derivative/) and the convention

$$
D_\mu=\partial_\mu+igW_\mu^aT^a+ig'YB_\mu.
$$

For the later pages on weak currents, it is helpful to remember that $SU(2)_L$ acts on left-handed fermion doublets but not on right-handed singlets in the minimal Standard Model.

## Core idea

The electroweak gauge basis is adapted to the unbroken Lagrangian:

$$
SU(2)_L\times U(1)_Y.
$$

The physical basis is adapted to the Higgs vacuum:

$$
SU(2)_L\times U(1)_Y
\longrightarrow
U(1)_{\rm em}.
$$

The two bases answer different questions.

| Question | Natural basis | Why |
|---|---|---|
| What is the gauge group before the Higgs vacuum? | $W^1,W^2,W^3,B$ | These are the gauge fields for $SU(2)_L$ and $U(1)_Y$. |
| Which bosons have definite electric charge? | $W^+,W^-,A,Z$ | The Higgs vacuum leaves $Q=T^3+Y$ unbroken. |
| Which bosons have definite tree-level mass? | $W^+,W^-,Z,A$ | The Higgs kinetic term is diagonal in this basis. |
| Which field mediates electromagnetism? | $A$ | It couples to $eQ$ and is massless. |
| Which field mediates the neutral weak interaction? | $Z$ | It couples to $T^3-s_W^2Q$. |

The main lesson is that electroweak mixing is not an optional convention. It is forced by having two neutral gauge fields, one neutral Higgs vacuum, and one unbroken electromagnetic generator.

## Setup and conventions

The charged weak fields are defined by

$$
W_\mu^\pm
=
\frac{1}{\sqrt2}(W_\mu^1\mp iW_\mu^2).
$$

The inverse relations are

$$
W_\mu^1=\frac{1}{\sqrt2}(W_\mu^++W_\mu^-),
\qquad
W_\mu^2=\frac{i}{\sqrt2}(W_\mu^+-W_\mu^-).
$$

The weak ladder generators are

$$
T^+=T^1+iT^2,
\qquad
T^-=T^1-iT^2.
$$

With these definitions,

$$
W_\mu^1T^1+W_\mu^2T^2
=
\frac{1}{\sqrt2}
\left(W_\mu^+T^+ + W_\mu^-T^-\right).
$$

The neutral fields are defined by the orthogonal rotation

$$
\binom{A_\mu}{Z_\mu}
=
\begin{pmatrix}
s_W&c_W\\
c_W&-s_W
\end{pmatrix}
\binom{W_\mu^3}{B_\mu}.
$$

Equivalently,

$$
A_\mu=s_WW_\mu^3+c_WB_\mu,
\qquad
Z_\mu=c_WW_\mu^3-s_WB_\mu.
$$

The same matrix is its own inverse, so

$$
W_\mu^3=s_WA_\mu+c_WZ_\mu,
\qquad
B_\mu=c_WA_\mu-s_WZ_\mu.
$$

The angle is fixed by

$$
\tan\theta_W=\frac{g'}{g},
$$

so

$$
s_W=\frac{g'}{\sqrt{g^2+g'^2}},
\qquad
c_W=\frac{g}{\sqrt{g^2+g'^2}}.
$$

Finally,

$$
e=gs_W=g'c_W
=
\frac{gg'}{\sqrt{g^2+g'^2}}.
$$

This is the electric charge coupling in the convention $Q=T^3+Y$.

## Charged bosons

The fields $W^+$ and $W^-$ are complex conjugate charged vector fields. They are not two unrelated real gauge fields; together they encode the two real fields $W^1$ and $W^2$.

Their tree-level mass is

$$
m_W=\frac{gv}{2}.
$$

The charged-current part of the covariant derivative is

$$
D_\mu\supset
\frac{ig}{\sqrt2}
\left(W_\mu^+T^+ + W_\mu^-T^-\right).
$$

For a left-handed doublet

$$
\Psi_L=\binom{\psi_{+L}}{\psi_{-L}},
$$

the currents are schematically

$$
J_+^\mu=\bar\psi_{+L}\gamma^\mu\psi_{-L},
\qquad
J_-^\mu=\bar\psi_{-L}\gamma^\mu\psi_{+L}.
$$

Because the fermion kinetic term is $\bar\Psi i\gamma^\mu D_\mu\Psi$, our $D_\mu=\partial_\mu+i(\text{connection})$ convention gives the interaction sign

$$
\mathcal L_{W}
=
-\frac{g}{\sqrt2}
\left(W_\mu^+J_+^\mu+W_\mu^-J_-^\mu\right).
$$

For leptons,

$$
\binom{\nu_{\ell L}}{\ell_L},
$$

this includes

$$
J_+^\mu=\bar\nu_{\ell L}\gamma^\mu\ell_L,
\qquad
J_-^\mu=\bar\ell_L\gamma^\mu\nu_{\ell L}.
$$

For quarks, the same expression appears in the weak-interaction basis; after diagonalizing quark masses, the charged current contains the CKM matrix. That belongs in the Flavor and Neutrinos chapter, but the origin is already visible here: $W^\pm$ couple through the weak ladder generators.

### Electric charge of W bosons

The $W^\pm$ bosons carry electric charge because they are associated with the generators $T^\pm$, which change $T^3$. A quick algebraic way to see this is

$$
[Q,T^\pm]=[T^3+Y,T^\pm]=[T^3,T^\pm]=\pm T^\pm,
$$

since $Y$ commutes with $SU(2)_L$. The gauge boson multiplying $T^+$ carries charge $+1$, and the one multiplying $T^-$ carries charge $-1$.

Thus $W^+$ can mediate transitions such as

$$
e^-\longrightarrow \nu_e
$$

at the current vertex, while $W^-$ mediates the conjugate transition. More invariantly, the full interaction conserves electric charge at every vertex.

## Neutral bosons

The neutral mass term is

$$
\frac{v^2}{8}(gW_\mu^3-g'B_\mu)^2.
$$

The massive neutral field is the combination proportional to $gW^3-g'B$:

$$
Z_\mu=c_WW_\mu^3-s_WB_\mu.
$$

The orthogonal field is the photon:

$$
A_\mu=s_WW_\mu^3+c_WB_\mu.
$$

The corresponding masses are

$$
m_Z=\frac{v}{2}\sqrt{g^2+g'^2},
\qquad
m_A=0.
$$

The masslessness of $A_\mu$ is not a numerical accident. It is protected by the unbroken gauge redundancy associated with $U(1)_{\rm em}$.

The neutral part of the covariant derivative becomes

$$
D_\mu\supset ieQA_\mu+i\frac{g}{c_W}(T^3-s_W^2Q)Z_\mu.
$$

Therefore the photon interaction is

$$
\mathcal L_A=-eA_\mu J_{\rm em}^\mu,
$$

where

$$
J_{\rm em}^\mu=\sum_f Q_f\bar f\gamma^\mu f
$$

after assembling the relevant chiral fields into Dirac fermions for the charged matter.

The $Z$ interaction is

$$
\mathcal L_Z=-\frac{g}{c_W}Z_\mu J_Z^\mu.
$$

For Standard Model fermions, a compact Dirac-field form is

$$
J_Z^\mu
=
\sum_f
\bar f\gamma^\mu
\left(T_f^3P_L-s_W^2Q_f\right)f,
$$

where

$$
P_L=\frac{1-\gamma^5}{2}.
$$

Here $T_f^3$ is the weak-isospin eigenvalue of the left-handed component of $f$. The right-handed charged fermions have $T^3=0$, but they still couple to the $Z$ through the $-s_W^2Q_f$ term.

This is why neutral weak interactions are chiral even though they do not change electric charge.

## Coupling table for one generation

For one generation of charged fermions and neutrinos in the minimal Standard Model, the $Z$ coupling factor inside

$$
\frac{g}{c_W}(T^3P_L-s_W^2Q)
$$

is as follows.

| Fermion | $Q$ | Left-handed $T^3$ | $Z$ factor on left-handed part | $Z$ factor on right-handed part |
|---|---:|---:|---:|---:|
| $\nu$ | $0$ | $+1/2$ | $+1/2$ | absent in the minimal model |
| $e$ | $-1$ | $-1/2$ | $-1/2+s_W^2$ | $s_W^2$ |
| $u$ | $+2/3$ | $+1/2$ | $+1/2-\frac23s_W^2$ | $-\frac23s_W^2$ |
| $d$ | $-1/3$ | $-1/2$ | $-1/2+\frac13s_W^2$ | $+\frac13s_W^2$ |

The table is not a list of new assumptions. It is obtained by applying the single formula $T^3-s_W^2Q$ to the left-handed fields and $-s_W^2Q$ to the right-handed weak singlets.

## Polarizations and longitudinal modes

A massless spin-one gauge boson has two physical transverse polarizations. A massive spin-one particle has three physical polarizations. Therefore

$$
A_\mu:\ 2\text{ physical polarizations},
\qquad
W_\mu^\pm,Z_\mu:\ 3\text{ physical polarizations each}.
$$

The longitudinal polarizations of $W^\pm$ and $Z$ come from the three would-be Goldstone modes in the Higgs doublet. This is not just bookkeeping. At high energies, scattering amplitudes involving longitudinal weak bosons are closely related to amplitudes involving the corresponding Goldstone fields. That statement is the Goldstone equivalence theorem, treated later in the Higgs Sector chapter.

The Higgs boson $h$ is the remaining radial scalar excitation. Its interactions with $W$ and $Z$ follow by expanding

$$
(D_\mu H)^\dagger(D^\mu H)
$$

around

$$
H=\frac1{\sqrt2}\binom{0}{v+h}
$$

in unitary gauge. For example, replacing $v^2$ by $(v+h)^2$ in the mass terms immediately shows that Higgs couplings to weak bosons are tied to the same parameters that generate their masses.

## Gauge-boson self-interactions

Even after electroweak symmetry breaking, the non-Abelian origin of $SU(2)_L$ remains visible. The kinetic term

$$
-\frac14W_{\mu\nu}^aW^{a\mu\nu}
$$

contains triple and quartic self-interactions among the weak gauge fields. When rewritten in the physical basis, these include interactions such as

$$
A W^+W^- ,
\qquad
Z W^+W^- ,
\qquad
A A W^+W^- ,
\qquad
A Z W^+W^- ,
\qquad
Z Z W^+W^- ,
\qquad
W^+W^-W^+W^-.
$$

Their coefficients are fixed by $g$, $g'$, and the weak mixing angle. The photon coupling to $W^\pm$ is required because the $W$ bosons are electrically charged. The detailed Feynman rules belong to calculation-library and perturbative-gauge-theory pages, but the conceptual origin is already clear: the physical $W$ and $Z$ bosons are reorganized non-Abelian gauge fields, not arbitrary massive vector particles.

## Tree-level relations and what they mean

At tree level in the minimal Standard Model,

$$
m_W=\frac{gv}{2},
\qquad
m_Z=\frac{gv}{2c_W},
\qquad
m_A=0,
\qquad
e=gs_W.
$$

It is tempting to treat these as definitions. A better interpretation is:

$$
\text{one Higgs doublet + electroweak gauge invariance}
\quad\Longrightarrow\quad
\text{these tree-level relations}.
$$

Quantum corrections require specifying a renormalization scheme and a set of input observables. In precision electroweak physics, different definitions of the weak mixing angle are useful in different contexts. The tree-level angle $\theta_W$ on this page is the clean starting point, not the final word on precision fits.

The robust qualitative facts are:

- the photon is massless because $U(1)_{\rm em}$ remains unbroken;
- $W^\pm$ are electrically charged massive vector bosons;
- $Z$ is a neutral massive vector boson;
- electromagnetic couplings are proportional to $Q$;
- neutral weak couplings involve $T^3-s_W^2Q$;
- charged weak couplings act through $T^\pm$ and therefore only on weak doublets.

## Common pitfalls

**Using the wrong sign in the neutral rotation.** This chapter uses

$$
A=s_WW^3+c_WB,
\qquad
Z=c_WW^3-s_WB.
$$

With this choice and $D_\mu=\partial_\mu+igW^aT^a+ig'YB$, the neutral derivative becomes $ieQA+i\frac{g}{c_W}(T^3-s_W^2Q)Z$. A different sign convention for $D_\mu$ or for $Z$ changes intermediate signs but not observables.

**Forgetting that $W^\pm$ are charged.** They are made from neutral-looking real fields $W^1$ and $W^2$, but after symmetry breaking the unbroken charge generator acts nontrivially on them.

**Calling $Z$ a heavy photon.** The $Z$ is neutral, but its coupling is not proportional to electric charge. It couples to $T^3-s_W^2Q$ and therefore distinguishes left-handed weak doublet structure.

**Treating right-handed fermions as completely weak-neutral.** Right-handed charged fermions are $SU(2)_L$ singlets, so they do not couple to $W^\pm$ or to the $T^3$ part of the $Z$. They still carry hypercharge and electric charge, so they couple to $B$ before symmetry breaking and to $A$ and $Z$ after symmetry breaking.

**Confusing field names with measured particles before gauge fixing.** In a gauge-fixed perturbative treatment, $W^\pm$, $Z$, and $A$ are excellent particle variables. A fully gauge-invariant formulation phrases the physical content through gauge-invariant operators and observables. The two descriptions agree for physical predictions.

**Reading tree-level formulas as precision numerical definitions.** The weak mixing angle and masses receive quantum corrections. Precision pages must specify the renormalization scheme and input parameters.

## Relations to other pages

[Electroweak Symmetry Breaking](/gauge-theories-standard-model/electroweak/electroweak-symmetry-breaking/) derives the mass matrix and the unbroken electromagnetic generator. This page packages that result into the physical boson basis.

The next two pages, Weak Charged Current and Weak Neutral Current, use the interaction formulas here to study weak processes. The Fermi Theory Limit page then integrates out the $W$ boson at momenta much smaller than $m_W$.

The Higgs Sector chapter derives the Higgs couplings to $W$ and $Z$ more systematically and explains the Goldstone equivalence theorem. The Standard Model Architecture chapter later assembles these bosons with quarks, leptons, color, Yukawa couplings, and anomaly cancellation into the full theory.

## Research status

The definitions and tree-level relations on this page are established parts of the Standard Model. They are the starting point for electroweak precision calculations, collider predictions, and low-energy weak-interaction matching.

Active work lives around the edges: precision determinations of electroweak input parameters, higher-order corrections, possible SMEFT deformations of gauge-boson couplings, searches for anomalous triple and quartic gauge couplings, and tests of whether the minimal Higgs doublet is the whole story.

## Exercises

### Exercise 1: Diagonalize the neutral fields

Show that the field

$$
A_\mu=s_WW_\mu^3+c_WB_\mu
$$

is the massless direction of the neutral mass term

$$
\frac{v^2}{8}(gW_\mu^3-g'B_\mu)^2.
$$

<details><summary><strong>Solution</strong></summary>

A massless direction is a pair $(W^3,B)$ for which

$$
gW^3-g'B=0.
$$

The field $A$ corresponds to the direction

$$
(W^3,B)=(s_W,c_W).
$$

Then

$$
gs_W-g'c_W=0
$$

because

$$
gs_W=g'c_W=e.
$$

Thus the $A$ combination does not appear in the neutral mass term.

</details>

### Exercise 2: Derive the Z coupling

Starting from

$$
igW_\mu^3T^3+ig'B_\mu Y,
$$

use

$$
W_\mu^3=s_WA_\mu+c_WZ_\mu,
\qquad
B_\mu=c_WA_\mu-s_WZ_\mu,
$$

to show that the coefficient of $Z_\mu$ is

$$
i\frac{g}{c_W}(T^3-s_W^2Q).
$$

<details><summary><strong>Solution</strong></summary>

The $Z$ coefficient is

$$
igc_WT^3-ig's_WY.
$$

Using $g'=gs_W/c_W$, this becomes

$$
igc_WT^3-i\frac{gs_W^2}{c_W}Y
=
i\frac{g}{c_W}\left(c_W^2T^3-s_W^2Y\right).
$$

Since $c_W^2=1-s_W^2$,

$$
c_W^2T^3-s_W^2Y
=T^3-s_W^2(T^3+Y)
=T^3-s_W^2Q.
$$

Therefore

$$
igc_WT^3-ig's_WY
=
i\frac{g}{c_W}(T^3-s_W^2Q).
$$

</details>

### Exercise 3: Z couplings for the electron

For the electron, $Q=-1$. The left-handed electron has $T^3=-1/2$, while the right-handed electron has $T^3=0$. Find the two chiral $Z$ coupling factors.

<details><summary><strong>Solution</strong></summary>

The factor multiplying $g/c_W$ is

$$
T^3-s_W^2Q.
$$

For $e_L$,

$$
T^3-s_W^2Q
=-\frac12-s_W^2(-1)
=-\frac12+s_W^2.
$$

For $e_R$,

$$
T^3-s_W^2Q
=0-s_W^2(-1)
=s_W^2.
$$

Thus the $Z$ couples differently to the two chiralities. This is the neutral-current imprint of the chiral electroweak gauge structure.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§87–90, for the Standard Model gauge and Higgs sector, lepton sector, quark sector, and electroweak interactions of hadrons.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 29, for weak interactions, electroweak symmetry breaking, gauge-boson masses, charged currents, and neutral currents.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak interactions and spontaneously broken gauge theories.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for the conceptual origin of massive vector bosons in gauge theories with hidden symmetry.

## Version history

- **2026-06-18:** Initial polished draft. Defined the physical $A$, $W^\pm$, and $Z$ bosons, derived their tree-level masses, and organized their charged and neutral current couplings in the volume convention.
