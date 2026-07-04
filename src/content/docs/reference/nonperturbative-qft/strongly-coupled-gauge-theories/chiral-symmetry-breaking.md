---
title: "Chiral Symmetry Breaking"
description: "Explains how QCD realizes chiral flavor symmetry nonperturbatively through a quark condensate, Goldstone pions, and the chiral effective theory."
sidebar:
  label: "Chiral Symmetry Breaking"
  order: 2
level: Advanced
status: "Polished draft"
source: "Srednicki; Coleman; Weinberg, Vol. II; Shifman; Mariño; Burgess."
topics:
  - chiral symmetry breaking
  - QCD
  - quark condensate
  - pions
  - Goldstone bosons
  - chiral Lagrangian
  - GMOR relation
  - axial anomaly
  - Banks-Casher relation
canonicalTopics:
  - nonperturbative-qft
  - strongly-coupled-gauge-theories
  - chiral-symmetry-breaking
  - qcd
  - spontaneous-symmetry-breaking
  - condensates
researchStatus:
  established:
    - "The chiral symmetry breaking pattern of low-flavor QCD and its Goldstone-pion consequences are standard nonperturbative physics, supported by current algebra, phenomenology, effective theory, and lattice calculations."
  active:
    - "Deriving chiral symmetry breaking analytically from continuum QCD in four dimensions at theorem level, and mapping related patterns in broader gauge theories, remains an active subject."
---

## Summary

Chiral symmetry breaking is the nonperturbative statement that the vacuum of QCD with light quarks does not respect the full chiral flavor symmetry of the massless Lagrangian. For $N_f$ massless Dirac quarks in a complex color representation, the classical nonanomalous flavor symmetry contains

$$
SU(N_f)_L\times SU(N_f)_R\times U(1)_B,
$$

and ordinary QCD realizes it approximately as

$$
SU(N_f)_L\times SU(N_f)_R
\longrightarrow
SU(N_f)_V .
$$

The standard order parameter is the quark condensate,

$$
\Sigma(\mu)\equiv -\frac{1}{N_f}\langle \bar q q\rangle_\mu,
$$

where the scale and scheme remind us that the local composite operator must be renormalized. The physics is not the numerical value of $\Sigma$ by itself. The physics is that the vacuum pairs left- and right-handed quarks and leaves only the diagonal vector flavor symmetry unbroken.

The broken axial generators imply $N_f^2-1$ Goldstone bosons. In real QCD the light quarks have small masses, so the pions, kaons, and eta are pseudo-Goldstone bosons rather than exactly massless particles. This is why the pion is light compared with typical hadrons even though QCD has a strong scale.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Diagram showing left and right chiral flavor rotations connected by a quark condensate, leaving the diagonal vector subgroup unbroken and producing pion fields on the coset.](/figures/nonperturbative-qft/chiral-symmetry-breaking-pattern.svg)

<figcaption>

The chiral condensate couples $q_L$ and $q_R$. Independent left and right flavor rotations are no longer symmetries of the chosen vacuum; the diagonal rotations $L=R$ remain. The broken axial directions are represented at low energy by the pion field $U(x)\in SU(N_f)$.

</figcaption>
</figure>

## Prerequisites

You should know [QCD as a Strongly Coupled QFT](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-as-strongly-coupled-qft/), [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/), [Condensates](/nonperturbative-qft/order-parameters-diagnostics/condensates/), and [Fermion Zero Modes](/nonperturbative-qft/instantons-tunneling-theta-vacua/fermion-zero-modes/). The [Hadron Spectrum](/nonperturbative-qft/strongly-coupled-gauge-theories/hadron-spectrum/) page uses this material to explain why the light pseudoscalar mesons are special.

## Core idea

Massless QCD has more flavor symmetry than the observed low-energy spectrum seems to show. The vector part is visible: hadrons approximately form isospin and flavor multiplets. The axial part is hidden: it is not realized by parity-doubled hadrons of the same mass. Instead, the axial charges fail to annihilate the vacuum, and their action creates nearly massless pseudoscalar modes.

