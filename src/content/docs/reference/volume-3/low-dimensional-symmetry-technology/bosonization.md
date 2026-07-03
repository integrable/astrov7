---
title: "Bosonization"
description: "Explains the 1+1-dimensional fermion–boson dictionary, including currents, vertex operators, compactness, sine-Gordon/Thirring duality, symmetry, anomalies, and common normalization traps."
sidebar:
  label: "Bosonization"
  order: 1
level: Advanced
status: "Polished draft"
source: "Coleman; Mandelstam; Witten; Ginsparg; Di Francesco–Mathieu–Sénéchal; Altland–Simons Ch. 3; standard condensed-matter bosonization references."
topics:
  - bosonization
  - two-dimensional QFT
  - compact boson
  - Dirac fermion
  - sine-Gordon model
  - Thirring model
  - vertex operators
canonicalTopics:
  - bosonization
  - compact-boson
  - fermion-boson-duality
  - sine-gordon-thirring-correspondence
  - vertex-operator
researchStatus:
  established:
    - "Abelian bosonization of massless fermions in 1+1 dimensions and the sine-Gordon/massive-Thirring correspondence are standard results."
    - "Bosonization is a central tool in two-dimensional CFT, Luttinger liquids, spin chains, impurity problems, and low-dimensional duality."
  active:
    - "Modern work continues to generalize bosonization through non-Abelian, higher-dimensional, categorical, lattice, and anomaly-sensitive formulations."
---

## Summary

**Bosonization** is the statement that in one spatial dimension, some fermionic QFTs have an exactly equivalent bosonic description. The simplest case is a massless Dirac fermion in 1+1 dimensions, which is equivalent to a compact free scalar. In a standard Coleman normalization,

$$
j^\mu=\bar\psi\gamma^\mu\psi
\quad\longleftrightarrow\quad
\frac{1}{\sqrt{\pi}}\epsilon^{\mu\nu}\partial_\nu\phi,
$$

and the fermion mass operator maps to a cosine potential,

$$
\bar\psi\psi
\quad\longleftrightarrow\quad
C\,:\cos(2\sqrt{\pi}\phi):.
$$

Thus the massive Thirring model maps to the sine-Gordon model,

$$
\mathcal L_{\rm Th}
=
\bar\psi i\partial\!\!\!/\psi
-\frac{g}{2}(\bar\psi\gamma^\mu\psi)(\bar\psi\gamma_\mu\psi)
-m\bar\psi\psi
$$

and

$$
\mathcal L_{\rm SG}
=
\frac12(\partial_\mu\phi)(\partial^\mu\phi)
+\mu\,:\cos(\beta\phi):,
$$

with the coupling relation

$$
\frac{4\pi}{\beta^2}=1+\frac{g}{\pi}
$$

in Coleman’s convention.

The slogan is

$$
\text{fermion number}
\quad\longleftrightarrow\quad
\text{boson winding or dual flux}.
$$

<figure class="doc-figure" style="--figure-width: 54rem;">

![A bosonization dictionary diagram showing a massless Dirac fermion, a compact boson, currents, vertex operators, mass terms, and sine-Gordon/Thirring duality.](/figures/symmetry-anomalies-topology/bosonization-dictionary.svg)

<figcaption>

Bosonization is not a vague analogy. In 1+1 dimensions, fermion currents become derivatives of a compact scalar, fermion operators become vertex operators, fermion mass becomes a cosine perturbation, and the massive Thirring model becomes the sine-Gordon model in the appropriate normalization.

</figcaption>
</figure>

Bosonization is one of the great low-dimensional miracles: it converts statistics into topology, particles into solitons, and interacting fermions into bosons with changed radius or cosine interactions.

## Prerequisites

You should know free scalar and Dirac fields, Noether currents, normal ordering, and the distinction between local operators and charged operators. The pages on [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) and [Charged Extended Operators](/symmetry-anomalies-topology/higher-form-generalized-symmetries/charged-extended-operators/) are helpful because bosonization turns ordinary charge into a topological winding statement.

