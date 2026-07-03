---
title: "Decoupling Theorem"
description: "The EFT meaning of the Appelquist–Carazzone decoupling theorem: heavy fields leave local low-energy traces through parameter shifts and suppressed operators."
sidebar:
  label: "Decoupling Theorem"
  order: 8
level: Graduate
status: "Polished draft"
source: "Appelquist and Carazzone 1975; Weinberg Vol. II, ch. 18; Burgess 2020, chs. 1–3; Schwartz 2014, chs. 22–23; Collins, Renormalization; Georgi EFT lectures."
topics:
  - effective field theory
  - decoupling theorem
  - heavy particles
  - threshold matching
  - local operators
  - nondecoupling effects
canonicalTopics:
  - decoupling-theorem
  - appelquist-carazzone-theorem
  - heavy-field-decoupling
  - threshold-effects
researchStatus:
  established:
    - "The decoupling of heavy particles from low-energy observables, up to parameter shifts and local suppressed operators, is a standard theorem under appropriate locality and mass-gap assumptions."
  active:
    - "Decoupling and controlled failures of naive decoupling remain important in chiral gauge theories, spontaneously broken theories, anomaly matching, naturalness, gravitational EFT, finite-temperature systems, and multi-threshold precision calculations."
---

## Summary

The **decoupling theorem** says that sufficiently heavy particles do not need to appear as explicit low-energy degrees of freedom. If a theory contains light fields $\phi$ and heavy fields $H$ of mass $M$, then for external momenta

$$
Q\ll M,
$$

low-energy amplitudes involving only light external particles can be reproduced by an EFT containing only the light fields:

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\text{light}}^{\text{ren}}
+
\sum_i\frac{C_i(\mu)}{M^{\Delta_i-4}}\mathcal O_i.
$$

The heavy fields leave three kinds of traces:

1. finite or logarithmic shifts of light-theory parameters;
2. local higher-dimension operators suppressed by powers of $1/M$;
3. possible anomalous, topological, or symmetry-realization effects that must be matched rather than ignored.

The short slogan is

$$
\text{heavy particles disappear as particles, not as information.}
$$

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![A decoupling theorem map: a full theory with light and heavy fields is matched near the heavy scale onto a light-field EFT with shifted parameters and local higher-dimension operators, then used at low energies Q much smaller than M.](/figures/renormalization-rg-eft/decoupling-theorem-low-energy-map.svg)

<figcaption>

Below a heavy threshold, the EFT removes the heavy particle from the spectrum but keeps its low-energy imprint. Analytic heavy-particle effects become local operators and threshold shifts; nonanalytic low-energy dependence is produced by the remaining light fields.

</figcaption>
</figure>

:::note[Decoupling is not erasure]
A heavy particle may be absent from external states and low-energy loops, while still changing couplings, masses, theta angles, anomaly-matching terms, and Wilson coefficients.
:::

## Prerequisites

You should know [EFT Philosophy](/renormalization-rg-eft/effective-field-theory/eft-philosophy/), [Derivative Expansion](/renormalization-rg-eft/effective-field-theory/derivative-expansion/), [Matching](/renormalization-rg-eft/effective-field-theory/matching/), and [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/).

Useful background includes [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/), [Regulator Dependence](/renormalization-rg-eft/why-renormalization/regulator-dependence/), and [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/).

## Core idea

A low-energy experiment cannot resolve virtual propagation over distances of order $1/M$ when all external wavelengths are much longer:

$$
\lambda_{\text{external}}\sim Q^{-1}\gg M^{-1}.
$$

At such long distances, heavy-particle exchange looks pointlike. For example,

$$
\frac{1}{M^2-p^2}
=
\frac{1}{M^2}
+
\frac{p^2}{M^4}
+
\frac{p^4}{M^6}
+
\cdots,
\qquad |p^2|\ll M^2.
$$

The right-hand side is a series of local interactions with more and more derivatives. This is the elementary mechanism behind decoupling.

The loop version is slightly richer but conceptually the same. A loop containing heavy propagators can be expanded at low external momentum. The part of the loop momentum region of order $M$ produces local terms. The nonlocal low-energy behavior is reproduced by loops of the light fields in the EFT.

