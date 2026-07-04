---
title: "Instantons and Anomalies"
description: "Explains how instanton zero modes realize anomalous chiral selection rules, theta-angle shifts, and ’t Hooft vertices in gauge theory."
sidebar:
  label: "Instantons and Anomalies"
  order: 8
level: Advanced
status: "Polished draft"
source: "Srednicki ch. 94; Schwartz ch. 30; Shifman chs. 5 and 8; Mariño ch. 5; Coleman."
topics:
  - instantons
  - anomalies
  - axial anomaly
  - theta angle
  - fermion zero modes
  - ’t Hooft vertex
  - chiral symmetry
canonicalTopics:
  - nonperturbative-qft
  - instantons
  - anomalies
  - theta-vacua
  - chiral-symmetry
researchStatus:
  established:
    - "Instanton zero modes and the local axial anomaly give the same anomalous selection rules for chiral charge in topologically nontrivial gauge backgrounds."
  active:
    - "The role of instantons in strongly coupled anomaly matching, dense ensembles, finite-temperature transitions, and theories with subtle global forms remains an active interface between semiclassics, lattice theory, and topology."
---

## Summary

Instantons and anomalies are two windows onto the same obstruction. The local anomaly says that a classical chiral symmetry is not a symmetry of the regulated quantum path-integral measure. Instantons say that topologically nontrivial gauge backgrounds contain fermion zero modes, so correlation functions obey anomalous selection rules.

For $N_f$ Dirac fermions in the fundamental representation of $SU(N)$, the singlet axial current satisfies schematically, in the conventions of this volume,

$$
\partial_\mu J_A^\mu
=
2i\overline\psi M\gamma_5\psi
+
\frac{N_f}{8\pi^2}\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}.
$$

For massless fermions in a gauge background of topological charge $Q$,

$$
\Delta Q_A
=
\int d^4x\,\partial_\mu J_A^\mu
=
2N_fQ.
$$

That is exactly the amount of axial charge carried by the fermion zero modes in the instanton background. The instanton-induced effective interaction is the ’t Hooft vertex,

$$
\mathcal L_{\mathrm{eff}}^{(I)}
\sim
\kappa e^{i\theta}
\det_{f,g}\left(\overline\psi_{R f}\psi_{L g}\right)
+
\kappa e^{-i\theta}
\det_{f,g}\left(\overline\psi_{L f}\psi_{R g}\right).
$$

This vertex preserves anomaly-free symmetries and violates the anomalous axial $U(1)_A$ in exactly the way required by the anomaly.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A dictionary between the local anomaly, the integrated selection rule, the index theorem, fermion zero modes, theta shifts, and the ’t Hooft vertex.](/figures/nonperturbative-qft/instantons-anomalies-dictionary.svg)

<figcaption>

The local anomaly, integrated charge violation, index theorem, zero-mode saturation, theta-angle shift, and ’t Hooft vertex are different entries in one dictionary. For $N_f$ fundamental Dirac fermions, they encode the same selection rule $\Delta Q_A=2N_fQ$.

</figcaption>
</figure>

A crucial warning: instantons do not “cause” the anomaly in the narrow sense. The anomaly is a local ultraviolet statement that can be derived around the trivial background. Instantons are topologically nontrivial backgrounds that make the anomalous symmetry violation visible as a finite selection rule.

## Prerequisites

You should know [Fermion Zero Modes](/nonperturbative-qft/instantons-tunneling-theta-vacua/fermion-zero-modes/), [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/), [Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/), and [Tunneling Between Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/tunneling-between-vacua/).

You should also know the distinction between a classical symmetry of the action and a quantum symmetry of the path integral. An anomaly occurs when the action transformation can be compensated locally, but the measure or regulator cannot be chosen to preserve all the desired symmetries at once.

