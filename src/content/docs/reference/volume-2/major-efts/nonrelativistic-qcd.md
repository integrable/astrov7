---
title: "Nonrelativistic QCD"
description: "NRQCD as the effective field theory for heavy quark–antiquark systems with separated hard, soft, and ultrasoft scales."
sidebar:
  label: "Nonrelativistic QCD"
  order: 60
level: Advanced
status: "Polished draft"
source: "Caswell and Lepage 1986; Bodwin, Braaten, and Lepage 1995; Manohar and Stewart, EFT lectures; Schwartz 2014, heavy-quark physics; Burgess 2020, nonrelativistic EFT chapters."
topics:
  - nonrelativistic QCD
  - quarkonium
  - heavy-quark expansion
  - velocity power counting
  - matching
  - four-fermion operators
canonicalTopics:
  - nrqcd
  - nonrelativistic-effective-field-theory
  - quarkonium-effective-theory
researchStatus:
  established:
    - 'NRQCD is the standard EFT organizing heavy quark–antiquark systems with $v\ll 1$, separating hard physics at the heavy-quark mass from nonrelativistic dynamics.'
  active:
    - "Precision quarkonium phenomenology, threshold production, lattice NRQCD, factorization for inclusive production, and the interface with potential NRQCD remain active research areas."
---

## Summary

**Nonrelativistic QCD**, usually abbreviated **NRQCD**, is the effective field theory of heavy quarks moving slowly compared with the speed of light. It is designed for systems such as bottomonium, charmonium, heavy-quark threshold production, and heavy quarks in a lattice calculation where the rest mass is much larger than the momenta that determine the low-energy dynamics.

The physical hierarchy is

$$
m\gg mv\gg mv^2,
$$

where $m$ is the heavy-quark mass, $v$ is the typical heavy-quark velocity inside the bound state, $mv$ is the relative momentum scale, and $mv^2$ is the kinetic or binding-energy scale. In a Coulombic system $v\sim \alpha_s(mv)$; in real charmonium and bottomonium the hierarchy is partly perturbative and partly nonperturbative, but it remains the organizing idea.

NRQCD is not merely the Schrödinger equation with QCD color factors sprinkled on top. It is a local EFT with Pauli spinor fields for heavy quarks and antiquarks, gluons and light quarks, Wilson coefficients determined by matching to QCD at the hard scale $m$, and a systematic expansion in powers of $v$ and $1/m$.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 56rem;">

![Scale hierarchy for NRQCD: QCD at the hard scale m is matched onto NRQCD, which keeps nonrelativistic heavy quarks, gluons, and light fields at softer scales; potential NRQCD can be obtained by integrating out the relative-momentum scale mv.](/figures/renormalization-rg-eft/nrqcd-scale-hierarchy.svg)

<figcaption>

NRQCD separates the hard scale $m$ from the nonrelativistic momentum and energy scales $mv$ and $mv^2$. Matching at $\mu\sim m$ fixes Wilson coefficients. Further integrating out the relative-momentum scale $mv$ leads to potential NRQCD, where potentials become matching coefficients and ultrasoft gluons remain dynamical.

</figcaption>
</figure>

## Prerequisites

You should know [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), [Integrating Out Heavy Fields](/renormalization-rg-eft/matching-running-decoupling/integrating-out-heavy-fields/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), and [Heavy-Quark Effective Theory](/renormalization-rg-eft/major-efts/heavy-quark-effective-theory/). You should also be comfortable with QCD color notation and the idea that Wilson coefficients encode short-distance physics.

The key contrast is this:

| EFT | Typical system | Expansion | Heavy-particle kinematics |
|---|---|---|---|
| HQET | one heavy quark inside a heavy-light hadron | $\Lambda_{\mathrm{QCD}}/m$ | fixed velocity, residual momentum $k\sim \Lambda_{\mathrm{QCD}}$ |
| NRQED | nonrelativistic charged particles and photons | $v$, $1/m$, $\alpha$ | Pauli particles interacting electromagnetically |
| NRQCD | heavy quark–antiquark systems and heavy-particle thresholds | $v$, $1/m$, $\alpha_s$ | Pauli quarks and antiquarks with color interactions |

