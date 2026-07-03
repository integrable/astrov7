---
title: "Anomalies"
description: "Chapter overview for perturbative, global, gravitational, mixed, and trace anomalies in the Symmetry, Anomalies, and Topology volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Srednicki §§75–77; Schwartz Ch. 30; Coleman on chiral Ward identities and instantons; Bilal, Lectures on Anomalies; standard index-theorem, descent, and anomaly-inflow references."
topics:
  - anomalies
  - chiral anomalies
  - gauge anomalies
  - global anomalies
  - gravitational anomalies
  - mixed anomalies
  - trace anomaly
  - anomaly polynomial
  - descent equations
  - Wess–Zumino consistency
canonicalTopics:
  - anomaly
  - chiral-anomaly
  - gauge-anomaly
  - global-anomaly
  - gravitational-anomaly
  - mixed-anomaly
  - trace-anomaly
  - anomaly-polynomial
  - descent-equations
researchStatus:
  established:
    - "Anomalies are quantum obstructions to preserving a proposed symmetry, background-field invariance, or scaling law under the chosen regulator and locality requirements."
    - "Gauge anomalies must cancel for a gauge theory to be consistent, while global and ’t Hooft anomalies are consistent and constrain RG flow, phases, boundaries, and dualities."
  active:
    - "Modern anomaly theory continues to refine global, fermionic, higher-form, non-invertible, gravitational, and symmetry-TFT formulations, especially on general manifolds and in theories without Lagrangians."
---

Anomalies is the chapter in the Symmetry, Anomalies, and Topology volume where a slogan from elementary symmetry theory is finally corrected. A classical transformation of the action is not yet a quantum symmetry. The regulator, the path-integral measure, the operator product at coincident points, and the global topology of background fields all get a vote.

The chapter exists because anomalous symmetries are among the most useful failures in QFT. A gauge anomaly is usually fatal. A global anomaly is often a treasure: it explains physical processes, constrains possible infrared phases, forces massless modes or topological order, and makes dualities testable.

The guiding slogan is:

$$
\text{anomaly}=\text{nonremovable quantum obstruction to a proposed symmetry principle}.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![A roadmap for the Anomalies chapter. Classical symmetry enters the quantum path integral through regulator, measure, current, and background-field tests. Nonremovable failures become gauge anomalies, global anomalies, gravitational anomalies, mixed anomalies, trace anomalies, descent data, and anomaly inflow.](/figures/symmetry-anomalies-topology/anomalies-chapter-roadmap.svg)

<figcaption>

An anomaly is not just “a current is not conserved.” The same obstruction can be seen as a regulator conflict, a non-invariant measure, a broken Ward identity, a non-invariant effective action, or a failure of background gauging. Different pages in this chapter develop these views and then connect them through anomaly polynomials, descent, consistency conditions, and inflow.

</figcaption>
</figure>

This chapter starts conservatively: triangle diagrams, chiral currents, and the Fujikawa measure. It then broadens the definition until anomalies become background-field and topological data. That broadening is not fashion. It is what makes anomalies useful in strongly coupled theories, theories without Lagrangians, phases of matter, boundaries, higher-form symmetries, and symmetry TFT.

## Prerequisites

You should know the volume [Conventions and Notation](/symmetry-anomalies-topology/conventions/), especially the background-field sign convention $D_\mu=\partial_\mu-iA_\mu$ and the normalization caveats for Chern–Simons and theta terms.

From earlier chapters, the most useful pages are [Noether Currents](/symmetry-anomalies-topology/noether-currents-ward-identities/noether-currents/), [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/), [Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/), [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/), [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/), and [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/).

You should also be comfortable with Dirac and Weyl fermions, Feynman diagrams at one loop, path-integral changes of variables, and the distinction between a global symmetry and a gauge redundancy.

The later pages use differential forms, characteristic classes, spin structures, and index-theorem language. The first half of the chapter does not require all of that machinery.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | What Is an Anomaly? | The background-field, Ward-identity, regulator, and measure definitions in one place. |
| 2 | Regulator and Measure Viewpoints | Why quantization may force a choice between incompatible classical symmetries. |
| 3 | Triangle Anomaly | The one-loop diagram where the basic four-dimensional chiral anomaly first becomes unavoidable. |
| 4 | Chiral Anomaly | The physical axial-current anomaly, including $F\widetilde F$, pion decay, and instanton-facing consequences. |
| 5 | Fujikawa Method | The path-integral Jacobian derivation and the role of the regulated trace of $\gamma^5$. |
| 6 | Perturbative Gauge Anomalies | Gauge-anomaly cancellation, chiral fermions, representation traces, and why anomalous gauge redundancy is inconsistent. |
| 7 | Global Anomalies | Large transformations, signs of fermion determinants, and anomalies invisible in infinitesimal perturbation theory. |
| 8 | Gravitational Anomalies | Diffeomorphism and local-Lorentz anomalies, chiral matter, and the relation to index theory. |
| 9 | Mixed Anomalies | Obstructions involving several symmetries at once, including gauge–global, global–global, and symmetry–gravity mixtures. |
| 10 | Trace Anomaly | Why scale or Weyl invariance can fail quantum mechanically even when a classical action is scale invariant. |
| 11 | Consistent versus Covariant Anomalies | The difference between anomalies satisfying Wess–Zumino consistency and currents transforming covariantly. |
| 12 | Wess–Zumino Consistency Condition | The algebraic integrability condition obeyed by symmetry variations of the effective action. |
| 13 | Anomaly Polynomial | The compact characteristic-class package for perturbative anomalies in even-dimensional QFTs. |
| 14 | Descent Equations | How the anomaly polynomial produces Chern–Simons forms and local anomaly functionals. |

