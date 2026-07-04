---
title: "Fermion Zero Modes"
description: "Explains how Dirac zero modes in instanton backgrounds are counted by the index theorem and turn instantons into selection rules and ’t Hooft vertices."
sidebar:
  label: "Fermion Zero Modes"
  order: 7
level: Advanced
status: "Polished draft"
source: "Srednicki ch. 94; Shifman chs. 5 and 8; Mariño chs. 4–5; Coleman; Nakahara."
topics:
  - fermion zero modes
  - index theorem
  - instantons
  - Grassmann integration
  - ’t Hooft vertex
  - chiral symmetry
  - anomaly
canonicalTopics:
  - nonperturbative-qft
  - fermion-zero-modes
  - instantons
  - index-theorem
  - anomalies
researchStatus:
  established:
    - "In a topologically nontrivial gauge background, normalizable Dirac zero modes are counted by an index theorem and force exact Grassmann selection rules in the path integral."
  active:
    - "In strongly coupled theories, the semiclassical instanton expansion and zero-mode-induced vertices may require additional infrared input, lattice definitions, or effective-field-theory interpretation."
---

## Summary

Fermion zero modes are the reason instantons are not merely small corrections to bosonic correlation functions. In a topologically nontrivial gauge background, the Euclidean Dirac operator can have normalizable zero-eigenvalue solutions,

$$
\mathcal D_E \psi_0=0.
$$

For massless fermions, such modes make the ordinary fermion determinant vanish. That sentence sounds like the instanton has disappeared. It has not. The correct statement is sharper: the instanton contributes only to correlation functions whose operator insertions, or whose fermion mass terms, saturate the Grassmann integrations associated with the zero modes.

The number of unpaired chiral zero modes is topological. With the gauge-field normalization used in this volume,

$$
Q=\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu},
$$

and with fermions in a representation $R$ satisfying

$$
\operatorname{tr}_R(T^aT^b)=T(R)\delta^{ab},
$$

the index theorem says

$$
\operatorname{ind}\mathcal D_R
\equiv n_+-n_-
=\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}_R F_{\mu\nu}\widetilde F_{\mu\nu}
=2T(R)Q.
$$

Here $n_\pm$ count normalizable zero modes with $\gamma_5\psi_0=\pm\psi_0$. For a Dirac fermion in the fundamental representation of $SU(N)$, $T(F)=1/2$, so a charge-one instanton has one unpaired zero mode per flavor, in a chirality fixed by the sign convention for $Q$ and $\gamma_5$.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A schematic map from instanton topology to Dirac zero modes, Grassmann saturation, and the ’t Hooft vertex.](/figures/nonperturbative-qft/fermion-zero-modes-selection-rule.svg)

<figcaption>

A topological gauge background changes the Dirac spectrum. Nonzero modes pair by chirality, while zero modes are unpaired and are counted by the index theorem. The corresponding Grassmann integrations must be saturated by operator insertions or masses, producing instanton-induced selection rules and the ’t Hooft vertex.

</figcaption>
</figure>

The practical moral is simple and merciless: in an instanton background, counting zero modes is not optional bookkeeping. It tells you which amplitudes vanish, which amplitudes survive, and which symmetries are actually selection rules of the quantum theory.

## Prerequisites

You should know [Instantons in Field Theory](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-field-theory/), [Yang–Mills Instantons](/nonperturbative-qft/instantons-tunneling-theta-vacua/yang-mills-instantons/), [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/), [Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/), and [Tunneling Between Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/tunneling-between-vacua/).

You should also know the general semiclassical treatment of [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/) and [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/). Bosonic zero modes become ordinary integrals over moduli. Fermion zero modes become Grassmann integrals, and that one change is responsible for most of the physics on this page.

We work in Euclidean signature and use the topological-charge convention of [Conventions and Notation](/nonperturbative-qft/conventions/). Signs of chirality vary across books because authors choose different Euclidean gamma matrices, dual-field conventions, and definitions of $Q$. The invariant statements are the index formula and the selection rule, not the isolated phrase “left-handed instanton zero mode.”

## Core idea

Consider a massless Dirac fermion in a fixed Euclidean gauge background,

$$
S_F=\int d^4x\,\overline\psi\,\mathcal D_E\psi,
\qquad
\mathcal D_E=\gamma_\mu D_\mu.
$$

