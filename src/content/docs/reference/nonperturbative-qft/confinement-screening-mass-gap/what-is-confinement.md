---
title: "What Is Confinement?"
description: "Defines confinement carefully through probe charges, line operators, spectra, screening, and matter-content dependence."
sidebar:
  label: "What Is Confinement?"
  order: 1
level: Advanced
status: "Polished draft"
source: "Wilson; Polyakov; Srednicki ch. 82; Shifman chs. 1 and 9; Gaiotto–Kapustin–Seiberg–Willett."
topics:
  - confinement
  - screening
  - Wilson loops
  - line operators
  - center symmetry
  - one-form symmetry
  - mass gap
  - flux tubes
canonicalTopics:
  - nonperturbative-qft
  - confinement
  - screening
  - line-operators
  - one-form-symmetry
researchStatus:
  established:
    - "In pure Yang–Mills theory and related theories with unscreened center charge, confinement is sharply diagnosed by large Wilson loops, flux tubes, and one-form symmetry realization."
  active:
    - "In gauge theories with dynamical fundamental matter, no single Wilson-loop order parameter universally defines confinement; one must use spectra, screening, line operators, and long-distance phases together."
---

## Summary

Confinement is the nonperturbative phenomenon in which certain gauge charges cannot be isolated as finite-energy asymptotic objects. That sentence is true, but it is not yet a definition. In gauge theory, the words “charge,” “isolated,” “asymptotic,” and even “certain” all hide choices: the matter content, the global form of the gauge group, the allowed line operators, the spacetime dimension, and whether one is discussing probe charges or dynamical particles.

The cleanest practical definition is therefore diagnostic rather than slogan-based. In a pure confining gauge theory, a heavy external charge and its conjugate are connected by a flux tube whose energy grows linearly with separation,

$$
V(r)
\longrightarrow \sigma r
\qquad (r\to\infty),
$$

and the corresponding large rectangular Wilson loop obeys an area law. In modern language, this is also the phase where the electric center one-form symmetry is unbroken and Wilson lines charged under it have area-law behavior.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A confinement diagnostic map showing line operators, spectra, screening, and matter content feeding into a careful definition of confinement.](/figures/nonperturbative-qft/what-is-confinement-map.svg)

<figcaption>

Confinement is best treated as a network of diagnostics. In pure gauge theory, Wilson loops, flux tubes, one-form symmetry, and a gapped color-singlet spectrum point to the same phase. With dynamical fundamental matter, string breaking and screening remove the sharp Wilson-loop criterion even though colored asymptotic particles can still be absent.

</figcaption>
</figure>

The hard part is that QCD-like theories with light dynamical quarks do not have an exact asymptotic Wilson-loop area law: the string between external fundamental sources can break by quark–antiquark pair creation. Nevertheless, quarks and gluons do not appear as isolated particles in the observed spectrum. That is why a serious page on confinement must separate several ideas that are often fused together in casual speech.

## Prerequisites

You should know [Wilson-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/wilson-loop-diagnostics/), [’t Hooft-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/thooft-loop-diagnostics/), [Polyakov-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/polyakov-loop-diagnostics/), and [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/).

The page also uses [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/), [Continuum Limit](/nonperturbative-qft/nonperturbative-definitions/continuum-limit/), [Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/), and [Defects Versus Operators](/nonperturbative-qft/solitons-defects-extended-configurations/defects-versus-operators/).

## Core idea

Gauge theory has no gauge-invariant local operator that creates a single colored quark or gluon as an isolated physical particle. This is already a warning: one should not define confinement by saying “the gauge symmetry is unbroken” or “colored fields are not gauge invariant.” Gauge redundancy is never an ordinary physical symmetry. It is a descriptional redundancy, not a symmetry that acts on the physical Hilbert space in the same way as baryon number or rotations.

The physical question is different:

$$
\text{What happens to objects carrying nontrivial gauge-theory charge at long distance?}
$$

There are several possible answers.