The first six pages are the core graduate route. The last eight pages are the bridge to modern anomaly matching, inflow, topological phases, and symmetry TFT.

## Landmarks

The basic anomaly equation is not a new conservation law. It is a statement that the symmetry variation of the quantum effective action is a local functional that cannot be removed by local counterterms. In background-field notation,

$$
\delta_\lambda W[A]
=\int d^dx\,\lambda^a(x)\mathcal A_a[A]
$$

means that the corresponding Ward identity contains

$$
(D_\mu\langle j^\mu\rangle_A)_a=-\mathcal A_a[A]
$$

when no other charged sources are present. The sign follows the background-source convention used in this volume.

Gauge anomalies and global anomalies play different roles. A gauge transformation is a redundancy in the description. If the path integral is not invariant under it, the theory generally contains unphysical degrees of freedom or violates unitarity/locality. A global symmetry can be anomalous without making the theory inconsistent; the anomaly means the symmetry cannot be gauged, or cannot be realized trivially in the infrared.

The chiral anomaly is the simplest honest example. A massless Dirac fermion coupled vectorially to a background $U(1)$ gauge field has a classical axial symmetry. Quantum mechanically, preserving vector gauge invariance and locality gives, in a common normalization,

$$
\partial_\mu j_5^\mu
=\frac{q^2}{16\pi^2}F_{\mu\nu}\widetilde F^{\mu\nu}
$$

for a charge-$q$ Dirac fermion, up to explicit mass terms and convention-dependent signs. The right-hand side is local, finite, and topological enough to matter globally.

Perturbative anomalies often appear through one-loop diagrams, but they are not “just one-loop accidents.” Their coefficients are protected by consistency conditions and topology. In four dimensions, a chiral gauge theory with left-handed Weyl fermions in representations $R_i$ must satisfy the cubic gauge-anomaly cancellation condition

$$
\sum_i \operatorname{tr}_{R_i}\!\left(T^a\{T^b,T^c\}\right)=0
$$

for all gauge generators, together with any relevant mixed and global anomaly cancellation conditions.

The trace anomaly belongs in this chapter even though it is not always a symmetry anomaly in the same sense as a chiral anomaly. Classically scale-invariant theories can acquire a scale through renormalization, and the trace of the stress tensor can contain beta-function terms,

$$
T^\mu{}_{\mu}=\sum_I \beta^I\mathcal O_I+\text{curvature and contact terms}.
$$

This is the anomaly of scale or Weyl symmetry, and it is one of the cleanest ways renormalization talks to symmetry.

Anomaly polynomials and descent are the compression algorithm for perturbative anomalies. Instead of computing every anomalous Ward identity separately, one packages the data in a characteristic class in two dimensions higher, then descends to a local anomalous variation in the physical dimension. The machinery looks abstract at first; it is the reason anomalies in gauge theory, gravity, and mixed backgrounds share a common language.

Anomaly inflow turns an obstruction into a boundary condition. An anomalous $d$-dimensional theory may be perfectly consistent as the boundary of an invertible $(d+1)$-dimensional bulk whose variation cancels the boundary variation. This viewpoint is essential for ’t Hooft anomalies, discrete anomalies, fermionic phases, higher-form symmetries, and symmetry TFT.

## Common confusions

**Confusion 1: An anomaly means the quantum theory is inconsistent.** Only gauge anomalies are usually fatal. Global anomalies are consistent features of a theory with a global symmetry. They become obstructions only if one tries to gauge the symmetry or realize it trivially in a lower-energy description.

**Confusion 2: An anomaly is any failure of a classical current to be conserved.** Explicit breaking is not an anomaly. If the classical action already violates the symmetry, the nonconservation is ordinary breaking. An anomaly is a quantum obstruction that remains after all allowed local counterterms and regulator choices are accounted for.

**Confusion 3: Anomalies are regularization artifacts and therefore unphysical.** The calculation uses a regulator, but the nonremovable obstruction is physical. Different regulators can move terms among currents and contact terms; they cannot erase the anomaly class.

