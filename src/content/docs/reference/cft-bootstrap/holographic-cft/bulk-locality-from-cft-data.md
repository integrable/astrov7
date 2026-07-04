---
title: "Bulk Locality from CFT Data"
description: "How large central charge, sparse spectra, higher-spin gaps, Mellin growth, Regge behavior, and crossing constraints encode the emergence of local AdS effective field theory."
sidebar:
  label: "Bulk Locality from CFT Data"
  order: 4
level: Advanced
status: "Polished draft"
source: "Heemskerk, Penedones, Polchinski, and Sully; Fitzpatrick, Kaplan, Penedones, Raju, and van Rees; Maldacena and Zhiboedov; Camanho et al.; holographic bootstrap literature."
topics:
  - bulk locality
  - holographic CFT
  - AdS/CFT
  - large-N CFT
  - higher-spin gap
canonicalTopics:
  - bulk-locality-from-cft-data
  - cft-criteria-for-ads-locality
  - holographic-sparseness
researchStatus:
  established:
    - "Large central charge plus sparse low-dimension single-trace data and a higher-spin gap are central conditions for an approximate local AdS effective field theory description."
  active:
    - "Current research seeks sharper CFT criteria for locality, finite-N corrections, Regge bounds, stringy corrections, higher-spin gaps, black-hole thresholds, and bootstrap constraints on quantum gravity."
---

## Summary

**Bulk locality from CFT data** asks when a conformal field theory behaves as if it has a local gravitational theory in one higher-dimensional anti-de Sitter spacetime.

The answer is not just “large $N$.” Large $N$ gives factorization and weak connected correlators. Local Einstein-like bulk physics also needs a sparse spectrum of light single-trace operators, a large gap to higher-spin single-trace operators, controlled Mellin growth, acceptable Regge behavior, and crossing-compatible correlators.

A useful slogan is

$$
\text{large }C_T
+\text{sparse low spectrum}
+\text{higher-spin gap}
+\text{Regge control}
\quad\Rightarrow\quad
\text{approximate local AdS EFT}.
$$

This is not a one-line theorem. The precise statement depends on the CFT dimension, the operator sector, supersymmetry, the energy range, and the desired accuracy.

The central idea is that locality is encoded in CFT dimensions, OPE coefficients, correlator growth, and crossing symmetry. The bulk is not extra data; it is an emergent description of special CFT data.

## Prerequisites

Read [AdS/CFT Dictionary](/cft-bootstrap/holographic-cft/ads-cft-dictionary/), [Large-N and Factorization](/cft-bootstrap/holographic-cft/large-n-and-factorization/), [Witten Diagrams](/cft-bootstrap/holographic-cft/witten-diagrams/), [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/), and [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/) first.

You should know single-trace and double-trace operators, generalized free fields, Witten diagrams, Mellin amplitudes, conformal blocks, and large-spin anomalous dimensions.

## Core idea

A local bulk theory has a limited number of light fields and interactions organized by a derivative expansion. In CFT language, that means:

- few light single-trace primaries;
- double-trace towers behaving like multi-particle states;
- connected correlators suppressed by powers of $1/N$ or $1/C_T$;
- Mellin amplitudes with controlled polynomial growth;
- Regge behavior compatible with Lorentzian consistency;
- higher-spin single-trace operators appearing only above a large gap.

The conceptual chain is

$$
\text{CFT spectrum and OPE data}
\quad\to\quad
\text{large-}N\text{ correlators}
\quad\to\quad
\text{Mellin and Regge behavior}
\quad\to\quad
\text{local AdS EFT}.
$$

The CFT does not contain a fundamental bulk point. Bulk locality emerges as an approximate organizing principle for a special class of CFTs.

## What locality means in AdS

Bulk locality means that low-energy bulk physics can be described by an effective action of fields on AdS:

$$
S_{\rm EFT}=\int_{\rm AdS} d^{d+1}X\sqrt g\,
\left[\mathcal L_{\rm two\ derivatives}+\frac{1}{\Lambda^2}\mathcal L_{4\,\rm derivatives}+\cdots\right].
$$

The cutoff scale $\Lambda$ is where new stringy, higher-spin, or quantum-gravity degrees of freedom become important. In CFT units, this cutoff is related to a dimension gap:

$$
\Delta_{\rm gap}\sim \Lambda R_{\rm AdS}.
$$

If

$$
\Delta_{\rm gap}\gg1,
$$

then there is a wide energy window in AdS units where a local low-energy bulk EFT makes sense.

Locality is therefore approximate. It holds below a cutoff, in a suitable sector of states, and at sufficiently large $N$.

## Large central charge

The stress-tensor two-point coefficient $C_T$ controls the strength of bulk gravity:

$$
C_T\sim \frac{R_{\rm AdS}^{d-1}}{G_N}
$$

up to conventions. Large $C_T$ means

$$
G_N/R_{\rm AdS}^{d-1}\ll1,
$$

so bulk gravitational loops are suppressed.

But large $C_T$ is not enough. It only says that the gravitational coupling is small. One also needs a spectrum and OPE data consistent with a small number of low-energy bulk fields.

A vector model can have large $C_T$ and factorization while being better described by a higher-spin theory than by Einstein gravity. The spectrum decides the kind of bulk.

## Sparse low spectrum

A sparse low spectrum means that below some large dimension $\Delta_{\rm gap}$ there are only a few single-trace primaries. These light primaries correspond to light bulk fields.

The low-energy AdS EFT contains those fields. Heavier single-trace states are integrated out and contribute higher-derivative interactions suppressed by powers of

$$
\Delta_{\rm gap}^{-1}.
$$

The sparse-spectrum principle is

$$
\text{few light single traces}
\quad\Longleftrightarrow\quad
\text{few light bulk fields}.
$$

Without sparseness, the bulk can contain many light fields. It may still be holographic, but it is not the simple Einstein-like EFT one usually has in mind.

## Higher-spin gap

A particularly important condition is a large gap to single-trace operators with spin greater than two:

$$
\Delta_{\rm gap}^{\rm HS}\gg1.
$$

The stress tensor is the spin-two operator dual to the graviton. Conserved currents are spin-one operators dual to gauge fields. Additional light higher-spin single-trace operators signal extra high-spin bulk fields.

| CFT spectrum | Bulk interpretation |
|---|---|
| only expected low-spin light fields | Einstein-like EFT possible |
| many light higher-spin currents | higher-spin-like theory |
| large but finite higher-spin gap | stringy corrections are suppressed |
| no higher-spin gap | no simple Einstein-like low-energy regime |

Thus the higher-spin gap is one of the sharpest CFT diagnostics of bulk locality.

## Double-trace towers

Large-$N$ factorization produces double-trace operators

$$
[\mathcal O_1\mathcal O_2]_{n,\ell}
$$

with leading dimensions

$$
\Delta_{n,\ell}^{(0)}=\Delta_1+\Delta_2+2n+\ell.
$$

In AdS, these are two-particle states. Their anomalous dimensions are interaction energies:

$$
\gamma_{n,\ell}=\Delta_{n,\ell}-\Delta_{n,\ell}^{(0)}.
$$

A local bulk EFT predicts organized anomalous dimensions. Exchange of a light field gives large-spin tails controlled by the exchanged twist:

$$
\gamma_{n,\ell}^{(X)}\sim J^{-\tau_X}.
$$

Contact interactions give patterns associated with polynomial Mellin amplitudes. If the double-trace spectrum does not resemble weakly interacting multi-particle states, the simple bulk interpretation fails.

## Mellin growth and locality

Mellin amplitudes make locality visible. A contact interaction with finitely many derivatives gives a polynomial Mellin amplitude. For example,

$$
M_{\rm contact}(s,t)=c_0+c_1(s^2+t^2+u_M^2)+\cdots .
$$

The degree of the polynomial is related to the number of derivatives in the bulk interaction. If the Mellin amplitude grows too rapidly, the low-energy local EFT description has broken down or is missing degrees of freedom.

The rough dictionary is:

| Mellin behavior | Bulk interpretation |
|---|---|
| constant | non-derivative contact interaction |
| low-degree polynomial | finite-derivative local interaction |
| meromorphic poles | exchange of bulk fields |
| controlled high-energy growth | local EFT below a cutoff |
| uncontrolled growth | no simple local low-energy description |

This is why Mellin-space bootstrap is so useful for holographic CFTs.

## Regge behavior

