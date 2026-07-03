---
title: "Sigma Model Preview"
description: "A foundation-level preview of linear and nonlinear sigma models: symmetry breaking, Goldstone bosons, pions, target spaces, and the EFT boundary."
sidebar:
  label: "Sigma Model Preview"
  order: 5
---

## Summary

A **sigma model** is a field theory whose fields take values in a space with symmetry. In the most elementary linear version, the fields are ordinary scalar fields with an internal rotation symmetry. In the nonlinear version, the fields are constrained to live on a target manifold such as a sphere or a coset space.

The simplest relativistic example is the $O(N)$ linear sigma model,

$$
\mathcal L
=\frac12\partial_\mu\Phi^A\partial^\mu\Phi^A
-\frac{\lambda}{4}\left(\Phi^A\Phi^A-v^2\right)^2,
\qquad A=1,\ldots,N.
$$

Choosing a vacuum spontaneously breaks

$$
O(N)\longrightarrow O(N-1),
$$

leaving one massive radial mode and $N-1$ massless Goldstone modes. At energies far below the radial mass, the radial mode can be ignored and the remaining fields live on the vacuum manifold

$$
S^{N-1}\simeq O(N)/O(N-1).
$$

That low-energy theory is a nonlinear sigma model.

<figure class="doc-figure" style="--figure-width: 56rem;">

![Map from linear sigma model to nonlinear sigma model](/figures/foundations/sigma-model-preview-map.svg)

<figcaption>

The same symmetry-breaking pattern can be described by a linear sigma model with a radial mode, or by a nonlinear sigma model containing only the light Goldstone coordinates on the target space $G/H$. Explicit symmetry breaking turns exact Goldstone bosons into pseudo-Goldstone bosons.

</figcaption>
</figure>

This page is a **preview**. It gives enough sigma-model language to recognize why these models are everywhere: spontaneous symmetry breaking, soft pions, chiral dynamics, critical phenomena, magnets, effective field theory, solitons, and two-dimensional asymptotically free models. It does not replace the later full sections on spontaneous symmetry breaking, chiral perturbation theory, Wilsonian RG, topological terms, or nonperturbative QFT.

## Prerequisites

You should know [Scalar Fields](/foundations/classical-field-theory/scalar-fields/), [Noether Theorem](/foundations/classical-field-theory/noether-theorem/), [Internal Symmetries](/foundations/symmetry-and-spacetime/internal-symmetries/), [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/), [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/), [φ⁴ Theory](/foundations/foundational-models/phi-four-theory/), [Yukawa Theory](/foundations/foundational-models/yukawa-theory/), [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/), and [UV Divergences Preview](/foundations/interactions-and-wick-expansion/uv-divergences-preview/).

:::note[Scope]
The phrase “sigma model” is overloaded. In this page it means a family of scalar-field models organized by target spaces and symmetry-breaking patterns. We will mainly discuss the $O(N)$ linear model and the $SU(2)_L\times SU(2)_R/SU(2)_V$ chiral model. Other sigma models, including supersymmetric sigma models, Wess–Zumino–Witten models, string worldsheet sigma models, and disordered-system sigma models, belong in later sections.
:::

## Why sigma models belong in Foundations

Sigma models are not just another entry in a list of examples. They are where several foundational ideas collide:

| Idea | Sigma-model version |
|---|---|
| spontaneous symmetry breaking | a vacuum manifold replaces a single symmetric vacuum |
| Goldstone theorem | flat directions become massless angular fields |
| effective field theory | heavy radial modes are removed, leaving derivative interactions |
| current algebra | low-energy pion physics is constrained by symmetry |
| geometry | fields become maps from spacetime to a target manifold |
| topology | target-space homotopy can support solitons and theta terms |

