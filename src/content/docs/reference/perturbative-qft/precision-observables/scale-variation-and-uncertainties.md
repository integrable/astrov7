---
title: "Scale Variation and Uncertainties"
description: "How renormalization and factorization scale variation estimates missing higher orders, what it can and cannot diagnose, and how it fits into a precision theory-error budget."
sidebar:
  label: "Scale Variation and Uncertainties"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§27–28; Weinberg 1995, Vol. I, ch. 12 and Vol. II, ch. 18; Schwartz 2014, chs. 20, 23, 31–32; Cacciari–Houdeau 2011; LHC Higgs Cross Section Working Group reports."
topics:
  - scale variation
  - perturbative uncertainties
  - renormalization scale
  - factorization scale
canonicalTopics:
  - scale-variation
  - missing-higher-orders
  - precision-observable-uncertainties
researchStatus:
  established:
    - "Residual dependence on unphysical scales in a truncated perturbative calculation is a standard diagnostic for missing higher-order terms."
  active:
    - "Quantifying missing-higher-order uncertainties probabilistically, correlating them across bins and processes, and combining fixed-order, resummed, shower, PDF, and parametric uncertainties remain active precision-phenomenology problems."
---

## Summary

Exact observables do not depend on unphysical renormalization or factorization scales. Fixed-order predictions do, because the perturbative series has been truncated. **Scale variation** uses this residual dependence to estimate the size of missing higher-order terms.

If an observable starts at order $\alpha_s^p$ and is known through $N$ corrections beyond leading order, then schematically

$$
\frac{d\sigma_N}{d\ln\mu_R}
=
O(\alpha_s^{p+N+1})
$$

after the renormalization-group terms known at that order are included. This is the core idea: the leftover scale dependence is formally of the same order as the first omitted perturbative terms.

Scale variation is useful, but it is not a theorem about the true error. It can miss large constants, new partonic channels, threshold effects, endpoint logarithms, accidental cancellations, PDF correlations, nonperturbative corrections, and electroweak effects. It should be read as one diagnostic in a theory-error budget, not as a magic statistical confidence interval.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 54rem;">

![At higher perturbative orders, residual scale dependence often decreases, but the scale-variation band is only a diagnostic of missing terms.](/figures/perturbative-qft/scale-variation-uncertainties.svg)

<figcaption>

Scale variation probes residual dependence on unphysical scales. In a well-behaved perturbative expansion, higher orders often flatten the scale curve and reduce the envelope, but the envelope is not guaranteed to cover the true all-order answer.

</figcaption>
</figure>

## Prerequisites

You should know [Fixed-Order Predictions](/perturbative-qft/precision-observables/fixed-order-predictions/), [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/), [Callan–Symanzik Preview](/perturbative-qft/renormalized-perturbation-theory/callan-symanzik-preview/), [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/), and [Resummation Preview](/perturbative-qft/infrared-physics-factorization/resummation-preview/).

For hadron-collider predictions, review the role of PDFs and DGLAP evolution in the Gauge Theories and the Standard Model or Renormalization, RG, and EFT volumes.

## Core idea

An exact physical quantity $\sigma$ is independent of arbitrary scales introduced by our calculation:

$$
\frac{d\sigma}{d\ln\mu_R}=0,
\qquad
\frac{d\sigma}{d\ln\mu_F}=0.
$$

The scales are useful precisely because they separate pieces of the calculation. The renormalization scale $\mu_R$ tells us where the coupling and renormalized parameters are defined. The factorization scale $\mu_F$ tells us where long-distance collinear information has been absorbed into PDFs, fragmentation functions, beam functions, or other nonperturbative objects.

At all orders, the scale dependence of one piece cancels the scale dependence of the others. At finite order, the cancellation is incomplete. Varying the scales therefore gives a controlled way to poke the calculation and ask: “How sensitive is this prediction to terms we have not computed?”

That is a good question. It is not the same as asking: “What is the exact probability distribution for the missing terms?” Scale variation is a physics diagnostic, not a probability theorem handed down from Mount Renormalization.

## Setup and conventions

We use the same renormalized perturbation-theory conventions as the rest of the Perturbative QFT and Scattering volume. In QCD applications, $\alpha_s(\mu_R)$ usually denotes the $\overline{\rm MS}$ coupling, and PDFs are evaluated at $\mu_F$.

