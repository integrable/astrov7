---
title: "Conserved Charges"
description: "Explains how conserved currents define time-independent charges, how those charges generate symmetry transformations, and why boundaries, infrared effects, and gauge constraints can obstruct the naive construction."
sidebar:
  label: "Conserved Charges"
  order: 3
level: Graduate
status: "Polished draft"
source: "Coleman lectures on symmetries and conservation laws; Srednicki §22; Weinberg Vol. I on symmetry generators; Schwartz chapters on Noether's theorem and Ward identities."
topics:
  - conserved charges
  - Noether currents
  - surface independence
  - equal-time commutators
  - charge sectors
  - boundary flux
canonicalTopics:
  - conserved-charge
  - noether-charge
  - charge-generator
  - surface-charge
researchStatus:
  established:
    - "For an exact nonanomalous continuous symmetry with controlled boundary conditions, integrating the time component of a conserved current over a Cauchy surface gives a conserved charge that generates the symmetry action."
  active:
    - "In gauge theories, theories with boundaries, massless modes, spontaneous symmetry breaking, and generalized or non-invertible symmetries, the correct notion of charge is often a surface, edge, algebraic, or defect-theoretic object rather than a naive spatial integral."
---

## Summary

A conserved current becomes powerful when we integrate it.

For an ordinary continuous symmetry with current $j_a^\mu$, the associated charge on a time slice is

$$
Q_a(t)=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x),
$$

provided the integral exists and boundary conditions are controlled. If the current obeys

$$
\partial_\mu j_a^\mu=0,
$$

then

$$
\frac{dQ_a}{dt}
=-\int_{\partial\Sigma}dS_i\,j_a^i.
$$

If no charge flows through the boundary, the right-hand side vanishes and $Q_a$ is time independent.

The charge is not just a number. After quantization, it should be the operator that generates the symmetry:

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
U(\alpha)^\dagger\mathcal O U(\alpha)
=\mathcal O+\alpha^a\delta_a\mathcal O+O(\alpha^2),
$$

so, in the convention of this volume,

$$
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

That is the clean story. The grown-up story adds caveats: boundary flux, infrared tails, spontaneous symmetry breaking, gauge constraints, anomalies, current improvements, operator renormalization, and nontrivial topology can all change what the word “charge” means.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A spacetime slab bounded by two time slices and a side boundary, illustrating that the difference of charges on the two slices equals minus the current flux through the side boundary.](/figures/symmetry-anomalies-topology/conserved-charge-flux-balance.svg)

<figcaption>

A conserved current gives a conserved charge only after a boundary condition is imposed. In a spacetime slab, $Q(t_2)-Q(t_1)$ equals minus the flux through the side boundary. No side flux means $Q(t_2)=Q(t_1)$; nonzero side flux means the boundary carries part of the symmetry story.

</figcaption>
</figure>

## Prerequisites

Read [Noether Currents](/symmetry-anomalies-topology/noether-currents-ward-identities/noether-currents/) and [Improved Currents and Ambiguities](/symmetry-anomalies-topology/noether-currents-ward-identities/improved-currents-and-ambiguities/) first. We use the same current convention,

$$
j_a^\mu=\theta^\mu(\delta_a\Phi)-K_a^\mu,
$$

and the same operator-action convention,

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

You should be comfortable with Gauss' theorem, equal-time commutators, and the idea of a Cauchy surface. Contact terms and Ward identities are introduced here only as motivation; the next page treats them directly.

## Core idea

Local current conservation says charge cannot be created or destroyed in the bulk. A conserved charge is what remains after integrating this local statement over space.

Start with

$$
\partial_\mu j^\mu=0.
$$

Writing $x^0=t$, this is

$$
\partial_t j^0+\partial_i j^i=0.
$$

Integrate over a spatial region $\Sigma$:

$$
\frac{d}{dt}\int_\Sigma d^{d-1}\mathbf x\,j^0
=-\int_\Sigma d^{d-1}\mathbf x\,\partial_i j^i.
$$

By Gauss' theorem,

