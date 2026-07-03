---
title: "Pseudo-Goldstone Bosons"
description: "Explains how small explicit symmetry breaking lifts Goldstone directions, gives pseudo-Goldstone bosons small masses, and organizes the resulting EFT power counting."
sidebar:
  label: "Pseudo-Goldstone Bosons"
  order: 8
level: Graduate
status: "Polished draft"
source: "Coleman on soft pions and secret symmetry; Srednicki §§30–32; Schwartz Ch. 28; Weinberg Vol. II on chiral dynamics; Burgess on EFT symmetries; Altland–Simons on collective modes."
topics:
  - pseudo-Goldstone bosons
  - explicit symmetry breaking
  - spurions
  - PCAC
  - chiral symmetry breaking
  - Goldstone theorem
  - effective field theory
canonicalTopics:
  - pseudo-goldstone-boson
  - explicit-symmetry-breaking
  - spurion
  - partially-conserved-current
  - chiral-lagrangian
  - gell-mann-oakes-renner-relation
  - dashen-formula
researchStatus:
  established:
    - "Pseudo-Goldstone bosons arise when a symmetry is spontaneously broken but also explicitly broken by a small parameter; their masses vanish with that parameter."
    - "Their masses can be read either from the curvature of the explicit-breaking potential on the coset or from the divergence of the approximately conserved current."
  active:
    - "Modern applications include composite Higgs theories, axion-like particles, finite-density systems, nonrelativistic Goldstone counting, and pseudo-Goldstone modes in systems with approximate generalized or non-invertible structures."
---

## Summary

A **pseudo-Goldstone boson** is what remains of a Goldstone boson when the symmetry is not quite exact.

Start with an exact continuous internal symmetry $G$ that is spontaneously broken to $H$. The vacuum manifold is $G/H$, and the low-energy theory contains massless Goldstone fields. Now add a small explicit breaking term,

$$
S=S_0+\bar\epsilon\int d^d x\,\mathcal O_{\rm br}(x),
\qquad |\bar\epsilon|\ll 1
$$

in a sense made precise by the EFT power counting. The formerly flat directions are no longer perfectly flat. The Goldstone fields acquire a potential and therefore small masses,

$$
M_{\rm pGB}^2\propto \bar\epsilon.
$$

The word **pseudo** is not a pejorative. It means that the particle is protected by an approximate symmetry: as the explicit-breaking parameter is sent to zero, the mass must vanish.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A schematic map from exact spontaneous symmetry breaking to pseudo-Goldstone bosons. Exact symmetry gives a flat coset and massless modes; small explicit breaking adds a shallow potential whose curvature gives a small mass squared.](/figures/symmetry-anomalies-topology/pseudo-goldstone-mass-generation.svg)

<figcaption>

A pseudo-Goldstone mass is the curvature of a shallow potential on the old Goldstone manifold. Current algebra and PCAC give the same information through the divergence of the approximately conserved current.

</figcaption>
</figure>

The canonical examples are the pions. In massless two-flavor QCD, chiral symmetry would make the pions exact Goldstone bosons. In real QCD the light quark masses explicitly break chiral symmetry, so the pions are light but not massless.

## Prerequisites

Read [Goldstone Theorem](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-theorem/), [Goldstone Modes](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-modes/), [Coset Construction Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/coset-construction-preview/), [Nonlinear Sigma Models Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/nonlinear-sigma-models-preview/), and [Explicit Versus Spontaneous Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/explicit-versus-spontaneous-breaking/) first.

For the Ward-identity viewpoint, it helps to know [Noether Currents](/symmetry-anomalies-topology/noether-currents-ward-identities/noether-currents/), [Current Conservation in Correlation Functions](/symmetry-anomalies-topology/noether-currents-ward-identities/current-conservation-in-correlation-functions/), and [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/).

## Core idea

Exact spontaneous breaking gives a continuous family of physically equivalent vacua. Moving along that family costs no energy. The corresponding fields are massless.

Small explicit breaking changes the story in the mildest possible way. The continuous family of vacua becomes a shallow landscape. Motion along the old Goldstone directions now costs a small energy, so the Goldstone fields become light massive particles.