You do not need a full course in 2D CFT, but you should be comfortable with the idea that in two Euclidean dimensions one can use complex coordinates

$$
z=x+i\tau,\qquad \bar z=x-i\tau,
$$

and split massless fields into left- and right-moving parts.

## Core idea

In 1+1 dimensions, a conserved current can be written locally as the dual derivative of a scalar. If

$$
\partial_\mu j^\mu=0,
$$

then locally one can write

$$
j^\mu=\frac{1}{\sqrt{\pi}}\epsilon^{\mu\nu}\partial_\nu\phi.
$$

The normalization is conventional; the coefficient is chosen here to match the standard Dirac-fermion normalization. The charge is

$$
Q=\int dx\,j^0
=
\frac{1}{\sqrt{\pi}}\int dx\,\partial_x\phi
=
\frac{1}{\sqrt{\pi}}\bigl(\phi(+\infty)-\phi(-\infty)\bigr).
$$

So fermion number becomes a topological winding of the bosonic field. This is the conceptual heart of bosonization.

The second ingredient is that exponentials of a free scalar behave like fermions when the compactification radius and cocycle factors are chosen correctly. Fermion operators are represented by vertex operators,

$$
\psi_{R,L}\sim \kappa_{R,L}:e^{i(\text{chiral boson})}:,
$$

where the Klein factors $\kappa_{R,L}$ ensure the correct anticommutation between different species or chiralities.

The third ingredient is compactness. The boson is not just an ordinary real scalar. Its allowed momentum and winding sectors encode the fermionic Hilbert space, charge quantization, and spin-structure dependence.

:::caution[Compactness is not optional]
Many wrong bosonization derivations come from treating $\phi$ as a noncompact scalar. The compact radius, winding sectors, zero modes, and spin structure are part of the dictionary, not decorative refinements.
:::

## Setup and conventions

We work in 1+1-dimensional Lorentzian spacetime with $\epsilon^{01}=+1$. Let $\psi$ be a Dirac fermion with vector current

$$
j^\mu=\bar\psi\gamma^\mu\psi.
$$

In the Coleman normalization used on this page,

$$
j^\mu
=
\frac{1}{\sqrt{\pi}}\epsilon^{\mu\nu}\partial_\nu\phi,
\qquad
j_5^\mu
=
\bar\psi\gamma^\mu\gamma^5\psi
=
\frac{1}{\sqrt{\pi}}\partial^\mu\phi.
$$

The boson action at the free-fermion point is

$$
S_\phi=\frac12\int d^2x\,(\partial_\mu\phi)(\partial^\mu\phi),
$$

with a compact identification chosen so that $e^{\pm 2i\sqrt{\pi}\phi}$ has the quantum numbers of the fermion mass operator. Different CFT and condensed-matter references use different scalar normalizations, often writing the action as

$$
S=\frac{1}{8\pi}\int d^2x\,(\partial_\mu\varphi)(\partial^\mu\varphi).
$$

The translation between the two forms is a rescaling of the scalar. Always compare the current normalization and the periodicity together.

:::note[Source note: normalizations]
Coleman’s sine-Gordon/Thirring convention, CFT compact-boson conventions, and condensed-matter Luttinger-liquid conventions differ by rescalings of $\phi$, $\beta$, the current, and sometimes the dual field. This page states the Coleman-style dictionary explicitly and flags where radius language enters.
:::

## Chiral decomposition

A massless Dirac fermion has right- and left-moving components,

$$
\psi=
\begin{pmatrix}
\psi_R\\
\psi_L
\end{pmatrix}.
$$

A massless scalar decomposes into chiral pieces,

$$
\phi(t,x)=\phi_L(t+x)+\phi_R(t-x),
$$

up to convention-dependent signs. The dual scalar $\tilde\phi$ is defined by

