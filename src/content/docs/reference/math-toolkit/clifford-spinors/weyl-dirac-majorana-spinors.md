---
title: "Weyl, Dirac, and Majorana Spinors"
description: "Explains how Weyl, Dirac, and Majorana spinors are related as Lorentz representations, how their equations and mass terms work, and where chirality, helicity, and reality conditions enter QFT."
sidebar:
  label: "Weyl, Dirac, Majorana"
  order: 5
level: Graduate
status: "Polished draft"
source: "Standard Lorentz-representation and spinor references, including Weinberg, Srednicki, Schwartz, Zee, Coleman, and two-component spinor literature."
topics:
  - Weyl spinors
  - Dirac spinors
  - Majorana spinors
  - chirality
  - helicity
  - spinor mass terms
canonicalTopics:
  - weyl-spinors
  - dirac-spinors
  - majorana-spinors
  - chirality
  - helicity
  - spinor-mass-terms
researchStatus:
  established:
    - "The Weyl, Dirac, and Majorana spinor representations and their Lorentzian mass terms are standard parts of four-dimensional QFT."
  active:
    - "Reality conditions, fermion measures, anomalies, lattice fermions, neutrino mass models, Euclidean continuation, and spin-structure dependence remain active contexts where these distinctions matter."
---

## Summary

Four-dimensional relativistic fermions are built from two inequivalent spinor representations of the Lorentz group. Using

$$
\operatorname{Spin}^+(1,3)\simeq SL(2,\mathbb C),
$$

the irreducible Weyl spinors transform as

$$
\left(\frac12,0\right)
\qquad\text{and}\qquad
\left(0,\frac12\right).
$$

A **Weyl spinor** uses one of these irreducible representations. A **Dirac spinor** contains one left-chiral Weyl spinor and one right-chiral Weyl spinor, with the two pieces independent. A **Majorana spinor** is a Dirac spinor satisfying a Lorentzian reality condition, so its right-chiral part is related to the complex conjugate of its left-chiral part.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing a left Weyl spinor in the (1/2,0) representation and a right Weyl spinor in the (0,1/2) representation combining into a Dirac spinor, with Majorana and massless limits below.](/figures/math-toolkit/weyl-dirac-majorana-map.svg)

<figcaption>

In four-dimensional Lorentzian signature, a Dirac spinor is the direct sum of left- and right-chiral Weyl representations. A Majorana spinor imposes a charge-conjugation reality condition. In the massless limit, chirality becomes a good Lorentz-invariant label, and for positive-energy particles it matches helicity.

</figcaption>
</figure>

In the chiral gamma-matrix basis, with conventions from [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/), a Dirac spinor is written

$$
\Psi=
\begin{pmatrix}
\psi_L \\
\psi_R
\end{pmatrix},
\qquad
\gamma^5\Psi=
\begin{pmatrix}
-\psi_L \\
+\psi_R
\end{pmatrix}.
$$

The massless Dirac equation splits into two independent Weyl equations. A mass term couples left and right chirality. That single fact explains much of the taxonomy: Weyl fermions are chiral, Dirac masses need paired conjugate gauge representations, and Majorana masses are possible only when the relevant gauge and global charges allow a field to be identified with its charge conjugate.

## Prerequisites

Read [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/) first. This page uses

$$
\gamma^5=i\gamma^0\gamma^1\gamma^2\gamma^3,
\qquad
P_L=\frac{1-\gamma^5}{2},
\qquad
P_R=\frac{1+\gamma^5}{2}.
$$

It also assumes [Spin Groups](/math-toolkit/clifford-spinors/spin-groups/) and [SL(2,C) and the Lorentz Group](/math-toolkit/groups-representations/sl2c-and-lorentz-group/). The Pauli-matrix identities used in the two-component notation are reviewed in [Pauli Matrices](/math-toolkit/clifford-spinors/pauli-matrices/).

## Core idea

The Lorentz group has spinor representations that are smaller than the four-component Dirac notation suggests. In four dimensions, a Dirac spinor is reducible as a Lorentz representation:

$$
\text{Dirac}=\text{left Weyl}\oplus\text{right Weyl}.
$$

In representation labels,

$$
\left(\frac12,0\right)\oplus\left(0,\frac12\right).
$$

