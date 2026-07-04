---
title: "AdS/CFT Foundations"
description: "A friendly but technically serious graduate course on AdS/CFT, gauge/gravity duality, holography, large N quantum field theory, Anti-de Sitter geometry, black holes, entanglement, and quantum gravity."
sidebar:
  label: "Overview"
  order: 0
---

:::caution[Site under construction]
The initial drafts were prepared with the assistance of AI and have since been reviewed and edited by me. Although I have tried to ensure accuracy, some errors may remain. Especially, almost all figures were drawn by AI, and many are inaccurate. If you notice any significant mistakes, I would greatly appreciate your [feedback](/feedback/send-feedback).
:::

AdS/CFT is a surprising claim with a simple shape: a quantum theory of gravity in Anti-de Sitter spacetime can be exactly equivalent to an ordinary quantum field theory living on the boundary.

That sentence sounds almost too good to be true. This course is about making it precise.

If you are a senior undergraduate who has seen quantum field theory and general relativity, this course is meant to give you a real foothold. If you are a graduate student entering holography, it is meant to become your main spine. If you are a researcher from a nearby area, it is meant to be a reliable map of the assumptions, calculations, and modern language behind AdS/CFT.

The slogan is short:

$$
\text{gravity in asymptotically AdS spacetime}
\quad\longleftrightarrow\quad
\text{quantum field theory on the boundary}.
$$

The course is the long version of that slogan: why it is plausible, what it actually means, how to calculate with it, and where it stops being under control.

## Start here

A good first encounter with AdS/CFT should not begin with ten-dimensional supergravity or a forest of indices. It should begin with three questions.

**Why should gravity know about a lower-dimensional quantum theory?** Black-hole entropy, large-$N$ gauge theory, and string theory all point toward the same strange idea: the fundamental variables of a gravitational system need not look local in the bulk.

**Why Anti-de Sitter space?** AdS has a timelike conformal boundary, a large symmetry group, and a natural relation between radial position and energy scale. These features make it the cleanest laboratory for holography.

**What can I compute?** Boundary correlators, thermal free energies, transport coefficients, Wilson loops, entanglement entropies, black-hole thermodynamics, and aspects of quantum gravity can all be translated into bulk problems.

For a gentle first week, read:

1. [Why Holography?](./orientation/why-holography/)
2. [What the Duality Claims](./orientation/what-the-duality-claims/)
3. [Conformal Symmetry Minimum](./cft-large-n/conformal-symmetry-minimum/)
4. [AdS as a Spacetime](./ads-geometry/ads-as-a-spacetime/)
5. [Statement of the Correspondence](./dictionary/statement-of-the-correspondence/)
6. [GKPW Prescription](./dictionary/gkpw-prescription/)

Do not worry if the string-theory pages look unfamiliar on the first pass. The course introduces only the string theory needed to understand where the canonical example comes from.

## What you should bring

The course assumes working familiarity with:

- path integrals, sources, and correlation functions;
- Yang–Mills theory and basic gauge invariance;
- metrics, curvature, geodesics, horizons, and variational principles in general relativity;
- comfort with learning new mathematical notation as needed.

It does **not** assume that you already know conformal field theory, supersymmetry, or string theory. Those topics appear, but the course develops the parts needed for AdS/CFT instead of asking you to master three separate subjects first.

A senior undergraduate can read the conceptual flow and many derivations. A graduate student should work through the exercises and reproduce the central calculations. A researcher should use the course map and appendices as a reference spine.

## The central example

The canonical example is

$$
\mathcal N=4\; SU(N)\;\text{super-Yang–Mills theory in four dimensions}
\quad\longleftrightarrow\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5 .
$$

The field theory is a conformal gauge theory. The bulk theory is a quantum theory of closed strings, containing gravity. In a special large-$N$, strong-coupling regime, the string theory simplifies to classical supergravity on a weakly curved spacetime.

The most useful parameter map is

