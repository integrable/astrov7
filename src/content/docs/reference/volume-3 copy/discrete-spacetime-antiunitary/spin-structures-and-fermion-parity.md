---
title: "Spin Structures and Fermion Parity"
description: "Explains why fermionic QFTs require spin or Pin data, how fermion parity enters the operator algebra, and how boundary conditions around cycles become physical background data."
sidebar:
  label: "Spin Structures"
  order: 8
level: Advanced
status: "Polished draft"
source: "Weinberg Vol. I on spin and discrete symmetries; Witten on fermion path integrals and topological phases; Gaiotto–Kapustin on spin TQFT; Freed–Hopkins on reflection positivity and invertible phases; standard spin-geometry references."
topics:
  - spin structures
  - fermion parity
  - Pin structures
  - fermionic QFT
  - spin-statistics
  - thermal boundary conditions
  - fermion path integrals
  - spin TQFT
canonicalTopics:
  - spin-structure
  - fermion-parity
  - pin-structure
  - fermionic-qft
  - spin-statistics
  - fermion-boundary-conditions
researchStatus:
  established:
    - "A local relativistic QFT with fermionic operators is not just an oriented QFT on manifolds; its partition functions and correlation functions require spin, and sometimes Pin, structure data."
    - "Fermion parity $(-1)^F$ is the central order-two symmetry separating even and odd operators and is tied to the lift of rotations to the spin group."
  active:
    - "The modern classification of fermionic anomalies, fermionic SPT phases, spin TQFTs, and reflection symmetries uses spin/Pin cobordism and invertible field theories; conventions differ across high-energy, condensed-matter, and mathematical literature."
---

## Summary

A bosonic QFT can often be placed on any oriented spacetime manifold once its background fields are specified. A fermionic QFT needs more. It must know how spinors behave when transported around noncontractible cycles, and this information is not determined by the metric alone. That extra datum is a **spin structure**.

On a closed oriented Euclidean spacetime $M$, a spin structure is a choice of lift of the oriented orthonormal frame bundle from $SO(d)$ to $Spin(d)$. Informally, it is the globally consistent rule that tells a fermion whether it returns with sign $+$ or sign $-$ after being parallel transported around each cycle.

For a simple torus, one often describes the same data by saying whether the fermion is periodic or antiperiodic around the two independent cycles. Those signs are not a decorative convention. They change the fermion determinant, distinguish thermal traces from fermion-parity-graded traces, and control whether a proposed symmetry can be gauged.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Spin structure and fermion parity data: a spacetime with cycles needs spin or Pin data before fermion path integrals are numbers; boundary conditions around cycles compute ordinary or fermion-parity-graded traces.](/figures/symmetry-anomalies-topology/spin-structure-fermion-parity.svg)

<figcaption>

Fermionic QFTs need more than a metric and orientation. A spin structure chooses signs for fermions around cycles in a globally consistent way. On a Euclidean time circle, antiperiodic fermions compute $	ext{Tr}\,e^{-\beta H}$, while periodic fermions compute $	ext{Tr}\,(-1)^F e^{-\beta H}$. Orientation-reversing symmetries require Pin-type refinements rather than an ordinary spin structure alone.

</figcaption>
</figure>

The central operator

$$
(-1)^F
$$

is **fermion parity**. It acts by $+1$ on even states and by $-1$ on odd states. Bosonic local observables commute with it, while fermionic fields anticommute with it. In relativistic QFT, the $2\pi$ rotation on fermionic states is identified with this operator:

$$
R(2\pi)=(-1)^F.
$$

That sentence is short, but it is load-bearing. It is the bridge between spin-statistics, spin structures, supersymmetry, fermionic anomalies, and the modern language of spin TQFT.

## Prerequisites

Read [Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/parity/), [Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/time-reversal/), [Charge Conjugation](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/charge-conjugation/), [Antiunitary Symmetries](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/antiunitary-symmetries/), and [Reflection Positivity and Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/reflection-positivity-and-time-reversal/) first. You should also know the background-field viewpoint from [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/) and [Gauging Finite Symmetries: Preview](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-finite-symmetries-preview/).

