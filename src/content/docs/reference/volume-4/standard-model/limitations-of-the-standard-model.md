---
title: "Limitations of the Standard Model"
description: "Explains what the minimal renormalizable Standard Model does not explain, including neutrino masses, dark matter, baryogenesis, gravity, flavor, naturalness, strong CP, and EFT corrections."
sidebar:
  label: "Limitations of the Standard Model"
  order: 8
level: Graduate
status: "Polished draft"
source: "Srednicki §§87–94; Schwartz Chs. 29–31; Burgess Ch. 9; Weinberg Vol. II electroweak and Standard Model material."
topics:
  - Standard Model limitations
  - neutrino masses
  - dark matter
  - baryogenesis
  - hierarchy problem
  - strong CP problem
  - Standard Model EFT
canonicalTopics:
  - standard-model-limitations
  - standard-model-effective-field-theory
  - neutrino-mass-origin
  - dark-matter-problem
  - electroweak-hierarchy-problem
  - strong-cp-problem
researchStatus:
  established:
    - "The minimal renormalizable Standard Model is internally consistent after anomaly cancellation and accurately describes a vast range of nongravitational particle data, but it is not a complete theory of all observed physics."
  active:
    - "The origin of neutrino masses, dark matter, baryon asymmetry, flavor hierarchies, the smallness of strong CP violation, the Higgs scale, and quantum gravity remain open theoretical problems."
---

## Summary

The Standard Model is both spectacularly successful and visibly incomplete. Those statements are not in tension. A theory can be an excellent low-energy quantum field theory and still fail to explain why its parameters have their values, what dark matter is, how neutrinos get mass, or how gravity is quantized.

The clean way to say this is:

$$
\mathcal L_{\rm nature}
\;\longrightarrow\;
\mathcal L_{\rm SM}^{(d\le4)}
+
\frac{1}{\Lambda}\sum_i c_i^{(5)}\mathcal O_i^{(5)}
+
\frac{1}{\Lambda^2}\sum_i c_i^{(6)}\mathcal O_i^{(6)}
+\cdots
$$

at energies well below whatever new scales have been integrated out. The first term is the renormalizable Standard Model. The higher-dimensional operators encode possible low-energy traces of physics not included in the minimal field content.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Standard Model limitations map](/figures/gauge-theories-standard-model/standard-model-limitations-map.svg)

<figcaption>

The minimal renormalizable Standard Model is the leading low-energy gauge theory of known particle interactions. Its limitations split into missing ingredients, unexplained structures, and effective-field-theory corrections. These are not equally severe, but together they show where the next layer of theory must enter.

</figcaption>
</figure>

This page is not a beyond-Standard-Model catalog. It is a diagnostic page: what exactly does the minimal theory explain, what does it merely parametrize, and what does it omit?

## Prerequisites

You should know the [Standard Model Lagrangian](/gauge-theories-standard-model/standard-model/standard-model-lagrangian/), [Parameter Counting](/gauge-theories-standard-model/standard-model/parameter-counting/), [Accidental Symmetries](/gauge-theories-standard-model/standard-model/accidental-symmetries/), [Mass Spectrum and Couplings](/gauge-theories-standard-model/standard-model/mass-spectrum-and-couplings/), and [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/).

The default phrase **minimal renormalizable Standard Model** means the dimension-four theory with gauge group locally described by

$$
SU(3)_c\times SU(2)_L\times U(1)_Y,
$$

one Higgs doublet

$$
H\sim(\mathbf1,\mathbf2)_{1/2},
$$

and three generations of the usual chiral fermions, but no right-handed neutrinos and no higher-dimensional operators.

## What counts as a limitation?

Different limitations have different logical status. Mixing them together is how otherwise sensible conversations about the Standard Model become fog machines.

