---
title: "Stringy Corrections and Higher-Spin Gaps"
description: "How finite string scale, higher-spin single-trace operators, Regge behavior, and gap-suppressed corrections control the departure from Einstein-like AdS effective field theory."
sidebar:
  label: "Stringy Corrections and Higher-Spin Gaps"
  order: 11
level: Advanced
status: "Polished draft"
source: "Maldacena and Zhiboedov; Heemskerk et al.; Fitzpatrick et al.; Camanho et al.; Caron-Huot; holographic bootstrap and stringy AdS literature."
topics:
  - stringy corrections
  - higher-spin gap
  - holographic CFT
  - AdS effective field theory
  - Regge behavior
canonicalTopics:
  - stringy-corrections-and-higher-spin-gaps
  - higher-spin-gap
  - stringy-holography
researchStatus:
  established:
    - "Large central charge and a large higher-spin gap are central diagnostics of an Einstein-like AdS effective field theory regime."
    - "Finite higher-spin gaps generate stringy or higher-derivative corrections to holographic CFT correlators."
  active:
    - "Current research seeks quantitative bounds relating higher-spin gaps, Regge behavior, EFT coefficients, chaos, Mellin growth, and numerical bootstrap constraints."
---

## Summary

A holographic CFT can look gravitational at low energies but stringy at higher energies. The diagnostic is the **higher-spin gap**: the dimension scale where single-trace operators with spin greater than two first appear.

A simple Einstein-like bulk requires

$$
C_T \gg 1,
\qquad
\Delta_{\rm gap}^{\rm HS}\gg 1.
$$

Here $C_T$ suppresses bulk gravitational loops, while $\Delta_{\rm gap}^{\rm HS}$ suppresses stringy or higher-spin corrections. The first condition says gravity is weak. The second says the bulk has a wide low-energy regime containing only a small number of light fields.

When the gap is large but finite, the bulk is not exactly Einstein gravity. Heavy stringy or higher-spin states leave fingerprints in CFT data:

- higher-derivative corrections to Witten diagrams;
- polynomial corrections to Mellin amplitudes;
- modified Regge behavior;
- deviations from maximal chaos;
- gap-suppressed corrections to stress-tensor correlators;
- anomalous dimensions of double-trace operators with distinctive large-$n$ and large-spin behavior.

The slogan is

$$
\text{large gap}=\text{local gravity window},
\qquad
\text{finite gap}=\text{stringy corrections waiting upstairs}.
$$

This page explains what the higher-spin gap is, why it matters, and how CFT data reveal stringy corrections without ever drawing a fundamental string in the boundary theory.

## Prerequisites

Read [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/), [AdS Effective Field Theory](/cft-bootstrap/holographic-cft/ads-effective-field-theory/), [Mellin Amplitudes and Flat-Space Limits](/cft-bootstrap/holographic-cft/mellin-amplitudes-and-flat-space-limits/), and [Stress Tensor, Graviton, and Causality](/cft-bootstrap/holographic-cft/stress-tensor-graviton-and-causality/) first.

You should know large-$N$ factorization, single-trace and double-trace operators, Witten diagrams, Mellin amplitudes, Regge limits, and the stress-tensor/graviton dictionary.

## Core idea

A local AdS effective field theory is valid below a cutoff. In CFT language, that cutoff is a dimension gap:

$$
\Lambda R_{\rm AdS}\sim \Delta_{\rm gap}.
$$

For gravitational locality, the most important gap is the gap to higher-spin single-trace operators:

$$
\Delta_{\rm gap}^{\rm HS}.
$$

If this gap is large, then low-energy correlators can be described by gravity plus a small number of low-spin fields. If it is small, the bulk contains light higher-spin or stringy degrees of freedom, and Einstein gravity is not the right low-energy description.

The conceptual chain is

$$
\text{CFT spectrum}
\longrightarrow
\text{gap to higher-spin single traces}
\longrightarrow
\text{Regge behavior}
\longrightarrow
\text{bulk locality and string scale}.
$$

This is the heart of the holographic bootstrap approach to stringy corrections.

## What counts as higher spin

The stress tensor has spin two and is always present in a local CFT:

$$
\Delta_T=d,
\qquad
\ell_T=2.
$$

Conserved currents have spin one and correspond to bulk gauge fields. Scalars and low-spin matter fields can also be light.

