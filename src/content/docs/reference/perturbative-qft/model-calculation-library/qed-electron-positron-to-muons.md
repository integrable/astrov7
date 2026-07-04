---
title: "QED Electron–Positron to Muons"
description: "A complete tree-level calculation of electron–positron annihilation into a muon pair, including the s-channel amplitude, Ward check, angular distribution, total cross section, and threshold behavior."
sidebar:
  label: "QED e⁺e⁻ → μ⁺μ⁻"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§58–60; Coleman 2019, chs. 30 and 34–35; Schwartz 2014, chs. 5 and 13; Weinberg 1995, Vol. I, chs. 3, 6, and 8."
topics:
  - QED
  - electron-positron annihilation
  - muon-pair production
  - spin-averaged cross sections
  - model calculations
canonicalTopics:
  - qed-tree-amplitudes
  - electron-positron-annihilation
  - muon-pair-production
  - model-calculation-library
researchStatus:
  established:
    - "Tree-level electron–positron annihilation into a muon pair is a textbook-standard QED calculation and the cleanest benchmark for s-channel vector-current production."
  active:
    - "Precision versions require initial-state radiation, final-state radiation, vacuum polarization, electroweak corrections, beam effects, and realistic fiducial definitions."
---

## Summary

The process

$$
e^-(p_1)+e^+(p_2)\to \mu^-(p_3)+\mu^+(p_4)
$$

is the canonical annihilation calculation in spinor QED. At tree level, the electron–positron pair annihilates into a virtual photon, which then produces a muon pair. With the site’s QED vertex convention, the amplitude is

$$
\mathcal M
=
\frac{e^2}{s+i\epsilon}
\left[\overline v_e(p_2)\gamma^\mu u_e(p_1)\right]
\left[\overline u_\mu(p_3)\gamma_\mu v_\mu(p_4)\right],
$$

where

$$
s=(p_1+p_2)^2.
$$

Neglecting the electron mass but keeping the muon mass $M$, define

$$
\beta=\sqrt{1-\frac{4M^2}{s}}.
$$

Then the unpolarized center-of-momentum differential cross section is

$$
\frac{d\sigma}{d\Omega}
=
\frac{\alpha^2\beta}{4s}
\left[1+\cos^2\theta+(1-\beta^2)\sin^2\theta\right].
$$

The total cross section is

$$
\sigma(e^+e^-\to\mu^+\mu^-)
=
\frac{4\pi\alpha^2}{3s}\,\beta\left(1+\frac{2M^2}{s}\right).
$$

In the high-energy limit $s\gg M^2$, this becomes $4\pi\alpha^2/(3s)$. Near threshold it vanishes as $\beta$, because the final two-body phase space closes.

## Prerequisites

You should know [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/), [Spinor and Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/), and [QED Electron–Muon Scattering](/perturbative-qft/model-calculation-library/qed-electron-muon-scattering/). For the spinor background, review [Dirac Field](/foundations/free-fields/dirac-field/).

## Core idea

This calculation is the $s$-channel sibling of electron–muon scattering. Instead of two charged currents exchanging spacelike momentum, an electron current annihilates into a timelike virtual photon with invariant mass $\sqrt s$.

<figure class="doc-figure" style="--figure-width: 40rem; --caption-width: 54rem;">

![Tree-level electron-positron annihilation into a muon pair](/figures/perturbative-qft/qed-electron-positron-to-muons.svg)

<figcaption>

Tree-level $e^-e^+\to\mu^-\mu^+$ in QED. The electron–positron current produces a timelike virtual photon with $q^2=s$, and the photon creates the muon pair. This is the cleanest place to see how an $s$-channel propagator becomes a production cross section.

</figcaption>
</figure>

There are two reasons this process is a model-calculation workhorse. First, the final particles have different flavor from the initial ones, so there is no identical-particle exchange term. Second, at energies well below the $Z$ pole and above the muon threshold, the QED answer is a simple normalization benchmark for more complicated annihilation processes.

## Setup and conventions

The QED vertex for a charge-$q$ Dirac field is

$$
-iq\gamma^\mu.
$$

For the electron and muon, $q=-e$ with $e>0$, so each charged-lepton vertex is $+ie\gamma^\mu$. In Feynman gauge, the photon propagator is

$$
\frac{-i\eta_{\mu\nu}}{q^2+i\epsilon}.
$$

We take

