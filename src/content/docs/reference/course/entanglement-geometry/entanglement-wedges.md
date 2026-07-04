---
title: "Entanglement Wedges"
description: "The bulk region dual to a boundary reduced density matrix, including causal wedges, nesting, reconstruction, and quantum error correction."
sidebar:
  order: 40
---

The HRT formula computes one number, the entropy $S_A$. The next question is more ambitious: **which part of the bulk is described by the reduced density matrix $\rho_A$?**

The answer is not merely the region that can send signals to and receive signals from the boundary domain $D[A]$. That smaller causal region is important, but it is not the full story. Holography teaches us that the natural bulk dual of $\rho_A$ is the **entanglement wedge**.

Let $X_A$ be the HRT surface for a boundary region $A$. Choose a bulk achronal region $a$ satisfying

$$
\partial a=A\cup X_A.
$$

The **entanglement wedge** of $A$ is the bulk domain of dependence of $a$:

$$
\mathcal E[A]
=
D_{\mathrm{bulk}}[a].
$$

The slogan is

$$
\boxed{\rho_A\quad\longleftrightarrow\quad \mathcal E[A].}
$$

This slogan is one of the most important modern refinements of the AdS/CFT dictionary.

<figure class="doc-figure" style="--figure-width: 50rem;">

![The entanglement wedge bounded by a boundary region and its HRT surface, with the causal wedge shown as a smaller subregion.](/figures/course/entanglement-wedges.svg)

<figcaption>

The entanglement wedge $\mathcal E[A]$ is the bulk domain of dependence of a homology region $a$ with boundary $A\cup X_A$. The causal wedge $\mathcal C[A]$, built only from bulk causal curves connected to $D[A]$, is generally smaller. Entanglement wedge reconstruction says that bulk operators in $\mathcal E[A]$ can be represented on the boundary region $A$, within an appropriate code subspace.

</figcaption>
</figure>

## From an HRT surface to a wedge

The HRT prescription requires a homology region $a$ whose boundary is

$$
\partial a=A\cup X_A.
$$

This region $a$ is drawn on an achronal bulk slice. But the bulk physics associated with $\rho_A$ should not depend on a particular slicing of spacetime. The covariant object is therefore not $a$ itself, but its bulk domain of dependence:

$$
\mathcal E[A]=D_{\mathrm{bulk}}[a].
$$

A point $p$ lies in $D_{\mathrm{bulk}}[a]$ if every inextendible causal curve through $p$ intersects $a$. In ordinary field theory language, initial data on $a$ determines the physics in $D_{\mathrm{bulk}}[a]$. Thus the entanglement wedge is the causal development of the bulk region bounded by $A$ and its HRT surface.

For static RT examples, one can often draw $\mathcal E[A]$ as the spatial region between $A$ and $\gamma_A$, together with its time evolution. For genuinely time-dependent HRT examples, one should think directly in terms of the domain of dependence.

## The causal wedge

Before the entanglement wedge, an obvious guess was the **causal wedge**. Let $D[A]$ be the boundary domain of dependence of $A$. The causal wedge is

$$
\mathcal C[A]
=
J^+_{\mathrm{bulk}}(D[A])
\cap
J^-_{\mathrm{bulk}}(D[A]),
$$

where $J^+$ and $J^-$ denote the bulk causal future and causal past. Thus $\mathcal C[A]$ is the set of bulk points that can both receive signals from, and send signals to, the boundary domain $D[A]$.

This region has a direct operational meaning. If an observer restricted to $D[A]$ can send and receive causal signals through the bulk, those signals probe the causal wedge. The boundary of the causal wedge contains a codimension-two surface often called the **causal information surface**.

But the causal wedge is usually too small. Entanglement is not limited to causal communication. The reduced density matrix $\rho_A$ contains nonlocal information, and in holography that information reaches deeper into the bulk than causal propagation alone.

The typical hierarchy is

$$
\mathcal C[A]
\subseteq
\mathcal E[A],
$$