| Type | Meaning | Example |
|---|---|---|
| Missing ingredient | The minimal field content or dimension-four Lagrangian cannot describe an observed phenomenon. | Neutrino masses in the minimal renormalizable theory. |
| Unexplained parameter | The theory contains the parameter but does not predict its value. | Fermion masses, CKM angles, Higgs quartic coupling. |
| Naturalness question | The low-energy value is technically allowed but sensitive to possible high-scale physics. | The Higgs mass parameter. |
| Approximate empirical fact | The theory allows something small, but gives no reason it should be so small. | The effective QCD angle $\bar\theta$. |
| Missing sector | The theory is not designed to include a known part of nature. | Dynamical gravity. |
| EFT expectation | The dimension-four theory is the leading term, not the whole expansion. | Weinberg operator and dimension-six operators. |

The distinction matters. Neutrino masses require extending the minimal renormalizable theory. Flavor hierarchies do not by themselves contradict it; they are unexplained inputs. Naturalness is not a mathematical inconsistency; it is a question about why the effective parameters are stable or small compared with possible ultraviolet thresholds.

## Neutrino masses

The minimal renormalizable Standard Model has no right-handed neutrino field $\nu_R$. With the field content listed in [Standard Model Field Content](/gauge-theories-standard-model/standard-model/standard-model-field-content/), there is no gauge-invariant dimension-four Dirac neutrino Yukawa term analogous to

$$
-\bar L_LY_eHe_R+\text{h.c.}
$$

The observed phenomenon of neutrino oscillation requires nonzero neutrino mass splittings. In low-energy Standard-Model language, the most economical repair is the dimension-five Weinberg operator,

$$
\mathcal L_5
=
-\frac{1}{2\Lambda}\kappa_{ij}(L_iH)(L_jH)+\text{h.c.},
$$

where the $SU(2)_L$ indices are contracted antisymmetrically. After electroweak symmetry breaking,

$$
M_\nu\sim \frac{v^2}{\Lambda}\kappa.
$$

The precise normalization depends on how the operator is written, but the conclusion does not: neutrino masses are not part of the minimal renormalizable Standard Model. They point to either higher-dimensional operators, sterile fermions, a seesaw mechanism, radiative mass generation, or some other extension.

:::note[What this does and does not prove]
Neutrino masses do not force a unique ultraviolet completion. They force the minimal renormalizable theory to be enlarged. The Weinberg operator is deliberately agnostic about how that enlargement happens.
:::

## Dark matter

The Standard Model has no particle with the right combination of stability, abundance, neutrality, and cold/nonrelativistic behavior to serve as the dominant dark matter component. Massive neutrinos are part of the known particle spectrum once the minimal theory is extended, but they do not play the role required of the dominant cold dark matter in structure formation.

This limitation is not a small missing interaction term inside $\mathcal L_{\rm SM}^{(d\le4)}$. It is a missing sector or missing state. A dark-matter completion might add a stable particle, a hidden gauge sector, an axion, a sterile state, a topological relic, or something less particle-like. The Standard Model tells us how such a sector may couple to known fields through portals, but it does not supply the sector itself.

Common portal operators include schematic structures such as

$$
H^\dagger H\,\mathcal O_{\rm dark},
\qquad
B_{\mu\nu}X^{\mu\nu},
\qquad
\bar L H\,N,
$$

when the corresponding new fields exist. These are not Standard Model operators alone; they are examples of how new degrees of freedom can communicate with the Standard Model.

## Baryon asymmetry

The visible universe contains far more matter than antimatter. A mechanism for generating such an asymmetry must violate baryon number, violate C and CP, and occur out of thermal equilibrium. The Standard Model contains ingredients that look suggestive but are not enough in the minimal theory.

First, baryon number is anomalous in the electroweak sector. Nonperturbative electroweak processes violate

$$
B+L
$$

while preserving

$$
B-L
$$

for the usual Standard Model fermion content. Second, the CKM matrix contains CP violation. But the minimal electroweak theory does not provide a strong enough baryogenesis mechanism with its observed Higgs-sector structure and CKM CP violation. In modern language, baryogenesis is a signpost toward additional CP violation, additional dynamics, a first-order phase transition in an extended scalar sector, leptogenesis, or some other early-universe ingredient.

This is a useful example of a subtle limitation. The Standard Model does not conserve baryon number exactly, so “baryon number is impossible to violate” is wrong. But the amount and kind of baryon-number violation and CP violation in the minimal theory do not explain the cosmological asymmetry.

