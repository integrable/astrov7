---
title: "BV-BRST and Gauge Theory"
description: "Chapter overview for the cohomological formulation of gauge redundancy in the Mathematical and Rigorous QFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Faddeev–Popov; Becchi–Rouet–Stora–Tyutin; Batalin–Vilkovisky; Henneaux–Teitelboim; Barnich–Brandt–Henneaux"
topics:
  - gauge redundancy
  - BRST cohomology
  - BV formalism
  - ghosts
  - gauge fixing
canonicalTopics:
  - gauge-redundancy
  - brst-complex
  - bv-formalism
  - gauge-fixing
  - anomalies
  - perturbative-yang-mills
researchStatus:
  established:
    - "BRST and BV methods give a cohomological language for gauge redundancy, perturbative gauge fixing, observables, and anomalies."
  active:
    - "Nonperturbative gauge theory, global gauge-fixing obstructions, boundary charges, and fully rigorous interacting gauge models require additional hypotheses beyond the local BRST-BV complex."
---

BV-BRST and Gauge Theory is the chapter in the Mathematical and Rigorous QFT volume where gauge symmetry is treated as redundancy rather than as an ordinary physical symmetry. The chapter explains why gauge theories require extra mathematical structure before phrases such as “physical observable,” “path integral over gauge fields,” and “renormalized Yang–Mills theory” become precise.

The chapter begins with the classical quotient problem: a gauge field configuration is not a physical state by itself, because configurations related by gauge transformations represent the same local physics. BRST replaces the infinitesimal quotient by a differential complex. BV extends this idea by adding antifields and a master action, so that equations of motion, Noether identities, gauge algebra, observables, gauge fixing, and anomaly analysis are handled in a single framework.

Read this chapter when you want to know what ghosts are doing mathematically, why gauge fixing is not merely a trick, why physical observables are cohomology classes, and why anomalies are obstruction classes rather than just awkward loop diagrams.

$$
\text{gauge theory}
\quad\leadsto\quad
\text{quotient problem}
\quad\leadsto\quad
\text{cohomological resolution}.
$$

## Prerequisites

You should know the status conventions in [Conventions](/rigorous-qft/conventions/), the formal-series viewpoint in [Perturbative QFT as Formal Power Series](/rigorous-qft/perturbative-algebraic-qft/perturbative-qft-as-formal-power-series/), and the basic role of [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/) if you want the curved-spacetime motivation. The Algebraic QFT chapter is useful background for thinking about observables, but the first pages here are self-contained.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Gauge Symmetry as Redundancy](/rigorous-qft/bv-brst-gauge-theory/gauge-symmetry-as-redundancy-rigorous-view/) | The quotient problem behind gauge theory, the role of invariant observables, Noether identities, boundary caveats, and why naive gauge fixing is not the full story. |
| 2 | [BRST Complex](/rigorous-qft/bv-brst-gauge-theory/brst-complex/) | The first cohomological replacement for the gauge quotient: fields, ghosts, ghost number, the BRST differential, gauge-fixing doublets, and physical cohomology. |
| 3 | [BV Formalism](/rigorous-qft/bv-brst-gauge-theory/bv-formalism/) | The field–antifield extension, the antibracket, the BV differential, antifields as sources and resolution variables, and the Yang–Mills master action. |
| 4 | [Classical Master Equation](/rigorous-qft/bv-brst-gauge-theory/classical-master-equation/) | The compact equation $(S_{\mathrm{BV}},S_{\mathrm{BV}})=0$ and how it encodes gauge invariance, Noether identities, closure, Jacobi identities, and consistent deformations. |
| 5 | [Quantum Master Equation](/rigorous-qft/bv-brst-gauge-theory/quantum-master-equation/) | The finite-dimensional BV equation $\Delta e^{iS/\hbar}=0$, its order-by-order obstruction theory, why the BV Laplacian is singular in local QFT, and how anomaly classes appear. |
| 6 | [Ghosts, Antifields, and Cohomology](/rigorous-qft/bv-brst-gauge-theory/ghosts-antifields-and-cohomology/) | The ghost-number, pure-ghost, and antifield-number bookkeeping behind BRST-BV cohomology, including the Koszul–Tate resolution and the local groups that classify counterterms and anomalies. |
| 7 | [Observables as Cohomology](/rigorous-qft/bv-brst-gauge-theory/observables-as-cohomology/) | The reason physical observables are $s$-closed classes modulo $s$-exact and on-shell-trivial terms, and why local densities use $H^{g,d}(s\mid d)$. |
| 8 | [Gauge Fixing as a Lagrangian Submanifold](/rigorous-qft/bv-brst-gauge-theory/gauge-fixing-as-lagrangian-submanifold/) | The BV geometry of gauge fixing, the role of a gauge-fixing fermion, the recovery of Faddeev–Popov gauges, and the distinction between perturbative slices and global quotient problems. |
| 9 | [Anomalies as Obstructions](/rigorous-qft/bv-brst-gauge-theory/anomalies-as-obstructions/) | The cohomological meaning of gauge anomalies, Wess–Zumino consistency, removable versus nonremovable breakings, and the relation to local BRST cohomology. |
| 10 | [Perturbative Yang–Mills: Rigorous View](/rigorous-qft/bv-brst-gauge-theory/perturbative-yang-mills-rigorous-view/) | The precise perturbative status of Yang–Mills theory as a renormalized BRST-BV formal power series theory, and what this does not prove nonperturbatively. |

