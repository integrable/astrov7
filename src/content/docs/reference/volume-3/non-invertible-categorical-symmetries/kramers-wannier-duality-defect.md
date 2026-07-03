---
title: "Kramers–Wannier Duality Defect"
description: "Explains the Kramers–Wannier duality defect in the Ising model as the canonical example of a non-invertible topological symmetry defect."
sidebar:
  label: "Kramers–Wannier Duality Defect"
  order: 5
level: Advanced
status: "Polished draft"
source: "Kramers–Wannier; Fröhlich–Fuchs–Runkel–Schweigert; Shao TASI lectures; Ising CFT and lattice-defect references."
topics:
  - Kramers–Wannier duality
  - Ising model
  - duality defect
  - non-invertible symmetry
  - order-disorder duality
  - Tambara-Yamagami category
canonicalTopics:
  - kramers-wannier-duality
  - ising-duality-defect
  - order-disorder-defect
  - ising-noninvertible-symmetry
  - tambara-yamagami-example
researchStatus:
  established:
    - "The Kramers–Wannier duality of the Ising model is the canonical pedagogical example of a non-invertible self-duality defect."
    - 'At the critical point, the Ising duality defect is topological and obeys the fusion rule of the Ising category, including the non-invertible rule $\mathcal N^2=1+\eta$.'
  active:
    - "Precise lattice realizations, boundary conditions, translation mixing, and generalizations to broader quantum chains and higher-dimensional constructions remain active research topics."
---

## Summary

The Kramers–Wannier duality defect is the best first example of non-invertible symmetry. It comes from the order-disorder duality of the Ising model.

In the two-dimensional classical Ising model, Kramers–Wannier duality relates the low-temperature expansion of one Ising model to the high-temperature expansion of a dual Ising model. On the square lattice, the dual coupling $K^*$ satisfies

$$
\sinh(2K)\sinh(2K^*)=1.
$$

At the self-dual point,

$$
K=K^*,
\qquad
\sinh(2K_c)=1,
$$

which gives

$$
K_c=\frac12\log(1+\sqrt2).
$$

In the continuum critical Ising CFT, this self-duality becomes a topological line defect $\mathcal N$. It is not invertible. Its fusion rule is

$$
\mathcal N\times\mathcal N=1+\eta,
$$

where $\eta$ is the ordinary $\mathbb Z_2$ spin-flip defect. This one equation is the baby model of non-invertible symmetry.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A schematic showing the Kramers-Wannier duality defect converting order variables to disorder variables and obeying the non-invertible fusion rule N squared equals one plus eta.](/figures/symmetry-anomalies-topology/kramers-wannier-duality-defect.svg)

<figcaption>

The Kramers–Wannier defect $\mathcal N$ implements order-disorder duality. At the critical point it is topological, but not invertible: two such defects fuse to the direct sum of the transparent defect $1$ and the spin-flip defect $\eta$.

</figcaption>
</figure>

The Ising example is small enough to compute and rich enough to show nearly every important idea: order variables, disorder variables, gauging, self-duality, topological lines, direct-sum fusion, and non-invertible Ward identities.

## Prerequisites

You should know [Duality Defects](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/duality-defects/), [Fusion Rules](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/fusion-rules/), and the ordinary $\mathbb Z_2$ symmetry of the Ising model. It helps to know the transverse-field Ising chain, but the page introduces the needed formulas.

This page uses three related pictures:

| Picture | Object | Role |
|---|---|---|
| Classical 2D lattice model | Square-lattice Ising model | Original Kramers–Wannier relation between $K$ and $K^*$. |
| Quantum chain | Transverse-field Ising model | Dual variables and self-dual Hamiltonian. |
| Continuum CFT | Critical Ising CFT | Topological defect line with non-invertible fusion. |

The pictures are not identical. Boundary conditions, sectors, and lattice translations can matter. The continuum CFT picture is the cleanest place to state the topological fusion rule.

## Core idea

The Ising model has an ordinary $\mathbb Z_2$ spin-flip symmetry,

$$
\sigma_i\mapsto-\sigma_i.
$$

It also has a duality that exchanges order and disorder descriptions. In one description, the low-temperature phase has ordered spins. In the dual description, the high-temperature expansion becomes an ordered expansion of dual variables.

