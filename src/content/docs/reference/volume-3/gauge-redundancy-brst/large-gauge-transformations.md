---
title: "Large Gauge Transformations"
description: "Explains gauge transformations not connected to the identity, their topological classification, and their role in theta vacua, Chern–Simons quantization, boundary charges, and global anomalies."
sidebar:
  label: "Large Gauge Transformations"
  order: 10
level: Advanced
status: "Polished draft"
source: "Coleman, Aspects of Symmetry; Srednicki §§92–94; Weinberg Vol. II; Polyakov, Gauge Fields and Strings; standard instanton, theta-vacuum, and Chern–Simons treatments."
topics:
  - large gauge transformations
  - topological sectors
  - theta vacua
  - instantons
  - Chern-Simons level quantization
  - global anomalies
canonicalTopics:
  - large-gauge-transformations
  - small-gauge-transformations
  - theta-vacua
  - instanton-number
  - chern-simons-level-quantization
researchStatus:
  established:
    - "Gauge transformations can have disconnected topological sectors; in many gauge theories these sectors act nontrivially on vacuum labels, topological terms, line operators, and path-integral sectors."
    - "In four-dimensional Yang–Mills theory with compact simple gauge group, instanton number and theta periodicity are tied to the topology of large gauge transformations."
  active:
    - "The precise physical role of large gauge transformations depends on boundary conditions, global form of the gauge group, defects, anomalies, and coupling to gravity or higher-form backgrounds."
---

## Summary

Gauge transformations are maps from spacetime, or from a spatial slice, into a gauge group. Some of these maps can be continuously deformed to the identity. Others cannot. The latter are called **large gauge transformations**.

Small gauge transformations are generated infinitesimally by a gauge parameter $\alpha(x)$:

$$
U(x)=1+ig\alpha(x)+O(\alpha^2).
$$

Large gauge transformations live in different connected components of the gauge-transformation group. They are not visible in the infinitesimal gauge algebra alone.

This distinction matters because many topological effects in gauge theory are invisible if one only studies the Lie algebra. Large gauge transformations control:

- theta vacua in Yang–Mills theory;
- instanton number and tunneling between topological sectors;
- quantization of Chern–Simons levels;
- global gauge anomalies;
- periodicity of compact gauge holonomies;
- the difference between gauge redundancy, boundary symmetry, and superselection data.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Large gauge transformations relate integer-labeled vacuum sectors; theta vacua are phase-weighted superpositions.](/figures/symmetry-anomalies-topology/large-gauge-transformations-theta-vacua.svg)

<figcaption>

For $G=SU(N)$ on spatial $S^3$, large gauge transformations are classified by $\pi_3(G)=\mathbb Z$. They shift integer-labeled vacuum sectors. Theta vacua diagonalize this shift, and instantons later appear as Euclidean configurations interpolating between adjacent labels.

</figcaption>
</figure>

The slogan is:

$$
\text{gauge redundancy can have topology.}
$$

That sentence sounds innocent. It is not. It is the gateway to instantons, theta angles, Chern–Simons theory, global anomalies, and much of the modern relation between symmetry and topology.

## Prerequisites

Read [Gauge Symmetry Is Redundancy](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-symmetry-is-redundancy/), [Local Versus Global Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/local-versus-global-transformations/), [Gauge Fixing](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-fixing/), [BRST Symmetry](/symmetry-anomalies-topology/gauge-redundancy-brst/brst-symmetry/), and [Gribov Ambiguities Preview](/symmetry-anomalies-topology/gauge-redundancy-brst/gribov-ambiguities-preview/) first.

You should also know the basic topological idea that maps from one space to another can fall into disconnected homotopy classes, such as

$$
[S^3,SU(N)]\cong \pi_3(SU(N))\cong\mathbb Z.
$$

## Core idea

The infinitesimal gauge algebra sees only transformations near the identity. But the full gauge group can have disconnected components.

