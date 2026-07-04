---
title: "Perimeter Law and Screening"
description: "Explains how perimeter laws, dynamical screening, string breaking, and one-form symmetry refine Wilson-loop confinement diagnostics."
sidebar:
  label: "Perimeter Law and Screening"
  order: 2
level: Advanced
status: "Polished draft"
source: "Wilson; Srednicki ch. 82; Shifman ch. 1; Fradkin–Shenker; Gaiotto–Kapustin–Seiberg–Willett."
topics:
  - perimeter law
  - screening
  - string breaking
  - Wilson loops
  - dynamical matter
  - one-form symmetry
  - Higgs–confinement continuity
canonicalTopics:
  - nonperturbative-qft
  - confinement
  - screening
  - wilson-loops
  - one-form-symmetry
researchStatus:
  established:
    - "Perimeter-law behavior is the standard large-loop signal that the corresponding probe charge is not attached to an asymptotically stable confining string."
  active:
    - "In gauge theories with dynamical matter, the physical phrase confinement can remain useful even when Wilson’s strict asymptotic area-law criterion is absent."
---

## Summary

A Wilson-loop **perimeter law** has the schematic large-loop form

$$
\langle W_R(C)\rangle_{\rm ren}
\sim \exp[-\mu_R P(C)]
$$

rather than an area law

$$
\langle W_R(C)\rangle_{\rm ren}
\sim \exp[-\sigma_R A(C)].
$$

After local line renormalization, a perimeter-law loop has no infrared cost proportional to the area enclosed by the loop. In a rectangular-loop extraction, this means the corresponding static probe charges do not have an asymptotically linear potential.

The most important physical source of a perimeter law is **screening**. If the theory contains dynamical fields with the right charge, the vacuum can create particles that neutralize the external probes. The flux tube can then break, and the static energy saturates instead of growing like $\sigma r$ forever.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A schematic comparison of area-law confinement with perimeter-law screening and the corresponding static-potential crossover.](/figures/nonperturbative-qft/perimeter-law-screening-crossover.svg)

<figcaption>

A confining area-law channel fills the loop with a surface and gives $V(r)\sim \sigma r$. A screening channel lives near the worldlines of the external sources and scales like the perimeter. If dynamical matter can screen the probes, the static energy crosses over from an approximately linear regime to a broken-string plateau.

</figcaption>
</figure>

The perimeter law is not a synonym for “trivial.” It can mean a Coulomb phase, a Higgs phase, a deconfined topological phase, or merely the absence of a sharp Wilson-loop order parameter because the relevant one-form symmetry is explicitly broken by matter.

## Prerequisites

You should know [What Is Confinement?](/nonperturbative-qft/confinement-screening-mass-gap/what-is-confinement/), [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/), and [Wilson-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/wilson-loop-diagnostics/).

The page also uses the language of [Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/), [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/), and [Defects Versus Operators](/nonperturbative-qft/solitons-defects-extended-configurations/defects-versus-operators/). The one-form symmetry interpretation will be developed further later in this chapter.

## Core idea

An area law says that inserting a large Wilson loop forces the vacuum to pay a cost proportional to a two-dimensional sheet. A perimeter law says that the dominant cost is localized near the one-dimensional line operator itself.

For a scaled family of smooth loops $C_\lambda$, with all lengths multiplied by $\lambda$,

$$
P(C_\lambda)\sim \lambda,
\qquad
A(C_\lambda)\sim \lambda^2.
$$

Thus the two laws have parametrically different infrared scaling:

$$
-\log \langle W(C_\lambda)\rangle
\sim
\begin{cases}
\mu \lambda, & \text{perimeter law},\\
\sigma \lambda^2, & \text{area law}.
\end{cases}
$$

The physics question is: **Why is the sheet absent?** There are several answers.