The model is also pedagogically useful because it has two complementary descriptions. The **linear sigma model** is a renormalizable scalar theory in four dimensions. The **nonlinear sigma model** is usually an effective field theory in four dimensions, but it makes the geometry and Goldstone structure painfully visible. Painfully visible is good. It means fewer mysteries hiding in notation.

## The O(N) linear sigma model

Let

$$
\Phi(x)=\big(\Phi^1(x),\ldots,\Phi^N(x)\big)
$$

be a real $N$-component scalar field. The $O(N)$ linear sigma model is

$$
\boxed{
\mathcal L
=\frac12\partial_\mu\Phi^A\partial^\mu\Phi^A
-\frac{\lambda}{4}\left(\Phi^A\Phi^A-v^2\right)^2.
}
$$

The symmetry is

$$
\Phi^A(x)\mapsto R^A{}_B\Phi^B(x),
\qquad R\in O(N).
$$

The potential is

$$
V(\Phi)=\frac{\lambda}{4}\left(\Phi^A\Phi^A-v^2\right)^2,
\qquad \lambda>0.
$$

Its minima obey

$$
\Phi^A\Phi^A=v^2.
$$

Thus the set of classical vacua is the sphere $S^{N-1}$. Choosing one vacuum, say

$$
\langle\Phi^N\rangle=v,
\qquad
\langle\Phi^a\rangle=0,
\quad a=1,\ldots,N-1,
$$

breaks the symmetry to rotations of the first $N-1$ components:

$$
O(N)\to O(N-1).
$$

Write the shifted fields as

$$
\Phi^a=\pi^a,
\qquad
\Phi^N=v+\rho.
$$

Then

$$
\Phi^A\Phi^A-v^2
=(v+\rho)^2+\pi^a\pi^a-v^2
=2v\rho+\rho^2+\pi^a\pi^a.
$$

The potential becomes

$$
V=\frac{\lambda}{4}\left(2v\rho+\rho^2+\pi^a\pi^a\right)^2.
$$

The quadratic part is

$$
V_2=\lambda v^2\rho^2
=\frac12(2\lambda v^2)\rho^2.
$$

Therefore

$$
\boxed{m_\rho^2=2\lambda v^2,}
$$

while the $\pi^a$ fields have no mass term:

$$
\boxed{m_\pi^2=0.}
$$

The $\rho$ field is the radial mode. The $\pi^a$ fields are tangent to the vacuum sphere and are the Goldstone modes.

## Counting Goldstone modes

The number of broken generators is

$$
\dim O(N)-\dim O(N-1)
=\frac{N(N-1)}2-\frac{(N-1)(N-2)}2
=N-1.
$$

That equals the number of massless fields $\pi^a$.

This is the sigma-model version of Goldstone's theorem: each independent broken continuous global generator produces a massless mode, assuming the usual relativistic QFT conditions such as locality, positive energy, and a stable vacuum.

:::note[Assumptions]
This statement is for ordinary relativistic QFT with global internal symmetry. Gauge symmetries behave differently: in the Higgs mechanism, would-be Goldstone modes are gauge-dependent variables and become the longitudinal polarizations of massive gauge bosons.
:::

## The chiral SU(2) linear sigma model

The historically central sigma model is the Gell-Mann–Lévy model for pions and nucleons. Its bosonic fields are an isosinglet scalar $\sigma$ and an isotriplet pseudoscalar $\boldsymbol\pi=(\pi^1,\pi^2,\pi^3)$.

The four fields can be grouped as

$$
\Phi=(\boldsymbol\pi,\sigma),
$$

so the bosonic potential has an $O(4)$ symmetry:

$$
V(\sigma,\boldsymbol\pi)
=\frac{\lambda}{4}\left(\sigma^2+\boldsymbol\pi^2-v^2\right)^2.
$$

The group-theory miracle is

$$
SU(2)_L\times SU(2)_R\simeq SO(4),
\qquad
SU(2)_V\simeq SO(3).
$$

Choosing

$$
\langle\sigma\rangle=v,
\qquad
\langle\boldsymbol\pi\rangle=0
$$

