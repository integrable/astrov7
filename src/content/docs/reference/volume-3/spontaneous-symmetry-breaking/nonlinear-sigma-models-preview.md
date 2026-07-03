---
title: "Nonlinear Sigma Models Preview"
description: "Introduces nonlinear sigma models as effective field theories for Goldstone modes, emphasizing target-space geometry, derivative expansions, renormalization, and topological terms."
sidebar:
  label: "Nonlinear Sigma Models Preview"
  order: 6
level: Advanced
status: "Polished draft"
source: "Coleman on secret symmetry and classical lumps; Callan–Coleman–Wess–Zumino; Coleman–Wess–Zumino; Weinberg Vol. II; Zee; Burgess on nonlinear realizations; Altland–Simons on sigma models and topology."
topics:
  - nonlinear sigma models
  - Goldstone effective theory
  - target-space geometry
  - derivative expansion
  - chiral Lagrangian
  - topological terms
  - effective field theory
canonicalTopics:
  - nonlinear-sigma-model
  - goldstone-effective-field-theory
  - target-space-metric
  - derivative-expansion
  - chiral-lagrangian
  - topological-term
  - sigma-model-renormalization
researchStatus:
  established:
    - "Nonlinear sigma models are the universal leading effective theories for many systems with spontaneously broken continuous internal symmetries."
    - "Their leading interactions are controlled by the geometry of the target space and by symmetry, while loops require the usual EFT counterterms unless the model is treated in a special low-dimensional renormalizable setting."
  active:
    - "Sigma models with Wess–Zumino terms, theta terms, defects, boundaries, anomalies, finite density, and generalized-symmetry structure remain central in current research."
---

## Summary

A **nonlinear sigma model** is a field theory whose fields are maps

$$
\phi:M_d\longrightarrow \mathcal M,
$$

from spacetime $M_d$ into a target space $\mathcal M$. In the symmetry-breaking applications of this chapter, the target is usually the vacuum manifold

$$
\mathcal M=G/H,
$$

where $G$ is the symmetry of the theory and $H$ is the subgroup that preserves the chosen vacuum.

The leading Lorentz-invariant action is the geometric kinetic energy of this map:

$$
S_{\text{NLSM}}
=
\frac12\int d^d x\, g_{ij}(\phi)\,\partial_\mu\phi^i\partial^\mu\phi^j+
\cdots,
$$

where $g_{ij}$ is a metric on $\mathcal M$ and the dots denote higher-derivative terms, explicit-breaking terms, Wess–Zumino terms, theta terms, and other allowed interactions.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A diagram showing a spacetime manifold mapped into a curved target space. A point in spacetime maps to a point on the vacuum manifold G over H. Tangent directions are Goldstone fields, the target metric controls the leading kinetic term, and higher derivative and topological terms decorate the effective action.](/figures/symmetry-anomalies-topology/nonlinear-sigma-model-geometry.svg)

<figcaption>

A nonlinear sigma model is a theory of maps into a target space. For spontaneous breaking $G\to H$, the target is often $G/H$. The target metric gives the leading two-derivative Goldstone action; topology and symmetry determine possible extra terms.

</figcaption>
</figure>

The word “nonlinear” has two related meanings here. First, the field coordinates $\phi^i$ live on a curved space, so there is no globally preferred linear coordinate system. Second, the original symmetry group $G$ generally acts nonlinearly on the Goldstone coordinates, even though it acts linearly on the microscopic fields.

The shortest useful slogan is:

$$
\text{nonlinear sigma model}
=
\text{kinematics of slow motion on the vacuum manifold}.
$$

The better slogan is:

$$
\text{nonlinear sigma model}
=
\text{the derivative expansion of maps }M_d\to G/H,
\text{ including geometry and topology}.
$$

## Prerequisites

Read [Goldstone Modes](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-modes/) and [Coset Construction Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/coset-construction-preview/) first. You should also know [Order Parameters](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/order-parameters/), [Degenerate Vacua](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/degenerate-vacua/), and [Symmetry Algebras](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-algebras/).

