---
title: "Electroweak Corrections"
description: "How QED and weak radiative corrections enter precision observables, including input schemes, real radiation, photon-induced channels, Sudakov logarithms, and mixed QCD–EW effects."
sidebar:
  label: "Electroweak Corrections"
  order: 4
level: Graduate
status: "Polished draft"
source: "Denner and Dittmaier 2019; LHC Higgs Cross Section Working Group reports; Weinberg 1996, Vol. II; Schwartz 2014, chs. 8, 19, 31."
topics:
  - precision observables
  - electroweak corrections
  - QED radiation
  - Sudakov logarithms
canonicalTopics:
  - electroweak-corrections
  - precision-observables
  - radiative-corrections
researchStatus:
  established:
    - "One-loop electroweak corrections, QED real-radiation treatment, input-parameter renormalization, and high-energy electroweak Sudakov logarithms are standard ingredients of precision collider predictions."
  active:
    - "The active frontier includes automated higher-order EW corrections, mixed QCD–EW terms, photon and electroweak PDFs, unstable-particle treatments, high-energy resummation, and consistent uncertainty combinations for future precision programs."
---

## Summary

**Electroweak corrections** are radiative corrections involving photons, $W$ bosons, $Z$ bosons, Higgs bosons, electroweak counterterms, and electroweak input-parameter conversions. They matter whenever the target precision is at the percent level, whenever real photons affect the fiducial definition, or whenever a process probes energy scales far above the weak scale.

A typical prediction is organized schematically as

$$
\sigma
=
\sigma_{\rm LO}
+
\delta\sigma_{\rm QCD}
+
\delta\sigma_{\rm EW}
+
\delta\sigma_{\rm mixed}
+
\cdots,
$$

where $\delta\sigma_{\rm EW}$ may include virtual weak loops, photon loops, real photon emission, photon-induced partonic channels, and weak-boson radiation depending on the observable definition.

At high momentum transfer $Q\gg M_W$, purely weak virtual corrections often contain Sudakov logarithms of the form

$$
\delta_{\rm EW}
\sim
-\frac{\alpha}{4\pi s_W^2}\,C_{\rm EW}\,\log^2\!\left(\frac{Q^2}{M_W^2}\right)
+\cdots,
$$

with a process-dependent electroweak charge factor $C_{\rm EW}$. These logarithms are one reason electroweak corrections can become large in TeV tails even though $\alpha$ is small.

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 56rem;">

![Electroweak corrections combine input-scheme choices, virtual weak loops, real photon radiation, photon-induced channels, weak-boson radiation, and mixed QCD-EW effects.](/figures/perturbative-qft/electroweak-corrections.svg)

<figcaption>

An electroweak-corrected prediction is a workflow, not a single diagram: choose an input scheme, renormalize the electroweak parameters, add virtual and real corrections consistently, define photon and weak-boson radiation in the observable, and combine the result with QCD corrections without double counting.

</figcaption>
</figure>

## Prerequisites

You should know [Fixed-Order Predictions](/perturbative-qft/precision-observables/fixed-order-predictions/), [PDF and αs Uncertainties](/perturbative-qft/precision-observables/pdf-and-alpha-s-uncertainties/), [QED Tree Amplitudes](/perturbative-qft/tree-level-scattering/qed-tree-amplitudes/), [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/), [Soft Photon Theorem](/perturbative-qft/infrared-physics-factorization/soft-photon-theorem/), and [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/).

For full Standard Model applications, you should also know the electroweak gauge structure, symmetry breaking, and gauge-boson couplings from the Gauge Theories and the Standard Model volume.

## Core idea

Electroweak corrections are conceptually close to QCD corrections but operationally different in several ways.

Photons are massless, so QED corrections have genuine infrared and collinear singularities. These cancel only after the observable is defined inclusively enough, or after collinear pieces are absorbed into PDFs, fragmentation functions, or lepton structure functions.

Weak bosons are massive, so virtual $W$ and $Z$ loops are infrared finite. However, their finite remnants can be large at high energy because $M_W$ and $M_Z$ regulate soft-collinear regions. The result is not a pole in a regulator; it is a large logarithm of a physical ratio.

