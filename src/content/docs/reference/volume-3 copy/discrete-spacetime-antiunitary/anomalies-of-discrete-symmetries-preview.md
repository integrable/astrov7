---
title: "Anomalies of Discrete Symmetries: Preview"
description: "Introduces anomalies of finite, orientation-reversing, and fermionic discrete symmetries as obstructions to consistent background coupling and gauging, with anomaly inflow as the organizing principle."
sidebar:
  label: "Discrete Anomalies"
  order: 9
level: Advanced
status: "Polished draft"
source: "Witten on global anomalies and fermion path integrals; Gaiotto–Kapustin–Seiberg–Willett on generalized symmetries; Freed–Hopkins on invertible phases; standard anomaly-inflow and Dijkgraaf–Witten references."
topics:
  - discrete anomalies
  - finite symmetries
  - anomaly inflow
  - fermionic anomalies
  - Pin structures
  - parity anomaly
  - time reversal anomaly
  - Dijkgraaf–Witten theory
canonicalTopics:
  - discrete-symmetry-anomaly
  - anomaly-inflow
  - obstruction-to-gauging
  - fermionic-anomaly
  - finite-symmetry-gauging
  - pin-anomaly
researchStatus:
  established:
    - "A discrete symmetry anomaly is an obstruction to coupling the symmetry to background fields or to gauging it in a fully local and symmetry-preserving way."
    - "Many discrete anomalies are naturally described by anomaly inflow from an invertible field theory in one higher dimension."
  active:
    - "The classification and physical realization of fermionic, reflection, higher-form, non-invertible, and crystalline anomalies remains an active area, especially when spin/Pin structures and global forms of symmetry are essential."
---

## Summary

A discrete symmetry can be exact and still be anomalous.

That sentence sounds contradictory only if “symmetry” means “a transformation of a classical Lagrangian.” In quantum field theory, a symmetry is better tested by asking whether it can be coupled to a background field and, if desired, gauged. A discrete symmetry has an anomaly when this coupling or gauging cannot be made consistently while preserving locality and the symmetry.

For a finite internal symmetry $G$, a background field is a principal $G$ bundle. Since $G$ is finite, this is the same local data as a flat $G$ gauge field. The partition function should be a gauge-invariant function

$$
Z[M,A]
$$

of the spacetime $M$ and the background $A$. If a background gauge transformation changes it by a nontrivial phase that cannot be removed by a local counterterm, then the symmetry has an anomaly.

For orientation-reversing or antiunitary symmetries, such as parity or time reversal, the background data are more geometric. One may need unoriented manifolds, reflection twists, and spin or Pin structures. The same idea remains:

$$
\text{anomaly}=\text{obstruction to consistent background coupling or gauging}.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![Discrete anomaly inflow: a d-dimensional boundary theory with background A has a non-invariant partition function; the variation is canceled by an invertible (d+1)-dimensional bulk action, showing why standalone gauging is obstructed.](/figures/symmetry-anomalies-topology/discrete-symmetry-anomaly-inflow.svg)

<figcaption>

An anomalous $d$-dimensional theory can be consistently viewed as the boundary of an invertible $(d+1)$-dimensional bulk. The boundary partition function changes under a background gauge transformation, but the bulk phase changes by the inverse amount. Without the bulk, gauging the discrete symmetry is obstructed.

</figcaption>
</figure>

This page is a preview. The full anomaly chapter will treat perturbative anomalies, global anomalies, anomaly polynomials, descent, consistent versus covariant anomalies, and Wess–Zumino consistency. Here we focus on the discrete-symmetry version needed to finish the chapter on $C$, $P$, $T$, reflection, spin, and Pin structures.

## Prerequisites

Read [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/), [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/), [Gauging Finite Symmetries: Preview](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-finite-symmetries-preview/), and [Spin Structures and Fermion Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/spin-structures-and-fermion-parity/) first.

For orientation-reversing symmetries, also read [Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/parity/), [Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/time-reversal/), [Antiunitary Symmetries](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/antiunitary-symmetries/), and [Reflection Positivity and Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/reflection-positivity-and-time-reversal/).

The page assumes the volume convention that a genuine global symmetry can be coupled to a background field before being gauged. For fermionic theories, the background data include spin or Pin structures when appropriate.

## Core idea

