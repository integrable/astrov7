---
title: "Soft Gluon Theorem"
description: "The leading and subleading soft-gluon limits of gauge-theory amplitudes, including color-space notation, color conservation, Wilson lines, and the difference between Abelian and non-Abelian soft radiation."
sidebar:
  label: "Soft Gluon Theorem"
  order: 7
level: Graduate
status: "Polished draft"
source: "Weinberg 1965; Berends–Giele; Catani–Seymour; Sterman on QCD factorization; Schwartz chs. 20, 26, 32, and 36"
topics:
  - soft gluon theorem
  - non-Abelian infrared physics
  - color-space notation
  - Wilson lines
  - soft factorization
canonicalTopics:
  - soft-gluon-theorem
  - non-abelian-soft-factor
  - color-charge-conservation
  - wilson-line-soft-limit
researchStatus:
  established:
    - "The leading tree-level soft-gluon theorem is a universal consequence of external-line pole structure and non-Abelian gauge invariance, with color generators acting on the hard amplitude."
  active:
    - "Loop-level soft currents, subleading-power soft theorems, Glauber exchange, non-global logarithms, and soft factorization for realistic collider observables remain active research topics."
---

## Summary

The **soft gluon theorem** is the non-Abelian version of soft gauge-boson factorization. At tree level, when an extra gluon of momentum $k$ becomes soft, a gauge-theory amplitude factorizes into a universal soft current multiplying the hard amplitude:

$$
\mathcal M_{n+1}^{a}(p_1,\ldots,p_n;k,\varepsilon)
=
g_s\sum_{i=1}^n\eta_i\,\mathbf T_i^a
\frac{p_i\cdot\varepsilon^*(k)}{p_i\cdot k}
\mathcal M_n(p_1,\ldots,p_n)
+O(k^0).
$$

Here $\mathbf T_i^a$ is the color generator acting on external leg $i$, and $\eta_i=+1$ for an outgoing colored leg and $\eta_i=-1$ for an incoming colored leg. In an all-outgoing convention, the same sign information is absorbed into the crossed representation of the external leg.

The formula looks almost identical to the leading soft photon theorem, but the difference is enormous: electric charges are numbers, while color charges are operators. Soft gluons therefore know about color flow. Multiple soft gluons do not simply multiply as commuting factors; they require ordered color matrices and are naturally described by Wilson lines.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 55rem;">

![A soft gluon factors from a hard color amplitude through a sum of color-charge operators acting on external hard legs](/figures/perturbative-qft/soft-gluon-theorem.svg)

<figcaption>

A leading soft gluon cannot resolve the hard scattering. It couples to each external colored direction through the eikonal factor $p_i^\mu/(p_i\cdot k)$ multiplied by a color generator $\mathbf T_i^a$. Gauge invariance of the soft current is the statement that the total color charge of the hard amplitude vanishes.

</figcaption>
</figure>

## Prerequisites

You should know [Soft Divergences](/perturbative-qft/infrared-physics-factorization/soft-divergences/), [Collinear Divergences](/perturbative-qft/infrared-physics-factorization/collinear-divergences/), [Eikonal Approximation](/perturbative-qft/infrared-physics-factorization/eikonal-approximation/), [Soft Photon Theorem](/perturbative-qft/infrared-physics-factorization/soft-photon-theorem/), [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/), and [Color Factors](/perturbative-qft/gauge-theory-perturbation-theory/color-factors/).

## Core idea

A gluon with wavelength much longer than the hard scattering region cannot see the short-distance details of the process. At leading power it sees only the external colored particles and their directions. This is the same eikonal logic as in QED.

The new ingredient is that a gluon itself carries color. Emitting a soft gluon changes the color state of the hard amplitude. The soft factor is therefore not a scalar number; it is an operator on color space.

This turns the soft theorem into a compact dictionary:

| Abelian soft photon | Non-Abelian soft gluon |
|---|---|
| charge $Q_i$ is a number | color charge $\mathbf T_i^a$ is an operator |
| soft factors commute | soft factors generally do not commute |
| no photon self-charge | gluons radiate gluons |
| exponentiation is scalar-like | exponentiation uses ordered Wilson lines |
| gauge invariance gives charge conservation | gauge invariance gives color-charge conservation |

The theorem is not merely a clever way to simplify diagrams. It is the local form of non-Abelian infrared factorization. The same color-charge operators reappear in soft anomalous dimensions, parton showers, jet observables, subtraction schemes, and resummation.

## Setup and conventions

We use the gauge and scattering conventions fixed elsewhere on QFT.org. The hard amplitude $\mathcal M_n$ is treated as a vector in color space. For example, an amplitude with external quarks, antiquarks, and gluons has open color indices, and the color operator $\mathbf T_i^a$ acts only on the index of leg $i$.

For an outgoing quark, $\mathbf T_i^a$ acts by the fundamental generator $T^a$. For an outgoing antiquark, it acts by the conjugate representation. For an outgoing gluon, it acts in the adjoint representation. With Hermitian generators satisfying

$$
[T^a,T^b]=if^{abc}T^c,
$$

the adjoint generators may be written as

$$
(T_{\rm adj}^a)_{bc}=-if^{abc}.
$$

The sign $\eta_i$ tracks whether the colored particle is incoming or outgoing in the physical process. Many amplitude papers instead take all momenta outgoing; then an incoming quark is represented as an outgoing antiquark, and the sign is built into the crossed color representation.

The soft gluon has

$$
k^2=0,
\qquad
k^0\to0,
\qquad
k\cdot\varepsilon(k)=0.
$$

The formulas below are written for amplitudes with the overall momentum-conserving delta function stripped off.

## Color-space amplitudes

It is useful to write the hard amplitude as a ket in color space,

$$
|\mathcal M_n\rangle.
$$

The color generator acting on leg $i$ is denoted $\mathbf T_i^a$. Generators on different legs commute,

$$
[\mathbf T_i^a,\mathbf T_j^b]=0
\qquad (i\ne j),
$$

while generators on the same leg satisfy the representation's Lie algebra,

$$
[\mathbf T_i^a,\mathbf T_i^b]=if^{abc}\mathbf T_i^c.
$$

The quadratic color charge on leg $i$ is

$$
\mathbf T_i^2=C_i,
$$

where $C_i=C_F$ for a quark or antiquark and $C_i=C_A$ for a gluon.

Color conservation means that a gauge-invariant hard amplitude is annihilated by the total color charge:

$$
\sum_{i=1}^n\eta_i\mathbf T_i^a|\mathcal M_n\rangle=0.
$$

This is the non-Abelian version of $\sum_i\eta_iQ_i=0$ in QED.

## Leading soft-gluon theorem

The leading tree-level soft-gluon theorem is

$$
|\mathcal M_{n+1}^{a}(k,\varepsilon)\rangle
=
g_s\,\varepsilon^*_{\mu}(k)\,\mathbf J_a^\mu(k)
|\mathcal M_n\rangle
+O(k^0),
$$

with soft current

$$
\mathbf J_a^\mu(k)
=
\sum_{i=1}^n\eta_i\mathbf T_i^a\frac{p_i^\mu}{p_i\cdot k}.
$$

The factor $1/(p_i\cdot k)$ is the eikonal denominator. It comes from the propagator adjacent to the external leg becoming nearly on shell when the emitted gluon becomes soft. The numerator reduces to $p_i^\mu$ at leading power, independently of whether the hard external particle is a quark, antiquark, scalar, or gluon. The only representation-dependent information is the color generator.

Internal attachments do not change the leading theorem. If a soft gluon attaches inside a hard subdiagram, no hard internal propagator is forced on shell merely by taking $k\to0$. Such terms are at most $O(k^0)$ unless they belong to an overlapping soft or collinear region already represented by the factorized long-distance dynamics.

## Gauge invariance and color conservation