realizes

$$
SU(2)_L\times SU(2)_R\longrightarrow SU(2)_V.
$$

The unbroken group is isospin. The three broken axial generators produce the three pions as Goldstone bosons.

A compact bosonic Lagrangian is

$$
\mathcal L
=\frac12(\partial_\mu\sigma)^2
+\frac12(\partial_\mu\boldsymbol\pi)^2
-\frac{\lambda}{4}\left(\sigma^2+\boldsymbol\pi^2-v^2\right)^2.
$$

With a nucleon isodoublet

$$
N=\begin{pmatrix}p\\ n\end{pmatrix},
$$

the standard Yukawa coupling has the schematic form

$$
\mathcal L_Y
=-g\overline N\left(\sigma+i\gamma^5\boldsymbol\tau\cdot\boldsymbol\pi\right)N,
$$

up to convention choices for factors of $1/2$ in the isospin generators. After shifting $\sigma=v+\rho$, this produces a nucleon mass

$$
m_N=gv
$$

and pion-nucleon interactions tied to the same coupling.

This is why the model is such a good classroom animal. One vacuum expectation value simultaneously explains broken axial symmetry, massless pions in the symmetric limit, and fermion masses from a scalar condensate.

## Explicit breaking and pseudo-Goldstone pions

Real pions are light, not massless. The sigma model captures this by adding a small term that preserves isospin but breaks the axial part of the chiral symmetry. The simplest choice is

$$
\Delta\mathcal L=h\sigma,
$$

so the potential becomes

$$
V(\sigma,\boldsymbol\pi)
=\frac{\lambda}{4}\left(\sigma^2+\boldsymbol\pi^2-v^2\right)^2-h\sigma.
$$

The vacuum is still aligned in the $\sigma$ direction:

$$
\langle\sigma\rangle=f,
\qquad
\langle\boldsymbol\pi\rangle=0,
$$

but the minimum condition is now

$$
\lambda(f^2-v^2)f=h.
$$

The pion mass is the curvature in the pion directions:

$$
m_\pi^2
=\left.\frac{\partial^2 V}{\partial\pi^a\partial\pi^a}\right|_{\sigma=f,\boldsymbol\pi=0}
=\lambda(f^2-v^2)
=\frac{h}{f}.
$$

Thus

$$
\boxed{m_\pi^2=\frac{h}{f}.}
$$

This is the prototype of a pseudo-Goldstone mass relation. A small explicit breaking of the symmetry produces a small mass squared for the would-be Goldstone boson.

Coleman's lecture treatment emphasizes precisely this point in the language of PCAC: the sigma-model breaking term can be chosen so that the divergence of the axial current is proportional to the pion field. In modern QCD language, the up and down quark masses explicitly break chiral symmetry; the pions are light because they are approximate Goldstone bosons.

## From linear to nonlinear sigma models

At energies much smaller than the radial mass,

$$
E\ll m_\rho,
$$

the radial mode is not easily excited. The low-energy theory can therefore be written using only the coordinates on the vacuum manifold.

For the $O(N)$ model, impose

$$
\Phi^A\Phi^A=v^2.
$$

Write

$$
\Phi^A(x)=v n^A(x),
\qquad
n^A n^A=1.
$$

Substituting into the kinetic term gives

$$
\mathcal L_\text{NLSM}
=\frac{v^2}{2}\partial_\mu n^A\partial^\mu n^A,
\qquad
n^A n^A=1.
$$

This is the nonlinear sigma model with target space $S^{N-1}$.

To use unconstrained fields, choose local coordinates $\pi^a$ on the sphere. For example,

$$
n^a=\frac{\pi^a}{v},
\qquad
n^N=\sqrt{1-\frac{\boldsymbol\pi^2}{v^2}}.
$$

Then