| Long-distance behavior | Physical picture | Typical diagnostic |
|---|---|---|
| Confinement | electric flux is squeezed into a tube; isolated probe charges cost infinite energy | Wilson-loop area law |
| Screening | dynamical matter neutralizes the probe charge | Wilson-loop perimeter law or string breaking |
| Coulomb phase | flux spreads through space with a long-range field | massless gauge boson and Coulomb potential |
| Higgs phase | gauge field becomes massive and charges can be screened by condensates | perimeter law for suitable Wilson loops |
| Topological phase | no local massless particles but nontrivial line/surface sectors remain | topological line operators and ground-state structure |

Confinement is sharpest when there is an exact global symmetry whose charged objects are line operators. For pure $SU(N)$ Yang–Mills theory, or $SU(N)$ gauge theory with only adjoint matter, Wilson loops of nonzero $N$-ality are charged under a $\mathbb Z_N$ electric one-form symmetry. In the standard confining phase, those Wilson loops have an area law. The [one-form symmetry language](/nonperturbative-qft/confinement-screening-mass-gap/one-form-symmetry-confinement/) is not extra decoration; it explains why the Wilson loop can behave like an order parameter even though it is extended rather than local.

## Setup and conventions

We use the conventions of [Conventions and Notation](/nonperturbative-qft/conventions/). Let $G$ be a compact gauge group, and let $R$ be a representation used for a heavy external probe. The Wilson loop is

$$
W_R(C)=\frac{1}{\dim R}\operatorname{tr}_R\,\mathcal P
\exp\left(-i\oint_C A\right),
$$

where $C$ is a closed Euclidean curve and $A=A^a_\mu T^a_R dx^\mu$ is the gauge connection in representation $R$.

For a rectangular loop $C_{r,\mathcal T}$ of spatial size $r$ and Euclidean time extent $\mathcal T$, the static potential between heavy probe sources is extracted from

$$
V_R(r)
=-\lim_{\mathcal T\to\infty}\frac{1}{\mathcal T}
\log \langle W_R(C_{r,\mathcal T})\rangle_{\rm ren},
$$

up to additive self-energy conventions for the external sources.

A strict Wilson-loop confinement criterion says that, for large loops,

$$
\langle W_R(C)\rangle_{\rm ren}
\sim \exp[-\sigma_R A(C)]
$$

with $\sigma_R>0$ for the relevant unscreened probe charge. For rectangular loops this gives

$$
V_R(r)\sim \sigma_R r.
$$

Here $A(C)$ means the minimal area bounded by the loop in the large smooth-loop approximation. On the lattice it is more literal: at strong coupling the leading contribution is obtained by tiling the loop with plaquettes.

## Several meanings of confinement

Different communities use “confinement” in related but not identical ways. The following distinctions prevent most confusion.

### Probe-charge confinement

This is the Wilson criterion. Insert infinitely heavy external sources in a representation $R$. If the energy of the lowest state containing the source–antisource pair grows without bound as the separation $r$ grows,

$$
V_R(r)\to\infty,
$$

and especially if $V_R(r)\sim \sigma_R r$, the probe charge is confined.

This definition is clean in pure gauge theory because the heavy probes cannot be screened by dynamical fundamental charges. It is also the definition most directly connected to the Wilson-loop area law.

### Absence of colored asymptotic particles

In QCD one often says confinement means that quarks and gluons never appear as isolated particles in the $S$-matrix. The observed asymptotic states are color singlets such as mesons, baryons, and glueball candidates, not colored states.

This statement is physically central, but it is not the same as the Wilson criterion. Light dynamical quarks can break the string between external fundamental sources. Then the static potential stops growing linearly at sufficiently large distance, but isolated colored asymptotic particles are still absent. The phrase “quark confinement” often refers to this more phenomenological fact.

### One-form symmetry realization

In a theory with a genuine electric one-form symmetry, line operators are charged objects. In pure $SU(N)$ Yang–Mills theory, Wilson lines of nonzero $N$-ality are charged under the $\mathbb Z_N$ center one-form symmetry. A standard confining phase is one in which that one-form symmetry is unbroken. The charged Wilson loops obey an area law.