An ordinary Ward identity says that a symmetry operator can be moved without changing correlation functions except when it crosses charged insertions. A background-field version says that the generating functional is invariant under background gauge transformations.

For a continuous symmetry with background gauge field $A_\mu$, a gauge variation may look like

$$
\delta_\alpha W[A]=0.
$$

If instead

$$
\delta_\alpha W[A]\ne 0
$$

in a way that no allowed local counterterm can remove, the symmetry is anomalous.

For a discrete finite symmetry $G$, there is no infinitesimal parameter $\alpha$. The test is instead finite: compare $Z[M,A]$ and $Z[M,A^g]$, where $A^g$ is the background transformed by a $G$ gauge transformation. If

$$
Z[M,A^g]=Z[M,A]\,e^{i\Phi_g[M,A]},
$$

and the phase $e^{i\Phi_g}$ is not the variation of a local $d$-dimensional counterterm, then the symmetry is anomalous.

Anomalies are not failures of the theory to exist. They are failures of a proposed background coupling, gauging, or symmetry realization to exist in $d$ dimensions by itself. A theory with an anomaly can be perfectly consistent as a standalone QFT if the symmetry is kept global and the anomalous background is not gauged. It can also be perfectly consistent as the boundary of a higher-dimensional bulk.

## Setup and conventions

Let $M_d$ be Euclidean spacetime. For a finite internal symmetry group $G$, a background field is a principal $G$ bundle

$$
A\in \operatorname{Bun}_G(M_d),
$$

or equivalently a map

$$
A:M_d\to BG
$$

up to homotopy, where $BG$ is the classifying space of $G$.

For finite $G$, the local curvature vanishes because there is no Lie algebra-valued connection in the usual infinitesimal sense. Still, the background can have nontrivial holonomy around cycles:

$$
\operatorname{Hol}_\gamma(A)\in G.
$$

A nonanomalous theory assigns a gauge-invariant partition function

$$
Z[M_d,A]
$$

to such data. Gauging the symmetry then means a groupoid sum over these backgrounds:

$$
Z_{\text{gauged}}[M_d]
=\sum_{[A]\in \operatorname{Bun}_G(M_d)}\frac{1}{|\operatorname{Aut}(A)|}Z[M_d,A],
$$

possibly with a topological weight.

If $Z[M_d,A]$ is not gauge invariant, the groupoid sum is not well-defined. That is the most operational definition of a finite-symmetry anomaly.

:::note[Convention-sensitive source note]
For finite groups, physicists often write $A$ as a flat gauge field, a cocycle, a bundle, or a map to $BG$. These are different models for the same background data. The formulas in this preview are schematic and suppress triangulation, cochain, and groupoid-normalization details. Those details matter in explicit Dijkgraaf–Witten calculations.
:::

For fermionic theories, write

$$
Z[M_d,\rho,A]
$$

with spin or Pin data $\rho$. A discrete anomaly may involve $A$, $\rho$, the tangent bundle, or combinations of all three.

## Obstruction to gauging

The cleanest test for a discrete anomaly is:

> Can the symmetry be gauged?

For a finite internal symmetry, gauging means summing over twisted sectors. On a torus, for example, a two-dimensional theory with finite symmetry $G$ has sectors labeled by commuting holonomies

$$
g,h\in G,
\qquad gh=hg.
$$

The orbifold-like partition function has the schematic form

$$
Z_{\text{orb}}(T^2)=\frac{1}{|G|}\sum_{gh=hg} Z_{g,h}.
$$

If the symmetry is anomalous, the sectors $Z_{g,h}$ cannot be assigned phases that make the whole expression modular and gauge consistent. Sometimes the failure is a phase under a large diffeomorphism of the torus. Sometimes it is a failure of associativity for twisted-sector operators. Sometimes it is a sign depending on spin structure.

The important point is that anomaly is not detected only by local currents. Finite symmetries have no infinitesimal Noether current, but they can still have global obstructions.

## Anomaly inflow

The modern way to organize anomalies is anomaly inflow.

An anomalous $d$-dimensional theory is not best viewed as assigning a number to every closed $d$-manifold with backgrounds. Instead, it assigns a vector or boundary state in a one-dimensional Hilbert space determined by an invertible $(d+1)$-dimensional theory.

Schematic form:

$$
Z_{\partial}[M_d,A]\in \mathcal H_{\mathcal A}[M_d,A],
$$

