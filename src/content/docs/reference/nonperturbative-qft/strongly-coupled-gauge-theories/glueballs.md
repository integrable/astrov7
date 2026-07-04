---
title: "Glueballs"
description: "Defines glueballs as pure-gauge color-singlet states, explains how their quantum numbers and masses are extracted from gauge-invariant correlators, and clarifies their relation to the Yang–Mills mass gap and real QCD spectroscopy."
sidebar:
  label: "Glueballs"
  order: 4
level: Advanced
status: "Polished draft"
source: "Srednicki; Schwartz; Shifman; Coleman; Mariño; lattice glueball reviews."
topics:
  - glueballs
  - pure Yang–Mills theory
  - gauge-invariant operators
  - lattice spectroscopy
  - mass gap
  - large N
  - QCD spectroscopy
  - operator mixing
canonicalTopics:
  - nonperturbative-qft
  - strongly-coupled-gauge-theories
  - glueballs
  - yang-mills-mass-gap
  - lattice-qcd
  - large-n-qcd
researchStatus:
  established:
    - "Pure Yang–Mills theory has a nonperturbative color-singlet spectrum whose low-lying states are conventionally called glueballs and can be extracted from gauge-invariant Euclidean correlators."
  active:
    - "In full QCD, glueball operators mix with flavor-singlet quarkonium and multi-hadron channels, so experimental glueball identification and unquenched lattice spectroscopy remain active research areas."
---

## Summary

Glueballs are color-singlet excitations created by gauge-invariant operators built primarily from the gauge field. In pure Yang–Mills theory, where there are no dynamical quarks, they are the natural massive particles of the confining theory. The simplest interpolating operators are local gluonic operators such as

$$
\mathcal O_{0^{++}}(x)=\operatorname{tr}F_{\mu\nu}F_{\mu\nu}(x),
\qquad
\mathcal O_{0^{-+}}(x)=\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}(x),
$$

with Euclidean indices in this section. More refined operators use spatial Wilson loops, smeared field strengths, variational bases, and lattice irreducible representations.

A glueball is not literally a weakly bound pair of gluons. In a confining gauge theory, gluons are not asymptotic particles. A glueball is a state in the gauge-invariant Hilbert space, defined by the poles or exponential falloffs of correlators of gluonic operators. The slogan “made of gluons” is useful only as spectroscopy intuition.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A schematic map of glueball spectroscopy: gauge-invariant gluonic operators feed into a Euclidean correlator matrix, whose spectral decomposition gives glueball levels in pure Yang–Mills theory and mixing channels in full QCD.](/figures/nonperturbative-qft/glueball-correlator-spectrum.svg)

<figcaption>

Glueball spectroscopy starts from gauge-invariant gluonic operators, not from free gluon constituents. In pure Yang–Mills theory the correlator matrix extracts a discrete color-singlet spectrum. In full QCD the same operators can mix with flavor-singlet quarkonium and multi-hadron channels.

</figcaption>
</figure>

## Prerequisites

Read [QCD as a Strongly Coupled QFT](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-as-strongly-coupled-qft/), [Hadron Spectrum](/nonperturbative-qft/strongly-coupled-gauge-theories/hadron-spectrum/), [Mass Gap in Gauge Theory](/nonperturbative-qft/confinement-screening-mass-gap/mass-gap/), [Yang–Mills Mass Gap Problem](/nonperturbative-qft/confinement-screening-mass-gap/yang-mills-mass-gap-problem/), [Spectral Density](/nonperturbative-qft/order-parameters-diagnostics/spectral-density/), [Mass-Gap Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/mass-gap-diagnostics/), and [Lattice Regularization](/nonperturbative-qft/nonperturbative-definitions/lattice-regularization/) before this page.

It also helps to know [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/), [Flux Tubes](/nonperturbative-qft/confinement-screening-mass-gap/flux-tubes/), [Large-N Confinement](/nonperturbative-qft/confinement-screening-mass-gap/large-n-confinement/), and [Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/).

## Core idea

Pure Yang–Mills theory has no matter fields. Its microscopic Lagrangian contains only gauge bosons, but the physical Hilbert space is built from gauge-invariant states. In a confining, gapped theory, the low-energy spectrum consists of massive color-singlet excitations. These are called **glueballs**.

The operational definition is:

1. choose gauge-invariant operators made from gauge fields;
2. organize them by quantum numbers;
3. compute their Euclidean correlation functions;
4. extract masses from the spectral decomposition;
5. take the infinite-volume and continuum limits.

Thus the central formula is not a constituent model wave function. It is the Euclidean correlator

$$
C_{ij}(t)=\langle \mathcal O_i(t)\mathcal O_j^\dagger(0)\rangle
-\langle \mathcal O_i\rangle\langle \mathcal O_j^\dagger\rangle,
$$

where the vacuum subtraction is essential in channels such as $0^{++}$. On a finite volume,

$$
C_{ij}(t)=\sum_n Z_i^{(n)}Z_j^{(n)*}e^{-E_nt},
\qquad
Z_i^{(n)}=\langle0|\mathcal O_i|n\rangle .
$$

At large Euclidean time the lowest state with the same quantum numbers dominates, provided the operator has nonzero overlap with it. In practice, one uses a matrix of operators and a variational method rather than trusting a single correlator.

## Setup and conventions

Unless otherwise stated, this page uses Euclidean pure Yang–Mills theory with compact simple gauge group, usually $SU(N_c)$. The Euclidean action is written schematically as

$$
S_E=\frac{1}{2g^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}F_{\mu\nu},
$$

with the trace normalization following [Conventions and Notation](/nonperturbative-qft/conventions/). In pure Yang–Mills theory there are no dynamical quark fields, so there is no string breaking by light fundamental matter and no flavor-singlet quarkonium mixing.

The lattice theory has only cubic rotational symmetry at finite lattice spacing. Continuum spin $J$ is recovered only after the continuum limit. This means that lattice glueball spectroscopy classifies operators first by irreducible representations of the cubic group and then matches degeneracy patterns to continuum $J^{PC}$ quantum numbers.

When discussing full QCD, “glueball” means a glue-rich component or state inferred from operator overlaps and mixing analysis, not an exact superselection label. The Hilbert space does not know whether a state was created by a gluonic operator, a quark bilinear, or a two-meson operator; it only knows the conserved quantum numbers.

## Pure Yang–Mills glueballs

In pure Yang–Mills theory, the simplest glueball channels are labeled by spin, parity, and charge conjugation,

$$
J^{PC}=0^{++},\,2^{++},\,0^{-+},\,\ldots .
$$

The lowest state in four-dimensional $SU(3)$ pure Yang–Mills is found numerically to be a scalar $0^{++}$ glueball. The next low-lying channels typically include tensor and pseudoscalar glueballs. The exact numerical ratios depend on the gauge group, continuum extrapolation, scale-setting convention, and systematic uncertainties, so this page emphasizes definitions and diagnostics rather than a table of masses.

A useful continuum operator dictionary is:

| Channel | Example operator | What it probes |
|---|---|---|
| $0^{++}$ | $\operatorname{tr}F_{\mu\nu}F_{\mu\nu}$ | Scalar fluctuations of the gauge action density. |
| $0^{-+}$ | $\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}$ | Pseudoscalar topological-density fluctuations. |
| $2^{++}$ | Traceless tensor built from $F_{\mu\alpha}F_{\nu\alpha}$ | Spin-two gluonic excitations. |
| Higher $J^{PC}$ | Extended Wilson-loop shapes and derivative operators | Rotational and flux-tube-like excitations. |

On the lattice, local field-strength operators are often not enough. Glueball operators are usually built from closed Wilson loops of different shapes and sizes, then smeared or blocked to improve overlap with the low-energy states. The variational basis is not window dressing; it is what turns a noisy Euclidean inverse problem into a controllable calculation.

## Correlator matrices and the variational method

A single correlator can show an effective-mass plateau, but excited-state contamination is hard to diagnose from one operator. The standard strategy is to build a matrix

$$
C_{ij}(t)=\langle \mathcal O_i(t)\mathcal O_j^\dagger(0)\rangle_c
$$

from operators $\mathcal O_i$ with the same quantum numbers and solve a generalized eigenvalue problem

$$
C(t)v_n(t,t_0)=\lambda_n(t,t_0)C(t_0)v_n(t,t_0).
$$

For sufficiently large $t$,

$$
\lambda_n(t,t_0)\sim e^{-E_n(t-t_0)}
\left[1+O\!\left(e^{-\Delta E_n(t-t_0)}\right)\right].
$$

