---
title: "Bibliography"
description: "An annotated reading guide for AdS/CFT Foundations, organized by topic, course unit, and level of urgency."
sidebar:
  order: 90
---

This bibliography is a reading map, not a museum catalogue. The goal is to help you decide what to read next, why it matters, and where it fits in the logic of AdS/CFT.

The course itself is meant to be self-contained. The references below play three different roles:

- **Primary sources** are the papers that introduced a central idea or formula.
- **Reviews and lecture notes** are the best way to learn a topic efficiently.
- **Research gateways** are references that take you from the foundations into active research literature.

A good strategy is to read primary papers only after you know what question they answer. Many foundational papers are short but conceptually dense. Many reviews are long but pedagogically safer. Use both.

## A minimal reading stack

For a first serious pass through AdS/CFT, start with the following sequence.

### 1. The original proposal

**J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).**

This is the original AdS/CFT paper. It presents the D3-brane argument, the near-horizon geometry, and the broad claim that certain large-$N$ CFTs are dual to string/M-theory on AdS backgrounds. Read it once for the idea, then again after understanding D-branes and the parameter map.

### 2. The generating-functional dictionary

**S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).**

**E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).**

Together these are the origin of the GKP/Witten prescription,

$$
Z_{\mathrm{CFT}}[J]
=
Z_{\mathrm{bulk}}[\phi\to J].
$$

These papers turn the duality from a structural claim into a computational tool for CFT correlators.

### 3. The classic review

**O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).**

Still one of the most useful long reviews of the original subject. It covers the D-brane origin, the dictionary, finite temperature, other AdS backgrounds, and many early tests. It is not beginner-short, but it is exceptionally broad.

### 4. Holographic renormalization

**K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).**

**S. de Haro, S. N. Solodukhin, and K. Skenderis, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).**

The GKP/Witten formula is only schematic until divergences, counterterms, and one-point functions are handled properly. These references are the standard entry point to doing holographic calculations responsibly.

### 5. Real-time finite-temperature holography

