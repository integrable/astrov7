---
title: "Analytic-Numerical Bridges"
description: "How analytic bootstrap results and numerical bootstrap computations inform each other through large-spin data, asymptotic constraints, extremal spectra, and reliability checks."
sidebar:
  label: "Analytic-Numerical Bridges"
  order: 12
level: Advanced
status: "Polished draft"
source: "Poland, Rychkov, and Vichi 2019; Rychkov and Su 2024; Caron-Huot; Alday; analytic and numerical bootstrap literature."
topics:
  - analytic conformal bootstrap
  - numerical conformal bootstrap
  - large spin
  - extremal spectra
  - bootstrap reliability
canonicalTopics:
  - analytic-numerical-bridges
  - bootstrap-methods-interface
  - large-spin-numerical-bootstrap
researchStatus:
  established:
    - "Analytic and numerical bootstrap methods are complementary: analytic results control asymptotic CFT data while numerical methods constrain finite-dimensional regions and low-lying spectra."
  active:
    - "Current research uses analytic input to improve numerical searches and numerical data to test finite-spin extrapolations, islands, spectra, and large-N or holographic predictions."
---

## Summary

The **analytic bootstrap** and the **numerical bootstrap** are two ways of using the same crossing equations.

Numerical bootstrap turns crossing into finite optimization problems. It is excellent at excluding parameter regions, finding islands, and constraining low-lying CFT data.

Analytic bootstrap studies special limits of crossing. It is excellent at deriving universal large-spin behavior, asymptotic spectra, Regge constraints, inversion formulas, and averaged high-energy data.

The bridge is this:

$$
\text{analytic bootstrap controls limits},
\qquad
\text{numerical bootstrap controls finite regions}.
$$

Together they give a more complete picture than either method alone. Analytic results help numerical computations handle high spin, interpret kinks, test extremal spectra, and choose physical assumptions. Numerical results test analytic formulas at finite spin, discover unexpected structures, and provide nonperturbative data where analytic expansions are only asymptotic.

The slogan is

$$
\text{analytics explains the tails; numerics corners the body}.
$$

Tiny zoology of CFTs, but accurate.

## Prerequisites

Read the [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/) chapter and the [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) chapter first.

The most important pages are [Lightcone Bootstrap](/cft-bootstrap/analytic-bootstrap/lightcone-bootstrap/), [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/), [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/), [Derivative Truncations](/cft-bootstrap/numerical-bootstrap/derivative-truncations/), [Extremal Functional Method](/cft-bootstrap/numerical-bootstrap/extremal-functional-method/), and [Error Bars and Reliability](/cft-bootstrap/numerical-bootstrap/error-bars-and-reliability/).

## Core idea

A CFT is described by its spectrum and OPE coefficients. Numerical bootstrap studies whether candidate data can satisfy crossing, unitarity, and assumptions. Analytic bootstrap derives unavoidable structures in special limits.

The same crossing equation sits underneath both:

$$
\sum_{\mathcal O}a_{\mathcal O}\,F_{\Delta,\ell}(u,v)=0.
$$

Numerics projects this equation onto finitely many derivative constraints. Analytics studies singular limits such as lightcone, Regge, large-spin, or high-temperature limits.

The bridge is strongest when the two methods talk about the same CFT data:

| CFT data | Analytic viewpoint | Numerical viewpoint |
|---|---|---|
| low-lying scalar dimensions | hard, theory-dependent | directly bounded and islanded |
| large-spin double twist | universal asymptotics | high-spin consistency and spectrum tails |
| OPE coefficients | asymptotic or averaged formulas | finite-dimensional bounds and extraction |
| stress-tensor data | Ward identities and causality | $C_T$ bounds and mixed-correlator constraints |
| gaps | input to asymptotic or holographic regimes | assumptions that shrink islands |
| Regge behavior | controls inversion and causality | informs high-spin treatment and reliability |

The useful question is not “analytic or numerical?” It is “which part of the data is each method controlling?”

## High spin in numerical bootstrap

Numerical bootstrap computations must handle infinitely many spins. In scalar systems, the allowed spins may be

$$
\ell=0,2,4,\ldots .
$$

