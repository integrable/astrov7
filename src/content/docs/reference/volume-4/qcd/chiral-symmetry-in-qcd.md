---
title: "Chiral Symmetry in QCD"
description: "Explains the approximate left-right flavor symmetry of light-quark QCD, its currents, explicit mass breaking, and the axial singlet anomaly."
sidebar:
  label: "Chiral Symmetry in QCD"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki §§75–76 and §83; Schwartz Chs. 28–30 and 32; Coleman, Aspects of Symmetry, Chs. 2 and 5; Weinberg Vol. II Chs. 19–22."
topics:
  - QCD chiral symmetry
  - light quarks
  - flavor symmetry
  - axial currents
  - Ward identities
  - axial anomaly
canonicalTopics:
  - qcd-chiral-symmetry
  - flavor-symmetry
  - axial-current
  - ward-identity
  - axial-anomaly
researchStatus:
  established:
    - "The approximate chiral flavor symmetry of light-quark QCD and its explicit breaking by quark masses and the axial singlet anomaly are standard structural facts of QCD."
  active:
    - "Precise nonperturbative realization of chiral symmetry across finite temperature, finite density, and many-flavor gauge theories remains an active research area."
---

## Summary

QCD has more symmetry when some quark masses are neglected. Split the light quark fields into left- and right-handed parts,

$$
q_L=P_Lq,
\qquad
q_R=P_Rq,
\qquad
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2}.
$$

For $n_f$ massless quarks, the quark kinetic term separates into

$$
\bar q_L i\gamma^\mu D_\mu q_L
+
\bar q_R i\gamma^\mu D_\mu q_R.
$$

Because the QCD covariant derivative acts on color and spacetime but not on flavor, the massless light-quark theory is invariant under independent flavor rotations

$$
q_L\mapsto Lq_L,
\qquad
q_R\mapsto Rq_R,
\qquad
L,R\in U(n_f).
$$

Ignoring discrete quotient subtleties, the classical symmetry is

$$
U(n_f)_L\times U(n_f)_R
\simeq
SU(n_f)_L\times SU(n_f)_R\times U(1)_V\times U(1)_A.
$$

The vector part contains flavor and baryon number. The nonsinglet axial part is the approximate chiral symmetry that explains pions and current algebra. The singlet axial part $U(1)_A$ is not a true quantum symmetry of QCD: it is broken by the anomaly.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Map of chiral symmetries in massless light-quark QCD, showing vector, axial, mass-breaking, and anomaly pieces.](/figures/gauge-theories-standard-model/qcd-chiral-symmetry-map.svg)

<figcaption>

Chiral symmetry is the independent flavor rotation of left- and right-handed light quarks. Quark masses explicitly couple $q_L$ to $q_R$, while the quantum anomaly removes the singlet axial $U(1)_A$ symmetry. The robust approximate symmetry used in low-energy QCD is the nonsinglet $SU(n_f)_L\times SU(n_f)_R$ symmetry of light flavors.

</figcaption>
</figure>

## Prerequisites

You should know [QCD Lagrangian](/gauge-theories-standard-model/qcd/qcd-lagrangian/), [Color SU(3)](/gauge-theories-standard-model/qcd/color-su3/), [Quarks and Gluons](/gauge-theories-standard-model/qcd/quarks-and-gluons/), and [Running Alpha s](/gauge-theories-standard-model/qcd/running-alpha-s/). This page uses the QCD covariant derivative

$$
D_\mu q_f=(\partial_\mu+ig_sG_\mu^AT^A)q_f
$$

with $T^A$ acting on color. Flavor generators are denoted $t^a$ and normalized as

$$
\operatorname{tr}(t^at^b)=\frac12\delta^{ab}.
$$

We use

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3,
\qquad
\epsilon^{0123}=+1,
$$

and

$$
\widetilde G^{A\mu\nu}
=
\frac12\epsilon^{\mu\nu\rho\sigma}G^A_{\rho\sigma}.
$$

You should also know the basic distinction between global and gauge symmetry from [Global versus Gauge Symmetry](/gauge-theories-standard-model/gauge-principle/global-versus-gauge-symmetry/). Chiral flavor symmetry is a global symmetry, not a gauge redundancy.

