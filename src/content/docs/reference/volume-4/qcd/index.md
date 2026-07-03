---
title: "Quantum Chromodynamics"
description: "Chapter overview for QCD as the SU(3)c gauge theory of quarks and gluons, including its Lagrangian, color, running coupling, chiral symmetry, confinement, and theta angle."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki §§81–84 and §§93–94; Schwartz Chs. 25–32; Weinberg Vol. II Chs. 15–19; Coleman, Aspects of Symmetry, Chs. 1, 5–8."
topics:
  - quantum chromodynamics
  - QCD Lagrangian
  - color SU(3)
  - quarks and gluons
  - asymptotic freedom
  - chiral symmetry
  - confinement
  - theta angle
canonicalTopics:
  - quantum-chromodynamics
  - qcd-lagrangian
  - color-su3
  - strong-coupling
  - chiral-symmetry-breaking
  - confinement-in-qcd
  - strong-cp-problem
researchStatus:
  established:
    - "QCD is the SU(3)c non-Abelian gauge theory of quarks and gluons, and its ultraviolet asymptotic freedom is a textbook perturbative result."
  active:
    - "The detailed nonperturbative mechanism of confinement, real-time hadronization, finite-density QCD, and the origin of the small effective theta angle remain active research areas."
---

Quantum Chromodynamics is the chapter where the gauge-theory machinery becomes the strong interaction. The local structure is compact to write: an $SU(3)_c$ gauge field, quark fields in the fundamental representation, and the gauge-invariant kinetic and mass terms allowed by locality and Lorentz invariance. The physics is not compact at all.

QCD is asymptotically free at short distances, so high-energy quark and gluon processes can be computed perturbatively. At long distances the same theory becomes strongly coupled, confines colored probes, generates hadronic scales by dimensional transmutation, and reorganizes light-quark dynamics through chiral symmetry breaking.

This chapter is therefore the first place in the volume where the same Lagrangian must be read in two voices: as a perturbative quantum field theory of quarks and gluons in the ultraviolet, and as the underlying microscopic theory whose infrared observables are color-singlet hadrons.

$$
\text{QCD}
=
SU(3)_c\text{ Yang–Mills theory}
+
\text{dynamical quarks}
+
\text{strong infrared dynamics}.
$$

## Prerequisites

You should know the volume [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/), especially the sign convention

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
F_{\mu\nu}^a=\partial_\mu A_\nu^a-\partial_\nu A_\mu^a-gf^{abc}A_\mu^bA_\nu^c.
$$

You should also have read the Yang–Mills chapter through [Color and Representations](/gauge-theories-standard-model/yang-mills/color-and-representations/) and [Global Form and Center](/gauge-theories-standard-model/yang-mills/global-form-and-center/). Those pages supply the local $SU(N)$ notation, the adjoint gluon representation, and the center-symmetry caveats needed below.

For the quantum dynamics, you should know [Gauge Fixing and Faddeev–Popov](/gauge-theories-standard-model/gauge-quantization/gauge-fixing-and-faddeev-popov/), [Ghosts and Gauge-Fixed Action](/gauge-theories-standard-model/gauge-quantization/ghosts-and-gauge-fixed-action/), [Beta Function of Yang–Mills](/gauge-theories-standard-model/gauge-renormalization/beta-function-of-yang-mills/), [Asymptotic Freedom](/gauge-theories-standard-model/gauge-renormalization/asymptotic-freedom/), and [Dimensional Transmutation in Gauge Theory](/gauge-theories-standard-model/gauge-renormalization/dimensional-transmutation-in-gauge-theory/).

The Wilson-loop chapter is useful because it explains the line-operator diagnostics that become subtle once dynamical quarks can screen external color charges.

## Reading path

