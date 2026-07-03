---
title: "Chirality and Gauge Interactions"
description: "Explains chirality, helicity, left- and right-chiral projectors, vectorlike versus chiral gauge theories, and why Standard Model weak interactions act only on left-handed doublets."
sidebar:
  label: "Chirality and Gauge Interactions"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki §§34–36, §§75, §§87–91; Schwartz Chs. 10–11 and 29–30; Coleman, Aspects of Symmetry, Ch. 5; Weinberg Vol. II electroweak chapters."
topics:
  - chirality
  - helicity
  - chiral gauge theory
  - weak interactions
  - parity violation
canonicalTopics:
  - chirality
  - left-handed-weak-interaction
  - vectorlike-vs-chiral-gauge-theories
  - standard-model-chiral-fermions
researchStatus:
  established:
    - "The minimal Standard Model is chiral under SU(2)L × U(1)Y: left-handed fermions transform differently from right-handed charged fermions."
  active:
    - "Extensions with right-handed neutrinos, vectorlike fermions, mirror sectors, or flavor symmetries modify the chiral representation content and are active model-building directions."
---

## Summary

Chirality is the Lorentz-invariant distinction between the two irreducible Weyl pieces of a Dirac spinor. In the mostly-minus convention used in this volume,

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2},
\qquad
\psi_L=P_L\psi,
\qquad
\psi_R=P_R\psi.
$$

The Standard Model uses this distinction in its gauge structure. Left-chiral quarks and leptons sit in $SU(2)_L$ doublets,

$$
Q_L=\begin{pmatrix}u_L\\ d_L\end{pmatrix},
\qquad
L_L=\begin{pmatrix}\nu_L\\ e_L\end{pmatrix},
$$

while the right-chiral charged fields $u_R,d_R,e_R$ are $SU(2)_L$ singlets. Therefore the charged weak current is left-chiral:

$$
j_{W^+}^\mu
=
\bar\nu_L\gamma^\mu e_L
+
\bar u_L\gamma^\mu d_L
\quad\text{for one generation},
$$

with CKM mixing inserted in the quark mass basis for three generations.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Chirality and gauge interactions map](/figures/gauge-theories-standard-model/chirality-gauge-interactions-map.svg)

<figcaption>

A vectorlike gauge theory treats the two chiralities as conjugate pieces of a massive Dirac fermion, so a gauge-invariant mass can be written directly. A chiral gauge theory assigns different gauge representations to left- and right-chiral fields; in the Standard Model this forbids bare fermion masses and makes the weak charged current left-chiral.

</figcaption>
</figure>

The slogan is simple: **chirality is a property of Lorentz representations; the Standard Model turns it into a gauge principle.**

## Prerequisites

You should know [Standard Model Fermion Representations](/gauge-theories-standard-model/flavor-neutrinos/standard-model-fermion-representations/), [Weak Charged Current](/gauge-theories-standard-model/electroweak/weak-charged-current/), and [Weak Neutral Current](/gauge-theories-standard-model/electroweak/weak-neutral-current/). You should also be comfortable with the Dirac matrices and the definition of $\gamma^5$ from the Foundations of QFT spinor pages.

The relevant gauge convention is

$$
D_\mu
=
\partial_\mu
+ig_sG_\mu^AT_c^A
+igW_\mu^aT_L^a
+ig'YB_\mu,
$$

where the representation matrices depend on the field being differentiated.

## Core idea

A gauge theory is **vectorlike** if the left- and right-chiral components of its massive Dirac fermions transform in compatible gauge representations, so that gauge-invariant mass terms can be written without breaking the gauge symmetry. QED and QCD, after electroweak symmetry breaking, are vectorlike with respect to electric charge and color.

A gauge theory is **chiral** if its left- and right-chiral fermions transform differently under the gauge group. Then mass terms may be forbidden by gauge symmetry, and gauge anomalies become a serious consistency constraint.

The electroweak Standard Model is chiral. For example,