where $\mathcal A$ is the anomaly theory. If $M_d=\partial X_{d+1}$, one may combine the boundary partition function with a bulk phase

$$
\exp(iS_{\mathcal A}[X_{d+1},\widetilde A])
$$

to get a gauge-invariant combined system:

$$
Z_{\text{combined}}=Z_{\partial}[M_d,A]\,\exp(iS_{\mathcal A}[X_{d+1},\widetilde A]).
$$

Under a background gauge transformation, the boundary phase and bulk phase cancel:

$$
\delta \log Z_{\partial}+i\delta S_{\mathcal A}=0.
$$

This does not mean the boundary anomaly has disappeared. It means the boundary theory is consistently realized as the edge of a higher-dimensional invertible phase.

## Finite internal symmetries and Dijkgraaf–Witten phases

For a bosonic theory with finite internal symmetry $G$ in $d$ dimensions, a large and useful class of anomaly actions is represented by group cohomology classes

$$
[\omega]\in H^{d+1}(BG,U(1)).
$$

Given a background $A:M_d\to BG$ and an extension $\widetilde A:X_{d+1}\to BG$, the bulk phase is schematically

$$
\exp\left(2\pi i\int_{X_{d+1}}\widetilde A^*\omega\right).
$$

If the boundary theory transforms by the inverse of this phase, its anomaly is described by $\omega$.

This formula is conceptually useful but has two caveats.

First, group cohomology is a model for many bosonic finite-symmetry anomalies, but not the whole story in every dimension or with every tangential structure.

Second, fermionic theories, time-reversal symmetries, reflection symmetries, and spin-charge relations generally require spin/Pin or cobordism refinements. Replacing every anomaly by an element of $H^{d+1}(BG,U(1))$ is a common overreach.

## Fermionic and Pin anomalies

For fermionic theories, anomaly classification often depends on a tangential structure such as

$$
Spin,
\qquad Pin^+,
\qquad Pin^-,
\qquad Spin^c,
$$

possibly combined with an internal symmetry group. A rough modern slogan is

$$
\text{fermionic anomaly}=\text{invertible spin/Pin theory in one higher dimension}.
$$

The background fields include both ordinary symmetry bundles and geometric structures. A time-reversal anomaly may show up only when the theory is placed on an unorientable Euclidean manifold with the correct Pin structure. A fermion-parity-related anomaly may show up as a sign depending on the spin structure.

The two questions

$$
\mathsf T^2=1
\qquad\text{and}\qquad
\mathsf T^2=(-1)^F
$$

lead to different anomaly theories. They are not minor variants of the same symmetry.

:::note[Convention-sensitive source note]
Pin labels are notoriously convention-sensitive. The anomaly is not the symbol $Pin^+$ or $Pin^-$ by itself; it is the full specification of the orientation-reversing symmetry, its square on local fermions, and the Euclidean continuation used to define background fields.
:::

## The parity anomaly as a model example

A classic example is a single massless Dirac fermion in $2+1$ dimensions coupled to a background $U(1)$ gauge field. Classically, one might expect parity and time reversal to be symmetries. Quantum mechanically, preserving gauge invariance requires a regularization that effectively produces a half-integer Chern–Simons term:

$$
S_{\rm CS}[A]=\frac{k}{4\pi}\int_M A\wedge dA,
$$

with a half-integer shift in $k$ for one Dirac fermion. But Chern–Simons terms are odd under orientation reversal. Therefore one cannot preserve both large-gauge invariance and parity/time reversal in a purely $2+1$-dimensional standalone theory.

This is called the **parity anomaly**.

The modern interpretation is inflow. The anomalous $2+1$-dimensional fermion can live on the boundary of a $3+1$-dimensional bulk topological insulator. The bulk theta term supplies the missing transformation so that the combined bulk-plus-boundary system is consistent.

The exact normalizations depend on whether the theory is spin, Spin-c, or coupled to ordinary electromagnetic backgrounds. The lesson is robust: a discrete spacetime symmetry can be obstructed by the phase of a fermion determinant.

## Global anomalies and large transformations

Perturbative anomalies are detected by infinitesimal transformations. Discrete anomalies and global anomalies are often detected only by large transformations.