This page focuses on the singlet axial anomaly in QCD-like gauge theories because it is the cleanest bridge from instanton zero modes to physical selection rules. Gauge anomalies, mixed ’t Hooft anomalies, higher-form anomalies, and global anomalies are broader topics whose natural home is the Symmetry, Anomalies, and Topology volume.

## Core idea

There are two standard derivations of the axial anomaly.

The first is perturbative: a regulated one-loop triangle diagram shows that the axial current cannot be conserved together with gauge invariance.

The second is path-integral based: under a local axial rotation, the fermion action changes in the expected Noether way, but the fermion measure acquires a nontrivial Jacobian.

For a Dirac fermion, write an axial rotation as

$$
\psi\mapsto e^{-i\alpha\gamma_5}\psi,
\qquad
\overline\psi\mapsto\overline\psi e^{-i\alpha\gamma_5}.
$$

In a gauge background with topological charge $Q$, the measure transforms by a phase whose integrated effect is proportional to $Q$. For $N_f$ fundamental Dirac fermions,

$$
\mathcal D\overline\psi\mathcal D\psi
\mapsto
\exp\left(-2iN_f\alpha Q\right)
\mathcal D\overline\psi\mathcal D\psi,
$$

up to the sign convention for $\alpha$ and $Q$. Since the theta term weights the same sector by $e^{i\theta Q}$, this rotation shifts

$$
\theta\mapsto \theta-2N_f\alpha
$$

with the convention just chosen. A source that defines the axial rotation or $Q$ with the opposite sign will write the opposite shift.

Thus $\theta$ is not independent of chiral phase conventions. In QCD-like theories with a quark mass matrix $M$, the invariant CP-violating combination is schematically

$$
\overline\theta=\theta+\arg\det M,
$$

again up to the global sign convention for the axial rotation. If one quark is exactly massless, one can use its axial rotation to remove $\overline\theta$.

## Integrated anomaly and topological charge

Using the topological-charge convention

$$
Q=\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu},
$$

the singlet axial anomaly for $N_f$ fundamental Dirac fermions is

$$
\partial_\mu J_A^\mu
=
2i\overline\psi M\gamma_5\psi
+
\frac{N_f}{8\pi^2}\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}.
$$

In the massless limit,

$$
\int d^4x\,\partial_\mu J_A^\mu
=
2N_fQ.
$$

This equation has a direct instanton interpretation. A charge-one instanton has one fundamental zero mode per massless Dirac flavor in the relevant chirality. The corresponding ’t Hooft vertex contains $2N_f$ fermion fields and carries axial charge $2N_f$.

For a general representation $R$, the replacement is

$$
2N_fQ
\quad\longrightarrow\quad
4T(R)Q
$$

for one Dirac fermion in $R$, or the sum of this quantity over all fermion species. This matches the index-theorem relation

$$
\Delta Q_A=2\operatorname{ind}\mathcal D_R.
$$

## The theta-angle shift

The theta-dependent Euclidean partition function is

$$
Z(\theta)
=
\sum_Q e^{i\theta Q}Z_Q.
$$

An axial field redefinition is a change of integration variables, so physics cannot depend on the arbitrary phase convention used for fermions. However, the measure is anomalous, and the theta angle shifts. With $N_f$ fundamental Dirac fermions and the axial rotation convention above,

$$
\theta\to \theta-2N_f\alpha.
$$

The mass matrix transforms too. If

$$
\overline\psi_L M\psi_R+\overline\psi_RM^\dagger\psi_L
$$

is present, then an axial rotation changes the phase of $M$. Therefore the physical CP-violating parameter is not simply $\theta$; it is the invariant combination of $\theta$ and the phase of the fermion mass matrix.

For QCD-like theories,

$$
\overline\theta=\theta+\arg\det M
$$

is the standard convention, modulo signs inherited from the definition of the axial rotation. If $\det M=0$, the phase is not meaningful in the same way, and an axial rotation of a massless fermion can remove $\theta$ from the theory.

This is a beautiful place where three statements become one:

| Statement | Same physics in another language |
|---|---|
| $U(1)_A$ is anomalous. | The fermion measure is not invariant. |
| $\theta$ shifts under axial rotations. | $\theta$ is tied to the phase of $\det M$. |
| Instantons have fermion zero modes. | Nonzero-$Q$ sectors require insertions or masses. |

## The ’t Hooft vertex as anomaly bookkeeping

The instanton vertex for $N_f$ massless fundamental Dirac fermions is schematically

$$
\mathcal O_I
=
e^{i\theta}\det_{f,g}\left(\overline\psi_{R f}\psi_{L g}\right).
$$

The anti-instanton vertex is the conjugate,

$$
\mathcal O_{\overline I}
=
e^{-i\theta}\det_{f,g}\left(\overline\psi_{L f}\psi_{R g}\right).
$$

Under the axial rotation

$$
\psi_L\mapsto e^{+i\alpha}\psi_L,
\qquad
\psi_R\mapsto e^{-i\alpha}\psi_R,
$$

the determinant carries a phase. The theta factor carries the opposite phase once $\theta$ is shifted by the anomaly. Thus the full instanton contribution is invariant under a change of variables, even though neither the naive fermion operator nor $e^{i\theta Q}$ should be considered alone.

This is what good anomaly bookkeeping looks like: the effective vertex violates the classical $U(1)_A$ charge, but it does not violate the true quantum consistency conditions. It preserves the anomaly-free symmetries and realizes the anomalous one by a theta shift.

For $N_f=1$, the determinant is just a bilinear,

$$
\overline\psi_R\psi_L.
$$

This explains why instantons in a one-flavor QCD-like theory can generate an effective contribution with the same quantum numbers as a mass term. For $N_f>1$, the determinant structure couples all flavors and is central to the distinction between singlet axial symmetry and non-Abelian chiral symmetries.

## Anomaly matching versus instanton calculation

The phrase “’t Hooft anomaly” is broader than the instanton vertex. An ’t Hooft anomaly is an obstruction to gauging a global symmetry or to preserving it together with background gauge invariance. It must match along RG flows.

Instanton zero modes often provide a concrete semiclassical realization of anomaly-related selection rules, but anomaly matching does not require a dilute instanton gas. In strongly coupled theories, anomalies are still exact data even when no semiclassical instanton calculation is reliable.

Keep the hierarchy straight:

- the **local anomaly equation** is exact once the regulator and symmetries are specified;
- the **index theorem** gives exact zero-mode counting in a topological background;
- the **single-instanton coefficient** is a semiclassical approximation;
- the **IR phase** determines how the anomaly is realized in the spectrum, condensates, massless modes, topological order, or symmetry breaking.

This separation is one of the main reasons anomalies are so powerful: their existence does not depend on solving the strongly coupled theory.

## Examples

### One-flavor QCD-like theory

With one massless Dirac quark, an axial rotation can shift $\theta$ arbitrarily. Thus $\theta$ is not a physical parameter. In the zero-mode language, nonzero topological sectors have unsaturated fermion zero modes in the vacuum functional unless the mass or appropriate operator insertions are supplied.

If the quark is given a small complex mass, the phase of the mass and $\theta$ combine into $\overline\theta$. The instanton vertex has the same chiral quantum numbers as a mass term, which makes this connection visible in the effective action.

### Many-flavor QCD-like theory

For $N_f$ massless flavors, the instanton vertex

$$
\det_{f,g}\left(\overline\psi_{R f}\psi_{L g}\right)
$$

breaks the classical $U(1)_A$ symmetry while preserving the non-Abelian chiral flavor symmetries. It is one ingredient in the physics of the axial singlet channel. Strong-coupling chiral dynamics, confinement, and the full hadron spectrum require more than the one-instanton approximation.

### Electroweak baryon and lepton number violation