$$
\partial_\mu\tilde\phi=\epsilon_{\mu\nu}\partial^\nu\phi.
$$

Vertex operators built from $\phi$ and $\tilde\phi$ create states with definite momentum and winding. In one common schematic notation,

$$
\psi_R\sim \kappa_R:e^{+i\sqrt{\pi}(\phi+\tilde\phi)}:,
\qquad
\psi_L\sim \kappa_L:e^{-i\sqrt{\pi}(\phi-\tilde\phi)}:.
$$

Do not memorize this formula without its convention. Memorize the structural statement:

$$
\text{right/left fermion}
\quad\longleftrightarrow\quad
\text{chiral vertex operator}.
$$

The Klein factors $\kappa_R,\kappa_L$ are needed because exponentials of one bosonic field do not automatically anticommute as independent fermions. In a single-species local calculation they are often suppressed, but in multi-species theories they are essential.

## The current dictionary

The most reliable part of the bosonization dictionary is the current map. With the above convention,

$$
j^\mu
=
\bar\psi\gamma^\mu\psi
\longleftrightarrow
\frac{1}{\sqrt{\pi}}\epsilon^{\mu\nu}\partial_\nu\phi.
$$

This immediately gives

$$
j^0=\psi^\dagger\psi
\longleftrightarrow
\frac{1}{\sqrt{\pi}}\partial_x\phi,
$$

so fermion density is the spatial derivative of the boson. The axial current is

$$
j_5^\mu
=
\bar\psi\gamma^\mu\gamma^5\psi
\longleftrightarrow
\frac{1}{\sqrt{\pi}}\partial^\mu\phi.
$$

This makes the free-fermion kinetic term equivalent to a free-boson kinetic term. It also explains why bosonization is powerful for one-dimensional many-body systems: density fluctuations are the elementary bosonic excitations.

### Exercise 1: Charge as winding

Using the current map, show that the total fermion number equals the winding of $\phi$.

<details><summary><strong>Solution</strong></summary>

The total charge is

$$
Q=\int dx\,j^0.
$$

Using

$$
j^0=\frac{1}{\sqrt{\pi}}\partial_x\phi,
$$

we find

$$
Q
=
\frac{1}{\sqrt{\pi}}\int dx\,\partial_x\phi
=
\frac{1}{\sqrt{\pi}}\bigl(\phi(+\infty)-\phi(-\infty)\bigr).
$$

Thus nonzero fermion number corresponds to a field configuration in which the boson changes by a compact-period amount between the two ends of space. On a circle, the same statement is expressed in terms of winding sectors.

</details>

## Vertex operators and fermions

The free scalar has vertex operators

$$
V_\alpha(x)=:e^{i\alpha\phi(x)}:.
$$

Their scaling dimensions depend on the scalar normalization. In the Coleman normalization, the operator

$$
:e^{\pm 2i\sqrt{\pi}\phi}:
$$

has the quantum numbers of a fermion bilinear. Schematically,

$$
\bar\psi\psi
\longleftrightarrow
C\,:\cos(2\sqrt{\pi}\phi):,
$$

and

$$
\bar\psi i\gamma^5\psi
\longleftrightarrow
C\,:\sin(2\sqrt{\pi}\phi):.
$$

The constant $C$ is not universal; it depends on the UV normal ordering convention and cutoff. The charge assignments and scaling dimensions are universal once the fixed point and normalization are specified.

Fermion fields themselves are nontrivial vertex operators involving chiral bosons and Klein factors. Their correlation functions reproduce fermionic signs because vertex operators in two dimensions have branch cuts. What looks like statistics in the fermion language becomes monodromy in the boson language.

## The massive Thirring model and sine-Gordon model

The most famous interacting bosonization result is Coleman’s equivalence between the massive Thirring model and the sine-Gordon model. The massive Thirring Lagrangian is