A generic hadronic fixed-order prediction can be written as

$$
\sigma_N(\mu_R,\mu_F)
=
\sum_{i,j} f_i(\mu_F)\otimes f_j(\mu_F)
\otimes
\left[
\alpha_s^p(\mu_R)
\sum_{n=0}^{N}
\left(\frac{\alpha_s(\mu_R)}{2\pi}\right)^n C_{ij}^{(n)}(\mu_R,\mu_F)
\right].
$$

The symbol $\otimes$ denotes the appropriate momentum-fraction convolution. The coefficient functions contain explicit logarithms of the scales, while the coupling and PDFs have implicit scale dependence. Their interplay is fixed by RG equations.

For non-hadronic observables, there may be only $\mu_R$. For resummed observables, there may also be hard, jet, soft, rapidity, matching, or shower scales. Those extra scales are not decorations; they diagnose different missing logarithmic or matching terms.

## Renormalization-scale variation

The renormalization scale enters through running couplings and renormalized parameters. For a single-coupling observable,

$$
\sigma_N(\mu_R)
=
\alpha_s^p(\mu_R)
\left[
 c_0
 +\frac{\alpha_s(\mu_R)}{2\pi}c_1(\mu_R)
 +\cdots
 +\left(\frac{\alpha_s(\mu_R)}{2\pi}\right)^N c_N(\mu_R)
\right].
$$

The explicit $\mu_R$ dependence in the coefficients cancels the implicit running of $\alpha_s(\mu_R)$ up to the order being computed. The first uncanceled dependence is of the same perturbative order as the first missing correction.

At leading order, there may be no explicit logarithm to compensate the running coupling, so scale variation can be large. At NLO and NNLO, explicit logarithms and higher coefficients often flatten the curve. When this happens, it is evidence that the perturbative prediction is stabilizing. It is not proof that the next correction is small.

A common central choice is a scale $\mu_0$ comparable to the hard momentum transfer, mass, or transverse energy in the process. For multiscale observables, a dynamic scale such as an event-by-event transverse energy may be better than a fixed mass. The central scale should be physically motivated and stated explicitly.

## Factorization-scale variation

In hadron collisions, collinear radiation associated with the incoming hadrons is factorized into PDFs. The PDFs obey DGLAP evolution schematically written as

$$
\frac{d f_i(x,\mu_F)}{d\ln\mu_F}
=
\sum_j P_{ij}(\alpha_s(\mu_F))\otimes f_j(x,\mu_F),
$$

where $P_{ij}$ are splitting functions. The coefficient functions contain compensating $\mu_F$ dependence. At all orders, the physical prediction is independent of $\mu_F$.

At finite order, $\mu_F$ variation estimates sensitivity to missing collinear terms and to the separation between perturbative coefficient functions and PDFs. It is conceptually distinct from $\mu_R$ variation, although in many practical calculations the two scales are varied together or in a correlated set.

A common variation uses

$$
\mu_R=\kappa_R\mu_0,
\qquad
\mu_F=\kappa_F\mu_0,
$$

with $\kappa_R$ and $\kappa_F$ chosen from a finite set around $1$.

## Standard envelopes

A typical factor-two variation evaluates the prediction at scale choices near a central value. For one scale,

$$
\mu\in\left\{\frac{\mu_0}{2},\mu_0,2\mu_0\right\}.
$$

For two scales, a common seven-point set is

$$
(\kappa_R,\kappa_F)
\in
\left\{
(1,1),(2,1),(1,2),\left(\frac12,1\right),\left(1,\frac12\right),(2,2),\left(\frac12,\frac12\right)
\right\}.
$$

The highly anti-correlated points $(2,1/2)$ and $(1/2,2)$ are often omitted because they can generate large artificial logarithms of $\mu_R/\mu_F$. This convention is common, not sacred. For some observables, a different scale scan is more appropriate.

Given a set $S$ of scale choices, the envelope around the central prediction $\sigma_0=\sigma(\mu_0)$ is

$$
\Delta_+
=
\max_{s\in S}\bigl[\sigma(s)-\sigma_0\bigr],
\qquad
\Delta_-
=
\sigma_0-
\min_{s\in S}\bigl[\sigma(s)\bigr].
$$

The result is often quoted as

$$
\sigma_0^{+\Delta_+}_{-\Delta_-}.
$$

