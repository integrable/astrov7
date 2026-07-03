---
title: "PMNS Matrix"
description: "Explains how lepton mixing arises from diagonalizing charged-lepton and neutrino mass matrices, and how the PMNS matrix controls neutrino oscillations."
sidebar:
  label: "PMNS Matrix"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki §91; Schwartz Ch. 29; Burgess Chs. 7 and 9; Weinberg Vol. II electroweak chapters."
topics:
  - PMNS matrix
  - neutrino mixing
  - neutrino oscillations
  - Majorana phases
  - lepton flavor
canonicalTopics:
  - pmns-matrix
  - lepton-mixing
  - neutrino-oscillations
  - majorana-phases
researchStatus:
  established:
    - "Neutrino oscillations require nonzero neutrino mass splittings and a nontrivial lepton mixing matrix."
  active:
    - "The PMNS formalism does not by itself determine the absolute mass scale, the Majorana versus Dirac nature of neutrinos, or the ultraviolet origin of neutrino masses."
---

## Summary

The PMNS matrix is the lepton-sector analogue of the CKM matrix. It appears when the charged weak current is written in the mass basis after diagonalizing the charged-lepton and neutrino mass matrices. With gauge-basis fields marked by a superscript $0$, the charged current starts as

$$
\mathcal L_{\rm CC}
=
-\frac{g}{\sqrt2}W^-_\mu\,\bar e^0_{\alpha L}\gamma^\mu\nu^0_{\alpha L}
+\text{h.c.}
$$

If

$$
e_L^0=U_{eL}e_L,
\qquad
\nu_L^0=U_\nu\nu_L,
$$

then

$$
\mathcal L_{\rm CC}
=
-\frac{g}{\sqrt2}W^-_\mu\,\bar e_{\alpha L}\gamma^\mu
(U_{\rm PMNS})_{\alpha i}\nu_{iL}
+\text{h.c.},
\qquad
U_{\rm PMNS}=U_{eL}^\dagger U_\nu.
$$

The matrix is physical because the charged weak interaction couples the charged-lepton and neutrino fields inside the same $SU(2)_L$ doublet before mass diagonalization. Neutrino propagation is diagonal in the mass basis, while weak production and detection are organized by charged-lepton flavor. That mismatch is neutrino oscillation physics in one sentence.

<figure class="doc-figure" style="--figure-width: 48rem;">

![Origin of the PMNS matrix](/figures/gauge-theories-standard-model/pmns-mixing-map.svg)

<figcaption>

The PMNS matrix is the mismatch between the left-handed charged-lepton rotation and the neutrino rotation. It appears in the charged current and controls the coherent sum over mass eigenstates in neutrino oscillation amplitudes.

</figcaption>
</figure>

## Prerequisites

You should know [Fermion Mass Matrices](/gauge-theories-standard-model/flavor-neutrinos/fermion-mass-matrices/), [CKM Matrix](/gauge-theories-standard-model/flavor-neutrinos/ckm-matrix/), and [CP Violation](/gauge-theories-standard-model/flavor-neutrinos/cp-violation/). You should also remember from [Weak Charged Current](/gauge-theories-standard-model/electroweak/weak-charged-current/) that the charged weak interaction couples only to left-handed fermions.

The page uses the convention $Q=T^3+Y$ and writes the electroweak doublet as

$$
L_\alpha^0=
\begin{pmatrix}
\nu^0_{\alpha L}\\
e^0_{\alpha L}
\end{pmatrix},
\qquad
\alpha=e,\mu,\tau.
$$

## Core idea

The Standard Model charged current is diagonal in weak flavor before mass matrices are diagonalized. The mass basis is usually different. For charged leptons, one diagonalizes

$$
U_{eL}^\dagger M_e U_{eR}=D_e,
\qquad
D_e=\operatorname{diag}(m_e,m_\mu,m_\tau).
$$

For Majorana neutrinos, one diagonalizes a complex symmetric mass matrix by Takagi factorization,

$$
U_\nu^T M_\nu U_\nu=D_\nu,
\qquad
D_\nu=\operatorname{diag}(m_1,m_2,m_3),
\qquad
m_i\ge 0.
$$