In a Coulomb phase, the electric field spreads rather than forming a tube. In a Higgs phase, external electric flux is screened by the condensate. In a topologically ordered discrete gauge phase, loop laws depend on which electric or magnetic line is being probed. In full QCD-like theories with light fundamental matter, a string may form at intermediate distances but break at large distances.

Those mechanisms are different. The common diagnostic is that the relevant probe is not tied to a stable long string at arbitrarily large separation.

## Perimeter law as a loop asymptotic

A general large-loop expansion has the form

$$
-\log \langle W_R(C)\rangle
=
\mu_R P(C)+\sigma_R A(C)+\gamma_R(C)+\cdots.
$$

Here $P(C)$ is the loop perimeter, $A(C)$ is the appropriate large-area scale, and $\gamma_R(C)$ includes terms such as cusp contributions, logarithms, shape-dependent finite pieces, and topological data. The word “perimeter law” usually means that the infrared area coefficient vanishes in the channel being probed:

$$
\sigma_R=0.
$$

The coefficient $\mu_R$ is subtle. In a continuum definition of the Wilson loop it includes line self-energy divergences, so it is not by itself a universal infrared observable. A perimeter divergence can appear even in a free photon theory. Therefore the robust distinction is not whether $\mu_R$ is nonzero, but whether a nonzero $\sigma_R$ remains after the line operator is properly defined.

For a rectangular loop $C_{r,\mathcal T}$,

$$
\langle W_R(C_{r,\mathcal T})\rangle
\sim e^{-\mathcal T V_R(r)}
$$

at large Euclidean time. A perimeter law gives, at most,

$$
-\log\langle W_R(C_{r,\mathcal T})\rangle
\sim \mu_R(2r+2\mathcal T)+\cdots,
$$

so

$$
V_R(r)
=
2\mu_R+\lim_{\mathcal T\to\infty}\frac{2\mu_R r}{\mathcal T}+\cdots
=2\mu_R+\cdots.
$$

The $2\mu_R$ term is an additive static-source self-energy. It can be shifted by line renormalization. A true asymptotic string tension would instead appear as a term $\sigma_R r$ in $V_R(r)$.

## Screening in the static potential

Screening means that the external probe charge can be neutralized by dynamical degrees of freedom. Suppose an external heavy source $Q$ is in a representation that can combine with a dynamical particle $\bar q$ to form a gauge singlet or a lower-energy gauge-invariant object. Then a separated $Q\bar Q$ pair can reorganize as

$$
Q\bar Q
\longrightarrow
(Q\bar q)+(q\bar Q).
$$

The energy is then not forced to grow forever with the separation $r$. A schematic static potential is

$$
V(r)\approx
\begin{cases}
\sigma r + V_0, & r\ll r_{\rm br},\\
E_{\rm screen}, & r\gg r_{\rm br},
\end{cases}
$$

where $E_{\rm screen}$ is the energy of the two screened objects and

$$
r_{\rm br}\sim \frac{E_{\rm screen}-V_0}{\sigma}
$$

is the string-breaking distance. This estimate ignores mixing and finite-width effects, but it captures the basic energetics: once the energy stored in the tube is large enough to produce the screening pair, the unbroken string is no longer the ground state.

A more faithful description uses a two-state Hamiltonian in the heavy-source sector,

$$
H(r)=
\begin{pmatrix}
V_{\rm string}(r) & \Delta(r)\\
\Delta(r) & E_{\rm screen}
\end{pmatrix},
\qquad
V_{\rm string}(r)\approx \sigma r+V_0.
$$

The physical ground-state energy is the lower eigenvalue. Instead of a sharp crossing, the system has an avoided crossing when $\Delta(r)\neq0$. Wilson loops built from simple string-like operators may have poor overlap with the broken-string state, which is one reason string breaking can be numerically delicate in lattice simulations.

## Area contribution versus perimeter contribution

Screening can be seen directly in the loop expansion. Imagine two contributions to a large rectangular Wilson loop:

$$
\langle W(C)\rangle
\sim
A_0 e^{-\sigma A(C)}+B_0 e^{-\mu P(C)}+\cdots.
$$

For small loops or intermediate distances, the area-law term may dominate if $B_0$ is small. But for uniformly scaled loops, $A\sim \lambda^2$ and $P\sim \lambda$, so the perimeter term decays much more slowly at sufficiently large $\lambda$:

$$
e^{-\mu \lambda}\gg e^{-\sigma \lambda^2}
\qquad (\lambda\to\infty).
$$

This is why arbitrarily weak dynamical screening can remove the strict asymptotic area law. The confining string may still be visible as a long-lived or intermediate-distance object, but it is not the lowest-energy state at infinite separation.

This observation also explains a common mismatch between intuition and order parameters. The flux-tube picture may be excellent over a large range of distances, while the asymptotic Wilson-loop law is nevertheless perimeter-like.

## Charge matching and partial screening

Screening depends on charge. A dynamical particle can screen only the charges it carries, together with whatever charges can be supplied by dynamical gauge fields.

In pure $SU(N)$ Yang–Mills theory, gluons transform in the adjoint representation. They can screen representation labels down to the same center charge, or **N-ality**, but cannot remove nonzero N-ality. Thus asymptotic Wilson loops in pure Yang–Mills are organized by their charge under the electric center one-form symmetry $\mathbb Z_N$.

With fundamental dynamical matter, the story changes. A fundamental matter field can end a fundamental Wilson line, so the fundamental one-form symmetry is explicitly absent. Then the fundamental Wilson loop no longer has to be an order parameter. Its asymptotic behavior can be perimeter-like because the fundamental probe charge can be screened.

A useful schematic rule is:

| Dynamical matter | Probe charge | Large-distance fate |
|---|---|---|
| only adjoint fields | nonzero N-ality | no screening by gluons; stable center string possible |
| only adjoint fields | zero N-ality | screening by gluons possible |
| fundamental matter | fundamental probe | screening and string breaking possible |
| charge-$q$ matter in Abelian theory | charge-$r$ probe | screening possible only if the charge lattice permits it |

The last line is not decorative. In compact Abelian and discrete gauge systems, the distinction between charge-$1$ and charge-$2$ probes can decide whether a given Wilson loop has an area law or a perimeter law.

## Coulomb behavior is not quite perimeter behavior

In four-dimensional Maxwell theory without dynamical charges, a large rectangular Wilson loop gives the Coulomb potential rather than a confining potential:

$$
V(r)\sim -\frac{\alpha}{r}.
$$

The Wilson loop also has a divergent perimeter contribution from the self-energy of the infinitely heavy probe. After subtracting the local line renormalization, the remaining long-distance physics is Coulombic, not purely perimeter-like:

$$
\langle W(C_{r,\mathcal T})\rangle_{\rm ren}
\sim \exp\!\left[+\frac{\alpha\mathcal T}{r}+\cdots\right]
$$

up to sign conventions for attractive versus repulsive source choices. The essential point is that $V(r)$ is not proportional to $r$.

In the one-form symmetry language, a Coulomb phase of a four-dimensional $U(1)$ gauge theory has spontaneously broken continuous one-form symmetries, and the photon is the associated Goldstone mode. That is different from a gapped Higgs or screening phase, even though none of these gives a Wilson-loop area law for the same electric probe.

## Higgs screening and confinement continuity

Gauge-Higgs systems are the place where language can get treacherous. In a gauge theory with matter in the fundamental representation, there may be no gauge-invariant order parameter sharply separating a Higgs-like region from a confinement-like region. A Wilson loop can have a perimeter law because the source is screened; local gauge-variant fields may suggest a Higgs condensate in a gauge-fixed description; yet the gauge-invariant spectrum can evolve analytically across what naive language calls two regimes.

