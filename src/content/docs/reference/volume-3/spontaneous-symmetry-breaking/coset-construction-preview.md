---
title: "Coset Construction Preview"
description: "Introduces the coset construction for Goldstone effective field theories, including nonlinear symmetry action, Maurer–Cartan forms, invariant derivative expansions, examples, and caveats for spacetime symmetry breaking."
sidebar:
  label: "Coset Construction Preview"
  order: 5
level: Advanced
status: "Polished draft"
source: "Callan–Coleman–Wess–Zumino; Coleman–Wess–Zumino; Coleman on secret symmetry and soft pions; Weinberg Vol. II; Burgess on nonlinear realizations; Watanabe–Murayama for nonrelativistic refinements."
topics:
  - coset construction
  - nonlinear realization
  - Goldstone effective theory
  - Maurer–Cartan form
  - vacuum manifold
  - spontaneous symmetry breaking
  - chiral Lagrangian
  - nonlinear sigma model
canonicalTopics:
  - coset-construction
  - nonlinear-realization
  - maurer-cartan-form
  - goldstone-effective-field-theory
  - vacuum-manifold
  - ccwz
  - chiral-lagrangian
researchStatus:
  established:
    - "For spontaneously broken internal symmetries, the coset construction gives a systematic and universal way to build local effective actions for Goldstone fields."
    - "The leading derivative terms are fixed by G-invariant geometry on G/H together with H-invariant tensors and possible Wess–Zumino terms."
  active:
    - "Extensions to spacetime symmetries, finite density, defects, higher-form symmetries, non-invertible symmetries, and systems with subsystem constraints remain active and context-sensitive."
---

## Summary

The **coset construction** is the systematic way to write the low-energy effective theory of Goldstone modes when a continuous symmetry is spontaneously broken:

$$
G\longrightarrow H.
$$

The unbroken group $H$ preserves the selected vacuum. The broken directions are coordinates on the coset space

$$
G/H.
$$

Instead of guessing how Goldstone fields transform, one introduces a coset representative

$$
\xi(\pi)=e^{i\pi^aX_a/f},
$$

where $X_a$ are broken generators. A global transformation $g\in G$ acts by

