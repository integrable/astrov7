---
title: "Holographic CFT"
description: "Chapter overview for holographic conformal field theory in the CFT and Bootstrap volume."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Maldacena; Gubser, Klebanov, and Polyakov; Witten; Heemskerk et al.; Penedones; Ryu and Takayanagi; holographic bootstrap literature."
topics:
  - holographic CFT
  - AdS/CFT
  - large-N CFT
  - Witten diagrams
  - bulk locality
canonicalTopics:
  - holographic-cft
  - ads-cft-correspondence
  - large-n-holography
researchStatus:
  established:
    - "Large-N CFTs with sparse spectra provide the best-understood setting for emergent AdS effective field theory, Witten diagrams, and holographic bootstrap methods."
  active:
    - "Current research studies finite-N corrections, bulk locality, black holes, quantum error correction, islands, stringy corrections, Mellin amplitudes, and bootstrap constraints on emergent gravity."
---

Holographic CFT is the chapter where conformal field theory becomes a theory of quantum gravity in one higher-dimensional spacetime. The central idea is the AdS/CFT correspondence:

$$
\text{CFT in }d\text{ dimensions}
\quad\Longleftrightarrow\quad
\text{quantum gravity or string theory on AdS}_{d+1}.
$$

This chapter treats holography from the CFT side. The goal is not to assume a bulk spacetime and admire it from afar. The goal is to understand which CFT properties make a bulk interpretation possible, how CFT data encode bulk fields and interactions, and how bootstrap methods constrain emergent gravity.

The key organizing principle is

$$
\text{large }N + \text{sparse low-twist spectrum}
\quad\Rightarrow\quad
\text{local AdS effective field theory, approximately}.
$$

The word “approximately” matters. Finite $N$, stringy states, black holes, and quantum-gravity effects all leave fingerprints in CFT data.

## Prerequisites

Before this chapter, read [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/), [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/), [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/), [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/), and [Analytic-Numerical Bridges](/cft-bootstrap/analytic-bootstrap/analytic-numerical-bridges/).

You should know primary operators, OPE coefficients, double-trace operators, conformal blocks, crossing symmetry, large-$N$ factorization, and the stress tensor.

Helpful background from QFT includes effective field theory, gauge theory, path integrals, anomalies, and the renormalization group. Helpful background from geometry includes anti-de Sitter space, geodesics, conformal boundaries, and basic differential geometry.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [AdS/CFT Dictionary](/cft-bootstrap/holographic-cft/ads-cft-dictionary/) | The basic map between CFT operators and bulk fields. |
| 2 | [Large-N and Factorization](/cft-bootstrap/holographic-cft/large-n-and-factorization/) | Why generalized free fields and double-trace operators appear. |
| 3 | [Witten Diagrams](/cft-bootstrap/holographic-cft/witten-diagrams/) | The AdS analogue of Feynman diagrams for CFT correlators. |
| 4 | [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/) | How sparseness, gaps, and Mellin growth encode locality. |
| 5 | [AdS Effective Field Theory](/cft-bootstrap/holographic-cft/ads-effective-field-theory/) | Contact terms, exchange diagrams, derivative expansions, and power counting. |
| 6 | [Mellin Amplitudes and Flat-Space Limits](/cft-bootstrap/holographic-cft/mellin-amplitudes-and-flat-space-limits/) | How boundary correlators become scattering-amplitude-like. |
| 7 | [Stress Tensor, Graviton, and Causality](/cft-bootstrap/holographic-cft/stress-tensor-graviton-and-causality/) | How $T_{\mu\nu}$ encodes gravity and causal constraints. |
| 8 | [Entanglement and the Ryu-Takayanagi Formula](/cft-bootstrap/holographic-cft/entanglement-and-rt/) | Geometry from entanglement entropy. |
| 9 | [Black Holes and Thermal CFT](/cft-bootstrap/holographic-cft/black-holes-and-thermal-cft/) | Heavy states, thermal correlators, and AdS black holes. |
| 10 | [Quantum Error Correction and Entanglement Wedges](/cft-bootstrap/holographic-cft/quantum-error-correction-and-entanglement-wedges/) | Why bulk reconstruction has redundancy. |
| 11 | [Stringy Corrections and Higher-Spin Gaps](/cft-bootstrap/holographic-cft/stringy-corrections-and-higher-spin-gaps/) | How finite string scale appears in CFT spectra. |
| 12 | [Bootstrap Constraints on Holography](/cft-bootstrap/holographic-cft/bootstrap-constraints-on-holography/) | How crossing, Regge behavior, and positivity constrain possible bulk duals. |

The early pages build the dictionary. The middle pages explain correlators and locality. The later pages connect holography to entanglement, black holes, quantum information, and bootstrap constraints.

## Landmarks

| Landmark | Meaning | Why it matters |
|---|---|---|
| large $N$ | Parameter suppressing connected correlators. | Makes generalized free fields and perturbative bulk physics possible. |
| single-trace operator | CFT operator behaving like one elementary large-$N$ excitation. | Maps to a single-particle bulk field. |
| double-trace operator | Composite $[\mathcal O_1\mathcal O_2]_{n,\ell}$. | Maps to a two-particle AdS state. |
| sparse spectrum | Few light single-trace operators below a large gap. | Needed for local Einstein-like bulk EFT. |
| Witten diagram | AdS integral representation of a CFT correlator. | Bulk analogue of a Feynman diagram. |
| Mellin amplitude | Amplitude-like representation of a correlator. | Makes exchange poles and contact terms transparent. |
| stress tensor | Conserved spin-two CFT operator. | Maps to the graviton. |
| central charge $C_T$ | Normalization of stress-tensor two-point function. | Controls effective Newton coupling. |
| Regge behavior | Lorentzian high-energy growth. | Encodes causality and controls inversion. |
| Ryu-Takayanagi surface | Minimal or extremal surface computing entropy. | Connects entanglement and geometry. |
| entanglement wedge | Bulk region reconstructible from a boundary region. | Links holography to quantum error correction. |
| black-hole microstates | Heavy CFT states. | Encode quantum gravity thermodynamics. |

