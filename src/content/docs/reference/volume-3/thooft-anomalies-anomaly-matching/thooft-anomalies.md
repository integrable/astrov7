---
title: "’t Hooft Anomalies"
description: "Defines ’t Hooft anomalies as background-field obstructions to gauging global symmetries and explains their equivalent Ward-identity, counterterm, and inflow viewpoints."
sidebar:
  label: "’t Hooft Anomalies"
  order: 1
level: Advanced
status: "Polished draft"
source: "’t Hooft anomaly matching; background-field gauging; Wess–Zumino consistency; anomaly inflow; Srednicki §§75–77; Schwartz Ch. 30; Weinberg Vol. II; Gaiotto–Kapustin–Seiberg–Willett."
topics:
  - thooft anomalies
  - global symmetries
  - background fields
  - obstruction to gauging
  - anomaly inflow
  - counterterm ambiguity
  - Ward identities
canonicalTopics:
  - thooft-anomaly
  - background-field-anomaly
  - obstruction-to-gauging
  - anomaly-class
  - inflow
researchStatus:
  established:
    - "A ’t Hooft anomaly is an invariant obstruction to gauging a global symmetry, equivalently a nontrivial anomalous transformation of the background-field partition function."
    - "Local counterterms can change the representative of an anomaly but not its cohomology or invertible-field-theory class."
  active:
    - "For generalized, non-invertible, fermionic, crystalline, and subsystem symmetries, the same obstruction idea persists but the correct notion of background field and gauging is still an active organizing language."
---

## Summary

A **’t Hooft anomaly** is an anomaly of a **global symmetry**, not of a dynamical gauge redundancy. It says that the theory can be coupled to background fields for the symmetry, but the resulting background-field partition function cannot be made fully invariant under background gauge transformations by any choice of local counterterms.

For a theory $\mathcal T$ with global symmetry $G$, couple $G$ to a nondynamical background field $A$ and write the generating functional as $Z[A]$. A finite background gauge transformation $g$ may act as

$$
Z[A^g]=\exp\!\left(2\pi i\,\mathcal A_g[A]\right)Z[A].
$$

If the phase $\mathcal A_g[A]$ can be removed by a local counterterm depending only on the background fields, then it is a scheme artifact. If it cannot, the global symmetry has a ’t Hooft anomaly.

Equivalently,

$$
\text{’t Hooft anomaly}
=
\text{obstruction to gauging a global symmetry}.
$$

This obstruction is allowed. It does **not** mean that the original theory is inconsistent. It means that trying to promote the global symmetry to a dynamical gauge symmetry would fail unless the anomaly is cancelled by extra degrees of freedom or by anomaly inflow from one higher dimension.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing a global symmetry coupled to a background field, a background gauge transformation test, and the two outcomes: removable counterterm or nontrivial obstruction to gauging.](/figures/symmetry-anomalies-topology/thooft-anomaly-background-obstruction.svg)

<figcaption>

A ’t Hooft anomaly is detected only after coupling a global symmetry to background fields. If background gauge invariance can be restored by local counterterms, the anomaly representative was removable. If not, the obstruction is intrinsic and must be matched in the infrared.

</figcaption>
</figure>

## Prerequisites

You should know [What Is an Anomaly?](/symmetry-anomalies-topology/anomalies/what-is-an-anomaly/), [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/), [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/), and [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/).

It is especially important to keep the distinction from [Perturbative Gauge Anomalies](/symmetry-anomalies-topology/anomalies/perturbative-gauge-anomalies/) in mind: gauge anomalies of dynamical gauge redundancies are fatal, while ’t Hooft anomalies of global symmetries are consistent but constraining.

## Core idea

A global symmetry is tested by asking whether the theory can be consistently placed in arbitrary background fields for that symmetry. In ordinary language this means introducing sources for the symmetry current. In geometric language it means allowing $G$ bundles and connections, or their discrete or higher-form analogues, on spacetime.

The test has three layers.

| Layer | Question | Outcome |
|---|---|---|
| Background coupling | Can we define $Z[A]$? | Usually yes for a candidate global symmetry. |
| Background gauge invariance | Is $Z[A^g]=Z[A]$? | Maybe only up to a local phase. |
| Counterterm equivalence | Can the phase be removed locally? | If no, the anomaly is genuine. |