The eigenvectors encode optimized operator combinations. The eigenvalues encode finite-volume energy levels. To turn these into continuum physics, one must still control finite spatial volume, lattice spacing, scale setting, statistics, and operator-basis dependence.

For glueballs this is especially delicate because signal-to-noise degradation can be severe. Glueball correlators are vacuum quantum-number rich, disconnected-looking in their gauge-field fluctuations, and often noisier than simple meson correlators. That practical difficulty is part of the physics: pure gauge spectroscopy is a clean conceptual problem but a hard numerical problem.

## Relation to the mass gap

The Yang–Mills mass gap is the statement that the spectrum above the vacuum has a positive lowest excitation energy in infinite volume:

$$
\Delta=\inf_{n\ne0}(E_n-E_0)>0 .
$$

In pure Yang–Mills theory, the states above the vacuum are glueballs and multi-glueball states. Therefore the lightest glueball mass is the natural spectral manifestation of the mass gap.

This does not mean the mass-gap problem is “just measure the scalar glueball mass.” Lattice calculations provide powerful nonperturbative evidence and precise continuum-extrapolated results within the lattice framework. The Clay-style mathematical problem asks for a construction of four-dimensional quantum Yang–Mills theory satisfying the axioms and having a provable mass gap. That is a different standard.

The bridge is still important. Glueball correlators are the practical observables through which a gap is seen:

$$
\langle \mathcal O(x)\mathcal O(0)\rangle_c
\sim e^{-m_{\rm lightest}|x|}
$$

at large Euclidean separation, up to powers and channel details. If all connected gauge-invariant correlators have exponential decay with a common lowest scale, the theory is behaving as a gapped theory.

## Pure gauge theory versus full QCD

Pure Yang–Mills glueballs are conceptually sharp. Full QCD glueballs are not. The reason is simple: once dynamical quarks are present, any state with the same exact quantum numbers can mix.

For example, in the scalar-isoscalar channel, the following operators can overlap with the same physical finite-volume levels:

$$
\operatorname{tr}F_{\mu\nu}F_{\mu\nu},
\qquad
\bar q q,
\qquad
(\pi\pi)_{I=0},
\qquad
(K\bar K)_{I=0},
\qquad
\ldots .
$$

The physical states are eigenstates of the full Hamiltonian, not eigenstates of “gluon number.” Therefore a realistic glueball search is a mixing problem. One asks whether a state has unusually large overlap with gluonic operators, whether its mass and decay pattern fit lattice and large-$N$ expectations, and whether alternative quarkonium or molecular interpretations are disfavored.

This is why statements like “the scalar glueball is $f_0(1710)$” or “the pseudoscalar glueball is such-and-such resonance” should be treated carefully unless the evidence and assumptions are spelled out. The correct modern language is not a single constituent label; it is an operator-overlap and scattering-analysis problem.

## Large-N perspective

Large-$N$ counting makes glueballs cleaner. In the ’t Hooft limit,

$$
N_c\to\infty,
\qquad
\lambda=g^2N_c\text{ fixed},
$$

connected correlators of single-trace gluonic operators factorize. After appropriate normalization, glueball interactions are suppressed by powers of $1/N_c$. In this sense glueballs become narrow, weakly interacting particles at large $N_c$.

A schematic version of the counting is:

| Object | Large-$N_c$ behavior |
|---|---|
| Glueball masses | $O(N_c^0)$ |
| Glueball decay amplitudes | suppressed by powers of $1/N_c$ |
| Glueball widths | vanish as $N_c\to\infty$ |
| Glueball–meson mixing | suppressed in the standard ’t Hooft limit |
| Pure-glue vacuum energy | $O(N_c^2)$ |

This explains why glueball language is especially natural in pure Yang–Mills theory and in large-$N_c$ QCD. It does not make $N_c=3$ trivial. Scalar and pseudoscalar flavor-singlet channels can have substantial mixing and broad resonances, so large-$N_c$ intuition must be combined with actual spectral analysis.

## Closed flux tubes and glueball intuition

One common picture says that an open confining flux tube connects a heavy quark and antiquark, while a glueball is a closed flux tube. This is useful, but only if it is not taken too literally.

It is useful because:

- confinement suggests string-like color-electric flux tubes;
- closed loops of flux can carry glueball quantum numbers;
- large-$N_c$ counting resembles a string loop expansion;
- highly excited glueballs may organize approximately along stringy or Regge-like patterns.