$$
\frac{dQ_\Sigma}{dt}
=-\int_{\partial\Sigma}dS_i\,j^i.
$$

Thus $Q_\Sigma$ is conserved if there is no flux through $\partial\Sigma$.

This is not a technicality. The phrase “the charge is conserved” always hides a condition like one of the following:

- the fields fall off fast enough at spatial infinity;
- space is compact and has no boundary;
- boundary conditions force the normal current to vanish;
- edge degrees of freedom are included so that bulk-plus-edge charge is conserved.

Without such a condition, the continuity equation still holds locally, but the charge in the chosen region can change.

## Setup and conventions

Let $\Sigma_t$ be a spatial Cauchy surface at time $t$. For a current $j_a^\mu$, define

$$
Q_a(t)=\int_{\Sigma_t} d\Sigma_\mu\,j_a^\mu.
$$

On the standard flat time slice,

$$
d\Sigma_\mu=(d^{d-1}\mathbf x,0,\ldots,0),
$$

so

$$
Q_a(t)=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x).
$$

In differential-form notation, the dual current is

$$
J_a=\star j_a,
$$

a $(d-1)$-form. Conservation becomes

$$
dJ_a=0,
$$

and the charge is

$$
Q_a(\Sigma)=\int_\Sigma J_a.
$$

This notation makes surface independence transparent. If $\Sigma_1$ and $\Sigma_2$ are homologous and together bound a spacetime region $M$, then

$$
Q_a(\Sigma_2)-Q_a(\Sigma_1)
=\int_{\Sigma_2}J_a-\int_{\Sigma_1}J_a
=\int_{\partial M}J_a
=\int_M dJ_a.
$$

If $dJ_a=0$ and no operator insertions, boundary defects, or singularities lie inside $M$, then

$$
Q_a(\Sigma_2)=Q_a(\Sigma_1).
$$

:::note[Orientation note]
The sign in the surface formula depends on the orientation convention for $\partial M$. The physical statement is invariant: the change in charge between two surfaces equals the current flux through the remaining boundary. On the flat time slab used above, the convention gives

$$
Q(t_2)-Q(t_1)=-\int_{\text{side}}d\Sigma_i\,j^i.
$$
:::

## From continuity to time independence

Assume first that space is $\mathbb R^{d-1}$ and that the current falls off fast enough at infinity. Then

$$
Q_a(t)=\int_{\mathbb R^{d-1}}d^{d-1}\mathbf x\,j_a^0(t,\mathbf x)
$$

has derivative

$$
\frac{dQ_a}{dt}
=\int d^{d-1}\mathbf x\,\partial_tj_a^0
=-\int d^{d-1}\mathbf x\,\partial_i j_a^i.
$$

The last term is a surface integral at infinity:

$$
\frac{dQ_a}{dt}
=-\lim_{R\to\infty}\int_{S_R^{d-2}}dS_i\,j_a^i.
$$

If the surface integral vanishes,

$$
\frac{dQ_a}{dt}=0.
$$

This is the usual conservation law.

The same reasoning works on a compact spatial manifold without boundary. Then $\partial\Sigma=\varnothing$, so

$$
\int_\Sigma \partial_i j^i=0
$$

by Stokes' theorem, and the total charge is time independent.

If $\Sigma$ has a boundary, the conservation law becomes a balance equation:

$$
\frac{dQ_\Sigma}{dt}
=-\int_{\partial\Sigma}dS_i\,j^i.
$$

This is the field-theory version of charge in a box: the charge changes exactly by the amount flowing through the walls.

## Charge as generator

The reason conserved charges matter in QFT is that they implement symmetries on Hilbert space.

A continuous internal symmetry is represented by unitary operators

$$
U(\alpha)=e^{-i\alpha^aQ_a}.
$$

With the operator pullback convention used in this volume,

$$
\mathcal O\longmapsto U(\alpha)^\dagger\mathcal O U(\alpha).
$$

Expanding to first order gives

$$
U(\alpha)^\dagger\mathcal O U(\alpha)
=\mathcal O+i\alpha^a[Q_a,\mathcal O]+O(\alpha^2).
$$

