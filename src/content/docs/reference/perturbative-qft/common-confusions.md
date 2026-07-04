---
title: "Common Confusions"
description: "A diagnostic guide to the most common conceptual, convention, and calculational mistakes in perturbative QFT and scattering."
sidebar:
  label: "Common Confusions"
  order: 12
level: Graduate
status: "Polished draft"
source: "Srednicki 2007; Coleman 2019; Weinberg 1995; Zee 2010; Schwartz 2014"
topics:
  - perturbative QFT
  - scattering
  - Feynman diagrams
  - renormalization
  - infrared physics
canonicalTopics:
  - perturbative-qft-common-confusions
  - scattering-diagnostics
researchStatus:
  established:
    - "The distinctions collected here are textbook-standard across perturbative QFT, scattering theory, renormalization, and gauge-theory calculations."
  active:
    - "The practical handling of infrared-safe observables, precision predictions, and computational workflows continues to evolve in specialized contexts."
---

## Summary

This page is a repair manual for perturbative QFT. It collects mistakes that are easy to make even after one knows the formal rules: confusing Green functions with amplitudes, amputating external legs incorrectly, treating virtual particles as observable intermediate states, losing normalization factors, mixing schemes, overinterpreting individual gauge-dependent diagrams, and asking an infrared-divergent question of a massless theory.

The shortest diagnostic is this:

| Before trusting a formula, ask | Why it matters |
|---|---|
| What object is being computed? | A full correlator, connected correlator, amputated correlator, 1PI vertex, S-matrix element, cross section, or decay rate has different rules. |
| Are the external momenta on shell? | Operator insertions in Green functions may be off shell; asymptotic particles in the S-matrix are on shell. |
| Which convention fixes the factors? | The signs, $i$'s, $(2\pi)^4$, $2E_{\mathbf p}$, and delta functions follow from conventions, not vibes. |
| Is the quantity physical? | Off-shell Green functions, individual diagrams, gauge-fixed propagators, and scheme-dependent parameters are not observables by themselves. |
| Is the observable infrared safe? | Massless gauge theories do not assign finite probabilities to arbitrarily exclusive final states. |

A useful mental map is

$$
\text{correlators}
\longrightarrow
\text{connected pieces}
\longrightarrow
\text{amputated external propagators}
\longrightarrow
\text{on-shell external states}
\longrightarrow
\mathcal M
\longrightarrow
\text{rates and cross sections}.
$$

Every arrow has hypotheses. The most common errors in this volume come from using a formula from one stage as though it belonged to another.

## Prerequisites

You should know the QFT.org [Conventions and Notation](/perturbative-qft/conventions/), the basic [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/) normalization, the idea of [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/), and the distinction between [Connected and Disconnected Diagrams](/perturbative-qft/diagrammatics-feynman-rules/connected-and-disconnected-diagrams/). For loop and gauge-theory confusions, also review [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/) and [Gauge Fixing for Perturbation Theory](/perturbative-qft/gauge-theory-perturbation-theory/gauge-fixing-for-perturbation-theory/).

## Core idea

Perturbative QFT has many layers of bookkeeping because it computes several different kinds of objects with similar-looking diagrams. A line can be a propagator inside a Green function, an external leg waiting to be amputated, an on-shell wavefunction factor in an amplitude, or an unresolved soft/collinear particle contributing to an inclusive observable. The drawings look related because the same local Lagrangian controls them; the formulas differ because the questions differ.

When a calculation feels inconsistent, do not first suspect deep physics. First check the object, normalization, convention, gauge choice, regulator, renormalization scheme, and infrared definition. A large fraction of apparent paradoxes die there. Little ghost stories, mostly.

## Setup and conventions

This page uses the conventions fixed in [Conventions and Notation](/perturbative-qft/conventions/). In particular,

$$
S_{fi}=\delta_{fi}+i(2\pi)^4\delta^{(4)}(p_f-p_i)\mathcal M_{fi},
$$

and one-particle states use relativistic normalization. We do not repeat every convention here; the point of this page is to diagnose what went wrong when those conventions are mixed.

