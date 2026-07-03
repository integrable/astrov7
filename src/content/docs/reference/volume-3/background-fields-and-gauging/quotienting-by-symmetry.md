---
title: "Quotienting by Symmetry"
description: "Disentangles the different meanings of quotienting by a symmetry in QFT: gauge redundancy, global-form quotients, orbifolds, Hilbert-space projection, moduli-space quotients, and cosets."
sidebar:
  label: "Quotienting by Symmetry"
  order: 7
level: Graduate
status: "Polished draft"
source: "Faddeev–Popov and BRST treatments of gauge quotients; Dijkgraaf–Witten and orbifold literature on finite quotient QFTs; Coleman and Weinberg on cosets and spontaneous symmetry breaking."
topics:
  - quotient by symmetry
  - gauge redundancy
  - orbifold
  - gauging
  - invariant states
  - twisted sectors
  - global form
  - coset spaces
canonicalTopics:
  - quotient-by-symmetry
  - gauge-orbit-space
  - orbifold-qft
  - invariant-hilbert-space
  - global-form-quotient
  - coset-space
  - stacky-quotient
researchStatus:
  established:
    - "In QFT, quotienting can mean several distinct operations; gauging a global symmetry is a quantum operation, while quotienting gauge redundancy removes overcounted descriptions."
  active:
    - "Modern work refines quotienting using defects, stacks, higher symmetries, non-invertible gauging, boundary conditions, and symmetry TFT."
---

## Summary

“Quotient by a symmetry” is one of the most useful phrases in QFT — and one of the easiest phrases to misuse.

It can mean any of the following:

$$
\mathcal F/\mathcal G
\qquad\text{gauge-equivalence classes of field configurations,}
$$

$$
\mathcal H^G
\qquad\text{the invariant subspace of a Hilbert space,}
$$

$$
\mathcal T/G
\qquad\text{the theory obtained by gauging a global finite symmetry,}
$$

$$
\widetilde G/\Gamma
\qquad\text{a global-form quotient of a symmetry or gauge group,}
$$

or

$$
G/H
\qquad\text{a coset space of vacua or Goldstone fields.}
$$

These are related but not identical. Confusing them causes real errors: missing twisted sectors, dividing by a gauge group twice, treating gauge redundancy as physical symmetry, forgetting fixed-point sectors, or claiming an anomalous symmetry can be quotiented.

<figure class="doc-figure" style="--figure-width: 53rem;">

![A dictionary diagram showing five different meanings of quotient by symmetry: gauge-orbit quotient, finite gauging/orbifold, Hilbert-space invariant projection, global-form quotient, and coset or moduli quotient. The bottom warning says that quotienting points is not the same as quotienting quantum data.](/figures/symmetry-anomalies-topology/quotienting-by-symmetry-dictionary.svg)

<figcaption>

The word “quotient” is a dictionary, not a definition. The intended operation depends on whether one is removing gauge redundancy, gauging a global symmetry, choosing the faithful global form, projecting states, or describing a moduli/coset space.

</figcaption>
</figure>

The main lesson is:

$$
\text{classically one may quotient points; quantum mechanically one must quotient data}.
$$

The data include Hilbert spaces, bundles, defects, operator algebras, counterterms, anomalies, and boundary conditions.

## Prerequisites

Read [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/) and [Gauging Finite Symmetries: Preview](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-finite-symmetries-preview/) first. You should also know the conceptual distinction between global symmetry and gauge redundancy from [Background Fields versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/).

For the coset examples, it helps to know the broad idea of spontaneous symmetry breaking and Goldstone modes. No full coset construction is assumed.

## Core idea

A symmetry action partitions something into orbits. The tempting move is to identify points in the same orbit and call the quotient the physical object.

For finite-dimensional classical mechanics, this is sometimes enough. If a group $G$ acts freely and properly on a space $X$, the quotient $X/G$ is a well-behaved space whose points are $G$-orbits.

QFT is less forgiving. The “something” being quotiented may be:

- a space of field configurations,
- a phase space with a symplectic structure,
- a Hilbert space,
- an operator algebra,
- a category of boundary conditions or defects,
- a set of background bundles,
- a path integral measure,
- or an entire theory.

Each has its own quotient rule. The naive operation

$$
x\sim g\cdot x
$$

is only the beginning.

## Setup and conventions

Let $G$ be a group acting on some object. We write $X/G$ for a classical orbit-space quotient when $X$ is a space. We write $\mathcal T/G$ for the QFT obtained by gauging a global symmetry $G$ of a theory $\mathcal T$. We write $\mathcal F/\mathcal G$ for quotienting a field-configuration space by gauge transformations.

