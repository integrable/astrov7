---
title: "Kramers–Wannier Duality in the Ising Model"
description: "A model calculation deriving Kramers–Wannier duality in the two-dimensional Ising model, including high- and low-temperature expansions, the self-dual point, order-disorder variables, and the duality-defect viewpoint."
sidebar:
  label: "Kramers–Wannier Duality in Ising"
  order: 14
level: Graduate
status: "Polished draft"
source: "Kramers–Wannier; Polyakov Chs. 1, 3, and 4; Coleman symmetry lectures; modern defect treatments of Ising duality."
topics:
  - Kramers–Wannier duality
  - Ising model
  - order-disorder duality
  - finite symmetry gauging
  - duality defect
  - non-invertible symmetry
canonicalTopics:
  - kramers-wannier-duality
  - ising-model
  - order-disorder-operator
  - finite-symmetry-gauging
  - model-calculation
researchStatus:
  established:
    - "Kramers–Wannier duality maps the two-dimensional Ising model at coupling K to a dual Ising model at coupling K* with sinh(2K)sinh(2K*)=1."
    - "At criticality, the Ising duality line becomes a topological defect whose fusion is non-invertible: N squared equals the sum of the identity and spin-flip symmetry defects."
  active:
    - "Modern work generalizes the Ising duality-defect story to non-invertible symmetries, categorical symmetries, generalized gauging, lattice defects, and higher-dimensional analogues."
---

## Summary

Kramers–Wannier duality is the prototype of order–disorder duality. In the two-dimensional square-lattice Ising model, it maps the high-temperature expansion of one model to the low-temperature expansion of another model on the dual lattice.

The model is

$$
Z(K)=\sum_{\{\sigma_i=\pm1\}}
\exp\left(K\sum_{\langle ij\rangle}\sigma_i\sigma_j\right),
$$

where

$$
K=\beta J.
$$

The dual coupling $K^*$ is defined by

$$
\sinh(2K)\sinh(2K^*)=1.
$$

The self-dual point satisfies

$$
\sinh(2K_c)=1,
$$

so

$$
K_c=\frac12\log(1+\sqrt2).
$$

For the square-lattice Ising model, this self-dual point is the critical point.

<figure class="doc-figure" style="--figure-width: 45rem;">

![The square-lattice Ising model maps under Kramers–Wannier duality to a dual Ising model with domain-wall loops exchanged with high-temperature expansion loops.](/figures/symmetry-anomalies-topology/kramers-wannier-ising-duality.svg)

<figcaption>

Kramers–Wannier duality exchanges the high-temperature loop expansion of the Ising model with the low-temperature domain-wall expansion of the dual Ising model. At criticality the duality can be promoted to a topological defect, and in the Ising CFT its fusion is non-invertible.

</figcaption>
</figure>

The modern QFT lesson is bigger than the lattice calculation. Kramers–Wannier duality is a finite-symmetry gauging operation. At the self-dual point, it becomes a duality defect. In the critical Ising CFT this defect obeys

$$
\mathcal N^2=1+\eta,
$$

where $\eta$ is the $\mathbb Z_2$ spin-flip symmetry line. This is the simplest non-invertible symmetry relation.

## Prerequisites

You should know the pages on finite-symmetry gauging, orbifolds, Kramers–Wannier duality in low-dimensional symmetry technology, and non-invertible duality defects. This page is the model calculation version: the goal is to see the duality emerge from sums over spin configurations.

We use the classical two-dimensional square-lattice Ising model first. Then we translate to the one-dimensional quantum transverse-field Ising chain, where the same duality appears as a map between Pauli operators.

## The lattice model

Put Ising spins

$$
\sigma_i=\pm1
$$

on the vertices of a square lattice. The partition function is

$$
Z(K)=\sum_{\{\sigma\}}\prod_{\langle ij\rangle}e^{K\sigma_i\sigma_j}.
$$

The model has a global spin-flip symmetry

$$
\sigma_i\mapsto-\sigma_i.
$$

Low temperature means $K\gg1$. Neighboring spins prefer to align. The natural excitations are domain walls separating regions of opposite spin.

High temperature means $K\ll1$. The natural expansion is in closed graphs of activated bonds.

Kramers–Wannier duality says that these two expansions are the same expansion written on dual lattices, with dual couplings related by

$$
e^{-2K^*}=\tanh K.
$$

This equation is equivalent to

$$
\sinh(2K)\sinh(2K^*)=1.
$$

## High-temperature expansion

Use the identity

$$
e^{K\sigma_i\sigma_j}
=
\cosh K\left(1+\sigma_i\sigma_j\tanh K\right).
$$

