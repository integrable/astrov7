---
title: "Standard Model Lagrangian"
description: "Assembles the minimal renormalizable Standard Model Lagrangian in the Q = T3 + Y convention, including gauge, fermion, Higgs, Yukawa, theta, gauge-fixing, and ghost pieces."
sidebar:
  label: "Standard Model Lagrangian"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–91; Schwartz Chs. 29–31; Burgess Ch. 9; Weinberg Vol. II electroweak and Standard Model material."
topics:
  - Standard Model Lagrangian
  - gauge kinetic terms
  - Higgs sector
  - Yukawa couplings
  - theta angle
  - gauge fixing
canonicalTopics:
  - standard-model-lagrangian
  - standard-model-gauge-sector
  - standard-model-higgs-sector
  - standard-model-yukawa-sector
  - qcd-theta-angle
researchStatus:
  established:
    - "The minimal renormalizable Standard Model Lagrangian is the established local quantum field theory of known nongravitational particle interactions, before adding neutrino-mass operators or other higher-dimensional terms."
  active:
    - "The minimal Lagrangian leaves its numerical parameters unexplained and is naturally interpreted as the leading part of a larger effective theory."
---

## Summary

The minimal renormalizable Standard Model is the most compact way to write the known strong, weak, and electromagnetic interactions as one local quantum field theory. In the convention used throughout this volume,

$$
Q=T^3+Y,
$$

and the gauge algebra is

$$
\mathfrak g_{\rm SM}
=
\mathfrak{su}(3)_c\oplus\mathfrak{su}(2)_L\oplus\mathfrak u(1)_Y.
$$

The gauge-invariant classical core is

$$
\mathcal L_{\rm SM}^{\rm min}
=
\mathcal L_{\rm gauge}
+
\mathcal L_{\rm fermion}
+
\mathcal L_H
+
\mathcal L_Y
+
\mathcal L_\theta.
$$

For perturbation theory one adds gauge-fixing and ghost terms,

$$
\mathcal L_{\rm pert}
=
\mathcal L_{\rm SM}^{\rm min}
+
\mathcal L_{\rm gf}
+
\mathcal L_{\rm gh}.
$$

The gauge-fixing and ghost terms are not new physical interactions. They are the bookkeeping needed to quantize a redundant description.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Standard Model Lagrangian pieces](/figures/gauge-theories-standard-model/standard-model-lagrangian-pieces.svg)

<figcaption>

The Standard Model Lagrangian is a small number of allowed pieces, filtered by gauge invariance, Lorentz invariance, locality, and operator dimension. The Higgs and Yukawa sectors turn the gauge-basis theory into the observed mass-basis theory after electroweak symmetry breaking.

</figcaption>
</figure>

This page writes the pieces in one convention-consistent form. It is not a table of measured numerical values. The point is the architecture: which terms exist, which terms are forbidden, and which constants remain free.

## Prerequisites

You should know the [Standard Model Gauge Group](/gauge-theories-standard-model/standard-model/standard-model-gauge-group/), [Global Form of the Standard Model Gauge Group](/gauge-theories-standard-model/standard-model/global-form-of-standard-model-gauge-group/), and [Standard Model Field Content](/gauge-theories-standard-model/standard-model/standard-model-field-content/). You should also know the Higgs and flavor conventions from [Standard Model Higgs Doublet](/gauge-theories-standard-model/higgs-sector/standard-model-higgs-doublet/) and [Yukawa Couplings](/gauge-theories-standard-model/flavor-neutrinos/yukawa-couplings/).

We use mostly-minus metric, Hermitian gauge generators, and

$$
D_\mu
=
\partial_\mu
+ig_sG_\mu^AT_c^A
+igW_\mu^IT_L^I
+ig'YB_\mu.
$$

For non-Abelian field strengths this convention gives

$$
F^a_{\mu\nu}
=
\partial_\mu A^a_\nu-
\partial_\nu A^a_\mu
-g f^{abc}A^b_\mu A^c_\nu.
$$

## The one-line form

With generation sums suppressed, the minimal renormalizable Standard Model Lagrangian is

$$
\begin{aligned}
\mathcal L_{\rm SM}^{\rm min}
={}&
-\frac14G^A_{\mu\nu}G^{A\mu\nu}
-\frac14W^I_{\mu\nu}W^{I\mu\nu}
-\frac14B_{\mu\nu}B^{\mu\nu}
\\
&+
\sum_{\rm generations}
\left(
\bar Q_L i\gamma^\mu D_\mu Q_L
+
\bar u_R i\gamma^\mu D_\mu u_R
+
\bar d_R i\gamma^\mu D_\mu d_R
+
\bar L_L i\gamma^\mu D_\mu L_L
+
\bar e_R i\gamma^\mu D_\mu e_R
\right)
\\
&+
(D_\mu H)^\dagger D^\mu H
-
V(H)
+
\mathcal L_Y
+
\mathcal L_\theta.
\end{aligned}
$$