under standard classical assumptions. The inclusion can be strict.

## Why the entanglement wedge is the right object

There are several converging reasons to identify $\rho_A$ with $\mathcal E[A]$.

First, the HRT surface is not just an entropy surface. It is the boundary between the bulk region naturally assigned to $A$ and the bulk region naturally assigned to its complement. The homology region already appears in the entropy formula; the entanglement wedge is its covariant completion.

Second, relative entropy provides a powerful diagnostic. For nearby holographic states, the boundary relative entropy of reduced density matrices is matched by a bulk relative entropy in the entanglement wedge, together with the geometric area term associated with the HRT surface. Schematically,

$$
S(\rho_A\|\sigma_A)
=
S_{\mathrm{bulk}}(\rho_a\|\sigma_a)
+
\text{area contribution},
$$

with the precise statement depending on the order in $G_N$ and on the choice of code subspace.

Third, quantum error correction explains how the same bulk operator can be represented on different boundary regions. A bulk operator deep in the center of AdS may be reconstructable from many different boundary regions, as long as it lies in their entanglement wedges. This redundancy is not a bug; it is how local bulk physics can emerge from a nonlocal boundary encoding.

Thus the entanglement wedge is not merely a convenient drawing. It is the bulk region controlled by the boundary reduced density matrix.

## Entanglement wedge reconstruction

The strongest practical statement is **entanglement wedge reconstruction**:

$$
\text{bulk operators in }\mathcal E[A]
\quad\text{can be represented by operators acting on }A.
$$

More carefully, this statement is approximate and code-subspace dependent. It does not mean that a single exact boundary operator works in all CFT states. It means that within a suitable family of semiclassical bulk states, an operator localized in $\mathcal E[A]$ has a boundary representation supported on $A$ that reproduces its correlation functions in that code subspace.

If $\phi(x)$ is a low-energy bulk field with $x\in\mathcal E[A]$, then there should exist a boundary operator $\mathcal O_A[\phi(x)]$ supported in $A$ such that

$$
\langle \Psi_i|\phi(x)|\Psi_j\rangle_{\mathrm{bulk}}
=
\langle \Psi_i|\mathcal O_A[\phi(x)]|\Psi_j\rangle_{\mathrm{CFT}}
$$

for states $|\Psi_i\rangle,|\Psi_j\rangle$ in the chosen code subspace.

The same bulk operator may also be representable on another boundary region $B$, provided

$$
x\in \mathcal E[A]\cap \mathcal E[B].
$$

This looks paradoxical only if one expects a local bulk operator to have a unique boundary representation. Holography behaves more like an error-correcting code: logical information can be redundantly encoded in many physical subsystems.

## A first example: one interval in vacuum AdS$_3$/CFT$_2$

Take the vacuum of a two-dimensional holographic CFT, dual to pure AdS$_3$. Let $A$ be a single interval on a constant-time boundary slice. The RT surface $\gamma_A$ is a spacelike geodesic connecting the endpoints of $A$. On that time slice, the homology region $a$ is the bulk region between $A$ and $\gamma_A$. The entanglement wedge is the causal development of that region.

In the Poincaré disk picture, this is the bulk cap enclosed by the interval and its geodesic, evolved in time. This cap reaches deeper into AdS as the interval becomes larger.

This simple example already shows the radial/energy-scale intuition:

$$
A\text{ larger}
\quad\Rightarrow\quad
\mathcal E[A]\text{ reaches deeper into the bulk}.
$$

The exact statement, however, is geometric rather than purely radial: the wedge is determined by the HRT surface and the homology region.

## Entanglement wedge nesting

One of the most important consistency properties is **entanglement wedge nesting**. If two boundary regions obey

$$
A\subseteq B,
$$

then, under appropriate classical assumptions,

$$
\mathcal E[A]
\subseteq
\mathcal E[B].
$$

This is exactly what one expects if $\rho_B$ contains at least as much boundary information as $\rho_A$. The larger boundary region should reconstruct at least as much bulk as the smaller one.

