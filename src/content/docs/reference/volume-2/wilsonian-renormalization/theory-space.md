---
title: "Theory Space"
description: "Explains Wilsonian theory space as the space of local effective actions, with RG flow as a vector field, fixed points, critical surfaces, and coordinate-dependent couplings."
sidebar:
  label: "Theory Space"
  order: 4
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Zinn-Justin 2021; Weinberg Vol. II ch. 18; Schwartz ch. 23; Burgess chs. 2–3; Altland and Simons ch. 6."
topics:
  - theory space
  - Wilsonian RG
  - fixed points
  - critical surfaces
  - coupling coordinates
  - redundant operators
canonicalTopics:
  - theory-space
  - wilsonian-rg-flow
  - critical-surface
  - fixed-point-linearization
  - redundant-operators
researchStatus:
  established:
    - "Theory space is the standard geometric language for Wilsonian RG: actions are points, couplings are coordinates, and coarse graining plus rescaling defines an RG flow."
  active:
    - "In gauge theories, gravity, dual descriptions, categorical symmetry settings, and nonperturbative RG, the correct global description of theory space can be subtle and sometimes only partially known."
---

## Summary

**Theory space** is the space whose points are possible Wilsonian actions. Choosing coordinates on theory space means choosing an operator basis and writing

$$
S_\Lambda=\sum_i g_i(\Lambda)\int d^d x\,\mathcal O_i(x).
$$

A Wilsonian RG step sends one point in this space to another point:

$$
S_\Lambda
\longrightarrow
S_{\Lambda e^{-d\ell}}
\longrightarrow
\text{rescaled action at cutoff }\Lambda.
$$

After the rescaling step, the cutoff has been restored, so the new action can be compared with the old one. Repeating the procedure gives a trajectory through theory space. In dimensionless coordinates,

$$
\frac{d\tilde g^i}{d\ell}=\mathcal B^i(\tilde g),
$$

where $\ell$ increases toward the infrared in this chapter.

The geometric picture is powerful because it separates universal structure from coordinates. A fixed point, the number of relevant directions, and critical exponents are meaningful. The numerical value of a coupling in a particular cutoff scheme is usually not.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Theory space near a fixed point, showing an RG vector field, a critical surface, relevant, irrelevant, and marginal directions](/figures/renormalization-rg-eft/theory-space-linearization.svg)

<figcaption>

Near a fixed point $g_*$, theory space is locally organized by scaling directions. Irrelevant directions flow into the fixed point toward the infrared, relevant directions flow away from it, and marginal directions require nonlinear analysis. The critical surface is the set of points that reach the fixed point after the relevant coordinates have been tuned to their critical values.

</figcaption>
</figure>

:::note[The big upgrade]
Renormalization becomes much less mysterious when actions are treated as points and RG as a flow. Counterterms, running couplings, fixed points, universality, and EFT truncations are all different views of this one geometry.
:::

## Prerequisites

You should know [Wilsonian Effective Action](/renormalization-rg-eft/wilsonian-renormalization/wilsonian-effective-action/), [Integrating Out Modes](/renormalization-rg-eft/wilsonian-renormalization/integrating-out-modes/), and [Momentum-Shell RG](/renormalization-rg-eft/wilsonian-renormalization/momentum-shell-rg/). This page also uses the sign conventions from [Conventions and Notation](/renormalization-rg-eft/conventions/).

It helps to have seen [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/), because a change of renormalization scheme is a change of coordinates on theory space.

## Core idea

A Lagrangian written on one line is only a small chart inside a much larger space. If a theory has fields $\phi$ and a symmetry group $G$, the most general local Wilsonian action compatible with those choices is

$$
S_\Lambda[\phi]
=\sum_i g_i(\Lambda)\int d^d x\,\mathcal O_i(x),
$$

where $\mathcal O_i$ runs over all local operators allowed by the symmetries and by the chosen field variables. Even for a humble $\mathbb Z_2$-symmetric scalar field, this includes

$$
1,
\quad
\phi^2,
\quad
(\partial\phi)^2,
\quad
\phi^4,
\quad
\phi^6,
\quad
\phi^2(\partial\phi)^2,
\quad
(\partial^2\phi)^2,
\quad
\ldots
$$

So the natural home of a QFT is not a finite list of textbook couplings. It is an infinite-dimensional space of possible local actions.

The Wilsonian RG defines a map on this space:

$$
R_{d\ell}: S\mapsto S+dS.
$$

