---
title: "Examples of Anomaly Matching"
description: "Collects worked examples showing how ultraviolet ’t Hooft anomalies are matched by infrared gapless modes, Wess–Zumino terms, inflow, symmetry breaking, or topological order."
sidebar:
  label: "Examples of Anomaly Matching"
  order: 8
level: Advanced
status: "Polished draft"
source: "’t Hooft anomaly matching; Coleman; Srednicki; Schwartz; Wess–Zumino–Witten; bosonization; parity anomaly; modern higher-form anomaly examples."
topics:
  - anomaly matching examples
  - chiral symmetry
  - Wess Zumino Witten term
  - bosonization
  - parity anomaly
  - center symmetry
  - QCD
canonicalTopics:
  - examples-of-anomaly-matching
  - qcd-anomaly-matching
  - wzw-anomaly-matching
  - bosonization-anomaly-matching
  - parity-anomaly-inflow
researchStatus:
  established:
    - "The UV–IR equality of ’t Hooft anomaly classes gives a reliable nonperturbative constraint on symmetry-preserving RG flows."
    - "Classic examples include two-dimensional bosonization, QCD chiral symmetry matching by the Wess–Zumino–Witten term, and parity-anomaly inflow from a four-dimensional bulk."
  active:
    - "Modern examples involving higher-form symmetries, center symmetry, time reversal, non-invertible symmetry, and strongly coupled phases often require refined background fields and careful global-form choices."
---

## Summary

Anomaly matching is easiest to learn from examples. The rule is simple:

$$
[\mathcal A_{\rm UV}]=[\mathcal A_{\rm IR}]
$$

whenever the symmetry is exact and preserved along the flow. The art is recognizing **how** the IR carries the same anomaly.

The matching mechanism can look very different from the UV origin. A UV fermion triangle can become a Wess–Zumino–Witten term. A fermionic parity anomaly can become bulk inflow. A microscopic anomaly in a gauge theory can force CP breaking, topological order, or gaplessness in the IR. The anomaly survives; the carriers can change completely.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing four anomaly matching examples: two-dimensional Dirac fermion to compact boson, QCD-like quarks to WZW pions, parity anomaly to inflow or surface topological order, and Yang–Mills theta pi anomaly to nontrivial IR fates.](/figures/symmetry-anomalies-topology/anomaly-matching-examples-library.svg)

<figcaption>

Four matching patterns. The UV description, anomaly data, and IR realization may look unrelated, but they obey the same rule: preserving the symmetry preserves the anomaly class.

</figcaption>
</figure>

This page is a compact library, not a full review of each model. The goal is to train the diagnostic reflex: identify the symmetry, couple to backgrounds, compute or quote the anomaly class, and test candidate IR phases against it.

## Prerequisites

Read [’t Hooft Anomalies](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/thooft-anomalies/), [Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/), [Anomalies as RG Invariants](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-as-rg-invariants/), and [Anomalies and Symmetry-Protected Phases](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-and-symmetry-protected-phases/) first.

You should also be comfortable with [Chiral Anomaly](/symmetry-anomalies-topology/anomalies/chiral-anomaly/), [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/), [Global Anomalies](/symmetry-anomalies-topology/anomalies/global-anomalies/), and [Consistent Versus Covariant Anomalies](/symmetry-anomalies-topology/anomalies/consistent-versus-covariant-anomalies/).

## Core idea

To use anomaly matching in practice, proceed in four steps.

First, identify the exact symmetry $G$. This includes its global form, discrete quotients, higher-form factors, time-reversal or charge-conjugation actions, and any spin/Pin structure needed to define fermions.

Second, couple the theory to background fields $A$ for $G$. This is where many mistakes happen. If the background fields are wrong, the anomaly statement is wrong.

Third, determine the anomaly class $[\mathcal A]$. This may be a perturbative anomaly polynomial, a global anomaly, a finite-group cocycle, an eta-invariant phase, or a mixed anomaly involving several symmetries.

Fourth, ask how the proposed IR theory carries the same class. If no candidate IR degree of freedom can match it, the candidate phase is impossible.

The slogan is:

$$
\text{match the obstruction, not the fields}.
$$