**D. T. Son and A. O. Starinets, [Minkowski-Space Correlators in AdS/CFT Correspondence: Recipe and Applications](https://arxiv.org/abs/hep-th/0205051).**

This paper explains how retarded Green functions arise from infalling horizon boundary conditions, and why quasinormal frequencies become poles of retarded correlators.

### 6. Holographic entanglement

**S. Ryu and T. Takayanagi, [Holographic Derivation of Entanglement Entropy from AdS/CFT](https://arxiv.org/abs/hep-th/0603001).**

**V. E. Hubeny, M. Rangamani, and T. Takayanagi, [A Covariant Holographic Entanglement Entropy Proposal](https://arxiv.org/abs/0705.0016).**

These papers introduce the RT and HRT prescriptions,

$$
S_A = \frac{\mathrm{Area}(\gamma_A)}{4G_N},
$$

and their covariant generalization. They are essential for the modern geometry-from-entanglement view of holography.

### 7. AdS$_3$/CFT$_2$

**J. D. Brown and M. Henneaux, [Central Charges in the Canonical Realization of Asymptotic Symmetries: An Example from Three-Dimensional Gravity](https://projecteuclid.org/journals/communications-in-mathematical-physics/volume-104/issue-2/Central-charges-in-the-canonical-realization-of-asymptotic-symmetries/cmp/1104114999.full).**

This predates Maldacena's AdS/CFT proposal but is one of its clearest antecedents. It shows that asymptotically AdS$_3$ gravity has a Virasoro asymptotic symmetry algebra with

$$
c = \frac{3L}{2G_3}.
$$

## General textbooks, reviews, and lecture notes

### Broad AdS/CFT and holography reviews

**O. Aharony et al., [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).**

The classic all-purpose review. Best for readers who want a broad map of the original subject, including string-theory examples and early checks.

**I. R. Klebanov, [TASI Lectures: Introduction to the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0009139).**

A concise, friendly early introduction with a clear discussion of D3-branes, correlation functions, and Wilson loops.

**E. D'Hoker and D. Z. Freedman, [Supersymmetric Gauge Theories and the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0201253).**

A detailed review of $\mathcal N=4$ SYM, supergravity, correlation functions, and the supersymmetric structure of the canonical example. More technical than the present course.

**J. M. Maldacena, [TASI 2003 Lectures on AdS/CFT](https://arxiv.org/abs/hep-th/0309246).**

A compact set of lectures by Maldacena emphasizing the physical logic of the duality and its use in black-hole physics.

**J. Polchinski, [Introduction to Gauge/Gravity Duality](https://arxiv.org/abs/1010.6134).**

Excellent for the conceptual bridge between D-branes, strings, large $N$, and emergent gravity.

**J. McGreevy, [Holographic Duality with a View Toward Many-Body Physics](https://arxiv.org/abs/0909.0518).**

A broad and opinionated introduction with emphasis on condensed-matter motivations and holographic effective models.

**M. Ammon and J. Erdmenger, *Gauge/Gravity Duality: Foundations and Applications*.**

A textbook treatment, useful when you want a single-volume companion to the course.

**M. Natsuume, *AdS/CFT Duality User Guide*.**

A practical and calculation-friendly book, especially useful for thermodynamics, correlators, and transport.

**S. A. Hartnoll, A. Lucas, and S. Sachdev, *Holographic Quantum Matter*.**

A focused book on finite-density and condensed-matter applications, useful for the Applications and Beyond unit.

### String theory background

**J. Polchinski, *String Theory*, Volumes 1 and 2.**

The standard textbook. Volume 2 is especially important for D-branes, RR fields, and the string-theory origin of AdS/CFT.

**J. Polchinski, [TASI Lectures on D-Branes](https://arxiv.org/abs/hep-th/9611050).**

Probably the best short D-brane reference for this course. It explains why D-branes are both places where open strings end and sources for closed-string fields.

**C. V. Johnson, *D-Branes*.**

A detailed pedagogical book on D-branes, brane dynamics, and string-theory technology.

**B. Zwiebach, *A First Course in String Theory*.**

Less technical than Polchinski; useful for first exposure to strings, worldsheet ideas, and the string spectrum.

**D. Tong, [String Theory Lecture Notes](https://www.damtp.cam.ac.uk/user/tong/string.html).**

Clear lecture notes for basic string theory. Useful when the course briefly invokes string tension, $\alpha'$, worldsheet actions, and open/closed strings.

### Conformal field theory background

**P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*.**

The classic CFT textbook, especially strong for two-dimensional CFT.

**S. Rychkov, [EPFL Lectures on Conformal Field Theory in $D\ge 3$ Dimensions](https://arxiv.org/abs/1601.05000).**

A modern, clear introduction to higher-dimensional CFT, conformal symmetry, operator dimensions, OPEs, and bootstrap language.

**D. Simmons-Duffin, [TASI Lectures on the Conformal Bootstrap](https://arxiv.org/abs/1602.07982).**

A very useful modern CFT reference. Especially good for conformal blocks, crossing, and CFT data.

**H. Osborn and A. C. Petkou, [Implications of Conformal Invariance in Field Theories for General Dimensions](https://arxiv.org/abs/hep-th/9307010).**

A standard reference for conformal correlators, currents, and stress tensors in general dimensions.

**P. Calabrese and J. Cardy, [Entanglement Entropy and Conformal Field Theory](https://arxiv.org/abs/0905.4013).**

Useful for the two-dimensional CFT side of entanglement and the replica trick.

## Unit-by-unit references

## Orientation

### Holographic principle and black-hole entropy

**J. D. Bekenstein, [Black Holes and Entropy](https://doi.org/10.1103/PhysRevD.7.2333).**

Introduces the idea that black holes carry entropy proportional to horizon area.

**S. W. Hawking, [Particle Creation by Black Holes](https://doi.org/10.1007/BF02345020).**

Establishes Hawking radiation and the temperature of black holes.

**G. 't Hooft, [Dimensional Reduction in Quantum Gravity](https://arxiv.org/abs/gr-qc/9310026).**

One of the original statements of the holographic principle.

**L. Susskind, [The World as a Hologram](https://arxiv.org/abs/hep-th/9409089).**

A foundational essay on holography as a principle of quantum gravity.

**R. Bousso, [The Holographic Principle](https://arxiv.org/abs/hep-th/0203101).**

A broad review of entropy bounds and holographic ideas beyond AdS/CFT.

### Original AdS/CFT structure

**J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).**

The starting point for the course.

**S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).**

The source/operator generating-functional prescription.

**E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).**

The boundary-condition and CFT-generating-functional viewpoint.

## CFT and Large $N$

### Large-$N$ expansion

**G. 't Hooft, [A Planar Diagram Theory for Strong Interactions](https://doi.org/10.1016/0550-3213(74)90154-0).**

The origin of the topological expansion of gauge theory Feynman diagrams.

**E. Witten, [Baryons in the $1/N$ Expansion](https://doi.org/10.1016/0550-3213(79)90232-3).**

A classic paper on large-$N$ QCD. Not directly an AdS/CFT paper, but very useful for large-$N$ intuition.

**S. Coleman, *Aspects of Symmetry*.**

Contains valuable large-$N$ discussions in a broader QFT context.

**A. A. Migdal, *Loop Equations and $1/N$ Expansion*.**

Useful historically for large-$N$ gauge theory and Wilson-loop methods.

### CFT data and correlators

**S. Rychkov, [EPFL Lectures on Conformal Field Theory in $D\ge 3$ Dimensions](https://arxiv.org/abs/1601.05000).**

Best short modern introduction to the CFT data viewpoint.

**D. Simmons-Duffin, [TASI Lectures on the Conformal Bootstrap](https://arxiv.org/abs/1602.07982).**

Especially useful for four-point functions, OPEs, crossing, and conformal blocks.

**H. Osborn and A. C. Petkou, [Implications of Conformal Invariance in Field Theories for General Dimensions](https://arxiv.org/abs/hep-th/9307010).**

The standard technical source for conformal Ward identities and tensor structures.

### $\mathcal N=4$ super-Yang–Mills

**L. Brink, J. H. Schwarz, and J. Scherk, [Supersymmetric Yang–Mills Theories](https://doi.org/10.1016/0550-3213(77)90328-5).**

An early foundational reference for supersymmetric Yang–Mills theory.

**M. F. Sohnius, [Introducing Supersymmetry](https://doi.org/10.1016/0370-1573(85)90023-7).**

A classic supersymmetry review. Useful background, though more than this course requires.

**L. S. Brown, [Dimensional Regularization of Composite Operators in Scalar Field Theory](https://doi.org/10.1016/0003-4916(80)90226-6).**

Useful background for operator renormalization and sources, though not specific to AdS/CFT.

**N. Beisert et al., [Review of AdS/CFT Integrability: An Overview](https://arxiv.org/abs/1012.3982).**

For readers who want to understand the integrability side of planar $\mathcal N=4$ SYM. This is advanced and not part of the core course.

### Thermal field theory

**M. Le Bellac, *Thermal Field Theory*.**

A standard textbook reference for Matsubara correlators, KMS relations, and real-time finite-temperature QFT.

**J. I. Kapusta and C. Gale, *Finite-Temperature Field Theory*.**

Another standard reference, broader in particle/nuclear applications.

**A. Das, *Finite Temperature Field Theory*.**

Useful for compact derivations of imaginary-time and real-time formalisms.

## Anti-de Sitter geometry

### AdS spacetime and coordinates

**S. W. Hawking and G. F. R. Ellis, *The Large Scale Structure of Space-Time*.**

Classic GR background. Useful for causal structure, conformal diagrams, and global spacetime reasoning.

**R. M. Wald, *General Relativity*.**

The standard reference for GR conventions, variational principles, black holes, and global methods.

**M. Henneaux and C. Teitelboim, *Asymptotically Anti-de Sitter Spaces*.**

A foundational reference for AdS asymptotics and boundary conditions.

**P. Breitenlohner and D. Z. Freedman, [Stability in Gauged Extended Supergravity](https://doi.org/10.1016/0370-2693(82)90643-8).**

The origin of the BF stability bound.

**P. Breitenlohner and D. Z. Freedman, [Positive Energy in Anti-de Sitter Backgrounds and Gauged Extended Supergravity](https://doi.org/10.1016/0003-4916(82)90116-6).**

The detailed positive-energy analysis behind the BF bound.

### AdS black holes and Euclidean gravity

**G. W. Gibbons and S. W. Hawking, [Action Integrals and Partition Functions in Quantum Gravity](https://doi.org/10.1103/PhysRevD.15.2752).**

The classic Euclidean-gravity path-integral reference.

**S. W. Hawking and D. N. Page, [Thermodynamics of Black Holes in Anti-de Sitter Space](https://projecteuclid.org/journals/communications-in-mathematical-physics/volume-87/issue-4/Thermodynamics-of-black-holes-in-anti-de-Sitter-space/cmp/1103922135.full).**

The Hawking–Page transition.

**E. Witten, [Anti-de Sitter Space, Thermal Phase Transition, and Confinement in Gauge Theories](https://arxiv.org/abs/hep-th/9803131).**

The AdS/CFT interpretation of the Hawking–Page transition.

**J. D. Brown and J. W. York, [Quasilocal Energy and Conserved Charges Derived from the Gravitational Action](https://arxiv.org/abs/gr-qc/9209012).**

The Brown–York stress tensor, central to holographic stress-tensor calculations.

**V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).**

The standard holographic stress-tensor paper using counterterms.

## String theory origin

### D-branes and open/closed strings

**J. Polchinski, [Dirichlet-Branes and Ramond–Ramond Charges](https://arxiv.org/abs/hep-th/9510017).**

The original D-brane charge paper.

**J. Polchinski, [TASI Lectures on D-Branes](https://arxiv.org/abs/hep-th/9611050).**

The best concise D-brane reference for this course.

**C. G. Callan and J. M. Maldacena, [Brane Dynamics from the Born–Infeld Action](https://arxiv.org/abs/hep-th/9708147).**

Useful for understanding brane effective actions and string/brane solitons.

**A. A. Tseytlin, [Born–Infeld Action, Supersymmetry and String Theory](https://arxiv.org/abs/hep-th/9908105).**

A review of DBI actions and their string-theory origin.

### D3-branes and the near-horizon limit

**J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).**

The original D3-brane near-horizon argument.

**G. T. Horowitz and A. Strominger, [Black Strings and $p$-Branes](https://doi.org/10.1016/0550-3213(91)90440-9).**

An early black-brane reference.

**I. R. Klebanov, [World Volume Approach to Absorption by Non-Dilatonic Branes](https://arxiv.org/abs/hep-th/9702076).**

Important early evidence for D3-brane/gauge-theory matching.

**S. S. Gubser, I. R. Klebanov, and A. A. Tseytlin, [String Theory and Classical Absorption by Three-Branes](https://arxiv.org/abs/hep-th/9703040).**

Another important precursor to the D3-brane duality.

**N. Itzhaki, J. M. Maldacena, J. Sonnenschein, and S. Yankielowicz, [Supergravity and the Large $N$ Limit of Theories with Sixteen Supercharges](https://arxiv.org/abs/hep-th/9802042).**

The general D$p$-brane decoupling-limit analysis.

## The basic dictionary

### GKPW and scalar correlators

**S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).**

The original correlator prescription.

**E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).**

The original boundary-condition prescription.

**D. Z. Freedman, S. D. Mathur, A. Matusis, and L. Rastelli, [Correlation Functions in the CFT$_d$/AdS$_{d+1}$ Correspondence](https://arxiv.org/abs/hep-th/9804058).**

A standard explicit computation of two- and three-point functions.

**H. Liu and A. A. Tseytlin, [On Four-Point Functions in the CFT/AdS Correspondence](https://arxiv.org/abs/hep-th/9807097).**

Useful for early explicit four-point calculations.

**W. Mueck and K. S. Viswanathan, [Conformal Field Theory Correlators from Classical Scalar Field Theory on AdS](https://arxiv.org/abs/hep-th/9804035).**

A compact early scalar-correlator reference.

### Alternate quantization and multi-trace deformations

**I. R. Klebanov and E. Witten, [AdS/CFT Correspondence and Symmetry Breaking](https://arxiv.org/abs/hep-th/9905104).**

The standard alternate-quantization and double-trace boundary-condition reference.

**E. Witten, [Multi-Trace Operators, Boundary Conditions, and AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0112258).**

The classic multi-trace boundary-condition paper.

**M. Berkooz, A. Sever, and A. Shomer, [Double-Trace Deformations, Boundary Conditions and Spacetime Singularities](https://arxiv.org/abs/hep-th/0112264).**

A related treatment of double-trace deformations and boundary conditions.

**T. Faulkner, G. T. Horowitz, and M. M. Roberts, [Holographic Quantum Criticality from Multi-Trace Deformations](https://arxiv.org/abs/1008.1581).**

Useful for seeing alternate/mixed quantization in finite-density applications.

### Spin, currents, stress tensors

**D. Z. Freedman, S. D. Mathur, A. Matusis, and L. Rastelli, [Correlation Functions in the CFT$_d$/AdS$_{d+1}$ Correspondence](https://arxiv.org/abs/hep-th/9804058).**

A useful baseline for scalar correlators and Witten diagram normalization.

**M. Henningson and K. Sfetsos, [Spinors and the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/9803251).**

An early spinor dictionary reference.

**W. Mueck and K. S. Viswanathan, [Conformal Field Theory Correlators from Classical Field Theory on Anti-de Sitter Space II: Vector and Spinor Fields](https://arxiv.org/abs/hep-th/9805145).**

Vector and spinor correlators.

**V. Balasubramanian and P. Kraus, [A Stress Tensor for Anti-de Sitter Gravity](https://arxiv.org/abs/hep-th/9902121).**

The holographic stress tensor in practical form.

**M. Henningson and K. Skenderis, [The Holographic Weyl Anomaly](https://arxiv.org/abs/hep-th/9806087).**

The original holographic Weyl-anomaly computation.

## Holographic renormalization

### Core references

**S. de Haro, S. N. Solodukhin, and K. Skenderis, [Holographic Reconstruction of Spacetime and Renormalization in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0002230).**

The standard Fefferman–Graham reconstruction and holographic-renormalization paper.

**K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).**

The best lecture-note entry point.

**M. Bianchi, D. Z. Freedman, and K. Skenderis, [Holographic Renormalization](https://arxiv.org/abs/hep-th/0112119).**

A useful treatment of renormalization and one-point functions.

**I. Papadimitriou and K. Skenderis, [AdS/CFT Correspondence and Geometry](https://arxiv.org/abs/hep-th/0404176).**

A geometric and Hamiltonian perspective on holographic renormalization.

**I. Papadimitriou, [Holographic Renormalization as a Canonical Transformation](https://arxiv.org/abs/1007.4592).**

A deeper Hamiltonian formulation, good for advanced readers.

### Ward identities and anomalies

**M. Henningson and K. Skenderis, [The Holographic Weyl Anomaly](https://arxiv.org/abs/hep-th/9806087).**

The classic reference for holographic conformal anomalies.

**M. Bianchi, D. Z. Freedman, and K. Skenderis, [How to Go with an RG Flow](https://arxiv.org/abs/hep-th/0105276).**

Useful for one-point functions and Ward identities along holographic RG flows.

**D. Martelli and W. Mueck, [Holographic Renormalization and Ward Identities with the Hamilton-Jacobi Method](https://arxiv.org/abs/hep-th/0205061).**

A Hamilton–Jacobi approach to Ward identities.

## Correlators and probes

### Witten diagrams and CFT data

**E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).**

The origin of the AdS path-integral viewpoint.

**D. Z. Freedman, S. D. Mathur, A. Matusis, and L. Rastelli, [Correlation Functions in the CFT$_d$/AdS$_{d+1}$ Correspondence](https://arxiv.org/abs/hep-th/9804058).**

Standard explicit two- and three-point calculations.

**E. D'Hoker and D. Z. Freedman, [General Scalar Exchange in AdS$_{d+1}$](https://arxiv.org/abs/hep-th/9903196).**

A classic Witten-diagram exchange reference.

**E. D'Hoker, D. Z. Freedman, S. D. Mathur, A. Matusis, and L. Rastelli, [Graviton Exchange and Complete Four-Point Functions in the AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/9903196).**

A more advanced reference for four-point functions involving exchange diagrams.

**J. Penedones, [Writing CFT Correlation Functions as AdS Scattering Amplitudes](https://arxiv.org/abs/1011.1485).**

A key Mellin-space reference connecting CFT correlators to AdS scattering intuition.

**A. L. Fitzpatrick, J. Kaplan, J. Penedones, S. Raju, and B. C. van Rees, [A Natural Language for AdS/CFT Correlators](https://arxiv.org/abs/1107.1499).**

A major reference for Mellin amplitudes and bulk-locality intuition.

**M. S. Costa, V. Goncalves, and J. Penedones, [Spinning AdS Propagators](https://arxiv.org/abs/1404.5625).**

Useful for spinning correlators and tensor structures.

### Bulk locality from CFT

**I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151).**

The standard large-$N$ plus large-gap argument for local bulk EFT.

**A. L. Fitzpatrick and J. Kaplan, [Analyticity and the Holographic S-Matrix](https://arxiv.org/abs/1111.6972).**

Useful for connecting CFT analyticity to bulk scattering.

**S. El-Showk and K. Papadodimas, [Emergent Spacetime and Holographic CFTs](https://arxiv.org/abs/1101.4163).**

A conceptual reference on emergence of bulk locality.

**X. O. Camanho, J. D. Edelstein, J. Maldacena, and A. Zhiboedov, [Causality Constraints on Corrections to the Graviton Three-Point Coupling](https://arxiv.org/abs/1407.5597).**

A key paper on causality constraints and the need for higher-spin/stringy states when higher-derivative gravity interactions become too large.

### Wilson loops and probes

**J. Maldacena, [Wilson Loops in Large $N$ Field Theories](https://arxiv.org/abs/hep-th/9803002).**

The fundamental string prescription for Wilson loops.

**S.-J. Rey and J.-T. Yee, [Macroscopic Strings as Heavy Quarks in Large $N$ Gauge Theory and Anti-de Sitter Supergravity](https://arxiv.org/abs/hep-th/9803001).**

A parallel original Wilson-loop/string-worldsheet paper.

**N. Drukker, D. J. Gross, and H. Ooguri, [Wilson Loops and Minimal Surfaces](https://arxiv.org/abs/hep-th/9904191).**

Important for circular loops and worldsheet subtleties.

**A. Karch and E. Katz, [Adding Flavor to AdS/CFT](https://arxiv.org/abs/hep-th/0205236).**

The classic flavor-brane reference.

**M. Kruczenski, D. Mateos, R. C. Myers, and D. J. Winters, [Meson Spectroscopy in AdS/CFT with Flavour](https://arxiv.org/abs/hep-th/0304032).**

The canonical D3/D7 meson-spectrum reference.

**A. Karch, E. Katz, D. T. Son, and M. A. Stephanov, [Linear Confinement and AdS/QCD](https://arxiv.org/abs/hep-ph/0602229).**

The soft-wall AdS/QCD model.

## Thermal and real-time holography

### Finite temperature and black branes

**E. Witten, [Anti-de Sitter Space, Thermal Phase Transition, and Confinement in Gauge Theories](https://arxiv.org/abs/hep-th/9803131).**

The finite-temperature AdS/CFT classic.

**S. S. Gubser, I. R. Klebanov, and A. W. Peet, [Entropy and Temperature of Black 3-Branes](https://arxiv.org/abs/hep-th/9602135).**

The near-extremal D3-brane entropy calculation and the famous strong/weak comparison.

**S. S. Gubser, I. R. Klebanov, and A. A. Tseytlin, [Coupling Constant Dependence in the Thermodynamics of $N=4$ Supersymmetric Yang–Mills Theory](https://arxiv.org/abs/hep-th/9805156).**

Finite-coupling corrections to thermodynamics.

### Real-time correlators and quasinormal modes

**D. T. Son and A. O. Starinets, [Minkowski-Space Correlators in AdS/CFT Correspondence: Recipe and Applications](https://arxiv.org/abs/hep-th/0205051).**

The foundational real-time prescription.

**G. Policastro, D. T. Son, and A. O. Starinets, [From AdS/CFT Correspondence to Hydrodynamics](https://arxiv.org/abs/hep-th/0205052).**

Relates black-brane perturbations to hydrodynamic modes.

**P. K. Kovtun and A. O. Starinets, [Quasinormal Modes and Holography](https://arxiv.org/abs/hep-th/0506184).**

A standard reference connecting quasinormal spectra and retarded correlators.

**K. Skenderis and B. C. van Rees, [Real-Time Gauge/Gravity Duality](https://arxiv.org/abs/0902.4010).**

A systematic Schwinger–Keldysh approach to real-time holography.

**C. P. Herzog and D. T. Son, [Schwinger-Keldysh Propagators from AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0212072).**

Important early real-time finite-temperature treatment.

### Hydrodynamics and viscosity

**G. Policastro, D. T. Son, and A. O. Starinets, [Shear Viscosity of Strongly Coupled $N=4$ Supersymmetric Yang–Mills Plasma](https://arxiv.org/abs/hep-th/0104066).**

The original $\eta/s$ calculation.

**P. Kovtun, D. T. Son, and A. O. Starinets, [Viscosity in Strongly Interacting Quantum Field Theories from Black Hole Physics](https://arxiv.org/abs/hep-th/0405231).**

The famous $\eta/s=1/(4\pi)$ result and bound proposal.

**S. Bhattacharyya, V. E. Hubeny, S. Minwalla, and M. Rangamani, [Nonlinear Fluid Dynamics from Gravity](https://arxiv.org/abs/0712.2456).**

The foundational fluid/gravity correspondence paper.

**M. Rangamani, [Gravity and Hydrodynamics: Lectures on the Fluid-Gravity Correspondence](https://arxiv.org/abs/0905.4352).**

A pedagogical review of fluid/gravity.

**N. Iqbal and H. Liu, [Universality of the Hydrodynamic Limit in AdS/CFT and the Membrane Paradigm](https://arxiv.org/abs/0809.3808).**

The membrane-paradigm perspective on transport.

## Entanglement and geometry

### QFT entanglement

**P. Calabrese and J. Cardy, [Entanglement Entropy and Quantum Field Theory](https://arxiv.org/abs/hep-th/0405152).**

The classic CFT entanglement paper.

**P. Calabrese and J. Cardy, [Entanglement Entropy and Conformal Field Theory](https://arxiv.org/abs/0905.4013).**

A review with emphasis on two-dimensional CFT.

**H. Casini and M. Huerta, [Entanglement Entropy in Free Quantum Field Theory](https://arxiv.org/abs/0905.2562).**

A detailed QFT review.

**H. Casini, M. Huerta, and R. C. Myers, [Towards a Derivation of Holographic Entanglement Entropy](https://arxiv.org/abs/1102.0440).**

The sphere-to-hyperbolic-space map and its holographic interpretation.

### RT, HRT, and entanglement wedges

**S. Ryu and T. Takayanagi, [Holographic Derivation of Entanglement Entropy from AdS/CFT](https://arxiv.org/abs/hep-th/0603001).**

The original RT formula.

**S. Ryu and T. Takayanagi, [Aspects of Holographic Entanglement Entropy](https://arxiv.org/abs/hep-th/0605073).**

More examples and early developments.

**V. E. Hubeny, M. Rangamani, and T. Takayanagi, [A Covariant Holographic Entanglement Entropy Proposal](https://arxiv.org/abs/0705.0016).**

The HRT formula.

**A. Lewkowycz and J. Maldacena, [Generalized Gravitational Entropy](https://arxiv.org/abs/1304.4926).**

The gravitational replica argument for RT.

**M. Headrick and T. Takayanagi, [A Holographic Proof of the Strong Subadditivity of Entanglement Entropy](https://arxiv.org/abs/0704.3719).**

A beautiful proof of strong subadditivity for RT.

**A. C. Wall, [Maximin Surfaces, and the Strong Subadditivity of the Covariant Holographic Entanglement Entropy](https://arxiv.org/abs/1211.3494).**

The maximin approach to HRT.

**M. Rangamani and T. Takayanagi, [Holographic Entanglement Entropy](https://arxiv.org/abs/1609.01287).**

The standard review of holographic entanglement.

### Relative entropy, QES, and islands

**N. Lashkari, M. B. McDermott, and M. Van Raamsdonk, [Gravitational Dynamics from Entanglement Thermodynamics](https://arxiv.org/abs/1308.3716).**

A key paper connecting entanglement first laws to linearized gravity.

**T. Faulkner, M. Guica, T. Hartman, R. C. Myers, and M. Van Raamsdonk, [Gravitation from Entanglement in Holographic CFTs](https://arxiv.org/abs/1312.7856).**

A detailed derivation of linearized Einstein equations from entanglement.

**T. Faulkner, A. Lewkowycz, and J. Maldacena, [Quantum Corrections to Holographic Entanglement Entropy](https://arxiv.org/abs/1307.2892).**

The FLM correction:

$$
S_A = \frac{\mathrm{Area}}{4G_N}+S_{\mathrm{bulk}}+\cdots .
$$

**N. Engelhardt and A. C. Wall, [Quantum Extremal Surfaces: Holographic Entanglement Entropy Beyond the Classical Regime](https://arxiv.org/abs/1408.3203).**

The QES prescription.

**D. L. Jafferis, A. Lewkowycz, J. Maldacena, and S. J. Suh, [Relative Entropy Equals Bulk Relative Entropy](https://arxiv.org/abs/1512.06431).**

The JLMS relation.

**G. Penington, [Entanglement Wedge Reconstruction and the Information Paradox](https://arxiv.org/abs/1905.08255).**

A key island/Page-curve paper.

**A. Almheiri, N. Engelhardt, D. Marolf, and H. Maxfield, [The Entropy of Bulk Quantum Fields and the Entanglement Wedge of an Evaporating Black Hole](https://arxiv.org/abs/1905.08762).**

A key island/QES paper.

**A. Almheiri, R. Mahajan, J. Maldacena, and Y. Zhao, [The Page Curve of Hawking Radiation from Semiclassical Geometry](https://arxiv.org/abs/1908.10996).**

A clear semiclassical island construction.

**A. Almheiri, T. Hartman, J. Maldacena, E. Shaghoulian, and A. Tajdini, [The Entropy of Hawking Radiation](https://arxiv.org/abs/2006.06872).**

A review of islands, replica wormholes, and the Page curve.

## AdS$_3$/CFT$_2$

### Brown–Henneaux, BTZ, and Cardy

**J. D. Brown and M. Henneaux, [Central Charges in the Canonical Realization of Asymptotic Symmetries: An Example from Three-Dimensional Gravity](https://projecteuclid.org/journals/communications-in-mathematical-physics/volume-104/issue-2/Central-charges-in-the-canonical-realization-of-asymptotic-symmetries/cmp/1104114999.full).**

The Brown–Henneaux central charge.

**M. Banados, C. Teitelboim, and J. Zanelli, [The Black Hole in Three-Dimensional Space-Time](https://arxiv.org/abs/hep-th/9204099).**

The original BTZ black-hole paper.

**J. L. Cardy, [Operator Content of Two-Dimensional Conformally Invariant Theories](https://doi.org/10.1016/0550-3213(86)90552-3).**

The original Cardy formula paper.

**A. Strominger, [Black Hole Entropy from Near-Horizon Microstates](https://arxiv.org/abs/hep-th/9712251).**

Applies Cardy-type reasoning to black-hole entropy.

**S. Carlip, [Conformal Field Theory, $(2+1)$-Dimensional Gravity, and the BTZ Black Hole](https://arxiv.org/abs/gr-qc/0503022).**

A useful review of BTZ, Cardy, and $2+1$ gravity.

**P. Kraus, [Lectures on Black Holes and the AdS$_3$/CFT$_2$ Correspondence](https://arxiv.org/abs/hep-th/0609074).**

Excellent lectures for the AdS$_3$/CFT$_2$ unit.

### Boundary gravitons and quantum AdS$_3$

**A. Maloney and E. Witten, [Quantum Gravity Partition Functions in Three Dimensions](https://arxiv.org/abs/0712.0155).**

A foundational paper on pure AdS$_3$ gravity path integrals and modular sums.

**S. Giombi, A. Maloney, and X. Yin, [One-Loop Partition Functions of 3D Gravity](https://arxiv.org/abs/0804.1773).**

Boundary gravitons and one-loop determinants.

**A. Castro, A. Maloney, and A. Strominger, [Hidden Conformal Symmetry of the Kerr Black Hole](https://arxiv.org/abs/1004.0996).**

Not directly part of AdS$_3$/CFT$_2$, but useful for understanding how 2D conformal structures reappear in black-hole physics.

**M. R. Gaberdiel, R. Gopakumar, and A. Saha, [Quantum W Symmetry in AdS$_3$](https://arxiv.org/abs/1009.6087).**

A gateway into higher-spin AdS$_3$/CFT$_2$.

## Applications and beyond

### Other AdS backgrounds

**O. Aharony et al., [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).**

Still the best general starting point for other AdS backgrounds.

**O. Aharony, O. Bergman, D. L. Jafferis, and J. Maldacena, [N=6 Superconformal Chern–Simons-Matter Theories, M2-Branes and Their Gravity Duals](https://arxiv.org/abs/0806.1218).**

The ABJM duality.

**I. R. Klebanov and E. Witten, [Superconformal Field Theory on Threebranes at a Calabi–Yau Singularity](https://arxiv.org/abs/hep-th/9807080).**

The conifold AdS$_5$/CFT$_4$ example.

**I. R. Klebanov and M. J. Strassler, [Supergravity and a Confining Gauge Theory: Duality Cascades and $\chi$SB-Resolution of Naked Singularities](https://arxiv.org/abs/hep-th/0007191).**

A central top-down confining background.

**J. M. Maldacena and A. Strominger, [AdS$_3$ Black Holes and a Stringy Exclusion Principle](https://arxiv.org/abs/hep-th/9804085).**

A useful D1-D5/AdS$_3$ reference.

### Holographic RG flows and confinement

**L. Girardello, M. Petrini, M. Porrati, and A. Zaffaroni, [Novel Local CFT and Exact Results on Perturbations of $N=4$ Super Yang Mills from AdS Dynamics](https://arxiv.org/abs/hep-th/9810126).**

An early holographic RG-flow paper.

**D. Z. Freedman, S. S. Gubser, K. Pilch, and N. P. Warner, [Renormalization Group Flows from Holography—Supersymmetry and a c-Theorem](https://arxiv.org/abs/hep-th/9904017).**

A classic domain-wall/c-theorem reference.

**J. de Boer, E. Verlinde, and H. Verlinde, [On the Holographic Renormalization Group](https://arxiv.org/abs/hep-th/9912012).**

An influential holographic RG interpretation.

**J. Polchinski and M. J. Strassler, [The String Dual of a Confining Four-Dimensional Gauge Theory](https://arxiv.org/abs/hep-th/0003136).**

Top-down confinement physics from deformed $\mathcal N=4$ SYM.

**J. Erlich, E. Katz, D. T. Son, and M. A. Stephanov, [QCD and a Holographic Model of Hadrons](https://arxiv.org/abs/hep-ph/0501128).**

The hard-wall AdS/QCD model.

**L. Da Rold and A. Pomarol, [Chiral Symmetry Breaking from Five Dimensional Spaces](https://arxiv.org/abs/hep-ph/0501218).**

Another foundational hard-wall AdS/QCD reference.

**C. P. Herzog, [A Holographic Prediction of the Deconfinement Temperature](https://arxiv.org/abs/hep-th/0608151).**

Hawking–Page-like thermodynamics in hard-wall models.

### Finite density, AdS/CMT, and matter probes

**S. A. Hartnoll, [Lectures on Holographic Methods for Condensed Matter Physics](https://arxiv.org/abs/0903.3246).**

The standard AdS/CMT lecture notes.

**S. A. Hartnoll, C. P. Herzog, and G. T. Horowitz, [Building a Holographic Superconductor](https://arxiv.org/abs/0803.3295).**

The classic holographic superconductor construction.

**C. P. Herzog, [Lectures on Holographic Superfluidity and Superconductivity](https://arxiv.org/abs/0904.1975).**

A focused pedagogical review.

**S. S. Gubser, [Breaking an Abelian Gauge Symmetry Near a Black Hole Horizon](https://arxiv.org/abs/0801.2977).**

The instability mechanism behind holographic superconductors.

**T. Faulkner, H. Liu, J. McGreevy, and D. Vegh, [Emergent Quantum Criticality, Fermi Surfaces, and AdS$_2$](https://arxiv.org/abs/0907.2694).**

The standard AdS$_2$/fermion finite-density reference.

**H. Liu, J. McGreevy, and D. Vegh, [Non-Fermi Liquids from Holography](https://arxiv.org/abs/0903.2477).**

Holographic Fermi surfaces and non-Fermi-liquid spectral functions.

**M. Cubrovic, J. Zaanen, and K. Schalm, [String Theory, Quantum Phase Transitions and the Emergent Fermi Liquid](https://arxiv.org/abs/0904.1993).**

An early holographic fermion paper.

**S. A. Hartnoll and A. Tavanfar, [Electron Stars for Holographic Metallic Criticality](https://arxiv.org/abs/1008.2828).**

A gateway to electron-star finite-density geometries.

**T. Andrade and B. Withers, [A Simple Holographic Model of Momentum Relaxation](https://arxiv.org/abs/1311.5157).**

A simple model for finite DC conductivity with broken translations.

**A. Donos and J. P. Gauntlett, [Thermoelectric DC Conductivities from Black Hole Horizons](https://arxiv.org/abs/1406.4742).**

A practical horizon-formula reference for DC transport.

### Bottom-up models and caveats

**U. Gursoy, E. Kiritsis, and F. Nitti, [Exploring Improved Holographic Theories for QCD](https://arxiv.org/abs/0707.1324).**

Improved holographic QCD.

**S. S. Gubser and A. Nellore, [Mimicking the QCD Equation of State with a Dual Black Hole](https://arxiv.org/abs/0804.0434).**

A widely used Einstein-dilaton modeling reference.

**S. S. Gubser, [Curvature Singularities: The Good, the Bad, and the Naked](https://arxiv.org/abs/hep-th/0002160).**

A key reference for judging singularities in holographic RG flows and bottom-up models.

**S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [A Semi-Classical Limit of the Gauge/String Correspondence](https://arxiv.org/abs/hep-th/0204051).**

A gateway into semiclassical strings and large-charge/stringy sectors.

## Bulk quantum gravity from CFT

### Bulk effective field theory and locality

**I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151).**

The central large-gap/local-EFT reference.

**A. Fitzpatrick, E. Katz, D. Poland, and D. Simmons-Duffin, [Effective Conformal Theory and the Flat-Space Limit of AdS](https://arxiv.org/abs/1007.2412).**

Double-trace operators and the emergence of bulk EFT.

**M. Gary, S. B. Giddings, and J. Penedones, [Local Bulk S-Matrix Elements and CFT Singularities](https://arxiv.org/abs/0903.4437).**

A useful reference on extracting local scattering from CFT data.

**J. Penedones, [Writing CFT Correlation Functions as AdS Scattering Amplitudes](https://arxiv.org/abs/1011.1485).**

Mellin amplitudes and AdS scattering.

### Bulk reconstruction

**A. Hamilton, D. Kabat, G. Lifschytz, and D. A. Lowe, [Local Bulk Operators in AdS/CFT: A Boundary View of Horizons and Locality](https://arxiv.org/abs/hep-th/0506118).**

One of the foundational HKLL papers.

**A. Hamilton, D. Kabat, G. Lifschytz, and D. A. Lowe, [Holographic Representation of Local Bulk Operators](https://arxiv.org/abs/0606141).**

A detailed smearing-function construction.

**D. Kabat, G. Lifschytz, and D. A. Lowe, [Constructing Local Bulk Observables in Interacting AdS/CFT](https://arxiv.org/abs/1102.2910).**

Perturbative corrections to reconstruction.

**S. Leichenauer and V. Rosenhaus, [AdS Black Holes, the Bulk Reconstruction Kernel, and Smearing Functions](https://arxiv.org/abs/1304.6821).**

Useful for reconstruction in black-hole backgrounds.

### Quantum error correction and entanglement wedge reconstruction

**A. Almheiri, X. Dong, and D. Harlow, [Bulk Locality and Quantum Error Correction in AdS/CFT](https://arxiv.org/abs/1411.7041).**

The foundational QEC interpretation.

**F. Pastawski, B. Yoshida, D. Harlow, and J. Preskill, [Holographic Quantum Error-Correcting Codes: Toy Models for the Bulk/Boundary Correspondence](https://arxiv.org/abs/1503.06237).**

The HaPPY code.

**X. Dong, D. Harlow, and A. C. Wall, [Reconstruction of Bulk Operators within the Entanglement Wedge in Gauge-Gravity Duality](https://arxiv.org/abs/1601.05416).**

A central entanglement-wedge reconstruction paper.

**D. Harlow, [Ryu–Takayanagi formula from quantum error correction](https://arxiv.org/abs/1607.03901).**

Operator-algebra QEC and the RT formula.

**D. Harlow, [TASI Lectures on the Emergence of Bulk Physics in AdS/CFT](https://arxiv.org/abs/1802.01040).**

One of the best modern gateways into bulk emergence.

### Black-hole information

**D. N. Page, [Information in Black Hole Radiation](https://arxiv.org/abs/hep-th/9306083).**

The Page-curve logic.

**J. Maldacena, [Eternal Black Holes in Anti-de Sitter](https://arxiv.org/abs/hep-th/0106112).**

The thermofield-double/eternal-black-hole relation.

**D. Harlow, [Jerusalem Lectures on Black Holes and Quantum Information](https://arxiv.org/abs/1409.1231).**

A standard modern black-hole information review.

**A. Almheiri, D. Marolf, J. Polchinski, and J. Sully, [Black Holes: Complementarity or Firewalls?](https://arxiv.org/abs/1207.3123).**

The AMPS paradox.

**K. Papadodimas and S. Raju, [An Infalling Observer in AdS/CFT](https://arxiv.org/abs/1211.6767).**

A notable interior-reconstruction proposal.

**P. Hayden and J. Preskill, [Black Holes as Mirrors: Quantum Information in Random Subsystems](https://arxiv.org/abs/0708.4025).**

The Hayden–Preskill recovery problem.

**Y. Sekino and L. Susskind, [Fast Scramblers](https://arxiv.org/abs/0808.2096).**

The fast-scrambling conjecture.

**J. Maldacena, S. H. Shenker, and D. Stanford, [A Bound on Chaos](https://arxiv.org/abs/1503.01409).**

The chaos bound and its saturation by black holes.

### Stringy and quantum corrections

**S. S. Gubser, I. R. Klebanov, and A. A. Tseytlin, [Coupling Constant Dependence in the Thermodynamics of $N=4$ Supersymmetric Yang–Mills Theory](https://arxiv.org/abs/hep-th/9805156).**

The canonical finite-$\lambda$ correction to thermodynamics.

**J. Pawelczyk and S. Theisen, [AdS$_5\times S^5$ Black Hole Metric at $O(\alpha'^3)$](https://arxiv.org/abs/hep-th/9808126).**

A technical finite-coupling correction reference.

**M. B. Green, J. H. Schwarz, and E. Witten, *Superstring Theory*.**

Classic reference for string perturbation theory and higher-derivative corrections.

**M. B. Green, M. Gutperle, and P. Vanhove, [One Loop in Eleven Dimensions](https://arxiv.org/abs/hep-th/9706175).**

Useful background for higher-derivative terms in string/M-theory.

**T. Banks and M. B. Green, [Non-Perturbative Effects in AdS$_5\times S^5$ String Theory and $d=4$ SUSY Yang–Mills](https://arxiv.org/abs/hep-th/9804170).**

A reference on D-instantons and nonperturbative effects.

### Open directions and broader holography

**L. Susskind and E. Witten, [The Holographic Bound in Anti-de Sitter Space](https://arxiv.org/abs/hep-th/9805114).**

A foundational discussion of holographic bounds in AdS.

**J. Polchinski, [S-Matrices from AdS Space](https://arxiv.org/abs/hep-th/9901076).**

A classic reference for extracting flat-space scattering from AdS.

**J. Penedones, [Writing CFT Correlation Functions as AdS Scattering Amplitudes](https://arxiv.org/abs/1011.1485).**

The Mellin-amplitude approach to the flat-space limit.

**A. Strominger, [The dS/CFT Correspondence](https://arxiv.org/abs/hep-th/0106113).**

A classic de Sitter holography proposal.

**E. Witten, [Quantum Gravity in de Sitter Space](https://arxiv.org/abs/hep-th/0106109).**

A foundational discussion of conceptual obstacles in de Sitter quantum gravity.

**D. Anninos, [De Sitter Musings](https://arxiv.org/abs/1205.3855).**

A useful review-style set of notes on de Sitter holography.

**S. Pasterski, S.-H. Shao, and A. Strominger, [Flat Space Amplitudes and Conformal Symmetry of the Celestial Sphere](https://arxiv.org/abs/1701.00049).**

A gateway to celestial holography.

## Background references by technique

### Differential geometry and variational principles

**R. M. Wald, *General Relativity*.**

The default GR reference for curvature, variational principles, black holes, and the stress tensor.

**S. M. Carroll, *Spacetime and Geometry*.**

A friendly GR textbook. Good for readers who need a fast refresher.

**E. Poisson, *A Relativist's Toolkit*.**

Very useful for hypersurfaces, extrinsic curvature, and practical tensor manipulations.

**J. D. Brown and J. W. York, [Quasilocal Energy and Conserved Charges Derived from the Gravitational Action](https://arxiv.org/abs/gr-qc/9209012).**

The quasilocal stress-tensor reference.

**G. W. Gibbons and S. W. Hawking, [Action Integrals and Partition Functions in Quantum Gravity](https://doi.org/10.1103/PhysRevD.15.2752).**

The boundary term and Euclidean gravity reference.

### Quantum field theory and path integrals

**M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*.**

Standard background for perturbative QFT and generating functionals.

**S. Weinberg, *The Quantum Theory of Fields*, Volumes 1 and 2.**

A comprehensive reference for QFT and symmetry.

**M. Srednicki, *Quantum Field Theory*.**

A clear all-purpose QFT textbook.

**J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*.**

Useful for RG, generating functionals, and field-theory methods.

### Thermal, transport, and response theory

**L. D. Landau and E. M. Lifshitz, *Fluid Mechanics*.**

Classic hydrodynamics.

**P. Kovtun, [Lectures on Hydrodynamic Fluctuations in Relativistic Theories](https://arxiv.org/abs/1205.5040).**

Excellent modern hydrodynamics notes.

**A. Kamenev, *Field Theory of Non-Equilibrium Systems*.**

Useful for Schwinger–Keldysh techniques beyond what this course covers.

**G. D. Mahan, *Many-Particle Physics*.**

A standard many-body reference for spectral functions and response.

## Reading paths

### Path A: Minimal foundations

Read these if you want the shortest route to the core dictionary.

1. Maldacena, original proposal.
2. GKP and Witten, original dictionary.
3. Aharony et al., selected sections 1–3.
4. Skenderis, holographic renormalization lecture notes, first half.
5. Freedman–Mathur–Matusis–Rastelli, scalar correlators.

### Path B: Calculational holography

Read these if you want to compute observables.

1. Freedman–Mathur–Matusis–Rastelli, correlators.
2. de Haro–Solodukhin–Skenderis, near-boundary expansions.
3. Skenderis, holographic renormalization.
4. Son–Starinets, retarded correlators.
5. Iqbal–Liu, membrane paradigm.
6. D'Hoker–Freedman, Witten diagrams.

### Path C: Black holes and thermal QFT

Read these if your interest is thermal field theory, transport, and black holes.

1. Gibbons–Hawking, Euclidean action.
2. Hawking–Page, AdS black-hole thermodynamics.
3. Witten, thermal phase transition and confinement.
4. Gubser–Klebanov–Peet, D3-brane entropy.
5. Policastro–Son–Starinets, shear viscosity.
6. Son–Starinets, real-time correlators.
7. Bhattacharyya et al., fluid/gravity.

### Path D: Entanglement and emergent geometry

Read these if your interest is spacetime from entanglement.

1. Calabrese–Cardy, QFT entanglement.
2. Ryu–Takayanagi, RT formula.
3. Hubeny–Rangamani–Takayanagi, HRT formula.
4. Lewkowycz–Maldacena, gravitational entropy.
5. Faulkner–Lewkowycz–Maldacena, quantum corrections.
6. JLMS, relative entropy.
7. Engelhardt–Wall, QES.
8. Penington and Almheiri–Engelhardt–Marolf–Maxfield, islands.

### Path E: AdS$_3$/CFT$_2$

Read these if you want the sharp low-dimensional laboratory.

1. Brown–Henneaux, central charge.
2. BTZ, black holes in $2+1$ gravity.
3. Cardy, density of states.
4. Strominger, black-hole entropy from CFT.
5. Kraus, AdS$_3$/CFT$_2$ lectures.
6. Maloney–Witten, quantum AdS$_3$ gravity.

### Path F: AdS/CMT and finite-density applications

Read these if you want holography as a tool for strongly coupled matter.

1. Hartnoll, holographic methods lectures.
2. McGreevy, many-body holography review.
3. Iqbal–Liu, membrane paradigm.
4. Hartnoll–Herzog–Horowitz, holographic superconductors.
5. Faulkner–Liu–McGreevy–Vegh, AdS$_2$ and Fermi surfaces.
6. Donos–Gauntlett, DC conductivity from horizons.

### Path G: Bulk quantum gravity from CFT

Read these if you want the modern quantum-gravity interpretation.

1. HPPS, holography from CFT.
2. HKLL, local bulk operators.
3. Almheiri–Dong–Harlow, QEC in AdS/CFT.
4. Dong–Harlow–Wall, entanglement-wedge reconstruction.
5. Harlow, emergence of bulk physics lectures.
6. Harlow, black-hole information lectures.
7. Island papers by Penington and Almheiri et al.

## How to cite results from the course

When using this course in your own notes or research, cite the original papers for precise claims. A few common examples:

| Result or idea | Standard source |
|---|---|
| AdS/CFT proposal | Maldacena, `hep-th/9711200` |
| GKPW prescription | Gubser–Klebanov–Polyakov, `hep-th/9802109`; Witten, `hep-th/9802150` |
| Holographic stress tensor | Balasubramanian–Kraus, `hep-th/9902121` |
| Holographic renormalization | de Haro–Solodukhin–Skenderis, `hep-th/0002230`; Skenderis, `hep-th/0209067` |
| Real-time prescription | Son–Starinets, `hep-th/0205051` |
| Shear viscosity | Policastro–Son–Starinets, `hep-th/0104066`; Kovtun–Son–Starinets, `hep-th/0405231` |
| RT formula | Ryu–Takayanagi, `hep-th/0603001` |
| HRT formula | Hubeny–Rangamani–Takayanagi, `0705.0016` |
| Quantum corrections to RT | Faulkner–Lewkowycz–Maldacena, `1307.2892` |
| QES | Engelhardt–Wall, `1408.3203` |
| Islands | Penington, `1905.08255`; Almheiri–Engelhardt–Marolf–Maxfield, `1905.08762` |
| Brown–Henneaux central charge | Brown–Henneaux, Commun. Math. Phys. 104 (1986) |
| BTZ black hole | Banados–Teitelboim–Zanelli, `hep-th/9204099` |
| Local bulk EFT from CFT | Heemskerk–Penedones–Polchinski–Sully, `0907.0151` |
| Holographic QEC | Almheiri–Dong–Harlow, `1411.7041` |

## A final warning about references

The AdS/CFT literature is unusually interconnected. A reference may be “the original paper” for one idea, “a review” for another, and “too advanced” for a first reader. Read with a question in mind. The best question is usually not “What does this paper say?” but rather:

> Which piece of the bulk/boundary dictionary does this paper make sharper?

That question will keep the literature navigable.