It is dangerous because:

- the lightest glueballs are small and highly quantum;
- local gluonic operators, not literal classical loops, define the states;
- closed-string models are effective descriptions, not derivations of four-dimensional Yang–Mills;
- full QCD adds quarkonium and multi-meson mixing.

The next page, [QCD String Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-string-preview/), develops the flux-tube and effective-string side of this picture.

## Practical diagnostics

A good glueball analysis usually checks several things at once.

| Diagnostic | Why it matters |
|---|---|
| Gauge invariance | Physical glueball operators must be color singlets. |
| Quantum numbers | Operators must be projected into definite lattice or continuum symmetry channels. |
| Vacuum subtraction | Scalar channels require connected correlators. |
| Operator basis | Extended, smeared, and variational operators improve overlap and excited-state resolution. |
| Continuum limit | Lattice cubic irreps must recombine into continuum spin multiplets. |
| Finite-volume control | Multi-particle thresholds and volume dependence distinguish stable particles from scattering states. |
| Unquenching | Dynamical quarks introduce mixing and decays absent in pure Yang–Mills theory. |

A single mass estimate from one operator is therefore not a modern glueball calculation. It is, at best, a first diagnostic.

## Common pitfalls

**Calling glueballs “two-gluon bound states.”** That language imports a weak-coupling constituent picture into a confining theory. Glueballs are defined by gauge-invariant correlators, not by counting free gluons.

**Confusing pure Yang–Mills glueballs with full QCD resonances.** Pure glueballs are clean theoretical states. Real-world scalar and pseudoscalar resonances mix with quarkonium and multi-hadron states.

**Ignoring the vacuum subtraction in the scalar channel.** The operator $\operatorname{tr}F^2$ has vacuum quantum numbers and can have a nonzero vacuum expectation value. The connected correlator is the object that decays with the scalar glueball spectrum.

**Treating lattice cubic spin labels as continuum spin.** At finite lattice spacing, rotational symmetry is reduced. Continuum spin is inferred only after studying degeneracies and continuum extrapolation.

**Using glueball masses as a proof of the Yang–Mills mass gap.** They are compelling nonperturbative evidence and essential data, but theorem-level existence and mass-gap statements require a different mathematical construction.

**Overreading large-$N_c$ intuition at $N_c=3$.** Large-$N_c$ explains why glueballs can be narrow and weakly mixed in a limit. It does not remove the need for real-world mixing analysis.

## Research status

Pure Yang–Mills glueball spectroscopy is an established nonperturbative subject, especially on the lattice. The existence of a gapped color-singlet spectrum in numerical pure-gauge simulations is not controversial physics.

The frontier lies in precision and interpretation: continuum extrapolations for several gauge groups, excited states, large-$N_c$ trends, finite-volume systematics, anisotropic lattices, operator-basis optimization, and especially unquenched QCD where glueball operators mix with quarkonium and multi-hadron channels. Experimentally, glueball hunting remains subtle because the relevant resonances are flavor singlets with strong mixing and often significant widths.

## Exercises

### Exercise 1: Why subtract the vacuum in the scalar channel?

Let $\mathcal O=\operatorname{tr}F_{\mu\nu}F_{\mu\nu}$ have $\langle\mathcal O\rangle\ne0$. Show that the unsubtracted correlator contains a constant term and explain why the connected correlator is needed to extract a mass.

<details>
<summary><strong>Solution</strong></summary>

Insert the identity by writing

$$
\langle\mathcal O(t)\mathcal O(0)\rangle
=\langle\mathcal O\rangle^2+
\left[\langle\mathcal O(t)\mathcal O(0)\rangle-\langle\mathcal O\rangle^2\right].
$$

The first term is constant in Euclidean time and comes from the vacuum intermediate state. The connected correlator

$$
C(t)=\langle\mathcal O(t)\mathcal O(0)\rangle_c
$$

removes this vacuum piece. Its large-$t$ decay is governed by the lightest non-vacuum state with $0^{++}$ quantum numbers, so it can be used to extract the scalar glueball mass.

</details>

### Exercise 2: Gauge invariance of a local glueball operator

Under a gauge transformation, $F_{\mu\nu}\to UF_{\mu\nu}U^{-1}$. Show that $\operatorname{tr}F_{\mu\nu}F_{\mu\nu}$ is gauge invariant.

