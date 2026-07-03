---
title: "Anomalies as RG Invariants"
description: "Explains why ’t Hooft anomaly classes of exact global symmetries are invariant under symmetry-preserving RG flows, and how this differs from running couplings or anomaly representatives."
sidebar:
  label: "Anomalies as RG Invariants"
  order: 3
level: Advanced
status: "Polished draft"
source: "’t Hooft anomaly matching; Wilsonian RG with background fields; anomaly inflow; Wess–Zumino terms; Srednicki §§75–77; Schwartz Ch. 30; Weinberg Vol. II; Gaiotto–Kapustin–Seiberg–Willett."
topics:
  - thooft anomalies
  - RG invariance
  - anomaly matching
  - background fields
  - local counterterms
  - anomaly inflow
  - Wilsonian effective action
canonicalTopics:
  - anomalies-as-rg-invariants
  - uv-ir-anomaly-invariance
  - anomaly-class
  - counterterm-equivalence
  - anomaly-inflow
researchStatus:
  established:
    - "The ’t Hooft anomaly class of an exact global symmetry is invariant under symmetry-preserving RG flow."
    - "Wilsonian integration can change anomaly representatives by local background counterterms, but it cannot change a nontrivial anomaly class."
  active:
    - "For generalized, non-invertible, fermionic, crystalline, and subsystem symmetries, the RG-invariant object may be more refined than an anomaly polynomial and is often best organized by inflow or symmetry-TFT data."
---

## Summary

A **’t Hooft anomaly is an RG invariant**. More precisely, the anomaly **class** of an exact global symmetry is unchanged under any RG flow that preserves that symmetry.

If a UV theory $\mathcal T_{\rm UV}$ with global symmetry $G$ flows to an IR theory $\mathcal T_{\rm IR}$, then the same background-field obstruction must be present at long distances:

$$
[\mathcal A_G^{\rm UV}]=[\mathcal A_G^{\rm IR}].
$$

This statement is deliberately about the class $[\mathcal A_G]$, not about one chosen formula for the anomalous divergence of a current. The formula can change when we integrate out massive fields, choose different counterterms, or use different variables. The nontrivial obstruction to gauging the symmetry cannot change.

That is why anomaly matching is so powerful. A quantity often computable in the UV gives a nonperturbative constraint on the IR, even when the IR is strongly coupled.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing a UV theory and IR theory coupled to the same background field. The anomaly representative can change by local counterterms, but the anomaly class is rigid along the RG flow.](/figures/symmetry-anomalies-topology/anomalies-rg-invariant-class.svg)

<figcaption>

Along a symmetry-preserving RG flow, short-distance modes can shift local background counterterms and hence change anomaly representatives. They cannot change the invariant anomaly class $[\mathcal A_G]$.

</figcaption>
</figure>

## Prerequisites

Read [’t Hooft Anomalies](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/thooft-anomalies/) and [Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/) first. You should also know [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/), [Wess–Zumino Consistency Condition](/symmetry-anomalies-topology/anomalies/wess-zumino-consistency-condition/), [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/), and [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/).

The page assumes the usual Wilsonian idea that integrating out high-energy modes produces local effective interactions for low-energy fields and background sources.

## Core idea

Running couplings are local parameters in an effective action. They can and usually do depend on scale:

$$
\mu\frac{d g}{d\mu}=\beta(g).
$$

An anomaly class is different. It is not a continuous coupling multiplying an ordinary local operator. It is obstruction data for coupling a symmetry to background fields. If the obstruction is present in the UV, it must still be visible in the IR.

A useful slogan is

$$
\text{ordinary couplings run, but anomaly classes match}.
$$

The word “classes” is doing real work. An anomaly can be represented by a current-divergence formula, a background-field variation, an anomaly polynomial, a descent representative, a finite transformation phase, a determinant-line holonomy, or an inflow theory. Different representatives can look different. The invariant statement is that the obstruction modulo local counterterms is the same.

## Setup and conventions

Let $\mathcal T_{\rm UV}$ be a QFT with exact global symmetry $G$. Couple it to a nondynamical background $A$ for $G$ and write

$$
Z_{\rm UV}[A]=e^{iW_{\rm UV}[A]}.
$$

For a background gauge transformation $g$, the partition function may transform as

$$
Z_{\rm UV}[A^g]
=
\exp\!\left(2\pi i\mathcal A_g^{\rm UV}[A]\right)Z_{\rm UV}[A].
$$

The phase $\mathcal A_g^{\rm UV}[A]$ is meaningful only modulo shifts produced by local background counterterms. If we redefine