A pseudo-Goldstone boson is therefore controlled by two separate scales:

$$
F \quad \text{sets the stiffness of motion along } G/H,
$$

while

$$
\bar\epsilon \quad \text{sets the size of the explicit-breaking potential.}
$$

Schematic EFT reasoning gives

$$
\mathcal L_{\rm eff}
=
\frac12 F^2 g_{ab}(\xi)\partial_\mu\xi^a\partial^\mu\xi^b
-
V_{\rm br}(\xi),
$$

where $\xi^a$ are dimensionless coordinates on $G/H$. Expanding around the selected vacuum $\xi=0$ gives

$$
V_{\rm br}(\xi)
=
V_{\rm br}(0)
+
\frac12\,\xi^a\xi^b\,\partial_a\partial_bV_{\rm br}(0)+\cdots.
$$

The physical mass matrix is the curvature divided by the stiffness:

$$
(M^2)^a_{\ b}
=
\frac{1}{F^2}\,g^{ac}(0)\,\partial_c\partial_bV_{\rm br}(0)
+
\cdots.
$$

This formula is deliberately geometric. The mass is not a random relevant deformation of the Goldstone EFT; it is the Hessian of the explicitly symmetry-breaking potential on the old vacuum manifold.

## Setup and conventions

We use the volume conventions: mostly-minus metric, plane waves $e^{-ip\cdot x}$, and Hermitian charges. For an infinitesimal internal symmetry generated by $Q_A$, the action on an operator is

$$
\delta_A\mathcal O=i[Q_A,\mathcal O].
$$

A current associated with an exact symmetry obeys

$$
\partial_\mu j_A^\mu=0.
$$

With explicit breaking, we write

$$
\partial_\mu j_A^\mu=B_A,
$$

where $B_A$ is the breaking operator. This equation may hold as an operator identity, as a renormalized Ward identity inside correlators, or only after including contact terms and source conventions. Which version is meant depends on the context.

:::note[Convention-sensitive source note]
The sign in formulas involving $B_A$, $Q_A$, and the Hamiltonian breaking term depends on whether one defines $\delta_A\mathcal O=i[Q_A,\mathcal O]$ or $\delta_A\mathcal O=-i[Q_A,\mathcal O]$, and on whether the breaking term is written in the Lagrangian or Hamiltonian. This page uses the convention above and states mass formulas either as Hessians of the physical potential or with an explicit sign warning.
:::

For a one-particle pseudo-Goldstone state $|\pi_B(p)\rangle$, define the decay-constant matrix by

$$
\langle 0|j_A^\mu(0)|\pi_B(p)\rangle
=
iF_{AB}p^\mu.
$$

Using translation invariance and $p^2=M_B^2$, our plane-wave convention gives

$$
\langle 0|\partial_\mu j_A^\mu(0)|\pi_B(p)\rangle
=
F_{AB}M_B^2.
$$

Therefore the current-divergence Ward identity gives

$$
\langle 0|B_A(0)|\pi_B(p)\rangle
=
F_{AB}M_B^2.
$$

This is the cleanest general slogan:

$$
\text{small current nonconservation}
\quad\Longleftrightarrow\quad
\text{small pseudo-Goldstone mass}.
$$

## From flat directions to masses

Let $G$ be an exact symmetry of $S_0$ and suppose a vacuum $|\Omega\rangle$ preserves $H\subset G$. Broken generators are denoted $X_a$. At low energies, the Goldstone fields parametrize

$$
U(\xi)=\exp(i\xi^a X_a).
$$

The leading exact-symmetry EFT contains only derivative interactions,

$$
\mathcal L_0
=
\frac12F^2g_{ab}(\xi)\partial_\mu\xi^a\partial^\mu\xi^b+
\text{higher derivatives}.
$$

No nonconstant potential is allowed by the exact $G$ symmetry, because every point on $G/H$ is related to every other point by a symmetry. This is the Goldstone miracle in one sentence: exact symmetry forbids a mass term.

Now add a small breaking perturbation

$$
\Delta\mathcal L=\bar\epsilon\,\mathcal O_{\rm br}.
$$