The Euclidean fields $\psi$ and $\overline\psi$ are independent Grassmann variables. If $\mathcal D_E$ has eigenfunctions

$$
\mathcal D_E u_n=\lambda_n u_n,
$$

then we expand

$$
\psi(x)=\sum_n c_nu_n(x),
\qquad
\overline\psi(x)=\sum_n \overline c_n u_n^\dagger(x),
$$

so that schematically

$$
S_F=\sum_n \overline c_n\lambda_n c_n.
$$

For a nonzero eigenvalue $\lambda_n\ne0$, the Gaussian Grassmann integral gives a factor of $\lambda_n$:

$$
\int d\overline c_n\,dc_n\,e^{-\overline c_n\lambda_n c_n}=\lambda_n.
$$

A zero mode is different. If $\lambda_0=0$, then the action contains no term involving $\overline c_0c_0$. The integral over an unsaturated Grassmann variable vanishes:

$$
\int dc_0\,1=0.
$$

Therefore the massless fermion determinant vanishes in any background with at least one zero mode,

$$
\det\mathcal D_E=0.
$$

But a correlation function can survive. If an operator insertion contains the corresponding zero-mode Grassmann variable, then

$$
\int dc_0\,c_0=1.
$$

That is the whole mechanism. Instantons in theories with massless fermions are filtered by Grassmann saturation. The surviving amplitudes come with explicit fermion fields, or with mass insertions that soak up the zero modes.

## Chirality and paired eigenvalues

In a massless vectorlike gauge theory, the Euclidean Dirac operator anticommutes with chirality,

$$
\{\mathcal D_E,\gamma_5\}=0.
$$

If $u$ is an eigenfunction with eigenvalue $\lambda\ne0$, then $\gamma_5u$ is an eigenfunction with eigenvalue $-\lambda$:

$$
\mathcal D_E(\gamma_5u)=-\lambda(\gamma_5u).
$$

Thus nonzero eigenvalues come in opposite-sign pairs. These paired modes do not contribute to the index. Zero modes can be chosen to have definite chirality,

$$
\gamma_5u_0=+u_0
\qquad\text{or}\qquad
\gamma_5u_0=-u_0,
$$

and there is no guarantee that the two chiralities occur in pairs.

The unpaired difference

$$
n_+-n_-
$$

is stable under smooth deformations of the gauge field that do not change topology. It cannot change continuously, because it is an integer. This is why a topological invariant can count solutions of a differential equation.

For a charge-one instanton in the fundamental representation of $SU(N)$, the index is one. In common conventions this means one normalizable zero mode of one chirality per massless Dirac flavor. An anti-instanton has the opposite chirality. If you change the sign convention for $Q$ or for $\gamma_5$, the words “left” and “right” swap, but the physical selection rule does not.

## Index theorem in gauge theory

The index theorem relates the analytic data of the Dirac operator to the topological data of the gauge field. With our conventions,

$$
\operatorname{ind}\mathcal D_R
=n_+-n_-
=\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}_R F_{\mu\nu}\widetilde F_{\mu\nu}.
$$

If $R$ is the fundamental representation of $SU(N)$, this reduces to

$$
\operatorname{ind}\mathcal D_F=Q.
$$

For a general representation,

$$
\operatorname{ind}\mathcal D_R=2T(R)Q.
$$

Examples:

| Representation | $T(R)$ for $SU(N)$ | Index in charge $Q$ background |
|---|---:|---:|
| fundamental $F$ | $1/2$ | $Q$ |
| adjoint | $N$ | $2NQ$ |
| two-index representations | representation-dependent | $2T(R)Q$ |

The adjoint entry matters in supersymmetric Yang–Mills theory: one adjoint Weyl fermion has $2NQ$ zero modes in a charge-$Q$ instanton background. That is the seed of many exact supersymmetric instanton selection rules.

The index theorem is not an approximation. What is approximate is the use of a single-instanton saddle to compute an observable. The existence and net number of zero modes in a smooth background of charge $Q$ are topological facts.

## Grassmann saturation

Let a gauge background of charge $Q=1$ have one zero mode $u_0$ for a massless Dirac fermion. The zero-mode part of the field expansion is

$$
\psi(x)=c_0u_0(x)+\text{nonzero modes}.
$$

Then the one-point function of $\psi$ vanishes for ordinary symmetry reasons, but the schematic zero-mode part illustrates the rule:

$$
\int dc_0\,\psi(x)
=\int dc_0\,c_0u_0(x)
=u_0(x).
$$

For a Dirac fermion, the full zero-mode saturation usually involves the corresponding variables from $\psi$ and $\overline\psi$, so the instanton contribution to a local effective interaction contains a fermion bilinear per flavor. With $N_f$ massless Dirac fermions in the fundamental representation of $SU(N_c)$, a charge-one instanton produces the schematic interaction

$$
\mathcal O_I
\sim
e^{-S_I+i\theta}
\det_{f,g}\left(\overline\psi_{R f}\psi_{L g}\right),
$$

while an anti-instanton produces the conjugate interaction

$$
\mathcal O_{\overline I}
\sim
e^{-S_I-i\theta}
\det_{f,g}\left(\overline\psi_{L f}\psi_{R g}\right).
$$

The determinant is over flavor indices. The spin, color, and zero-mode wavefunction structure has been suppressed; it matters for detailed calculations, but the flavor determinant already displays the essential symmetry content.

This is the famous ’t Hooft vertex. It is not guessed from a Feynman diagram. It is forced by the zero-mode measure.

## Mass insertions and determinant zeros

Mass terms can also saturate zero modes. For one Dirac fermion,

$$
S_m=\int d^4x\,m\overline\psi\psi.
$$

In the zero-mode subspace this contributes a term proportional to

$$
m\overline c_0c_0.
$$

Thus a massive fermion determinant in a background with one zero-mode pair contains a factor of $m$ rather than zero. For $N_f$ fundamental Dirac fermions and topological charge $Q$, the leading mass dependence of the sector weight is schematically

$$
\prod_{f=1}^{N_f}m_f^{|Q|},
$$

up to nonzero-mode determinants and collective-coordinate factors.

This explains an important fact about theta dependence in QCD-like theories. If a quark is exactly massless, the vacuum functional in sectors with nonzero topological charge is suppressed by unsaturated zero modes unless appropriate insertions are present. Equivalently, an anomalous chiral rotation can remove the theta angle from the massless theory. With massive quarks, the mass matrix phases and the theta angle combine into a physical invariant.

A good slogan is:

$$
\text{zero modes turn topology into selection rules.}
$$

## The ’t Hooft vertex

For $N_f$ massless Dirac fermions in the fundamental representation, the instanton-induced vertex is often written schematically as

$$
\mathcal L_{\mathrm{eff}}^{(I)}
\propto
\kappa\,e^{i\theta}
\det_{f,g}\left(\overline\psi_{R f}\psi_{L g}\right)
+\kappa\,e^{-i\theta}
\det_{f,g}\left(\overline\psi_{L f}\psi_{R g}\right),
$$

where $\kappa$ includes the instanton density, determinant ratio, collective-coordinate measure, and any infrared regulator or running-coupling information. This expression is local only after the instanton size has been integrated out or approximated in a regime where the instanton is small compared with the scales of interest.

The vertex has three important symmetry properties.

First, it preserves vector flavor symmetries and baryon number. It does not create net quark number in QCD.

Second, it violates the classical axial $U(1)_A$ symmetry. Under an axial rotation, the determinant transforms by a phase. This is exactly compensated by the anomaly-induced shift of $\theta$ in the full path integral.

Third, it respects anomaly-free chiral flavor symmetries. For massless QCD with $N_f$ flavors, the determinant structure is compatible with the non-Abelian chiral symmetries, while the anomalous singlet axial symmetry is not a true symmetry of the quantum theory.

The same logic appears in many theories, not just QCD. In supersymmetric gauge theory, adjoint fermion zero modes determine which superpotential or correlation-function contributions are possible. In electroweak theory, $SU(2)$ instantons and finite-temperature sphalerons violate anomalous combinations of baryon and lepton number.

## Selection rules

The integrated axial anomaly for one massless Dirac fermion in representation $R$ gives

$$
\Delta Q_5
=2\operatorname{ind}\mathcal D_R
=4T(R)Q.
$$

For $N_f$ fundamental Dirac fermions,

$$
\Delta Q_5=2N_fQ.
$$

This is the operator-language version of the zero-mode counting. A charge-one instanton changes axial charge by $2N_f$ units. Therefore a correlation function in the one-instanton sector can be nonzero only if its insertions carry the corresponding axial charge.