Kramers–Wannier duality is not just a symmetry acting on each spin independently. It is nonlocal in the original variables. It turns local order variables into disorder variables and maps strong coupling to weak coupling.

At the critical point, the theory is self-dual. The duality can then be represented by a topological line $\mathcal N$ in the critical Ising CFT. Because the duality operation forgets a $\mathbb Z_2$ sector, $\mathcal N$ has no inverse. Instead,

$$
\mathcal N^2=1+\eta.
$$

This is the non-invertible symmetry.

## Classical Ising duality

The square-lattice Ising partition function is

$$
Z(K)=\sum_{\{\sigma_i=\pm1\}}
\exp\left(K\sum_{\langle ij\rangle}\sigma_i\sigma_j\right),
$$

where $K=J/T$ in units with Boltzmann’s constant set to one.

The high-temperature expansion writes each Boltzmann factor as

$$
e^{K\sigma_i\sigma_j}
=\cosh K\left(1+v\sigma_i\sigma_j\right),
\qquad
v=\tanh K.
$$

Summing over spins kills configurations with an odd number of occupied bonds incident at a site. The surviving configurations are closed loops on the original lattice.

The low-temperature expansion instead counts domain walls separating regions of $\sigma=+1$ and $\sigma=-1$. These domain walls live naturally on the dual lattice. Matching the loop weights gives the duality relation

$$
e^{-2K^*}=\tanh K.
$$

Equivalently,

$$
\sinh(2K)\sinh(2K^*)=1.
$$

At a self-dual critical point $K=K^*$, this gives

$$
\sinh(2K_c)=1.
$$

Kramers and Wannier used this, plus the assumption of a unique transition, to locate the critical temperature before the exact solution was known.

:::note[Source note]
The lattice duality relation depends on normalization and boundary conditions. The clean thermodynamic statement is about the free energy density, with boundary-sector terms becoming subleading in infinite volume. The defect statement keeps track of the sector information rather than throwing it away.
:::

## Quantum Ising chain version

The one-dimensional transverse-field Ising chain is

$$
H=-J\sum_i Z_iZ_{i+1}-h\sum_i X_i,
$$

where $X_i$ and $Z_i$ are Pauli matrices. Define dual variables on links by

$$
\mu^x_{i+1/2}=Z_iZ_{i+1},
\qquad
\mu^z_{i+1/2}=\prod_{j\le i}X_j.
$$

Then

$$
\mu^z_{i-1/2}\mu^z_{i+1/2}=X_i.
$$

The Hamiltonian becomes, schematically,

$$
H=-J\sum_i\mu^x_{i+1/2}-h\sum_i\mu^z_{i-1/2}\mu^z_{i+1/2}.
$$

The duality exchanges the coupling of the nearest-neighbor spin term with the transverse-field term:

$$
J\longleftrightarrow h.
$$

At $J=h$, the chain is self-dual. In the scaling limit this is the critical Ising CFT.

The transformation is nonlocal because $\mu^z$ is a string of $X$ operators. It also changes boundary conditions and the action of the global spin-flip symmetry. Those boundary and sector subtleties are the lattice shadow of non-invertibility.

## Order and disorder operators

The spin operator $\sigma$ is an order operator. It detects whether the $\mathbb Z_2$ spin-flip symmetry is spontaneously broken. The disorder operator $\mu$ creates a branch cut or a twist for the spin variables. On the lattice, inserting a disorder operator changes the sign of couplings along a path ending at the insertion.

Kramers–Wannier duality exchanges order and disorder:

$$
\sigma\quad\longleftrightarrow\quad \mu.
$$

This is already more subtle than an ordinary symmetry action. The disorder operator is not a simple local polynomial in the original spin variables; it is defined by modifying boundary conditions along a defect line. The duality defect is precisely the object that makes this exchange local in the enlarged defect language.

A useful mental picture is:

$$
\text{cross }\mathcal N
\quad\Rightarrow\quad
\text{order variables become disorder variables.}
$$

At criticality, the distinction between order and disorder variables becomes part of a topological defect network.

## Critical Ising CFT defects

The critical Ising CFT has three simple topological defects often labeled by the same symbols as the three primary fields:

$$
1,
\qquad
\eta,
\qquad
\mathcal N.
$$

Here $1$ is the transparent defect, $\eta$ is the invertible spin-flip defect, and $\mathcal N$ is the non-invertible Kramers–Wannier defect.