This modern formulation has two virtues. First, it makes confinement look like ordinary symmetry realization, but with extended charged operators. Second, it immediately explains why fundamental matter changes the story: dynamical fundamental fields explicitly break the center one-form symmetry, so the Wilson loop is no longer an exact order parameter.

### Flux-tube confinement

The physical image behind the area law is that the color-electric flux between two distant sources does not spread into all of space. It collimates into a tube with approximately fixed energy per unit length. If the flux tube cannot break, the energy grows as

$$
E_{\rm flux}(r)\approx \sigma r.
$$

The flux-tube picture is vivid and useful, but it is not a complete definition. Some confining theories have multiple string tensions, screening by adjoint matter, or topological sectors that require a more refined line-operator description.

## Confinement is not the same as a mass gap

A mass gap is a statement about the spectrum above the vacuum. In a relativistic theory on infinite space, a mass gap means that the lowest non-vacuum excitation has positive energy at zero momentum. Equivalently, connected Euclidean correlators of local operators decay exponentially at long distance:

$$
\langle \mathcal O(x)\mathcal O(0)\rangle_c
\sim e^{-m|x|}
$$

for the lightest state that couples to $\mathcal O$.

Confinement is a statement about charge sectors and long-distance response to external probes. The two are related in pure Yang–Mills theory but not logically identical.

| Theory or phase | Mass gap? | Confinement? | Comment |
|---|---:|---:|---|
| massive scalar theory | yes | no | No gauge charge is being confined. |
| free Maxwell theory in four dimensions | no | no | Photon is massless; Wilson potential is Coulombic. |
| pure Yang–Mills, expected continuum phase | yes | yes | Glueball spectrum and Wilson-loop area law are expected. |
| Higgs phase with fundamental matter | yes | not sharply, by Wilson criterion | Charges can be screened; no exact center one-form order parameter. |
| QCD with physical quark masses | yes, physically | subtle | No colored asymptotic states, but fundamental strings can break. |
| QCD in the exact chiral limit | no, because Goldstone pions are massless | subtle | Chiral symmetry breaking removes the mass gap while color confinement can still be discussed. |

The mathematical [Yang–Mills Mass Gap Problem](/nonperturbative-qft/confinement-screening-mass-gap/yang-mills-mass-gap-problem/) asks for a rigorous construction of four-dimensional quantum Yang–Mills theory and proof of a positive mass gap. That is a much stronger statement than “lattice data and physical arguments strongly support confinement.”

## Screening and string breaking

Suppose one inserts a heavy fundamental source $Q$ and antisource $\overline Q$ into a theory with light dynamical quarks $q$. At intermediate distances, the state may look like a flux tube connecting $Q$ and $\overline Q$:

$$
E(r)\approx \sigma r.
$$

But once $\sigma r$ exceeds the energy needed to create a light pair $q\overline q$, the system can rearrange:

$$
Q\overline Q
\longrightarrow
(Q\overline q)+(q\overline Q).
$$

The flux tube breaks into two color-singlet heavy-light mesons. The asymptotic static energy saturates rather than growing forever. The large Wilson loop then no longer has the pure area-law behavior expected in a theory with no screening charges.

This is not a small technicality. It is why “Wilson-loop area law” is a sharp confinement diagnostic in pure gauge theory but not a universal definition of confinement in all QCD-like theories.

## N-ality and what gluons can screen

In pure $SU(N)$ Yang–Mills theory, dynamical gluons transform in the adjoint representation. Adjoint matter has zero charge under the center $\mathbb Z_N$. Therefore adjoint gluons can screen some representation-theoretic details of an external source, but they cannot change its $N$-ality.

The $N$-ality of a representation is its charge under the center. Representations with the same $N$-ality are expected to have the same asymptotic confinement class, even if their intermediate-distance potentials differ.

For example, in $SU(3)$:

| Representation | Center charge | Asymptotic behavior in pure gauge theory |
|---|---:|---|
| fundamental $\mathbf 3$ | nonzero | confined by a nonzero string tension |
| antifundamental $\overline{\mathbf 3}$ | nonzero | confined with conjugate charge |
| adjoint $\mathbf 8$ | zero | can be screened by gluons |