In formulas, the low-energy theory is organized by a field

$$
U(x)\in SU(N_f),
\qquad
U\to LUR^\dagger,
$$

which describes the orientation of the condensate in flavor space. The vacuum chooses one orientation; slowly varying changes of that orientation are the pions.

## Setup and conventions

We use the conventions of the [Nonperturbative QFT conventions page](/nonperturbative-qft/conventions/). Let

$$
q_L=P_Lq,
\qquad
q_R=P_Rq,
\qquad
P_{L,R}=\frac12(1\mp\gamma^5).
$$

For $N_f$ massless quarks, the quark kinetic term is invariant under independent flavor rotations

$$
q_L\to Lq_L,
\qquad
q_R\to Rq_R,
\qquad
L,R\in SU(N_f).
$$

The anomalous $U(1)_A$ symmetry is not part of the exact quantum symmetry of QCD. The baryon-number symmetry $U(1)_B$ remains, and it classifies baryon number rather than producing Goldstone bosons.

We write the quark mass matrix as $M_q$. It explicitly breaks chiral symmetry as a spurion transforming like

$$
M_q\to L M_q R^\dagger,
$$

so that chiral formulas can keep track of how small quark masses perturb the chiral limit.

## The symmetry of massless QCD

In the chiral limit the quark part of the QCD Lagrangian is schematically

$$
\mathcal L_q
=i\bar q_L\gamma^\mu D_\mu q_L
+i\bar q_R\gamma^\mu D_\mu q_R .
$$

The left- and right-handed flavor indices do not talk to each other in this term. That decoupling is the origin of chiral symmetry. The symmetry is not a small technical decoration; it is the organizing principle of light-hadron physics.

The useful decomposition is

$$
SU(N_f)_L\times SU(N_f)_R
\simeq
SU(N_f)_V\times SU(N_f)_A
$$

locally near the identity. Vector rotations take $L=R$ and act the same way on $q_L$ and $q_R$. Axial rotations take $L=R^\dagger$ and act oppositely on the two chiralities.

If the full chiral symmetry were realized linearly on ordinary hadrons, one would expect parity partners to appear in degenerate multiplets: roughly, each hadron would have an opposite-parity cousin with the same mass in the chiral limit. That is not how the light spectrum is organized. Instead, the vector symmetry is visible in approximate multiplets, while the axial symmetry is realized through Goldstone bosons.

## The condensate and the breaking pattern

Define the flavor matrix

$$
\mathcal M^i{}_j(x)=\bar q_{Rj}(x)q_L^i(x).
$$

Under chiral rotations,

$$
\mathcal M\to L\mathcal M R^\dagger.
$$

A vacuum expectation value proportional to the identity,

$$
\langle \mathcal M^i{}_j\rangle
=-\frac{\Sigma}{2}\delta^i{}_j,
$$

is invariant under $L=R$ but not under a general pair $(L,R)$. Therefore it preserves $SU(N_f)_V$ and breaks the axial generators. Equivalently,

$$
\langle \bar q q\rangle
=\langle \bar q_L q_R+\bar q_R q_L\rangle
=-N_f\Sigma
$$

up to the convention used to define $\Sigma$.

:::caution[The condensate is a renormalized composite operator]
The bare expression $\bar q q$ is not a finite observable by itself. Its value depends on renormalization scheme and scale. Statements such as “the condensate is nonzero in the chiral limit” are physical only after a consistent renormalized definition and the correct infinite-volume/chiral limits are specified.
:::

The order of limits matters. Spontaneous symmetry breaking requires the thermodynamic limit. On a finite spatial volume the exact ground state cannot choose a continuous orientation permanently. The chiral condensate as an order parameter should be understood schematically as

$$
\Sigma
=\lim_{m\to0}\lim_{V\to\infty}
\left[-\frac{1}{N_fV}\frac{\partial}{\partial m}\log Z(m,V)\right],
$$

where the infinite-volume limit is taken before the chiral limit.

## Goldstone fields and the chiral Lagrangian

