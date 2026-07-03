---
title: "BF Theory Terms"
description: "Defines BF terms, explains their higher-form gauge invariance, coefficient quantization, linking phases, discrete gauge theory, boundary terms, and relation to generalized symmetries."
sidebar:
  label: "BF Theory Terms"
  order: 6
level: Advanced
status: "Polished draft"
source: "Topological field theory and higher-form symmetry references; Horowitz; Blau–Thompson; Dijkgraaf–Witten; Gaiotto–Kapustin–Seiberg–Willett; Polyakov; Altland–Simons Ch. 8."
topics:
  - BF theory
  - topological terms
  - higher-form gauge fields
  - linking phases
  - discrete gauge theory
  - topological order
  - anomaly inflow
canonicalTopics:
  - bf-theory-terms
  - higher-form-gauge-fields
  - linking-pairing
  - discrete-gauge-theory
  - topological-response
researchStatus:
  established:
    - "BF terms are metric-independent couplings between higher-form gauge fields and are standard continuum descriptions of linking phases, finite abelian gauge theories, and higher-form topological response."
    - "For compact higher-form gauge fields, large gauge transformations quantize the BF coefficient."
  active:
    - "Modern refinements track differential cohomology, torsion sectors, spin structures, nonabelian generalizations, subsystem symmetries, fracton-like variants, and categorical boundary/defect data."
---

## Summary

A BF term is a topological coupling between two differential-form gauge fields. On a $d$-dimensional spacetime manifold $M_d$, let $A_p$ be a compact $p$-form gauge field and let $B_{d-p-1}$ be a compact $(d-p-1)$-form gauge field. The basic abelian BF action is

$$
S_{\mathrm{BF}}[A,B]
=\frac{k}{2\pi}\int_{M_d} B_{d-p-1}\wedge dA_p.
$$

The name is literal: $B$ is coupled to the field strength $F=dA$. The term is metric independent. In the absence of sources, its equations of motion say

$$
dA=0,
\qquad
 dB=0,
$$

so the pure BF theory has no local propagating bulk degrees of freedom. It is still far from trivial. Compactness, holonomy, linking, boundaries, and large gauge transformations make it a genuine quantum theory rather than an empty formal integral.

<figure class="doc-figure" style="--figure-width: 60rem;">

![Diagram showing the BF action, compact higher-form gauge fields, integer level quantization, flatness equations, charged Wilson and surface operators, linking phases, finite gauge theory, higher-form symmetry, and boundary inflow.](/figures/symmetry-anomalies-topology/bf-theory-linking-pairing.svg)

<figcaption>

A BF term couples two gauge fields of complementary degree. In the bulk it imposes flatness, but in the quantum theory it records linking phases, finite gauge structure, higher-form symmetry data, and boundary anomaly inflow.

</figcaption>
</figure>

The two most useful cases are:

$$
\begin{array}{c|c|c|c}
\text{dimension} & A & B & \text{common interpretation} \\
\hline
3 & A_1 & B_1 & \text{mutual Chern–Simons theory, }\mathbb Z_k\text{ gauge theory} \\
4 & A_1 & B_2 & \text{particle-string linking, one-form symmetry, }\mathbb Z_k\text{ gauge theory}
\end{array}
$$

BF terms are the unsung plumbing of modern symmetry. Chern–Simons terms get the dramatic lighting, but BF terms are often what actually carries the higher-form gauge bookkeeping.

## Prerequisites

Read [Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/) first. You should also know the background-field viewpoint from [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/), the distinction between background and dynamical fields from [Background Fields Versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/), and the role of large transformations from [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/).

For the higher-form interpretation, the later page [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) will give the full dictionary. This page uses the language already, but only at the level needed to understand the term $B\wedge dA$.

## Core idea

A BF term pairs two gauge fields whose degrees add up correctly:

$$
\deg B+\deg dA=d.
$$

Thus if $A$ is a $p$-form, $B$ must be a $(d-p-1)$-form. The two fields have complementary charged operators:

$$
W_A(C_p)=\exp\left(i\int_{C_p}A_p\right),
\qquad
W_B(\Sigma_{d-p-1})=\exp\left(i\int_{\Sigma_{d-p-1}}B_{d-p-1}\right).
$$

Here $C_p$ is a closed $p$-cycle and $\Sigma_{d-p-1}$ is a closed $(d-p-1)$-cycle. Their dimensions add to $d-1$, which is exactly the condition that the cycles can link inside $M_d$. The BF path integral detects that linking.

The slogan is

$$
\text{BF theory} = \text{flat higher-form gauge fields plus linking phases}.
$$

This is why BF terms are natural in finite gauge theory, topological order, symmetry protected response, and mixed higher-form anomalies.

## Setup and conventions

Let $M_d$ be an oriented $d$-manifold. Unless stated otherwise, it is closed. We work with abelian compact higher-form gauge fields. The compactness convention is that field strengths have integral periods:

$$
\frac{1}{2\pi}\int_{\Gamma_{p+1}}dA\in\mathbb Z,
\qquad
\frac{1}{2\pi}\int_{\Gamma_{d-p}}dB\in\mathbb Z,
$$

for closed cycles of the indicated dimension. The local gauge transformations are

$$
A_p\longmapsto A_p+d\lambda_{p-1},
\qquad
B_{d-p-1}\longmapsto B_{d-p-1}+d\Lambda_{d-p-2}.
$$

The BF action is

$$
S_{\mathrm{BF}}
=\frac{k}{2\pi}\int_{M_d}B\wedge dA.
$$

For compact fields, the coefficient $k$ is quantized:

$$
k\in\mathbb Z.
$$

The differential-form expression is a convenient local notation. A fully global treatment uses differential cohomology or Deligne–Beilinson cocycles, because $A$ and $B$ need not be globally defined forms on nontrivial bundles. The local formula is enough for most physics calculations, as long as the period normalization and large-gauge quantization are kept visible.

:::note[Convention-sensitive source note]
Some references write the action as $\frac{i k}{2\pi}\int B\wedge dA$ in Euclidean signature. This page writes Lorentzian path-integral phases as $e^{iS}$ and therefore keeps $S_{\mathrm{BF}}=\frac{k}{2\pi}\int B\wedge dA$. Wick rotation moves factors of $i$ between the action and the exponent.
:::

## Gauge invariance and quantization

Under a small gauge transformation on a closed manifold,

$$
A\mapsto A+d\lambda,
$$

the action changes by

$$
\Delta S_{\mathrm{BF}}
=\frac{k}{2\pi}\int B\wedge d^2\lambda=0.
$$

Similarly, under $B\mapsto B+d\Lambda$,

$$
\Delta S_{\mathrm{BF}}
=\frac{k}{2\pi}\int d\Lambda\wedge dA
=\frac{k}{2\pi}\int d(\Lambda\wedge dA)=0
$$

on a closed manifold.

The real constraint comes from large gauge transformations and globally nontrivial configurations. For compact fields, $dA/2\pi$ and $dB/2\pi$ have integral periods. The BF action can shift by integer multiples of $2\pi k$. Therefore the exponentiated action

$$
e^{iS_{\mathrm{BF}}}
$$

is well defined when $k$ is an integer. More refined global choices can alter the allowed lattice of coefficients, especially on non-spin versus spin manifolds or in theories with torsion. But the basic lesson is stable:

$$
\text{compact higher-form gauge fields force quantized BF coefficients.}
$$

If $A$ and $B$ are treated as ordinary noncompact differential forms, then the same large-gauge argument is absent. That theory is not the same quantum theory. Compactness is not decorative; it is part of the definition.

## Equations of motion

On a closed manifold, the variation is

$$
\delta S_{\mathrm{BF}}
=\frac{k}{2\pi}\int_{M_d}\delta B\wedge dA
+\frac{k}{2\pi}\int_{M_d}B\wedge d\delta A.
$$

Integrating the second term by parts gives

$$
\delta S_{\mathrm{BF}}
=\frac{k}{2\pi}\int_{M_d}\delta B\wedge dA
+(-1)^{d-p}\frac{k}{2\pi}\int_{M_d}dB\wedge\delta A.
$$