## Core idea

QCD treats left-handed and right-handed massless quarks almost independently. This fact is easy to miss because Dirac notation hides it.

The quark part of the QCD Lagrangian is

$$
\mathcal L_q
=
\bar q(i\gamma^\mu D_\mu-M)q.
$$

Using $q=q_L+q_R$, the kinetic term becomes

$$
\bar q i\gamma^\mu D_\mu q
=
\bar q_L i\gamma^\mu D_\mu q_L
+
\bar q_R i\gamma^\mu D_\mu q_R.
$$

The mass term does the opposite:

$$
\mathcal L_m
=
-
\bar q_LMq_R
-
\bar q_RM^\dagger q_L.
$$

It couples left to right. Therefore chiral symmetry is exact only in the massless idealization $M=0$.

The physical importance is enormous. The $u$ and $d$ quark masses are small compared with the characteristic QCD scale; the $s$ quark is often light enough to be included with more caution. Thus real-world low-energy QCD has an approximate chiral symmetry. The symmetry is not manifest in the hadron spectrum in the naive way, because the vacuum spontaneously breaks it. That is the subject of the next page.

## Setup and conventions

Let

$$
q=
\begin{pmatrix}
q_1\\
\vdots\\
q_{n_f}
\end{pmatrix}
$$

collect $n_f$ quark flavors. Color and spinor indices are suppressed. Each $q_i$ is a color triplet Dirac field.

The light-quark QCD Lagrangian is

$$
\mathcal L_{\mathrm{light}}
=
-
\frac14G_{\mu\nu}^AG^{A\mu\nu}
+
\bar q_L i\gamma^\mu D_\mu q_L
+
\bar q_R i\gamma^\mu D_\mu q_R
-
\bar q_LMq_R
-
\bar q_RM^\dagger q_L.
$$

For ordinary QCD one often takes

$$
M=\operatorname{diag}(m_u,m_d,m_s,\ldots)
$$

for whichever flavors are being treated as light and dynamical at the scale of interest. When the quark masses are real and positive, this is just the usual Dirac mass term.

The left- and right-handed fields transform under flavor as

$$
q_L\mapsto Lq_L,
\qquad
q_R\mapsto Rq_R,
$$

where $L$ and $R$ are unitary matrices acting on flavor. Since $D_\mu$ contains color generators and not flavor generators, the kinetic terms are invariant under independent $L$ and $R$.

The mass matrix can be treated as a spurion. If one assigns

$$
M\mapsto LMR^\dagger,
$$

then the mass term is formally invariant. Holding $M$ fixed then tells us which part of the chiral symmetry is explicitly broken.

## The massless light-quark limit

Set $M=0$. Then

$$
\mathcal L_{\mathrm{light}}^{M=0}
=
-
\frac14G_{\mu\nu}^AG^{A\mu\nu}
+
\bar q_L i\gamma^\mu D_\mu q_L
+
\bar q_R i\gamma^\mu D_\mu q_R.
$$

The flavor symmetry is

$$
G_{\mathrm{cl}}=U(n_f)_L\times U(n_f)_R.
$$

The abbreviation “chiral symmetry” usually refers to the non-Abelian part

$$
SU(n_f)_L\times SU(n_f)_R.
$$

The word “chiral” here means that left-handed and right-handed fields transform differently. A vector rotation has $L=R$. An axial rotation has $L=R^\dagger$ for infinitesimal nonsinglet transformations.

For $n_f=2$, the most important approximate symmetry is

$$
SU(2)_L\times SU(2)_R,
$$

acting on the light doublet

$$
q=\begin{pmatrix}u\\d\end{pmatrix}.
$$

For $n_f=3$, one often considers

$$
SU(3)_L\times SU(3)_R,
$$

acting on

$$
q=\begin{pmatrix}u\\d\\s\end{pmatrix}.
$$

The three-flavor symmetry is less accurate because the strange quark is noticeably heavier than $u$ and $d$, but it is still a powerful organizing principle for the light pseudoscalar mesons.

## Decomposing the classical symmetry