The Higgs potential is

$$
V(H)=-\mu^2H^\dagger H+\lambda(H^\dagger H)^2,
\qquad
\lambda>0.
$$

The charged-fermion Yukawa sector is

$$
\mathcal L_Y
=
-
\bar Q_LY_dHd_R
-
\bar Q_LY_u\widetilde H u_R
-
\bar L_LY_eHe_R
+\mathrm{h.c.},
$$

where

$$
\widetilde H=i\sigma^2H^*.
$$

The matrices $Y_u,Y_d,Y_e$ act in generation space. Color and weak indices are contracted in the unique gauge-invariant way, as explained in the Yukawa page.

This is the formula to memorize. The rest of the page is the audit trail.

## Gauge sector

The gauge fields are

$$
G_\mu^A,
\qquad
W_\mu^I,
\qquad
B_\mu,
$$

for $SU(3)_c$, $SU(2)_L$, and $U(1)_Y$, respectively. The field strengths are

$$
G^A_{\mu\nu}
=
\partial_\mu G^A_\nu-
\partial_\nu G^A_\mu
-g_sf^{ABC}G^B_\mu G^C_\nu,
$$

$$
W^I_{\mu\nu}
=
\partial_\mu W^I_\nu-
\partial_\nu W^I_\mu
-g\epsilon^{IJK}W^J_\mu W^K_\nu,
$$

and

$$
B_{\mu\nu}=\partial_\mu B_\nu-\partial_\nu B_\mu.
$$

The gauge kinetic terms are

$$
\mathcal L_{\rm gauge}
=
-\frac14G^A_{\mu\nu}G^{A\mu\nu}
-\frac14W^I_{\mu\nu}W^{I\mu\nu}
-\frac14B_{\mu\nu}B^{\mu\nu}.
$$

The three gauge couplings $g_s,g,g'$ enter through $D_\mu$ and through the non-Abelian field strengths. In this normalization the kinetic terms have canonical coefficient $-1/4$, and the interaction strengths sit in the covariant derivative and commutator pieces.

The gauge sector alone has self-interactions for gluons and weak gauge bosons, but not for the hypercharge gauge boson. That difference is not a historical accident. It is the difference between non-Abelian and Abelian curvature.

## Fermion kinetic sector

For one generation the chiral fermion multiplets are

| Field | Representation under $SU(3)_c\times SU(2)_L$ | Hypercharge |
|---|---:|---:|
| $Q_L=(u_L,d_L)^T$ | $(\mathbf3,\mathbf2)$ | $+1/6$ |
| $u_R$ | $(\mathbf3,\mathbf1)$ | $+2/3$ |
| $d_R$ | $(\mathbf3,\mathbf1)$ | $-1/3$ |
| $L_L=(\nu_L,e_L)^T$ | $(\mathbf1,\mathbf2)$ | $-1/2$ |
| $e_R$ | $(\mathbf1,\mathbf1)$ | $-1$ |

The kinetic terms are

$$
\begin{aligned}
\mathcal L_{\rm fermion}
=
\sum_{i=1}^3
\big(
&\bar Q_{Li}i\gamma^\mu D_\mu Q_{Li}
+\bar u_{Ri}i\gamma^\mu D_\mu u_{Ri}
+\bar d_{Ri}i\gamma^\mu D_\mu d_{Ri}
\\
&+
\bar L_{Li}i\gamma^\mu D_\mu L_{Li}
+\bar e_{Ri}i\gamma^\mu D_\mu e_{Ri}
\big).
\end{aligned}
$$

The covariant derivative knows which representation it is acting on. For example,