This page is a preview because nonlinear sigma models eventually belong to several volumes at once: symmetry, EFT, topology, critical phenomena, two-dimensional QFT, and nonperturbative physics. Here the goal is to understand why they are the natural next language after Goldstone’s theorem.

## Core idea

Goldstone’s theorem says that exact continuous internal symmetry breaking produces gapless excitations. It does not by itself give their full interactions. The nonlinear sigma model does.

The key physical observation is that at energies well below the mass of radial or amplitude modes, the system cannot easily move off the vacuum manifold. It can only move along it. The low-energy field is therefore not a vector in the original microscopic field space, but a point on the manifold of vacua.

For a breaking pattern

$$
G\longrightarrow H,
$$

the vacuum manifold is, under the usual homogeneous-space assumptions,

$$
\mathcal M=G/H.
$$

Goldstone fields are local coordinates on this manifold:

$$
\pi^a(x)\quad\text{coordinates on }G/H.
$$

A constant $\pi^a$ simply labels a vacuum. A slowly varying $\pi^a(x)$ describes a long-wavelength fluctuation that changes the chosen vacuum from point to point. The energy must vanish for constant motion along the vacuum manifold, so the leading action contains derivatives:

$$
\mathcal L_{2}
=
\frac12 g_{ab}(\pi)\,\partial_\mu\pi^a\partial^\mu\pi^b.
$$

This derivative coupling is the first great lesson of Goldstone EFT: symmetry forces Goldstone interactions to become weak at low momentum, even when the underlying microscopic theory is strongly coupled.

## Setup and conventions

We use the mostly-minus metric of the volume. Thus

$$
\partial_\mu\pi^a\partial^\mu\pi^b
=
\dot\pi^a\dot\pi^b-\nabla\pi^a\cdot\nabla\pi^b.
$$

The leading Lorentzian Lagrangian for a sigma model with target metric $g_{ij}$ is

$$
\mathcal L_2
=
\frac12 g_{ij}(\phi)\,\partial_\mu\phi^i\partial^\mu\phi^j.
$$

For compact group manifolds and coset spaces it is common to factor out a decay constant $F$ and use dimensionless coordinates. A typical convention is

$$
g_{ij}(\phi)=F^2\,\widehat g_{ij}(\phi),
$$

so that

$$
\mathcal L_2
=
\frac{F^2}{2}\widehat g_{ij}(\phi)\,\partial_\mu\phi^i\partial^\mu\phi^j.
$$

In $d$ spacetime dimensions,

$$
[F^2]=d-2.
$$

Therefore $F$ has mass dimension $1$ in four spacetime dimensions and dimension $0$ in two spacetime dimensions.

:::note[Source note: normalization of $F$]
The normalization of $F$, $f$, or $v$ varies across the literature. In chiral Lagrangians one often writes $F^2/4\,\operatorname{tr}(\partial_\mu U^\dagger\partial^\mu U)$, while in $O(N)$ models one often writes $F^2/2\,\partial_\mu n\cdot\partial^\mu n$ with $n\cdot n=1$. These are convention choices. Physical decay constants are fixed by current matrix elements, not by the letter used in the Lagrangian.
:::

## From a linear model to a nonlinear model

The cleanest prototype is the $O(N)$ linear sigma model,

$$
\mathcal L
=
\frac12\partial_\mu\Phi^I\partial^\mu\Phi^I
-
\frac\lambda4\left(\Phi^I\Phi^I-v^2\right)^2,
\qquad I=1,\ldots,N.
$$

The potential is minimized when

$$
\Phi^I\Phi^I=v^2.
$$

Thus the classical vacuum manifold is the sphere

$$
S^{N-1}\simeq O(N)/O(N-1).
$$

Choose a vacuum in the $N$th direction and write

$$
\Phi^I(x)=\bigl(v+\sigma(x)\bigr)n^I(x),
\qquad
n^I n^I=1.
$$

Here $\sigma$ is the radial mode and $n^I$ describes motion along the sphere. Substituting gives

$$
\frac12\partial_\mu\Phi^I\partial^\mu\Phi^I
=
\frac12(\partial_\mu\sigma)^2
+
\frac12(v+\sigma)^2\partial_\mu n^I\partial^\mu n^I.
$$

