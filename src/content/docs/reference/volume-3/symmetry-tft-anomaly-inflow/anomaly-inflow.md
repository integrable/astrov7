---
title: "Anomaly Inflow"
description: "Explains anomaly inflow as the cancellation of a boundary anomaly by a one-higher-dimensional topological bulk theory."
sidebar:
  label: "Anomaly Inflow"
  order: 3
level: Advanced
status: "Polished draft"
source: "Callan–Harvey; Alvarez-Gaumé–Witten; Witten global anomalies; Kapustin–Seiberg; Freed; Gaiotto–Kapustin–Seiberg–Willett; modern SymTFT reviews."
topics:
  - anomaly inflow
  - symmetry TFT
  - t Hooft anomaly
  - invertible field theory
  - descent equations
  - boundary anomalies
canonicalTopics:
  - anomaly-inflow
  - anomaly-cancellation
  - invertible-anomaly-theory
  - descent-equations
  - relative-qft
researchStatus:
  established:
    - "Anomaly inflow is a standard and precise way to represent many perturbative and global anomalies by a one-higher-dimensional bulk theory."
    - "For ordinary and higher-form invertible anomalies, the bulk theory can often be understood as an invertible topological field theory whose boundary variation cancels the anomalous boundary variation."
  active:
    - "For non-invertible, categorical, subsystem, fermionic, and spacetime symmetries, the inflow viewpoint remains powerful but the most natural language often uses defects, relative QFT, generalized cohomology, or fully extended field theory."
---

## Summary

**Anomaly inflow** is the statement that an anomalous $d$-dimensional theory can be consistently realized as the boundary of a $(d+1)$-dimensional bulk theory. The boundary theory alone transforms anomalously. The bulk transforms oppositely. The combined bulk-boundary system is invariant.

If $A$ denotes background fields and $g$ is a background gauge transformation, the boundary anomaly has the schematic form

$$
Z_{\partial}[A^g]
=
Z_{\partial}[A]\exp\bigl(i\mathcal A[A,g]\bigr).
$$

An inflow theory on a bulk $X_{d+1}$ with $\partial X_{d+1}=M_d$ supplies

$$
\exp\bigl(iS_{\mathrm{bulk}}[A^g]\bigr)
=
\exp\bigl(iS_{\mathrm{bulk}}[A]\bigr)
\exp\bigl(-i\mathcal A[A,g]\bigr).
$$

Therefore

$$
Z_{\mathrm{bulk}}[A]\,Z_{\partial}[A]
$$

is invariant.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A diagram of anomaly inflow: an anomalous boundary variation is cancelled by the opposite variation of a one-higher-dimensional bulk action.](/figures/symmetry-anomalies-topology/anomaly-inflow-boundary-cancellation.svg)

<figcaption>

Anomaly inflow turns a boundary failure into a bulk-boundary cancellation. The boundary theory $\mathcal T_d$ is not invariant by itself, but the bulk invertible theory $\mathcal I_{d+1}$ transforms oppositely. The product is the honest gauge-invariant object.

</figcaption>
</figure>

The slogan is:

$$
\text{anomaly of the boundary}
=
\text{variation of the bulk}.
$$

In the SymTFT viewpoint, anomaly inflow is not just a rescue mechanism. It is part of the dictionary that says symmetry, gauging, boundary conditions, charged objects, and obstructions are naturally encoded in one higher dimension.

## Prerequisites

Read [Symmetry TFT Idea](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/symmetry-tft-idea/) and [Bulk-Boundary Viewpoint](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/bulk-boundary-viewpoint/) first. You should also know the basic definitions of ’t Hooft anomaly, background field, topological defect, and gauging.

Helpful earlier pages include [What Is an Anomaly?](/symmetry-anomalies-topology/anomalies/what-is-an-anomaly/), [Obstruction to Gauging](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/obstruction-to-gauging/), and [Background Fields for Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/background-fields-for-higher-form-symmetries/).

This page uses differential forms and the descent notation

$$
I_{d+2}=dI_{d+1}^{(0)},
\qquad
\delta_\lambda I_{d+1}^{(0)}=dI_d^{(1)}(\lambda),
$$

but the conceptual content does not require mastering characteristic classes on a first pass.

## Core idea

An anomaly is often introduced as a failure:

$$
\text{classical symmetry}
\quad \not\Rightarrow \quad
\text{quantum symmetry}.
$$

Inflow reinterprets the failure as boundary data. The anomalous $d$-dimensional theory is not an inconsistent object if the anomalous symmetry is global. Instead, its partition function is naturally attached to a one-higher-dimensional bulk theory.