Classically,

$$
U(n_f)_L\times U(n_f)_R
$$

can be organized as

$$
SU(n_f)_L\times SU(n_f)_R\times U(1)_V\times U(1)_A,
$$

up to discrete identifications.

The pieces have different physical meanings.

| Symmetry | Transformation | Meaning | Fate in QCD |
|---|---|---|---|
| $SU(n_f)_V$ | $q_L\mapsto Vq_L$, $q_R\mapsto Vq_R$ | Ordinary flavor rotations | Approximate; exact if included light masses are degenerate and electroweak effects are neglected. |
| $SU(n_f)_A$ | $q_L\mapsto Aq_L$, $q_R\mapsto A^\dagger q_R$ | Nonsinglet axial rotations | Exact in massless QCD, then spontaneously broken in the vacuum. |
| $U(1)_V$ | $q\mapsto e^{i\alpha}q$ | Quark number; baryon number after assigning $B=1/3$ per quark | Exact in QCD. |
| $U(1)_A$ | $q_L\mapsto e^{i\alpha}q_L$, $q_R\mapsto e^{-i\alpha}q_R$ | Singlet axial rotation | Broken by the quantum anomaly. |

The faithful global form has quotient subtleties involving centers and baryon number. Those subtleties matter for line operators, background gauge fields, and anomaly matching. For local current algebra and low-energy pion physics, the Lie algebra statement above is the right first-pass description.

## Currents and Ward identities

For each nonsinglet flavor generator $t^a$, define the vector and axial currents

$$
V^{a\mu}=\bar q\gamma^\mu t^a q,
\qquad
A^{a\mu}=\bar q\gamma^\mu\gamma^5 t^a q.
$$

Equivalently,

$$
V^{a\mu}
=
\bar q_L\gamma^\mu t^a q_L
+
\bar q_R\gamma^\mu t^a q_R,
$$

while

$$
A^{a\mu}
=
-
\bar q_L\gamma^\mu t^a q_L
+
\bar q_R\gamma^\mu t^a q_R,
$$

with the sign following from $\gamma^5q_L=-q_L$ and $\gamma^5q_R=q_R$.

In massless QCD, the nonsinglet currents obey

$$
\partial_\mu V^{a\mu}=0,
\qquad
\partial_\mu A^{a\mu}=0,
$$

as operator equations up to the usual contact terms in correlation functions. In a path integral, those contact terms encode the action of the charge on inserted fields. Schematically,

$$
\partial_\mu\langle J^{\mu a}(x)\,\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=
-i\sum_{k=1}^n\delta^{(4)}(x-x_k)
\langle\mathcal O_1\cdots (t^a\mathcal O_k)\cdots\mathcal O_n\rangle.
$$

The exact sign and factor of $i$ depend on whether one writes the Ward identity in Lorentzian or Euclidean conventions. The structural point is invariant: a conserved current generates a symmetry action on operator insertions.

## What quark masses do

The mass term

$$
\mathcal L_m
=
-
\bar q_LMq_R
-
\bar q_RM^\dagger q_L
$$

breaks chiral symmetry explicitly because it ties left-handed and right-handed flavor indices together.

For real diagonal $M$, the vector and axial divergences are

$$
\partial_\mu V^{a\mu}
=
i\bar q[M,t^a]q,
$$

and

$$
\partial_\mu A^{a\mu}
=
i\bar q\gamma^5\{M,t^a\}q,
$$

for nonsinglet currents. These formulas are one of the quickest ways to remember what the mass matrix does.

If all included light quarks have the same mass,

$$
M=m\mathbf 1_{n_f},
$$

then

$$
[M,t^a]=0,
$$

so $SU(n_f)_V$ is still exact. But

$$
\{M,t^a\}=2mt^a,
$$

so the axial currents are no longer conserved unless $m=0$.

If the quark masses are unequal, even the non-Abelian vector flavor symmetry is explicitly reduced. For example, with $m_u\ne m_d$, isospin is not exact. In practice $m_u$ and $m_d$ are close enough that isospin remains an excellent approximate symmetry of strong interactions, while electromagnetic effects and the mass difference produce controlled corrections.

