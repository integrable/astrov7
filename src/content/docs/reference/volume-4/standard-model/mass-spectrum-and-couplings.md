---
title: "Mass Spectrum and Couplings"
description: "Derives the tree-level Standard Model mass spectrum and coupling dictionary after electroweak symmetry breaking, including gauge bosons, Higgs boson, fermions, charged currents, neutral currents, and Higgs couplings."
sidebar:
  label: "Mass Spectrum and Couplings"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–91; Schwartz Chs. 29–31; Burgess Chs. 7 and 9; Weinberg Vol. II electroweak and Standard Model material."
topics:
  - Standard Model spectrum
  - electroweak symmetry breaking
  - W boson
  - Z boson
  - photon
  - Higgs couplings
  - fermion masses
canonicalTopics:
  - standard-model-mass-spectrum
  - electroweak-mass-basis
  - standard-model-couplings
  - higgs-couplings
  - weak-neutral-current
researchStatus:
  established:
    - "The tree-level mass and coupling relations follow from the Higgs vacuum, gauge invariance, and Yukawa matrices; loop-level precision work then specifies the renormalization scheme and measured input set."
  active:
    - "The minimal Standard Model does not explain the numerical pattern of fermion masses, mixing angles, neutrino masses, or the hierarchy between the Higgs scale and possible ultraviolet scales."
---

## Summary

The Standard Model is written most compactly in the **gauge basis**, but experiments see particles in the **mass basis**. Electroweak symmetry breaking is the dictionary between them.

In unitary gauge,

$$
H(x)=
\frac1{\sqrt2}
\begin{pmatrix}
0\\
v+h(x)
\end{pmatrix},
$$

and the tree-level spectrum becomes

$$
\begin{array}{c|c}
\text{field} & \text{tree-level mass}\\
\hline
8\text{ gluons }G_\mu^A & 0\\
\text{photon }A_\mu & 0\\
W^\pm_\mu & M_W=\frac12gv\\
Z_\mu & M_Z=\frac12\sqrt{g^2+g'^2}\,v\\
h & m_h=\sqrt{2\lambda}\,v\\
f & m_f=\frac{y_f v}{\sqrt2}\text{ after diagonalizing Yukawas}
\end{array}
$$

The two massless vector boson sectors are protected by unbroken gauge symmetries:

$$
SU(3)_c\times U(1)_{\rm em}.
$$

Everything else massive in the electroweak gauge sector gets its mass from the Higgs kinetic term, not from an explicit Proca mass.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Standard Model mass spectrum and coupling map](/figures/gauge-theories-standard-model/standard-model-mass-spectrum-coupling-map.svg)

<figcaption>

Electroweak symmetry breaking turns the gauge-basis fields $W^1,W^2,W^3,B$ and the Higgs doublet $H$ into the mass-basis fields $W^\pm,Z,A,h$ plus fermion mass eigenstates. The same vacuum expectation value $v$ controls $M_W$, $M_Z$, fermion masses, and the leading Higgs couplings.

</figcaption>
</figure>

This page gives the tree-level dictionary. Precision calculations refine it with loop corrections, scheme choices, and experimentally chosen input parameters. The tree-level dictionary remains the skeleton.

## Prerequisites

You should know [Electroweak Symmetry Breaking](/gauge-theories-standard-model/electroweak/electroweak-symmetry-breaking/), [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/), [Gauge-Boson Masses](/gauge-theories-standard-model/higgs-sector/gauge-boson-masses/), [Higgs Boson Couplings](/gauge-theories-standard-model/higgs-sector/higgs-boson-couplings/), [Fermion Mass Matrices](/gauge-theories-standard-model/flavor-neutrinos/fermion-mass-matrices/), and [CKM Matrix](/gauge-theories-standard-model/flavor-neutrinos/ckm-matrix/).

We use

$$
Q=T^3+Y,
\qquad
D_\mu
=
\partial_\mu
+ig_sG_\mu^AT_c^A
+igW_\mu^IT_L^I
+ig'YB_\mu,
$$

and the Higgs potential convention

$$
V(H)=-\mu^2H^\dagger H+\lambda(H^\dagger H)^2,
\qquad
v^2=\frac{\mu^2}{\lambda}.
$$

## What “spectrum” means here

At tree level, “mass spectrum” means the eigenvalues of the quadratic part of the Lagrangian after expanding around the Higgs vacuum and diagonalizing fields. In a gauge theory, this phrase needs three caveats.

First, gauge-dependent fields are not all physical particles. In $R_\xi$ gauges, Goldstone and ghost fields appear with gauge-dependent masses. They are useful in calculations but are not physical asymptotic particles.

