---
title: "Reproducibility and Benchmarks"
description: "A practical standard for making perturbative-QFT calculations inspectable, rerunnable, benchmarked, and comparable across tools and conventions."
sidebar:
  label: "Reproducibility"
  order: 5
level: Advanced
status: "Polished draft"
source: "Les Houches event-file standards; HepMC; LHAPDF; Rivet; HEPData; FORM/FeynCalc/MadGraph/Sherpa workflows; QFT.org computational policy."
topics:
  - computational perturbative QFT
  - reproducibility
  - benchmarks
  - validation
  - metadata
canonicalTopics:
  - reproducibility-and-benchmarks
  - computational-provenance
  - qft-benchmark-workflows
  - validation-of-perturbative-calculations
researchStatus:
  established:
    - "Perturbative calculations become scientifically useful only when their physics inputs, conventions, workflow, software environment, statistical treatment, and validation tests are recorded well enough for independent checking."
  active:
    - "Portable workflows, long-term preservation of executable environments, standardized benchmark suites, floating-point stability, GPU reproducibility, and cross-tool validation remain active infrastructure challenges."
---

## Summary

A perturbative-QFT calculation is reproducible when another competent reader can reconstruct the path from physics question to numerical or analytic answer. That path includes not only the final formula, but also the conventions, input parameters, renormalization scheme, code version, random seeds, cuts, scale choices, integration settings, output format, and validation checks.

A useful shorthand is

$$
\text{prediction}
=
\text{theory}
+
\text{scheme}
+
\text{inputs}
+
\text{observable definition}
+
\text{workflow}
+
\text{validation}.
$$

Leaving out any one of these pieces can make two correct-looking numbers incomparable. This is especially dangerous in precision QFT, where percent-level or per-mille-level differences can come from physics, conventions, numerical settings, or plain bookkeeping.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Reproducibility workflow connecting physics inputs, environment, workflow, outputs, archive, and benchmark checks](/figures/perturbative-qft/reproducibility-benchmarks.svg)

<figcaption>

A reproducible calculation carries its provenance with it. Inputs, environment, workflow, outputs, benchmark tests, and archival metadata should be recorded as part of the scientific result.

</figcaption>
</figure>

This page gives a practical standard for reproducible perturbative-QFT work. It is not a software manifesto. It is a way to prevent perfectly good calculations from becoming mysterious artifacts six months later.

## Prerequisites

You should know [Symbolic Amplitude Tools](/perturbative-qft/computational-perturbative-qft/symbolic-amplitude-tools/), [Diagram Generation Workflows](/perturbative-qft/computational-perturbative-qft/diagram-generation-workflows/), [Loop Reduction Workflows](/perturbative-qft/computational-perturbative-qft/loop-reduction-workflows/), [Numerical Phase-Space Integration](/perturbative-qft/computational-perturbative-qft/numerical-phase-space-integration/), [Fixed-Order Predictions](/perturbative-qft/precision-observables/fixed-order-predictions/), [Scale Variation and Uncertainties](/perturbative-qft/precision-observables/scale-variation-and-uncertainties/), [PDF and Alpha-s Uncertainties](/perturbative-qft/precision-observables/pdf-and-alpha-s-uncertainties/), and [Fiducial Observables](/perturbative-qft/precision-observables/fiducial-observables/).

## Core idea

Reproducibility is not the same as rerunning a script. It has several levels.

| Level | Meaning | Typical failure mode |
|---|---|---|
| conceptual reproducibility | the physics question is specified clearly | two people compute different observables |
| algebraic reproducibility | formulas and conventions can be checked | sign, normalization, color, or scheme mismatch |
| computational reproducibility | code and settings can be rerun | missing version, hidden patch, missing model file |
| statistical reproducibility | stochastic errors can be calibrated | one seed accidentally looked lucky |
| benchmark reproducibility | results agree with known limits or independent tools | wrong result passes a single internal check |
| archival reproducibility | outputs remain interpretable years later | plots survive but input cards vanish |

