---
title: "Domain Walls as Defects"
description: "Domain walls viewed as codimension-one defects: dynamical solitons, inserted interfaces, symmetry walls, topological walls, displacement operators, and anomaly inflow."
sidebar:
  label: "Domain Walls as Defects"
  order: 7
level: Advanced
status: "Polished draft"
source: "Coleman, Aspects of Symmetry, Ch. 5; Srednicki §§30–32, 82, 92–93; Polyakov Chs. 1, 5–7; Gaiotto–Kapustin–Seiberg–Willett; standard defect-QFT literature."
topics:
  - domain walls
  - codimension-one defects
  - topological defects
  - symmetry walls
  - displacement operators
  - anomaly inflow
canonicalTopics:
  - defects-extended-operators
  - spontaneous-symmetry-breaking
  - topological-sectors
  - generalized-symmetry
researchStatus:
  established:
    - "Domain walls can be treated either as dynamical solitons or as prescribed codimension-one defect operators, depending on the question."
    - "Topological symmetry walls implement symmetry actions on operators and fuse according to the symmetry law when the symmetry is non-anomalous."
  active:
    - "The categorical organization of general topological, duality, and non-invertible domain walls is a modern research language developed further in later chapters."
---

## Summary

A **domain wall** is a codimension-one object. In $d$ spacetime dimensions its worldvolume is a $(d-1)$-dimensional hypersurface $\Sigma$. The phrase has two closely related meanings.

First, a domain wall can be a **dynamical soliton**: a field configuration interpolating between distinct vacua or phases. This is the wall in a broken discrete symmetry, a kink in $1+1$ dimensions, or a membrane separating regions of different order parameter in higher dimensions.

Second, a domain wall can be an **inserted defect**: a prescribed codimension-one rule in the path integral or operator formalism. It may separate two QFTs, impose a symmetry transformation, carry lower-dimensional degrees of freedom, or encode a topological interface. This is the viewpoint used throughout the defects chapter.

The same picture can therefore be read in two directions:

$$
\text{dynamical wall} \quad \leadsto \quad \text{state or sector of one QFT},
$$

while

$$
\text{inserted wall} \quad \leadsto \quad \text{operator, interface, or gluing datum}.
$$

That distinction is the whole page. A tremendous amount of confusion evaporates once you ask: **is the wall being summed over as part of the dynamics, or inserted as external defect data?**

<figure class="doc-figure" style="--figure-width: 62rem;">

![Three complementary readings of a codimension-one wall: a finite-tension wall between vacua, a topological symmetry wall acting on crossing operators, and a fusion or junction algebra of walls.](/figures/symmetry-anomalies-topology/domain-wall-defect-dictionary.svg)

<figcaption>

A codimension-one wall may be a finite-tension soliton, a topological symmetry wall, or an interface with fusion and junction data. The defect viewpoint keeps these cases in one language while preserving the crucial distinction between tensionful and topological walls.

</figcaption>
</figure>

## Prerequisites

You should know the earlier pages on local and extended operators, Wilson lines, ’t Hooft lines, surface operators, disorder operators, and twist operators. The pages on degenerate vacua, domain walls, anomaly inflow, and topological charge conservation provide the complementary soliton-side viewpoint.

We use the volume convention that spacetime is Lorentzian unless stated otherwise, with mostly-minus metric. A wall worldvolume is denoted $\Sigma$. Near a smooth wall we often use local coordinates

$$
x^\mu=(y,x^a),\qquad a=0,1,\ldots,d-2,
$$

where $y$ is the normal coordinate and $x^a$ are coordinates along $\Sigma$.

## Two lives of the same object

The word **wall** is deliberately physical. It suggests a real extended thing in spacetime. But in QFT there are two different operations that can produce such a thing.

A **dynamical wall** appears as a configuration of the fields. For a scalar theory with two vacua, a static wall may satisfy

$$
\phi(y\to -\infty)=v_-,\qquad \phi(y\to +\infty)=v_+.
$$

The wall position is a collective coordinate. The wall tension contributes to the energy. Quantum fluctuations of the wall are part of the Hilbert space.

An **inserted wall** is instead part of the definition of an observable. We specify a hypersurface $\Sigma$ and define a defect operator $D_\Sigma$ by modifying the path integral near $\Sigma$:

$$
\langle \mathcal O_1\cdots \mathcal O_n D_\Sigma\rangle
=
\int_{\mathcal B_\Sigma}\mathcal D\Phi\,
\exp\!
\left(iS_{\text{bulk}}[\Phi]+iS_\Sigma[\Phi|_\Sigma,\chi]\right)
\mathcal O_1\cdots \mathcal O_n.
$$

