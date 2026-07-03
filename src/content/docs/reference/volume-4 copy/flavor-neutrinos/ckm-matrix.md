---
title: "CKM Matrix"
description: "Explains the origin, parameter counting, standard parametrizations, unitarity relations, and physical meaning of the Cabibbo–Kobayashi–Maskawa matrix in the Standard Model."
sidebar:
  label: "CKM Matrix"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§88–91; Schwartz Chs. 29–31; Weinberg Vol. II electroweak chapters; Burgess Ch. 9."
topics:
  - CKM matrix
  - quark flavor mixing
  - charged weak currents
  - mass basis
  - unitarity triangles
canonicalTopics:
  - ckm-matrix
  - quark-charged-current-mixing
  - flavor-basis-redefinitions
  - ckm-parameter-counting
  - unitarity-triangle
researchStatus:
  established:
    - "In the minimal Standard Model, all tree-level quark flavor changing occurs through the charged weak current and is governed by one unitary CKM matrix."
  active:
    - "Precision tests of CKM unitarity, semileptonic form factors, rare decays, and flavor anomalies remain active probes of physics beyond the Standard Model."
---

## Summary

The Cabibbo–Kobayashi–Maskawa matrix is the unitary matrix that appears in the quark charged weak current after the up- and down-type quark mass matrices are diagonalized. It is not a new gauge coupling and it is not an extra field. It is the surviving mismatch between two allowed choices of flavor basis.

Starting from the gauge-basis charged current,

$$
\bar u_L^{\rm gauge}\gamma^\mu d_L^{\rm gauge},
$$

and using the mass-basis rotations

$$
u_L^{\rm gauge}=U_{uL}u_L^{\rm mass},
\qquad
d_L^{\rm gauge}=U_{dL}d_L^{\rm mass},
$$

one finds

$$
\bar u_L^{\rm gauge}\gamma^\mu d_L^{\rm gauge}
=
\bar u_L^{\rm mass}\gamma^\mu
\left(U_{uL}^\dagger U_{dL}\right)d_L^{\rm mass}.
$$

The CKM matrix is therefore

$$
V_{\rm CKM}=U_{uL}^\dagger U_{dL}.
$$

The quark charged-current interaction in the mass basis is

$$
\mathcal L_{Wqq}
=
-\frac{g}{\sqrt2}\left(
W_\mu^+\bar u_L\gamma^\mu V_{\rm CKM}d_L
+W_\mu^-\bar d_L\gamma^\mu V_{\rm CKM}^\dagger u_L
\right),
$$

where $u_L=(u_L,c_L,t_L)^T$ and $d_L=(d_L,s_L,b_L)^T$ are mass-eigenstate columns. The overall sign follows from the volume convention $D_\mu=\partial_\mu+igW_\mu^aT^a+ig'YB_\mu$; changing the definition of $W^\pm$ can move harmless signs around, but it cannot remove $V_{\rm CKM}$.

<figure class="doc-figure" style="--figure-width: 58rem;">

![CKM matrix from quark mass diagonalization](/figures/gauge-theories-standard-model/ckm-origin-map.svg)

<figcaption>

The CKM matrix is the mismatch between the left-handed rotations that diagonalize the up- and down-type quark mass matrices. Neutral currents compare a rotation with itself and remain diagonal; charged currents compare two different rotations and retain $V_{\rm CKM}=U_{uL}^\dagger U_{dL}$.

</figcaption>
</figure>

For three generations, a general unitary $3\times3$ CKM matrix contains three physical mixing angles and one physical CP-violating phase. The matrix is not predicted by Standard Model gauge symmetry; it is part of the measured flavor data of the Standard Model.

## Prerequisites

You should know [Fermion Mass Matrices](/gauge-theories-standard-model/flavor-neutrinos/fermion-mass-matrices/), especially the biunitary diagonalizations of $M_u$ and $M_d$. You should also know [Weak Charged Current](/gauge-theories-standard-model/electroweak/weak-charged-current/), where the left-handed charged current was derived from the $SU(2)_L$ ladder generators.

The only linear algebra needed here is unitary diagonalization and the idea that field phases can be redefined without changing the kinetic terms. That innocent-looking freedom is the reason that not every complex phase in a unitary matrix is physical.

## Core idea

Gauge interactions are generation universal in the gauge basis. The quark part of the charged weak current begins as

$$
J_{W^+}^{\mu,q}
=
\bar u_L^{\rm gauge}\gamma^\mu d_L^{\rm gauge},
$$

where $u_L^{\rm gauge}$ and $d_L^{\rm gauge}$ are three-component vectors in generation space. The quark mass matrices are diagonalized by