There are two complementary ways to say this.

First, in background-field language, the boundary partition function is not a gauge-invariant number. It transforms by a phase or, more generally, by a line-bundle transition function.

Second, in bulk-boundary language, the boundary theory is **relative** to a bulk invertible theory. It becomes an ordinary number only after choosing a compatible bulk filling or topological boundary condition.

The inflow perspective is powerful because it separates two questions:

| Question | Boundary answer | Bulk answer |
|---|---|---|
| What symmetry is anomalous? | The boundary generating functional fails to be invariant. | The bulk topological action has a matching variation. |
| Can the symmetry be gauged on the boundary alone? | No, not without extra data or cancellation. | Yes, only the combined bulk-boundary system is gauge invariant. |
| What is RG invariant? | The anomalous variation. | The bulk invertible field theory. |
| What must an infrared theory reproduce? | The same anomaly. | The same inflow theory, possibly through different boundary degrees of freedom. |

This is why anomaly inflow is the natural partner of anomaly matching.

## Setup and conventions

Let $M_d$ be the spacetime of the $d$-dimensional QFT and let $X_{d+1}$ be a bulk manifold with

$$
\partial X_{d+1}=M_d.
$$

We denote the boundary theory by $\mathcal T_d$ and the bulk inflow theory by $\mathcal I_{d+1}$. Background fields are collectively denoted by $A$. These may include ordinary gauge fields, higher-form gauge fields, spin connections, metrics, spin structures, or discrete cocycles, depending on the symmetry being probed.

The combined partition function is written schematically as

$$
Z_{\mathrm{total}}[X_{d+1},M_d;A]
=
Z_{\mathcal I}[X_{d+1};A]\,
Z_{\mathcal T}[M_d;A].
$$

The inflow condition is

$$
Z_{\mathrm{total}}[A^g]=Z_{\mathrm{total}}[A].
$$

On a page about perturbative local anomalies, one often writes

$$
Z_{\mathcal T}[A]=e^{iW[A]}.
$$

Then the anomalous variation is

$$
\delta_\lambda W[A]=\int_{M_d}\lambda^a\mathcal A_a[A],
$$

or, in descent notation,

$$
\delta_\lambda W[A]=2\pi\int_{M_d} I_d^{(1)}(\lambda,A).
$$

Some sources include a factor of $i$ in Euclidean signature and some absorb $2\pi$ into the normalization of characteristic classes. This page uses the schematic normalization

$$
\delta_\lambda S_{\mathrm{bulk}}=-\delta_\lambda W
$$

as the invariant statement.

:::note[Source note: signs and factors]
The signs in inflow formulas depend on orientation conventions, Lorentzian versus Euclidean signature, and whether $W$ is defined by $Z=e^{iW}$ or $Z=e^{-W_E}$. The robust statement is that the bulk and boundary variations cancel. Later anomaly-polynomial pages fix exact factors for specific examples.
:::

## Perturbative anomalies and descent

For many continuous symmetries in even spacetime dimension $d=2n$, perturbative anomalies are encoded by an anomaly polynomial

$$
I_{d+2}.
$$

This is a closed $(d+2)$-form built from characteristic classes of background gauge fields and tangent-bundle data. Locally one writes

$$
I_{d+2}=dI_{d+1}^{(0)}.
$$

Under a gauge transformation with parameter $\lambda$,

$$
\delta_\lambda I_{d+1}^{(0)}=dI_d^{(1)}(\lambda).
$$

The boundary anomaly is represented by

$$
\delta_\lambda W[A]
=
2\pi\int_{M_d}I_d^{(1)}(\lambda,A).
$$

The inflow action is

$$
S_{\mathrm{inflow}}[A]
=
-2\pi\int_{X_{d+1}}I_{d+1}^{(0)}(A),
$$

with the sign chosen so that

$$
\delta_\lambda S_{\mathrm{inflow}}
=
-2\pi\int_{M_d}I_d^{(1)}(\lambda,A).
$$

Then

$$
\delta_\lambda\bigl(W+S_{\mathrm{inflow}}\bigr)=0.
$$

The descent equations are bookkeeping, not magic. They express a simple geometrical idea: a closed topological density in one dimension higher has a locally defined Chern–Simons-like primitive, and the gauge variation of that primitive is a total derivative. The boundary term is the anomaly.

## The Chern–Simons example

The simplest concrete inflow formula comes from a three-dimensional Abelian Chern–Simons term on a bulk $X_3$ with boundary $M_2$:

$$
S_{\mathrm{CS}}[A]=\frac{k}{4\pi}\int_{X_3} A\wedge dA.
$$

Under

$$
A\mapsto A+d\lambda,
$$

the variation is

$$
\delta_\lambda S_{\mathrm{CS}}
=
\frac{k}{4\pi}\int_{X_3}d\lambda\wedge dA
=
\frac{k}{4\pi}\int_{M_2}\lambda\,dA.
$$

Thus a two-dimensional boundary theory with anomalous variation

$$
\delta_\lambda W_{\partial}
=
-\frac{k}{4\pi}\int_{M_2}\lambda\,dA
$$

is made gauge invariant by the bulk.

This is the prototype for many examples. A boundary chiral mode can carry an anomaly that is cancelled by a bulk Chern–Simons response. The bulk by itself is not gauge invariant on a manifold with boundary; the boundary by itself is anomalous; the pair is consistent.

:::note[Physical picture]
In condensed-matter language, this is the logic behind protected boundary modes of a topological phase. In high-energy language, it is the logic behind anomaly cancellation between bulk inflow and boundary degrees of freedom. The same mathematics is doing both jobs.
:::

## Global anomalies

Not all anomalies appear as local current-divergence formulas. A **global anomaly** can be invisible to infinitesimal gauge transformations but visible under large gauge transformations or diffeomorphisms.

In such cases, the boundary partition function may transform by a sign or phase under a large transformation:

$$
Z_{\partial}[A^g]=e^{i\alpha(g,A)}Z_{\partial}[A].
$$

There may be no local $I_d^{(1)}$ that captures the effect on a single coordinate patch. Still, anomaly inflow can work. The bulk theory is then usually described as an invertible field theory whose partition function is a global invariant, often involving eta invariants, bordism classes, or other nonlocal topological data.

The lesson is:

$$
\text{descent formulas are local tools;}
\qquad
\text{inflow is the global idea}.
$$

A local anomaly polynomial may determine only the perturbative part of the anomaly. The full anomaly can contain torsion or global information invisible to differential forms.

## Gauge anomalies versus ’t Hooft anomalies

A gauge anomaly is an anomaly in a redundancy. If a dynamical gauge field is being integrated over, gauge invariance is not optional. A gauge anomaly means the theory is not consistently defined unless the anomaly cancels or is repaired by an allowed inflow system.

A ’t Hooft anomaly is an anomaly of a global symmetry. The QFT is perfectly consistent as a theory with global symmetry, but the symmetry cannot be gauged by itself.

Inflow treats both with similar formulas but different interpretation.

| Case | Boundary anomaly means | Inflow interpretation |
|---|---|---|
| Gauge anomaly | A redundancy is inconsistent. | The boundary must be paired with a bulk or additional degrees of freedom so the dynamical gauge redundancy is restored. |
| ’t Hooft anomaly | A global symmetry cannot be gauged on the boundary alone. | The boundary is a legitimate anomalous boundary of an invertible bulk. |
| Mixed anomaly | Two structures cannot be simultaneously gauged or preserved independently. | The bulk depends on both background fields and records their coupled obstruction. |

The same phase factor can therefore be either fatal or useful, depending on whether the symmetry is dynamical redundancy or global structure.

## Inflow and anomaly matching

Anomaly matching says that ’t Hooft anomalies do not change under RG flow, provided the symmetry is preserved. Inflow makes this geometrically obvious.

If a UV theory is the boundary of an invertible bulk $\mathcal I_{d+1}$, then any IR theory obtained by symmetry-preserving RG flow must be a boundary of the same bulk:

$$
\mathcal T_{\mathrm{UV}}
\quad\longrightarrow_{\mathrm{RG}}\quad
\mathcal T_{\mathrm{IR}},
\qquad
\partial\mathcal I_{d+1}=\mathcal T_{\mathrm{UV}}=\mathcal T_{\mathrm{IR}}
\quad\text{as anomaly data}.
$$

The IR can match the anomaly in several ways:

1. It can contain massless degrees of freedom with the same anomaly.
2. It can have spontaneous symmetry breaking with Wess–Zumino terms.
3. It can contain topological order whose symmetry action carries the anomaly.
4. It can live as a boundary of the same SPT/invertible bulk.

The anomaly does not say which option occurs. It constrains the menu.

## Defects and localized inflow

Anomaly inflow is not only about spacetime boundaries. It can occur on defects.

