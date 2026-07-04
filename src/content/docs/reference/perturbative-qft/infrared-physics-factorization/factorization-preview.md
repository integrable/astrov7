---
title: "Factorization Preview"
description: "A first map of infrared factorization: how hard, collinear, and soft physics separate in perturbative QFT observables with multiple scales."
sidebar:
  label: "Factorization Preview"
  order: 9
level: Graduate
status: "Polished draft"
source: "Collins–Soper–Sterman; Sterman on QCD factorization; Catani–Seymour; Bauer–Fleming–Luke–Pirjol–Stewart on SCET; Schwartz chs. 20, 32, and 36"
topics:
  - infrared factorization
  - hard functions
  - jet functions
  - soft functions
  - parton distribution functions
  - effective field theory
canonicalTopics:
  - infrared-factorization
  - hard-jet-soft-factorization
  - factorization-theorems
  - scet-preview
researchStatus:
  established:
    - "Factorization theorems for many inclusive and sufficiently infrared-safe observables separate short-distance coefficients from long-distance universal functions, up to specified power corrections."
  active:
    - "Factorization in the presence of Glauber exchange, non-global measurements, small-x dynamics, jet substructure, multi-scale observables, and power corrections remains an active research area."
---

## Summary

**Factorization** is the statement that a physical observable with well-separated scales can often be written as a product or convolution of simpler objects, each sensitive to only one class of modes. In perturbative QCD the basic separation is

$$
\text{hard short-distance physics}
\quad\times\quad
\text{collinear jet physics}
\quad\times\quad
\text{soft wide-angle physics}
\quad\times\quad
\text{hadronic long-distance input, if needed}.
$$

A schematic factorization formula for an infrared-sensitive but infrared-safe observable is

$$
\sigma[V]
=
H(Q,\mu)
\otimes
J_1(\mu)
\otimes\cdots\otimes
J_N(\mu)
\otimes
S(\mu)
+
\text{power corrections}.
$$

The hard function $H$ knows about virtual momenta of order the hard scale $Q$. The jet functions $J_i$ know about energetic radiation collinear to hard directions. The soft function $S$ knows about low-energy radiation exchanged among those directions. The symbol $\otimes$ means that the factors may be convoluted over momentum fractions, invariant masses, energies, angles, or other measurement variables.

This page is a preview. It explains the logic and anatomy of factorization, not a full proof. The full story requires careful definitions of observables, regulators, Wilson lines, Glauber regions, parton distributions, rapidity logarithms, and effective field theory.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![A hard scattering factorizes into short-distance hard physics, collinear jet functions, and a soft function linking the energetic directions](/figures/perturbative-qft/factorization-preview.svg)

<figcaption>

Factorization separates momentum regions. The hard interaction is localized at scale $Q^{-1}$. Each energetic direction produces a collinear jet function. Soft radiation has long wavelength and couples coherently to the directions through Wilson lines. The pieces are not separately physical in every convention; their product or convolution gives the observable up to controlled power corrections.

</figcaption>
</figure>

## Prerequisites

You should know [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/), [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/), [KLN Theorem](/perturbative-qft/infrared-physics-factorization/kln-theorem/), [Eikonal Approximation](/perturbative-qft/infrared-physics-factorization/eikonal-approximation/), [Soft Gluon Theorem](/perturbative-qft/infrared-physics-factorization/soft-gluon-theorem/), and [Jets and Inclusive Observables](/perturbative-qft/infrared-physics-factorization/jets-and-inclusive-observables/).

For the perturbative ingredients, review [Loop Expansion](/perturbative-qft/loop-expansion-regularization/loop-expansion/), [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/), and [Color Factors](/perturbative-qft/gauge-theory-perturbation-theory/color-factors/).

## Core idea

A high-energy event often contains several physically distinct scales. For example, in an event with narrow jets,

$$
Q \gg m_J \gg E_s,
$$

where $Q$ is the hard collision energy, $m_J$ is a typical jet invariant mass, and $E_s$ is a typical soft energy. A fixed-order diagram contains all momentum regions at once. Factorization rewrites the answer so that each region is isolated into its own object.

This is possible because long-wavelength radiation cannot resolve short-distance details. A soft gluon sees each energetic particle as an approximately classical color source moving along a lightlike or nearly lightlike direction. Collinear radiation sees the energetic direction and its nearby splittings, but not the full hard scattering. Hard virtual fluctuations see the short-distance collision, but not late-time fragmentation.

The resulting separation is not just aesthetic. It does three jobs:

| Job | Why it matters |
|---|---|
| Separates scales | Each factor can be evaluated or modeled at its natural scale. |
| Organizes logarithms | Large logarithms of scale ratios can be resummed by evolving factors between scales. |
| Isolates universality | Some long-distance factors, such as PDFs, fragmentation functions, jet functions, and soft functions, recur in many observables. |

Factorization is therefore the bridge from formal infrared theorems to practical QCD predictions.

## Setup and conventions

Consider an observable depending on a hard scale $Q$ and a smaller scale $q\ll Q$. The small parameter is often

$$
\lambda\sim \frac{q}{Q}
$$

or a square root of an event-shape variable. Factorization is an expansion in powers of $\lambda$. The leading-power formula captures the most singular terms as $\lambda\to0$; subleading-power factorization describes corrections suppressed by powers of $q/Q$.

A factorization formula has three layers:

1. **Mode content.** Which momentum regions contribute at leading power?
2. **Operator definition.** Which matrix elements define the hard, jet, soft, beam, or fragmentation functions?
3. **Matching and evolution.** How are the pieces computed, renormalized, and combined without double counting?

The formula is meaningful only after these choices are specified. The same physical observable can have different-looking factorization formulas in different schemes or effective-theory conventions, but physical predictions agree after all ingredients are combined.

## Momentum regions

The most common regions in high-energy QCD are hard, collinear, and soft.

A hard momentum has all components of order $Q$:

$$
p_h^\mu\sim Q(1,1,1).
$$

For a jet along a lightlike direction $n^\mu$, introduce another lightlike vector $\bar n^\mu$ with $n\cdot\bar n=2$. A momentum decomposes as

$$
p^\mu
=
\frac{\bar n\cdot p}{2}n^\mu
+
\frac{n\cdot p}{2}\bar n^\mu
+
p_\perp^\mu.
$$

An $n$-collinear momentum has hierarchical components,

$$
(\bar n\cdot p_c,\;p_{c\perp},\;n\cdot p_c)
\sim
Q(1,\lambda,\lambda^2),
$$

so that

$$
p_c^2\sim Q^2\lambda^2.
$$

A soft momentum has uniformly small components. Depending on the observable, one may encounter soft scaling

$$
p_s^\mu\sim Q(\lambda,\lambda,\lambda)
$$

or ultrasoft scaling

$$
p_{us}^\mu\sim Q(\lambda^2,\lambda^2,\lambda^2).
$$

The exact scaling is not universal. It is determined by the measurement. That is why factorization is an observable-by-observable statement, not a single theorem that automatically covers everything with jets.

## Anatomy of a factorized observable

A typical leading-power factorization formula has the structure

$$
\frac{d\sigma}{dV}
=
H(Q,\mu)
\int d\omega\,d\ell_1\cdots d\ell_N\,
S(\omega,\mu)
\prod_{i=1}^N J_i(\ell_i,\mu)
\,\delta\!\left(V-\widehat V(\omega,\ell_1,\ldots,\ell_N)\right)
+
O\!\left(\frac{q}{Q}\right).
$$

The hard function $H$ is usually the square of a short-distance matching coefficient. It is computed from virtual corrections with infrared behavior subtracted or matched away.

A jet function $J_i$ describes collinear radiation along direction $i$. In simple final-state cases it can be defined as a discontinuity of a gauge-invariant collinear two-point function. In practical terms, it describes how invariant mass, energy flow, or a similar measurement is distributed inside a jet.

The soft function $S$ is a matrix element of Wilson lines. It describes soft radiation exchanged among the energetic directions. It often carries nontrivial color correlations because soft gluons can connect different jets.

The measurement function $\widehat V$ tells the factorized ingredients how to reconstruct the observed quantity. Without the measurement, the words “hard,” “jet,” and “soft” are too vague to determine the convolution.

## Wilson lines and eikonalization

Soft factorization is built on the eikonal approximation. A soft gluon emitted from a hard particle with momentum $p_i$ produces the leading factor

$$
g_s\,\mathbf T_i^a\frac{p_i^\mu}{p_i\cdot k}.
$$

Multiple soft emissions exponentiate into Wilson lines along the hard directions. A lightlike Wilson line in representation $R_i$ has the schematic form

$$
Y_{n_i}(x)
=
P\exp\!\left[
ig_s\int_0^\infty ds\,n_i\cdot A^a(x+s n_i)T^a_{R_i}
\right].
$$

The soft function for an $N$-jet observable is then built from a vacuum matrix element of such Wilson lines, with an insertion of the measurement operator:

$$
S(\omega,\mu)
\sim
\langle0|\,
Y_{n_1}\cdots Y_{n_N}\,
\delta(\omega-\widehat\omega)
\,Y_{n_N}^\dagger\cdots Y_{n_1}^\dagger
|0\rangle.
$$

This formula is schematic because color indices, time ordering, incoming versus outgoing directions, regulators, and the precise measurement matter. The main lesson is robust: soft physics is encoded by Wilson lines, not by the detailed hard scattering.

## Collinear factorization

Collinear singularities arise when massless particles split at small angle. In a final-state jet, collinear radiation is part of the measured jet. In an initial-state hadron collision, collinear radiation from the incoming hadron is not perturbatively calculable from first principles at low scales and is absorbed into parton distribution functions.

A hadron-collider factorization formula has the schematic form

$$
d\sigma(h_1h_2\to X)
=
\sum_{a,b}
\int_0^1 dx_1\,dx_2\,
f_{a/h_1}(x_1,\mu)
f_{b/h_2}(x_2,\mu)
d\widehat\sigma_{ab\to X}(x_1p_1,x_2p_2,\mu)
+
\text{power corrections}.
$$

The partonic cross section $d\widehat\sigma$ is perturbatively calculable. The PDFs $f_{a/h}(x,\mu)$ are universal nonperturbative inputs that evolve with $\mu$.

For less inclusive observables, the partonic cross section itself may further factorize into hard, beam, jet, and soft functions:

$$
d\widehat\sigma
\sim
H\otimes B_1\otimes B_2\otimes J_1\otimes\cdots\otimes J_N\otimes S.
$$

Here beam functions describe collinear radiation tied to the incoming directions when the measurement is more differential than ordinary inclusive PDF factorization.

## Example: two-jet event shapes

For $e^+e^-$ annihilation into two narrow jets, event shapes such as thrust probe a hierarchy of scales. Define

$$
\tau=1-T,
$$

where $T$ is thrust. The two-jet limit is $\tau\ll1$. The relevant scales are roughly

$$
\mu_H\sim Q,
\qquad
\mu_J\sim Q\sqrt{\tau},
\qquad
\mu_S\sim Q\tau.
$$

A schematic leading-power factorization formula is

$$
\frac{d\sigma}{d\tau}
=
H(Q,\mu)
\int ds_n\,ds_{\bar n}\,dk\,
J_n(s_n,\mu)J_{\bar n}(s_{\bar n},\mu)S(k,\mu)
\delta\!\left(\tau-\frac{s_n+s_{\bar n}}{Q^2}-\frac{k}{Q}\right)
+
O(\tau).
$$

The hard function describes the production of a short-distance quark-antiquark pair. The jet functions describe collinear invariant masses in the two hemispheres. The soft function describes low-energy radiation crossing the event at wide angles.

This formula explains why large logarithms appear in the two-jet limit. If all factors are evaluated at a common scale $\mu$, at least some of them contain logarithms of ratios such as $Q/(Q\tau)$ or $Q/(Q\sqrt{\tau})$. Resummation evolves each factor from its natural scale to a common scale.

## Factorization is not automatic

The KLN theorem says that sufficiently inclusive sums over degenerate states have infrared-finite predictions. It does not by itself provide a factorized formula. Factorization requires more: it requires that the long-distance sensitivity can be absorbed into universal objects whose definitions do not depend on the microscopic hard process except through charges, directions, and representations.

Several obstructions or complications can appear.

**Glauber exchange** involves momentum regions with small energy transfer but transverse momentum exchange. Such modes can cancel for many inclusive observables but can obstruct simple factorization in less inclusive settings.

**Non-global measurements** observe radiation in part of phase space while being inclusive elsewhere. Their soft radiation is correlated in a way that produces non-global logarithms not captured by the simplest independent-jet picture.

**Rapidity divergences** appear when soft and collinear modes have the same invariant mass but different rapidities. They require additional regulators and rapidity renormalization group equations.

**Power corrections** become important when the supposedly small parameter is not very small, or when hadronization enters with enhanced sensitivity.

**Color entanglement** can make the soft function a matrix in color space rather than a scalar function.

These complications are not defects of factorization. They are where factorization becomes interesting instead of cartoonish.

## Effective-theory viewpoint

Soft-collinear effective theory, or SCET, is a systematic language for deriving many factorization formulas. Its logic is:

```txt
full QCD at scale Q
  → match onto hard operators built from collinear fields in fixed directions
  → decouple leading soft interactions into Wilson lines
  → define jet, beam, and soft matrix elements
  → use RG evolution to resum logarithms.
```

