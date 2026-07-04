---
title: "Analytic Conformal Bootstrap"
description: "Chapter overview for analytic conformal bootstrap methods in the CFT and Bootstrap volume."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Komargodski and Zhiboedov; Fitzpatrick, Kaplan, Poland, and Simmons-Duffin; Caron-Huot; Alday; Simmons-Duffin TASI lectures; Poland, Rychkov, and Vichi 2019."
topics:
  - analytic conformal bootstrap
  - lightcone bootstrap
  - large spin
  - Lorentzian inversion
  - crossing symmetry
canonicalTopics:
  - analytic-conformal-bootstrap
  - lightcone-bootstrap
  - lorentzian-cft-data
researchStatus:
  established:
    - "Analytic bootstrap methods derive universal large-spin and lightcone CFT data from crossing symmetry, unitarity, and Lorentzian analyticity."
  active:
    - "Current research extends analytic bootstrap to finite spin, spinning correlators, defects, thermal systems, Mellin amplitudes, Regge limits, nonunitary theories, and holographic CFT data."
---

Analytic Conformal Bootstrap is the chapter where crossing symmetry is used as an analytic tool rather than only as a numerical constraint. The goal is to derive universal information about CFT spectra and OPE coefficients from special limits of correlation functions.

The central idea is that some regions of cross-ratio space are dominated by a small set of operators. Crossing then forces infinite families of operators in the crossed channel. This is the origin of large-spin double-twist families, lightcone expansions, Lorentzian inversion, and many modern results about holographic CFT data.

The chapter is the bridge from numerical bootstrap to Lorentzian CFT. Numerical bootstrap asks whether a spectrum is allowed. Analytic bootstrap asks what crossing forces asymptotically and, in favorable cases, how to reconstruct CFT data from discontinuities, Regge behavior, and light-ray operators.

## Prerequisites

You should know [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/), [Operator Product Expansion](/cft-bootstrap/operator-product-expansion/), [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), [Higher-Dimensional CFT](/cft-bootstrap/higher-dimensional-cft/), and the [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) chapter.

The most important concrete prerequisites are the cross-ratios

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z),
$$

the conformal block expansion of scalar four-point functions, and the meaning of twist:

$$
\tau=\Delta-\ell.
$$

For later pages, comfort with complex analysis, contour deformation, branch cuts, and Lorentzian operator ordering will help. The chapter introduces the physics first and postpones the hardest analytic details until they are needed.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Lightcone Bootstrap](/cft-bootstrap/analytic-bootstrap/lightcone-bootstrap/) | The basic crossing argument forcing large-spin double-twist operators. |
| 2 | [Large-Spin Perturbation Theory](/cft-bootstrap/analytic-bootstrap/large-spin-perturbation-theory/) | How anomalous dimensions and OPE coefficients are expanded at large spin. |
| 3 | [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/) | The operator families $[\mathcal O_1\mathcal O_2]_{n,\ell}$ and their asymptotic data. |
| 4 | [Anomalous Dimensions from Crossing](/cft-bootstrap/analytic-bootstrap/anomalous-dimensions-from-crossing/) | How exchanged low-twist operators generate corrections to double-twist dimensions. |
| 5 | [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/) | How CFT data at spin greater than one are reconstructed from double discontinuities. |
| 6 | [Double Discontinuity](/cft-bootstrap/analytic-bootstrap/double-discontinuity/) | The positive Lorentzian object that appears in inversion and dispersion relations. |
| 7 | [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/) | High-energy Lorentzian limits, bounded growth, and causality constraints. |
| 8 | [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/) | The Mellin-amplitude language, especially useful for holographic CFTs. |
| 9 | [Polyakov Bootstrap](/cft-bootstrap/analytic-bootstrap/polyakov-bootstrap/) | Crossing-symmetric expansions and sum rules that avoid channel-by-channel artifacts. |
| 10 | [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/) | Perturbation around generalized free fields and AdS effective interactions. |
| 11 | [Tauberian and Asymptotic Methods](/cft-bootstrap/analytic-bootstrap/tauberian-and-asymptotic-methods/) | How averaged high-energy CFT data follow from singularities and positivity. |
| 12 | [Analytic-Numerical Bridges](/cft-bootstrap/analytic-bootstrap/analytic-numerical-bridges/) | How analytic constraints improve numerical bootstrap and explain numerical features. |

The early pages are about universal large-spin structure. The middle pages are about Lorentzian inversion and discontinuities. The later pages connect analytic bootstrap to holography, numerical methods, and asymptotic spectral theory.

## Landmarks

