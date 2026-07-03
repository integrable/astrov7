---
title: "Anomalies and Boundaries"
description: "Explains how ’t Hooft anomalies constrain boundary conditions, interfaces, edge modes, and possible symmetric gapped boundary phases."
sidebar:
  label: "Anomalies and Boundaries"
  order: 6
level: Advanced
status: "Polished draft"
source: "Anomaly inflow; SPT bulk–boundary correspondence; boundary CFT and edge modes; topological order; Gaiotto–Kapustin–Seiberg–Willett; Freed–Hopkins."
topics:
  - anomalies and boundaries
  - anomaly matching
  - boundary conditions
  - edge modes
  - symmetry protected phases
  - topological order
  - anomaly inflow
canonicalTopics:
  - anomalies-and-boundaries
  - anomalous-boundary
  - boundary-anomaly-matching
  - spt-boundary
  - symmetric-gapped-boundary
researchStatus:
  established:
    - "A nontrivial ’t Hooft anomaly forbids a trivially gapped, nondegenerate, symmetry-preserving boundary realization of the anomalous symmetry."
    - "Anomalous boundary theories can be consistently realized as boundaries of one-higher-dimensional inflow theories."
  active:
    - "The classification of symmetric gapped boundaries, anomalous topological orders, non-invertible boundary symmetries, and higher-codimension anomaly inflow remains an active research area."
---

## Summary

Anomalies are boundary constraints in disguise. A nontrivial ’t Hooft anomaly says that a theory cannot be both standalone and gauge invariant under background transformations. If the theory appears on the boundary of a one-higher-dimensional bulk, the anomaly can be cancelled by inflow. But the boundary still has to **realize** the anomaly somehow.

That realization has sharp consequences. A boundary with nontrivial anomaly cannot flow to a completely trivial, symmetry-preserving, gapped state. Its infrared fate must include at least one of the following:

- gapless degrees of freedom;
- spontaneous symmetry breaking;
- intrinsic topological order;
- a relative realization tied to a bulk anomaly theory;
- boundary defects or lower-dimensional modes that carry the remaining anomaly.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing possible infrared fates of an anomalous boundary: gapless modes, symmetry breaking, topological order, or relative bulk attachment, while a trivial symmetric gapped boundary is forbidden.](/figures/symmetry-anomalies-topology/anomalous-boundary-fates.svg)

<figcaption>

A nontrivial boundary anomaly is an IR constraint. It forbids a completely trivial symmetric gapped boundary, but it does not force a unique outcome. Gaplessness, symmetry breaking, topological order, or relative bulk attachment can all match anomaly data.

</figcaption>
</figure>

## Prerequisites

Read [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/), [Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/), and [Obstruction to Gauging](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/obstruction-to-gauging/) first.

It is also helpful to know [Boundaries and Interfaces](/symmetry-anomalies-topology/defects-extended-operators/boundaries-and-interfaces/), [Domain Walls as Defects](/symmetry-anomalies-topology/defects-extended-operators/domain-walls-as-defects/), and [Spin Structures and Fermion Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/spin-structures-and-fermion-parity/).

## Core idea

A boundary is not just a place where fields stop. It is a physical system with its own degrees of freedom, boundary conditions, operator algebra, and symmetry action. When anomalies are present, the boundary must account for them.

There are two closely related situations:

1. A $d$-dimensional anomalous theory is placed on the boundary of a $(d+1)$-dimensional inflow theory.
2. A $(d+1)$-dimensional symmetry-protected or invertible bulk has a boundary whose symmetry action is anomalous.

In both cases, the same principle applies:

$$
\text{boundary anomaly}
=
\text{bulk variation to be cancelled}.
$$

This is a local consistency condition and an RG constraint. If a boundary theory changes under RG flow, its anomaly class must still match the bulk. Therefore a proposed boundary IR phase must pass the anomaly test.

## Setup and conventions

Let $X_{d+1}$ be a bulk spacetime with boundary $M_d=\partial X_{d+1}$. Let $A$ denote background fields for a symmetry $G$. The bulk–boundary partition function is

$$
Z_{\rm total}[X_{d+1},A]
=
Z_{\rm bulk}[X_{d+1},A]Z_{\partial}[M_d,A|_{M_d}].
$$

If the bulk transforms as