This is another reason why one should not say simply “all colored charges have the same linear potential forever.” The asymptotic classification is controlled by unscreened global charge, not just by the Lie algebra representation at short distances.

## What one should check in practice

A responsible confinement claim should specify the theory and the observable. Useful checks include:

| Check | What it tests | What it cannot do alone |
|---|---|---|
| Wilson-loop area law | confinement of electric probe charges | define confinement with fundamental dynamical matter |
| Static potential | energy of heavy source–antisource sector | prove absence of all colored asymptotic states |
| Polyakov loop | thermal free energy of a static source and center symmetry in pure gauge theory | diagnose zero-temperature confinement by itself |
| ’t Hooft loop | magnetic or dual disorder response | replace the Wilson criterion in all theories |
| Local correlator gap | massive color-singlet spectrum | prove line-operator confinement |
| Lattice continuum extrapolation | nonperturbative numerical evidence | equal a constructive proof automatically |
| One-form symmetry | sharp order-parameter language for genuine lines | apply when dynamical matter explicitly breaks the symmetry |

For pure Yang–Mills theory, these diagnostics strongly reinforce each other. [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/) adds a complementary organizing limit in which color-singlet states become narrow and flux-tube interactions are suppressed. At finite $N$, these diagnostics still reinforce each other: the theory is expected to have a mass gap, a spectrum of glueballs, confining flux tubes, and Wilson-loop area laws for nonzero center charge. For full QCD, one must combine several diagnostics with the empirical fact that the physical spectrum contains color singlets.

## Common pitfalls

**Saying that gauge symmetry is confined.** Gauge symmetry is redundancy, not an ordinary physical symmetry. Confinement concerns gauge-invariant observables, charge sectors, and line operators.

**Treating the Wilson-loop area law as a universal definition.** It is sharp in pure gauge theory and related theories without screening charges. With dynamical fundamental matter, string breaking changes the large-loop behavior.

**Equating confinement with strong coupling.** Some confinement mechanisms are visible semiclassically in special regimes, and some strongly coupled theories are conformal rather than confining. Strong coupling and confinement are related ideas, not synonyms.

**Equating confinement with a mass gap.** A theory can be gapped without confining. Confinement is about the fate of charges or line operators; a mass gap is about the spectrum.

**Ignoring the global form of the gauge group.** The Lie algebra does not determine the complete set of genuine line operators. The global form of the gauge group matters for Wilson lines, ’t Hooft lines, one-form symmetries, and phase distinctions.

## Research status

- **Established:** Wilson loops, static potentials, Polyakov loops, ’t Hooft loops, center symmetry, and one-form symmetry provide standard gauge-invariant diagnostics of confinement and screening in appropriate theories.
- **Established:** Lattice gauge theory gives a nonperturbative regulator and strong numerical evidence for confinement and a mass gap in pure non-Abelian gauge theory.
- **Established:** In theories with dynamical fundamental matter, the fundamental Wilson-loop area law is not an exact asymptotic order parameter because flux tubes can break.
- **Active:** A complete analytic explanation of four-dimensional confinement in ordinary Yang–Mills theory remains a major research problem.
- **Active:** The best language for classifying phases of gauge theories with varied matter content, global form, anomalies, and generalized symmetries is still developing.
- **Open mathematical problem:** Constructing four-dimensional pure Yang–Mills theory and proving a positive mass gap at full mathematical rigor remains open.

## Relation to other topics

The next calculation is [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/). That page turns the qualitative statement “linear confinement” into a precise relation between large rectangular loops, static potentials, and string tension. The complementary page [Perimeter Law and Screening](/nonperturbative-qft/confinement-screening-mass-gap/perimeter-law-and-screening/) explains what replaces the area-law criterion when charges can be screened.

For the operator side, see [Wilson-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/wilson-loop-diagnostics/), [’t Hooft-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/thooft-loop-diagnostics/), and [Polyakov-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/polyakov-loop-diagnostics/). For the spectral side, see [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/) and [Spectral Density](/nonperturbative-qft/order-parameters-diagnostics/spectral-density/).