| Landmark | Meaning | Where it appears |
|---|---|---|
| twist $\tau=\Delta-\ell$ | Dimension minus spin; controls lightcone singularities. | Lightcone bootstrap. |
| double-twist family $[\mathcal O_1\mathcal O_2]_{n,\ell}$ | Operators with dimensions approaching $\Delta_1+\Delta_2+2n+\ell$ at large spin. | Large-spin perturbation theory. |
| lightcone limit | Limit where one cross-ratio becomes small while another approaches a channel singularity. | First analytic-bootstrap argument. |
| minimal twist | Lowest twist operator in a channel; controls leading crossed-channel corrections. | Anomalous dimensions. |
| anomalous dimension $\gamma_{n,\ell}$ | Deviation from additive double-twist dimension. | Large-spin expansions. |
| conformal spin $J$ | Natural large-spin variable for asymptotic expansions. | Large-spin perturbation theory. |
| double discontinuity | Lorentzian discontinuity combination with positivity properties. | Inversion formula. |
| Lorentzian inversion formula | Reconstructs CFT data from double discontinuities. | Central modern tool. |
| Regge boundedness | Growth condition in Lorentzian high-energy limits. | Causality and inversion. |
| Mellin amplitude | CFT analogue of scattering amplitude variables. | Holographic bootstrap. |
| Polyakov block | Crossing-symmetric exchange object. | Polyakov bootstrap. |

The chapter's biggest conceptual landmark is the move from Euclidean symmetry constraints to Lorentzian analytic structure.

## Common confusions

**Analytic bootstrap is not only exact solutions.** Many results are asymptotic, perturbative, or averaged. That is a strength, not a defect.

**Large spin is not the same as large dimension.** The expansion is organized by spin or conformal spin, often at fixed radial excitation number $n$.

**Double-twist does not mean literal double-trace.** In large-$N$ theories the language overlaps, but generic CFTs also have double-twist families forced by crossing.

**The lightcone limit is not just the OPE limit.** It combines an OPE limit in one channel with a singular crossed-channel regime.

**Lorentzian inversion is not a numerical inversion of a finite table.** It is an analytic formula involving double discontinuities and integration over Lorentzian kinematics.

**The identity operator is not the whole story.** Identity exchange gives the leading large-spin double-twist spectrum; other low-twist operators give anomalous dimensions and OPE corrections.

**Finite spin is harder.** Many analytic formulas are safest at large spin or above a spin threshold. Extrapolating to spin zero is often useful but not automatically justified.

## Boundaries

This chapter focuses on analytic consequences of crossing, unitarity, lightcone limits, Lorentzian analyticity, and large-spin expansions.

It does not replace the [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) chapter. Numerical methods produce rigorous-looking finite-cutoff bounds and islands; analytic methods explain universal structures and asymptotic data.

It does not replace the [Holographic CFT](/cft-bootstrap/holographic-cft/) chapter. Holography uses analytic bootstrap heavily, but bulk effective field theory, AdS diagrams, black holes, and quantum gravity interpretations belong there.

It does not replace the [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) and Virasoro chapters. Two-dimensional CFT has extra chiral symmetry and exact methods; analytic bootstrap in higher dimensions uses a different toolkit, even when ideas rhyme.

It does not claim every CFT datum is analytically accessible. Generic finite-spin spectra and arbitrary OPE coefficients remain hard. The power of the chapter is in universal limits and controlled perturbations.

## Where to go next

After this chapter, go to [Holographic CFT](/cft-bootstrap/holographic-cft/) for AdS interpretations of large-$N$ analytic bootstrap, Mellin amplitudes, and bulk locality.

Return to [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) to see how analytic results inform gaps, extremal spectra, asymptotic spin treatment, and interpretation of islands.

For Lorentzian physics, continue to [Thermal and Lorentzian CFT](/cft-bootstrap/thermal-lorentzian-cft/), where causality, chaos, light-ray operators, and thermal correlators become central.

For statistical applications, connect back to [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/) and [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/), where large-spin operators and low-twist exchanges organize real CFT spectra.

## References

- A. L. Fitzpatrick, J. Kaplan, D. Poland, and D. Simmons-Duffin, “The analytic bootstrap and AdS superhorizon locality,” *Journal of High Energy Physics* **2013**.
- Z. Komargodski and A. Zhiboedov, “Convexity and liberation at large spin,” *Journal of High Energy Physics* **2013**.
- L. F. Alday, “Large spin perturbation theory for conformal field theories,” *Physical Review Letters* **119** (2017).
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.

## Version history

- 2026-07-01: Replaced scaffold with a polished chapter overview. Added prerequisites, reading path, landmarks, common confusions, boundaries, next routes, references, and version history.
