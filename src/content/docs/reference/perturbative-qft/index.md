---
title: "Perturbative QFT and Scattering"
description: "Graduate-level overview of perturbative QFT as a calculation engine for amplitudes, Green functions, decay rates, cross sections, loop corrections, infrared-safe observables, and precision predictions."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki 2007; Coleman 2019; Weinberg 1995; Zee 2010; Schwartz 2014; Zinn-Justin 2021"
topics:
  - perturbative QFT
  - scattering amplitudes
  - Feynman diagrams
  - LSZ reduction
  - phase space
  - loop integrals
  - renormalized amplitudes
  - infrared physics
  - precision observables
canonicalTopics:
  - perturbative-qft-and-scattering
  - amplitudes-and-observables
  - diagrammatic-expansion
  - scattering-technology
researchStatus:
  established:
    - "The perturbative expansion, Feynman rules, LSZ reduction, phase-space formulas, loop regularization, renormalized amplitudes, and basic scattering observables are standard parts of relativistic quantum field theory."
    - "The normalization of amplitudes, states, spin sums, color factors, and phase space is convention-sensitive; this volume uses the qft.org scattering conventions throughout."
  active:
    - "Multi-loop amplitudes, infrared subtraction and resummation, factorization, precision collider observables, generalized unitarity, positive geometry, double-copy structures, and celestial reorganizations of scattering data remain active research areas."
---

## Summary

**Perturbative QFT and Scattering** is the volume of QFT.org where the formal language of quantum fields becomes a calculation engine.

The central question is:

> Given a Lagrangian and a regime in which expansion around a solvable theory is meaningful, how do we compute amplitudes, rates, cross sections, loop corrections, infrared-safe observables, and precision predictions?

The basic pipeline is

$$
\mathcal L
\longrightarrow
\text{correlators}
\longrightarrow
\text{diagrams}
\longrightarrow
\mathcal M
\longrightarrow
\Gamma,\ \sigma,\ \text{distributions}.
$$

Here $\mathcal M$ is an invariant amplitude, $\Gamma$ is a decay rate, and $\sigma$ is a cross section. The first half of the pipeline is formal. The second half is measurable. This volume is about keeping the bridge between them precise.

:::note[What makes a calculation trustworthy]
A perturbative calculation should state the observable, the external states, the normalization convention, the diagrams or cuts included, the approximation order, the regulator and scheme if loops appear, the gauge or infrared caveats if relevant, and the checks that make the answer credible.
:::

## What this volume teaches

Foundations explains what fields, propagators, Wick contractions, and path integrals are. This volume explains how to use those objects to compute.

| Theme | What you learn to do |
|---|---|
| Scattering theory | Relate in/out states, the $S$-matrix, the $T$-matrix, connected amplitudes, and observables. |
| LSZ reduction | Extract on-shell scattering amplitudes from poles of time-ordered correlation functions. |
| Diagrammatics | Move from Wick contractions and source functionals to position-space and momentum-space Feynman rules. |
| Tree amplitudes | Compute first amplitudes in scalar theory, Yukawa theory, QED, and Yang–Mills theory. |
| Phase space | Convert $\mathcal M$ into decay rates, differential cross sections, and inclusive observables. |
| Loop expansion | Organize perturbation theory by loop order and recognize where ultraviolet divergences enter. |
| Loop integral technology | Use parameters, tensor reduction, integration-by-parts identities, master integrals, discontinuities, and singularity analysis. |
| Renormalized perturbation theory | Combine loops and counterterms into finite scheme-defined amplitudes. |
| Gauge-theory perturbation theory | Use gauge fixing, ghosts, Ward identities, color factors, and gauge-parameter checks correctly. |
| Infrared physics | Distinguish soft and collinear singularities from ultraviolet divergences and define infrared-safe observables. |
| Unitarity and analyticity | Use optical theorems, cuts, discontinuities, thresholds, dispersion relations, and partial waves. |
| Modern on-shell amplitudes | Reorganize calculations using spinor-helicity variables, color ordering, recursion, generalized unitarity, soft limits, and double-copy ideas. |
| Form factors and composite operators | Compute matrix elements of local operators between states, including currents and stress tensors. |
| Precision observables | Understand how fixed-order terms, real radiation, factorization, resummation, parton showers, and uncertainty estimates fit together. |
| Computational workflows | Make symbolic, diagrammatic, loop-reduction, phase-space, and benchmark calculations reproducible. |

