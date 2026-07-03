---
title: "Kramers–Wannier Duality"
description: "Explains Kramers–Wannier duality as the order–disorder duality of the two-dimensional Ising model, its finite-gauging interpretation, and its topological defect realization at criticality."
sidebar:
  label: "Kramers–Wannier Duality"
  order: 5
level: Advanced
status: "Polished draft"
source: "Kramers–Wannier; Kadanoff–Ceva; Fröhlich–Fuchs–Runkel–Schweigert; Gaiotto–Kapustin–Seiberg–Willett; standard Ising CFT and statistical field theory references."
topics:
  - Kramers–Wannier duality
  - Ising model
  - order and disorder operators
  - duality defects
  - non-invertible symmetry
  - finite symmetry gauging
canonicalTopics:
  - kramers-wannier-duality
  - order-disorder-duality
  - ising-duality-defect
  - non-invertible-duality-defect
researchStatus:
  established:
    - "Kramers–Wannier duality is the standard order–disorder duality of the two-dimensional Ising model and maps high-temperature and low-temperature descriptions."
    - "At the critical point, the duality is implemented by a topological defect whose fusion is non-invertible."
  active:
    - "Modern work uses Kramers–Wannier duality as the basic laboratory for non-invertible symmetry, categorical defects, generalized gauging, and lattice topological defects."
---

## Summary

**Kramers–Wannier duality** is the order–disorder duality of the two-dimensional Ising model. It exchanges low-temperature ordered physics with high-temperature disordered physics and maps spin variables on a lattice to disorder variables on the dual lattice.

For the square-lattice Ising model with coupling $K$, the dual coupling $K^*$ is defined by

$$
\sinh(2K)\sinh(2K^*)=1.
$$

The self-dual point satisfies

$$
\sinh(2K_c)=1.
$$

At the critical point, Kramers–Wannier duality becomes a topological defect $\mathcal N$. This defect is not an ordinary invertible symmetry line. Its hallmark fusion rule in the critical Ising theory is

$$
\mathcal N\times \mathcal N=1+\eta,
$$

where $\eta$ is the ordinary spin-flip symmetry line. The plus sign is the whole story: fusing two duality defects gives a sum of sectors, not a single inverse.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A diagram showing Kramers–Wannier duality exchanging spins on a lattice with disorder variables on the dual lattice, and becoming a non-invertible topological defect at criticality.](/figures/symmetry-anomalies-topology/kramers-wannier-duality.svg)

<figcaption>

Kramers–Wannier duality has three compatible faces: a high-temperature/low-temperature lattice map, an order–disorder operator map, and at criticality a topological duality defect $\mathcal N$ with fusion $\mathcal N^2=1+\eta$.

</figcaption>
</figure>

This page treats Kramers–Wannier duality as low-dimensional symmetry technology: a concrete bridge between finite gauging, disorder operators, lattice duality, and non-invertible symmetry.

## Prerequisites

You should know [Gauging Finite Symmetries](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/gauging-finite-symmetries/), [Orbifolds](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/orbifolds/), [Disorder Operators](/symmetry-anomalies-topology/defects-extended-operators/disorder-operators/), and [Duality Defects](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/duality-defects/).

You do not need the exact Onsager solution. The page uses only the Ising partition function, the idea of a dual lattice, order and disorder operators, and topological defect fusion.

## Core idea

The two-dimensional Ising model has spin variables

$$
\sigma_i=\pm1
$$

on lattice sites, with partition function

$$
Z(K)=\sum_{\{ \sigma_i \}}
\exp\left(K\sum_{\langle ij\rangle}\sigma_i\sigma_j\right).
$$

At low temperature, neighboring spins prefer to align. The natural variables are ordered domains and domain walls. At high temperature, the expansion is in small correlated clusters. Kramers–Wannier duality says that the high-temperature expansion of one Ising model can be reorganized as the low-temperature expansion of another Ising model on the dual lattice.

The duality is not just a clever series identity. It exchanges the order parameter with a disorder operator:

$$
\text{spin order }\sigma
\quad \longleftrightarrow \quad
\text{disorder operator }\mu.
$$

The disorder operator creates a branch cut or line across which the sign of the Ising coupling is flipped. Moving the cut without moving its endpoints does not change the physics. That topological behavior is the seed of the duality-defect viewpoint.

