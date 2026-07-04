---
title: "PDF and αₛ Uncertainties"
description: "How parton-distribution and strong-coupling uncertainties enter precision hadron-collider predictions, how they are propagated, and how they differ from scale variation."
sidebar:
  label: "PDF and αₛ Uncertainties"
  order: 3
level: Graduate
status: "Polished draft"
source: "PDF4LHC21; PDG Review of Particle Physics, Quantum Chromodynamics; Schwartz 2014, chs. 20, 26, and 32."
topics:
  - precision observables
  - parton distributions
  - strong coupling
  - collider uncertainties
canonicalTopics:
  - pdf-uncertainties
  - alpha-s-uncertainties
  - factorized-hadronic-predictions
researchStatus:
  established:
    - "PDF and strong-coupling uncertainties are standard components of precision hadron-collider theory predictions and are propagated through factorized cross sections using PDF error sets, replicas, covariance matrices, or combined ensembles."
  active:
    - "The detailed treatment of correlations, theory uncertainties in PDF fits, photon and heavy-flavor PDFs, nuclear corrections, small-x dynamics, and high-luminosity collider constraints remains an active precision-phenomenology topic."
---

## Summary

Hadron-collider predictions require two ingredients that are not fixed by the short-distance matrix element alone: parton distribution functions and the value of the strong coupling. For a proton-proton observable, the schematic factorization formula is

$$
X=
\sum_{i,j}\int_0^1 dx_1\,dx_2\,
 f_{i/p}(x_1,\mu_F)f_{j/p}(x_2,\mu_F)
\,\widehat X_{ij}(x_1,x_2;\mu_F,\mu_R,\alpha_s(\mu_R),\{m\}),
$$

where $f_{i/p}$ are PDFs, $\mu_F$ is the factorization scale, $\mu_R$ is the renormalization scale, and $\widehat X_{ij}$ is the partonic prediction. The PDFs and $\alpha_s$ enter both the convolution and the perturbative expansion. They therefore produce uncertainties that are related to, but conceptually different from, missing-higher-order scale variation.

A clean precision prediction should state which PDF set was used, which value of $\alpha_s(M_Z)$ was used, how the PDF uncertainty was propagated, how the $\alpha_s$ uncertainty was propagated, whether PDF–$\alpha_s$ correlations were included, and whether the quoted uncertainty is meant to be experimental, theoretical, statistical, or a combined recommendation.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 54rem;">

![PDF and strong-coupling uncertainty flow](/figures/perturbative-qft/pdf-alpha-s-uncertainties.svg)

<figcaption>

A hadron-collider prediction inherits uncertainty from the fitted PDFs, from the value of $\alpha_s$, from perturbative scales, and from choices made in the fit and hard calculation. PDF and $\alpha_s$ uncertainties are parametric inputs to the factorized prediction; scale variation estimates missing higher orders in the short-distance calculation.

</figcaption>
</figure>

## Prerequisites

You should know the factorized cross-section formula from [fixed-order predictions](/perturbative-qft/precision-observables/fixed-order-predictions/), the role of scale variation from [Scale Variation and Uncertainties](/perturbative-qft/precision-observables/scale-variation-and-uncertainties/), and the basic idea of soft-collinear factorization from [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/). For the origin of $\alpha_s$ running, review [Coupling Renormalization](/perturbative-qft/renormalized-perturbation-theory/coupling-renormalization/).

## Core idea

A proton is not a beam of free quarks and gluons with known momenta. In a high-energy process, the short-distance scattering sees partons carrying momentum fractions $x_1$ and $x_2$. The probability densities for finding those partons at the factorization scale $\mu_F$ are extracted from global fits to data, evolved with perturbative QCD, and distributed as PDF error sets or replicas.

The strong coupling appears in two different places.

First, it appears explicitly in the perturbative partonic cross section:

$$
\widehat X_{ij}
=
\alpha_s^{n_0}(\mu_R)\widehat X^{(0)}_{ij}
+\alpha_s^{n_0+1}(\mu_R)\widehat X^{(1)}_{ij}
+\alpha_s^{n_0+2}(\mu_R)\widehat X^{(2)}_{ij}
+\cdots.
$$

Second, it appears inside the DGLAP evolution used to obtain $f_{i/p}(x,\mu_F)$ from the fitted PDFs. Changing $\alpha_s(M_Z)$ therefore does not merely rescale a hard matrix element. It can also change the fitted gluon, quark, and sea distributions.

