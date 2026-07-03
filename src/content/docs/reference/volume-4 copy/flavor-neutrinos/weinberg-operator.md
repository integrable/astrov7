---
title: "Weinberg Operator"
description: "Defines the dimension-five Standard Model operator that generates Majorana neutrino masses after electroweak symmetry breaking."
sidebar:
  label: "Weinberg Operator"
  order: 8
level: Graduate
status: "Polished draft"
source: "Srednicki §91; Schwartz Chs. 29–30; Burgess Chs. 7 and 9; Weinberg Vol. II electroweak chapters."
topics:
  - Weinberg operator
  - neutrino masses
  - Majorana mass
  - lepton number violation
  - Standard Model EFT
canonicalTopics:
  - weinberg-operator
  - majorana-neutrino-mass
  - dimension-five-operator
  - lepton-number-violation
researchStatus:
  established:
    - "The Weinberg operator is the leading Standard-Model-gauge-invariant effective operator that gives Majorana masses to neutrinos without adding light fields."
  active:
    - "The operator does not by itself determine its ultraviolet origin, the flavor structure of its coefficient, or which additional degrees of freedom generate it."
---

## Summary

The Weinberg operator is the unique dimension-five operator built only from Standard Model fields that gives neutrinos a mass after electroweak symmetry breaking. In a compact four-component notation, write

$$
\mathcal L_5
=
-\frac{1}{2} C^{(5)}_{ij}
\left(\overline{L_i^c}\,\tilde H^*\right)
\left(\tilde H^\dagger L_j\right)
+\text{h.c.},
$$

where $i,j$ are generation indices,

$$
\tilde H=i\sigma^2H^*,
$$

and $C^{(5)}$ has mass dimension $-1$. After

$$
H\to \frac{1}{\sqrt2}\begin{pmatrix}0\\ v+h\end{pmatrix},
$$

the operator gives the Majorana mass matrix

$$
M_\nu=\frac{v^2}{2}C^{(5)}.
$$

This page explains the gauge contractions, the dimension counting, the lepton-number violation, the relation to the PMNS matrix, and the sense in which the operator is an effective low-energy memory of heavy physics.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Weinberg operator map](/figures/gauge-theories-standard-model/weinberg-operator-map.svg)

<figcaption>

The Weinberg operator combines two lepton doublets and two Higgs doublets into a gauge-invariant dimension-five interaction. After electroweak symmetry breaking, it becomes a Majorana mass matrix for the light neutrinos.

</figcaption>
</figure>

## Prerequisites

You should know [Standard Model Fermion Representations](/gauge-theories-standard-model/flavor-neutrinos/standard-model-fermion-representations/), [Yukawa Couplings](/gauge-theories-standard-model/flavor-neutrinos/yukawa-couplings/), [Fermion Mass Matrices](/gauge-theories-standard-model/flavor-neutrinos/fermion-mass-matrices/), and [PMNS Matrix](/gauge-theories-standard-model/flavor-neutrinos/pmns-matrix/). You should also know the Higgs convention from [Standard Model Higgs Doublet](/gauge-theories-standard-model/higgs-sector/standard-model-higgs-doublet/):

$$
H=\begin{pmatrix}H^+\\ H^0\end{pmatrix},
\qquad
Y(H)=\frac{1}{2},
\qquad
Q=T^3+Y.
$$

## Core idea

The minimal renormalizable Standard Model has no right-handed neutrino field $\nu_R$. Therefore it has no gauge-invariant Dirac neutrino Yukawa coupling of the form

$$
\bar L_L\tilde H\nu_R,
$$

because $\nu_R$ is simply not in the minimal field list. It also has no renormalizable Majorana mass for $\nu_L$, because $\nu_L$ lives inside an $SU(2)_L$ doublet.

The Weinberg operator is the lowest-dimension way to repair this using only Standard Model fields. It is not renormalizable in the old power-counting sense; it is an effective operator suppressed by a heavy scale. But it is perfectly natural in effective field theory:

$$
\mathcal L_{\rm EFT}
=
\mathcal L_{\rm SM}
+\mathcal L_5
+\mathcal O(\Lambda^{-2}).
$$

Its coefficient is a complex symmetric matrix in flavor space. Once the Higgs gets a vacuum expectation value, that matrix becomes the neutrino Majorana mass matrix.

## Setup and conventions

The lepton and Higgs doublets transform as

$$
L_i=
\begin{pmatrix}\nu_{iL}\\ e_{iL}\end{pmatrix}
\sim(\mathbf1,\mathbf2)_{-1/2},
\qquad
H=
\begin{pmatrix}H^+\\ H^0\end{pmatrix}
\sim(\mathbf1,\mathbf2)_{1/2}.
$$

The conjugate Higgs doublet is

$$
\tilde H=i\sigma^2H^*
=
\begin{pmatrix}H^{0*}\\ -H^-\end{pmatrix},
\qquad
\tilde H\sim(\mathbf1,\mathbf2)_{-1/2}.
$$

Thus

$$
\tilde H^\dagger L_i
$$

is an $SU(2)_L$ singlet with hypercharge zero. In two-component notation, the same singlet is often written as

$$
L_iH\equiv \epsilon_{ab}L_i^aH^b,
\qquad
\epsilon_{12}=1,
$$

with the Lorentz spinor contraction between the two $LH$ factors left implicit. Schematically,

$$
\mathcal L_5
=
-\frac{1}{2} C^{(5)}_{ij}(L_iH)(L_jH)+\text{h.c.}
$$

This schematic formula is the one to remember, but it hides two contractions: one in weak isospin and one in spinor space.

## Dimension counting and uniqueness

In four spacetime dimensions,

$$
[L]=\frac32,
\qquad
[H]=1.
$$

Therefore

$$
[(LH)(LH)]=2\left(\frac32+1\right)=5.
$$

The Lagrangian density has dimension four, so the coefficient has dimension

$$
[C^{(5)}]=-1.
$$

It is common to write

$$
C^{(5)}=\frac{\kappa}{\Lambda},
$$

where $\Lambda$ is a heavy scale and $\kappa$ is dimensionless.

Why is this the leading operator? The Standard Model field content, Lorentz invariance, and gauge invariance rule out a neutrino mass operator at dimension three or four. At dimension five, two lepton doublets and two Higgs doublets can be contracted into a gauge singlet. Up to flavor coefficients, integration by parts, and hermitian conjugation, this is the unique baryon-number-conserving dimension-five Standard Model operator.

## Gauge invariance in components

The $SU(2)_L$ contraction

$$
L_iH=\epsilon_{ab}L_i^aH^b
$$

gives

$$
L_iH
=
\nu_{iL}H^0-e_{iL}H^+.
$$

Its hypercharge is

$$
Y(L_iH)=Y(L_i)+Y(H)=-\frac{1}{2}+\frac{1}{2}=0.
$$

Therefore $(L_iH)(L_jH)$ is neutral under $SU(2)_L\times U(1)_Y$ and color neutral automatically. This is why the operator is allowed by Standard Model gauge symmetry even though a bare Majorana mass

$$
\nu_L^T C\nu_L
$$

is not gauge invariant by itself before electroweak symmetry breaking.

## Electroweak symmetry breaking

In unitary gauge,

$$
H=\frac1{\sqrt2}\begin{pmatrix}0\\ v+h\end{pmatrix},
\qquad
\tilde H=\frac1{\sqrt2}\begin{pmatrix}v+h\\0\end{pmatrix}.
$$

Then

$$
\tilde H^\dagger L_i
=
\frac{v+h}{\sqrt2}\nu_{iL}.
$$

The Weinberg operator becomes

$$
\mathcal L_5
\supset
-\frac{1}{2}\left(\frac{v+h}{\sqrt2}\right)^2
C^{(5)}_{ij}\,
\nu_{iL}^T C\nu_{jL}
+\text{h.c.}
$$

Equivalently,