Then

$$
Z(K)
=
(\cosh K)^{N_b}
\sum_{\{\sigma\}}
\prod_{\langle ij\rangle}
\left(1+x\sigma_i\sigma_j\right),
\qquad
x=\tanh K,
$$

where $N_b$ is the number of bonds.

Expanding the product means choosing a subset $\Gamma$ of bonds. A chosen bond contributes $\sigma_i\sigma_j$. For a given subset $\Gamma$, the spin sum factorizes by vertices:

$$
\sum_{\{\sigma\}}\prod_{\langle ij\rangle\in\Gamma}\sigma_i\sigma_j.
$$

At each vertex, the spin $\sigma_i$ appears with exponent equal to the number of chosen bonds ending on that vertex. The sum over $\sigma_i=\pm1$ vanishes unless this exponent is even. Therefore only even subgraphs contribute.

On the square lattice, an even subgraph is a union of closed loops. Thus

$$
Z(K)
=
2^{N_s}(\cosh K)^{N_b}
\sum_{\Gamma\,{\rm closed}} x^{|\Gamma|},
$$

where $N_s$ is the number of sites and $|\Gamma|$ is the number of occupied bonds.

This is the high-temperature loop expansion.

## Low-temperature expansion

At low temperature, choose a reference ground state, say all spins up. A configuration differs from it by flipped domains. The boundaries of those domains are closed loops on the dual lattice.

A bond $\langle ij\rangle$ is frustrated if

$$
\sigma_i\sigma_j=-1.
$$

Relative to the aligned bond weight $e^K$, a frustrated bond has weight $e^{-K}$, so each domain-wall segment costs

$$
e^{-2K}.
$$

Thus the partition function can be written schematically as

$$
Z(K)
=
2e^{KN_b}
\sum_{\Gamma^*\,{\rm closed}} e^{-2K|\Gamma^*|},
$$

where the factor $2$ counts the two uniform ground states on a connected lattice without boundary complications.

The domain walls $\Gamma^*$ live on the dual lattice. Comparing with the high-temperature expansion, we identify

$$
x=\tanh K=e^{-2K^*}.
$$

Thus the high-temperature expansion at $K$ equals, up to a known prefactor, the low-temperature expansion at $K^*$ on the dual lattice.

:::note[Boundary and topology caveat]
On a finite torus, the exact duality includes sums over winding sectors and spin structures. On an infinite plane, or with simple boundary conditions, the loop comparison captures the essential relation. Boundary conditions are not optional in the exact finite-volume statement.
:::

## The self-dual point

The duality relation is

$$
e^{-2K^*}=\tanh K.
$$

At the self-dual point,

$$
K^*=K.
$$

Therefore

$$
e^{-2K}=\tanh K.
$$

Solving gives

$$
\sinh(2K_c)=1,
$$

so

$$
K_c=\frac12\log(1+\sqrt2).
$$

For the square-lattice Ising model, the critical point is known to occur at this self-dual point. Duality alone identifies a candidate transition point; additional input is needed to prove that there is a unique transition and that it is exactly there.

## Order and disorder variables

The Ising spin $\sigma_i$ is the order variable. It is odd under the global $\mathbb Z_2$ symmetry. In the ordered phase, it can have a nonzero expectation value after choosing a vacuum.

The disorder variable $\mu_{p}$ lives on the dual lattice. Informally, inserting two disorder operators forces a branch cut between them across which Ising bonds are flipped. Equivalently, it inserts endpoints of a dual disorder line.

Kramers–Wannier duality exchanges

$$
\sigma \quad\longleftrightarrow\quad \mu.
$$

It maps the ordered phase of one description to the disordered phase of the dual description. This is why it is called order–disorder duality.

In the critical Ising CFT, both $\sigma$ and $\mu$ have scaling dimension

$$
\Delta_\sigma=\Delta_\mu=\frac18.
$$

The equality is a consequence of the self-dual critical theory, not a property of generic massive points away from criticality.

## Quantum transverse-field Ising chain

The same duality appears in the one-dimensional quantum Ising chain,

$$
H=-J\sum_i \sigma_i^z\sigma_{i+1}^z-h\sum_i\sigma_i^x.
$$

Define dual Pauli variables on links $i+\frac12$ by

$$
\mu_{i+1/2}^x=\sigma_i^z\sigma_{i+1}^z,
$$

and

$$
\mu_{i-1/2}^z\mu_{i+1/2}^z=\sigma_i^x.
$$

One explicit choice is

$$
\mu_{i+1/2}^z=\prod_{j\le i}\sigma_j^x.
$$