In this language the hard function comes from matching full QCD onto effective operators. Jet and beam functions are collinear matrix elements. Soft functions are Wilson-line matrix elements. Power corrections come from subleading operators and subleading Lagrangian insertions.

The effective theory is not required to use factorization, but it makes the assumptions, degrees of freedom, and power counting explicit. It also provides a clean path from factorization to resummation.

## What is universal?

“Universal” does not mean “the same number in every process.” It means “the same operator or function appears across a class of processes.”

Examples include:

| Object | Kind of universality |
|---|---|
| PDFs | Same hadron structure in many hard processes. |
| Fragmentation functions | Same identified-hadron formation functions in many processes. |
| Cusp anomalous dimension | Controls many Sudakov double logarithms. |
| Eikonal Wilson lines | Same soft approximation for long-wavelength gauge radiation. |
| Splitting functions | Same collinear limits governing DGLAP evolution. |
| Jet functions | Same collinear dynamics for specified jet measurements. |

The hard function is usually not universal. It remembers the short-distance process. Factorization is powerful precisely because it confines process-specific information to hard coefficients while reusing long-distance or infrared-sensitive structures.

## Common pitfalls

**Thinking factorization means ordinary multiplication.** Many factorization formulas involve convolutions, matrices in color space, distributions, and scale-dependent renormalized functions.

**Calling every split into pieces a theorem.** A factorization theorem has assumptions, a power counting, operator definitions, and a proof or derivation. A diagrammatic sketch is not yet a theorem.

**Forgetting the measurement.** The observable decides which soft and collinear modes matter and how their momenta are convoluted.

**Treating individual factors as observables.** Hard, jet, soft, and beam functions can be scheme-dependent, regulator-dependent, or gauge-dependent before they are combined into a physical prediction.

**Ignoring power corrections.** Leading-power factorization is not the whole answer. Corrections suppressed by $q/Q$ can be numerically important.

**Confusing factorization with hadronization.** Factorization separates perturbative short-distance physics from long-distance input. It does not magically compute all nonperturbative hadron formation from perturbation theory.

## Relations to other pages

- [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/) and [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/) identify the singular limits factorization organizes.
- [Eikonal Approximation](/perturbative-qft/infrared-physics-factorization/eikonal-approximation/) explains the external-line approximation behind Wilson-line soft functions.
- [Soft Gluon Theorem](/perturbative-qft/infrared-physics-factorization/soft-gluon-theorem/) gives the leading soft building block in non-Abelian gauge theory.
- [Jets and Inclusive Observables](/perturbative-qft/infrared-physics-factorization/jets-and-inclusive-observables/) explains the measurement side of infrared safety.
- [Resummation Preview](/perturbative-qft/infrared-physics-factorization/resummation-preview/) uses factorization formulas to sum logarithms of scale ratios.
- [Callan–Symanzik Preview](/perturbative-qft/renormalized-perturbation-theory/callan-symanzik-preview/) gives the basic RG logic that reappears in factorized predictions.

## Research status

**Established:** Leading-power factorization is standard for many important classes of observables, including sufficiently inclusive hard scattering, deep-inelastic scattering, Drell–Yan production, many event shapes, and many jet observables. PDFs, hard functions, jet functions, and soft Wilson-line matrix elements are central to modern perturbative QCD.

**Active:** Many realistic observables require refinements: rapidity factorization, Glauber modes, non-global logarithms, jet grooming, transverse-momentum dependence, multi-jet color correlations, subleading-power factorization, hadronization corrections, and heavy-flavor mass effects.

**Speculative:** Factorization-inspired language is sometimes used outside its proven range. Such uses can be illuminating, but the status should be labeled carefully: analogy, conjecture, effective model, or theorem.

## Exercises

### Exercise 1: Identify the scales in a two-jet event shape

In $e^+e^-$ annihilation at center-of-mass energy $Q$, consider the two-jet region of thrust, $\tau=1-T\ll1$. The jet invariant masses scale like $m_J^2\sim Q^2\tau$, and soft radiation contributes energy $E_s\sim Q\tau$.

Find the natural hard, jet, and soft scales.

<details>
<summary><strong>Solution</strong></summary>

The hard scale is the short-distance collision energy,

$$
\mu_H\sim Q.
$$

The jet scale is set by the invariant mass of collinear radiation,

$$
\mu_J\sim m_J\sim Q\sqrt{\tau}.
$$

The soft scale is set by the soft energy contribution to the event shape,

$$
\mu_S\sim E_s\sim Q\tau.
$$

Thus the two-jet limit creates the hierarchy

$$
Q\gg Q\sqrt{\tau}\gg Q\tau.
$$