$$
p_1^2=p_2^2\simeq 0,
\qquad
p_3^2=p_4^2=M^2,
$$

where $M$ is the muon mass. The Mandelstam variables are

$$
s=(p_1+p_2)^2,
\qquad
t=(p_1-p_3)^2,
\qquad
u=(p_1-p_4)^2,
$$

with

$$
s+t+u=2M^2.
$$

In the center-of-momentum frame,

$$
t-M^2=-\frac{s}{2}(1-\beta\cos\theta),
\qquad
u-M^2=-\frac{s}{2}(1+\beta\cos\theta).
$$

The final-state velocity is

$$
\beta=\frac{|\mathbf p_3|}{E_3}
=\sqrt{1-\frac{4M^2}{s}}.
$$

## Tree-level amplitude

Let

$$
q=p_1+p_2=p_3+p_4,
\qquad q^2=s.
$$

The $s$-channel photon diagram gives

$$
\begin{aligned}
i\mathcal M
&=
\left[\overline v_e(p_2)(+ie\gamma^\mu)u_e(p_1)\right]
\frac{-i\eta_{\mu\nu}}{s+i\epsilon}
\left[\overline u_\mu(p_3)(+ie\gamma^\nu)v_\mu(p_4)\right]\\
&=
i\frac{e^2}{s+i\epsilon}
\left[\overline v_e(p_2)\gamma^\mu u_e(p_1)\right]
\left[\overline u_\mu(p_3)\gamma_\mu v_\mu(p_4)\right].
\end{aligned}
$$

Thus

$$
\mathcal M
=
\frac{e^2}{s+i\epsilon}
\left[\overline v_e(p_2)\gamma^\mu u_e(p_1)\right]
\left[\overline u_\mu(p_3)\gamma_\mu v_\mu(p_4)\right].
$$

The amplitude is a product of an annihilation current and a production current. The internal photon is not a final-state photon; it is a propagator carrying timelike momentum.

## Ward check

The longitudinal part of the photon propagator does not contribute. For the initial current,

$$
J_e^\mu=\overline v_e(p_2)\gamma^\mu u_e(p_1),
\qquad q=p_1+p_2.
$$

Then

$$
q_\mu J_e^\mu
=
\overline v_e(p_2)(p_1\!\!\!/+p_2\!\!\!/)u_e(p_1).
$$

Using the Dirac equations

$$
p_1\!\!\!/\,u_e(p_1)=m_e u_e(p_1),
\qquad
\overline v_e(p_2)p_2\!\!\!/=-m_e\overline v_e(p_2),
$$

we get

$$
q_\mu J_e^\mu=0.
$$

Similarly, for the muon current

$$
J_\mu^\nu=\overline u_\mu(p_3)\gamma^\nu v_\mu(p_4),
$$

one has

$$
q_\nu J_\mu^\nu=0.
$$

This is the same physical statement as in electron–muon scattering: the photon couples to a conserved current. The difference is that here the conserved current creates or annihilates a particle–antiparticle pair.

## Spin average

For an unpolarized cross section,

$$
\overline{|\mathcal M|^2}
=
\frac14\sum_{\text{spins}}|\mathcal M|^2.
$$

Neglecting the electron mass, the initial trace is

$$
L_e^{\mu\nu}
=
\operatorname{tr}\left[p_2\!\!\!/\gamma^\mu p_1\!\!\!/\gamma^\nu\right].
$$

The final muon trace is

$$
L_{\mu,\mu\nu}
=
\operatorname{tr}\left[
(p_3\!\!\!/+M)\gamma_\mu(p_4\!\!\!/-M)\gamma_\nu
\right].
$$

Therefore

$$
\overline{|\mathcal M|^2}
=
\frac{e^4}{s^2}\frac14 L_e^{\mu\nu}L_{\mu,\mu\nu}.
$$

Evaluating the traces gives the invariant result

$$
\overline{|\mathcal M|^2}
=
\frac{2e^4}{s^2}
\left[(t-M^2)^2+(u-M^2)^2+2M^2s\right].
$$

In the center-of-momentum frame this becomes

$$
\overline{|\mathcal M|^2}
=e^4\left[2-\beta^2\sin^2\theta\right],
$$

or equivalently

$$
\overline{|\mathcal M|^2}
=e^4\left[1+\cos^2\theta+(1-\beta^2)\sin^2\theta\right].
$$