When $G$ is finite, a group action on a Hilbert space has invariant projector

$$
\Pi_G=\frac{1}{|G|}\sum_{g\in G}U_g.
$$

When $G$ is continuous and compact, the analogous formal projector uses Haar measure,

$$
\Pi_G=\int_G dg\,U_g,
$$

with $\int_G dg=1$. For gauge redundancy, this formal expression is not the whole story because the gauge group is infinite-dimensional and acts on fields with local stabilizers, zero modes, boundaries, and possible Gribov complications.

:::note[Convention-sensitive source note]
The notation $\mathcal T/G$ is reserved here for gauging a global symmetry of a QFT. The notation $\mathcal F/\mathcal G$ is reserved for removing gauge redundancy from a configuration space. Both are quotients, but they are different operations with different physical meanings.
:::

## Meaning 1: quotienting gauge redundancy

Gauge transformations relate different descriptions of the same physical configuration. If $\mathcal F$ is the space of gauge fields and matter fields, and $\mathcal G$ is the gauge group, the physical configuration space is morally

$$
\mathcal F/\mathcal G.
$$

For a $U(1)$ gauge field,

$$
A_\mu\sim A_\mu+\partial_\mu\alpha.
$$

For a nonabelian connection,

$$
A_\mu\sim A_\mu^g
=gA_\mu g^{-1}-i(\partial_\mu g)g^{-1}
$$

in the convention $D_\mu=\partial_\mu-iA_\mu$.

This quotient is not a physical symmetry operation. It does not map one physical state to a different physical state. It removes redundant labels from the description.

In the path integral, one cannot usually integrate over $\mathcal F/\mathcal G$ directly. Instead one writes

$$
\frac{1}{\operatorname{Vol}(\mathcal G)}\int_{\mathcal F}\mathcal D\Phi\,e^{iS[\Phi]}
$$

as a slogan and then implements it by gauge fixing, Faddeev–Popov determinants, BRST symmetry, or BV methods.

The quotient can be singular. Some field configurations have nontrivial stabilizers: gauge transformations that leave them fixed. Boundary conditions can turn would-be gauge transformations into physical edge symmetries. Large gauge transformations can label topological sectors. Thus even for gauge redundancy, quotienting means more than crossing out variables.

## Meaning 2: projecting to invariant states

If $G$ is a genuine global symmetry of a quantum theory, it acts on the Hilbert space by operators $U_g$. The invariant subspace is

$$
\mathcal H^G=\{\psi\in\mathcal H\mid U_g\psi=\psi\text{ for all }g\in G\}.
$$

For finite $G$ this is the image of

$$
\Pi_G=\frac{1}{|G|}\sum_{g\in G}U_g.
$$

This construction is often the first step in gauging a finite symmetry. It is not the full gauged theory.

For example, in a two-dimensional orbifold, the invariant subspace of the untwisted Hilbert space is only

$$
\mathcal H_1^G.
$$

The gauged Hilbert space is instead

$$
\mathcal H_{\mathcal T/G}
=\bigoplus_{[g]}\mathcal H_g^{C(g)},
$$

where $\mathcal H_g$ is the $g$-twisted sector and $C(g)$ is the centralizer of $g$.

Thus:

$$
\mathcal H^G\text{ is a projection; }\mathcal T/G\text{ is a new QFT}.
$$

The projection sees charged states. The gauged theory also sees bundles.

## Meaning 3: gauging a finite global symmetry

When a finite global symmetry $G$ is gauged, the result is often called a quotient theory or orbifold:

$$
\mathcal T\longmapsto\mathcal T/G.
$$

The path-integral definition is the finite-background sum

$$
Z_{\mathcal T/G}(M)
=
\sum_{[P\to M]}
\frac{1}{|\operatorname{Aut}(P)|}
Z_{\mathcal T}[M;P]e^{iS_\omega[P]}.
$$

This expression quotients in two ways at once.

First, it identifies background fields related by finite gauge transformations. This is why we sum over isomorphism classes or divide by automorphism groups.

Second, it changes the operator content of the theory. Non-invariant local operators are removed as genuine local operators, but twisted-sector operators and topological defects may appear.

This operation requires the finite symmetry to be anomaly-free. If the background partition function is not gauge invariant as a function of the finite background $P$, the quotient theory is not a standalone QFT.

## Meaning 4: quotienting the global form of a group