If $\mathcal O_{\rm br}$ is not invariant under $G$, the low-energy EFT may contain a nonconstant function on $G/H$:

$$
\Delta\mathcal L_{\rm eff}=-V_{\rm br}(\xi).
$$

The sign is chosen so that the Hamiltonian density contains $+V_{\rm br}$ for static configurations.

Expanding around a minimum,

$$
V_{\rm br}(\xi)
=V_0+\frac12F^2(M^2)_{ab}\xi^a\xi^b+\frac{1}{3!}c_{abc}\xi^a\xi^b\xi^c+
\cdots,
$$

gives massive pseudo-Goldstone modes. If the explicit breaking vanishes, then $V_{\rm br}$ becomes constant and

$$
(M^2)_{ab}\to0.
$$

That vanishing limit is the physical content. The exact coefficient is model-dependent, but the proportionality to the explicit-breaking spurion is not.

## Spurions and why the mass is protected

The spurion method is the tidiest way to organize approximate symmetry.

Suppose a term

$$
\bar\epsilon_i\mathcal O^i
$$

breaks $G$ because $\mathcal O^i$ transforms nontrivially. Instead of declaring the term non-invariant, temporarily assign a transformation law to $\bar\epsilon_i$ so that

$$
\bar\epsilon_i\mathcal O^i
$$

is formally invariant. Then write every possible low-energy operator that is invariant under this combined transformation. At the end, set $\bar\epsilon_i$ equal to its physical fixed value.

This trick is not cosmetic. It tells you which terms are allowed and how many powers of explicit breaking they contain. For example, a pseudo-Goldstone mass term must contain at least one spurion insertion if the exact symmetry would forbid it:

$$
M_{\rm pGB}^2=\mathcal O(\bar\epsilon).
$$

Loops cannot generate an unsuppressed mass because an unsuppressed mass term would violate the spurion symmetry. This is the technical-naturalness statement:

$$
\bar\epsilon=0
\quad\Rightarrow\quad
\text{enhanced symmetry}.
$$

Small pseudo-Goldstone masses are stable under radiative corrections for the same reason small fermion masses can be stable when chiral symmetry is restored at zero mass.

## The PCAC viewpoint

The traditional current-algebra language uses **partial conservation of the axial current**, abbreviated PCAC.

For an exact broken symmetry, the current creates a Goldstone pole:

$$
\langle0|j_A^\mu(0)|\pi_B(p)\rangle=iF_{AB}p^\mu,
$$

and current conservation is compatible with masslessness because

$$
p_\mu p^\mu=0.
$$

With small explicit breaking,

$$
\partial_\mu j_A^\mu=B_A.
$$

Taking the one-particle matrix element gives

$$
F_{AB}M_B^2
=
\langle0|B_A(0)|\pi_B(p)\rangle.
$$

Thus $M_B^2$ is small if $B_A$ is small in the low-energy expansion.

This equation also explains why pseudo-Goldstone masses are usually proportional to the explicit-breaking parameter itself, not its square. The current divergence is linear in the breaking operator; the pole residue converts that linear breaking into $M^2$.

## Dashen formula

There is also a useful Hamiltonian form. Let the explicit-breaking Hamiltonian be

$$
H=H_0+H_{\rm br},
$$

with $H_0$ invariant under $G$. Moving the vacuum along the broken direction $X_a$ produces a family of trial states

$$
|\xi\rangle=e^{i\xi^aQ_a/F}|\Omega\rangle.
$$

The explicit-breaking energy density is

$$
V_{\rm br}(\xi)
=\frac{1}{\mathcal V}\langle\xi|H_{\rm br}|\xi\rangle,
$$

where $\mathcal V$ is the spatial volume. The pseudo-Goldstone mass matrix is the Hessian of this energy on the vacuum manifold:

$$
F^2(M^2)_{ab}
=
\partial_a\partial_bV_{\rm br}(0).
$$

Using the charge commutator convention above, this can be written schematically as

$$
F^2(M^2)_{ab}
=
-\frac{1}{\mathcal V}
\langle\Omega|[Q_a,[Q_b,H_{\rm br}]]|\Omega\rangle,
$$

up to the convention-dependent placement of signs and generator labels.