$$
\mathcal L_\text{NLSM}
=\frac12\partial_\mu\pi^a\partial^\mu\pi^a
+\frac{1}{2v^2}\frac{(\pi^a\partial_\mu\pi^a)^2}{1-\boldsymbol\pi^2/v^2}.
$$

Expanding the denominator gives an infinite tower of derivative interactions:

$$
\mathcal L_\text{NLSM}
=\frac12(\partial\boldsymbol\pi)^2
+\frac{1}{2v^2}(\boldsymbol\pi\cdot\partial_\mu\boldsymbol\pi)^2
+\frac{1}{2v^4}\boldsymbol\pi^2(\boldsymbol\pi\cdot\partial_\mu\boldsymbol\pi)^2
+\cdots.
$$

The interactions vanish at zero momentum. That is the low-energy fingerprint of Goldstone bosons.

## Chiral matrix notation

For the two-flavor chiral model it is often cleaner to assemble the fields into a matrix

$$
\Sigma=\sigma\mathbf 1+i\boldsymbol\tau\cdot\boldsymbol\pi.
$$

Under chiral rotations,

$$
\Sigma\mapsto L\Sigma R^\dagger,
\qquad L,R\in SU(2).
$$

In the nonlinear model, the radial constraint is replaced by a unitary matrix field

$$
U(x)\in SU(2),
$$

with transformation law

$$
U\mapsto LUR^\dagger.
$$

The leading chiral Lagrangian is

$$
\boxed{
\mathcal L_2
=\frac{F^2}{4}\operatorname{Tr}\left(\partial_\mu U^\dagger\partial^\mu U\right).
}
$$

One common parametrization is

$$
U(x)=\exp\left(\frac{i\boldsymbol\tau\cdot\boldsymbol\pi(x)}{F}\right).
$$

The constant $F$ sets the interaction scale. In pion physics, it is related to the pion decay constant, up to convention-dependent normalizations.

## What the nonlinear model computes

The nonlinear sigma model is not merely the linear model with a constraint imposed for fun. It computes the most general low-energy amplitudes consistent with the symmetry-breaking pattern.

The leading chiral Lagrangian contains two derivatives, so tree-level Goldstone scattering starts at order

$$
\mathcal M\sim \frac{p^2}{F^2}.
$$

The next corrections come from two sources:

1. loops built from the leading two-derivative Lagrangian,
2. local four-derivative operators with new coefficients.

This is the usual EFT rhythm. Loop divergences are not a disaster; they tell you which local operators must be included at the next order.

In four dimensions, the nonlinear sigma model is nonrenormalizable in the old power-counting sense because the coupling $1/F$ has negative mass dimension. But it is perfectly sensible as an effective field theory organized by powers of $p/F$ and $p/\Lambda$, where $\Lambda$ is the scale at which heavier states or new dynamics appear.

## Geometry viewpoint

The nonlinear sigma model can be written as a theory of maps

$$
X:M_\text{spacetime}\to\mathcal T,
$$

where $\mathcal T$ is the target manifold. In local coordinates $X^A(x)$ on $\mathcal T$, the action is

$$
S=\frac12\int d^dx\,G_{AB}(X)\partial_\mu X^A\partial^\mu X^B+\text{higher-derivative terms}.
$$

The target-space metric $G_{AB}(X)$ determines the two-derivative interactions. Curvature of the target space becomes interaction strength.

This geometric phrasing becomes essential in later topics:

| Later topic | Sigma-model bridge |
|---|---|
| chiral perturbation theory | target space is a symmetry coset $G/H$ |
| magnets and critical systems | order-parameter fields live on spheres or cosets |
| two-dimensional QFT | sigma-model couplings run; mass gaps can appear |
| string theory | worldsheet fields map into spacetime target manifolds |
| topology | instantons, skyrmions, theta terms, WZW terms |

Foundations only needs the bridge. The hiking expedition happens elsewhere.

## Currents and PCAC

In the exact chiral limit, the axial currents are conserved:

$$
\partial_\mu A^{a\mu}=0.
$$

When a small explicit breaking term is added, the divergence is no longer zero. In the sigma model with $\Delta\mathcal L=h\sigma$, the axial variation of $\sigma$ is proportional to $\pi^a$, so

$$
\partial_\mu A^{a\mu}\propto h\pi^a.
$$

Using $m_\pi^2=h/f$, this becomes the schematic PCAC relation

$$
\boxed{\partial_\mu A^{a\mu}\sim f m_\pi^2\pi^a.}
$$

The precise normalization depends on the current convention, but the structure is the key point: exact axial symmetry gives massless Goldstones; weak explicit breaking gives light pseudo-Goldstones and a nearly conserved axial current.

## Relation to renormalizability

The linear and nonlinear sigma models teach different lessons about renormalizability.

In four dimensions, the linear $O(N)$ sigma model is a renormalizable scalar theory. It contains a finite set of operators:

$$
(\partial\Phi)^2,
\qquad
\Phi^2,
\qquad
(\Phi^2)^2,
$$

plus possible symmetry-allowed Yukawa couplings and soft breaking terms.

The nonlinear sigma model in four dimensions contains infinitely many derivative interactions when expanded in coordinates. It is not renormalizable as a fundamental four-dimensional theory in the old sense, but it is a controlled low-energy EFT.

In two dimensions, the story is different: the nonlinear sigma model coupling is dimensionless, and many sigma models become central examples of asymptotic freedom, dimensional transmutation, instantons, and mass-gap generation. That is why sigma models show up both in particle theory and in statistical mechanics. Same beast, different weather.

## Common pitfalls

**Pitfall 1: Thinking nonlinear means nonperturbative.**

“Nonlinear” means the fields are constrained or the target-space metric depends on the fields. You can still do perturbation theory in small fluctuations or in a derivative expansion.

**Pitfall 2: Thinking Goldstone bosons must be exactly massless in nature.**

They are exactly massless only when the symmetry is exact and global. Small explicit breaking gives pseudo-Goldstone bosons with small masses.

**Pitfall 3: Confusing radial and angular modes.**

The radial mode changes the length of the order parameter. Goldstone modes move along the vacuum manifold. At low energy, the radial mode may decouple while the angular modes remain.

**Pitfall 4: Treating the nonlinear sigma model as one unique theory.**

A target space and a leading kinetic term are only the start. EFT requires all higher-derivative operators allowed by the symmetries.

**Pitfall 5: Forgetting the gauge-theory exception.**

Goldstone bosons from broken global symmetries are physical massless particles. Would-be Goldstone modes in gauge theories are not physical particles in the same way; they are tied to gauge choice and massive vector polarizations.

## Relation to other pages

- [φ⁴ Theory](/foundations/foundational-models/phi-four-theory/) is the single-field ancestor: one real scalar, one quartic potential, and possible discrete symmetry breaking.
- [Yukawa Theory](/foundations/foundational-models/yukawa-theory/) supplies the scalar-fermion coupling that appears in the nucleon version of the sigma model.
- [Scalar QED](/foundations/foundational-models/scalar-qed/) and [QED Preview](/foundations/foundational-models/qed-preview/) show how gauge symmetry changes the symmetry-breaking story.
- [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/) explains why current conservation and contact terms constrain correlators.
- [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/) explains the quantum-corrected potential and the meaning of expanding around a chosen vacuum.
- Later pages on chiral perturbation theory, Wilsonian RG, two-dimensional sigma models, solitons, and string worldsheet QFT should take over from here.

## Exercises

### Exercise 1: Count the Goldstone modes

For the symmetry-breaking pattern

$$
O(N)\to O(N-1),
$$

show that the number of Goldstone modes is $N-1$.

<details>
<summary><strong>Solution</strong></summary>

The dimension of $O(N)$ is