Here $\mathcal B_\Sigma$ denotes the allowed boundary, gluing, monodromy, or singularity condition along the wall, and $\chi$ denotes possible defect-local fields.

These two notions are related but not interchangeable. A semiclassical soliton can often be used to build a defect effective theory on its worldvolume. Conversely, an inserted defect can sometimes be made dynamical by summing over its position and internal fields. But those are additional operations, not automatic identifications.

:::note[Terminology]
In this chapter, **domain wall** usually means a codimension-one defect, while **dynamical domain wall** means a soliton separating vacua. Later pages on non-invertible and categorical symmetries often say **wall** or **defect** for the inserted version.
:::

## Local data on a wall

An inserted wall between two theories $\mathcal T_-$ and $\mathcal T_+$ can be described schematically by an action

$$
S=S_-\big[\Phi_-\big]+S_+\big[\Phi_+\big]
+\int_\Sigma d^{d-1}x\,\mathcal L_\Sigma
\big(\Phi_-|_\Sigma,\Phi_+|_\Sigma,\chi\big).
$$

The wall Lagrangian $\mathcal L_\Sigma$ may be trivial, but the gluing condition may still be nontrivial. For example, a free scalar interface might impose continuity of the field and a jump condition on the normal derivative. A gauge-theory wall might impose a relation between gauge fields on the two sides and include lower-dimensional charged matter.

The variational principle makes the wall data concrete. For a scalar field on the two sides, variation of the bulk action produces boundary terms

$$
\delta S_{\text{bulk}}\supset
\int_\Sigma d^{d-1}x\,
\left(
\Pi^y_+\delta\phi_+ - \Pi^y_-\delta\phi_-
\right),
$$

where $\Pi^y=\partial\mathcal L/\partial(\partial_y\phi)$ is the normal canonical momentum density. The defect action contributes its own variation. A consistent wall requires the sum of these terms to vanish under the allowed variations.

For a simple interface with $\phi_+|_\Sigma=\phi_-|_\Sigma=\varphi$ and defect potential $U(\varphi)$, one gets a schematic jump condition

$$
\Pi^y_+ - \Pi^y_- + \frac{\partial U}{\partial\varphi}=0.
$$

The precise signs depend on whether both normals are chosen outward or whether one uses a single normal pointing from $-$ to $+$. The formula above uses the latter convention.

:::caution[Source note]
Boundary and interface signs are notoriously convention-sensitive because the normal vector orientation, Lorentzian versus Euclidean continuation, and integration-by-parts convention all matter. In this volume, the normal $n$ usually points from the $-$ side to the $+$ side. If a reference uses outward normals on both sides, one of the normal-momentum signs flips.
:::

## The displacement operator

A generic defect breaks translations in the directions normal to its support. The operator that measures this breaking is the **displacement operator**. For a codimension-one wall at $y=0$, the Ward identity has the schematic form

$$
\partial_\mu T^{\mu y}(x)=\delta(y)\,\mathcal D(x^a),
$$

where $\mathcal D$ is a local operator living on the wall.

This equation says something beautifully simple. The wall can absorb normal momentum. The amount absorbed is the displacement operator.

For tangential translations, assuming the wall preserves translation along $\Sigma$, one instead has conservation of the combined bulk-plus-defect momentum along the wall. In local coordinates this looks schematically like

$$
\partial_\mu T^{\mu a}_{\text{bulk}}+
\delta(y)\,\partial_b T_\Sigma^{ba}=0,
$$

possibly with additional terms if background fields or explicit position dependence are present.

A defect is **topological** when its position can be deformed without changing correlators, as long as it does not cross insertions. In this language, the topological condition is

$$
\mathcal D=0
$$

inside correlation functions, away from contact terms with other defects or endpoints.

This is the codimension-one version of a general defect principle: local deformations of a defect are generated by its displacement operator. Topological defects have no local displacement response.

## Symmetry walls

The cleanest examples of topological domain walls are **symmetry walls**.

Let $G$ be an ordinary global symmetry. For $g\in G$, the wall $D_g(\Sigma)$ acts by applying $g$ to operators that cross it. If $\mathcal O_R$ transforms in representation $R$, then moving the wall past $\mathcal O_R(x)$ gives

$$
D_g(\Sigma)\,\mathcal O_R(x)
\quad \longrightarrow \quad
R(g)\mathcal O_R(x)\,D_g(\Sigma).
$$

For an abelian charge-$q$ operator and $g=e^{i\alpha}$,

$$
D_\alpha(\Sigma)\,\mathcal O_q(x)
\quad \longrightarrow \quad
e^{iq\alpha}\mathcal O_q(x)D_\alpha(\Sigma).
$$

