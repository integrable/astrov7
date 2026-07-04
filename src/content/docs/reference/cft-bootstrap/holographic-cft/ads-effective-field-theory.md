---
title: "AdS Effective Field Theory"
description: "How local bulk effective field theory in AdS organizes holographic CFT correlators, derivative expansions, contact terms, exchange diagrams, loops, and cutoff effects."
sidebar:
  label: "AdS Effective Field Theory"
  order: 5
level: Advanced
status: "Polished draft"
source: "Heemskerk, Penedones, Polchinski, and Sully; Fitzpatrick, Kaplan, Penedones, Raju, and van Rees; Burgess EFT; holographic bootstrap literature."
topics:
  - AdS effective field theory
  - holographic CFT
  - Witten diagrams
  - Mellin amplitudes
  - bulk locality
canonicalTopics:
  - ads-effective-field-theory
  - holographic-eft
  - ads-derivative-expansion
researchStatus:
  established:
    - "AdS effective field theory is the standard low-energy description of large-N holographic CFTs with sparse spectra and a large higher-spin gap."
  active:
    - "Current research sharpens EFT bounds from crossing, Regge behavior, causality, higher-spin gaps, finite-N effects, black-hole thresholds, and holographic loop reconstruction."
---

## Summary

**AdS effective field theory** is the low-energy bulk language for a special class of large-$N$ CFTs. When a CFT has large central charge, sparse light single-trace spectrum, and a large gap to higher-spin single-trace operators, its low-energy correlators can often be described by a local action in AdS:

$$
S_{\rm EFT}=\int_{\rm AdS} d^{d+1}X\sqrt g\,
\left[\mathcal L_{\rm light}+\sum_i \frac{c_i}{\Lambda^{k_i}}\mathcal O_i\right].
$$

Here $\Lambda$ is the bulk cutoff. In CFT units,

$$
\Lambda R_{\rm AdS}\sim \Delta_{\rm gap},
$$

where $\Delta_{\rm gap}$ is the dimension of the heavy single-trace states that have been integrated out.

The EFT computes CFT correlators through Witten diagrams. Contact interactions produce polynomial Mellin amplitudes. Exchange interactions produce meromorphic Mellin amplitudes. Loops produce higher-order $1/N$ corrections. Higher-derivative terms are suppressed by the gap.

The slogan is

$$
\text{AdS EFT}=\text{the derivative expansion of holographic CFT data}.
$$

This page explains what is meant by an AdS EFT, how it appears in CFT data, and where it breaks down.

## Prerequisites

Read [AdS/CFT Dictionary](/cft-bootstrap/holographic-cft/ads-cft-dictionary/), [Large-N and Factorization](/cft-bootstrap/holographic-cft/large-n-and-factorization/), [Witten Diagrams](/cft-bootstrap/holographic-cft/witten-diagrams/), and [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/) first.

You should also know [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/) and [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/), because AdS EFT is often most transparent in Mellin space and in perturbation theory around generalized free fields.

## Core idea

An effective field theory is a description valid below a cutoff. It includes all interactions compatible with symmetries, organized by powers of the cutoff. In AdS/CFT, the cutoff is measured in AdS units and is visible in the CFT as a gap in operator dimensions.

The bulk picture is:

$$
E\ll \Lambda
\quad\Longrightarrow\quad
\text{local AdS EFT is useful}.
$$

The CFT picture is:

$$
\Delta\ll \Delta_{\rm gap}
\quad\Longrightarrow\quad
\text{light single-trace data and double-trace towers dominate}.
$$

The same statement is being made in two languages.

A local EFT does not require knowing the microscopic string theory or quantum gravity completion. It requires knowing the light fields, their symmetries, the cutoff scale, and the allowed interactions. The heavy states are encoded in higher-derivative contact terms.

## The EFT action

A typical scalar-gravity EFT in AdS has the schematic form

$$
S_{\rm EFT}=\frac{1}{16\pi G_N}\int d^{d+1}X\sqrt g\,(R-2\Lambda_{\rm cos})
+\int d^{d+1}X\sqrt g\,\mathcal L_{\rm matter}
+S_{\rm higher\ derivative}.
$$

For a scalar field $\Phi$, the matter terms might include

$$
\mathcal L_{\rm matter}
=\frac12(\nabla\Phi)^2+\frac12m^2\Phi^2
+g_3\Phi^3+g_4\Phi^4+\cdots .
$$

Higher-derivative terms look like