Equivalently, if a correlator is built from operators whose axial charge does not match the zero-mode measure, the Grassmann integral kills the instanton contribution. This is why instantons produce very specific vertices rather than arbitrary symmetry-violating terms.

The selection rule is exact. The coefficient multiplying the allowed vertex is a dynamical question. In weakly coupled semiclassical regimes, it can be computed from the instanton action, determinants, and collective-coordinate integrals. In strongly coupled regimes, the selection rule remains true, but the semiclassical coefficient may not be reliable.

## Physical consequences

Fermion zero modes give a unified explanation of several famous facts.

**Theta can become unobservable with a massless quark.** In a QCD-like theory with at least one exactly massless quark, an axial rotation can shift away $\theta$. The zero-mode perspective says the same thing: nonzero-$Q$ vacuum sectors require mass or operator insertions to saturate the zero modes.

**The axial singlet symmetry is not a quantum symmetry.** The instanton-induced determinant vertex violates $U(1)_A$ while preserving anomaly-free symmetries. This is closely related to the axial anomaly.

**Some amplitudes are nonzero only because of instantons.** A correlator carrying the right anomalous charge can receive a leading contribution from instanton zero modes even when ordinary perturbation theory around the trivial vacuum gives zero.

**Not every zero-mode statement is a semiclassical estimate.** The index is topological. The dilute instanton density is semiclassical. Mixing those two levels of certainty is a classic source of mistakes.

## Common pitfalls

**Saying the instanton contribution vanishes because the determinant vanishes.** The vacuum determinant may vanish in a massless theory, but correlation functions with the right fermion insertions can survive. The zero modes are telling you what to insert.

**Forgetting that $\psi$ and $\overline\psi$ are independent in the Euclidean path integral.** Grassmann saturation is a statement about integration variables, not about complex conjugation in Lorentzian Hilbert space.

**Treating the index as the full number of zero modes.** The index gives $n_+-n_-$. In a generic instanton background, one often knows more, such as vanishing of the opposite-chirality zero modes. In a general background, the total number $n_++n_-$ may contain paired zero modes not fixed by topology.

**Confusing chirality conventions.** The statement “instantons have left-handed zero modes” is convention-sensitive. The index formula and the transformation of the ’t Hooft vertex are safer.

**Assuming the local ’t Hooft vertex is always valid.** The vertex is a low-energy representation of zero-mode saturation. Its coefficient and locality depend on the instanton size integral, running coupling, masses, and infrared physics.

**Calling the index theorem a perturbative anomaly calculation.** The index theorem is a topological result about differential operators. The anomaly is a local quantum statement about the measure or regulator. They agree beautifully, but they are not the same calculation.

## Relations to other pages

- [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/) explains the general saddle-point role of zero modes before specializing to fermions.
- [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/) treats bosonic zero modes as ordinary moduli integrals.
- [Yang–Mills Instantons](/nonperturbative-qft/instantons-tunneling-theta-vacua/yang-mills-instantons/) gives the gauge-field saddle whose topology produces the zero modes.
- [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/) fixes the normalization of $Q$ used in the index theorem.
- [Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/) explains why the factor $e^{i\theta Q}$ appears in instanton sectors.
- [Instantons and Anomalies](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-and-anomalies/) connects the zero-mode selection rules to the local axial anomaly.
- [Condensates](/nonperturbative-qft/order-parameters-diagnostics/condensates/) discusses order parameters such as chiral condensates, which interact subtly with instanton physics.

## Research status

**Established.** The index theorem, the pairing of nonzero Dirac eigenvalues, the Grassmann saturation rule, and the existence of ’t Hooft vertices in instanton backgrounds are standard nonperturbative results.

**Convention-dependent.** The sign of chirality attached to instantons versus anti-instantons depends on $\gamma_5$, Euclidean continuation, and topological-charge conventions. This page emphasizes formulas that translate cleanly.

**Active.** In strongly coupled QCD-like theories, instanton ensembles, infrared-divergent size integrals, overlap with chiral symmetry breaking, and relation to confinement are dynamical questions. The selection rules are robust; the semiclassical numerical weight may not be.

**Speculative.** None of the basic zero-mode counting is speculative. Speculation enters only when one tries to use uncontrolled instanton ensembles as a full model of strongly coupled vacuum dynamics.

## Exercises

### Exercise 1: Pairing of nonzero eigenvalues