In the Standard Model, anomalous electroweak processes violate $B+L$ while preserving $B-L$. At zero temperature the instanton contribution is enormously suppressed by the weak-coupling instanton action. At high temperature, transitions over the barrier are described by sphalerons rather than ordinary zero-temperature tunneling. This is the same topological/anomalous logic in a different dynamical regime.

## Common pitfalls

**Saying that instantons are the anomaly.** The anomaly is local and can be derived perturbatively. Instantons are global topological configurations that reveal the integrated anomaly through zero modes and selection rules.

**Forgetting the mass matrix.** In QCD-like theories, the physical CP-violating parameter is not just $\theta$; it is the combination involving the phase of the fermion mass matrix. A massless fermion changes the story qualitatively.

**Treating the ’t Hooft vertex as an ordinary perturbative vertex.** It is an effective insertion generated by a nontrivial saddle and zero-mode integration. Its coefficient contains the instanton action, determinants, zero-mode normalizations, and size integration.

**Assuming anomaly matching requires instantons.** Anomalies are exact constraints on RG flows. Semiclassical instantons are one way to see some of their consequences, not the definition of anomaly matching.

**Ignoring global forms and discrete quotients.** The precise periodicity of $\theta$, the allowed instanton sectors, and the genuine line operators can depend on the global form of the gauge group and on background fields. The simple $SU(N)$ story is the clean first case, not the final word.

**Overusing instantons in strongly coupled QCD.** Zero-mode selection rules are robust. A dilute gas of small instantons is not automatically a controlled model of the QCD vacuum.

## Relations to other pages

- [Fermion Zero Modes](/nonperturbative-qft/instantons-tunneling-theta-vacua/fermion-zero-modes/) gives the zero-mode and Grassmann-saturation derivation of the ’t Hooft vertex.
- [Theta Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/theta-vacua/) explains the sector-sum meaning of $e^{i\theta Q}$.
- [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/) fixes the normalization of $Q$.
- [Tunneling Between Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/tunneling-between-vacua/) explains how topological transitions appear as Euclidean amplitudes.
- [Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/) studies the curvature of the vacuum energy in $\theta$.
- [Condensates](/nonperturbative-qft/order-parameters-diagnostics/condensates/) is the natural diagnostic page for chiral symmetry breaking and fermion bilinears.
- Later pages on strongly coupled gauge theory will use these anomaly constraints without assuming a dilute instanton gas.

## Research status

**Established.** The axial anomaly, the anomalous theta-angle shift, the index-theorem connection to zero modes, and the anomaly selection rule $\Delta Q_A=2N_fQ$ in QCD-like theories are standard results.

**Convention-dependent.** Signs in the anomaly equation, theta shift, and left/right labeling depend on Euclidean continuation, $\epsilon$-tensor conventions, and the chosen axial rotation. Physical invariant combinations and selection rules are convention independent.

**Active.** How instanton effects compete with confinement, chiral symmetry breaking, finite-temperature sphalerons, dense matter, and large-N limits remains a live research interface. Anomalies remain exact even where instanton semiclassics is uncontrolled.

**Speculative.** None of the anomaly/zero-mode matching described here is speculative. Speculation enters only in proposed dynamical models of strongly coupled vacua based on instanton ensembles or related semiclassical objects outside their controlled regime.

## Exercises

### Exercise 1: Integrated anomaly

Using

$$
Q=\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu},
$$

and

$$
\partial_\mu J_A^\mu=\frac{N_f}{8\pi^2}\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}
$$

in the massless theory, derive $\Delta Q_A=2N_fQ$.

<details>
<summary><strong>Solution</strong></summary>

Integrating the anomaly equation gives

$$
\Delta Q_A
=\int d^4x\,\partial_\mu J_A^\mu
=\frac{N_f}{8\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}.
$$

Using the definition of $Q$,

$$
\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}=16\pi^2Q.
$$

Therefore

$$
\Delta Q_A=\frac{N_f}{8\pi^2}(16\pi^2Q)=2N_fQ.
$$

</details>