HQET removes the large rest mass of a single heavy quark and expands around a fixed four-velocity. NRQCD keeps both heavy quarks and heavy antiquarks and describes their slow relative motion.

## Core idea

Start with QCD containing a heavy quark $Q$ of mass $m$. At energies much smaller than $m$, pair creation of heavy quarks from hard virtual momenta is not resolved as a dynamical short-distance process. The heavy quark and antiquark still exist as explicit nonrelativistic degrees of freedom, but their relativistic fluctuations at energy and momentum of order $m$ are absorbed into Wilson coefficients.

The EFT replaces the Dirac field $Q$ by two Pauli spinors:

| Field | Meaning |
|---|---|
| $\psi$ | annihilates a heavy quark |
| $\chi$ | creates a heavy antiquark |

The leading kinetic terms are nonrelativistic:

$$
\mathcal L_{\text{kin}}
=\psi^\dagger\left(iD_t+\frac{\mathbf D^2}{2m}\right)\psi
+\chi^\dagger\left(iD_t-\frac{\mathbf D^2}{2m}\right)\chi
+\cdots,
$$

where $D_t$ and $\mathbf D$ are QCD covariant derivatives in the appropriate color representations. Different sign conventions for $\chi$ appear in the literature, depending on whether one writes the antiquark as a charge-conjugate field. The invariant content is that quarks and antiquarks propagate with nonrelativistic kinetic energy $\mathbf p^2/(2m)$ after the rest energy has been removed.

The ellipsis contains spin interactions, relativistic corrections, Darwin and spin-orbit terms, four-fermion annihilation operators, and higher-dimension operators constrained by gauge symmetry, rotations, parity, time reversal, charge conjugation, and reparameterization-type relations inherited from Lorentz invariance.

## Why NRQCD is needed

A heavy quarkonium bound state is not controlled by a single scale. The rest mass, momentum, and binding energy are parametrically different:

$$
E_{\text{rest}}\sim m,
\qquad
|\mathbf p|\sim mv,
\qquad
E_{\text{kin}}\sim \frac{\mathbf p^2}{2m}\sim mv^2.
$$

Trying to describe all three scales with ordinary fixed-order QCD is inefficient. Near threshold, powers of $\alpha_s/v$ arise from repeated Coulomb exchange. These terms are not small if $v\sim \alpha_s$, even when $\alpha_s$ itself is perturbative. The bound state is therefore intrinsically nonrelativistic but not described by a finite number of ordinary QCD diagrams.

NRQCD reorganizes the calculation. The leading kinetic term is kept exactly, while short-distance relativistic effects are expanded in local operators. Coulombic enhancements are treated as part of the low-energy dynamics rather than as a badly behaved perturbative afterthought.

## The NRQCD Lagrangian

A standard schematic form is

$$
\mathcal L_{\text{NRQCD}}
=\mathcal L_{\text{light}}
+\mathcal L_\psi
+\mathcal L_\chi
+\mathcal L_{\psi\chi}
+\cdots,
$$

where $\mathcal L_{\text{light}}$ is the ordinary QCD Lagrangian for gluons and light quarks, and

$$
\begin{aligned}
\mathcal L_\psi
=\psi^\dagger\Bigg(&iD_t+\frac{\mathbf D^2}{2m}
+c_F\,\frac{g\,\boldsymbol\sigma\cdot\mathbf B}{2m}
+c_D\,\frac{g\,[\mathbf D\cdot\mathbf E-\mathbf E\cdot\mathbf D]}{8m^2}
\\
&+ic_S\,\frac{g\,\boldsymbol\sigma\cdot(\mathbf D\times\mathbf E-\mathbf E\times\mathbf D)}{8m^2}
+\frac{c_4\mathbf D^4}{8m^3}
+\cdots\Bigg)\psi .
\end{aligned}
$$

Here $\mathbf E^i=G^{i0}$ and $\mathbf B^i=-\frac12\epsilon^{ijk}G^{jk}$ up to the sign convention for the field strength. The coefficients $c_F,c_D,c_S,c_4,\ldots$ are Wilson coefficients. At tree level, many of them are one, but loop matching changes them.