This envelope is easy to compute and easy to communicate. That is part of its popularity. The price is that it has no universal probabilistic interpretation.

## What scale variation can diagnose

Scale variation is most informative when the missing terms are dominated by logarithms related to running couplings or factorization. It can diagnose:

| Feature | How it appears |
|---|---|
| Poor central scale choice | Strong slope or unstable prediction near $\mu_0$. |
| Perturbative stabilization | Reduced scale dependence at higher orders. |
| Large collinear effects | Significant sensitivity to $\mu_F$. |
| Large logarithms | Large changes under scales tied to the hierarchy. |
| New channels | Sudden K-factor changes, though scale variation may underestimate them before they appear. |

A shrinking scale band from LO to NLO to NNLO is encouraging. A band that shifts without overlap is a warning sign. A tiny band after an accidental cancellation deserves suspicion, not champagne.

## What scale variation can miss

Scale variation can underestimate uncertainty when the next correction contains a large constant rather than a large logarithm. It can also miss qualitatively new structures.

Important failure modes include:

| Failure mode | Why scale variation may miss it |
|---|---|
| New partonic channel | The channel is absent at the current order, so varying scales cannot reveal its size. |
| New kinematic topology | A higher-order final state opens a region of phase space unavailable at lower order. |
| Large nonlogarithmic constants | The scale derivative is blind to constants not tied to RG logarithms. |
| Endpoint logarithms | Fixed-order scale variation may not represent towers of Sudakov logarithms. |
| Accidental cancellations | The central band can look small because different pieces cancel at the scanned scales. |
| PDF correlations | The PDF fit and $\alpha_s$ value may be correlated with perturbative choices. |
| Nonperturbative effects | Hadronization and underlying-event corrections do not arise from varying $\mu_R$ or $\mu_F$. |
| Electroweak Sudakov effects | At high energies, electroweak logarithms can matter even when QCD scale bands are small. |

This is why precision predictions often combine scale variation with independent PDF, $\alpha_s$, mass, electroweak, nonperturbative, resummation, matching, and numerical uncertainties.

## Correlations across bins and processes

Scale uncertainties are usually correlated. If every bin of a distribution is shifted up by increasing $\mu_R$, the uncertainty is not independent bin by bin. Treating correlated theory errors as independent can artificially overconstrain fits.

For a binned distribution, there are several common strategies:

| Strategy | Meaning |
|---|---|
| Fully correlated normalization variation | One scale shift moves all bins coherently. |
| Shape-and-normalization decomposition | Separate total-rate and shape components. |
| Independent bin envelope | Conservative in some contexts, over-flexible in others. |
| Nuisance-parameter model | Treat scale choices or theory components as correlated nuisance directions. |
| Covariance model | Build an explicit covariance matrix for theory uncertainty. |

No single strategy is universal. A total cross section, a normalized shape, a jet-bin measurement, and a global EFT fit need different correlation models.

## Relation to resummation and matching scales

When a prediction is resummed, the scale story becomes richer. A factorized observable may involve hard, jet, and soft scales:

$$
\sigma
\sim
H(Q,\mu_H)\,J(q,\mu_J)\,S(q,\mu_S)
\times \text{evolution factors}.
$$

Varying these scales probes missing fixed-order terms in the hard, jet, and soft functions and missing logarithmic terms in the evolution. A single common scale variation may not test the relevant uncertainty directions.

For matched fixed-order plus resummed predictions, one should distinguish:

| Scale type | What it probes |
|---|---|
| Fixed-order scales | Missing nonlogarithmic terms in the fixed-order expansion. |
| Resummation scales | Missing logarithmic terms in the resummed series. |
| Matching scales | Dependence on the transition between resummed and fixed-order regions. |
| Shower scales | Approximation and matching uncertainties in event-generator descriptions. |

This is why a precision paper should state not only the scale range but also the variation prescription.

## Toy example: why the derivative is higher order

Consider

$$
R_1(\mu)
=
\alpha_s(\mu)c_0
+\alpha_s^2(\mu)
\left[c_1+b_0c_0\ln\frac{\mu}{Q}\right],
$$

with one-loop running

$$
\frac{d\alpha_s}{d\ln\mu}=-b_0\alpha_s^2+O(\alpha_s^3).
$$

Differentiating gives