The two summands are exchanged by parity and by charge conjugation, but a proper orthochronous Lorentz transformation does not mix them. This is why massless chiral fermions can exist: the left-handed piece can propagate by itself without needing the right-handed piece.

Mass changes the story. The Lorentz-invariant mass term for an ordinary Dirac fermion pairs the two chiralities. In chiral basis, the free Dirac equation is not two separate massive Weyl equations; it is two first-order equations coupled by $m$.

Majorana spinors are different again. They do not introduce a third Lorentz representation. A Majorana spinor is a Dirac spinor with a reality condition compatible with Lorentz transformations. In four-dimensional Lorentzian signature, this turns one Weyl spinor into a four-component object by adjoining its complex conjugate.

## Setup and conventions

We use the mostly-minus metric

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
$$

and the chiral gamma matrices

$$
\gamma^\mu=
\begin{pmatrix}
0 & \sigma^\mu \\
\bar\sigma^\mu & 0
\end{pmatrix},
$$

with

$$
\sigma^\mu=(\mathbf 1,\sigma^i),
\qquad
\bar\sigma^\mu=(\mathbf 1,-\sigma^i).
$$

Then

$$
\gamma^5=
\begin{pmatrix}
-\mathbf 1 & 0 \\
0 & \mathbf 1
\end{pmatrix}.
$$

A four-component Dirac spinor decomposes as

$$
\Psi=
\begin{pmatrix}
\chi_\alpha \\
\bar\eta^{\dot\alpha}
\end{pmatrix}.
$$

Here $\chi_\alpha$ is a left-chiral Weyl spinor transforming in $\left(\frac12,0\right)$, while $\bar\eta^{\dot\alpha}$ is a right-chiral Weyl spinor transforming in $\left(0,\frac12\right)$. The bar on $\bar\eta^{\dot\alpha}$ denotes the complex conjugate of an undotted Weyl spinor $\eta_\alpha$; it is not the Dirac adjoint.

The Dirac adjoint of $\Psi$ is

$$
\bar\Psi=\Psi^\dagger\gamma^0.
$$

This notation clash is unfortunate but standard: bars on two-component spinors usually indicate complex conjugation and dotted indices, while a bar on a four-component spinor usually indicates the Dirac adjoint. Context saves us. Usually.

## Two-component index conventions

Undotted indices are written

$$
\alpha,\beta=1,2,
$$

and dotted indices are written

$$
\dot\alpha,\dot\beta=1,2.
$$

The antisymmetric symbols raise and lower indices. We choose

$$
\epsilon^{12}=\epsilon_{21}=+1,
\qquad
\epsilon_{12}=\epsilon^{21}=-1,
$$

so that

$$
\epsilon^{\alpha\beta}\epsilon_{\beta\gamma}=\delta^\alpha{}_{\gamma}.
$$

For an undotted spinor,

$$
\chi^\alpha=\epsilon^{\alpha\beta}\chi_\beta,
\qquad
\chi_\alpha=\epsilon_{\alpha\beta}\chi^\beta.
$$

The same convention applies to dotted indices. Lorentz-invariant contractions are formed by antisymmetric contraction:

$$
\chi\eta\equiv\chi^\alpha\eta_\alpha.
$$

For anticommuting spinor fields, this contraction is symmetric under exchange of the two spinors:

$$
\chi\eta=\eta\chi.
$$

That can feel backward at first. The epsilon tensor is antisymmetric, but the spinor components also anticommute, so the two signs cancel.

The sigma matrices carry one undotted and one dotted index:

$$
\sigma^\mu_{\alpha\dot\alpha},
\qquad
\bar\sigma^{\mu\dot\alpha\alpha}.
$$

They obey

$$
\sigma^\mu_{\alpha\dot\alpha}\bar\sigma^{\nu\dot\alpha\beta}
+
\sigma^\nu_{\alpha\dot\alpha}\bar\sigma^{\mu\dot\alpha\beta}
=2\eta^{\mu\nu}\delta_\alpha{}^\beta,
$$

and the dotted version with $\sigma$ and $\bar\sigma$ reversed.

## Weyl spinors