$$
S_{\rm higher\ derivative}
=\int d^{d+1}X\sqrt g\,
\left[
\frac{a_1}{\Lambda^2}(\nabla\Phi)^4
+\frac{a_2}{\Lambda^4}(\nabla\nabla\Phi)^2\Phi^2
+\frac{b_1}{\Lambda^2}R^2
+\cdots
\right].
$$

The exact operator basis depends on fields, symmetries, and field redefinitions. The principle is universal: write every allowed local term and organize it by powers of the cutoff.

## CFT interpretation of EFT terms

Each EFT term has a CFT meaning.

| AdS EFT term | CFT interpretation |
|---|---|
| free kinetic term | single-trace two-point function and operator dimension |
| cubic coupling | single-trace three-point coefficient |
| quartic contact term | connected four-point function and double-trace shifts |
| exchange diagram | single-trace exchange in a CFT four-point function |
| higher-derivative term | higher-degree Mellin polynomial and gap-suppressed correction |
| bulk loop | higher-order $1/N$ correction to CFT data |
| counterterm | contact ambiguity or scheme-dependent local term |

For example, a quartic contact interaction shifts double-trace dimensions:

$$
\Delta_{n,\ell}=\Delta_{n,\ell}^{(0)}+N^{-p}\gamma_{n,\ell}^{(1)}+\cdots .
$$

In the bulk, this is a two-particle interaction energy. In the CFT, it is an anomalous dimension required by crossing at subleading order.

## Derivative expansion

The derivative expansion is the heart of EFT. At energies far below the cutoff, higher-derivative terms are suppressed.

If a term contains $k$ extra derivatives, its coefficient is typically suppressed by

$$
\Lambda^{-k}.
$$

In AdS units, this becomes

$$
(\Lambda R_{\rm AdS})^{-k}\sim \Delta_{\rm gap}^{-k}.
$$

Thus a large CFT gap suppresses higher-derivative bulk interactions.

This is why the higher-spin gap matters. If the first heavy higher-spin single-trace operators appear at large dimension, then low-energy correlators should be well approximated by a small number of low-derivative AdS interactions.

The derivative expansion is not just a calculational convenience. It is one of the main signatures of bulk locality.

## Contact terms

Contact interactions are the simplest EFT effects. A non-derivative quartic scalar term

$$
\int_{\rm AdS} d^{d+1}X\sqrt g\,g_4\Phi^4
$$

produces a four-point contact Witten diagram. In Mellin space it gives a constant Mellin amplitude:

$$
M(s,t)=\text{constant}.
$$

A derivative interaction such as

$$
\int_{\rm AdS} d^{d+1}X\sqrt g\,\frac{a}{\Lambda^2}(\nabla\Phi)^4
$$

gives a polynomial Mellin amplitude, schematically

$$
M(s,t)\sim \frac{a}{\Lambda^2}(s^2+t^2+u_M^2)+\cdots .
$$

The degree of the Mellin polynomial tracks the number of derivatives. This is the cleanest reason Mellin space is beloved in holographic EFT. It turns derivative counting into polynomial counting. Very civilized, for quantum gravity.

## Exchange terms

If the EFT contains a light field $X$, it can be exchanged between two pairs of external fields. In CFT language, this is the exchange of a single-trace operator $\mathcal X$.

An exchange Witten diagram is controlled by cubic couplings such as

$$
g_{12X},\qquad g_{34X}.
$$

These map to OPE coefficients:

$$
g_{12X}\leftrightarrow \lambda_{12X},
\qquad
 g_{34X}\leftrightarrow \lambda_{34X}.
$$

In Mellin space, exchange produces poles:

$$
M_{\rm exchange}(s,t)
=\sum_{m=0}^{\infty}\frac{R_m(t)}{s-(\Delta_X-\ell_X+2m)}+\text{contact ambiguity}.
$$

The pole locations encode the exchanged primary and its descendants. The contact ambiguity reflects the freedom to add local interactions with the same external fields.

## Integrating out heavy fields

Suppose a heavy bulk field $H$ of mass

$$
M_H R_{\rm AdS}\sim \Delta_H
$$

couples to light fields. At energies

$$
E\ll M_H,
$$

one can integrate it out. The result is a series of local contact interactions among the light fields.

A schematic example is

$$
\frac{g^2}{M_H^2}\Phi^4
+\frac{g^2}{M_H^4}(\nabla\Phi)^2\Phi^2+\cdots .
$$