This is nonlocal in the original variables. In terms of the dual variables,

$$
H=-J\sum_i\mu_{i+1/2}^x-h\sum_i\mu_{i-1/2}^z\mu_{i+1/2}^z.
$$

This has the same form as the original Hamiltonian with

$$
J\longleftrightarrow h.
$$

The self-dual point is therefore

$$
J=h,
$$

which is the critical point of the transverse-field Ising chain.

## Boundary sectors and the global Z₂ symmetry

The duality map in the quantum chain is not quite an isomorphism of Hilbert spaces with fixed boundary conditions. The definition

$$
\mu_{i+1/2}^z=\prod_{j\le i}\sigma_j^x
$$

depends on a choice of starting point and boundary. On a circle, it relates periodic and twisted sectors and keeps track of the global spin-flip charge

$$
\eta=\prod_i\sigma_i^x.
$$

This is the finite-volume shadow of the orbifold statement: gauging the $\mathbb Z_2$ symmetry introduces twisted sectors and projects onto invariant states. Kramers–Wannier duality is not merely a local change of variables; it is tied to summing over or exchanging global sectors.

This is why modern treatments describe Kramers–Wannier duality as a gauging interface or duality defect.

## Duality defect and non-invertible fusion

At the critical point, the duality operation can be represented by a topological line defect $\mathcal N$. Crossing this defect maps local fields to their duals. In particular, it exchanges order and disorder fields,

$$
\sigma\leftrightarrow \mu,
$$

up to convention-dependent normalizations and branch-cut choices.

The Ising model also has the ordinary $\mathbb Z_2$ spin-flip symmetry line $\eta$. It acts as

$$
\eta:\sigma\mapsto-\sigma,
$$

while leaving the energy operator invariant.

The duality defect obeys the fusion rule

$$
\mathcal N\times\mathcal N=1+\eta.
$$

This is the hallmark of non-invertibility. If $\mathcal N$ had an inverse, then $\mathcal N\times\mathcal N$ would be a single defect. Instead, fusing two duality defects gives a direct sum of two sectors: the identity sector and the spin-flip sector.

The quantum dimension follows from the fusion rule:

$$
d_{\mathcal N}^2=d_1+d_\eta=2,
$$

so

$$
d_{\mathcal N}=\sqrt2.
$$

## Relation to finite-symmetry gauging

For a theory with a finite group $G$, gauging means summing over flat $G$ backgrounds and projecting onto $G$-invariant states, with twisted sectors included. For the Ising model, $G=\mathbb Z_2$.

Kramers–Wannier duality can be understood as the statement that the Ising model is related to its $\mathbb Z_2$ gauged version. At the self-dual point, the theory is equivalent to its gauged version. The interface that implements gauging is the duality defect $\mathcal N$.

This is the conceptual bridge:

$$
\text{finite-symmetry gauging}
\quad\longrightarrow\quad
\text{duality interface}
\quad\longrightarrow\quad
\text{non-invertible defect at self-duality}.
$$

The lattice high/low-temperature derivation is the computational ancestor of this modern statement.

## What the calculation teaches

Kramers–Wannier duality teaches several lessons that recur throughout QFT.

First, the same theory may have two descriptions with different local variables. The dual spin $\mu$ is nonlocal in the original spin variables.

Second, global sectors matter. Exact finite-volume duality requires careful treatment of boundary conditions, twists, and symmetry projection.

Third, gauging a finite symmetry can produce a dual theory rather than merely removing degrees of freedom.

Fourth, a duality can become a topological defect at a fixed point. If that defect fuses non-invertibly, it is a genuine non-invertible symmetry.

## Common pitfalls

**“Duality is just a change of variables.”** Locally it may look like one, but globally it changes sectors and boundary conditions. On a torus, this is unavoidable.

**“Self-dual automatically means critical.”** Self-duality identifies a candidate point. Showing it is the critical point requires additional input, such as uniqueness of the phase transition.

**“The disorder operator is another local spin.”** It is local in the dual variables but nonlocal in the original variables. It creates or terminates a disorder line.

**“The duality defect is invertible because duality sounds reversible.”** At the critical Ising point, the topological duality defect is non-invertible: $\mathcal N^2=1+\eta$.

**“Boundary conditions are minor details.”** Boundary sectors are part of the exact duality. Ignoring them gives correct intuition but incomplete equations.

## Relations to other pages

This page is the calculation-library companion to the low-dimensional Kramers–Wannier Duality page, the finite-symmetry gauging page, and the non-invertible duality-defect pages.

