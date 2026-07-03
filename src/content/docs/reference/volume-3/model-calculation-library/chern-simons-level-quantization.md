---
title: "Chern–Simons Level Quantization"
description: "Model calculation deriving why the Chern–Simons level is quantized by large gauge transformations and how the answer depends on global and spin data."
sidebar:
  label: "Chern–Simons Level Quantization"
  order: 9
level: Advanced
status: "Polished draft"
source: "Srednicki §§69–77, 93; Schwartz Chs. 25, 30; Altland–Simons Ch. 8; Witten, Quantum Field Theory and the Jones Polynomial."
topics:
  - Chern–Simons theory
  - level quantization
  - large gauge transformations
  - topological terms
  - global anomalies
canonicalTopics:
  - chern-simons-level-quantization
  - large-gauge-transformations
  - topological-action
  - gauge-invariance
researchStatus:
  established:
    - "For compact gauge groups, quantum Chern–Simons theory has quantized levels fixed by large gauge transformations and global consistency conditions."
  active:
    - "Precise quantization can depend on global form, spin structure, boundary conditions, transparent lines, and the spectrum of allowed Wilson lines."
---

## Summary

Chern–Simons theory is the cleanest example of a local-looking action whose coefficient is fixed by global topology. In three dimensions, the non-Abelian Chern–Simons action is

$$
S_{\mathrm{CS}}[A]
=\frac{k}{4\pi}\int_M
\operatorname{tr}\left(A\wedge dA+\frac{2i}{3}A\wedge A\wedge A\right),
$$

where this page uses Hermitian gauge fields and Hermitian generators. The field equation is

$$
F=dA+iA\wedge A=0,
$$

so the theory has no ordinary propagating local gauge-boson modes. Nevertheless, it is far from empty: Wilson lines, boundary states, framing, knot invariants, and topological phases all remember the level $k$.

The central calculation is the following. Under a large gauge transformation, the Chern–Simons functional shifts by an integer multiple of $2\pi$:

$$
S_{\mathrm{CS}}[A^g]-S_{\mathrm{CS}}[A]=2\pi k\,n(g),
\qquad n(g)\in\mathbb Z.
$$

The quantum weight is $e^{iS}$, so it is gauge-invariant on closed manifolds only if

$$
k\in\mathbb Z
$$

for the standard simply connected compact simple cases with the trace normalized in the usual way. Variants with Abelian factors, non-simply connected groups, spin structures, matter fields, and boundaries require refinements, but the mechanism is always the same: **large gauge transformations see topology, and the path integral forces the coefficient to be quantized**.

<figure class="doc-figure" style="--figure-width: 44rem;">

![A large gauge transformation shifts the Chern–Simons functional by an integer winding number times 2π.](/figures/symmetry-anomalies-topology/chern-simons-level-quantization.svg)

<figcaption>

A small gauge transformation changes the Chern–Simons form by a total derivative. A large gauge transformation can also add $2\pi k n(g)$ on a closed three-manifold. Requiring $e^{iS}$ to be single-valued gives the level quantization condition.

</figcaption>
</figure>

## Prerequisites

You should know the model-library pages on the theta term and anomaly calculations, the chapter pages on topological terms and Chern–Simons theory, and the volume conventions for Hermitian generators. We use

$$
\operatorname{tr}_{\mathbf N}(T^aT^b)=\frac12\delta^{ab}
$$

for the fundamental representation of $SU(N)$ unless stated otherwise, and

$$
F=dA+iA\wedge A.
$$

For a compact simple group with Hermitian generators, the background transformation convention is

$$
A\mapsto A^g=g^{-1}Ag-i g^{-1}dg.
$$

With anti-Hermitian gauge fields, the same statements are usually written without the explicit factors of $i$. This is a convention change, not a physics change.

## The calculation in one line

Define the normalized Chern–Simons functional

$$
\operatorname{CS}(A)
=\frac{1}{4\pi}\int_M
\operatorname{tr}\left(A\wedge dA+\frac{2i}{3}A\wedge A\wedge A\right).
$$

For a closed oriented three-manifold $M$ and a gauge transformation $g:M\to G$,

$$
\operatorname{CS}(A^g)=\operatorname{CS}(A)+2\pi n(g),
$$

where $n(g)$ is the winding number of $g$. Therefore