Let $\mathcal G$ be the group of allowed gauge transformations. Its connected component containing the identity is denoted $\mathcal G_0$. A **small gauge transformation** lies in $\mathcal G_0$. A **large gauge transformation** lies in another component:

$$
U\in\mathcal G/\mathcal G_0,
\qquad
U\notin\mathcal G_0.
$$

Large gauge transformations are not necessarily large in size. They can be smooth and gentle everywhere. “Large” means topologically large: no continuous path inside the allowed transformation space connects them to the identity.

This is why the phrase can be misleading. A large gauge transformation is not a gauge transformation with big amplitude. It is a gauge transformation with nontrivial topology.

## Setup and conventions

Use the gauge-field convention from the previous pages in this chapter:

$$
D_\mu=\partial_\mu+igA_\mu,
\qquad
A_\mu=A_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c.
$$

The finite gauge transformation is

$$
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

A transformation is called small if it can be written as a continuous path $U_t(x)$ with

$$
U_0(x)=1,
\qquad
U_1(x)=U(x),
$$

while preserving the boundary conditions required in the theory. If no such path exists, it is large.

:::note[Boundary-sensitive definition]
“Allowed gauge transformation” is not a purely local phrase. It depends on boundary conditions, operator insertions, gauge-bundle data, and which transformations are treated as redundancies rather than physical symmetries. A transformation that is a redundancy in a closed universe may act as a physical asymptotic symmetry in a system with boundary.
:::

## A first example: U(1) gauge theory on a circle

The simplest large gauge transformations already appear for compact $U(1)$ gauge theory on a spatial circle of circumference $L$. Let $x\sim x+L$ and take

$$
U_n(x)=e^{2\pi i n x/L},
\qquad
n\in\mathbb Z.
$$

This map is single-valued because

$$
U_n(x+L)=U_n(x)e^{2\pi i n}=U_n(x).
$$

But for $n\neq0$, it cannot be continuously unwound to the identity while remaining a single-valued map $S^1\to U(1)$. It has winding number $n$.

For a constant gauge field component $A_x=a$, the transformation shifts

$$
a\mapsto a+\frac{2\pi n}{gL},
$$

with the sign following the convention for $A^U$. The Wilson loop around the circle is

$$
W=\exp\!\left(ig\int_0^L dx\,A_x\right)
=\exp(igLa).
$$

Under the shift,

$$
W\mapsto W\,e^{2\pi i n}=W.
$$

So large gauge transformations identify values of $a$ that look different as local gauge potentials but give the same compact holonomy. The physical zero mode is an angle, not a real number.

This example is small enough to keep in your pocket. It captures the big lesson: topology of gauge transformations can make a naive field variable periodic.

## Yang–Mills vacua and winding number

Now consider pure Yang–Mills theory on $\mathbb R^3$ with finite-energy boundary conditions. At spatial infinity, finite energy requires the field strength to vanish. The gauge field approaches a pure gauge:

$$
A_i\to -\frac{i}{g}U^{-1}\partial_iU
\qquad
\text{as }|\mathbf x|\to\infty,
$$

up to convention-dependent sign choices.

After adding the point at infinity, the spatial slice becomes topologically $S^3$. A pure-gauge vacuum configuration is therefore described by a map

$$
U:S^3\to G.
$$

For $G=SU(N)$ with $N\ge2$,

$$
\pi_3(SU(N))\cong\mathbb Z.
$$

Thus classical vacuum configurations come in winding sectors labeled by an integer $n$:

$$
|n\rangle,
\qquad n\in\mathbb Z.
$$

A large gauge transformation of winding $k$ shifts this label:

$$
U_k|n\rangle=|n+k\rangle.
$$

The local Yang–Mills Hamiltonian is built from field strengths, so it is invariant under gauge transformations. Therefore matrix elements between these winding-labeled states can only depend on differences such as $n'-n$.

The vacuum labels are not labels of different local physics. They are labels of topological sectors in the gauge-field configuration space. Quantum tunneling can mix them.

