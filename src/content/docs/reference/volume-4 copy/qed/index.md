---
title: "Abelian Gauge Theory and QED"
description: "Chapter overview for Maxwell theory, scalar and spinor QED, gauge fixing, photon propagators, Ward identities, vacuum polarization, and the running electric charge."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki §§54–68; Schwartz Chs. 8–21; Coleman lectures on electromagnetic interactions, Faddeev–Popov, Ward identities, and QED renormalization; Zee Parts II–III and VII."
topics:
  - quantum electrodynamics
  - Abelian gauge theory
  - Maxwell theory
  - Ward identities
  - vacuum polarization
canonicalTopics:
  - qed
  - abelian-gauge-theory
  - ward-takahashi-identity
  - photon-propagator
researchStatus:
  established:
    - "Perturbative QED is the textbook prototype of a renormalized gauge theory and one of the most precisely tested frameworks in physics."
  active:
    - "Infrared-safe charged-sector observables, asymptotic symmetries, dressed states, and precision multi-loop calculations remain active subjects connected to later chapters."
---

Abelian Gauge Theory and QED is the chapter where the abstract gauge principle becomes the quantum field theory of photons and charged matter. It starts from Maxwell theory as a $U(1)$ gauge theory, then adds charged scalars and charged spinors, fixes gauges, derives photon propagators and vertices, and explains the Ward identities that protect charge conservation and gauge independence.

The chapter is deliberately more than “Feynman rules for electrons and photons.” QED is the cleanest laboratory for the big ideas of gauge theory: redundant potentials, gauge-invariant field strengths, charged matter, Gauss law, gauge fixing, infrared subtleties, vacuum polarization, and running couplings.

Read this chapter when you want the simplest fully worked gauge theory before non-Abelian self-interactions, confinement, electroweak symmetry breaking, and Standard Model representation bookkeeping arrive.

$$
\text{QED}
=
\text{Maxwell gauge field}
+
\text{charged matter}
+
\text{quantization respecting Ward identities}.
$$

## Prerequisites

You should know [Conventions and Normalizations](/gauge-theories-standard-model/orientation/conventions-and-normalizations/), especially the Abelian specialization of the volume convention. For a field of physical charge $q=eQ$,

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\psi\mapsto e^{-iq\lambda}\psi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\lambda.
$$

Here $e>0$ is the magnitude of the proton charge and $Q$ is the dimensionless charge. The electron has $Q=-1$, so $q=-e$.

You should also know the Gauge Principle chapter through [Gauge-Invariant Observables](/gauge-theories-standard-model/gauge-principle/gauge-invariant-observables/). The most important takeaways are: $A_\mu$ is gauge-dependent, $F_{\mu\nu}$ is gauge invariant in Abelian theory, charged fields are not themselves gauge-invariant observables, and gauge fixing is a calculational choice rather than physics.

For calculations, you should be comfortable with free scalar and Dirac fields, path integrals, Gaussian integration, Feynman propagators, LSZ reduction at a basic level, and one-loop regularization. The chapter recalls what it needs, but it does not reteach perturbation theory from scratch.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Maxwell Theory as Gauge Theory](/gauge-theories-standard-model/qed/maxwell-theory-as-gauge-theory/) | The classical $U(1)$ gauge field, $F_{\mu\nu}$, equations of motion, gauge redundancy, and physical polarizations. |
| 2 | [Scalar QED](/gauge-theories-standard-model/qed/scalar-qed/) | The simplest charged matter model, covariant derivatives for complex scalars, seagull interactions, and current coupling. |
| 3 | [Spinor QED](/gauge-theories-standard-model/qed/spinor-qed/) | The Dirac field coupled to electromagnetism, electron charge conventions, current normalization, and the photon–fermion vertex. |
| 4 | [QED Lagrangian](/gauge-theories-standard-model/qed/qed-lagrangian/) | The unified Abelian gauge-theory Lagrangian, equations of motion, gauge fixing, current structure, and counterterm preview. |
| 5 | [Gauge Fixing in QED](/gauge-theories-standard-model/qed/gauge-fixing-in-qed/) | Why the photon kinetic operator cannot be inverted before fixing gauge, and how covariant gauges repair it. |
| 6 | [Photon Propagator](/gauge-theories-standard-model/qed/photon-propagator/) | The covariant-gauge photon propagator, gauge parameter dependence, and conserved-current simplifications. |
| 7 | [QED Vertices](/gauge-theories-standard-model/qed/qed-vertices/) | The scalar and spinor QED interaction vertices in the volume conventions, including the scalar seagull vertex. |
| 8 | [Ward–Takahashi Identity](/gauge-theories-standard-model/qed/ward-takahashi-identity/) | The identity that relates current conservation, gauge invariance, charge renormalization, and amplitude transversality. |
| 9 | [Vacuum Polarization](/gauge-theories-standard-model/qed/vacuum-polarization/) | The one-loop photon self-energy, transversality, screening, and the physical origin of charge running. |
| 10 | [Running Electric Charge](/gauge-theories-standard-model/qed/running-electric-charge/) | The QED beta function, effective charge, Landau-pole warning, and comparison with non-Abelian asymptotic freedom. |

