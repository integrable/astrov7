---
title: "Topological Defects as Symmetries"
description: "Explains the defect-first definition of symmetry, including deformation invariance, crossing rules, defect actions on operators, and the bridge to non-invertible symmetry."
sidebar:
  label: "Topological Defects as Symmetries"
  order: 2
level: Advanced
status: "Polished draft"
source: "Gaiotto–Kapustin–Seiberg–Willett; Shao TASI lectures; Schäfer-Nameki ICTP lectures; standard 2D CFT and defect QFT references."
topics:
  - topological defects
  - symmetry defects
  - non-invertible symmetry
  - defect action
  - Ward identities
  - crossing rules
canonicalTopics:
  - topological-defect-symmetry
  - symmetry-defect
  - defect-crossing-rule
  - non-invertible-ward-identity
researchStatus:
  established:
    - "Ordinary finite and continuous symmetries can be represented by codimension-one topological defects whose deformation and crossing rules reproduce Ward identities and selection rules."
    - "Topological defects provide the natural common language for ordinary, higher-form, and non-invertible symmetries."
  active:
    - "The extension to higher-dimensional non-invertible, fermionic, anomalous, and non-semisimple defect structures is an active research area with conventions that vary across communities."
---

## Summary

A topological defect is a symmetry when it can be inserted, deformed, crossed through operators, and fused in a way that gives exact constraints on the QFT. This is the defect-first viewpoint on symmetry.

For an ordinary group-like symmetry, each group element $g$ gives a codimension-one topological defect $U_g(\Sigma)$. If $\Sigma$ is moved without crossing insertions, nothing changes. If it crosses a local operator $\mathcal O(x)$, it implements the symmetry action:

$$
U_g\text{ crossing }\mathcal O(x)
\quad\leadsto\quad
g\cdot\mathcal O(x).
$$

The same language also covers higher-form symmetries, where charged objects are extended, and non-invertible symmetries, where the defects need not form a group under fusion.

The key idea is:

$$
\text{symmetry} \simeq \text{topological defect data acting on observables}.
$$

<figure class="doc-figure" style="--figure-width: 46rem;">

![A topological codimension-one defect crossing a local operator and changing it into its transformed operator.](/figures/symmetry-anomalies-topology/topological-defect-crossing.svg)

<figcaption>

A symmetry defect is topological: it can be moved freely until it crosses an insertion. The crossing rule is the operator version of the symmetry action. For non-invertible defects, crossing may produce projections, sums over sectors, or defect-local data rather than a single group action.

</figcaption>
</figure>

This page explains what “topological defect as symmetry” means before the fusion rules become more algebraic.

## Prerequisites

You should know [Invertible Versus Non-Invertible Symmetry](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/invertible-versus-non-invertible-symmetry/), [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/), and [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/). The most important prior idea is that a topological defect is an extended operator whose correlation functions are invariant under smooth deformations of its support, as long as no other insertion is crossed and no boundary condition is changed.

This page uses Euclidean language because topological deformation is easiest to draw there. Lorentzian operator statements can usually be recovered by placing the theory on a spatial slice or by radial quantization, but the Euclidean defect picture is the cleanest starting point.

## Core idea

Ordinary symmetry can be introduced in several equivalent ways. One can say it is a unitary operator $U_g$ on Hilbert space. One can say it is an automorphism of the operator algebra. One can say it is a change of variables in the path integral. The defect-first viewpoint packages these into a geometric statement.

For a $d$-dimensional Euclidean QFT, an ordinary internal symmetry element $g$ is represented by a codimension-one defect supported on a closed $(d-1)$-manifold $\Sigma$:

$$
U_g(\Sigma).
$$

Because $U_g(\Sigma)$ is topological, deforming $\Sigma$ away from insertions does not change the correlator:

$$
\frac{d}{dt}
\left\langle
U_g(\Sigma_t)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)
\right\rangle
=0
$$

whenever the family $\Sigma_t$ crosses no insertion.

If $\Sigma$ crosses an operator, it acts on that operator. This is the Ward identity without writing a current. The current form of the Ward identity is what one obtains when the symmetry is continuous and one looks infinitesimally.

For ordinary symmetries, the defects are invertible and obey

$$
U_g\times U_h=U_{gh}.
$$

