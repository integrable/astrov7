---
title: "Bibliography"
description: "A curated bibliography for perturbative QFT, scattering, amplitudes, loop technology, infrared physics, precision observables, and computational workflows."
sidebar:
  label: "Bibliography"
  order: 14
level: Graduate
status: "Polished draft"
source: "Srednicki 2007; Coleman 2019; Weinberg 1995–2000; Zee 2010; Schwartz 2014; Zinn-Justin 2021"
topics:
  - bibliography
  - perturbative QFT
  - scattering amplitudes
  - loop integrals
  - precision observables
canonicalTopics:
  - perturbative-qft-bibliography
  - scattering-literature-guide
researchStatus:
  established:
    - "The core textbooks and classic papers listed here are stable reference points for perturbative QFT and scattering."
  active:
    - "The literature on multi-loop amplitudes, infrared subtraction, resummation, event generators, and computational tools evolves quickly, so specialized pages should cite current reviews and package documentation when needed."
---

## Summary

This bibliography is a guided map, not a trophy shelf. Perturbative QFT has too many useful references for one page to list everything responsibly. The goal here is to tell a reader which sources to use for which task: learning the formalism, checking conventions, computing scattering amplitudes, evaluating loop integrals, handling infrared physics, understanding gauge-theory consistency, using modern on-shell methods, and making precision predictions reproducible.

The most efficient reading strategy is not to pick one book forever. Use different sources for different jobs:

| Task | Good starting point |
|---|---|
| Learn the basic perturbative machine | Coleman, Srednicki, Schwartz, Peskin–Schroeder |
| Check scattering and normalization conventions | Weinberg Vol. I, Srednicki, Schwartz |
| Learn diagrammatic renormalization | Srednicki, Schwartz, Peskin–Schroeder, Collins |
| Learn gauge-theory perturbation theory | Weinberg Vols. I–II, Schwartz, Peskin–Schroeder, Sterman |
| Learn loop-integral technology | Smirnov, Collins, Henn, Passarino–Veltman, IBP literature |
| Learn modern amplitudes | Elvang–Huang, Henn–Plefka, Dixon, Bern–Dixon–Kosower reviews |
| Learn infrared and precision physics | Sterman, Collins, Schwartz, QCD and SCET reviews |
| Verify computational workflows | Original tool papers plus current package manuals |

References are grouped by use case. Most ordinary pages in this volume should cite only the few entries relevant to that page, then point here for the wider map.

## How to use this bibliography

If you are learning perturbative QFT for the first time, start with one narrative textbook and one calculation-heavy companion. A good pairing is Srednicki plus Schwartz, or Coleman plus Peskin–Schroeder. If you are already comfortable with the basics and need a reference-grade statement, use Weinberg. If you want physical intuition before doing algebra, Zee is often the quickest way into the room.

If you are doing a calculation, use this order:

1. identify the object being computed: correlator, amplitude, rate, cross section, form factor, or inclusive observable;
2. check the conventions against [Conventions and Notation](/perturbative-qft/conventions/);
3. use a textbook for the conceptual derivation;
4. use original papers or reviews for specialized technology;
5. use package papers and documentation only for implementation details.

A page-specific reference list should be compact. Long reference dumps belong here, not under every derivation.

## Core textbooks for perturbative QFT

### Standard first pass

- **Mark Srednicki, *Quantum Field Theory* (Cambridge, 2007).** Excellent modular structure for scalar theory, LSZ, Feynman rules, cross sections, loop corrections, renormalization, QED, spinor technology, non-Abelian gauge theory, and many model calculations. Especially useful when you want a clean step-by-step calculation.
- **Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory* (World Scientific, 2019).** A superb conceptual and calculational source for interaction-picture perturbation theory, Wick diagrams, scattering, LSZ, renormalization, gauge fixing, Ward identities, current algebra, and spontaneous symmetry breaking. The lectures are unusually good at explaining why a formal step is being taken.
- **Matthew D. Schwartz, *Quantum Field Theory and the Standard Model* (Cambridge, 2014).** Very useful for modern perturbative QFT as used in the Standard Model: S-matrix normalization, QED calculations, renormalized perturbation theory, infrared divergences, Yang–Mills theory, spinor-helicity methods, jets, and SCET.
- **Michael E. Peskin and Daniel V. Schroeder, *An Introduction to Quantum Field Theory* (Westview, 1995).** A classic graduate text for Feynman rules, QED, loops, renormalization, non-Abelian gauge theory, the Standard Model, and practical calculations. Its conventions differ from qft.org in some places, so check signs and normalizations.
- **A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed. (Princeton, 2010).** Best used for physical intuition, quick conceptual orientation, and memorable explanations. It is not the most systematic reference for every normalization, but it is often the fastest way to understand what a calculation means.