The two left-handed rotations need not agree. Their mismatch is

$$
U_{\rm PMNS}=U_{eL}^\dagger U_\nu.
$$

If there were no neutrino masses, there would be no neutrino mass basis to compare with the charged-lepton mass basis. If all neutrino masses were exactly degenerate, much of the apparent mixing could be rotated away. Physical oscillations require both nontrivial mixing and nonzero mass-squared splittings.

## Setup and conventions

We write flavor indices as $\alpha,\beta=e,\mu,\tau$ and neutrino mass indices as $i,j=1,2,3$. The mass eigenstate neutrinos are $\nu_i$, with masses $m_i$. The PMNS matrix elements are

$$
U_{\alpha i}\equiv (U_{\rm PMNS})_{\alpha i}.
$$

The charged current in the lepton mass basis is

$$
\mathcal L_{\rm CC}
=
-\frac{g}{\sqrt2}W^-_\mu
\sum_{\alpha,i}
\bar e_{\alpha L}\gamma^\mu U_{\alpha i}\nu_{iL}
+\text{h.c.}
$$

Equivalently, the weak-interaction neutrino state associated with charged lepton $\alpha$ is written

$$
|\nu_\alpha\rangle
=
\sum_i U_{\alpha i}^*|\nu_i\rangle,
$$

up to the usual wave-packet qualifications needed for a fully realistic source and detector. This equation is a compact way to remember how weak flavor and mass propagation are related.

## Derivation from mass diagonalization

Start in the gauge basis. The lepton charged current is

$$
\mathcal L_{\rm CC}
=
-\frac{g}{\sqrt2}W^-_\mu\,\bar e^0_L\gamma^\mu\nu^0_L
+\text{h.c.},
$$

where generation indices are suppressed. Now rotate to mass eigenstates,

$$
e_L^0=U_{eL}e_L,
\qquad
\nu_L^0=U_\nu\nu_L.
$$

Then

$$
\bar e_L^0\gamma^\mu\nu_L^0
=
\bar e_LU_{eL}^\dagger\gamma^\mu U_\nu\nu_L.
$$

The generation-space matrices commute with $\gamma^\mu$, so

$$
\bar e_L^0\gamma^\mu\nu_L^0
=
\bar e_L\gamma^\mu (U_{eL}^\dagger U_\nu)\nu_L.
$$

Thus

$$
U_{\rm PMNS}=U_{eL}^\dagger U_\nu.
$$

This is exactly parallel to

$$
V_{\rm CKM}=U_{uL}^\dagger U_{dL},
$$

but with one conceptual wrinkle: in the minimal renormalizable Standard Model there is no neutrino mass matrix. The PMNS matrix becomes physical only after neutrino masses are added, either through right-handed neutrinos, the Weinberg operator, or another ultraviolet completion.

## Dirac versus Majorana neutrinos

If neutrinos are Dirac fermions, one introduces right-handed gauge singlets $\nu_R$ and a Dirac mass matrix

$$
U_{\nu L}^\dagger M_\nu U_{\nu R}=D_\nu.
$$

Then

$$
U_{\rm PMNS}=U_{eL}^\dagger U_{\nu L}.
$$

For three Dirac neutrinos, the PMNS matrix has the same type of physical parameters as the CKM matrix:

$$
3\text{ mixing angles}+1\text{ Dirac CP phase}.
$$

If neutrinos are Majorana fermions, the mass term has the schematic form

$$
\mathcal L_m
=
-\frac12\nu_L^T C M_\nu\nu_L+\text{h.c.},
$$

with $M_\nu=M_\nu^T$. The diagonalization is Takagi rather than biunitary:

$$
U_\nu^T M_\nu U_\nu=D_\nu.
$$

Majorana fields cannot be freely rephased in the same way as Dirac fields, because a rephasing would change the Majorana mass term. For three Majorana neutrinos, the PMNS matrix has

$$
3\text{ mixing angles}+1\text{ Dirac CP phase}+2\text{ Majorana phases}.
$$