## Correlators are not automatically amplitudes

A time-ordered Green function is an expectation value of operator insertions. For a scalar field,

$$
G_n(x_1,\ldots,x_n)=\langle0|T\{\phi(x_1)\cdots\phi(x_n)\}|0\rangle.
$$

An S-matrix element is a transition amplitude between asymptotic particle states. These are related by LSZ reduction when the external fields overlap with one-particle states and the theory has suitable asymptotic states, but they are not identical objects.

| Object | What it includes | Typical use |
|---|---|---|
| Full correlator | Connected and disconnected pieces, including external propagators | Source-functional differentiation and operator correlators |
| Connected correlator | Pieces connected to the insertions | Scattering-relevant Green functions and clustering |
| Amputated correlator | External propagators removed | Intermediate object before LSZ/on-shell projection |
| 1PI vertex | Graphs that cannot be split by cutting one internal line | Effective action and Dyson resummation |
| S-matrix amplitude | On-shell asymptotic states with momentum conservation stripped off | Cross sections, decay rates, unitarity |

The most dangerous shortcut is to write down a Feynman diagram and say “this is the amplitude” before specifying which of these objects the diagram represents. In a scalar tree-level example the distinction may be hidden because many external factors are trivial. In loop, spinor, gauge, composite-operator, or unstable-particle calculations, the distinction becomes load-bearing.

## Amputation is not the same as going on shell

Amputation removes external propagators. Going on shell imposes the physical pole condition for external particles. These are separate operations.

For a scalar two-point function with an isolated one-particle pole,

$$
G_2(p)\sim \frac{iZ}{p^2-m^2+i\epsilon}+\text{terms regular at }p^2=m^2.
$$

LSZ uses the residue of this pole. Roughly speaking, multiplying by inverse external propagators amputates the legs, while taking the on-shell limit extracts the pole residue. Setting $p^2=m^2$ too early usually gives either zero, infinity, or a formula with the right smell and the wrong substance.

Common repairs:

| Mistake | Repair |
|---|---|
| “The external propagator is singular, so the amplitude diverges.” | LSZ multiplies by inverse pole factors before taking the on-shell limit. |
| “Amputated means on shell.” | Amputated Green functions can be kept off shell. On-shell projection is an additional step. |
| “The residue is always one.” | The residue is one only in a field normalization or scheme where the corresponding $Z$ has been fixed that way. |

## Virtual particles are not observed particles

Internal lines are propagators, not particles registered by a detector. The momentum flowing through an internal line is usually integrated over and need not satisfy an on-shell relation. Calling an internal line a “virtual particle” is harmless shorthand only if one remembers what it is shorthand for.

A virtual particle is not a short-lived ordinary particle. It is not literally hiding inside the detector until the uncertainty principle lets it get away with something. It is a piece of a perturbative representation of a quantum amplitude.

This also explains why a different gauge, field basis, or diagram organization can change the apparent internal story while leaving the final observable unchanged. If the internal story were literal, this would be a disaster. Since it is bookkeeping, it is fine.

## Diagrams are not microscopic movies

Feynman diagrams organize terms in an expansion. They are not spacetime photographs of what “really happened.” The axes are usually absent for a reason.

**Time ordering does not mean a unique classical time sequence.** Covariant diagrams combine contributions that would be separated in old-fashioned time-ordered perturbation theory. The covariant propagator packages them into a Lorentz-friendly object.

**Loops do not mean particles moving in little circles.** A loop indicates an unfixed momentum integration. Its physical effects can include renormalization, thresholds, absorptive parts, anomalous dimensions, or vacuum polarization, depending on the observable.

**A diagrammatic channel is not always a separate physical process.** The $s$-, $t$-, and $u$-channel terms are often individually useful, but the physical amplitude may require their coherent sum, especially for identical particles or gauge theories.

## Delta functions, volumes, and probabilities

The S-matrix is normalized with momentum-conserving delta functions. The formula

$$
S_{fi}=\delta_{fi}+i(2\pi)^4\delta^{(4)}(p_f-p_i)\mathcal M_{fi}
$$