The wall is topological because only which operators it encloses matters, not the detailed shape of $\Sigma$.

For a continuous non-anomalous symmetry with current $j^\mu_a$, a small symmetry wall can be written formally as

$$
D_{\alpha}(\Sigma)
=\exp\left(i\alpha^a\int_\Sigma d\Sigma_\mu\,j_a^\mu\right),
$$

where $\Sigma$ is a codimension-one surface. Conservation of $j^\mu_a$ implies surface deformation invariance, up to contact terms when $\Sigma$ crosses charged operators.

For a finite symmetry, there need not be a Noether current, but the topological wall still exists. This is a crucial moral: **topological symmetry defects are more fundamental than currents**. Currents are the continuous-symmetry specialization.

The fusion law is

$$
D_g\times D_h=D_{gh},
$$

and the orientation-reversed wall is

$$
D_g^{\vee}=D_{g^{-1}}.
$$

These equations are the ordinary invertible case. Non-invertible walls generalize this by replacing group multiplication with a fusion algebra.

## Dynamical walls from broken discrete symmetry

Now compare symmetry walls with solitonic walls.

Consider a real scalar with potential

$$
V(\phi)=\frac{\lambda}{4}\left(\phi^2-v^2\right)^2.
$$

The two classical vacua $\phi=\pm v$ are exchanged by a $\mathbb Z_2$ symmetry. In $1+1$ dimensions, the static kink is a particle. In $3+1$ dimensions, the same profile extended in two spatial directions is a domain wall.

For a static wall profile $\phi(y)$, the tension is

$$
T_{\text{wall}}
=\int_{-\infty}^{+\infty}dy\,
\left[
\frac12\left(\frac{d\phi}{dy}\right)^2+V(\phi)-V(v)
\right].
$$

The wall is stable because the boundary conditions at $y=\pm\infty$ cannot be continuously deformed into one another while staying in finite-energy configurations. The charge is often described by the element of

$$
\pi_0(\mathcal M_{\text{vac}}),
$$

where $\mathcal M_{\text{vac}}$ is the vacuum manifold.

This wall is not automatically a topological defect operator. It has tension. Moving it changes the field configuration, and bending it costs energy. It can have fluctuations, zero modes, localized excitations, and interactions with other walls. At long distances, one often writes an effective worldvolume theory for these degrees of freedom.

The relation to the inserted-defect viewpoint is semiclassical: one can condition the path integral to include a wall separating the two asymptotic vacua. But if the wall is dynamical, one must also integrate over its collective coordinates and fluctuations.

## Topological versus tensionful walls

There are three common cases.

A **symmetry wall** is topological. It implements an exact global symmetry and can be freely deformed until it crosses charged operators or other defects.

A **dynamical soliton wall** is usually tensionful. It is an excitation of the theory, not merely an operator that changes correlation functions by crossing rules.

A **topological interface** may separate two different-looking theories that are nevertheless equivalent after crossing the wall. Such a wall is not necessarily associated with an ordinary group symmetry. In two-dimensional CFT, for example, duality walls can implement Kramers–Wannier-type dualities. In modern language, these are often non-invertible or categorical defects.

The stress-tensor test is efficient. If the wall is topological, the stress tensor can pass through it without producing a displacement insertion. If the wall reflects, absorbs, or dissipates energy, it is not topological in that sense.

One should not confuse **topological charge** with **topological defect**. A solitonic wall can be topologically stable but not a topological operator. The former means it cannot decay within a sector; the latter means its position is unphysical in correlators.

Tiny phrase, huge difference.

## Walls between theories

A codimension-one defect can separate two distinct QFTs $\mathcal T_A$ and $\mathcal T_B$. Such an object is often called an **interface**. The local data at the wall specify how fields, states, and operators on the two sides talk to each other.

In Hamiltonian language, an interface creates a Hilbert space on a spatial slice divided by a codimension-one locus. In Euclidean language, it is an operator inserted on a hypersurface. In categorical language, an interface is sometimes treated as a morphism between theories.

Special cases are useful:

$$
\begin{array}{ccl}
\text{wall within one theory} &:& \mathcal T_A=\mathcal T_B,\\
\text{boundary} &:& \mathcal T_B=\mathbf 1,\\
\text{duality wall} &:& \mathcal T_A\simeq\mathcal T_B \text{ by crossing},\\
\text{RG interface} &:& \mathcal T_A \text{ flows to } \mathcal T_B.
\end{array}
$$

Here $\mathbf 1$ denotes the trivial theory.