The short slogan is:

```txt
Foundations explains why diagrams exist.
Perturbative QFT explains how diagrams become predictions.
```

## Prerequisites

You should know the qft.org [Conventions and Normalizations](/foundations/conventions-and-normalizations/), especially the metric, Fourier phases, state normalization, and propagator conventions. You should also be comfortable with [Fock Space](/foundations/relativistic-particles-and-fields/fock-space/), [Free Relativistic Fields](/foundations/free-fields/), [Correlation Functions and Propagators](/foundations/correlators-and-propagators/), [Path Integral Formalism](/foundations/path-integral-formalism/), and [Interactions and Wick Expansion](/foundations/interactions-and-wick-expansion/).

Readers who want to begin calculating quickly can start with [Conventions and Notation](/perturbative-qft/conventions/), then follow the [Roadmap](/perturbative-qft/roadmap/). The early chapters are written so that scalar scattering and two-body phase space become available before the loop and gauge-theory chapters.

You do not need to know advanced renormalization, QCD factorization, multi-loop methods, collider phenomenology, or modern amplitude geometry before starting. Those appear later, with status labels and cross-links.

## Default conventions

This volume uses the qft.org mostly-minus convention

$$
\eta_{\mu\nu}=\operatorname{diag}(+,-,-,-),
\qquad
\hbar=c=1,
$$

with plane waves $e^{-ip\cdot x}$ and covariantly normalized one-particle states. The companion page [Conventions and Notation](/perturbative-qft/conventions/) fixes the scattering-specific choices.

The two formulas to keep nearby are

$$
\langle \mathbf p',s'\mid \mathbf p,s\rangle
=(2\pi)^3 2E_{\mathbf p}\,
\delta^{(3)}(\mathbf p-\mathbf p')\delta_{ss'},
$$

and

$$
\langle f\mid iT\mid i\rangle
=
i(2\pi)^4\delta^{(4)}(P_f-P_i)\mathcal M_{fi},
\qquad
S=\mathbf 1+iT.
$$

Once these are fixed, the phase-space and flux formulas are no longer negotiable decoration. They are part of the definition of the observable.

## Chapter map

| Chapter | Role |
|---|---|
| [From Correlators to the S-Matrix](/perturbative-qft/from-correlators-to-s-matrix/) | Builds the bridge from Green functions to in/out states, $S=\mathbf 1+iT$, LSZ, external-leg normalization, crossing, and optical-theorem previews. |
| [Diagrammatics and Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/) | Develops perturbative expansion, Wick recaps, generating functionals, symmetry factors, momentum-space rules, vertices, propagators, connected diagrams, 1PI diagrams, and counterterm previews. |
| [Tree-Level Scattering](/perturbative-qft/tree-level-scattering/) | Computes first tree amplitudes and teaches Mandelstam variables, scalar amplitudes, Yukawa exchange, QED examples, Yang–Mills examples, polarization sums, helicity previews, and identical-particle care. |
| [Phase Space, Cross Sections, and Decays](/perturbative-qft/phase-space-cross-sections-decays/) | Converts amplitudes into Lorentz-invariant phase space, flux factors, two-body formulas, two-to-two cross sections, decay rates, resonances, inclusive observables, and rate versions of the optical theorem. |
| [Loop Expansion and Regularization](/perturbative-qft/loop-expansion-regularization/) | Introduces loop order, power counting, regulators, bubble integrals, self-energies, vertex corrections, vacuum bubbles, and counterterm insertions. |
| [Loop Integral Technology](/perturbative-qft/loop-integral-technology/) | Provides the practical technology of Feynman and Schwinger parameters, tensor reduction, Passarino–Veltman reduction, IBP identities, master integrals, differential equations, cuts, Landau singularities, polylogarithms, and elliptic previews. |
| [Renormalized Perturbation Theory](/perturbative-qft/renormalized-perturbation-theory/) | Explains bare and renormalized parameters, counterterm Lagrangians, renormalization conditions, on-shell and minimal-subtraction schemes, wavefunction, mass, and coupling renormalization, renormalized amplitudes, and Callan–Symanzik previews. |
| [Gauge-Theory Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/) | Adds gauge fixing, Faddeev–Popov ghosts, QED Ward identities, Yang–Mills rules, color factors, background-field previews, gauge-parameter independence, and BRST checks. |
| [Infrared Physics and Factorization](/perturbative-qft/infrared-physics-factorization/) | Explains soft and collinear divergences, Bloch–Nordsieck and KLN logic, eikonal factors, soft photon and gluon theorems, jets, inclusive observables, factorization, resummation, and SCET previews. |
| [Unitarity, Analyticity, and Dispersion](/perturbative-qft/unitarity-analyticity-dispersion/) | Develops the optical theorem, Cutkosky rules, branch cuts, dispersion relations, partial-wave unitarity, threshold behavior, positivity bounds, and S-matrix bootstrap previews. |
| [Modern On-Shell Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/) | Introduces spinor-helicity variables, three-point amplitudes, color decomposition, color ordering, BCFW recursion, generalized unitarity, on-shell diagrams, soft limits, double copy, amplituhedron previews, and celestial amplitudes previews. |
| [Form Factors and Composite Operators](/perturbative-qft/form-factors-composite-operators/) | Studies local operator insertions, form factors, operator-renormalization previews, current matrix elements, stress-tensor form factors, and anomalous dimensions. |
| [Precision Observables](/perturbative-qft/precision-observables/) | Shows how fixed-order predictions, scale variation, PDF and $\alpha_s$ uncertainties, electroweak corrections, fiducial observables, parton-shower matching, and resummation enter real predictions. |
| [Computational Perturbative QFT](/perturbative-qft/computational-perturbative-qft/) | Records reproducible workflows for symbolic amplitude tools, diagram generation, loop reduction, numerical phase-space integration, and benchmark hygiene. |
| [Model Calculation Library](/perturbative-qft/model-calculation-library/) | Collects complete worked examples in $\phi^4$ theory, Yukawa theory, and QED, including $e^+e^-\to\mu^+\mu^-$ and Compton scattering. |