## Setup and conventions

For a $d$-dimensional theory with background fields $A$, write the anomalous transformation as

$$
Z[A^g]
=
\exp\!\left(2\pi i\mathcal A_g[A]\right)Z[A].
$$

Two anomaly functionals that differ by the variation of a local counterterm represent the same anomaly class:

$$
\mathcal A\sim \mathcal A+\delta \mathcal C_{\rm local}.
$$

Anomaly matching means equality of the class, not equality of a chosen representative:

$$
[\mathcal A_{\rm UV}]=[\mathcal A_{\rm IR}].
$$

:::note[Convention-sensitive source note]
Many examples below are stated at the level of anomaly coefficients rather than full background-field representatives. Coefficients depend on generator normalization. For non-Abelian flavor groups, this page uses the common convention

$$
\operatorname{tr}_{\square}(T^aT^b)=\frac12\delta^{ab},
$$

so a fundamental left-handed Weyl fermion contributes one unit to the cubic flavor anomaly coefficient. If a source uses $\operatorname{tr}_{\square}(T^aT^b)=\delta^{ab}$, the displayed coefficients are rescaled accordingly.
:::

## Example 1: two-dimensional Dirac fermion and bosonization

A massless Dirac fermion in $1+1$ dimensions can be written in terms of left- and right-moving Weyl fermions,

$$
\psi=(\psi_L,\psi_R).
$$

Classically it has vector and axial symmetries,

$$
U(1)_V\times U(1)_A,
$$

with currents

$$
j_V^\mu=\bar\psi\gamma^\mu\psi,
\qquad
j_A^\mu=\bar\psi\gamma^\mu\gamma^5\psi.
$$

If the vector symmetry is coupled to a background gauge field $A_V$ and is preserved as a true background gauge symmetry, the axial symmetry has an anomaly:

$$
\partial_\mu j_A^\mu
=\frac{1}{\pi}\,F_{01}^{V}
$$

in a common normalization for a unit-charge Dirac fermion.

The bosonized IR description is a compact scalar $\varphi$. The vector and axial symmetries act as winding and shift symmetries of the boson. The bosonized action includes a background coupling schematically of the form

$$
S_{\rm bkgd}
\sim
\frac{1}{2\pi}\int \varphi\, dA_V,
$$

up to normalization conventions for the compactification radius and current normalization. Under the axial shift $\varphi\mapsto\varphi+\alpha$, this term changes by

$$
\delta_\alpha S_{\rm bkgd}
\sim
\frac{\alpha}{2\pi}\int dA_V,
$$

which reproduces the same mixed anomaly after the corresponding normalization of the axial parameter is chosen.

The lesson is excellent: the UV anomaly carried by fermion chirality is matched in the IR by a bosonic shift response. Nothing in anomaly matching says the IR degrees of freedom must have the same statistics as the UV fields.

## Example 2: QCD chiral symmetry and the Wess–Zumino–Witten term

Consider QCD-like $SU(N_c)$ gauge theory with $N_f$ massless Dirac quarks in the fundamental representation. Ignoring quotient subtleties for a moment, the continuous flavor symmetry contains

$$
SU(N_f)_L\times SU(N_f)_R\times U(1)_B.
$$

The left-handed quarks transform as fundamentals under $SU(N_f)_L$, and the right-handed quarks transform as fundamentals under $SU(N_f)_R$. Since each flavor fermion also carries color, the cubic flavor anomaly has coefficient $N_c$:

$$
SU(N_f)_L^3: \quad +N_c,
\qquad
SU(N_f)_R^3: \quad -N_c,
$$

where the sign difference comes from writing right-handed fermions as left-handed conjugates.

The expected low-energy phase for ordinary QCD at small $N_f$ is chiral symmetry breaking,

$$
SU(N_f)_L\times SU(N_f)_R
\longrightarrow
SU(N_f)_V.
$$

The Goldstone fields are packaged into

$$
U(x)\in SU(N_f),
$$

transforming as

$$
U\mapsto g_L U g_R^{-1}.
$$