The mathematical prerequisites are modest if you read this page conceptually: covers, bundles, and holonomies. The precise construction uses frame bundles, Stiefel–Whitney classes, Clifford algebras, spin groups, and Pin groups.

## Core idea

Fermions are not ordinary functions on spacetime. A fermion field is a section of a spinor bundle. The spinor bundle exists only after choosing suitable global lifting data.

Locally, there is no drama. In a small coordinate patch, one writes a Dirac field as

$$
\psi_\alpha(x),
$$

and under a local Lorentz rotation one transforms the spinor index by a spin representation. Globally, however, one must ask whether these local spinor frames can be glued consistently around loops.

A vector rotated by $2\pi$ returns to itself. A spinor rotated by $2\pi$ changes sign:

$$
\psi\mapsto -\psi.
$$

This means the group acting on spinors is not $SO(d)$ but its double cover $Spin(d)$:

$$
1\longrightarrow \mathbb Z_2\longrightarrow Spin(d)\longrightarrow SO(d)\longrightarrow 1.
$$

A spin structure is the choice that tells the theory how to lift the $SO(d)$ frame bundle of spacetime to a $Spin(d)$ bundle. Without that lift, the phrase “the fermion determinant on $M$” is usually not a well-defined number.

In operator language, the same physics appears as fermion parity. The operator $(-1)^F$ is central and squares to one:

$$
((-1)^F)^2=1.
$$

For an even operator $\mathcal O_+$ and an odd operator $\mathcal O_-$,

$$
(-1)^F\mathcal O_+(-1)^F=\mathcal O_+,
\qquad
(-1)^F\mathcal O_-(-1)^F=-\mathcal O_-.
$$

Thus the operator algebra is $\mathbb Z_2$-graded. The even part is the algebra of bosonic observables. The odd part consists of fermionic operators; these are indispensable in many formulations, but their correlation functions depend on spin data.

## Setup and conventions

The volume uses Lorentzian signature

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1)
$$

unless a page says otherwise. Spin-structure questions are often clearest in Euclidean signature, where a closed spacetime $M_d$ is used as the argument of a partition function

$$
Z[M_d,\rho,A,\ldots].
$$

Here $\rho$ denotes the spin structure and $A$ denotes any additional background fields. A fermionic partition function should be thought of as a function of $\rho$:

$$
Z_\rho[M_d,A].
$$

Changing $\rho$ can change the answer.

For an oriented manifold $M$, a spin structure exists only if

$$
w_2(TM)=0,
$$

where $w_2(TM)$ is the second Stiefel–Whitney class of the tangent bundle. If spin structures exist, the set of spin structures is not naturally a vector space, but it is a torsor for

$$
H^1(M,\mathbb Z_2).
$$

Concretely, shifting the spin structure by a flat $\mathbb Z_2$ gauge field changes the signs assigned to fermions around cycles.

:::note[Convention-sensitive source note]
The notation $\rho$ for a spin structure is common in parts of the modern anomalies and TQFT literature, but other sources use $\eta$, $s$, or write the boundary conditions explicitly. Also, the sign convention “periodic versus antiperiodic” around a cycle depends on whether one is discussing the spin structure itself, the fermion field boundary condition, or a trace convention. This page uses the physics convention: around Euclidean time, antiperiodic fermions compute the ordinary thermal trace, while periodic fermions compute the $(-1)^F$-graded trace.
:::

## Fermion parity as a symmetry

Every local fermionic QFT has a distinguished central order-two symmetry called fermion parity,

$$
\mathbb Z_2^F=\{1,(-1)^F\}.
$$

It is not the same thing as a conserved continuous fermion number. A Majorana fermion may have no $U(1)$ number symmetry, but it still has $(-1)^F$.

A Dirac theory often has a $U(1)$ symmetry

$$
\psi\mapsto e^{i\alpha}\psi,
$$

with number operator $N$. In that case

$$
(-1)^F=e^{i\pi N}
$$

on the elementary fermions. But this formula is not the definition in full generality. Fermion parity is more primitive than fermion number.

The grading of the Hilbert space is