The practical consequence is simple: for precision work, PDF and $\alpha_s$ uncertainties should be propagated with PDF sets designed for that purpose, not guessed from dimensional analysis alone.

## Setup and conventions

We use the scattering and phase-space conventions of this volume. The hadronic observable may be a total cross section, a fiducial cross section, a binned distribution, an efficiency-corrected rate, a normalized distribution, or a template used to extract a parameter.

The default factorized form is

$$
X=
\sum_{i,j}\int dx_1\,dx_2\,
 f_{i/A}(x_1,\mu_F)
 f_{j/B}(x_2,\mu_F)
 \widehat X_{ij}.
$$

The ingredients that must be declared are:

| Ingredient | Why it matters |
|---|---|
| PDF set | Determines the central parton luminosities and uncertainty prescription. |
| Perturbative order | PDFs and matrix elements should normally be matched in order, such as NLO with NLO PDFs. |
| $\alpha_s(M_Z)$ | Sets the normalization and running of the QCD coupling. |
| Heavy-flavor scheme | Controls charm and bottom thresholds and fitted heavy-quark effects. |
| Confidence level | Some Hessian sets are supplied at $68\%$ confidence level, others historically at $90\%$. |
| Error prescription | Hessian, Monte Carlo replica, compressed replica, envelope, or collaboration-specific rule. |
| Scales | $\mu_F$ and $\mu_R$ variations are separate from PDF and $\alpha_s$ variations. |

For current collider analyses, always check the latest recommendations of the relevant experiment, PDF fitting groups, and PDF4LHC working group. The concepts on this page are stable; the recommended datasets and combinations are not frozen forever.

## Parton luminosities

Many hadronic uncertainties are easiest to understand through parton luminosities. For an invariant partonic fraction $\tau=\hat s/s$, define the symmetrized luminosity

$$
\frac{d\mathcal L_{ij}}{d\tau}
=
\frac{1}{1+\delta_{ij}}
\int_\tau^1\frac{dx}{x}
\left[
 f_{i/p}(x,\mu_F)f_{j/p}\!\left(\frac{\tau}{x},\mu_F\right)
+f_{j/p}(x,\mu_F)f_{i/p}\!\left(\frac{\tau}{x},\mu_F\right)
\right].
$$

Then a narrow partonic process is roughly weighted by $d\mathcal L_{ij}/d\tau$ at the corresponding value of $\tau$. This explains why different observables are sensitive to different PDF combinations:

| Observable type | Dominant PDF sensitivity |
|---|---|
| Drell–Yan near the $Z$ pole | quark and antiquark luminosities at moderate $x$ |
| Gluon-fusion Higgs production | gluon luminosity around $x\sim m_H/\sqrt s$ |
| High-mass dileptons or dijets | large-$x$ quarks and gluons |
| Forward vector-boson production | asymmetric small-$x$ and large-$x$ combinations |
| Top-pair production | gluon and quark luminosities, depending on collider energy and kinematics |
| Precision $W$ mass templates | flavor-separated quark PDFs and correlated shape effects |

The uncertainty is therefore not a single universal percentage. It is an observable-dependent projection of a high-dimensional PDF covariance or replica ensemble.

## Hessian PDF uncertainties

Many PDF sets provide a central member and eigenvector variations. If an observable evaluated with the central set is $X_0$, and the two variations along Hessian eigenvector $k$ give $X_k^+$ and $X_k^-$, the common symmetric Hessian estimate is

$$
\Delta X_{\rm PDF}
=
\frac12
\left[
\sum_{k=1}^{N_{\rm eig}}
\left(X_k^+ - X_k^-\right)^2
\right]^{1/2}.
$$

A more careful asymmetric estimate is often useful when the response is nonlinear:

$$
\Delta X^+_{\rm PDF}
=
\left[
\sum_k
\max\left(X_k^+ - X_0,\,X_k^- - X_0,\,0\right)^2
\right]^{1/2},
$$

$$
\Delta X^-_{\rm PDF}
=
\left[
\sum_k
\max\left(X_0 - X_k^+,\,X_0 - X_k^-,\,0\right)^2
\right]^{1/2}.
$$

These formulas assume the error sets and confidence level are interpreted correctly. Some older PDF releases used $90\%$ confidence-level tolerances; combining such results with $68\%$ confidence-level uncertainties without rescaling is a classic small-print trap.

