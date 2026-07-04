---
title: "QED Electron–Muon Scattering"
description: "A complete tree-level calculation of elastic electron–muon scattering in QED, including the photon-exchange amplitude, Ward check, spin average, cross section, and Rutherford limit."
sidebar:
  label: "QED Electron–Muon Scattering"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§58–59; Coleman 2019, chs. 30 and 34; Schwartz 2014, chs. 5 and 13; Weinberg 1995, Vol. I, chs. 3, 6, and 8."
topics:
  - QED
  - electron-muon scattering
  - photon exchange
  - spin-averaged cross sections
  - model calculations
canonicalTopics:
  - qed-tree-amplitudes
  - electron-muon-scattering
  - photon-exchange-amplitudes
  - model-calculation-library
researchStatus:
  established:
    - "Tree-level electron–muon scattering by one-photon exchange is a textbook-standard QED calculation and a clean benchmark for spinor traces and the Rutherford limit."
  active:
    - "Precision versions require loop corrections, soft photon radiation, lepton-mass effects, detector definitions, and sometimes hadronic vacuum-polarization input."
---

## Summary

Electron–muon scattering is one of the cleanest QED model calculations because the two charged particles are distinguishable. The process

$$
e^-(p_1)+\mu^-(p_2)\to e^-(p_3)+\mu^-(p_4)
$$

has one tree-level diagram: $t$-channel photon exchange. Using the charge convention of the QED tree-amplitude page, the amplitude is

$$
\mathcal M_t
=
\frac{e^2}{t+i\epsilon}
\left[\overline u_e(p_3)\gamma^\mu u_e(p_1)\right]
\left[\overline u_\mu(p_4)\gamma_\mu u_\mu(p_2)\right],
$$

where

$$
t=(p_1-p_3)^2.
$$

For unpolarized scattering, with electron mass $m$ and muon mass $M$,

$$
\overline{|\mathcal M_t|^2}
=
\frac{2e^4}{t^2}
\left[
(s-m^2-M^2)^2
+(u-m^2-M^2)^2
+2t(m^2+M^2)
\right].
$$

The center-of-momentum cross section is

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2s}
\overline{|\mathcal M_t|^2}.
$$

In the nonrelativistic limit, the same amplitude reduces to repulsive Coulomb scattering and gives the Rutherford angular dependence. This page is the vector-exchange sibling of [Yukawa Exchange Scattering](/perturbative-qft/model-calculation-library/yukawa-exchange-scattering/).

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/), [Spinor and Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), and [Two-to-Two Scattering](/perturbative-qft/phase-space-cross-sections-decays/two-to-two-scattering/). For the field-theory background, review [Dirac Field](/foundations/free-fields/dirac-field/) and [Maxwell Field](/foundations/free-fields/maxwell-field/).

## Core idea

Photon exchange couples two conserved vector currents. For electron–muon scattering, the electron line supplies

$$
J_e^\mu=\overline u_e(p_3)\gamma^\mu u_e(p_1),
$$

and the muon line supplies

$$
J_\mu^\nu=\overline u_\mu(p_4)\gamma^\nu u_\mu(p_2).
$$

The photon propagator contracts the two Lorentz indices. In Feynman gauge,

$$
J_e^\mu\frac{-i\eta_{\mu\nu}}{t+i\epsilon}J_\mu^\nu
$$

is the whole internal-line structure.

<figure class="doc-figure" style="--figure-width: 43rem; --caption-width: 54rem;">

![Tree-level QED electron-muon scattering](/figures/perturbative-qft/qed-electron-muon-scattering.svg)

<figcaption>

Tree-level electron–muon scattering by one-photon exchange. The amplitude is a product of two conserved Dirac currents connected by the photon propagator. The nonrelativistic limit gives the repulsive Coulomb potential and the Rutherford angular dependence.

</figcaption>
</figure>

This calculation is deliberately chosen instead of Møller scattering $e^-e^-\to e^-e^-$. Because the particles are distinguishable, there is no exchange diagram and no identical-fermion minus sign. That makes it the right first full trace calculation in QED.

## Setup and conventions

The relevant QED interaction for a charge-$q$ Dirac field is

$$
\mathcal L_{\rm int}
=-q\,\overline\psi\gamma^\mu A_\mu\psi.
$$

The charge-$q$ photon–fermion vertex is therefore

$$
-iq\gamma^\mu.
$$

For both the electron and the muon,

$$
q=-e,
\qquad e>0,
$$

so each vertex is

$$
+ie\gamma^\mu.
$$

In Feynman gauge, the photon propagator is

$$
\frac{-i\eta_{\mu\nu}}{k^2+i\epsilon}.
$$

We assign momenta as

$$
e^-(p_1,s_1)+\mu^-(p_2,s_2)\to e^-(p_3,s_3)+\mu^-(p_4,s_4),
$$