$$
Z_{\rm bulk}[X_{d+1},A^g]
=
\exp\!\left(-2\pi i\mathcal A_g[M_d,A]\right)Z_{\rm bulk}[X_{d+1},A],
$$

then the boundary must transform as

$$
Z_{\partial}[M_d,A^g]
=
\exp\!\left(2\pi i\mathcal A_g[M_d,A]\right)Z_{\partial}[M_d,A]
$$

for the product to be invariant.

A boundary condition is **symmetric** if it preserves the symmetry $G$ after including any necessary boundary degrees of freedom. It is **trivially gapped** if it has a unique gapped ground state on closed spatial slices, no intrinsic topological order, no protected edge modes, and no symmetry breaking. A nontrivial anomaly rules out this last possibility.

:::note[Boundary orientation convention]
The sign of a boundary anomaly depends on the orientation convention for $\partial X$. Reversing the orientation of $M_d$ reverses the inflow sign. Throughout this page, the boundary orientation is the one induced by the outward-normal-first convention, and the anomaly sign is fixed by gauge invariance of $Z_{\rm bulk}Z_{\partial}$.
:::

## Boundaries as anomaly matchers

The cleanest boundary rule is just anomaly matching:

$$
[\mathcal A_{\rm boundary,UV}]
=
[\mathcal A_{\rm boundary,IR}].
$$

If the boundary is the edge of a bulk SPT or invertible phase, then this class is determined by the bulk. If the boundary undergoes RG flow, any IR description must reproduce the same class.

For example, suppose a boundary theory carries a nonzero anomaly for $G$. A proposed IR boundary consisting of a unique symmetric gapped state has no anomaly. That proposal cannot be correct unless the anomaly was removed by changing the problem: breaking $G$, adding another boundary sector with the opposite anomaly, or attaching to a different bulk.

Thus anomalies are not merely diagnostic. They are no-go theorems for overly simple boundary phases.

## The four standard boundary fates

A nontrivial anomaly can be matched in several ways.

### Gapless boundary modes

The boundary may remain gapless. This is the familiar possibility in chiral edge theories, conformal boundary theories, and surface states of some topological phases.

Gaplessness can match the anomaly because massless degrees of freedom can carry anomalous Ward identities. In two-dimensional chiral edge theories, for instance, the anomalous current divergence is visible directly in the edge theory and is cancelled by bulk Chern–Simons inflow.

But gaplessness is not guaranteed. It is a mechanism, not a theorem, unless additional assumptions rule out the other possibilities.

### Spontaneous symmetry breaking

The boundary can break the anomalous symmetry. Once the symmetry is not preserved by the boundary state, the original anomaly constraint is avoided rather than matched in a symmetric way.

This is not cheating. Anomaly matching constrains symmetry-preserving RG flows. If the boundary spontaneously breaks $G$, the low-energy boundary contains order parameters, degenerate sectors, domain walls, or Goldstone modes appropriate to the broken symmetry pattern.

### Intrinsic topological order

The boundary can be gapped and symmetric if it develops intrinsic topological order. In that case, the anomaly is carried by the way the symmetry acts on anyons, lines, surfaces, or other extended excitations.

This is one of the most important modern lessons. A nontrivial anomaly rules out a **trivial** symmetric gapped boundary, but not necessarily every symmetric gapped boundary.

For example, a three-dimensional bosonic SPT may have a two-dimensional symmetric gapped boundary only if the boundary supports topological order whose anyons transform anomalously under the symmetry. The topological order cannot exist as a purely two-dimensional symmetric system with the same symmetry action; it is anomalous and needs the bulk.

### Relative boundary condition

Sometimes the most precise statement is that the boundary is a relative theory for the bulk anomaly theory. Its partition function is not an ordinary number but a vector in a background-dependent line or state space. The bulk supplies the dual object needed to produce a number.

This language is especially useful for generalized symmetries, finite symmetries, non-invertible symmetry defects, and fully extended TQFT descriptions.

## Why a trivial symmetric gapped boundary is forbidden

A trivially gapped symmetric boundary has no long-distance degrees of freedom that can carry a nontrivial anomaly. Its partition function on large manifolds is a local, symmetry-invariant functional of the background fields, up to removable counterterms.

Equivalently, the boundary IR theory is the empty theory plus local contact terms. The empty theory has anomaly class zero:

$$
[\mathcal A_{\rm empty}]=0.
$$