$$
u_L^{\rm gauge}=U_{uL}u_L^{\rm mass},
\qquad
d_L^{\rm gauge}=U_{dL}d_L^{\rm mass}.
$$

Substitution gives

$$
J_{W^+}^{\mu,q}
=
\bar u_L^{\rm mass}\gamma^\mu
\left(U_{uL}^\dagger U_{dL}\right)d_L^{\rm mass}.
$$

Thus

$$
V_{\rm CKM}=U_{uL}^\dagger U_{dL}.
$$

That is the whole origin story. There is no separate “CKM force.” The charged weak interaction couples an up-type and a down-type member of an $SU(2)_L$ doublet; the two mass matrices do not generally choose the same generation axes.

## Gauge basis, mass basis, and physical basis choices

The gauge basis is the basis in which the electroweak representations are simple. The mass basis is the basis in which the quadratic mass terms are diagonal. These bases are related by unitary transformations in generation space.

The quark kinetic terms have a large flavor-basis redundancy before Yukawa matrices are specified:

$$
Q_L\to W_QQ_L,
\qquad
u_R\to W_uu_R,
\qquad
d_R\to W_dd_R,
$$

with $W_Q,W_u,W_d\in U(3)$. The Yukawa matrices transform as

$$
Y_u\to W_QY_uW_u^\dagger,
\qquad
Y_d\to W_QY_dW_d^\dagger.
$$

Physical quantities cannot depend on this choice of weak flavor coordinates. For example, one convenient choice is to diagonalize the up-type mass matrix first, setting $U_{uL}=\mathbf1$ by a basis choice. Then

$$
V_{\rm CKM}=U_{dL}.
$$

Another equally valid choice diagonalizes the down-type mass matrix first, giving

$$
V_{\rm CKM}=U_{uL}^\dagger.
$$

Neither description is more physical. The only invariant statement is the relative rotation $U_{uL}^\dagger U_{dL}$.

## The charged-current Lagrangian

Let

$$
u_L=
\begin{pmatrix}
u_L\\ c_L\\ t_L
\end{pmatrix},
\qquad
d_L=
\begin{pmatrix}
d_L\\ s_L\\ b_L
\end{pmatrix}
$$

be the mass-basis quark vectors. Then the quark charged-current interaction is

$$
\mathcal L_{Wqq}
=
-\frac{g}{\sqrt2}\left(
W_\mu^+\bar u_L\gamma^\mu V_{\rm CKM}d_L
+
W_\mu^-\bar d_L\gamma^\mu V_{\rm CKM}^\dagger u_L
\right).
$$

Written with indices,

$$
\mathcal L_{Wqq}
=
-\frac{g}{\sqrt2}\left(
W_\mu^+\sum_{i,j}\bar u_{iL}\gamma^\mu V_{ij}d_{jL}
+
W_\mu^-\sum_{i,j}\bar d_{jL}\gamma^\mu V_{ij}^*u_{iL}
\right).
$$

The matrix element $V_{ij}$ controls the amplitude for a $W^+$ to couple to $\bar u_i d_j$, or equivalently for a down-type quark $d_j$ to transition into an up-type quark $u_i$ through the charged current. Which process description is used depends on arrow flow, external particles, and crossing; the matrix is the same object.

## Why neutral currents stay diagonal

The neutral gauge currents for a given quark species have the schematic form

$$
\bar f_L^{\rm gauge}\gamma^\mu f_L^{\rm gauge}
=
\bar f_L^{\rm mass}U_{fL}^\dagger\gamma^\mu U_{fL}f_L^{\rm mass}
=
\bar f_L^{\rm mass}\gamma^\mu f_L^{\rm mass},
$$

because $U_{fL}^\dagger U_{fL}=\mathbf1$. The same cancellation occurs for right-handed neutral currents. This is why the photon, gluon, and tree-level $Z$ interactions are flavor diagonal in the Standard Model mass basis.

This tree-level diagonal structure is the beginning of the Glashow–Iliopoulos–Maiani mechanism. Flavor-changing neutral-current processes such as $s\to d$ or $b\to s$ do occur in the Standard Model, but they first arise through loops and are controlled by CKM products and mass splittings. They are therefore unusually sensitive to new physics.

## Unitarity

Since $U_{uL}$ and $U_{dL}$ are unitary, $V_{\rm CKM}$ is unitary:

$$
V^\dagger V=VV^\dagger=\mathbf1.
$$

In components,

$$
\sum_k V_{ki}^*V_{kj}=\delta_{ij},
\qquad
\sum_k V_{ik}V_{jk}^*=\delta_{ij}.
$$

The diagonal relations say that the squared magnitudes in each row or column add to one. The off-diagonal relations say that distinct rows and columns are orthogonal. For example,