Their fusion rules are

$$
\eta\times\eta=1,
\qquad
\eta\times\mathcal N=\mathcal N,
\qquad
\mathcal N\times\mathcal N=1+\eta.
$$

These are the Ising fusion rules. The defect $\eta$ behaves like a $\mathbb Z_2$ group element. The defect $\mathcal N$ does not. Its square is a direct sum of two channels.

The quantum dimension follows immediately. Since $d_1=d_\eta=1$,

$$
d_\mathcal N^2=d_1+d_\eta=2,
$$

so

$$
d_\mathcal N=\sqrt2.
$$

An invertible simple defect has quantum dimension $1$. The value $\sqrt2$ diagnoses non-invertibility.

## Why the square is one plus spin-flip

The rule

$$
\mathcal N^2=1+\eta
$$

has a physical interpretation. Kramers–Wannier duality can be thought of as gauging the ordinary $\mathbb Z_2$ symmetry, followed by an identification of the gauged theory with the original theory at the self-dual point.

Doing this twice does not simply undo the operation. Instead, the two operations leave behind a sum over the possible $\mathbb Z_2$ symmetry sectors. In defect language, those sectors are represented by the transparent defect and the spin-flip defect:

$$
\bigoplus_{a\in\mathbb Z_2}U_a=1+\eta.
$$

This is the simplest instance of the general half-space gauging formula

$$
\mathcal N\times\mathcal N^\dagger
=\bigoplus_{a\in A}U_a.
$$

For the Ising model, $A=\mathbb Z_2$ and $\mathcal N^\dagger=\mathcal N$.

## Defect action on local fields

In the critical Ising CFT, the familiar local primary fields are

$$
1,
\qquad
\varepsilon,
\qquad
\sigma,
$$

where $\varepsilon$ is the energy operator and $\sigma$ is the spin operator. In the diagonal CFT, topological defects act diagonally on bulk primaries in a basis determined by the modular $S$-matrix. With common conventions, the spin-flip defect $\eta$ acts as

$$
\eta: \sigma\mapsto-\sigma,
\qquad
\eta: \varepsilon\mapsto\varepsilon.
$$

The Kramers–Wannier defect $\mathcal N$ acts more subtly. It is not an ordinary transformation of all local fields. It exchanges order and disorder sectors, and in the purely diagonal local CFT description its action on bulk primaries is best understood through defect crossing, endpoints, and defect-local operators rather than as a naive field map.

In rational CFT language, one can describe the action of topological defects on bulk sectors using modular data. In lattice language, one sees the same subtlety as the nonlocal string definition of disorder variables and the dependence on boundary conditions.

:::caution[Do not oversimplify the action]
It is tempting to say “$\mathcal N$ sends $\sigma$ to $\mu$” and stop there. That is a useful slogan in the lattice order-disorder picture, but the exact CFT defect action also involves sectors and defect endpoints. The slogan is pedagogically good; the defect network is the precise object.
:::

## Ward identities without a group

The Kramers–Wannier defect gives Ward identities even though it is not invertible. Insert a closed $\mathcal N$ loop in a correlator. Because $\mathcal N$ is topological, the loop can be deformed. If it crosses operators or other defects, crossing rules rewrite the correlator.

For an ordinary $\mathbb Z_2$ symmetry defect $\eta$, a closed loop gives a selection rule: an odd number of spin fields has vanishing correlator in a symmetric vacuum. For $\mathcal N$, the rule is not just a charge-parity condition. Moving $\mathcal N$ through a correlator can convert order insertions to disorder insertions, produce defect endpoints, or project onto sectors compatible with the duality.

This is the first concrete example of a non-invertible Ward identity:

$$
\text{topological deformation still constrains correlators, even without an inverse.}
$$

The constraint is geometric rather than group-theoretic.

## Boundary conditions

Duality defects act naturally on boundary conditions. In the Ising model, the standard conformal boundary conditions are often described as fixed $+$, fixed $-$, and free. Kramers–Wannier duality exchanges fixed and free types in a controlled way, with sums over fixed sectors appearing because of the same non-invertible fusion.

Schematic statements look like

$$
\mathcal N\cdot \text{fixed} \sim \text{free},
\qquad
\mathcal N\cdot \text{free} \sim \text{fixed }+\text{ fixed }-.
$$