Therefore

$$
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

For a charged operator $\mathcal O_q$ with $U(1)$ charge $q$,

$$
[Q,\mathcal O_q]=q\mathcal O_q,
$$

so

$$
U(\alpha)^\dagger\mathcal O_qU(\alpha)
=e^{iq\alpha}\mathcal O_q.
$$

States transform with $U(\alpha)$ itself. If

$$
Q|q\rangle=q|q\rangle,
$$

then

$$
U(\alpha)|q\rangle=e^{-i\alpha q}|q\rangle.
$$

This opposite-looking sign between states and pulled-back operators is not a contradiction. It is the usual active/passive pairing between a state transformation and an operator pullback.

:::note[Convention-sensitive source note]
Many references write the finite operator transformation as $U\mathcal O U^{-1}$ rather than $U^\dagger\mathcal O U$, or define $U(\alpha)=e^{+i\alpha Q}$. Those choices move signs between $U$, $Q$, and $\delta\mathcal O$. The invariant check is whether the integrated charge reproduces the stated infinitesimal field variation.
:::

## Equal-time commutators

In canonical quantization, the charge-generator relation is checked using equal-time commutators.

For bosonic fields $\Phi^I$ with conjugate momenta $\Pi_I$,

$$
[\Phi^I(t,\mathbf x),\Pi_J(t,\mathbf y)]
=i\delta^I{}_J\delta^{(d-1)}(\mathbf x-\mathbf y).
$$

Suppose the Noether charge has the schematic form

$$
Q_a=\int d^{d-1}\mathbf x\,\Pi_I\delta_a\Phi^I
$$

up to signs and possible total-derivative terms fixed by the Lagrangian. Then its commutator with $\Phi^I$ gives the field variation.

The exact local formula depends on the theory, but the structural criterion is always

$$
i[Q_a,\Phi^I]=\delta_a\Phi^I.
$$

When this fails, at least one assumption has broken: the current representative may be wrong, boundary terms may be missing, constraints may not have been imposed, composite operators may need renormalization, or the symmetry may be anomalous.

## Example: complex scalar charge

For the complex scalar field with

$$
\mathcal L
=\partial_\mu\phi^\dagger\partial^\mu\phi
-m^2\phi^\dagger\phi
-V(\phi^\dagger\phi),
$$

the $U(1)$ phase symmetry is

$$
\delta\phi=i\phi,
\qquad
\delta\phi^\dagger=-i\phi^\dagger.
$$

The Noether current found earlier is

$$
j^\mu
=i(\partial^\mu\phi^\dagger)\phi
-i(\partial^\mu\phi)\phi^\dagger.
$$

The charge is

$$
Q=\int d^{d-1}\mathbf x\,
\left(i\dot\phi^\dagger\phi-i\dot\phi\,\phi^\dagger\right).
$$

The canonical momenta are

$$
\pi=\dot\phi^\dagger,
\qquad
\pi^\dagger=\dot\phi,
$$

so

$$
Q=\int d^{d-1}\mathbf x\,
\left(i\pi\phi-i\pi^\dagger\phi^\dagger\right).
$$

Using

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(d-1)}(\mathbf x-\mathbf y),
$$

we get

$$
[Q,\phi(t,\mathbf y)]=\phi(t,\mathbf y),
$$

and hence

$$
i[Q,\phi]=i\phi=\delta\phi.
$$

Similarly,

$$
[Q,\phi^\dagger]=-\phi^\dagger,
\qquad
i[Q,\phi^\dagger]=-i\phi^\dagger=\delta\phi^\dagger.
$$

This simple check is worth doing once because it fixes the sign convention for almost every later Ward identity.

## Example: translations and energy-momentum

For spacetime translations, the conserved currents are the components of the stress tensor. With the convention of the Noether-current page, an infinitesimal active translation of a scalar field is

$$
\delta_\nu\phi=\partial_\nu\phi.
$$

The corresponding current is

