---
title: "Spontaneous Chiral Symmetry Breaking"
description: "Explains how the QCD vacuum realizes light-quark chiral symmetry, producing Goldstone pions, pseudo-Goldstone masses, and low-energy chiral dynamics."
sidebar:
  label: "Spontaneous Chiral Symmetry Breaking"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki §83; Coleman, Aspects of Symmetry, Chs. 2 and 5; Schwartz Chs. 28 and 32; Weinberg Vol. II Chs. 19–22."
topics:
  - spontaneous chiral symmetry breaking
  - quark condensate
  - Goldstone bosons
  - pions
  - chiral Lagrangian
  - GMOR relation
canonicalTopics:
  - spontaneous-chiral-symmetry-breaking
  - quark-condensate
  - pion-goldstone-boson
  - chiral-lagrangian
  - gell-mann-oakes-renner
researchStatus:
  established:
    - "Light-quark QCD realizes approximate nonsinglet chiral symmetry in the Nambu–Goldstone mode, producing the light pseudoscalar mesons as pseudo-Goldstone bosons."
  active:
    - "The detailed relationship between chiral symmetry breaking, confinement, topology, finite-temperature restoration, finite-density phases, and many-flavor conformality remains an active nonperturbative research area."
---

## Summary

In the massless light-quark limit, QCD has the global chiral symmetry

$$
SU(n_f)_L\times SU(n_f)_R.
$$

The vacuum does not realize this symmetry by placing hadrons into degenerate left-right multiplets. Instead, the vacuum spontaneously breaks it to the diagonal vector subgroup,

$$
SU(n_f)_L\times SU(n_f)_R
\longrightarrow
SU(n_f)_V.
$$

A standard order parameter is the quark condensate,

$$
\langle \bar q q\rangle\ne0,
$$

or, more precisely, the matrix condensate

$$
\langle\bar q_R^{\,j}q_L^{\,i}\rangle
\propto
\delta^{ij}.
$$

The broken generators produce

$$
n_f^2-1
$$

Goldstone bosons. For $n_f=2$, these are the three pions in the massless limit. For $n_f=3$, they form the pseudoscalar octet: pions, kaons, and the octet $\eta$. Small quark masses make them pseudo-Goldstone bosons rather than exactly massless particles.

<figure class="doc-figure" style="--figure-width: 40rem;">

![Spontaneous chiral symmetry breaking pattern in QCD: SU(nf)L times SU(nf)R broken by the quark condensate to SU(nf)V, with Goldstone directions and small mass effects.](/figures/gauge-theories-standard-model/qcd-chiral-breaking-pattern.svg)

<figcaption>

The QCD vacuum aligns the matrix order parameter so that only common left-right flavor rotations remain unbroken. The broken axial directions are parametrized by $U(x)=\exp(2i\pi^at^a/f)$; small quark masses tilt the vacuum and give the Goldstone modes small masses.

</figcaption>
</figure>

## Prerequisites

You should first read [Chiral Symmetry in QCD](/gauge-theories-standard-model/qcd/chiral-symmetry-in-qcd/). This page assumes the massless light-quark symmetry

$$
q_L\mapsto Lq_L,
\qquad
q_R\mapsto Rq_R,
\qquad
L,R\in SU(n_f),
$$

and the mass spurion convention

$$
M\mapsto LMR^\dagger.
$$

You should also know [Running Alpha s](/gauge-theories-standard-model/qcd/running-alpha-s/), because spontaneous chiral symmetry breaking is an infrared phenomenon of strongly coupled QCD. The microscopic theory remains the [QCD Lagrangian](/gauge-theories-standard-model/qcd/qcd-lagrangian/), but its useful low-energy variables are hadrons and Goldstone fields, not weakly coupled quarks and gluons.

## Core idea

A symmetry of the Lagrangian can be realized in two broad ways.

In the **Wigner–Weyl mode**, the vacuum is invariant and states assemble into linear multiplets of the symmetry. If low-energy QCD realized $SU(n_f)_L\times SU(n_f)_R$ this way, one would expect nearly degenerate opposite-parity hadrons related by axial rotations.

In the **Nambu–Goldstone mode**, the Lagrangian is symmetric but the vacuum is not. The symmetry still exists, but the broken charges do not annihilate the vacuum. Instead, the broken generators create massless modes.