A **higher-spin single-trace operator** usually means a single-trace primary with

$$
\ell>2.
$$

In an Einstein-like holographic CFT, such operators should be heavy:

$$
\Delta_{\ell>2}^{\rm single\ trace}\ge \Delta_{\rm gap}^{\rm HS}.
$$

The word single-trace is essential. Double-trace operators with high spin are unavoidable; they are multi-particle states. The dangerous objects for simple gravity are light high-spin single-particle fields.

The distinction is:

| Operator | Bulk meaning | Allowed to be light in Einstein-like EFT? |
|---|---|---|
| stress tensor | graviton | yes |
| conserved current | gauge field | yes |
| scalar single trace | matter field | yes |
| high-spin double trace | multi-particle state | yes |
| high-spin single trace | stringy or higher-spin particle | only above a gap |

## String scale and gap

In a stringy AdS compactification, the first massive string states have mass roughly

$$
M_s\sim \frac{1}{\ell_s}.
$$

In AdS units this becomes a CFT dimension scale

$$
\Delta_{\rm string}\sim M_s R_{\rm AdS}\sim \frac{R_{\rm AdS}}{\ell_s}.
$$

This scale is a higher-spin gap because massive string excitations include many higher-spin states. A large string scale in AdS units means

$$
\frac{R_{\rm AdS}}{\ell_s}\gg1.
$$

Then the bulk has a wide energy range where ordinary low-derivative gravity is useful.

When the string scale is finite, stringy corrections appear as powers of

$$
\frac{1}{\Delta_{\rm gap}^{\rm HS}}.
$$

The exact power depends on the interaction. The robust message is that higher-derivative corrections are not arbitrary; their size is tied to the gap where new states enter.

## Higher-derivative corrections

Integrating out heavy stringy states produces higher-derivative terms in the AdS effective action. A schematic gravitational EFT contains

$$
S=\int d^{d+1}X\sqrt g\,\left[R-2\Lambda_{\rm cos}+a_2R^2+a_3R^3+\cdots\right].
$$

The coefficients are suppressed by powers of the heavy scale:

$$
a_k\sim \left(\Delta_{\rm gap}^{\rm HS}\right)^{-p_k}
$$

in appropriate AdS units.

These terms affect CFT observables such as:

- stress-tensor three-point functions;
- stress-tensor four-point functions;
- conformal collider data;
- Regge growth;
- graviton scattering in AdS;
- double-trace anomalous dimensions.

The larger the higher-spin gap, the smaller these corrections should be.

## Mellin-space signatures

Mellin amplitudes make the stringy expansion visible. Local contact interactions with finitely many derivatives give polynomial Mellin amplitudes. Stringy physics adds new poles, softer Regge behavior, and an infinite tower of massive states.

A useful dictionary is:

| Mellin feature | Bulk interpretation |
|---|---|
| low-degree polynomial | low-derivative contact term |
| high-degree polynomial | higher-derivative EFT correction |
| poles from light single traces | exchange of light bulk fields |
| many high-spin poles above a gap | stringy spectrum |
| softened Regge growth | Reggeization by string states |
| uncontrolled growth | EFT used beyond its range |

At low Mellin variables compared with the gap, stringy states can be integrated out. At Mellin variables near the gap, the EFT expansion breaks down and the stringy tower must be treated explicitly.

## Regge behavior

The Regge limit is one of the sharpest diagnostics of stringy corrections. Einstein gravity has strong spin-two exchange. A stringy theory softens high-energy behavior by replacing a single graviton exchange with a Regge trajectory.

In CFT language, the leading Regge behavior is controlled by an effective intercept

$$
J_0.
$$

Einstein gravity gives behavior associated with spin two. Finite string scale lowers and smooths the effective intercept in a way controlled by the gap.

This matters because excessive Regge growth can violate causality or invalidate unsubtracted inversion formulas. The higher-spin gap and Regge behavior are therefore linked:

$$
\text{large gap}\longrightarrow \text{Einstein-like Regge window},
\qquad
\text{finite gap}\longrightarrow \text{stringy Regge corrections}.
$$

Regge behavior is not a fancy asymptotic hobby. It is where the bulk theory proves whether it can be causal.

## Causality constraints

Higher-derivative gravitational terms can modify high-energy scattering in AdS. If such terms are too large, they can produce time advances or bad polarization-dependent propagation.