### Reference-grade treatments

- **Steven Weinberg, *The Quantum Theory of Fields*, Vol. I: *Foundations* (Cambridge, 1995).** The main reference for scattering theory, one-particle states, S-matrix conventions, cluster decomposition, Feynman rules, symmetries, QED, path integrals, renormalization, and infrared effects from a structural viewpoint.
- **Steven Weinberg, *The Quantum Theory of Fields*, Vol. II: *Modern Applications* (Cambridge, 1996).** Especially useful for non-Abelian gauge theory, BRST, renormalization of gauge theories, the renormalization group, OPE, effective field theory, chiral symmetry, and the Standard Model.
- **Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, 5th ed. (Oxford, 2021).** A deep reference for functional methods, renormalization, RG, composite operators, critical phenomena, and the bridge between particle and statistical field theory. Less scattering-centered, but excellent for understanding why perturbation theory and RG work.
- **Claude Itzykson and Jean-Bernard Zuber, *Quantum Field Theory* (McGraw–Hill, 1980).** A broad classic reference, especially useful for older conventions, diagrammatic methods, gauge theory, renormalization, and connections to statistical physics.
- **Lowell S. Brown, *Quantum Field Theory* (Cambridge, 1992).** A careful and often elegant reference for perturbation theory, Green functions, and gauge-field calculations.

## Scattering theory, phase space, and unitarity

- **Weinberg, Vol. I.** Use chapters on scattering theory, symmetries of the S-matrix, rates and cross sections, perturbation theory, and implications of unitarity.
- **Srednicki.** Use the chapters on LSZ reduction, scattering amplitudes and Feynman rules, cross sections and decay rates, unstable particles, and infrared divergences.
- **Schwartz.** Use the chapters on cross sections and decay rates, the S-matrix and LSZ, QED examples, implications of unitarity, and precision Standard Model calculations.
- **R. J. Eden, P. V. Landshoff, D. I. Olive, and J. C. Polkinghorne, *The Analytic S-Matrix* (Cambridge, 1966).** A classic source for analyticity, branch cuts, dispersion relations, and S-matrix logic.
- **André Martin and Froissart-bound literature.** Use for rigorous high-energy bounds and analyticity constraints when entering dispersion-relation or positivity-bound territory.

### Classic papers

- **F. J. Dyson, “The S Matrix in Quantum Electrodynamics,” *Physical Review* 75 (1949).** A foundational S-matrix and perturbation-theory paper.
- **R. P. Feynman, “Space-Time Approach to Quantum Electrodynamics,” *Physical Review* 76 (1949).** The classic Feynman-diagram paper.
- **G. C. Wick, “The Evaluation of the Collision Matrix,” *Physical Review* 80 (1950).** The classic Wick-theorem paper.
- **H. Lehmann, K. Symanzik, and W. Zimmermann, “Zur Formulierung quantisierter Feldtheorien,” *Nuovo Cimento* 1 (1955).** The original LSZ formulation.
- **R. E. Cutkosky, “Singularities and Discontinuities of Feynman Amplitudes,” *Journal of Mathematical Physics* 1 (1960).** The classic source for cutting rules and discontinuities.

## Diagrammatics and renormalized perturbation theory

- **Coleman.** Particularly strong for the transition from Dyson expansion to Wick diagrams, the meaning of connected diagrams, counterterms, and early renormalization.
- **Srednicki.** Excellent for scalar examples, all-orders perturbation theory, 1PI diagrams, self-energies, vertices, and renormalized amplitudes.
- **Peskin–Schroeder.** Standard source for diagrammatic renormalization, QED, Ward identities, non-Abelian gauge theory, and one-loop examples.
- **Schwartz.** Strong on multiple derivations of Feynman rules, renormalized perturbation theory, counterterms, minimal subtraction, and the relation to the Standard Model.
- **John C. Collins, *Renormalization* (Cambridge, 1984).** A classic deeper source on renormalization, counterterms, power counting, composite operators, and factorization-related thinking.