Gauge invariance gives the simplest check. Replace the polarization by the soft momentum:

$$
\varepsilon^\mu(k)\longrightarrow k^\mu.
$$

The leading soft factor becomes

$$
g_s\sum_i\eta_i\mathbf T_i^a\frac{p_i\cdot k}{p_i\cdot k}
=
g_s\sum_i\eta_i\mathbf T_i^a.
$$

Therefore the Ward identity reduces to

$$
\sum_i\eta_i\mathbf T_i^a|\mathcal M_n\rangle=0.
$$

In words: a physical hard scattering amplitude is a color singlet under a simultaneous color rotation of all external colored legs. Individual emissions from individual legs are not gauge invariant. The gauge-invariant object is the sum over all external color charges.

This is one reason soft gluon physics is more subtle than soft photon physics. The leading soft current is universal, but its action depends on the color state of the whole amplitude.

## Squared amplitudes and color dipoles

For cross sections, the leading soft limit is often written in terms of color-correlated Born amplitudes. Summing over the soft gluon color and physical polarizations gives a dipole structure of the form

$$
\sum_{a,\lambda}
|\mathcal M_{n+1}^{a}(k,\lambda)|^2
\simeq
-g_s^2
\sum_{i,j}\eta_i\eta_j
\frac{p_i\cdot p_j}{(p_i\cdot k)(p_j\cdot k)}
\langle\mathcal M_n|\mathbf T_i\cdot\mathbf T_j|\mathcal M_n\rangle.
$$

The sign shown is the usual mostly-minus result after the physical polarization sum is represented covariantly. The final radiation probability is positive after the full color-correlated sum is evaluated.

The important structural point is the appearance of **color dipoles**. Soft gluon radiation is not naturally assigned to one isolated colored particle. It is emitted coherently by pairs of color charges. In a color-singlet $q\bar q$ system, for instance,

$$
\mathbf T_q\cdot\mathbf T_{\bar q}=-C_F
$$

on the singlet color state. This is the color algebra behind the familiar dipole radiation pattern in $e^+e^-\to q\bar q+$ soft gluon.

## Wilson-line form

The eikonal approximation can be rewritten as a Wilson line along the direction of each hard colored particle. Schematically, for an outgoing energetic parton moving with four-velocity proportional to $p_i^\mu$,

$$
Y_i
=
P\exp\left[
ig_s\int_0^\infty ds\,p_i\cdot A^a(sp_i)\,\mathbf T_i^a
\right].
$$

The symbol $P$ denotes path ordering. It is essential because the color matrices do not generally commute. Expanding the Wilson line to first order in $g_s$ gives precisely the leading eikonal soft emission factor. Expanding to higher orders gives ordered multiple soft emissions from the same hard direction.

In factorization theorems, the product of Wilson lines defines a **soft function**. The soft function is where wide-angle soft radiation, non-Abelian exponentiation, cusp anomalous dimensions, and non-global logarithms live.

## Multiple soft gluons

For photons, two soft emissions are essentially obtained by multiplying two leading soft factors. For gluons, two new effects appear.

First, color generators on the same leg do not commute:

$$
\mathbf T_i^a\mathbf T_i^b\ne \mathbf T_i^b\mathbf T_i^a.
$$

Thus the order of emissions matters. The Wilson-line path ordering remembers which soft gluon is emitted earlier along the eikonal trajectory.

Second, gluons self-interact. A soft gluon can split into softer gluons, and diagrams with three-gluon vertices contribute to multiple-soft limits. These contributions are still universal at leading power, but they are not captured by treating gluons as independent Abelian emissions.

This is why non-Abelian soft physics is usually organized with Wilson lines, color operators, and soft anomalous dimensions rather than with a single scalar radiation factor.

## Subleading soft gluons

At tree level, the next term in the single-soft expansion has a compact form parallel to Low's theorem:

$$
|\mathcal M_{n+1}^{a}(k,\varepsilon)\rangle
=
g_s\sum_i\eta_i\mathbf T_i^a
\left[
\frac{p_i\cdot\varepsilon^*}{p_i\cdot k}
-i\frac{\varepsilon_\mu^* k_\nu J_i^{\mu\nu}}{p_i\cdot k}
\right]
|\mathcal M_n\rangle
+O(k).
$$

The angular momentum operator

$$
J_i^{\mu\nu}=L_i^{\mu\nu}+\Sigma_i^{\mu\nu}
$$

acts on the momentum and spin or polarization labels of hard leg $i$.

This formula is cleanest at tree level. In loop amplitudes and in physical cross sections, subleading soft behavior mixes with collinear regions, regulator choices, virtual soft exchange, and process-dependent terms. For that reason, the leading theorem is the durable workhorse for infrared factorization, while subleading-power factorization is a more delicate subject.

## Common pitfalls

**Treating color as a number.** In QCD the soft factor acts on the color vector $|\mathcal M_n\rangle$. Replacing $\mathbf T_i^a$ by a scalar charge misses non-Abelian coherence.

**Assigning soft radiation to a single leg.** Individual eikonal terms are not gauge invariant. The gauge-invariant leading current is the sum over all external color charges.

**Forgetting color conservation.** The replacement $\varepsilon\to k$ gives the total color charge. The theorem is compatible with gauge invariance only because physical hard amplitudes satisfy the color Ward identity.

**Confusing leading soft universality with full factorization.** The leading single-soft theorem is universal. Realistic cross sections also require collinear factorization, jet definitions, soft functions, PDFs for hadron beams, and sometimes resummation.

**Assuming multiple soft gluons commute.** Non-Abelian soft emissions require color ordering or Wilson-line path ordering.

## Relations to other pages

- [Soft Photon Theorem](/perturbative-qft/infrared-physics-factorization/soft-photon-theorem/) is the Abelian limit where the color generators become ordinary charges.
- [Eikonal Approximation](/perturbative-qft/infrared-physics-factorization/eikonal-approximation/) derives the universal denominator $1/(p_i\cdot k)$.
- [Color Factors](/perturbative-qft/gauge-theory-perturbation-theory/color-factors/) explains $C_F$, $C_A$, and color-correlated amplitudes.
- [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/) gives the vertices whose soft limits produce the theorem.
- [Jets and Inclusive Observables](/perturbative-qft/infrared-physics-factorization/jets-and-inclusive-observables/) explains how soft and collinear singularities become finite measured quantities.
- [Factorization Preview](/perturbative-qft/infrared-physics-factorization/factorization-preview/) will organize Wilson lines, jet functions, hard functions, and PDFs into full factorization theorems.

## Research status

- **Established:** The leading tree-level single-soft gluon theorem, its color-space form, and its Wilson-line interpretation are standard components of perturbative QCD.
- **Active:** Subleading-power soft theorems, loop corrections to soft currents, Glauber regions, factorization violation in hadron scattering, and non-global logarithms are active topics.
- **Speculative:** Connections between soft theorems, asymptotic symmetries, celestial amplitudes, and nonperturbative confinement physics are promising but not a substitute for ordinary factorization proofs.

## Exercises

### Exercise 1: Gauge invariance of the leading soft current

Use the leading soft-gluon theorem to show that replacing $\varepsilon^\mu(k)$ by $k^\mu$ gives the total color charge of the hard amplitude.

<details>
<summary><strong>Solution</strong></summary>

The leading soft factor is

$$
g_s\sum_i\eta_i\mathbf T_i^a
\frac{p_i\cdot\varepsilon^*}{p_i\cdot k}.
$$

Under $\varepsilon^\mu\to k^\mu$, it becomes

$$
g_s\sum_i\eta_i\mathbf T_i^a
\frac{p_i\cdot k}{p_i\cdot k}
=
g_s\sum_i\eta_i\mathbf T_i^a.
$$

Gauge invariance therefore requires

$$
\sum_i\eta_i\mathbf T_i^a|\mathcal M_n\rangle=0,
$$

