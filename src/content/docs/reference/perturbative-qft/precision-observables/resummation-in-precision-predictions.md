---
title: "Resummation in Precision Predictions"
description: "How large logarithms are organized, resummed, matched to fixed order, and validated in precision perturbative QFT predictions."
sidebar:
  label: "Resummation in Precision"
  order: 7
level: Advanced
status: "Polished draft"
source: "Collins–Soper–Sterman; Sterman; Catani–Trentadue; Banfi–Salam–Zanderighi; Becher–Neubert; Schwartz 2014, chs. 20, 32, and 36."
topics:
  - precision observables
  - resummation
  - large logarithms
  - factorization
  - QCD
  - SCET
canonicalTopics:
  - resummation-in-precision-predictions
  - large-logarithms
  - matched-resummed-predictions
  - logarithmic-accuracy
researchStatus:
  established:
    - "Resummation of logarithmically enhanced perturbative terms is a standard part of precision QCD, electroweak, and effective-field-theory predictions."
  active:
    - "High-accuracy resummation for realistic multi-scale fiducial observables, non-global logarithms, subleading-power corrections, matching to parton showers, and robust uncertainty prescriptions remain active research and tool-development areas."
---

## Summary

Fixed-order perturbation theory works best when all physical scales in an observable are comparable. It becomes unreliable when phase-space cuts, resolution variables, thresholds, or vetoes create a hierarchy of scales. The perturbative series then contains powers of large logarithms, schematically

$$
\Sigma(v)
=
\sigma_0
\sum_{n=0}^{\infty}
\alpha_s^n
\sum_{m=0}^{2n} c_{nm}\,L^m,
\qquad
L=\ln\frac{1}{v},
\qquad v\ll1.
$$

Even if $\alpha_s$ is small, $\alpha_s L^2$ may not be. **Resummation** reorganizes the calculation so that the logarithmically enhanced terms are included to all orders, while fixed-order matching restores the nonsingular information needed away from the logarithmic region.

A common schematic form for a cumulative observable is

$$
\ln \Sigma(v)
=
L g_1(\alpha_s L)+g_2(\alpha_s L)+\alpha_s g_3(\alpha_s L)+\cdots,
$$

where the functions $g_i$ collect towers of logarithms. The precise definition of LL, NLL, NNLL, and higher accuracy depends on the observable and on whether one counts logarithms in the exponent, the cumulant, or the differential spectrum. A trustworthy prediction always states the counting convention.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 58rem;">

![Workflow for resummation in precision predictions](/figures/perturbative-qft/resummation-precision-predictions.svg)

<figcaption>

A resummed precision prediction starts from a region where fixed order contains large logarithms. Factorization separates hard, jet, beam, and soft physics; RG evolution resums logarithms between their natural scales; matching restores the fixed-order result outside the singular region.

</figcaption>
</figure>

## Prerequisites

You should know [Fixed-Order Predictions](/perturbative-qft/precision-observables/fixed-order-predictions/), [Scale Variation and Uncertainties](/perturbative-qft/precision-observables/scale-variation-and-uncertainties/), [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/), [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/), [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/), and [SCET Preview](/perturbative-qft/infrared-physics-factorization/scet-preview/). For observable definitions, review [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) and [Fiducial Observables](/perturbative-qft/precision-observables/fiducial-observables/).

## Core idea

Resummation is not a new interaction and not a replacement for fixed order. It is a controlled reorganization of perturbation theory when an observable asks the theory to distinguish widely separated scales.

The pattern is:

1. identify the small variable or scale ratio that produces large logarithms;
2. factorize the observable into functions with single natural scales;
3. evolve those functions between scales using renormalization-group equations;
4. match the resummed result to the fixed-order result;
5. validate by expanding the resummed expression and checking that it reproduces the fixed-order singular terms.

The most important practical lesson is that resummation has two jobs. In the logarithmic region it restores perturbative stability. Away from that region, it must gracefully hand back control to the ordinary fixed-order prediction.