This does not mean every Higgs phase and every confinement phase are identical. The distinction depends on global form, matter representation, line operators, and unbroken higher-form symmetries. With adjoint matter, with discrete gauge theories, or with nontrivial one-form symmetries, sharp distinctions can remain.

The safe statement is:

> A perimeter law for one Wilson loop says that this particular line is not attached to an asymptotically stable string. It does not, by itself, classify the full phase of the gauge theory.

## One-form symmetry viewpoint

When a genuine one-form global symmetry exists, loop laws become symmetry diagnostics. A line charged under an unbroken one-form symmetry has an area law. A line whose charge is screened, neutral, or associated with a broken one-form symmetry can have perimeter or Coulomb behavior.

For example, pure $SU(N)$ Yang–Mills has an electric $\mathbb Z_N$ one-form symmetry. Fundamental Wilson loops are charged under it. In the standard confining phase, they have an area law, and the one-form symmetry is unbroken.

If the theory contains fundamental matter, the electric one-form symmetry is explicitly broken: a fundamental Wilson line can end on a dynamical field. In that case there is no exact one-form symmetry whose breaking pattern could be measured by the fundamental Wilson loop.

This is the conceptual upgrade over the old slogan “area law means confinement, perimeter law means deconfinement.” The upgraded version asks:

1. Which line operator is genuine?
2. Which global one-form symmetry, if any, charges it?
3. Which dynamical objects can end it or screen it?
4. What is the asymptotic large-loop law after local renormalization?

Without these questions, the same words can describe inequivalent physics.

## Common mistakes

**Mistake 1: Calling every perimeter law deconfinement.** A perimeter law can arise from screening by dynamical matter, Higgsing, Coulomb behavior after line renormalization, or a topological deconfined phase. These are not the same.

**Mistake 2: Ignoring the representation of the probe.** A Wilson loop in a zero-N-ality representation and one in a nonzero-N-ality representation may have different asymptotic laws in the same theory.

**Mistake 3: Forgetting the order of limits.** A long intermediate linear regime does not determine the strict $r\to\infty$ limit. String breaking is precisely a large-distance effect.

**Mistake 4: Confusing absence of colored particles with Wilson’s area law.** Full QCD does not have a strict asymptotic fundamental Wilson-loop area law, but quarks and gluons still do not appear as isolated asymptotic particles.

**Mistake 5: Treating perimeter coefficients as universal observables.** Wilson loops are extended composite operators. Their perimeter terms include regularization-dependent self-energies unless a renormalization prescription has been specified.

## Research status

- **Established:** In free four-dimensional electrodynamics, Wilson loops exhibit perimeter/self-energy behavior plus Coulombic long-distance physics, not a confining area law.
- **Established:** Dynamical matter carrying the probe charge can screen Wilson loops and replace the asymptotic area law by a perimeter law.
- **Established:** In pure or adjoint-matter $SU(N)$ gauge theories, N-ality controls which Wilson-line charges can be screened by gluons.
- **Established:** Higher-form symmetry gives a clean language for area, perimeter, and Coulomb laws of genuine line operators.
- **Active:** In many strongly coupled gauge theories, identifying the most useful confinement diagnostic requires combining line operators, spectrum, anomalies, finite-temperature probes, and lattice data.

## Relation to other topics

This page refines [Wilson-Loop Area Law](/nonperturbative-qft/confinement-screening-mass-gap/wilson-loop-area-law/) by explaining when the area law fails as an asymptotic criterion. The next natural page is [String Tension](/nonperturbative-qft/confinement-screening-mass-gap/string-tension/), which explains what remains physically meaningful when a stable or metastable flux tube exists.