**Confusion 4: The anomalous current is unique.** Currents can be improved, shifted by local background terms, or changed by Bardeen counterterms. The distinction between consistent and covariant currents is exactly about this scheme dependence. The invariant statement is the anomaly class and its consequences.

**Confusion 5: If an anomaly appears at one loop, higher loops must correct it.** The coefficient of many standard chiral anomalies is fixed once and for all by consistency, topology, and short-distance structure. Higher-loop diagrams can affect definitions of composite operators and currents, but they do not freely renormalize the anomaly coefficient.

**Confusion 6: ’t Hooft anomaly matching says UV and IR Lagrangians must look the same.** It says the global anomaly must match. The infrared may contain massless particles, a topological field theory, spontaneous symmetry breaking, or a boundary realization that carries the same anomaly.

**Confusion 7: Gravitational anomalies are anomalies caused by quantum gravity.** In ordinary QFT, a gravitational anomaly is an anomaly in diffeomorphism or local-Lorentz invariance when the theory is coupled to a background metric or spin connection. It can be studied without quantizing gravity.

## Boundaries

This chapter is not the canonical home of the full Standard Model anomaly-cancellation story. It gives the anomaly principles and the representation-theoretic tests; the Gauge Theories and the Standard Model volume applies them to the Standard Model field content.

This chapter is not a complete course on characteristic classes, index theorems, or spin geometry. The pages on anomaly polynomials and descent introduce the amount needed for QFT. The Mathematical Toolkit and Mathematical and Rigorous QFT volumes carry the theorem-level background.

This chapter is not the full theory of generalized symmetry. It uses higher-form and finite-symmetry backgrounds when anomalies require them, but the canonical treatment of generalized symmetry lives in the Higher-Form and Generalized Symmetries, Non-Invertible and Categorical Symmetries, and Symmetry TFT chapters.

This chapter is not the canonical home of every topological response term. Theta terms, Wess–Zumino terms, Chern–Simons terms, BF terms, and eta invariants are developed in the Topological Terms chapter. Here they appear when they diagnose or cancel anomalies.

## Where to go next

After this chapter, continue to [’t Hooft Anomalies and Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/) to see anomalies used as renormalization-group invariants.

Continue to [Topological Terms](/symmetry-anomalies-topology/topological-terms/) if you want theta terms, Chern–Simons terms, Wess–Zumino terms, WZW terms, and quantized response actions.

Continue to [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) for the modern bulk-boundary formulation of anomalies, especially for generalized and non-invertible symmetries.

Continue to [Model Calculation Library](/symmetry-anomalies-topology/model-calculation-library/) for explicit computations: the ABJ triangle, the Fujikawa Jacobian, Standard Model anomaly cancellation, Chern–Simons level quantization, and WZW terms from inflow.

## References

- S. Adler, “Axial-Vector Vertex in Spinor Electrodynamics,” *Physical Review* 177 (1969). The classic axial anomaly paper.
- J. S. Bell and R. Jackiw, “A PCAC Puzzle: $\pi^0\to\gamma\gamma$ in the Sigma Model,” *Il Nuovo Cimento A* 60 (1969). The companion classic on the axial anomaly and pion decay.
- K. Fujikawa, “Path-Integral Measure for Gauge-Invariant Fermion Theories,” *Physical Review Letters* 42 (1979). The path-integral Jacobian viewpoint.
- J. Wess and B. Zumino, “Consequences of Anomalous Ward Identities,” *Physics Letters B* 37 (1971). The consistency-condition viewpoint.
- L. Alvarez-Gaumé and E. Witten, “Gravitational Anomalies,” *Nuclear Physics B* 234 (1984). The standard reference for gravitational anomalies and index-theorem methods.
- M. Srednicki, *Quantum Field Theory*, especially §§75–77. Chiral gauge anomalies, anomalies in global symmetries, and the fermion path-integral measure.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 30. Triangle anomalies, the measure derivation, gauge anomalies, global anomalies, and anomaly matching.
- S. Coleman, *Aspects of Symmetry*, especially “Soft Pions” and “The Uses of Instantons.” Current algebra, PCAC, chiral Ward identities, instantons, and the $U(1)$ problem.
- A. Bilal, “Lectures on Anomalies,” arXiv:0802.0634. A detailed graduate-level bridge from triangle diagrams and Fujikawa’s method to descent, Wess–Zumino consistency, and anomaly polynomials.
- S. Monnier, “A Modern Point of View on Anomalies,” arXiv:1903.02828. A concise modern introduction to anomaly field theories and inflow.

## Version history

- 2026-06-18: Initial polished draft. Replaced placeholder overview with reading path, landmarks, anomaly taxonomy, boundaries, and handoffs to anomaly matching, topological terms, and symmetry TFT.