The first form makes the threshold limit simple; the second form makes the high-energy angular distribution obvious.

## Differential and total cross section

For two massless initial particles and two equal-mass final particles,

$$
\frac{d\sigma}{d\Omega}
=
\frac{\beta}{64\pi^2s}\overline{|\mathcal M|^2}.
$$

Using $e^2=4\pi\alpha$, we obtain

$$
\frac{d\sigma}{d\Omega}
=
\frac{\alpha^2\beta}{4s}
\left[1+\cos^2\theta+(1-\beta^2)\sin^2\theta\right].
$$

Integrating over angles gives

$$
\sigma
=
\frac{2\pi\alpha^2}{3s}\,\beta(3-\beta^2).
$$

Since

$$
1+\frac{2M^2}{s}=\frac{3-\beta^2}{2},
$$

this is also

$$
\sigma
=
\frac{4\pi\alpha^2}{3s}\,\beta\left(1+\frac{2M^2}{s}\right).
$$

This is one of the standard normalization anchors for annihilation processes.

## High-energy and threshold limits

At high energy,

$$
\beta\to 1,
$$

so

$$
\frac{d\sigma}{d\Omega}
\to
\frac{\alpha^2}{4s}(1+\cos^2\theta),
\qquad
\sigma\to\frac{4\pi\alpha^2}{3s}.
$$

Near threshold,

$$
s\to 4M^2,
\qquad
\beta\to 0.
$$

The squared amplitude remains finite and isotropic,

$$
\overline{|\mathcal M|^2}\to 2e^4,
$$

but the cross section vanishes as $\beta$ because the two-body phase space has no final momentum available.

## Relation to crossing and other QED benchmarks

This calculation is related by crossing to other tree-level QED processes.

| Process | Channel structure | Main extra issue |
|---|---|---|
| $e^-\mu^-\to e^-\mu^-$ | $t$-channel photon exchange | spacelike momentum transfer |
| $e^-e^+\to\mu^-\mu^+$ | $s$-channel photon exchange | positron and antimuon spinors |
| $e^-e^+\to e^-e^+$ | $s$ and $t$ photon exchange | Bhabha interference |
| $e^-\gamma\to e^-\gamma$ | $s$ and $u$ electron exchange | two diagrams required by gauge invariance |

For hadronic final states, the same $s$-channel photon structure underlies the famous ratio

$$
R(s)=\frac{\sigma(e^+e^-\to\text{hadrons})}{\sigma(e^+e^-\to\mu^+\mu^-)}.
$$

That observable belongs to QCD and precision phenomenology, but its denominator is precisely the high-energy limit derived here.

## Common pitfalls

**Using $u$ spinors for the incoming positron.** Incoming antifermions are represented by $v$ spinors. The initial current is $\overline v(p_2)\gamma^\mu u(p_1)$, not $\overline u(p_2)\gamma^\mu u(p_1)$.

**Forgetting the phase-space velocity.** The squared amplitude does not vanish at muon threshold, but the cross section does because of the final-state factor $\beta$.

**Double-counting the final state.** The final particles are $\mu^-$ and $\mu^+$, which are distinguishable by charge. There is no final-state factor $1/2!$.

**Confusing this with Bhabha scattering.** For $e^-e^+\to e^-e^+$, an additional $t$-channel diagram contributes and interferes with the annihilation diagram.

**Treating the virtual photon as an observed photon.** The internal photon carries $q^2=s$, so for $s>0$ it is timelike and off shell. It is not part of the final state.

**Ignoring electroweak corrections near the $Z$ pole.** At energies near $m_Z$, $Z$ exchange and photon–$Z$ interference are essential. This page is the pure tree-level QED benchmark.

## Relations to other pages

- [QED Electron–Muon Scattering](/perturbative-qft/model-calculation-library/qed-electron-muon-scattering/) is the crossed distinguishable-scattering benchmark.
- [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/) gives the general QED tree rules used here.
- [Crossing Symmetry](/perturbative-qft/from-correlators-to-s-matrix/crossing-symmetry/) explains how annihilation and scattering processes are analytically related.
- [Spinor and Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/) gives the spin sums and trace identities used in the squared amplitude.
- [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/) supplies the phase-space conversion.
- [Electroweak Corrections](/perturbative-qft/precision-observables/electroweak-corrections/) explains why the pure QED answer is only the first approximation near electroweak scales.

## Research status