## Winding number formula

For maps

$$
U:S^3\to SU(N),
$$

a standard winding number is

$$
\nu(U)
=\frac{1}{24\pi^2}\int_{S^3}
\operatorname{tr}\left(U^{-1}dU\right)^3.
$$

The cube means wedge product:

$$
\operatorname{tr}(U^{-1}dU)^3
=\operatorname{tr}(U^{-1}dU\wedge U^{-1}dU\wedge U^{-1}dU).
$$

This integer counts how many times the spatial $S^3$ wraps the group manifold. For $SU(2)$, the group manifold itself is topologically $S^3$, so the winding number is especially literal.

Multiplication of maps adds winding numbers:

$$
\nu(UV)=\nu(U)+\nu(V).
$$

That additivity is the topological reason large gauge transformations shift vacuum labels by integers.

:::note[Convention-sensitive source note]
Some authors use $UdU^{-1}$ instead of $U^{-1}dU$, or define pure gauges with the opposite sign. This flips the sign of $\nu$. The invariant content is the integer classification and the additivity under composition.
:::

## Instantons and theta vacua

Euclidean Yang–Mills configurations can interpolate between winding sectors. If a configuration approaches a vacuum of winding $n_-$ at Euclidean time $-\infty$ and a vacuum of winding $n_+$ at $+\infty$, then the topological charge is

$$
Q=n_+-n_-.
$$

With the Hermitian gauge-field convention above, a common normalization is

$$
Q=\frac{g^2}{8\pi^2}\int \operatorname{tr}(F\wedge F)
=\frac{g^2}{32\pi^2}\int d^4x\,F^a_{\mu\nu}\widetilde F^{a\mu\nu}
\in\mathbb Z,
$$

where $\operatorname{tr}(T^aT^b)=\frac12\delta^{ab}$. Equivalently, if one absorbs $igA$ into an anti-Hermitian mathematical connection $\mathcal A$, the same formula is often written without the explicit $g^2$.

:::note[Convention-sensitive source note]
Instanton-number formulas vary by factors of $g$, $i$, $2$, and signs because authors choose different normalizations for $A$, $F$, and the trace. The invariant statement is that finite-action Euclidean Yang–Mills configurations on compactified four-space have an integer topological charge, and the Yang–Mills instanton action is proportional to $8\pi^2|Q|/g^2$ in standard normalization.
:::

Instantons with $Q=1$ mediate transitions

$$
|n\rangle\to|n+1\rangle.
$$

Therefore the energy eigenstates are not individual $|n\rangle$ states. They are theta superpositions:

$$
|\theta\rangle
=\sum_{n\in\mathbb Z}e^{-in\theta}|n\rangle.
$$

The path-integral version is

$$
Z(\theta)=\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q.
$$

Since $Q$ is integer,

$$
\theta\sim\theta+2\pi.
$$

This is one of the cleanest examples of topology becoming a physical parameter in QFT. Locally the Lagrangian density may differ by a total derivative, but globally the path integral remembers the integer.

## Small versus large is not global versus local symmetry

Do not confuse two distinctions:

| Distinction | Meaning |
|---|---|
| small versus large | connected or disconnected from the identity inside the gauge-transformation group |
| gauge versus global | redundancy or physical transformation acting on states/operators |

A large transformation can still be a gauge redundancy. A small transformation that does not vanish at a boundary can act as a physical asymptotic symmetry. A constant transformation can be a global symmetry in one setup and a gauge redundancy in another.

The deciding data are boundary conditions and the definition of the operator algebra.

For example, in electrodynamics on all of space, gauge transformations that vanish at infinity are usually treated as redundancies. Transformations approaching a constant at infinity act on charged states and are associated with electric charge. In non-Abelian gauge theory, transformations approaching center elements can affect line-operator sectors. In gravity, the analogous distinction between pure gauge and asymptotic symmetry is even more delicate.

Large gauge transformations live exactly at this boundary between local redundancy and global structure.