$$
T^\mu{}_\nu
=\frac{\partial\mathcal L}{\partial(\partial_\mu\phi)}\partial_\nu\phi
-\delta^\mu{}_\nu\mathcal L.
$$

The conserved charges are

$$
P_\nu=\int d^{d-1}\mathbf x\,T^0{}_\nu.
$$

They generate translations of local operators:

$$
i[P_\nu,\mathcal O(x)]=\partial_\nu\mathcal O(x)
$$

for scalar operators, with spin terms added for operators carrying Lorentz indices. The Hamiltonian is the charge associated with time translations, up to the index-position convention for $P_0$ and $H$.

Stress tensors have more improvement ambiguities than ordinary internal currents. The Belinfante stress tensor, symmetric stress tensors, Hilbert stress tensors from metric variation, and conformally improved stress tensors are different representatives of related physical data. The stress-tensor pages in Foundations and CFT will treat those distinctions in detail.

## Local charges in a region

It is often useful to define the charge inside a finite spatial region $R$:

$$
Q_R(t)=\int_R d^{d-1}\mathbf x\,j^0(t,\mathbf x).
$$

Then

$$
\frac{dQ_R}{dt}=-\int_{\partial R}dS_i\,j^i.
$$

This is not usually a conserved charge; it is a bookkeeping device. It says that the amount of charge inside $R$ changes only by flux through the boundary.

In quantum theory, local charges require some care because sharply cutting a region can create ultraviolet-sensitive boundary terms. One often smooths the characteristic function of $R$:

$$
Q_f(t)=\int d^{d-1}\mathbf x\,f(\mathbf x)j^0(t,\mathbf x),
$$

where $f$ equals $1$ in the region of interest and decays smoothly to $0$. Then commutators with local operators deep inside the $f=1$ region reproduce the symmetry action, while the transition region records the boundary flux.

This smearing viewpoint is especially useful in algebraic QFT, gauge theory, and entanglement theory, where sharp subregion factorization can fail.

## Surface independence and symmetry defects

The differential-form expression

$$
Q_a(\Sigma)=\int_\Sigma J_a
$$

makes a conserved charge look like a codimension-one operator. Exponentiating it gives

$$
U_\Sigma(\alpha)=\exp\left(-i\alpha^a\int_\Sigma J_a\right).
$$

When $dJ_a=0$ and no charged insertions are crossed, this operator is invariant under smooth deformations of $\Sigma$:

$$
U_{\Sigma_1}(\alpha)=U_{\Sigma_2}(\alpha).
$$

When the surface crosses a charged local operator, the operator transforms. This is the bridge to the topological-defect picture of ordinary global symmetry:

$$
\text{conserved current}
\quad\leadsto\quad
\text{topological codimension-one symmetry operator}.
$$

The next page makes this statement precise inside correlation functions. The contact terms in the Ward identity are the infinitesimal version of “the symmetry wall acts when it crosses an operator.”

## Algebra of charges

If the currents realize a Lie algebra with generators $T_a$, the charges should satisfy

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c
$$

up to possible central terms, boundary terms, or Schwinger terms.

Classically, the corresponding statement is often written using Poisson brackets. Quantum mechanically, equal-time products of current densities can be singular, so the charge algebra is subtler than the formal integral suggests. In many ordinary finite-dimensional internal symmetries, the algebra is represented without surprises. In current algebras, two-dimensional CFT, anomalous theories, gauge theories with boundaries, and asymptotic symmetry algebras, extra terms can be the whole point.

The important distinction is:

$$
\text{finite-dimensional global charge algebra}
\quad\text{versus}\quad
\text{local current algebra}.
$$

The former may be clean even when the latter contains contact terms. The Current Algebra page later in this chapter returns to this distinction.

## When the charge fails to exist

The formula

$$
Q=\int d^{d-1}\mathbf x\,j^0
$$

looks innocent, but QFT is not obligated to make the integral a good Hilbert-space operator. Here are the main failure modes.

### Boundary flux

If

$$
\int_{\partial\Sigma}dS_i\,j^i\neq0,
$$