Hence the classical bulk equations are

$$
dA=0,
\qquad
 dB=0,
$$

up to a sign convention in the second equation that does not change its content.

This is why pure BF theory is topological. Locally, both gauge fields are flat. Globally, flat higher-form gauge fields can still have holonomies around nontrivial cycles. Those holonomies are the physical data.

If Maxwell-like kinetic terms are added,

$$
S= -\frac{1}{2e^2}\int dA\wedge *dA
-\frac{1}{2g^2}\int dB\wedge *dB
+\frac{k}{2\pi}\int B\wedge dA,
$$

the full theory is no longer topological. The BF term can then produce topological mass mixing between $A$ and $B$. This is an important mechanism in effective field theory, but it is different from pure BF theory.

## Wilson operators and linking phases

The operators naturally coupled to $A$ and $B$ are extended:

$$
W_A(C_p)=\exp\left(iq_A\int_{C_p}A\right),
\qquad
W_B(\Sigma_{d-p-1})=\exp\left(iq_B\int_{\Sigma_{d-p-1}}B\right).
$$

Because $C_p$ and $\Sigma_{d-p-1}$ have complementary dimensions, they can link in $M_d$. In pure compact BF theory at level $k$, the expectation value of a pair of unit operators contains the phase

$$
\left\langle W_A(C_p)W_B(\Sigma_{d-p-1})\right\rangle
\propto
\exp\left(\frac{2\pi i}{k}\operatorname{Link}(C_p,\Sigma_{d-p-1})\right).
$$

For charges $q_A$ and $q_B$, the phase is multiplied by $q_Aq_B$ in the numerator:

$$
\exp\left(\frac{2\pi i q_Aq_B}{k}\operatorname{Link}(C_p,\Sigma_{d-p-1})\right).
$$

This formula is the operational heart of BF theory. It says that BF theory measures how extended probes wind around one another. In $2+1$ dimensions, it describes mutual anyonic statistics. In $3+1$ dimensions, it describes the phase from braiding a particle worldline around a string worldsheet.

:::note[Source note]
The exact normalization of the linking phase depends on the normalization of the compact gauge fields and charges. The convention here is that minimally charged operators have holonomy $\exp(i\int A)$ and $\exp(i\int B)$, and the BF coefficient is $k/2\pi$.
:::

## Three-dimensional BF theory

In $d=3$, take $A$ and $B$ to be one-form gauge fields, often written $a$ and $b$:

$$
S_{\mathrm{BF}}=\frac{k}{2\pi}\int_{M_3}b\wedge da.
$$

This is also a Chern–Simons theory with a two-component $K$-matrix,

$$
S=\frac{1}{4\pi}\int K_{IJ}a^I\wedge da^J,
\qquad
K=\begin{pmatrix}0&k\\ k&0\end{pmatrix}.
$$

For compact dynamical $a$ and $b$, the theory describes the continuum limit of $\mathbb Z_k$ gauge theory in $2+1$ dimensions. The electric and magnetic line operators have mutual braiding phase

$$
e^{2\pi i/k}.
$$

On a spatial two-torus, this theory has $k^2$ ground states. That degeneracy is not a local particle-counting statement. It comes from global flat holonomies around noncontractible cycles.

This is the cleanest example where “topological” means exactly what it should mean: no local propagating degrees of freedom, but nontrivial global Hilbert spaces and line-operator braiding.

## Four-dimensional BF theory

In $d=4$, the most common BF term couples a one-form $A$ to a two-form $B$:

$$
S_{\mathrm{BF}}=\frac{k}{2\pi}\int_{M_4}B_2\wedge dA_1.
$$

The natural charged operators are a line and a surface:

$$
W_A(C)=\exp\left(i\int_C A\right),
\qquad
W_B(\Sigma)=\exp\left(i\int_\Sigma B\right).
$$

The linking phase is now a particle-string braiding phase:

$$
\left\langle W_A(C)W_B(\Sigma)\right\rangle
\propto
\exp\left(\frac{2\pi i}{k}\operatorname{Link}(C,\Sigma)\right).
$$