Suppose $\mathcal G$ is a group of background gauge transformations. A global anomaly may appear as a phase under a transformation $g\in\mathcal G$ not connected to the identity:

$$
Z[A^g]=Z[A]e^{i\Phi_g[A]}.
$$

The famous four-dimensional $SU(2)$ global anomaly is of this type: a theory with an odd number of Weyl fermion doublets suffers a sign change under a large $SU(2)$ gauge transformation. Although this is a gauge anomaly rather than a finite internal global-symmetry anomaly, it is pedagogically important because it teaches the right lesson: the obstruction is invisible in the local anomaly polynomial but fatal for gauging.

Discrete global anomalies obey the same philosophy. They are often less about a local divergence equation and more about the global consistency of the partition function over background-field space.

## Discrete chiral symmetries

Anomalies can also reduce continuous symmetries to discrete subgroups. In a gauge theory with instantons, a classical axial $U(1)_A$ symmetry can fail quantum mechanically. A residual discrete subgroup may survive.

For example, if a chiral rotation changes the fermion measure by

$$
\exp\left(i\alpha\,\mathcal I\right),
$$

where $\mathcal I$ is an integer topological charge, then only values of $\alpha$ for which the phase is always one remain genuine symmetries. This is one way discrete chiral symmetries arise.

But the remaining discrete symmetry may itself have mixed anomalies with other symmetries. This is common in gauge theories, where discrete chiral symmetry, center symmetry, flavor symmetry, and spacetime symmetry can be linked in a nontrivial anomaly web.

The safe rule is:

$$
\text{survives the perturbative anomaly test}
\not\Rightarrow
\text{is anomaly-free in all backgrounds}.
$$

## Mixed anomalies

A discrete symmetry may be nonanomalous by itself but anomalous together with another symmetry. This is called a mixed anomaly.

For example, let $G$ and $H$ be two symmetries. Coupling only to $G$ backgrounds may be consistent, and coupling only to $H$ backgrounds may be consistent, but coupling to both may produce a nontrivial phase:

$$
Z[M,A_G^g,A_H]=Z[M,A_G,A_H]e^{i\Phi_g[M,A_G,A_H]}.
$$

Mixed anomalies are powerful because they constrain RG flows. If the UV theory has a mixed anomaly, then the IR theory must reproduce it. The IR cannot be a trivially gapped unique vacuum preserving all symmetries unless there is a topological sector that carries the anomaly.

For discrete symmetries, this is often the most useful anomaly-matching statement:

$$
\text{anomaly in UV}=\text{anomaly in IR}.
$$

The matching can be realized by massless degrees of freedom, symmetry breaking, topological order, a nontrivial TQFT, or boundary inflow.

## Relation to symmetry defects

A finite symmetry transformation can be represented by a codimension-one topological defect. For $g\in G$, write the defect as

$$
U_g(\Sigma).
$$

If the symmetry is nonanomalous, these defects fuse according to the group law:

$$
U_g\times U_h=U_{gh}
$$

in a strictly associative way, up to harmless local conventions.

An anomaly can appear as a projective or higher-cocycle failure of this defect calculus. For example, fusing three symmetry defects may differ by a topological phase controlled by a cocycle. In two dimensions, this is a very concrete way to see why anomalous finite symmetries cannot be orbifolded: the defect network does not have a gauge-invariant sum.

This viewpoint is the bridge from ordinary discrete anomalies to non-invertible symmetries and symmetry TFT. Once symmetry is encoded by topological defects, anomalies become obstructions to choosing consistent local junctions, fusion, and gauging data.

## What an anomaly is not

A discrete anomaly is not the same as explicit breaking. If the Lagrangian contains a term that is not invariant under a $\mathbb Z_2$ transformation, then the $\mathbb Z_2$ is not a symmetry. There is no anomaly puzzle.

A discrete anomaly is not the same as spontaneous breaking. If the theory has two vacua exchanged by $\mathbb Z_2$, then the symmetry may be exact but spontaneously broken. Gauging can still be possible if there is no anomaly.

A discrete anomaly is not the same as a regulator inconvenience. Sometimes one regulator hides a symmetry and another preserves it. A genuine anomaly means no regulator and no local counterterm can preserve all desired symmetries and locality simultaneously.

A discrete anomaly is not always visible in a local current equation. Finite symmetries may have no current. Orientation-reversing symmetries may not be continuously connected to anything. Global obstructions live in global background-field data.