$$
\mathcal L_{\rm Th}
=
\bar\psi i\partial\!\!\!/\psi
-\frac{g}{2}j_\mu j^\mu
-m\bar\psi\psi.
$$

Using the current dictionary,

$$
j_\mu j^\mu
\longleftrightarrow
-\frac{1}{\pi}(\partial_\mu\phi)(\partial^\mu\phi),
$$

up to signature conventions. The four-fermion interaction changes the coefficient of the boson kinetic term. Rescaling the boson to canonical normalization changes the frequency $\beta$ of the cosine potential. The mass term becomes

$$
m\bar\psi\psi
\longleftrightarrow
\mu:\cos(\beta\phi):.
$$

The result is the sine-Gordon Lagrangian

$$
\mathcal L_{\rm SG}
=
\frac12(\partial_\mu\phi)(\partial^\mu\phi)
+\mu:\cos(\beta\phi):,
$$

with

$$
\frac{4\pi}{\beta^2}=1+\frac{g}{\pi}.
$$

When $g=0$, we get $\beta^2=4\pi$, the free-fermion point.

:::note[Source note: Coleman relation]
The displayed relation is the standard Coleman convention. Some authors write the Thirring interaction with the opposite sign or absorb factors of $\pi$ into $g$, which changes the appearance of the relation. Compare conventions before using this formula numerically.
:::

## Solitons become particles

The sine-Gordon model has soliton configurations in which $\phi$ interpolates between neighboring minima of the cosine potential. The topological charge is

$$
Q_{\rm top}
=
\frac{\beta}{2\pi}\int dx\,\partial_x\phi.
$$

Under the bosonization dictionary, this topological charge is the fermion number of the Thirring model. Thus the fermion is not mapped to a small oscillation of the sine-Gordon field; it is mapped to a soliton.

This is one of the deepest lessons of bosonization:

$$
\text{elementary particle in one description}
\quad\longleftrightarrow\quad
\text{topological soliton in another}.
$$

This is why bosonization belongs in a volume about symmetry, anomalies, and topology, not only in a volume about exactly solvable models.

## Compact bosons, radius, and charge lattices

A compact scalar satisfies

$$
\phi\sim \phi+2\pi R.
$$

On a spatial circle, states are labeled by momentum and winding numbers. Very schematically,

$$
p\in \frac{1}{R}\mathbb Z,
\qquad
w\in R\mathbb Z.
$$

The precise normalization depends on whether one uses $\phi$, $\varphi$, or separate chiral fields. The important point is that the bosonic Hilbert space has sectors, and those sectors encode fermion number, fermion parity, and spin-structure data.

At special radii, the compact boson has enhanced symmetry. For example, the free Dirac fermion point can be described as a compact boson at a particular radius, where vertex operators reproduce fermion fields and bilinears. Changing the radius corresponds to changing interaction strength in the fermionic description, as in the Luttinger-liquid or Thirring-model language.

This radius dependence is often the cleanest way to understand why a continuum of interacting fermion fixed points can be described by a continuum of compact-boson theories.

## Spin structures and fermion parity

Bosonization is not complete until spin structures are included. A fermion path integral depends on the choice of periodic or antiperiodic boundary conditions around cycles of spacetime. On a torus, there are four spin structures.

The bosonic dual must reproduce this dependence. Depending on the version of the dictionary, this can require summing over sectors with phases, coupling to a background $\mathbb Z_2$ gauge field for fermion parity, or using a bosonic theory with a carefully chosen radius and projection.

The practical warning is:

$$
\text{fermionic theory}
\neq
\text{just one naive compact boson partition function}.
$$

For local correlators on the plane, spin-structure issues may be invisible. For torus partition functions, boundaries, defects, and gauging, they are central.

## Symmetry interpretation

Bosonization translates ordinary symmetries into geometric operations of the compact boson.