$$
L_L=(\nu_L,e_L)^T\sim(\mathbf1,\mathbf2)_{-1/2},
\qquad
e_R\sim(\mathbf1,\mathbf1)_{-1}.
$$

The object $\bar e_Le_R$ is not an electroweak singlet. The gauge-invariant Yukawa operator is instead

$$
\bar L_LHe_R.
$$

When the neutral Higgs component gets a vacuum expectation value, this operator becomes an electron mass term. Before that, the mass term is not allowed.

That is the basic architecture of chiral gauge theory: gauge symmetry controls which chiral fields may talk to which other chiral fields.

## Chirality versus helicity

Chirality and helicity are related but not identical.

Chirality is defined by $\gamma^5$ and the projectors

$$
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2}.
$$

It is an intrinsic Lorentz-representation label. A left-chiral Weyl spinor transforms in one irreducible spinor representation of the Lorentz group; a right-chiral Weyl spinor transforms in the conjugate representation.

Helicity is the projection of spin along momentum:

$$
h=\frac{\mathbf S\cdot\mathbf p}{|\mathbf p|}.
$$

For a massive particle, helicity is frame-dependent: one can boost past the particle and reverse its momentum. Chirality is still well-defined, but a massive Dirac equation mixes the two chiralities.

For a massless fermion, chirality and helicity are locked. A left-chiral field creates particles of one helicity and antiparticles of the opposite helicity. This is why high-energy weak interactions are often described as “left-handed,” but the more precise word in the Lagrangian is **left-chiral**.

## Spinor projectors in the kinetic term

Let

$$
\psi=\psi_L+\psi_R,
\qquad
\psi_L=P_L\psi,
\qquad
\psi_R=P_R\psi.
$$

Because

$$
\{\gamma^5,\gamma^\mu\}=0,
$$

the massless Dirac kinetic term splits into two independent chiral pieces:

$$
\bar\psi i\gamma^\mu\partial_\mu\psi
=
\bar\psi_Li\gamma^\mu\partial_\mu\psi_L
+
\bar\psi_Ri\gamma^\mu\partial_\mu\psi_R.
$$

A vectorlike gauge interaction can preserve this split while acting similarly on both chiralities:

$$
\bar\psi i\gamma^\mu D_\mu\psi
=
\bar\psi_Li\gamma^\mu D_\mu\psi_L
+
\bar\psi_Ri\gamma^\mu D_\mu\psi_R,
$$

with the same gauge representation assigned to $\psi_L$ and $\psi_R$ in four-component notation.

A mass term has a different structure:

$$
-m\bar\psi\psi
=-m(\bar\psi_L\psi_R+\bar\psi_R\psi_L).
$$

Mass terms couple left and right. Therefore a gauge-invariant Dirac mass exists only if the left and right fields can be paired into a gauge singlet.

## Vectorlike gauge interactions

QED is the simplest vectorlike example. A charged Dirac fermion has

$$
D_\mu\psi=(\partial_\mu+ieQA_\mu)\psi,
$$

and both chiralities have the same electric charge:

$$
\psi_L\to e^{iQ\alpha(x)}\psi_L,
\qquad
\psi_R\to e^{iQ\alpha(x)}\psi_R.
$$

The Dirac mass term is gauge invariant because

$$
\bar\psi_L\psi_R\to
\bar\psi_Le^{-iQ\alpha}e^{iQ\alpha}\psi_R
=\bar\psi_L\psi_R.
$$

QCD is also vectorlike for quarks after the electroweak symmetry has been broken and the quark mass eigenstates are formed. Both $u_L$ and $u_R$ are color triplets, and both have electric charge $2/3$; both $d_L$ and $d_R$ are color triplets, and both have electric charge $-1/3$.

This does not mean QCD is simple. It means that color itself does not distinguish left from right. QCD confinement is hard for nonperturbative reasons, not because color is chiral.

## Chiral electroweak interactions