$$
\mathcal H=\mathcal H_+\oplus\mathcal H_-,
$$

where

$$
(-1)^F|\psi_\pm\rangle=\pm |\psi_\pm\rangle.
$$

Even local operators preserve the grading. Odd operators flip it:

$$
\mathcal O_-:\mathcal H_+\leftrightarrow\mathcal H_-.
$$

This is why fermion parity is sometimes described as a superselection label for the algebra of bosonic observables. If one restricts to the even local observable algebra, no local bosonic experiment changes the parity sector.

### Why fermion parity is not optional

One might try to define a theory of “fermions” without declaring $(-1)^F$. That is like trying to define a charged theory without saying what charge conjugation or the charge grading does. The statistics of the fields, the signs in operator products, the allowed traces, and the consistency of the path integral all need the grading.

The basic algebraic sign is

$$
\mathcal O_-(x)\mathcal O_-(y)=-\mathcal O_-(y)\mathcal O_-(x)
$$

at spacelike separation, up to the representation-dependent spinor indices and the usual locality caveats. Even operators commute at spacelike separation in the ordinary bosonic sense. Odd operators are local only in the graded sense.

A useful slogan is

$$
\text{fermionic QFT}=\text{locality with a }\mathbb Z_2^F\text{ grading}.
$$

## Spin structure as background data

A global symmetry can be coupled to a background gauge field. Fermion parity is special because the background data for it are entangled with spacetime spin data.

On a torus $T^2$, there are four spin structures. If the two independent cycles are called $a$ and $b$, one may label them by signs

$$
(\epsilon_a,\epsilon_b),\qquad \epsilon_a,\epsilon_b\in\{+1,-1\},
$$

where $+1$ means periodic and $-1$ means antiperiodic boundary conditions for fermions around that cycle.

On a spatial circle of length $L$,

$$
\psi(x+L)=\epsilon\,\psi(x).
$$

For $\epsilon=-1$, momenta are half-integer moded:

$$
p_n=\frac{2\pi}{L}\left(n+\frac12\right).
$$

For $\epsilon=+1$, momenta are integer moded:

$$
p_n=\frac{2\pi n}{L}.
$$

This difference changes the Hilbert space spectrum. It is not removable by a local counterterm.

On a Euclidean thermal circle of circumference $\beta$, the trace interpretation is

$$
Z_{\rm A}(\beta)=\operatorname{Tr}_{\mathcal H} e^{-\beta H},
$$

for antiperiodic fermions, and

$$
Z_{\rm P}(\beta)=\operatorname{Tr}_{\mathcal H} (-1)^F e^{-\beta H},
$$

for periodic fermions. The latter is the basic structure behind the Witten index in supersymmetric theories.

:::note[Convention-sensitive source note]
Thermal antiperiodic boundary conditions are a trace convention, not a statement that the microscopic fermion has somehow ceased to be a fermion. They come from the cyclicity of the trace combined with the sign picked up when moving fermionic coherent-state variables around the trace. Periodic Euclidean time corresponds to inserting $(-1)^F$ in the trace.
:::

## Spin and the 2π rotation

For a relativistic fermion, a $2\pi$ spatial rotation is not the identity on the state vector. It acts as

$$
R(2\pi)=-1
$$

on a one-fermion state. On a state with $F$ fermions, it acts as

$$
R(2\pi)=(-1)^F.
$$

This is the physical reason the central $\mathbb Z_2$ in $Spin(d)$ must be identified with fermion parity.

For an internal symmetry group $G_f$ of a fermionic theory, the subgroup $\mathbb Z_2^F$ is usually required to be central:

$$
\mathbb Z_2^F\subset Z(G_f).
$$

The true combined structure of spacetime and internal symmetry can be more subtle than a direct product. A common modern notation is a quotient of the form

$$
Spin(d)\times_{\mathbb Z_2^F}G_f,
$$

meaning that the central element $-1\in Spin(d)$ is identified with fermion parity inside $G_f$.