## Replica PDF uncertainties

Monte Carlo replica sets instead provide $N_{\rm rep}$ equally weighted PDF members. Evaluate the observable on each replica to obtain $X_r$. The central value and standard deviation are

$$
\langle X\rangle
=\frac{1}{N_{\rm rep}}\sum_{r=1}^{N_{\rm rep}}X_r,
$$

$$
\Delta X_{\rm PDF}
=
\left[
\frac{1}{N_{\rm rep}-1}
\sum_{r=1}^{N_{\rm rep}}(X_r-\langle X\rangle)^2
\right]^{1/2}.
$$

Replica methods are especially transparent for non-Gaussian distributions and nonlinear observables. Their practical cost is that many predictions must be recomputed. Compressed replica sets and Hessian reductions are designed to keep the information but reduce the computational burden.

## Strong-coupling uncertainty

The $\alpha_s$ uncertainty has an explicit hard-scattering part and an implicit PDF part. For a simple leading-order channel with $X\propto \alpha_s^n$, a first estimate gives

$$
\frac{\Delta X}{X}\simeq n\frac{\Delta\alpha_s}{\alpha_s}.
$$

That estimate is useful for orientation, but it misses the PDF response and higher-order terms. In a global PDF fit, the value of $\alpha_s$ affects scaling violations and therefore the fitted PDFs. A precise propagation uses PDF members fitted at different $\alpha_s(M_Z)$ values, or a combined PDF–$\alpha_s$ ensemble.

A common approximate prescription is

$$
(\Delta X_{\rm PDF+\alpha_s})^2
\simeq
(\Delta X_{\rm PDF})^2+(\Delta X_{\alpha_s})^2,
$$

where $\Delta X_{\alpha_s}$ is obtained using the dedicated $\alpha_s$ variation sets. This quadrature formula is not a theorem of QCD. It is an approximation whose reliability depends on the fit prescription and the observable. When an official combined prescription is supplied, use it.

## PDF, αₛ, and scale uncertainties are different

PDF uncertainty asks: given the data and fitting assumptions, how well do we know the parton densities?

$\alpha_s$ uncertainty asks: how well do we know the strong coupling input, and how does its variation correlate with the PDFs and the hard cross section?

Scale variation asks: how sensitive is a fixed-order truncated perturbative prediction to unphysical scales that would cancel in the all-orders result?

They are not interchangeable. For a final theory prediction, one often reports them separately before combining them. A clear report might read schematically:

$$
X=X_0
{}^{+\Delta_{\rm scale}^+}_{-\Delta_{\rm scale}^-}
{}^{+\Delta_{\rm PDF}^+}_{-\Delta_{\rm PDF}^-}
{}^{+\Delta_{\alpha_s}^+}_{-\Delta_{\alpha_s}^-}
{}^{+\Delta_{\rm param}^+}_{-\Delta_{\rm param}^-}.
$$

Whether to combine these uncertainties linearly, in quadrature, through an envelope, or through a likelihood depends on the experimental and theoretical context.

## Correlations and ratios

Correlations matter whenever observables share the same parton luminosities or the same fitted data. For two observables $X$ and $Y$, the uncertainty of a ratio

$$
R=\frac{X}{Y}
$$

is not obtained by blindly adding relative PDF uncertainties. If the same parton luminosities dominate numerator and denominator, much of the PDF dependence may cancel. If the numerator and denominator probe different $x$ regions or different flavors, the cancellation may be weak or absent.

In a replica method, the correlation coefficient is directly estimated as

$$
\rho_{XY}
=
\frac{
\sum_r (X_r-\langle X\rangle)(Y_r-\langle Y\rangle)
}{
\sqrt{\sum_r (X_r-\langle X\rangle)^2}
\sqrt{\sum_r (Y_r-\langle Y\rangle)^2}
}.
$$

This is one reason to keep the full ensemble information as long as possible in precision fits and template analyses.

## A practical reporting checklist

For a precision observable involving hadrons, report at least the following:

| Item | Example of what to say |
|---|---|
| PDF set | “PDF4LHC21 NNLO Hessian set” or the specific CT, MSHT, NNPDF, or other release. |
| $\alpha_s$ value | “$\alpha_s(M_Z)=\cdots$ as supplied by the PDF set.” |
| Order | LO, NLO, NNLO, N$^3$LO, approximate N$^3$LO, and whether electroweak corrections are included. |
| Flavor scheme | Fixed-flavor, variable-flavor, five-flavor, four-flavor, or process-specific scheme. |
| Error prescription | Hessian symmetric, Hessian asymmetric, replicas, envelope, or combined recommendation. |
| Confidence level | State whether uncertainties are $68\%$ CL, $90\%$ CL, or something else. |
| Correlations | Say whether PDF and $\alpha_s$ correlations are included, neglected, or handled through official sets. |
| Combination rule | Separate, quadrature, envelope, likelihood, nuisance-parameter profiling, or fit-specific treatment. |

This is not bureaucracy. It is the difference between a number that can be compared and a number that merely looks official.

## Common pitfalls

**Using mismatched perturbative orders.** An NNLO hard calculation with an LO PDF set is usually not a precision prediction. There are specialized exceptions, but they require explanation.

**Treating $\alpha_s$ variation as a pure normalization.** It changes partonic coefficients, running, and fitted PDFs.

**Adding everything in quadrature by reflex.** Quadrature assumes approximate independence and Gaussian behavior. PDF fitting, scale variation, and missing-higher-order theory uncertainties do not always satisfy those assumptions.

**Forgetting confidence-level conventions.** A $90\%$ CL Hessian uncertainty is not the same object as a $68\%$ CL one.

**Ignoring PDF correlations in ratios.** Ratios and normalized distributions can be much more precise than their numerator and denominator separately, but only if correlations are propagated.

**Using an old recommendation because it is familiar.** PDF recommendations evolve with new data, new fit methodology, and new perturbative calculations. A historical benchmark is not automatically the current best choice.

**Confusing PDF uncertainty with proton ignorance in general.** A PDF uncertainty is conditional on a fit methodology, datasets, theory settings, and parametrization assumptions. It is not a Platonic error bar on the proton.

## Relations to other pages

- [Fixed-Order Predictions](/perturbative-qft/precision-observables/fixed-order-predictions/) explains where PDF and $\alpha_s$ inputs enter a perturbative prediction.
- [Scale Variation and Uncertainties](/perturbative-qft/precision-observables/scale-variation-and-uncertainties/) explains the separate role of $\mu_R$ and $\mu_F$ variation.
- [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) explains why long-distance PDFs can multiply short-distance hard functions.
- [Jets and Inclusive Observables](/perturbative-qft/infrared-physics-factorization/jets-and-inclusive-observables/) gives examples where PDF sensitivity and infrared safety meet.
- [Coupling Renormalization](/perturbative-qft/renormalized-perturbation-theory/coupling-renormalization/) explains why $\alpha_s$ runs and why its value must be specified at a reference scale.
- [Electroweak Corrections](/perturbative-qft/precision-observables/electroweak-corrections/) discusses photon PDFs and mixed QCD–electroweak effects.

## Research status

**Established:** Collinear factorization, DGLAP evolution, global PDF fitting, Hessian and replica uncertainty propagation, and dedicated $\alpha_s$ variation sets are standard components of collider precision predictions.

**Active:** Modern PDF uncertainty treatment includes correlated experimental systematics, methodology uncertainty, heavy-flavor schemes, photon PDFs, nuclear corrections, small-$x$ questions, missing higher-order theory uncertainties in the fit, and joint interpretation with precision measurements such as $W$ mass, Higgs rates, top production, and high-mass tails.

**Speculative:** The basic uncertainty-propagation framework is not speculative. More ambitious global likelihood combinations of experimental, PDF, $\alpha_s$, and perturbative theory uncertainties remain methodology-dependent.

## Exercises

### Exercise 1: Leading αₛ sensitivity

Suppose a leading-order observable behaves as $X=C\alpha_s^2$ when PDFs are held fixed. Show that a small coupling variation gives $\Delta X/X\simeq 2\Delta\alpha_s/\alpha_s$.

<details>
<summary><strong>Solution</strong></summary>

Taking the logarithm,

$$
\log X=\log C+2\log\alpha_s.
$$

For a small variation at fixed $C$,

$$
\frac{\Delta X}{X}
=2\frac{\Delta\alpha_s}{\alpha_s}.
$$

This is only the explicit hard-scattering sensitivity. In a real PDF fit, $C$ is not fixed because the PDFs and their evolution also depend on the value of $\alpha_s$.

</details>

### Exercise 2: Hessian uncertainty