QCD chooses the second option for light-quark chiral symmetry. The most compact expression of the result is

$$
\langle\bar q_R^{\,j}q_L^{\,i}\rangle
\propto
\delta^{ij}.
$$

This condensate is invariant under $L=R$ but not under independent $L$ and $R$. Thus the unbroken subgroup is $SU(n_f)_V$.

The physical punchline is that pions are light not because of an accidental quark-model binding energy, but because they are pseudo-Goldstone bosons of an approximate spontaneously broken symmetry.

## Setup and conventions

Collect the $n_f$ light quarks as a flavor vector $q$. The massless light-quark QCD Lagrangian has

$$
G_\chi=SU(n_f)_L\times SU(n_f)_R
$$

as a global symmetry. We ignore the anomalous $U(1)_A$ factor and keep the exact $U(1)_V$ baryon-number symmetry in the background; baryon number is not broken by the chiral condensate.

The order parameter can be packaged as a matrix

$$
\Sigma^i{}_{j}\sim\bar q_R^{\,j}q_L^{\,i}.
$$

Under chiral rotations,

$$
\Sigma\mapsto L\Sigma R^\dagger.
$$

If the vacuum expectation value is proportional to the identity,

$$
\langle\Sigma\rangle=v^3\mathbf 1_{n_f},
$$

then invariance requires

$$
L\langle\Sigma\rangle R^\dagger=\langle\Sigma\rangle.
$$

For $v^3\ne0$, this implies

$$
L=R.
$$

Therefore the unbroken group is the diagonal subgroup

$$
SU(n_f)_V=\{(V,V):V\in SU(n_f)\}.
$$

The sign and renormalization-scale value of $\langle\bar q q\rangle$ are convention- and scheme-dependent. The symmetry-breaking statement is not: in the massless infinite-volume theory, the vacuum has a nonzero chiral order parameter.

## Goldstone counting

The broken generators are the axial generators. The counting is

$$
\dim SU(n_f)_L+\dim SU(n_f)_R-\dim SU(n_f)_V.
$$

Since

$$
\dim SU(n_f)=n_f^2-1,
$$

we get

$$
N_{\mathrm{GB}}
=
2(n_f^2-1)-(n_f^2-1)
=
n_f^2-1.
$$

For two light flavors,

$$
SU(2)_L\times SU(2)_R\to SU(2)_V,
$$

so

$$
N_{\mathrm{GB}}=3.
$$

These are the pions $\pi^+$, $\pi^0$, and $\pi^-$ in the chiral limit.

For three massless flavors,

$$
SU(3)_L\times SU(3)_R\to SU(3)_V,
$$

so

$$
N_{\mathrm{GB}}=8.
$$

These modes are organized as the pseudoscalar octet

$$
\pi^\pm,
\quad
\pi^0,
\quad
K^\pm,
\quad
K^0,
\quad
\bar K^0,
\quad
\eta_8.
$$

The physical $\eta$ and $\eta'$ involve mixing and anomaly physics. The short version is this: the octet-like $\eta$ participates in chiral symmetry, while the singlet-like $\eta'$ is not a ninth Goldstone boson because $U(1)_A$ is anomalous.

## Goldstone fields and nonlinear realization

The Goldstone modes live on the coset space

$$
\frac{SU(n_f)_L\times SU(n_f)_R}{SU(n_f)_V}
\simeq
SU(n_f).
$$

A standard field variable is an $SU(n_f)$-valued matrix

$$
U(x)=\exp\left(\frac{2i\pi^a(x)t^a}{f}\right),
$$

where $t^a$ are flavor generators and $f$ is the Goldstone decay constant in the chosen normalization. The transformation law is

$$
U(x)\mapsto L U(x) R^\dagger.
$$

This transformation law mirrors that of the order parameter. In a low-energy effective theory, $U(x)$ is the field that remembers the spontaneously broken chiral symmetry after strongly coupled quarks and gluons have been traded for hadronic degrees of freedom.

The leading chiral Lagrangian is

$$
\mathcal L_\chi
=
\frac{f^2}{4}\operatorname{tr}(\partial_\mu U\partial^\mu U^\dagger)
+
\frac{f^2B_0}{2}\operatorname{tr}(MU^\dagger+UM^\dagger)
+\cdots.
$$