The goal is not to freeze every calculation into a museum specimen. The goal is to preserve enough information that the result can be audited, rerun, compared, and extended.

## Setup and conventions

This page assumes QFT.org conventions for amplitudes, phase space, and renormalized perturbation theory. A workflow should not rewrite site-wide conventions every time, but it should record any deviation from them.

A reproducibility manifest should include:

| Category | Examples |
|---|---|
| physics target | process, observable, perturbative order, approximations |
| theory data | Lagrangian, model file, field basis, gauge fixing, counterterms |
| conventions | metric, Fourier phases, $S$-matrix normalization, color normalization, spin averages |
| numerical inputs | masses, widths, couplings, CKM entries, PDFs, scales, cuts |
| schemes | renormalization scheme, factorization scheme, mass scheme, width scheme |
| software | package names, versions, commits, local patches, compiler options |
| stochastic data | random seeds, number of samples, integration grids, adaptation logs |
| outputs | tables, histograms, events, amplitudes, intermediate reductions |
| validation | benchmark comparisons, internal checks, independent reruns |
| archive | DOI, repository commit, release tag, license, README, environment file |

The manifest can be a YAML file, JSON file, notebook header, paper appendix, repository README, or structured metadata file. The format matters less than completeness and readability.

## Anatomy of a reproducible calculation

A perturbative calculation usually moves through several layers:

$$
\text{model}
\to
\text{diagrams}
\to
\text{amplitudes}
\to
\text{reduction}
\to
\text{renormalization}
\to
\text{phase space}
\to
\text{observable}.
$$

Each layer should have its own reproducibility information.

### Model layer

Record the fields, parameters, interactions, gauge fixing, and counterterms. If the model is imported from a file, archive that file. If the model is derived from a Lagrangian in the text, state the field basis and normalization.

For EFT calculations, also record the operator basis, coefficient normalization, truncation order, and whether quadratic dimension-six terms or only interference terms are retained. “Dimension-six result” is not a complete specification.

### Diagram and amplitude layer

Record the process, coupling order, loop order, particle crossing convention, incoming/outgoing convention, helicity or spin-sum treatment, color basis, and diagram filters.

For gauge theories, include Ward-identity or gauge-parameter checks when possible. For non-Abelian amplitudes, include enough color information to reconstruct whether the reported result is color summed, color averaged, color ordered, or color decomposed.

### Loop and reduction layer

Record the regulator, loop-measure normalization, integral families, master-integral basis, reduction tool settings, treatment of scaleless integrals, and analytic continuation. If reduction tables are too large for the paper, archive them.

A compact published expression should say where the full reduction lives. Otherwise the calculation becomes unreviewable at precisely the point where mistakes are easiest.

### Renormalization layer

Record the renormalization scheme, input parameters, counterterm definitions, subtraction convention, and scale choices. For mixed QCD–electroweak calculations, record which coupling expansion is being used.

A statement like “we use the on-shell scheme” is not always enough. In electroweak calculations, for example, different input schemes can share on-shell masses but differ in which measured quantities define the couplings.

### Phase-space and observable layer

Record the cuts, binning, jet definitions, recombination rules, isolation rules, PDFs, factorization scales, renormalization scales, and statistical integration settings. For event files, record the event format and the meaning of the stored weights.

The final plot should be reconstructible from the archived histogram or event data and the plotting script. A plot alone is a photograph of a calculation, not the calculation.

## Minimal metadata templates

The following tables give practical checklists. They are not sacred. They are a starting point.

### Amplitude benchmark metadata

| Field | Example |
|---|---|
| process | $e^-e^+\to\mu^-\mu^+$ |
| convention | all momenta incoming, mostly-minus metric |
| external states | helicity fixed or spin summed/averaged |
| couplings | powers of $e$, $g_s$, EFT coefficients |
| gauge | Feynman gauge, $R_\xi$ gauge, axial gauge |
| color basis | trace basis, color-flow basis, adjoint basis |
| checks | Ward identity, crossing, soft limit, known analytic result |