Lorentzian Regge behavior constrains holographic locality. In the CFT, the Regge limit probes high-energy, large-boost behavior of correlators on a Lorentzian sheet. In the bulk, it is related to high-energy scattering in AdS.

A good local bulk EFT should have Regge behavior compatible with Lorentzian consistency. Higher-derivative terms cannot be chosen arbitrarily; their coefficients are constrained by the requirement that correlators have acceptable analytic behavior.

This principle ties together:

- higher-spin gaps;
- stress-tensor three-point data;
- conformal collider bounds;
- Mellin growth;
- validity of Lorentzian inversion;
- suppression of higher-derivative interactions.

Regge behavior is therefore not a decorative asymptotic limit. It is one of the places where locality is tested.

## Contact terms and EFT coefficients

Integrating out heavy bulk fields produces local contact interactions among light fields. In CFT language, these are crossing-symmetric deformations of generalized free field data.

A higher-derivative contact term is suppressed by powers of a cutoff:

$$
\mathcal L_{\rm EFT}\supset \frac{1}{\Lambda^k}\mathcal O_{\rm higher\ derivative}.
$$

Since

$$
\Lambda R_{\rm AdS}\sim \Delta_{\rm gap},
$$

one expects coefficients suppressed by powers of $\Delta_{\rm gap}^{-1}$.

This gives a quantitative version of locality: the larger the gap, the more suppressed higher-derivative interactions should be.

## Crossing as the consistency engine

A proposed local AdS interaction is not acceptable merely because it looks local. It must produce a CFT correlator compatible with crossing, unitarity, OPE positivity, and Lorentzian behavior.

The bootstrap logic is

$$
\text{write possible AdS interactions}
\quad\to\quad
\text{compute or parametrize CFT correlators}
\quad\to\quad
\text{impose crossing and positivity}
\quad\to\quad
\text{constrain bulk locality}.
$$

This is why holographic CFT is more than bulk perturbation theory. The boundary CFT supplies the nonperturbative consistency conditions.

## Approximate locality

Bulk locality is approximate even in excellent holographic CFTs. At finite $N$, gravitational constraints and gauge redundancies prevent naive exact local bulk observables from being fundamental.

Instead, bulk fields are reconstructed in appropriate sectors of states around a semiclassical background. Within such a sector, local EFT works to a controlled accuracy.

The CFT encodes the approximation through:

- large but finite $C_T$;
- suppressed but nonzero connected correlators;
- finite higher-spin gap;
- multi-trace mixing at higher orders;
- high-energy states beyond the EFT regime;
- nonperturbative effects invisible in finite-order $1/N$ expansions.

So “bulk locality” always means locality in a regime. It is not a microscopic axiom of the CFT.

## Practical diagnostics

To test whether a CFT has a local AdS EFT regime, examine:

| Diagnostic | Local-bulk expectation |
|---|---|
| $C_T$ | large |
| connected single-trace correlators | suppressed |
| low single-trace spectrum | sparse |
| higher-spin single-trace gap | large |
| double-trace dimensions | near additive at large $N$ |
| double-trace anomalous dimensions | structured by exchange and contact terms |
| Mellin amplitude | meromorphic with controlled polynomial growth |
| Regge behavior | controlled |
| stress-tensor couplings | compatible with collider and causality constraints |
| high-energy density | consistent with gravitational thermodynamics in the right regime |

No single diagnostic is enough. Locality is an emergent pattern across many pieces of CFT data.

## Common pitfalls

**Do not say large $N$ implies local Einstein gravity.** It implies factorization, not necessarily a sparse low-spin spectrum.

**Do not ignore higher-spin operators.** A small higher-spin gap changes the bulk interpretation.

**Do not treat Mellin polynomial growth as optional.** It encodes locality and derivative counting.

**Do not forget Regge behavior.** It controls Lorentzian consistency and inversion thresholds.

**Do not assume bulk locality is exact at finite $N$.** It is approximate and sector-dependent.

**Do not identify all double-trace data with free particles.** Anomalous dimensions and mixing encode interactions.

**Do not confuse sparse low spectrum with no heavy states.** Holographic CFTs still contain high-energy states beyond the EFT window.

## Relations to other pages