The Majorana phases do not affect ordinary neutrino oscillation probabilities, but they can enter lepton-number-violating amplitudes such as neutrinoless double beta decay.

## Standard parameterization

A common parameterization is

$$
U_{\rm PMNS}
=
V(\theta_{12},\theta_{23},\theta_{13},\delta)
\begin{pmatrix}
1&0&0\\
0&e^{i\alpha_{21}/2}&0\\
0&0&e^{i\alpha_{31}/2}
\end{pmatrix},
$$

where the final diagonal matrix is present only for Majorana neutrinos. The CKM-like part is

$$
V=
\begin{pmatrix}
c_{12}c_{13}&s_{12}c_{13}&s_{13}e^{-i\delta}\\
-s_{12}c_{23}-c_{12}s_{23}s_{13}e^{i\delta}&
c_{12}c_{23}-s_{12}s_{23}s_{13}e^{i\delta}&
s_{23}c_{13}\\
s_{12}s_{23}-c_{12}c_{23}s_{13}e^{i\delta}&
-c_{12}s_{23}-s_{12}c_{23}s_{13}e^{i\delta}&
c_{23}c_{13}
\end{pmatrix},
$$

with

$$
s_{ij}=\sin\theta_{ij},
\qquad
c_{ij}=\cos\theta_{ij}.
$$

The phase $\delta$ is the Dirac CP phase. It can affect oscillation probabilities. The phases $\alpha_{21}$ and $\alpha_{31}$ are Majorana phases. They do not affect oscillations because oscillation amplitudes always contain products in which the final diagonal Majorana phase matrix cancels.

## Oscillation amplitudes

A neutrino produced with charged-lepton flavor $\alpha$ is a coherent superposition of mass eigenstates,

$$
|\nu_\alpha\rangle
=
\sum_i U_{\alpha i}^*|\nu_i\rangle.
$$

For relativistic neutrinos with a common energy scale $E$, the mass eigenstate $\nu_i$ accumulates the phase

$$
\exp\left(-i\frac{m_i^2L}{2E}\right),
$$

up to a common phase that drops out of probabilities. The amplitude for $\nu_\alpha$ to be detected as $\nu_\beta$ is therefore

$$
\mathcal A_{\alpha\to\beta}(L)
=
\sum_i U_{\beta i}
\exp\left(-i\frac{m_i^2L}{2E}\right)
U_{\alpha i}^*.
$$

Only mass-squared differences matter, because a common phase multiplying all terms is unobservable. Define

$$
\Delta m_{ij}^2=m_i^2-m_j^2,
\qquad
\Delta_{ij}=\frac{\Delta m_{ij}^2L}{4E}.
$$

Then the oscillation probability is

$$
\begin{aligned}
P(\nu_\alpha\to\nu_\beta)
&=
\delta_{\alpha\beta}
-4\sum_{i<j}\operatorname{Re}
\left(U_{\alpha i}^*U_{\beta i}U_{\alpha j}U_{\beta j}^*\right)
\sin^2\Delta_{ij}
\\
&\quad
+2\sum_{i<j}\operatorname{Im}
\left(U_{\alpha i}^*U_{\beta i}U_{\alpha j}U_{\beta j}^*\right)
\sin(2\Delta_{ij}).
\end{aligned}
$$

For antineutrinos, replace $U$ by $U^*$. Thus CP-odd oscillation effects come from the imaginary rephasing-invariant combinations

$$
\operatorname{Im}
\left(U_{\alpha i}^*U_{\beta i}U_{\alpha j}U_{\beta j}^*\right).
$$

For three generations, all such imaginary parts have the same magnitude up to signs if $U$ is unitary. The corresponding leptonic Jarlskog invariant is

$$
J_{\rm PMNS}
=
\operatorname{Im}(U_{e1}U_{\mu2}U_{e2}^*U_{\mu1}^*)
=
c_{12}c_{23}c_{13}^2s_{12}s_{23}s_{13}\sin\delta.
$$

## What oscillations do and do not measure