## The flavor puzzle

The Standard Model explains how fermion masses and mixings enter:

$$
M_u=\frac{v}{\sqrt2}Y_u,
\qquad
M_d=\frac{v}{\sqrt2}Y_d,
\qquad
M_e=\frac{v}{\sqrt2}Y_e.
$$

It does not explain why the eigenvalues and mixing angles have their observed pattern. The Yukawa matrices are allowed by gauge symmetry but not predicted by it.

The puzzle has several faces:

- the large hierarchy among charged-fermion masses;
- the smallness of most CKM mixing angles;
- the existence of an irreducible CKM CP phase;
- the qualitative difference between quark mixing and lepton mixing;
- the smallness of neutrino masses relative to charged-fermion masses;
- the replication of three generations.

None of these facts is inconsistent with the Standard Model. They are simply not explained by the gauge principle plus the minimal Higgs sector. The Standard Model turns flavor into matrices. It does not explain the matrices. Rude, but efficient.

## The hierarchy and naturalness problem

The Higgs mass parameter is special because the operator

$$
H^\dagger H
$$

has dimension two. Relevant scalar operators are sensitive to threshold corrections from heavy physics. If a heavy field of mass $M$ couples to the Higgs, matching at the scale $M$ can naturally generate corrections of the schematic form

$$
\delta m_H^2\sim \frac{\lambda_{\rm heavy}}{16\pi^2}M^2,
$$

up to signs, group factors, and scheme-dependent details.

The physical issue is not that a particular cutoff regulator produces a quadratic divergence. Regulators are bookkeeping devices. The deeper issue is that scalar mass parameters are relevant couplings, and heavy thresholds generically feed into them unless protected by a symmetry, dynamics, or special structure.

There are several possible attitudes:

| Attitude | Core idea |
|---|---|
| Symmetry protection | Supersymmetry, shift symmetry, compositeness, or related mechanisms protect the Higgs scale. |
| Dynamical selection | Vacuum selection, environmental reasoning, or cosmological dynamics explains the low scale. |
| No nearby solution | The Higgs mass is simply a parameter of the low-energy effective theory. |
| Modified ultraviolet structure | The high-energy completion does not generate the naive dangerous thresholds. |

The hierarchy problem is therefore not a theorem that new particles must appear at a specific scale. It is a sharp question about why the electroweak scale is small compared with any much larger physical thresholds that couple to the Higgs.

## Strong CP problem

QCD allows the topological term

$$
\mathcal L_\theta
=
\frac{\theta g_s^2}{32\pi^2}
G^A_{\mu\nu}\widetilde G^{A\mu\nu}.
$$

After including quark mass phases, the physical parameter is

$$
\bar\theta
=
\theta+\arg\det(Y_uY_d).
$$

A generic value of $\bar\theta$ would violate CP in strong interactions. Empirically, strong CP violation is extremely small. The Standard Model can accommodate a small $\bar\theta$ by choosing it small, but it does not explain why it is small.

The standard proposed resolutions include an anomalous Peccei–Quinn symmetry and axion, a massless up quark scenario, or ultraviolet CP/parity mechanisms. The first is the most widely used modern template, but the page’s main point is simpler: the smallness of $\bar\theta$ is an unexplained parameter fact in the minimal theory.

## Gravity and spacetime

The Standard Model is a quantum field theory on a spacetime background. It does not include dynamical quantum gravity. Coupling the Standard Model to a classical metric is straightforward at the level of effective field theory, but that is not the same as a complete quantum theory of spacetime.

At low energies, gravity can also be treated as an effective field theory. The leading action contains the Einstein–Hilbert term plus higher-curvature operators,

$$
S_{\rm grav}
=
\int d^4x\sqrt{-g}\left[\frac{M_{\rm Pl}^2}{2}R-\Lambda_{\rm cc}+c_1R^2+c_2R_{\mu\nu}R^{\mu\nu}+\cdots\right].
$$

The Standard Model can be placed inside this framework, but the result is not a UV-complete theory of quantum gravity. This limitation belongs partly to this volume and partly to the Spacetime, Gravity, and Holography volume.

## Vacuum structure and high-scale extrapolation