Second, quarks are not observed as isolated asymptotic states because of confinement. The quark masses in the Lagrangian are still physical parameters, but their precise numerical definitions depend on the renormalization scheme. A pole-mass language is especially delicate for colored particles.

Third, loop corrections shift relations among masses and couplings. The equations on this page are tree-level relations in the classical Lagrangian. Precision pages later explain how to choose input schemes such as $\alpha$, $G_F$, and $M_Z$.

## Gauge bosons before symmetry breaking

Before electroweak symmetry breaking, the gauge fields are

$$
G_\mu^A,\qquad W_\mu^I,\qquad B_\mu,
$$

with

$$
A=1,\dots,8,\qquad I=1,2,3.
$$

The gauge kinetic terms do not contain ordinary mass terms. A term such as

$$
\frac12M^2 W_\mu^IW^{I\mu}
$$

would not be invariant under the full $SU(2)_L$ gauge symmetry. The masses must come from the covariant Higgs kinetic term

$$
(D_\mu H)^\dagger(D^\mu H).
$$

The unbroken gauge group after the Higgs vacuum is

$$
SU(3)_c\times U(1)_{\rm em}.
$$

Therefore the gluons and photon remain massless at this stage:

$$
M_g=0,\qquad M_\gamma=0.
$$

The statement $M_\gamma=0$ is not an accident of diagonalizing a matrix. It is protected by the exact unbroken electromagnetic gauge symmetry.

## Charged gauge bosons

Define

$$
W^\pm_\mu
=
\frac{1}{\sqrt2}
\left(W_\mu^1\mp iW_\mu^2\right).
$$

Expanding $(D_\mu H)^\dagger(D^\mu H)$ around the vacuum gives the charged mass term

$$
M_W^2 W^+_\mu W^{-\mu},
$$

with

$$
M_W=\frac12gv.
$$

The charged $W^\pm$ bosons are massive spin-one particles with electric charges

$$
Q(W^\pm)=\pm1.
$$

Their interactions with fermions are purely left-handed at the gauge-interaction level. In the mass basis,

$$
\mathcal L_{Wff}
=
\frac{g}{\sqrt2}
\left[
W^+_\mu
\left(
\bar u_L\gamma^\mu V_{\rm CKM}d_L
+
\bar\nu_L\gamma^\mu e_L
\right)
+\text{h.c.}
\right],
$$

for the minimal massless-neutrino theory. If neutrino masses are included, the lepton charged current contains the PMNS matrix.

This single formula is where many qualitative facts come from: charged-current weak interactions change weak isospin, act only on left-handed fermions before mass insertions, and carry CKM or PMNS mixing in the mass basis.

## Neutral gauge bosons

The neutral electroweak fields $W^3_\mu$ and $B_\mu$ mix. Define the weak mixing angle by