The point is not that the background field $A$ is physical by itself. The point is that $A$ is a diagnostic probe. If the global symmetry were truly gaugeable, summing over $A$ would make sense. A nontrivial ’t Hooft anomaly is precisely the obstruction to doing that sum as a standalone $d$-dimensional theory.

## Setup and conventions

We work in the conventions of this volume. For an ordinary continuous symmetry, a Hermitian background gauge field has

$$
D=d-iA,
\qquad
F=dA-iA\wedge A.
$$

For an infinitesimal background gauge transformation with parameter $\alpha$,

$$
\delta_\alpha A=D\alpha,
\qquad
\delta_\alpha F=i[\alpha,F].
$$

A local perturbative anomaly can be written in descent form as

$$
\delta_\alpha \log Z[A]
=2\pi i\int_{M_d} I_d^{(1)}(\alpha,A),
$$

where $I_d^{(1)}$ is defined modulo the variation of local counterterms. For a finite or global anomaly, the anomaly may instead be a phase of the partition function under a large transformation or on a nontrivial background bundle:

$$
Z[A^g]=\exp\!\left(2\pi i\,\mathcal A_g[A]\right)Z[A].
$$

Here $\mathcal A_g[A]$ is defined modulo integers, because only its exponential is physical.

:::note[Convention-sensitive source note]
Some references define gauge transformations with the opposite sign, use anti-Hermitian connections, or absorb $2\pi$ factors into characteristic classes. Compare the transformation law of $A$ and the normalization of $\delta\log Z$, not just the printed coefficient in a current-divergence formula.
:::

## Definition by background fields

Let $\mathcal T$ be a $d$-dimensional QFT with global symmetry $G$. To probe $G$, place the theory on a spacetime $M_d$ and couple it to background $G$ data $A$. For a continuous ordinary symmetry, $A$ is a background gauge connection. For a finite symmetry, $A$ is a background flat bundle. For a higher-form symmetry, $A$ is a higher-form gauge field. For a symmetry involving fermion parity, reflection, or time reversal, $A$ may include spin, Pin, or orientation-reversing structure.

The background-field partition function is

$$
Z_{\mathcal T}[A].
$$

A non-anomalous global symmetry has a scheme in which

$$
Z_{\mathcal T}[A^g]=Z_{\mathcal T}[A]
$$

for every allowed background gauge transformation $g$.

A ’t Hooft anomaly is present when the best possible transformation law is

$$
Z_{\mathcal T}[A^g]
=\exp\!\left(2\pi i\,\mathcal A_g[A]\right)Z_{\mathcal T}[A],
$$

and no local background counterterm removes $\mathcal A_g[A]$ for all $A$ and all $g$.

The phrase **local background counterterm** matters. We are allowed to redefine the scheme by multiplying the partition function by

$$
\exp\!\left(2\pi i\int_{M_d} B[A]\right),
$$

where $B[A]$ is a local functional of the background fields, such as a Chern–Simons-like term, theta-like term, discrete Dijkgraaf–Witten term, or curvature counterterm when appropriate. This changes the anomaly representative by

$$
\mathcal A_g[A]
\longmapsto
\mathcal A_g[A]
+
\int_{M_d}B[A^g]-\int_{M_d}B[A].
$$

The anomaly is the equivalence class that remains after this freedom is divided out.

## The cocycle condition

The anomalous phases cannot be arbitrary. Applying two background gauge transformations in succession must be associative. Schematically, if $A\mapsto A^g$ is the convention for the group action, the phases obey a cocycle condition of the form

$$
\mathcal A_{g_1g_2}[A]
=
\mathcal A_{g_1}[A^{g_2}]+\mathcal A_{g_2}[A]
\quad \mathrm{mod}\;\mathbb Z.
$$

A local counterterm shifts $\mathcal A$ by a coboundary. Thus the genuine anomaly is a cohomology class, or more generally an invertible-field-theory class.

The infinitesimal version is the Wess–Zumino consistency condition. If

$$
\delta_\alpha \log Z[A]=2\pi i\int_{M_d}I_d^{(1)}(\alpha,A),
$$

then the commutator of two transformations must reproduce the Lie algebra:

$$
[\delta_{\alpha_1},\delta_{\alpha_2}]\log Z[A]
=
\delta_{i[\alpha_1,\alpha_2]}\log Z[A],
$$

with the sign fixed by the Hermitian-connection convention above.