The exact normalization and labeling depend on the CFT convention. The important lesson is that non-invertible defects act on boundary conditions by sums, not always by permutations.

This is the boundary version of

$$
\mathcal N^2=1+\eta.
$$

An ordinary invertible symmetry permutes boundary conditions. A non-invertible duality defect can send one boundary condition to a direct sum of boundary conditions.

## Relation to Tambara–Yamagami categories

The Ising fusion rule is the smallest example of a broader pattern. For a finite Abelian group $A$, a Tambara–Yamagami-type fusion category contains invertible objects labeled by $a\in A$ and one non-invertible object $\mathcal N$ obeying

$$
a\times b=ab,
\qquad
 a\times\mathcal N=\mathcal N,
\qquad
\mathcal N\times\mathcal N=\bigoplus_{a\in A}a.
$$

For $A=\mathbb Z_2$, this is exactly

$$
\eta^2=1,
\qquad
\eta\mathcal N=\mathcal N,
\qquad
\mathcal N^2=1+\eta.
$$

The Ising example is therefore not an isolated miracle. It is the minimal member of a general family of duality-like non-invertible symmetries.

## What is topological, and where

The Kramers–Wannier transformation exists away from criticality as a duality between different couplings. But the duality defect is topological as a defect of a single theory only at the self-dual critical point, or in a topological subsector where the required deformation invariance holds.

Away from criticality, moving the interface generally changes physics because the two sides correspond to different couplings or phases. At criticality, scale invariance and self-duality make the defect topological in the CFT.

This is an important distinction:

$$
\text{duality of partition functions away from criticality}
\ne
\text{topological symmetry defect of one QFT}.
$$

The latter is stronger and is the object used in non-invertible symmetry.

## Lattice subtleties

On a finite periodic chain, Kramers–Wannier duality changes boundary conditions and may mix with translation. It may not be represented by a simple operator acting within a single Hilbert space sector. This is not a contradiction. It is precisely why the continuum defect language is helpful.

The lattice teaches three lessons.

First, order-disorder duality is nonlocal in the original spin variables.

Second, sector and boundary data are not optional; they are part of the duality.

Third, the clean non-invertible fusion rule emerges most naturally after passing to the self-dual critical theory and organizing all sectors correctly.

So the right statement is not that every lattice Kramers–Wannier map is literally the same as the CFT topological line. The right statement is that the CFT line is the universal infrared form of the self-duality defect, once sector subtleties are handled correctly.

## Common pitfalls

**Thinking Kramers–Wannier is an ordinary $\mathbb Z_2$ symmetry.** The ordinary $\mathbb Z_2$ symmetry is spin flip $\eta$. The Kramers–Wannier defect is $\mathcal N$, and it is non-invertible.

**Saying $\mathcal N^2=1$.** The correct Ising fusion rule is $\mathcal N^2=1+\eta$, not $1$.

**Ignoring disorder operators.** The duality exchanges order and disorder descriptions. If disorder insertions are omitted, the duality looks mysterious or ill-defined.

**Forgetting boundary conditions.** On finite systems, duality can change boundary sectors. This is not a small correction; it is the origin of the non-invertible structure.

**Confusing lattice duality with topological CFT defect.** The lattice duality can relate different couplings. The topological defect is the critical self-duality object.

**Treating the fusion sum as probability.** The $1+\eta$ is a direct sum of topological channels, not a random outcome.

## Relations to other pages

[Duality Defects](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/duality-defects/) gives the general language. [Fusion Rules](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/fusion-rules/) explains how to read $\mathcal N^2=1+\eta$. [Gauging and Orbifolding](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/gauging-and-orbifolding/) will explain the construction of $\mathcal N$ from gauging $\mathbb Z_2$. [Tambara–Yamagami Preview](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/tambara-yamagami-preview/) will generalize the Ising fusion rule to finite Abelian groups.

This page also connects to [Twist Operators](/symmetry-anomalies-topology/defects-extended-operators/twist-operators/), [Generalized Symmetry Breaking](/symmetry-anomalies-topology/higher-form-generalized-symmetries/generalized-symmetry-breaking/), and the CFT pages on the Ising model and rational conformal field theory.

## Research status