In the CFT, the heavy single-trace operator no longer appears as an explicit low-energy exchange. Instead, its effect is encoded in higher-derivative contact terms suppressed by powers of

$$
\Delta_H^{-1}.
$$

This is the CFT meaning of decoupling in holography.

## Field redefinitions

EFTs contain redundancies. Some operators can be removed using equations of motion or field redefinitions. For example, terms proportional to the leading equations of motion can be shifted into other interactions without changing physical correlators.

In AdS/CFT, field redefinitions can change the form of the bulk action while leaving CFT correlators unchanged. Therefore not every coefficient in a written bulk Lagrangian is directly observable.

Observable data are quantities such as:

- CFT dimensions;
- OPE coefficients;
- correlators;
- Mellin amplitudes modulo contact-basis choices;
- anomalous dimensions of double-trace operators;
- physical Regge behavior.

The EFT basis is a bookkeeping choice. The CFT data are the invariant content.

## Power counting

Power counting estimates which diagrams and operators matter at a given order. In holographic EFT there are two common expansions:

1. the derivative expansion in powers of $E/\Lambda$;
2. the loop expansion in powers of $G_N/R_{\rm AdS}^{d-1}$ or $1/C_T$.

A tree-level contact diagram from a term with $k$ extra derivatives is suppressed by

$$
\left(\frac{E}{\Lambda}\right)^k.
$$

A one-loop diagram is additionally suppressed by a power of

$$
G_N/R_{\rm AdS}^{d-1}\sim C_T^{-1}.
$$

In many large-$N$ gauge-theory examples,

$$
C_T\sim N^2,
$$

so bulk loops correspond to powers of $1/N^2$.

The two expansions are logically distinct. A theory can have weak gravity but a low string scale, or a high gap but finite-$N$ corrections.

## Loops and counterterms

Loop Witten diagrams produce higher-order corrections to CFT data. They can also generate UV divergences in the bulk EFT. These divergences are absorbed into local counterterms, just as in ordinary EFT.

In CFT language, loop corrections affect:

- double-trace anomalous dimensions at higher order;
- OPE coefficient corrections;
- multi-trace mixing;
- double discontinuities;
- contact-term ambiguities.

Lorentzian inversion is especially useful at loop level because the double discontinuity of a loop correlator is often determined by lower-order data. This is the AdS/CFT cousin of unitarity cuts in flat-space amplitudes.

The lesson is:

$$
\text{bulk renormalization}\quad\leftrightarrow\quad
\text{consistent higher-order CFT data plus contact ambiguities}.
$$

## Gravitational EFT

When the stress tensor is present, the bulk EFT includes gravity. The leading gravitational action is Einstein-Hilbert with negative cosmological constant:

$$
S_{\rm grav}=\frac{1}{16\pi G_N}\int d^{d+1}X\sqrt g\,(R-2\Lambda_{\rm cos}).
$$

Higher-derivative gravitational terms include curvature-squared and curvature-cubed terms:

$$
\int \sqrt g\,\left(a R^2+b R_{MN}R^{MN}+c R_{MNRS}R^{MNRS}+\cdots\right).
$$

Not all of these are independent because of field redefinitions and topological terms. Their observable effects appear in stress-tensor correlators, conformal collider data, Regge behavior, and graviton scattering in AdS.

Causality and positivity strongly constrain such corrections. Large higher-derivative gravitational interactions often require new higher-spin states below the scale where the EFT would otherwise misbehave.

## Validity and breakdown

AdS EFT breaks down when one leaves its regime of validity. Common breakdown mechanisms include:

| Breakdown mechanism | CFT signal |
|---|---|
| finite cutoff | heavy single-trace operators become important |
| strong curvature or high energy | high-dimension states and black holes enter |
| finite $N$ | bulk loops and nonperturbative effects matter |
| small higher-spin gap | stringy or higher-spin physics appears early |
| poor Regge behavior | causality or inversion assumptions fail |
| large operator mixing | simple particle interpretation becomes unreliable |

This is normal. EFT is not supposed to describe everything. It is supposed to describe a controlled regime better than a full microscopic theory would let us see directly.

## Common pitfalls

**Do not treat the AdS EFT as the exact theory.** It is a low-energy, large-$N$ approximation.

**Do not forget the cutoff.** Higher-derivative terms are meaningful only relative to a scale such as $\Delta_{\rm gap}$.

**Do not identify all Lagrangian coefficients as observables.** Field redefinitions and integration by parts create redundancies.

**Do not ignore contact ambiguities.** Exchange diagrams and loop reconstructions are defined modulo local terms.