$$
V_{ud}V_{ub}^*+V_{cd}V_{cb}^*+V_{td}V_{tb}^*=0.
$$

This is a sum of three complex numbers equal to zero, so it can be drawn as a triangle in the complex plane. Such unitarity triangles are not decorative geometry; their nonzero area is a rephasing-invariant measure of CP violation.

## Parameter count for N generations

An $N\times N$ unitary matrix contains $N^2$ real parameters. These can be organized into

$$
\frac{N(N-1)}{2}
$$

real rotation angles and

$$
\frac{N(N+1)}{2}
$$

phases.

However, not all phases in $V$ are physical. Rephasing the mass eigenstate quarks as

$$
u_i\to e^{i\alpha_i}u_i,
\qquad
d_j\to e^{i\beta_j}d_j
$$

changes the matrix entries by

$$
V_{ij}\to e^{-i\alpha_i}V_{ij}e^{i\beta_j}.
$$

There are $2N$ quark phases, but one common baryon-number phase leaves all $V_{ij}$ unchanged. Thus $2N-1$ phases can be removed. The number of physical phases is

$$
\frac{N(N+1)}{2}-(2N-1)
=
\frac{(N-1)(N-2)}{2}.
$$

So:

| Generations | Mixing angles | CP-violating phases |
|---:|---:|---:|
| $N=1$ | $0$ | $0$ |
| $N=2$ | $1$ | $0$ |
| $N=3$ | $3$ | $1$ |

This is why the existence of three generations is structurally essential for CKM CP violation. With two generations, the Cabibbo angle gives mixing but no irreducible complex phase.

## Standard parameterization

A common parameterization writes the CKM matrix in terms of three angles $\theta_{12},\theta_{23},\theta_{13}$ and one phase $\delta$. Define

$$
s_{ij}=\sin\theta_{ij},
\qquad
c_{ij}=\cos\theta_{ij}.
$$

Then

$$
V_{\rm CKM}
=
\begin{pmatrix}
c_{12}c_{13} & s_{12}c_{13} & s_{13}e^{-i\delta}\\
-s_{12}c_{23}-c_{12}s_{23}s_{13}e^{i\delta} &
c_{12}c_{23}-s_{12}s_{23}s_{13}e^{i\delta} &
s_{23}c_{13}\\
s_{12}s_{23}-c_{12}c_{23}s_{13}e^{i\delta} &
-c_{12}s_{23}-s_{12}c_{23}s_{13}e^{i\delta} &
c_{23}c_{13}
\end{pmatrix}.
$$

This is a convention, not a law of nature. Rephasing quark fields moves phases among entries. The invariant content is the set of moduli, unitarity relations, and CP-odd rephasing invariants such as the Jarlskog invariant discussed on the next page.

## A useful small-mixing picture

Empirically, the CKM matrix is close to the identity matrix: transitions within the same generation are largest, transitions between neighboring generations are smaller, and transitions between the first and third generations are smallest. One often organizes this pattern with a small parameter, traditionally called $\lambda$, but the exact numerical values belong in a date-stamped reference table rather than in this conceptual page.

The qualitative hierarchy matters because it explains why some weak decays are common while others are rare. It also makes flavor physics an excellent interferometer: small Standard Model amplitudes can be unusually sensitive to additional heavy degrees of freedom.

## Common pitfalls

**Thinking CKM is a new interaction.** It is not. CKM is the mismatch between two mass diagonalizations inside the ordinary charged weak current.

**Putting CKM in neutral currents.** Tree-level neutral currents remain diagonal because the same unitary rotation appears on both sides of a neutral current. Flavor-changing neutral currents first appear through loops in the minimal Standard Model.

**Treating every complex phase as physical.** Many phases can be removed by rephasing quark fields. For three generations, only one CKM phase is physical.

**Forgetting that parameterizations are conventions.** The standard parameterization is convenient, but a different rephasing convention can place the complex phase in different entries.

**Confusing CKM entries with decay rates.** CKM factors multiply amplitudes. Actual rates also depend on matrix elements, kinematics, QCD, and radiative corrections.

## Relations to other pages

This page follows [Fermion Mass Matrices](/gauge-theories-standard-model/flavor-neutrinos/fermion-mass-matrices/) and prepares [CP Violation](/gauge-theories-standard-model/flavor-neutrinos/cp-violation/). The electroweak interaction itself was derived in [Weak Charged Current](/gauge-theories-standard-model/electroweak/weak-charged-current/), while the loop-level suppression of neutral flavor change belongs later in precision and flavor-EFT pages.