does not by itself give a probability. Squaring it produces the familiar formal factor $[(2\pi)^4\delta^{(4)}(P)]^2$, which must be interpreted through wave packets, finite spacetime volume regularization, or the standard derivation of rates and cross sections.

The repair is to use the invariant phase-space formula, not to square delta functions by instinct. For a decay,

$$
d\Gamma=\frac{1}{2M}|\mathcal M|^2 d\Pi_n,
$$

with symmetry factors for identical final particles when needed. For a two-particle scattering process,

$$
d\sigma=\frac{1}{4E_1E_2|\mathbf v_1-\mathbf v_2|}|\mathcal M|^2 d\Pi_n,
$$

in the same normalization. The flux factor and the phase-space measure are not optional decorations; they are what turn amplitudes into measurable rates.

## Symmetry factors are not aesthetic choices

A symmetry factor divides by overcounting. It is not a guess based on whether the graph “looks symmetric.” The honest definition is combinatorial: count the number of Wick contractions that produce the same labeled contribution, including the factorials already present in the Dyson expansion and in the interaction Lagrangian.

For example, in $\lambda\phi^4/4!$ theory, the first four-point contact diagram has no leftover factor for labeled external insertions: the $4!$ attachments cancel the $1/4!$. The one-loop tadpole correction to the two-point function has a leftover factor $1/2$. The cure for confusion is not memorizing a zoo of factors; it is returning to Wick contractions for a small representative example.

## Identical particles affect amplitudes and phase space

Identical particles enter twice.

First, the amplitude must respect Bose or Fermi exchange properties. For identical external particles, different attachments or channels may represent indistinguishable alternatives that must be added coherently.

Second, the phase-space integral for identical final particles includes a statistical factor. If $n_a$ identical particles of species $a$ appear in the final state, divide by $n_a!$ in the final-state counting. This factor prevents counting the same physical final state multiple times.

Do not use the phase-space symmetry factor to replace the exchange terms in the amplitude. One handles state counting; the other handles quantum interference.

## The iε prescription is not just a convergence trick

The $i\epsilon$ prescription tells us which Green function is being computed and how poles are bypassed. For the scalar Feynman propagator,

$$
\frac{i}{p^2-m^2+i\epsilon}
$$

is a distribution with a definite causal and analytic meaning. Replacing $i\epsilon$ by “a small number that helps the integral converge” loses the point.

The prescription controls time ordering, Wick rotation, thresholds, discontinuities, and unitarity cuts. It is also one of the first places where a sign error can masquerade as deep confusion. If two sources disagree, compare their metric, Fourier transform, and propagator equation before deciding that physics changed.

## Regulators are not renormalization schemes

A regulator makes intermediate expressions well-defined. A renormalization scheme tells us how to define finite parameters after divergences have been isolated.

| Word | Role |
|---|---|
| Regulator | Temporarily modifies integrals, for example by a cutoff or by dimensional continuation. |
| Counterterm | Local term chosen to cancel regulator dependence and impose renormalization conditions. |
| Scheme | Rule for choosing the finite parts of counterterms. |
| Scale | Auxiliary parameter such as $\mu$ introduced by the renormalization convention. |
| Observable | Scheme-independent quantity after all pieces are consistently combined. |

Dimensional regularization and minimal subtraction often appear together, but they are not the same thing. One is a regulator; the other is a subtraction prescription. A cutoff regulator with physical renormalization conditions is another possible combination.

## Bare parameters are not measured parameters

Bare parameters are bookkeeping variables in a regulated description. They are not what a detector measures. A mass appearing in the bare Lagrangian, a pole mass, an on-shell mass, and an $\overline{\rm MS}$ running mass are different objects with different uses.

The same is true for couplings. The symbol $e$, $g$, or $\lambda$ is not enough. One must know the scheme, scale, and definition. Precision QFT without this metadata is numerology wearing a blazer.

## Counterterms are not cheating

A counterterm is not an admission that the theory failed. In perturbative renormalization, counterterms are the local terms required to express predictions in terms of chosen physical or renormalized parameters.