## Lattice duality

On the square lattice, the Ising partition function can be expanded in two complementary ways.

In the high-temperature expansion, use

$$
e^{K\sigma_i\sigma_j}
=
\cosh K\left(1+v\sigma_i\sigma_j\right),
\qquad
v=\tanh K.
$$

After summing over spins, only configurations in which an even number of occupied edges meet at each site survive. These are closed loops on the lattice.

In the low-temperature expansion, domain walls separating $+$ and $-$ spin domains live on the dual lattice. The weight of a domain wall is controlled by

$$
e^{-2K^*}.
$$

Matching the loop weights gives

$$
\tanh K=e^{-2K^*},
$$

which is equivalent to

$$
\sinh(2K)\sinh(2K^*)=1.
$$

Thus the high-temperature expansion of the model at $K$ is mapped to the low-temperature expansion of the dual model at $K^*$, up to an overall normalization and boundary-condition subtleties.

:::note[Source note: self-duality and criticality]
The self-dual equation identifies a candidate critical point. To conclude that it is the critical point of the square-lattice Ising model, one also uses the existence and uniqueness of the transition. The duality relation alone is not a universal proof strategy for every lattice model.
:::

## Order and disorder operators

The spin field $\sigma$ is an order operator. A nonzero expectation value

$$
\langle \sigma \rangle\neq0
$$

signals the ordered phase with spontaneously broken spin-flip symmetry.

The disorder operator $\mu$ is defined differently. In the lattice model, insert a line $\gamma$ on the dual lattice and flip the sign of the Ising coupling on every edge crossed by $\gamma$. The endpoint of this line is a disorder insertion. Moving $\gamma$ without moving its endpoint changes variables in the spin sum and leaves correlation functions unchanged, except when the line crosses spin insertions.

The order–disorder relation is therefore topological in the same sense as symmetry-defect crossing. The line attached to $\mu$ is not a local polynomial in spins; it is a prescription for changing the allowed weights in the path integral.

A schematic mixed correlator has branch-cut behavior:

$$
\sigma \text{ encircles } \mu
\quad \Longrightarrow \quad
\text{a sign is produced}.
$$

This is the lattice ancestor of mutual locality and defect-crossing rules in two-dimensional QFT.

## The finite-gauging interpretation

Kramers–Wannier duality can be understood as gauging the spin-flip $\mathbb Z_2$ symmetry.

Let $T(K)$ be the Ising model at coupling $K$. Gauging the spin-flip symmetry gives a dual Ising model at coupling $K^*$:

$$
T(K)/\mathbb Z_2 \simeq T(K^*),
$$

with normalization and boundary-condition caveats. At the self-dual point $K=K^*$, gauging maps the theory to itself. This is why the critical Ising model has a duality defect.

This interpretation connects the Ising duality to the previous page:

$$
\text{Kramers–Wannier duality}
=
\text{finite }\mathbb Z_2\text{ gauging, specialized to the Ising family}.
$$

Away from criticality, the duality relates two different couplings. At criticality, it becomes an operation inside a single conformal field theory.

## The critical defect

At the critical point, the Ising model is described by the Ising CFT. The spin-flip symmetry is represented by an invertible topological line $\eta$ obeying

$$
\eta^2=1.
$$

The Kramers–Wannier duality is represented by a topological defect $\mathcal N$. Its fusion rules include

$$
\eta\times \mathcal N=\mathcal N\times \eta=\mathcal N,
$$

and

$$
\mathcal N\times \mathcal N=1+\eta.
$$

Thus $\mathcal N$ has quantum dimension

$$
d_{\mathcal N}=\sqrt2.
$$

It cannot have an inverse, because an inverse would fuse with it to give a single identity defect. Instead, two copies of $\mathcal N$ produce a sum of the trivial sector and the spin-flip sector.

This is the canonical baby example of a non-invertible symmetry.

## What the defect does

The duality defect maps order data to disorder data. If an order field crosses the duality defect, it becomes a disorder field; if a disorder field crosses it, it becomes order data in the dual frame. More carefully, the crossing rules depend on whether one works in a bosonic, fermionic, extended, or defect-completed presentation of the Ising theory. But the physical message is stable:

$$
\mathcal N \text{ exchanges order and disorder descriptions.}
$$