$$
Z[A]\longrightarrow Z'[A]
=
\exp\!\left(iS_{\rm ct}[A]\right)Z[A],
$$

then

$$
\mathcal A_g[A]
\longrightarrow
\mathcal A'_g[A]
=
\mathcal A_g[A]
+
\frac{1}{2\pi}
\left(S_{\rm ct}[A^g]-S_{\rm ct}[A]\right)
\quad \mathrm{mod}\;\mathbb Z.
$$

Therefore the RG-invariant object is the equivalence class

$$
[\mathcal A_G]
=
\mathcal A_G
\;\;\mathrm{mod}\;\;\text{local counterterm shifts}.
$$

For local perturbative anomalies, this class can often be packaged by an anomaly polynomial $I_{d+2}$ and descent. For finite, torsion, global, spin, Pin, crystalline, or higher-form anomalies, the invariant may not be visible in a polynomial. The safest phrase is **anomaly class**.

:::note[Convention-sensitive source note]
Anomaly-polynomial formulas depend on generator normalization, characteristic-class normalization, and whether right-handed fermions are rewritten as left-handed conjugates. RG invariance is a statement about the same background-field problem in UV and IR, not about matching two formulas written in different conventions.
:::

## Wilsonian derivation

The cleanest proof uses RG in fixed background fields. Keep the background $A$ arbitrary and integrate out modes above a scale $\mu$. The background is a source, not a dynamical field, so it is not integrated out.

At long distances, locality gives

$$
Z_{\rm UV}[A]
\simeq
\exp\!\left(iS_{\rm local}[A]\right)Z_{\rm IR}[A],
$$

where $S_{\rm local}[A]$ is a local functional of background fields, possibly including contact terms and topological response terms, and $Z_{\rm IR}[A]$ is the generating functional of the low-energy degrees of freedom.

Now perform a background gauge transformation:

$$
Z_{\rm UV}[A^g]
\simeq
\exp\!\left(iS_{\rm local}[A^g]\right)Z_{\rm IR}[A^g].
$$

Using

$$
Z_{\rm UV}[A^g]
=e^{2\pi i\mathcal A_g^{\rm UV}[A]}Z_{\rm UV}[A],
\qquad
Z_{\rm IR}[A^g]
=e^{2\pi i\mathcal A_g^{\rm IR}[A]}Z_{\rm IR}[A],
$$

and substituting the Wilsonian relation, one obtains

$$
\mathcal A_g^{\rm UV}[A]
=
\mathcal A_g^{\rm IR}[A]
+
\frac{1}{2\pi}
\left(S_{\rm local}[A^g]-S_{\rm local}[A]\right)
\quad \mathrm{mod}\;\mathbb Z.
$$

Thus

$$
[\mathcal A_G^{\rm UV}]=[\mathcal A_G^{\rm IR}].
$$

That is the whole theorem in practical form: integrating out short-distance physics can produce local terms, but local terms are precisely the ambiguity by which anomaly representatives are identified.

## What exactly is invariant?

Different problems use different anomaly languages. The invariant can be described as follows.

| Anomaly language | What is invariant under RG |
|---|---|
| Current divergence | The cohomology class of the anomalous Ward identity, not necessarily the displayed current. |
| Effective action | The anomalous transformation of $W[A]$ modulo local counterterm variations. |
| Anomaly polynomial | The characteristic-class polynomial $I_{d+2}$, modulo trivial descendants and counterterm conventions. |
| Global anomaly | The phase/holonomy of the determinant line over background-field space. |
| Inflow | The one-higher-dimensional invertible field theory whose boundary is the anomalous QFT. |
| Symmetry TFT | The bulk topological data encoding the symmetry and anomaly of the boundary theory. |

The common thread is that an anomaly is a property of the theory as a function of backgrounds. RG can change the low-energy variables, but it cannot change the obstruction attached to the exact symmetry.

## Representatives can change

It is tempting to say “the anomaly coefficient is invariant.” Often that is true, but it is too narrow.

For a simple four-dimensional Weyl-fermion flavor anomaly, a cubic trace such as

$$
\operatorname{Tr}(T_a\{T_b,T_c\})
$$

is invariant under RG, because it represents a local perturbative anomaly coefficient. But in more general settings the same anomaly class can be represented by several different-looking formulas.

A Bardeen counterterm can move anomaly between vector and axial currents. A Chern–Simons counterterm can shift a three-dimensional parity-anomaly representative. A Wess–Zumino–Witten term in a Goldstone action can replace a UV fermion triangle. A finite anomaly may have no infinitesimal current-divergence formula at all.