This notation becomes essential in theories with spin-charge relations. For example, a theory may be formulated not on arbitrary spin manifolds, but on manifolds with a combined spin and gauge structure, such as a $Spin^c$ structure. Then some excitations that look spinorial can be consistently defined only together with a background gauge field.

## Spin, Spin-c, and spin-charge relations

A $Spin^c$ structure is a refinement that lets charged fermions be defined on some oriented manifolds that are not spin, provided a $U(1)$ gauge background compensates the obstruction. Schematically, one replaces the condition

$$
w_2(TM)=0
$$

by a condition involving the first Chern class of a $U(1)$ bundle:

$$
c_1(L)\equiv w_2(TM)\pmod 2.
$$

This is not just mathematical decoration. In condensed matter and high-energy examples, the microscopic theory may impose a spin-charge relation: particles with odd electric charge are fermions and particles with even electric charge are bosons, or some variant of that statement. Then the actual background field is not simply “a metric plus an electromagnetic field”; it is a combined geometric structure.

The lesson is that “the global symmetry group” of a fermionic theory is not determined only by a Lie algebra. It includes how internal symmetry, spacetime rotations, and fermion parity are glued together.

## Pin structures and reflections

Spin structures are for oriented manifolds. But parity, time reversal after Wick rotation, and reflection symmetries naturally ask us to consider orientation-reversing operations. Then the relevant double covers are Pin groups rather than Spin groups.

There are two common Pin groups:

$$
Pin^+(d),\qquad Pin^-(d).
$$

They differ by the square of a lifted reflection. Roughly, if $r$ is a unit reflection in the Clifford algebra, then the two versions encode whether the lifted reflection squares to $+1$ or $-1$, with convention-dependent signs.

In QFT language, the difference shows up in questions like

$$
\mathsf T^2=1
\qquad\text{or}\qquad
\mathsf T^2=(-1)^F,
$$

and similarly for reflection symmetries. Which Pin structure is used depends on the Lorentzian-to-Euclidean dictionary and on whether the reflected coordinate is interpreted as time or space.

:::caution[Do not memorize a Pin table without the convention]
Different communities attach $Pin^+$ and $Pin^-$ to Lorentzian time reversal and spatial reflection in different but related ways. In one widely used condensed-matter/anomalies convention, a fermionic time-reversal symmetry with $\mathsf T^2=(-1)^F$ is associated to a $Pin^+$ Euclidean structure, while $\mathsf T^2=1$ is associated to $Pin^-$. Other sources reverse the dictionary because they reflect a different coordinate or use a different Clifford-sign convention. The invariant question is: what is the square of the lifted orientation-reversing symmetry on fermions?
:::

This is why pages about time reversal, reflection positivity, and discrete anomalies must be explicit about conventions. The symbol $\mathsf T$ alone is not enough.

## Fermionic partition functions

For a bosonic theory, one often writes

$$
Z[M,A]
$$

for the partition function on spacetime $M$ with background field $A$. For a fermionic theory, the better notation is

$$
Z[M,\rho,A],
$$

where $\rho$ is a spin or Pin structure.

A free massive Majorana fermion in Euclidean signature gives a Pfaffian rather than an ordinary determinant:

$$
Z_\rho[M]\propto \operatorname{Pf}(D_\rho+m),
$$

where $D_\rho$ is the Dirac operator built from the chosen spin structure. A Dirac fermion gives a determinant:

$$
Z_\rho[M]\propto \det(D_\rho+m).
$$

These expressions are schematic because regularization, phases, zero modes, and background fields matter. Still, they reveal the main point: the operator whose determinant is being taken depends on $\rho$.

Zero modes can make this dependence spectacular. If $D_\rho$ has zero modes and the massless path integral has no insertions to soak them up, then

$$
Z_\rho[M]=0.
$$

Changing the spin structure can change the number of zero modes and hence change whether the partition function vanishes.

## Gauging fermion parity and summing over spin structures

For an ordinary finite bosonic symmetry $G$, gauging means summing over background $G$ bundles, weighted by automorphism factors and possible topological actions. For a fermionic theory, “gauging $(-1)^F$” is more subtle because the $\mathbb Z_2^F$ background is tied to spin structure.