This is why consistent anomalies are not just arbitrary violations of Ward identities. They satisfy integrability conditions because they come from the variation of a generating functional.

## Ward-identity viewpoint

In flat space and near the trivial background, a ’t Hooft anomaly often appears as an anomalous contact term in a Ward identity. Suppose $J_a^\mu$ is the current for a continuous global symmetry. In the absence of backgrounds, the current may be conserved as an operator equation away from contact points:

$$
\partial_\mu J_a^\mu=0.
$$

After coupling to background fields, the conservation law can become

$$
D_\mu J_a^\mu
=\mathcal I_a[A],
$$

where $\mathcal I_a[A]$ is a local expression built from background field strengths and curvature. For example, for four-dimensional left-handed Weyl fermions, cubic flavor anomalies are controlled by symmetric traces of the form

$$
k_{abc}=\operatorname{Tr}_{\text{left Weyl}}(T_a\{T_b,T_c\}).
$$

The exact component coefficient depends on current normalization, generator normalization, chirality convention, and whether the connection is Hermitian or anti-Hermitian. The invariant information is the corresponding anomaly class.

There is a useful slogan:

$$
\text{current nonconservation in backgrounds}
\quad\leftrightarrow\quad
\text{background gauge non-invariance of } Z[A].
$$

But the background-field statement is more robust. It handles contact terms, global transformations, finite symmetries, curved manifolds, higher-form symmetries, and topological sectors more cleanly than a naive current-divergence equation.

## Gauge anomaly versus ’t Hooft anomaly

The same formula can be fatal or useful depending on what is being transformed.

If $A$ is a **dynamical gauge field**, then gauge transformations are redundancies. The path integral must divide by them, and physical states must obey gauge constraints. A nonzero gauge anomaly means the redundancy is not consistently implemented. The theory is sick unless the anomaly cancels.

If $A$ is a **background field for a global symmetry**, then background gauge transformations are a way of expressing the global symmetry locally in source space. Non-invariance under these transformations is allowed. It means that gauging the global symmetry would be obstructed, and therefore that the original global-symmetry realization contains robust information.

A compact comparison is:

| Anomaly type | Transformation acts on | Consequence |
|---|---|---|
| Gauge anomaly | Dynamical gauge redundancy | Inconsistent unless cancelled. |
| ’t Hooft anomaly | Background field for global symmetry | Consistent, but symmetry cannot be gauged as a standalone operation. |
| Explicit breaking | The action is not invariant even before quantization | Symmetry is not exact; no matching required except for preserved subgroups. |
| Spontaneous breaking | The theory is symmetric but the state is not | Symmetry exists; anomalies still constrain the low-energy theory. |

This comparison is the fastest way to avoid most anomaly folklore disasters.

## Simple examples

### Free Weyl fermions with flavor symmetry

Take massless left-handed Weyl fermions transforming in a representation $R$ of a global flavor group $G$. Coupling $G$ to a background field exposes a perturbative flavor anomaly proportional to invariant traces in $R$. If $G$ remains global, this is a ’t Hooft anomaly. If one tries to gauge $G$, the same anomaly becomes a gauge anomaly and must cancel.

This example is pedagogically clean because the microscopic fermions directly compute the anomaly. It is not the deep part of anomaly matching yet. The deep part is that any interacting infrared description must reproduce the same anomaly without necessarily containing the same fermions.

### QCD-like chiral flavor symmetry

Massless QCD with $N_f$ Dirac quarks has chiral flavor symmetry in a simplified local description,

$$
SU(N_f)_L\times SU(N_f)_R\times U(1)_B,
$$

up to important discrete quotients and possible background-field refinements. The color gauge anomaly cancels because the theory is vector-like with respect to color. But the chiral flavor symmetry has ’t Hooft anomalies when coupled to flavor backgrounds.

At low energies, if chiral symmetry spontaneously breaks as

$$
SU(N_f)_L\times SU(N_f)_R
\longrightarrow
SU(N_f)_V,
$$

then the Goldstone bosons must carry the anomaly. They do so through the Wess–Zumino–Witten term. The coefficient is fixed by the number of colors $N_c$.

:::note[Convention-sensitive source note]
The full global symmetry of QCD-like theories is not always the naive product group written above. Quotients by common centers, baryon-number normalization, spin structure, and background bundle choices affect refined anomaly statements. The product-group formula is a local first pass, not the final global-form theorem.
:::