Oscillation experiments measure mixing angles, CP-sensitive combinations, and mass-squared differences. They do not by themselves measure the absolute neutrino mass scale. If all masses are shifted in a way that keeps $\Delta m_{ij}^2$ fixed, the oscillation phases are unchanged up to an overall common phase.

Oscillations also do not determine whether neutrinos are Dirac or Majorana particles. Majorana phases cancel from ordinary oscillation probabilities. To probe the Majorana nature, one needs lepton-number-violating observables or other information beyond oscillation kinematics.

Finally, the PMNS matrix is not a complete theory of neutrino masses. It is the low-energy mixing matrix after masses have been introduced. The [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/) page explains the simplest Standard-Model-only operator that can generate a Majorana neutrino mass matrix.

## Common pitfalls

**The PMNS matrix is not “the neutrino mass matrix.”** It is a unitary mixing matrix. It helps diagonalize the neutrino mass matrix only after one chooses the charged-lepton basis.

**The PMNS matrix depends on the charged-lepton rotation too.** In a basis where $M_e$ is already diagonal, one often writes $U_{\rm PMNS}=U_\nu$. That is a basis choice, not the general definition.

**Majorana phases do not affect ordinary oscillations.** They are physical if neutrinos are Majorana particles, but oscillation probabilities contain products of $U$ in which the final diagonal Majorana phase matrix cancels.

**Oscillations measure mass-squared differences, not masses.** The phase difference is controlled by $\Delta m_{ij}^2L/(2E)$, not by $m_i$ alone.

**Flavor neutrino states are an approximation with a job.** In a full production-and-detection calculation, neutrinos are internal or external wave packets. The flavor-state language is an excellent effective description when coherence conditions are satisfied.

**Large PMNS angles do not mean large neutrino masses.** Mixing angles describe the orientation of mass eigenstates relative to weak flavor. Mass eigenvalues describe the spectrum. They are different data.

## Relations to other pages

This page follows [CP Violation](/gauge-theories-standard-model/flavor-neutrinos/cp-violation/) and completes the parallel between quark and lepton mixing. The next page, [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/), explains a minimal effective operator that generates a Majorana neutrino mass matrix and therefore a PMNS matrix after diagonalization.

Later Standard Model Architecture pages assemble the gauge sector, Higgs sector, Yukawa sector, neutrino-mass extensions, accidental symmetries, and anomaly constraints into one Lagrangian-level picture.

## Research status

The existence of neutrino oscillations is established. The QFT interpretation is also settled: oscillations require coherent propagation of neutrino mass eigenstates with nonzero mass-squared splittings, and PMNS mixing appears in the charged weak current.

Oscillations alone do not fix the absolute mass scale, do not decide Dirac versus Majorana, and do not by themselves identify the ultraviolet origin of neutrino masses. The PMNS matrix is therefore a low-energy mixing object, not a complete theory of why the neutrino sector has its observed structure or whether that structure is connected to matter–antimatter asymmetry.

## Exercises

### Exercise 1: Derive the PMNS matrix from field rotations

Starting from

$$
\mathcal L_{\rm CC}
=
-\frac{g}{\sqrt2}W^-_\mu\bar e_L^0\gamma^\mu\nu_L^0+\text{h.c.},
$$

use

$$
e_L^0=U_{eL}e_L,
\qquad
\nu_L^0=U_\nu\nu_L
$$

to derive $U_{\rm PMNS}=U_{eL}^\dagger U_\nu$.

<details><summary><strong>Solution</strong></summary>

The conjugate field transforms as

$$
\bar e_L^0=\bar e_LU_{eL}^\dagger.
$$

Substitution gives

$$
\bar e_L^0\gamma^\mu\nu_L^0
=
\bar e_LU_{eL}^\dagger\gamma^\mu U_\nu\nu_L.
$$

Generation-space matrices commute with $\gamma^\mu$, so

$$
\bar e_L^0\gamma^\mu\nu_L^0
=
\bar e_L\gamma^\mu(U_{eL}^\dagger U_\nu)\nu_L.
$$

Therefore

$$
U_{\rm PMNS}=U_{eL}^\dagger U_\nu.
$$

</details>