The Goldstone manifold is the coset

$$
\frac{SU(N_f)_L\times SU(N_f)_R}{SU(N_f)_V}
\simeq SU(N_f).
$$

It is convenient to parameterize the Goldstone fields by

$$
U(x)=\exp\left(\frac{2i\Pi(x)}{f}\right),
\qquad
\Pi(x)=\pi^a(x)T^a,
$$

with generators normalized by $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$. The leading chiral effective Lagrangian is

$$
\mathcal L_\chi
=\frac{f^2}{4}\operatorname{tr}(\partial_\mu U\partial^\mu U^\dagger)
+\frac{f^2B}{2}\operatorname{tr}(M_qU^\dagger+UM_q^\dagger)+\cdots .
$$

The constants $f$ and $B$ are low-energy constants. At leading order,

$$
\Sigma=f^2B
$$

in the same renormalization convention used for $M_q$ and $\bar q q$.

For two light flavors with $M_q=\operatorname{diag}(m_u,m_d)$ and approximate isospin symmetry, the leading pion mass relation is

$$
m_\pi^2 f_\pi^2
=(m_u+m_d)\Sigma+O(m_q^2).
$$

Equivalently, with $\Sigma=-\langle\bar u u\rangle$ per light flavor in the isospin limit,

$$
f_\pi^2m_\pi^2=-(m_u+m_d)\langle\bar u u\rangle+O(m_q^2).
$$

This is the Gell-Mann–Oakes–Renner relation in a common convention. It says the pion mass-squared is linear in the explicit chiral symmetry breaking, not of order $\Lambda_{\mathrm{QCD}}^2$.

## Axial anomaly and the missing ninth Goldstone boson

For $N_f$ massless quarks, the classical flavor symmetry is larger than $SU(N_f)_L\times SU(N_f)_R\times U(1)_B$ because it also contains an axial $U(1)_A$. Quantum mechanically this symmetry is anomalous. The singlet axial current obeys schematically

$$
\partial_\mu J_5^\mu
=\frac{g^2N_f}{16\pi^2}\operatorname{tr}(F_{\mu\nu}\widetilde F^{\mu\nu})
+2i\bar q M_q\gamma^5 q,
$$

with normalization depending on the trace convention. Therefore the would-be singlet Goldstone boson is not protected in the same way as the octet pions, kaons, and eta. In three-flavor QCD this is the core reason the $\eta'$ is much heavier than the pseudo-Goldstone octet.

The anomaly also ties chiral rotations to the theta angle. If one quark were exactly massless, an axial rotation could remove the physical theta parameter. With massive quarks, the invariant combination involves both theta and the phase of the quark mass matrix. This is why chiral symmetry, instantons, and theta vacua are not separate stories.

## Spectral diagnostics: Banks–Casher

The condensate has a useful Euclidean Dirac-operator diagnostic. Let $\rho(\lambda)$ be the spectral density of the Dirac operator near eigenvalue $\lambda$ in a large volume. Under standard assumptions, the Banks–Casher relation states

$$
\Sigma=\pi\rho(0),
$$

where the infinite-volume limit is taken before the chiral limit. This relation gives a sharp intuition: chiral symmetry breaking is associated with an accumulation of near-zero Dirac eigenvalues.

This is not merely a numerical trick. It explains why topology, instantons, near-zero modes, and chiral symmetry breaking keep appearing in the same conversations. Exact zero modes are controlled by topology and the index theorem; near-zero modes encode the infrared dynamics responsible for the condensate.

## What chiral symmetry breaking does and does not imply

Chiral symmetry breaking explains why light pseudoscalar mesons are special, why their interactions are derivative at leading order in the chiral limit, and why low-energy amplitudes obey current-algebra and soft-pion constraints. It also gives a natural effective field theory: chiral perturbation theory.

It does **not** by itself prove confinement. The two phenomena coexist in real low-flavor QCD, and they influence each other, but they diagnose different features of the infrared theory. Confinement concerns color, line operators, flux tubes, and the absence of colored asymptotic states. Chiral symmetry breaking concerns the realization of global flavor symmetry in the vacuum.