## Large gauge transformations and Chern–Simons quantization

Three-dimensional Chern–Simons theory gives a classic use of large gauge transformations. For a compact gauge group, the Chern–Simons action has the schematic form

$$
S_{\rm CS}
=\frac{k}{4\pi}\int_M\operatorname{tr}\left(
A\wedge dA+\frac{2}{3}A\wedge A\wedge A
\right),
$$

with conventions depending on whether $A$ is Hermitian or anti-Hermitian.

Under a small gauge transformation, the action changes by a boundary term. On a closed three-manifold, this is harmless. Under a large gauge transformation of winding $n$, the action shifts by

$$
S_{\rm CS}\mapsto S_{\rm CS}+2\pi k n.
$$

The quantum path integral contains $e^{iS_{\rm CS}}$. For this phase to be invariant under all allowed large gauge transformations, one needs

$$
k\in\mathbb Z.
$$

This is the simplest conceptual derivation of Chern–Simons level quantization. The local equations of motion do not see the integrality of $k$. The large gauge transformations do.

Spin Chern–Simons theories, fermion-induced shifts, global forms of gauge groups, and boundary chiral modes refine this statement, but the basic mechanism is exactly this: the exponentiated action, not necessarily the action itself, must be well-defined under large gauge transformations.

## Large gauge transformations and global anomalies

Some anomalies are visible perturbatively through triangle diagrams or local descent equations. Others are global. A **global gauge anomaly** can occur when a large gauge transformation changes the sign or phase of the fermion path-integral measure.

Schematically, for a fermion determinant,

$$
\det D\!\!/_A
\mapsto
\det D\!\!/_{A^U},
$$

local gauge invariance would suggest equality. A global anomaly occurs if for some large $U$ the determinant changes by a nontrivial phase:

$$
\det D\!\!/_{A^U}=e^{i\varphi(U)}\det D\!\!/_A,
\qquad
 e^{i\varphi(U)}\neq1.
$$

The famous four-dimensional $SU(2)$ anomaly discovered by Witten is of this kind. It is invisible to the ordinary perturbative gauge-anomaly polynomial in the simplest way, but it still obstructs consistent gauging for an odd number of Weyl fermion doublets.

This volume treats anomalies later in detail. Here the important lesson is that checking infinitesimal gauge invariance is not always enough. A quantum theory must be invariant under all gauge transformations that are declared redundancies, including large ones.

## Large transformations and background fields

Large gauge transformations are just as important for background gauge fields as for dynamical gauge fields.

If $A$ is a background for a global symmetry, then invariance under background gauge transformations encodes Ward identities and the consistency of coupling to background bundles. Large background gauge transformations can impose quantization conditions on contact terms, Chern–Simons counterterms, theta terms, and anomaly phases.

This is why anomaly discussions often use background fields. A global symmetry has an ’t Hooft anomaly if the partition function coupled to a background field cannot be made invariant under all background gauge transformations:

$$
Z[A^U]\neq Z[A].
$$

For local transformations this leads to local anomaly equations. For large transformations it leads to global anomaly phases.

## Boundary conditions decide the story

On a closed compact manifold, all gauge transformations that preserve the bundle data are often treated as redundancies. On a manifold with boundary, this is not automatic.

A gauge transformation that is nontrivial at the boundary can change boundary data. It may therefore act on the Hilbert space as a physical symmetry rather than as a redundancy. This is the origin of edge modes, asymptotic charges, soft symmetries, and many modern boundary/defect refinements.

A useful hierarchy is:

| Transformation | Typical role |
|---|---|
| vanishes at boundary and connected to identity | pure gauge redundancy |
| nontrivial at boundary | possible global or asymptotic symmetry |
| disconnected from identity | possible large redundancy or topological sector action |
| changes bundle/topological sector | may relate sectors or label distinct sums |

The word “possible” is doing real work. The theory must say which transformations are included in $\mathcal G$, which are divided out, and which act on states.

