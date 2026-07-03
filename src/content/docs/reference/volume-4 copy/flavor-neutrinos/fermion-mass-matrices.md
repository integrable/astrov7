---
title: "Fermion Mass Matrices"
description: "Explains how Standard Model Yukawa matrices become fermion mass matrices, how biunitary diagonalization defines mass eigenstates, and why left-handed misalignment produces CKM mixing."
sidebar:
  label: "Fermion Mass Matrices"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki §§88–91; Schwartz Chs. 29–31; Burgess Ch. 9; Weinberg Vol. II electroweak chapters."
topics:
  - fermion mass matrices
  - biunitary diagonalization
  - mass eigenstates
  - CKM matrix
  - Higgs flavor alignment
canonicalTopics:
  - fermion-mass-matrix-diagonalization
  - mass-basis-vs-gauge-basis
  - ckm-origin
  - higgs-yukawa-alignment
researchStatus:
  established:
    - "The charged-fermion mass matrices of the minimal Standard Model are proportional to the Yukawa matrices and can be diagonalized by unitary rotations of left- and right-chiral fields."
  active:
    - "The observed eigenvalue hierarchy and mixing pattern are not predicted by the minimal Standard Model and motivate flavor-model and EFT investigations."
---

## Summary

After electroweak symmetry breaking, the Standard Model Yukawa matrices become charged-fermion mass matrices,

$$
M_u=\frac{v}{\sqrt2}Y_u,
\qquad
M_d=\frac{v}{\sqrt2}Y_d,
\qquad
M_e=\frac{v}{\sqrt2}Y_e.
$$

These matrices are general complex $3\times3$ matrices. They are not usually Hermitian and should not be diagonalized by a single unitary matrix. The correct statement is the singular-value, or biunitary, diagonalization:

$$
U_{fL}^\dagger M_fU_{fR}
=
M_f^{\rm diag}
=
\operatorname{diag}(m_{f1},m_{f2},m_{f3}),
\qquad
m_{fi}\ge0.
$$

The corresponding field redefinition is

$$
f_L^{\rm gauge}=U_{fL}f_L^{\rm mass},
\qquad
f_R^{\rm gauge}=U_{fR}f_R^{\rm mass}.
$$

Neutral gauge interactions remain flavor diagonal because the same unitary matrix appears on both sides of a neutral current. Charged weak currents compare two different left-handed rotations. In the quark sector this mismatch is

$$
V_{\rm CKM}=U_{uL}^\dagger U_{dL}.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![Fermion mass diagonalization and charged-current mixing](/figures/gauge-theories-standard-model/fermion-mass-diagonalization-map.svg)

<figcaption>

Yukawa matrices become mass matrices after the Higgs vacuum is inserted. Each mass matrix is diagonalized by independent left- and right-handed unitary rotations. Neutral currents are unchanged by these unitary rotations, but the charged weak current compares the up-type and down-type left rotations, leaving the physical CKM matrix.

</figcaption>
</figure>

The mass basis is not a different theory. It is the basis in which propagation is diagonal. The price of making masses simple is that charged weak interactions remember the mismatch between the diagonalizations.

## Prerequisites

You should know [Yukawa Couplings](/gauge-theories-standard-model/flavor-neutrinos/yukawa-couplings/), especially the relation $M_f=vY_f/\sqrt2$. You should also know [Weak Charged Current](/gauge-theories-standard-model/electroweak/weak-charged-current/) and [Weak Neutral Current](/gauge-theories-standard-model/electroweak/weak-neutral-current/), since the whole point of the mass basis is to see which gauge interactions do and do not acquire flavor matrices.

The linear-algebra input is the singular-value decomposition: for any complex matrix $M$, there are unitary matrices $U_L,U_R$ such that $U_L^\dagger MU_R$ is diagonal with nonnegative entries.

## Core idea

There are two natural bases for fermions.

The **gauge basis** is the basis in which the electroweak representation assignments and gauge interactions are simple. Before Yukawa matrices are diagonalized, the charged weak current has the schematic form

$$
J_{W^+}^\mu
=
\bar u_L^{\rm gauge}\gamma^\mu d_L^{\rm gauge}
+
\bar\nu_L^{\rm gauge}\gamma^\mu e_L^{\rm gauge}.
$$

The **mass basis** is the basis in which the quadratic mass terms are diagonal and particles propagate with definite masses. For charged fermions it is defined by diagonalizing $M_u,M_d,M_e$.

If all mass matrices were already diagonal in the same gauge basis, flavor would be boring. Nature is not that kind. The up- and down-type quark mass matrices are diagonalized by different left-handed rotations, and the charged weak current is sensitive to that difference. That is the origin of the CKM matrix.

