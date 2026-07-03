---
title: "Nonrelativistic QED"
description: "Nonrelativistic QED as the effective field theory of slowly moving charged particles: Pauli fields, hard-mode matching, spin interactions, Darwin and spin-orbit terms, power counting, bound states, and precision atomic observables."
sidebar:
  label: "Nonrelativistic QED"
  order: 50
level: Graduate
status: "Polished draft"
source: "Caswell and Lepage 1986; Lepage 1997; Manohar 1997; Labelle 1998; Pineda and Soto 1998; Burgess 2020, chs. 3 and 11–12; Schwartz 2014, advanced EFT chapters."
topics:
  - nonrelativistic QED
  - NRQED
  - Pauli fields
  - bound-state EFT
  - matching
  - power counting
canonicalTopics:
  - nonrelativistic-qed
  - nrqed
  - pauli-effective-lagrangian
researchStatus:
  established:
    - "NRQED is the standard EFT for nonrelativistic charged particles interacting with photons, used in precision atomic, positronium, muonium, and hadronic-structure calculations."
  active:
    - "Higher-order bound-state calculations, proton-structure effects, precision spectroscopy, lattice-QCD matching for composite particles, and interface with potential NRQED remain active."
---

## Summary

Nonrelativistic QED, usually abbreviated NRQED, is the effective field theory of slowly moving charged particles interacting with photons. It is used when the particle mass $m$ is much larger than the kinetic energy and three-momentum scales of interest:

$$
|\mathbf p|\ll m,
\qquad
E_{\mathrm{kin}}\sim \frac{\mathbf p^2}{2m}\ll m.
$$

Instead of keeping a relativistic Dirac field with particle and antiparticle modes equally explicit, NRQED uses nonrelativistic Pauli fields for the low-energy charged particles. Antiparticles and hard virtual modes of order $m$ are integrated out and represented by local operators with Wilson coefficients.

For a spin-half particle of charge $q$, a standard one-particle part of the NRQED Lagrangian is

$$
\begin{aligned}
\mathcal L_{\mathrm{NRQED}}
=\psi^\dagger\bigg[
&iD_t
+\frac{\mathbf D^2}{2m}
+\frac{\mathbf D^4}{8m^3}
+c_F\frac{q\,\boldsymbol\sigma\cdot\mathbf B}{2m}
+c_D\frac{q\,\boldsymbol\nabla\cdot\mathbf E}{8m^2}
\\
&+i c_S\frac{q\,\boldsymbol\sigma\cdot(\mathbf D\times\mathbf E-\mathbf E\times\mathbf D)}{8m^2}
+\cdots
\bigg]\psi
+\mathcal L_{\mathrm{photons}}
+\mathcal L_{\text{4f}}
+\cdots .
\end{aligned}
$$

The displayed terms are, respectively, the Schrödinger kinetic term, relativistic kinetic correction, magnetic moment, Darwin term, spin-orbit term, and higher-order local corrections. The coefficients $c_i$ are Wilson coefficients. For a point Dirac fermion at tree level,

$$
c_2=c_4=c_F=c_D=c_S=1,
$$

with convention-dependent labels for $c_2$ and $c_4$ sometimes left implicit. Loops and compositeness change the coefficients.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Nonrelativistic QED map from relativistic QED through hard matching at the mass scale to Pauli fields, Wilson coefficients, operator hierarchy, bound-state power counting, and precision observables](/figures/renormalization-rg-eft/nrqed-operator-hierarchy.svg)

<figcaption>

NRQED integrates out the hard scale $m$ and describes charged particles with Pauli fields. Relativistic, spin, contact, and structure effects appear as local operators ordered by powers of velocity, momentum over mass, and couplings.

</figcaption>
</figure>

:::note[The punchline]
NRQED is not "the Schrödinger equation plus corrections by folklore." It is the most general gauge-invariant EFT of nonrelativistic charged particles and photons, with coefficients fixed by matching to relativistic QED or to data.
:::

## Prerequisites

You should know [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/), [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), and [Nonrenormalizable Does Not Mean Useless](/renormalization-rg-eft/effective-field-theory/nonrenormalizable-does-not-mean-useless/). It is also useful to know the Dirac equation, Pauli matrices, electromagnetic gauge invariance, and basic bound-state perturbation theory.

We use a Pauli field $\psi$ for a nonrelativistic spin-half particle. Let

$$
D_t=\partial_t+iqA_0,
\qquad
\mathbf D=\boldsymbol\nabla-iq\mathbf A,
$$

with a corresponding gauge convention chosen so that $D_t\psi$ and $\mathbf D\psi$ transform like $\psi$. If another page uses a different charge sign convention, signs in magnetic and electric couplings must be translated accordingly.