<details>
<summary><strong>Solution</strong></summary>

The transformed operator is

$$
\operatorname{tr}\left(UF_{\mu\nu}U^{-1}UF_{\mu\nu}U^{-1}\right)
=\operatorname{tr}\left(UF_{\mu\nu}F_{\mu\nu}U^{-1}\right).
$$

Using cyclicity of the trace,

$$
\operatorname{tr}\left(UF_{\mu\nu}F_{\mu\nu}U^{-1}\right)
=\operatorname{tr}\left(F_{\mu\nu}F_{\mu\nu}U^{-1}U\right)
=\operatorname{tr}F_{\mu\nu}F_{\mu\nu}.
$$

Thus the operator is gauge invariant.

</details>

### Exercise 3: Large-N width scaling

Suppose a glueball decay amplitude scales as $\mathcal A(G\to GG)\sim 1/N_c$. What is the scaling of the width at fixed kinematics?

<details>
<summary><strong>Solution</strong></summary>

At fixed kinematics, the width is proportional to the squared amplitude times phase space:

$$
\Gamma\propto |\mathcal A|^2.
$$

If $\mathcal A\sim 1/N_c$, then

$$
\Gamma\sim \frac{1}{N_c^2}.
$$

Thus glueballs become narrow at large $N_c$ in the standard large-$N_c$ counting.

</details>

### Exercise 4: Why glueball labels are not exact in full QCD

Explain why a scalar gluonic operator and a scalar quark bilinear can overlap with the same physical state in full QCD.

<details>
<summary><strong>Solution</strong></summary>

The Hamiltonian eigenstates are classified by exact symmetries, not by the schematic field content of an interpolating operator. Both

$$
\operatorname{tr}F_{\mu\nu}F_{\mu\nu}
\qquad\text{and}\qquad
\bar q q
$$

can have $I=0$ and $J^{PC}=0^{++}$. If no exact symmetry forbids mixing, both operators can have nonzero matrix elements to the same physical eigenstate:

$$
\langle0|\operatorname{tr}F^2|n\rangle\ne0,
\qquad
\langle0|\bar q q|n\rangle\ne0.
$$

Therefore “glueball” in full QCD is a statement about operator overlaps, mixing patterns, and dynamics, not an exact conserved label.

</details>

## Relations to other pages

This page follows [Hadron Spectrum](/nonperturbative-qft/strongly-coupled-gauge-theories/hadron-spectrum/) and specializes the spectral method to gluonic operators. It connects directly to [Mass Gap in Gauge Theory](/nonperturbative-qft/confinement-screening-mass-gap/mass-gap/) and [Yang–Mills Mass Gap Problem](/nonperturbative-qft/confinement-screening-mass-gap/yang-mills-mass-gap-problem/), where the lightest pure-gauge excitation is the practical signal of a gap.

Continue to [QCD String Preview](/nonperturbative-qft/strongly-coupled-gauge-theories/qcd-string-preview/) for the flux-tube and effective-string picture, and later to Large-N Methods for the systematic large-$N_c$ counting behind narrow glueballs and topological string-like expansions.

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, especially the chapters on Wilson loops, lattice theory, confinement, solitons, monopoles, instantons, and theta vacua.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on Yang–Mills theory, lattice gauge theory, QCD, spectral decomposition, and resonances.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the discussion of phases of gauge theories, glueballs as pure-gauge excitations, large-$N$, and confinement.

### Deeper references

- S. Coleman, *Aspects of Symmetry*, especially the large-$N$ lectures for meson, glueball, and mixing counting.
- M. Mariño, *Instantons and Large N*, especially the large-$N$ QCD chapter and glueball/meson correlator counting.
- A. M. Polyakov, *Gauge Fields and Strings*, for strong coupling, loops, confinement, and string-like intuition.
- C. Morningstar and M. Peardon, “The glueball spectrum from an anisotropic lattice study,” *Physical Review D* **60** (1999), for a classic lattice glueball spectrum calculation.
- H. B. Meyer, C. Morningstar, Y. Chen et al., and later lattice reviews, for continuum-extrapolated glueball spectroscopy and operator-basis methods.
- Particle Data Group reviews and recent glueball reviews for the current experimental and phenomenological status of glueball candidates.

## Version history

- **2026-06-27:** Initial polished draft, added after Hadron Spectrum in the Strongly Coupled Gauge Theories chapter.