$$
\dim O(N)=\frac{N(N-1)}2.
$$

The unbroken subgroup has

$$
\dim O(N-1)=\frac{(N-1)(N-2)}2.
$$

The number of broken generators is

$$
\frac{N(N-1)}2-\frac{(N-1)(N-2)}2
=\frac{N-1}{2}\big[N-(N-2)\big]
=N-1.
$$

Thus the model has $N-1$ Goldstone bosons.

</details>

### Exercise 2: Radial mass in the linear model

For

$$
V=\frac{\lambda}{4}\left(\Phi^A\Phi^A-v^2\right)^2,
$$

expand around

$$
\Phi^N=v+\rho,
\qquad
\Phi^a=\pi^a.
$$

Find the mass of $\rho$ and the mass of $\pi^a$.

<details>
<summary><strong>Solution</strong></summary>

We have

$$
\Phi^A\Phi^A-v^2=(v+\rho)^2+\pi^a\pi^a-v^2
=2v\rho+\rho^2+\pi^a\pi^a.
$$

Thus

$$
V=\frac{\lambda}{4}\left(2v\rho+\rho^2+\pi^a\pi^a\right)^2.
$$

The quadratic part is

$$
V_2=\frac{\lambda}{4}(2v\rho)^2=\lambda v^2\rho^2.
$$

Comparing with $V_2=\frac12m_\rho^2\rho^2$, we find

$$
m_\rho^2=2\lambda v^2.
$$

There is no quadratic term in $\pi^a$, so

$$
m_\pi^2=0.
$$

</details>

### Exercise 3: Pseudo-Goldstone mass from a tilt

For

$$
V=\frac{\lambda}{4}\left(\sigma^2+\boldsymbol\pi^2-v^2\right)^2-h\sigma,
$$

assume the vacuum is

$$
\sigma=f,
\qquad
\boldsymbol\pi=0.
$$

Show that

$$
m_\pi^2=\frac{h}{f}.
$$

<details>
<summary><strong>Solution</strong></summary>

The minimum condition in the $\sigma$ direction is

$$
0=\left.\frac{\partial V}{\partial\sigma}\right|_{f,0}
=\lambda(f^2-v^2)f-h.
$$

Therefore

$$
\lambda(f^2-v^2)=\frac{h}{f}.
$$

The pion mass comes from the second derivative in a pion direction:

$$
m_\pi^2
=\left.\frac{\partial^2V}{\partial\pi^a\partial\pi^a}\right|_{f,0}
=\lambda(f^2-v^2).
$$

Hence

$$
\boxed{m_\pi^2=\frac{h}{f}.}
$$

</details>

### Exercise 4: Constraint gives derivative interactions

Use

$$
n^a=\frac{\pi^a}{v},
\qquad
n^N=\sqrt{1-\frac{\boldsymbol\pi^2}{v^2}}
$$

in

$$
\mathcal L=\frac{v^2}{2}\partial_\mu n^A\partial^\mu n^A
$$

to show that the first interaction term is

$$
\frac{1}{2v^2}(\boldsymbol\pi\cdot\partial_\mu\boldsymbol\pi)^2.
$$

<details>
<summary><strong>Solution</strong></summary>

First,

$$
\partial_\mu n^a=\frac{1}{v}\partial_\mu\pi^a.
$$

Also,

$$
\partial_\mu n^N
=\partial_\mu\left(1-\frac{\boldsymbol\pi^2}{v^2}\right)^{1/2}
=-\frac{\boldsymbol\pi\cdot\partial_\mu\boldsymbol\pi}{v^2\sqrt{1-\boldsymbol\pi^2/v^2}}.
$$

Then

$$
\frac{v^2}{2}\partial_\mu n^a\partial^\mu n^a
=\frac12\partial_\mu\pi^a\partial^\mu\pi^a,
$$

and