The diagnostic background lives in [Wilson-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/wilson-loop-diagnostics/), [’t Hooft-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/thooft-loop-diagnostics/), and [Polyakov-Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/polyakov-loop-diagnostics/). [Center Symmetry](/nonperturbative-qft/confinement-screening-mass-gap/center-symmetry/), [One-Form Symmetry and Confinement](/nonperturbative-qft/confinement-screening-mass-gap/one-form-symmetry-confinement/), [Higgs versus Confinement](/nonperturbative-qft/confinement-screening-mass-gap/higgs-versus-confinement/), and [Compact QED in Three Dimensions](/nonperturbative-qft/confinement-screening-mass-gap/compact-qed-three-dimensions/) develop these screening caveats in more detail.

## Exercises

### Exercise 1: Which term wins asymptotically?

Suppose a Wilson loop has two contributions,

$$
\langle W(C_\lambda)\rangle
\sim A_0e^{-\sigma \lambda^2}+B_0e^{-\mu\lambda},
$$

with $A_0,B_0,\sigma,\mu>0$. Which term dominates as $\lambda\to\infty$?

<details>
<summary><strong>Solution</strong></summary>

Compare the ratio

$$
\frac{A_0e^{-\sigma\lambda^2}}{B_0e^{-\mu\lambda}}
=\frac{A_0}{B_0}e^{-\sigma\lambda^2+\mu\lambda}.
$$

As $\lambda\to\infty$, the $-\sigma\lambda^2$ term dominates the exponent, so the ratio goes to zero. Therefore the perimeter contribution dominates asymptotically, even if its prefactor is small.

</details>

### Exercise 2: Estimate the string-breaking distance

Assume an unbroken string state has energy

$$
V_{\rm string}(r)=\sigma r+V_0
$$

and a screened two-particle state has energy $E_{\rm screen}$. Estimate the distance at which string breaking becomes energetically favorable.

<details>
<summary><strong>Solution</strong></summary>

String breaking becomes favorable when

$$
\sigma r+V_0\approx E_{\rm screen}.
$$

Solving gives

$$
r_{\rm br}\approx \frac{E_{\rm screen}-V_0}{\sigma}.
$$

If the two states mix, this is the approximate location of an avoided crossing rather than an exact level crossing.

</details>

### Exercise 3: N-ality and screening

In pure $SU(3)$ Yang–Mills theory, can adjoint gluons screen a fundamental external charge completely? Can they screen an adjoint external charge completely?

<details>
<summary><strong>Solution</strong></summary>

Adjoint gluons have zero charge under the center $\mathbb Z_3$. Tensoring with adjoints cannot change N-ality. A fundamental external charge has nonzero N-ality, so adjoint gluons cannot screen it to a singlet.

An adjoint external charge has zero N-ality. It can be screened by gluons to a color singlet. Therefore an adjoint Wilson loop need not have an asymptotic area law in pure Yang–Mills theory, even though a fundamental Wilson loop can.

</details>

## References

### Standard first pass

- M. Srednicki, *Quantum Field Theory*, chapter 82, for Wilson loops, the free-electrodynamics perimeter law, and the static-potential interpretation.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapter 1, for phases of gauge theories, Wilson’s criterion, and the string-breaking caveat with dynamical quarks.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, chapter 9, for gauge theories with matter, perimeter laws, deconfinement, and screening in lattice Hamiltonian examples.

### Deeper references

- K. Wilson, “Confinement of Quarks,” for the original Wilson-loop confinement criterion.
- E. Fradkin and S. Shenker, “Phase Diagrams of Lattice Gauge Theories with Higgs Fields,” for Higgs–confinement continuity in gauge-Higgs systems.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the modern higher-form symmetry interpretation of area, perimeter, and Coulomb behavior.
- J. Greensite, *An Introduction to the Confinement Problem*, for lattice and continuum discussions of screening and string breaking.

## Version history

- **2026-06-27:** Initial polished page. Added perimeter-law scaling, static-potential interpretation, screening and string-breaking channels, representation dependence, one-form symmetry viewpoint, and exercises.
- **2026-06-27:** Linked the dedicated center-symmetry and one-form-symmetry pages.