So the careful statement is:

$$
\text{RG preserves the obstruction class, not a favorite representative.}
$$

This is why anomaly matching is robust across dualities. Dual variables can make the anomaly look unrecognizable locally, while the background-field transformation remains the same.

## Massive fields and local remnants

A common worry is that massive fields disappear from the IR. If massive fermions disappear, how can their anomalies remain?

The answer is that massive fields can leave local topological terms and Wess–Zumino terms. Those terms may be invisible in ordinary particle spectra but very visible in background fields.

A useful schematic relation is

$$
\int \mathcal D\Psi_{\rm massive}\,e^{iS[\Psi,A]}
=
\exp\!\left(iS_{\rm local}[A]\right)
\times
\left(\text{irrelevant corrections}\right).
$$

If the massive field helped carry an anomaly, the low-energy local functional cannot be discarded as “just a contact term.” Its variation is part of the anomaly bookkeeping.

### Goldstone example

In a theory with spontaneous chiral symmetry breaking, the UV anomaly of massless quarks is not matched by massless quarks in the IR. It is matched by a Wess–Zumino–Witten term for Goldstone fields.

Schematically,

$$
\delta_\alpha S_{\rm WZW}[U,A]
=
-\delta_\alpha W_{\rm UV}[A].
$$

The Goldstone fields are different from the quarks, but the anomalous background variation is the same.

### Topological response example

In odd spacetime dimensions, integrating out a massive fermion can leave a Chern–Simons response term. The coefficient depends on the sign of the mass and on the regulator. This is not a contradiction with RG invariance; it is the way the anomaly is represented after the massive fermion is gone.

The precise statement is again about the full anomaly class of the symmetry being tested, including any time-reversal, reflection, spin, or gauge-invariance conditions imposed on the regulator.

:::note[Convention-sensitive source note]
The “massive fermion leaves half a Chern–Simons term” slogan is dangerously compressed. The coefficient depends on whether the gauge field is background or dynamical, on spin-structure assumptions, and on which discrete symmetry one tries to preserve. Use it as a diagnostic example, not as a standalone formula without its setup.
:::

## Anomalies versus running couplings

The phrase “RG invariant” can mislead if read too quickly. A ’t Hooft anomaly is not invariant in the same way as a conserved charge eigenvalue, and it is not a running coupling set to a fixed value.

Here is the useful distinction.

| Quantity | Under RG flow |
|---|---|
| Relevant couplings | Usually grow toward the IR. |
| Marginal couplings | Can run logarithmically. |
| Irrelevant couplings | Usually become less important in the IR. |
| Contact terms | Can shift by scheme-dependent local terms. |
| Trace anomaly coefficients | May change along RG flow, depending on dimension and context. |
| ’t Hooft anomaly class of an exact global symmetry | Must match between UV and IR. |

The trace anomaly deserves special caution. The word “anomaly” appears, but trace/Weyl anomalies are not all RG invariants of the same type. For example, in four-dimensional unitary flows the $a$ coefficient changes monotonically between CFT fixed points, while ordinary flavor ’t Hooft anomalies of exact symmetries match.

A sharp way to remember the difference is:

$$
\text{flavor anomaly: obstruction for symmetry backgrounds}
$$

whereas

$$
\text{trace anomaly: response to Weyl rescaling and scale dependence}.
$$

There are relations between the two in supersymmetric theories and conformal theories, but they are not the same concept.

## Exact, broken, and emergent symmetries

Anomaly matching applies to exact symmetries along the flow. If a deformation explicitly breaks the symmetry, the anomaly for that symmetry no longer has to match.

Suppose a UV theory has symmetry $G$ but we perturb it by an operator that preserves only $H\subset G$. Then the IR must match the anomaly of $H$, not the whole anomaly of $G$.

If $G$ is spontaneously broken to $H$, the full $G$ anomaly still constrains the IR because $G$ remains a symmetry of the theory even though the vacuum is not invariant. The anomaly is then realized by Goldstone fields, Wess–Zumino terms, domain walls, or other low-energy data.

If a symmetry is accidental or emergent in the IR, it can have its own anomaly as an IR symmetry. But anomaly matching from the UV applies only to the UV symmetries that can be coupled to backgrounds throughout the flow. To compare an emergent symmetry with UV data, one must specify how it embeds into or extends the UV symmetry structure.

This subtlety is everywhere in duality. A symmetry may be manifest in one description, emergent in another, and mixed with topological or higher-form symmetries after gauging.

## Inflow viewpoint