Sometimes “quotienting by symmetry” means choosing the faithful group that actually acts.

If a normal subgroup $K\subset G$ acts trivially on all relevant physical objects, the faithful symmetry is

$$
G_{\mathrm{faithful}}=G/K.
$$

For connected Lie groups, one often starts from a simply connected group $\widetilde G$ and quotients by a subgroup of its center:

$$
G=\widetilde G/\Gamma,
\qquad
\Gamma\subset Z(\widetilde G).
$$

For example,

$$
SO(3)=SU(2)/\mathbb Z_2.
$$

This is not a gauging operation by itself. It is a statement about which finite transformations, representations, background bundles, and large transformations are part of the symmetry structure.

Changing $SU(2)$ to $SO(3)$ changes which representations are honest and which background bundles are allowed. It does not automatically mean that one has gauged the center. In gauge theory, gauging a one-form center symmetry can change the global form of the gauge group; that is a more specific operation developed later.

## Meaning 5: quotienting a moduli space or coset

In spontaneous symmetry breaking, a group $G$ may act transitively on a set of degenerate vacua, while a subgroup $H$ preserves one chosen vacuum. The vacuum manifold is then

$$
\mathcal M_{\mathrm{vac}}
\simeq G/H.
$$

The Goldstone fields can be viewed locally as coordinates on $G/H$. This quotient is a coset space, not a gauge quotient and not a finite orbifold unless extra operations are added.

For example, if

$$
G=O(N),
\qquad
H=O(N-1),
$$

then

$$
G/H\simeq S^{N-1}.
$$

The nonlinear sigma model target $S^{N-1}$ describes low-energy Goldstone modes for the symmetry-breaking pattern $O(N)\to O(N-1)$.

There is a related but different construction in gauge theory. If a scalar field has vacuum manifold $G/H$ and part of $G$ is gauged, some would-be Goldstone modes are gauge redundancy and are eaten by gauge fields. One should not say simply “the gauge symmetry is broken and then quotient by it.” Gauge redundancy is not a physical symmetry to be broken. The physical statement is about the spectrum, gauge-invariant order parameters, and the Higgs mechanism.

## Geometric quotients and fixed points

Suppose a finite group $G$ acts on a target space $X$. The naive quotient is the orbit space

$$
X/G.
$$

If the action is free, this is often a good geometric space. If the action has fixed points, $X/G$ has orbifold singularities. Quantum theory does not generally allow us to ignore those fixed points.

A sigma model with target $X/G$ is not always the same as the orbifold of a sigma model with target $X$ by $G$. The orbifold remembers twisted sectors associated with strings or fields closing only up to the group action. In stringy and two-dimensional CFT language, these sectors are localized near fixed loci and are essential for consistency.

The modern mathematical language for this memory is a **stack quotient** or **groupoid quotient**:

$$
[X/G],
$$

which remembers not only orbits but stabilizer groups. The full stack language is not needed for most calculations, but the lesson is practical: fixed points carry quantum data.

## Quotienting operator algebras

In algebraic language, a symmetry $G$ acts by automorphisms of an operator algebra $\mathcal A$. The invariant subalgebra is

$$
\mathcal A^G=\{\mathcal O\in\mathcal A\mid g\cdot\mathcal O=\mathcal O\text{ for all }g\in G\}.
$$

For local operators, gauging keeps $\mathcal A^G$ as part of the local operator algebra. But again, this is only part of the quotient theory. Defect operators, twisted sectors, topological lines, boundary conditions, and nonlocal observables are not determined by $\mathcal A^G$ alone.

This distinction becomes dramatic in generalized symmetry. A symmetry may act trivially on local operators but nontrivially on line operators. Quotienting only the local operator algebra would miss the symmetry entirely.

## Quotienting and anomalies

A global symmetry can be quotiented as a QFT operation only if it can be gauged. The obstruction is an anomaly.

For finite $G$, an anomaly means that the background partition function

$$
Z_{\mathcal T}[M;P]
$$

cannot be made into a gauge-invariant function of the finite background $P$. For continuous $G$, the same idea appears as failure of the generating functional $Z[A]$ to be invariant under background gauge transformations.

An anomalous symmetry can still be useful. It constrains RG flows, boundary conditions, defects, and possible phases. It may become gaugeable when paired with a bulk inflow theory. But the standalone quotient $\mathcal T/G$ is not defined without adding extra data that cancels the anomaly.

This is the clean way to read the phrase:

$$
\text{an anomaly is an obstruction to quotienting a global symmetry by gauging it.}
$$