with

$$
p_1^2=p_3^2=m^2,
\qquad
p_2^2=p_4^2=M^2.
$$

The Mandelstam invariants are

$$
s=(p_1+p_2)^2,
\qquad
t=(p_1-p_3)^2,
\qquad
u=(p_1-p_4)^2,
$$

and

$$
s+t+u=2m^2+2M^2.
$$

## Tree-level amplitude

Let

$$
q=p_1-p_3=p_4-p_2,
\qquad
q^2=t.
$$

The tree diagram gives

$$
\begin{aligned}
i\mathcal M_t
&=
\left[\overline u_e(p_3)(+ie\gamma^\mu)u_e(p_1)\right]
\frac{-i\eta_{\mu\nu}}{t+i\epsilon}
\left[\overline u_\mu(p_4)(+ie\gamma^\nu)u_\mu(p_2)\right] \\
&=
i\frac{e^2}{t+i\epsilon}
\left[\overline u_e(p_3)\gamma^\mu u_e(p_1)\right]
\left[\overline u_\mu(p_4)\gamma_\mu u_\mu(p_2)\right].
\end{aligned}
$$

Therefore

$$
\mathcal M_t
=
\frac{e^2}{t+i\epsilon}
\left[\overline u_e(p_3)\gamma^\mu u_e(p_1)\right]
\left[\overline u_\mu(p_4)\gamma_\mu u_\mu(p_2)\right].
$$

For physical spacelike momentum transfer, $t<0$. In the nonrelativistic limit the amplitude is negative, which corresponds to a positive repulsive potential after Born matching.

## Current conservation and gauge independence

The Feynman-gauge propagator may be replaced by a general covariant-gauge propagator containing longitudinal terms proportional to $q_\mu q_\nu$. These terms do not affect the amplitude because the external Dirac currents are conserved.

For the electron current,

$$
q_\mu \overline u_e(p_3)\gamma^\mu u_e(p_1)
=
\overline u_e(p_3)(p_1\!\!\!/-p_3\!\!\!/)u_e(p_1).
$$

Using the external Dirac equations,

$$
p_1\!\!\!/\,u_e(p_1)=m u_e(p_1),
\qquad
\overline u_e(p_3)p_3\!\!\!/=m\overline u_e(p_3),
$$

we get

$$
q_\mu J_e^\mu=0.
$$

The same argument gives $q_\nu J_\mu^\nu=0$ for the muon current. Thus the longitudinal part of the photon propagator drops out. This is the simplest Ward-identity check in a model calculation.

## Spin average by traces

For an unpolarized cross section,

$$
\overline{|\mathcal M_t|^2}
=
\frac14\sum_{\text{spins}}|\mathcal M_t|^2.
$$

The spin sums give

$$
\overline{|\mathcal M_t|^2}
=
\frac{e^4}{t^2}\frac14
L_e^{\mu\nu}L_{\mu,\mu\nu},
$$

where

$$
L_e^{\mu\nu}
=
\operatorname{tr}\left[
(p_3\!\!\!/+m)\gamma^\mu(p_1\!\!\!/+m)\gamma^\nu
\right],
$$

and

$$
L_{\mu,\mu\nu}
=
\operatorname{tr}\left[
(p_4\!\!\!/+M)\gamma_\mu(p_2\!\!\!/+M)\gamma_\nu
\right].
$$

The basic trace identity is

$$
\operatorname{tr}\left[
(a\!\!\!/+m)\gamma^\mu(b\!\!\!/+m)\gamma^\nu
\right]
=
4\left[
a^\mu b^\nu+a^\nu b^\mu-(a\cdot b-m^2)\eta^{\mu\nu}
\right].
$$

For elastic scattering,

$$
p_1\cdot p_3=m^2-\frac{t}{2},
\qquad
p_2\cdot p_4=M^2-\frac{t}{2}.
$$

Contracting the two tensors and rewriting the remaining dot products in terms of $s$, $t$, and $u$ gives

$$
\overline{|\mathcal M_t|^2}
=
\frac{2e^4}{t^2}
\left[
(s-m^2-M^2)^2
+(u-m^2-M^2)^2
+2t(m^2+M^2)
\right].
$$

This expression is symmetric under exchanging the initial and final labels on either fermion line, but it is not symmetric under $t\leftrightarrow u$ because electron–muon scattering has no identical-particle exchange term.

## Cross section

For elastic two-body scattering in the center-of-momentum frame,

$$
\frac{d\sigma}{d\Omega}
=
\frac{1}{64\pi^2s}\overline{|\mathcal M_t|^2}.
$$

Thus