### Discrete and global anomalies

Not every ’t Hooft anomaly is visible in an infinitesimal current divergence. A finite symmetry can have an anomaly detected by putting the theory on a nontrivial background bundle. A time-reversal or reflection anomaly can require unorientable manifolds and Pin structures. A global anomaly can show up only under a large transformation disconnected from the identity.

In these cases the anomaly is often better described as a phase of the partition function or as a one-higher-dimensional invertible theory. There may be no useful local polynomial $I_{d+2}$ that captures the whole story.

## Inflow viewpoint

A powerful way to define an anomaly is to find a $(d+1)$-dimensional invertible bulk theory whose boundary variation cancels the anomalous variation of the $d$-dimensional theory.

If $X_{d+1}$ has boundary $\partial X_{d+1}=M_d$, then the combined partition function

$$
Z_{\rm bulk}[A]Z_{\mathcal T}[A]
$$

can be gauge invariant even if $Z_{\mathcal T}[A]$ alone is not. In this language,

$$
\text{anomaly of }\mathcal T
=
\text{bulk invertible response whose boundary is }\mathcal T.
$$

For local perturbative anomalies, the bulk action is often a Chern–Simons descendant. For discrete, fermionic, or global anomalies, it may be an eta invariant, bordism invariant, or other invertible topological field theory.

This viewpoint explains why a ’t Hooft anomaly is not removable by changing the microscopic regulator. Removing it would require eliminating a bulk topological response class, not merely changing a local formula.

## Common pitfalls

**Calling every anomalous current divergence a ’t Hooft anomaly.** A ’t Hooft anomaly is an obstruction for an exact global symmetry. If the putative symmetry is explicitly broken or broken by a dynamical gauge-field effect to a smaller exact subgroup, the anomaly should be stated for the exact subgroup and its backgrounds.

**Forgetting counterterms.** The expression multiplying $\alpha(x)$ in a Ward identity is not always the anomaly class. Local counterterms can move anomaly terms between currents or between bulk and boundary descriptions.

**Confusing background and dynamical fields.** A gauge anomaly for a dynamical gauge field is inconsistent. The same-looking anomaly for a background flavor field can be a perfectly healthy ’t Hooft anomaly.

**Ignoring global form.** The Lie algebra of the symmetry does not determine all allowed background bundles. Different global forms can have different anomalies, especially when centers, one-form symmetries, spin structures, or discrete quotients are involved.

**Assuming anomaly polynomials see everything.** Anomaly polynomials capture local perturbative anomalies. They do not by themselves capture all global, torsion, finite-group, spin, Pin, or non-invertible anomaly data.

## Relations to other pages

- [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/) explains the source-coupling setup used to define $Z[A]$.
- [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/) explains why summing over backgrounds is the operation obstructed by a ’t Hooft anomaly.
- [What Is an Anomaly?](/symmetry-anomalies-topology/anomalies/what-is-an-anomaly/) gives the broader anomaly taxonomy before this page specializes to global-symmetry anomalies.
- [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/) and [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/) compute local perturbative representatives of anomaly classes.
- [Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/) explains the main consequence: the same anomaly class must appear in the infrared.

## Research status

The background-field and obstruction-to-gauging definition of ordinary ’t Hooft anomalies is textbook-standard. The local perturbative part is well understood through anomaly polynomials, descent, Wess–Zumino consistency, and inflow.

The active frontier is not the basic principle, but its generality. Modern work extends the same obstruction language to higher-form symmetries, higher groups, finite and fermionic symmetries, crystalline symmetries, subsystem symmetries, non-invertible symmetries, symmetry TFT, and relative QFT. In those settings, the phrase “background field” can mean more than an ordinary connection, and “gauging” can mean a categorical or topological operation rather than an elementary path integral over one-form gauge fields.

## Exercises

### Exercise 1: Counterterm shift

Suppose

$$
Z[A^g]=e^{2\pi i\mathcal A_g[A]}Z[A].
$$

Redefine

$$
Z'[A]=e^{2\pi i\int_{M_d}B[A]}Z[A].
$$

Find the anomaly phase $\mathcal A'_g[A]$ of $Z'[A]$.

<details>
<summary><strong>Solution</strong></summary>

Compute directly:

$$
Z'[A^g]
=e^{2\pi i\int B[A^g]}Z[A^g]
=e^{2\pi i\int B[A^g]}e^{2\pi i\mathcal A_g[A]}Z[A].
$$

Since

$$
Z[A]=e^{-2\pi i\int B[A]}Z'[A],
$$

we get

$$
Z'[A^g]
=e^{2\pi i\left(\mathcal A_g[A]+\int B[A^g]-\int B[A]\right)}Z'[A].
$$

Therefore

$$
\mathcal A'_g[A]
=
\mathcal A_g[A]+\int B[A^g]-\int B[A]
\quad \mathrm{mod}\;\mathbb Z.
$$

This is why the anomaly is an equivalence class, not a single formula.

</details>

### Exercise 2: Gauge or global?

A set of Weyl fermions has a nonzero cubic anomaly coefficient for a symmetry $G$. Explain the different consequences when $G$ is a dynamical gauge group and when $G$ is only a global flavor symmetry.

<details>
<summary><strong>Solution</strong></summary>

If $G$ is dynamical, gauge transformations are redundancies. A nonzero cubic gauge anomaly means the gauge constraint is inconsistent and the theory cannot be a standalone quantum gauge theory unless additional fields or sectors cancel the anomaly.

If $G$ is global, the same coefficient is a ’t Hooft anomaly. The theory is consistent, but the symmetry cannot be gauged as an ordinary $d$-dimensional operation. The anomaly becomes useful because it must be reproduced by every symmetry-preserving infrared description.

</details>

### Exercise 3: Why a background field is needed

Why is it not enough to say that a global symmetry has an anomaly only by looking at $\partial_\mu J^\mu$ at zero background field?

<details>
<summary><strong>Solution</strong></summary>

At zero background field, many anomaly terms vanish or reduce to contact terms in correlation functions. The background-field generating functional collects those contact terms into a covariant object $Z[A]$ and tests how it transforms under local background gauge transformations.

This also captures finite, global, and topological anomalies that may not have a simple local current-divergence expression. The robust definition is therefore the obstruction to background gauge invariance modulo local counterterms.

</details>

### Exercise 4: Symmetry subgroup after anomaly

Suppose a classical $U(1)$ transformation changes the quantum path-integral measure in a way that leaves only a finite subgroup invariant. Which symmetry should be used for ’t Hooft anomaly matching?

<details>
<summary><strong>Solution</strong></summary>

Anomaly matching applies to exact symmetries. If the continuous $U(1)$ is not an exact quantum symmetry, one should not match it as a continuous global symmetry. Instead one should identify the exact remnant, often a finite subgroup possibly mixed with other symmetries, and study its background fields and anomalies.

In QCD-like examples, this distinction is essential for axial symmetries: the naive axial $U(1)$ is not the exact global symmetry, while discrete remnants and nonabelian chiral flavor symmetries can still have meaningful ’t Hooft anomalies.

</details>

## References

### Standard first pass

- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Chapter 30. Triangle anomalies, global anomalies, and anomaly matching.
- M. Srednicki, *Quantum Field Theory*, §§75–77. Chiral gauge anomalies, global anomalies, and the fermion path-integral measure.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II. Gauge symmetries, chiral symmetries, and consistency conditions in gauge theory.

### Deeper references

- G. ’t Hooft, **Naturalness, Chiral Symmetry, and Spontaneous Chiral Symmetry Breaking**, in *Recent Developments in Gauge Theories*, Cargèse 1979. The classic origin of anomaly matching as an infrared constraint.
- E. Witten, **Global Aspects of Current Algebra**, *Nuclear Physics B* 223 (1983). Wess–Zumino–Witten terms and chiral anomaly matching.
- C. G. Callan and J. A. Harvey, **Anomalies and Fermion Zero Modes on Strings and Domain Walls**, *Nuclear Physics B* 250 (1985). The anomaly-inflow paradigm.
- J. A. Harvey, **TASI 2003 Lectures on Anomalies**, arXiv:hep-th/0509097. A broad review of anomaly polynomials, descent, inflow, and global aspects.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, **Generalized Global Symmetries**, arXiv:1412.5148. Modern background-field, gauging, higher-form symmetry, and ’t Hooft anomaly viewpoint.

## Version history

- **2026-06-18:** Initial polished draft. Added background-field definition, counterterm equivalence, Ward-identity viewpoint, gauge-versus-global distinction, examples, inflow viewpoint, and exercises.