Anomaly inflow gives a geometric proof of RG invariance.

If a $d$-dimensional theory has anomaly $\mathcal A_G$, we can represent it as the boundary of a $(d+1)$-dimensional invertible theory:

$$
Z_{d}[A]\,Z_{d+1}^{\rm inv}[A]
$$

is gauge invariant when $M_d=\partial X_{d+1}$.

Now run RG on the boundary. Boundary degrees of freedom may change dramatically. Massive particles may disappear, Goldstone bosons may appear, and a topological sector may survive. But the bulk invertible theory does not disappear under a boundary RG flow. Therefore the boundary anomaly class is unchanged.

This viewpoint is especially useful when the anomaly is discrete, torsion, fermionic, or global. In those cases a local polynomial can miss essential data, while the inflow theory still records the anomaly.

## Practical checklist

To use “anomalies are RG invariants” responsibly, run through this checklist.

| Step | Question | Why it matters |
|---:|---|---|
| 1 | What is the exact symmetry $G$? | Matching the wrong symmetry gives a wrong constraint. |
| 2 | What is the global form of $G$? | Background bundles depend on quotients and charge lattices. |
| 3 | What backgrounds are allowed? | Local connection data may miss torsion or spin data. |
| 4 | What is the anomaly class, not just a formula? | Counterterms can shift representatives. |
| 5 | Which deformation defines the RG flow? | Explicit symmetry breaking reduces the matching requirement. |
| 6 | What IR data carry the anomaly? | Massless fields, Goldstones, TQFTs, edges, and defects all count. |
| 7 | Are there accidental or emergent symmetries? | Their anomalies are not automatically UV constraints. |

This is the grown-up version of anomaly matching: first identify the background-field problem, then compare classes.

## Common pitfalls

**Saying “anomalies do not renormalize” without specifying the anomaly.** Perturbative anomaly coefficients are often one-loop exact, but the deeper statement is RG invariance of the ’t Hooft anomaly class. Trace anomalies and beta-function data behave differently.

**Matching only the Lie algebra.** Two symmetries with the same Lie algebra but different global form can have different backgrounds and different anomalies.

**Forgetting local counterterms.** If two anomaly formulas differ by the variation of a local counterterm, they represent the same anomaly class.

**Ignoring topological IR sectors.** A symmetric gapped IR phase can match an anomaly if it contains suitable topological order or an anomalous TQFT sector. The forbidden endpoint is a trivial symmetric gap.

**Treating emergent symmetries as UV symmetries.** Emergent IR symmetries can be real and useful, but UV–IR matching applies only after specifying their relation to UV background fields.

## Relations to other pages

- [Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/) gives the main UV–IR consequence of this page.
- [Obstruction to Gauging](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/obstruction-to-gauging/) explains why the invariant obstruction prevents standalone gauging.
- [Consistent Versus Covariant Anomalies](/symmetry-anomalies-topology/anomalies/consistent-versus-covariant-anomalies/) explains why different current choices can represent the same anomaly differently.
- [Wess–Zumino Consistency Condition](/symmetry-anomalies-topology/anomalies/wess-zumino-consistency-condition/) gives the local cohomological condition behind perturbative anomaly classes.
- [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/) develops the bulk-boundary viewpoint used here.

## Research status

The RG invariance of ’t Hooft anomaly classes is established and is one of the basic nonperturbative constraints of QFT. It is used in QCD-like theories, chiral gauge theories, dualities, topological phases, conformal field theories, and generalized-symmetry analyses.

The active frontier is not whether anomalies match, but what counts as the complete anomaly data for increasingly general symmetry structures. Higher-form symmetries, higher groups, non-invertible defects, fermionic symmetries, Pin and spin structures, crystalline symmetries, subsystem symmetries, and relative QFTs often require a language more refined than current divergences or anomaly polynomials.

## Exercises

### Exercise 1: Counterterm shift and matching

Assume

$$
Z_{\rm UV}[A]
=
e^{iS_{\rm local}[A]}Z_{\rm IR}[A].
$$

Show that if $Z_{\rm UV}$ and $Z_{\rm IR}$ transform anomalously under $A\mapsto A^g$, then their anomaly phases differ by the transformation of $S_{\rm local}[A]$.

<details>
<summary><strong>Solution</strong></summary>

Write

$$
Z_{\rm UV}[A^g]
=e^{2\pi i\mathcal A_g^{\rm UV}[A]}Z_{\rm UV}[A],
\qquad
Z_{\rm IR}[A^g]
=e^{2\pi i\mathcal A_g^{\rm IR}[A]}Z_{\rm IR}[A].
$$