The first term is fixed by symmetry and derivative counting. The second term is fixed by treating $M$ as a spurion transforming as $M\mapsto LMR^\dagger$ and then setting $M$ equal to the physical quark mass matrix.

This is a nonlinear realization of chiral symmetry. The symmetry is still there, but it does not act on the pion fields as a simple linear rotation.

## Why the pions are light

Goldstone’s theorem says that an exactly spontaneously broken continuous global symmetry produces massless excitations. QCD with exactly massless $u,d$ quarks would therefore have massless pions.

Real pions are not massless because $m_u$ and $m_d$ are not zero. But they are much lighter than typical hadrons because the explicit breaking is small. This is the pseudo-Goldstone mechanism.

A standard leading relation is the Gell-Mann–Oakes–Renner relation. In the isospin-symmetric two-flavor chiral limit, define

$$
\Sigma_q\equiv -\langle\bar u u\rangle
=-\langle\bar d d\rangle
$$

as a positive condensate parameter. Then, to leading order in the light quark masses,

$$
f_\pi^2m_\pi^2
=
(m_u+m_d)\Sigma_q
+O(m_q^2).
$$

Equivalently,

$$
f_\pi^2m_\pi^2
=
-(m_u+m_d)\langle\bar u u\rangle
+O(m_q^2),
$$

assuming $\langle\bar u u\rangle=\langle\bar d d\rangle$ in the chiral limit.

The important scaling is

$$
m_\pi^2\propto m_q,
$$

not $m_\pi\propto m_q$. That square-root sensitivity of the pion mass to the quark mass is one of the cleanest fingerprints of pseudo-Goldstone physics.

For two degenerate light quarks with $M=m_q\mathbf 1$, expanding the leading chiral Lagrangian gives

$$
m_\pi^2=2B_0m_q.
$$

The constant $B_0$ is related to the condensate by $B_0=\Sigma_q/f^2$ in the same leading convention.

## Why this is nonperturbative

The condensate is not obtained by expanding QCD around $g_s=0$. At weak coupling, massless quarks and gluons are the right short-distance variables, and the vacuum does not obviously contain a quark–antiquark condensate. The condensate is an infrared property of the strongly coupled theory.

Several kinds of evidence support the standard picture:

| Evidence | What it suggests |
|---|---|
| Light pions | Pions behave like pseudo-Goldstone bosons of broken axial flavor symmetry. |
| Absence of parity doubling at low energies | The vacuum is not invariant under axial rotations acting linearly on hadrons. |
| Current algebra and soft-pion relations | Axial currents couple to pion poles in the expected way. |
| Lattice QCD | Nonperturbative simulations observe chiral condensates and the quark-mass dependence of pseudoscalar masses. |
| Chiral perturbation theory | A systematic EFT expansion describes low-energy pion physics. |

There is also a useful spectral diagnostic. In Euclidean QCD, the Banks–Casher relation states schematically that

$$
\langle\bar q q\rangle=-\pi\rho(0),
$$

where $\rho(0)$ is the density of near-zero Dirac eigenvalues per unit volume in the chiral limit. The precise statement requires the infinite-volume and zero-mass limits in the right order. Conceptually, chiral symmetry breaking is tied to an accumulation of near-zero Dirac modes in the gauge-field ensemble.

## PCAC and axial currents

For small quark masses, the axial current is only partially conserved. In the two-flavor theory one often writes schematically

$$
\partial_\mu A^{\mu a}
=
f_\pi m_\pi^2\pi^a+
\cdots,
$$

where the ellipsis includes higher-order terms and convention-dependent normalizations of the pion field.

The chiral-limit statement is sharper: the axial current creates a one-pion state from the vacuum,

$$
\langle0|A^{\mu a}(0)|\pi^b(p)\rangle
=
i f_\pi p^\mu\delta^{ab},
$$

up to normalization conventions for states and fields. Taking the divergence gives the pion pole structure behind many soft-pion results.

This is the bridge from symmetry breaking to actual hadron amplitudes. Chiral symmetry is not just a group-theory label; it controls how matrix elements behave when pion momenta and quark masses are small.