The Ising Kramers–Wannier defect is established and pedagogically central. Its continuum description as a non-invertible topological defect is a standard example in modern lectures on generalized symmetry.

Active work concerns lattice realizations, the precise relation between microscopic Kramers–Wannier operators and infrared topological lines, generalizations to Potts, clock, anyonic, Hopf-algebraic, and higher-dimensional systems, and anomaly/fractionalization structures of self-duality defects.

## Exercises

### Exercise 1: Self-dual Ising coupling

Starting from

$$
\sinh(2K_c)=1,
$$

show that

$$
K_c=\frac12\log(1+\sqrt2).
$$

<details><summary><strong>Solution</strong></summary>

Let $x=e^{2K_c}$. Then

$$
\sinh(2K_c)=\frac{x-x^{-1}}2=1.
$$

Multiplying by $2x$ gives

$$
x^2-1=2x,
$$

so

$$
x^2-2x-1=0.
$$

The positive solution is

$$
x=1+\sqrt2.
$$

Therefore

$$
2K_c=\log(1+\sqrt2),
\qquad
K_c=\frac12\log(1+\sqrt2).
$$

</details>

### Exercise 2: Quantum dimension

Use

$$
\mathcal N^2=1+\eta,
\qquad
\eta^2=1,
$$

and $d_1=d_\eta=1$ to compute $d_\mathcal N$.

<details><summary><strong>Solution</strong></summary>

Quantum dimensions multiply under fusion and add under direct sums. Thus

$$
d_\mathcal N^2=d_1+d_\eta=1+1=2.
$$

Taking the positive solution in a unitary theory gives

$$
d_\mathcal N=\sqrt2.
$$

Because this is not $1$, $\mathcal N$ is non-invertible.

</details>

### Exercise 3: Dual variables in the Ising chain

Given

$$
\mu^x_{i+1/2}=Z_iZ_{i+1},
\qquad
\mu^z_{i+1/2}=\prod_{j\le i}X_j,
$$

show that

$$
\mu^z_{i-1/2}\mu^z_{i+1/2}=X_i.
$$

<details><summary><strong>Solution</strong></summary>

By definition,

$$
\mu^z_{i-1/2}=\prod_{j\le i-1}X_j,
\qquad
\mu^z_{i+1/2}=\prod_{j\le i}X_j.
$$

Multiplying gives

$$
\mu^z_{i-1/2}\mu^z_{i+1/2}
=\left(\prod_{j\le i-1}X_j\right)
\left(\prod_{j\le i}X_j\right).
$$

All factors with $j\le i-1$ square to $1$ and cancel, leaving

$$
X_i.
$$

</details>

### Exercise 4: Why non-invertible?

Explain in words why order-disorder duality can be exact but non-invertible.

<details><summary><strong>Solution</strong></summary>

Order-disorder duality relates two descriptions of the theory, but it is nonlocal in the original variables and changes sector data such as boundary conditions and spin-flip twists. At a self-dual point, this relation becomes an exact topological defect. However, fusing the defect with itself does not return a single transparent channel; it returns a sum over the $\mathbb Z_2$ sectors, $1+\eta$. Thus the defect is exact and topological but lacks an inverse.

</details>

## References

- H. A. Kramers and G. H. Wannier, “Statistics of the Two-Dimensional Ferromagnet,” Parts I and II.
- L. Onsager, “Crystal Statistics. I. A Two-Dimensional Model with an Order-Disorder Transition.”
- J. Fröhlich, J. Fuchs, I. Runkel, and C. Schweigert, “Kramers–Wannier Duality from Conformal Defects.”
- J. Fröhlich, J. Fuchs, I. Runkel, and C. Schweigert, “Duality and Defects in Rational Conformal Field Theory.”
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, for the Ising CFT and minimal-model background.
- S.-H. Shao, “What’s Done Cannot Be Undone: TASI Lectures on Non-Invertible Symmetries.”
- H.-C. Zhang and G. Sierra, “Kramers–Wannier Self-Duality and Non-Invertible Translation Symmetry in Quantum Chains: A Wave-Function Perspective.”

## Version history

- **2026-06-20:** Initial polished draft. Added classical lattice duality, transverse-field chain dual variables, critical Ising CFT defect fusion, quantum dimension, order-disorder crossing interpretation, boundary subtleties, Tambara–Yamagami preview, and exercises.