$$
e^{ik\operatorname{CS}(A^g)}=e^{ik\operatorname{CS}(A)}e^{2\pi i k n(g)}.
$$

Gauge invariance of the quantum theory for every allowed large gauge transformation requires

$$
e^{2\pi i k n}=1
\qquad\text{for all }n\in\mathbb Z,
$$

hence

$$
k\in\mathbb Z.
$$

This is the core derivation. The rest of the page explains what is hidden in the words “normalized,” “closed,” “allowed,” and “large.”

## Small gauge transformations give a boundary term

The Chern–Simons three-form is

$$
\omega_3(A)=\operatorname{tr}\left(A\wedge dA+\frac{2i}{3}A\wedge A\wedge A\right).
$$

It obeys

$$
d\omega_3(A)=\operatorname{tr}(F\wedge F).
$$

Under an infinitesimal gauge transformation with parameter $\lambda$,

$$
\delta_\lambda A=D\lambda=d\lambda+i[A,\lambda]
$$

up to the sign convention for active transformations. Varying the Chern–Simons form gives

$$
\delta\omega_3(A)=2\operatorname{tr}(\delta A\wedge F)+d\operatorname{tr}(A\wedge\delta A).
$$

For a gauge variation, the bulk term is a total derivative because $DF=0$. Thus

$$
\delta_\lambda S_{\mathrm{CS}}
=\frac{k}{4\pi}\int_M d(\cdots).
$$

On a closed manifold, small gauge transformations do not change $S_{\mathrm{CS}}$. On a manifold with boundary, this boundary term is not zero; it is the seed of boundary current algebra, Wess–Zumino–Witten models, and anomaly inflow.

:::note[Source note: boundary terms]
The same term that is harmless on a closed three-manifold is precisely what becomes physical on a boundary. This is why Chern–Simons theory is simultaneously a topological bulk theory, a source of boundary chiral dynamics, and an anomaly-inflow theory.
:::

## Large gauge transformations see the winding number

A large gauge transformation is not continuously connected to the identity. For compact simple groups such as $SU(N)$,

$$
\pi_3(SU(N))\cong\mathbb Z.
$$

Thus maps

$$
g:M^3\to SU(N)
$$

can have an integer winding number when $M$ is closed and oriented. The precise component formula depends on whether gauge fields are Hermitian or anti-Hermitian, but the invariant statement is

$$
\operatorname{CS}(A^g)-\operatorname{CS}(A)=2\pi n(g).
$$

Since the path integral uses

$$
Z=\int\frac{\mathcal DA}{\text{gauge}}\,e^{iS[A]},
$$

it is not enough for the classical equations of motion to be gauge covariant. The exponential weight must be well-defined on gauge-equivalence classes. This gives

$$
S[A^g]-S[A]\in 2\pi\mathbb Z.
$$

For $S=k\operatorname{CS}(A)$ and arbitrary winding $n(g)$, this becomes $k\in\mathbb Z$.

## Why the trace normalization matters

The integer condition is a statement about the pair

$$
(\text{trace normalization},\ k).
$$

If one rescales the trace by a factor $c$, then the same action written with that trace has an effectively rescaled level. This is why Chern–Simons levels are convention-dependent until the invariant bilinear form on the Lie algebra is specified.

For $SU(N)$, the common particle-physics convention is

$$
\operatorname{tr}_{\mathbf N}(T^aT^b)=\frac12\delta^{ab}.
$$

With this convention, integer $k$ gives a well-defined $SU(N)_k$ Chern–Simons theory on closed oriented three-manifolds. Mathematicians often package this by saying that the invariant bilinear form defining the level must be integral on the appropriate cocharacter lattice.

For a non-simply connected group such as $SO(3)$, $PSU(N)$, or a quotient of a product group, the same local Lie algebra can have stricter or different global quantization conditions. The global form of the gauge group is not decoration; it changes the allowed bundles, lines, and levels.

## Abelian Chern–Simons theory

For a compact $U(1)$ gauge field, the action is

$$
S=\frac{k}{4\pi}\int_M A\wedge dA.
$$

If one treats $A$ as an ordinary globally defined one-form, it is tempting to say that the level is arbitrary. That is the wrong test. A compact gauge field is a connection on a line bundle, and its flux obeys

$$
\frac{1}{2\pi}\int_\Sigma dA\in\mathbb Z
$$