The defect is topological at criticality. It can be moved freely through correlation functions until it crosses operator insertions or other defects. Sliding it through a correlator produces duality relations among correlators.

This is a non-invertible Ward identity. It is not generated by integrating a Noether current. It is generated by deforming a topological defect network.

## Boundary conditions

Kramers–Wannier duality also acts on boundary conditions. In the Ising model, standard boundary conditions include fixed $+$, fixed $-$, and free. Under the duality, fixed and free boundary conditions are exchanged in an appropriate sense, while superpositions or boundary-changing operators may be required depending on the precise categorical setup.

This is a useful diagnostic: if a proposed duality action works on local bulk fields but fails on boundary conditions, it has not captured the full QFT. Defects, boundaries, and Hilbert-space sectors are part of the theory’s global data.

## Continuum Majorana viewpoint

The critical Ising CFT is also the theory of a massless Majorana fermion. Perturbing by the energy operator corresponds to adding a Majorana mass. The two signs of the mass describe the ordered and disordered phases:

$$
m>0 \quad \text{and} \quad m<0
$$

are separated by the critical point $m=0$, with conventions depending on normalization. Kramers–Wannier duality exchanges the two sides.

This is a continuum reminder that duality is not merely a lattice trick. The lattice construction gives a microscopic definition; the continuum limit packages it as an operation on phases, defects, and relevant perturbations.

## Relation to non-invertible symmetry

Kramers–Wannier duality is often the first honest example where “symmetry” must be broader than “group action.” The duality defect has a fusion rule, is topological at criticality, and constrains observables. But it is not invertible.

The structure is:

| Object | Meaning |
|---|---|
| $1$ | trivial topological defect |
| $\eta$ | spin-flip symmetry defect |
| $\mathcal N$ | Kramers–Wannier duality defect |
| $\eta^2=1$ | ordinary invertible symmetry |
| $\eta\mathcal N=\mathcal N$ | spin flip is absorbed by the duality defect |
| $\mathcal N^2=1+\eta$ | non-invertible fusion |

This tiny fusion table is the reason the Ising model appears everywhere in discussions of non-invertible symmetry. It is simple enough to compute and rich enough to teach the concept.

## Relation to orbifolds and gauging

The critical Ising model is self-dual under gauging its spin-flip symmetry. In the language of two-dimensional CFT, it is closely related to a $\mathbb Z_2$ orbifold construction. In the language of topological defects, the gauging interface becomes the duality defect.

This explains why the same object appears under different names:

$$
\text{finite gauging interface}
\quad \leftrightarrow \quad
\text{orbifold interface}
\quad \leftrightarrow \quad
\text{Kramers–Wannier defect}.
$$

The precise statement depends on boundary conditions, spin structures, and whether one works with the bosonic Ising model, fermionic Majorana theory, or an extended theory containing both order and disorder fields. The conceptual relation is robust: Kramers–Wannier duality is finite gauging made visible in the Ising model.

## Common pitfalls

**“Kramers–Wannier duality is an ordinary symmetry everywhere.”** Away from the self-dual point it maps one coupling to another. At the critical self-dual point it becomes a topological duality defect of a single theory.

**“Self-duality alone proves criticality.”** It identifies a candidate transition point. Additional input is needed to conclude that this is the unique critical point.

**“The disorder operator is a local function of spins.”** It is defined by changing couplings along a line or imposing a branch condition. Its endpoint is local in the continuum sense only after including the appropriate defect data.

**“The duality defect has an inverse.”** It does not. Its square is $1+\eta$, not $1$.

**“Order and disorder fields always live in the same local operator algebra.”** This depends on the presentation. One may need an extended operator algebra, defect endpoints, or fermionic/spin-structure data to discuss both simultaneously.

**“The Ising example is just a toy.”** It is a toy in the best possible sense: simple, exact, and structurally representative of finite gauging and non-invertible defects.

## Relations to other pages

[Gauging Finite Symmetries](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/gauging-finite-symmetries/) explains the operation that produces the dual Ising description.

[Orbifolds](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/orbifolds/) gives the sector-sum language that underlies finite $\mathbb Z_2$ gauging.

[Kramers–Wannier Duality Defect](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/kramers-wannier-duality-defect/) treats the same object from the categorical/non-invertible symmetry chapter.