This interface viewpoint is the natural bridge to the next page on boundaries and interfaces.

## Symmetry walls and gauging

Symmetry walls make gauging geometrically vivid. To gauge a finite symmetry $G$, one sums over networks of $G$-walls, modulo local moves that express fusion and topological invariance. In lattice language these networks are discrete gauge fields. In continuum language they are background flat $G$-bundles.

For ordinary invertible symmetries, a consistent network requires associativity of fusion. If there is an ’t Hooft anomaly, the local moves fail by phases. This failure is the defect-network version of the obstruction to gauging.

For a continuous symmetry, the background-field viewpoint says the same thing differently: if the effective action cannot be made invariant under background gauge transformations, the corresponding symmetry-wall network cannot be consistently summed.

This is why domain walls sit at the crossroads of symmetry and topology. They are where abstract global transformations become visible extended objects.

## Anomaly inflow onto walls

A wall can support anomaly inflow. Suppose a parameter such as a theta angle jumps across a hypersurface:

$$
\theta(y)=\theta_-+\Delta\theta\,\Theta(y).
$$

In four dimensions, the topological term

$$
S_\theta=\frac{1}{8\pi^2}\int \theta\,\operatorname{tr}(F\wedge F)
$$

can be integrated by parts locally using

$$
\operatorname{tr}(F\wedge F)=d\omega_3(A),
$$

so the jump produces an effective wall term

$$
S_\Sigma\sim \frac{\Delta\theta}{8\pi^2}\int_\Sigma \omega_3(A),
$$

up to convention-dependent trace normalization and boundary terms. This is a Chern–Simons-like response localized on the wall.

:::caution[Source note]
The coefficient of the wall Chern–Simons term depends on the normalization of $\operatorname{tr}(T^aT^b)$ and on the convention for $F=dA-iA\wedge A$ versus $F=dA+A\wedge A$. This volume uses Hermitian gauge generators and $D=d-iA$ unless a page says otherwise.
:::

More generally, a bulk anomaly or topological response can terminate on a wall only if the wall carries precisely the degrees of freedom or topological theory needed to make the combined system consistent. This is the wall version of anomaly inflow.

## Endpoints and junctions

A codimension-one wall can end only if the endpoint carries additional data. If a symmetry wall ends on a codimension-two locus, that endpoint is a twist defect. If a topological interface ends, the endpoint must absorb the failure of the crossing rule.

Similarly, several walls can meet at junctions. For symmetry walls, a trivalent junction expresses group multiplication:

$$
D_g\times D_h\to D_{gh}.
$$

For non-invertible walls, junctions encode fusion spaces rather than a single multiplication map. Later pages develop this into defect fusion and line-operator algebras.

The moral is local: **defects can have defects on them**. A wall can carry line defects, local wall operators, junction operators, and boundary conditions for fields living on the wall.

## Common pitfalls

### “Topologically stable” does not mean “topological operator”

A kink is topologically stable because its boundary conditions cannot be unwound at finite energy. A symmetry wall is topological because its shape can be deformed in correlation functions. These are different statements.

### A wall is not always a boundary

A boundary is an interface with the trivial theory. A wall inside spacetime generally has two sides, and both sides may carry nontrivial QFTs.

### A finite symmetry has no current, but it still has walls

Noether currents are not required for symmetry defects. Finite symmetries are often best understood through their topological walls from the start.

### A gauge transformation wall is not automatically physical

Gauge redundancy is not a global symmetry. A wall implementing a gauge transformation is usually invisible unless the transformation has nontrivial boundary behavior, global topology, or acts on charged line operators in a way that survives the quotient.

### A duality wall need not be invertible

Kramers–Wannier-type duality walls often do not have an inverse wall. Their fusion can produce a sum of defects rather than the identity.

## Relation to nearby pages

The page on **Domain Walls** in the topological-sectors chapter studies solitonic walls as configurations interpolating between vacua. This page studies the same codimension-one geometry as defect data.

The page on **Twist Operators** describes codimension-two endpoints of symmetry walls. The page on **Boundaries and Interfaces** develops the general codimension-one gluing problem. The page on **Defect Fusion** explains how topological walls compose. Higher-form and non-invertible symmetry chapters later treat domain walls as the basic carriers of generalized symmetry structure.

## Research status

The solitonic theory of domain walls is standard and established. The defect-operator viewpoint is also standard in CFT, TQFT, lattice models, and modern generalized-symmetry language.

The active frontier is the classification and use of topological, duality, and non-invertible walls in general QFTs. In that setting, the simple group law $D_gD_h=D_{gh}$ becomes only the first example of a much richer fusion structure.

## Exercises