A left-chiral Weyl spinor is a two-component field $\chi_\alpha$ transforming in $\left(\frac12,0\right)$. Its kinetic term is

$$
\mathcal L_\chi
=i\chi^\dagger_{\dot\alpha}\bar\sigma^{\mu\dot\alpha\alpha}\partial_\mu\chi_\alpha.
$$

The equation of motion is

$$
i\bar\sigma^{\mu\dot\alpha\alpha}\partial_\mu\chi_\alpha=0.
$$

This is the left-handed Weyl equation.

The complex conjugate field $\chi^\dagger_{\dot\alpha}$ transforms in the conjugate representation $\left(0,\frac12\right)$. In Lorentzian signature, complex conjugation really maps one Weyl representation to the other:

$$
\left(\frac12,0\right)^*\simeq\left(0,\frac12\right).
$$

A Weyl fermion can be massless without introducing its opposite chirality. Whether it can carry a gauge charge depends on the gauge representation. A single charged Weyl fermion is common in chiral gauge theories, but gauge anomalies may impose severe consistency constraints.

## Dirac spinors

A Dirac spinor contains two independent Weyl spinors:

$$
\Psi_D=
\begin{pmatrix}
\chi_\alpha \\
\bar\eta^{\dot\alpha}
\end{pmatrix}.
$$

The free Dirac Lagrangian is

$$
\mathcal L_D
=\bar\Psi_D(i\gamma^\mu\partial_\mu-m)\Psi_D.
$$

In two-component notation this becomes

$$
\mathcal L_D
=i\chi^\dagger\bar\sigma^\mu\partial_\mu\chi
+i\eta^\dagger\bar\sigma^\mu\partial_\mu\eta
-m(\eta\chi+\chi^\dagger\eta^\dagger),
$$

with spinor indices suppressed. The mass term pairs two left-handed Weyl spinors $\chi$ and $\eta$ in conjugate gauge representations, or equivalently pairs left and right chiralities in four-component language.

The Dirac equation

$$
(i\gamma^\mu\partial_\mu-m)\Psi_D=0
$$

becomes the coupled system

$$
i\sigma^\mu_{\alpha\dot\alpha}\partial_\mu\bar\eta^{\dot\alpha}-m\chi_\alpha=0,
$$

and

$$
i\bar\sigma^{\mu\dot\alpha\alpha}\partial_\mu\chi_\alpha-m\bar\eta^{\dot\alpha}=0.
$$

When $m=0$, the equations decouple. When $m\ne0$, neither chirality propagates independently.

A Dirac mass preserves a $U(1)$ fermion number symmetry if $\chi$ and $\eta$ have opposite charges in the two-component left-handed notation. In four-component language this is the familiar phase symmetry

$$
\Psi_D\mapsto e^{i\alpha}\Psi_D.
$$

## Majorana spinors

A Majorana spinor is a Dirac spinor satisfying

$$
\Psi_M^c=\Psi_M,
$$

where

$$
\Psi^c=C\bar\Psi^T
$$

is charge conjugation and $C$ obeys

$$
C^{-1}\gamma^\mu C=-(\gamma^\mu)^T.
$$

In chiral notation, a Majorana spinor can be written using one Weyl spinor:

$$
\Psi_M=
\begin{pmatrix}
\chi_\alpha \\
\chi^{\dagger\dot\alpha}
\end{pmatrix}.
$$

The Majorana mass term is commonly written

$$
\mathcal L_M
=i\chi^\dagger\bar\sigma^\mu\partial_\mu\chi
-\frac12 m(\chi\chi+\chi^\dagger\chi^\dagger).
$$

Equivalently, in four-component notation one often writes

$$
\mathcal L_M=\frac12\bar\Psi_M(i\gamma^\mu\partial_\mu-m)\Psi_M.
$$

The factor $1/2$ in the four-component expression prevents double-counting degrees of freedom, because the field is related to its own charge conjugate. In two-component notation the same factor appears in the mass term.

A Majorana mass is allowed only when the charges permit it. If $\chi$ carries an ordinary conserved $U(1)$ charge $q$, then $\chi\chi$ carries charge $2q$ and is forbidden unless that symmetry is absent, broken, or $q=0$ in the relevant sense. This is why Majorana masses are natural for gauge-singlet neutral fermions and impossible for an electron without breaking electric charge.