Transform the Wilsonian relation:

$$
Z_{\rm UV}[A^g]
=e^{iS_{\rm local}[A^g]}Z_{\rm IR}[A^g].
$$

Substitute the anomaly transformations and also

$$
Z_{\rm UV}[A]=e^{iS_{\rm local}[A]}Z_{\rm IR}[A].
$$

After cancelling $Z_{\rm IR}[A]$, one obtains

$$
\mathcal A_g^{\rm UV}[A]
=
\mathcal A_g^{\rm IR}[A]
+
\frac{1}{2\pi}
\left(S_{\rm local}[A^g]-S_{\rm local}[A]\right)
\quad \mathrm{mod}\;\mathbb Z.
$$

Thus the two anomaly representatives differ by a local counterterm shift and define the same class.

</details>

### Exercise 2: Why a mass gap is not enough

Explain why a nonzero anomaly forbids a trivially gapped symmetric IR phase, but does not forbid every gapped symmetric IR phase.

<details>
<summary><strong>Solution</strong></summary>

A trivially gapped symmetric phase has a unique vacuum, no long-distance massless modes, and no topological order. Its response to background fields is purely local and cannot carry a nontrivial obstruction to gauging. Therefore its anomaly class is zero.

A gapped phase with topological order can have a nontrivial background dependence. Its TQFT sector may transform anomalously under background gauge transformations or may require inflow from a bulk. Such a phase can match a nonzero anomaly while remaining gapped.

</details>

### Exercise 3: Explicit breaking

A UV theory has global symmetry $G$ with nonzero anomaly. A relevant deformation preserves only $H\subset G$. Which anomaly must the IR match?

<details>
<summary><strong>Solution</strong></summary>

The IR must match the anomaly of the exact symmetry preserved along the flow, namely $H$. The anomaly of the explicitly broken part of $G$ no longer imposes a constraint, because one can no longer couple the whole flow consistently to arbitrary $G$ backgrounds.

However, the $G$ anomaly can still be useful: restricting the $G$ anomaly to $H$ gives the anomaly data for $H$, provided the deformation and background coupling are compatible with that restriction.

</details>

### Exercise 4: Trace anomaly caveat

Why is it misleading to use the phrase “anomalies are RG invariants” for all trace-anomaly coefficients?

<details>
<summary><strong>Solution</strong></summary>

A ’t Hooft anomaly is an obstruction to gauging an exact global symmetry and must match along symmetry-preserving RG flow. Trace anomalies describe the response to Weyl transformations and are tied to scale dependence. In many theories, trace-anomaly coefficients change between UV and IR fixed points; for example, the four-dimensional $a$ coefficient is not equal at the two ends of a nontrivial unitary flow.

Therefore the RG-invariant statement applies to ’t Hooft anomaly classes of exact symmetries, not to every quantity called an anomaly.

</details>

## References

### Standard first pass

- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Chapter 30. Anomalies, Standard Model anomaly cancellation, global anomalies, and anomaly matching.
- M. Srednicki, *Quantum Field Theory*, §§75–77 and §83. Chiral anomalies, fermion path-integral measure, and QCD chiral symmetry breaking.
- S. Coleman, *Aspects of Symmetry*, especially **Soft Pions**, **Dilatations**, **Secret Symmetry**, and **The Uses of Instantons**.

### Deeper references

- G. ’t Hooft, **Naturalness, Chiral Symmetry, and Spontaneous Chiral Symmetry Breaking**, in *Recent Developments in Gauge Theories*, Cargèse 1979. The classic anomaly-matching argument.
- E. Witten, **Global Aspects of Current Algebra**, *Nuclear Physics B* 223 (1983). Wess–Zumino–Witten terms and global aspects of anomaly matching.
- C. G. Callan and J. A. Harvey, **Anomalies and Fermion Zero Modes on Strings and Domain Walls**, *Nuclear Physics B* 250 (1985). Anomaly inflow as a robust matching mechanism.
- J. A. Harvey, **TASI 2003 Lectures on Anomalies**, arXiv:hep-th/0509097. Review of anomaly polynomials, descent, inflow, and global aspects.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, **Generalized Global Symmetries**, arXiv:1412.5148. Background fields, gauging, higher-form symmetries, and generalized anomaly matching.

## Version history

- **2026-06-18:** Initial polished draft. Added Wilsonian proof, distinction between anomaly classes and representatives, massive-field remnants, trace-anomaly caveat, exact/broken/emergent symmetry conditions, inflow viewpoint, checklist, and exercises.