### Exercise 2: Show why Majorana phases cancel from oscillations

Let

$$
U=V P,
\qquad
P=\operatorname{diag}(1,e^{i\alpha_{21}/2},e^{i\alpha_{31}/2}).
$$

Show that the oscillation product

$$
U_{\beta i}U_{\alpha i}^*
$$

is independent of the Majorana phase attached to column $i$.

<details><summary><strong>Solution</strong></summary>

The diagonal matrix $P$ multiplies column $i$ of $V$ by a phase $P_i$. Thus

$$
U_{\beta i}=V_{\beta i}P_i,
\qquad
U_{\alpha i}^*=V_{\alpha i}^*P_i^*.
$$

Therefore

$$
U_{\beta i}U_{\alpha i}^*
=
V_{\beta i}V_{\alpha i}^*P_iP_i^*
=
V_{\beta i}V_{\alpha i}^*.
$$

The Majorana phase cancels column by column.

</details>

### Exercise 3: Derive the two-flavor oscillation formula

For two flavors with

$$
U=
\begin{pmatrix}
\cos\theta&\sin\theta\\
-\sin\theta&\cos\theta
\end{pmatrix},
$$

show that

$$
P(\nu_e\to\nu_\mu)
=
\sin^2(2\theta)
\sin^2\left(\frac{\Delta m^2 L}{4E}\right).
$$

<details><summary><strong>Solution</strong></summary>

The amplitude is

$$
\mathcal A_{e\to\mu}
=
\sum_i U_{\mu i}e^{-im_i^2L/(2E)}U_{ei}^*.
$$

With the real two-flavor matrix,

$$
\mathcal A_{e\to\mu}
=
(-\sin\theta)(\cos\theta)e^{-im_1^2L/(2E)}
+ (\cos\theta)(\sin\theta)e^{-im_2^2L/(2E)}.
$$

Thus

$$
\mathcal A_{e\to\mu}
=
\sin\theta\cos\theta
\left(e^{-im_2^2L/(2E)}-e^{-im_1^2L/(2E)}\right).
$$

Taking the absolute square gives

$$
P(\nu_e\to\nu_\mu)
=4\sin^2\theta\cos^2\theta
\sin^2\left(\frac{\Delta m^2L}{4E}\right)
=
\sin^2(2\theta)
\sin^2\left(\frac{\Delta m^2L}{4E}\right).
$$

</details>

### Exercise 4: Count Majorana phases for three neutrinos

A general $3\times3$ unitary matrix has three angles and six phases. Explain why three Majorana neutrinos leave three physical phases, while three Dirac neutrinos leave only one.

<details><summary><strong>Solution</strong></summary>

For Dirac fermions, one may rephase the three charged leptons and the three neutrinos. One common overall phase is irrelevant, so five phases can be removed from the mixing matrix. Starting from six phases, this leaves one physical phase.

For Majorana neutrinos, neutrino rephasings are not freely available because they change the Majorana mass terms. Only the three charged-lepton phases can be used to remove phases from the mixing matrix. Starting from six phases, this leaves three physical phases: one Dirac-type phase and two Majorana phases.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §91, for neutrino masses in the Standard Model context.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 29, for weak interactions, fermion mixing, and CP violation.
- Burgess, *Introduction to Effective Field Theory*, Chs. 7 and 9, for the Fermi theory, Standard Model EFT viewpoint, and neutrino-mass operators.

### Deeper references

- Pontecorvo, “Mesonium and Antimesonium,” and later neutrino-oscillation papers, for the original mixing idea.
- Maki, Nakagawa, and Sakata, “Remarks on the Unified Model of Elementary Particles,” for the lepton mixing matrix in early form.
- Bilenky, *Introduction to the Physics of Massive and Mixed Neutrinos*, for a focused treatment of oscillations, Majorana phases, and neutrino phenomenology.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak theory and neutrino-mass extensions.

## Version history

- **2026-06-19:** Initial page. Added derivation from lepton mass diagonalization, Dirac versus Majorana phase counting, standard parameterization, oscillation probability, exercises, and PMNS mixing figure.