For non-Abelian gauge symmetries, the representation must admit the appropriate invariant pairing. Real and pseudoreal representations have additional possibilities; complex representations generally require a conjugate partner for a Dirac mass.

## Chirality versus helicity

Chirality is an eigenvalue of $\gamma^5$:

$$
\gamma^5\psi_L=-\psi_L,
\qquad
\gamma^5\psi_R=+\psi_R.
$$

It is a representation-theoretic label. Helicity is the projection of spin along momentum:

$$
h=\frac{\mathbf S\cdot\mathbf p}{|\mathbf p|}.
$$

For massive particles, helicity is not invariant under all Lorentz transformations: one can boost past the particle and reverse its momentum. Chirality remains a Lorentz-representation label, but a massive spinor is not an eigenstate of chirality under time evolution because the mass term couples left and right components.

For massless particles, helicity is Lorentz-invariant under proper orthochronous transformations. In the conventions of this page, positive-energy massless particle states in the left-chiral representation have negative helicity, while positive-energy massless particle states in the right-chiral representation have positive helicity. For antiparticle states the relation is reversed.

So the slogan “chirality equals helicity” is useful but incomplete. A safer version is:

> For massless positive-energy particles, chirality determines helicity; for antiparticles, the sign relation is opposite; for massive particles, chirality and helicity are different notions.

## Degrees of freedom

A two-component Weyl field has two complex components off shell. In a quantum field theory these components are Grassmann-valued fields in the path integral or operator-valued distributions in canonical quantization.

A Dirac spinor has four complex components off shell. On shell, the Dirac equation removes half the independent wavefunction data in the usual first-order way, leaving particle and antiparticle spin states.

A Majorana spinor has four real components off shell. Equivalently, it is one Weyl spinor plus its conjugate. On shell, it describes a neutral fermion whose particle and antiparticle are identified.

This counting is representation counting, not yet a Hilbert-space particle-counting theorem. In QFT, the physical particle content also depends on equations of motion, gauge constraints, reality conditions, and quantization.

## Mass terms and gauge representations

Suppose $\chi$ and $\eta$ are left-handed Weyl spinors. A Dirac mass term has the form

$$
-m\eta\chi+\text{h.c.}
$$

It is gauge-invariant if the product $\eta\chi$ contains a singlet. In common cases this means $\eta$ transforms in the conjugate representation to $\chi$.

A Majorana mass term has the form

$$
-\frac12m\chi\chi+\text{h.c.}
$$

It is gauge-invariant if $\chi\chi$ contains a singlet. For an ordinary $U(1)$ charge, this requires the charge to vanish. For a non-Abelian group, it depends on the invariant tensors of the representation.

In the Standard Model before electroweak symmetry breaking, charged fermion masses are Yukawa couplings involving the Higgs field rather than bare Dirac masses. After the Higgs gets a vacuum expectation value, those Yukawa couplings become Dirac masses. Neutrino masses are subtle precisely because Majorana and Dirac options correspond to different symmetry assumptions.

## Parity and charge conjugation

Parity exchanges the two Lorentz spinor representations:

$$
\left(\frac12,0\right)
\leftrightarrow
\left(0,\frac12\right).
$$

Therefore a single Weyl spinor by itself cannot furnish a parity-invariant theory unless parity also maps it to another field. A Dirac spinor can carry a simple parity action because it contains both chiralities.

Charge conjugation maps a field to a field transforming in the conjugate internal representation and opposite charges. For a Dirac spinor, charge conjugation exchanges particle and antiparticle. For a Majorana spinor, the field is equal to its charge conjugate, so the particle is its own antiparticle in the appropriate neutral sense.

Do not confuse charge conjugation with Hermitian conjugation. A charged Dirac field has $\Psi^\dagger$, $\bar\Psi$, and $\Psi^c$, and they serve different purposes.

## Euclidean warning

The clean Majorana reality condition above is Lorentzian. In Euclidean signature, complex conjugation does not relate the two chiral spinor representations in the same way. As a result, Majorana conditions can fail or require modification, depending on dimension and signature.