A one-eigenvector PDF set gives $X_0=100$, $X^+=104$, and $X^-=98$. Compute the symmetric Hessian PDF uncertainty.

<details>
<summary><strong>Solution</strong></summary>

For one eigenvector,

$$
\Delta X_{\rm PDF}
=\frac12|X^+-X^-|.
$$

Therefore

$$
\Delta X_{\rm PDF}
=\frac12|104-98|=3.
$$

The result is $X=100\pm3$ in the confidence-level convention of the PDF set.

</details>

### Exercise 3: Replica uncertainty

Four replicas give $X_r=98,100,103,99$. Compute the replica mean and standard deviation.

<details>
<summary><strong>Solution</strong></summary>

The mean is

$$
\langle X\rangle=\frac{98+100+103+99}{4}=100.
$$

The sample variance is

$$
\frac{1}{3}\left[(-2)^2+0^2+3^2+(-1)^2\right]
=\frac{14}{3}.
$$

Thus

$$
\Delta X=\sqrt{\frac{14}{3}}\simeq2.16.
$$

</details>

### Exercise 4: Correlated ratio

Let two observables have fractional PDF uncertainties $\delta_X$ and $\delta_Y$ and correlation coefficient $\rho$. Show that the fractional uncertainty of $R=X/Y$ is

$$
\delta_R^2=\delta_X^2+\delta_Y^2-2\rho\delta_X\delta_Y.
$$

<details>
<summary><strong>Solution</strong></summary>

For small variations,

$$
\frac{\Delta R}{R}=\frac{\Delta X}{X}-\frac{\Delta Y}{Y}.
$$

Squaring and averaging gives

$$
\delta_R^2
=\left\langle
\left(\frac{\Delta X}{X}-\frac{\Delta Y}{Y}\right)^2
\right\rangle.
$$

Using

$$
\left\langle\frac{\Delta X}{X}\frac{\Delta Y}{Y}\right\rangle
=\rho\delta_X\delta_Y,
$$

one obtains

$$
\delta_R^2=\delta_X^2+\delta_Y^2-2\rho\delta_X\delta_Y.
$$

If $\rho\simeq1$ and $\delta_X\simeq\delta_Y$, the ratio is much better determined than the two observables separately.

</details>

### Exercise 5: Factorization scale versus PDF uncertainty

Explain why varying $\mu_F$ is not the same as varying the PDF error sets.

<details>
<summary><strong>Solution</strong></summary>

Varying $\mu_F$ probes the residual dependence of a truncated perturbative prediction on the arbitrary scale that separates long-distance PDFs from short-distance coefficients. In the all-orders prediction this dependence cancels between PDFs and hard functions.

PDF error sets instead represent uncertainty in the fitted PDFs at fixed theory settings and fitted data. They describe imperfect knowledge of the parton densities, not the missing higher-order terms in the hard scattering. Both affect the prediction, but they answer different questions.

</details>

## References

- PDF4LHC Working Group, *The PDF4LHC21 Combination of Global PDF Fits for the LHC Run III*, for modern combined PDF recommendations and uncertainty propagation.
- S. Navas et al. (Particle Data Group), *Review of Particle Physics*, especially the reviews on Quantum Chromodynamics and structure functions.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 20, 26, and 32, for infrared divergences, QCD, PDFs, and factorization.
- R. D. Ball et al. and the NNPDF Collaboration papers, for Monte Carlo replica methods and neural-network PDF fitting.
- T.-J. Hou et al., *New CTEQ Global Analysis of Quantum Chromodynamics with High-Precision Data from the LHC*, for CT18 methodology and global-fit uncertainties.
- S. Bailey et al., *Parton Distributions from LHC, HERA, Tevatron and Fixed Target Data: MSHT20 PDFs*, for MSHT methodology and uncertainties.
- M. Botje et al., *The PDF4LHC Working Group Interim Recommendations*, and J. Butterworth et al., *PDF4LHC Recommendations for LHC Run II*, for historical uncertainty prescriptions.
- A. Buckley et al., *LHAPDF6: Parton Density Access in the LHC Precision Era*, for the standard library interface used to access PDF sets.

## Version history

- **2026-06-13:** Initial polished draft. Added factorized prediction formula, Hessian and replica propagation formulas, $\alpha_s$ variation logic, correlation discussion, reporting checklist, solved exercises, and one summary figure.