If the UV boundary has nonzero anomaly class, anomaly matching would require

$$
[\mathcal A_{\rm UV}]=0,
$$

which is a contradiction.

Therefore

$$
[\mathcal A]\neq 0
\quad\Rightarrow\quad
\text{no trivial symmetric gapped boundary}.
$$

The words “trivial,” “symmetric,” and “gapped” are all necessary. Remove any one of them and the conclusion can fail.

## Boundary conditions versus boundary degrees of freedom

In Lagrangian QFT, a boundary can be described by imposing boundary conditions on bulk fields. But anomaly cancellation may require adding genuine boundary degrees of freedom.

For a gauge field, varying the action often produces a boundary term. A boundary condition can make the variational principle well-defined. Separately, a background gauge transformation can produce a boundary variation. A boundary condition alone may or may not cancel that variation. When it cannot, the boundary must carry extra fields, topological order, or a relative state that transforms appropriately.

A useful distinction is

$$
\begin{aligned}
\text{variational boundary problem} &: \delta S=0\text{ for allowed variations},\\
\text{anomaly boundary problem} &: \delta_g(S_{\rm bulk}+W_{\partial})=0.
\end{aligned}
$$

They often interact, but they are not the same problem.

## Interfaces and anomaly differences

An interface between two bulk phases is a boundary for the **difference** of their anomaly theories. Suppose the left and right bulks have invertible responses $\mathcal I_L$ and $\mathcal I_R$. The interface anomaly is

$$
[\mathcal A_{\rm interface}]
=
[\mathcal I_L]-[\mathcal I_R].
$$

If the two bulks are in the same SPT phase, the difference is trivial and the interface can in principle be trivially gapped while preserving symmetry. If the difference is nontrivial, the interface must match the anomaly by one of the same mechanisms: gaplessness, symmetry breaking, topological order, or relative realization.

Domain walls inside a single theory work the same way. If a parameter such as a mass or theta angle jumps across a wall, the effective topological response can jump. The wall then carries the anomaly difference.

## Boundaries of gauge theories

Gauge theories add one more layer of subtlety. Gauge redundancy is not a physical global symmetry, but gauge transformations that do not vanish at the boundary can become physical boundary symmetries. The boundary may therefore carry edge modes or boundary charges.

For example, Chern–Simons theory on a closed three-manifold is gauge invariant. On a manifold with boundary, its gauge variation is a boundary term. To define the theory, one must either impose boundary conditions that restrict gauge transformations, add boundary degrees of freedom such as a Wess–Zumino–Witten model, or keep track of the boundary Hilbert space on which the would-be gauge transformations act.

This is not merely a technicality. The boundary modes of Chern–Simons theory are physical in many applications, including quantum Hall edges and topological phases.

## Boundaries and current conservation

Even without anomalies, a boundary modifies conservation laws. If $j^\mu$ is a conserved current in the bulk, then on a spatial region $\Sigma$ with boundary $\partial\Sigma$,

$$
\frac{d}{dt}\int_\Sigma d^{d-1}x\,j^0
=
-\int_{\partial\Sigma} \star j.
$$

Charge can leave the region through the boundary. With a boundary condition, the flux may vanish, or it may be absorbed by boundary degrees of freedom.

With an anomaly, the Ward identity can contain an additional local term:

$$
\partial_\mu j^\mu=\mathcal A[A].
$$

In a bulk–boundary system, the apparent nonconservation of boundary charge can be interpreted as inflow from the bulk. The boundary is not violating total symmetry; it is exchanging symmetry charge or anomalous variation with the bulk response.

:::note[Do not over-literalize charge flow]
For ordinary Chern–Simons examples, “charge flows from the bulk to the boundary” is an excellent physical picture. For general global, gravitational, fermionic, or finite anomalies, inflow may be better understood as cancellation of partition-function phases, not as literal transport of a locally conserved charge density.
:::

## Boundary counterterms

Boundary local counterterms can shift anomaly representatives. If

$$
Z_{\partial}[A]
\longmapsto
\exp\!\left(iS_{\partial,\rm ct}[A]\right)Z_{\partial}[A],
$$

then the boundary anomaly changes by

$$
\mathcal A_g[A]
\longmapsto
\mathcal A_g[A]
+
\frac{1}{2\pi}\left(S_{\partial,\rm ct}[A^g]-S_{\partial,\rm ct}[A]\right)
\quad \mathrm{mod}\;\mathbb Z.
$$