This matters in instanton calculations, supersymmetric localization, finite-temperature path integrals, and anomaly computations. A common practical approach is to complexify the fermions in Euclidean signature and impose Lorentzian reality conditions only after analytic continuation. That is often correct, but it should be stated rather than silently assumed.

## Common pitfalls

**Calling every four-component spinor “Dirac.”** A Majorana spinor is often written with four components, but it is not a generic Dirac spinor. It satisfies a reality constraint and has half as many independent complex components.

**Thinking a Weyl spinor is half of a nonrelativistic spinor.** A Weyl spinor is an irreducible representation of the Lorentz group, not merely a two-component notation for ordinary spin. Its transformation law involves $SL(2,\mathbb C)$, not just $SU(2)$.

**Confusing chirality with helicity for massive fermions.** Chirality is defined by $\gamma^5$. Helicity is spin projected along momentum. They coincide only in the massless sense described above.

**Forgetting gauge charges in mass terms.** Lorentz invariance is not enough. A Majorana mass for a charged fermion may be Lorentz-invariant but gauge-forbidden.

**Treating bars uniformly.** In two-component notation, a bar often means complex conjugation and dotted indices. In four-component notation, $\bar\Psi$ means $\Psi^\dagger\gamma^0$. These are related but not identical operations.

**Using Lorentzian reality conditions in Euclidean calculations without comment.** Euclidean spinors have their own signature-dependent reality structure. This is one of the sneaky places where formal manipulations become notational quicksand.

## Relations to other pages

This page builds directly on [Gamma-Matrix Conventions](/math-toolkit/clifford-spinors/gamma-matrix-conventions/), [Spin Groups](/math-toolkit/clifford-spinors/spin-groups/), and [SL(2,C) and the Lorentz Group](/math-toolkit/groups-representations/sl2c-and-lorentz-group/). It prepares the ground for spinor bilinears, Fierz identities, spinor-helicity methods, Dirac fields, Majorana fermions, chiral gauge theories, supersymmetry, anomalies, and neutrino mass models.

The representation-theory input belongs to the groups and spin chapters. The field-theory use of these spinors belongs to later pages on free fermion fields, fermion propagators, Yukawa couplings, gauge anomalies, and Standard Model fermions.

## Research status

The Lorentzian representation theory of Weyl, Dirac, and Majorana spinors in four dimensions is settled. The subtle work begins when this representation theory is combined with gauge symmetry, topology, quantization, and regularization.

Examples include chiral gauge anomaly cancellation, global anomalies, Majorana fermion path-integral signs, Pfaffian phases, fermions on manifolds without chosen spin structure, Euclidean supersymmetry, and lattice formulations of chiral fermions. The basic definitions are old; the best bookkeeping is still precious.

## Exercises

### Exercise 1: Split the Dirac equation

Using

$$
\gamma^\mu=
\begin{pmatrix}
0 & \sigma^\mu \\
\bar\sigma^\mu & 0
\end{pmatrix},
\qquad
\Psi_D=\begin{pmatrix}\chi_\alpha\\ \bar\eta^{\dot\alpha}\end{pmatrix},
$$

show that

$$
(i\gamma^\mu\partial_\mu-m)\Psi_D=0
$$

is equivalent to the two coupled equations given in the page.

<details><summary><strong>Solution</strong></summary>

Multiplying out the block matrix gives

$$
i\gamma^\mu\partial_\mu\Psi_D
=
\begin{pmatrix}
i\sigma^\mu_{\alpha\dot\alpha}\partial_\mu\bar\eta^{\dot\alpha}\\
i\bar\sigma^{\mu\dot\alpha\alpha}\partial_\mu\chi_\alpha
\end{pmatrix}.
$$

Subtracting $m\Psi_D$ gives

$$
\begin{pmatrix}
i\sigma^\mu_{\alpha\dot\alpha}\partial_\mu\bar\eta^{\dot\alpha}-m\chi_\alpha\\
i\bar\sigma^{\mu\dot\alpha\alpha}\partial_\mu\chi_\alpha-m\bar\eta^{\dot\alpha}
\end{pmatrix}
=0.
$$

Therefore

$$
i\sigma^\mu_{\alpha\dot\alpha}\partial_\mu\bar\eta^{\dot\alpha}-m\chi_\alpha=0,
$$

and