## Loop integrals and multi-loop technology

### One-loop and tensor reduction

- **G. ’t Hooft and M. Veltman, “Scalar One-Loop Integrals,” *Nuclear Physics B* 153 (1979).** A classic source for one-loop scalar integrals.
- **G. Passarino and M. Veltman, “One-Loop Corrections for $e^+e^-$ Annihilation into $\mu^+\mu^-$ in the Weinberg Model,” *Nuclear Physics B* 160 (1979).** The standard origin of Passarino–Veltman tensor reduction.
- **A. Denner, “Techniques for Calculation of Electroweak Radiative Corrections at the One-Loop Level,” *Fortschritte der Physik* 41 (1993).** A practical reference for one-loop electroweak calculations and conventions.

### Feynman integrals beyond one loop

- **V. A. Smirnov, *Evaluating Feynman Integrals* (Springer, 2004).** Standard book for analytic evaluation methods, expansion techniques, and examples.
- **V. A. Smirnov, *Analytic Tools for Feynman Integrals* (Springer, 2012).** More advanced methods, including Mellin–Barnes representations and multi-loop techniques.
- **F. V. Tkachov, “A Theorem on Analytical Calculability of Four-Loop Renormalization Group Functions,” *Physics Letters B* 100 (1981).** One of the original integration-by-parts sources.
- **K. G. Chetyrkin and F. V. Tkachov, “Integration by Parts: The Algorithm to Calculate Beta Functions in 4 Loops,” *Nuclear Physics B* 192 (1981).** Foundational IBP reference.
- **S. Laporta, “High-Precision Calculation of Multi-Loop Feynman Integrals by Difference Equations,” *International Journal of Modern Physics A* 15 (2000).** The classic Laporta-algorithm reference for systematic IBP reduction.
- **J. M. Henn, “Multiloop Integrals in Dimensional Regularization Made Simple,” *Physical Review Letters* 110 (2013).** A key source for canonical differential equations for master integrals.

### Analytic structure and special functions

- **L. D. Landau, “On Analytic Properties of Vertex Parts in Quantum Field Theory,” *Nuclear Physics* 13 (1959).** Classic source for Landau singularities.
- **A. B. Goncharov and polylogarithm literature.** Use for symbol technology, iterated integrals, and multiple polylogarithms.
- **S. Bloch, M. Kerr, P. Vanhove, and related elliptic-integral literature.** Useful for the transition from polylogarithmic to elliptic Feynman integrals.

## Gauge theory, infrared physics, and precision observables

### Gauge theory and Ward identities

- **Weinberg, Vols. I–II.** Use for QED, non-Abelian gauge theory, ghosts, BRST, renormalization of gauge theories, and the background-field method.
- **Schwartz.** Use for gauge invariance, Ward identities, QED, Yang–Mills theory, gluon scattering, jets, and SCET.
- **Srednicki.** Use for QED, Ward identities, non-Abelian gauge theory, Faddeev–Popov ghosts, BRST, and background-field gauge.
- **L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* 25 (1967).** Foundational gauge-fixing and ghost reference.
- **C. Becchi, A. Rouet, and R. Stora; I. V. Tyutin.** Foundational references for BRST symmetry.

### Infrared physics and factorization

- **F. Bloch and A. Nordsieck, “Note on the Radiation Field of the Electron,” *Physical Review* 52 (1937).** Classic soft-photon cancellation reference.
- **T. Kinoshita, “Mass Singularities of Feynman Amplitudes,” *Journal of Mathematical Physics* 3 (1962).** Original KLN theorem source.
- **T. D. Lee and M. Nauenberg, “Degenerate Systems and Mass Singularities,” *Physical Review* 133 (1964).** Original KLN theorem source.
- **D. R. Yennie, S. C. Frautschi, and H. Suura, “The Infrared Divergence Phenomena and High-Energy Processes,” *Annals of Physics* 13 (1961).** Classic exponentiation reference.
- **George Sterman, *An Introduction to Quantum Field Theory* (Cambridge, 1993).** Strong for scattering, infrared physics, factorization ideas, and QCD-oriented perturbation theory.
- **John C. Collins, *Foundations of Perturbative QCD* (Cambridge, 2011).** Reference-grade source for factorization, PDFs, infrared structure, and perturbative QCD foundations.
- **R. K. Ellis, W. J. Stirling, and B. R. Webber, *QCD and Collider Physics* (Cambridge, 1996).** Classic collider-QCD reference for partons, jets, and perturbative predictions.