then $Q_\Sigma$ is not conserved. This is not a bug. It means charge is flowing through the boundary. The correct conserved quantity may include an edge contribution,

$$
Q_{\mathrm{total}}=Q_{\mathrm{bulk}}+Q_{\mathrm{edge}}.
$$

This is common in gauge theory, Chern–Simons theory, anomaly inflow, and systems with physical boundaries.

### Infrared tails

In theories with massless fields, the current density can fall off too slowly for the spatial integral to converge as an ordinary operator. Long-range electromagnetic fields, Goldstone modes, and gravitational fields all produce infrared subtleties. Sometimes the charge exists only after smearing, dressing, or specifying asymptotic data.

### Spontaneous symmetry breaking

In a phase with spontaneously broken continuous symmetry, the current can exist locally while the global charge fails to be a well-defined operator on the vacuum Hilbert space. Roughly, acting with the charge tries to move the system through an infinite-volume family of vacua. The Goldstone theorem is born from precisely this tension between local current conservation and global charge implementation.

### Gauge constraints

Gauge transformations with compact support are redundancies, not physical global symmetries. Their would-be charges vanish on physical states after constraints are imposed. Transformations that do not vanish at the boundary can instead become genuine global or asymptotic symmetries with boundary charges.

This is one of the deepest reasons to separate global symmetry from gauge redundancy. A local gauge parameter does not automatically mean a family of physical Noether charges.

### Anomalies

If the quantum theory has an anomaly,

$$
\partial_\mu j^\mu=\mathcal A,
$$

then $Q$ is not conserved in backgrounds for which the integrated anomaly is nonzero. In a gauge anomaly, this is fatal for consistency if the anomalous symmetry was supposed to be gauged. In a global anomaly, it is valuable information: it is an obstruction to gauging and an RG-invariant datum.

### Operator renormalization

The current is a composite operator. In an interacting QFT, the bare expression may not be the finite operator that appears in Ward identities. One may need a renormalized current,

$$
[j^\mu]_{\mathrm R},
$$

possibly mixed with other operators of the same quantum numbers. Exact symmetries often protect the normalization of the associated charge, but the local current representative can still be scheme dependent.

## Conserved charge versus conserved number

In elementary quantum mechanics, a conserved quantity is often introduced as an operator commuting with the Hamiltonian:

$$
\frac{dQ}{dt}=i[H,Q]+\frac{\partial Q}{\partial t}=0.
$$

In QFT, a Noether charge has the additional feature that it is spatially local before integration. It comes from a current satisfying a continuity equation. That locality is what produces Ward identities, soft theorems, current algebras, and topological symmetry operators.

Thus there is a hierarchy:

$$
\text{local current conservation}
\quad\Longrightarrow\quad
\text{conserved charge}
\quad\Longrightarrow\quad
\text{selection rules}.
$$

The arrows do not reverse automatically. A conserved operator need not arise from a local current, and a selection rule may come from a discrete symmetry with no Noether current.

## Common pitfalls

**Forgetting the boundary condition.** The step from $\partial_\mu j^\mu=0$ to $dQ/dt=0$ assumes no flux through the boundary. If charge can escape to infinity or into an edge mode, the bulk charge is not conserved by itself.

**Confusing charge conservation with charge neutrality.** Conservation says $Q$ is time independent. Neutrality is a statement about a state or correlator having total charge zero. A charged particle can carry a conserved nonzero charge.

**Using a current representative as if it were unique.** Improvements can change $j^0$ locally. Under good boundary conditions they do not change the total $Q$, but they can change local charge density and contact terms.

**Assuming every formal charge integral is an operator.** Infinite-volume limits, massless modes, and spontaneous symmetry breaking can make $Q$ ill-defined even when $j^\mu$ is perfectly meaningful as a local operator.

**Treating gauge redundancy as global symmetry.** Gauge transformations with compact support normally generate constraints and act trivially on physical states. Global or boundary transformations are different and must be identified separately.

**Dropping contact terms in commutator checks.** Equal-time commutators of local densities are distributions. The charge action is obtained only after the correct delta functions and possible Schwinger terms are handled.