## Relation to global form of the gauge group

The global form of the gauge group affects large gauge transformations.

A Lie algebra such as $\mathfrak{su}(N)$ does not uniquely determine the gauge group. One can have $SU(N)$ or quotients such as

$$
PSU(N)=SU(N)/\mathbb Z_N.
$$

These choices can change:

- which bundles are allowed;
- which Wilson lines are genuine;
- which magnetic fluxes exist;
- which large gauge transformations are allowed;
- which theta-like discrete parameters appear.

This is one reason modern QFT treats the global form of the gauge group as physical data, not a decorative afterthought. The local gauge algebra tells you the infinitesimal interactions. The global form tells you the nonlocal and topological sectors.

## Large gauge transformations versus Gribov copies

Large gauge transformations and Gribov ambiguities are related but not identical.

A large gauge transformation is a topologically nontrivial element of the gauge-transformation group. A Gribov copy is a repeated intersection of a gauge orbit with a chosen gauge-fixing slice.

A Gribov copy may be produced by a large transformation, but it need not be. Copies can also be associated with transformations connected to the identity. Conversely, a large gauge transformation can act on topological sectors without being discussed in a gauge-fixing slice at all.

The common theme is global geometry. Gribov copies say the quotient $\mathcal A/\mathcal G$ is not globally covered by a simple gauge slice. Large gauge transformations say $\mathcal G$ itself has nontrivial topology.

## Common pitfalls

**Pitfall 1: thinking large means numerically large.**

Large means disconnected from the identity, not big in amplitude.

**Pitfall 2: assuming every large gauge transformation is physical.**

Some large transformations are redundancies. Some act as physical symmetries. Boundary conditions and operator definitions decide.

**Pitfall 3: checking only the gauge algebra.**

Infinitesimal gauge invariance checks the connected component of the identity. Large gauge transformations can impose extra quantization or anomaly-cancellation conditions.

**Pitfall 4: forgetting compactness.**

Large $U(1)$ gauge transformations and periodic holonomies rely on compact $U(1)$, not the additive group $\mathbb R$.

**Pitfall 5: treating theta terms as local irrelevancies.**

The density $\operatorname{tr}(F\wedge F)$ is locally a total derivative, but its integral over a topologically nontrivial configuration is an integer. The path integral sees it.

## Relations to other pages

[Local Versus Global Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/local-versus-global-transformations/) explains why not every transformation with a spacetime-dependent parameter is pure redundancy in the same physical sense.

[Gribov Ambiguities Preview](/symmetry-anomalies-topology/gauge-redundancy-brst/gribov-ambiguities-preview/) discusses a different global obstruction: the failure of a gauge slice to intersect each orbit uniquely.

[Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/) and [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/) use large background transformations to test anomalies and counterterm quantization.

Later pages on theta terms, Chern–Simons terms, instanton number, global anomalies, anomaly inflow, and line operators will repeatedly use the same theme: the Lie algebra is not the whole gauge theory.

## Research status

The topology of compact Lie groups, instanton number, theta periodicity, and Chern–Simons level quantization are standard parts of modern QFT.

The active frontier lies in refined contexts: manifolds with boundary, extended operators, higher-form backgrounds, non-simply connected gauge groups, fermionic theories on spin or non-spin manifolds, generalized global symmetries, and coupling to dynamical gravity. In those settings, the phrase “large gauge transformation” still means “not connected to the identity,” but what it does physically can be surprisingly rich.

## Exercises

### Exercise 1. Large U(1) transformation on a circle

Let $x\sim x+L$ and

$$
U_n(x)=e^{2\pi i n x/L}.
$$

Show that $U_n$ is single-valued exactly when $n\in\mathbb Z$.

<details><summary><strong>Solution</strong></summary>

Single-valuedness requires

$$
U_n(x+L)=U_n(x).
$$

But

$$
U_n(x+L)=e^{2\pi i n(x+L)/L}=e^{2\pi i n x/L}e^{2\pi i n}.
$$