After this path, you should be able to explain why ghosts are coordinates along gauge directions, why antifields are not antiparticles, why the master equation is the natural consistency condition for gauge theory, why observables are cohomology classes, why gauge fixing should not change physical cohomology classes, how anomaly classes obstruct quantum gauge symmetry, and what is rigorous about perturbative Yang–Mills theory.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| Gauge orbit | The set of field configurations related by gauge transformations. | Gauge fixing, quotient stacks, physical observables. |
| Gauge-invariant observable | A function or functional constant along gauge orbits. | BRST cohomology and observables as cohomology. |
| Noether identity | A relation among Euler–Lagrange equations caused by gauge redundancy. | BV antifields and Koszul–Tate resolution. |
| Ghost $c$ | Odd variable replacing an infinitesimal gauge parameter. | BRST differential and Faddeev–Popov determinant. |
| BRST differential $s$ | Odd derivation of ghost number $+1$ satisfying $s^2=0$. | Observables, gauge fixing, anomalies. |
| $H^0(s)$ | Degree-zero BRST cohomology, the first approximation to physical observables. | Observables as cohomology and local BRST cohomology. |
| Local BRST cohomology $H^{g,d}(s\mid d)$ | Cohomology of local densities modulo total derivatives. | Counterterms, deformations, anomalies. |
| Antifield $\Phi_A^*$ | Shifted cotangent variable paired with a field or ghost. | BV antibracket, master action, gauge fixing. |
| BV antibracket $(F,G)$ | Odd Poisson bracket pairing fields and antifields. | Classical and quantum master equations. |
| BV action $S_{\mathrm{BV}}$ | Original action plus gauge transformations, algebra, and higher identities. | Classical master equation and deformation theory. |
| Classical master equation | $(S_{\mathrm{BV}},S_{\mathrm{BV}})=0$. | Quantum master equation, anomalies, consistent interactions. |
| BV Laplacian $\Delta$ | Finite-dimensional divergence operator whose failure to be a derivation is the antibracket. | Quantum master equation and measure compatibility. |
| Quantum master equation | $\Delta e^{iS/\hbar}=0$, or equivalently $\frac12(S,S)-i\hbar\Delta S=0$ in finite dimension. | Gauge-fixing independence and anomaly obstruction theory. |
| Koszul–Tate differential $\delta$ | The homological part resolving equations of motion and Noether identities. | Local BRST cohomology and conserved currents. |
| BRST doublet | A pair such as $(\bar c,b)$ with $s\bar c=b$ and $sb=0$. | Gauge fixing without changing physical cohomology. |
| Gauge-fixing fermion $\Psi$ | Odd functional of ghost number $-1$ whose graph sets antifields. | BV gauge fixing and Faddeev–Popov gauges. |
| Lagrangian submanifold $\mathcal L_\Psi$ | The BV geometric replacement for a gauge slice. | Gauge-fixed actions and gauge-independence arguments. |
| Anomaly class | Failure of quantum BRST/BV invariance represented cohomologically. | Quantum master equation and anomalies as obstructions. |
| Wess–Zumino consistency | Closure condition $s\mathcal A=0$ for an anomaly candidate. | Local BRST cohomology and anomaly cancellation. |
| Trivial anomaly | An exact breaking $\mathcal A=sB$ removable by a local counterterm. | Renormalization ambiguities and finite counterterms. |
| Perturbative Yang–Mills algebra | Formal power series algebra of interacting fields obtained from a gauge-fixed auxiliary theory. | pAQFT, Epstein–Glaser renormalization, rigorous perturbative gauge theory. |