## Setup and conventions

We use the scattering and phase-space conventions of this volume. Consider an infrared-safe observable depending on a hard scale $Q$ and a dimensionless resolution variable $v$. The logarithmic region is $v\ll1$, where emissions are restricted by the measurement.

Examples include:

| Observable region | Large logarithm |
|---|---|
| event-shape endpoint, such as thrust $\tau\ll1$ | $\ln(1/\tau)$ |
| small transverse momentum $q_T\ll Q$ | $\ln(Q/q_T)$ |
| jet veto $p_T^{\rm veto}\ll Q$ | $\ln(Q/p_T^{\rm veto})$ |
| partonic threshold $z\to1$ | $\ln(1-z)$ or Mellin-space logarithms |
| small jet radius $R\ll1$ | $\ln R$ |

A resummation formula depends on the observable definition, factorization theorem, logarithmic accuracy, matching prescription, perturbative order, PDF set and $\alpha_s$ input for hadron collisions, and treatment of nonperturbative corrections. These choices are part of the prediction, not decorative metadata.

## When fixed order fails

Suppose a cumulative observable has the one-loop structure

$$
\Sigma(v)
=
\sigma_0
\left[
1+\frac{\alpha_s}{4\pi}\left(a_2L^2+a_1L+a_0\right)+O(\alpha_s^2)
\right].
$$

If $L$ is modest, this is an ordinary perturbative expansion. If $v$ is very small, $L$ can be large enough that the nominally one-loop correction is order one. At two loops the series contains $\alpha_s^2L^4$, $\alpha_s^2L^3$, and lower powers; at $n$ loops it contains still higher powers. The truncation by powers of $\alpha_s$ no longer tracks numerical importance.

This is not a UV divergence and not a failure of renormalization. It is a hierarchy problem inside an otherwise perturbative calculation. The observable has introduced a small scale, and the theory responds with logarithms of scale ratios.

A physical way to say the same thing is this: a tight measurement restriction makes many emissions individually unresolved but collectively important. One soft or collinear emission is easy. Many ordered emissions generate logarithmic towers, and those towers must be summed.

## Factorization and evolution

Resummation usually begins with a factorization theorem. For a hard process with a small resolution variable $v$, the singular part of the cross section often has the schematic form

$$
\frac{d\sigma}{dv}
\sim
H(Q,\mu)
\left[
B_a\otimes B_b\otimes J_1\otimes\cdots\otimes J_N\otimes S
\right](v,\mu),
$$

where the ingredients have different physical roles.

| Factor | Typical role |
|---|---|
| $H$ | virtual hard scattering at scale $Q$ |
| $B_a,B_b$ | beam-collinear radiation and PDFs for incoming hadrons |
| $J_i$ | final-state collinear radiation inside jets |
| $S$ | wide-angle soft radiation constrained by the measurement |

The same logic appears in older QCD factorization formalisms and in SCET. The language differs, but the mechanism is the same: isolate the dynamics associated with each scale, compute each object at a scale where it has no large logarithms, then evolve between scales.

Each factor obeys an RG equation of the form

$$
\mu\frac{d}{d\mu}F(\mu)=\gamma_F(\mu)F(\mu),
$$

possibly with convolutions in momentum fractions or measurement variables. Consistency of the physical cross section requires the anomalous dimensions to combine so that the final prediction is independent of the arbitrary common scale up to the perturbative order used.

This gives the resummation engine:

$$
F(\mu_F)\longrightarrow U_F(\mu_F,\mu)F(\mu_F),
$$

where $\mu_F$ is a natural scale for $F$ and $U_F$ evolves it to a common scale. Large logarithms are moved from fixed-order coefficients into evolution kernels.

## Logarithmic accuracy

Logarithmic labels are useful but dangerous unless their convention is stated. For many cumulative observables one writes