Assume $\{\mathcal D_E,\gamma_5\}=0$ and $\mathcal D_Eu=\lambda u$ with $\lambda\ne0$. Show that $\gamma_5u$ is an eigenfunction with eigenvalue $-\lambda$. Explain why this pairing does not determine the number of zero modes.

<details>
<summary><strong>Solution</strong></summary>

Using the anticommutator,

$$
\mathcal D_E(\gamma_5u)=-\gamma_5\mathcal D_Eu=-\lambda\gamma_5u.
$$

Thus nonzero eigenvalues are paired as $\lambda$ and $-\lambda$. For $\lambda=0$, this argument maps a zero mode to another zero mode, not to a distinct eigenvalue. Zero modes can be chosen to have definite chirality, and the difference $n_+-n_-$ is not fixed by nonzero-mode pairing. It is fixed by topology through the index theorem.

</details>

### Exercise 2: Grassmann saturation

Evaluate the two Grassmann integrals

$$
\int dc\,1,
\qquad
\int dc\,c.
$$

Then explain why a massless fermion zero mode makes the determinant vanish but can give a nonzero correlator with an insertion of the corresponding fermion field.

<details>
<summary><strong>Solution</strong></summary>

By the defining rules of Grassmann integration,

$$
\int dc\,1=0,
\qquad
\int dc\,c=1.
$$

If a zero-mode Grassmann coefficient $c_0$ does not appear in the action, the vacuum functional contains an unsaturated integral $\int dc_0\,1$, which vanishes. If an operator insertion contains the zero-mode piece of the field, it supplies a factor of $c_0$, and the integral becomes $\int dc_0\,c_0=1$. This is why zero modes kill some amplitudes and enable others.

</details>

### Exercise 3: Axial charge violation from the index

For $N_f$ massless Dirac fermions in the fundamental representation of $SU(N)$, use $T(F)=1/2$ to show that a charge-$Q$ instanton background violates singlet axial charge by

$$
\Delta Q_5=2N_fQ.
$$

<details>
<summary><strong>Solution</strong></summary>

For one Dirac fermion in representation $R$,

$$
\Delta Q_5=2\operatorname{ind}\mathcal D_R=4T(R)Q.
$$

In the fundamental representation, $T(F)=1/2$, so one Dirac flavor gives

$$
\Delta Q_5=2Q.
$$

With $N_f$ flavors, the singlet axial current is the sum of the flavor currents, so

$$
\Delta Q_5=2N_fQ.
$$

For $Q=1$, this is the axial-charge violation encoded by the $2N_f$ fermion legs of the ’t Hooft vertex.

</details>

### Exercise 4: Mass suppression in nonzero topological sectors

Consider $N_f$ fundamental Dirac fermions with small masses $m_f$ in a background of charge $Q=1$. Explain why the fermion determinant is proportional to

$$
\prod_{f=1}^{N_f}m_f
$$

to leading order in the masses.

<details>
<summary><strong>Solution</strong></summary>

Each flavor has one zero mode in a charge-one fundamental instanton background. Without a mass or insertion, the corresponding Grassmann integration is unsaturated and the determinant vanishes. A mass term supplies one bilinear factor capable of saturating the zero-mode variables for that flavor. Therefore each flavor contributes one power of its mass, giving

$$
\det(\mathcal D_E+M)\propto \prod_{f=1}^{N_f}m_f
$$

up to nonzero-mode determinants and normalization factors. For charge $Q$, the leading mass dependence is generalized schematically to $\prod_f m_f^{|Q|}$.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, especially the discussion of quarks and theta vacua.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapters on instantons and anomalies.
- M. Mariño, *Instantons and Large N*, especially the chapters on Yang–Mills instantons and instantons with fermions.
- S. Coleman, *Aspects of Symmetry*, for the classic instanton and anomaly viewpoint.
- M. Nakahara, *Geometry, Topology and Physics*, for the index-theorem and gauge-topology background.
- G. ’t Hooft, “Symmetry Breaking Through Bell–Jackiw Anomalies,” and “Computation of the Quantum Effects Due to a Four-Dimensional Pseudoparticle,” for the original instanton zero-mode and vertex analysis.

## Version history

- **2026-06-27:** Initial polished draft. Added after Theta Vacua and Tunneling Between Vacua as the first fermionic page in the instantons chapter.