$$
\mathcal L_5
\supset
-\frac{1}{2} (M_\nu)_{ij}\,
\nu_{iL}^T C\nu_{jL}
\left(1+\frac{h}{v}\right)^2
+\text{h.c.},
$$

with

$$
M_\nu=\frac{v^2}{2}C^{(5)}.
$$

This expansion also predicts extremely small Higgs–neutrino interactions proportional to the neutrino mass matrix. The mass term is the central low-energy effect; the $h\nu\nu$ and $hh\nu\nu$ terms are required by electroweak gauge invariance.

## Lepton number violation

Assign lepton number

$$
L(L_i)=1,
\qquad
L(H)=0.
$$

Then

$$
L\big((L_iH)(L_jH)\big)=2.
$$

Thus the Weinberg operator violates total lepton number by two units:

$$
\Delta L=2.
$$

This is the cleanest low-energy distinction between a Majorana mass and a Dirac mass. A Dirac mass pairs independent left-handed and right-handed fields and can conserve lepton number. A Majorana mass identifies a neutral fermion with its charge conjugate and violates any lepton number under which that fermion is charged.

Gauge symmetry alone allows the Weinberg operator. The renormalizable Standard Model accidentally conserves baryon number and lepton number, but these are not imposed by gauge symmetry in the same way that hypercharge is. Effective operators can break accidental symmetries while preserving the gauge symmetry.

## Flavor structure and PMNS mixing

The coefficient matrix satisfies

$$
C^{(5)}_{ij}=C^{(5)}_{ji},
$$

so the neutrino mass matrix is complex symmetric:

$$
M_\nu=M_\nu^T.
$$

It is diagonalized by Takagi factorization,

$$
U_\nu^T M_\nu U_\nu=D_\nu,
\qquad
D_\nu=\operatorname{diag}(m_1,m_2,m_3),
\qquad
m_i\ge0.
$$

The charged lepton mass matrix is diagonalized by

$$
U_{eL}^\dagger M_eU_{eR}=D_e.
$$

The observable lepton mixing matrix is then

$$
U_{\rm PMNS}=U_{eL}^\dagger U_\nu.
$$

In the charged-lepton mass basis, $U_{eL}=1$ and the PMNS matrix is simply the unitary matrix that Takagi-diagonalizes $M_\nu$. In another basis, it is the mismatch between charged-lepton and neutrino diagonalization. The physics is basis independent; the bookkeeping is not.

## Scale estimate

If

$$
C^{(5)}\sim\frac1\Lambda,
$$

then a characteristic neutrino mass is

$$
m_\nu\sim\frac{v^2}{2\Lambda}.
$$

Solving for the scale gives

$$
\Lambda\sim\frac{v^2}{2m_\nu}.
$$

For a representative neutrino mass scale $m_\nu\sim 0.05\,\mathrm{eV}$,

$$
\Lambda\sim 6\times10^{14}\,\mathrm{GeV}
$$

if the dimensionless coefficient is order one. This estimate is not a measurement of the new-physics scale. It is a lesson in hierarchy: very small neutrino masses can come from a very high scale, a small dimensionless coefficient, or both.

## Type-I seesaw as an example

One simple ultraviolet completion adds heavy gauge-singlet fermions $N_R$ with

$$
\mathcal L
\supset
-\bar L Y_\nu\tilde H N_R
-\frac{1}{2}\overline{N_R^c}M_NN_R
+\text{h.c.}
$$

After electroweak symmetry breaking, the Dirac mass matrix is

$$
m_D=\frac{v}{\sqrt2}Y_\nu.
$$

In the basis $(\nu_L,N_R^c)$, the neutral-fermion mass matrix has the block form

$$
\mathcal M=
\begin{pmatrix}
0&m_D\\
m_D^T&M_N
\end{pmatrix}.
$$

If the eigenvalues of $M_N$ are much larger than the entries of $m_D$, the light-neutrino mass matrix is approximately

$$
M_\nu\simeq -m_D M_N^{-1}m_D^T.
$$