Before electroweak symmetry breaking, the Standard Model assignments are not vectorlike under $SU(2)_L\times U(1)_Y$. The quark fields transform as

$$
Q_L\sim(\mathbf3,\mathbf2)_{1/6},
\qquad
u_R\sim(\mathbf3,\mathbf1)_{2/3},
\qquad
d_R\sim(\mathbf3,\mathbf1)_{-1/3}.
$$

The lepton fields transform as

$$
L_L\sim(\mathbf1,\mathbf2)_{-1/2},
\qquad
e_R\sim(\mathbf1,\mathbf1)_{-1}.
$$

The left-handed neutrino $\nu_L$ is the upper component of $L_L$. A right-handed neutrino $\nu_R$ is not present in the minimal renormalizable Standard Model.

Since the right-chiral charged fermions are weak singlets, the $W^\pm$ bosons couple only to left-chiral doublets. For one generation,

$$
\mathcal L_{\rm cc}
=
-\frac{g}{\sqrt2}
\left[
W_\mu^+
\left(\bar\nu_L\gamma^\mu e_L+\bar u_L\gamma^\mu d_L\right)
+\text{h.c.}
\right].
$$

No term of the form

$$
W_\mu^+\bar u_R\gamma^\mu d_R
$$

appears in the minimal Standard Model.

## Neutral currents and chirality

The neutral weak current also remembers chirality, even though it does not change the upper/lower member of a weak doublet. After electroweak symmetry breaking, the $Z$ coupling is

$$
\mathcal L_Z
=
-\frac{g}{c_W}Z_\mu
\bar f\gamma^\mu
\left[(T^3_f-s_W^2Q_f)P_L-s_W^2Q_fP_R\right]f,
$$

for a charged Dirac fermion $f$ assembled from a left-chiral doublet component and a right-chiral singlet. Equivalently, the left- and right-chiral couplings are

$$
g_L^f=T^3_f-s_W^2Q_f,
\qquad
g_R^f=-s_W^2Q_f.
$$

For a right-chiral charged fermion, $T^3=0$. That is why $g_L^f$ and $g_R^f$ generally differ. The $Z$ current is therefore parity-violating even though it is electrically neutral.

The photon coupling is different. It is

$$
\mathcal L_{\rm em}=-eA_\mu J_{\rm em}^\mu,
\qquad
J_{\rm em}^\mu=\sum_f Q_f\bar f\gamma^\mu f,
$$

and it is vectorlike for the observed charged Dirac fermions.

## Why the Higgs is needed for masses

Because the electroweak theory is chiral, the renormalizable fermion masses must come from Yukawa couplings:

$$
\mathcal L_Y
=
-\bar Q_LY_dHd_R
-\bar Q_LY_u\tilde H u_R
-\bar L_LY_eHe_R
+\text{h.c.}
$$

When

$$
H\to\frac{1}{\sqrt2}\begin{pmatrix}0\\ v+h\end{pmatrix},
$$

these become

$$
M_d=\frac{v}{\sqrt2}Y_d,
\qquad
M_u=\frac{v}{\sqrt2}Y_u,
\qquad
M_e=\frac{v}{\sqrt2}Y_e.
$$

The mass terms then mix chiralities:

$$
-\bar f_LM_ff_R-\bar f_RM_f^\dagger f_L.
$$

The important distinction is temporal and structural: before the Higgs vacuum, the chiral representation data are fundamental; after the Higgs vacuum, one may assemble massive Dirac fermions and talk about left- and right-chiral projections of a mass eigenstate.

## Parity violation

Parity swaps the two Lorentz chiralities. Schematically,

$$
P:\quad \psi_L(t,\mathbf x)\leftrightarrow \psi_R(t,-\mathbf x).
$$

A gauge theory that treats $\psi_L$ and $\psi_R$ identically can be parity invariant, at least as far as that interaction is concerned. The weak charged current cannot be parity invariant because it contains $\psi_L$ but not the corresponding right-chiral charged current.