The lesson from holographic causality is:

$$
\text{large higher-derivative correction}
\quad\Rightarrow\quad
\text{new higher-spin states cannot be too far away}.
$$

In CFT terms, this becomes a constraint on stress-tensor correlators and the higher-spin gap. If a CFT has a very large higher-spin gap, its stress-tensor data must be close to the Einstein-gravity values.

This is why the phrase **Einstein gravity from CFT** always hides several assumptions:

- large $C_T$;
- sparse low single-trace spectrum;
- large higher-spin gap;
- stress-tensor data close to the Einstein point;
- acceptable Regge behavior.

Skip any one of these and the bulk can become stringy, higher-spin-like, or nonlocal.

## Large-spin double traces

Stringy corrections also show up in double-trace data. For two single-trace scalars,

$$
[\mathcal O_1\mathcal O_2]_{n,\ell}
$$

has leading dimension

$$
\Delta_{n,\ell}^{(0)}=\Delta_1+\Delta_2+2n+\ell.
$$

Interactions shift it by

$$
\gamma_{n,\ell}=\Delta_{n,\ell}-\Delta_{n,\ell}^{(0)}.
$$

At fixed $n$ and large spin, low-twist exchange controls the tail. At large $n$, the two-particle state probes higher bulk energies. If $n$ approaches the gap scale, stringy corrections become important.

Thus the same double-trace family contains several regimes:

| Regime | Bulk meaning |
|---|---|
| fixed $n$, large $\ell$ | long-distance force in AdS |
| large $n$ below gap | high-energy EFT scattering |
| $n$ near gap | stringy or higher-spin states enter |
| very high energy | black-hole physics may dominate |

A local EFT should not be trusted through all regimes. The double-trace spectrum kindly tells you when your approximation is getting cocky.

## Vector models versus stringy holography

Large $N$ does not guarantee a large higher-spin gap. Vector models often have many approximately conserved higher-spin currents. These are dual to higher-spin theories rather than Einstein gravity.

The contrast is useful:

| CFT type | Higher-spin spectrum | Bulk tendency |
|---|---|---|
| matrix large $N$ with sparse spectrum | large gap | Einstein-like or stringy gravity |
| vector large $N$ | many light high-spin currents | higher-spin theory |
| free CFT | conserved higher-spin tower | no Einstein-like local gravity |
| strongly coupled holographic CFT | high-spin states heavy | local gravity window |

Stringy holography is not the same as higher-spin holography. In stringy holography, high-spin states exist but are heavy compared with the AdS scale. In higher-spin theories, high-spin fields remain light.

## Bootstrap diagnostics

The higher-spin gap can be studied through several bootstrap diagnostics:

| Diagnostic | What it tests |
|---|---|
| stress-tensor three-point data | higher-derivative gravity corrections |
| conformal collider bounds | positivity and causality |
| Regge behavior | high-energy consistency |
| Mellin growth | local EFT and string scale |
| double-trace anomalous dimensions | bulk forces and contact interactions |
| numerical gaps in spin sectors | candidate holographic sparseness |
| Lorentzian inversion | spin trajectories and large-spin tails |
| chaos exponents | gravitational versus stringy Regge behavior |

No single diagnostic proves a full string theory. Together, they reveal whether the CFT data look like weakly curved gravity below a string scale.

## Common pitfalls

**Do not confuse high-spin double traces with high-spin single traces.** Double traces are multi-particle states and are always present. The higher-spin gap concerns single-trace operators.

**Do not say large $N$ implies Einstein gravity.** Large $N$ gives weak coupling. The higher-spin gap decides whether the weakly coupled bulk is Einstein-like, stringy, or higher-spin-like.

**Do not take the infinite-gap limit literally.** Quantum gravity is expected to have new states. Infinite gap is an approximation, not a complete UV theory.

**Do not treat higher-derivative coefficients as arbitrary.** Causality and Regge behavior constrain them.

**Do not ignore large-$n$ double traces.** They probe high-energy AdS scattering and can leave the EFT window.

**Do not assume stringy corrections are always small.** They are small only below the gap and when the gap is large.

**Do not use flat-space intuition without AdS translation.** Dimensions, Mellin variables, and global AdS energies must be scaled carefully.

## Relations to other pages