## Common confusions

**Gauge symmetry is just a physical symmetry.** An ordinary global symmetry acts on physical states and organizes sectors. A pure gauge transformation is redundancy: it changes coordinates on the same physical configuration. Boundary and asymptotic transformations are the main caveat.

**Ghosts are unphysical particles added by hand.** In covariant perturbation theory ghosts are fields, but their mathematical role is to encode the gauge quotient and its Jacobian or cohomological resolution. They are not extra physical polarizations.

**Antifields are antiparticles.** Antifields are shifted dual variables paired with fields and ghosts by the BV antibracket. They are not particle species.

**Antighosts are antifields.** The antighost $\bar c$ is a nonminimal gauge-fixing variable. The ghost antifield $c^*$ is a BV resolution variable. Their names are historically similar but mathematically different.

**Gauge fixing chooses physics.** Gauge fixing chooses a representative or a Lagrangian submanifold for calculation. Physical observables should be represented by cohomology classes and should not depend on allowed changes of gauge fixing.

**Gauge fixing solves the quotient globally.** A gauge condition can work locally in field space or perturbatively around a background. Globally the quotient can be singular and Gribov-type obstructions can appear.

**BRST invariance automatically proves nonperturbative existence.** BRST and BV are powerful local and perturbative organizing principles. They do not by themselves construct a continuum measure for interacting Yang–Mills theory.

**The finite-dimensional quantum master equation can be copied into QFT literally.** The naive BV Laplacian is singular on local functionals. A field-theoretic quantum master equation requires regularization, renormalized time-ordered products, effective actions, or another precise replacement.

**Every anomaly is a gauge anomaly.** A global or 't Hooft anomaly can be physical data. A gauge anomaly for a redundancy is an obstruction. The same-looking local formula can have different status depending on what symmetry is being varied.

**Perturbative Yang–Mills solves nonperturbative Yang–Mills.** A formal power series construction is a rigorous perturbative result. It is not a construction of the continuum measure, mass gap, confinement, or asymptotic completeness.

## Boundaries

This chapter treats gauge symmetry as mathematical structure inside rigorous QFT. It explains quotient problems, BRST complexes, BV fields and antifields, master equations, gauge fixing, observables, anomalies, and perturbative control of Yang–Mills-type gauge theories.

This chapter does not try to be the canonical physical introduction to Yang–Mills theory, electroweak theory, or the Standard Model. Those topics belong in the Gauge Theories and the Standard Model volume. It also does not replace the Symmetry, Anomalies, and Topology volume, where anomalies and generalized symmetries are treated as physical organizing principles.

The main boundary is status. BRST/BV gives precise algebraic control of local gauge redundancy and perturbative gauge theory. It is not a complete nonperturbative construction of four-dimensional non-Abelian gauge theory.

## Where to go next

After this chapter, the natural continuation is the Microlocal Analysis in QFT chapter, beginning with products of distributions and the microlocal spectrum condition. For perturbative renormalization, return to [Renormalization Ambiguities](/rigorous-qft/perturbative-algebraic-qft/renormalization-ambiguities/) and [Interacting Fields as Formal Series](/rigorous-qft/perturbative-algebraic-qft/interacting-fields-as-formal-series/). For local covariance and curved spacetime, use [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/) as the bridge. For nonperturbative gauge theory, continue later to lattice-to-continuum constructions and open problems.