Thus the full theory and the EFT can agree order by order:

$$
\mathcal A_{\text{full}}(Q,M)
=
\mathcal A_{\text{EFT}}(Q;C_i(\mu),\mu)
+O\left(\frac{Q^{n+1}}{M^{n+1}}\right).
$$

The EFT is not pretending the heavy field never existed. It is representing the heavy field by the most general local imprint allowed by symmetry.

## Setup and conventions

Let $M$ be a heavy mass and $Q$ a light external scale. We assume

$$
Q\ll M.
$$

A matching scale $\mu_M$ is chosen near the threshold:

$$
\mu_M\sim M.
$$

The EFT below $M$ contains only light propagating fields. Its Lagrangian is written as

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\text{light}}(g_a(\mu),m_r(\mu))
+
\sum_{\Delta_i>4}\frac{C_i(\mu)}{M^{\Delta_i-4}}\mathcal O_i.
$$

The parameters $g_a(\mu)$ and $m_r(\mu)$ are not necessarily the same numbers as the full-theory parameters. They include threshold corrections. In a mass-independent scheme such as MS or $\overline{\mathrm{MS}}$, heavy particles do not automatically disappear from beta functions; one normally implements decoupling by explicit matching at thresholds.

## Statement of the theorem

A practical form of the Appelquist–Carazzone decoupling theorem is:

> In a local renormalizable quantum field theory with light particles and particles of mass $M$, low-energy Green functions with only light external fields can be reproduced, for external momenta and light masses much smaller than $M$, by a theory of the light fields alone. The difference between the full theory and the light theory is absorbed into renormalized light parameters and local operators suppressed by powers of $1/M$, provided the relevant assumptions about locality, mass gaps, and fixed couplings are satisfied.

Symbolically,