After this path, you should be able to write the QED action, derive its basic Feynman rules, understand why gauge-dependent pieces cancel from physical amplitudes, and recognize which one-loop structures lead to the running of the electric charge.

## Landmarks

| Landmark | Meaning | Why it matters later |
|---|---|---|
| $A_\mu\mapsto A_\mu+\partial_\mu\lambda$ | The electromagnetic potential is a redundant gauge variable, with the coupling absorbed into $\lambda$. | Gauge fixing, photon propagator, Gauss law, and dressed charges. |
| $F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu$ | Abelian field strength is gauge invariant. | Maxwell theory, electromagnetic observables, and local QED operators. |
| $D_\mu=\partial_\mu+iqA_\mu$ | Charged matter couples through the covariant derivative, where $q=eQ$ is the physical charge in the chosen normalization. | Scalar QED, spinor QED, and the Standard Model charge convention. |
| $\mathcal L_{\mathrm{QED}}=-\frac14F_{\mu\nu}F^{\mu\nu}+\bar\psi(i\gamma^\mu D_\mu-m)\psi$ | Minimal spinor QED in mostly-minus conventions. | Electron–photon Feynman rules and Ward identities. |
| $-\frac{1}{2\xi}(\partial_\mu A^\mu)^2$ | Covariant gauge-fixing term. | Makes the photon kinetic operator invertible while introducing gauge-parameter dependence. |
| $D_{\mu\nu}(k)=\frac{-i}{k^2+i\epsilon}\left[\eta_{\mu\nu}-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}\right]$ | Covariant-gauge photon propagator. | Longitudinal terms cancel against conserved currents or Ward identities. |
| $-iq\gamma^\mu$ | Spinor-QED photon–fermion vertex for a field of charge $q$. | Electron scattering, loop diagrams, and the fermion Ward–Takahashi identity. |
| $-iq(p+p')^\mu$ and $2iq^2\eta^{\mu\nu}$ | Scalar-QED one-photon and seagull vertices in charge-flow notation. | Scalar Compton scattering and scalar-QED Ward identities. |
| $k_\mu\mathcal M^\mu=0$ | Prototype amplitude-level Ward identity for an external photon of momentum $k$. | Gauge independence and replacement of polarization vectors by momenta. |
| $\Pi_{\mu\nu}(q)=(q_\mu q_\nu-q^2\eta_{\mu\nu})\Pi(q^2)$ | Transverse vacuum polarization. | Charge renormalization, running coupling, and the contrast with Yang–Mills theory. |
| $\beta(e)=e^3/(12\pi^2)$ for one unit-charged Dirac fermion | One-loop spinor-QED beta function. | QED screens charge; non-Abelian gauge theory can antiscreen. |

## Common confusions

**QED is not just Maxwell theory with particles added by hand.** Once charged quantum fields are dynamical, gauge invariance fixes the form of their leading coupling and constrains the quantum corrections. The photon, electron, current, and charge renormalization are tied together by Ward identities.

**The photon propagator is not an observable.** It depends on the gauge-fixing parameter $\xi$. This dependence is useful and harmless as long as physical amplitudes and gauge-invariant correlation functions do not depend on it.

**The electron field is not itself gauge invariant.** The local Dirac field $\psi(x)$ transforms by a phase. Physical charged states require dressing, asymptotic structure, or an inclusive scattering framework. In perturbative QED we often compute with $\psi$ because it is the efficient gauge-fixed variable, not because it is a local gauge-invariant observable.

**Gauge invariance is not the same thing as current conservation, but they are linked.** In QED, local gauge redundancy forces the coupling to a conserved current. Quantum mechanically, the Ward–Takahashi identity is the precise statement tying current conservation, gauge invariance, and renormalization together.

**Scalar QED has a two-photon seagull vertex.** The term $(D_\mu\phi)^\dagger D^\mu\phi$ contains both a one-photon current interaction and a two-photon contact interaction. Forgetting the seagull vertex breaks Ward identities in scalar-QED calculations.

**QED is Abelian, but not trivial.** The photon has no classical self-interaction in the minimal Maxwell action, but loops of charged matter polarize the vacuum, generate running couplings, and produce nonlinear effective photon interactions at low energy.

**Infrared physics is not optional.** Massless photons make exclusive charged-particle S-matrix elements infrared delicate. Physically meaningful predictions often require inclusive observables, dressed states, or careful soft-photon treatment. This chapter flags the issue; the perturbative and scattering volumes develop it further.

## Boundaries

This chapter does:

- formulate Maxwell theory as a $U(1)$ gauge theory;
- couple complex scalars and Dirac fermions to the photon using the volume conventions;
- derive the QED Lagrangian, equations of motion, currents, and basic vertices;
- explain gauge fixing and the covariant-gauge photon propagator;
- introduce Ward and Ward–Takahashi identities;
- compute or organize the first quantum correction to the photon propagator;
- explain charge renormalization and the qualitative meaning of the running electric charge.

This chapter does not try to do:

- provide a complete course in scattering theory or cross-section calculations;
- fully analyze infrared divergences, coherent states, or asymptotic symmetries;
- derive high-precision QED observables such as the anomalous magnetic moment in detail;
- replace the later Gauge Quantization chapter on Faddeev–Popov and BRST;
- treat non-Abelian gauge boson self-interactions;
- develop QCD, electroweak theory, or the full Standard Model.

The boundary is intentional. QED is used here as the first complete gauge-theory laboratory. Precision QED calculations, infrared factorization, and experimental comparisons are important, but they belong in more specialized calculation and perturbative-scattering pages.

## Where to go next

On a linear path, begin with Maxwell Theory as Gauge Theory and move through the reading path above. After the QED chapter, continue to [Non-Abelian Gauge Theory and Yang–Mills](/gauge-theories-standard-model/yang-mills/), where the same gauge principle becomes genuinely nonlinear: field strengths carry charge, gauge bosons self-interact, ghosts become unavoidable in covariant quantization, and the beta function can change sign.

If you are mainly interested in calculations, pair this chapter with the Perturbative QFT and Scattering volume pages on Feynman rules, LSZ, loop integrals, renormalized perturbation theory, and infrared divergences.

If you are mainly interested in conceptual gauge theory, go next to Gauge Quantization for Faddeev–Popov and BRST, then Wilson Loops, Phases, and Confinement for the nonperturbative role of line operators.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §§54–68, for Maxwell theory, photon quantization, spinor electrodynamics, scalar electrodynamics, loop corrections, QED beta functions, and Ward identities.
- Schwartz, *Quantum Field Theory and the Standard Model*, Chs. 8–21, for gauge invariance, scalar QED, spinor QED, path-integral Ward identities, vacuum polarization, renormalized perturbation theory, and infrared divergences.
- Zee, *Quantum Field Theory in a Nutshell*, especially the QED and gauge-invariance chapters, for physical intuition and a brisk route through the core ideas.

### Deeper references

- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on electromagnetic interactions, Faddeev–Popov, Ward identities, QED renormalization, and famous QED results.
- Weinberg, *The Quantum Theory of Fields*, Vol. I, for a systematic particle-physics treatment of QED, scattering, renormalization, and infrared structure.
- Itzykson and Zuber, *Quantum Field Theory*, and Peskin and Schroeder, *An Introduction to Quantum Field Theory*, for additional standard derivations and QED calculations.

## Version history

- **2026-06-17:** Initial chapter overview for the improved Abelian Gauge Theory and QED chapter.
- **2026-06-17:** Linked the first two ordinary pages: Maxwell Theory as Gauge Theory and Scalar QED.
- **2026-06-17:** Linked Spinor QED and QED Lagrangian, and corrected the covariant-derivative landmark to $D_\mu=\partial_\mu+iqA_\mu$.
- **2026-06-17:** Linked Gauge Fixing in QED and Photon Propagator, completing the transition from the gauge-invariant QED Lagrangian to covariant perturbation theory.
- **2026-06-17:** Linked QED Vertices and Ward–Takahashi Identity, completing the chapter path from local QED Feynman rules to exact Abelian gauge identities; corrected the scalar-QED charge-flow vertex sign in the chapter landmark table.
- **2026-06-17:** Linked Vacuum Polarization and Running Electric Charge, completing the first-pass QED path from the classical Maxwell field through gauge fixing, vertices, Ward identities, one-loop screening, and the QED beta function.
- **2026-06-17:** Linked the next chapter overview, Non-Abelian Gauge Theory and Yang–Mills, as the continuation after QED.