## Core idea

Relativistic QED contains several scales even before bound-state dynamics is considered. A particle with mass $m$ has rest energy $m$, but a nonrelativistic process has kinetic energy and momentum much smaller than $m$. For a Coulombic bound state,

$$
|\mathbf p|\sim mv,
\qquad
E\sim mv^2,
\qquad
v\sim \alpha
$$

for a hydrogenic system with small coupling $\alpha$.

NRQED removes the hard scale $m$ from the list of explicit dynamical scales. Hard effects become Wilson coefficients. The remaining fields describe particles, not relativistic particle-antiparticle pairs. Pair creation is not kinematically accessible at low energy; its virtual effects appear through local contact terms.

This is the same EFT logic seen elsewhere:

$$
\text{hard relativistic physics at }m
\quad\longrightarrow\quad
\text{local Wilson coefficients}
\quad+
\text{low-energy fields}.
$$

The difference is that the low-energy expansion is nonrelativistic. Operators are organized not just by mass dimension, but also by velocity and the hierarchy among $m$, $mv$, and $mv^2$.

## From Dirac to Pauli fields

A relativistic Dirac field contains positive-energy and negative-energy modes. At energies much smaller than $2m$, real pair creation is absent. One can therefore remove the rest-mass oscillation and project onto particle modes, much as in other heavy-particle EFTs.

The free relativistic dispersion relation is

$$
E=\sqrt{m^2+\mathbf p^2}
=m+\frac{\mathbf p^2}{2m}-\frac{\mathbf p^4}{8m^3}+O\!\left(\frac{\mathbf p^6}{m^5}\right).
$$

After subtracting the rest energy $m$, the nonrelativistic energy is

$$
E_{\mathrm{NR}}
=\frac{\mathbf p^2}{2m}-\frac{\mathbf p^4}{8m^3}+\cdots.
$$

This is why the NRQED Lagrangian contains

$$
\psi^\dagger
\left(iD_t+\frac{\mathbf D^2}{2m}+\frac{\mathbf D^4}{8m^3}+\cdots\right)
\psi.
$$

For a plane wave with $\mathbf D^2\to-\mathbf p^2$, the equation of motion gives the expansion above.

## The operator hierarchy

The simplest NRQED terms are fixed by gauge invariance and matching. Up to order $1/m^2$, the one-particle terms are often written

$$
\begin{aligned}
\mathcal L_\psi=\psi^\dagger\bigg[
&iD_t
+\frac{\mathbf D^2}{2m}
+\frac{\mathbf D^4}{8m^3}
+c_F\frac{q\,\boldsymbol\sigma\cdot\mathbf B}{2m}
+c_D\frac{q\,\boldsymbol\nabla\cdot\mathbf E}{8m^2}
\\
&+i c_S\frac{q\,\boldsymbol\sigma\cdot(\mathbf D\times\mathbf E-\mathbf E\times\mathbf D)}{8m^2}
+\cdots
\bigg]\psi.
\end{aligned}
$$

The physical meanings are:

| Term | Physical meaning |
|---|---|
| $\mathbf D^2/(2m)$ | Schrödinger kinetic energy. |
| $\mathbf D^4/(8m^3)$ | Relativistic correction to kinetic energy. |
| $c_F q\boldsymbol\sigma\cdot\mathbf B/(2m)$ | Magnetic moment interaction. |
| $c_D q\boldsymbol\nabla\cdot\mathbf E/(8m^2)$ | Darwin contact interaction. |
| $c_S$ spin-orbit term | Coupling of spin to electric-field gradients and orbital motion. |
| Four-fermion operators | Short-distance annihilation, hard exchange, or composite structure. |

For an elementary Dirac particle, tree-level matching gives the Dirac values. For an electron, loops shift $c_F$ through the anomalous magnetic moment. For a proton, $c_F$, $c_D$, and higher coefficients encode magnetic moment, charge radius, polarizabilities, and other structure effects.

## Gauge invariance and locality

NRQED is local at the scale $1/m$. It is not local at all possible low-energy scales after further reductions. For example, the Coulomb potential in a bound-state Schrödinger problem is nonlocal in space when written as an instantaneous potential. That potential arises after additional modes have been integrated out or solved for.

The NRQED Lagrangian itself is written in terms of gauge-covariant local operators built from

$$
\psi,
\qquad
D_t,
\qquad
\mathbf D,
\qquad
\mathbf E,
\qquad
\mathbf B.
$$