[String Tension](/nonperturbative-qft/confinement-screening-mass-gap/string-tension/) isolates the physical coefficient $\sigma$ from the area-law formula, and [Flux Tubes](/nonperturbative-qft/confinement-screening-mass-gap/flux-tubes/) explains the corresponding color-electric field configuration and long-string description. [Mass Gap in Gauge Theory](/nonperturbative-qft/confinement-screening-mass-gap/mass-gap/) separates the spectral question from the line-operator question. [Strong-Coupling Expansion](/nonperturbative-qft/confinement-screening-mass-gap/strong-coupling-expansion/) derives an area law by lattice plaquette tiling, while [Compact QED in Three Dimensions](/nonperturbative-qft/confinement-screening-mass-gap/compact-qed-three-dimensions/) derives one from monopole instantons. [Higgs versus Confinement](/nonperturbative-qft/confinement-screening-mass-gap/higgs-versus-confinement/) explains when the Higgs-like and confinement-like regimes are smoothly connected, and [Confinement Mechanisms](/nonperturbative-qft/confinement-screening-mass-gap/confinement-mechanisms/) compares the main proposed dynamical explanations.

## Exercises

### Exercise 1: Mass gap versus confinement

Give an example of a theory with a mass gap but no confinement. Explain which part of the definition of confinement fails.

<details>
<summary><strong>Solution</strong></summary>

A free massive scalar field has a mass gap $m$ because its lightest particle has positive mass and its Euclidean two-point function decays exponentially. But there is no gauge charge whose isolation is obstructed, no Wilson-loop area law, and no flux tube between external sources. Therefore the theory is gapped but not confining.

</details>

### Exercise 2: String breaking

Suppose a heavy source–antisource pair initially has energy $V(r)\approx \sigma r$. In a theory with light dynamical matter, the energy needed to create the pair that screens the sources is approximately $2M$. Estimate the string-breaking distance.

<details>
<summary><strong>Solution</strong></summary>

String breaking becomes energetically favorable when the flux-tube energy is comparable to the screening threshold:

$$
\sigma r_{\rm break}\sim 2M.
$$

Thus

$$
r_{\rm break}\sim \frac{2M}{\sigma}.
$$

This is only a parametric estimate. The actual crossover depends on mixing between the flux-tube state and the two screened heavy-light states.

</details>

### Exercise 3: N-ality screening

In pure $SU(N)$ Yang–Mills theory, explain why adjoint gluons can screen an adjoint external source but cannot screen a fundamental external source all the way to the vacuum.

<details>
<summary><strong>Solution</strong></summary>

Adjoint gluons have zero charge under the center $\mathbb Z_N$. Screening by gluons can change the detailed representation of a source by tensoring with adjoint representations, but it cannot change the source’s center charge. An adjoint source has zero $N$-ality and can be screened to a singlet. A fundamental source has nonzero $N$-ality, so no number of adjoint gluons can remove its center charge. In pure gauge theory it remains in a nontrivial asymptotic string sector.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, especially the discussion of Wilson loops, lattice gauge theory, and confinement.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapters on phases of gauge theories and confinement in four-dimensional and lower-dimensional models.
- A. M. Polyakov, *Gauge Fields and Strings*, especially strong-coupling expansion, quark confinement, compact QED, and loop dynamics.

### Deeper references

- K. Wilson, “Confinement of Quarks,” for the lattice Wilson-loop criterion.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the one-form symmetry interpretation of confinement and line-operator laws.
- J. Greensite, *An Introduction to the Confinement Problem*, for a broad review of confinement mechanisms and diagnostics.
- A. Jaffe and E. Witten, “Quantum Yang–Mills Theory,” and the Clay Mathematics Institute problem page for the mathematical existence and mass-gap problem.

## Version history

- **2026-06-27:** Initial polished page. Separated probe confinement, spectral confinement, one-form symmetry, screening, and mass gap.
- **2026-06-27:** Added links to the center-symmetry and one-form-symmetry pages.
- **2026-06-27:** Added links to the strong-coupling and compact-QED mechanism pages.
- **2026-06-27:** Added links to the dedicated Mass Gap and Flux Tubes pages.