:::note[Source note]
This double-commutator formula is often called Dashen's formula in current-algebra discussions. The safest way to use it is to compute the explicit-breaking energy $V_{\rm br}(\xi)$ and then take its Hessian. The Hessian form is convention-independent; the double-commutator sign depends on generator conventions.
:::

The formula makes the physics wonderfully blunt: the mass is the second derivative of the explicit-breaking energy with respect to motion along a broken generator.

## Example: tilted O(2) model

Consider a complex scalar written as

$$
\Phi=\frac{1}{\sqrt2}(v+\rho)e^{i\theta},
$$

with an exact $O(2)$ or $U(1)$ symmetry broken by $v\ne0$. The Goldstone field is the phase. The leading kinetic term is

$$
\mathcal L_{\rm kin}
=\frac12(v+\rho)^2\partial_\mu\theta\partial^\mu\theta.
$$

At low energies we may set the heavy radial mode $\rho$ to zero, giving

$$
\mathcal L_{\rm kin}
=\frac12v^2\partial_\mu\theta\partial^\mu\theta.
$$

Now add a small explicit breaking term that favors $\theta=0$:

$$
\Delta V=-\eta v\cos\theta,
\qquad \eta>0.
$$

Expanding near $\theta=0$,

$$
\Delta V=-\eta v+\frac12\eta v\theta^2+\mathcal O(\theta^4).
$$

The canonically normalized field is

$$
\pi=v\theta.
$$

Therefore

$$
\Delta V
=
-\eta v+\frac12\frac{\eta}{v}\pi^2+\cdots,
$$

and

$$
M_\pi^2=\frac{\eta}{v}.
$$

The result vanishes as $\eta\to0$. The small mass is not tuned; it is protected by the restoration of $U(1)$ symmetry when the tilt is removed.

## Example: pions and the chiral Lagrangian

For $N_f$ massless quarks, QCD has an approximate chiral symmetry

$$
SU(N_f)_L\times SU(N_f)_R,
$$

ignoring the anomalous axial $U(1)$ for the moment. The chiral condensate spontaneously breaks this symmetry to the diagonal subgroup,

$$
SU(N_f)_L\times SU(N_f)_R\to SU(N_f)_V.
$$

The Goldstone fields are collected in

$$
U(x)=\exp\left(\frac{i\pi^a(x)T^a}{F}\right),
\qquad
U\in SU(N_f),
$$

with transformation law

$$
U\to LUR^\dagger.
$$

The leading chiral Lagrangian is

$$
\mathcal L_2
=
\frac{F^2}{4}\operatorname{tr}(\partial_\mu U\partial^\mu U^\dagger)
+
\frac{F^2B}{2}\operatorname{tr}(MU^\dagger+UM^\dagger),
$$

where $M$ is the quark-mass matrix treated as a spurion transforming as

$$
M\to LMR^\dagger.
$$

After setting $M$ to its physical value, chiral symmetry is explicitly broken. For two approximately degenerate light quarks,

$$
M=m_q\mathbf 1,
$$

the leading pion mass is

$$
M_\pi^2=2Bm_q.
$$

Equivalently, in the isospin-symmetric notation with

$$
\Sigma=-\langle0|\bar u u|0\rangle_{m_q\to0}
=-\langle0|\bar d d|0\rangle_{m_q\to0},
$$

the Gell-Mann–Oakes–Renner relation is

$$
F_\pi^2M_\pi^2=(m_u+m_d)\Sigma+
\mathcal O(m_q^2).
$$

The formula is famous because it ties together the three ingredients of a pseudo-Goldstone boson:

$$
\text{spontaneous breaking }(\Sigma)
\quad+
\text{explicit breaking }(m_u,m_d)
\quad\Rightarrow\quad
\text{small mass }M_\pi.
$$

:::note[Normalization note]
Different texts place factors of $2$, $F$, and generator normalization differently. This page uses the common convention in which $\operatorname{tr}(T^aT^b)=2\delta^{ab}$ for the exponential written above. If instead one uses $\operatorname{tr}(t^at^b)=\delta^{ab}/2$ and $U=\exp(2i\pi^at^a/F)$, the physical mass formula is unchanged.
:::