which is color-charge conservation for the hard amplitude.

</details>

### Exercise 2: Abelian limit

Show that the leading soft-gluon theorem reduces to the leading soft photon theorem if the color generators are replaced by commuting charges.

<details>
<summary><strong>Solution</strong></summary>

Replace

$$
g_s\mathbf T_i^a\longrightarrow eQ_i.
$$

Because $Q_i$ is a number, there is no color-space action and no noncommutativity. The soft-gluon formula becomes

$$
\mathcal M_{n+1}
=
\left[
e\sum_i\eta_i Q_i\frac{p_i\cdot\varepsilon^*}{p_i\cdot k}
\right]
\mathcal M_n+O(k^0),
$$

which is the leading soft photon theorem.

</details>

### Exercise 3: Color dipole in a singlet quark pair

Let a hard amplitude contain a color-singlet $q\bar q$ pair. Use color conservation to show that

$$
\mathbf T_q\cdot\mathbf T_{\bar q}=-C_F
$$

on the singlet state.

<details>
<summary><strong>Solution</strong></summary>

For a color-singlet pair,

$$
(\mathbf T_q^a+\mathbf T_{\bar q}^a)|\text{singlet}\rangle=0.
$$

Squaring the total color charge gives

$$
(\mathbf T_q+\mathbf T_{\bar q})^2|\text{singlet}\rangle=0.
$$

Expanding,

$$
\left(\mathbf T_q^2+\mathbf T_{\bar q}^2+2\mathbf T_q\cdot\mathbf T_{\bar q}\right)|\text{singlet}\rangle=0.
$$

Since a quark and antiquark both have quadratic Casimir $C_F$,

$$
(2C_F+2\mathbf T_q\cdot\mathbf T_{\bar q})|\text{singlet}\rangle=0.
$$

Therefore

$$
\mathbf T_q\cdot\mathbf T_{\bar q}|\text{singlet}\rangle=-C_F|\text{singlet}\rangle.
$$

</details>

### Exercise 4: Why path ordering appears

Explain why a Wilson line is needed for multiple soft gluons in QCD but not for multiple soft photons in QED.

<details>
<summary><strong>Solution</strong></summary>

For QED, the charge factors are ordinary numbers, so two soft photon emissions commute:

$$
Q_iQ_i=Q_i^2,
$$

independent of any emission order.

For QCD, two soft gluons of colors $a$ and $b$ emitted from the same external leg produce products such as

$$
\mathbf T_i^a\mathbf T_i^b
\quad\text{and}\quad
\mathbf T_i^b\mathbf T_i^a.
$$

Their commutator is

$$
[\mathbf T_i^a,\mathbf T_i^b]=if^{abc}\mathbf T_i^c,
$$

which is generally nonzero. A Wilson line includes the path-ordering symbol $P$ precisely to remember the order of noncommuting color matrices along the eikonal trajectory.

</details>

## References

- S. Weinberg, “Infrared Photons and Gravitons,” *Physical Review* **140** (1965), for the classic universal soft-factor argument.
- F. A. Berends and W. T. Giele, “Multiple Soft Gluon Radiation in Parton Processes,” *Nuclear Physics B* **313** (1989), for non-Abelian multi-soft structures.
- S. Catani and M. H. Seymour, “A General Algorithm for Calculating Jet Cross Sections in NLO QCD,” *Nuclear Physics B* **485** (1997), for color-space soft and collinear limits used in subtraction.
- G. Sterman, *An Introduction to Quantum Field Theory*, and Sterman's QCD factorization lectures, for QCD infrared behavior and Wilson-line factorization.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 20, 26, 32, and 36, for soft gluons, QCD, jets, and effective-theory language.
- Z. Bern, L. Dixon, and D. A. Kosower, reviews on gauge-theory amplitudes, for color-space soft limits and amplitude applications.

## Version history

- **2026-06-13:** Initial page. Uses color-space notation and emphasizes the distinction between Abelian soft charges and non-Abelian color-charge operators.