The top-level reference pages [Common Confusions](/perturbative-qft/common-confusions/), [Exercises](/perturbative-qft/exercises/), and [Bibliography](/perturbative-qft/bibliography/) support the whole volume.

## Recommended reading routes

### Core graduate route

Start here if you are learning perturbative QFT for the first time.

| Step | Read | Goal |
|---:|---|---|
| 1 | [Conventions and Notation](/perturbative-qft/conventions/) | Fix amplitude, state, phase-space, spin, color, and loop-measure conventions. |
| 2 | [Diagrammatics and Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/) | Learn how the perturbative expansion becomes rules for graphs. |
| 3 | [From Correlators to the S-Matrix](/perturbative-qft/from-correlators-to-s-matrix/) | Understand why amplitudes are on-shell residues of correlators. |
| 4 | [Tree-Level Scattering](/perturbative-qft/tree-level-scattering/) | Compute first scalar, Yukawa, QED, and Yang–Mills amplitudes. |
| 5 | [Phase Space, Cross Sections, and Decays](/perturbative-qft/phase-space-cross-sections-decays/) | Convert amplitudes into observable rates and cross sections. |
| 6 | [Model Calculation Library](/perturbative-qft/model-calculation-library/) | Work through complete benchmark calculations. |

After this route, you should be able to compute a simple $2\to2$ tree-level process, square the amplitude with the correct sums and averages, and insert it into the two-body cross-section formula.

### Loop and renormalization route

Follow this route after the core graduate route.

$$
\text{loops}
\longrightarrow
\text{regularization}
\longrightarrow
\text{counterterms}
\longrightarrow
\text{renormalized amplitudes}.
$$

Read [Loop Expansion and Regularization](/perturbative-qft/loop-expansion-regularization/), then [Loop Integral Technology](/perturbative-qft/loop-integral-technology/), then [Renormalized Perturbation Theory](/perturbative-qft/renormalized-perturbation-theory/). The main skill is to distinguish a divergent intermediate integral from a finite scheme-defined prediction.

### Gauge theory and infrared route

This route is for QED, Yang–Mills, QCD-adjacent calculations, and precision predictions.

Read [Gauge-Theory Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/), then [Infrared Physics and Factorization](/perturbative-qft/infrared-physics-factorization/), then [Precision Observables](/perturbative-qft/precision-observables/). The guiding discipline is: individual diagrams can be gauge-dependent or infrared-divergent, while properly defined physical observables are not.

### Modern amplitudes route

This route is for readers entering scattering-amplitudes research.