### Precision predictions and event-level calculations

- **S. Catani and M. H. Seymour, dipole subtraction papers.** Standard references for infrared subtraction at NLO.
- **S. Frixione, Z. Kunszt, and A. Signer, subtraction-method literature.** Important for practical NLO calculations.
- **S. Frixione and B. R. Webber, MC@NLO; P. Nason, POWHEG.** Standard sources for matching fixed-order calculations to parton showers.
- **SCET reviews by C. W. Bauer, S. Fleming, D. Pirjol, I. W. Stewart, T. Becher, M. Neubert, and collaborators.** Use for modern factorization and resummation technology.

## Modern on-shell amplitudes

### Textbooks and lecture notes

- **Henriette Elvang and Yu-tin Huang, *Scattering Amplitudes in Gauge Theory and Gravity* (Cambridge, 2015).** The most accessible modern textbook for spinor helicity, three-point amplitudes, BCFW recursion, color ordering, generalized unitarity, supersymmetric amplitudes, and gravity.
- **Johannes M. Henn and Jan C. Plefka, *Scattering Amplitudes in Gauge Theories* (Springer, 2014).** Compact and useful for modern amplitude methods and loop technology.
- **Lance Dixon, “Calculating Scattering Amplitudes Efficiently,” TASI lectures (1996).** A classic bridge into helicity methods, color decomposition, and one-loop amplitudes.
- **Zvi Bern, Lance Dixon, and David A. Kosower reviews.** Essential for one-loop and multi-loop amplitudes, generalized unitarity, and gauge-theory amplitude organization.

### Key papers and themes

- **R. Britto, F. Cachazo, and B. Feng; R. Britto, F. Cachazo, B. Feng, and E. Witten.** Original BCFW recursion papers.
- **Z. Bern, J. J. M. Carrasco, and H. Johansson.** Original color–kinematics duality and double-copy references.
- **E. Witten, “Perturbative Gauge Theory as a String Theory in Twistor Space,” *Communications in Mathematical Physics* 252 (2004).** A turning point for modern twistor-inspired amplitude methods.
- **N. Arkani-Hamed, J. Trnka, and collaborators.** Original amplituhedron and positive-geometry references.
- **Celestial-amplitudes literature by Pasterski, Shao, Strominger, and collaborators.** Use for Mellin transforms of amplitudes and the celestial basis.

## Form factors and composite operators

- **Weinberg, Vol. II.** Use for current matrix elements, OPE, renormalized operators, and effective field theory context.
- **Zinn-Justin.** Use for composite-operator renormalization, anomalous dimensions, and short-distance expansions.
- **Collins, *Renormalization*.** Use for operator renormalization and mixing in perturbation theory.
- **Schwartz.** Use for form factors in QED, electroweak precision tests, parton physics, and effective operators.
- **QCD form-factor and Sudakov literature.** Use specialized reviews for cusp anomalous dimensions, Sudakov logarithms, and multi-loop form factors.

## Computational tools and reproducibility

Tools change faster than textbooks. Cite original papers for algorithms and current manuals for syntax. A package reference should never replace an explanation of the physics.

### Symbolic algebra and amplitudes

- **J. A. M. Vermaseren, FORM papers and manual.** Standard high-performance symbolic manipulation system for large QFT expressions.
- **R. Mertig, M. Böhm, and A. Denner, FeynCalc.** Mathematica-based tensor and Feynman-integral algebra.
- **T. Hahn, FeynArts and FormCalc.** Diagram generation and amplitude-processing tools.
- **A. Alloul, N. D. Christensen, C. Degrande, C. Duhr, and B. Fuks, FeynRules.** Lagrangian-to-Feynman-rules automation.
- **J. Alwall and collaborators, MadGraph5_aMC@NLO.** Automated matrix elements and event-generation workflows.

### Reduction, loop evaluation, and numerical integration