Very roughly, summing over spin structures can turn a spin theory into a bosonic theory, sometimes after adding a topological weight such as an Arf invariant in two dimensions. Conversely, fermionization can recover a spin theory from a bosonic theory with an appropriate one-form or defect structure.

A famous two-dimensional example uses the Arf invariant

$$
\operatorname{Arf}(\rho)\in \mathbb Z_2,
$$

which assigns a mod-two number to a spin structure on a Riemann surface. The invertible spin TQFT with partition function

$$
Z_\rho=(-1)^{\operatorname{Arf}(\rho)}
$$

is a minimal example of a fermionic topological phase.

This is one of the first places where the modern language of spin TQFT is not optional. Fermionic phases, fermionic anomalies, and fermionic dualities often cannot be stated cleanly without tracking spin structures.

## Boundary conditions, sectors, and traces

A common source of confusion is mixing up three different uses of “periodic” and “antiperiodic.”

First, a spatial boundary condition labels a Hilbert space. On a spatial circle,

$$
\psi(x+L)=\pm \psi(x)
$$

can define different sectors of the theory.

Second, a Euclidean-time boundary condition labels a trace. Around thermal time,

$$
\psi(\tau+\beta)= -\psi(\tau)
$$

computes the ordinary thermal trace, while

$$
\psi(\tau+\beta)= +\psi(\tau)
$$

computes the fermion-parity-graded trace.

Third, a spin structure on a general closed manifold is not merely a list of signs assigned independently to cycles. The signs must satisfy global consistency conditions encoded by the spin bundle.

On a genus-$g$ Riemann surface, if spin structures exist, there are

$$
2^{2g}
$$

of them. They are often divided into even and odd spin structures according to the parity of the number of holomorphic spinor zero modes. That parity is related to the Arf invariant.

## Fermion parity and local operators

A local operator has a fermion parity:

$$
|\mathcal O|\in\{0,1\}.
$$

The value $0$ means even, and the value $1$ means odd. In a graded-local theory, exchanging two spacelike-separated homogeneous operators gives the sign

$$
\mathcal O_1(x)\mathcal O_2(y)
= (-1)^{|\mathcal O_1||\mathcal O_2|}\mathcal O_2(y)\mathcal O_1(x),
$$

up to the usual spinor/tensor index transformations and ordering conventions.

A bosonic QFT, in the strict sense, has only even local operators. A fermionic QFT has a graded operator algebra, but its even subalgebra is what one can probe without choosing spin-sensitive line data.

This distinction becomes important for dualities. Two descriptions may have very different elementary fields but the same even operator algebra. In two dimensions, bosonization is the classic example: fermionic operators on one side map to disorder or twist-like operators on the bosonic side, and the spin structure becomes part of the dictionary.

## Symmetries of fermionic theories

An internal symmetry of a fermionic QFT should commute with fermion parity. Thus the full internal symmetry group is not merely $G$ but a pair

$$
(G_f,\mathbb Z_2^F\subset Z(G_f)).
$$

The bosonic symmetry group is often the quotient

$$
G_b=G_f/\mathbb Z_2^F.
$$

This quotient can be physically useful, but it can also hide information. A symmetry action on fermions may be projective from the viewpoint of $G_b$ but honest from the viewpoint of $G_f$.

For example, suppose a symmetry element $g$ squares to fermion parity:

$$
g^2=(-1)^F.
$$

Then $g$ has order four in $G_f$ but order two in $G_b$. Saying merely “there is a $\mathbb Z_2$ symmetry” loses the distinction between

$$
g^2=1
\qquad\text{and}\qquad
 g^2=(-1)^F.
$$

This distinction is exactly the kind of input that changes Pin structures, anomaly classifications, and boundary-state degeneracies.

## Relation to anomalies

A fermionic theory may be perfectly consistent on every spin manifold but impossible to define as an ordinary bosonic theory independent of spin structure. That is not a bug; it is what being fermionic means.

An anomaly appears when a proposed symmetry or background coupling cannot be made consistent even after the required spin/Pin data are included. For example, an attempted time-reversal symmetry may force the partition function to transform by a sign or phase under a change of Pin structure. That sign may be removable by a local counterterm, or it may represent a genuine anomaly.