Read these pages in order on a first pass. The first-pass QCD chapter arc is now available.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [QCD Lagrangian](/gauge-theories-standard-model/qcd/qcd-lagrangian/) | The gauge-invariant QCD action, quark representations, gluon field strength, gauge fixing, ghosts, theta term, and main sign conventions. |
| 2 | [Color SU(3)](/gauge-theories-standard-model/qcd/color-su3/) | The concrete $SU(3)_c$ data: triplets, antitriplets, octets, color indices, Casimirs, Dynkin index, and color contractions. |
| 3 | [Quarks and Gluons](/gauge-theories-standard-model/qcd/quarks-and-gluons/) | The perturbative degrees of freedom, physical color-singlet observables, jets, partons, and why quarks and gluons are not asymptotic hadrons. |
| 4 | [QCD Beta Function](/gauge-theories-standard-model/qcd/qcd-beta-function/) | The one-loop and two-loop running of $g_s$, the role of $n_f$, active flavors, and the sign difference from QED. |
| 5 | [Running Alpha s](/gauge-theories-standard-model/qcd/running-alpha-s/) | The practical running coupling $\alpha_s(\mu)$, heavy-quark thresholds, $\Lambda_{\rm QCD}$, and scheme dependence. |
| 6 | [Chiral Symmetry in QCD](/gauge-theories-standard-model/qcd/chiral-symmetry-in-qcd/) | The approximate $SU(n_f)_L\times SU(n_f)_R$ flavor symmetry of light quarks and its vector, axial, singlet, and anomalous pieces. |
| 7 | [Spontaneous Chiral Symmetry Breaking](/gauge-theories-standard-model/qcd/spontaneous-chiral-symmetry-breaking/) | The quark condensate, pions as pseudo-Goldstone bosons, and why light hadrons are not organized by unbroken chiral symmetry. |
| 8 | [Confinement in QCD](/gauge-theories-standard-model/qcd/confinement-in-qcd/) | Confinement with dynamical quarks, string breaking, color-singlet spectrum, and the difference between pure Yang–Mills confinement and real-world QCD. |
| 9 | [Theta Angle and Strong CP Problem](/gauge-theories-standard-model/qcd/theta-angle-and-strong-cp-problem/) | The topological term, axial rotations, $\bar\theta$, instanton sectors, neutron electric dipole constraints, and the strong CP puzzle. |

The chapter starts with the Lagrangian because everything else is a different question about the same object: which fields it uses, which symmetries it has, how its coupling runs, what it does in the infrared, and which parameters remain mysterious.

## Landmarks

| Landmark | Meaning | Why it matters later |
|---|---|---|
| $SU(3)_c$ | The color gauge group of QCD. | Fixes eight gluons, triplet quarks, adjoint ghosts, and the group factors in the beta function. |
| $G_\mu^A$ | The gluon gauge field, with $A=1,\ldots,8$. | The connection for local color-frame changes. |
| $q_f$ | A Dirac quark field of flavor $f$ in the fundamental representation $\mathbf 3$ of color. | Quarks carry color and flavor; flavor is not the same as color. |
| $D_\mu q_f=(\partial_\mu+ig_sG_\mu^AT^A)q_f$ | The QCD covariant derivative in the fundamental representation. | Produces the quark–gluon vertex and fixes the sign convention. |
| $G_{\mu\nu}^A$ | The non-Abelian gluon field strength. | Contains both gluon propagation and gluon self-interactions. |
| $\alpha_s=g_s^2/(4\pi)$ | The strong coupling. | The practical coupling used in perturbative QCD and running-coupling plots. |
| $b_0=11-\frac23n_f$ | The one-loop QCD beta-function coefficient for $n_f$ Dirac quarks in the fundamental representation. | Positive $b_0$ gives asymptotic freedom in the usual convention $\mu\,d g_s/d\mu=-b_0g_s^3/(16\pi^2)+\cdots$. |
| $\Lambda_{\rm QCD}$ | The dynamically generated strong scale. | Converts dimensionless classical input into hadron masses, string tensions, and condensate scales. |
| $SU(n_f)_L\times SU(n_f)_R$ | Approximate chiral flavor symmetry for $n_f$ light quarks. | Explains pions, current algebra, chiral perturbation theory, and many low-energy hadron relations. |
| $\langle\bar q q\rangle$ | The quark condensate. | Standard order parameter for spontaneous chiral symmetry breaking in the massless idealization. |
| Wilson loops | Gauge-invariant probes of external color sources. | Area-law intuition survives, but dynamical quarks allow screening and string breaking. |
| $\theta G\widetilde G$ | The topological theta term. | Leads to the strong CP problem and instanton/topological-susceptibility questions. |

The landmarks divide cleanly into three layers: local QCD data, perturbative running, and infrared nonperturbative physics.

## Common confusions

**QCD is not just “Yang–Mills with $N=3$.”** Pure $SU(3)$ Yang–Mills theory has only gluons. QCD also has dynamical quarks. That changes screening, global symmetries, the spectrum, the meaning of Wilson-loop diagnostics, and the infrared physics.

**Color is not flavor.** Color is gauged and has no gauge-invariant local charge label for isolated asymptotic particles. Flavor is an approximate global structure acting on quark species. A red up quark and a blue up quark differ by color; an up quark and a down quark differ by flavor.

**Quarks and gluons are not gauge-invariant local observables.** They are the efficient variables in the Lagrangian and in high-energy perturbation theory. Physical asymptotic states in zero-temperature QCD are color singlets such as mesons, baryons, glueball-like states, and multihadron states.