A finite computation treats some spins explicitly and relies on asymptotic control for the rest. Analytic bootstrap supplies precisely this kind of high-spin understanding.

The lightcone bootstrap predicts double-twist families

$$
[\phi\phi]_{n,\ell},
\qquad
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell+\gamma_{n,\ell},
$$

with

$$
\gamma_{n,\ell}\to0
\qquad
(\ell\to\infty).
$$

This helps explain why high-spin spectra in numerical extremal solutions often look mean-field-like. It also guides large-spin truncation tests: if the high-spin tail behaves wildly, either the assumptions, numerical precision, or interpretation need attention.

Analytic large-spin data do not replace the finite numerical problem, but they make the infinite spin tail less mysterious.

## Extremal spectra and large-spin tails

The extremal functional method extracts candidate spectra from zeros of an optimal numerical functional. At low spin, these zeros are strongly theory-dependent. At high spin, analytic bootstrap predicts universal organization.

A good extremal spectrum should often show:

1. low-lying operators characteristic of the target CFT;
2. stress tensor and currents in the correct sectors;
3. double-twist families at large spin;
4. anomalous dimensions compatible with low-twist exchange;
5. OPE coefficients approaching asymptotic expectations.

For example, if a scalar operator of twist $\tau_s$ is the leading non-identity crossed-channel exchange, then analytic bootstrap predicts large-spin corrections of order

$$
\gamma_{n,\ell}^{(s)}\sim J^{-\tau_s}.
$$

A numerical spectrum near a stable boundary can be checked against this tail. Agreement is not a proof, but it is a strong consistency check. Disagreement is a clue, and sometimes a very loud one.

## Kinks and analytic structure

Numerical bounds often show kinks. Analytic bootstrap helps interpret them, but does not automatically explain every kink.

A kink may arise when the extremal solution changes operator content, when a protected or conserved operator becomes important, when a free or generalized-free solution sits on a boundary, or when a low-twist operator controls a change in large-spin behavior.

Analytic tools can test these possibilities by asking:

- What low-twist operators would control the large-spin tail near the kink?
- Does the extremal spectrum contain expected double-twist families?
- Are stress-tensor and current contributions consistent with Ward identities?
- Does Lorentzian inversion predict a trajectory compatible with the numerical data?
- Is the kink stable as the derivative cutoff increases?

The point is not to turn a kink into a theorem by vibes. The point is to replace “sharp corner!” with spectral diagnostics.

## Islands and gap assumptions

Numerical islands usually require assumptions: external operator ordering, sector gaps, uniqueness of conserved operators, or absence of low-dimension operators. Analytic bootstrap helps make those assumptions physically meaningful.

For example, in an ordinary critical point one may assume that the next singlet scalar is irrelevant:

$$
\Delta_{S,0}^{\rm next}>d.
$$

Analytic RG and large-spin reasoning can support this kind of assumption when it matches the expected relevant-operator count or low-twist spectrum.

In large-$N$ or holographic CFTs, analytic bootstrap predicts double-trace towers and gaps to higher-spin single-trace operators. These predictions can motivate numerical assumptions such as sparse spectra or large central charge.

The rule is:

$$
\text{analytic input can motivate gaps, but the final island remains conditional on them}.
$$

Assumptions do not become free just because they have a nice asymptotic accent.

## Large-N tests

Large-$N$ analytic bootstrap predicts that leading connected correlators perturb generalized free field data. Double-trace operators have dimensions

$$
\Delta_{n,\ell}=\Delta_1+\Delta_2+2n+\ell+N^{-p}\gamma_{n,\ell}^{(1)}+\cdots .
$$

Numerical bootstrap can test this structure at finite $N$ or finite central charge. One can ask whether allowed regions approach generalized-free data, whether double-trace families appear in extremal spectra, and whether stress-tensor exchange produces the expected large-spin tail.

This is especially useful for gauge-theory CFTs, where analytic expansions may be asymptotic or limited to special regimes. Numerical bounds can reveal whether a proposed large-$N$ picture survives at small or moderate $N$.

The bridge is two-way:

$$
\text{large-}N\text{ analytics gives a map},
\qquad
\text{numerics checks the terrain}.
$$

## Lorentzian inversion as a diagnostic

The Lorentzian inversion formula reconstructs spin-dependent CFT data from the double discontinuity:

$$
c(\Delta,J)\sim\int dz\,d\bar z\;K_{\Delta,J}(z,\bar z)\,\operatorname{dDisc}\mathcal G(z,\bar z).
$$

This gives analytic trajectories in spin above a Regge-controlled threshold. Numerical data can be compared to these trajectories.

Useful diagnostics include:

| Diagnostic | What it tests |
|---|---|
| large-spin anomalous dimensions | low-twist crossed-channel exchange |
| OPE coefficient tails | normalization and block conventions |
| convexity of twist trajectories | unitarity and causality expectations |
| stress-tensor contribution | Ward identity and $C_T$ consistency |
| finite-spin deviations | size of low-spin ambiguity or mixing |

When numerical extraction and inversion agree in their shared regime, confidence grows. When they disagree, the issue may be finite cutoff, mixing, wrong assumptions, or an overextended analytic approximation.

## Tauberian and averaged checks

Tauberian methods control averaged high-energy or high-dimension data. Numerical bootstrap usually focuses on low-lying dimensions and OPE coefficients. These may seem far apart, but they can meet through consistency checks.

For example, a numerical solution should not imply high-dimension OPE growth incompatible with known Euclidean OPE convergence or thermal asymptotics. Conversely, Tauberian results can give coarse expectations for spectral density or averaged OPE behavior beyond the range where numerical spectrum extraction is reliable.

The relation is not usually a direct point-by-point comparison. It is a consistency envelope:

$$
\text{low data from numerics}
\quad\text{must fit inside}\quad
\text{asymptotic constraints from analytics}.
$$

This is especially important in holographic or thermal contexts, where high-energy density and black-hole-like behavior can constrain what low-energy spectra are plausible.

## How analytic input improves computations

Analytic information can improve numerical bootstrap in practical ways:

| Analytic input | Numerical use |
|---|---|
| unitarity bounds | baseline positivity constraints |
| Ward identities | normalize stress tensors and currents |
| large-spin asymptotics | guide spin truncation and tail checks |
| known protected operators | isolate contributions in mixed systems |
| Regge boundedness | motivate assumptions and inversion thresholds |
| generalized-free data | benchmark block generation and extremal spectra |
| large-$N$ scaling | choose coordinates and expected island shape |
| Tauberian estimates | check high-dimension consistency |

The best numerical studies often contain analytic fingerprints everywhere: in the assumptions, in the expected spectra, in the reliability checks, and in the interpretation.

## How numerical data improves analytics

Numerical bootstrap also feeds analytic work. It can reveal structures before analytic formulas explain them.

Examples of numerical-to-analytic feedback include:

- kinks suggesting special CFTs;
- islands identifying operator dimensions with high precision;
- extremal spectra suggesting double-twist trajectories;
- observed level repulsion motivating finite-spin analytic questions;
- bounds on irrelevant operators testing RG expectations;
- finite-$N$ data testing large-$N$ predictions;
- numerical counterexamples warning against overgeneral analytic claims.

Numerics is a discovery engine. Analytics is often the explanation engine. The fun begins when they disagree politely enough to teach us something.

## Common pitfalls

**Do not use analytic asymptotics as exact finite-spin data.** Large-spin formulas can be excellent guides and terrible low-spin laws.

**Do not call numerical allowed regions existence proofs.** Numerical bootstrap excludes; it does not automatically construct a full CFT.

**Do not impose analytic expectations as hidden assumptions.** If a large-$N$ gap or operator ordering is assumed, state it.

**Do not compare OPE coefficients across methods without matching normalization.** Analytic and numerical conventions often differ.

**Do not ignore mixing.** Both extremal spectra and large-spin formulas can hide degenerate operator families.

**Do not treat Regge boundedness as a decorative hypothesis.** It controls inversion thresholds and low-spin ambiguities.

**Do not confuse agreement in a tail with proof of the full spectrum.** Asymptotic consistency is powerful but partial.