## Mass terms after symmetry breaking

The charged-fermion mass Lagrangian is

$$
\mathcal L_m
=
-\bar u_LM_uu_R
-\bar d_LM_dd_R
-\bar e_LM_ee_R
+\mathrm{h.c.}
$$

The fields here are still in a gauge basis. The matrices $M_f$ are arbitrary complex matrices in generation space. The Hermitian conjugate terms are needed because the displayed terms connect left- and right-chiral fields:

$$
-\bar f_LM_ff_R+\mathrm{h.c.}
=
-\bar f_LM_ff_R-\bar f_RM_f^\dagger f_L.
$$

A common repair is to combine the chiral fields into a four-component Dirac vector after diagonalization. But before diagonalization, the matrix structure is clearer in chiral notation.

For each charged fermion species $f=u,d,e$, choose unitary matrices $U_{fL}$ and $U_{fR}$ such that

$$
U_{fL}^\dagger M_fU_{fR}=M_f^{\rm diag}.
$$

Then define the mass-basis fields by

$$
f_L^{\rm gauge}=U_{fL}f_L^{\rm mass},
\qquad
f_R^{\rm gauge}=U_{fR}f_R^{\rm mass}.
$$

Substitution gives

$$
-\bar f_L^{\rm gauge}M_ff_R^{\rm gauge}
=
-\bar f_L^{\rm mass}U_{fL}^\dagger M_fU_{fR}f_R^{\rm mass}
=
-\bar f_L^{\rm mass}M_f^{\rm diag}f_R^{\rm mass}.
$$

The diagonal entries are chosen nonnegative by rephasing the fields. They are the physical charged-fermion masses at tree level, subject to the usual distinction between running masses and pole masses in a renormalized quantum theory.

## Why a single unitary matrix is not enough

A general complex mass matrix is not Hermitian:

$$
M_f^\dagger\ne M_f
$$

in a generic gauge basis. Therefore one should not try to write

$$
U^\dagger M_fU=M_f^{\rm diag}
$$

unless $M_f$ happens to be normal. The mass term connects two independent vector spaces: left-chiral fields and right-chiral fields. The correct diagonalization uses one unitary matrix acting on the left and one acting on the right.

Equivalently, $M_fM_f^\dagger$ and $M_f^\dagger M_f$ are Hermitian and are diagonalized by different unitary matrices:

$$
U_{fL}^\dagger M_fM_f^\dagger U_{fL}=(M_f^{\rm diag})^2,
$$

$$
U_{fR}^\dagger M_f^\dagger M_f U_{fR}=(M_f^{\rm diag})^2.
$$

The nonnegative masses are the square roots of the eigenvalues of either Hermitian matrix. This is just singular-value decomposition wearing a QFT hat.

## Gauge interactions in the mass basis

The kinetic terms are invariant under constant unitary rotations in generation space. For example,

$$
\bar f_L^{\rm gauge}i\gamma^\mu D_\mu f_L^{\rm gauge}
=
\bar f_L^{\rm mass}U_{fL}^\dagger i\gamma^\mu D_\mu U_{fL}f_L^{\rm mass}.
$$

For gauge interactions that are generation universal and act as the identity in flavor space, the unitary matrices cancel:

$$
U_{fL}^\dagger U_{fL}=\mathbf1.
$$

This is why photon, gluon, and tree-level $Z$ interactions remain flavor diagonal in the charged-fermion mass basis. Neutral currents do not compare $U_{uL}$ with $U_{dL}$; they compare a unitary matrix with itself.

The charged weak current is different. In the gauge basis, the quark part is

$$
J_{W^+}^{\mu,q}
=
\bar u_L^{\rm gauge}\gamma^\mu d_L^{\rm gauge}.
$$

Using

$$
u_L^{\rm gauge}=U_{uL}u_L^{\rm mass},
\qquad
d_L^{\rm gauge}=U_{dL}d_L^{\rm mass},
$$

we get

$$
J_{W^+}^{\mu,q}
=
\bar u_L^{\rm mass}U_{uL}^\dagger U_{dL}\gamma^\mu d_L^{\rm mass}.
$$

Since flavor matrices commute with the Dirac matrices, this is usually written as

$$
J_{W^+}^{\mu,q}
=
\bar u_L^{\rm mass}\gamma^\mu V_{\rm CKM}d_L^{\rm mass},
\qquad
V_{\rm CKM}=U_{uL}^\dagger U_{dL}.
$$

The right-handed rotations $U_{uR}$ and $U_{dR}$ do not enter because the Standard Model charged weak current couples only to left-chiral doublets.

## Charged leptons

For the charged-lepton mass matrix, choose