The electroweak theory is spontaneously broken. This means that input choices such as $\alpha(0)$, $\alpha(M_Z)$, $G_F$, $M_W$, and $M_Z$ are not mere cosmetic choices at finite order. They decide which universal corrections are absorbed into leading input parameters and which appear explicitly in loop corrections.

Finally, at hadron colliders electroweak corrections interact with QCD factorization. Photon PDFs, photon-induced channels, QED evolution, mixed QCD–EW corrections, and jet/lepton/photon definitions all enter. Precision predictions are where gauge theory stops being a slogan and starts asking whether your lepton is dressed.

## Setup and conventions

We use the conventions of this volume and the site-wide electroweak conventions. The electromagnetic coupling is denoted $\alpha=e^2/(4\pi)$, the weak mixing angle by $s_W=\sin\theta_W$ and $c_W=\cos\theta_W$, and the weak scale by masses such as $M_W$ and $M_Z$.

For a process with Born amplitude $\mathcal M_0$, the NLO electroweak correction contains a virtual contribution

$$
d\sigma_{\rm virt}^{\rm EW}
\propto
2\,\operatorname{Re}\left(\mathcal M_0^*\mathcal M_1^{\rm EW}\right)d\Phi_n,
$$

plus counterterms and real-emission terms such as

$$
d\sigma_{\rm real}^{\gamma}
\propto
|\mathcal M_{n+\gamma}|^2d\Phi_{n+\gamma}.
$$

For hadronic initial states, there can also be photon-induced channels such as

$$
\gamma q\to X,
\qquad
\gamma\gamma\to X,
$$

if they contribute at the same claimed accuracy. Whether these are called “electroweak corrections,” “photon-induced corrections,” or “separate channels” is less important than whether they are included and documented.

## Anatomy of an NLO electroweak prediction

A realistic NLO electroweak prediction usually has several ingredients.

| Ingredient | Role | Typical caveat |
|---|---|---|
| Virtual weak loops | Finite $W$, $Z$, Higgs, top, and Goldstone-loop corrections | Can contain large Sudakov logarithms at high $Q$ |
| Virtual photon loops | QED loop corrections | Infrared singular before real radiation is included |
| Real photon emission | Cancels soft singularities and affects fiducial cuts | Requires photon isolation, lepton dressing, or fragmentation treatment |
| Initial-state QED collinear terms | Absorbed into PDFs for hadronic initial states | Requires a PDF set and factorization convention with QED if relevant |
| Photon-induced channels | Contributions from photon PDFs | Can be important in some high-energy or electroweak processes |
| Real weak-boson radiation | Extra $W$ or $Z$ in the final state | May or may not belong to the measured signal |
| Electroweak counterterms | Renormalize masses, fields, mixing angle, charges | Depend on the chosen input scheme |
| Mixed QCD–EW terms | Corrections of order $\alpha_s\alpha$ relative to suitable Born powers | Often estimated by additive or multiplicative combinations when exact results are unavailable |

The first mistake students make is to imagine that “the electroweak correction” is one universal factor. It is not. It is a correction to a specific observable definition, with a specific input scheme and a specific treatment of real radiation.

## Input-parameter schemes

The electroweak Standard Model has several precisely measured input quantities. At finite perturbative order, choosing which ones define the tree-level parameters changes the numerical size and interpretation of the loop correction.

| Scheme | Typical inputs | Useful when | Caveat |
|---|---|---|---|
| $\alpha(0)$ scheme | $\alpha(0)$, $M_W$, $M_Z$ or related masses | External real photons and low-energy electromagnetic normalization are central | Large light-fermion vacuum-polarization effects appear in weak-scale predictions |
| $\alpha(M_Z)$ scheme | Effective electromagnetic coupling near the $Z$ scale | Weak-scale neutral-current observables | Running of $\alpha$ is absorbed, but the scheme is less directly tied to muon decay |
| $G_\mu$ scheme | $G_F$, $M_W$, $M_Z$ | Weak processes at high energy and many collider predictions | Universal corrections from muon decay are absorbed into the Born normalization |

The $G_\mu$ scheme is common in LHC electroweak predictions because it absorbs important universal corrections associated with the relation between muon decay and the weak scale. The $\alpha(0)$ scheme remains natural when external resolved photons are central. The right choice is process-dependent.

A finite-order prediction should state the input scheme. Otherwise, two correct calculations can appear to disagree by a few percent simply because they put the same universal physics in different perturbative places.