## Matching and constraints

Anomalies are RG invariants. If a UV theory has a discrete anomaly, the IR must carry the same anomaly.

This has sharp consequences. Suppose a $d$-dimensional theory has a finite symmetry $G$ with anomaly $\mathcal A$. A trivially gapped symmetric phase would have a partition function that is a gauge-invariant number for every $G$ background. That cannot reproduce a nontrivial anomaly.

Therefore a nontrivial anomaly forbids the simplest IR outcome:

$$
\text{unique gapped vacuum preserving }G
$$

unless the anomaly is canceled by coupling to a bulk or by adding other degrees of freedom. The IR must instead contain at least one of:

- massless excitations;
- spontaneous symmetry breaking;
- topological order or a TQFT;
- a boundary realization of a higher-dimensional invertible phase;
- nontrivial defect or categorical symmetry data.

This is why anomalies are useful even when they are “only” discrete. They constrain phases without requiring weak coupling.

## Common pitfalls

**Pitfall 1: “Discrete symmetries cannot have anomalies because they have no current.”**

False. The background-field and gauging tests do not require an infinitesimal current.

**Pitfall 2: “If a symmetry cannot be gauged, it is not a symmetry.”**

False. An anomalous symmetry can be an exact global symmetry. The anomaly says it cannot be gauged as a standalone $d$-dimensional operation.

**Pitfall 3: “All finite-symmetry anomalies are group cohomology classes.”**

Too quick. Group cohomology captures many bosonic finite internal-symmetry anomalies. Fermions, reflections, crystalline symmetries, higher-form symmetries, and some beyond-group-cohomology phases need refined frameworks.

**Pitfall 4: “The parity anomaly means parity is explicitly broken.”**

No. The point is that in the quantum theory one cannot preserve all desired structures simultaneously, such as parity/time reversal and large-gauge invariance, in a purely three-dimensional standalone regularization.

**Pitfall 5: “Adding a bulk cancels the anomaly, so the boundary symmetry becomes ordinary.”**

The combined system is gauge invariant. The boundary still carries the anomaly; it is realized by inflow from the bulk.

## Relations to other pages

This page closes the **Discrete, Spacetime, and Antiunitary Symmetries** chapter by explaining how $C$, $P$, $T$, reflection, spin, Pin, and finite symmetry data can fail the background-field consistency test.

It depends on the background/gauging pages: [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/), [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/), and [Gauging Finite Symmetries: Preview](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-finite-symmetries-preview/).

It also depends on [Spin Structures and Fermion Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/spin-structures-and-fermion-parity/) because many discrete anomalies of time reversal, reflection, and fermionic symmetries are meaningless unless spin/Pin data are specified.

The full anomaly chapter will expand this preview into perturbative anomalies, global anomalies, descent equations, anomaly polynomials, consistent versus covariant anomalies, and Wess–Zumino consistency. The ’t Hooft anomaly chapter will emphasize anomaly matching and RG constraints.

## Research status

The obstruction-to-gauging definition of anomalies is established. Anomaly inflow is the standard conceptual framework for understanding why anomalous boundary theories are consistent when paired with suitable bulk invertible phases.

The active frontier is classification and application. Modern work studies anomalies of higher-form symmetries, higher-group symmetries, non-invertible symmetries, subsystem symmetries, crystalline symmetries, fermionic symmetries, and mixed spacetime-internal symmetries. Spin and Pin cobordism methods give a powerful language for many of these problems, but applying the resulting classifications to concrete continuum QFTs still requires physical judgment.

For readers, the most important durable lesson is not a particular classification table. It is the diagnostic:

$$
\boxed{\text{couple to backgrounds, test gauge invariance, classify unremovable phases.}}
$$

That workflow survives changes in notation and research fashion.

## Exercises

### Exercise 1: A phase under background gauge transformations

Suppose a finite-symmetry background transformation sends

$$
Z[M,A]\mapsto Z[M,A]e^{i\Phi[M,A]}.
$$

What must be true for this phase to represent no genuine anomaly?

<details><summary><strong>Solution</strong></summary>

The phase must be removable by a local counterterm in $d$ dimensions. That is, there should exist a local functional $S_{\rm ct}[M,A]$ such that its variation under the same background gauge transformation is