For non-invertible symmetries, the same topological-defect logic remains, but fusion can take the form

$$
\mathcal D_a\times\mathcal D_b
=
\bigoplus_c N_{ab}{}^c\,\mathcal D_c.
$$

That is why topological defects are the right doorway into categorical symmetry.

## Setup and notation

Let $T$ be a Euclidean QFT in $d$ dimensions. A codimension-one defect $\mathcal D(\Sigma)$ is supported on a closed oriented hypersurface $\Sigma^{d-1}$ unless otherwise stated. “Closed” means no boundary:

$$
\partial\Sigma=0.
$$

The transparent defect is denoted by $1$. It can be inserted without changing the theory:

$$
1(\Sigma)\quad\text{does nothing}.
$$

Fusion is written as $\times$ or by juxtaposition:

$$
\mathcal D_a\times\mathcal D_b.
$$

Orientation reversal or Hermitian adjunction is denoted by $\mathcal D^\dagger$ when the distinction matters. In a unitary Euclidean theory, reflection positivity often relates orientation reversal to adjunction, but this can depend on spacetime, spin, and antiunitary structures.

A defect is **topological** if local changes of its embedding are invisible in correlation functions away from crossings and endpoints. This does not mean the defect is dynamically tensionless as a physical brane. It means the defect defines a deformation-invariant operator.

:::note[Source note]
The generalized-global-symmetry literature uses topological operators as the intrinsic diagnostic of symmetry. For ordinary $q=0$ symmetries the topological operator has codimension one and acts on local operators. For a $q$-form symmetry it has codimension $q+1$ and acts on $q$-dimensional charged operators.
:::

## From Hilbert-space symmetry to defect

In canonical language, an internal symmetry is implemented by $U_g$ on the Hilbert space. If the theory is placed on a spatial slice $M_{d-1}$, then the symmetry operator acts as

$$
U_g(M_{d-1}):\mathcal H(M_{d-1})\to\mathcal H(M_{d-1}).
$$

The Euclidean defect $U_g(\Sigma)$ is the spacetime version of the same object. When $\Sigma$ is a time slice, it acts on states. When $\Sigma$ is deformed into a small sphere surrounding a local operator, it acts on that operator. When $\Sigma$ is moved across a collection of insertions, it produces a Ward identity.

This is why the defect picture is more flexible than the Hilbert-space picture. The same geometric object can be used to discuss states, operators, correlation functions, boundaries, interfaces, and selection rules.

For a finite group symmetry $G$, inserting a closed $U_g$ surface and moving it across all operator insertions gives

$$
\left\langle \mathcal O_1\cdots \mathcal O_n\right\rangle
=
\left\langle (g\cdot\mathcal O_1)\cdots(g\cdot\mathcal O_n)\right\rangle
$$

in a $G$-invariant vacuum. For an Abelian symmetry with charged local operators,

$$
g\cdot\mathcal O_{q}= \chi_q(g)\mathcal O_q,
$$

so a nonzero correlator requires

$$
\prod_{i=1}^n\chi_{q_i}(g)=1
\qquad\text{for all }g.
$$

This is the finite-defect version of charge conservation.

## Crossing rules

The central local datum of a symmetry defect is the crossing rule. Suppose $\mathcal D$ is a codimension-one defect and $\mathcal O_A(x)$ is a local operator. If $\mathcal D$ crosses $x$, the insertion is replaced by whatever the defect action prescribes:

$$
\mathcal O_A(x)
\quad\mapsto\quad
\mathcal D\cdot\mathcal O_A(x).
$$

For a group-like symmetry this is a linear action on local operators:

$$
U_g\cdot\mathcal O_A
=
R(g)_A{}^B\mathcal O_B.
$$

For a non-invertible defect the crossing can be subtler. It may map an operator to a sum of operators, project onto an invariant subsector, attach a defect-local endpoint, or require specifying junction data. The simple matrix-action picture can be too small.

A useful way to say this is:

$$
\text{ordinary symmetry acts on operators;}
\qquad
\text{non-invertible symmetry acts on the operator algebra plus sectors}.
$$

This is not a slogan to memorize; it is a warning. In non-invertible symmetry, one should not expect a faithful description purely as a transformation of elementary fields.