## Relations to other pages

[Noether Currents](/symmetry-anomalies-topology/noether-currents-ward-identities/noether-currents/) constructs $j_a^\mu$ from local variations. This page integrates $j_a^\mu$ to obtain $Q_a$ and explains when the integral is meaningful.

[Improved Currents and Ambiguities](/symmetry-anomalies-topology/noether-currents-ward-identities/improved-currents-and-ambiguities/) explains why different local representatives can give the same charge under suitable boundary conditions.

[Current Conservation in Correlation Functions](/symmetry-anomalies-topology/noether-currents-ward-identities/current-conservation-in-correlation-functions/) is the next step: it explains why the conservation equation becomes a distributional Ward identity with contact terms at charged insertions.

[Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/) treats charge sectors, superselection, and representation-theoretic organization from the symmetry side.

[Symmetry Defects and Topological Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-defects-and-topological-operators/) treats the exponentiated charge as a topological symmetry wall. The present page gives the current-based derivation of the same picture.

Later pages on Ward identities, current algebra, background fields, spontaneous symmetry breaking, gauge redundancy, and anomalies each relax one of the simplifying assumptions made here.

## Research status

For ordinary exact continuous global symmetries in well-behaved relativistic QFTs, the relation between currents, charges, and symmetry generators is established textbook material.

The subtle cases are not marginal. Modern research often lives exactly where the naive charge integral needs refinement: asymptotic symmetries in gauge theory and gravity, edge modes in gauge systems, anomalies and anomaly inflow, generalized symmetries, non-invertible topological defects, spontaneous symmetry breaking in infinite volume, and algebraic definitions of charge sectors.

A safe research-level attitude is:

$$
Q=\int j^0
$$

is a powerful first approximation, not a universal definition. The universal data are the symmetry action, Ward identities, defect/surface operators, boundary conditions, and anomaly class.

## Exercises

### Exercise 1: Flux balance in a finite region

Let $j^\mu$ obey $\partial_\mu j^\mu=0$. For a spatial region $R$, define

$$
Q_R(t)=\int_R d^{d-1}\mathbf x\,j^0(t,\mathbf x).
$$

Show that

$$
\frac{dQ_R}{dt}=-\int_{\partial R}dS_i\,j^i.
$$

<details><summary><strong>Solution</strong></summary>

Use the continuity equation,

$$
\partial_tj^0=-\partial_i j^i.
$$

Then

$$
\frac{dQ_R}{dt}
=\int_R d^{d-1}\mathbf x\,\partial_tj^0
=-\int_R d^{d-1}\mathbf x\,\partial_i j^i.
$$

By Gauss' theorem,

$$
\int_R d^{d-1}\mathbf x\,\partial_i j^i
=\int_{\partial R}dS_i\,j^i.
$$

Therefore

$$
\frac{dQ_R}{dt}=-\int_{\partial R}dS_i\,j^i.
$$

</details>

### Exercise 2: Improvement and charge

Let

$$
j'^\mu=j^\mu+\partial_\nu B^{\mu\nu},
\qquad
B^{\mu\nu}=-B^{\nu\mu}.
$$

Show that the charge changes by a boundary term.

<details><summary><strong>Solution</strong></summary>

On a flat time slice,

$$
Q'=\int d^{d-1}\mathbf x\,j'^0
=Q+\int d^{d-1}\mathbf x\,\partial_\nu B^{0\nu}.
$$

Since $B^{00}=0$, only spatial derivatives remain:

$$
Q'=Q+\int d^{d-1}\mathbf x\,\partial_iB^{0i}.
$$

By Gauss' theorem,

$$
Q'=Q+\int_{\partial\Sigma}dS_i\,B^{0i}.
$$

Thus $Q'=Q$ if the boundary term vanishes. Otherwise, the improvement changes the surface or edge contribution to the charge.

</details>

### Exercise 3: Complex scalar generator

Using

$$
Q=\int d^{d-1}\mathbf x\,\left(i\pi\phi-i\pi^\dagger\phi^\dagger\right),
$$

and the canonical equal-time commutators