## Real photon radiation and fiducial definitions

QED real radiation is not optional bookkeeping. It changes what the detector sees.

For final-state charged leptons, collinear photon emission produces logarithms involving the lepton mass if the observable distinguishes a bare lepton from a nearby photon. Many collider measurements instead use **dressed leptons**, recombining photons in a small cone around the lepton. This makes the observable more collinear safe and often closer to what is reconstructed experimentally.

For photons in the final state, isolation matters. A photon-plus-jet observable with a hard isolated photon is not the same as an inclusive QED-radiative correction. Isolation prescriptions decide how much hadronic or partonic energy may accompany the photon.

For hadronic initial states, collinear photon emission from incoming quarks can be factorized into PDFs, analogously to QCD collinear factorization. This introduces QED factorization conventions and, in modern high-precision contexts, photon PDFs.

The practical rule is simple: define the measured object first. Then decide which real-radiation contributions are included. Never do it the other way around.

## Weak Sudakov logarithms

At energies much larger than the weak scale, virtual electroweak corrections contain logarithms such as

$$
\log\!\left(\frac{Q^2}{M_W^2}\right),
\qquad
\log^2\!\left(\frac{Q^2}{M_W^2}\right).
$$

They arise from soft and collinear regions regulated by the physical $W$ and $Z$ masses. A schematic one-loop high-energy correction has the form

$$
\delta_{\rm weak}^{(1)}
=
-\frac{\alpha}{4\pi}
\left[
C_2\log^2\!\left(\frac{Q^2}{M_W^2}\right)
+C_1\log\!\left(\frac{Q^2}{M_W^2}\right)
+C_0
\right],
$$

where the coefficients depend on the external particles, their electroweak charges, and the process.

These logarithms are analogous to QCD and QED Sudakov logarithms, but the cancellation story is different. Real $W$ and $Z$ emission changes the observed final state, and typical proton beams are not averaged over full weak-isospin multiplets. Therefore the virtual weak Sudakov corrections are often visible in exclusive high-energy distributions.

At multi-TeV scales, fixed-order electroweak logarithms may need resummation, especially for future colliders or tails used for new-physics searches. At ordinary inclusive weak-scale observables, fixed-order treatment may be enough.

## Combining QCD and electroweak corrections

Suppose a process has an LO cross section $\sigma_0$, a relative QCD correction $\delta_{\rm QCD}$, and a relative electroweak correction $\delta_{\rm EW}$. Two common approximations are

$$
\sigma_{\rm add}
=
\sigma_0\left(1+\delta_{\rm QCD}+\delta_{\rm EW}\right),
$$

and

$$
\sigma_{\rm mult}
=
\sigma_0\left(1+\delta_{\rm QCD}\right)
\left(1+\delta_{\rm EW}\right).
$$

Their difference is

$$
\sigma_{\rm mult}-\sigma_{\rm add}
=
\sigma_0\,\delta_{\rm QCD}\delta_{\rm EW}.
$$

This is an estimate of a mixed QCD–EW contribution. It is useful, but it is not a substitute for an actual mixed calculation when percent-level precision is required.

The multiplicative approximation is often motivated when QCD and electroweak effects factorize approximately, as in some Sudakov or production-times-decay situations. The additive approximation is more conservative when the factorization of corrections is not established. A good precision paper states which combination is used and treats the difference as a possible uncertainty if no exact mixed result is available.

## Electroweak corrections in precision fits

Electroweak corrections enter two different kinds of precision work.

The first is **precision Standard Model prediction**: compute a fiducial or inclusive observable with enough QCD, electroweak, PDF, and nonperturbative control to compare with data.

The second is **electroweak-parameter inference**: use observables to extract or constrain quantities such as $M_W$, $\sin^2\theta_{\rm eff}$, Higgs couplings, anomalous gauge couplings, or SMEFT Wilson coefficients.

In the second use, electroweak corrections are not merely corrections to a cross section. They decide which parameter is being extracted. A shift in the input scheme, missing mixed correction, or mis-modeled photon radiation can look like a shift in a weak mixing angle or a new-physics coefficient.

This is why precision electroweak fits have a reputation for being fussy. The fuss is not ceremonial. It is the price of extracting physical information from percent-level and sub-percent-level differences.