### Exercise 2: Theta shift from an axial rotation

Suppose the measure in a charge-$Q$ sector transforms as

$$
\mathcal D\overline\psi\mathcal D\psi
\mapsto e^{-2iN_f\alpha Q}\mathcal D\overline\psi\mathcal D\psi
$$

under $\psi\mapsto e^{-i\alpha\gamma_5}\psi$. Show that this is equivalent to shifting $\theta\mapsto\theta-2N_f\alpha$ in the sector weight $e^{i\theta Q}$.

<details>
<summary><strong>Solution</strong></summary>

The original topological weight is

$$
e^{i\theta Q}.
$$

The anomalous measure contributes

$$
e^{-2iN_f\alpha Q}.
$$

Depending on whether one moves the Jacobian to the action or regards the field redefinition as a change in the parameter labeling, this is represented by a shift of the theta parameter. With the convention used in the page, the same physics is written as

$$
e^{i(\theta-2N_f\alpha)Q}.
$$

If a source chooses the opposite sign for the axial rotation or for $Q$, the displayed sign changes; the invariant point is that axial rotations shift $\theta$ by an amount proportional to $2N_f\alpha$.

</details>

### Exercise 3: Invariance of the instanton vertex

Let

$$
\mathcal O_I=e^{i\theta}\det_{f,g}(\overline\psi_{R f}\psi_{L g}).
$$

Under an axial rotation, assume the determinant picks up the phase $e^{+2iN_f\alpha}$ and $\theta\to\theta-2N_f\alpha$. Show that $\mathcal O_I$ is invariant.

<details>
<summary><strong>Solution</strong></summary>

The determinant transforms as

$$
\det(\overline\psi_R\psi_L)
\mapsto
 e^{+2iN_f\alpha}\det(\overline\psi_R\psi_L).
$$

The theta factor transforms as

$$
e^{i\theta}\mapsto e^{i(\theta-2N_f\alpha)}=e^{i\theta}e^{-2iN_f\alpha}.
$$

Multiplying the two factors,

$$
e^{i\theta}e^{-2iN_f\alpha}\cdot e^{+2iN_f\alpha}\det(\overline\psi_R\psi_L)
=
e^{i\theta}\det(\overline\psi_R\psi_L).
$$

Thus the instanton contribution is invariant under the combined anomalous transformation.

</details>

### Exercise 4: The physical theta angle with masses

In a QCD-like theory with complex mass matrix $M$, explain why a chiral rotation can move phase between $\theta$ and $\arg\det M$, so that the physical combination is schematically

$$
\overline\theta=\theta+\arg\det M.
$$

What changes if $\det M=0$?

<details>
<summary><strong>Solution</strong></summary>

An axial rotation is a change of fermion variables. Because the measure is anomalous, it shifts $\theta$. The same rotation also changes the phase of the mass matrix in the chiral mass term. Therefore the separate quantities $\theta$ and $\arg\det M$ depend on the chosen chiral basis; the invariant combination is their sum, up to sign conventions.

If $\det M=0$, at least one fermion is massless. Its axial phase can be used to remove $\theta$ without inducing a compensating phase in a nonzero mass. In that case the usual massive-theory parameter $\overline\theta$ is not a physical CP-violating parameter in the same way.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, especially the chapters on anomalies, instantons and theta vacua, and quarks and theta vacua.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, especially the path-integral measure derivation of the chiral anomaly.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapters on instantons and anomalies.
- M. Mariño, *Instantons and Large N*, especially the chapter on instantons and fermions.
- S. Coleman, *Aspects of Symmetry*, for classic lectures on instantons, anomalies, and symmetry realization.
- G. ’t Hooft, “Symmetry Breaking Through Bell–Jackiw Anomalies,” for the original instanton/anomaly selection-rule analysis.

## Version history

- **2026-06-27:** Initial polished draft. Added after Fermion Zero Modes as the anomaly-facing completion of the first instanton-and-fermion pair.