The ordinary nonlinear sigma model on $SU(N_f)$ does not by itself reproduce the chiral anomaly. The missing term is the Wess–Zumino–Witten term. For $N_f\geq 3$, the WZW term can be written using an extension of $U$ to a five-dimensional manifold $X_5$ with boundary $M_4$:

$$
S_{\rm WZW}
=
\frac{N_c}{240\pi^2}\int_{X_5}
\operatorname{tr}\left(U^{-1}dU\right)^5
+
\text{background-field completions}.
$$

The coefficient is quantized, and the coefficient $N_c$ is fixed by anomaly matching. When background flavor fields are included, the variation of the WZW functional reproduces the same $SU(N_f)_L^3$, $SU(N_f)_R^3$, and mixed flavor anomalies as the quarks.

This is the flagship example of anomaly matching:

$$
\text{quark triangle anomaly in the UV}
\quad\longrightarrow\quad
\text{WZW term for pions in the IR}.
$$

:::note[Why the coefficient matters]
The WZW coefficient cannot be tuned continuously. Its quantization is what lets it remember the integer $N_c$ after the quarks and gluons have disappeared from the low-energy spectrum. This is a wonderfully efficient bit of infrared archaeology.
:::

## Example 3: the neutral pion decay as an anomaly footprint

The decay

$$
\pi^0\to \gamma\gamma
$$

is often introduced as a direct consequence of the axial anomaly. In the anomaly-matching viewpoint, it is also a low-energy footprint of the same UV chiral anomaly.

In the chiral Lagrangian, electromagnetic gauge fields are embedded into flavor background fields. The gauged WZW term contains an interaction of the form

$$
\mathcal L_{\pi^0\gamma\gamma}
\propto
\frac{N_c e^2}{24\pi^2 f_\pi}\,\pi^0 F_{\mu\nu}\widetilde F^{\mu\nu},
$$

with the exact coefficient depending on charge-matrix normalization and the convention for $f_\pi$.

The key point is not the specific convention-dependent prefactor. It is that the pion effective theory must reproduce the electromagnetic part of the UV flavor anomaly. The WZW term does exactly that.

This example connects three languages:

$$
\text{fermion triangle}
\quad\leftrightarrow\quad
\text{anomalous Ward identity}
\quad\leftrightarrow\quad
\text{WZW interaction in the pion EFT}.
$$

## Example 4: anomaly matching by massless composite fermions

The QCD chiral example above matches the anomaly through symmetry breaking and a WZW term. Another logical possibility is that the IR remains symmetric and contains massless composite fermions whose anomalies equal the UV anomalies.

This was one of ’t Hooft’s original uses of anomaly matching. Suppose a strongly coupled theory confines without breaking an exact global symmetry $G$. Then the low-energy spectrum would consist of gauge-invariant massless composites transforming under $G$. Their fermion triangle anomalies must equal those of the elementary UV fermions.

This gives a powerful test of proposed confining phases. If no set of massless composites can match the UV anomaly, then the assumed symmetric confining phase is impossible.

The rule is algebraic. If the UV anomaly coefficient is

$$
\mathcal A_{\rm UV}^{abc}=\sum_{\text{UV Weyl }i}\operatorname{tr}_{R_i}\!\left(T^a\{T^b,T^c\}\right),
$$

then a symmetric massless-composite IR must satisfy

$$
\mathcal A_{\rm IR}^{abc}=\sum_{\text{IR Weyl }j}\operatorname{tr}_{r_j}\!\left(T^a\{T^b,T^c\}\right)
=
\mathcal A_{\rm UV}^{abc}.
$$

This is why anomaly matching is so useful in chiral gauge theories, where the IR may not be known. It can rule out entire classes of proposed spectra.

## Example 5: gauge anomaly cancellation in the Standard Model

Gauge anomaly cancellation is not the same as ’t Hooft anomaly matching, but it is a nearby consistency check worth keeping in the same mental folder.

A dynamical gauge symmetry is redundancy. Its anomaly must vanish. In the Standard Model, the chiral fermion hypercharges are arranged so that the dangerous perturbative gauge anomalies cancel, including

$$
SU(3)^2U(1)_Y,
\qquad
SU(2)^2U(1)_Y,
\qquad
U(1)_Y^3,
\qquad
\text{gravity}^2 U(1)_Y.
$$