$$
U_{eL}^\dagger M_eU_{eR}=M_e^{\rm diag}.
$$

If neutrinos are massless and no additional lepton-number-violating interaction is present, one may rotate the neutrino fields together with the lepton doublets so that no physical lepton mixing matrix appears in charged currents. In that minimal limit, the charged-lepton masses are physical, but the leptonic analogue of CKM can be removed by field redefinitions.

Once neutrino masses are introduced, this changes. The diagonalization of the neutrino mass matrix is not generally aligned with $U_{eL}$. Their mismatch produces the PMNS matrix. That belongs to the later neutrino pages; here the main lesson is that mixing matrices come from comparing diagonalization matrices, not from adding an extra gauge interaction by hand.

## Higgs couplings in the mass basis

The Yukawa page showed that before diagonalization

$$
\mathcal L_{hff}
=
-\frac{h}{v}
\left(
\bar u_LM_uu_R+\bar d_LM_dd_R+\bar e_LM_ee_R
\right)
+\mathrm{h.c.}
$$

Using the same rotations that diagonalize the mass terms gives

$$
\mathcal L_{hff}
=
-\sum_{f=u,d,e}\sum_i\frac{m_{fi}}{v}h\bar f_i f_i.
$$

This is the Standard Model flavor alignment of Higgs couplings. The matrix that multiplies $h$ is the same matrix that multiplies $v$. Therefore, after moving to the mass basis, the Higgs couplings are diagonal at tree level.

This statement is special. In a generic theory with several Higgs doublets or additional scalar flavor structures, the matrix that gives mass and the matrix that couples a physical scalar need not be diagonalized by the same rotations. Then tree-level flavor-changing neutral scalar couplings can appear. The minimal Standard Model avoids them because one Higgs doublet supplies all charged-fermion masses.

## A compact parameter count

The quark Yukawa sector contains two complex $3\times3$ matrices, $Y_u$ and $Y_d$, so it starts with

$$
2\times 9\text{ complex}=36\text{ real parameters}.
$$

The quark kinetic terms allow independent unitary rotations

$$
U(3)_Q\times U(3)_u\times U(3)_d.
$$

These contain $27$ real transformation parameters. One overall baryon-number phase leaves both Yukawa matrices unchanged, so only $26$ of them remove Yukawa parameters. The quark sector therefore has

$$
36-26=10
$$

physical parameters: six quark masses, three CKM mixing angles, and one CKM CP-violating phase. This count is developed in more detail on the CKM and CP-violation pages.

For charged leptons alone, $Y_e$ can be diagonalized so that only three charged-lepton masses remain. Neutrino masses add new parameters and new physical mixing.

## Common pitfalls

**Diagonalizing a general mass matrix with one unitary matrix.** A generic fermion mass matrix maps right-chiral fields to left-chiral fields. It requires two unitary rotations. Use singular values, not ordinary eigenvalues, for physical masses.

**Calling the gauge basis “wrong.”** The gauge basis is the natural basis for representation theory and currents. The mass basis is the natural basis for propagation. Physics is basis-independent; the useful basis depends on the question.

**Expecting neutral currents to contain CKM.** Neutral currents contain $U^\dagger U=1$ for a single species. Charged currents contain $U_{uL}^\dagger U_{dL}$ because they connect two species inside a weak doublet.

**Forgetting right-handed rotations.** They are needed to diagonalize masses, even though they do not appear in the Standard Model charged weak current.

**Confusing running masses with pole masses.** The tree-level formula $m_f=y_fv/\sqrt2$ is the starting point. In the quantum theory, masses and Yukawa couplings depend on the renormalization scheme and scale unless a physical pole mass or other observable definition is specified.

## Relations to other pages

This page follows [Yukawa Couplings](/gauge-theories-standard-model/flavor-neutrinos/yukawa-couplings/) and supplies the linear algebra needed for [CKM Matrix](/gauge-theories-standard-model/flavor-neutrinos/ckm-matrix/) and [CP Violation](/gauge-theories-standard-model/flavor-neutrinos/cp-violation/). The lepton-sector version continues in [PMNS Matrix](/gauge-theories-standard-model/flavor-neutrinos/pmns-matrix/) and [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/).

The Higgs alignment statement connects back to [Higgs Boson Couplings](/gauge-theories-standard-model/higgs-sector/higgs-boson-couplings/), while the absence of tree-level neutral flavor change connects forward to precision and flavor-EFT pages.

## Research status

The diagonalization of charged-fermion mass matrices and the emergence of the CKM matrix are established parts of the Standard Model. What remains unexplained is the pattern: why the eigenvalues are so hierarchical, why quark mixing angles are small, why the CKM CP phase has its observed size, and why lepton mixing looks different once neutrino masses are included.