## Unstable particles and gauge invariance

Many electroweak observables involve unstable particles: $W$, $Z$, top quarks, Higgs bosons, and resonant intermediate states. A naive insertion of widths into propagators can break gauge invariance if it is not done consistently.

Common controlled treatments include

| Method | Idea | Use |
|---|---|---|
| Narrow-width approximation | Factorize production and decay near a resonance | Simple when off-shell and interference effects are small |
| Pole approximation | Expand around the complex pole of the unstable particle | Preserves gauge-invariant resonant information |
| Complex-mass scheme | Treat masses as complex parameters consistently in the renormalized theory | Useful for off-shell multi-particle calculations |
| Full off-shell calculation | Include all diagrams for the measured final state | Most complete, often computationally expensive |

The lesson is not that one method is always best. The lesson is that the resonance treatment is part of the theory definition for the prediction.

## Common pitfalls

**Calling every non-QCD correction “electroweak” without defining the observable.** Real photons, photon-induced channels, and real weak-boson radiation depend on the fiducial definition.

**Forgetting the input scheme.** A correction quoted in the $\alpha(0)$ scheme can look different from the same physics quoted in the $G_\mu$ scheme.

**Assuming weak corrections are always tiny.** At high $Q$, electroweak Sudakov logarithms can make one-loop weak corrections numerically important.

**Adding real weak bosons automatically.** Real $W$ or $Z$ emission usually changes the experimental final state. KLN cancellation does not let you add it blindly to an exclusive process.

**Neglecting photon PDFs when they are relevant.** Some processes receive photon-induced contributions at the same claimed precision as the loop correction.

**Using additive or multiplicative QCD–EW combinations without saying which.** The difference estimates mixed terms and can matter in precision fits.

**Breaking gauge invariance with unstable-particle widths.** Resonances require a consistent approximation or scheme.

## Relations to other pages

- [Fixed-Order Predictions](/perturbative-qft/precision-observables/fixed-order-predictions/) gives the general perturbative prediction workflow.
- [PDF and αs Uncertainties](/perturbative-qft/precision-observables/pdf-and-alpha-s-uncertainties/) treats PDF, photon-PDF, and $\alpha_s$ input uncertainties.
- [Soft Photon Theorem](/perturbative-qft/infrared-physics-factorization/soft-photon-theorem/) explains the universal soft-photon limit behind QED real-emission corrections.
- [Bloch–Nordsieck Theorem](/perturbative-qft/infrared-physics-factorization/bloch-nordsieck-theorem/) and [KLN Theorem](/perturbative-qft/infrared-physics-factorization/kln-theorem/) explain inclusive cancellation of infrared singularities.
- [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/) explains the gauge-invariance constraints on QED radiative corrections.
- [Narrow-Width Approximation](/perturbative-qft/phase-space-cross-sections-decays/narrow-width-approximation/) gives the first controlled approximation for unstable resonances.
- [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/) explains how loop amplitudes become finite after counterterms and renormalization conditions.

## Research status

- **Established:** One-loop electroweak corrections, QED infrared subtraction, lepton dressing, photon-induced channels, electroweak input schemes, high-energy Sudakov logarithms, and gauge-invariant treatments of unstable particles are standard precision-collider tools.
- **Active:** Two-loop electroweak and mixed QCD–EW corrections, electroweak resummation, electroweak PDFs, photon-PDF uncertainties, automated off-shell calculations, realistic shower matching, and future-collider sub-percent systematics remain active.
- **Convention-dependent:** The split between “QED,” “weak,” “photon-induced,” and “electroweak” pieces depends on input scheme, factorization convention, and observable definition. The physical prediction is the combined observable, not the bookkeeping label.

## Exercises

### Exercise 1: Additive versus multiplicative combination

Let $\delta_{\rm QCD}=0.30$ and $\delta_{\rm EW}=-0.05$. Compute the difference between multiplicative and additive combination in units of the LO cross section.

<details>
<summary><strong>Solution</strong></summary>

The difference is

$$
\frac{\sigma_{\rm mult}-\sigma_{\rm add}}{\sigma_0}
=
\delta_{\rm QCD}\delta_{\rm EW}.
$$

Thus