- **A. V. Smirnov, FIRE.** IBP reduction software.
- **R. N. Lee, LiteRed.** IBP and symmetry automation.
- **P. Maierhöfer, J. Usovitsch, and P. Uwer, Kira.** Modern IBP reduction implementation.
- **C. Studerus; A. von Manteuffel and C. Studerus, Reduze.** IBP reduction and related workflows.
- **G. Heinrich, S. Borowka, and collaborators, SecDec/pySecDec.** Sector decomposition and numerical evaluation of multi-scale integrals.
- **T. Hahn and M. Pérez-Victoria, LoopTools.** One-loop scalar and tensor integral evaluation.

### Monte Carlo and event-generator references

- **T. Sjöstrand and collaborators, PYTHIA.** Parton showers, hadronization models, and event generation.
- **M. Bahr, S. Gieseke, and collaborators, Herwig.** Event generation and shower/hadronization frameworks.
- **T. Gleisberg and collaborators, Sherpa.** Matrix-element plus parton-shower event generation.
- **Manuals and validation papers for each generator.** Use the current documentation for syntax, tunings, and physics options.

## Original-paper anchors

This list is not a complete history. It identifies papers whose names appear repeatedly in perturbative-QFT terminology.

| Topic | Anchor references |
|---|---|
| Feynman diagrams | Feynman 1949; Dyson 1949; Wick 1950 |
| LSZ reduction | Lehmann–Symanzik–Zimmermann 1955 |
| Dimensional regularization | ’t Hooft and Veltman 1972; Bollini and Giambiagi 1972 |
| Renormalization group | Gell-Mann and Low 1954; Callan 1970; Symanzik 1970 |
| Gauge fixing and ghosts | Faddeev–Popov 1967 |
| BRST symmetry | Becchi–Rouet–Stora 1975; Tyutin 1975 |
| Cutting rules | Cutkosky 1960 |
| Infrared cancellation | Bloch–Nordsieck 1937; Kinoshita 1962; Lee–Nauenberg 1964 |
| One-loop tensor reduction | Passarino–Veltman 1979 |
| IBP reduction | Tkachov 1981; Chetyrkin–Tkachov 1981; Laporta 2000 |
| Spinor-helicity and amplitudes | Parke–Taylor 1986; Dixon TASI; BCFW papers; Bern–Dixon–Kosower reviews |
| Double copy | Bern–Carrasco–Johansson 2008 and later work |

## QFT.org page citation practice

Use page references with a job in mind.

- Cite textbooks for conceptual derivations and convention checks.
- Cite original papers for named methods, theorems, and historically specific results.
- Cite reviews for active or rapidly moving areas such as multi-loop technology, SCET, amplitudes, event generators, and precision predictions.
- Cite package papers and manuals for computational workflows, but also include independent validation checks.
- Avoid pretending that a modern result is “textbook-standard” merely because it is widely used in a specialized community.

For QFT.org ordinary pages, a compact reference section is usually enough. The page should say what the references are for: first pass, deeper derivation, computational implementation, or primary source.

## Relations to other pages

- [Roadmap](/perturbative-qft/roadmap/) explains how this volume is organized and where each cluster of references is used.
- [Common Confusions](/perturbative-qft/common-confusions/) is the troubleshooting companion to this bibliography.
- [Loop Integral Technology](/perturbative-qft/loop-integral-technology/) uses the references on Feynman parameters, IBP, master integrals, differential equations, and analytic structure.
- [Infrared Physics and Factorization](/perturbative-qft/infrared-physics-factorization/) uses the Bloch–Nordsieck, KLN, factorization, jet, SCET, and resummation literature.
- [Modern On-Shell Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/) uses the spinor-helicity, BCFW, generalized-unitarity, double-copy, amplituhedron, and celestial-amplitudes references.
- [Precision Observables](/perturbative-qft/precision-observables/) uses the collider-QCD, electroweak-correction, PDF, subtraction, matching, and event-generator literature.
- [Computational Perturbative QFT](/perturbative-qft/computational-perturbative-qft/) uses the tool and reproducibility references.

## Research status

The classic textbook and original-paper references are stable. The fastest-moving parts of this bibliography are multi-loop integral technology, infrared subtraction and resummation, event-generator matching, positive geometry, celestial amplitudes, and computational tooling. Pages in those areas should use this bibliography as a starting map, not as a substitute for checking specialized reviews and current documentation.

A mature QFT.org page should make the status of its sources clear: textbook-standard, primary historical source, modern review, computational implementation, or active research literature.

## Version history

- **2026-06-14:** Initial curated bibliography for the Perturbative QFT and Scattering volume.