:::note[Current masses are not constituent masses]
The quark masses in $M$ are the QCD Lagrangian masses in a renormalization scheme. They are not the much larger “constituent quark masses” used in phenomenological quark models. The smallness of $m_u$ and $m_d$ compared with $\Lambda_{\mathrm{QCD}}$ is what makes chiral symmetry useful.
:::

## The axial singlet and the anomaly

The singlet axial current is

$$
J_5^\mu=\bar q\gamma^\mu\gamma^5q.
$$

Classically, with $M=0$, it would be conserved. Quantum mechanically, it is not. The divergence has the form

$$
\partial_\mu J_5^\mu
=
2i\bar qM\gamma^5q
+
\frac{g_s^2n_f}{16\pi^2}
G_{\mu\nu}^A\widetilde G^{A\mu\nu},
$$

up to the conventional correlated sign choice for $\gamma^5$ and $\epsilon^{\mu\nu\rho\sigma}$. The important point is not the displayed sign; it is that the right-hand side contains $G\widetilde G$ even when $M=0$.

This is the $U(1)_A$ anomaly. It explains why the singlet axial symmetry does not produce an extra light Goldstone boson analogous to the pions. In three-flavor language, the $\eta'$ is not the ninth Goldstone boson of $U(3)_L\times U(3)_R$; it is lifted by anomaly-related topological dynamics.

The nonsinglet axial currents do not have a pure QCD anomaly because the flavor generators $t^a$ are traceless. They can, however, have anomalies after coupling to additional background fields such as electromagnetism. The classic physical consequence is $\pi^0\to\gamma\gamma$.

## What symmetry predicts before symmetry breaking

If $SU(n_f)_L\times SU(n_f)_R$ were realized on the hadron Hilbert space in the Wigner–Weyl mode, hadrons would organize into linear multiplets of the full chiral group. In particular, one would expect systematic parity doubling: states related by axial rotations would have equal masses with opposite parity.

That is not what the low-energy hadron spectrum looks like. Instead, nature realizes the approximate chiral symmetry in the Nambu–Goldstone mode:

$$
SU(n_f)_L\times SU(n_f)_R
\longrightarrow
SU(n_f)_V.
$$

The light pseudoscalar mesons are the corresponding pseudo-Goldstone bosons. The next page explains this spontaneous breaking pattern and its consequences.

## Common pitfalls

**Chiral symmetry is a flavor symmetry, not color.** The matrices $L$ and $R$ act on quark flavors such as $u,d,s$. They do not act on the color index. Color is gauged; chiral flavor symmetry is global.

**A massless Dirac quark is not the same thing as two unrelated theories.** The left- and right-handed components can be independently rotated in flavor space, but they still interact with the same gluon field and belong to the same QCD path integral.

**The axial singlet is special.** It is tempting to say massless QCD has $U(n_f)_L\times U(n_f)_R$ quantum mechanically. The $U(1)_A$ factor is anomalous. The nonsinglet $SU(n_f)_A$ currents are the ones responsible for ordinary pion physics.

**Approximate symmetry is still powerful.** The real $u,d,s$ masses are not zero. Chiral symmetry is nevertheless predictive because the breaking is organized by small parameters in low-energy effective theory.

**Do not confuse current quark masses with hadron masses.** Most of the proton mass is not the sum of the QCD Lagrangian masses of its valence quarks. It is generated dynamically by strong interactions.

**The symmetry and its realization are different questions.** This page identifies the symmetry of the Lagrangian. The next page explains how the vacuum realizes it. QCD’s low-energy physics depends crucially on the distinction.

## Relations to other pages

- [QCD Lagrangian](/gauge-theories-standard-model/qcd/qcd-lagrangian/) gives the microscopic action whose light-quark limit is analyzed here.
- [Running Alpha s](/gauge-theories-standard-model/qcd/running-alpha-s/) explains why QCD becomes strongly coupled in the infrared, where chiral symmetry is realized nonperturbatively.
- [Spontaneous Chiral Symmetry Breaking](/gauge-theories-standard-model/qcd/spontaneous-chiral-symmetry-breaking/) explains the vacuum pattern $SU(n_f)_L\times SU(n_f)_R\to SU(n_f)_V$.
- Later Standard Model and anomaly pages explain why electroweak gauge interactions are chiral and why gauge anomalies must cancel.