$$
\delta S_{\rm ct}[M,A]=-\Phi[M,A]
$$

modulo $2\pi$. Then redefining

$$
Z[M,A]\mapsto Z[M,A]e^{iS_{\rm ct}[M,A]}
$$

makes the partition function gauge invariant. If no such local counterterm exists, the phase is a genuine anomaly.

</details>

### Exercise 2: Why anomalous symmetries cannot be gauged

Explain why the groupoid sum

$$
Z_{\text{gauged}}[M]=\sum_{[A]}\frac{1}{|\operatorname{Aut}(A)|}Z[M,A]
$$

is not well-defined if $Z[M,A]$ is not invariant under background gauge transformations.

<details><summary><strong>Solution</strong></summary>

The sum is over gauge-equivalence classes of backgrounds. For it to be well-defined, $Z[M,A]$ must assign the same value to all representatives of the same class. If a gauge transformation changes $Z[M,A]$ by a nontrivial phase, then the contribution of a class depends on the arbitrary representative chosen. Thus the gauged partition function is not a well-defined number. This is the operational obstruction to gauging.

</details>

### Exercise 3: Inflow cancellation

Let a boundary theory transform as

$$
Z_{\partial}\mapsto Z_{\partial}e^{i\Phi}.
$$

A bulk invertible theory transforms as

$$
e^{iS_{\rm bulk}}\mapsto e^{iS_{\rm bulk}}e^{-i\Phi}.
$$

Show that the combined system is invariant.

<details><summary><strong>Solution</strong></summary>

The combined partition function is

$$
Z_{\rm combined}=Z_{\partial}e^{iS_{\rm bulk}}.
$$

Under the transformation,

$$
Z_{\rm combined}\mapsto
Z_{\partial}e^{i\Phi}\,e^{iS_{\rm bulk}}e^{-i\Phi}
=Z_{\partial}e^{iS_{\rm bulk}}.
$$

The phases cancel. This is anomaly inflow. The boundary anomaly is not absent; it is canceled by the bulk variation.

</details>

### Exercise 4: Anomaly matching and a trivial IR

A UV theory has a nontrivial anomaly for an exact finite symmetry $G$. Can the IR be a unique trivially gapped vacuum preserving $G$? Explain.

<details><summary><strong>Solution</strong></summary>

No, not as a standalone $d$-dimensional theory. A unique trivially gapped symmetric vacuum has no massless degrees of freedom, no symmetry breaking, and no topological order. Its partition function in background $G$ fields is a gauge-invariant local number and cannot reproduce a nontrivial anomaly. The IR must instead contain massless modes, symmetry breaking, topological order, a TQFT, or be realized as the boundary of a bulk invertible phase.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*. See the sections on chiral gauge theories, anomalies in global symmetries, and fermion path-integral measures.
- Steven Weinberg, *The Quantum Theory of Fields*, Vols. I and II. See the discussions of discrete symmetries, global anomalies, gauge invariance, and BRST.
- Sidney Coleman, *Aspects of Symmetry*. See the lectures on soft pions, current commutators, instantons, and the $U(1)$ problem.
- Edward Witten, “An SU(2) Anomaly,” *Physics Letters B* 117 (1982) 324–328.
- Edward Witten, “Fermion Path Integrals And Topological Phases,” arXiv:1508.04715.
- Xie Chen, Zheng-Cheng Gu, Zheng-Xin Liu, and Xiao-Gang Wen, “Symmetry Protected Topological Orders and the Group Cohomology of Their Symmetry Group,” arXiv:1106.4772.
- Robbert Dijkgraaf and Edward Witten, “Topological Gauge Theories and Group Cohomology,” *Communications in Mathematical Physics* 129 (1990) 393–429.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” arXiv:1412.5148.
- Daniel S. Freed and Michael J. Hopkins, “Reflection Positivity and Invertible Topological Phases,” arXiv:1604.06527.
- Edward Witten and Kazuya Yonekura, “Anomaly Inflow and the η-Invariant,” arXiv:1909.08775.

## Version history

- 2026-06-18: First polished draft. Added obstruction-to-gauging diagnostic, finite-background formulation, inflow picture, Dijkgraaf–Witten preview, fermionic/Pin caveats, parity anomaly example, mixed anomalies, symmetry-defect viewpoint, exercises, and references.