## Pseudo-Goldstone power counting

A pure Goldstone EFT is an expansion in derivatives:

$$
\partial_\mu\sim p.
$$

A pseudo-Goldstone EFT also expands in explicit breaking. In chiral perturbation theory, for example, one counts

$$
m_q\sim p^2,
\qquad
M_\pi^2\sim p^2.
$$

This is not dimensional analysis alone. It is physical bookkeeping: a pion mass insertion competes with two derivatives because the propagator is

$$
\frac{i}{p^2-M_\pi^2+i\epsilon}.
$$

Thus the leading pseudo-Goldstone EFT keeps both

$$
\partial U\partial U^\dagger
\quad\text{and}\quad
MU^\dagger+UM^\dagger.
$$

Higher-order terms include more derivatives, more spurions, or both:

$$
\mathcal O(p^4),
\qquad
\mathcal O(m_qp^2),
\qquad
\mathcal O(m_q^2).
$$

This logic is reusable far beyond pions. Whenever a light scalar is protected by approximate symmetry, its EFT should be organized by both derivatives and explicit-breaking spurions.

## Other important examples

### Axions and axion-like particles

An axion is often described as a pseudo-Goldstone boson of an approximate shift symmetry,

$$
a\to a+\text{constant}.
$$

The shift symmetry forbids an ordinary mass term. Nonperturbative effects or small explicit breaking generate a periodic potential,

$$
V(a)=\Lambda^4\left(1-\cos\frac{a}{f_a}\right),
$$

so

$$
m_a^2=\frac{\Lambda^4}{f_a^2}.
$$

The important point is not the cosine itself; it is the symmetry. The potential must vanish, or become constant, when the explicit breaking of the shift symmetry vanishes.

### Composite Higgs models

In composite Higgs models, the Higgs doublet is treated as a pseudo-Goldstone multiplet of a larger spontaneously broken global symmetry. Gauge and Yukawa couplings explicitly break that global symmetry and generate a potential for the Higgs. The hope is to explain why the Higgs is lighter than the strong scale of the composite sector.

The full model-building story belongs elsewhere, but the symmetry logic is exactly the one on this page:

$$
\text{approximate global symmetry}
\quad\Rightarrow\quad
\text{light scalar protected from large masses}.
$$

### Magnons with anisotropy

In a magnet with exact spin-rotation symmetry, spontaneous magnetization gives gapless spin waves. Weak anisotropy explicitly reduces the spin symmetry. The would-be Goldstone mode can become a gapped pseudo-Goldstone mode. The gap is controlled by the anisotropy, not by the microscopic exchange scale.

### Pinned phonons and charge-density waves

Translations can be spontaneously broken by a crystal or density wave. If impurities or a lattice potential explicitly break continuous translation symmetry, the sliding mode can become pinned. The corresponding low-energy mode is then a pseudo-Goldstone mode of translation.

This example involves spacetime symmetry and disorder, so it has extra caveats. Still, the basic pattern remains: exact sliding symmetry gives a gapless mode; weak explicit pinning gives a small gap.

## Relation to anomalies

An anomaly can act like a quantum explicit breaking of a classical symmetry. The classic QCD warning is the axial $U(1)_A$ symmetry. Classically, massless QCD seems to have an axial $U(1)_A$ symmetry. Quantum mechanically, the fermion measure is anomalous, so this symmetry is not an exact global symmetry of the quantum theory.

Therefore the would-be Goldstone boson associated with $U(1)_A$ is not an ordinary light pseudo-Goldstone boson controlled only by small quark masses. The $\eta'$ is much heavier than the pions because the anomaly removes the corresponding exact symmetry in the chiral limit.

The lesson is simple but easy to forget:

$$
\text{only actual quantum symmetries protect masses}.
$$

A classical symmetry that is broken by the regulator or measure cannot be used as an exact protection mechanism.

## Common pitfalls

**Pitfall 1: Calling every light scalar a pseudo-Goldstone boson.**

A pseudo-Goldstone boson must become massless when a specific explicit-breaking parameter is set to zero. A merely light scalar is not automatically a pseudo-Goldstone boson.