[Disorder Operators](/symmetry-anomalies-topology/defects-extended-operators/disorder-operators/) explains the general operator logic behind disorder insertions.

[Generalized Symmetry Breaking](/symmetry-anomalies-topology/higher-form-generalized-symmetries/generalized-symmetry-breaking/) connects order/disorder diagnostics to symmetry realization.

## Research status

Kramers–Wannier duality in the two-dimensional Ising model is established classic physics. Its modern interpretation as a topological non-invertible defect at criticality is also standard in current symmetry language.

Active work uses this example as the gateway to broader questions: lattice realizations of non-invertible defects, categorical symmetries in rational CFT, generalized gauging, fermionic refinements, higher-dimensional analogues, and SymTFT descriptions of duality interfaces.

## Exercises

### Exercise 1: Dual coupling relation

Starting from

$$
\tanh K=e^{-2K^*},
$$

show that

$$
\sinh(2K)\sinh(2K^*)=1.
$$

<details><summary><strong>Solution</strong></summary>

Let $v=\tanh K=e^{-2K^*}$. Then

$$
\sinh(2K)=\frac{2\tanh K}{1-\tanh^2K}=\frac{2v}{1-v^2}.
$$

Since $v=e^{-2K^*}$,

$$
\sinh(2K^*)=\frac{e^{2K^*}-e^{-2K^*}}{2}=\frac{1/v-v}{2}=\frac{1-v^2}{2v}.
$$

Multiplying gives

$$
\sinh(2K)\sinh(2K^*)=1.
$$

</details>

### Exercise 2: Self-dual coupling

Solve the self-duality equation

$$
\sinh(2K_c)=1
$$

for $K_c$.

<details><summary><strong>Solution</strong></summary>

The equation gives

$$
\frac{e^{2K_c}-e^{-2K_c}}{2}=1.
$$

Let $x=e^{2K_c}$. Then

$$
x-\frac1x=2,
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
K_c=\frac12\log(1+\sqrt2).
$$

</details>

### Exercise 3: Non-invertibility from fusion

Use

$$
\mathcal N^2=1+\eta
$$

to explain why $\mathcal N$ cannot be an invertible symmetry defect.

<details><summary><strong>Solution</strong></summary>

If $\mathcal N$ were invertible, there would be a defect $\mathcal N^{-1}$ with

$$
\mathcal N\times \mathcal N^{-1}=1.
$$

In particular, fusion with $\mathcal N$ would map simple sectors to single simple sectors. But the square of $\mathcal N$ is not a single defect; it is the direct sum

$$
1+\eta.
$$

Thus $\mathcal N$ has no inverse under fusion. Its quantum dimension is $\sqrt2$, not $1$.

</details>

### Exercise 4: Projection from two duality defects

Physically interpret why two Kramers–Wannier duality operations produce both the identity sector and the spin-flip sector.

<details><summary><strong>Solution</strong></summary>

A Kramers–Wannier operation is closely related to gauging the spin-flip $\mathbb Z_2$ symmetry. Gauging and then ungauging involves summing over sectors and projecting onto gauge-invariant data. In the defect language, the two duality defects leave a residual choice: the trivial sector or a spin-flip line between them. This residual topological line is exactly the $\eta$ term in

$$
\mathcal N^2=1+\eta.
$$

</details>

## References

- H. Kramers and G. Wannier, “Statistics of the Two-Dimensional Ferromagnet,” for the original lattice duality.
- L. Kadanoff and H. Ceva, “Determination of an Operator Algebra for the Two-Dimensional Ising Model,” for order and disorder operators.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, for the Ising CFT and its operator/duality data.
- J. Fröhlich, J. Fuchs, I. Runkel, and C. Schweigert, “Kramers–Wannier Duality from Conformal Defects,” for the defect-theoretic interpretation.
- D. Aasen, R. S. K. Mong, and P. Fendley, “Topological Defects on the Lattice: I. The Ising Model,” for lattice topological-defect constructions.
- S.-H. Shao, “What’s Done Cannot Be Undone,” for a modern non-invertible-symmetry introduction using Kramers–Wannier duality.

## Version history

- **2026-06-23:** Initial polished draft. Added lattice duality, order/disorder operators, finite-gauging interpretation, critical duality defect, non-invertible fusion, and exercises.