$$
g\xi(\pi)=\xi(\pi')h(g,\pi),
\qquad
h(g,\pi)\in H.
$$

This equation is the heart of nonlinear realization. The transformed Goldstone field $\pi'$ is generally a nonlinear function of $g$ and $\pi$, while the compensator $h(g,\pi)$ tells matter fields how to transform under the unbroken group.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A flow diagram for the coset construction. The breaking pattern G to H determines a coset representative xi(pi). Its nonlinear transformation law gives a compensator h. The Maurer-Cartan form splits into broken vielbein pieces and unbroken connection pieces. These provide H-covariant building blocks for an invariant derivative expansion, with extra allowed Wess-Zumino, anomaly, spurion, and spacetime-symmetry refinements.](/figures/symmetry-anomalies-topology/coset-construction-flow.svg)

<figcaption>

The coset construction packages Goldstone EFT into a geometric recipe. Choose coordinates on $G/H$, compute the Maurer–Cartan form, split it into broken and unbroken pieces, and build $H$-invariant derivative terms. The result realizes the full group $G$ nonlinearly, even though only $H$ acts linearly on the fields at the origin.

</figcaption>
</figure>

This page is a preview. It gives enough of the construction to recognize chiral Lagrangians, nonlinear sigma models, superfluid EFTs, and Wess–Zumino terms later, without trying to replace a full EFT chapter.

## Prerequisites

Read [Goldstone Modes](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-modes/) first. You should also know [Symmetry Groups and Representations](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-groups-and-representations/), [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/), [Symmetry Algebras](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-algebras/), and [Order Parameters](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/order-parameters/).

For the geometric language, it helps to know the ideas of a manifold, tangent space, and connection. The page is written so that the formulas can still be used before a full differential-geometry course.

## Core idea

A broken symmetry is still a symmetry of the theory. It is just not linearly realized on the selected vacuum. The coset construction solves the following problem:

> Given $G\to H$, write the most general local low-energy action for Goldstone fields that realizes $G$.

The answer has three steps.

First, split the Lie algebra into unbroken and broken generators:

$$
\mathfrak g=\mathfrak h\oplus\mathfrak k,
\qquad
T_i\in\mathfrak h,
\qquad
X_a\in\mathfrak k.
$$

Second, introduce a coset representative

$$
\xi(\pi)=e^{i\pi^aX_a/f}.
$$

The fields $\pi^a(x)$ are Goldstone coordinates. The scale $f$ is inserted so that $\pi^a$ has the usual mass dimension in four-dimensional relativistic examples.

Third, compute the Maurer–Cartan form

$$
-i\xi^{-1}d\xi=e^aX_a+\omega^iT_i.
$$

The pieces $e^a$ are the covariant one-forms associated with broken directions; the pieces $\omega^i$ behave like an $H$ connection. In components,

$$
e^a=e_\mu^{\ a}dx^\mu,
\qquad
\omega^i=\omega_\mu^{\ i}dx^\mu.
$$

Then build the effective Lagrangian from $H$-invariant contractions of $e_\mu^{\ a}$, covariant derivatives, matter fields, and possible Wess–Zumino terms.

## Setup and conventions

We take generators to be Hermitian and write group elements as exponentials $e^{i\alpha^AT_A}$. The commutators are

$$
[T_A,T_B]=if_{AB}^{\ \ C}T_C.
$$

The unbroken generators are $T_i$, and the broken generators are $X_a$. Thus

$$
[T_i,T_j]=if_{ij}^{\ \ k}T_k,
$$

while the mixed and broken commutators take the schematic form

$$
[T_i,X_a]=if_{ia}^{\ \ b}X_b+if_{ia}^{\ \ j}T_j,
$$

$$
[X_a,X_b]=if_{ab}^{\ \ c}X_c+if_{ab}^{\ \ i}T_i.
$$

For many familiar internal-symmetry examples one chooses a reductive splitting, so

$$
[T_i,X_a]=if_{ia}^{\ \ b}X_b.
$$

This means the broken generators transform among themselves under $H$. If the coset is also symmetric, then

$$
[X_a,X_b]\subset\mathfrak h.
$$

Symmetric cosets are common and technically pleasant, but the construction does not require every coset to be symmetric.

:::note[Convention-sensitive source note]
Some references define the Maurer–Cartan form as $\xi^{-1}d\xi=i(e^aX_a+\omega^iT_i)$ rather than $-i\xi^{-1}d\xi=e^aX_a+\omega^iT_i$. This page uses the latter so that $e^a=d\pi^a/f+O(\pi^2)$ for $\xi=e^{i\pi^aX_a/f}$. If your signs differ, check the placement of $i$ before comparing formulas for currents or Wess–Zumino terms.
:::

## Why cosets appear

Let $|\Omega\rangle$ be a chosen broken vacuum. The subgroup $H\subset G$ preserves it. Acting with a general element $g\in G$ may move the vacuum, but acting with an element of $H$ does not produce a new point on the vacuum manifold:

$$
g|\Omega\rangle
\sim
gh|\Omega\rangle,
\qquad h\in H.
$$

Therefore the physically distinct symmetry-related vacua are labeled by equivalence classes

$$
[g]\in G/H.
$$

Goldstone fields are spacetime-dependent choices of such equivalence classes:

$$
x\mapsto [g(x)]\in G/H.
$$

This is why $G/H$ is not a decorative phrase. It is the target space of the Goldstone fields.

For internal symmetry breaking, the number of local coordinates on $G/H$ is

$$
\dim(G/H)=\dim G-\dim H=n_{\text{broken}}.
$$

In a Lorentz-invariant vacuum, these coordinates correspond to the Goldstone bosons counted by the Goldstone theorem.

## Nonlinear symmetry action

A linear representation acts on fields by matrices. Goldstone fields usually do not transform this simply. Their transformation law is inherited from multiplication in $G$ followed by returning to the chosen coset representative.

Choose a representative $\xi(\pi)$ for each point of $G/H$. For $g\in G$, the product $g\xi(\pi)$ is generally not in the chosen representative form. One restores the chosen form by multiplying on the right by an element of $H$:

$$
g\xi(\pi)=\xi(\pi')h(g,\pi).
$$

This defines both $\pi'$ and the compensator $h(g,\pi)$.

For an infinitesimal broken transformation near $\pi=0$, the leading behavior is a shift:

$$
\pi^a\mapsto\pi^a+f\epsilon^a+O(\epsilon\pi).
$$

For an infinitesimal unbroken transformation, the Goldstones rotate in a representation of $H$:

$$
\pi^a\mapsto \pi^a+\epsilon^i f_{ib}^{\ \ a}\pi^b+O(\pi^2).
$$

Thus $H$ is linearly visible at the origin, while the broken part of $G$ acts nonlinearly.

This is the precise meaning of saying that the symmetry is nonlinearly realized.

## The Maurer–Cartan form

The Maurer–Cartan form is

$$
\Theta=-i\xi^{-1}d\xi.
$$

It is Lie-algebra valued, so it can be split into broken and unbroken components:

$$
\Theta=e^aX_a+\omega^iT_i.
$$

Under $g\in G$, with

$$
g\xi(\pi)=\xi(\pi')h,
$$

the Maurer–Cartan form transforms as

$$
\Theta(\pi')
=
h\Theta(\pi)h^{-1}-i hdh^{-1}.
$$

The broken piece $e^aX_a$ transforms covariantly under $H$. The unbroken piece $\omega^iT_i$ transforms like an $H$ connection. This is exactly what one needs to build invariant actions.

At leading order in $\pi$,

$$
e^a=\frac{d\pi^a}{f}+O(\pi^2),
$$

so the usual kinetic term is recovered from contracting $e_\mu^{\ a}$ with itself.

## Building the leading effective Lagrangian

The leading relativistic two-derivative Goldstone Lagrangian has the schematic form

$$
\mathcal L_2
=\frac{f^2}{2}\kappa_{ab}e_\mu^{\ a}e^{\mu b},
$$

where $\kappa_{ab}$ is an $H$-invariant symmetric tensor on the broken-generator space. $H$-invariance means

$$
\kappa_{ab}D(h)^a_{\ c}D(h)^b_{\ d}=\kappa_{cd}.
$$

For an irreducible broken representation, symmetry often fixes $\kappa_{ab}$ up to one overall constant. If the broken generators split into several irreducible $H$ representations, there can be several independent decay constants.

In coordinate language, the same Lagrangian is

$$
\mathcal L_2
=\frac12 g_{ab}(\pi)\partial_\mu\pi^a\partial^\mu\pi^b,
$$

where $g_{ab}(\pi)$ is a $G$-invariant metric on $G/H$.

Higher-derivative terms are built similarly:

$$
\mathcal L_{\text{eff}}
=\mathcal L_2+\mathcal L_4+\mathcal L_6+\cdots.
$$

The derivative expansion is valid at momenta small compared with the mass of the non-Goldstone modes or the cutoff scale of the EFT.

## Example: broken U(1)

Let

$$
G=U(1),
\qquad
H=\{1\}.
$$

There is one broken generator $Q$. The coset representative is

$$
\xi(\pi)=e^{i\pi Q/f}.
$$

The Maurer–Cartan form is

$$
-i\xi^{-1}d\xi=\frac{d\pi}{f}Q.
$$

Thus

$$
e=\frac{d\pi}{f}.
$$

The leading invariant Lagrangian is

$$
\mathcal L_2
=\frac{f^2}{2}e_\mu e^\mu
=\frac12\partial_\mu\pi\partial^\mu\pi.
$$

The broken $U(1)$ acts as

$$
\pi\mapsto \pi+f\alpha.
$$

This is the simplest Goldstone shift symmetry.

## Example: O(N) to O(N−1)

For

$$
O(N)\longrightarrow O(N-1),
$$

the coset is the sphere

$$
O(N)/O(N-1)\simeq S^{N-1}.
$$

One can represent the Goldstone fields by a unit vector

$$
n^i(x)n^i(x)=1.
$$

The leading invariant Lagrangian is

$$
\mathcal L_2
=\frac{f^2}{2}\partial_\mu n^i\partial^\mu n^i.
$$

This is the nonlinear sigma model on $S^{N-1}$. The constraint removes one component, leaving $N-1$ Goldstone coordinates.

Expanding near the north pole,

$$
n^a=\frac{\pi^a}{f}+O(\pi^3),
\qquad
n^N=\sqrt{1-\frac{\pi^a\pi^a}{f^2}},
$$

gives

$$
\mathcal L_2
=\frac12\partial_\mu\pi^a\partial^\mu\pi^a
+\frac{1}{2f^2}\frac{(\pi^a\partial_\mu\pi^a)^2}{1-\pi^b\pi^b/f^2}.
$$

The nonlinear interactions are fixed by the geometry of the sphere.

## Example: chiral symmetry breaking

For QCD with idealized massless quarks, the chiral symmetry breaking pattern is

$$
SU(N_f)_L\times SU(N_f)_R
\longrightarrow
SU(N_f)_V.
$$

The Goldstone manifold is isomorphic to $SU(N_f)$. A standard field is

$$
U(x)=e^{2i\pi^a(x)T^a/f_\pi}.
$$

It transforms linearly under the left and right groups:

$$
U\mapsto g_LUg_R^{-1}.
$$

The leading invariant Lagrangian is

$$
\mathcal L_2
=\frac{f_\pi^2}{4}\operatorname{tr}\big(\partial_\mu U^\dagger\partial^\mu U\big).
$$

This compact expression contains the kinetic terms and leading derivative interactions of the pions. Small quark masses can be included as spurions, producing pseudo-Goldstone masses. Anomalies require Wess–Zumino–Witten terms, which are not visible from the metric on $G/H$ alone.

:::note[Why this example looks different]
The chiral field $U$ is a convenient coordinate on the coset, not a fundamental ultraviolet scalar. The transformation law $U\mapsto g_LUg_R^{-1}$ is simple because the coset has a special group-manifold structure. In a generic coset $G/H$, the compensator $h(g,\pi)$ is unavoidable.
:::

## Matter fields and the compensator

Suppose a matter field $\psi$ transforms in a representation $R$ of the unbroken group $H$. Under a full $G$ transformation, it transforms using the compensator:

$$
\psi(x)\mapsto R\big(h(g,\pi(x))\big)\psi(x).
$$

This looks strange at first because $h$ depends on the Goldstone field. But it is exactly what is needed for the nonlinear realization of $G$.

The unbroken part of the Maurer–Cartan form, $\omega_\mu^iT_i$, defines an $H$-covariant derivative:

$$
D_\mu\psi
=
\partial_\mu\psi+i\omega_\mu^iR(T_i)\psi.
$$

Then terms such as

$$
\bar\psi i\gamma^\mu D_\mu\psi
$$

can be made invariant under the full group $G$, even though $\psi$ transforms linearly only under $H$.

This is one reason the coset construction is more than a way of writing Goldstone kinetic terms. It also tells you how non-Goldstone matter couples to the broken symmetry.

## Wess–Zumino terms

Not every allowed term is an ordinary invariant made by contracting local Maurer–Cartan components. Some terms are invariant only up to a total derivative. These are **Wess–Zumino terms**.

A schematic example is a term whose variation is

$$
\delta S=\int d\alpha
$$

for some local expression $\alpha$. The equations of motion and path integral can still be invariant when the exponentiated action is well defined.

Wess–Zumino terms are essential in many places:

- chiral Lagrangians and anomaly matching;
- ferromagnets and type-B Goldstone modes;
- Chern–Simons-like effective theories;
- boundary theories related to anomaly inflow.

The ordinary coset metric determines derivative kinetic terms. Wess–Zumino terms encode additional topology and anomaly data.

## Spurions and explicit breaking

Small explicit breaking can be included by introducing spurion fields that transform under $G$ and then freezing them to fixed values. For example, in the chiral Lagrangian, the quark mass matrix $M$ is treated as a spurion transforming as

$$
M\mapsto g_LMg_R^{-1}.
$$

Then one may write

$$
\mathcal L_{\text{mass}}
=\frac{f_\pi^2B_0}{2}\operatorname{tr}(MU^\dagger+UM^\dagger).
$$

After setting $M$ to the physical quark mass matrix, chiral symmetry is explicitly broken and the Goldstone bosons acquire masses. The spurion method keeps track of which terms are allowed and how small masses enter observables.

This is the EFT version of the statement:

$$
\text{explicit breaking controls pseudo-Goldstone masses}.
$$

## Relation to nonlinear sigma models

A nonlinear sigma model is a field theory whose fields are maps from spacetime into a target manifold:

$$
\phi:M_d\to\mathcal M.
$$

For internal symmetry breaking, the target manifold is often

$$
\mathcal M=G/H.
$$

The leading action is the energy of the map measured by a target-space metric:

$$
S=\frac12\int d^dx\,g_{ab}(\phi)\partial_\mu\phi^a\partial^\mu\phi^b.
$$

The coset construction explains why this sigma model has a nonlinear $G$ symmetry and which target-space metrics and extra terms are allowed. Conversely, the sigma-model language makes clear that Goldstone interactions are geometric.

## When spacetime symmetries are broken

The cleanest coset construction is for internal symmetries. Spacetime symmetries introduce extra complications because translations act on coordinates, not just on fields.

For spacetime symmetry breaking, a coset representative often includes spacetime translations explicitly:

$$
\xi(x,\pi)=e^{ix^\mu P_\mu}e^{i\pi^a(x)X_a}.
$$

Then the Maurer–Cartan form contains a vielbein-like part, covariant derivatives of Goldstone fields, and connections for unbroken spacetime symmetries.

A new phenomenon appears: some Goldstone fields can be **inessential**. They are removed by inverse-Higgs constraints when commutators of unbroken translations with broken generators relate one broken direction to derivatives of another. Schematically, if

$$
[P_\mu,X_a]\sim X_b+\cdots,
$$

then the Goldstone for $X_b$ may be expressible in terms of a derivative of the Goldstone for $X_a$.

This is why crystals do not have independent low-energy Goldstone fields for every broken rotation generator. The rotational Goldstone data are contained in gradients of the displacement fields.

:::caution
For spacetime symmetries, the coset construction is a powerful tool, not a one-line theorem. The relation between broken generators, essential Goldstones, inverse-Higgs constraints, and universal low-energy dynamics depends on locality, translations, the state, and the physical meaning of the broken transformations.
:::

## What the construction does and does not determine

The coset construction determines the allowed form of the EFT. It does not determine every coefficient.

It fixes:

- the nonlinear transformation law of Goldstone fields;
- the derivative nature of exact Goldstone interactions;
- the $H$ representation structure of building blocks;
- which local operators are allowed by symmetry;
- relations among interactions required by nonlinear $G$ invariance.

It does not usually fix:

- the numerical value of decay constants;
- all higher-derivative Wilson coefficients;
- the cutoff scale of the EFT;
- whether the UV theory actually realizes the assumed phase;
- nonperturbative effects not captured by the local derivative expansion;
- anomaly coefficients unless anomaly data are supplied.

In short:

$$
\text{coset construction}=
\text{kinematics of symmetry realization, not full dynamics}.
$$

## Common pitfalls

**“The coset is a quotient of the Lagrangian.”** No. The coset $G/H$ is the space of symmetry-related vacua, or more precisely the local target space of Goldstone fields. It is not obtained by dividing the Lagrangian by a group.

**“The compensator is a new gauge field.”** The compensator $h(g,\pi)$ is an element of the unbroken group needed to return to the chosen coset representative. It is not a new dynamical gauge field. The connection $\omega_\mu$ is a composite object built from Goldstone fields.

**“Every coordinate choice gives a different theory.”** Different coset parametrizations are field redefinitions. They can make formulas look different, but physical observables agree when the EFT is transformed consistently.

**“The leading kinetic term is always unique.”** It is unique only when the broken generators form a single irreducible representation of $H$ and no extra invariant tensors or Wess–Zumino terms are available. Otherwise multiple constants can appear.

**“Wess–Zumino terms are optional decorations.”** In anomaly matching, topological response, and ferromagnets, Wess–Zumino terms can be the most important part of the EFT.

**“Spacetime cosets work exactly like internal cosets.”** They share the group-theoretic language, but spacetime symmetries act on coordinates. Inverse-Higgs constraints and redundant Goldstones are central.

## Relations to other pages

- [Goldstone Modes](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-modes/) motivates the fields $\pi^a(x)$ as coordinates on $G/H$.
- [Nonlinear Sigma Models Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/nonlinear-sigma-models-preview/) develops the target-space field theory viewpoint.
- [Explicit versus Spontaneous Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/explicit-versus-spontaneous-breaking/) explains why spurions create pseudo-Goldstone potentials.
- [Pseudo-Goldstone Bosons](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/pseudo-goldstone-bosons/) applies the spurion logic to small masses.
- [Wess–Zumino Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-terms/) and [Wess–Zumino–Witten Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-witten-terms/) develop the topological terms only previewed here.
- [Anomaly Matching](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-matching/) explains why Goldstone EFTs sometimes must contain Wess–Zumino terms.
- [Gauge Symmetry Is Redundancy](/symmetry-anomalies-topology/gauge-redundancy-brst/gauge-symmetry-is-redundancy/) prevents a common misreading of the Higgs mechanism as ordinary global SSB.

## Research status

For internal symmetries, the coset construction is established and standard. It is a backbone of chiral perturbation theory, pion physics, nonlinear sigma models, superfluid EFTs, and many symmetry-based effective theories.

Spacetime symmetry breaking is more subtle. The coset method remains extremely useful, but inverse-Higgs constraints, redundant Goldstones, finite-density states, anomalies, defects, subsystem symmetries, and nonrelativistic kinematics require additional physical input. Modern work continues to refine when a coset construction gives a universal EFT and when it merely gives a useful parametrization.

The construction has also expanded beyond its original home. Current research uses coset-like logic in hydrodynamics, solids, fracton phases, branes, conformal symmetry breaking, supersymmetry breaking, and generalized symmetry settings.

## Exercises

### Exercise 1: Broken U(1) from the Maurer–Cartan form

Let $G=U(1)$ and $H=\{1\}$. Take

$$
\xi(\pi)=e^{i\pi Q/f}.
$$

Compute $-i\xi^{-1}d\xi$ and derive the leading kinetic term.

<details><summary><strong>Solution</strong></summary>

Since $U(1)$ is abelian,

$$
\xi^{-1}d\xi
=e^{-i\pi Q/f}d(e^{i\pi Q/f})
=i\frac{d\pi}{f}Q.
$$

Therefore

$$
-i\xi^{-1}d\xi=\frac{d\pi}{f}Q.
$$

The broken one-form is

$$
e=\frac{d\pi}{f}.
$$

The leading invariant Lagrangian is

$$
\mathcal L_2=\frac{f^2}{2}e_\mu e^\mu
=\frac12\partial_\mu\pi\partial^\mu\pi.
$$

</details>

### Exercise 2: Counting coordinates on O(N)/O(N−1)

Show that the coset $O(N)/O(N-1)$ has dimension $N-1$.

<details><summary><strong>Solution</strong></summary>

The dimension of $O(N)$ is the number of antisymmetric $N\times N$ matrices:

$$
\dim O(N)=\frac{N(N-1)}2.
$$

Similarly,

$$
\dim O(N-1)=\frac{(N-1)(N-2)}2.
$$

Therefore

$$
\dim\frac{O(N)}{O(N-1)}
=\frac{N(N-1)}2-\frac{(N-1)(N-2)}2
=N-1.
$$

These are the $N-1$ coordinates on $S^{N-1}$ and the $N-1$ Goldstone modes in the relativistic internal-symmetry setting.

</details>

### Exercise 3: Leading expansion of the sphere sigma model

Let

$$
n^a=\frac{\pi^a}{f},
\qquad
n^N=\sqrt{1-\frac{\pi^a\pi^a}{f^2}},
\qquad
a=1,\ldots,N-1.
$$

Show that

$$
\frac{f^2}{2}\partial_\mu n^i\partial^\mu n^i
=\frac12\partial_\mu\pi^a\partial^\mu\pi^a+O(\pi^2(\partial\pi)^2/f^2).
$$

<details><summary><strong>Solution</strong></summary>

For the first $N-1$ components,

$$
\partial_\mu n^a=\frac{\partial_\mu\pi^a}{f}.
$$

For the last component,

$$
\partial_\mu n^N
=-\frac{\pi^a\partial_\mu\pi^a}{f^2\sqrt{1-\pi^b\pi^b/f^2}}.
$$

Thus

$$
\partial_\mu n^i\partial^\mu n^i
=\frac{1}{f^2}\partial_\mu\pi^a\partial^\mu\pi^a
+\frac{(\pi^a\partial_\mu\pi^a)(\pi^b\partial^\mu\pi^b)}{f^4(1-\pi^c\pi^c/f^2)}.
$$

Multiplying by $f^2/2$ gives

$$
\frac{f^2}{2}\partial_\mu n^i\partial^\mu n^i
=\frac12\partial_\mu\pi^a\partial^\mu\pi^a
+O\left(\frac{\pi^2(\partial\pi)^2}{f^2}\right).
$$

</details>

### Exercise 4: Why the compensator is needed

Explain why the equation

$$
g\xi(\pi)=\xi(\pi')h(g,\pi)
$$

contains an element $h\in H$ rather than simply $g\xi(\pi)=\xi(\pi')$.

<details><summary><strong>Solution</strong></summary>

The coset representative $\xi(\pi)$ is a choice of one group element from each equivalence class in $G/H$. Multiplying by a general $g\in G$ usually produces a group element that is not in the chosen representative form. However, it belongs to some equivalence class. To bring it back to the chosen representative of that class, one is allowed to multiply on the right by an element of $H$, because elements differing by right multiplication by $H$ represent the same point in $G/H$.

Thus $h(g,\pi)$ is the compensating unbroken transformation needed to maintain the chosen coordinate convention on the coset.

</details>

## References

- S. R. Coleman, J. Wess, and B. Zumino, “Structure of Phenomenological Lagrangians. I,” *Physical Review* **177** (1969) 2239–2247.
- C. G. Callan, S. R. Coleman, J. Wess, and B. Zumino, “Structure of Phenomenological Lagrangians. II,” *Physical Review* **177** (1969) 2247–2250.
- D. V. Volkov, “Phenomenological Lagrangians,” *Soviet Journal of Particles and Nuclei* **4** (1973) 3–41.
- Sidney Coleman, *Aspects of Symmetry*, especially “Secret Symmetry” and “Soft Pions.” Classic source for broken symmetry, current algebra, and pion effective reasoning.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II. Systematic treatment of effective Lagrangians, broken symmetries, and low-energy theorems.
- C. P. Burgess, *Introduction to Effective Field Theory*, Ch. 4. Clear EFT discussion of linear versus nonlinear realization and symmetry constraints.
- H. Leutwyler, “Nonrelativistic Effective Lagrangians,” *Physical Review D* **49** (1994) 3033–3043.
- I. Low and A. V. Manohar, “Spontaneously Broken Spacetime Symmetries and Goldstone's Theorem,” *Physical Review Letters* **88** (2002) 101602.
- H. Watanabe and H. Murayama, “Effective Lagrangian for Nonrelativistic Systems,” *Physical Review X* **4** (2014) 031057.
- A. Nicolis, R. Penco, F. Piazza, and R. A. Rosen, “More on gapped Goldstones at finite density: More gapped Goldstones,” *Journal of High Energy Physics* **11** (2013) 055.

## Version history

- 2026-06-17: First polished draft. Added the CCWZ-style coset recipe, nonlinear transformation law, Maurer–Cartan building blocks, leading Lagrangians, examples, matter-field couplings, Wess–Zumino and spurion previews, spacetime-symmetry caveats, exercises, and the coset-construction figure.