The vector $U(1)$ fermion number symmetry becomes a shift of the dual boson or, equivalently, conservation of winding. The axial $U(1)$ symmetry becomes a shift of $\phi$ in the massless theory. The fermion mass term breaks the axial symmetry to a discrete subgroup because

$$
\cos(2\sqrt{\pi}\phi)
$$

is invariant only under discrete shifts.

Fermion parity corresponds to a special shift or sector projection in the bosonic theory. Charge conjugation, parity, and time reversal have bosonic actions that depend on convention. Because these discrete symmetries can be anomaly-sensitive, a careful page should state them rather than infer them casually.

Bosonization therefore teaches a general lesson: the same symmetry can look like a phase rotation, a shift symmetry, a winding conservation law, or a topological defect action depending on variables.

## Non-Abelian bosonization preview

For $N$ free Dirac fermions with non-Abelian flavor symmetry, bosonization can produce Wess–Zumino–Witten models. A basic slogan is

$$
\text{free fermions with }G\text{ currents}
\quad\longleftrightarrow\quad
G_k\text{ WZW theory plus Abelian factors},
$$

with the level $k$ determined by the representation and number of fermions.

The non-Abelian currents become affine Lie algebra currents. This is why bosonization connects directly to current algebras, WZW models, and rational CFT. The Abelian bosonization page you are reading is the entry point; the full non-Abelian story requires current-algebra and WZW technology.

## How to use bosonization in practice

A practical bosonization calculation usually follows this workflow.

1. Identify the low-energy fermions and their chiralities.
2. Choose a boson normalization and compactification radius.
3. Write the current dictionary.
4. Translate fermion bilinears and allowed interactions into vertex operators.
5. Use symmetry to check which cosine or derivative terms are allowed.
6. Determine which perturbations are relevant, marginal, or irrelevant.
7. Interpret phases using pinned boson fields, solitons, winding, and allowed defects.
8. Translate physical observables back to the fermion language.

In condensed matter, this is the standard logic behind Luttinger liquids and many one-dimensional spin-chain analyses. In high-energy language, it is the logic behind the sine-Gordon/Thirring correspondence and two-dimensional current algebra examples.

## Common pitfalls

**Forgetting compactness.** A noncompact scalar misses charge quantization, winding, and fermion parity.

**Ignoring zero modes.** Oscillator modes reproduce many local correlators, but zero modes determine sectors and charges.

**Suppressing Klein factors too early.** Klein factors are often harmless for one species in one correlator. They are not harmless for multiple species or global sign questions.

**Comparing formulas across incompatible normalizations.** The same physical dictionary can contain $2\sqrt{\pi}\phi$, $\phi$, $\sqrt{4\pi}\phi$, or radius-dependent factors depending on the scalar action.

**Thinking the fermion maps to a small boson fluctuation.** In the interacting massive correspondence, the fermion maps to a soliton of the sine-Gordon field.

**Treating torus partition functions as automatic.** Fermionic spin structures and bosonic winding sums must be matched carefully.

**Forgetting anomalies.** Chiral rotations, background gauge fields, and spin structures can reveal anomalies that are invisible in a naive local dictionary.

## Relations to other pages

Fermionization reverses the logic of this page and explains when a bosonic theory can be rewritten using fermions.

Kramers–Wannier Duality uses the same moral idea that order variables and disorder variables can exchange roles.

Current Algebras explains the chiral-current side of two-dimensional QFT, including affine Lie algebras and WZW models.

Anomalies in Two Dimensions explains how bosonization captures chiral anomaly inflow, background fields, and anomalous current transformations.

The CFT and Bootstrap volume develops compact bosons, vertex operator algebras, modular invariance, and rational CFT in full detail.

## Research status

Abelian bosonization in 1+1 dimensions is established. The Coleman correspondence, Mandelstam fermion construction, compact-boson CFT, and Luttinger-liquid applications are standard.