**Asymptotic freedom is not the same as confinement.** The negative beta function at small coupling is perturbative and explains why QCD becomes weakly coupled in the ultraviolet. Confinement is an infrared, nonperturbative statement. The former strongly suggests the latter in real QCD, but it is not a proof.

**The Wilson-loop area law must be qualified with dynamical quarks.** In pure Yang–Mills theory, an area law for fundamental Wilson loops sharply diagnoses confinement. In QCD with light fundamental quarks, the external flux tube can break by pair creation, so a sufficiently large fundamental Wilson loop need not obey a strict asymptotic area law.

**The theta term is not visible in ordinary perturbation theory around the trivial vacuum.** Locally $G\widetilde G$ is a total derivative, but globally it weights topological sectors. Its physical effect is tied to instantons, axial rotations, quark masses, and CP violation.

**QCD has many useful approximations, not one magic approximation.** High-energy scattering uses perturbation theory and factorization. Low-energy pions use chiral effective theory. Heavy quarks use heavy-quark expansions. Lattice QCD uses Euclidean nonperturbative simulation. These are complementary windows on the same theory.

## Boundaries

This chapter does:

- formulate QCD as an $SU(3)_c$ gauge theory of quarks and gluons;
- fix the Lagrangian, covariant derivative, field strength, gauge-fixing, ghost, and theta-term conventions;
- explain the representation data needed for color calculations;
- connect Yang–Mills asymptotic freedom to the running strong coupling;
- introduce chiral symmetry and spontaneous chiral symmetry breaking;
- explain how confinement in QCD differs from confinement diagnostics in pure Yang–Mills;
- prepare the electroweak and Standard Model chapters by separating color, flavor, chirality, and gauge representation.

This chapter does not try to:

- become a full course in perturbative QCD, jets, factorization, or collider phenomenology;
- replace the Nonperturbative QFT volume’s treatment of confinement, mass gap, lattice definitions, and topological sectors;
- provide numerical hadron masses, parton distribution functions, or current world-average data tables;
- derive chiral perturbation theory in full;
- solve finite-density QCD, the sign problem, or real-time hadronization;
- prove confinement or the Yang–Mills mass gap.

The chapter’s job is to make QCD legible as a quantum field theory: what the microscopic theory is, which symmetries it has, what perturbation theory controls, and where nonperturbative physics begins.

## Where to go next

After this chapter, continue to [Electroweak Theory](/gauge-theories-standard-model/electroweak/). The electroweak interaction is also a gauge theory, but its chiral matter content, Higgs mechanism, symmetry breaking pattern, and anomaly constraints are different from QCD in exactly the ways that make the Standard Model interesting.

If your goal is strong-interaction calculations, pair this chapter with the Perturbative QFT and Scattering volume on cross sections, loop integrals, infrared physics, factorization, and amplitudes. If your goal is hadron physics, pair it with the Nonperturbative QFT and Matter/Statistical Physics volumes, especially lattice gauge theory, chiral effective theory, finite temperature, and transport.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§81–83 and §§93–94, for scattering in QCD, Wilson loops, chiral symmetry breaking, instantons, and theta vacua.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 25–26 and 32, for Yang–Mills theory, quantum Yang–Mills, running coupling, and QCD/parton-model physics.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Chs. 15–19, for non-Abelian gauge theory, renormalization, RG methods, and strong-interaction applications.

### Deeper references

- Coleman, *Aspects of Symmetry*, especially the lectures on unitary symmetry, gauge fields, instantons, and large-$N$ methods.
- Polyakov, *Gauge Fields and Strings*, for asymptotic freedom, strong-coupling gauge expansions, confinement criteria, loop dynamics, and large-$N$ thinking.
- Peskin and Schroeder, *An Introduction to Quantum Field Theory*, for standard QCD Feynman rules, beta functions, and perturbative applications.
- Manohar and Wise, *Heavy Quark Physics*, and Georgi, *Weak Interactions and Modern Particle Theory*, for useful bridges from QCD to effective descriptions.

## Version history

- **2026-06-18:** Linked the completed first-pass QCD arc forward to the Electroweak Theory chapter.
- **2026-06-18:** Added Confinement in QCD and Theta Angle and Strong CP Problem, completing the first-pass QCD chapter arc.
- **2026-06-18:** Added Chiral Symmetry in QCD and Spontaneous Chiral Symmetry Breaking to the reading path.
- **2026-06-18:** Added QCD Beta Function and Running Alpha s to the reading path.
- **2026-06-18:** Added links to Color SU(3) and Quarks and Gluons in the reading path.
- **2026-06-18:** Initial chapter overview. Added the first-pass QCD reading path and linked the QCD Lagrangian page.