$$
\tan\theta_W=\frac{g'}{g},
$$

and write

$$
s_W=\sin\theta_W,\qquad c_W=\cos\theta_W.
$$

The mass eigenstates are

$$
A_\mu=s_WW^3_\mu+c_WB_\mu,
$$

and

$$
Z_\mu=c_WW^3_\mu-s_WB_\mu.
$$

The photon is massless,

$$
M_A=0,
$$

while the $Z$ boson has

$$
M_Z=\frac12\sqrt{g^2+g'^2}\,v.
$$

The electromagnetic coupling is

$$
e=gs_W=g'c_W.
$$

At tree level,

$$
M_W=M_Zc_W,
$$

or equivalently

$$
\rho
=
\frac{M_W^2}{M_Z^2c_W^2}=1.
$$

This relation is a consequence of the Higgs being a complex $SU(2)_L$ doublet with $Y=1/2$. It is not true for arbitrary Higgs representations.

## Photon and Z couplings

The photon couples to the conserved electromagnetic current:

$$
\mathcal L_{\rm em}
=
eA_\mu J_{\rm em}^\mu,
\qquad
J_{\rm em}^\mu
=
\sum_f Q_f\bar f\gamma^\mu f.
$$

With the sign convention for the covariant derivative used in this volume, signs in the interaction Lagrangian depend on whether one writes $\mathcal L=\bar\psi i\gamma^\mu D_\mu\psi$ or extracts the vertex factor. The invariant content is the charge assignment and the coupling magnitude $eQ_f$.

The $Z$ boson couples to the neutral current

$$
\mathcal L_Z
=
\frac{g}{c_W}Z_\mu
\sum_f
\bar f\gamma^\mu
\left[
(T^3_f-Q_fs_W^2)P_L
-
Q_fs_W^2P_R
\right]f,
$$

where $T^3_f$ is nonzero only for the left-handed weak doublet component. Equivalently, one defines

$$
g_L^f=T^3_f-Q_fs_W^2,
\qquad
g_R^f=-Q_fs_W^2.
$$

The important conceptual point is that the photon couples vectorially to electric charge, while the $Z$ couples differently to left- and right-handed fermions. Neutral currents therefore remember the chiral electroweak origin of the theory even after symmetry breaking.

## Higgs boson mass

The Higgs potential is

$$
V(H)=-\mu^2H^\dagger H+\lambda(H^\dagger H)^2.
$$

At the minimum,

$$
H^\dagger H=\frac{v^2}{2},
\qquad
v^2=\frac{\mu^2}{\lambda}.
$$

Writing

$$
H=
\frac{1}{\sqrt2}
\begin{pmatrix}
0\\
v+h
\end{pmatrix}
$$

in unitary gauge gives

$$
m_h^2=2\lambda v^2.
$$

The three other real components of the Higgs doublet are not physical scalar particles in the broken phase. They become the longitudinal polarizations of $W^+$, $W^-$, and $Z$.

The degree-of-freedom count is

$$
4\text{ real Higgs components}
+
3\text{ massless weak gauge bosons}\times2
+
1\text{ hypercharge boson}\times2
$$

before breaking, and

$$
1\text{ Higgs scalar}
+
3\text{ massive weak bosons}\times3
+
1\text{ photon}\times2
$$

after breaking. The numbers match:

$$
4+6+2=1+9+2=12.
$$

## Fermion masses

The Yukawa interactions give fermion masses when $H$ gets a vacuum expectation value:

$$
\mathcal L_Y
=
-\bar Q_L\widetilde H Y_u u_R
-\bar Q_LH Y_d d_R
-\bar L_LH Y_e e_R
+\text{h.c.}
$$

After symmetry breaking,

$$
M_u=\frac{v}{\sqrt2}Y_u,
\qquad
M_d=\frac{v}{\sqrt2}Y_d,
\qquad
M_e=\frac{v}{\sqrt2}Y_e.
$$

Biunitary diagonalization gives positive real masses,

$$
U_{uL}^\dagger M_uU_{uR}=M_u^{\rm diag},
\qquad
U_{dL}^\dagger M_dU_{dR}=M_d^{\rm diag},
\qquad
U_{eL}^\dagger M_eU_{eR}=M_e^{\rm diag}.
$$

The mismatch

$$
V_{\rm CKM}=U_{uL}^\dagger U_{dL}
$$

appears in the charged weak current.

In the minimal renormalizable Standard Model, neutrinos remain massless. If the Weinberg operator is added, neutrino masses arise from

$$
\mathcal O_5\sim\frac{1}{\Lambda}(LH)(LH),
$$

and the lepton charged current contains

$$
U_{\rm PMNS}.
$$

So the mass spectrum depends on which theory we are counting:

$$
\text{minimal renormalizable SM}
\neq
\text{SM plus neutrino-mass operator}.
$$

## Higgs couplings as mass derivatives

The Higgs field is a fluctuation in the length of the order parameter. Since many masses come from $v$, the Higgs coupling to a particle is often the derivative of that particle's mass term with respect to $v$.

For vector bosons, the mass terms expand as

$$
M_W^2 W^+_\mu W^{-\mu}
\left(1+\frac{h}{v}\right)^2
$$

and

$$
\frac12M_Z^2 Z_\mu Z^\mu
\left(1+\frac{h}{v}\right)^2.
$$

Therefore the Lagrangian contains

$$
\mathcal L
\supset
\frac{2M_W^2}{v}hW^+_\mu W^{-\mu}
+
\frac{M_Z^2}{v}hZ_\mu Z^\mu
+\cdots.
$$

The corresponding Feynman rule for $hZZ$ has an extra factor of $2$ relative to the coefficient of $hZ_\mu Z^\mu$, because the two $Z$ fields are identical.

For a Dirac fermion mass term,

$$
-m_f\bar f f,
$$

the Higgs interaction is

$$
\mathcal L
\supset
-\frac{m_f}{v}h\bar f f.
$$

Thus, at tree level,

$$
g_{hff}=\frac{m_f}{v}.
$$

The Higgs couples more strongly to heavier particles because their masses are more sensitive to the Higgs vacuum. Not “because mass attracts Higgs,” which is a phrase that sounds profound until it commits crimes.

## Higgs self-couplings

Using

$$
m_h^2=2\lambda v^2,
$$

the Higgs potential expanded around the vacuum is

$$
V(h)
=
\text{constant}
+
\frac12m_h^2h^2
+
\frac{m_h^2}{2v}h^3
+
\frac{m_h^2}{8v^2}h^4.
$$

Since the Lagrangian contains $-V$, the cubic and quartic Higgs self-interactions are controlled by $m_h$ and $v$ at tree level:

$$
\mathcal L
\supset
-\frac{m_h^2}{2v}h^3
-\frac{m_h^2}{8v^2}h^4.
$$

These relations are special to the minimal Higgs potential. Extended Higgs sectors or higher-dimensional operators can change Higgs self-couplings without changing the gauge-boson masses in the same way.

## Compact coupling dictionary

The following table is the useful lookup version.

| Sector | Tree-level relation | Meaning |
|---|---|---|
| electromagnetic | $e=gs_W=g'c_W$ | Photon coupling after electroweak mixing. |
| charged weak | $M_W=gv/2$ | $W^\pm$ mass from the Higgs kinetic term. |
| neutral weak | $M_Z=\sqrt{g^2+g'^2}\,v/2$ | $Z$ mass from the neutral gauge-boson mass matrix. |
| weak angle | $\tan\theta_W=g'/g$ | Rotation from $(W^3,B)$ to $(A,Z)$. |
| Higgs | $m_h^2=2\lambda v^2$ | Radial Higgs mass from the scalar potential. |
| fermions | $M_f=vY_f/\sqrt2$ | Yukawa matrices become mass matrices. |
| Higgs–fermion | $g_{hff}=m_f/v$ | Higgs coupling proportional to fermion mass. |
| Higgs–$W$ | Lagrangian coefficient $2M_W^2/v$ | Single-Higgs coupling to $W^+W^-$. |
| Higgs–$Z$ | Lagrangian coefficient $M_Z^2/v$ | Single-Higgs coupling to $ZZ$. |
| QCD | $g_s$ | Gluon coupling to color generators. |

The table is tree-level. In precision work, one must say which masses are pole masses, which couplings are running couplings, and which input scheme is being used.

## Common mistakes

**Calling $W^3$ the photon.** The photon is $A=s_WW^3+c_WB$, not $W^3$ alone. The orthogonal combination is the $Z$.

**Forgetting that $T^3$ only acts on left-handed doublets.** Right-handed charged fermions have $T^3=0$ but nonzero hypercharge. This is why $Z$ couplings are chiral.

**Confusing Lagrangian coefficients with Feynman rules.** Identical fields create combinatoric factors. The coefficient of $hZ_\mu Z^\mu$ in the Lagrangian is $M_Z^2/v$, while the vertex factor has $2M_Z^2/v$ times the usual $i\eta_{\mu\nu}$ convention.

**Treating quark masses as directly measured particle masses.** Quarks are confined. Their masses are parameters extracted in schemes such as $\overline{\rm MS}$ or in heavy-quark threshold schemes, not isolated on-shell particle masses in the same sense as the electron mass.

**Putting neutrino masses into the minimal renormalizable Standard Model.** Minimal means no $\nu_R$ and no Weinberg operator. Neutrino masses are an extension, even if a very well-motivated one.

## Exercises

### Exercise 1: Diagonalize the neutral mass matrix

Starting from the neutral mass term

$$
\frac{v^2}{8}(gW_\mu^3-g'B_\mu)^2,
$$

show that one neutral vector boson is massless.

<details><summary><strong>Solution</strong></summary>

The mass term corresponds to the matrix

$$
\frac{v^2}{4}
\begin{pmatrix}
W^3_\mu & B_\mu
\end{pmatrix}
\begin{pmatrix}
g^2 & -gg'\\
-gg' & g'^2
\end{pmatrix}
\begin{pmatrix}
W^{3\mu}\\
B^\mu
\end{pmatrix}.
$$

The determinant of the matrix is

$$
g^2g'^2-(gg')^2=0,
$$

so one eigenvalue is zero. The zero eigenvector is proportional to

$$
\begin{pmatrix}
g'\\
g
\end{pmatrix},
$$

which gives

$$
A_\mu=s_WW^3_\mu+c_WB_\mu.
$$

The orthogonal eigenvector is $Z_\mu=c_WW^3_\mu-s_WB_\mu$ with eigenvalue proportional to $g^2+g'^2$.

</details>

### Exercise 2: Derive the rho relation

Use

$$
M_W=\frac12gv,
\qquad
M_Z=\frac12\sqrt{g^2+g'^2}\,v,
\qquad
c_W=\frac{g}{\sqrt{g^2+g'^2}},
$$

to show that $\rho=1$ at tree level.

<details><summary><strong>Solution</strong></summary>

Compute

$$
M_Z^2c_W^2
=
\frac14(g^2+g'^2)v^2
\frac{g^2}{g^2+g'^2}
=
\frac14g^2v^2
=
M_W^2.
$$

Therefore

$$
\rho
=
\frac{M_W^2}{M_Z^2c_W^2}=1.
$$

</details>

### Exercise 3: Higgs coupling to a Dirac fermion

Starting from

$$
-y_f\bar f_L\frac{v+h}{\sqrt2}f_R+\text{h.c.},
$$

derive the fermion mass and Higgs–fermion coupling.

<details><summary><strong>Solution</strong></summary>

The mass term is

$$
-\frac{y_fv}{\sqrt2}\bar f f,
$$

so

$$
m_f=\frac{y_fv}{\sqrt2}.
$$

The one-Higgs term is

$$
-\frac{y_f}{\sqrt2}h\bar f f
=
-\frac{m_f}{v}h\bar f f.
$$

Thus the tree-level Higgs–fermion coupling is $m_f/v$.

</details>

### Exercise 4: Count the eaten Goldstones

Show that the Higgs doublet has enough real degrees of freedom to give longitudinal polarizations to $W^+$, $W^-$, and $Z$ while leaving one physical scalar.

<details><summary><strong>Solution</strong></summary>

A complex $SU(2)$ doublet has four real components. Electroweak symmetry breaking leaves one generator unbroken, $Q=T^3+Y$, and breaks three generators. The three broken directions correspond to three Goldstone modes. In a gauge theory these become the longitudinal polarizations of the three massive gauge bosons $W^+$, $W^-$, and $Z$. The remaining radial component is the physical Higgs boson $h$.

</details>

## Relations to other pages

- [Electroweak Symmetry Breaking](/gauge-theories-standard-model/electroweak/electroweak-symmetry-breaking/) derives the unbroken electromagnetic generator.
- [Photon, W, and Z Bosons](/gauge-theories-standard-model/electroweak/photon-w-z-bosons/) develops the electroweak mixing angle and gauge-boson basis change.
- [Gauge-Boson Masses](/gauge-theories-standard-model/higgs-sector/gauge-boson-masses/) derives $M_W$ and $M_Z$ directly from the Higgs kinetic term.
- [Higgs Boson Couplings](/gauge-theories-standard-model/higgs-sector/higgs-boson-couplings/) explains the mass-proportional Higgs coupling pattern.
- [Fermion Mass Matrices](/gauge-theories-standard-model/flavor-neutrinos/fermion-mass-matrices/) explains how Yukawa matrices become masses and mixing matrices.
- [Weak Neutral Current](/gauge-theories-standard-model/electroweak/weak-neutral-current/) explains the chiral $Z$ couplings in detail.
- [Limitations of the Standard Model](/gauge-theories-standard-model/standard-model/limitations-of-the-standard-model/) discusses what the spectrum and couplings fail to explain.

## Research status

The tree-level mass and coupling dictionary is established. Its precision interpretation is a renormalized, scheme-dependent subject: masses may be pole or running masses, couplings run with scale, quark masses require QCD conventions, and electroweak observables receive loop corrections. The open problem is not how the Standard Model converts $v$ and Yukawa matrices into masses; it is why the inputs have their observed pattern.

## Where to go next

Continue to [Limitations of the Standard Model](/gauge-theories-standard-model/standard-model/limitations-of-the-standard-model/) for the conceptual handoff: neutrino masses, dark matter, baryogenesis, the hierarchy problem, strong CP, flavor, and quantum gravity.

For a consistency-focused route, continue to [Anomalies and Consistency](/gauge-theories-standard-model/sm-anomalies-consistency/).

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the Standard Model gauge/Higgs, lepton, quark, and neutrino-mass sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the weak-interaction, Higgs, CP-violation, anomaly, and precision-test chapters.
- Burgess, *Introduction to Effective Field Theory*, especially the Fermi-theory, gauge/Goldstone equivalence, and Standard Model EFT sections.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak symmetry breaking, masses, currents, and renormalized electroweak interactions.
- Coleman, *Aspects of Symmetry*, especially “Secret Symmetry” for the conceptual origin of massive vector bosons in a gauge theory.

## Version history

- **2026-06-19:** Linked forward to the limitations page and Anomalies and Consistency chapter.
- **2026-06-19:** Initial page deriving the tree-level Standard Model mass spectrum, electroweak mixing, and coupling dictionary after symmetry breaking.