There is also the global $SU(2)$ Witten anomaly: an $SU(2)$ gauge theory is inconsistent with an odd number of left-handed Weyl doublets. Per Standard Model generation, the number of $SU(2)_L$ doublets is

$$
3\ \text{quark doublets} + 1\ \text{lepton doublet}=4,
$$

which is even. Therefore the global $SU(2)$ gauge anomaly cancels generation by generation.

The anomaly-matching lesson is the distinction:

$$
\text{gauge anomaly} = \text{must cancel},
$$

whereas

$$
\text{global ’t Hooft anomaly} = \text{may be nonzero, but must match}.
$$

## Example 6: baryon and lepton number in the electroweak theory

The classical Standard Model has accidental baryon and lepton number currents. Quantum mechanically, the electroweak $SU(2)_L$ anomaly gives

$$
\partial_\mu j_B^\mu
=\partial_\mu j_L^\mu
\propto
N_g\,\operatorname{tr}(W_{\mu\nu}\widetilde W^{\mu\nu}),
$$

where $N_g$ is the number of generations.

The combination $B+L$ is anomalous in electroweak backgrounds. The combination $B-L$ is anomaly-free with respect to the electroweak $SU(2)_L$ instanton selection rule; if one wants to gauge $B-L$ as an ordinary continuous gauge symmetry, additional anomaly checks are required, and the familiar minimal completion adds right-handed neutrinos.

Electroweak instantons and sphalerons violate

$$
\Delta B=\Delta L=N_g\,n
$$

for topological charge $n$, but preserve

$$
\Delta(B-L)=0.
$$

The anomaly is not just a formal failure of a current equation. It controls which processes are allowed nonperturbatively.

## Example 7: parity anomaly and topological-insulator surface

A single two-component Dirac fermion in $2+1$ dimensions coupled to a background $U(1)$ field has the parity anomaly. A gauge-invariant regularization generates a half-integer Chern–Simons contact term:

$$
S_{\rm contact}
=\frac{1}{8\pi}\int A\wedge dA
$$

up to sign and spin-structure refinements. A purely $2+1$-dimensional bosonic Chern–Simons contact term is ordinarily quantized in integer units. The half-level signals that the theory is not a conventional standalone $2+1$-dimensional theory preserving all desired symmetries.

As the boundary of a $3+1$-dimensional topological insulator, the surface Dirac cone is consistent. The bulk theta response at $\theta=\pi$ supplies the missing inflow. The anomaly can be matched by:

- a gapless surface Dirac fermion;
- time-reversal breaking with a half-quantized surface Hall response plus bulk inflow;
- a symmetric gapped surface with intrinsic topological order.

This is one of the clearest bridges between particle-physics anomaly language and condensed-matter SPT language.

## Example 8: pure Yang–Mills at theta equals pi

Pure $SU(N)$ Yang–Mills theory has a $\mathbb Z_N$ one-form center symmetry acting on Wilson lines. At

$$
\theta=\pi,
$$

there is a mixed anomaly, or for some $N$ a closely related global inconsistency, involving CP and the one-form center symmetry. The precise statement depends on the global form of the gauge group, the allowed line operators, and the background two-form field for the center symmetry.

The practical consequence is robust: the theory cannot have a completely trivial, gapped, confining, center-preserving and CP-preserving vacuum at $\theta=\pi$.

The expected large-$N$ and semiclassical intuition is that CP is spontaneously broken at $\theta=\pi$, giving two vacua exchanged by CP. In other regimes, the anomaly could instead be matched by topological order or gapless modes.

This example is important because the anomaly involves an extended-operator symmetry, not an ordinary particle-number symmetry. The charged objects are Wilson lines, and the background is a two-form gauge field. It is a modern version of the same old matching rule.

:::note[Global-form caveat]
For Yang–Mills examples, do not say “the anomaly of the Lie algebra.” The global form of the gauge group and the spectrum of genuine line operators matter. $SU(N)$, $PSU(N)$, and variants with different discrete theta angles can have different one-form symmetries and different anomaly data.
:::