Gauge invariance is non-negotiable. It relates operators and prevents arbitrary insertions that would spoil charge conservation. Lorentz invariance is not manifest in NRQED, but remnants of the original relativistic symmetry impose relations among coefficients. These constraints are often described as reparametrization invariance or boost invariance.

One important relation for a spin-half particle is commonly written

$$
c_S=2c_F-1,
$$

in standard conventions. It expresses the fact that the spin-orbit interaction and magnetic moment are not independent once the EFT descends from a Lorentz-invariant relativistic theory.

## Matching

Wilson coefficients are fixed by demanding that NRQED reproduce low-energy amplitudes or matrix elements of relativistic QED. For example, one may match the scattering of a charged particle in a weak external electromagnetic field.

The relativistic current matrix element can be written in terms of form factors:

$$
\langle p'|J^\mu|p\rangle
=\bar u(p')\left[
F_1(q^2)\gamma^\mu
+\frac{iF_2(q^2)}{2m}\sigma^{\mu\nu}q_\nu
\right]u(p),
$$

where $q=p'-p$. Expanding this expression for small three-momenta and comparing with NRQED determines coefficients such as $c_F$ and $c_D$. Schematically,

$$
c_F=F_1(0)+F_2(0),
$$

while $c_D$ depends on $F_1(0)$, $F_2(0)$, and the slope of $F_1(q^2)$ at $q^2=0$, with conventions depending on the precise operator basis.

This is how compositeness enters. A proton at atomic scales can be represented by a Pauli field, but its Wilson coefficients are not the point-Dirac values. They remember the proton's internal structure.

## Bound-state power counting

For a Coulombic bound state, the typical velocity is $v\sim\alpha$. The hierarchy is

$$
m
\gg mv
\gg mv^2.
$$

For hydrogen,

$$
|\mathbf p|\sim m_e\alpha,
\qquad
E_{\mathrm{bind}}\sim m_e\alpha^2.
$$

This hierarchy explains why different operators contribute at different orders. For example,

$$
\frac{\mathbf p^4}{8m^3}
\sim m\alpha^4,
$$

which contributes to the fine structure at order $m\alpha^4$. Magnetic, Darwin, and spin-orbit terms also contribute at characteristic fine-structure orders.

Loops in NRQED must be counted with the same scale hierarchy. A loop momentum of order $mv$ is not the same as a loop energy of order $mv^2$. Bound-state calculations often become cleaner after moving from NRQED to potential NRQED, where potential, soft, and ultrasoft modes are separated more explicitly.

## What the coefficients mean

The Wilson coefficients in NRQED are not arbitrary knobs. They have precise meanings:

| Coefficient | What it knows about |
|---|---|
| $c_F$ | Magnetic moment and anomalous magnetic moment. |
| $c_D$ | Darwin interaction and charge-radius information. |
| $c_S$ | Spin-orbit coupling, constrained by Lorentz symmetry remnants. |
| Four-fermion coefficients | Annihilation, short-distance scattering, hard exchange, or composite structure. |
| Photon-sector coefficients | Vacuum polarization or heavy charged particles that have been integrated out. |

For a point electron, the coefficients can be computed perturbatively in $\alpha$. For nuclei or hadrons, some coefficients are extracted from experiment or matched from QCD, lattice QCD, or other hadronic calculations.

## Examples of use

NRQED is used in several precision contexts:

| System | Role of NRQED |
|---|---|
| Hydrogen | Fine structure, Lamb shift, recoil corrections, proton-structure effects. |
| Positronium | Relativistic corrections, annihilation operators, hyperfine splitting. |
| Muonium | Clean lepton-only bound state with recoil and radiative corrections. |
| Muonic hydrogen | Enhanced sensitivity to proton charge radius and polarizability. |
| Low-energy lepton-hadron scattering | Separation of pointlike QED effects from hadronic structure. |

NRQED is also the electromagnetic cousin of [Nonrelativistic QCD](/renormalization-rg-eft/major-efts/nonrelativistic-qcd/). The QCD version has additional complications from color, nonabelian gauge fields, and strong dynamics, but the EFT architecture is similar.

## Relation to the Schrödinger equation

The leading NRQED equation of motion is the Schrödinger equation with gauge coupling:

$$
iD_t\psi=-\frac{\mathbf D^2}{2m}\psi+\cdots.
$$

This does not mean NRQED is merely first-quantized quantum mechanics. NRQED is a quantum field theory. It can describe multiple particles, particle number sectors, loops, radiation, annihilation contact terms, and systematic matching to relativistic QED.

The Schrödinger equation is the leading single-particle sector. NRQED is the organizing structure around it.

## Common pitfalls

**Thinking NRQED is nonrelativistic QED with photons made nonrelativistic.** The charged matter is nonrelativistic. Photons can still be relativistic modes, with energies and momenta appropriate to the process.