$$
\Gamma^{(n)}_{\text{full}}(p_i;m_{\text{light}},M)
=
Z_{\text{match}}^{n/2}
\Gamma^{(n)}_{\text{light}}(p_i;m'_{\text{light}})
+
\sum_{k\ge1}\frac{1}{M^k}
\Gamma^{(n)}_{k}(p_i)
$$

for

$$
|p_i|,m_{\text{light}}\ll M.
$$

The first term says that the renormalizable light theory has shifted parameters and field normalizations. The remaining terms come from higher-dimension local operators.

This statement is not a guarantee that every heavy particle has a numerically tiny effect on every low-energy quantity. Relevant operators, symmetry breaking, anomalies, or couplings that grow with $M$ can leave important low-energy traces.

## Why heavy effects become local

The analytic structure of amplitudes explains decoupling. A heavy particle of mass $M$ produces thresholds at energies of order $M$, such as

$$
p^2=4M^2
$$

for pair production. Far below threshold, amplitudes are analytic in the small external momenta. Analytic functions can be Taylor expanded:

$$
\mathcal A_{\text{heavy}}(p)
=
A_0+A_2\frac{p^2}{M^2}+A_4\frac{p^4}{M^4}+\cdots.
$$

A polynomial in momenta is the momentum-space signature of local operators in position space. The term $A_0$ shifts a low-dimension coupling. The term proportional to $p^2/M^2$ corresponds to a higher-derivative operator. Higher powers give higher-dimension operators.

Nonanalytic terms such as

$$
\log(-p^2),
\qquad
\sqrt{p^2-4m^2},
\qquad
\frac{1}{p^2}
$$

come from light thresholds, massless particles, or on-shell propagation. Those effects are not integrated out; they must be produced by the EFT loops and matrix elements.

## Tree-level decoupling: heavy exchange

Consider a heavy scalar $H$ coupled to a light scalar $\phi$:

$$
\mathcal L
=\frac12(\partial\phi)^2-\frac12m^2\phi^2
+\frac12(\partial H)^2-\frac12M^2H^2
-\frac{g}{2}H\phi^2.
$$

At tree level, exchange of $H$ produces a light four-point amplitude proportional to

$$
-\frac{g^2}{M^2-p^2}.
$$

For $p^2\ll M^2$,

$$
-\frac{g^2}{M^2-p^2}
=
-\frac{g^2}{M^2}
-\frac{g^2p^2}{M^4}
-\frac{g^2p^4}{M^6}
-\cdots.
$$

The EFT contains

$$
\mathcal L_{\text{EFT}}
\supset
-\frac{g^2}{8M^2}\phi^4
+
\text{higher-derivative terms},
$$

where the coefficient depends on the normalization convention for $\phi^4$. What matters is the structure: heavy exchange becomes a local tower.

This is decoupling at its most transparent. Below the heavy mass, the propagator cannot be resolved as a propagator.

## Loop-level decoupling and hard regions

Loop diagrams make decoupling more subtle because loop momentum can be large even when external momentum is small. A one-loop integral involving a heavy field has two useful regions:

| Momentum region | Meaning in EFT |
|---|---|
| hard loop momentum $k\sim M$ | short-distance contribution; becomes Wilson coefficients and threshold corrections |
| soft loop momentum $k\sim Q$ | long-distance contribution; reproduced by loops of light EFT fields |

The hard region is analytic in the external momenta and light masses, so it gives local operators. The soft region contains the infrared structure. Matching is designed to isolate the hard difference between the full theory and the EFT.

In dimensional regularization, this often becomes especially clean. If the same infrared regulator is used on both sides, the infrared terms agree and cancel in the matching difference. The Wilson coefficient is then determined by the short-distance remainder.

## Decoupling and renormalization schemes

In a physical momentum-subtraction scheme, a heavy loop contribution to a low-momentum process often visibly dies as $Q^2/M^2$. In an MS-like scheme, the beta function can still include the heavy particle even when $\mu\ll M$, because MS subtracts poles without asking whether a particle is kinematically active.

This means:

$$
\text{MS does not automatically decouple heavy particles.}
$$

The EFT solution is threshold matching. At $\mu_M\sim M$, one relates the full-theory coupling to the EFT coupling:

$$
g_{\text{EFT}}(\mu_M)
=
g_{\text{full}}(\mu_M)+\Delta g_{\text{threshold}}(M,\mu_M).
$$

Below $M$, one runs $g_{\text{EFT}}$ with the beta function of the light theory only.

Thus a heavy quark in QCD, a heavy charged lepton in QED, or a massive BSM particle in SMEFT calculations should not be left in the low-energy beta function merely because the subtraction scheme is mass independent. One matches it out.

## Example: a heavy charged fermion in QED

Suppose a charged fermion of mass $M$ couples to the photon. At momenta $q^2\ll M^2$, its vacuum-polarization contribution is analytic after charge renormalization:

$$
\Pi(q^2)-\Pi(0)
=
O\left(\frac{q^2}{M^2}\right).
$$

The constant part $\Pi(0)$ shifts the definition of the low-energy electric charge. The remaining terms generate higher-derivative photon operators. If all charged matter is integrated out, the photon EFT contains terms such as

$$
\mathcal L_{\text{EFT}}
=
-\frac14F_{\mu\nu}F^{\mu\nu}
+
\frac{c_1}{M^4}(F_{\mu\nu}F^{\mu\nu})^2
+
\frac{c_2}{M^4}(F_{\mu\nu}\widetilde F^{\mu\nu})^2
+\cdots.
$$

The heavy fermion no longer appears as an external particle or a loop degree of freedom below threshold, but it leaves local photon self-interactions and threshold shifts.

## Decoupling versus nondecoupling

Decoupling has assumptions. When those assumptions are violated or subtly modified, heavy particles can leave effects that are not simply suppressed by powers of $Q/M$.

Important cases include:

| Situation | What can happen |
|---|---|
| relevant operators | scalar masses or vacuum energies can receive contributions proportional to heavy scales |
| spontaneous symmetry breaking | heavy masses generated by large couplings to an order parameter can leave unsuppressed symmetry-breaking effects |
| anomalies | heavy fermions can leave Wess–Zumino terms or anomaly-matching data |
| topological terms | theta angles and Chern–Simons levels can shift discretely or by finite amounts |
| chiral gauge theories | gauge-invariant mass terms may be unavailable, so decoupling requires care |
| finite temperature or density | particles with $T\sim M$ or chemical potential near threshold are not thermally decoupled |
| massless mediators | long-range forces produce nonanalytic infrared behavior that cannot be Taylor expanded locally |

This is why the word decoupling should not be used as a reflexive dismissal. A heavy particle may decouple from low-energy propagation while still controlling a low-energy parameter or anomaly.

## Decoupling and naturalness

The decoupling theorem explains why higher-dimension operators are suppressed. It does **not** by itself solve naturalness problems for relevant operators.

A scalar mass term has dimension two:

$$
\mathcal L\supset -\frac12m^2\phi^2.
$$

Heavy physics can shift it by an amount of order

$$
\Delta m^2\sim \frac{\lambda}{16\pi^2}M^2
$$

in a cutoff-sensitive or threshold-sensitive situation. This is not a contradiction of decoupling. The mass term is a relevant operator already present in the low-energy theory. Heavy physics is allowed to shift its coefficient.

For an irrelevant operator, heavy physics gives suppression by powers of $1/M$. For a relevant operator, heavy physics can instead create sensitivity to positive powers of $M$. This distinction is one of the roots of the hierarchy problem.

## Decoupling and anomalies

Anomalies are also not erased by making particles heavy. If a heavy fermion participates in anomaly cancellation, the low-energy theory must still know how gauge invariance or global anomaly matching works after that fermion is removed from the spectrum.

Depending on the situation, the low-energy description may require:

- Wess–Zumino terms;
- Chern–Simons terms;
- axion-like couplings;
- modified transformation laws;
- additional light degrees of freedom;
- a different global form of the symmetry.

The slogan is:

$$
\text{mass gaps remove particles, not consistency conditions.}
$$

This is why anomaly matching is a low-energy constraint, not merely a statement about massless elementary fermions.

## Wilsonian interpretation

In Wilsonian language, decoupling is almost tautological. Lower the cutoff below the heavy mass:

$$
\Lambda<M.
$$

Modes with characteristic energy of order $M$ are no longer present explicitly. Their effects have been absorbed into the Wilsonian action

$$
S_\Lambda[\phi]
=
\sum_i g_i(\Lambda)\int d^d x\,\mathcal O_i(x).
$$

The local expansion is justified because the heavy correlation length is short:

$$
\xi_H\sim M^{-1}.
$$

At distances much longer than $\xi_H$, the details of the heavy field are invisible except through local couplings. This is the same intuition behind universality in critical phenomena and the derivative expansion in EFT.

## Common pitfalls

**Saying heavy particles have no low-energy effect.** They may shift marginal couplings, relevant parameters, theta angles, anomaly terms, and Wilson coefficients.

**Using MS beta functions below thresholds without matching.** In mass-independent schemes, heavy particles do not automatically disappear from beta functions. Build the appropriate EFT.

**Confusing decoupling with small numerical impact.** A contribution suppressed by $1/M^2$ may still be experimentally important if measured precisely or enhanced by symmetry factors, large multiplicities, or infrared effects.

**Applying the theorem without a mass gap.** If the would-be heavy sector contains massless modes, Goldstone bosons, gauge fields, or near-threshold states, the simple Taylor expansion can fail.

**Forgetting relevant operators.** Heavy physics can strongly affect scalar masses and vacuum energy because these are relevant operators.

**Ignoring anomaly matching.** A heavy anomalous sector must leave a consistent low-energy remnant. Gauge invariance is not optional below threshold.

## Relations to other pages

[Matching](/renormalization-rg-eft/effective-field-theory/matching/) is the practical implementation of decoupling. It fixes the threshold corrections and Wilson coefficients left behind by the heavy degrees of freedom.

[Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/) explains what happens after decoupling: once the heavy fields are removed, Wilson coefficients evolve with the anomalous dimensions of the light EFT.

[Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/) explains why the local operators left by decoupling can be organized by powers of $Q/M$. The later naturalness pages will treat the relevant-operator caveat in more detail.

## Research status

The decoupling theorem is established QFT infrastructure. Its EFT interpretation is the default modern language for threshold physics, heavy particles, and low-energy expansions.

The active work lies in precise applications and controlled exceptions: multi-loop threshold matching, decoupling in gauge theories with spontaneous symmetry breaking, chiral theories, anomaly matching, nonperturbative thresholds, gravitational EFT, finite-temperature EFT, finite-density EFT, nuclear EFT, and theories with multiple nearby scales.

## Exercises

### Exercise 1: Heavy propagator to local operators

Show that a heavy exchange amplitude

$$
\mathcal A(p^2)=-\frac{g^2}{M^2-p^2}
$$

has a local low-energy expansion for $|p^2|\ll M^2$. Identify the first two powers of $1/M$.

<details><summary><strong>Solution</strong></summary>

Use the geometric expansion

$$
\frac{1}{M^2-p^2}
=
\frac{1}{M^2}\frac{1}{1-p^2/M^2}
=
\frac{1}{M^2}
\left(1+\frac{p^2}{M^2}+\frac{p^4}{M^4}+\cdots\right).
$$

Therefore

$$
\mathcal A(p^2)
=
-\frac{g^2}{M^2}
-\frac{g^2p^2}{M^4}
+O\left(\frac{p^4}{M^6}\right).
$$

The first term corresponds to a non-derivative local operator. The second corresponds to an operator with two derivatives.

</details>

### Exercise 2: Why nonanalytic terms signal light physics

Explain why a term like $\log(-p^2/M^2)$ cannot be reproduced by a finite number of local operators in a low-energy Lagrangian.

<details><summary><strong>Solution</strong></summary>

A finite set of local operators gives a polynomial in external momenta. An infinite derivative expansion can give a power series analytic near $p^2=0$. The function $\log(-p^2/M^2)$ is nonanalytic at $p^2=0$, so it cannot arise from integrating out only heavy gapped physics.

Such logarithms usually come from massless or light degrees of freedom. In EFT, they are reproduced by loops of the light fields, not by Wilson coefficients from heavy matching alone.

</details>

### Exercise 3: MS and decoupling

Why can a heavy particle contribute to an MS beta function even for $\mu\ll M$, and how does EFT repair this?

<details><summary><strong>Solution</strong></summary>

MS subtracts ultraviolet poles in dimensional regularization. The subtraction rule is mass independent; it does not automatically test whether a particle of mass $M$ is kinematically active at the scale $\mu$. Therefore the full-theory beta function can include the heavy particle even when $\mu\ll M$.

EFT repairs this by matching at $\mu_M\sim M$ and then removing the heavy particle from the dynamical field content below $M$. The low-energy coupling runs with the beta function of the light theory only, while the heavy particle appears through threshold corrections and higher-dimension operators.

</details>

### Exercise 4: Relevant operators and heavy scales

A light scalar has a mass term $m^2\phi^2/2$. Explain why a threshold correction $\Delta m^2\sim \lambda M^2/(16\pi^2)$ is not a violation of decoupling.

<details><summary><strong>Solution</strong></summary>

Decoupling says that heavy physics appears at low energy through local operators and parameter shifts. The scalar mass term is a relevant local operator already allowed in the light theory. Heavy physics is allowed to shift its coefficient by a contribution proportional to the heavy scale.

The suppression by powers of $1/M$ applies to irrelevant operators of dimension greater than four. Relevant operators have positive mass-dimension coefficients, so their sensitivity to heavy scales is precisely the naturalness issue, not a contradiction of decoupling.

</details>

## References

- T. Appelquist and J. Carazzone, "Infrared Singularities and Massive Fields," *Physical Review D* **11** (1975) 2856, for the classic decoupling theorem.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for renormalization group methods, mass effects, and decoupling in modern field theory.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapters 1–3, for the EFT interpretation of decoupling, matching, Wilson actions, and power counting.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters 22–23, for nonrenormalizable theories, Wilsonian RG, and EFT running.
- John Collins, *Renormalization*, for a systematic treatment of renormalization, subtraction schemes, and decoupling.
- Howard Georgi, EFT lectures, for the practical physics viewpoint that low-energy theories should contain only the degrees of freedom they need.

## Version history

- 2026-06-18: First polished draft. Added theorem statement, EFT interpretation, scheme dependence, examples, caveats, and exercises.