These landmarks are the reusable vocabulary of the chapter.

## Core dictionary

The basic AdS/CFT dictionary identifies CFT data with bulk data.

| CFT side | Bulk side |
|---|---|
| spacetime dimension $d$ | AdS dimension $d+1$ |
| local primary operator $\mathcal O$ | bulk field $\Phi$ |
| operator dimension $\Delta$ | bulk mass $m$ |
| spin $\ell$ | bulk spin |
| OPE coefficient | bulk cubic coupling |
| four-point function | bulk scattering in AdS |
| stress tensor $T_{\mu\nu}$ | graviton |
| global current $J_\mu$ | gauge field |
| large central charge | weak bulk gravity |
| double-trace operator | two-particle state |
| thermal state | black hole or thermal AdS |
| entanglement entropy | area plus quantum corrections |

For a scalar field in AdS, the mass-dimension relation is

$$
m^2R_{\rm AdS}^2=\Delta(\Delta-d),
$$

with the usual caveats about quantization choices near the Breitenlohner-Freedman window.

## What this chapter is not

This chapter is not a complete string theory course. String worldsheets, compactification technology, branes, and full string perturbation theory belong in the string theory and quantum gravity parts of QFT.org when those chapters are expanded.

This chapter is not a replacement for the analytic bootstrap chapter. It uses large-spin, Mellin, inversion, and Regge tools, but focuses on their holographic interpretation.

This chapter is not a general relativity textbook. It uses AdS geometry, black holes, and extremal surfaces, but only as needed to interpret CFT data.

This chapter is not only about supersymmetric examples. Supersymmetry gives important solvable cases, but the conceptual question is broader: when does a CFT behave like quantum gravity in AdS?

## Common confusions

**Large $N$ is not enough.** A vector model can have large $N$ without an Einstein-like local bulk dual. Sparseness and a higher-spin gap matter.

**A bulk field is not inserted by hand.** It is encoded by a CFT primary operator and its correlation functions.

**Double-trace does not mean unimportant.** Double-trace operators are the two-particle spectrum of the bulk and carry interaction energies through anomalous dimensions.

**The boundary is not literally a wall in the lab.** The CFT lives on the conformal boundary of AdS in the dual description.

**Witten diagrams are not ordinary flat-space Feynman diagrams.** They compute boundary correlators through AdS bulk integrals.

**Mellin amplitudes are not automatically flat-space S-matrices.** The flat-space limit requires a controlled scaling regime.

**Entanglement entropy is not only area.** Quantum corrections, bulk entropy, islands, and code subspaces matter beyond the leading classical limit.

**Holography is a statement about exact CFT data.** The bulk description is emergent and approximate in regimes where the CFT data have the right structure.

## Boundaries with other chapters

The [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/) chapter develops tools such as lightcone bootstrap, Lorentzian inversion, Mellin amplitudes, and Regge behavior. This chapter uses those tools to explain AdS physics.

The [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) chapter explains how CFT data are constrained by finite optimization. Holographic CFT pages will use numerical results mainly as tests of large-$N$ and sparse-spectrum hypotheses.

The [Higher-Dimensional CFT](/cft-bootstrap/higher-dimensional-cft/) chapter contains general CFT examples such as Ising, $O(N)$, and gauge-theory CFTs. This chapter focuses specifically on CFTs with gravitational or stringy AdS interpretations.

The [Thermal and Lorentzian CFT](/cft-bootstrap/thermal-lorentzian-cft/) chapter is the natural home for general OTOCs, KMS relations, real-time thermal correlators, and chaos. Holographic pages discuss those topics when black holes or AdS gravity are central.

## Where to go next

Start with [AdS/CFT Dictionary](/cft-bootstrap/holographic-cft/ads-cft-dictionary/) once it is available.

For the CFT-data side, return to [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/) and [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/).

For entanglement and geometry, continue toward [Entanglement and the Ryu-Takayanagi Formula](/cft-bootstrap/holographic-cft/entanglement-and-rt/) and later quantum-information pages.

For black holes and chaos, connect to [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/) and the thermal Lorentzian CFT chapter.

For constraints on possible quantum gravities, read the bootstrap constraints pages and the future Swampland or quantum-gravity chapters.

## References

- J. Maldacena, “The Large N Limit of Superconformal Field Theories and Supergravity,” *Advances in Theoretical and Mathematical Physics* **2** (1998).
- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, “Gauge theory correlators from non-critical string theory,” *Physics Letters B* **428** (1998).
- E. Witten, “Anti de Sitter space and holography,” *Advances in Theoretical and Mathematical Physics* **2** (1998).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, “Holography from conformal field theory,” *Journal of High Energy Physics* **2009**.
- J. Penedones, “Writing CFT correlation functions as AdS scattering amplitudes,” *Journal of High Energy Physics* **2011**.
- S. Ryu and T. Takayanagi, “Holographic derivation of entanglement entropy from AdS/CFT,” *Physical Review Letters* **96** (2006).
- T. Faulkner, A. Lewkowycz, and J. Maldacena, “Quantum corrections to holographic entanglement entropy,” *Journal of High Energy Physics* **2013**.

## Version history

- 2026-07-01: Replaced scaffold with a polished chapter overview. Added prerequisites, reading path, landmarks, core dictionary, boundaries, common confusions, next routes, references, and version history.