The sign is convention dependent and can be absorbed into Majorana phase choices. Comparing with

$$
M_\nu=\frac{v^2}{2}C^{(5)},
$$

one finds the matching, up to the same sign convention,

$$
C^{(5)}\simeq -Y_\nu M_N^{-1}Y_\nu^T.
$$

This is called a seesaw because making $M_N$ large makes the light neutrino masses small. Other common completions generate the same low-energy operator using a heavy scalar triplet or a heavy fermion triplet. The low-energy Weinberg operator does not by itself tell you which completion is correct.

## Common pitfalls

**The schematic expression $(LH)(LH)$ hides contractions.** The two $SU(2)_L$ doublets are contracted with $\epsilon_{ab}$, and the two left-handed spinors are contracted into a Lorentz scalar. Treating $LH$ as an ordinary number misses the point.

**The coefficient is symmetric, not Hermitian.** A Majorana mass matrix is complex symmetric and is diagonalized by Takagi factorization, not by the usual Hermitian diagonalization.

**The operator is gauge invariant before symmetry breaking.** The bare-looking Majorana mass $\nu_L\nu_L$ is not gauge invariant before electroweak symmetry breaking. The Higgs fields in the Weinberg operator are what make the expression legal.

**The Weinberg operator does not require light right-handed neutrinos.** It can arise after heavy fields are integrated out. Adding light or heavy singlet neutrinos is one possible explanation, not part of the operator itself.

**A small neutrino mass does not uniquely imply a huge scale.** The estimate $\Lambda\sim v^2/(2m_\nu)$ assumes an order-one coefficient. Flavor structure, small couplings, loops, or other dynamics can change the inferred scale.

**Oscillations do not prove the Weinberg operator.** Oscillations prove nonzero mass splittings and mixing. The Weinberg operator is the leading Standard-Model-gauge-invariant EFT description if neutrino masses are Majorana and no additional light fields are kept.

## Relations to other pages

This page follows [PMNS Matrix](/gauge-theories-standard-model/flavor-neutrinos/pmns-matrix/) because the Weinberg operator supplies the Majorana mass matrix whose diagonalization enters PMNS mixing. It also completes the chapter’s first pass: Standard Model representations, chirality, Yukawa couplings, mass matrices, CKM mixing, CP violation, PMNS mixing, and neutrino masses.

The next chapter, Standard Model Architecture, assembles this material into the full field content and Lagrangian. The Standard Model consistency chapter later returns to anomaly cancellation, while the Renormalization, RG, and EFT volume treats the Weinberg operator as part of the broader SMEFT operator expansion.

## Research status

The Weinberg operator is a settled EFT statement: given the Standard Model gauge group and field content, it is the leading operator that produces Majorana neutrino masses. Its coefficient is not predicted by Standard Model gauge symmetry.

The operator does not identify the origin of $C^{(5)}$. It could come from heavy singlet fermions, scalar triplets, fermion triplets, loop-level mechanisms, flavor dynamics, extra dimensions, or something more exotic. Low-energy information about neutrino masses and mixing constrains this space of possibilities, but it does not directly read off a unique ultraviolet theory.

## Exercises

### Exercise 1: Check the operator dimension

Use

$$
[L]=\frac32,
\qquad
[H]=1
$$

to show that $(LH)(LH)$ has dimension five and that $C^{(5)}$ has dimension $-1$.

<details><summary><strong>Solution</strong></summary>

Each factor $LH$ has dimension

$$
[LH]=\frac32+1=\frac52.
$$

Therefore

$$
[(LH)(LH)]=2\times\frac52=5.
$$

Since the Lagrangian density has dimension four,

$$
[C^{(5)}]+5=4,
$$

so

$$
[C^{(5)}]=-1.
$$

</details>

### Exercise 2: Check hypercharge conservation

Using

$$
Y(L)=-\frac{1}{2},
\qquad
Y(H)=\frac{1}{2},
$$

show that $(LH)(LH)$ is neutral under $U(1)_Y$.

<details><summary><strong>Solution</strong></summary>