## Topological deformation is the Ward identity

For continuous ordinary symmetries, Ward identities are often written using a conserved current:

$$
\partial_\mu j^\mu=0
$$

away from charged insertions. The topological-defect picture is the integrated version.

If $\Sigma$ is a symmetry surface, deforming it past insertions changes the correlator only by the prescribed crossing action. This is exactly what a Ward identity does: it says that the effect of a symmetry transformation can be moved around until it reaches the charged operators.

In the continuous case, a small symmetry parameter gives

$$
U(\alpha,\Sigma)=
\exp\!\left(-i\alpha\int_\Sigma {*j}\right),
$$

at least when the current and charge are well-defined. Differentiating with respect to $\alpha$ gives the current Ward identity with contact terms.

For finite or non-invertible symmetries there may be no current. The defect deformation statement remains meaningful. This is one of the main reasons the topological-defect viewpoint is more general than Noether-current language.

:::note[Source note]
When a finite symmetry has no Noether current, the topological defect still supplies a Ward identity: moving the defect through a correlator relates the correlator to one with transformed insertions. This is the right template for non-invertible Ward identities.
:::

## Symmetry defects versus arbitrary defects

Not every topological defect should automatically be called a symmetry. A defect becomes symmetry data when it is part of a stable, closed set of topological operations acting on observables.

A useful checklist is:

| Question | Why it matters |
|---|---|
| Is the defect topological? | Otherwise deformation does not give exact constraints. |
| Does it have a controlled crossing rule? | Otherwise it does not act on observables. |
| Does it fuse with other symmetry defects? | Otherwise there is no symmetry algebra. |
| Is there an identity defect? | Otherwise there is no unit operation. |
| Are junctions and endpoints specified? | Otherwise associativity and actions are incomplete. |
| Is the structure stable under allowed deformations? | Otherwise it is not robust symmetry data. |

A boundary condition can be topological without being a symmetry of the bulk. An interface between two different theories can be topological without being a symmetry of either single theory. A defect is a symmetry defect of a theory when it is a topological endomorphism of that theory, meaning it maps the theory back to itself and can be inserted as an operator in correlators of that theory.

## Interfaces, folding, and endomorphism

A defect between two QFTs $T_1$ and $T_2$ is often called an interface:

$$
\mathcal I:T_1\to T_2.
$$

If $T_1=T_2=T$, it is a defect of $T$:

$$
\mathcal D:T\to T.
$$

Only the second case is directly a symmetry candidate of a single QFT.

There is a useful folding trick. An interface between $T_1$ and $T_2$ can be viewed as a boundary condition for the product theory

$$
T_1\otimes \overline{T_2},
$$

where $\overline{T_2}$ denotes the orientation-reversed theory. This trick is common in two-dimensional CFT and in defect QFT more generally. It reminds us that “defect,” “boundary,” and “interface” are closely related notions, but not identical.

A duality between two different theories is an invertible interface if it has an inverse interface. A duality defect becomes a symmetry defect only at a self-dual point, where the interface begins and ends on the same QFT.

## Fusion enters automatically

Once defects can be inserted, they can be placed near each other. If two parallel codimension-one topological defects $\mathcal D_a$ and $\mathcal D_b$ are brought together, the resulting composite is again topological:

$$
\mathcal D_a\times\mathcal D_b.
$$

For group-like symmetry defects,

$$
U_g\times U_h=U_{gh}.
$$

For non-invertible defects,

$$
\mathcal D_a\times\mathcal D_b
=
\bigoplus_c N_{ab}{}^c\mathcal D_c.
$$

The next page studies this equation in detail. Here the main point is conceptual: fusion is not extra decoration. It is forced by the ability to insert more than one topological defect.

Fusion is the operation that turns “a list of defects” into symmetry structure.

## Defect-local operators and junctions

Defects have their own local operators. A defect-local operator is inserted on the defect worldvolume rather than in the ambient bulk. If $\mathcal D(\Sigma)$ is a defect and $y\in\Sigma$, a defect-local operator may be denoted

$$
\widehat{\mathcal O}(y)\in \mathcal D.
$$

Junctions are places where defects meet. For codimension-one defects, a junction is supported in codimension two. Junctions are essential because fusion and associativity are not only equations between labels; they are implemented by local junction operators.