Suppose a defect $\mathcal D$ supports degrees of freedom with an anomaly. A bulk or ambient topological term may fail to be invariant in precisely a way localized on $\mathcal D$. The defect anomaly is cancelled by inflow from the surrounding theory.

This is common for domain walls, interfaces, symmetry defects, and topological phases. If a background field jumps across a wall or a theta angle changes by a discrete amount, the variation of the bulk term can localize on the wall. The wall must then carry degrees of freedom or a topological theory whose anomaly matches the inflow.

This logic explains why anomaly inflow is central to the study of:

- chiral modes on domain walls,
- edge states of topological phases,
- defects carrying projective or anomalous symmetry actions,
- symmetry defects in anomalous theories,
- boundaries of SPT phases,
- relative and symmetry-TFT descriptions of anomalous QFTs.

A defect can be anomalous in exactly the same sense as a boundary: it may not be a standalone theory, but it can be a consistent embedded object.

## Relative partition functions

In an anomaly-free theory, the partition function on a closed spacetime is a complex number:

$$
Z(M_d;A)\in\mathbb C.
$$

In an anomalous theory, it is often better to say that the partition function is a vector in a one-dimensional vector space associated with the background data:

$$
Z(M_d;A)\in \mathcal L_{M_d,A}.
$$

The bulk invertible theory supplies the line $\mathcal L_{M_d,A}$ and its transformation rules. Choosing a trivialization of this line is like choosing a convention for the anomalous phase. Different trivializations differ by local counterterms or global phase choices.

This language prevents a common mistake. The anomalous partition function is not simply “not gauge invariant because someone forgot a counterterm.” It may be a well-defined vector in a line bundle over background-field space. The anomaly is the obstruction to canonically trivializing that bundle.

The SymTFT viewpoint generalizes this from lines to more general state spaces. An anomalous or relative theory may naturally take values in the Hilbert space of the bulk topological theory.

## Inflow and local counterterms

Some apparent anomalies can be shifted by adding local counterterms. This is why one distinguishes:

- scheme-dependent contact terms,
- consistent versus covariant anomaly representatives,
- trivial anomalies removable by counterterms,
- genuine anomaly classes.

In descent language, adding a local counterterm to the boundary shifts $W[A]$ by

$$
W[A]\mapsto W[A]+2\pi\int_{M_d}J_d[A].
$$

Its variation shifts the anomaly by

$$
\delta_\lambda W[A]\mapsto
\delta_\lambda W[A]+2\pi\int_{M_d}\delta_\lambda J_d[A].
$$

If the whole anomaly can be removed this way, it is not a genuine obstruction. If only its representative changes, the anomaly class remains.

Inflow is sensitive to the class, not merely to one local formula. The bulk invertible theory represents the genuine anomaly data after quotienting by trivial counterterms.

## Common pitfalls

**“Inflow cancels the anomaly, so the boundary symmetry is not anomalous.”** The boundary symmetry remains anomalous as a standalone theory. The combined bulk-boundary system is invariant.

**“All anomalies are described by anomaly polynomials.”** Perturbative local anomalies often are. Global and torsion anomalies may require eta invariants, bordism, or other global data.

**“A gauge anomaly and a ’t Hooft anomaly are the same problem.”** They can be represented similarly, but their physical interpretation differs. A gauge anomaly threatens consistency. A global ’t Hooft anomaly is allowed and constraining.

**“Anomaly inflow means adding arbitrary higher-dimensional physics.”** The bulk is topological or invertible in the anomaly-only setting. It encodes obstruction data, not new arbitrary local dynamics.

**“If the anomaly vanishes locally, it vanishes globally.”** Large gauge transformations and spacetime topology can still detect a global anomaly.

**“A boundary counterterm can always fix the problem.”** Counterterms can change representatives. They cannot remove a nontrivial anomaly class.

## Relations to other pages

[Bulk-Boundary Viewpoint](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/bulk-boundary-viewpoint/) explains the general bulk-boundary dictionary used here. [Invertible Field Theories](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/invertible-field-theories/) explains the kind of bulk theory that represents ordinary anomaly data. [SPT Phases and Anomalies](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/spt-phases-and-anomalies/) develops the condensed-matter version of the same idea.

The [Anomalies](/symmetry-anomalies-topology/anomalies/) chapter treats local computations such as triangle diagrams, Fujikawa Jacobians, consistent versus covariant anomalies, anomaly polynomials, and descent equations. The [’t Hooft Anomalies and Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/) chapter explains why the obstruction is preserved under RG flow.

## Research status