## Example: charge conjugation versus gauge quotient

Consider QED with gauge field $A_\mu$ and charged matter. Gauge transformations act locally by

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

They are redundancy. Physical operators must be gauge invariant or appropriately dressed.

Charge conjugation, by contrast, may act as a genuine discrete global symmetry:

$$
A_\mu\mapsto -A_\mu,
\qquad
\psi\mapsto C\bar\psi^T.
$$

Quotienting by gauge transformations is part of defining the QED configuration space. Gauging charge conjugation, if allowed and if all background data are specified, would be a new QFT operation involving orientation of charge sectors and possible discrete gauge backgrounds.

The two quotients are not the same kind of quotient. The first removes redundant descriptions. The second changes the theory.

## Example: scalar sign flip

Let $\mathcal T$ contain a real scalar with a $\mathbb Z_2$ global symmetry

$$
\phi\mapsto -\phi.
$$

The invariant local operators include

$$
\phi^2,
\qquad
\phi\partial_\mu\phi,
\qquad
\phi^4,
$$

while $\phi$ is odd and is projected out of the gauge-invariant local algebra after gauging.

But the gauged theory is not only the theory generated by even polynomials in $\phi$. On a spacetime with nontrivial cycles, one must sum over $\mathbb Z_2$ bundles. Across a codimension-one branch cut, $\phi$ may change sign. Endpoints or boundaries of such cuts can create twist defects, depending on dimension.

So the naive quotient “identify $\phi$ and $-\phi$” catches the local invariant idea but misses the bundle and defect sectors.

## Example: coset is not orbifold

The quotient

$$
SU(2)/U(1)\simeq S^2
$$

appears in many sigma models and in the description of Goldstone modes. This quotient is a homogeneous space. It is not, by itself, the result of gauging the $U(1)$ symmetry of a QFT.

A sigma model with target $S^2$ may be constructed by introducing an $SU(2)$-valued field and a local $U(1)$ redundancy, then quotienting by that redundancy. That is a useful presentation. But the physical global symmetry of the resulting model, its topological sectors, and its possible theta terms require separate analysis.

The moral: coset notation describes a space. A QFT requires an action, measure, operator content, topological sectors, and symmetries.

## Practical decision tree

When a page says “quotient by $G$,” ask five questions.

| Question | If yes, the quotient likely means |
|---|---|
| Is $G$ gauge redundancy of the variables? | Remove overcounting: $\mathcal F/\mathcal G$, gauge fixing, BRST/BV |
| Is $G$ a finite global symmetry of a QFT? | Gauge/orbifold: $\mathcal T/G$, sum over flat bundles |
| Does $G$ act on a Hilbert space in one fixed sector? | Projector: $\mathcal H^G$ |
| Is a central subgroup acting trivially? | Faithful/global-form quotient: $G/K$ |
| Is this about vacua or Goldstones? | Coset/moduli quotient: $G/H$ or $\mathcal M/G$ |

If none of these is clear, the phrase is under-specified.

## Common pitfalls

**Pitfall 1: Equating $\mathcal H^G$ with $\mathcal T/G$.**  
The invariant Hilbert space in the untwisted sector is not the full gauged theory. Finite gauging includes twisted sectors and background sums.

**Pitfall 2: Treating gauge redundancy as physical symmetry.**  
Gauge transformations do not create new physical states. They relate different descriptions of the same state, except for boundary or asymptotic transformations that may become physical.

**Pitfall 3: Forgetting fixed points.**  
A geometric quotient with fixed points can have singularities. In quantum theory, fixed loci often support additional sectors or operators.

**Pitfall 4: Saying “divide by $G$” without specifying a measure.**  
Finite quotients use groupoid weights. Continuous gauge quotients require gauge fixing or an equivalent formalism.

**Pitfall 5: Quotienting an anomalous symmetry.**  
If the symmetry has a ’t Hooft anomaly, the gauged quotient is obstructed unless extra inflow or degrees of freedom cancel the anomaly.

## Relations to other pages

- [Global Form of Symmetry Groups](/symmetry-anomalies-topology/background-fields-and-gauging/global-form-of-symmetry-groups/) explains quotienting a universal cover by a central subgroup.
- [Gauging Finite Symmetries: Preview](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-finite-symmetries-preview/) explains the finite orbifold operation $\mathcal T/G$.
- **Gauge Symmetry Is Redundancy** later develops the redundancy quotient.
- **Goldstone Modes** and **Coset Construction: Preview** later develop $G/H$ for spontaneous symmetry breaking.
- **Topological Defects as Symmetries** later explains how quotienting can produce non-invertible defect structures.