## Relation to confinement

Chiral symmetry breaking and confinement both occur in low-temperature real-world QCD, but they are logically distinct.

Confinement says that isolated colored asymptotic states are absent and the physical spectrum is built from color singlets. Chiral symmetry breaking says that the light-quark flavor symmetry is realized in the Nambu–Goldstone mode.

They often appear together because both are generated by strong infrared dynamics, but neither statement is a simple theorem following from the other.

| Setting | Why the distinction matters |
|---|---|
| Pure Yang–Mills theory | There are no dynamical quarks and no ordinary light-quark chiral symmetry, but confinement diagnostics still exist. |
| QCD with light quarks | Wilson-loop area laws are softened by string breaking, while chiral symmetry breaking remains sharply meaningful in the chiral limit. |
| Finite temperature | Chiral restoration and deconfinement are related but not identical concepts. For physical quark masses QCD has crossovers rather than exact phase transitions. |
| Many-flavor gauge theories | As $n_f$ increases, asymptotic freedom weakens and infrared conformal behavior may replace confinement and chiral breaking. |

For the Standard Model, the practical lesson is simple: QCD generates much of the visible mass and a rich hadron spectrum from a compact gauge theory with small light-quark masses.

## What happens to U(1) axial symmetry

If one naively included the classical singlet axial symmetry, the breaking pattern would seem to predict an additional Goldstone boson. That would lead to a ninth light pseudoscalar in the three-flavor theory.

QCD does not do that. The singlet axial current obeys the anomalous Ward identity

$$
\partial_\mu J_5^\mu
=
2i\bar qM\gamma^5q
+
\frac{n_fg_s^2}{16\pi^2}G_{\mu\nu}^A\widetilde G^{A\mu\nu},
$$

up to the sign convention for the anomaly term. The anomaly and topological gauge-field dynamics lift the would-be singlet Goldstone mode. This is the qualitative resolution of the old $U(1)_A$ puzzle.

The later theta-angle page will revisit this same equation from another direction: axial rotations shift phases between the mass matrix and the theta term.

## Common pitfalls

**Spontaneous chiral symmetry breaking is not gauge-symmetry breaking.** The broken symmetry is a global flavor symmetry. Color remains a gauge redundancy, and physical states remain color singlets.

**The condensate is not a directly measured particle mass.** $\langle\bar q q\rangle$ is a scheme-dependent local operator expectation value. Its nonzero value in the chiral limit is an order parameter, not a standalone observable independent of convention.

**Pions are pseudo-Goldstone bosons, not exact Goldstone bosons in nature.** Real quark masses explicitly break chiral symmetry, so the pions have nonzero mass.

**The $\eta'$ is not missing from the Goldstone count by accident.** The singlet axial symmetry is anomalous in QCD. It is not included in the $n_f^2-1$ Goldstone count.

**Do not infer confinement from the condensate alone.** A nonzero condensate diagnoses chiral symmetry breaking. It is not by itself a proof of confinement.

**Do not forget the order of limits.** In finite volume, spontaneous breaking of an exact continuous symmetry is subtle. The clean order parameter is defined by taking the infinite-volume limit before taking the quark mass to zero.

## Relations to other pages

- [Chiral Symmetry in QCD](/gauge-theories-standard-model/qcd/chiral-symmetry-in-qcd/) gives the symmetry and current algebra that this page uses.
- [QCD Lagrangian](/gauge-theories-standard-model/qcd/qcd-lagrangian/) identifies the mass matrix and theta term in the microscopic theory.
- The planned Confinement in QCD page will compare chiral symmetry breaking with confinement and screening.
- The planned Theta Angle and Strong CP Problem page will explain the singlet axial anomaly, mass phases, and $\bar\theta$.
- Later electroweak pages will use chirality differently: weak interactions are chiral gauge interactions, while QCD chiral symmetry is a global flavor symmetry of light quarks.

## Research status

The symmetry-breaking pattern

$$
SU(n_f)_L\times SU(n_f)_R\to SU(n_f)_V
$$

and the pseudo-Goldstone interpretation of pions are established pillars of low-energy QCD.