The lepton-sector analogue appears in [PMNS Matrix](/gauge-theories-standard-model/flavor-neutrinos/pmns-matrix/), but with an important twist: neutrino masses are not part of the minimal renormalizable Standard Model field content.

## Research status

The CKM framework is an established part of the Standard Model. Its conceptual status is clean: one unitary matrix describes quark mixing in charged currents. The frontier is precision. Overconstraining CKM unitarity with beta decays, kaon decays, charm physics, $B$ physics, top physics, and loop-dominated processes tests whether all flavor data truly fit the minimal Standard Model pattern.

The deeper flavor puzzle remains open: the Standard Model permits the observed quark masses and mixings but does not explain their numerical hierarchy.

## Exercises

### Exercise 1: Derive the CKM matrix from the charged current

Starting from $J_{W^+}^{\mu,q}=\bar u_L^{\rm gauge}\gamma^\mu d_L^{\rm gauge}$ and the field redefinitions $u_L^{\rm gauge}=U_{uL}u_L$ and $d_L^{\rm gauge}=U_{dL}d_L$, derive $V=U_{uL}^\dagger U_{dL}$.

<details><summary><strong>Solution</strong></summary>

The conjugate field transforms as

$$
\bar u_L^{\rm gauge}=\bar u_LU_{uL}^\dagger.
$$

Therefore

$$
J_{W^+}^{\mu,q}
=
\bar u_LU_{uL}^\dagger\gamma^\mu U_{dL}d_L.
$$

The unitary matrices act in generation space and commute with $\gamma^\mu$, so

$$
J_{W^+}^{\mu,q}
=
\bar u_L\gamma^\mu(U_{uL}^\dagger U_{dL})d_L.
$$

Thus $V=U_{uL}^\dagger U_{dL}$.

</details>

### Exercise 2: Count CKM phases

Show that an $N$-generation CKM matrix has $(N-1)(N-2)/2$ physical phases.

<details><summary><strong>Solution</strong></summary>

An $N\times N$ unitary matrix has $N^2$ real parameters, of which $N(N-1)/2$ may be taken as angles. The remaining $N(N+1)/2$ are phases. Rephasing the $N$ up-type and $N$ down-type mass eigenstates removes $2N-1$ phases, because one common baryon-number phase leaves $V$ unchanged. Hence the number of physical phases is

$$
\frac{N(N+1)}{2}-(2N-1)
=
\frac{(N-1)(N-2)}{2}.
$$

For $N=3$, this gives one physical CP-violating phase.

</details>

### Exercise 3: Show a unitarity-triangle relation

Use $V^\dagger V=1$ to derive

$$
V_{ud}V_{ub}^*+V_{cd}V_{cb}^*+V_{td}V_{tb}^*=0.
$$

<details><summary><strong>Solution</strong></summary>

The relation $V^\dagger V=1$ gives column orthogonality:

$$
\sum_i V_{id}^*V_{ib}=0.
$$

Taking the complex conjugate gives

$$
\sum_i V_{id}V_{ib}^*=0.
$$

With $i=u,c,t$, this is

$$
V_{ud}V_{ub}^*+V_{cd}V_{cb}^*+V_{td}V_{tb}^*=0.
$$

</details>

### Exercise 4: Why two generations cannot have CKM CP violation

Use the phase-counting formula to explain why a two-generation quark sector can have mixing but no irreducible CP-violating CKM phase.

<details><summary><strong>Solution</strong></summary>

For $N=2$, the number of mixing angles is

$$
\frac{N(N-1)}{2}=1,
$$

while the number of physical phases is

$$
\frac{(N-1)(N-2)}{2}=0.
$$

Thus two generations allow one real mixing angle, the Cabibbo angle, but all phases in the $2\times2$ unitary matrix can be removed by rephasing the quark fields.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§88–91 for the Standard Model lepton, quark, electroweak, and neutrino sectors.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 29 for weak interactions, the fermion sector, and CP violation.
- Burgess, *Introduction to Effective Field Theory*, Ch. 9 for Standard Model field content, symmetries, and the EFT viewpoint.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for a systematic treatment of electroweak theory and fermion mixing.
- Cabibbo, “Unitary Symmetry and Leptonic Decays,” for the original two-generation mixing angle.
- Kobayashi and Maskawa, “CP-Violation in the Renormalizable Theory of Weak Interaction,” for the three-generation origin of irreducible CKM CP violation.
- Branco, Lavoura, and Silva, *CP Violation*, for flavor-basis invariants and detailed CKM phenomenology.

## Version history

- **2026-06-19:** Initial page. Added derivation from mass diagonalization, charged-current form, neutral-current cancellation, unitarity relations, parameter counting, standard parameterization, exercises, and CKM-origin map figure.