**Pitfall 2: Saying the mass is proportional to the breaking rather than the mass squared.**

For relativistic pseudo-Goldstone bosons, it is usually $M^2$ that is linear in the explicit-breaking parameter:

$$
M^2\sim\bar\epsilon.
$$

The mass itself then scales as $M\sim\sqrt{\bar\epsilon}$ unless the microscopic parameter already has dimension two or the dispersion relation is nonrelativistic.

**Pitfall 3: Forgetting the stiffness.**

The same explicit-breaking potential gives different masses depending on the kinetic normalization. The schematic formula is

$$
M^2\sim \frac{\text{potential curvature}}{\text{stiffness}}.
$$

**Pitfall 4: Treating spurions as new particles.**

A spurion is usually not a dynamical field. It is a bookkeeping device for symmetry breaking. After classifying allowed terms, one sets the spurion to its fixed value.

**Pitfall 5: Confusing pseudo-Goldstone bosons with Higgsed Goldstone modes.**

A pseudo-Goldstone boson is a physical light mode made massive by explicit breaking. In the Higgs mechanism, a would-be Goldstone mode is removed from the physical spectrum by gauge redundancy and becomes the longitudinal polarization of a gauge field.

**Pitfall 6: Ignoring finite volume.**

Strict spontaneous breaking is an infinite-volume statement. In finite volume, exact zero modes must be treated carefully. A small explicit breaking source can select a vacuum, but if it is left nonzero it also gives a pseudo-Goldstone mass.

## Relations to other pages

[Explicit Versus Spontaneous Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/explicit-versus-spontaneous-breaking/) explains the action/state distinction behind this page. [Goldstone Modes](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-modes/) explains the massless limit, and [Coset Construction Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/coset-construction-preview/) explains why the fields live on $G/H$.

[Nonlinear Sigma Models Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/nonlinear-sigma-models-preview/) gives the derivative expansion that becomes the pseudo-Goldstone EFT once spurions are added. [Coleman–Mermin–Wagner Theorem Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/coleman-mermin-wagner-theorem-preview/) explains why the existence of exact Goldstone modes becomes subtle in low dimensions.

Later pages on [Anomalies](/symmetry-anomalies-topology/anomalies/) and [’t Hooft Anomalies](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/thooft-anomalies/) will separate small explicit breaking from genuine quantum obstructions to a symmetry.

## Research status

The basic mechanism of pseudo-Goldstone masses is established textbook physics. The EFT logic is especially mature in chiral perturbation theory, where quark masses are spurions and pion interactions are organized by simultaneous expansions in momenta and quark masses.

Active research uses the same idea in less settled environments: composite Higgs theories, axion-like sectors, dense matter, cold atoms, nonequilibrium systems, quasicrystals, generalized symmetries, and systems where spacetime symmetry breaking complicates the Goldstone counting. In those settings the word "pseudo-Goldstone" remains useful, but the dispersion relation, damping, mixing, and protection mechanism must be checked case by case.

## Exercises

### Exercise 1: Tilted Mexican hat

Consider

$$
\mathcal L
=\partial_\mu\Phi^*\partial^\mu\Phi
-\lambda\left(|\Phi|^2-\frac{v^2}{2}\right)^2
+\frac{h}{\sqrt2}(\Phi+\Phi^*),
$$

with small $h>0$. Write

$$
\Phi=\frac{1}{\sqrt2}(v+\rho)e^{i\theta}
$$

and ignore the radial fluctuation $\rho$. Find the pseudo-Goldstone mass to leading order in $h$.

<details><summary><strong>Solution</strong></summary>

The explicit term is

$$
\Delta\mathcal L
=\frac{h}{\sqrt2}\left(\frac{v}{\sqrt2}e^{i\theta}+\frac{v}{\sqrt2}e^{-i\theta}\right)
=hv\cos\theta.
$$

Thus the static potential contribution is

$$
\Delta V=-hv\cos\theta.
$$

Expanding near $\theta=0$,

$$
\Delta V=-hv+\frac12hv\theta^2+\cdots.
$$

The kinetic term is

$$
\frac12v^2\partial_\mu\theta\partial^\mu\theta.
$$