The active frontier is broader bosonization: non-Abelian bosonization, dualities in higher dimensions, anomaly-sensitive lattice bosonization, fermionization with spin-TQFT data, and categorical interpretations of duality defects. These are not replacements for the elementary dictionary; they are refinements and generalizations.

## Exercises

### Exercise 2: Current-current interaction

Using

$$
j^\mu=\frac{1}{\sqrt{\pi}}\epsilon^{\mu\nu}\partial_\nu\phi,
$$

show that $j_\mu j^\mu$ is proportional to $(\partial_\mu\phi)(\partial^\mu\phi)$ up to a sign determined by the metric convention.

<details><summary><strong>Solution</strong></summary>

We compute

$$
j_\mu j^\mu
=
\frac{1}{\pi}
\epsilon_{\mu\rho}\epsilon^{\mu\nu}
(\partial^\rho\phi)(\partial_\nu\phi).
$$

In mostly-minus Lorentzian signature with $\epsilon^{01}=+1$, the contraction gives a minus sign relative to the identity tensor:

$$
\epsilon_{\mu\rho}\epsilon^{\mu\nu}=-\delta_\rho{}^\nu.
$$

Therefore

$$
j_\mu j^\mu
=
-\frac{1}{\pi}(\partial_\mu\phi)(\partial^\mu\phi).
$$

This is why the Thirring current-current interaction changes the coefficient of the boson kinetic term.

</details>

### Exercise 3: Free-fermion point

Use Coleman’s relation

$$
\frac{4\pi}{\beta^2}=1+\frac{g}{\pi}
$$

to find $\beta^2$ for the free massive Dirac fermion, where $g=0$.

<details><summary><strong>Solution</strong></summary>

Set $g=0$. Then

$$
\frac{4\pi}{\beta^2}=1,
$$

so

$$
\beta^2=4\pi.
$$

Thus the sine-Gordon model at $\beta^2=4\pi$ corresponds to the free massive Dirac fermion in this convention.

</details>

### Exercise 4: Axial symmetry breaking by a mass term

Suppose the massless bosonized theory has a shift symmetry $\phi\mapsto\phi+c$. Which shifts preserve the operator $\cos(2\sqrt{\pi}\phi)$?

<details><summary><strong>Solution</strong></summary>

We need

$$
\cos(2\sqrt{\pi}(\phi+c))=\cos(2\sqrt{\pi}\phi)
$$

for all $\phi$. This holds when

$$
2\sqrt{\pi}c=2\pi n,
\qquad n\in\mathbb Z.
$$

Thus

$$
c=n\sqrt{\pi}.
$$

The mass term breaks the continuous shift symmetry to a discrete subgroup. The precise interpretation of this subgroup depends on the compactification radius and the fermionic symmetry being represented.

</details>

## References

- Sidney Coleman, “Quantum Sine-Gordon Equation as the Massive Thirring Model,” for the classic interacting equivalence and coupling relation.
- Stanley Mandelstam, “Soliton Operators for the Quantized Sine-Gordon Equation,” for the fermion operator construction.
- Edward Witten, “Non-Abelian Bosonization in Two Dimensions,” for the WZW/current-algebra generalization.
- Paul Ginsparg, “Applied Conformal Field Theory,” for compact-boson and CFT conventions.
- Philippe Di Francesco, Pierre Mathieu, and David Sénéchal, *Conformal Field Theory*, for compact bosons, fermions, modular data, and operator dictionaries.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, for field-theoretical bosonization and many-body applications.
- A. O. Gogolin, A. A. Nersesyan, and A. M. Tsvelik, *Bosonization and Strongly Correlated Systems*, for condensed-matter applications.
- T. Giamarchi, *Quantum Physics in One Dimension*, for Luttinger-liquid conventions and applications.

## Version history

- **2026-06-23:** Initial polished draft. Added Coleman-normalization current dictionary, compactness and spin-structure cautions, sine-Gordon/Thirring correspondence, soliton interpretation, symmetry dictionary, exercises, and normalization warnings.