This is the field-theoretic core of maximal parity violation in charged weak interactions. In low-energy beta decay, it appears as the famous vector-minus-axial form

$$
\bar\psi\gamma^\mu(1-\gamma^5)\psi
=2\bar\psi_L\gamma^\mu\psi_L.
$$

The factor of $2$ is convention bookkeeping from the projector $P_L=(1-\gamma^5)/2$.

## Flavor and chirality

Chirality also explains why mixing matrices appear in charged currents rather than everywhere.

The quark mass matrices are diagonalized by independent left- and right-handed rotations:

$$
U_{uL}^\dagger M_uU_{uR}=M_u^{\rm diag},
\qquad
U_{dL}^\dagger M_dU_{dR}=M_d^{\rm diag}.
$$

The charged current contains only the left-handed fields. Therefore the mismatch between $U_{uL}$ and $U_{dL}$ survives as

$$
V_{\rm CKM}=U_{uL}^\dagger U_{dL}.
$$

The right-handed rotations do not appear in the Standard Model charged weak current. They help define the mass basis, but they do not multiply the $W$ interaction. That is another place where chirality is not a cosmetic word; it changes which field redefinitions become observable.

## Common pitfalls

**Calling chirality the same thing as helicity.** They coincide in a useful sense for massless fermions, but they are not the same definition. Chirality is defined by $\gamma^5$; helicity is spin projected along momentum.

**Saying weak interactions couple to left-handed particles only.** The Lagrangian couples to left-chiral fields. For ultra-relativistic particles this is nearly the same as saying left-helicity particles, but the distinction matters for massive fermions and antiparticles.

**Forgetting the neutral current.** The $Z$ boson couples to both chiralities of charged fermions, but with different coefficients. The $W$ charged current is the maximally left-chiral one.

**Calling QCD chiral because quarks have chiral symmetries.** Massless QCD has global chiral symmetries, but the color gauge interaction itself is vectorlike. These are different uses of the word “chiral.”

**Writing bare Standard Model fermion masses before electroweak symmetry breaking.** The Higgs field is required to make the mass operators gauge invariant.

**Ignoring anomalies.** Chiral gauge theories are delicate. The Standard Model fermion representations cancel gauge anomalies; a random chiral representation table usually does not.

## Relations to other pages

The previous page, [Standard Model Fermion Representations](/gauge-theories-standard-model/flavor-neutrinos/standard-model-fermion-representations/), lists the representation data. This page explains why those data make the electroweak theory chiral.

The next pages on Yukawa Couplings and Fermion Mass Matrices use this chirality structure to explain why the Higgs doublet is needed and why diagonalizing mass matrices produces CKM mixing. The later anomaly-cancellation pages revisit chirality from the consistency side: chiral gauge theories are only quantum theories when their gauge anomalies vanish.

## Research status

The chiral electroweak structure of the Standard Model is established. It is tested in charged-current weak interactions, neutral-current parity violation, neutrino scattering, precision electroweak data, and flavor physics.

Open questions begin where the representation table stops explaining things. Why are there three chiral generations? Why are the Yukawa matrices hierarchical? Are there right-handed neutrinos? Are there additional vectorlike fermions at higher energy? Is chirality tied to unification, topology, extra dimensions, or flavor symmetries? The minimal Standard Model does not answer these questions.

## Exercises

### Exercise 1: Show that a Dirac mass mixes chirality

Use $\psi=\psi_L+\psi_R$ to show that $\bar\psi\psi=\bar\psi_L\psi_R+\bar\psi_R\psi_L$.

<details><summary><strong>Solution</strong></summary>

Since $\psi_L=P_L\psi$ and $\psi_R=P_R\psi$, the conjugates satisfy $\bar\psi_L=\bar\psi P_R$ and $\bar\psi_R=\bar\psi P_L$. Therefore

$$
\bar\psi_L\psi_L=\bar\psi P_RP_L\psi=0,
\qquad
\bar\psi_R\psi_R=\bar\psi P_LP_R\psi=0.
$$