This can move anomaly between different boundary currents, between an interface and adjacent boundary terms, or between “consistent” and “covariant” representatives. It cannot remove a nontrivial anomaly class.

Boundary counterterms are therefore like gauge choices for anomaly bookkeeping: useful, sometimes necessary, but not capable of changing the underlying class.

## Examples

### Quantum Hall edge

A two-dimensional quantum Hall bulk has a three-dimensional spacetime response

$$
S_{\rm bulk}=\frac{k}{4\pi}\int A\wedge dA.
$$

On a manifold with boundary, this action is not invariant under $A\mapsto A+d\lambda$. The edge supports chiral modes whose anomaly cancels the bulk variation. The edge cannot be removed without changing the bulk phase, breaking the relevant symmetry, or adding compensating boundary structure.

### Topological insulator surface

A three-dimensional topological insulator can have a surface Dirac fermion protected by time-reversal symmetry and charge conservation. A single surface Dirac cone is anomalous as a purely two-dimensional system with the same symmetry implementation. It is consistent as the boundary of the three-dimensional bulk.

The surface need not always remain gapless. It can be gapped by breaking the protecting symmetry, or in interacting systems by developing symmetry-preserving topological order that carries the anomaly.

### Chiral gauge theory on a domain wall

A domain-wall mass can localize chiral fermion modes. The wall modes may have a gauge variation if isolated. The massive bulk modes generate an inflow term that cancels the wall anomaly. This is the domain-wall version of anomaly cancellation.

### Wess–Zumino–Witten boundary terms

In chiral Lagrangians, Wess–Zumino–Witten terms can encode anomaly matching. They are often written using an extension of the field configuration to one higher dimension. The dependence on the extension is harmless only when the coefficient is properly quantized. This is a boundary-style manifestation of the same inflow logic.

## Common pitfalls

**Pitfall 1: Saying an anomaly always forces a gapless boundary.**

No. A nontrivial anomaly forbids a trivial symmetric gapped boundary. Symmetry breaking and topological order can also match the anomaly.

**Pitfall 2: Forgetting that boundary conditions can change the symmetry.**

A boundary may preserve all of $G$, only a subgroup $H$, or a modified combination of bulk and boundary transformations. The relevant anomaly is the one for the preserved symmetry.

**Pitfall 3: Confusing gauge redundancy with boundary global symmetry.**

Gauge transformations that are pure redundancy in the bulk can become physical at a boundary if they act nontrivially on boundary data. This is one reason edge modes appear.

**Pitfall 4: Treating boundary counterterms as anomaly erasers.**

Counterterms can change representatives. They cannot trivialize a nonzero anomaly class.

**Pitfall 5: Ignoring orientation.**

The sign of a boundary anomaly depends on the boundary orientation. Interfaces carry the difference between the anomaly theories on the two sides.

## Relations to other pages

- [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/) explains the bulk–boundary cancellation mechanism used throughout this page.
- [Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/) gives the RG logic behind boundary anomaly matching.
- [Anomalies and Symmetry-Protected Phases](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomalies-and-symmetry-protected-phases/) develops the SPT interpretation.
- [Boundaries and Interfaces](/symmetry-anomalies-topology/defects-extended-operators/boundaries-and-interfaces/) treats boundary conditions and interfaces as extended operators.
- [Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/) develops the main topological response appearing in quantum Hall and edge-mode examples.
- [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) gives the advanced framework for relative theories and generalized boundary conditions.

## Research status

The basic statement that anomalies constrain boundaries is established. It is central in quantum Hall physics, topological insulators, chiral gauge theories, Wess–Zumino–Witten terms, domain-wall fermions, and SPT phases.

Active research concerns classification and construction: which anomalous boundaries admit symmetric topological order, how generalized and non-invertible symmetries act on boundary excitations, how crystalline and subsystem symmetries modify inflow, and how to formulate fully extended anomaly matching for defects of arbitrary codimension.

## Exercises

### 1. Why a trivial symmetric gapped boundary cannot match a nonzero anomaly

Assume a boundary theory flows to a unique gapped symmetric state with no topological order. Explain why it cannot match a nonzero ’t Hooft anomaly.

<details><summary><strong>Solution</strong></summary>