$$
\frac{dR_1}{d\ln\mu}
=
(-b_0\alpha_s^2)c_0
+
\alpha_s^2 b_0c_0
+O(\alpha_s^3)
=
O(\alpha_s^3).
$$

The explicit logarithm cancels the running of the leading term through $O(\alpha_s^2)$. The remaining scale dependence is one order beyond the accuracy of $R_1$. This is the little algebraic motor behind scale variation.

## Common pitfalls

**Treating the scale band as a confidence interval.** The usual envelope is not automatically a $68\%$ or $95\%$ probability interval.

**Varying only one scale in a multiscale problem.** If the observable has hard, jet, soft, factorization, and matching scales, one common variation can miss important directions.

**Using a central scale without physics.** A bad $\mu_0$ can make the series look worse or better than it is.

**Forgetting normalized distributions.** Normalizing a distribution can cancel common scale dependence, producing small shape bands that do not represent the uncertainty in the total rate.

**Confusing scale uncertainty with PDF uncertainty.** PDFs, $\alpha_s$, and perturbative coefficients are related but distinct ingredients.

**Ignoring new channels.** A small LO scale band does not predict whether a large new NLO channel will appear.

**Over-interpreting overlap.** Overlap of scale bands between orders is reassuring, not a proof of convergence. Lack of overlap is a warning, not an automatic failure.

## Relations to other pages

- [Fixed-Order Predictions](/perturbative-qft/precision-observables/fixed-order-predictions/) explains the prediction framework in which scale variation is used.
- [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/) explains why the scale $\mu$ appears in dimensional regularization.
- [Callan–Symanzik Preview](/perturbative-qft/renormalized-perturbation-theory/callan-symanzik-preview/) explains scale dependence through RG equations.
- [Coupling Renormalization](/perturbative-qft/renormalized-perturbation-theory/coupling-renormalization/) explains running couplings.
- [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) explains the separation of hard, collinear, and soft physics.
- [Resummation Preview](/perturbative-qft/infrared-physics-factorization/resummation-preview/) explains why fixed-order scale variation is not enough in logarithmically enhanced regions.
- [SCET Preview](/perturbative-qft/infrared-physics-factorization/scet-preview/) gives the effective-theory language for multiple physical scales.

## Research status

- **Established:** Residual scale dependence is a standard fixed-order diagnostic for missing perturbative terms. It is routinely used in precision QCD and electroweak phenomenology.
- **Active:** Better models of missing-higher-order uncertainties, correlations across bins and processes, and combinations of fixed-order, resummed, shower, PDF, and parametric uncertainties are active research and analysis topics.
- **Subtle:** A smaller scale band is not always a more reliable prediction. It can reflect a real improvement, an accidental cancellation, or an insufficient variation prescription.
- **Speculative:** Probabilistic models for missing higher orders can be useful, but no single model is a universal replacement for physics judgment and explicit higher-order calculations.

## Exercises

### Exercise 1: Scale derivative at leading order

Let

$$
R_{\rm LO}(\mu)=c_0\alpha_s^p(\mu),
$$

with

$$
\frac{d\alpha_s}{d\ln\mu}=-b_0\alpha_s^2+O(\alpha_s^3).
$$

Show that the residual scale dependence of the LO prediction is of relative order $\alpha_s$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
\frac{dR_{\rm LO}}{d\ln\mu}
=
p c_0\alpha_s^{p-1}\frac{d\alpha_s}{d\ln\mu}
=
-pb_0c_0\alpha_s^{p+1}+O(\alpha_s^{p+2}).
$$

Since

$$
R_{\rm LO}=c_0\alpha_s^p,
$$

the relative scale derivative is

$$
\frac{1}{R_{\rm LO}}\frac{dR_{\rm LO}}{d\ln\mu}
=
-pb_0\alpha_s+O(\alpha_s^2).
$$

Thus LO residual scale dependence is relatively one power of $\alpha_s$ beyond the LO result.

</details>

### Exercise 2: Cancellation of explicit and implicit scale dependence

For

$$
R_1(\mu)
=
\alpha_s(\mu)c_0
+\alpha_s^2(\mu)\left[c_1+b_0c_0\ln\frac{\mu}{Q}\right],
$$

show that $dR_1/d\ln\mu=O(\alpha_s^3)$ using one-loop running.

<details>
<summary><strong>Solution</strong></summary>