In coordinates this becomes a vector field,

$$
\frac{d\tilde g^i}{d\ell}=\mathcal B^i(\tilde g),
$$

where the $\tilde g^i$ are dimensionless couplings. The notation $\mathcal B^i$ is used here to emphasize Wilsonian IR-time flow; it is related to the usual Callan–Symanzik beta functions by a possible sign flip and coordinate change.

The payoff is enormous: fixed points are zeros of this vector field, relevant perturbations are unstable directions, irrelevant perturbations are stable directions, and universality is the statement that many microscopic actions flow into the same long-distance neighborhood.

## Setup and conventions

This page uses Euclidean Wilsonian language. The cutoff is $\Lambda$, and the infrared RG time is

$$
\ell=\log\frac{\Lambda_0}{\Lambda}.
$$

Thus $\ell$ increases as the cutoff is lowered. For dimensionful couplings $g_i(\Lambda)$, define dimensionless coordinates by

$$
\tilde g_i(\Lambda)=\Lambda^{\Delta_i-d}g_i(\Lambda),
$$

where $\Delta_i$ is the scaling dimension of $\mathcal O_i$ at the fixed point being used as the reference. Near the Gaussian fixed point, $\Delta_i$ is the engineering dimension. Near an interacting fixed point, it includes anomalous dimensions.

In these coordinates, the Wilsonian flow is

$$
\frac{d\tilde g^i}{d\ell}=\mathcal B^i(\tilde g).
$$

A fixed point is a point $\tilde g_*^i$ such that

$$
\mathcal B^i(\tilde g_*)=0
\qquad\text{for all }i.
$$

Because the flow parameter points toward the infrared, relevant directions have positive eigenvalues in this chapter's Wilsonian convention. The ultraviolet-oriented convention $\beta^i=\mu\,dg^i/d\mu$ reverses this sign if $\mu$ is identified with a running cutoff.

## What counts as a point?

At first pass, a point in theory space is a Wilsonian action $S_\Lambda$. But this statement needs care.

Two actions may describe the same physics if they differ by a change of field variables, by total derivatives, by equation-of-motion operators inside on-shell observables, or by a choice of redundant normalization. For example, rescaling a scalar field,

$$
\phi\longrightarrow A\phi,
$$

changes the numerical coefficients multiplying $\phi^2$, $\phi^4$, and $(\partial\phi)^2$, but it need not change the physical content if all observables are transformed consistently.

Thus there are two useful levels of language.

| Level | What a point means | Why it is useful |
|---|---|---|
| Coordinate theory space | a local action written in a chosen field basis and regulator | practical calculations and truncations |
| Physical theory space | equivalence classes under redundant descriptions | universal statements and classification |

Most computations begin in coordinate theory space. Most conceptual statements should be phrased so they survive passage to physical theory space.

:::tip[Coordinates are allowed]
Do not become allergic to coordinates. Couplings, cutoffs, field normalizations, and schemes are indispensable for calculation. Just do not confuse the coordinate grid with the invariant geometry.
:::

## Operator bases and coordinates

To coordinatize theory space, choose a basis of local operators:

$$
\{\mathcal O_i\}.
$$

Then write

$$
S=\sum_i g_i\int d^d x\,\mathcal O_i(x).
$$

A different basis gives different coordinates. If

$$
\mathcal O'_a=M_a{}^i\mathcal O_i,
$$

then the couplings transform contragrediently so that the action is unchanged:

$$
g_i=g'_a M_a{}^i.
$$

Equivalently, if one solves for the primed couplings, the inverse matrix appears. More generally, nonlinear field redefinitions and finite renormalizations give nonlinear coordinate transformations

$$
\tilde g^i\longrightarrow \tilde g^{\prime i}(\tilde g).
$$

Under such transformations, the RG flow transforms as a vector field:

$$
\mathcal B^{\prime i}(\tilde g')
=
\frac{\partial \tilde g^{\prime i}}{\partial \tilde g^j}\mathcal B^j(\tilde g).
$$

This is the Wilsonian version of scheme dependence. A beta function is not a scalar function carved into the universe. It is a coordinate representation of a flow.

## Symmetry subspaces

Symmetries carve out subspaces of theory space. If a theory has a $\mathbb Z_2$ symmetry

$$
\phi\longrightarrow -\phi,
$$

then operators odd in $\phi$ are absent. The $\mathbb Z_2$-symmetric actions form a subspace. If the regulator and RG transformation respect the symmetry, the flow stays inside that subspace.

This simple observation is one of the reasons symmetries are so important. They do not merely forbid terms in a Lagrangian once. They define invariant regions of theory space.

Examples:

| Symmetry assumption | Operators excluded or constrained |
|---|---|
| $\mathbb Z_2$ scalar symmetry | odd powers such as $\phi$, $\phi^3$ |
| shift symmetry $\phi\to\phi+c$ | non-derivative potentials |
| chiral symmetry | additive fermion mass terms |
| gauge redundancy | non-gauge-invariant local terms |
| spacetime symmetry | Lorentz-violating or rotation-violating terms |

A symmetry can also be emergent. A microscopic action may start outside a symmetric subspace, but if the symmetry-violating couplings are irrelevant, the long-distance trajectory approaches the symmetric fixed point.

## Fixed points

A fixed point is a scale-invariant action under the full Wilsonian step: integrate modes, then rescale. In coordinates,

$$
\mathcal B^i(\tilde g_*)=0.
$$

The Gaussian fixed point is the free scale-invariant theory. Interacting fixed points include the Wilson–Fisher fixed point in $d=4-\epsilon$, many two-dimensional CFTs, and other conformal or scale-invariant theories.

At a fixed point, correlation functions have scaling behavior. Perturbing away from the fixed point by local operators gives nearby trajectories. The local geometry near $g_*$ therefore controls long-distance universality.

A subtle but important point: a fixed point is defined by the RG transformation, not by the vanishing of all dimensionful parameters in some arbitrary Lagrangian. The correct statement uses dimensionless couplings and includes the rescaling step.

## Linearization near a fixed point

Let

$$
\tilde g^i=\tilde g_*^i+\delta\tilde g^i.
$$

Linearizing the flow gives

$$
\frac{d}{d\ell}\delta\tilde g^i
=M^i{}_j\delta\tilde g^j+O(\delta\tilde g^2),
$$

where

$$
M^i{}_j=\left.\frac{\partial\mathcal B^i}{\partial\tilde g^j}\right|_{\tilde g_*}.
$$

If $v_a^i$ is an eigenvector,

$$
M^i{}_jv_a^j=y_a v_a^i,
$$

then the corresponding perturbation evolves as

$$
\delta\tilde g_a(\ell)=e^{y_a\ell}\delta\tilde g_a(0)
$$

at linear order.

The eigenvalues $y_a$ are RG eigenvalues. In the IR-time convention used here:

| Direction | $y_a$ | IR behavior |
|---|---:|---|
| relevant | $y_a>0$ | grows away from the fixed point |
| irrelevant | $y_a<0$ | decays toward the fixed point |
| marginal | $y_a=0$ | decided by nonlinear terms |

The next page develops this classification in detail.

## Critical surfaces

The **critical surface** of a fixed point is the set of points whose infrared flow approaches that fixed point. Locally, it is spanned by irrelevant directions and, when they remain controlled, marginally irrelevant or exactly marginal directions. Relevant directions point away from it.

If a fixed point has $n$ relevant directions, then reaching it in the infrared usually requires tuning $n$ parameters. This is the Wilsonian meaning of criticality.

For the Ising universality class, the temperature-like perturbation is relevant. To reach the critical point, one tunes the temperature to $T_c$. Other microscopic details, such as lattice spacing and many short-distance couplings, correspond to irrelevant perturbations. They change nonuniversal numbers but not the leading critical exponents.

The geometry is:

$$
\text{many microscopic Hamiltonians}
\longrightarrow
\text{same fixed point neighborhood}
\longrightarrow
\text{same universal scaling data}.
$$

That is universality in one line.

## Theory space is not finite-dimensional

Diagrams often show two or three axes because humans have trouble drawing infinity. The real Wilsonian theory space is infinite-dimensional. Even if a microscopic action starts with only

$$
\frac12(\partial\phi)^2+\frac12 r\phi^2+\frac{u}{4!}\phi^4,
$$

RG steps generate all allowed operators:

$$
\phi^6,
\quad
\phi^8,
\quad
\phi^2(\partial\phi)^2,
\quad
(\partial^2\phi)^2,
\quad
\ldots
$$

A finite-dimensional truncation is an approximation. It can be excellent when irrelevant directions rapidly decay, but it should never be mistaken for the exact space.

This point also explains why renormalizable theories are predictive. Near a fixed point, only finitely many directions may be relevant or marginally relevant. If the infinitely many other directions are irrelevant, their detailed microscopic values fade at long distances.

## Universality as basin structure

A fixed point has a basin of attraction: the region of theory space whose trajectories approach it in the infrared after the necessary relevant parameters are tuned. The basin is not determined by the fixed point alone; it depends on the global flow.

Universality classes are often identified by fixed points together with their relevant data and symmetry assumptions. Two microscopic systems can look wildly different and still share the same universality class if their long-distance flows approach the same fixed point with the same relevant perturbations.

This is why the same field theory can describe a magnet, a liquid-gas critical point, a lattice scalar model, or a continuum scalar QFT near criticality. Their microscopic points in theory space are different, but their long-distance trajectories pass near the same fixed point.

## Redundant directions

Some directions in coordinate theory space are redundant. They change the description rather than the physical theory.

Typical sources include:

| Redundancy | Example | Physical message |
|---|---|---|
| Field redefinitions | $\phi\to\phi+a\phi^3/\Lambda^2$ | shifts higher operators without changing observables |
| Total derivatives | $\partial_\mu J^\mu$ | no effect on bulk correlation functions without boundaries |
| Equation-of-motion operators | $F(\phi)\,\delta S/\delta\phi$ | removable from on-shell amplitudes under suitable assumptions |
| Normalization choices | fixing the kinetic term coefficient | chooses a coordinate convention |

Redundant directions matter because they can pollute naive eigenvalue calculations. The physical scaling operators are obtained after quotienting out redundancies or after choosing a gauge-like convention for the coordinates.

This is also why the phrase "space of all Lagrangians" is slightly too crude. The more careful object is the space of physical theories or the space of local actions modulo redundancies, depending on the question.

## Relation to renormalized perturbation theory

In renormalized perturbation theory, one often works with a finite list of renormalized parameters and writes Callan–Symanzik equations. This is a coordinate chart adapted to a particular calculation.

Wilsonian theory space is broader. It includes every local operator allowed by symmetry, including irrelevant ones. The renormalized perturbative beta function is a projection of the full Wilsonian flow onto a chosen set of coordinates.

The two languages agree when used in their overlapping regime, but they emphasize different things.

| Renormalized perturbation theory | Wilsonian theory space |
|---|---|
| finite set of chosen renormalized parameters | infinite set of local couplings |
| scale $\mu$ labels subtraction convention | cutoff $\Lambda$ labels degrees of freedom retained |
| beta functions describe $\mu$ dependence | RG flow describes coarse graining plus rescaling |
| excellent for precision calculations | excellent for universality and EFT logic |

Neither viewpoint replaces the other. They are two coordinate systems for the theory of scale.

## Common pitfalls

**Thinking theory space is literally the set of textbook Lagrangians.** Textbook Lagrangians are low-dimensional slices through a much larger space.

**Forgetting symmetry subspaces.** If the RG regulator and truncation respect a symmetry, the flow remains in the corresponding subspace. If they do not, apparent symmetry violation may be a regulator artifact.

**Treating couplings as invariant observables.** Couplings are coordinates. Fixed-point exponents, scaling dimensions, ratios of physical quantities, and properly defined observables are the invariant data.

**Calling a finite truncation exact.** Truncations are useful because irrelevant operators often matter less, not because they are absent.

**Ignoring redundant operators.** Not every direction in a coordinate action space changes physics. Some directions correspond to field redefinitions or equations of motion.

**Using one diagram of theory space too literally.** A two-dimensional drawing can show a fixed point and a critical surface, but real theory space is infinite-dimensional and may have complicated global structure.

## Relations to other pages

This page follows [Momentum-Shell RG](/renormalization-rg-eft/wilsonian-renormalization/momentum-shell-rg/) and prepares [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/) and [Universality](/renormalization-rg-eft/wilsonian-renormalization/universality/).

It connects back to [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/), where coordinate changes appear in renormalized perturbation theory. It also connects forward to [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), and [Redundant Operators](/renormalization-rg-eft/local-operators-and-ope/redundant-operators/).

## Research status

Theory-space language is established and indispensable in Wilsonian RG, EFT, critical phenomena, conformal perturbation theory, and functional RG.

Active questions often concern global structure: how to define theory space nonperturbatively, how to quotient by dualities and redundancies, how to treat gauge theory and gravity without misleading coordinates, how to describe spaces of CFTs, and how generalized symmetries, defects, boundaries, and nonlocal operators enlarge the notion of a theory.

In practical calculations, the frontier is rarely the slogan "there is a theory space." The hard part is choosing coordinates and truncations that preserve the physics one cares about.

## Exercises

### Exercise 1: Dimensionless coordinates

Let

$$
S\supset g_i\int d^d x\,\mathcal O_i(x),
$$

where $\mathcal O_i$ has scaling dimension $\Delta_i$. Show that the dimensionless coordinate is

$$
\tilde g_i=\Lambda^{\Delta_i-d}g_i.
$$

<details><summary><strong>Solution</strong></summary>

The action is dimensionless and

$$
[d^d x]=-d,
\qquad
[\mathcal O_i]=\Delta_i.
$$

Therefore

$$
[g_i]+\Delta_i-d=0,
$$

so

$$
[g_i]=d-\Delta_i.
$$

Multiplying by $\Lambda^{\Delta_i-d}$ removes the mass dimension, giving

$$
[\tilde g_i]=0.
$$

</details>

### Exercise 2: Vector-field transformation law

Suppose $d g^i/d\ell=\mathcal B^i(g)$ and define new coordinates $g^{\prime a}=f^a(g)$. Show that

$$
\mathcal B^{\prime a}(g')=\frac{\partial f^a}{\partial g^i}\mathcal B^i(g).
$$

<details><summary><strong>Solution</strong></summary>

Differentiate the coordinate transformation along the flow:

$$
\frac{d g^{\prime a}}{d\ell}
=\frac{\partial f^a}{\partial g^i}\frac{d g^i}{d\ell}.
$$

Using $d g^i/d\ell=\mathcal B^i(g)$ gives

$$
\frac{d g^{\prime a}}{d\ell}
=\frac{\partial f^a}{\partial g^i}\mathcal B^i(g).
$$

By definition the left-hand side is $\mathcal B^{\prime a}(g')$, so the desired transformation law follows.

</details>

### Exercise 3: Linearized flow

Let a fixed point have two nearby coordinates satisfying

$$
\frac{d}{d\ell}
\begin{pmatrix}
\delta g_1\\
\delta g_2
\end{pmatrix}
=
\begin{pmatrix}
2&0\\
0&-1
\end{pmatrix}
\begin{pmatrix}
\delta g_1\\
\delta g_2
\end{pmatrix}.
$$

Identify the relevant and irrelevant directions in IR time.

<details><summary><strong>Solution</strong></summary>

The solutions are

$$
\delta g_1(\ell)=e^{2\ell}\delta g_1(0),
\qquad
\delta g_2(\ell)=e^{-\ell}\delta g_2(0).
$$

Because $\ell$ increases toward the infrared, $\delta g_1$ grows and is relevant. The direction $\delta g_2$ decays and is irrelevant.

</details>

### Exercise 4: Critical surface codimension

Suppose a fixed point has $n$ relevant directions and all other directions are irrelevant. What is the codimension of the critical surface flowing into the fixed point?

<details><summary><strong>Solution</strong></summary>

To approach the fixed point in the infrared, the components along relevant directions must be tuned to zero. Each independent relevant direction gives one condition. Therefore the critical surface has codimension $n$ in theory space.

</details>

### Exercise 5: A redundant operator from a field redefinition

Consider a small field redefinition

$$
\phi\to\phi+\epsilon F(\phi).
$$

Show schematically that the action changes by an equation-of-motion operator at first order in $\epsilon$.

<details><summary><strong>Solution</strong></summary>

Expanding the action gives

$$
S[\phi+\epsilon F]
=S[\phi]+\epsilon\int d^d x\,\frac{\delta S}{\delta\phi(x)}F(\phi(x))+O(\epsilon^2).
$$

Thus the first-order change is proportional to the equations of motion. Such directions can often be removed from physical on-shell quantities by a field redefinition, though care is needed for contact terms, sources, anomalies, and boundaries.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the classic fixed-point and trajectory picture of RG.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for theory space, RG eigenoperators, critical surfaces, and scaling fields.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for RG flows, critical phenomena, and universality from a QFT perspective.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter 23, for Wilsonian RG and the relation to renormalized perturbation theory.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapters 2–3, for Wilson actions, scaling, redundancy, power counting, and EFT logic.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, chapter 6, for theory-space reasoning in condensed matter and critical phenomena.

## Version history

- 2026-06-17: First polished draft. Introduced theory space, coupling coordinates, RG vector fields, fixed points, critical surfaces, symmetry subspaces, universality basins, and redundant directions.