$$
\lambda = g_{\mathrm{YM}}^2 N,
\qquad
\frac{L^4}{\alpha'^2} \sim \lambda,
\qquad
g_s \sim \frac{\lambda}{N}.
$$

Here $L$ is the AdS radius, $\alpha'$ is the string length squared, $g_s$ is the string coupling, and $\lambda$ is the 't Hooft coupling. The interpretation is:

- large $N$ suppresses quantum loops in the bulk;
- large $\lambda$ suppresses stringy corrections;
- finite $N$ probes quantum gravity;
- finite $\lambda$ probes stringy physics.

Classical Einstein gravity is therefore not the full duality. It is a powerful and controlled corner of a larger equivalence.

## The first dictionary

The basic working form of the correspondence is the relation between boundary generating functionals and bulk partition functions:

$$
Z_{\mathrm{CFT}}[\phi_{(0)}]
=
Z_{\mathrm{bulk}}\!\left[\phi \to \phi_{(0)}\right].
$$

In the classical Euclidean gravity approximation,

$$
Z_{\mathrm{bulk}}\!\left[\phi \to \phi_{(0)}\right]
\approx
\exp\!\left(-S_{\text{ren,on-shell}}[\phi_{(0)}]\right),
$$

so that

$$
W_{\mathrm{CFT}}[\phi_{(0)}]
\approx
-S_{\text{ren,on-shell}}[\phi_{(0)}].
$$

The boundary value $\phi_{(0)}$ of a bulk field $\phi$ acts as a source for a boundary operator $\mathcal O$:

$$
Z_{\mathrm{CFT}}[\phi_{(0)}]
=
\left\langle
\exp\!\left(
\int_{\partial\mathrm{AdS}} \phi_{(0)}\mathcal O
\right)
\right\rangle.
$$

This formula is schematic until one specifies boundary conditions, counterterms, Lorentzian versus Euclidean signature, and normalization conventions. Much of the course is devoted to turning this compact equation into a dependable computational method.

## What you will learn to do

By the end of the core path, you should be able to:

1. explain why large-$N$ gauge theories naturally resemble weakly coupled bulk theories;
2. derive the emergence of $\mathrm{AdS}_5\times S^5$ from the near-horizon limit of D3-branes;
3. compute simple CFT correlators from bulk on-shell actions;
4. derive the scalar mass-dimension relation

   $$
   m^2L^2=\Delta(\Delta-d);
   $$

5. distinguish sources, responses, normalizable modes, and expectation values;
6. carry out the basic steps of holographic renormalization;
7. relate black branes to thermal CFT states;
8. understand why quasinormal modes are poles of retarded Green functions;
9. use RT/HRT surfaces to compute and interpret entanglement entropy;
10. recognize which claims are exact, which are semiclassical, and which are phenomenological models.

The point is not to memorize a dictionary. The point is to learn how the dictionary is built.

## Suggested reading paths

### Senior-undergraduate first pass

This path is for readers who want the big picture before the technical machinery:

1. [Why Holography?](./orientation/why-holography/)
2. [What the Duality Claims](./orientation/what-the-duality-claims/)
3. [Conformal Symmetry Minimum](./cft-large-n/conformal-symmetry-minimum/)
4. [AdS as a Spacetime](./ads-geometry/ads-as-a-spacetime/)
5. [Global AdS and the Cylinder](./ads-geometry/global-ads-and-the-cylinder/)
6. [D3-Branes: Two Descriptions](./string-origin/d3-branes-two-descriptions/)
7. [Statement of the Correspondence](./dictionary/statement-of-the-correspondence/)
8. [Ryu–Takayanagi formula](./entanglement-geometry/ryu-takayanagi-formula/)

Skip long derivations on the first pass; return to them when the conceptual map is stable.

### Minimal technical core

This path gives the calculational foundation:

1. [QFT Data and Generating Functionals](./cft-large-n/qft-data-and-generating-functionals/)
2. [Large N Gauge Theory](./cft-large-n/large-n-gauge-theory/)
3. [Fields in AdS](./ads-geometry/fields-in-ads/)
4. [GKPW Prescription](./dictionary/gkpw-prescription/)
5. [Scalar Two-Point Functions](./dictionary/scalar-two-point-functions/)
6. [Mass-Dimension Relation](./dictionary/mass-dimension-relation/)
7. [Counterterms and Renormalized Action](./holographic-renormalization/counterterms-and-renormalized-action/)
8. [Practical Recipe](./holographic-renormalization/practical-recipe/)

### Correlators and probes path

After the basic dictionary:

1. [Witten Diagrams](./correlators-probes/witten-diagrams/)
2. [Three-Point Functions and Bulk Couplings](./correlators-probes/three-point-functions-and-bulk-couplings/)
3. [Four-Point Functions and Bulk Locality](./correlators-probes/four-point-functions-and-bulk-locality/)
4. [Wilson Loops](./correlators-probes/wilson-loops/)
5. [Probe Branes and Flavor](./correlators-probes/probe-branes-and-flavor/)

### Black-hole and real-time path

For thermal field theory, transport, and response:

1. [Black Branes and Thermal CFTs](./thermal-real-time/black-branes-and-thermal-cfts/)
2. [Hawking–Page transition](./thermal-real-time/hawking-page-transition/)
3. [Euclidean Gravity and Free Energy](./thermal-real-time/euclidean-gravity-and-free-energy/)
4. [Real-Time Prescription](./thermal-real-time/real-time-prescription/)
5. [Retarded Green Functions](./thermal-real-time/retarded-green-functions/)
6. [Quasinormal Modes](./thermal-real-time/quasinormal-modes/)
7. [Hydrodynamics from Gravity](./thermal-real-time/hydrodynamics-from-gravity/)
8. [Shear Viscosity](./thermal-real-time/shear-viscosity/)

### Entanglement path

For quantum information and emergent spacetime:

1. [Entanglement Entropy in QFT](./entanglement-geometry/entanglement-entropy-in-qft/)
2. [Ryu–Takayanagi formula](./entanglement-geometry/ryu-takayanagi-formula/)
3. [Covariant HRT formula](./entanglement-geometry/covariant-hrt-formula/)
4. [Entanglement Wedges](./entanglement-geometry/entanglement-wedges/)
5. [Relative Entropy and Linearized Gravity](./entanglement-geometry/relative-entropy-and-linearized-gravity/)
6. [Quantum Extremal Surfaces](./entanglement-geometry/quantum-extremal-surfaces/)
7. [Islands and Information](./entanglement-geometry/islands-and-information/)

### Quantum-gravity path

For bulk emergence, reconstruction, and black-hole information:

1. [Bulk Effective Field Theory](./bulk-quantum-gravity/bulk-effective-field-theory/)
2. [Large N Factorization and Fock Space](./bulk-quantum-gravity/large-n-factorization-and-fock-space/)
3. [Bulk Reconstruction](./bulk-quantum-gravity/bulk-reconstruction/)
4. [Quantum Error Correction](./bulk-quantum-gravity/quantum-error-correction/)
5. [Black-Hole Information in AdS/CFT](./bulk-quantum-gravity/black-hole-information-in-ads-cft/)
6. [Stringy and Quantum Corrections](./bulk-quantum-gravity/stringy-and-quantum-corrections/)
7. [Open Problems and Research Map](./bulk-quantum-gravity/open-problems-and-research-map/)

## Full course map

### Orientation

| Page | Purpose |
|---|---|
| [Why Holography?](./orientation/why-holography/) | Motivation from quantum gravity, strongly coupled QFT, entropy, and black holes. |
| [What the Duality Claims](./orientation/what-the-duality-claims/) | The exact, semiclassical, and practical meanings of AdS/CFT. |
| [Regimes of Validity](./orientation/regimes-of-validity/) | When the bulk is quantum string theory, classical string theory, supergravity, or Einstein gravity. |
| [Conventions and Units](./orientation/conventions-and-units/) | Course-wide signatures, dimensions, indices, Fourier conventions, and source normalizations. |
| [Roadmap](./orientation/roadmap/) | How to navigate the course by interest and preparation. |

### CFT and Large N

| Page | Purpose |
|---|---|
| [QFT Data and Generating Functionals](./cft-large-n/qft-data-and-generating-functionals/) | Sources, $Z[J]$, $W[J]$, connected correlators, and Ward identities. |
| [Conformal Symmetry Minimum](./cft-large-n/conformal-symmetry-minimum/) | The CFT ingredients needed for holography. |
| [Radial Quantization and the Cylinder](./cft-large-n/radial-quantization-and-the-cylinder/) | The map from flat-space CFT to the cylinder Hilbert space. |
| [Large N Gauge Theory](./cft-large-n/large-n-gauge-theory/) | 't Hooft counting, planar diagrams, and the string-genus expansion. |
| [Single Trace and Factorization](./cft-large-n/single-trace-and-factorization/) | Single-particle/multiparticle bulk interpretation from CFT operators. |
| [$\mathcal N=4$ Super-Yang–Mills](./cft-large-n/n4-super-yang-mills/) | The canonical boundary theory of AdS$_5$/CFT$_4$. |
| [Thermal States and Density Matrices](./cft-large-n/thermal-states-and-density-matrices/) | Boundary thermal field theory before black branes. |

### Anti-de Sitter Geometry

| Page | Purpose |
|---|---|
| [AdS as a Spacetime](./ads-geometry/ads-as-a-spacetime/) | Embedding, curvature, universal cover, and boundary intuition. |
| [Coordinate Systems](./ads-geometry/coordinate-systems/) | Global, Poincare, Fefferman–Graham, black-brane, and EF coordinates. |
| [Conformal Boundary](./ads-geometry/conformal-boundary/) | Conformal compactification and boundary conformal classes. |
| [Global AdS and the Cylinder](./ads-geometry/global-ads-and-the-cylinder/) | Why global AdS talks to the CFT on $\mathbb R\times S^{d-1}$. |
| [Isometries and Conformal Symmetry](./ads-geometry/isometries-and-conformal-symmetry/) | The $SO(2,d)$ symmetry match. |
| [Fields in AdS](./ads-geometry/fields-in-ads/) | Near-boundary falloffs and the first source-response bridge. |
| [Black Holes and Black Branes](./ads-geometry/black-holes-and-black-branes/) | The geometric side of thermal CFT states. |
| [Euclidean AdS and Thermal Circles](./ads-geometry/euclidean-ads-and-thermal-circles/) | Smooth Euclidean horizons and Hawking temperature. |

### String Theory Origin

| Page | Purpose |
|---|---|
| [Open and Closed Strings](./string-origin/open-and-closed-strings/) | The minimal string ingredients behind gauge fields and gravitons. |
| [D-Branes for Field Theorists](./string-origin/d-branes-for-field-theorists/) | D-branes as open-string worlds, gauge theories, and closed-string sources. |
| [D3-Branes: Two Descriptions](./string-origin/d3-branes-two-descriptions/) | The open-string SYM and closed-string geometry descriptions. |
| [Near-Horizon Geometry](./string-origin/near-horizon-geometry/) | How the D3-brane throat becomes $\mathrm{AdS}_5\times S^5$. |
| [Decoupling Limit](./string-origin/decoupling-limit/) | Why the field theory and AdS throat decouple from flat-space gravity. |
| [Parameter Map](./string-origin/parameter-map/) | The map between $N$, $\lambda$, $g_s$, $L$, $\alpha'$, and Newton constants. |
| [Why Classical Gravity Emerges](./string-origin/why-classical-gravity-emerges/) | How large $N$ and large gap/large $\lambda$ produce classical bulk gravity. |

### The Basic Dictionary

| Page | Purpose |
|---|---|
| [Statement of the Correspondence](./dictionary/statement-of-the-correspondence/) | The exact, semiclassical, and classical statements of the duality. |
| [GKPW Prescription](./dictionary/gkpw-prescription/) | Boundary sources as bulk boundary values. |
| [Scalar Two-Point Functions](./dictionary/scalar-two-point-functions/) | A complete first correlator computation. |
| [Mass-Dimension Relation](./dictionary/mass-dimension-relation/) | The derivation of $m^2L^2=\Delta(\Delta-d)$. |
| [Alternate Quantization and BF Bound](./dictionary/alternate-quantization-and-bf-bound/) | Stability, falloffs, and source-response exchange. |
| [One-Point Functions and VEVs](./dictionary/one-point-functions-and-vevs/) | Extracting expectation values from renormalized variations. |
| [Spin, Symmetry, and Conserved Currents](./dictionary/spin-symmetry-and-conserved-currents/) | Scalars, spinors, gauge fields, currents, and symmetries. |
| [Stress Tensor and the Metric](./dictionary/stress-tensor-and-the-metric/) | The boundary metric source and holographic stress tensor. |

### Holographic Renormalization

| Page | Purpose |
|---|---|
| [Why Renormalization Is Needed](./holographic-renormalization/why-renormalization-is-needed/) | Infinite AdS volume, UV/IR relation, and local counterterms. |
| [Near-Boundary Expansion](./holographic-renormalization/near-boundary-expansion/) | The asymptotic expansions for scalars, metrics, and gauge fields. |
| [Counterterms and Renormalized Action](./holographic-renormalization/counterterms-and-renormalized-action/) | Constructing $S_{\rm ren}$ from regulated actions and counterterms. |
| [One-Point Functions from Variation](./holographic-renormalization/one-point-functions-from-variation/) | Canonical momenta and finite vevs. |
| [Ward Identities and Anomalies](./holographic-renormalization/ward-identities-and-anomalies/) | Gauge, diffeomorphism, and Weyl identities from bulk constraints. |
| [Radial Hamiltonian Viewpoint](./holographic-renormalization/radial-hamiltonian-viewpoint/) | Holographic renormalization as a Hamilton–Jacobi problem. |
| [Practical Recipe](./holographic-renormalization/practical-recipe/) | A reusable checklist for calculations. |

### Correlators and Probes

| Page | Purpose |
|---|---|
| [Witten Diagrams](./correlators-probes/witten-diagrams/) | The AdS analogue of Feynman diagrams. |
| [Three-Point Functions and Bulk Couplings](./correlators-probes/three-point-functions-and-bulk-couplings/) | Cubic couplings and CFT OPE coefficients. |
| [Four-Point Functions and Bulk Locality](./correlators-probes/four-point-functions-and-bulk-locality/) | Cross ratios, double-trace towers, Mellin amplitudes, and locality. |
| [Heavy Operators and Geodesics](./correlators-probes/heavy-operators-and-geodesics/) | Large-$\Delta$ operators as bulk particles. |
| [Wilson Loops](./correlators-probes/wilson-loops/) | Fundamental strings ending on boundary loops. |
| [Probe Branes and Flavor](./correlators-probes/probe-branes-and-flavor/) | Flavor branes, mesons, and probe limits. |
| [Bulk Causality and Boundary Consistency](./correlators-probes/bulk-causality-and-boundary-consistency/) | Boundary constraints on bulk effective interactions. |

### Thermal and Real-Time Holography

| Page | Purpose |
|---|---|
| [Black Branes and Thermal CFTs](./thermal-real-time/black-branes-and-thermal-cfts/) | Planar horizons as homogeneous thermal states. |
| [Hawking–Page transition](./thermal-real-time/hawking-page-transition/) | Thermal AdS versus global AdS black holes. |
| [Euclidean Gravity and Free Energy](./thermal-real-time/euclidean-gravity-and-free-energy/) | Computing $F$, $E$, and $S$ from $I_E$. |
| [Real-Time Prescription](./thermal-real-time/real-time-prescription/) | Lorentzian AdS/CFT and infalling boundary conditions. |
| [Retarded Green Functions](./thermal-real-time/retarded-green-functions/) | Practical computation of $G_R$. |
| [Quasinormal Modes](./thermal-real-time/quasinormal-modes/) | QNM spectra as poles of retarded correlators. |
| [Hydrodynamics from Gravity](./thermal-real-time/hydrodynamics-from-gravity/) | Fluid/gravity and long-wavelength black-brane dynamics. |
| [Shear Viscosity](./thermal-real-time/shear-viscosity/) | The Kubo calculation of $\eta/s=1/(4\pi)$. |

### Entanglement and Geometry

| Page | Purpose |
|---|---|
| [Entanglement Entropy in QFT](./entanglement-geometry/entanglement-entropy-in-qft/) | Reduced density matrices, replica trick, and modular Hamiltonians. |
| [Ryu–Takayanagi formula](./entanglement-geometry/ryu-takayanagi-formula/) | Static holographic entanglement from minimal surfaces. |
| [Covariant HRT formula](./entanglement-geometry/covariant-hrt-formula/) | Time-dependent entanglement from extremal surfaces. |
| [Entanglement Wedges](./entanglement-geometry/entanglement-wedges/) | Subregion duality and reconstructable bulk regions. |
| [Relative Entropy and Linearized Gravity](./entanglement-geometry/relative-entropy-and-linearized-gravity/) | How entanglement first laws imply linearized Einstein equations. |
| [Quantum Extremal Surfaces](./entanglement-geometry/quantum-extremal-surfaces/) | Generalized entropy and bulk quantum corrections. |
| [Islands and Information](./entanglement-geometry/islands-and-information/) | Page curves, islands, and black-hole information. |

### AdS$_3$/CFT$_2$

| Page | Purpose |
|---|---|
| [Why AdS$_3$ Is Special](./ads3-cft2/why-ads3-is-special/) | No local gravitons, boundary gravitons, and strong CFT$_2$ control. |
| [Brown–Henneaux central charge](./ads3-cft2/brown-henneaux-central-charge/) | The derivation and meaning of $c=3L/(2G_3)$. |
| [BTZ Black Holes](./ads3-cft2/btz-black-holes/) | Rotating BTZ geometry, thermodynamics, and CFT charges. |
| [Cardy Formula and Black-Hole Entropy](./ads3-cft2/cardy-formula-and-black-hole-entropy/) | Matching BTZ entropy from Virasoro state counting. |
| [Virasoro Symmetry and Boundary Gravitons](./ads3-cft2/virasoro-symmetry-and-boundary-gravitons/) | Physical large diffeomorphisms and the vacuum module. |
| [Lessons for Higher-Dimensional Holography](./ads3-cft2/lessons-for-higher-dimensional-holography/) | What generalizes and what is special to three dimensions. |

### Applications and Beyond

| Page | Purpose |
|---|---|
| [What Counts as a Holographic CFT?](./applications-beyond/what-counts-as-a-holographic-cft/) | Large $N$, sparse spectrum, large gap, and local bulk EFT. |
| [Other AdS Backgrounds](./applications-beyond/other-ads-backgrounds/) | ABJM, M5, conifolds, D1-D5, quivers, and internal spaces. |
| [RG Flows and Domain Walls](./applications-beyond/rg-flows-and-domain-walls/) | Relevant deformations and radial evolution. |
| [Confinement and Hard-Wall Models](./applications-beyond/confinement-and-hard-wall-models/) | Mass gaps, hard-wall AdS/QCD, and confinement diagnostics. |
| [Finite Density and Bulk Gauge Fields](./applications-beyond/finite-density-and-bulk-gauge-fields/) | Chemical potentials, charge density, and boundary conditions. |
| [Reissner–Nordstrom AdS](./applications-beyond/reissner-nordstrom-ads/) | Charged black branes and finite-density states. |
| [AdS$_2$ Throats and IR Criticality](./applications-beyond/ads2-throats-and-ir-criticality/) | Emergent near-horizon scaling at extremality. |
| [Holographic Conductivity](./applications-beyond/holographic-conductivity/) | Kubo formulas, membrane paradigm, and transport caveats. |
| [Holographic Superconductors](./applications-beyond/holographic-superconductors/) | Charged scalar hair and condensates. |
| [Fermions and Spectral Functions](./applications-beyond/fermions-and-spectral-functions/) | Bulk spinors, spectral densities, and holographic Fermi surfaces. |
| [Bottom-Up Models](./applications-beyond/bottom-up-models/) | How to build useful phenomenological holographic models responsibly. |
| [Limits of the Dictionary](./applications-beyond/limits-of-the-dictionary/) | What is controlled, what is effective, and what is still speculative. |

### Bulk Quantum Gravity from CFT

| Page | Purpose |
|---|---|
| [Bulk Effective Field Theory](./bulk-quantum-gravity/bulk-effective-field-theory/) | How CFT data yields approximate local bulk EFT. |
| [Large N Factorization and Fock Space](./bulk-quantum-gravity/large-n-factorization-and-fock-space/) | Multiparticle bulk Hilbert spaces from multi-trace operators. |
| [Bulk Reconstruction](./bulk-quantum-gravity/bulk-reconstruction/) | HKLL, subregion reconstruction, and gravitational dressing. |
| [Quantum Error Correction](./bulk-quantum-gravity/quantum-error-correction/) | Redundant encoding, code subspaces, and entanglement wedges. |
| [Black-Hole Information in AdS/CFT](./bulk-quantum-gravity/black-hole-information-in-ads-cft/) | Boundary unitarity, Page curves, islands, and interiors. |
| [Stringy and Quantum Corrections](./bulk-quantum-gravity/stringy-and-quantum-corrections/) | $1/N$, $1/\lambda$, higher-derivative, KK, and nonperturbative corrections. |
| [Open Problems and Research Map](./bulk-quantum-gravity/open-problems-and-research-map/) | Research directions after the course. |

### Appendices

| Page | Purpose |
|---|---|
| [Notation](./appendices/notation/) | Symbols and conventions used throughout the course. |
| [Differential Geometry Cheatsheet](./appendices/differential-geometry-cheatsheet/) | Curvature, hypersurfaces, extrinsic curvature, and Brown–York data. |
| [AdS Coordinate Systems](./appendices/ads-coordinate-systems/) | A reference atlas for common AdS metrics. |
| [Variational Principles and Boundary Terms](./appendices/variational-principles-and-boundary-terms/) | Scalar, Maxwell, gravity, fermion, and mixed-boundary variations. |
| [Green Functions Cheatsheet](./appendices/green-functions-cheatsheet/) | Euclidean, retarded, Feynman, spectral, thermal, and SK correlators. |
| [CFT Cheatsheet](./appendices/cft-cheatsheet/) | Conformal symmetry, OPEs, blocks, Ward identities, and CFT data. |
| [String Theory Cheatsheet](./appendices/string-theory-cheatsheet/) | Strings, branes, fluxes, parameter maps, and correction hierarchies. |
| [Problem Sets](./appendices/problem-sets/) | Course-wide exercises with solutions. |
| [Bibliography](./appendices/bibliography/) | Annotated references and reading paths. |

## Dictionary at a glance

| Boundary QFT | Bulk AdS description |
|---|---|
| spacetime where the QFT lives | conformal boundary of AdS |
| energy scale | radial position |
| source $\phi_{(0)}$ | boundary value of bulk field $\phi$ |
| local operator $\mathcal O$ | bulk field $\phi$ |
| expectation value $\langle\mathcal O\rangle$ | normalizable response of $\phi$ |
| stress tensor $T_{ij}$ | bulk metric $g_{MN}$ |
| conserved current $J^i$ | bulk gauge field $A_M$ |
| thermal state | AdS black hole or black brane |
| entropy | horizon area or extremal-surface area |
| large $N$ | weak bulk quantum loops |
| large $\lambda$ or large spectral gap | weak stringy/higher-spin corrections |

This table is only a first orientation. Every entry has qualifications, and many of the most important pages explain those qualifications.

## Common false starts

### “The boundary is a wall inside AdS.”

Not quite. The AdS boundary is reached after conformal compactification. It is not an ordinary material surface at finite proper distance.

### “The radial direction is just another spatial direction.”

From the bulk point of view, it is geometric. From the boundary point of view, it is tied to energy scale and renormalization.

### “Classical gravity is AdS/CFT.”

Classical gravity is a limit of AdS/CFT. The full correspondence involves quantum string theory or M-theory.

### “Every CFT has a simple Einstein-gravity dual.”

No. A simple local bulk EFT requires special CFT properties, especially large $N$ and a sparse light spectrum with a large gap.

## How to use the course

A good first pass is to read for structure rather than mastery. Learn what each page is for, then return to the derivations when you need them. The appendices are designed to be opened constantly while reading the main course pages.

The exercises are intentionally mixed: some check definitions, some reproduce core derivations, and some point toward research-level questions. Work through the solved exercises actively; many contain the fastest route to understanding the dictionary.