These questions are often called the flavor puzzle. They are not inconsistencies. They are places where the minimal Standard Model trades explanation for parameters.

## Exercises

### Exercise 1: Verify the mass-basis transformation

Starting from $-\bar f_L^{\rm gauge}M_ff_R^{\rm gauge}$ and the field redefinitions $f_L^{\rm gauge}=U_{fL}f_L^{\rm mass}$ and $f_R^{\rm gauge}=U_{fR}f_R^{\rm mass}$, derive the diagonal mass term.

<details><summary><strong>Solution</strong></summary>

The conjugate field transforms as

$$
\bar f_L^{\rm gauge}=\bar f_L^{\rm mass}U_{fL}^\dagger.
$$

Therefore

$$
-\bar f_L^{\rm gauge}M_ff_R^{\rm gauge}
=
-\bar f_L^{\rm mass}U_{fL}^\dagger M_fU_{fR}f_R^{\rm mass}
=
-\bar f_L^{\rm mass}M_f^{\rm diag}f_R^{\rm mass}.
$$

</details>

### Exercise 2: Derive CKM from the charged current

Use $u_L^{\rm gauge}=U_{uL}u_L^{\rm mass}$ and $d_L^{\rm gauge}=U_{dL}d_L^{\rm mass}$ to show that $\bar u_L^{\rm gauge}\gamma^\mu d_L^{\rm gauge}$ contains $V_{\rm CKM}=U_{uL}^\dagger U_{dL}$.

<details><summary><strong>Solution</strong></summary>

Substitution gives

$$
\bar u_L^{\rm gauge}\gamma^\mu d_L^{\rm gauge}
=
\bar u_L^{\rm mass}U_{uL}^\dagger\gamma^\mu U_{dL}d_L^{\rm mass}.
$$

The unitary matrices act on generation space and commute with $\gamma^\mu$, so

$$
\bar u_L^{\rm gauge}\gamma^\mu d_L^{\rm gauge}
=
\bar u_L^{\rm mass}\gamma^\mu
(U_{uL}^\dagger U_{dL})d_L^{\rm mass}.
$$

Thus $V_{\rm CKM}=U_{uL}^\dagger U_{dL}$.

</details>

### Exercise 3: Show that neutral currents stay diagonal

Let $f_L^{\rm gauge}=U_{fL}f_L^{\rm mass}$. Show that $\bar f_L^{\rm gauge}\gamma^\mu f_L^{\rm gauge}$ has no flavor matrix.

<details><summary><strong>Solution</strong></summary>

Substituting gives

$$
\bar f_L^{\rm gauge}\gamma^\mu f_L^{\rm gauge}
=
\bar f_L^{\rm mass}U_{fL}^\dagger\gamma^\mu U_{fL}f_L^{\rm mass}
=
\bar f_L^{\rm mass}\gamma^\mu f_L^{\rm mass},
$$

because $U_{fL}^\dagger U_{fL}=1$ and the unitary matrices act only in generation space. Neutral currents compare the same rotation with itself.

</details>

### Exercise 4: Count quark-sector physical parameters

Explain why two complex $3\times3$ Yukawa matrices contain $36$ real parameters and why the physical quark sector contains $10$ parameters.

<details><summary><strong>Solution</strong></summary>

Each complex $3\times3$ matrix has $9$ complex entries, or $18$ real parameters. Two such matrices have $36$. The kinetic terms allow $U(3)_Q\times U(3)_u\times U(3)_d$ basis rotations, containing $3\times9=27$ real parameters. One overall baryon-number phase is an exact symmetry and cannot be used to remove Yukawa data, so $26$ parameters are removable. The physical count is

$$
36-26=10.
$$

These are six quark masses, three CKM angles, and one CKM phase.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§88–91 for Standard Model lepton, quark, electroweak, and neutrino sectors.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 29 for weak interactions and flavor mixing, and Ch. 31 for precision/flavor context.
- Burgess, *Introduction to Effective Field Theory*, Ch. 9 for the Standard Model as an effective theory and parameter organization beyond the renormalizable level.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for a systematic treatment of electroweak symmetry breaking and fermion masses.
- Georgi, *Weak Interactions and Modern Particle Theory*, for a concise route from mass matrices to weak charged-current mixing.
- Branco, Lavoura, and Silva, *CP Violation*, for a detailed treatment of flavor bases, rephasings, and CP-odd invariants.

## Version history

- **2026-06-19:** Initial page. Added biunitary diagonalization, gauge-basis versus mass-basis discussion, CKM origin, neutral-current cancellation, Higgs alignment, parameter counting, exercises, and mass-diagonalization map figure.