Nesting is not just intuitive. It is tied to boundary causality, relative entropy monotonicity, and the maximin construction of HRT surfaces. In the quantum-corrected theory, the analogous statement becomes more subtle but remains central.

## Two intervals and wedge phase transitions

Let $A=A_1\cup A_2$ be two disjoint intervals in a holographic CFT$_2$ vacuum. There are two natural RT candidate topologies:

$$
\text{disconnected:}
\qquad
\gamma_{A_1}+\gamma_{A_2},
$$

and

$$
\text{connected:}
\qquad
\gamma_{13}+\gamma_{24},
$$

where the labels denote geodesics connecting different endpoint pairings.

When the intervals are far apart, the disconnected surface dominates. The entanglement wedge is disconnected, and the leading large-$N$ mutual information vanishes:

$$
I(A_1:A_2)=O(N^0).
$$

When the intervals are close enough, the connected surface dominates. The entanglement wedge becomes connected, and the mutual information is order $N^2$:

$$
I(A_1:A_2)=O(N^2).
$$

This is a crucial lesson. The connectivity of the entanglement wedge is not fixed by the topology of the boundary region alone. It depends on the dominant HRT surface, which depends on the state and region sizes.

## Black holes and horizons

For a one-sided thermal state dual to an AdS black hole, a boundary region can have an entanglement wedge that approaches the horizon depending on its size. For the entire boundary of a thermal density matrix, the relevant entropy includes the black-hole entropy.

For the eternal two-sided AdS black hole, the boundary theory consists of two entangled CFTs in the thermofield-double state. The entanglement wedge of one entire boundary is roughly its exterior region, bounded by the bifurcation surface. The entanglement wedge of both boundaries together can include the two-sided exterior and, depending on the setting and quantum corrections, portions associated with the wormhole interior.

A safe slogan is

$$
\text{horizons are not boundaries of the dictionary; they are part of the dictionary.}
$$

Entanglement wedges are one of the cleanest ways to ask which boundary subsystem knows about which bulk region near or behind a horizon.

## Complementarity and purity

Suppose the total boundary state is pure and the boundary Cauchy slice is divided into $A$ and $\bar A$. Then

$$
S_A=S_{\bar A}.
$$

In the leading classical HRT formula, this equality is reflected by the fact that $A$ and $\bar A$ often share the same HRT surface:

$$
X_A=X_{\bar A}.
$$

Their entanglement wedges are complementary domains separated by the shared HRT surface.

In mixed states, especially thermal states, this simple complementarity can fail. The HRT surface for $A$ and the HRT surface for $\bar A$ can differ by horizon components, reflecting entropy of degrees of freedom outside the chosen boundary subsystem.

## The wedge is state-dependent

The entanglement wedge depends on the bulk geometry, and the bulk geometry depends on the CFT state. Therefore $\mathcal E[A]$ is not determined only by the abstract shape of $A$.

The same boundary interval in different states can have different HRT surfaces and different entanglement wedges. A vacuum interval, a thermal interval, an interval after a quench, and an interval in a state with a heavy operator insertion can probe different bulk regions.

This state dependence is not a flaw. It is precisely what allows boundary density matrices to encode dynamical geometry.

## Classical versus quantum entanglement wedges

At leading order, the boundary of the entanglement wedge is determined by the HRT surface $X_A$. At the next order, the entropy formula is corrected by bulk entanglement across the surface:

$$
S_A
=
\frac{\operatorname{Area}(X_A)}{4G_N}
+
S_{\mathrm{bulk}}(a)
+\cdots .
$$

The fully quantum version replaces the classical HRT surface by a **quantum extremal surface**. The corresponding region is the **quantum entanglement wedge**. This refinement is essential for islands, Page curves, and black-hole information.

For now, the classical picture is enough:

$$
\text{classical entanglement wedge}
=
\text{domain of dependence of the HRT homology region}.
$$

## What lives in the wedge?