The antiquark sector has analogous terms for $\chi$. The quark–antiquark sector contains four-fermion operators, for example schematically

$$
\mathcal L_{\psi\chi}
=\frac{d_1}{m^2}\psi^\dagger\chi\,\chi^\dagger\psi
+\frac{d_2}{m^2}\psi^\dagger\boldsymbol\sigma\chi\cdot\chi^\dagger\boldsymbol\sigma\psi
+\frac{d_3}{m^2}\psi^\dagger T^a\chi\,\chi^\dagger T^a\psi
+\cdots.
$$

These operators encode short-distance annihilation and production channels. Their coefficients can have imaginary parts; those imaginary parts are how inclusive quarkonium decay widths enter the EFT.

:::note[Wilson coefficients are not decoration]
The coefficients $c_i$ and $d_i$ are where hard QCD lives. Omitting them is not a harmless simplification if the goal is precision. NRQCD is predictive because the same coefficients control many processes once they are matched.
:::

## Matching at the hard scale

The matching step compares QCD and NRQCD for external states with momenta much smaller than $m$. One computes the same low-energy amplitude in both theories and chooses NRQCD coefficients so that

$$
\mathcal A_{\text{QCD}}(p\ll m)
=\mathcal A_{\text{NRQCD}}(p;c_i(\mu),d_i(\mu),\mu)
+O\left(\frac{p^{n+1}}{m^{n+1}}\right).
$$

At the hard scale $\mu\sim m$, the EFT loop integrals reproduce low-energy contributions. The difference between the full-theory result and the EFT result is analytic in the small external momenta and is absorbed into local Wilson coefficients.

A simple example is the chromomagnetic operator. Matching the heavy-quark scattering amplitude in an external background gluon field determines $c_F(\mu)$ in

$$
\psi^\dagger c_F\frac{g\boldsymbol\sigma\cdot\mathbf B}{2m}\psi.
$$

At tree level $c_F=1$. Loop corrections know about hard gluons with momenta of order $m$, so they belong in $c_F$ rather than in long-distance wave functions.

## Velocity power counting

The expansion is usually organized by the heavy-quark velocity $v$. The basic estimates are

$$
|\mathbf p|\sim mv,
\qquad
E\sim mv^2,
\qquad
\mathbf D\sim mv,
\qquad
D_t\sim mv^2.
$$

The leading nonrelativistic kinetic terms satisfy

$$
iD_t\sim \frac{\mathbf D^2}{2m}\sim mv^2.
$$

That is why both terms must be kept together. Treating the kinetic energy as a perturbation around $iD_t$ would destroy the bound-state expansion.

The chromomagnetic term is suppressed by one power of $1/m$ and by the scaling of the magnetic field. Spin-dependent splittings are therefore smaller than the leading binding energy. This is the EFT origin of approximate heavy-quark spin symmetry in quarkonium spectra.

Power counting in NRQCD is more subtle than in a single-scale EFT because different modes carry different scalings. A complete analysis distinguishes potential heavy quarks, soft gluons, ultrasoft gluons, and sometimes additional modes. The details depend on whether $mv$ is perturbative and whether one descends further to potential NRQCD.

## Potentials and potential NRQCD

NRQCD itself is not identical to a potential model. However, when the scale $mv$ can be integrated out, the EFT becomes **potential NRQCD**. In that theory the heavy quark–antiquark pair is represented by color-singlet and color-octet fields depending on the relative coordinate $\mathbf r$, and potentials appear as Wilson coefficients.

At leading perturbative order the color-singlet potential is Coulombic:

$$
V_s(r)=-\frac{C_F\alpha_s}{r},
\qquad
C_F=\frac{N_c^2-1}{2N_c}.
$$

The leading Schrödinger Hamiltonian is then

$$
H_0=\frac{\mathbf p^2}{m}+V_s(r),
$$

where $\mathbf p^2/m$ is the relative kinetic energy for two equal masses. Relativistic corrections, spin interactions, annihilation terms, ultrasoft gluon effects, and nonperturbative condensate effects enter systematically as higher-order EFT contributions.