Thus

$$
\bar\psi\psi
=(\bar\psi_L+\bar\psi_R)(\psi_L+\psi_R)
=\bar\psi_L\psi_R+\bar\psi_R\psi_L.
$$

</details>

### Exercise 2: Check that the electron bare mass is not gauge invariant

Show that $\bar e_Le_R$ is not neutral under $U(1)_Y$, but $\bar L_LHe_R$ is.

<details><summary><strong>Solution</strong></summary>

The hypercharges are

$$
Y(e_L)=-\frac12,
\qquad
Y(e_R)=-1,
\qquad
Y(H)=\frac12.
$$

Therefore $Y(\bar e_L)=+1/2$, so

$$
Y(\bar e_Le_R)=\frac12-1=-\frac12\ne0.
$$

The operator is not hypercharge neutral. For the Yukawa operator,

$$
Y(\bar L_LHe_R)=\frac12+\frac12-1=0.
$$

The weak doublets $\bar L_L$ and $H$ can also be contracted into an $SU(2)_L$ singlet. Thus $\bar L_LHe_R$ is gauge invariant.

</details>

### Exercise 3: Derive the one-generation charged current

Start from $\Psi_L=(\psi_u,\psi_d)^T$ and $T^+=\begin{pmatrix}0&1\\0&0\end{pmatrix}$. Show that $\bar\Psi_L\gamma^\mu T^+\Psi_L=\bar\psi_{uL}\gamma^\mu\psi_{dL}$.

<details><summary><strong>Solution</strong></summary>

Acting with $T^+$ gives

$$
T^+\Psi_L
=
\begin{pmatrix}0&1\\0&0\end{pmatrix}
\begin{pmatrix}\psi_u\\\psi_d\end{pmatrix}_L
=
\begin{pmatrix}\psi_d\\0\end{pmatrix}_L.
$$

Then

$$
\bar\Psi_L\gamma^\mu T^+\Psi_L
=
(\bar\psi_{uL},\bar\psi_{dL})\gamma^\mu
\begin{pmatrix}\psi_{dL}\\0\end{pmatrix}
=\bar\psi_{uL}\gamma^\mu\psi_{dL}.
$$

For leptons this gives $\bar\nu_L\gamma^\mu e_L$; for quarks it gives $\bar u_L\gamma^\mu d_L$ before generation mixing is included.

</details>

### Exercise 4: Vectorlike or chiral?

Classify QED with one massive electron and the electroweak interaction before symmetry breaking as vectorlike or chiral.

<details><summary><strong>Solution</strong></summary>

QED with one massive electron is vectorlike: $e_L$ and $e_R$ have the same electric charge, and the mass term $m\bar ee$ is invariant under electromagnetic gauge transformations.

The electroweak interaction before symmetry breaking is chiral: $e_L$ is part of the doublet $L_L\sim(\mathbf1,\mathbf2)_{-1/2}$, while $e_R\sim(\mathbf1,\mathbf1)_{-1}$. They transform differently under $SU(2)_L\times U(1)_Y$, and a bare mass term is forbidden.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§34–36 for Weyl and Dirac spinors, §75 for chiral gauge theories and anomalies, and §§87–91 for Standard Model fermions.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 10–11 for spinors and chirality, Ch. 29 for weak interactions, and Ch. 30 for anomalies.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for the Higgs phenomenon and chiral electroweak mass generation in a broader symmetry-breaking context.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for electroweak theory and chiral fermion representations.
- Georgi, *Weak Interactions and Modern Particle Theory*, for a compact physics-first treatment of chiral weak interactions.
- Bilal, “Lectures on Anomalies,” for a detailed bridge from chiral fermions to anomaly constraints.

## Version history

- **2026-06-18:** Initial page. Added chirality/helicity distinction, vectorlike versus chiral gauge theory comparison, charged and neutral current formulas, mass-generation logic, exercises, and chirality map figure.