For group-like symmetries, one often suppresses these details because the junctions are canonical. For non-invertible symmetries, defect-local operators and junction spaces are part of the symmetry data. Ignoring them is like trying to do representation theory while ignoring vector spaces.

A simplified fusion rule such as

$$
\mathcal N^2=1+\eta
$$

is the visible shadow of a richer defect algebra containing junctions and associators.

## Examples

### Ordinary $\mathbb Z_2$ symmetry

Let $\eta$ be the topological defect for a $\mathbb Z_2$ spin-flip symmetry. It obeys

$$
\eta\times\eta=1.
$$

If $\mathcal O_+$ is even and $\mathcal O_-$ is odd, crossing gives

$$
\eta\cdot\mathcal O_+=\mathcal O_+,
\qquad
\eta\cdot\mathcal O_-=-\mathcal O_-.
$$

Moving a closed $\eta$ defect around a correlator gives the usual parity selection rule: an odd number of odd operators has zero expectation value in a symmetric vacuum.

### Kramers–Wannier-type duality defect

At the self-dual point of the two-dimensional Ising model, there is a duality defect $\mathcal N$ with schematic fusion

$$
\mathcal N\times\mathcal N=1+\eta,
$$

where $\eta$ is the spin-flip defect. The defect $\mathcal N$ is topological but not invertible. Its crossing rules exchange order and disorder data rather than acting as an ordinary spin-flip group element.

This example is pedagogically important because it shows that non-invertible symmetry is not vague. It can be encoded in explicit topological defects with definite fusion rules.

### Gauging defect

Many non-invertible defects can be built by gauging a finite symmetry on half of spacetime. The defect separating the gauged and ungauged regions can be topological at special points or under suitable conditions. When folded back into a defect of a single theory, this construction often produces non-invertible fusion.

The intuition is that gauging forgets some information. Forgetting is not invertible, and the associated defect fusion remembers this as a sum over sectors.

## What topological defects constrain

Topological symmetry defects can constrain:

- which local operators can appear in the action;
- which correlators vanish;
- how defect endpoints and disorder operators transform;
- which boundary conditions are compatible with a symmetry;
- which deformations preserve or break the symmetry;
- which phases or RG flows are allowed;
- which anomalies must be matched.

For ordinary symmetries these constraints are often expressible as charge conservation. For non-invertible symmetries, the constraints can be more projection-like. They may say that certain sectors must appear together, certain deformations are forbidden, or certain boundary conditions cannot exist without extra topological degrees of freedom.

## Common pitfalls

**“Topological” means “zero energy.”** No. Topological means deformation-invariant as an operator. It is not a statement about a dynamical brane’s tension.

**“A symmetry defect must act on elementary fields.”** No. It must act on physical observables and sectors. Elementary fields may be absent or gauge-variant.

**“If a defect is topological, it is automatically a symmetry.”** No. It must be part of a closed action/fusion structure on the QFT. A single topological interface between different theories is not automatically a symmetry of either one.

**“Crossing rules are always ordinary transformations.”** For non-invertible defects, crossing can involve sums, projections, endpoints, or junction data.

**“Fusion rules are all the data.”** Fusion rules are only the first layer. Associators, junction spaces, braiding, orientation, and anomaly data can matter.

## Relations to other pages

[Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/) explains fusion as a general operation for defects. [Invertible Versus Non-Invertible Symmetry](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/invertible-versus-non-invertible-symmetry/) explains why the group case is only the invertible special case. [Fusion Rules](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/fusion-rules/) develops the algebraic notation used here.

The higher-form chapter explains how topological symmetry operators of codimension $q+1$ act on $q$-dimensional charged operators. The symmetry-TFT chapter will package topological defects, boundary conditions, and gauging operations in one higher dimension.

## Research status

The defect-first formulation of ordinary and higher-form symmetries is standard. The two-dimensional non-invertible story is also well established in many examples, especially in rational CFT, lattice models, and orbifold constructions.

The higher-dimensional story is active. Defects may form higher categories rather than ordinary fusion categories. Fermionic theories require spin-sensitive refinements. Anomalies and symmetry TFTs provide a powerful organizing framework, but conventions and levels of mathematical precision vary across the literature.