A unique symmetric gapped boundary has no long-distance degrees of freedom carrying an anomalous symmetry action. Its IR partition function is equivalent to the empty theory plus local symmetric counterterms. The empty theory has zero anomaly class. Since anomaly classes are invariant under symmetry-preserving RG flow, the UV anomaly must equal zero. This contradicts the assumption of a nonzero anomaly.

</details>

### 2. Why gaplessness is not forced

A boundary has a nontrivial anomaly. A colleague says, “Therefore the boundary must be gapless.” What is missing from this statement?

<details><summary><strong>Solution</strong></summary>

The anomaly forbids only a trivial symmetric gapped boundary. The boundary can also match the anomaly by spontaneously breaking the symmetry or by developing intrinsic topological order with an anomalous symmetry action. Therefore nonzero anomaly implies “not trivially symmetric gapped,” not necessarily “gapless.”

</details>

### 3. Interface anomaly as a difference

Two bulk phases have anomaly theories $\mathcal I_L$ and $\mathcal I_R$. Show why an interface between them carries the difference $[\mathcal I_L]-[\mathcal I_R]$.

<details><summary><strong>Solution</strong></summary>

The interface can be viewed as the boundary of the left bulk stacked with the orientation reversal of the right bulk. Orientation reversal changes the sign of the anomaly theory. Therefore the net inflow into the interface is

$$
[\mathcal A_{\rm interface}]=[\mathcal I_L]+[-\mathcal I_R]=[\mathcal I_L]-[\mathcal I_R].
$$

If this difference is nonzero, the interface must match it by gapless modes, symmetry breaking, topological order, or a relative realization.

</details>

### 4. Boundary counterterms and anomaly representatives

Let a boundary partition function transform as

$$
Z[A^g]=e^{2\pi i\mathcal A_g[A]}Z[A].
$$

After multiplying by $e^{iS_{\rm ct}[A]}$, what is the new anomaly representative?

<details><summary><strong>Solution</strong></summary>

The new partition function is

$$
Z'[A]=e^{iS_{\rm ct}[A]}Z[A].
$$

Thus

$$
Z'[A^g]
=
e^{iS_{\rm ct}[A^g]}e^{2\pi i\mathcal A_g[A]}Z[A]
=
\exp\!\left(2\pi i\mathcal A_g[A]+iS_{\rm ct}[A^g]-iS_{\rm ct}[A]\right)Z'[A].
$$

Therefore

$$
\mathcal A'_g[A]
=
\mathcal A_g[A]
+
\frac{1}{2\pi}\left(S_{\rm ct}[A^g]-S_{\rm ct}[A]\right)
\quad\mathrm{mod}\;\mathbb Z.
$$

The representative changed, but the anomaly class changed only by a counterterm-exact piece.

</details>

## References

- C. G. Callan and J. A. Harvey, “Anomalies and Fermion Zero Modes on Strings and Domain Walls,” *Nuclear Physics B* 250 (1985) 427.
- X.-G. Wen, “Theory of the Edge States in Fractional Quantum Hall Effects,” *International Journal of Modern Physics B* 6 (1992) 1711.
- E. Witten, “Global Aspects of Current Algebra,” *Nuclear Physics B* 223 (1983) 422.
- R. Dijkgraaf and E. Witten, “Topological Gauge Theories and Group Cohomology,” *Communications in Mathematical Physics* 129 (1990) 393.
- A. Kapustin, “Symmetry Protected Topological Phases, Anomalies, and Cobordisms,” arXiv:1403.1467.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” arXiv:1412.5148.
- D. S. Freed and M. J. Hopkins, “Reflection Positivity and Invertible Topological Phases,” arXiv:1604.06527.
- C. Wang, A. C. Potter, and T. Senthil, “Classification of Interacting Electronic Topological Insulators in Three Dimensions,” *Science* 343 (2014) 629.
- E. Witten and K. Yonekura, “Anomaly Inflow and the eta-Invariant,” arXiv:1909.08775.
- A. Kapustin and N. Saulina, “Topological Boundary Conditions in Abelian Chern–Simons Theory,” *Nuclear Physics B* 845 (2011) 393.

## Version history

- 2026-06-18: First polished draft. Added anomaly-matching boundary fates, trivial-boundary obstruction, interface anomaly difference, gauge-theory boundary subtleties, examples, and exercises.