The radial mode has mass

$$
m_\sigma^2=2\lambda v^2.
$$

At energies $E\ll m_\sigma$, we can integrate out $\sigma$ or, at tree level, set it to its low-energy value. The leading effective theory is

$$
\mathcal L_{\text{NLSM}}
=
\frac{v^2}{2}\,\partial_\mu n^I\partial^\mu n^I,
\qquad
n^I n^I=1.
$$

This is the $O(N)$ nonlinear sigma model.

Two facts are worth holding onto.

First, the constraint $n^2=1$ is not an arbitrary trick. It expresses the decoupling of the massive radial mode from the low-energy theory.

Second, the constraint is not the whole theory. The low-energy action also contains higher-derivative terms such as

$$
\mathcal L_4
=
c_1\bigl(\partial_\mu n\cdot\partial^\mu n\bigr)^2
+
c_2\bigl(\partial_\mu n\cdot\partial_\nu n\bigr)
     \bigl(\partial^\mu n\cdot\partial^\nu n\bigr)
+
\cdots.
$$

The coefficients $c_i$ depend on short-distance physics. The leading two-derivative term is universal in form; the numerical values of higher-derivative couplings are data of the EFT.

## Geometry of the target space

A nonlinear sigma model is most naturally written without choosing a special coordinate system on $\mathcal M$. Let $\phi^i$ be local coordinates. Under a change of target coordinates

$$
\phi^i\longrightarrow \phi'^i(\phi),
$$

the metric transforms as a tensor, and the action

$$
S_2=\frac12\int d^d x\,g_{ij}(\phi)\partial_\mu\phi^i\partial^\mu\phi^j
$$

is invariant as a geometric object.

Perturbatively, one usually expands around a point $\phi_0\in\mathcal M$. In Riemann normal coordinates near $\phi_0$,

$$
g_{ij}(\phi)
=
\delta_{ij}
-
\frac13 R_{ikjl}(\phi_0)\,\phi^k\phi^l+
\cdots.
$$

Then the Lagrangian becomes

$$
\mathcal L_2
=
\frac12\partial_\mu\phi^i\partial^\mu\phi^i
-
\frac16 R_{ikjl}(\phi_0)\phi^k\phi^l
\partial_\mu\phi^i\partial^\mu\phi^j
+
\cdots.
$$

So target-space curvature becomes interaction strength. A flat target gives free massless fields at leading order; a curved target gives derivative self-interactions.

This geometric viewpoint is useful beyond spontaneous symmetry breaking. Sigma models appear whenever long-distance fields are coordinates on a manifold: spin systems, strings, branes, moduli-space dynamics, sigma-model descriptions of disordered matter, and many effective theories of fluids and solids.

## Coset sigma models

For symmetry breaking $G\to H$, the target space is often a coset $G/H$. The coset construction packages the geometry in group-theoretic form.

Choose broken generators $X_a$ and write a coset representative

$$
\xi(\pi)=e^{i\pi^aX_a/F}.
$$

The Maurer–Cartan form is

$$
-i\xi^{-1}\partial_\mu\xi
=
E_\mu^{\ a}X_a+\omega_\mu^{\ \alpha}T_\alpha,
$$

where $T_\alpha$ are unbroken generators. The components $E_\mu^{\ a}$ behave like covariant derivatives of Goldstone fields, while $\omega_\mu^{\ \alpha}$ behaves like an $H$ connection.

The leading invariant Lagrangian has the schematic form

$$
\mathcal L_2
=
\frac{F^2}{2}\,\kappa_{ab}E_\mu^{\ a}E^{\mu b},
$$

where $\kappa_{ab}$ is an $H$-invariant positive tensor on the broken directions. For symmetric spaces and simple examples, this is essentially the unique two-derivative term up to normalization. In more general cases, there can be several independent invariant tensors and therefore several decay constants.

:::note[Source note: coset and sigma-model conventions]
Some references write $\xi=e^{i\pi^aX_a}$ and put all dimensions into the metric. Others write $\xi=e^{i\pi^aX_a/F}$. The second convention makes the fields $\pi^a$ have canonical mass dimension in four-dimensional EFT. Both descriptions are equivalent after rescaling coordinates on $G/H$.
:::