Active work remains at the quantitative edges and in extreme regimes: precise low-energy constants, finite-temperature chiral restoration, the order of the chiral transition for different quark masses, finite-density QCD, real-time dynamics of chiral modes, many-flavor gauge theories, and connections between topology, chiral symmetry, and confinement.

## Exercises

### Exercise 1: Unbroken vector subgroup

Let $\Sigma=\Sigma_0\mathbf 1$ transform as $\Sigma\mapsto L\Sigma R^\dagger$. Show that the stabilizer of $\Sigma$ inside $SU(n_f)_L\times SU(n_f)_R$ is $SU(n_f)_V$.

<details><summary><strong>Solution</strong></summary>

The condition for invariance is

$$
L\Sigma_0\mathbf 1R^\dagger=\Sigma_0\mathbf 1.
$$

Since $\Sigma_0\ne0$, this gives

$$
LR^\dagger=\mathbf 1,
$$

or $L=R$. Thus the unbroken subgroup consists of pairs $(V,V)$ with $V\in SU(n_f)$, which is the diagonal subgroup $SU(n_f)_V$.

</details>

### Exercise 2: Goldstone counting

Compute the number of Goldstone bosons for $n_f=2$ and $n_f=3$.

<details><summary><strong>Solution</strong></summary>

The general count is

$$
N_{\mathrm{GB}}=n_f^2-1.
$$

For $n_f=2$,

$$
N_{\mathrm{GB}}=2^2-1=3,
$$

which gives the three pions in the chiral limit. For $n_f=3$,

$$
N_{\mathrm{GB}}=3^2-1=8,
$$

which gives the pseudoscalar octet in the idealized three-flavor chiral limit.

</details>

### Exercise 3: Leading pion mass from the chiral Lagrangian

For two degenerate quark masses $M=m\mathbf 1_2$, expand

$$
U=\exp\left(\frac{2i\pi^at^a}{f}\right)
$$

to quadratic order in

$$
\frac{f^2B_0}{2}\operatorname{tr}(MU^\dagger+UM^\dagger)
$$

and show that the leading mass is $m_\pi^2=2B_0m$.

<details><summary><strong>Solution</strong></summary>

Use $\operatorname{tr}(t^at^b)=\frac12\delta^{ab}$. Expanding,

$$
U=1+\frac{2i\pi^at^a}{f}
-\frac{2\pi^a\pi^bt^at^b}{f^2}+O(\pi^3),
$$

and similarly for $U^\dagger$. For $M=m\mathbf 1_2$, the quadratic part of the mass term is

$$
-2B_0m\operatorname{tr}(\pi^a\pi^bt^at^b)
=
-B_0m\pi^a\pi^a.
$$

The canonical scalar mass term in mostly-minus convention is

$$
-\frac12m_\pi^2\pi^a\pi^a,
$$

so

$$
m_\pi^2=2B_0m.
$$

</details>

### Exercise 4: Why no ninth Goldstone boson?

Explain why $U(1)_A$ does not add one more Goldstone boson to the three-flavor pseudoscalar octet.

<details><summary><strong>Solution</strong></summary>

The classical $U(1)_A$ symmetry is broken by the quantum axial anomaly. Its current has a divergence proportional to $G_{\mu\nu}^A\widetilde G^{A\mu\nu}$ even when the quark masses vanish. Therefore $U(1)_A$ is not an exact global symmetry of quantum QCD, so Goldstone’s theorem does not apply to it. The non-Abelian chiral symmetry gives an octet of Goldstone bosons, while the singlet pseudoscalar is lifted by anomaly and topological dynamics.

</details>

## References

- Srednicki, *Quantum Field Theory*, §83, for chiral symmetry breaking in QCD.
- Coleman, *Aspects of Symmetry*, especially “Soft Pions” and “Secret Symmetry,” for current algebra, PCAC, Goldstone bosons, and spontaneous symmetry breaking.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 28 and 32, for spontaneous symmetry breaking and QCD context.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Chs. 19–22, for chiral dynamics and effective Lagrangians.
- Gasser and Leutwyler, classic papers on chiral perturbation theory, for the systematic low-energy effective theory of QCD.

## Version history

- **2026-06-18:** Initial polished draft. Added the condensate order parameter, symmetry-breaking pattern, Goldstone counting, leading chiral Lagrangian, GMOR relation, exercises, and chiral-breaking figure.