This hierarchy is the source of large logarithms in fixed-order perturbation theory.

</details>

### Exercise 2: RG consistency of a factorized product

Suppose a simple factorized observable has the form

$$
\sigma=H(Q,\mu)J(\mu)S(\mu),
$$

where

$$
\mu\frac{dH}{d\mu}=\gamma_H H,
\qquad
\mu\frac{dJ}{d\mu}=\gamma_J J,
\qquad
\mu\frac{dS}{d\mu}=\gamma_S S.
$$

What condition must the anomalous dimensions satisfy for $\sigma$ to be independent of $\mu$?

<details>
<summary><strong>Solution</strong></summary>

Differentiate the product:

$$
\mu\frac{d\sigma}{d\mu}
=
(\gamma_H+\gamma_J+\gamma_S)HJS.
$$

A physical observable cannot depend on the arbitrary renormalization scale, so at the accuracy where the factorization formula is valid we need

$$
\gamma_H+\gamma_J+\gamma_S=0.
$$

For realistic formulas with convolutions or color matrices, this condition becomes a convolution or matrix equation. The meaning is the same: the scale dependence of the factors cancels in the physical prediction.

</details>

### Exercise 3: Soft Wilson-line origin

Use the leading eikonal factor

$$
g_s\mathbf T_i^a\frac{p_i^\mu}{p_i\cdot k}
$$

to explain why the soft function depends on the directions and color representations of hard particles rather than on the detailed hard scattering amplitude.

<details>
<summary><strong>Solution</strong></summary>

In the soft limit, the emitted gluon momentum $k$ is much smaller than the hard momenta. The leading denominator from emission off leg $i$ is $2p_i\cdot k$, and the numerator reduces to a factor proportional to $p_i^\mu$. The only information retained about the hard leg is therefore its direction, momentum normalization through $p_i\cdot k$, and color generator $\mathbf T_i^a$.

Multiple soft emissions repeat this same eikonal coupling and organize into a Wilson line along the direction of the hard particle. The detailed short-distance amplitude determines the hard function and color state, but the soft radiation itself couples through Wilson lines.

</details>

### Exercise 4: Why the measurement matters

Explain why the same hard process can have different soft functions for two different event shapes.

<details>
<summary><strong>Solution</strong></summary>

The soft function contains an operator that measures soft radiation. Different event shapes weight soft momenta differently: one observable may measure hemisphere energy, another may measure transverse momentum, angularities, or energy flow in only part of phase space.

Even if the Wilson-line directions and color representations are the same, the measurement insertion changes the matrix element. Therefore the soft function is observable-dependent. Universality applies only within a class of observables sharing the same operator definition or related limiting behavior.

</details>

### Exercise 5: Leading power versus power corrections

A factorization formula is derived at leading power in $\lambda=q/Q$. If $\lambda=0.1$, estimate the expected size of first power corrections before considering numerical coefficients. Why might the actual correction be larger or smaller?

<details>
<summary><strong>Solution</strong></summary>

A first power correction scales like

$$
O(\lambda)=O(0.1),
$$

so a naive estimate is a ten percent correction. The actual correction may be smaller if its coefficient is numerically small, if it is symmetry-suppressed, or if it first appears at higher power. It may be larger if the coefficient is large, if logarithms enhance it, if the observable is unusually sensitive to hadronization, or if the hierarchy is not clean in the measured region.

</details>

## References

- J. C. Collins, *Foundations of Perturbative QCD*, for systematic factorization, PDFs, transverse-momentum dependence, and proofs.
- G. Sterman, *An Introduction to Quantum Field Theory* and writings on QCD factorization, for a clear perturbative and infrared-focused treatment.
- G. P. Korchemsky and A. V. Radyushkin, classic papers on Wilson lines, cusp anomalous dimensions, and soft factorization.
- S. Catani and M. H. Seymour, “A general algorithm for calculating jet cross sections in NLO QCD,” for subtraction and factorized singular limits.
- C. W. Bauer, S. Fleming, D. Pirjol, I. W. Stewart, and collaborators, early SCET papers, for the effective-theory formulation of hard-collinear-soft factorization.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 20, 32, and 36, for infrared divergences, jets, QCD factorization, and SCET.
- T. Becher, A. Broggio, and A. Ferroglia, *Introduction to Soft-Collinear Effective Theory*, for a compact modern SCET treatment.

## Version history

- **2026-06-13:** Initial page. Gives the leading-power anatomy of infrared factorization, with a two-jet event-shape example and explicit warnings about measurements, power corrections, and factorization status.