The conceptual upgrade from old potential models is that potentials are not guessed. They are matched coefficients, run with scale, mix under renormalization, and come with a controlled power counting.

## Observables

NRQCD is used for several classes of observables.

| Observable | EFT ingredients |
|---|---|
| Quarkonium spectra | kinetic terms, potentials, spin-dependent corrections, nonperturbative matrix elements |
| Electromagnetic decays | local currents matched from QCD, wave function at origin, relativistic corrections |
| Hadronic annihilation decays | four-fermion operators with imaginary coefficients |
| Threshold production | Coulomb resummation, current matching, finite-width effects for top quarks |
| Lattice heavy quarks | discretized NRQCD action with improved coefficients |
| Inclusive production | NRQCD production operators and velocity-scaling matrix elements |

The most famous production formula has the schematic form

$$
\sigma(H)=\sum_n \hat\sigma(Q\bar Q[n])\,\langle 0|\mathcal O_n^H|0\rangle.
$$

Here $\hat\sigma$ is a short-distance partonic coefficient for producing a heavy quark pair in a state $n$, while $\mathcal O_n^H$ is a long-distance NRQCD matrix element for forming the hadron $H$. This factorization is powerful but subtle; its range of validity and phenomenological implementation are active topics.

## Worked example: why Coulomb exchange is leading

Consider heavy quarks near threshold with relative velocity $v$. The kinetic energy is

$$
E_{\text{kin}}\sim mv^2.
$$

A Coulomb potential generated by one-gluon exchange scales as

$$
V(r)\sim \frac{\alpha_s}{r}.
$$

Since the relative momentum is $p\sim mv$, the typical separation is

$$
r\sim \frac{1}{mv}.
$$

Therefore

$$
V(r)\sim \alpha_s mv.
$$

For a Coulombic bound state the virial estimate sets kinetic and potential energies of the same order:

$$
mv^2\sim \alpha_s mv.
$$

Thus

$$
v\sim \alpha_s.
$$

This is why Coulomb exchange cannot be treated as a small fixed-order correction when $v\sim \alpha_s$. The ladder diagrams with powers $(\alpha_s/v)^n$ must be resummed, and the resummation is just the leading nonrelativistic bound-state dynamics.

## Common pitfalls

**Confusing NRQCD with HQET.** HQET is optimized for one heavy quark inside a hadron with light degrees of freedom. NRQCD is optimized for slow heavy quarks and antiquarks, especially near threshold.

**Forgetting the hierarchy has three scales.** The hard scale $m$, soft scale $mv$, and ultrasoft scale $mv^2$ play different roles. Collapsing them into one scale usually produces wrong logarithms or wrong power counting.

**Treating $1/m$ counting and $v$ counting as identical.** They are related but not the same. Time derivatives, spatial derivatives, gluon fields, and four-fermion operators carry velocity scalings that must be assigned consistently.

**Calling every potential nonperturbative.** Potentials can be perturbatively matched coefficients in a controlled hierarchy. Nonperturbative physics enters when scales such as $mv$ or $mv^2$ approach $\Lambda_{\mathrm{QCD}}$.

**Assuming all Wilson coefficients are real.** Four-fermion annihilation coefficients may have imaginary parts, and those imaginary parts encode physical decay widths.

**Using a potential model without matching.** Potential models can be useful phenomenologically, but NRQCD is more than a model: it states which operators exist, how coefficients are matched, and how errors are organized.

## Relations to other pages

NRQCD sits in a family of EFTs.

| Theory | Relation |
|---|---|
| QCD | full theory matched at $\mu\sim m$ |
| HQET | single-heavy-particle EFT; shares $1/m$ logic but not quark–antiquark threshold dynamics |
| NRQED | Abelian version for atoms and precision electromagnetic bound states |
| pNRQCD | lower-energy EFT obtained by integrating out the relative-momentum scale $mv$ |
| SCET | EFT for energetic collinear particles; often combined with NRQCD in heavy-quark production and decay problems |
| Lattice NRQCD | numerical implementation where the heavy mass is removed before discretization |

## Research status

NRQCD as an EFT framework is established. Its operator expansion, matching logic, and velocity power counting are standard. Precision calculations in bottomonium, top threshold production, and lattice heavy-quark physics are mature.