With $\pi=v\theta$,

$$
\Delta V=-hv+\frac12\frac{h}{v}\pi^2+\cdots.
$$

Therefore

$$
M_\pi^2=\frac{h}{v}.
$$

</details>

### Exercise 2: PCAC mass relation

Assume

$$
\langle0|j_A^\mu(0)|\pi_B(p)\rangle=iF_{AB}p^\mu
$$

and $\partial_\mu j_A^\mu=B_A$. Using the plane-wave convention $e^{-ip\cdot x}$, show that

$$
\langle0|B_A(0)|\pi_B(p)\rangle=F_{AB}M_B^2.
$$

<details><summary><strong>Solution</strong></summary>

Translation invariance gives

$$
\langle0|j_A^\mu(x)|\pi_B(p)\rangle
=e^{-ip\cdot x}\langle0|j_A^\mu(0)|\pi_B(p)\rangle.
$$

Therefore

$$
\langle0|\partial_\mu j_A^\mu(x)|\pi_B(p)\rangle
=(-ip_\mu)e^{-ip\cdot x}(iF_{AB}p^\mu)
=F_{AB}p^2e^{-ip\cdot x}.
$$

On shell, $p^2=M_B^2$. Setting $x=0$ and using $\partial_\mu j_A^\mu=B_A$ gives

$$
\langle0|B_A(0)|\pi_B(p)\rangle=F_{AB}M_B^2.
$$

</details>

### Exercise 3: Spurion for a mass matrix

Let

$$
U\to LUR^\dagger
$$

under $SU(N_f)_L\times SU(N_f)_R$. Find the transformation law of $M$ that makes

$$
\operatorname{tr}(MU^\dagger+UM^\dagger)
$$

formally invariant.

<details><summary><strong>Solution</strong></summary>

Since

$$
U^\dagger\to RU^\dagger L^\dagger,
$$

we want

$$
\operatorname{tr}(M'U'^\dagger)
=\operatorname{tr}(MU^\dagger).
$$

This is achieved by

$$
M\to LMR^\dagger.
$$

Then

$$
M'U'^\dagger
=LMR^\dagger RU^\dagger L^\dagger
=LMU^\dagger L^\dagger,
$$

and the trace is invariant. The Hermitian conjugate term works similarly.

</details>

### Exercise 4: Why mass squared is linear

Suppose a pseudo-Goldstone coordinate $\xi$ has

$$
\mathcal L
=\frac12F^2(\partial\xi)^2
-\epsilon\Lambda^4(1-\cos\xi).
$$

Find the canonically normalized mass and explain why $M^2$, not $M$, is linear in $\epsilon$.

<details><summary><strong>Solution</strong></summary>

Expanding the potential,

$$
\epsilon\Lambda^4(1-\cos\xi)
=\frac12\epsilon\Lambda^4\xi^2+\cdots.
$$

The canonical field is

$$
\pi=F\xi.
$$

Thus

$$
V=\frac12\frac{\epsilon\Lambda^4}{F^2}\pi^2+\cdots,
$$

so

$$
M^2=\frac{\epsilon\Lambda^4}{F^2}.
$$

The Lagrangian mass term is quadratic in the field, so the potential curvature directly gives $M^2$. Therefore $M^2$ is linear in the small explicit-breaking coefficient.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially “Soft pions” and “Secret symmetry.”
- M. Gell-Mann, R. J. Oakes, and B. Renner, “Behavior of Current Divergences under $SU(3)\times SU(3)$.”
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters on phenomenological Lagrangians and chiral dynamics.
- M. Srednicki, *Quantum Field Theory*, sections on spontaneous symmetry breaking and continuous symmetries.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter on spontaneous symmetry breaking and anomalies.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapters on symmetries and nonlinear realizations.
- J. Gasser and H. Leutwyler, classic papers on chiral perturbation theory.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, chapters on broken symmetry, collective modes, and topological terms.

## Version history

- 2026-06-17: Initial polished draft. Added the geometric mass-curvature picture, PCAC derivation, Dashen formula, tilted $O(2)$ example, chiral Lagrangian and GMOR relation, spurion power counting, examples, caveats, and exercises.