## Relations to other pages

This page closes the [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/) chapter and points back to the [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) chapter.

For analytic input, see [Lightcone Bootstrap](/cft-bootstrap/analytic-bootstrap/lightcone-bootstrap/), [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/), [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/), and [Tauberian and Asymptotic Methods](/cft-bootstrap/analytic-bootstrap/tauberian-and-asymptotic-methods/).

For numerical output, see [Kinks, Islands, and Gaps](/cft-bootstrap/numerical-bootstrap/kinks-islands-and-gaps/), [Mixed-Correlator Systems](/cft-bootstrap/numerical-bootstrap/mixed-correlator-systems/), [Extremal Functional Method](/cft-bootstrap/numerical-bootstrap/extremal-functional-method/), and [Error Bars and Reliability](/cft-bootstrap/numerical-bootstrap/error-bars-and-reliability/).

The next chapter, [Holographic CFT](/cft-bootstrap/holographic-cft/), uses many of these bridges in the large-$N$ and AdS setting.

## Research status

The complementarity between analytic and numerical bootstrap is established and central to modern CFT practice. Analytic large-spin results, Lorentzian inversion, and numerical mixed-correlator bootstrap are all mature tools.

Active research is sharpening their interface: incorporating analytic high-spin data into numerical workflows, using numerical islands to test finite-spin inversion, extracting spectra more reliably, controlling large-$N$ mixing, and building hybrid methods for holographic, gauge-theory, defect, and supersymmetric CFTs.

## Exercises

### Exercise 1

Give one example of analytic input that helps numerical bootstrap.

<details><summary><strong>Solution</strong></summary>

One example is large-spin asymptotics. Analytic bootstrap predicts that double-twist families have

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell+\gamma_{n,\ell},
\qquad
\gamma_{n,\ell}\to0.
$$

This helps numerical studies interpret high-spin extremal spectra and check spin truncation reliability.

</details>

### Exercise 2

Give one example of numerical data that helps analytic bootstrap.

<details><summary><strong>Solution</strong></summary>

A numerical kink or island can identify a candidate CFT and provide approximate low-lying dimensions and OPE coefficients. Analytic work can then try to explain the observed spectrum, large-spin trajectories, or finite-spin deviations using lightcone bootstrap, inversion formulas, or large-$N$ expansions.

</details>

### Exercise 3

Why should one be cautious when comparing large-spin formulas to spin-zero operators?

<details><summary><strong>Solution</strong></summary>

Large-spin formulas are asymptotic expansions in inverse conformal spin $J$. Spin-zero operators are far from the controlled large-$J$ regime. They may be affected by mixing, low-spin ambiguities, contact terms, or non-asymptotic dynamics. Extrapolation can be useful, but it is not automatic.

</details>

### Exercise 4

How can extremal functional spectra be checked using analytic bootstrap?

<details><summary><strong>Solution</strong></summary>

At high spin, extremal spectra should often organize into double-twist families. Their anomalous dimensions and OPE coefficients can be compared with analytic predictions from low-twist crossed-channel exchange. Stability of this agreement as the numerical cutoff increases is a useful reliability check.

</details>

### Exercise 5

Why are gap assumptions part of the analytic-numerical bridge?

<details><summary><strong>Solution</strong></summary>

Numerical islands often require spectral gaps. Analytic physics, such as relevant-operator counting, large-$N$ sparseness, or protected-sector structure, can motivate those gaps. But the final numerical result remains conditional on the assumptions. The bridge helps choose and test gaps; it does not make them assumption-free.

</details>

## References

- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- L. F. Alday, “Large spin perturbation theory for conformal field theories,” *Physical Review Letters* **119** (2017).
- A. L. Fitzpatrick, J. Kaplan, D. Poland, and D. Simmons-Duffin, “The analytic bootstrap and AdS superhorizon locality,” *Journal of High Energy Physics* **2013**.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.

## Version history

- 2026-07-01: First polished draft. Added comparison of analytic and numerical bootstrap, high-spin and extremal-spectrum bridges, kink and island interpretation, large-$N$ tests, inversion and Tauberian diagnostics, pitfalls, exercises, and references.