The practical test is locality. UV divergences in local QFT appear as local polynomials in external momenta and fields. They can be absorbed into local terms compatible with the symmetries. If a proposed divergence cannot be absorbed into allowed local operators, the theory or observable has a deeper consistency problem.

## Gauge-dependent objects are not observables

Gauge fixing is a method for computing. It introduces gauge-dependent propagators, ghost fields, and sometimes gauge-parameter dependence in intermediate Green functions. Physical S-matrix elements between physical states and gauge-invariant observables must not depend on the gauge parameter.

Common traps:

| Trap | Repair |
|---|---|
| “This propagator has unphysical polarizations, so the theory has negative-probability particles.” | Gauge fixing enlarges the bookkeeping space; physical states are selected by constraints, Ward identities, or BRST cohomology. |
| “Ghosts are particles with wrong statistics.” | Faddeev–Popov ghosts are anticommuting scalar fields that cancel unphysical gauge degrees of freedom in loops. They are not asymptotic detector particles. |
| “A single diagram is not gauge invariant, so something is wrong.” | Gauge invariance is usually restored only after summing the required set of diagrams and counterterms. |
| “Off-shell Green functions should be gauge independent.” | Off-shell gauge-fixed correlators can depend on gauge choice. Physical observables should not. |

Gauge theory is where diagrammatic intuition becomes least literal and most useful. It is also where sloppy language about “particles inside diagrams” causes maximum mayhem.

## Ward identities are not optional consistency checks

Ward, Ward–Takahashi, and Slavnov–Taylor identities are the algebraic memory of gauge symmetry after quantization and gauge fixing. They relate diagrams that may look unrelated. In QED, a basic momentum-space Ward–Takahashi identity has the schematic form

$$
q_\mu\Gamma^\mu(p+q,p)=S^{-1}(p+q)-S^{-1}(p),
$$

up to convention-dependent definitions of the full vertex and inverse propagator. This identity is not a decorative afterthought; it controls charge renormalization, gauge-parameter cancellations, and the consistency of external photon amplitudes.

If a gauge-theory calculation violates the relevant identity, check signs, momentum flow, ghost diagrams, counterterms, and external polarization sums before drawing a physical conclusion.

## Infrared divergences are questions answered too exclusively

UV divergences come from short distances or large loop momenta. Infrared divergences come from long distances, soft particles, or collinear configurations. They have different meanings and different cures.

In massless gauge theories, an amplitude for producing exactly a fixed number of photons or gluons is often not a physical observable. Detectors have finite resolution, and degenerate states with additional soft or collinear radiation must be included. The Bloch–Nordsieck and Kinoshita–Lee–Nauenberg mechanisms explain how cancellations occur for sufficiently inclusive quantities.

The right question is not always “why is this amplitude divergent?” Often it is “what observable did I actually define?”

## Inclusive does not mean careless

An inclusive observable sums over unresolved final states according to a measurement function. It is not a vague instruction to add “some radiation.” A well-defined observable specifies what is measured, what is summed over, the resolution scale, and whether the definition is infrared and collinear safe.

For collider-like observables, jet definitions and cuts are part of the theoretical observable. For decay rates, inclusive may mean summing over soft radiation below a detector threshold. For partonic calculations, factorization may be needed to absorb collinear sensitivity into parton distributions or fragmentation functions.

## The optical theorem relates forward amplitudes to inclusive sums

The optical theorem is a consequence of unitarity, not a model-specific trick. Schematically,

$$
2\,\operatorname{Im}\mathcal M_{i\to i}
=
\sum_X \int d\Pi_X\,|\mathcal M_{i\to X}|^2,
$$

with the precise normalization fixed by the S-matrix convention. The right-hand side is inclusive over allowed intermediate or final states. That inclusivity is the point.

A common mistake is to compare the imaginary part of one diagram with the square of one diagram. The theorem applies after the correct cuts, states, symmetry factors, and perturbative order are identified.

## Modern amplitude methods change representation, not physics

Spinor-helicity variables, color ordering, BCFW recursion, generalized unitarity, on-shell diagrams, and double-copy relations reorganize amplitudes around on-shell information. They often make locality, gauge redundancy, and diagram proliferation less visible. That is a feature, not a bug.