This theory is a continuum description of four-dimensional $\mathbb Z_k$ gauge theory. It also appears when a $U(1)$ gauge theory is Higgsed by charge-$k$ matter. At long distances, the massive Higgs and photon modes decouple, but a residual $\mathbb Z_k$ gauge theory remains. BF theory is the compact way to write that residual topological sector.

The two-form gauge field $B$ is not just a random auxiliary field. It is the field naturally coupled to stringlike objects and to one-form symmetry backgrounds. That is why four-dimensional BF theory is a standard doorway into higher-form symmetry.

## BF terms and finite gauge theory

For finite abelian gauge groups, BF theory is often the continuum avatar of Dijkgraaf–Witten gauge theory. For example, $\mathbb Z_k$ gauge theory can be represented by compact $U(1)$ fields with the BF action

$$
\frac{k}{2\pi}\int B\wedge dA.
$$

Integrating over $B$ imposes that $A$ is flat with holonomies constrained to $k$th roots of unity. Informally,

$$
dA=0,
\qquad
\oint A\in \frac{2\pi}{k}\mathbb Z.
$$

Thus a continuous-looking $U(1)$ description secretly encodes a finite gauge group at low energy.

This is one reason BF theory is so useful. It lets us write finite gauge theory using differential forms, while still remembering the crucial finite global data through compactness and level quantization.

## Background BF terms and mixed anomalies

So far $A$ and $B$ have been dynamical. One can also use BF terms as background response actions. Suppose $A$ and $B$ are nondynamical background fields for two generalized global symmetries. A term

$$
S_{\mathrm{anom}}[A,B]=\frac{k}{2\pi}\int B\wedge dA
$$

can represent a mixed anomaly or SPT response, depending on dimension and context. In that case the term is not an equation of motion for $A$ or $B$. Instead, it is part of the background-field dependence of the generating functional.

The distinction matters:

$$
\begin{array}{c|c|c}
\text{field status} & \text{operation} & \text{meaning of BF term} \\
\hline
\text{background} & \text{do not integrate} & \text{response or anomaly functional} \\
\text{dynamical} & \text{sum over fields} & \text{topological gauge theory}
\end{array}
$$

The same differential expression can play both roles. The path integral instruction tells you which theory you are defining.

## Boundaries

If $M_d$ has boundary, the variation produces a boundary term. For the local action,

$$
\delta S_{\mathrm{BF}}
=\text{bulk terms}
+\frac{k}{2\pi}\int_{\partial M_d} B\wedge\delta A,
$$

up to a sign determined by degrees. A well-defined variational principle requires boundary conditions or boundary degrees of freedom.

Similarly, gauge transformations can produce boundary variations. On a closed manifold they vanish or become $2\pi$ multiples. On a manifold with boundary, they can become honest boundary anomalies. There are several common resolutions:

1. Fix one field at the boundary.
2. Choose a Lagrangian boundary condition relating the boundary values of $A$ and $B$.
3. Add boundary degrees of freedom whose anomaly cancels the BF variation.
4. Interpret the boundary theory as relative to the bulk topological theory.

The last option is the modern anomaly-inflow viewpoint. BF theory is a particularly transparent example because all the relevant terms are low-degree forms and linking phases.

## Relation to Chern–Simons terms

Three-dimensional BF theory is a mutual Chern–Simons theory. With two one-form gauge fields $a$ and $b$,

$$
\frac{k}{2\pi}\int b\wedge da
$$

is equivalent to a Chern–Simons $K$-matrix theory with off-diagonal matrix entries. This is why many facts about abelian Chern–Simons theory immediately translate to BF theory: level quantization, line braiding, torus degeneracy, and boundary modes.

There is also a useful change of variables when $k$ is even or when spin structures are allowed. Define

$$
a_\pm=a\pm b.
$$

Then the BF action can be rewritten as a difference of two abelian Chern–Simons terms, schematically

$$
\frac{k}{2\pi}b\wedge da
\sim
\frac{k}{8\pi}a_+\wedge da_+
-\frac{k}{8\pi}a_-\wedge da_-.
$$