$$
\delta_{\rm QCD}\delta_{\rm EW}
=(0.30)(-0.05)=-0.015.
$$

The multiplicative result is lower than the additive result by $1.5\%$ of the LO cross section. This difference estimates a mixed QCD–EW effect in this simplified treatment.

</details>

### Exercise 2: Sudakov growth

A weak correction contains a term

$$
-\frac{\alpha}{4\pi s_W^2}C\log^2\!\left(\frac{Q^2}{M_W^2}\right).
$$

Explain why this term grows in magnitude at high $Q$ even though the weak boson is massive.

<details>
<summary><strong>Solution</strong></summary>

The weak-boson mass regulates the would-be soft and collinear singularity. Instead of a regulator pole, the finite answer contains a logarithm of the ratio between the hard scale and the weak scale:

$$
\log\!\left(\frac{Q^2}{M_W^2}\right).
$$

When $Q\gg M_W$, this logarithm becomes large. Its square can compensate the small prefactor $\alpha/(4\pi s_W^2)$, producing numerically important corrections in high-energy tails.

</details>

### Exercise 3: Collinear safety for leptons

Why does recombining photons close to a charged lepton reduce sensitivity to final-state collinear logarithms?

<details>
<summary><strong>Solution</strong></summary>

Collinear photon emission from a charged lepton produces configurations where the photon and lepton are nearly parallel. If the observable treats the bare lepton and the nearby photon as separate, the result can retain logarithms of the lepton mass.

Dressing the lepton by recombining nearby photons makes the measurement insensitive to the exact splitting of a collinear lepton–photon pair. The observable is then more collinear safe, and the large mass logarithms are reduced or canceled in the inclusive recombined quantity.

</details>

### Exercise 4: Input scheme dependence

Why can two finite-order electroweak calculations using different input schemes give different numerical corrections while agreeing on the physical all-order prediction?

<details>
<summary><strong>Solution</strong></summary>

An input scheme decides which measured quantities define the tree-level parameters. Changing the scheme moves some universal radiative effects between the Born term and the loop correction.

At all orders, this reshuffling cancels in the final physical prediction. At finite order, the cancellation is incomplete by terms beyond the computed order. Therefore different schemes can give different finite-order correction factors even when they describe the same physics.

</details>

### Exercise 5: Real weak-boson emission

Why does adding real $Z$ emission not automatically cancel virtual weak Sudakov logarithms in an exclusive high-$p_T$ dilepton measurement?

<details>
<summary><strong>Solution</strong></summary>

A real emitted $Z$ changes the final state. An exclusive dilepton measurement without an additional weak boson does not include those events. Since the observable is not inclusive over real weak-boson radiation, the virtual weak Sudakov terms need not cancel.

There is also no exact analogue of fully inclusive QED cancellation for typical hadron-collider weak corrections because the beams and measured states are not averaged over complete weak-isospin multiplets. The physical $W$ and $Z$ masses make the correction finite, but the high-energy logarithms remain visible.

</details>

## References

- A. Denner and S. Dittmaier, “Electroweak Radiative Corrections for Collider Physics,” *Physics Reports* **864** (2020) 1–163, arXiv:1912.06823.
- D. de Florian et al., *Handbook of LHC Higgs Cross Sections: 4. Deciphering the Nature of the Higgs Sector*, CERN Yellow Report, arXiv:1610.07922.
- J.-y. Chiu, R. Kelley, and A. V. Manohar, “Electroweak Corrections using Effective Field Theory: Applications to the LHC,” *Physical Review D* **78** (2008) 073006, arXiv:0806.1240.
- A. Denner and S. Pozzorini, “One-loop leading logarithms in electroweak radiative corrections,” *European Physical Journal C* **18** (2001) 461–480, and follow-up work on electroweak Sudakov logarithms.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 8, 19, and 31, for gauge invariance, renormalized perturbation theory, and electroweak precision tests.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, chs. 15, 17, and 21, for non-Abelian gauge theory, gauge-theory renormalization, and spontaneously broken gauge theories.
- Particle Data Group, *Review of Particle Physics*, current reviews on the electroweak model, QCD, Higgs physics, and precision constraints.

## Version history

- **2026-06-13:** Initial polished draft. Emphasizes durable electroweak-correction workflows and avoids hard-coding time-sensitive numerical electroweak fit inputs.