Using

$$
\frac{d\alpha_s}{d\ln\mu}=-b_0\alpha_s^2+O(\alpha_s^3),
$$

we get

$$
\frac{d}{d\ln\mu}\bigl[\alpha_s c_0\bigr]
=
-b_0c_0\alpha_s^2+O(\alpha_s^3).
$$

The derivative of the $\alpha_s^2$ prefactor contributes only at $O(\alpha_s^3)$, so at $O(\alpha_s^2)$ the second term gives only the derivative of the logarithm:

$$
\frac{d}{d\ln\mu}\left[\alpha_s^2 b_0c_0\ln\frac{\mu}{Q}\right]
=
b_0c_0\alpha_s^2+O(\alpha_s^3).
$$

The two $O(\alpha_s^2)$ terms cancel, leaving

$$
\frac{dR_1}{d\ln\mu}=O(\alpha_s^3).
$$

</details>

### Exercise 3: Seven-point scale envelope

For a prediction with central scale $\mu_0$, list the common seven scale choices used for $(\mu_R,\mu_F)$ variation.

<details>
<summary><strong>Solution</strong></summary>

The common seven-point set is

$$
(\mu_R,\mu_F)
=
\mu_0\times
\left\{
(1,1),(2,1),(1,2),\left(\frac12,1\right),\left(1,\frac12\right),(2,2),\left(\frac12,\frac12\right)
\right\}.
$$

The anti-correlated choices

$$
(\mu_R,\mu_F)=(2\mu_0,\mu_0/2),
\qquad
(\mu_R,\mu_F)=(\mu_0/2,2\mu_0)
$$

are often omitted. This is a convention for many collider calculations, not a theorem.

</details>

### Exercise 4: Why a small LO band can be misleading

Give one reason a leading-order prediction can have a small scale-variation band but still receive a large NLO correction.

<details>
<summary><strong>Solution</strong></summary>

A new partonic channel may first appear at NLO. Since it is absent at LO, varying the LO scales cannot estimate its size. If the new channel has a large parton luminosity or populates an important kinematic region, the NLO correction can be large even though the LO scale band was small.

Another possibility is a large nonlogarithmic constant at NLO. Scale variation mainly probes logarithmic dependence tied to RG structure, so it can miss a large constant term.

</details>

### Exercise 5: Normalized distributions

Let

$$
\frac{1}{\sigma}\frac{d\sigma}{dx}
$$

be a normalized distribution. Why can its scale uncertainty be smaller than the scale uncertainty of $d\sigma/dx$ itself?

<details>
<summary><strong>Solution</strong></summary>

Both the numerator and denominator depend on the scales. If scale variation mostly changes the overall normalization, then similar scale dependence appears in $d\sigma/dx$ and in $\sigma$. Their ratio cancels much of that common dependence.

This cancellation may be appropriate when the observable is genuinely normalized. But it also means the normalized scale band describes shape uncertainty, not the uncertainty in the absolute rate.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§27–28, for renormalization schemes and RG ideas in perturbation theory.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 12 and Vol. II, ch. 18, for renormalization and RG methods.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 20, 23, 31, and 32, for infrared divergences, RG equations, precision tests, and QCD factorization.
- R. K. Ellis, W. J. Stirling, and B. R. Webber, *QCD and Collider Physics*, for collider-QCD scale choices and perturbative uncertainty practice.
- M. Cacciari and N. Houdeau, “Meaningful Characterisation of Perturbative Theoretical Uncertainties,” *Journal of High Energy Physics* **09** (2011), for a Bayesian model of missing higher orders.
- M. Bonvini, “Probabilistic Definition of the Perturbative Theoretical Uncertainty from Missing Higher Orders,” *European Physical Journal C* **80** (2020), for modern probabilistic uncertainty modeling.
- LHC Higgs Cross Section Working Group reports for practical scale-variation prescriptions, PDF and $\alpha_s$ treatment, and uncertainty bookkeeping in Higgs precision predictions.
- G. P. Salam, “Towards Jetography,” *European Physical Journal C* **67** (2010), for infrared-safe jets and the relation between observable definitions and perturbative stability.

## Version history

- **2026-06-13:** Initial polished draft for the Precision Observables chapter, emphasizing residual scale dependence, standard variation envelopes, factorization-scale logic, limitations, correlations, and relation to resummation.