$$
i\bar\sigma^{\mu\dot\alpha\alpha}\partial_\mu\chi_\alpha-m\bar\eta^{\dot\alpha}=0.
$$

When $m=0$, the two equations decouple into Weyl equations.

</details>

### Exercise 2: Gauge charge of a Majorana mass

Let $\chi$ be a left-handed Weyl spinor with $U(1)$ charge $q$. Under

$$
\chi\mapsto e^{iq\alpha}\chi,
$$

how does $\chi\chi$ transform? When is a Majorana mass allowed by this $U(1)$ symmetry?

<details><summary><strong>Solution</strong></summary>

The bilinear transforms as

$$
\chi\chi\mapsto e^{2iq\alpha}\chi\chi.
$$

Therefore the Majorana mass term

$$
-\frac12m\chi\chi+\text{h.c.}
$$

is invariant only if $e^{2iq\alpha}=1$ for all allowed transformations. For a continuous ordinary $U(1)$ symmetry, this requires

$$
q=0.
$$

If $q\ne0$, the Majorana mass violates the $U(1)$ charge by two units of $q$ and is forbidden unless the symmetry is broken or reduced to a suitable discrete subgroup.

</details>

### Exercise 3: Chirality projectors in chiral basis

Using

$$
\gamma^5=
\begin{pmatrix}
-\mathbf 1 & 0 \\
0 & \mathbf 1
\end{pmatrix},
$$

compute $P_L\Psi$ and $P_R\Psi$ for

$$
\Psi=\begin{pmatrix}\psi_L\\\psi_R\end{pmatrix}.
$$

<details><summary><strong>Solution</strong></summary>

The projectors are

$$
P_L=\frac{1-\gamma^5}{2}
=
\begin{pmatrix}
\mathbf 1 & 0\\
0 & 0
\end{pmatrix},
$$

and

$$
P_R=\frac{1+\gamma^5}{2}
=
\begin{pmatrix}
0 & 0\\
0 & \mathbf 1
\end{pmatrix}.
$$

Therefore

$$
P_L\Psi=
\begin{pmatrix}
\psi_L\\
0
\end{pmatrix},
\qquad
P_R\Psi=
\begin{pmatrix}
0\\
\psi_R
\end{pmatrix}.
$$

So the upper two components are left-chiral and the lower two components are right-chiral in this convention.

</details>

### Exercise 4: Dirac versus Majorana data

Explain why

$$
\Psi_D=\begin{pmatrix}\chi_\alpha\\\bar\eta^{\dot\alpha}\end{pmatrix}
$$

contains more independent data than

$$
\Psi_M=\begin{pmatrix}\chi_\alpha\\\chi^{\dagger\dot\alpha}\end{pmatrix}.
$$

<details><summary><strong>Solution</strong></summary>

In $\Psi_D$, the left Weyl spinor $\chi_\alpha$ and the right Weyl spinor $\bar\eta^{\dot\alpha}$ are independent fields. Equivalently, the Dirac spinor is built from two independent left-handed Weyl spinors, $\chi$ and $\eta$, after conjugating one of them into the right-handed representation.

In $\Psi_M$, the lower component is fixed to be the complex conjugate of the upper component. There is only one independent Weyl spinor. This is the four-component expression of the Majorana reality condition

$$
\Psi_M^c=\Psi_M.
$$

Thus a Majorana spinor has half the independent complex field data of a generic Dirac spinor.

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I. See the treatment of one-particle states, Lorentz representations, and spinor fields.
- M. Srednicki, *Quantum Field Theory*. See the chapters on representations of the Lorentz group, left- and right-handed spinor fields, spinor indices, spinor Lagrangians, and Majorana fields.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*. See the chapters on spinors, chirality, helicity, Majorana and Weyl fermions, and Standard Model fermions.
- A. Zee, *Quantum Field Theory in a Nutshell*. Useful for physical intuition about Dirac and Majorana fermions.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*. Useful for Lorentz covariance, fields, and symmetry logic.

## Version history

- **2026-06-24:** Initial polished draft. Defined Weyl, Dirac, and Majorana spinors in mostly-minus chiral conventions, including two-component notation, equations of motion, mass terms, chirality versus helicity, and Euclidean warnings.