Thus we need

$$
e^{2\pi i n}=1,
$$

which holds exactly for integer $n$.

</details>

### Exercise 2. Holonomy periodicity

For a constant $U(1)$ gauge field $A_x=a$ on a circle, define

$$
W=\exp\!\left(ig\int_0^L dx\,A_x\right).
$$

Using the transformation $a\mapsto a-2\pi n/(gL)$, show that $W$ is invariant.

<details><summary><strong>Solution</strong></summary>

Under the shift,

$$
\int_0^L dx\,A_x
\mapsto
La-\frac{2\pi n}{g}.
$$

Therefore

$$
W\mapsto
\exp\!\left(igLa-i2\pi n\right)
=W e^{i2\pi n}.
$$

For $n\in\mathbb Z$,

$$
e^{i2\pi n}=1,
$$

so $W$ is invariant.

</details>

### Exercise 3. Theta periodicity

Suppose the Euclidean path integral decomposes as

$$
Z(\theta)=\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q.
$$

Show that $Z(\theta+2\pi)=Z(\theta)$.

<details><summary><strong>Solution</strong></summary>

We compute

$$
Z(\theta+2\pi)
=\sum_{Q\in\mathbb Z}e^{i(\theta+2\pi)Q}Z_Q
=\sum_{Q\in\mathbb Z}e^{i\theta Q}e^{i2\pi Q}Z_Q.
$$

Since $Q$ is an integer,

$$
e^{i2\pi Q}=1.
$$

Therefore

$$
Z(\theta+2\pi)=Z(\theta).
$$

</details>

### Exercise 4. Chern–Simons level quantization

Suppose a Chern–Simons action shifts under a large gauge transformation as

$$
S_{\rm CS}\mapsto S_{\rm CS}+2\pi k n,
\qquad n\in\mathbb Z.
$$

Show that invariance of $e^{iS_{\rm CS}}$ for all $n$ requires $k\in\mathbb Z$.

<details><summary><strong>Solution</strong></summary>

The exponentiated action transforms as

$$
e^{iS_{\rm CS}}
\mapsto
 e^{iS_{\rm CS}}e^{i2\pi k n}.
$$

For this to equal $e^{iS_{\rm CS}}$ for every integer $n$, we need

$$
e^{i2\pi k n}=1
$$

for all $n\in\mathbb Z$. Taking $n=1$ gives

$$
e^{i2\pi k}=1,
$$

so $k$ must be an integer.

</details>

### Exercise 5. Why infinitesimal checks are insufficient

Explain why verifying invariance under $U=1+ig\alpha+O(\alpha^2)$ does not automatically prove invariance under all gauge transformations.

<details><summary><strong>Solution</strong></summary>

An infinitesimal transformation probes only the connected component of the identity in the gauge-transformation group. If the group has disconnected components, a transformation in another component cannot be reached by exponentiating a small continuous path from the identity.

Therefore infinitesimal invariance checks local gauge invariance but may miss global constraints, such as Chern–Simons level quantization or global gauge anomalies.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, lectures on instantons, theta vacua, and classical lumps.
- M. Srednicki, *Quantum Field Theory*, Sections 92–94.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters on non-Abelian gauge theories and instantons.
- A. M. Polyakov, *Gauge Fields and Strings*, chapters on topology of gauge fields and related problems.
- G. ’t Hooft, papers on instantons and the $U(1)$ problem.
- R. Jackiw and C. Rebbi, papers on vacuum periodicity and theta vacua.
- C. G. Callan, R. Dashen, and D. J. Gross, papers on instantons and the Yang–Mills vacuum.
- E. Witten, “An SU(2) Anomaly.”
- S. Deser, R. Jackiw, and S. Templeton, and E. Witten, classic references on Chern–Simons gauge theory.

## Version history

- 2026-06-17: Initial polished page for the Gauge Redundancy and BRST chapter.