for closed two-cycles $\Sigma$. Large gauge transformations and nontrivial bundles then force $k$ to be quantized.

For spin Chern–Simons theory, integer $k$ is natural. For a bosonic theory defined on arbitrary oriented three-manifolds without spin structure, a single diagonal $U(1)$ Chern–Simons term has an additional evenness condition in the usual $K$-matrix normalization: odd diagonal levels require spin structure. In condensed-matter language, odd diagonal entries describe theories that know about transparent fermions or spin structure.

:::caution[Abelian caveat]
The phrase “$U(1)_k$” is not enough to specify every global detail. One must say whether the theory is spin or non-spin, what the Wilson-line lattice is, and what transparent lines are identified.
:::

## Boundaries and anomaly inflow

If $M$ has a boundary, the small-gauge-variation boundary term does not vanish:

$$
\delta_\lambda S_{\mathrm{CS}}=\text{boundary term on }\partial M.
$$

There are two standard resolutions.

First, impose boundary conditions and restrict gauge transformations at the boundary. This can make the variational principle and gauge symmetry well-defined, but it also changes the boundary physics.

Second, add boundary degrees of freedom whose anomalous variation cancels the Chern–Simons boundary variation. This is the anomaly-inflow picture. For compact simple groups, the boundary theory is closely related to a chiral Wess–Zumino–Witten model at level $k$.

The lesson is subtle but important: on a closed three-manifold, level quantization makes $e^{iS}$ gauge invariant. On a manifold with boundary, the same Chern–Simons term is intentionally not gauge invariant by itself; its variation is what cancels the anomaly of the boundary theory.

## Wilson lines know the level

Wilson lines in representation $R$ are

$$
W_R(C)=\operatorname{tr}_R\,P\exp\left(i\oint_C A\right).
$$

In Chern–Simons theory, their correlation functions are topological link invariants after the framing data are specified. The allowed representations are constrained by the level. For $SU(2)_k$, for example, integrable Wilson-line labels satisfy

$$
j=0,\frac12,1,\ldots,\frac{k}{2}.
$$

This is another way the integer $k$ appears physically. The level is not merely a coefficient in the action. It controls the line-operator algebra, fusion rules, boundary current algebra, and the topological order of the theory.

## Relation to the four-dimensional theta term

The Chern–Simons form is not gauge invariant, but its exterior derivative is:

$$
d\omega_3(A)=\operatorname{tr}(F\wedge F).
$$

Thus a Chern–Simons term on a three-manifold can be viewed as living on the boundary of a four-dimensional topological term:

$$
\int_{M_4}\operatorname{tr}(F\wedge F),
\qquad \partial M_4=M_3.
$$

This relation explains both level quantization and anomaly inflow. The four-dimensional instanton number is quantized, and the three-dimensional Chern–Simons functional is a secondary invariant whose ambiguity is exactly what the quantum theory must tolerate.

In the model-library page on the Yang–Mills theta term, the integer

$$
\frac{1}{8\pi^2}\int\operatorname{tr}(F\wedge F)
$$

labels topological sectors. Here the Chern–Simons functional is the boundary object whose gauge variation measures the same topology.

## Common pitfalls

**Thinking the classical action must be strictly invariant.** For Chern–Simons theory, the action may shift by $2\pi$ times an integer without changing the quantum weight.

**Forgetting large gauge transformations.** Small gauge transformations only see local current conservation. Level quantization is a large-gauge-transformation statement.

**Ignoring trace normalization.** The integer condition applies to the correctly normalized invariant form. Rescale the trace and the numerical value of $k$ changes.

**Ignoring spin structure.** Abelian and quotient-group Chern–Simons theories can distinguish spin and non-spin theories. Odd diagonal $K$-matrix entries are the classic warning sign.

**Forgetting boundaries.** On a manifold with boundary, Chern–Simons theory is not gauge invariant by itself unless boundary conditions or boundary degrees of freedom are specified.

**Calling all real $k$ allowed because the equation of motion is $F=0$.** The equation of motion is local. Level quantization is global and quantum.

## Relations to other pages

This page is a model calculation for the Topological Terms and Topological QFT chapters. It relies on the theta-term calculation, the Chern–Simons theory page, and the line-operator algebra page. It also prepares for anomaly inflow, Wess–Zumino consistency, WZW terms, SymTFT examples, response theory, and fractional quantum Hall effective actions.