**Do not assume large $C_T$ means high cutoff.** Weak gravity and high string scale are different conditions.

**Do not extrapolate low-energy EFT through the black-hole regime.** High-energy holographic states are not described by a few-particle EFT.

**Do not quote Mellin polynomial degree without conventions.** Mellin variables and Gamma factors differ across references.

## Relations to other pages

This page follows [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/) and prepares [Mellin Amplitudes and Flat-Space Limits](/cft-bootstrap/holographic-cft/mellin-amplitudes-and-flat-space-limits/) and [Stress Tensor, Graviton, and Causality](/cft-bootstrap/holographic-cft/stress-tensor-graviton-and-causality/).

It connects back to [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/), [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/), and [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/).

For general EFT background, see the broader QFT.org chapters on renormalization and effective field theory when available.

## Research status

AdS EFT is an established framework for holographic CFTs with large central charge, sparse spectra, and large higher-spin gaps. Tree-level contact and exchange Witten diagrams and their Mellin-space descriptions are standard tools.

Active research focuses on loop-level reconstruction, contact ambiguities, causality and positivity bounds, finite-$N$ effects, black-hole thresholds, stringy corrections, and quantitative bootstrap constraints on EFT coefficients and gaps.

## Exercises

### Exercise 1

What CFT quantity plays the role of the AdS EFT cutoff?

<details><summary><strong>Solution</strong></summary>

The cutoff is related to the dimension gap to heavy single-trace states:

$$
\Lambda R_{\rm AdS}\sim \Delta_{\rm gap}.
$$

A large gap means there is a wide energy range in which a local bulk EFT is valid.

</details>

### Exercise 2

Why do higher-derivative terms correspond to higher-degree Mellin polynomials?

<details><summary><strong>Solution</strong></summary>

Derivatives in AdS interactions translate into powers of Mellin variables. A non-derivative contact term gives a constant Mellin amplitude, while additional derivatives produce higher powers of $s,t,u_M$. Thus the polynomial degree tracks derivative order.

</details>

### Exercise 3

What is the CFT interpretation of a double-trace anomalous dimension?

<details><summary><strong>Solution</strong></summary>

For a double-trace operator,

$$
\Delta_{n,\ell}=\Delta_{n,\ell}^{(0)}+\gamma_{n,\ell},
$$

where $\Delta_{n,\ell}^{(0)}$ is the additive two-particle dimension. The anomalous dimension $\gamma_{n,\ell}$ is the CFT encoding of the interaction energy of the corresponding two-particle AdS state.

</details>

### Exercise 4

Why are field redefinitions important in AdS EFT?

<details><summary><strong>Solution</strong></summary>

Field redefinitions can move terms between different operators in the bulk Lagrangian without changing physical CFT correlators. Therefore individual Lagrangian coefficients may be basis-dependent. Observable quantities are CFT data such as dimensions, OPE coefficients, correlators, and invariant combinations of EFT coefficients.

</details>

### Exercise 5

Name two ways AdS EFT can break down.

<details><summary><strong>Solution</strong></summary>

Examples include reaching the gap scale where heavy single-trace states become important, going to high energies where black-hole states dominate, losing the large-$N$ expansion, having a small higher-spin gap, or encountering Regge behavior incompatible with the assumed low-energy EFT.

</details>

## References

- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, “Holography from conformal field theory,” *Journal of High Energy Physics* **2009**.
- A. L. Fitzpatrick, J. Kaplan, J. Penedones, S. Raju, and B. C. van Rees, “A natural language for AdS/CFT correlators,” *Journal of High Energy Physics* **2011**.
- J. Penedones, “Writing CFT correlation functions as AdS scattering amplitudes,” *Journal of High Energy Physics* **2011**.
- X. O. Camanho, J. D. Edelstein, J. Maldacena, and A. Zhiboedov, “Causality constraints on corrections to the graviton three-point coupling,” *Journal of High Energy Physics* **2016**.
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- D. Meltzer, E. Perlmutter, and A. Sivaramakrishnan, “Unitarity methods in AdS/CFT,” *Journal of High Energy Physics* **2020**.
- C. P. Burgess, *Introduction to Effective Field Theory*, Cambridge University Press, 2020.

## Version history

- 2026-07-01: First polished draft. Added AdS EFT action, derivative expansion, contact and exchange interactions, integrating out heavy fields, field redefinitions, power counting, loops and counterterms, gravitational EFT, validity caveats, exercises, and references.