**Forgetting antiparticles.** Antiparticles are not explicit low-energy fields in the simplest NRQED particle sector, but their virtual effects appear in Wilson coefficients and four-fermion operators.

**Using dimensions alone for power counting.** Nonrelativistic systems have several low-energy scales. Velocity counting is usually more informative than mass dimension alone.

**Assuming point-particle coefficients for composite particles.** A proton represented by a Pauli field is not a point Dirac fermion. Its Wilson coefficients encode form factors and polarizabilities.

**Confusing NRQED with potential NRQED.** NRQED still contains dynamical photons and local operators. Potential NRQED is a further EFT adapted to bound-state potentials and ultrasoft radiation.

## Relation to other pages

This page is a concrete example of [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/), and [Operator Basis Choice](/renormalization-rg-eft/matching-running-decoupling/operator-basis-choice/). It should be read together with [Heavy-Quark Effective Theory](/renormalization-rg-eft/major-efts/heavy-quark-effective-theory/) and [Nonrelativistic QCD](/renormalization-rg-eft/major-efts/nonrelativistic-qcd/).

## Research status

The structure of NRQED is standard. Active work concerns high-order precision calculations, bound-state logarithms, recoil corrections, proton-radius and polarizability effects, positronium and muonium spectroscopy, lattice matching for hadronic coefficients, and clean separation of QED, nuclear, and hadronic uncertainties.

## Exercises

### Exercise 1: Relativistic kinetic correction

Starting from

$$
E=\sqrt{m^2+\mathbf p^2},
$$

subtract the rest mass and derive the first two terms in the nonrelativistic kinetic energy.

<details><summary><strong>Solution</strong></summary>

Expand for $|\mathbf p|\ll m$:

$$
E=m\sqrt{1+\frac{\mathbf p^2}{m^2}}
=m\left[1+\frac{\mathbf p^2}{2m^2}-\frac{\mathbf p^4}{8m^4}+O\!\left(\frac{\mathbf p^6}{m^6}\right)\right].
$$

Subtracting $m$ gives

$$
E_{\mathrm{NR}}
=\frac{\mathbf p^2}{2m}-\frac{\mathbf p^4}{8m^3}+O\!\left(\frac{\mathbf p^6}{m^5}\right).
$$

This is reproduced by the NRQED kinetic terms when $\mathbf D^2\to-\mathbf p^2$.

</details>

### Exercise 2: Scaling of the fine-structure correction

For a Coulombic bound state with $v\sim\alpha$ and $|\mathbf p|\sim m\alpha$, estimate the size of the relativistic kinetic correction $-\mathbf p^4/(8m^3)$.

<details><summary><strong>Solution</strong></summary>

Using $|\mathbf p|\sim m\alpha$,

$$
\frac{\mathbf p^4}{8m^3}\sim \frac{m^4\alpha^4}{8m^3}\sim m\alpha^4.
$$

The leading binding energy is $m\alpha^2$, so this correction is suppressed by $\alpha^2$ relative to the leading energy. This is the standard fine-structure order.

</details>

### Exercise 3: Why four-fermion operators appear

Explain why NRQED contains local four-fermion operators even though the original relativistic theory only has photon exchange.

<details><summary><strong>Solution</strong></summary>

At low energies, not every relativistic process is represented by explicit low-energy propagation. Hard photon exchange, hard loop momentum, or particle-antiparticle annihilation at distances of order $1/m$ cannot be resolved by nonrelativistic modes. Their effects are analytic in low external momenta and therefore appear as local operators.

For two nonrelativistic fermion species, a schematic contact term is

$$
\frac{d}{m^2}\psi_1^\dagger\psi_1\psi_2^\dagger\psi_2.
$$

The coefficient $d$ is fixed by matching a low-energy scattering amplitude in the relativistic theory to the NRQED amplitude.

</details>

## References

- W. E. Caswell and G. P. Lepage, original formulation of NRQED for bound-state calculations.
- G. P. Lepage, lectures on how to use effective field theory and NRQED in precision calculations.
- A. V. Manohar, reviews of effective field theories for nonrelativistic systems.
- P. Labelle, reviews and applications of NRQED to bound states.
- A. Pineda and J. Soto, work on potential NRQED and bound-state scale separation.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on power counting, matching, and nonrelativistic applications.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, for the relativistic QED, renormalization, and EFT background.

## Version history

- 2026-06-19: First polished draft. Added Pauli-field Lagrangian, matching interpretation, bound-state power counting, coefficient meanings, relation to Schrödinger theory and potential NRQED, pitfalls, exercises, and figure.