$$
\frac{v^2}{2}\partial_\mu n^N\partial^\mu n^N
=\frac{1}{2v^2}\frac{(\boldsymbol\pi\cdot\partial_\mu\boldsymbol\pi)^2}{1-\boldsymbol\pi^2/v^2}.
$$

Expanding the denominator gives the first interaction term

$$
\boxed{\frac{1}{2v^2}(\boldsymbol\pi\cdot\partial_\mu\boldsymbol\pi)^2.}
$$

</details>

### Exercise 5: Engineering dimension of the nonlinear coupling

In $d$ spacetime dimensions, find the mass dimension of $F$ in

$$
\mathcal L=\frac{F^2}{2}\partial_\mu n^A\partial^\mu n^A,
\qquad
n^A n^A=1.
$$

What does this suggest in two and four dimensions?

<details>
<summary><strong>Solution</strong></summary>

The field $n^A$ is dimensionless because of the constraint. The derivative has dimension one, so

$$
[\partial_\mu n^A\partial^\mu n^A]=2.
$$

The Lagrangian density has dimension $d$, hence

$$
[F^2]+2=d.
$$

Therefore

$$
[F]=\frac{d-2}{2}.
$$

Equivalently, the coupling $1/F$ has dimension

$$
[1/F]=\frac{2-d}{2}.
$$

In two dimensions, $F$ is dimensionless, so the nonlinear sigma model is marginal by engineering dimension. In four dimensions, $1/F$ has dimension $-1$, so interactions are nonrenormalizable by old power counting but perfectly natural in an EFT expansion.

</details>

### Exercise 6: Why Goldstone interactions vanish at zero momentum

Explain why the leading nonlinear sigma model contains derivative interactions and why that implies soft Goldstone scattering amplitudes vanish as momenta go to zero, up to explicit symmetry-breaking effects.

<details>
<summary><strong>Solution</strong></summary>

Goldstone fields parametrize motion along a vacuum manifold. A constant shift along a broken direction changes the chosen point on the vacuum manifold but costs no potential energy. Therefore the leading invariant terms cannot contain an ordinary potential for exact Goldstones; they must contain derivatives.

The leading interaction terms are built from factors such as

$$
\partial_\mu\pi^a.
$$

Each external Goldstone attached through these interactions contributes powers of its momentum. Therefore amplitudes built from the exact Goldstone derivative couplings vanish in the soft limit. Explicit symmetry-breaking terms can add non-derivative interactions proportional to the small breaking parameters, such as $m_\pi^2$.

</details>

## Sources and further reading

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 43–45, especially §§45.3–45.4, for spontaneous symmetry breaking, the sigma model, PCAC, the Goldberger–Treiman relation, and pions as approximate Goldstone bosons.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, §§19.5–19.6, for nonlinear sigma models as effective field theories of Goldstone bosons, chiral $SU(2)_L\times SU(2)_R/SU(2)_V$, and the modern EFT justification.
- Anthony Zee, *Quantum Field Theory in a Nutshell*, chs. IV.1–IV.3 and VI.4, for symmetry breaking, effective potentials, and sigma models as effective field theories.
- Mark Srednicki, *Quantum Field Theory*, §§30–32 and §§83–84, for spontaneous symmetry breaking, Goldstone bosons, chiral symmetry breaking, and the gauge-theory contrast.
- M. Gell-Mann and M. Lévy, “The Axial Vector Current in Beta Decay,” *Il Nuovo Cimento* **16** (1960), 705–726, for the original sigma-model construction.
- A. M. Polyakov, *Gauge Fields and Strings*, chs. 1–2 and 8, for sigma models in the statistical-mechanics/QFT interface, renormalization, and large-$N$ viewpoints.

## Version history

- **2026-05-24:** Initial qft.org sigma-model preview page: linear and nonlinear sigma models, Goldstone modes, chiral $SU(2)$ model, explicit breaking, PCAC, target-space geometry, EFT boundary, pitfalls, and exercises.