### Loop benchmark metadata

| Field | Example |
|---|---|
| regulator | dimensional regularization, $d=4-2\epsilon$ |
| loop measure | explicit normalization with powers of $i\pi^{d/2}$ or $(2\pi)^d$ |
| integral family | denominator list and momentum routing |
| master basis | named basis and boundary conditions |
| scheme | MS, $\overline{\rm MS}$, on-shell, custom |
| expansion | order in $\epsilon$ retained |
| checks | UV poles, IR poles, threshold behavior, independent reduction |

### Observable benchmark metadata

| Field | Example |
|---|---|
| observable | total rate, fiducial cross section, differential distribution |
| cuts | exact numerical cut values and object definitions |
| input parameters | masses, widths, couplings, PDFs, scales |
| perturbative order | LO, NLO, NNLO, resummed accuracy, matching scheme |
| integration | seeds, sample counts, grids, error estimates |
| units | fb, pb, GeV, normalized distribution |
| checks | bin closure, independent seeds, scale variation, benchmark process |

## Benchmarks

A benchmark is a deliberately simple calculation or data point whose purpose is to expose mistakes. It should be easier to check than the production calculation.

Good benchmarks have at least one of the following properties:

| Benchmark type | Example | What it tests |
|---|---|---|
| analytic result | two-body decay with constant matrix element | normalization and phase space |
| symmetry identity | Ward identity $k_\mu\mathcal M^\mu=0$ | gauge invariance and external-state conventions |
| limiting behavior | soft, collinear, threshold, high-energy limit | singular structure and maps |
| independent code | second toolchain or private implementation | implementation-specific mistakes |
| published number | standard process with specified inputs | global normalization and input agreement |
| regression test | old output for same commit and input | accidental workflow changes |
| stress test | extreme kinematic point | numerical stability |

A benchmark should state what is being compared and with what tolerance. “Agrees” is a vibe; “relative difference below $10^{-8}$ at these phase-space points” is a test.

## Analytic checks

Analytic checks are the highest-value benchmarks because they do not depend on another large code path.

### Dimensional analysis

Before running anything, check the mass dimension. A $2\to n$ cross section in four spacetime dimensions has dimension

$$
[\sigma]=-2.
$$

A decay rate has dimension

$$
[\Gamma]=1.
$$

If a code returns a number with the wrong implicit units, no amount of Monte Carlo sampling will save it.

### Ward identities

For a QED amplitude with an external photon polarization vector $\epsilon_\mu(k)$, replace

$$
\epsilon_\mu(k)\to k_\mu.
$$

The physical amplitude should vanish after all diagrams contributing to the gauge-invariant process are included. In non-Abelian gauge theory the corresponding checks can involve color, ghosts, and gauge fixing, but the philosophy is the same: unphysical polarizations should not survive in the final physical amplitude.

### Soft and collinear limits

In a soft limit, an $(n+1)$-particle amplitude should factorize into an $n$-particle amplitude times a universal soft factor at leading power. In a collinear limit, it should factorize into a lower-point amplitude times a splitting function or splitting amplitude.

These limits are not just theory ornaments. They are excellent debugging tools for signs, color factors, spin correlations, and momentum mappings.

### Pole structure

Loop amplitudes in dimensional regularization often have predictable UV and IR pole structures. If a renormalized physical observable still contains uncanceled $1/\epsilon$ poles where none should remain, the calculation is not finished.

Conversely, a miraculous cancellation of poles is not enough. Finite parts can still be wrong.

## Numerical checks

Numerical reproducibility has its own traps.

### Random seeds