But these methods come with their own traps:

| Method | Common mistake |
|---|---|
| Spinor helicity | Forgetting little-group weights or complex-momentum conventions. |
| Color ordering | Treating a color-ordered partial amplitude as the full color-dressed amplitude. |
| BCFW recursion | Assuming the boundary term vanishes without checking large-complex-momentum behavior. |
| Generalized unitarity | Confusing cut-constructible information with the full regulated amplitude. |
| Double copy | Replacing color by kinematics without satisfying the needed numerator relations or using a valid generalized-gauge representation. |

Modern methods are powerful because they expose hidden structure. They do not remove the need to define the object being computed.

## Fast convention checks

Use this table when formulas disagree across sources.

| Symptom | Check first |
|---|---|
| Propagator denominator has the opposite sign | Metric signature and Fourier phase. |
| Amplitude differs by a sign of $i$ | Whether the interaction is written in $\mathcal L_{\rm int}$ or $\mathcal H_I$, and how the S-matrix is defined. |
| Cross section differs by factors of $2E$ | State normalization and phase-space convention. |
| Fermion amplitude differs by a sign | External spinor ordering, fermion-flow convention, and anticommuting source convention. |
| Gauge-theory answer depends on a gauge parameter | Missing diagrams, ghosts, counterterms, or use of an unphysical off-shell quantity. |
| Loop result differs by a finite constant | Renormalization scheme, subtraction convention, and definition of $\mu$. |
| IR result is infinite | Observable may be too exclusive, or real and virtual radiation have not been combined. |

## Relations to other pages

- [Conventions and Notation](/perturbative-qft/conventions/) fixes the normalization choices that remove most factor-of-two and factor-of-$i$ arguments.
- [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/) separates external propagator removal from on-shell projection.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) gives the diagrammatic bookkeeping behind propagators, vertices, and loop measures.
- [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/) explains how graph factors arise from Wick contractions.
- [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/) explains how finite scattering amplitudes are assembled from loops, counterterms, and external-leg factors.
- [Gauge-Parameter Independence](/perturbative-qft/gauge-theory-perturbation-theory/gauge-parameter-independence/) explains why gauge-dependent intermediate expressions can still produce gauge-independent physical observables.
- [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) and [Jets and Inclusive Observables](/perturbative-qft/infrared-physics-factorization/jets-and-inclusive-observables/) explain how infrared-safe measurements are defined.

## Research status

The confusions listed here are not research controversies. They are standard distinctions that become sharp in textbook perturbative QFT. What remains active is the practical frontier: defining and computing increasingly differential infrared-safe observables, automating high-order perturbative calculations, organizing gauge-theory amplitudes efficiently, and matching fixed-order predictions to resummation and parton showers.

The safest attitude is conservative: treat individual diagrams, off-shell Green functions, running parameters, and regulator-dependent expressions as intermediate objects unless a page explicitly explains why they are physical in the context at hand.

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, especially the chapters on LSZ reduction, Feynman rules, cross sections and decay rates, loop corrections, infrared divergences, QED, and non-Abelian gauge theory.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on perturbation theory, Wick diagrams, scattering, LSZ, renormalization, QED, Faddeev–Popov gauge fixing, and Ward identities.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on the S-matrix, Feynman rules, QED, renormalized perturbation theory, infrared divergences, unitarity, Yang–Mills theory, jets, and SCET.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, for a systematic treatment of scattering theory, cluster decomposition, Feynman rules, symmetries of the S-matrix, unitarity, QED, path integrals, and renormalization.
- A. Zee, *Quantum Field Theory in a Nutshell*, for compact physical explanations of diagrams, gauge invariance, counterterms, and unitarity.
- M. E. Peskin and D. V. Schroeder, *An Introduction to Quantum Field Theory*, for a standard diagrammatic route through scattering, loops, gauge theory, renormalization, and infrared issues.

## Version history

- **2026-06-14:** Initial polished diagnostic page for common perturbative-QFT and scattering confusions.