This identity is locally simple but globally delicate. Compactness, charge lattices, spin structure, and allowed line operators determine whether the change of variables is an equivalence of quantum theories.

## Relation to generalized symmetries

A $p$-form global symmetry acts on $p$-dimensional charged operators. Its background field is a $(p+1)$-form gauge field. BF theory naturally couples such backgrounds and gauge fields.

For example, in four-dimensional Maxwell theory, electric and magnetic one-form symmetries have two-form background fields. Mixed terms involving two-form backgrounds encode how line operators transform and how electric/magnetic choices are globally constrained. In discrete gauge theory, BF terms give the topological operators implementing finite higher-form symmetries.

This is the broader reason BF terms appear everywhere in modern QFT. They are the simplest local topological terms that know how extended operators link.

## Common pitfalls

**“BF theory is just a constraint, so it is trivial.”** The local equations impose flatness, but compact flat fields have holonomies. Their global sectors, line and surface operators, and linking phases are physical.

**“The coefficient $k$ is a continuous coupling.”** Not for compact fields. Large gauge transformations quantize it. Treating $k$ as continuous usually means you have changed the global definition of the fields.

**“$B$ is always an auxiliary field.”** Sometimes integrating out $B$ is a useful move. But if $B$ is compact, or if surface operators are present, or if there are boundaries, calling it auxiliary can hide the most important data.

**“A BF term is the same thing as a Chern–Simons term.”** In three dimensions abelian BF theory is a mutual Chern–Simons theory. In higher dimensions BF terms involve higher-form fields and have different operator content.

**“Background and dynamical BF terms mean the same thing.”** They use the same differential form, but the path integral instructions differ. Background BF terms encode response or anomalies. Dynamical BF terms define topological gauge theory.

**“The form formula is globally complete.”** It is not. On nontrivial manifolds, the correct global object is a differential cohomology pairing. The form notation is the local face of that pairing.

## Relations to other pages

- [Chern–Simons Terms](/symmetry-anomalies-topology/topological-terms/chern-simons-terms/) explains the three-dimensional cousin and the boundary-WZW story.
- [Topological Response](/symmetry-anomalies-topology/topological-terms/topological-response/) uses BF terms as response functionals for gapped phases and generalized symmetries.
- [Gauging Finite Symmetries: Preview](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-finite-symmetries-preview/) explains why summing over finite flat backgrounds is a gauge-theory operation.
- [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) gives the intrinsic symmetry language behind BF terms.
- [Topological Quantum Field Theory](/symmetry-anomalies-topology/topological-qft/) later treats BF theory as a standalone TQFT.

## Research status

The basic abelian BF theory is established. Its canonical quantization, path-integral linking phases, finite abelian gauge-theory interpretation, and relation to abelian Chern–Simons theory are standard.

The refined global story is still an active interface between physics and mathematics. Important refinements include torsion pairings, differential cohomology, spin and Pin structures, nonabelian higher-form gauge theory, boundary categories, non-invertible defects, and subsystem or fracton-like generalizations. For most QFT applications, the local formula $\frac{k}{2\pi}\int B\wedge dA$ is the start of the story, not the whole story.

## Exercises

### Exercise 1: Equations of motion

Let $A$ be a one-form and $B$ a two-form on a closed four-manifold. Vary

$$
S=\frac{k}{2\pi}\int B\wedge dA.
$$

Show that the equations of motion are $dA=0$ and $dB=0$.

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta S=\frac{k}{2\pi}\int \delta B\wedge dA
+\frac{k}{2\pi}\int B\wedge d\delta A.
$$

Using $d(B\wedge\delta A)=dB\wedge\delta A+B\wedge d\delta A$ because $B$ has degree $2$, and dropping the total derivative on a closed manifold, we get

$$
\delta S=\frac{k}{2\pi}\int \delta B\wedge dA
-\frac{k}{2\pi}\int dB\wedge\delta A.
$$

Since $\delta A$ and $\delta B$ are arbitrary, the equations are