The Standard Model parameters run with scale. If one extrapolates the renormalized couplings far above experimentally accessible energies, questions arise about the Higgs quartic coupling, electroweak vacuum stability, Landau poles in abelian couplings, and possible thresholds. These questions depend on precision inputs and on assuming no new physics over many decades of energy.

The key conceptual lesson is modest: the Standard Model is not just a classical formula. It is a renormalized quantum field theory with scale-dependent couplings. Its apparent high-scale behavior should be read through the lens of effective field theory, threshold matching, and uncertainty about new degrees of freedom.

## Standard Model as an effective theory

The effective-field-theory expansion organizes many limitations without guessing the ultraviolet completion. With Standard Model fields only, the leading correction is dimension five:

$$
\mathcal O_5=(LH)(LH),
$$

which gives Majorana neutrino masses. At dimension six, many new operator classes appear, including corrections to electroweak precision observables, flavor-changing processes, dipole moments, four-fermion interactions, and baryon-number violation.

A schematic expansion is

$$
\mathcal L_{\rm SMEFT}
=
\mathcal L_{\rm SM}^{(d\le4)}
+
\frac{1}{\Lambda}\mathcal L^{(5)}
+
\frac{1}{\Lambda^2}\mathcal L^{(6)}
+\cdots.
$$

This is not a sign of defeat. It is the modern meaning of a successful low-energy theory. The Standard Model is the first line of the expansion. The open question is what determines the coefficients beyond it.

## Common pitfalls

**Pitfall 1: Treating every limitation as a contradiction.** Neutrino masses contradict the minimal renormalizable field content. Flavor hierarchies do not contradict it; they are unexplained inputs.

**Pitfall 2: Saying “the Standard Model has no baryon violation.”** Perturbatively at dimension four, baryon number is accidental. Nonperturbatively in the electroweak theory, $B+L$ is anomalous.

**Pitfall 3: Confusing the hierarchy problem with a regulator artifact.** Quadratic divergences depend on how the calculation is regulated. Sensitivity of scalar masses to physical heavy thresholds is the sharper statement.

**Pitfall 4: Assuming neutrino mass implies one specific model.** Right-handed neutrinos are elegant, but the low-energy fact is captured by an operator or mass matrix. The ultraviolet explanation is not unique.

**Pitfall 5: Thinking EFT means “anything goes.”** EFT is highly constrained by gauge symmetry, Lorentz invariance, field content, power counting, and data. It is a disciplined ignorance expansion. Which, honestly, is most of science on a good day.

## Exercises

### Exercise 1: Classify the limitation

Classify each item as a missing ingredient, unexplained parameter, naturalness question, or missing sector: neutrino masses, dark matter, fermion mass hierarchy, Higgs hierarchy problem, quantum gravity.

<details><summary><strong>Solution</strong></summary>

A useful classification is:

| Item | Classification |
|---|---|
| Neutrino masses | Missing ingredient in the minimal renormalizable theory. |
| Dark matter | Missing sector or missing state. |
| Fermion mass hierarchy | Unexplained parameter pattern. |
| Higgs hierarchy problem | Naturalness question about sensitivity to high-scale thresholds. |
| Quantum gravity | Missing sector: the Standard Model is not a theory of dynamical spacetime. |

The categories are not sacred, but they prevent a common confusion: not every unsolved question has the same logical status.

</details>

### Exercise 2: Estimate the Weinberg scale

Suppose a typical neutrino mass is $m_\nu\sim v^2/\Lambda$ and take $v\sim246\,\mathrm{GeV}$. Estimate $\Lambda$ for $m_\nu\sim0.05\,\mathrm{eV}$ and an order-one coefficient.

<details><summary><strong>Solution</strong></summary>

Convert

$$
0.05\,\mathrm{eV}
\sim
5\times10^{-11}\,\mathrm{GeV}.
$$

Then

$$
\Lambda
\sim
\frac{v^2}{m_\nu}
\sim
\frac{(246\,\mathrm{GeV})^2}{5\times10^{-11}\,\mathrm{GeV}}
\sim
1.2\times10^{15}\,\mathrm{GeV}.
$$