A seed is not always enough to reproduce a parallel Monte Carlo run. The result may depend on thread scheduling, vectorization, GPU kernels, or the order in which random numbers are consumed. For serious preservation, record the random-number generator, seed sequence, parallelization strategy, and whether the run is expected to be bitwise or statistically reproducible.

Bitwise reproducibility is ideal for regression tests. Statistical reproducibility is often enough for stochastic physics results, but then the tolerance must be statistical rather than exact.

### Floating-point stability

Perturbative calculations often contain cancellations among large terms. A stable workflow tests representative phase-space points in more than one precision or with more than one algebraic form. If a weight changes wildly between double precision and higher precision, the production run needs stability controls.

Useful diagnostics include:

| Diagnostic | Meaning |
|---|---|
| relative precision estimate | how many digits survive cancellation |
| exceptional-point count | how often stability rescue is needed |
| weight tail | whether rare unstable points dominate variance |
| high-precision spot checks | independent check of difficult points |
| gauge-variation test | stability of physical gauge cancellations |

### Independent seeds

For Monte Carlo integration, run independent seeds and compare the scatter with the quoted uncertainties. A single impressive run is not a calibrated uncertainty estimate. Several boring runs are better.

### Regression tests

A regression test compares a known input to a known output. It should be run whenever the code, compiler, dependencies, model file, or integration settings change.

Good regression tests are small, fast, and focused. They should fail loudly when a convention changes.

## Cross-tool comparisons

Cross-tool comparisons are powerful but delicate. Two tools rarely use identical defaults. Before comparing, align:

| Input | Typical mismatch |
|---|---|
| masses and widths | pole mass versus running mass, fixed width versus complex mass |
| coupling definitions | $\alpha(0)$, $G_F$ scheme, $\alpha_s(M_Z)$, running couplings |
| PDFs and scales | different PDF sets or factorization scales |
| cuts and jets | different recombination or isolation rules |
| spin/color averaging | summed in one code, averaged in another |
| widths and resonances | off-shell treatment, narrow-width approximation, diagram filters |
| perturbative order | different included coupling powers or loop-induced pieces |
| units | pb versus fb, normalized versus absolute distributions |

Once aligned, compare more than one number. A total rate can agree while distributions disagree. A distribution can agree while a gauge-variant subcomponent is wrong. The goal is to isolate mistakes, not win a screenshot duel.

## Reporting uncertainties

A precision result usually has several uncertainty components. A clean report separates them:

$$
O
=
O_0
\pm\Delta_{\rm stat}
\pm\Delta_{\rm scale}
\pm\Delta_{\rm input}
\pm\Delta_{\rm method}.
$$

The labels depend on the calculation. For collider predictions, common components include Monte Carlo statistical uncertainty, scale variation, PDF uncertainty, $\alpha_s$ uncertainty, mass and width input uncertainty, matching or shower uncertainty, and missing higher-order uncertainty.

Do not combine uncertainties in a way that hides their origin unless the combination rule is stated. Statistical errors and theory estimates do not have the same meaning.

## Archiving outputs

A reproducible calculation should archive more than the final plot.

Recommended artifacts include:

| Artifact | Why it matters |
|---|---|
| human-readable README | tells future readers what is inside |
| input cards | define the physics and numerical setup |
| model files | define fields, rules, and parameters |
| scripts | reconstruct tables and figures |
| logs | record code versions, warnings, and run settings |
| histogram data | allow plots to be remade without rerunning everything |
| event files | preserve event-level information where appropriate |
| integration grids | avoid expensive retraining and enable debugging |
| benchmark outputs | show that the workflow was checked |
| environment file | records dependencies and executable context |

Avoid archiving only binary blobs unless a documented reader exists. A future reader should not need to reverse-engineer your file format while emotionally negotiating with a deprecated library.

## A practical reproducibility manifest

A compact manifest might look conceptually like this:

```yaml
calculation:
  process: "p p -> Z + jet"
  observable: "fiducial pT(Z) distribution"
  perturbative_order: "NLO QCD"
  units: "fb / GeV"

theory:
  model: "Standard Model"
  scheme: "MSbar alpha_s, on-shell electroweak masses"
  pdf: "record exact set and member"
  scales: "record central scale and variation prescription"

workflow:
  generator: "record tool name, version, commit, patches"
  integration: "record seeds, grids, iterations, target precision"
  cuts: "record object definitions, jet algorithm, bin edges"

validation:
  checks:
    - "LO benchmark against independent code"
    - "Ward identity at sampled phase-space points"
    - "bin closure for total rate"
    - "three independent seeds"

archive:
  repository: "record URL or DOI"
  commit: "record immutable commit"
  date: "record date of production run"
```

The exact keys can differ. The discipline is the important part.

## Common pitfalls

**Publishing a number without the observable.** A cross section is meaningless without cuts, scheme, input parameters, order, and units.

**Treating package defaults as documentation.** Defaults change, and different tools use different defaults. Record the choices explicitly.

**Archiving plots but not data.** A plot is hard to reuse, hard to compare, and easy to misread. Archive the table behind it.

**Confusing bitwise and statistical reproducibility.** Stochastic workflows may not reproduce bit by bit, especially in parallel. They should reproduce statistically within stated uncertainties.

**Forgetting local patches.** A one-line private patch can matter more than a version number. Record it or archive the patched source.

**Using benchmarks that are too close to the production calculation.** A benchmark should isolate one layer. If it depends on the entire pipeline, it may only confirm that the whole pipeline is self-consistent.

**Comparing to another code before aligning conventions.** Cross-tool disagreement is often a convention mismatch. Cross-tool agreement is not proof unless the common inputs are documented.

**Hiding failed checks.** A failed check that is understood and resolved is useful. A failed check that disappears from the record is a time bomb.

## Relations to other pages

- [Symbolic Amplitude Tools](/perturbative-qft/computational-perturbative-qft/symbolic-amplitude-tools/) discusses symbolic manipulation and algebraic checks.
- [Diagram Generation Workflows](/perturbative-qft/computational-perturbative-qft/diagram-generation-workflows/) explains reproducibility at the diagram and model-file level.
- [Loop Reduction Workflows](/perturbative-qft/computational-perturbative-qft/loop-reduction-workflows/) explains reduction metadata, integral families, and master-integral workflows.
- [Numerical Phase-Space Integration](/perturbative-qft/computational-perturbative-qft/numerical-phase-space-integration/) explains stochastic integration, phase-space maps, and error estimates.
- [Fixed-Order Predictions](/perturbative-qft/precision-observables/fixed-order-predictions/) explains how perturbative components assemble into predictions.
- [Scale Variation and Uncertainties](/perturbative-qft/precision-observables/scale-variation-and-uncertainties/) discusses one of the standard uncertainty diagnostics.
- [Fiducial Observables](/perturbative-qft/precision-observables/fiducial-observables/) explains why cuts, object definitions, and bins are part of the observable.

## Research status

- **Established:** Reproducible perturbative calculations require explicit physics inputs, conventions, software environments, workflow settings, outputs, and validation checks. This is standard scientific practice, even when individual communities differ in format.
- **Active:** Long-term preservation of executable workflows, GPU and parallel reproducibility, public benchmark suites, automated provenance capture, robust uncertainty propagation, and cross-tool validation remain active infrastructure problems.
- **Convention-dependent:** Benchmarks are useful only when conventions are aligned. A benchmark value without its input card is not a benchmark.
- **Good practice, not magic:** Reproducibility metadata does not prove correctness. It makes correctness checkable.

## Exercises

### Exercise 1: Build a manifest for a tree-level benchmark

Write the minimal metadata needed to reproduce a tree-level calculation of $e^-e^+\to\mu^-\mu^+$ at fixed center-of-momentum energy.

<details>
<summary><strong>Solution</strong></summary>

A minimal manifest should include:

| Category | Needed data |
|---|---|
| process | $e^-e^+\to\mu^-\mu^+$, with incoming/outgoing convention |
| order | tree-level QED, order $e^2$ in the amplitude |
| input parameters | $\sqrt s$, lepton masses or massless approximation, value of $\alpha$ |
| external states | spin summed and averaged, or specified helicities |
| phase space | total cross section or angular distribution, angular cuts if any |
| conventions | $S$-matrix normalization, spinor normalization, metric if not site-default |
| code | script or notebook, version, commit if applicable |
| checks | compare with analytic angular distribution and total rate |

For a benchmark, it is better to choose a simple massless or equal-input setup and state it exactly than to quote a realistic-looking number with hidden assumptions.

</details>

### Exercise 2: Bitwise versus statistical reproducibility

A Monte Carlo integration with the same seed gives slightly different last digits on two machines. Does this necessarily mean the calculation is not reproducible?

<details>
<summary><strong>Solution</strong></summary>

No. If the workflow uses floating-point arithmetic, parallel scheduling, vectorization, or different math libraries, bitwise equality may fail even when the calculation is statistically reproducible. The correct question is whether independent runs agree within the stated statistical and numerical uncertainties.

For regression tests, bitwise reproducibility is useful and sometimes necessary. For production Monte Carlo results, statistical reproducibility is often the meaningful requirement. The report should state which level is expected.

</details>

### Exercise 3: Design a Ward-identity benchmark

For a QED amplitude with one external photon, describe a numerical Ward-identity test.

<details>
<summary><strong>Solution</strong></summary>

Compute the amplitude in the usual way with photon polarization vector $\epsilon_\mu(k)$. Then replace the polarization vector by the photon momentum:

$$
\epsilon_\mu(k)\to k_\mu.
$$

For a gauge-invariant set of diagrams and compatible external states, the resulting amplitude should vanish up to numerical precision. The test should be run at several nonexceptional phase-space points. If it fails, possible causes include missing diagrams, inconsistent charges, wrong signs, incorrect spinor flow, gauge-invariant subsets not being used, or numerical instability.

</details>

### Exercise 4: Why archive histograms as tables?

Explain why a plotted distribution is not a sufficient archival object for a precision prediction.

<details>
<summary><strong>Solution</strong></summary>

A plot usually does not contain exact bin edges, central values, uncertainties, correlations, overflow definitions, normalization conventions, or enough precision to compare with another calculation. It also cannot easily be reprocessed into a ratio plot or combined with another uncertainty.

A table can record the bin edges, central values, statistical errors, systematic components, covariance information when available, and units. The plot can then be regenerated from the table. The table is the scientific data product; the plot is a visualization.

</details>

## References

- J. Alwall et al., “A Standard Format for Les Houches Event Files,” *Computer Physics Communications* **176** (2007), 300–304.
- M. Dobbs and J. B. Hansen, “The HepMC C++ Monte Carlo Event Record for High Energy Physics,” *Computer Physics Communications* **134** (2001), 41–46.
- A. Buckley et al., “Rivet User Manual,” *Computer Physics Communications* **184** (2013), 2803–2819.
- A. Buckley et al., “LHAPDF6: Parton Density Access in the LHC Precision Era,” *European Physical Journal C* **75** (2015), 132.
- T. Hahn, “Cuba: A Library for Multidimensional Numerical Integration,” *Computer Physics Communications* **168** (2005), 78–95.
- J. A. M. Vermaseren, “New Features of FORM,” *arXiv:math-ph/0010025*, for large symbolic manipulation workflows.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 20, 31, 32, and 36, for infrared-safe observables, precision tests, parton showers, and SCET examples.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 3 and Vol. II, ch. 18, for scattering observables, unitarity, and large-logarithm/RG issues.

## Version history

- **2026-06-13:** Initial polished draft for QFT.org, setting a practical reproducibility and benchmark standard for computational perturbative-QFT workflows.