$$
dA=0,
\qquad
 dB=0.
$$

</details>

### Exercise 2: Three-dimensional BF as a K-matrix theory

Show that

$$
S=\frac{k}{2\pi}\int b\wedge da
$$

can be written as

$$
S=\frac{1}{4\pi}\int K_{IJ}a^I\wedge da^J
$$

with

$$
K=\begin{pmatrix}0&k\\ k&0\end{pmatrix},
\qquad
 a^1=a,
\quad
 a^2=b,
$$

up to a boundary term.

<details><summary><strong>Solution</strong></summary>

The $K$-matrix action is

$$
S=\frac{1}{4\pi}\int \left(k a\wedge db+k b\wedge da\right).
$$

On a closed three-manifold,

$$
d(a\wedge b)=da\wedge b-a\wedge db.
$$

Since $da\wedge b=b\wedge da$, this gives

$$
a\wedge db=b\wedge da-d(a\wedge b).
$$

Dropping the total derivative, the action becomes

$$
S=\frac{1}{4\pi}\int 2k b\wedge da
=\frac{k}{2\pi}\int b\wedge da.
$$

</details>

### Exercise 3: Linking phase

In pure BF theory at level $k$, unit $A$- and $B$-charged operators have mutual phase

$$
\exp\left(\frac{2\pi i}{k}\operatorname{Link}(C,\Sigma)\right).
$$

What happens if the $A$-operator has charge $q_A$ and the $B$-operator has charge $q_B$?

<details><summary><strong>Solution</strong></summary>

The source strengths are multiplied by $q_A$ and $q_B$. The classical solution sourced by one operator is linear in its charge, and the phase picked up by the other operator is also linear in its charge. Therefore the linking phase becomes

$$
\exp\left(\frac{2\pi i q_Aq_B}{k}\operatorname{Link}(C,\Sigma)\right).
$$

Charges are naturally understood modulo $k$ in the compact $\mathbb Z_k$ theory.

</details>

### Exercise 4: Boundary variation

Let $M_4$ have boundary. For

$$
S=\frac{k}{2\pi}\int_{M_4}B\wedge dA,
$$

show that the variation includes a boundary term proportional to $\int_{\partial M_4}B\wedge\delta A$.

<details><summary><strong>Solution</strong></summary>

Starting from

$$
\delta S=\frac{k}{2\pi}\int_{M_4}\delta B\wedge dA
+\frac{k}{2\pi}\int_{M_4}B\wedge d\delta A,
$$

use

$$
B\wedge d\delta A=d(B\wedge\delta A)-dB\wedge\delta A.
$$

Then

$$
\delta S=\frac{k}{2\pi}\int_{M_4}\delta B\wedge dA
-\frac{k}{2\pi}\int_{M_4}dB\wedge\delta A
+\frac{k}{2\pi}\int_{\partial M_4}B\wedge\delta A.
$$

The last term must be canceled, fixed, or interpreted by choosing boundary conditions or adding boundary degrees of freedom.

</details>

## References

- G. T. Horowitz, “Exactly Soluble Diffeomorphism Invariant Theories,” *Communications in Mathematical Physics* **125** (1989).
- M. Blau and G. Thompson, “Topological Gauge Theories of Antisymmetric Tensor Fields,” *Annals of Physics* **205** (1991).
- R. Dijkgraaf and E. Witten, “Topological Gauge Theories and Group Cohomology,” *Communications in Mathematical Physics* **129** (1990).
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” *Journal of High Energy Physics* **2015**.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on gauge systems, compact gauge fields, instantons, and loop dynamics.
- A. Zee, *Quantum Field Theory in a Nutshell*, especially the discussions of Chern–Simons terms, quantum Hall fluids, and topological field theory.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, Ch. 8, for topological terms and response in matter-oriented field theory.
- Edward Witten, “Quantum Field Theory and the Jones Polynomial,” *Communications in Mathematical Physics* **121** (1989), for the broader Chern–Simons and TQFT context.

## Version history

- 2026-06-18: Initial polished draft for the improved Symmetry, Anomalies, and Topology plan.