It also prepares the WZW anomaly-inflow calculation by showing how two-dimensional QFT often teaches general lessons through defects, sector sums, and dual descriptions.

## Research status

The two-dimensional Ising duality calculation is classic and settled. The modern reinterpretation in terms of finite gauging, topological defects, and non-invertible symmetry is now standard in current QFT language.

Active directions include higher-dimensional Kramers–Wannier-type dualities, generalized gauging, duality defects in lattice models, categorical symmetry, subsystem-symmetry analogues, and non-invertible symmetries in gauge theories and statistical systems beyond the Ising universality class.

## Exercises

### Exercise 1: High-temperature even graphs

Show that the high-temperature expansion of the Ising model receives contributions only from subgraphs with an even number of occupied bonds at every vertex.

<details><summary><strong>Solution</strong></summary>

Expand

$$
\prod_{\langle ij\rangle}(1+x\sigma_i\sigma_j).
$$

A chosen subgraph $\Gamma$ contributes

$$
\prod_{\langle ij\rangle\in\Gamma}\sigma_i\sigma_j.
$$

At a vertex $i$, the spin appears with power equal to the degree of $i$ in $\Gamma$. Since

$$
\sum_{\sigma_i=\pm1}\sigma_i^m
$$

vanishes for odd $m$ and equals $2$ for even $m$, every vertex must have even degree. Hence the contributing subgraphs are closed loops.

</details>

### Exercise 2: Self-dual coupling

Starting from

$$
e^{-2K^*}=\tanh K,
$$

derive

$$
K_c=\frac12\log(1+\sqrt2).
$$

<details><summary><strong>Solution</strong></summary>

At self-duality $K^*=K$, so

$$
e^{-2K}=\tanh K=\frac{e^{2K}-1}{e^{2K}+1}.
$$

Let $y=e^{2K}$. Then

$$
\frac1y=\frac{y-1}{y+1}.
$$

Thus

$$
y+1=y^2-y,
$$

or

$$
y^2-2y-1=0.
$$

The positive solution is

$$
y=1+\sqrt2.
$$

Therefore

$$
K_c=\frac12\log(1+\sqrt2).
$$

</details>

### Exercise 3: Quantum-chain duality

Use

$$
\mu_{i+1/2}^x=\sigma_i^z\sigma_{i+1}^z,
\qquad
\mu_{i-1/2}^z\mu_{i+1/2}^z=\sigma_i^x
$$

to rewrite

$$
H=-J\sum_i \sigma_i^z\sigma_{i+1}^z-h\sum_i\sigma_i^x.
$$

<details><summary><strong>Solution</strong></summary>

Substitute the definitions directly:

$$
\sigma_i^z\sigma_{i+1}^z=\mu_{i+1/2}^x,
$$

and

$$
\sigma_i^x=\mu_{i-1/2}^z\mu_{i+1/2}^z.
$$

Therefore

$$
H=-J\sum_i\mu_{i+1/2}^x-h\sum_i\mu_{i-1/2}^z\mu_{i+1/2}^z.
$$

This has the same form as the original Hamiltonian with $J$ and $h$ exchanged, after relabeling the dual lattice sites.

</details>

### Exercise 4: Quantum dimension

Given

$$
\mathcal N^2=1+\eta,
\qquad
\eta^2=1,
$$

and assuming quantum dimensions are additive under direct sums and multiplicative under fusion, find $d_{\mathcal N}$.

<details><summary><strong>Solution</strong></summary>

The identity and $\eta$ are invertible defects, so

$$
d_1=d_\eta=1.
$$

The fusion rule gives

$$
d_{\mathcal N}^2=d_1+d_\eta=2.
$$

Thus

$$
d_{\mathcal N}=\sqrt2.
$$

</details>

## References

- H. A. Kramers and G. H. Wannier, “Statistics of the Two-Dimensional Ferromagnet. Part I.”
- A. M. Polyakov, *Gauge Fields and Strings*, especially the early chapters on statistical mechanics, Ising models, strong-coupling expansions, and instantons.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for symmetry and current-algebra intuition that helps organize the continuum limit.
- Paul Ginsparg, “Applied Conformal Field Theory,” for the critical Ising CFT and two-dimensional CFT background.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” for the modern generalized-symmetry viewpoint.
- Recent reviews on non-invertible symmetries and lattice topological defects for the defect fusion rule $\mathcal N^2=1+\eta$.

## Version history

- **2026-06-23:** Initial polished model-calculation page deriving Kramers–Wannier duality, the self-dual point, the transverse-field Ising duality map, and the non-invertible duality-defect fusion rule.