$$
\ln \Sigma(v)
=
L g_1(\lambda)+g_2(\lambda)+\alpha_s g_3(\lambda)+\alpha_s^2 g_4(\lambda)+\cdots,
\qquad
\lambda=\alpha_s L.
$$

Then a common convention is:

| Accuracy | What is controlled schematically |
|---|---|
| LL | $L g_1(\alpha_s L)$ |
| NLL | $L g_1+g_2$ |
| NNLL | $L g_1+g_2+\alpha_s g_3$ |
| N$^3$LL | add $\alpha_s^2 g_4$ |

For a real prediction this table must be translated into anomalous dimensions, fixed-order boundary terms, beta-function order, matching coefficients, PDFs, and nonsingular contributions. Two papers may both say “NNLL” while differing in constants, matching order, or treatment of fiducial cuts. The accuracy label is a summary, not a replacement for the formula.

A good rule is: trust a logarithmic-accuracy claim only after checking what the authors mean by expanding the resummed expression and listing which fixed-order singular terms are reproduced.

## Matching to fixed order

A purely resummed expression is designed for the logarithmic region. A fixed-order expression is designed for the hard region. Precision predictions combine them.

The simplest additive matching formula is

$$
\sigma_{\rm matched}
=
\sigma_{\rm resum}
+
\sigma_{\rm FO}
-
\left.\sigma_{\rm resum}\right|_{\rm expanded\ to\ FO}.
$$

The subtraction removes the terms already present in fixed order. Expanding the matched result to the fixed order gives $\sigma_{\rm FO}$; going into the logarithmic region keeps the all-order resummation.

Other matching prescriptions exist, including multiplicative matching and log-$R$ matching. They differ by terms beyond the claimed accuracy when used consistently, but those differences can be numerically important and are often included in uncertainty estimates.

Matching is where many precision mistakes hide. The fixed-order prediction and the resummed prediction must describe the same observable, same fiducial cuts, same normalization, same PDFs, same couplings, and same perturbative scheme. Otherwise the subtraction does not subtract the correct overlap.

## Profile scales and turning off resummation

In the logarithmic region the natural scales may be separated, for example

$$
\mu_H\sim Q,
\qquad
\mu_J\sim Q\sqrt v,
\qquad
\mu_S\sim Qv
$$

for a thrust-like observable. But away from the endpoint, $v$ is not small, and these scale choices should smoothly return to a common fixed-order scale. This is the purpose of profile scales.

A profile scale is a scale choice that behaves like the canonical resummation scale in the singular region and like an ordinary fixed-order scale in the nonsingular region. It avoids applying endpoint resummation where the endpoint approximation is no longer appropriate.

Profile choices are not unique. They are part of the theory-error estimate. A careful prediction varies the hard, jet, beam, soft, matching, and profile scales in a correlated way that preserves the intended scale hierarchy in the region where the factorization theorem applies.

## Validation checks

A resummed precision prediction should pass several checks before being trusted.

| Check | What it tests |
|---|---|
| Fixed-order expansion | The resummed formula reproduces the known singular terms. |
| Matching expansion | The matched result expands to the fixed-order result through the advertised order. |
| Scale cancellation | Dependence on arbitrary factorization and renormalization scales cancels to the expected order. |
| Endpoint behavior | The prediction is finite and physical in the region it was designed for. |
| Fixed-order region | Resummation turns off smoothly where logs are not large. |
| Normalization | The integrated prediction agrees with the appropriate inclusive result when required. |
| Scheme comparison | Equivalent formalisms agree within stated higher-order differences. |

These are not optional niceties. They are the difference between a resummed calculation and a beautiful machine for summing the wrong logarithms.

## Common pitfalls

**Resumming an observable before proving it factorizes.** Large logarithms signal a scale hierarchy, but not every hierarchy has a simple factorization theorem. Non-global observables, complicated fiducial cuts, recoil-sensitive measurements, and jet algorithms can introduce extra structures.