In modern language, the anomaly of a $d$-dimensional fermionic theory is often encoded by an invertible $(d+1)$-dimensional spin or Pin field theory. The boundary theory is then not an ordinary standalone number-valued partition function; it is naturally a boundary state for the bulk anomaly theory.

This is the conceptual handoff to [Anomalies of Discrete Symmetries: Preview](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/anomalies-of-discrete-symmetries-preview/).

## Common pitfalls

**Pitfall 1: “Fermion parity is just fermion number mod two.”**

Sometimes yes, but not as a definition. Majorana theories have fermion parity even without a conserved $U(1)$ fermion number.

**Pitfall 2: “A spin structure is just periodic or antiperiodic boundary conditions.”**

That description works for simple cycles on simple manifolds. The general definition is a lift of the frame bundle. The cycle signs are shadows of that lift.

**Pitfall 3: “Thermal fermions are antiperiodic because fermions are antiperiodic in space.”**

No. Antiperiodicity around Euclidean time comes from the trace and the Grassmann nature of coherent states. Spatial boundary conditions are separate spin-structure data.

**Pitfall 4: “Pin plus and Pin minus have universal physics labels.”**

They do not without a convention. Always ask which reflection is being lifted and what the square of that lift is on fermions.

**Pitfall 5: “If a theory depends on spin structure, it is anomalous.”**

No. Dependence on spin structure is normal for a fermionic theory. An anomaly is an obstruction to a proposed symmetry, gauging, or background-field coupling after including the required geometric data.

## Relations to other pages

This page completes the discrete-symmetry setup begun in [Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/parity/), [Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/time-reversal/), [Charge Conjugation](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/charge-conjugation/), and [CPT Theorem Perspective](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/cpt-theorem-perspective/).

It also connects directly to [Reflection Positivity and Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/reflection-positivity-and-time-reversal/), where Euclidean reflection and Lorentzian antiunitarity meet.

The background-field and gauging viewpoint is developed in [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/). The role of fermion parity in finite gauging, spin TQFT, and anomaly inflow becomes central in the anomaly and symmetry-TFT chapters.

## Research status

The basic need for spin structures in fermionic QFT is settled. The connection between $2\pi$ rotation, spin-statistics, and fermion parity is part of the standard structure of relativistic QFT.

What is more modern is the systematic use of spin and Pin structures to classify fermionic anomalies, fermionic SPT phases, spin TQFTs, and nonperturbative definitions of fermionic theories. This subject is active because it sits at the intersection of high-energy QFT, condensed matter, topology, and category theory.

A safe reader habit is to separate three levels:

1. **Standard QFT level:** fermions require spin structures, and $(-1)^F$ grades the Hilbert space.
2. **Anomaly level:** proposed symmetries may require spin/Pin background fields and may have inflow anomalies.
3. **Classification level:** invertible spin/Pin TQFTs and cobordism groups classify broad families of fermionic phases and anomalies under specified assumptions.

The third level is powerful but convention-heavy. Do not import a classification table without checking dimension, reflection convention, symmetry extension, and whether the theory is bosonic or fermionic.

## Exercises

### Exercise 1: Thermal trace and fermion parity

Let $H$ commute with $(-1)^F$. Explain why antiperiodic fermions around the Euclidean time circle compute

$$
Z_{\rm A}(\beta)=\operatorname{Tr}e^{-\beta H},
$$

while periodic fermions compute

$$
Z_{\rm P}(\beta)=\operatorname{Tr}(-1)^F e^{-\beta H}.
$$

<details><summary><strong>Solution</strong></summary>

In the operator trace, the final state is identified with the initial state after evolving by $e^{-\beta H}$. For bosonic coherent variables this identification is periodic. For fermionic coherent variables, cyclically moving Grassmann variables through the trace produces a minus sign. Therefore the ordinary trace corresponds to antiperiodic fermionic fields around Euclidean time.

If one inserts $(-1)^F$, the extra sign from fermion parity cancels the Grassmann trace sign. The resulting path integral has periodic fermions around Euclidean time. Thus