$$
D_\mu Q_L
=
\left(\partial_\mu
+ig_sG_\mu^AT^A_{\mathbf3}
+igW_\mu^I\frac{\tau^I}{2}
+ig'\frac16B_\mu\right)Q_L,
$$

while

$$
D_\mu e_R
=
(\partial_\mu-ig'B_\mu)e_R.
$$

There is no direct fermion mass term in the gauge-basis Lagrangian. A term such as

$$
-m_e\bar e_Le_R+\mathrm{h.c.}
$$

is not invariant under $SU(2)_L\times U(1)_Y$, because $e_L$ lives inside the doublet $L_L$ while $e_R$ is a singlet. Charged-fermion masses must come from Yukawa couplings after the Higgs develops a vacuum expectation value.

## Higgs sector

The Higgs field is

$$
H=\begin{pmatrix}H^+\\H^0\end{pmatrix}
\sim(\mathbf1,\mathbf2)_{1/2}.
$$

Its gauge-invariant renormalizable Lagrangian is

$$
\mathcal L_H
=(D_\mu H)^\dagger D^\mu H
-
V(H),
$$

with

$$
V(H)=-\mu^2H^\dagger H+\lambda(H^\dagger H)^2.
$$

For $\mu^2>0$ and $\lambda>0$, the classical minimum satisfies

$$
H^\dagger H=\frac{v^2}{2},
\qquad
v^2=\frac{\mu^2}{\lambda}.
$$

A convenient unitary-gauge representative is

$$
H(x)=\frac{1}{\sqrt2}\begin{pmatrix}0\\v+h(x)\end{pmatrix}.
$$

Then the Higgs kinetic term produces the weak gauge-boson masses, and the Higgs potential gives

$$
m_h^2=2\lambda v^2.
$$

The Higgs field is doing several jobs at once: it breaks $SU(2)_L\times U(1)_Y$ to $U(1)_{\rm em}$, gives masses to $W^\pm$ and $Z$, leaves the photon massless, gives charged fermions masses through Yukawa couplings, and supplies the physical scalar excitation $h$.

## Yukawa sector

The Yukawa terms are

$$
\mathcal L_Y
=
-
\bar Q_{Li}^{\alpha a}(Y_d)_{ij}H_a d_{Rj}^{\alpha}
-
\bar Q_{Li}^{\alpha a}(Y_u)_{ij}\widetilde H_a u_{Rj}^{\alpha}
-
\bar L_{Li}^{a}(Y_e)_{ij}H_a e_{Rj}
+
\mathrm{h.c.}
$$

Here $i,j$ are generation indices, $\alpha$ is a color index, and $a$ is a weak index. The matrices $Y_u,Y_d,Y_e$ are arbitrary complex $3\times3$ matrices before choosing a flavor basis.

After electroweak symmetry breaking,

$$
\widetilde H
\to
\frac1{\sqrt2}\begin{pmatrix}v+h\\0\end{pmatrix},
\qquad
H
\to
\frac1{\sqrt2}\begin{pmatrix}0\\v+h\end{pmatrix},
$$

so the mass matrices are

$$
M_u=\frac{v}{\sqrt2}Y_u,
\qquad
M_d=\frac{v}{\sqrt2}Y_d,
\qquad
M_e=\frac{v}{\sqrt2}Y_e.
$$

The same matrices that make masses also make Higgs–fermion couplings. This is why the Higgs coupling to a charged fermion is proportional to that fermion's mass in the minimal theory.

The minimal renormalizable Standard Model contains no neutrino mass term. Neutrino masses require either adding new fields, such as right-handed neutrinos, or adding a higher-dimensional operator such as the Weinberg operator.

## Topological terms

In four dimensions one can also write CP-odd topological densities. The QCD term is

$$
\mathcal L_{\theta,3}
=
\frac{\theta_3g_s^2}{32\pi^2}
G^A_{\mu\nu}\widetilde G^{A\mu\nu},
$$

where

$$
\widetilde G^{A\mu\nu}
=
\frac12\epsilon^{\mu\nu\rho\sigma}G^A_{\rho\sigma}.
$$

Because chiral quark rephasings shift both $\theta_3$ and the phases of the quark mass matrices, the physical strong-CP parameter is conventionally written as

$$
\bar\theta
=
\theta_3+\arg\det(M_uM_d),
$$

up to sign conventions for the anomaly and mass matrices. The convention-independent statement is that only the anomalous rephasing-invariant combination is physical.

Analogous $W\widetilde W$ and $B\widetilde B$ terms require more care. The electroweak theta angle is removable in the minimal theory using anomalous baryon-plus-lepton rotations, but it can become meaningful if one adds certain baryon- or lepton-number-violating interactions. The hypercharge term is usually a boundary/topological subtlety rather than a perturbative parameter. For the minimal Standard Model parameter count, the robust physical theta parameter is $\bar\theta_{\rm QCD}$.

## Gauge fixing and ghosts

The gauge-invariant Lagrangian is redundant. To define perturbation theory, we choose a gauge. Before electroweak symmetry breaking, a simple covariant gauge has

$$
\mathcal L_{\rm gf}
=
-
\frac{1}{2\xi_3}(\partial_\mu G^{A\mu})^2
-
\frac{1}{2\xi_2}(\partial_\mu W^{I\mu})^2
-
\frac{1}{2\xi_1}(\partial_\mu B^\mu)^2.
$$

The non-Abelian factors have Faddeev–Popov ghosts,

$$
\mathcal L_{\rm gh}
=
\bar c^A(-\partial^\mu D_\mu^{AB}[G])c^B
+
\bar\eta^I(-\partial^\mu D_\mu^{IJ}[W])\eta^J
+
\bar\zeta(-\partial^2)\zeta.
$$

The hypercharge ghost $\zeta$ decouples in this simple gauge, but it is often included to keep the bookkeeping uniform.

After electroweak symmetry breaking, practical calculations usually use $R_\xi$ gauges adapted to the massive $W^\pm$ and $Z$ bosons. Those gauges mix the gauge-fixing functions with the would-be Goldstone fields so that quadratic gauge–Goldstone mixing cancels. The S-matrix is independent of the gauge parameters when the calculation is done correctly.

## What is forbidden

The compact formula above is powerful partly because of what it does **not** contain.

There are no gauge-boson mass terms such as

$$
m_g^2G^A_\mu G^{A\mu},
\qquad
m_W^2W^I_\mu W^{I\mu},
\qquad
m_B^2B_\mu B^\mu,
$$

because they are not invariant under the full gauge symmetry. The $W$ and $Z$ masses arise from $(D_\mu H)^\dagger D^\mu H$ after the Higgs vacuum is chosen.

There are no direct charged-fermion mass terms because the left- and right-chiral fermions have different electroweak representations. Fermion masses arise from Yukawa terms.

There is no Majorana mass term for the active neutrinos using only the minimal field content and dimension-four operators. The operator

$$
\frac{c_{ij}}{\Lambda}(L_iH)(L_jH)+\mathrm{h.c.}
$$

is gauge invariant but has dimension five. It belongs to the effective theory beyond the minimal renormalizable Lagrangian.

There are no arbitrary four-fermion weak interactions at the fundamental dimension-four level. The Fermi theory appears after integrating out the $W$ boson at energies much smaller than $m_W$.

## Before and after electroweak symmetry breaking

Before electroweak symmetry breaking, the Lagrangian is most simply written in the gauge basis:

$$
G_\mu^A,
\qquad
W_\mu^I,
\qquad
B_\mu,
\qquad
Q_L,u_R,d_R,L_L,e_R,H.
$$

After choosing the Higgs vacuum and diagonalizing mass matrices, the fields reorganize into

$$
\text{gluons},\quad A_\mu,\quad W_\mu^\pm,\quad Z_\mu,\quad h,
$$

and the charged fermion mass eigenstates. The neutral gauge bosons are

$$
A_\mu=s_WW_\mu^3+c_WB_\mu,
\qquad
Z_\mu=c_WW_\mu^3-s_WB_\mu,
$$

with

$$
e=gs_W=g'c_W.
$$

The gauge symmetry is not “destroyed.” The redundancy remains; it is realized in a different set of variables. The unbroken physical gauge group is $SU(3)_c\times U(1)_{\rm em}$, and the massive vector bosons are consistent precisely because the full gauge-invariant Higgs theory is still present underneath.

## Common mistakes

**Writing the broken-basis theory as if it were fundamental.** The photon, $W^\pm$, $Z$, Higgs boson, charged fermion masses, and CKM matrix are physical and useful, but the shortest fundamental expression is the unbroken gauge-basis Lagrangian.

**Forgetting the Hermitian conjugate in the Yukawa sector.** The displayed Yukawa operators are not Hermitian by themselves. The $+\mathrm{h.c.}$ is part of the Lagrangian.

**Using $H$ instead of $\widetilde H$ in the up-type Yukawa term.** Hypercharge forces the up-type operator to use the conjugate doublet.

**Counting gauge-fixing terms as physical interactions.** Gauge fixing changes propagators and introduces ghosts, but physical gauge-invariant quantities do not depend on the gauge parameter.

**Adding neutrino masses without saying how.** Neutrino masses are real physics, but they are not present in the minimal renormalizable Standard Model. They require an EFT operator or new fields.

## Exercises

### Exercise 1: Check an up-type Yukawa hypercharge

Using $Y(Q_L)=1/6$, $Y(u_R)=2/3$, and $Y(\widetilde H)=-1/2$, show that $\bar Q_L\widetilde H u_R$ is hypercharge neutral.

<details><summary><strong>Solution</strong></summary>

The conjugate field $\bar Q_L$ has hypercharge $-1/6$. Therefore

$$
Y(\bar Q_L\widetilde H u_R)
=
-
\frac16-
\frac12+
\frac23
=0.
$$

Thus the operator is neutral under $U(1)_Y$. The weak indices are contracted between the anti-doublet from $\bar Q_L$ and the doublet $\widetilde H$, and the color indices are contracted between $\bar Q_L$ and $u_R$.

</details>

### Exercise 2: Higgs vacuum and Higgs mass

For

$$
V(H)=-\mu^2H^\dagger H+\lambda(H^\dagger H)^2,
$$

with $\mu^2>0$ and $\lambda>0$, show that $v^2=\mu^2/\lambda$ and $m_h^2=2\lambda v^2$.

<details><summary><strong>Solution</strong></summary>

Let $r=H^\dagger H$. Then

$$
V(r)=-\mu^2r+\lambda r^2.
$$

The minimum satisfies

$$
\frac{dV}{dr}=-\mu^2+2\lambda r=0,
$$

so

$$
r=\frac{\mu^2}{2\lambda}.
$$

In the vacuum $H^\dagger H=v^2/2$, hence

$$
v^2=\frac{\mu^2}{\lambda}.
$$

Writing $H=(0,(v+h)/\sqrt2)^T$ gives

$$
V(h)=\text{constant}+\lambda v^2h^2+\cdots.
$$

Since the Lagrangian contains $-V$ and the mass term is $-\frac12m_h^2h^2$, we get

$$
m_h^2=2\lambda v^2.
$$

</details>

### Exercise 3: Why a bare electron mass is forbidden

Show that $\bar L_Le_R$ is not gauge invariant before electroweak symmetry breaking.

<details><summary><strong>Solution</strong></summary>

The field $L_L$ is an $SU(2)_L$ doublet with $Y=-1/2$, so $\bar L_L$ is an anti-doublet with $Y=+1/2$. The field $e_R$ is an $SU(2)_L$ singlet with $Y=-1$. Thus

$$
Y(\bar L_Le_R)=\frac12-1=-\frac12,
$$

and the operator still transforms as an anti-doublet under $SU(2)_L$. It is not a gauge singlet. Multiplying by $H\sim(\mathbf1,\mathbf2)_{1/2}$ gives the invariant operator $\bar L_LHe_R$.

</details>

## Relations to other pages

- [Standard Model Field Content](/gauge-theories-standard-model/standard-model/standard-model-field-content/) gives the representation table used in this formula.
- [Yukawa Couplings](/gauge-theories-standard-model/flavor-neutrinos/yukawa-couplings/) derives the gauge-invariant Yukawa operators in detail.
- [Gauge-Boson Masses](/gauge-theories-standard-model/higgs-sector/gauge-boson-masses/) derives the $W$ and $Z$ masses from the Higgs kinetic term.
- [Fermi Theory Limit](/gauge-theories-standard-model/electroweak/fermi-theory-limit/) shows how the four-fermion weak interaction emerges by integrating out $W$ exchange.
- [Parameter Counting](/gauge-theories-standard-model/standard-model/parameter-counting/) explains how many constants in this Lagrangian are physically independent.

## Research status

The minimal renormalizable Standard Model Lagrangian is established as the correct low-energy QFT structure for known nongravitational particle interactions over a vast range of experiments. The theory is not, however, a final explanation of its own inputs. It does not explain the number of generations, the Yukawa hierarchy, the smallness of neutrino masses, dark matter, baryogenesis, quantum gravity, or the electroweak hierarchy. Modern usage therefore treats this Lagrangian both as a successful renormalizable QFT and as the leading piece of a broader effective field theory.

## Where to go next

Continue to [Parameter Counting](/gauge-theories-standard-model/standard-model/parameter-counting/), which explains how many independent physical constants remain after field redefinitions. Then go to [Accidental Symmetries](/gauge-theories-standard-model/standard-model/accidental-symmetries/) and the Anomalies and Consistency chapter.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the Standard Model gauge/Higgs, lepton, quark, and neutrino-mass sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the Yang–Mills, weak-interaction, anomaly, and precision-test chapters.
- Burgess, *Introduction to Effective Field Theory*, especially the chapter on the Standard Model as an effective theory.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the electroweak theory and Standard Model structure.
- Coleman, *Aspects of Symmetry*, especially “Secret Symmetry” for the Higgs-mechanism logic behind the broken-basis theory.

## Version history

- **2026-06-19:** Initial page assembling the minimal Standard Model Lagrangian, topological term caveats, and gauge-fixing/ghost additions.