This page follows [Witten Diagrams](/cft-bootstrap/holographic-cft/witten-diagrams/) and prepares [AdS Effective Field Theory](/cft-bootstrap/holographic-cft/ads-effective-field-theory/) and [Mellin Amplitudes and Flat-Space Limits](/cft-bootstrap/holographic-cft/mellin-amplitudes-and-flat-space-limits/).

It connects to [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/), [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/), [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/), and [Analytic-Numerical Bridges](/cft-bootstrap/analytic-bootstrap/analytic-numerical-bridges/).

For later constraints, see [Bootstrap Constraints on Holography](/cft-bootstrap/holographic-cft/bootstrap-constraints-on-holography/) once available.

## Research status

The broad conditions for semiclassical local AdS physics are well established: large central charge, large-$N$ factorization, sparse light single-trace spectrum, higher-spin gap, controlled Mellin growth, and Regge behavior.

Active research seeks sharper quantitative criteria: how large the gap must be, how EFT coefficients scale with it, how high-energy states enter, how locality emerges from entanglement and quantum error correction, and how numerical bootstrap can test holographic locality at finite central charge.

## Exercises

### Exercise 1

Why is large $N$ not enough to guarantee Einstein-like bulk locality?

<details><summary><strong>Solution</strong></summary>

Large $N$ gives factorization and weak connected correlators. But an Einstein-like local bulk also requires a sparse light spectrum and a large gap to higher-spin single-trace operators. Without that gap, the bulk may contain many light higher-spin fields.

</details>

### Exercise 2

What CFT quantity controls the bulk Newton coupling?

<details><summary><strong>Solution</strong></summary>

The stress-tensor two-point normalization $C_T$ controls the bulk Newton coupling:

$$
C_T\sim \frac{R_{\rm AdS}^{d-1}}{G_N}
$$

up to conventions. Large $C_T$ means weak bulk gravity in AdS units.

</details>

### Exercise 3

What does a large higher-spin gap mean in CFT language?

<details><summary><strong>Solution</strong></summary>

It means that single-trace operators with spin greater than two have large dimensions:

$$
\Delta_{\rm gap}^{\rm HS}\gg1.
$$

This suppresses light higher-spin bulk fields and allows an Einstein-like low-energy AdS effective theory.

</details>

### Exercise 4

How does Mellin-space polynomial growth encode locality?

<details><summary><strong>Solution</strong></summary>

A local AdS contact interaction with finitely many derivatives gives a polynomial Mellin amplitude. The degree of the polynomial is related to the number of derivatives. Controlled polynomial growth at large Mellin variables indicates a local derivative expansion below a cutoff.

</details>

### Exercise 5

Why are double-trace anomalous dimensions useful diagnostics of bulk interactions?

<details><summary><strong>Solution</strong></summary>

Double-trace operators represent two-particle AdS states. Their leading dimensions are additive. Interactions shift these dimensions by anomalous dimensions:

$$
\gamma_{n,\ell}=\Delta_{n,\ell}-\Delta_{n,\ell}^{(0)}.
$$

The pattern of these shifts reveals whether the interaction looks like exchange of light fields, local contact terms, or something less local.

</details>

## References

- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, “Holography from conformal field theory,” *Journal of High Energy Physics* **2009**.
- A. L. Fitzpatrick, J. Kaplan, J. Penedones, S. Raju, and B. C. van Rees, “A natural language for AdS/CFT correlators,” *Journal of High Energy Physics* **2011**.
- J. Maldacena and A. Zhiboedov, “Constraining conformal field theories with a higher spin symmetry,” *Journal of Physics A* **46** (2013).
- X. O. Camanho, J. D. Edelstein, J. Maldacena, and A. Zhiboedov, “Causality constraints on corrections to the graviton three-point coupling,” *Journal of High Energy Physics* **2016**.
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- D. Meltzer, E. Perlmutter, and A. Sivaramakrishnan, “Unitarity methods in AdS/CFT,” *Journal of High Energy Physics* **2020**.

## Version history

- 2026-07-01: First polished draft. Added criteria for bulk locality from CFT data, large-$C_T$ and sparseness discussion, higher-spin-gap diagnostics, Mellin-growth and Regge conditions, contact-term scaling, approximate-locality caveats, practical diagnostics, exercises, and references.