### Exercise 1: Kink tension by completing the square

For

$$
V(\phi)=\frac{\lambda}{4}(\phi^2-v^2)^2,
$$

show that the static kink tension can be written as a sum of a positive square and a boundary term. Find the first-order equation solved by a minimum-tension kink.

<details><summary><strong>Solution</strong></summary>

Write

$$
V(\phi)=\frac12\left(W'(\phi)\right)^2,
$$

with

$$
W'(\phi)=\sqrt{\frac{\lambda}{2}}(v^2-\phi^2).
$$

Then

$$
T=\int dy\left[\frac12(\partial_y\phi)^2+\frac12(W')^2\right]
=\int dy\left[\frac12(\partial_y\phi-W')^2+\partial_y\phi\,W'\right].
$$

The second term is

$$
\int dy\,\partial_y W(\phi)=W(\phi(+\infty))-W(\phi(-\infty)).
$$

The minimum satisfies

$$
\partial_y\phi=W'(\phi)=\sqrt{\frac{\lambda}{2}}(v^2-\phi^2),
$$

or the sign-reversed equation for the anti-kink. This gives the usual tanh profile.

</details>

### Exercise 2: Symmetry wall crossing

Let $G=U(1)$ and let $\mathcal O_q$ have charge $q$. A symmetry wall $D_\alpha$ for $e^{i\alpha}\in U(1)$ is moved past $\mathcal O_q$. What factor appears? What happens for a product $\mathcal O_{q_1}\cdots \mathcal O_{q_n}$ enclosed by a closed wall?

<details><summary><strong>Solution</strong></summary>

Crossing the wall gives

$$
\mathcal O_q\mapsto e^{iq\alpha}\mathcal O_q.
$$

For a product of enclosed operators, the factor is

$$
\exp\left(i\alpha\sum_{r=1}^n q_r\right).
$$

If the wall is contractible and no anomaly or boundary is present, the correlator must be unchanged after shrinking the wall. Therefore a nonzero correlator requires

$$
\sum_{r=1}^n q_r=0
$$

for continuous $U(1)$ symmetry. For finite cyclic symmetry, the sum is understood modulo the group order.

</details>

### Exercise 3: Displacement and topological invariance

Assume a codimension-one defect at $y=0$ obeys

$$
\partial_\mu T^{\mu y}=\delta(y)\mathcal D.
$$

Explain why $\mathcal D=0$ is the infinitesimal condition for the defect to be deformable in the normal direction.

<details><summary><strong>Solution</strong></summary>

A small normal deformation of the defect changes the correlator by inserting the operator conjugate to normal displacement. The Ward identity identifies that operator as $\mathcal D$. Thus the first-order variation is schematically

$$
\delta\langle D_\Sigma\cdots\rangle
= i\int_\Sigma d^{d-1}x\,\epsilon(x)\langle \mathcal D(x)D_\Sigma\cdots\rangle,
$$

up to Euclidean/Lorentzian factors. If $\mathcal D=0$ in correlators away from contact terms, local deformations do not change the correlator. Contact terms appear when the deformed wall crosses operators, endpoints, or other defects.

</details>

### Exercise 4: Boundary as a special wall

Explain why a boundary condition for a QFT $\mathcal T$ can be viewed as an interface between $\mathcal T$ and the trivial theory $\mathbf 1$.

<details><summary><strong>Solution</strong></summary>

An interface specifies how degrees of freedom on two sides of a hypersurface are glued. If the right side has no bulk degrees of freedom, the only remaining data are conditions on the fields of $\mathcal T$ and possible degrees of freedom living on the hypersurface itself. That is precisely a boundary condition. Symbolically,

$$
\text{boundary of }\mathcal T
=\text{interface }\mathcal T|\mathbf 1.
$$

This viewpoint is useful because many operations on walls, such as fusion and anomaly inflow, also apply to boundaries.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially the lectures on secret symmetry and solitons.
- M. Srednicki, *Quantum Field Theory*, §§30, 32, 92–94, for spontaneous symmetry breaking, solitons, monopoles, instantons, and theta vacua.
- A. M. Polyakov, *Gauge Fields and Strings*, Chs. 4–7, for instantons, compact gauge theory, Wilson loops, and gauge-field topology.
- M. Nakahara, *Geometry, Topology and Physics*, Chs. 4, 9, 10, for homotopy, bundles, monopoles, and instantons.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” arXiv:1412.5148.
- J. Fuchs, C. Schweigert, and A. Valentino, “A geometric approach to boundaries and surface defects in Dijkgraaf–Witten theories,” arXiv:1307.3632.

## Version history

- 2026-06-19: Initial polished draft.