## The chiral Lagrangian as the canonical example

For QCD with light quarks, an idealized massless theory has approximate chiral symmetry

$$
G=SU(N_f)_L\times SU(N_f)_R,
$$

which is spontaneously broken to the diagonal subgroup

$$
H=SU(N_f)_V.
$$

The Goldstone fields are encoded in a unitary matrix

$$
U(x)=\exp\left(\frac{2i\pi^a(x)T^a}{F}\right),
\qquad
U\in SU(N_f).
$$

The leading chiral Lagrangian is

$$
\mathcal L_2
=
\frac{F^2}{4}\operatorname{tr}\left(\partial_\mu U^\dagger\partial^\mu U\right).
$$

Under chiral transformations,

$$
U\longrightarrow LUR^\dagger,
\qquad
L\in SU(N_f)_L,
\quad
R\in SU(N_f)_R.
$$

Expanding $U$ gives canonical pion kinetic terms plus infinitely many derivative interactions. The infinite series is not a bug. It is exactly what it means for the pions to be coordinates on a compact curved target space.

When quark masses are included, the symmetry is explicitly broken and the pions become pseudo-Goldstone bosons. That is the subject of the next page.

## Power counting and the EFT expansion

In four spacetime dimensions, the nonlinear sigma model is usually an effective field theory. The leading operator has coefficient $F^2$, and interactions scale with powers of momentum over $F$.

A typical low-energy expansion has the form

$$
\mathcal L_{\text{eff}}
=
\mathcal L_2+
\mathcal L_4+
\mathcal L_6+
\cdots,
$$

where $\mathcal L_{2k}$ contains $2k$ derivatives, or derivatives plus spurion insertions counted with an assigned order. Observables are expanded in powers of

$$
\frac{p}{\Lambda},
$$

where $\Lambda$ is the cutoff scale of the EFT, often of order $4\pi F$ in strongly coupled four-dimensional examples.

Loops from $\mathcal L_2$ generate divergences with the form of higher-derivative terms. Therefore $\mathcal L_4$, $\mathcal L_6$, and so on are not optional decorations. They are required by renormalization once one computes beyond tree level.

This is the correct modern attitude:

$$
\text{nonrenormalizable}
\ne
\text{unusable}.
$$

A four-dimensional nonlinear sigma model is predictive order by order at low energy, provided one includes all operators allowed by symmetry up to the desired order.

## Two-dimensional sigma models

In two spacetime dimensions, the coefficient $F^2$ is dimensionless. This makes two-dimensional sigma models much more delicate and much more powerful.

For a general target-space metric, the one-loop renormalization group flow is controlled by target-space curvature:

$$
\mu\frac{d}{d\mu}g_{ij}
\propto
R_{ij}+\cdots,
$$

up to convention-dependent constants and higher-loop corrections. Ricci curvature therefore becomes beta-function data.

This formula is one of the places where geometry and QFT meet in an almost suspiciously elegant way. It underlies the asymptotic freedom of some sigma models, the study of strings propagating in curved backgrounds, and many exact or integrable two-dimensional examples.

:::note[Source note: sign conventions for the sigma-model beta function]
The sign of the displayed curvature flow depends on whether the running is written for $g_{ij}$, its inverse, a coupling multiplying a fixed metric, and whether the flow parameter is $\mu$ or length scale. The invariant statement is that the one-loop counterterm is proportional to the Ricci tensor of the target metric.
:::

## Topological terms

The kinetic term depends on the metric of $\mathcal M$. Sigma models can also contain terms that depend on topology rather than on local metric data.

Examples include theta terms built from closed differential forms on the target. If $\omega_d$ is a closed $d$-form on $\mathcal M$, then one can sometimes write

$$
S_\theta
=
i\theta\int_{M_d}\phi^*\omega_d
$$

in Euclidean signature, with quantization or periodicity conditions determined by the periods of $\omega_d$.

Another important class is Wess–Zumino or Wess–Zumino–Witten terms. These are often written by extending the field configuration into a one-higher-dimensional manifold $B_{d+1}$ with boundary $\partial B_{d+1}=M_d$:

$$
S_{\text{WZ}}
=
2\pi i k\int_{B_{d+1}}\widetilde\phi^*\Omega_{d+1}.
$$

The coefficient $k$ is quantized so that the path integral does not depend on the arbitrary extension. Such terms are not small higher-derivative corrections in the naive sense; they encode anomalies, quantized response, and global topology.

This is why nonlinear sigma models sit naturally in this volume. They are where spontaneous symmetry breaking, EFT, topology, anomalies, solitons, and low-dimensional dualities first start talking to each other.

## What the model does and does not say

The nonlinear sigma model says that the low-energy theory is organized by maps into a target space and by a derivative expansion. It does not automatically say that every possible target-space map is physically allowed with equal weight, nor that the target space is literally the microscopic configuration space.

In particular:

- The target $G/H$ describes low-energy vacuum directions, not all microscopic fields.
- The cutoff matters. The model is not meant to describe arbitrary short-distance variations of $\phi(x)$.
- Higher-derivative terms are part of the same EFT, not evidence that the leading sigma model “failed.”
- Global questions such as winding sectors, spin structures, and Wess–Zumino quantization can change the quantum theory even when the local Lagrangian looks the same.

The local geometry controls perturbative Goldstone scattering. The global topology controls sectors, defects, and quantized terms. Both are part of the theory.

## Common pitfalls

**Mistaking the constraint for the physics.** The equation $n^2=1$ is only a coordinate-efficient way of describing a target sphere. The physics is the low-energy motion on the vacuum manifold plus the allowed derivative and topological terms.

**Assuming the leading term is the whole EFT.** In four dimensions, the leading sigma-model action is only the first term in an expansion. Loop calculations require higher-derivative counterterms.

**Forgetting that coordinates on target space are unphysical.** Different parameterizations of $G/H$ can make the Lagrangian look different. Observables do not depend on this choice.

**Confusing spacetime topology with target-space topology.** Topological sectors classify maps from spacetime, or spatial slices, into the target. Both the domain and the target matter.

**Treating all sigma models as Goldstone EFTs.** Many are, but not all. Some sigma models describe string embeddings, disordered systems, moduli spaces, or statistical systems with no direct spontaneous-breaking interpretation.

## Relations to other pages

[Coset Construction Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/coset-construction-preview/) gives the group-theoretic machinery behind $G/H$ sigma models. [Explicit Versus Spontaneous Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/explicit-versus-spontaneous-breaking/) explains how small symmetry-breaking terms generate potentials and masses for Goldstone fields.

Later pages on [Wess–Zumino Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-terms/), [Wess–Zumino–Witten Terms](/symmetry-anomalies-topology/topological-terms/wess-zumino-witten-terms/), [Theta Terms](/symmetry-anomalies-topology/topological-terms/theta-terms/), and [Skyrmions Preview](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/skyrmions-preview/) will return to the topological side of sigma models.

The Renormalization, RG, and EFT volume treats power counting, matching, and loop renormalization systematically. The Matter, Statistical Physics, and Quantum Information volume treats sigma models as effective theories of magnets, superfluids, quantum Hall systems, and disordered matter.

## Research status

The basic role of nonlinear sigma models as Goldstone EFTs is settled. The leading two-derivative construction for internal symmetry breaking is standard, and the EFT interpretation of higher-derivative terms is now routine.

Active and subtle directions include sigma models with anomalies, boundaries, defects, non-invertible symmetry, finite-density terms, higher-form symmetries, theta terms, Wess–Zumino terms, and strong infrared dynamics in low dimensions. Two-dimensional sigma models remain especially rich because they can be asymptotically free, conformal, integrable, massive, or topological depending on target geometry and extra terms.

## Exercises

### Exercise 1: The sphere metric from constrained fields

Let $n^I n^I=1$ for $I=1,\ldots,N$. Choose local coordinates $\pi^a$, $a=1,\ldots,N-1$, by

$$
n^a=\frac{\pi^a}{v},
\qquad
n^N=\sqrt{1-\frac{\pi^a\pi^a}{v^2}}.
$$

Show that