This page follows [Quantum Error Correction and Entanglement Wedges](/cft-bootstrap/holographic-cft/quantum-error-correction-and-entanglement-wedges/) in the chapter sequence and builds on [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/), [AdS Effective Field Theory](/cft-bootstrap/holographic-cft/ads-effective-field-theory/), and [Mellin Amplitudes and Flat-Space Limits](/cft-bootstrap/holographic-cft/mellin-amplitudes-and-flat-space-limits/).

It prepares [Bootstrap Constraints on Holography](/cft-bootstrap/holographic-cft/bootstrap-constraints-on-holography/), where the gap, Regge behavior, and positivity become constraints on possible quantum gravities.

For analytic tools, see [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/), [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/), and [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/).

## Research status

The role of the higher-spin gap as a diagnostic of local Einstein-like holography is established. Large-gap expansions, Mellin amplitudes, and Regge causality are standard tools for understanding stringy corrections to AdS EFT.

Active research seeks sharper quantitative inequalities relating the higher-spin gap to stress-tensor data, gravitational EFT coefficients, chaos, flat-space limits, numerical bootstrap bounds, and the onset of black-hole physics.

## Exercises

### Exercise 1

What is the difference between a high-spin double-trace operator and a high-spin single-trace operator?

<details><summary><strong>Solution</strong></summary>

A high-spin double-trace operator is a multi-particle state, such as $[\mathcal O_1\mathcal O_2]_{n,\ell}$ with large $\ell$. Such operators are forced by large-$N$ factorization and crossing. A high-spin single-trace operator is a one-particle bulk field with spin greater than two. A large gap to high-spin single traces is needed for an Einstein-like low-energy bulk.

</details>

### Exercise 2

Why does a large higher-spin gap support a local AdS EFT?

<details><summary><strong>Solution</strong></summary>

If higher-spin single-trace operators are heavy, then the low-energy bulk contains only the graviton and a small number of low-spin fields. Heavy stringy or higher-spin states can be integrated out, producing higher-derivative interactions suppressed by powers of the gap. This gives a local derivative expansion below the cutoff.

</details>

### Exercise 3

How do stringy corrections appear in Mellin space?

<details><summary><strong>Solution</strong></summary>

At low energies, integrating out stringy states produces higher-degree polynomial Mellin terms. Near the string scale, new poles and Regge behavior from the string tower appear. Thus Mellin amplitudes show both EFT contact corrections and the onset of explicit stringy states.

</details>

### Exercise 4

Why does causality constrain higher-derivative gravity?

<details><summary><strong>Solution</strong></summary>

Higher-derivative gravitational terms can modify high-energy scattering and produce time advances or bad Regge growth. A causal UV completion must avoid these pathologies, often by introducing new higher-spin or stringy states below the dangerous scale. In CFT language, stress-tensor correlators and the higher-spin gap are constrained.

</details>

### Exercise 5

What happens when large-$n$ double-trace states approach the gap scale?

<details><summary><strong>Solution</strong></summary>

Large $n$ corresponds to high-energy two-particle states in AdS. When this energy approaches the gap, the low-energy EFT can no longer be trusted. Heavy stringy or higher-spin single-trace states become important, and the double-trace anomalous dimensions receive corrections not captured by the low-derivative EFT alone.

</details>

## References

- J. Maldacena and A. Zhiboedov, “Constraining conformal field theories with a higher spin symmetry,” *Journal of Physics A* **46** (2013).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, “Holography from conformal field theory,” *Journal of High Energy Physics* **2009**.
- A. L. Fitzpatrick, J. Kaplan, J. Penedones, S. Raju, and B. C. van Rees, “A natural language for AdS/CFT correlators,” *Journal of High Energy Physics* **2011**.
- X. O. Camanho, J. D. Edelstein, J. Maldacena, and A. Zhiboedov, “Causality constraints on corrections to the graviton three-point coupling,” *Journal of High Energy Physics* **2016**.
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- D. Meltzer, E. Perlmutter, and A. Sivaramakrishnan, “Unitarity methods in AdS/CFT,” *Journal of High Energy Physics* **2020**.

## Version history

- 2026-07-02: First polished draft. Added higher-spin-gap definition, string-scale dictionary, EFT and Mellin signatures, Regge and causality constraints, large-spin and large-$n$ double-trace diagnostics, vector-model contrast, exercises, and references.