Read [Unitarity, Analyticity, and Dispersion](/perturbative-qft/unitarity-analyticity-dispersion/) together with [Modern On-Shell Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/). Then return to [Loop Integral Technology](/perturbative-qft/loop-integral-technology/) for generalized unitarity, master integrals, differential equations, and analytic structure.

### Calculation repair route

Use this route when your answer is off by a factor of $i$, $2\pi$, $2E_{\mathbf p}$, $1/2!$, a spin average, a color average, or an identical-particle factor. Start with [Common Confusions](/perturbative-qft/common-confusions/), then jump to [Conventions and Notation](/perturbative-qft/conventions/), [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/), [External-Leg Normalization](/perturbative-qft/from-correlators-to-s-matrix/external-leg-normalization/), [Flux Factors](/perturbative-qft/phase-space-cross-sections-decays/flux-factors/), or [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/).

This route is less glamorous than the amplituhedron. It is also where many real calculations are rescued from doom.

## What belongs elsewhere

This volume cross-links heavily to neighboring volumes, but it has a specific job. It teaches perturbative methods and scattering technology.

| Topic | Main home |
|---|---|
| Fields, states, canonical quantization, path integrals, propagators, Wick theorem | [Foundations of QFT](/foundations/) |
| Wilsonian RG, universality, EFT philosophy, matching as a conceptual framework | [Renormalization, RG, and EFT](/renormalization-rg-eft/) |
| QED, QCD, electroweak theory, and the Standard Model as physical theories | [Gauge Theories and the Standard Model](/gauge-theories-standard-model/) |
| Anomalies, generalized symmetries, topological terms, and defects | [Symmetry, Anomalies, and Topology](/symmetry-anomalies-topology/) |
| Instantons, confinement, mass gaps, lattice definitions, strong coupling | [Nonperturbative QFT](/nonperturbative-qft/) |
| Conformal correlators, conformal blocks, and bootstrap theory | [CFT and Bootstrap](/cft-bootstrap/) |
| Curved spacetime, quantum gravity, black holes, holography | [Spacetime, Gravity, and Holography](/spacetime-gravity-holography/) |
| Theorem-first definitions, reconstruction, algebraic QFT, constructive QFT | [Mathematical and Rigorous QFT](/rigorous-qft/) |

The boundary is practical, not territorial. A scattering calculation may use gauge theory, RG, CFT, or topology, but the page should be clear about which volume owns the deeper explanation.

## Page standards

A mature page in this volume should make the following visible:

| Standard | What it prevents |
|---|---|
| State the object being computed | Confusing correlators, amplitudes, rates, and cross sections. |
| State the approximation | Mixing tree level, one loop, leading power, soft limit, and high-energy limit. |
| State the convention | Losing factors of $i$, $2\pi$, $2E_{\mathbf p}$, spin averages, or color averages. |
| State what is unphysical | Mistaking gauge-dependent, scheme-dependent, or off-shell objects for observables. |
| Show at least one check | Missing diagrams, wrong signs, bad dimensions, or broken Ward identities. |
| Link nearby concepts | Turning each page into an isolated island of notation. |
| Label research status | Blurring textbook tools, standard practice, active methods, and speculative reorganizations. |

When a page uses site-wide conventions, it should normally link the convention page rather than reprinting every convention. When a convention is unusually important for the calculation, it should be restated locally.

## References

- M. Srednicki, *Quantum Field Theory*, especially the chapters on LSZ, scattering amplitudes, Feynman rules, cross sections and decay rates, loop corrections, infrared divergences, QED, gauge theory, and spinor-helicity methods.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the chapters on perturbation theory, Wick diagrams, scattering, LSZ, renormalization, QED, and gauge fields.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, especially the chapters on scattering theory, Feynman rules, path integrals, and renormalization; Vol. II for gauge theory, infrared structure, and renormalization group methods.
- A. Zee, *Quantum Field Theory in a Nutshell*, especially the diagrammatic, renormalization, gauge-invariance, and modern-amplitude chapters and appendices.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on cross sections, LSZ, Feynman rules, QED, renormalization, infrared divergences, unitarity, Yang–Mills theory, spinor-helicity methods, parton showers, and SCET.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional methods, perturbative expansions, renormalization, composite operators, and field-theoretic links to statistical physics.

## Version history

- **2026-06-14:** Final cleanup pass after the initial page set was drafted. Replaced scaffold language with a full volume overview, completed chapter map, reading routes, boundaries, page standards, and updated references.