## Exercises

### Exercise 1: Ordinary selection rule from a defect

Let $\eta$ be a $\mathbb Z_2$ symmetry defect, and let $\mathcal O_i$ be operators with parities $p_i=\pm1$. Use a closed $\eta$ defect surrounding all insertions to derive the condition for

$$
\left\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\right\rangle
$$

to be nonzero in a $\mathbb Z_2$-invariant vacuum.

<details><summary><strong>Solution</strong></summary>

Insert a closed $\eta$ defect around all operators. Since the vacuum is invariant and the defect is topological, the enclosing defect can be removed. Now shrink it through the insertions. Each crossing multiplies $\mathcal O_i$ by $p_i$. Therefore the correlator equals

$$
\left(\prod_i p_i\right)
\left\langle \mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\right\rangle.
$$

A nonzero correlator requires

$$
\prod_i p_i=1.
$$

Thus an odd number of odd insertions gives zero.

</details>

### Exercise 2: Why the duality defect is not invertible

Suppose a topological defect $\mathcal N$ obeys

$$
\mathcal N\times\mathcal N=1+\eta,
\qquad
\eta\times\eta=1.
$$

Assuming direct sums are nontrivial, explain why $\mathcal N$ cannot have an inverse under fusion.

<details><summary><strong>Solution</strong></summary>

If $\mathcal N$ had an inverse $\mathcal N^{-1}$, then fusing the equation on the right by $\mathcal N^{-1}$ would give

$$
\mathcal N=(1+\eta)\times\mathcal N^{-1}
=
\mathcal N^{-1}+(\eta\times\mathcal N^{-1}).
$$

The right-hand side is a direct sum of two nonzero channels in the usual semisimple setting, not a single simple defect. Equivalently, using quantum dimensions gives

$$
d_{\mathcal N}^2=d_1+d_\eta=2,
$$

so $d_{\mathcal N}=\sqrt2$, while invertible simple defects have $d=1$. Thus $\mathcal N$ is not invertible.

</details>

### Exercise 3: Interface or symmetry defect?

Classify the following as a defect of one theory or an interface between two theories.

1. A domain wall between a theory $T$ and its gauged version $T/G$.
2. A topological line implementing a $\mathbb Z_2$ symmetry inside a single Ising CFT.
3. A duality wall between two different descriptions that are not at the same point in theory space.
4. A self-duality defect at a self-dual point.

<details><summary><strong>Solution</strong></summary>

1. This is naturally an interface $T\to T/G$.
2. This is a defect of one theory and can represent an ordinary symmetry.
3. This is an interface between theories or descriptions. It is not automatically a symmetry defect of one QFT.
4. At a self-dual point the interface begins and ends on the same theory, so it can be treated as a defect of one QFT. It may be invertible or non-invertible depending on its fusion rule.

</details>

### Exercise 4: Current Ward identity versus defect Ward identity

Why does the topological-defect Ward identity still make sense for a finite symmetry with no Noether current?

<details><summary><strong>Solution</strong></summary>

A Noether current requires an infinitesimal continuous parameter. A finite symmetry has no such infinitesimal generator and therefore no ordinary Noether current. But it can still have topological symmetry defects labeled by group elements. Moving such a defect through a correlator gives a finite relation among correlators. This deformation/crossing statement is a Ward identity in integrated topological form, even though no current divergence equation exists.

</details>

## References

- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the topological-operator definition of generalized symmetry.
- S.-H. Shao, “What’s Done Cannot Be Undone: TASI Lectures on Non-Invertible Symmetries,” for a modern physics-first introduction centered on duality defects.
- S. Schäfer-Nameki, “ICTP Lectures on (Non-)Invertible Generalized Symmetries,” for a broad review of topological defects, symmetry TFT, and higher-dimensional examples.
- J. Fuchs, I. Runkel, and C. Schweigert, work on topological defects and rational CFT, for a mathematically controlled two-dimensional setting.
- A. Kapustin and N. Saulina, and related work on surface operators and defect categories, for bridges to TQFT and higher categories.

## Version history

- **2026-06-20:** Initial polished draft. Added defect-first definition of symmetry, crossing rules, interface distinctions, Ward-identity interpretation, non-invertible caveats, examples, and exercises.