## Research status

The elementary distinctions on this page are standard. Gauge redundancy, Hilbert-space projection, finite gauging, global-form quotients, and coset spaces are all established concepts.

The modern frontier is not whether quotients exist, but what data a quotient must retain. In categorical and symmetry-TFT language, quotienting is often described by changing boundary conditions, condensing algebra objects, gauging topological defects, or passing to equivariant categories. In geometric language, one often replaces orbit spaces by stacks or groupoids to retain stabilizers. These refinements are not cosmetic; they prevent the loss of twisted sectors, line operators, and anomalies.

The practical lesson for this volume is stable: whenever the word “quotient” appears, identify the object being quotiented and the data that survive the quotient.

## Exercises

### Exercise 1: Projection is not the full orbifold

Let a finite group $G$ act on a two-dimensional QFT. Explain why the invariant untwisted Hilbert space $\mathcal H_1^G$ is generally not the full Hilbert space of the orbifold theory.

<details><summary><strong>Solution</strong></summary>

The invariant untwisted Hilbert space contains states on a spatial circle with trivial $G$ holonomy, projected by the group action. The orbifold theory must also include sectors with nontrivial holonomy around the spatial circle. These are the $g$-twisted sectors $\mathcal H_g$. The full expression is schematically

$$
\mathcal H_{\mathcal T/G}
=\bigoplus_{[g]}\mathcal H_g^{C(g)}.
$$

The $g=1$ term is $\mathcal H_1^G$. The terms with $g\ne 1$ are missing if one only projects.

</details>

### Exercise 2: Faithful quotient

Suppose $G$ acts on all local operators through a representation with kernel $K\subset G$. Show that the local operator action factors through $G/K$.

<details><summary><strong>Solution</strong></summary>

If $K$ is the kernel, then for every $k\in K$ and every local operator $\mathcal O$,

$$
k\cdot\mathcal O=\mathcal O.
$$

If two elements $g,g'\in G$ differ by an element of $K$, then $g'=gk$ for some $k\in K$, and

$$
g'\cdot\mathcal O=(gk)\cdot\mathcal O=g\cdot(k\cdot\mathcal O)=g\cdot\mathcal O.
$$

Therefore the action depends only on the coset $gK\in G/K$. The action on local operators factors through the quotient group $G/K$.

The caveat is that extended operators may transform under $K$ even if local operators do not. Then the faithful symmetry of the full theory may require including those extended objects.

</details>

### Exercise 3: Coset dimension

Let a compact Lie group $G$ break spontaneously to a closed subgroup $H$. Show that the number of Goldstone coordinates in the simplest relativistic internal-symmetry case is

$$
\dim G-\dim H.
$$

<details><summary><strong>Solution</strong></summary>

The vacuum manifold is the coset space $G/H$. Its tangent space at the identity coset is

$$
T_{eH}(G/H)\simeq \mathfrak g/\mathfrak h,
$$

where $\mathfrak g$ and $\mathfrak h$ are the Lie algebras of $G$ and $H$. Therefore

$$
\dim(G/H)=\dim\mathfrak g-\dim\mathfrak h=\dim G-\dim H.
$$

In a Lorentz-invariant theory with ordinary internal symmetries and standard assumptions, this is the number of Goldstone bosons. Nonrelativistic systems can have modified counting because pairs of broken generators can create one type-B Goldstone mode.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially “Secret Symmetry” and “Classical Lumps and Their Quantum Descendants.” Cosets, spontaneous symmetry breaking, gauge fields, and topological sectors.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters 15–17. Gauge quotient, Faddeev–Popov, BRST, external fields, and gauge-theory renormalization.
- Mark Srednicki, *Quantum Field Theory*, especially §§69–74. Gauge theory, gauge fixing, ghosts, and BRST symmetry.
- Robbert Dijkgraaf and Edward Witten, “Topological Gauge Theories and Group Cohomology,” 1990. Finite gauging as a sum over finite gauge fields with topological weights.
- Lance Dixon, Jeffrey Harvey, Cumrun Vafa, and Edward Witten, “Strings on Orbifolds,” 1985–1986. Classic twisted-sector construction.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” 2015. Modern background-field viewpoint on gauging and symmetry operators.

## Version history

- **2026-06-17:** Initial polished page disentangling gauge quotients, global symmetry gauging, invariant projection, global-form quotients, geometric orbifolds, and cosets.