$$
\frac{d\sigma}{d\Omega}
=
\frac{e^4}{32\pi^2s\,t^2}
\left[
(s-m^2-M^2)^2
+(u-m^2-M^2)^2
+2t(m^2+M^2)
\right].
$$

This is the compact invariant answer. The angle dependence enters through $t$ and $u$. In the center-of-momentum frame,

$$
t=-2|\mathbf p|^2(1-\cos\theta)
=-4|\mathbf p|^2\sin^2\frac{\theta}{2}.
$$

The forward divergence is the long-range Coulomb singularity. In any physical experiment, finite angular resolution, screening, wave packets, or real soft radiation regulates what is actually measured.

## Massless check

If $m=M=0$, then

$$
s+t+u=0,
$$

and the spin-averaged squared amplitude reduces to

$$
\overline{|\mathcal M_t|^2}
=
\frac{2e^4}{t^2}(s^2+u^2).
$$

This is the standard massless current-current result. It is a useful check on signs and factors of $2$.

## Nonrelativistic Coulomb and Rutherford limit

For small three-momenta,

$$
\overline u(p')\gamma^0u(p)\simeq 2m,
\qquad
\overline u(p')\gamma^iu(p)=O(|\mathbf p|),
$$

so

$$
J_e\cdot J_\mu\simeq 4mM,
\qquad
t\simeq-\mathbf q^2.
$$

The amplitude becomes

$$
\mathcal M_{\rm NR}
\simeq
-\frac{4mM e^2}{\mathbf q^2}.
$$

The Born matching

$$
\mathcal M_{\rm NR}=-4mM\,\widetilde V(\mathbf q)
$$

therefore gives

$$
\widetilde V(\mathbf q)=\frac{e^2}{\mathbf q^2},
\qquad
V(r)=\frac{e^2}{4\pi r}=\frac{\alpha}{r}.
$$

This is repulsive for two negatively charged particles. With reduced mass $\mu_{\rm red}=mM/(m+M)$ and relative velocity $v$, the Rutherford limit is

$$
\frac{d\sigma}{d\Omega}
=
\frac{\alpha^2}{4\mu_{\rm red}^2v^4\sin^4(\theta/2)}.
$$

This check is worth doing at least once: it confirms the sign of the QED amplitude and the normalization of relativistic states.

## Relation to other QED processes

Electron–muon scattering is the distinguishable-particle prototype. Closely related tree-level QED processes differ only by crossing and identical-particle bookkeeping:

| Process | Tree-level structure | Extra issue |
|---|---|---|
| $e^-\mu^-\to e^-\mu^-$ | $t$-channel photon exchange | none |
| $e^-e^-\to e^-e^-$ | $t$ and $u$ photon exchange | identical-fermion minus sign |
| $e^-e^+\to\mu^-\mu^+$ | $s$-channel photon exchange | positron $v$ spinors |
| $e^-\gamma\to e^-\gamma$ | two electron-exchange diagrams | Ward identity requires both diagrams |

That is why this page is a good benchmark: it isolates the vector-current trace without mixing in annihilation or identical-particle exchange.

## Common pitfalls

**Using the wrong QED vertex sign.** The site convention gives a charge-$q$ vertex $-iq\gamma^\mu$. For an electron or muon, $q=-e$, so the vertex is $+ie\gamma^\mu$.

**Forgetting to average over initial spins.** The unpolarized result includes a factor $1/4$ from the two initial spin states of the electron and the two initial spin states of the muon.

**Dropping masses too early.** The massless formula is elegant, but it hides the nonrelativistic Rutherford limit and changes the interpretation of helicity and threshold behavior.

**Calling the exchanged photon a detected particle.** The internal photon is a propagator. It is generally off shell and not an element of the final state.

**Forgetting gauge independence.** A single photon-exchange diagram between conserved external currents is gauge-parameter independent. If your answer depends on the longitudinal propagator term, the current-conservation algebra has gone sideways.

**Confusing electron–muon scattering with Møller scattering.** Møller scattering has an additional exchange diagram and interference term because the external fermions are identical. This page intentionally avoids that complication.

## Relations to other pages

- [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/) gives the general tree-level QED rules and related processes.
- [Yukawa Exchange Scattering](/perturbative-qft/model-calculation-library/yukawa-exchange-scattering/) is the scalar-exchange comparison calculation.
- [Spinor and Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/) explains the spin sums and traces used here.
- [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/) develops the gauge-invariance logic beyond this simple current-conservation check.
- [Soft Photon Theorem](/perturbative-qft/infrared-physics-factorization/soft-photon-theorem/) and [Bloch–Nordsieck Theorem](/perturbative-qft/infrared-physics-factorization/bloch-nordsieck-theorem/) explain why precision QED scattering requires real soft radiation.
- [Fixed-Order Predictions](/perturbative-qft/precision-observables/fixed-order-predictions/) explains how tree-level results become the lowest term in a precision prediction.

## Research status

- **Established:** The one-photon-exchange amplitude, Ward check, spin-averaged trace, and Rutherford limit are standard QED results.
- **Active:** High-precision lepton scattering depends on loop corrections, infrared-safe observable definitions, vacuum polarization, electroweak effects, and experimental cuts.
- **Convention-dependent:** The intermediate vertex signs depend on the covariant-derivative convention. The invariant cross section and Rutherford limit are physical.

## Exercises

### Exercise 1: Current conservation

Show that

$$
q_\mu\overline u(p_3)\gamma^\mu u(p_1)=0
$$

for elastic scattering of an on-shell Dirac fermion with $q=p_1-p_3$.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
q_\mu\overline u(p_3)\gamma^\mu u(p_1)
=
\overline u(p_3)(p_1\!\!\!/-p_3\!\!\!/)u(p_1).
$$

The external Dirac equations give

$$
p_1\!\!\!/\,u(p_1)=m u(p_1),
\qquad
\overline u(p_3)p_3\!\!\!/=m\overline u(p_3).
$$

Therefore

$$
\overline u(p_3)(p_1\!\!\!/-p_3\!\!\!/)u(p_1)
=
m\overline u(p_3)u(p_1)-m\overline u(p_3)u(p_1)=0.
$$

</details>

### Exercise 2: Massless limit

Starting from the massive spin-averaged result,

$$
\overline{|\mathcal M_t|^2}
=
\frac{2e^4}{t^2}
\left[
(s-m^2-M^2)^2
+(u-m^2-M^2)^2
+2t(m^2+M^2)
\right],
$$

take $m=M=0$.

<details>
<summary><strong>Solution</strong></summary>

Setting $m=M=0$ immediately gives

$$
\overline{|\mathcal M_t|^2}
=
\frac{2e^4}{t^2}(s^2+u^2).
$$

For massless four-point kinematics, $s+t+u=0$, but no further simplification is needed. This is the standard massless $t$-channel vector-exchange result.

</details>

### Exercise 3: Nonrelativistic potential

Use the nonrelativistic limit of the amplitude to recover the Coulomb potential.

<details>
<summary><strong>Solution</strong></summary>

The leading nonrelativistic currents are

$$
J_e^0\simeq 2m,
\qquad
J_\mu^0\simeq 2M,
$$

with spatial components suppressed. Since $t\simeq-\mathbf q^2$,

$$
\mathcal M_{\rm NR}
\simeq
-\frac{4mM e^2}{\mathbf q^2}.
$$

Matching to

$$
\mathcal M_{\rm NR}=-4mM\,\widetilde V(\mathbf q)
$$

gives

$$
\widetilde V(\mathbf q)=\frac{e^2}{\mathbf q^2}.
$$

Fourier transformation gives

$$
V(r)=\frac{e^2}{4\pi r}.
$$

</details>

### Exercise 4: Trace contraction

Use the trace identity in the page to show that the spin-averaged squared amplitude can be written in terms of $s$, $t$, and $u$ as

$$
\overline{|\mathcal M_t|^2}
=
\frac{2e^4}{t^2}
\left[
(s-m^2-M^2)^2
+(u-m^2-M^2)^2
+2t(m^2+M^2)
\right].
$$

<details>
<summary><strong>Solution</strong></summary>

The electron trace is

$$
L_e^{\mu\nu}
=
4\left[
p_3^\mu p_1^\nu+p_3^\nu p_1^\mu
-(p_3\cdot p_1-m^2)\eta^{\mu\nu}
\right],
$$

and the muon trace has the same form with $p_3,p_1,m$ replaced by $p_4,p_2,M$ and lowered Lorentz indices. Since

$$
p_3\cdot p_1-m^2=-\frac{t}{2},
\qquad
p_4\cdot p_2-M^2=-\frac{t}{2},
$$

the contraction reduces to

$$
\frac14 L_e^{\mu\nu}L_{\mu,\mu\nu}
=
2\left[
(s-m^2-M^2)^2
+(u-m^2-M^2)^2
+2t(m^2+M^2)
\right].
$$

Multiplying by $e^4/t^2$ gives the stated result.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§58–59, for spinor electrodynamics and scattering examples.
- S. Coleman, *Lectures on Quantum Field Theory*, chs. 30 and 34, for QED quantization, low-order spinor-electrodynamics computations, and physical QED checks.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 5 and 13, for cross sections, QED Feynman rules, and electron scattering examples.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 3, 6, and 8, for scattering conventions, Feynman rules, and quantum electrodynamics.

## Version history

- **2026-06-13:** Initial model-calculation page for tree-level electron–muon scattering, including the QED amplitude, Ward check, spin-averaged trace, cross section, and Rutherford limit.