It also does not mean every strongly coupled gauge theory behaves like QCD. If one changes the number of flavors, the representation, the gauge group, or the dimension, the infrared theory can instead be conformal, chirally symmetric, topologically ordered, or otherwise exotic.

## Common pitfalls

**Forgetting the order of limits.** In finite volume, continuous spontaneous symmetry breaking is rounded. The correct chiral order parameter requires taking $V\to\infty$ before sending the quark mass to zero.

**Treating $\langle\bar q q\rangle$ as a scheme-independent number.** The condensate is a renormalized composite operator. Products such as $m_q\langle\bar q q\rangle$ and physical relations such as the pion mass formula are meaningful when the mass and condensate are defined consistently.

**Confusing $U(1)_A$ with nonanomalous chiral symmetry.** The singlet axial symmetry is broken by the anomaly even when the quark masses vanish. The light pseudo-Goldstone multiplet comes from the non-Abelian axial generators, not from an exact $U(1)_A$ Goldstone boson.

**Identifying chiral symmetry breaking with confinement.** In QCD they are deeply related, but they are not the same diagnostic. A page about chiral symmetry breaking is not a proof of Wilson-loop area law, and a page about confinement is not automatically a proof of a chiral condensate.

**Thinking the pion is light because QCD is weak.** The pion is light because it is a pseudo-Goldstone boson. Most hadron masses are set by the strong scale, not by the light quark masses.

## Relations to other pages

- [QCD as a Strongly Coupled QFT](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-as-strongly-coupled-qft/) gives the UV-to-IR story in which chiral symmetry breaking appears.
- [Hadron Spectrum](/nonperturbative-qft/strongly-coupled-gauge-theories/hadron-spectrum/) explains how the pseudo-Goldstone pions sit inside the broader color-singlet spectrum.
- [Condensates](/nonperturbative-qft/order-parameters-diagnostics/condensates/) explains renormalized local order parameters and why condensates require scheme care.
- [Spontaneous Symmetry Breaking](/nonperturbative-qft/vacuum-structure-phases/spontaneous-symmetry-breaking/) gives the general vacuum-selection logic behind the chiral example.
- [Fermion Zero Modes](/nonperturbative-qft/instantons-tunneling-theta-vacua/fermion-zero-modes/) and [Instantons and Anomalies](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-and-anomalies/) explain the axial anomaly and its relation to topology.

## Research status

For ordinary low-flavor QCD, the chiral symmetry breaking pattern and pseudo-Goldstone description are established physics. The evidence comes from current algebra, pion phenomenology, chiral effective theory, hadron spectroscopy, lattice calculations, and the failure of a parity-doubled linear realization at low energy.

What is not available is a short analytic derivation from the continuum QCD path integral in four dimensions at the same rigor as, say, a perturbative Ward identity. Broader gauge theories are even more varied: chiral symmetry may break, remain unbroken, be constrained by anomalies, or disappear into a conformal fixed point. That broader map belongs to the conformal-window, walking, and chiral-gauge-theory pages later in this chapter.

## Exercises

### Exercise 1: Which subgroup preserves the condensate?

Let $\mathcal M\to L\mathcal M R^\dagger$ and suppose

$$
\langle\mathcal M\rangle=c\mathbf 1_{N_f}.
$$

Show that the unbroken subgroup is $SU(N_f)_V$.

<details>
<summary><strong>Solution</strong></summary>

The transformed condensate is

$$
\langle\mathcal M\rangle\to cLR^\dagger .
$$

It equals the original condensate $c\mathbf 1_{N_f}$ precisely when

$$
LR^\dagger=\mathbf 1_{N_f},
\qquad L=R.
$$

Thus the unbroken transformations are the diagonal subgroup

$$
SU(N_f)_V=\{(L,R):L=R\}.
$$

</details>

### Exercise 2: Count the Goldstone bosons

Assuming

$$
SU(N_f)_L\times SU(N_f)_R\to SU(N_f)_V,
$$