**Quoting LL, NLL, or NNLL without defining the counting.** The label can refer to logarithms in an exponent, a cumulant, a distribution, or a SCET evolution formula. Always state which anomalous dimensions, matching constants, and fixed-order terms are included.

**Forgetting nonsingular terms.** Resummation controls the singular logarithmic terms. Away from the singular region, fixed-order nonsingular contributions can be numerically important and must be restored by matching.

**Varying scales in a way that breaks the hierarchy.** Independent scale variation is not automatically meaningful. In a resummed prediction, variations should preserve the physical scale ordering in the region where the factorization theorem is being used.

**Treating resummation uncertainty as the whole theory uncertainty.** PDFs, $\alpha_s$, masses, electroweak inputs, nonperturbative corrections, fiducial definitions, missing nonsingular terms, and matching to showers may all matter for a precision observable.

## Relations to other pages

- [Fixed-Order Predictions](/perturbative-qft/precision-observables/fixed-order-predictions/) explains the finite-order calculation that resummation must reproduce after expansion.
- [Scale Variation and Uncertainties](/perturbative-qft/precision-observables/scale-variation-and-uncertainties/) explains the baseline uncertainty logic that becomes more intricate in resummed predictions.
- [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) introduces the separation of hard, collinear, and soft dynamics used here.
- [SCET Preview](/perturbative-qft/infrared-physics-factorization/scet-preview/) gives the effective-theory language behind many modern resummations.
- [Jets and Inclusive Observables](/perturbative-qft/infrared-physics-factorization/jets-and-inclusive-observables/) explains why infrared-safe measurement definitions are the prerequisite for perturbative predictions.
- [Parton-Shower Matching](/perturbative-qft/precision-observables/parton-shower-matching/) discusses the more event-generator-oriented all-order approximation that must often be combined with fixed-order and resummed calculations.

## Research status

Resummation is textbook-standard for many global event shapes, threshold observables, transverse-momentum spectra, jet vetoes, and related inclusive or semi-inclusive quantities. The mathematical ingredients — factorization, anomalous dimensions, RG evolution, matching, and fixed-order expansion checks — are established perturbative QFT technology.

The active frontier is precision in realistic environments. Fiducial cuts, multi-scale measurements, non-global logarithms, jet clustering logarithms, subleading-power corrections, electroweak Sudakov logarithms, heavy-quark mass effects, resummation–shower interfaces, and correlated theory uncertainties are still live subjects. The correct answer is often not “resummation or fixed order,” but a documented combination of fixed order, resummation, PDFs, power corrections, and experimental measurement definitions.

## Exercises

### Exercise 1: Estimate when fixed order becomes unstable

Let $v=10^{-3}$ and $L=\ln(1/v)$. Estimate $\alpha_s L^2$ for $\alpha_s=0.1$. What does the result suggest?

<details>
<summary><strong>Solution</strong></summary>

We have

$$
L=\ln(10^3)\approx 6.91,
\qquad
\alpha_s L^2\approx 0.1\times 47.7\approx 4.8.
$$

A term that is formally first order in $\alpha_s$ can be numerically larger than one because it is multiplied by a large logarithm. This is a typical signal that fixed-order truncation is not organized by numerical size and that resummation is needed.

</details>

### Exercise 2: Check additive matching

Assume

$$
\sigma_{\rm resum}=\sigma^{(0)}+\alpha_s\sigma^{(1)}_{\rm sing}+O(\alpha_s^2),
$$

and

$$
\sigma_{\rm FO}=\sigma^{(0)}+\alpha_s\left(\sigma^{(1)}_{\rm sing}+\sigma^{(1)}_{\rm nons}\right)+O(\alpha_s^2).
$$

Show that additive matching reproduces $\sigma_{\rm FO}$ through $O(\alpha_s)$.

<details>
<summary><strong>Solution</strong></summary>

The additive formula gives

$$
\sigma_{\rm matched}
=
\sigma_{\rm resum}+\sigma_{\rm FO}
-\left.\sigma_{\rm resum}\right|_{O(\alpha_s)}.
$$