$$
\frac{v^2}{2}\partial_\mu n^I\partial^\mu n^I
=
\frac12 g_{ab}(\pi)\partial_\mu\pi^a\partial^\mu\pi^b,
$$

and find $g_{ab}(\pi)$.

<details><summary><strong>Solution</strong></summary>

We have

$$
\partial_\mu n^a=\frac1v\partial_\mu\pi^a,
$$

and

$$
\partial_\mu n^N
=
-\frac{\pi^a\partial_\mu\pi^a}{v^2\sqrt{1-\pi^2/v^2}},
\qquad
\pi^2\equiv\pi^a\pi^a.
$$

Therefore

$$
\partial_\mu n^I\partial^\mu n^I
=
\frac1{v^2}\partial_\mu\pi^a\partial^\mu\pi^a
+
\frac{(\pi^a\partial_\mu\pi^a)(\pi^b\partial^\mu\pi^b)}{v^4(1-\pi^2/v^2)}.
$$

Multiplying by $v^2/2$ gives

$$
g_{ab}(\pi)
=
\delta_{ab}
+
\frac{\pi_a\pi_b}{v^2-\pi^2}.
$$

This is the round metric on $S^{N-1}$ in this coordinate patch, scaled by $v^2$.

</details>

### Exercise 2: Why Goldstone interactions are derivative

For the $O(N)$ nonlinear sigma model

$$
\mathcal L=\frac{v^2}{2}\partial_\mu n^I\partial^\mu n^I,
\qquad n^2=1,
$$

explain why a constant field configuration $n^I(x)=n_0^I$ has zero energy and why this forbids a potential on the exact vacuum manifold.

<details><summary><strong>Solution</strong></summary>

If $n^I(x)=n_0^I$ is constant, then $\partial_\mu n^I=0$, so the sigma-model Lagrangian density vanishes. This reflects the fact that every constant point on the vacuum manifold is a vacuum with the same energy.

A nonconstant potential $V(n)$ on the sphere would assign different energies to different points of the vacuum manifold. That would explicitly lift the degeneracy and break the symmetry, unless $V$ were constant. Therefore exact spontaneous breaking allows derivative interactions along the vacuum manifold but not a symmetry-breaking potential for the Goldstone coordinates.

</details>

### Exercise 3: Dimension of the sigma-model coupling

In $d$ spacetime dimensions, suppose

$$
\mathcal L=\frac{F^2}{2}\widehat g_{ij}(\phi)\partial_\mu\phi^i\partial^\mu\phi^j,
$$

where $\phi^i$ are dimensionless coordinates. Find the mass dimension of $F^2$ and explain why $d=2$ is special.

<details><summary><strong>Solution</strong></summary>

The Lagrangian density has mass dimension $d$. Since $\partial_\mu$ has dimension $1$ and $\phi^i$ is dimensionless, the operator $\widehat g_{ij}\partial\phi^i\partial\phi^j$ has dimension $2$. Therefore

$$
[F^2]=d-2.
$$

In $d=2$, $F^2$ is dimensionless. This makes the two-dimensional nonlinear sigma model power-counting marginal, so quantum effects can generate logarithmic running. In $d=4$, $F^2$ has dimension $2$, and the model is naturally interpreted as a low-energy EFT.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially “Secret symmetry” and “Classical lumps and their quantum descendants.”
- C. G. Callan, S. Coleman, J. Wess, and B. Zumino, “Structure of phenomenological Lagrangians. II.”
- S. Coleman, J. Wess, and B. Zumino, “Structure of phenomenological Lagrangians. I.”
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters on effective Lagrangians and chiral dynamics.
- A. Zee, *Quantum Field Theory in a Nutshell*, chapters on symmetry breaking, nonlinear sigma models, and topology.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapters on nonlinear realization and Goldstone EFT.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, chapters on renormalization group, sigma models, and topological terms.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chapters on nonlinear sigma models and critical phenomena.

## Version history

- 2026-06-17: Initial polished draft. Added the geometric definition, the $O(N)$ prototype, coset sigma models, chiral Lagrangian normalization, power counting, two-dimensional curvature-flow warning, topological terms, and exercises.