The hypercharge of one $LH$ factor is

$$
Y(LH)=Y(L)+Y(H)=-\frac{1}{2}+\frac{1}{2}=0.
$$

Therefore

$$
Y((LH)(LH))=0+0=0.
$$

The operator is hypercharge neutral.

</details>

### Exercise 3: Derive the Majorana mass matrix after symmetry breaking

Starting from

$$
\mathcal L_5
=
-\frac{1}{2} C^{(5)}_{ij}(L_iH)(L_jH)+\text{h.c.},
$$

use

$$
H\to\frac1{\sqrt2}\begin{pmatrix}0\\v+h\end{pmatrix}
$$

to show that $M_\nu=v^2C^{(5)}/2$.

<details><summary><strong>Solution</strong></summary>

The weak singlet is

$$
L_iH=\nu_{iL}H^0-e_{iL}H^+.
$$

In unitary gauge, $H^+=0$ and $H^0=(v+h)/\sqrt2$, so

$$
L_iH\to \frac{v+h}{\sqrt2}\nu_{iL}.
$$

Thus

$$
\mathcal L_5
\to
-\frac{1}{2} C^{(5)}_{ij}\frac{(v+h)^2}{2}\nu_{iL}\nu_{jL}+\text{h.c.}
$$

The mass term is the part with $v^2$:

$$
\mathcal L_m
=
-\frac{1}{2}\left(\frac{v^2}{2}C^{(5)}_{ij}\right)\nu_{iL}\nu_{jL}+\text{h.c.},
$$

so

$$
M_\nu=\frac{v^2}{2}C^{(5)}.
$$

</details>

### Exercise 4: Obtain the seesaw scaling

For one generation, consider the mass matrix

$$
\mathcal M=
\begin{pmatrix}
0&m_D\\
m_D&M_N
\end{pmatrix},
\qquad
M_N\gg m_D.
$$

Find the approximate light eigenvalue.

<details><summary><strong>Solution</strong></summary>

The eigenvalues satisfy

$$
\lambda^2-M_N\lambda-m_D^2=0.
$$

For $M_N\gg m_D$, the small eigenvalue is approximately

$$
\lambda_{\rm light}\simeq -\frac{m_D^2}{M_N}.
$$

The sign can be absorbed into a Majorana phase convention, so the physical light mass scales as

$$
m_\nu\sim\frac{m_D^2}{M_N}.
$$

With $m_D=vY_\nu/\sqrt2$, this matches the Weinberg-operator scaling

$$
m_\nu\sim\frac{v^2Y_\nu^2}{2M_N}.
$$

</details>

## Where to go next

The flavor chapter ends here. Continue to [Standard Model](/gauge-theories-standard-model/standard-model/) for the synthesis chapter, where the gauge group, field content, Higgs sector, Yukawa sector, accidental symmetries, parameter counting, anomaly constraints, and limitations of the minimal theory are assembled into one QFT.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §91, for neutrino masses in the Standard Model context.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 29–30, for weak interactions, Standard Model fermions, CP violation, and anomalies.
- Burgess, *Introduction to Effective Field Theory*, Chs. 7 and 9, for the Fermi theory, Standard Model EFT, and higher-dimensional neutrino-mass operators.

### Deeper references

- Weinberg, “Baryon- and Lepton-Nonconserving Processes,” for the original dimension-five operator.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak theory and neutrino-mass extensions.
- Minkowski; Gell-Mann, Ramond, and Slansky; Yanagida; and Mohapatra and Senjanović for classic seesaw mechanisms.
- Bilenky, *Introduction to the Physics of Massive and Mixed Neutrinos*, for neutrino mass and mixing phenomenology.

## Version history

- **2026-06-19:** Linked forward to the Standard Model chapter.
- **2026-06-19:** Initial page. Added gauge and Lorentz contractions, dimension counting, electroweak symmetry breaking, lepton-number violation, PMNS relation, scale estimate, type-I seesaw matching, exercises, and Weinberg-operator figure.