$$
[\phi(t,\mathbf x),\pi(t,\mathbf y)]
=i\delta^{(d-1)}(\mathbf x-\mathbf y),
$$

show that $i[Q,\phi]=i\phi$.

<details><summary><strong>Solution</strong></summary>

Only the $i\pi\phi$ term contributes to $[Q,\phi]$:

$$
[Q,\phi(t,\mathbf y)]
=\int d^{d-1}\mathbf x\,i[\pi(t,\mathbf x)\phi(t,\mathbf x),\phi(t,\mathbf y)].
$$

Since $[\phi(\mathbf x),\phi(\mathbf y)]=0$,

$$
[\pi(\mathbf x)\phi(\mathbf x),\phi(\mathbf y)]
=[\pi(\mathbf x),\phi(\mathbf y)]\phi(\mathbf x).
$$

Using

$$
[\pi(\mathbf x),\phi(\mathbf y)]
=-i\delta^{(d-1)}(\mathbf x-\mathbf y),
$$

we find

$$
[Q,\phi(t,\mathbf y)]
=\int d^{d-1}\mathbf x\,i(-i)\delta^{(d-1)}(\mathbf x-\mathbf y)\phi(t,\mathbf x)
=\phi(t,\mathbf y).
$$

Therefore

$$
i[Q,\phi]=i\phi,
$$

which is the desired infinitesimal phase rotation.

</details>

### Exercise 4: Surface independence in form notation

Let $J$ be a closed $(d-1)$-form, $dJ=0$. Suppose two closed oriented surfaces $\Sigma_1$ and $\Sigma_2$ are homologous, so that $\Sigma_2-\Sigma_1=\partial M$. Show that

$$
\int_{\Sigma_2}J=\int_{\Sigma_1}J.
$$

<details><summary><strong>Solution</strong></summary>

Since $\Sigma_2-\Sigma_1=\partial M$,

$$
\int_{\Sigma_2}J-\int_{\Sigma_1}J
=\int_{\partial M}J.
$$

By Stokes' theorem,

$$
\int_{\partial M}J=\int_M dJ.
$$

Since $dJ=0$,

$$
\int_M dJ=0.
$$

Therefore

$$
\int_{\Sigma_2}J=\int_{\Sigma_1}J.
$$

</details>

### Exercise 5: Charged operator finite action

Assume

$$
[Q,\mathcal O_q]=q\mathcal O_q,
\qquad
U(\alpha)=e^{-i\alpha Q}.
$$

Show that

$$
U(\alpha)^\dagger\mathcal O_qU(\alpha)=e^{iq\alpha}\mathcal O_q.
$$

<details><summary><strong>Solution</strong></summary>

Define

$$
F(\alpha)=U(\alpha)^\dagger\mathcal O_qU(\alpha)
=e^{i\alpha Q}\mathcal O_qe^{-i\alpha Q}.
$$

Differentiate:

$$
\frac{dF}{d\alpha}
=i e^{i\alpha Q}[Q,\mathcal O_q]e^{-i\alpha Q}.
$$

Using $[Q,\mathcal O_q]=q\mathcal O_q$,

$$
\frac{dF}{d\alpha}=iqF(\alpha).
$$

With $F(0)=\mathcal O_q$, the solution is

$$
F(\alpha)=e^{iq\alpha}\mathcal O_q.
$$

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chapters 5–6. Operator-centered treatment of spacetime and internal symmetries, conserved currents, and charges.
- Sidney Coleman, *Aspects of Symmetry*, especially “Soft Pions,” “Dilatations,” and “Secret Symmetry.” Classic examples where charges, currents, and symmetry breaking interact.
- Mark Srednicki, *Quantum Field Theory*, §22. Concise derivation of currents and charges for continuous symmetries.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I. Foundational treatment of symmetry generators, states, and local fields.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*. Useful textbook discussion of Noether's theorem, conserved charges, and Ward–Takahashi identities.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Useful for current insertions, composite operators, and functional methods.

## Version history

- **2026-06-17:** Initial polished page on conserved charges.