## Research status

The symmetry statements on this page are established. They follow from the QCD Lagrangian, Noether’s theorem, and the axial anomaly.

The nonperturbative realization of these symmetries is richer. Lattice QCD gives strong quantitative control over many zero-temperature chiral observables. The finite-temperature chiral crossover, the relation between chiral restoration and deconfinement, finite-density QCD, and many-flavor gauge theories near a conformal window remain active research areas.

## Exercises

### Exercise 1: Independent flavor rotations

Show that the massless light-quark kinetic term

$$
\bar q_L i\gamma^\mu D_\mu q_L
+
\bar q_R i\gamma^\mu D_\mu q_R
$$

is invariant under $q_L\mapsto Lq_L$ and $q_R\mapsto Rq_R$ for constant $L,R\in U(n_f)$.

<details><summary><strong>Solution</strong></summary>

The covariant derivative acts on color, not on flavor. Therefore, for constant $L$,

$$
D_\mu(Lq_L)=L D_\mu q_L.
$$

Also $\bar q_L\mapsto \bar q_LL^\dagger$. Hence

$$
\bar q_L i\gamma^\mu D_\mu q_L
\mapsto
\bar q_LL^\dagger i\gamma^\mu L D_\mu q_L
=
\bar q_L i\gamma^\mu D_\mu q_L,
$$

because $L^\dagger L=1$ and $L$ commutes with the spinor matrices. The right-handed term is identical with $R$ in place of $L$.

</details>

### Exercise 2: What mass degeneracy preserves

Let $M=m\mathbf 1_{n_f}$. Show that the mass term preserves $U(n_f)_V$ but not $SU(n_f)_A$ for $m\ne0$.

<details><summary><strong>Solution</strong></summary>

The mass term is

$$
\mathcal L_m=-\bar q_LMq_R-\bar q_RM^\dagger q_L.
$$

For a vector transformation $q_L\mapsto Vq_L$, $q_R\mapsto Vq_R$,

$$
\bar q_LMq_R
\mapsto
\bar q_LV^\dagger m\mathbf 1 Vq_R
=m\bar q_Lq_R.
$$

So the term is invariant.

For an axial transformation, $q_L\mapsto Aq_L$ and $q_R\mapsto A^\dagger q_R$. Then

$$
\bar q_LMq_R
\mapsto
m\bar q_LA^\dagger A^\dagger q_R,
$$

which is not equal to $m\bar q_Lq_R$ for a generic nontrivial $A$. Thus the mass term breaks the axial part unless $m=0$.

</details>

### Exercise 3: Nonsinglet versus singlet anomaly

Explain why the pure QCD anomaly affects the singlet axial current but not the nonsinglet axial currents.

<details><summary><strong>Solution</strong></summary>

The anomaly coefficient for an axial current with flavor generator $t$ is proportional to the flavor trace $\operatorname{tr}_{\mathrm{flavor}}t$ multiplied by the color factor from the gluon vertices. For a nonsinglet generator $t^a\in su(n_f)$,

$$
\operatorname{tr}t^a=0.
$$

Therefore the pure QCD anomaly cancels among flavors for the nonsinglet current. For the singlet axial current, the flavor generator is proportional to the identity, whose trace is $n_f$, so the anomaly is proportional to $n_fG\widetilde G$.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§75–76 and §83, for chiral anomalies, global anomalies, and chiral symmetry breaking.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 28–30 and 32, for symmetry breaking, weak interactions, anomalies, and QCD.
- Coleman, *Aspects of Symmetry*, especially “Soft Pions” and “Secret Symmetry,” for current algebra, PCAC, and symmetry realization.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Chs. 19–22, for chiral symmetry, current algebra, and effective Lagrangian methods.

## Version history

- **2026-06-18:** Initial polished draft. Added the light-quark chiral symmetry decomposition, current divergences, anomaly discussion, exercises, and chiral-symmetry map figure.