At low energies and large $N$, the entanglement wedge contains ordinary bulk effective field theory degrees of freedom. Examples include:

- scalar fields dual to single-trace scalar operators;
- gauge fields dual to conserved currents;
- metric fluctuations dual to stress-tensor data;
- probe-brane fluctuations dual to flavor-sector operators;
- semiclassical matter fields contributing to bulk entropy.

But the phrase “lives in the wedge” should be interpreted in the code-subspace sense. Bulk locality is approximate. The boundary representation of a bulk operator can be highly nonlocal within $A$, and different reconstructions can be equivalent only inside a chosen set of states.

A good working dictionary is

$$
\text{bulk EFT in }\mathcal E[A]
\quad\longleftrightarrow\quad
\text{operator algebra reconstructable from }A.
$$

## Relation to modular flow

The modular Hamiltonian of $A$ is

$$
K_A=-\log\rho_A.
$$

For a generic region, $K_A$ is complicated and nonlocal. In holography, modular flow generated by $K_A$ has a bulk interpretation in the entanglement wedge. Roughly, boundary modular flow for $A$ corresponds to bulk modular flow in $\mathcal E[A]$, together with geometric terms associated with the HRT surface.

This is one of the deepest reasons the entanglement wedge, rather than the causal wedge, is the correct subregion dual. The reduced density matrix $\rho_A$ contains modular information, not just causal signals.

## Dictionary checkpoint

The subregion dictionary becomes:

| Boundary object | Bulk object |
|---|---|
| region $A$ | asymptotic boundary of a homology region |
| reduced density matrix $\rho_A$ | entanglement wedge $\mathcal E[A]$ |
| entropy $S_A$ | area of $X_A$ plus quantum corrections |
| modular flow of $\rho_A$ | bulk modular flow in $\mathcal E[A]$ |
| operator algebra on $A$ | bulk operator algebra in $\mathcal E[A]$ |
| inclusion $A\subseteq B$ | wedge nesting $\mathcal E[A]\subseteq\mathcal E[B]$ |
| mutual-information transition | connected/disconnected wedge transition |

The key upgrade from the previous page is

$$
X_A\text{ computes }S_A,
\qquad
\mathcal E[A]\text{ is the bulk region encoded by }\rho_A.
$$

## Common confusions

### “The entanglement wedge is the same as the causal wedge.”

No. The causal wedge is defined by bulk causal curves connected to $D[A]$. The entanglement wedge is defined by the HRT surface and homology. The causal wedge is typically contained in the entanglement wedge, but it is generally smaller.

### “If a bulk point is visually near $A$, it must be in $\mathcal E[A]$.”

Not necessarily. Membership in the entanglement wedge is determined by the HRT surface and the homology region, not by visual proximity in a drawing.

### “Entanglement wedge reconstruction is exact for all CFT states.”

No. The clean statement is code-subspace dependent and approximate in the semiclassical expansion. Exact nonperturbative statements are subtler.

### “A bulk operator has one unique boundary representation.”

No. A single bulk operator can have many boundary representations on different regions, as long as those regions contain the operator in their entanglement wedges. This redundancy is the quantum-error-correcting nature of holography.

### “The wedge is fixed once the boundary region is fixed.”

No. The wedge depends on the state because the HRT surface depends on the bulk geometry.

## Exercises

### Exercise 1: Entanglement wedge of a half-space

Consider the vacuum of a holographic CFT on flat space and let $A$ be the half-space $x^1>0$ on a constant-time slice. What is the qualitative shape of the entanglement wedge?

<details>
<summary><strong>Solution</strong></summary>

The RT surface for a half-space in vacuum Poincaré AdS is the vertical plane extending into the bulk from the entangling plane $x^1=0$. The homology region is the bulk half-space $x^1>0$ bounded by this vertical plane and the boundary region $A$. The entanglement wedge is the bulk domain of dependence of that half-space. Because the setup is highly symmetric, the wedge is also the AdS-Rindler wedge associated with the boundary domain of dependence of the half-space.