The Wess–Zumino consistency-condition page is the companion calculation: Chern–Simons descent explains why the anomaly produced on a boundary obeys a Lie-algebra consistency equation.

## Research status

The integer quantization of compact Chern–Simons levels is settled. The modern frontier is not the basic quantization argument; it is the refined global data: spin versus non-spin theories, non-simply connected gauge groups, one-form symmetries, transparent lines, extended TQFT structure, anomalous boundaries, and categorical line-operator data.

## Exercises

### Exercise 1: Gauge invariance of the exponent

Suppose a functional obeys

$$
I[A^g]=I[A]+2\pi n(g),\qquad n(g)\in\mathbb Z.
$$

For $S=kI[A]$, show that $e^{iS}$ is invariant under all such transformations if and only if $k\in\mathbb Z$.

<details><summary><strong>Solution</strong></summary>

The exponent changes by

$$
e^{iS[A^g]}=e^{ikI[A]}e^{2\pi i k n(g)}.
$$

For this to equal $e^{ikI[A]}$ for all integers $n(g)$, we need

$$
e^{2\pi i k n}=1
$$

for all $n\in\mathbb Z$. Taking $n=1$ gives $e^{2\pi i k}=1$, hence $k\in\mathbb Z$.

</details>

### Exercise 2: The equation of motion

Vary the non-Abelian Chern–Simons action on a closed three-manifold and show that the equation of motion is $F=0$.

<details><summary><strong>Solution</strong></summary>

The variation of the Chern–Simons three-form is

$$
\delta\omega_3(A)=2\operatorname{tr}(\delta A\wedge F)+d(\cdots).
$$

On a closed manifold the total derivative integrates to zero. Thus

$$
\delta S_{\mathrm{CS}}=\frac{k}{2\pi}\int_M\operatorname{tr}(\delta A\wedge F).
$$

Since $\delta A$ is arbitrary, the Euler–Lagrange equation is

$$
F=0.
$$

</details>

### Exercise 3: Boundary anomaly intuition

Explain why the same Chern–Simons action can be gauge-invariant on a closed manifold but anomalous on a manifold with boundary.

<details><summary><strong>Solution</strong></summary>

Under an infinitesimal gauge transformation, the Chern–Simons variation is a total derivative:

$$
\delta_\lambda S_{\mathrm{CS}}=\int_M d(\cdots).
$$

If $M$ is closed, this integral vanishes. If $M$ has boundary, Stokes’s theorem gives a boundary contribution

$$
\int_{\partial M}(\cdots).
$$

This boundary variation must be canceled by boundary degrees of freedom, boundary conditions, or an additional counterterm. In anomaly-inflow language, it cancels the anomaly of the boundary theory.

</details>

### Exercise 4: Spin warning for Abelian Chern–Simons theory

Why is the statement “$k$ is an integer” incomplete for a single compact $U(1)$ Chern–Simons theory?

<details><summary><strong>Solution</strong></summary>

Integer $k$ is the basic compact-gauge-field quantization. But whether the theory is defined on arbitrary oriented three-manifolds or only on spin three-manifolds depends on additional global data. In the usual Abelian $K$-matrix normalization, an odd diagonal level describes a spin theory; a bosonic non-spin theory has even diagonal entries. Thus one must specify not only $k$, but also the spin/non-spin nature and the allowed line lattice.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, especially §§69–77 for non-Abelian gauge theory, BRST, and anomalies; §82 for Wilson loops; and §93 for instantons and theta vacua.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chs. 25 and 30 for Yang–Mills theory, Wilson lines, and anomalies.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, ch. 8 for topological field theory, theta terms, Wess–Zumino terms, and Chern–Simons terms.
- E. Witten, “Quantum Field Theory and the Jones Polynomial,” *Communications in Mathematical Physics* **121** (1989).
- S. Elitzur, G. Moore, A. Schwimmer, and N. Seiberg, “Remarks on the Canonical Quantization of the Chern–Simons–Witten Theory,” *Nuclear Physics B* **326** (1989).
- X.-G. Wen, *Quantum Field Theory of Many-Body Systems*, for Abelian Chern–Simons $K$-matrix conventions in topological phases.

## Version history

- 2026-06-23: Initial polished model-library page. Fixed Hermitian-generator convention, large-gauge-transformation derivation, Abelian spin caveat, boundary inflow explanation, and exercises.