Anomaly inflow is a standard tool in QFT, string theory, condensed matter, and mathematical physics. Perturbative anomaly inflow through Chern–Simons descendants is textbook material. Global anomaly inflow through eta invariants and invertible field theories is also well established, though mathematically more sophisticated.

Active research directions include inflow for non-invertible symmetries, categorical symmetry, subsystem symmetry, non-semisimple defect networks, symmetry TFTs for strongly coupled theories, and the relation between anomaly inflow, generalized gauging, and boundary topological order.

## Exercises

### Exercise 1: Boundary variation of Abelian Chern–Simons theory

Let

$$
S_{\mathrm{CS}}[A]=\frac{k}{4\pi}\int_{X_3}A\wedge dA,
\qquad
\partial X_3=M_2.
$$

Show that under $A\mapsto A+d\lambda$,

$$
\delta_\lambda S_{\mathrm{CS}}=\frac{k}{4\pi}\int_{M_2}\lambda\,dA.
$$

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta_\lambda S_{\mathrm{CS}}
=
\frac{k}{4\pi}\int_{X_3} d\lambda\wedge dA.
$$

Since $d^2A=0$,

$$
d(\lambda\,dA)=d\lambda\wedge dA.
$$

By Stokes’ theorem,

$$
\delta_\lambda S_{\mathrm{CS}}
=
\frac{k}{4\pi}\int_{X_3}d(\lambda\,dA)
=
\frac{k}{4\pi}\int_{M_2}\lambda\,dA.
$$

</details>

### Exercise 2: Inflow cancellation

Suppose a boundary theory has

$$
\delta_\lambda W_{\partial}
=
-\frac{k}{4\pi}\int_{M_2}\lambda\,dA.
$$

Use Exercise 1 to show that $W_{\partial}+S_{\mathrm{CS}}$ is gauge invariant.

<details><summary><strong>Solution</strong></summary>

Exercise 1 gives

$$
\delta_\lambda S_{\mathrm{CS}}
=
\frac{k}{4\pi}\int_{M_2}\lambda\,dA.
$$

Therefore

$$
\delta_\lambda(W_{\partial}+S_{\mathrm{CS}})
=
-\frac{k}{4\pi}\int_{M_2}\lambda\,dA
+
\frac{k}{4\pi}\int_{M_2}\lambda\,dA
=0.
$$

</details>

### Exercise 3: Why anomaly matching follows from inflow

Explain why a symmetry-preserving RG flow cannot change the inflow bulk theory.

<details><summary><strong>Solution</strong></summary>

An RG flow changes local dynamics but not the background-field obstruction class of an exact symmetry. If the UV theory is a boundary of an invertible bulk $\mathcal I_{d+1}$, then the combined bulk-boundary system is gauge invariant. A symmetry-preserving IR description must produce the same gauge-invariant combined system. Therefore the IR boundary must carry the same anomalous variation, equivalently the same inflow bulk. The IR can realize this anomaly through massless fields, spontaneous breaking, Wess–Zumino terms, or topological order, but the anomaly class is fixed.

</details>

### Exercise 4: Counterterm or genuine anomaly?

A boundary anomalous variation is shifted by adding a local counterterm. Does this prove the anomaly is trivial?

<details><summary><strong>Solution</strong></summary>

Not by itself. Local counterterms change the representative of the anomaly. The anomaly is trivial only if some allowed local counterterm cancels the full anomalous variation for all allowed backgrounds and transformations. If no such counterterm exists, the anomaly class is nontrivial even though particular formulas for it can shift.

</details>

## References

- C. Callan and J. Harvey, “Anomalies and Fermion Zero Modes on Strings and Domain Walls.” The classic physical inflow picture.
- L. Alvarez-Gaumé and E. Witten, “Gravitational Anomalies.” Standard source for gravitational anomaly descent and inflow.
- E. Witten, “An SU(2) Anomaly.” The canonical global anomaly example.
- D. Freed, “Anomalies and Invertible Field Theories.” Modern geometric viewpoint on anomalies as invertible field theories.
- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality.” A precursor to the modern SymTFT viewpoint.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries.” Higher-form symmetry, backgrounds, gauging, and anomalies.
- D. Freed and M. Hopkins, “Reflection Positivity and Invertible Topological Phases.” Classification viewpoint for invertible phases and anomaly theories.

## Version history

- **2026-06-20:** Initial polished draft. Added inflow definition, descent formulas, Chern–Simons example, global anomaly caveats, relative partition functions, counterterm discussion, and exercises.