- **Established:** The tree-level QED amplitude, spin average, angular distribution, threshold behavior, and high-energy total cross section are textbook-standard.
- **Active:** Precision $e^+e^-$ predictions include QED radiation, vacuum polarization, electroweak exchange, beam effects, detector cuts, and hadronic final-state modeling.
- **Approximate:** The formulas on this page neglect the electron mass except where it regulates collinear radiation, which is beyond this tree-level calculation.

## Exercises

### Exercise 1: Ward check for the annihilation current

Show that

$$
q_\mu\overline v(p_2)\gamma^\mu u(p_1)=0,
\qquad q=p_1+p_2,
$$

for an on-shell electron–positron pair of equal mass $m$.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
q_\mu\overline v(p_2)\gamma^\mu u(p_1)
=
\overline v(p_2)(p_1\!\!\!/+p_2\!\!\!/)u(p_1).
$$

The spinors obey

$$
p_1\!\!\!/\,u(p_1)=m u(p_1),
\qquad
\overline v(p_2)p_2\!\!\!/=-m\overline v(p_2).
$$

Therefore

$$
\overline v(p_2)(p_1\!\!\!/+p_2\!\!\!/)u(p_1)
=
m\overline v(p_2)u(p_1)-m\overline v(p_2)u(p_1)=0.
$$

</details>

### Exercise 2: Massless angular distribution

Take $M=0$ in the result for $\overline{|\mathcal M|^2}$ and show that

$$
\frac{d\sigma}{d\Omega}
=
\frac{\alpha^2}{4s}(1+\cos^2\theta).
$$

<details>
<summary><strong>Solution</strong></summary>

For $M=0$,

$$
\beta=1,
$$

and

$$
\overline{|\mathcal M|^2}
=e^4(1+\cos^2\theta).
$$

The two-body formula for massless initial and final particles is

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2s}\overline{|\mathcal M|^2}.
$$

Using $e^2=4\pi\alpha$ gives

$$
\frac{d\sigma}{d\Omega}
=
\frac{16\pi^2\alpha^2}{64\pi^2s}(1+\cos^2\theta)
=
\frac{\alpha^2}{4s}(1+\cos^2\theta).
$$

</details>

### Exercise 3: Total cross section

Starting from

$$
\frac{d\sigma}{d\Omega}
=
\frac{\alpha^2\beta}{4s}(2-\beta^2\sin^2\theta),
$$

integrate over solid angle to obtain

$$
\sigma=\frac{2\pi\alpha^2}{3s}\beta(3-\beta^2).
$$

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\int d\Omega=4\pi,
\qquad
\int d\Omega\,\sin^2\theta=\frac{8\pi}{3}.
$$

Then

$$
\begin{aligned}
\sigma
&=\frac{\alpha^2\beta}{4s}
\left[2(4\pi)-\beta^2\frac{8\pi}{3}\right]\\
&=\frac{\alpha^2\beta}{4s}\,8\pi\left(1-\frac{\beta^2}{3}\right)\\
&=\frac{2\pi\alpha^2}{3s}\beta(3-\beta^2).
\end{aligned}
$$

</details>

### Exercise 4: Threshold behavior

Explain why the total cross section vanishes at threshold even though $\overline{|\mathcal M|^2}$ is finite.

<details>
<summary><strong>Solution</strong></summary>

At threshold,

$$
s=4M^2,
\qquad
\beta=\sqrt{1-\frac{4M^2}{s}}=0.
$$

The squared amplitude approaches

$$
\overline{|\mathcal M|^2}\to 2e^4,
$$

so the matrix element itself is not singular or zero. The total cross section contains the two-body final-state phase-space factor $\beta$. Physically, the muons have no available three-momentum at threshold, so the density of final states closes and

$$
\sigma\propto\beta\to0.
$$

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§58–60, for spinor electrodynamics and QED scattering examples.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 30 and 34–35, for QED quantization, low-order spinor-electrodynamics computations, and precision QED motivation.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5 and 13, especially the $e^+e^-\to\mu^+\mu^-$ calculation and QED Feynman rules.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 3, 6, and 8, for scattering theory, Feynman rules, and quantum electrodynamics.

## Version history

- **2026-06-14:** Initial model-calculation page for $e^+e^-\to\mu^+\mu^-$, including the tree-level amplitude, Ward check, spin average, angular distribution, total cross section, and threshold behavior.