$$
\operatorname{Tr}e^{-\beta H}\leftrightarrow \psi(\tau+\beta)=-\psi(\tau),
$$

and

$$
\operatorname{Tr}(-1)^F e^{-\beta H}\leftrightarrow \psi(\tau+\beta)=+\psi(\tau).
$$

</details>

### Exercise 2: Fermion parity without fermion number

A Majorana fermion has no ordinary $U(1)$ particle-number symmetry. Why does it still have fermion parity?

<details><summary><strong>Solution</strong></summary>

A Majorana field satisfies a reality condition, so the phase rotation $\psi\mapsto e^{i\alpha}\psi$ is not a symmetry for general $\alpha$. However, the sign flip

$$
\psi\mapsto -\psi
$$

preserves the Majorana condition and the fermionic operator algebra. This sign flip is $(-1)^F$ acting on odd operators. It squares to one and is central in the graded operator algebra. Thus fermion parity exists even when a continuous fermion-number symmetry does not.

</details>

### Exercise 3: Spin structures on a torus

The torus $T^2$ has

$$
H^1(T^2,\mathbb Z_2)\cong \mathbb Z_2\oplus\mathbb Z_2.
$$

Assuming one spin structure exists, how many spin structures does $T^2$ have? How can they be labeled physically?

<details><summary><strong>Solution</strong></summary>

If spin structures exist, they form a torsor for $H^1(M,\mathbb Z_2)$. Therefore $T^2$ has

$$
|H^1(T^2,\mathbb Z_2)|=4
$$

spin structures. Physically, choose two independent cycles $a$ and $b$. The four spin structures are labeled by whether the fermion is periodic or antiperiodic around each cycle:

$$
(P,P),\quad(P,A),\quad(A,P),\quad(A,A).
$$

The labels depend on a choice of basis of cycles, but the statement that there are four choices is invariant.

</details>

### Exercise 4: Central extension versus quotient

Suppose $G_f$ contains a central element $(-1)^F$, and an element $g\in G_f$ obeys

$$
g^2=(-1)^F.
$$

What is the order of $g$ in $G_f$? What is the order of its image in $G_b=G_f/\mathbb Z_2^F$?

<details><summary><strong>Solution</strong></summary>

Since

$$
g^2=(-1)^F
$$

and $((-1)^F)^2=1$, one has

$$
g^4=1.
$$

If $g^2\ne 1$, then $g$ has order four in $G_f$. In the quotient $G_b$, the element $(-1)^F$ becomes the identity. Therefore the image $\bar g$ satisfies

$$
\bar g^2=1.
$$

So $\bar g$ has order two in the bosonic quotient. This is why specifying only $G_b$ loses fermionic symmetry data.

</details>

## References

- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I. See the discussion of Wigner symmetries, projective representations, Lorentz representations, and discrete transformations.
- Mark Srednicki, *Quantum Field Theory*. See the sections on discrete symmetries, spinor fields, gauge fields, BRST, and anomalies.
- Sidney Coleman, *Aspects of Symmetry*. See especially lectures on symmetry, spontaneous symmetry breaking, instantons, and fermionic zero modes.
- Edward Witten, “Fermion Path Integrals And Topological Phases,” arXiv:1508.04715.
- Davide Gaiotto and Anton Kapustin, “Spin TQFTs and Fermionic Phases of Matter,” arXiv:1505.05856.
- Lakshya Bhardwaj, Davide Gaiotto, and Anton Kapustin, “State Sum Constructions of Spin-TFTs and String Net Constructions of Fermionic Phases of Matter,” arXiv:1605.01640.
- Daniel S. Freed and Michael J. Hopkins, “Reflection Positivity and Invertible Topological Phases,” arXiv:1604.06527.
- H. Blaine Lawson and Marie-Louise Michelsohn, *Spin Geometry*.

## Version history

- 2026-06-18: First polished draft. Added spin-structure definitions, fermion parity, thermal trace conventions, Pin-structure caveats, spin-charge relations, exercises, and anomaly handoff.