Substituting the expansions,

$$
\begin{aligned}
\sigma_{\rm matched}
&=\sigma_{\rm resum}
+\left[\sigma^{(0)}+\alpha_s(\sigma^{(1)}_{\rm sing}+\sigma^{(1)}_{\rm nons})\right]
-\left[\sigma^{(0)}+\alpha_s\sigma^{(1)}_{\rm sing}\right] \\
&=\sigma_{\rm resum}+\alpha_s\sigma^{(1)}_{\rm nons}+O(\alpha_s^2).
\end{aligned}
$$

Expanding this result to $O(\alpha_s)$ gives

$$
\sigma^{(0)}+\alpha_s(\sigma^{(1)}_{\rm sing}+\sigma^{(1)}_{\rm nons}),
$$

which is the fixed-order result.

</details>

### Exercise 3: RG consistency of a factorized cross section

Suppose a simplified factorization theorem has

$$
\sigma=H(\mu)J(\mu)S(\mu),
$$

with

$$
\mu\frac{dH}{d\mu}=\gamma_HH,
\qquad
\mu\frac{dJ}{d\mu}=\gamma_JJ,
\qquad
\mu\frac{dS}{d\mu}=\gamma_SS.
$$

What condition on the anomalous dimensions is required for $\sigma$ to be $\mu$ independent?

<details>
<summary><strong>Solution</strong></summary>

Taking the logarithmic derivative gives

$$
\mu\frac{d\sigma}{d\mu}
=
(\gamma_H+\gamma_J+\gamma_S)\sigma.
$$

Therefore the physical cross section is independent of the arbitrary scale if

$$
\gamma_H+\gamma_J+\gamma_S=0.
$$

In realistic factorization the equation may involve convolutions and matrix anomalous dimensions, but the same consistency idea remains: the scale dependence of unphysical factors cancels in the physical observable.

</details>

### Exercise 4: Identify the missing ingredient

A calculation resums the endpoint logarithms of an event shape and agrees with fixed order in the singular terms, but it is compared directly to data at moderate values of the event shape without matching. What ingredient is missing?

<details>
<summary><strong>Solution</strong></summary>

The calculation is missing the nonsingular fixed-order terms and a prescription for turning off endpoint resummation away from the endpoint. It should be matched to the fixed-order prediction, typically with profile scales or an equivalent mechanism that returns the result to fixed-order behavior where logarithms are not large.

</details>

## References

### Standard first pass

- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the discussions of infrared divergences, jets, QCD factorization, and SCET.
- G. Sterman, *An Introduction to Quantum Field Theory*, for classic perturbative and resummation logic.
- T. Becher, A. Broggio, and A. Ferroglia, *Introduction to Soft-Collinear Effective Theory*, for a modern SCET-based treatment.

### Deeper references

- J. C. Collins, D. E. Soper, and G. Sterman, “Factorization of Hard Processes in QCD,” in *Perturbative Quantum Chromodynamics*, for the classic factorization and resummation framework.
- G. Sterman, “Summation of Large Corrections to Short-Distance Hadronic Cross Sections,” *Nuclear Physics B* **281** (1987), for threshold resummation.
- S. Catani and L. Trentadue, “Resummation of the QCD Perturbative Series for Hard Processes,” *Nuclear Physics B* **327** (1989), for Mellin-space threshold resummation.
- A. Banfi, G. P. Salam, and G. Zanderighi, “Principles of General Final-State Resummation and Automated Implementation,” *Journal of High Energy Physics* **0503** (2005), for automated global-observable resummation.
- T. Becher and M. Neubert, “Drell–Yan Production at Small $q_T$, Transverse Parton Distributions and the Collinear Anomaly,” *European Physical Journal C* **71** (2011), for a representative modern SCET resummation analysis.

## Version history

- **2026-06-13:** Initial standardized page.