The active frontier is not whether NRQCD is useful. It is how cleanly factorization works in difficult production environments, how to control nonperturbative matrix elements, how to combine NRQCD with SCET in multiscale processes, and how to quantify systematic uncertainties when the hierarchy $m\gg mv\gg mv^2$ is only moderately separated.

## Exercises

### Exercise 1: Kinetic energy scaling

Show that the leading kinetic term $\mathbf D^2/(2m)$ scales as $mv^2$ if $|\mathbf D|\sim mv$. Explain why it must be kept in the leading propagator.

<details><summary><strong>Solution</strong></summary>

With $|\mathbf D|\sim mv$,

$$
\frac{\mathbf D^2}{2m}\sim \frac{m^2v^2}{2m}\sim mv^2.
$$

The residual energy of a nonrelativistic heavy quark is also $E\sim mv^2$. Therefore $iD_t$ and $\mathbf D^2/(2m)$ are the same order. The leading propagator must contain both terms:

$$
\frac{i}{E-\mathbf p^2/(2m)+i\epsilon}.
$$

If the kinetic energy were treated as a perturbation, the pole structure of the nonrelativistic particle would be lost.

</details>

### Exercise 2: Tree-level matching of a heavy propagator expansion

Expand the relativistic energy

$$
E=\sqrt{m^2+\mathbf p^2}
$$

for $|\mathbf p|\ll m$ through order $\mathbf p^4/m^3$. Identify the corresponding correction to the NRQCD Hamiltonian.

<details><summary><strong>Solution</strong></summary>

Use

$$
\sqrt{m^2+\mathbf p^2}=m\sqrt{1+\frac{\mathbf p^2}{m^2}}.
$$

Expanding,

$$
E=m+\frac{\mathbf p^2}{2m}-\frac{\mathbf p^4}{8m^3}+O\left(\frac{\mathbf p^6}{m^5}\right).
$$

After removing the rest energy $m$, the nonrelativistic Hamiltonian contains

$$
H=\frac{\mathbf p^2}{2m}-\frac{\mathbf p^4}{8m^3}+\cdots.
$$

In the Lagrangian convention where the leading term is $\psi^\dagger(iD_t+\mathbf D^2/(2m)+\cdots)\psi$, this corresponds to the higher-derivative correction often written with coefficient $c_4$.

</details>

### Exercise 3: Coulomb resummation criterion

Suppose a near-threshold amplitude receives ladder corrections scaling as $(\alpha_s/v)^n$. Explain why fixed-order perturbation theory fails when $v\sim \alpha_s$.

<details><summary><strong>Solution</strong></summary>

If $v\sim \alpha_s$, then

$$
\frac{\alpha_s}{v}\sim 1.
$$

A term with $n$ Coulomb exchanges scales as

$$
\left(\frac{\alpha_s}{v}\right)^n\sim 1.
$$

Therefore all ladder diagrams are parametrically the same size. A fixed-order truncation does not approximate the answer. The correct leading-order treatment resums these terms into the nonrelativistic Green function or Schrödinger equation.

</details>

## References

- W. E. Caswell and G. P. Lepage, "Effective Lagrangians for Bound State Problems in QED, QCD, and Other Field Theories," *Physics Letters B* **167** (1986) 437.
- G. T. Bodwin, E. Braaten, and G. P. Lepage, "Rigorous QCD analysis of inclusive annihilation and production of heavy quarkonium," *Physical Review D* **51** (1995) 1125.
- A. V. Manohar and I. W. Stewart, lectures and reviews on heavy-quark and nonrelativistic effective field theories.
- A. Pineda and J. Soto, papers and reviews on potential NRQCD.
- M. E. Luke, A. V. Manohar, and I. Z. Rothstein, work on reparameterization and velocity power counting in NRQCD.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the heavy-quark physics chapter.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially the chapters on nonrelativistic applications and hierarchy logic.

## Version history

- 2026-06-19: First polished draft. Introduced NRQCD fields, scale hierarchy, matching, velocity power counting, potentials, observables, and relation to HQET, NRQED, pNRQCD, and SCET.