## Example 9: anomaly matching across dualities

Dualities provide high-precision anomaly tests. If two UV-looking Lagrangians describe the same IR QFT, they must have the same ’t Hooft anomalies for the same global symmetry.

This is one reason anomaly matching is so prominent in supersymmetric duality, three-dimensional bosonization duality, two-dimensional duality, and modern generalized-symmetry dualities. Before comparing detailed dynamics, one checks:

$$
G_{\rm left}=G_{\rm right},
\qquad
[\mathcal A_{\rm left}]=[\mathcal A_{\rm right}].
$$

Failure of the anomaly check usually means one of three things:

- the proposed duality is wrong;
- the global symmetry was misidentified;
- a decoupled sector, spin-structure choice, contact term, quotient, or topological field theory was omitted.

The third possibility is common. Anomaly matching often tells you what extra topological sector must be included for the duality to be true.

## Diagnostic table

| Situation | What to check | Possible IR match |
|---|---|---|
| UV chiral fermions with flavor symmetry | cubic and mixed flavor anomalies | massless fermions, WZW term, symmetry breaking |
| finite symmetry | cocycle or bordism anomaly | anomalous boundary TQFT, symmetry breaking, gaplessness |
| time reversal or reflection | Pin-structure-dependent anomaly | protected surface, symmetry breaking, topological order |
| higher-form symmetry | background higher-form gauge field response | deconfined gauge field, topological order, broken higher-form symmetry |
| proposed duality | equality of all contact terms and anomalies | matching topological sectors or counterterms |

The table is deliberately schematic. In real calculations, the hard work is specifying the background fields and global form correctly.

## Common pitfalls

**“Matching the anomaly means matching the current equation literally.”**  Not quite. Current equations depend on contact terms and scheme choices. The invariant object is the anomaly class.

**“The same fields must appear in the IR.”**  No. The QCD example is the classic counterexample: UV quarks match through IR pions plus a WZW term.

**“Gauge anomaly cancellation is anomaly matching.”**  Gauge anomalies must cancel for consistency. ’t Hooft anomalies are allowed for global symmetries and must match under RG flow.

**“A vanishing perturbative anomaly means no anomaly.”**  Not necessarily. Global, finite, torsion, spin/Pin, and higher-form anomalies can remain invisible to the perturbative anomaly polynomial.

**“One-form symmetry anomalies are optional decorations.”**  No. Once a theory has a genuine one-form symmetry, its anomaly data constrain confinement, screening, line operators, and possible trivially gapped phases.

## Relations to other pages

[Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/) gives the general proof logic. This page shows what the logic looks like in concrete models.

[Anomalies and Symmetry-Protected Phases](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-and-symmetry-protected-phases/) explains the bulk perspective behind the parity-anomaly and boundary examples.

[Wess–Zumino–Witten Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-witten-terms/) will develop the pion WZW term and its quantization in more detail.

[Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) will give the systematic language behind the Yang–Mills center-symmetry example.

The full dynamics of QCD, electroweak anomalies, instantons, and sphalerons belongs in Gauge Theories and the Standard Model and Nonperturbative QFT. Here they serve as anomaly-matching examples.

## Research status

The examples involving two-dimensional bosonization, QCD chiral symmetry, WZW matching, perturbative flavor anomalies, Standard Model gauge anomaly cancellation, and the parity anomaly are established textbook material.

The higher-form Yang–Mills examples are established in modern generalized-symmetry language, but their physical realization depends on the theory, parameters, global form, and assumptions about the IR phase.

Duality anomaly checks are a central research tool. In modern work, matching increasingly includes finite counterterms, spin structures, one-form symmetries, non-invertible defects, and topological sectors that older analyses would have ignored.

## Exercises

### Exercise 1: QCD flavor anomaly coefficient

In $SU(N_c)$ QCD with $N_f$ massless Dirac quarks, explain why the $SU(N_f)_L^3$ flavor anomaly coefficient is proportional to $N_c$.

<details><summary><strong>Solution</strong></summary>

Each color copy of a left-handed quark transforms as a fundamental of $SU(N_f)_L$. There are $N_c$ independent color copies. Therefore the total cubic flavor anomaly is $N_c$ times the anomaly of one fundamental left-handed Weyl fermion:

$$
\mathcal A_{SU(N_f)_L^3}=N_c.
$$

The right-handed quarks give the opposite sign when written as left-handed conjugates, so

$$
\mathcal A_{SU(N_f)_R^3}=-N_c.
$$

</details>

### Exercise 2: Why the pion sigma model needs the WZW term

Why is an ordinary two-derivative nonlinear sigma model for pions not enough to match the QCD chiral anomaly?

<details><summary><strong>Solution</strong></summary>

The two-derivative pion action is invariant under chiral transformations once background fields are transformed appropriately. It does not have the anomalous background variation required by the UV quark flavor anomaly.

The Wess–Zumino–Witten term has a quantized coefficient and a controlled anomalous variation in flavor backgrounds. With coefficient $N_c$, it reproduces the UV chiral anomaly. Therefore the pion theory without the WZW term has the wrong anomaly class.

</details>

### Exercise 3: Even number of Standard Model doublets

Count the number of $SU(2)_L$ Weyl doublets in one Standard Model generation and explain why there is no Witten $SU(2)$ gauge anomaly.

<details><summary><strong>Solution</strong></summary>

One generation has one lepton doublet and one quark doublet for each of three colors. Therefore the number of left-handed $SU(2)_L$ doublets is

$$
1+3=4.
$$

The Witten global anomaly occurs for an odd number of left-handed Weyl doublets. Since $4$ is even, the anomaly cancels generation by generation.

</details>

### Exercise 4: Trivially gapped Yang–Mills at theta equals pi

Suppose pure $SU(N)$ Yang–Mills at $\theta=\pi$ has a mixed anomaly involving CP and center symmetry. Why is a unique, trivially gapped, center-preserving, CP-preserving vacuum forbidden?

<details><summary><strong>Solution</strong></summary>

A unique trivially gapped symmetric vacuum has no long-distance degrees of freedom and no topological order that could carry a nonzero anomaly. Its anomaly class is zero, up to removable local counterterms.

If the UV theory has a nontrivial mixed anomaly between CP and center symmetry, anomaly matching requires the IR to carry the same class. A trivially gapped symmetric vacuum cannot do so. The theory must instead break one of the symmetries, remain gapless, or develop topological order or another nontrivial IR realization.

</details>

## References

- G. ’t Hooft, “Naturalness, chiral symmetry, and spontaneous chiral symmetry breaking,” in *Recent Developments in Gauge Theories*, NATO Advanced Study Institutes Series B, Vol. 59, 1980.
- J. Wess and B. Zumino, “Consequences of anomalous Ward identities,” *Physics Letters B* **37** (1971) 95.
- E. Witten, “Global aspects of current algebra,” *Nuclear Physics B* **223** (1983) 422.
- E. Witten, “An SU(2) anomaly,” *Physics Letters B* **117** (1982) 324.
- S. Coleman, *Aspects of Symmetry*, especially “Soft pions,” “The uses of instantons,” and anomaly-related discussions.
- M. Srednicki, *Quantum Field Theory*, sections on chiral gauge theories, global anomalies, path-integral anomalies, chiral symmetry breaking, and theta vacua.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Chapter 30.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” [arXiv:1412.5148](https://arxiv.org/abs/1412.5148).
- A. Kapustin and R. Thorngren, “Anomalies of discrete symmetries in various dimensions and group cohomology,” [arXiv:1404.3230](https://arxiv.org/abs/1404.3230).
- D. Gaiotto, A. Kapustin, Z. Komargodski, and N. Seiberg, “Theta, Time Reversal, and Temperature,” [arXiv:1703.00501](https://arxiv.org/abs/1703.00501).
- E. Witten, “Fermion path integrals and topological phases,” [arXiv:1508.04715](https://arxiv.org/abs/1508.04715).

## Version history

- 2026-06-18: First polished draft. Added examples from bosonization, QCD chiral symmetry, WZW matching, Standard Model anomaly cancellation, electroweak baryon/lepton violation, parity anomaly, Yang–Mills center symmetry, and duality checks.