</details>

### Exercise 2: Why causal access is not enough

Explain why the causal wedge is a natural first guess for the bulk dual of $\rho_A$, and why it is not generally the full answer.

<details>
<summary><strong>Solution</strong></summary>

The causal wedge is natural because an observer restricted to $D[A]$ can send and receive signals only through that bulk region. Thus it captures the bulk region accessible by causal experiments using the boundary domain $D[A]$.

However, a reduced density matrix contains more than causal signaling data. It contains nonlocal entanglement and modular information. Holographic entropy and relative-entropy arguments show that $\rho_A$ controls the larger entanglement wedge bounded by the HRT surface. Hence the causal wedge is generally only a subset of the entanglement wedge.

</details>

### Exercise 3: Two intervals and mutual information

For two disjoint intervals $A_1$ and $A_2$ in a holographic CFT$_2$ vacuum, explain why the leading large-$N$ mutual information can vanish when the intervals are far apart.

<details>
<summary><strong>Solution</strong></summary>

At leading large $N$, entropies are computed by RT geodesic lengths. For far-separated intervals, the disconnected surface for $A_1\cup A_2$ dominates:

$$
S_{A_1\cup A_2}
=
S_{A_1}+S_{A_2}
+O(N^0).
$$

Therefore

$$
I(A_1:A_2)
=
S_{A_1}+S_{A_2}-S_{A_1\cup A_2}
=O(N^0).
$$

The entanglement wedge is disconnected at leading classical order. When the intervals become close enough, a connected surface can dominate, and the mutual information becomes order $N^2$.

</details>

### Exercise 4: Wedge nesting

Suppose $A\subseteq B$. Why is $\mathcal E[A]\subseteq\mathcal E[B]$ the expected holographic counterpart of ordinary quantum-information monotonicity?

<details>
<summary><strong>Solution</strong></summary>

If $A\subseteq B$, then the boundary region $B$ contains all degrees of freedom in $A$ plus more. Therefore $\rho_B$ should have at least as much reconstructive power as $\rho_A$. In the bulk, this means that any operator reconstructable from $A$ should also be reconstructable from $B$. The geometric expression of this statement is

$$
\mathcal E[A]\subseteq\mathcal E[B].
$$

This property is entanglement wedge nesting. It is closely related to relative entropy monotonicity and to the maximin proof of covariant holographic entropy inequalities.

</details>

### Exercise 5: Complementary wedges in a pure state

In a pure boundary state, why do $A$ and $\bar A$ often share the same HRT surface at leading order?

<details>
<summary><strong>Solution</strong></summary>

For a pure state,

$$
S_A=S_{\bar A}.
$$

At leading holographic order, these entropies are computed by areas. If the same extremal surface is homologous to $A$ on one side and to $\bar A$ on the other, then it gives equal areas for both entropies. The corresponding entanglement wedges are complementary bulk domains separated by the shared HRT surface. This simple relation can be modified in mixed states or when horizon components enter the homology condition.

</details>

## Further reading

- M. Headrick, V. E. Hubeny, A. Lawrence, and M. Rangamani, [Causality & Holographic Entanglement Entropy](https://arxiv.org/abs/1408.6300).
- D. L. Jafferis, A. Lewkowycz, J. Maldacena, and S. J. Suh, [Relative Entropy Equals Bulk Relative Entropy](https://arxiv.org/abs/1512.06431).
- X. Dong, D. Harlow, and A. C. Wall, [Reconstruction of Bulk Operators within the Entanglement Wedge in Gauge-Gravity Duality](https://arxiv.org/abs/1601.05416).
- A. Almheiri, X. Dong, and D. Harlow, [Bulk Locality and Quantum Error Correction in AdS/CFT](https://arxiv.org/abs/1411.7041).
- B. Czech, L. Lamprou, S. McCandlish, and J. Sully, [Integral Geometry and Holography](https://arxiv.org/abs/1505.05515).