show that the number of Goldstone bosons is $N_f^2-1$. Evaluate this for $N_f=2$ and $N_f=3$.

<details>
<summary><strong>Solution</strong></summary>

The dimension of $SU(N_f)$ is $N_f^2-1$. The original group has dimension

$$
2(N_f^2-1),
$$

while the unbroken diagonal subgroup has dimension

$$
N_f^2-1.
$$

The number of broken generators is therefore

$$
2(N_f^2-1)-(N_f^2-1)=N_f^2-1.
$$

For $N_f=2$ this gives $3$ Goldstone bosons, identified with the pions in the two-flavor theory. For $N_f=3$ it gives $8$, identified with the pseudoscalar octet in the approximate three-flavor theory.

</details>

### Exercise 3: Extract the pion mass from the leading chiral Lagrangian

For two degenerate light quarks $m_u=m_d=m$, use

$$
\mathcal L_\chi
=\frac{f^2}{4}\operatorname{tr}(\partial_\mu U\partial^\mu U^\dagger)
+\frac{f^2B}{2}\operatorname{tr}(M_qU^\dagger+UM_q^\dagger)
$$

and $U=\exp(2i\pi^aT^a/f)$ to show that $m_\pi^2=2Bm$ at leading order.

<details>
<summary><strong>Solution</strong></summary>

With $M_q=m\mathbf 1$, expand

$$
U=1+\frac{2i\Pi}{f}-\frac{2\Pi^2}{f^2}+O(\Pi^3),
\qquad
\Pi=\pi^aT^a.
$$

The linear term cancels in $U+U^\dagger$. Since $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$,

$$
\operatorname{tr}(U+U^\dagger)
=2N_f-\frac{4}{f^2}\operatorname{tr}\Pi^2+\cdots
=2N_f-\frac{2}{f^2}\pi^a\pi^a+\cdots .
$$

The mass term in the Lagrangian is therefore

$$
\frac{f^2B}{2}m\operatorname{tr}(U+U^\dagger)
=\text{constant}-Bm\pi^a\pi^a+\cdots .
$$

Comparing with $-\frac12m_\pi^2\pi^a\pi^a$ gives

$$
m_\pi^2=2Bm.
$$

</details>

### Exercise 4: Why does Banks–Casher require infinite volume?

Explain why a nonzero $\rho(0)$ in

$$
\Sigma=\pi\rho(0)
$$

requires an infinite-volume limit before the chiral limit.

<details>
<summary><strong>Solution</strong></summary>

In finite volume, the Dirac operator has a discrete spectrum. Away from exact topological zero modes, the eigenvalues are isolated, so a smooth nonzero spectral density at exactly $\lambda=0$ is not obtained as an ordinary finite-volume function. In the thermodynamic limit, the eigenvalue spacing near zero can shrink like $1/V$, allowing a continuous density to build up. Taking $V\to\infty$ before $m\to0$ is therefore the spectral version of the ordinary order-of-limits requirement for spontaneous symmetry breaking.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, ch. 83, for a compact treatment of chiral symmetry breaking, the quark condensate, pions, and the chiral Lagrangian.
- S. Coleman, *Aspects of Symmetry*, especially the lectures on soft pions, current algebra, and spontaneous symmetry breaking.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, for chiral symmetry, current algebra, pions, and strong-interaction applications.

### Deeper references

- M. Mariño, *Instantons and Large N*, especially the discussion of fermions, chiral symmetry in QCD, the axial anomaly, and the Witten–Veneziano logic.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, for phases of gauge theories, chiral and other anomalies, and strong-dynamics examples.
- C. P. Burgess, *Introduction to Effective Field Theory*, for QCD and chiral perturbation theory as an effective field theory.
- T. Banks and A. Casher, “Chiral Symmetry Breaking in Confining Theories,” *Nuclear Physics B* **169** (1980), for the spectral-density criterion.

## Version history

- **2026-06-27:** Initial polished draft, added after the QCD overview page in the Strongly Coupled Gauge Theories chapter.