## References

### Standard first pass

- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* **25** (1967), 29–30. [doi:10.1016/0370-2693(67)90067-6](https://doi.org/10.1016/0370-2693(67)90067-6).
- C. Becchi, A. Rouet, and R. Stora, “Renormalization of Gauge Theories,” *Annals of Physics* **98** (1976), 287–321. [doi:10.1016/0003-4916(76)90156-1](https://doi.org/10.1016/0003-4916(76)90156-1).
- I. V. Tyutin, “Gauge Invariance in Field Theory and Statistical Physics in Operator Formalism,” Lebedev preprint (1975). [arXiv:0812.0580](https://arxiv.org/abs/0812.0580).
- I. A. Batalin and G. A. Vilkovisky, “Gauge Algebra and Quantization,” *Physics Letters B* **102** (1981), 27–31. [doi:10.1016/0370-2693(81)90205-7](https://doi.org/10.1016/0370-2693(81)90205-7).
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*, Princeton University Press, 1992. [doi:10.1515/9780691213866](https://doi.org/10.1515/9780691213866).

### Deeper references

- I. A. Batalin and G. A. Vilkovisky, “Quantization of Gauge Theories with Linearly Dependent Generators,” *Physical Review D* **28** (1983), 2567–2582. [doi:10.1103/PhysRevD.28.2567](https://doi.org/10.1103/PhysRevD.28.2567).
- A. Schwarz, “Geometry of Batalin–Vilkovisky Quantization,” *Communications in Mathematical Physics* **155** (1993), 249–260. [arXiv:hep-th/9205088](https://arxiv.org/abs/hep-th/9205088), [doi:10.1007/BF02097392](https://doi.org/10.1007/BF02097392).
- J. Gomis, J. París, and S. Samuel, “Antibracket, Antifields and Gauge-Theory Quantization,” *Physics Reports* **259** (1995), 1–145. [arXiv:hep-th/9412228](https://arxiv.org/abs/hep-th/9412228), [doi:10.1016/0370-1573(94)00112-G](https://doi.org/10.1016/0370-1573(94)00112-G).
- G. Barnich, F. Brandt, and M. Henneaux, “Local BRST Cohomology in Gauge Theories,” *Physics Reports* **338** (2000), 439–569. [arXiv:hep-th/0002245](https://arxiv.org/abs/hep-th/0002245), [doi:10.1016/S0370-1573(00)00049-1](https://doi.org/10.1016/S0370-1573(00)00049-1).
- O. Piguet and S. P. Sorella, *Algebraic Renormalization: Perturbative Renormalization, Symmetries and Anomalies*, Springer, 1995. [doi:10.1007/978-3-540-49192-7](https://doi.org/10.1007/978-3-540-49192-7).
- J. Wess and B. Zumino, “Consequences of Anomalous Ward Identities,” *Physics Letters B* **37** (1971), 95–97. [doi:10.1016/0370-2693(71)90582-X](https://doi.org/10.1016/0370-2693(71)90582-X).
- S. Hollands, “Renormalized Quantum Yang–Mills Fields in Curved Spacetime,” *Reviews in Mathematical Physics* **20** (2008), 1033–1172. [arXiv:0705.3340](https://arxiv.org/abs/0705.3340), [doi:10.1142/S0129055X08003420](https://doi.org/10.1142/S0129055X08003420).

## Version history

- **2026-07-01:** Updated overview after adding anomalies as obstructions and perturbative Yang–Mills from the rigorous BV-BRST viewpoint.
- **2026-07-01:** Updated overview after adding observables as cohomology and gauge fixing as a Lagrangian submanifold.
- **2026-07-01:** Updated overview after adding the quantum master equation and ghosts–antifields–cohomology pages.
- **2026-07-01:** Updated overview after adding the BV formalism and classical master equation pages.
- **2026-07-01:** Initial polished draft of the chapter overview with the first two BV-BRST pages.