The estimate changes with the coefficient and normalization of the operator, but it shows why the Weinberg operator naturally points to very high scales when its coefficient is order one.

</details>

### Exercise 3: Why small Yukawas are technically allowed

Explain why a tiny electron Yukawa coupling is not an internal inconsistency of the Standard Model, even though it remains unexplained.

<details><summary><strong>Solution</strong></summary>

A small Yukawa coupling is a perfectly valid dimensionless parameter. In fact, setting a Yukawa coupling to zero usually increases chiral flavor symmetry, so small Yukawa couplings can be technically natural in the sense that radiative corrections are proportional to symmetry-breaking parameters.

The puzzle is not consistency. The puzzle is origin: the Standard Model does not explain why the observed Yukawa eigenvalues span such a large range or why the mixing matrices have their observed structure.

</details>

### Exercise 4: What does $\bar\theta$ know about Yukawas?

Why is the physical strong CP parameter not just the bare $\theta$ appearing in $G\widetilde G$?

<details><summary><strong>Solution</strong></summary>

Chiral rotations of quark fields can move phases between the quark mass matrices and the topological $\theta$ term because the path-integral measure is anomalous. As a result, the invariant combination is

$$
\bar\theta=\theta+\arg\det(Y_uY_d),
$$

up to convention-dependent sign choices. The physical CP-violating parameter therefore depends both on the gauge topological angle and on the phase of the quark mass determinant.

</details>

## Relations to other pages

- [Standard Model Lagrangian](/gauge-theories-standard-model/standard-model/standard-model-lagrangian/) gives the dimension-four theory whose limitations are being diagnosed.
- [Parameter Counting](/gauge-theories-standard-model/standard-model/parameter-counting/) explains which constants the minimal theory leaves as inputs.
- [Accidental Symmetries](/gauge-theories-standard-model/standard-model/accidental-symmetries/) explains why baryon and lepton number appear at dimension four and how anomalies and higher-dimensional operators qualify that statement.
- [Weinberg Operator](/gauge-theories-standard-model/flavor-neutrinos/weinberg-operator/) gives the leading Standard-Model-field operator for Majorana neutrino masses.
- [Theta Angle and Strong CP Problem](/gauge-theories-standard-model/qcd/theta-angle-and-strong-cp-problem/) develops the QCD side of the strong CP problem.
- [Anomalies and Consistency of the Standard Model](/gauge-theories-standard-model/sm-anomalies-consistency/) explains why the Standard Model chiral field content is quantum-mechanically consistent.

## Research status

The existence of limitations is established; their resolutions are not. Neutrino masses require extending the minimal renormalizable theory, but the ultraviolet mechanism is open. Dark matter and baryogenesis point beyond the minimal particle content and interactions. The hierarchy, strong CP, and flavor problems are explanatory problems, not direct inconsistencies. The EFT viewpoint is settled: higher-dimensional operators are the systematic language for low-energy traces of heavy physics.

## Where to go next

Continue to [Anomalies and Consistency of the Standard Model](/gauge-theories-standard-model/sm-anomalies-consistency/). The previous pages assembled what the Standard Model is; the next chapter explains why its chiral gauge structure is consistent as a quantum gauge theory.

For a scale-first perspective, later continue to the Precision and SMEFT chapter or to the Renormalization, RG, and EFT volume.

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, especially the Standard Model, neutrino-mass, instanton, theta-vacuum, and quark-theta sections.
- Schwartz, *Quantum Field Theory and the Standard Model*, especially the weak-interaction, CP-violation, anomaly, precision-test, and Standard Model chapters.
- Burgess, *Introduction to Effective Field Theory*, especially the Standard Model as an effective theory, dimension-five and dimension-six operators, and naturalness discussion.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, for the Standard Model and electroweak theory in a broad field-theoretic setting.
- Coleman, *Aspects of Symmetry*, especially the lectures on symmetries, renormalization, and hidden symmetry.

## Version history

- **2026-06-19:** Initial page distinguishing observational incompleteness, unexplained parameters, naturalness questions, strong CP, baryogenesis, dark matter, gravity, and EFT corrections.
