---
title: "Order Parameters"
description: "Defines order parameters in QFT, explains how they diagnose spontaneous symmetry breaking, and separates local, composite, nonlocal, gauge-invariant, and generalized diagnostics."
sidebar:
  label: "Order Parameters"
  order: 1
level: Graduate
status: "Polished draft"
source: "Coleman on secret symmetry and current algebra; Srednicki §§30–32; Schwartz Ch. 28; Altland–Simons on broken symmetry and collective phenomena; modern generalized-symmetry language from Gaiotto–Kapustin–Seiberg–Willett."
topics:
  - order parameters
  - spontaneous symmetry breaking
  - long-range order
  - source limits
  - degenerate vacua
  - chiral condensate
  - Wilson loops
  - gauge-invariant diagnostics
canonicalTopics:
  - order-parameter
  - symmetry-breaking-diagnostic
  - long-range-order
  - source-selection
  - cluster-decomposition
  - condensate
  - nonlocal-order-parameter
researchStatus:
  established:
    - "For ordinary Landau symmetry breaking, an order parameter is an observable whose expectation value or long-distance correlator distinguishes symmetry-realization patterns."
    - "In QFT, the correct broken-phase order parameter requires an infinite-volume or thermodynamic limit before the symmetry-selecting source is removed."
  active:
    - "Many modern phases require nonlocal, categorical, higher-form, mixed-state, or boundary-sensitive diagnostics rather than a single local order parameter."
---

## Summary

An **order parameter** is an observable, or sometimes a family of observables, that distinguishes phases. In the simplest case it is a local operator $\mathcal O$ whose expectation value is zero in a symmetric phase and nonzero in a broken phase:

$$
\langle\mathcal O\rangle =0
\qquad\text{symmetric phase,}
$$

$$
\langle\mathcal O\rangle \ne 0
\qquad\text{broken phase.}
$$

That slogan is useful, but incomplete. In QFT an order parameter must answer three questions:

1. **What symmetry or phase distinction is being tested?**
2. **Which observable is being measured?**
3. **Which limit defines the phase?**

The third question is the one beginners are least likely to ask and experts are least likely to forgive. A finite quantum system can have a unique symmetric ground state even when the infinite system has symmetry-broken phases. To see a broken order parameter, one usually adds a tiny source, takes the infinite-volume limit, and only then removes the source:

$$
\langle\mathcal O\rangle_{\text{broken}}
=
\lim_{h\to0}\lim_{V\to\infty}\langle\mathcal O\rangle_{h,V}.
$$

The reverse order often gives zero.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A diagnostic flowchart for order parameters: choose a symmetry and phase distinction, choose an operator or extended observable, couple a source, take the infinite-volume limit before removing the source, check transformation under the symmetry, and interpret zero or nonzero results with caveats about gauge redundancy, renormalization, and nonlocal diagnostics.](/figures/symmetry-anomalies-topology/order-parameter-diagnostics.svg)

<figcaption>

An order parameter is not just a nonzero number. It is a diagnostic protocol: specify the symmetry, choose the observable, define the source and limits, and check whether the result transforms nontrivially. If no local diagnostic exists, try extended operators, defects, boundary probes, response functions, or generalized-symmetry data.

</figcaption>
</figure>

The most important lesson is:

$$
\text{order parameter} = \text{observable} + \text{symmetry action} + \text{phase-defining limit}.
$$

This page develops that sentence carefully.

## Prerequisites

Read [What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/), [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/), [Conserved Charges](/symmetry-anomalies-topology/noether-currents-ward-identities/conserved-charges/), and [Charges Acting on Local Operators](/symmetry-anomalies-topology/noether-currents-ward-identities/charges-acting-on-local-operators/) first.

It is also useful to know [Sources and Background Fields](/symmetry-anomalies-topology/background-fields-and-gauging/sources-and-background-fields/), because order parameters are cleanest when defined by coupling sources to operators.

## Core idea

Let $G$ be an internal global symmetry of a QFT and let $|\Omega\rangle$ be a state or vacuum. A local operator $\mathcal O_i$ transforms in some representation of $G$:

$$
U(g)\mathcal O_i(x)U(g)^{-1}
=
D_i{}^j(g)\mathcal O_j(x).
$$

Its expectation value

$$
v_i=\langle\Omega|\mathcal O_i|\Omega\rangle
$$

is an order parameter for breaking $G$ if $v_i$ is not invariant under all of $G$. The unbroken subgroup is the stabilizer of $v$:

$$
H=\{g\in G\mid D(g)v=v\}.
$$

If $H\ne G$, the state has spontaneously broken $G$ to $H$.

For infinitesimal transformations, using this volume's charge convention,

$$
\delta_a\mathcal O_i=i[Q_a,\mathcal O_i],
$$

a candidate order parameter detects breaking of the generator $Q_a$ when

$$
\langle\delta_a\mathcal O_i\rangle\ne 0.
$$

Equivalently,

$$
i\langle[Q_a,\mathcal O_i]\rangle\ne 0.
$$

That compact formula is the bridge from order parameters to Goldstone's theorem. A broken generator is one whose charge fails to annihilate the vacuum in a way visible to local observables.

:::note[Convention-sensitive source note]
The sign in $\delta_a\mathcal O=i[Q_a,\mathcal O]$ matches the convention used earlier in this volume. Many books instead write $\delta\mathcal O=-i[\epsilon Q,\mathcal O]$ or choose $U(\epsilon)=e^{+i\epsilon Q}$. The physics is unchanged, but the sign in the commutator test changes with the convention.
:::

## Setup and conventions

We work in a relativistic QFT unless otherwise stated. Spacetime dimension is $d$, spatial volume is $V$, and $G$ is an internal global symmetry with conserved currents $j_a^\mu$ and charges

$$
Q_a=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x),
$$

when the integral is well-defined. For local arguments, use a regulated charge

$$
Q_a[f_R]=\int d^{d-1}\mathbf x\, f_R(\mathbf x)j_a^0(t,\mathbf x),
$$

where $f_R$ is $1$ near the operator insertion and smoothly dies off at large radius. This avoids pretending that infinite-volume charges are harmless operators.

To select a phase, introduce a source $h^i$ coupled to $\mathcal O_i$. In Lorentzian notation,

$$
Z[h]
=
\int\mathcal D\Phi\,
\exp\left(iS[\Phi]+i\int d^dx\,h^i\mathcal O_i\right),
\qquad
Z[h]=e^{iW[h]}.
$$

With this convention,

$$
\frac{\delta W}{\delta h^i(x)}=\langle\mathcal O_i(x)\rangle_h.
$$

For a constant source and translation-invariant state, this becomes

$$
\langle\mathcal O_i\rangle_h
=
\frac{1}{\operatorname{Vol}(M)}\frac{\partial W}{\partial h^i}.
$$

At finite temperature, a common Euclidean thermodynamic convention is

$$
H_h=H-h\int d^{d-1}\mathbf x\,\mathcal O,
\qquad
f(h)=-\frac{1}{\beta V}\log Z_E(h),
$$

so that

$$
\langle\mathcal O\rangle_h=-\frac{\partial f}{\partial h}.
$$

:::note[Source-sign note]
The minus sign in the thermodynamic formula comes from defining $H_h=H-h\int\mathcal O$. In Lorentzian source language we instead wrote $+i\int h\mathcal O$ in the exponent. Both conventions are standard. Always state whether the source is added to the action or subtracted from the Hamiltonian.
:::

## Order parameters from sources

The cleanest definition of a broken-phase order parameter uses a source. Let $h$ be a constant source that explicitly favors one direction of the would-be order parameter. Define

$$
\langle\mathcal O\rangle_{\text{phase}}
=
\lim_{h\to0^+}\lim_{V\to\infty}\langle\mathcal O\rangle_{h,V}.
$$

The source does two jobs.

First, it selects one phase. In an Ising-like theory with $\mathbb Z_2$ symmetry $\phi\mapsto-\phi$, a positive source $h\phi$ selects the $\langle\phi\rangle>0$ phase, while a negative source selects the $\langle\phi\rangle<0$ phase.

Second, it prevents finite-volume tunneling from averaging the order parameter to zero. In a finite box, a symmetric ground state can be approximately

$$
|\Omega_+\rangle+|\Omega_-\rangle,
$$

so that $\langle\phi\rangle=0$. In infinite volume, the overlap between macroscopically distinct phases vanishes:

$$
\langle\Omega_+|\Omega_-\rangle\to0.
$$

The order of limits is therefore not etiquette. It is physics.

A useful mental model is the magnetization of a ferromagnet. In a finite system with no external magnetic field, exact spin-rotation symmetry may force the total magnetization vector to vanish. In a macroscopic sample, an infinitesimal magnetic field selects a direction; after taking the thermodynamic limit, the field can be removed and the magnetization remains.

## The long-distance correlator criterion

Sometimes the one-point function vanishes because the state is symmetric, because finite-volume tunneling has restored the symmetry, or because one is deliberately working in an ensemble that averages over broken phases. Long-distance correlators can still reveal order.

For a scalar order parameter, cluster decomposition in a pure broken phase gives

$$
\lim_{|x-y|\to\infty}
\langle\mathcal O(x)\mathcal O(y)\rangle
=
\langle\mathcal O\rangle^2.
$$

Thus a nonzero constant at long distance indicates long-range order:

$$
\lim_{|x-y|\to\infty}
\langle\mathcal O(x)\mathcal O(y)\rangle\ne0.
$$

In the Ising example, a finite-volume symmetric state may have

$$
\langle\phi\rangle=0,
$$

but below the critical temperature,

$$
\lim_{|x-y|\to\infty}\langle\phi(x)\phi(y)\rangle=v^2.
$$

This is why long-distance correlators are often more robust than one-point functions.

The connected correlator is

$$
\langle\mathcal O(x)\mathcal O(y)\rangle_c
=
\langle\mathcal O(x)\mathcal O(y)\rangle
-\langle\mathcal O(x)\rangle\langle\mathcal O(y)\rangle.
$$

In a gapped pure phase, it decays exponentially at long distance:

$$
\langle\mathcal O(x)\mathcal O(y)\rangle_c
\sim e^{-|x-y|/\xi},
$$

where $\xi$ is the correlation length. At a continuous phase transition, $\xi$ diverges and the order parameter becomes part of the critical scaling data.

## Examples

### Ising-type discrete symmetry

Consider a real scalar field with $\mathbb Z_2$ symmetry

$$
\phi\mapsto-\phi.
$$

The simplest order parameter is

$$
\langle\phi\rangle.
$$

In a symmetric phase,

$$
\langle\phi\rangle=0.
$$

In a broken phase,

$$
\langle\phi\rangle=+v
\qquad\text{or}\qquad
\langle\phi\rangle=-v.
$$

The unbroken subgroup is trivial because the nontrivial element of $\mathbb Z_2$ maps one phase to the other. There is no Goldstone boson because the broken symmetry is discrete. Domain walls can separate spatial regions in different vacua.

A classical potential that illustrates the pattern is

$$
V(\phi)=\frac{\lambda}{4}(\phi^2-v^2)^2.
$$

The two minima are symmetry-related. The quantum statement is not that the potential drawing itself proves SSB; it is that the infinite-volume quantum theory can have pure phases localized near either minimum.

### O(N) vector order parameter

Let $\boldsymbol\phi=(\phi^1,\ldots,\phi^N)$ transform in the vector representation of $O(N)$. A broken phase can have

$$
\langle\phi^i\rangle=v n^i,
\qquad
n^in^i=1.
$$

The direction $n^i$ is chosen by the state. The subgroup that preserves it is

$$
O(N-1),
$$

so the breaking pattern is

$$
O(N)\to O(N-1).
$$

The vacuum manifold is

$$
O(N)/O(N-1)\simeq S^{N-1}.
$$

For relativistic internal symmetry breaking, the number of Goldstone modes is

$$
\dim O(N)-\dim O(N-1)=N-1.
$$

The invariant magnitude $v$ characterizes the phase, while the direction $n^i$ labels which pure phase has been selected.

### Chiral condensate

In QCD-like theories with approximately massless quarks, a standard order parameter for chiral symmetry breaking is the fermion bilinear

$$
\Sigma^i{}_j
=\langle\bar\psi_{Rj}\psi_L^i\rangle.
$$

For $N_f$ light flavors, the classical continuous flavor symmetry is roughly

$$
SU(N_f)_L\times SU(N_f)_R,
$$

ignoring the anomalous axial $U(1)$ and other global-form refinements. A condensate proportional to the identity,

$$
\Sigma^i{}_j\propto \delta^i{}_j,
$$

preserves the diagonal vector subgroup,

$$
SU(N_f)_L\times SU(N_f)_R\to SU(N_f)_V.
$$

The pions are the corresponding pseudo-Goldstone bosons when quark masses are small but nonzero. This example is important because the order parameter is composite, not a fundamental scalar field.

### Superfluid order parameter

For a system with a global $U(1)$ particle-number symmetry, a superfluid phase is often described by a complex order parameter

$$
\langle\Psi\rangle=\rho^{1/2}e^{i\theta}.
$$

The phase $\theta$ labels the broken $U(1)$ direction. The Goldstone mode is the long-wavelength fluctuation of $\theta$. In relativistic language, the same idea appears for a complex scalar field with

$$
\phi\mapsto e^{i\alpha}\phi,
\qquad
\langle\phi\rangle\ne0.
$$

In actual many-body systems, number conservation, finite volume, boundary conditions, and the grand-canonical ensemble require care. The order parameter is still an efficient long-distance diagnostic because the phase stiffness and correlation functions reveal the broken symmetry.

### Wilson loops and generalized order parameters

Not every important phase distinction is detected by a local operator. In gauge theories and generalized symmetry, an extended operator can play the role of an order parameter.

For a Wilson loop $W(C)$ in a gauge theory, large-loop behavior can diagnose confinement or screening:

$$
\langle W(C)\rangle\sim e^{-\sigma\operatorname{Area}(C)}
\qquad\text{area law,}
$$

or

$$
\langle W(C)\rangle\sim e^{-\mu\operatorname{Perimeter}(C)}
\qquad\text{perimeter law.}
$$

In modern language, this is naturally tied to one-form symmetry and its realization. This is not ordinary zero-form Landau order, but the logic is analogous: identify the symmetry, identify charged probes, and study their long-distance behavior.

## Order parameters and unbroken subgroups

An order parameter does not merely say “broken” or “unbroken.” It tells you the breaking pattern.

Let $\mathcal O_i$ transform in a representation $R$ of $G$. A vacuum expectation value $v_i$ defines a stabilizer subgroup

$$
H_v=\{g\in G\mid R(g)_i{}^jv_j=v_i\}.
$$

The broken generators are those $T_a$ for which

$$
(T_a)_i{}^jv_j\ne0.
$$

Using the charge-action convention,

$$
\langle\delta_a\mathcal O_i\rangle
=(T_a)_i{}^jv_j,
$$

up to the representation convention for $T_a$. Therefore the number of broken generators is

$$
\dim G-\dim H_v.
$$

In the relativistic internal-symmetry case, this number is also the number of Goldstone fields. The Goldstone fields can be thought of as slow spacetime-dependent motion along the orbit

$$
G\cdot v\simeq G/H_v.
$$

The radial or amplitude fluctuations are not fixed by symmetry and are often massive. That separation is the origin of the nonlinear sigma model as the low-energy theory of the order-parameter direction.

## Susceptibility and response

An order parameter is often accompanied by a susceptibility. If $h$ couples to $\mathcal O$, then

$$
\chi_{\mathcal O}
=\frac{\partial\langle\mathcal O\rangle_h}{\partial h}\bigg|_{h=0}
$$

measures how strongly the system responds to the source. In Euclidean finite-temperature language,

$$
\chi_{\mathcal O}
=\int_0^\beta d\tau\int d^{d-1}\mathbf x\,
\langle\mathcal O(\tau,\mathbf x)\mathcal O(0,\mathbf 0)\rangle_c,
$$

up to normalization conventions for volume-averaged operators.

Near a continuous phase transition, the susceptibility can diverge. This signals that the order-parameter fluctuations become long-ranged. In a relativistic critical theory, the order parameter becomes a scaling operator with dimension $\Delta_{\mathcal O}$, and its two-point function behaves schematically as

$$
\langle\mathcal O(x)\mathcal O(0)\rangle
\sim \frac{1}{|x|^{2\Delta_{\mathcal O}}}.
$$

Thus order parameters are not only phase labels; they are also entries in the critical data of the theory.

## Effective potentials and what they do not prove

A common way to visualize an order parameter is through an effective potential. If $\varphi$ denotes a constant classical field or expectation value, one writes an effective action of the form

$$
\Gamma[\varphi]
= -\int d^dx\, V_{\text{eff}}(\varphi)+\cdots
$$

in Lorentzian signature, or

$$
\Gamma_E[\varphi]
= \int d^dx_E\, V_{\text{eff}}(\varphi)+\cdots
$$

in Euclidean signature. Minima of $V_{\text{eff}}$ identify candidate vacuum expectation values.

For the $\mathbb Z_2$ example, a double-well potential suggests two phases. For a complex scalar, a Mexican-hat potential suggests a circle of phases:

$$
V(\phi)=\lambda(|\phi|^2-v^2)^2.
$$

But there are two important caveats.

First, a classical or one-loop potential is a tool, not a theorem. Quantum fluctuations, infrared effects, gauge dependence, and nonperturbative tunneling can change the interpretation.

Second, the exact Legendre effective potential is convex under broad assumptions. In a broken phase, the familiar nonconvex double-well picture is often a semiclassical or constrained effective potential, while the exact convex potential contains flat regions associated with mixed states. For identifying pure phases, one must still keep the source and infinite-volume limits straight.

:::note[Convention-sensitive source note]
Some books define $V_{\text{eff}}$ by $\Gamma=-\int V_{\text{eff}}$ in Lorentzian signature; others define it directly in Euclidean signature. The sign of the potential term in $\Gamma$ therefore changes between conventions, but the physical rule “vacua minimize the energy density” does not.
:::

## Renormalization of order parameters

In an interacting QFT, a local order parameter is usually a composite operator. Composite operators require renormalization. A bare operator $\mathcal O_0$ may be related to renormalized operators by

$$
\mathcal O_{0,i}=Z_i{}^j\mathcal O_{R,j}+\sum_k c_i{}^k\mathcal O_{R,k},
$$

where the sum includes all operators with the same quantum numbers and compatible dimension or power-counting status. If the identity operator has the same quantum numbers, additive renormalization can occur.

This matters in practice. The statement “$\langle\mathcal O\rangle$ is nonzero” is cleanest when $\mathcal O$ transforms nontrivially, so it cannot mix with the identity. For example, an Ising-odd field cannot mix additively with the identity while the $\mathbb Z_2$ symmetry is exact.

For symmetry-neutral condensates, one must often subtract contact terms or compare phases. The energy density, for instance, can distinguish phases, but its absolute value is scheme-dependent.

The robust information is usually not the raw number but the transformation property, scaling behavior, discontinuity across a transition, or long-distance correlator.

## Gauge-invariant diagnostics

A local gauge-charged field is not a physical order parameter for a gauge symmetry. In an unfixed gauge,

$$
\langle\phi(x)\rangle=0
$$

for a gauge-charged field $\phi$ under very general circumstances. This is not a failure of the Higgs mechanism. It is a reminder that gauge symmetry is redundancy.

Physical diagnostics of Higgs, Coulomb, confined, or topologically ordered phases include:

- gauge-invariant composite operators,
- spectra of massive vector and scalar excitations,
- Wilson and ’t Hooft loop behavior,
- response to background fields for global symmetries,
- boundary conditions and edge modes,
- remnants of global symmetries after quotienting gauge redundancy,
- and higher-form symmetry realization.

For scalar QED, writing $\langle\phi\rangle\ne0$ in a fixed gauge is often a useful perturbative shorthand. The gauge-invariant content is that the spectrum and long-distance force law are those of a Higgs phase.

This distinction prevents a common error: treating a gauge choice as a physical symmetry-breaking statement.

## Nonlocal and generalized order parameters

Landau's paradigm is built around local order parameters for ordinary symmetries. QFT has more possibilities.

A **disorder operator** creates a defect rather than measuring an ordinary local field. In the two-dimensional Ising model, order and disorder operators exchange roles under Kramers–Wannier duality.

A **line operator** can be an order parameter for a one-form symmetry. In $d$ dimensions, a one-form symmetry acts on line operators rather than local operators. Whether the symmetry is broken can be diagnosed by the large-size behavior of the charged line.

A **surface operator** can similarly diagnose higher-form symmetry realization.

A **topological phase** may have no local order parameter at all. Its phase distinction can be encoded by ground-state degeneracy on nontrivial spatial manifolds, anyon data, topological entanglement entropy, modular transformations, or a TQFT sector.

The modern moral is not that order parameters are obsolete. It is that “order parameter” has expanded from a single local expectation value to a menu of symmetry-sensitive diagnostics.

## Algebraic criterion for broken generators

The order-parameter test can be phrased without committing to a particular elementary field. Choose a local operator $\mathcal O$ and a regulated charge $Q_a[f_R]$. A generator is spontaneously broken if

$$
\lim_{R\to\infty}
\langle\Omega|i[Q_a[f_R],\mathcal O(0)]|\Omega\rangle\ne0.
$$

Using current conservation, this commutator can be represented by a current insertion integrated over a surface around $\mathcal O$. This is the operator form of the Ward identity.

In the next pages, this nonzero commutator becomes the starting point for Goldstone's theorem. Schematically, one studies

$$
\langle\Omega|j_a^\mu(x)\mathcal O(0)|\Omega\rangle
$$

and uses current conservation plus the spectral representation. A nonzero equal-time commutator forces massless spectral support. Thus the order parameter is not merely a diagnostic after the fact; it is the input that makes the theorem go.

## Common pitfalls

**Taking the limits in the wrong order.** If you send $h\to0$ before $V\to\infty$, a finite system usually returns the symmetric expectation value. Broken phases require the infinite-volume or thermodynamic limit first.

**Calling any VEV an order parameter.** A nonzero expectation value matters only if it distinguishes a phase or transforms in a way that detects symmetry realization.

**Forgetting operator renormalization.** Composite order parameters require renormalization. Their numerical value can be scheme-dependent even when the phase distinction is not.

**Using a gauge-variant field as a physical diagnostic.** Gauge-fixed VEVs can organize perturbation theory, but physical order parameters must be gauge-invariant or be rephrased in terms of gauge-invariant observables.

**Assuming the order parameter is unique.** A phase can have many order parameters. Any operator with overlap with the broken direction can diagnose the same long-distance order.

**Confusing explicit breaking with source selection.** A small source is a tool for selecting a phase and then is removed. A physical symmetry-breaking term left in the Hamiltonian or action is explicit breaking.

**Missing long-distance order because the one-point function vanishes.** Symmetric ensembles and finite boxes can have zero one-point function while long-distance correlators reveal order.

**Expecting local order parameters for all phases.** Topological phases, deconfined gauge theories, and generalized-symmetry phases can require extended or categorical diagnostics.

## Relations to other pages

This page is the entry point for the Spontaneous Symmetry Breaking chapter. [Degenerate Vacua](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/degenerate-vacua/) will explain why symmetry-related phases become distinct in infinite volume. [Goldstone Theorem](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-theorem/) will use the nonzero commutator criterion to derive massless modes.

The Noether pages supply the current and charge machinery, especially [Charges Acting on Local Operators](/symmetry-anomalies-topology/noether-currents-ward-identities/charges-acting-on-local-operators/). The Background Fields and Gauging chapter supplies the source language used to define response and phase selection.

Later, [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) generalizes the order-parameter idea from local operators to extended charged operators. [Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/) develops Wilson lines, ’t Hooft lines, disorder operators, and domain walls. The Anomalies chapters explain how broken phases can match ultraviolet anomalies through Goldstone and Wess–Zumino terms.

## Research status

For ordinary Landau phases, the role of local order parameters is established and textbook-standard. The main subtleties are conceptual rather than speculative: limits, finite volume, renormalization, gauge invariance, and long-distance correlators.

The active frontier is the expansion of “order” beyond local Landau order. Higher-form symmetries, non-invertible symmetries, topological order, fracton phases, mixed-state phases, subsystem symmetries, boundary-sensitive order, and categorical symmetry all require more refined diagnostics. Modern QFT often treats local order parameters as one important member of a much larger family of symmetry-sensitive observables.

## Exercises

### Exercise 1: The stabilizer of an O(N) vector

Let $\phi^i$ transform as a vector under $O(N)$ and suppose

$$
\langle\phi^i\rangle=v\delta^{iN}.
$$

Find the unbroken subgroup and the number of broken generators.

<details><summary><strong>Solution</strong></summary>

The unbroken subgroup consists of orthogonal transformations that leave the $N$th unit vector fixed. These transformations rotate only the first $N-1$ components, so

$$
H=O(N-1).
$$

The dimensions are

$$
\dim O(N)=\frac{N(N-1)}{2},
\qquad
\dim O(N-1)=\frac{(N-1)(N-2)}{2}.
$$

Thus the number of broken generators is

$$
\frac{N(N-1)}{2}-\frac{(N-1)(N-2)}{2}=N-1.
$$

The vacuum manifold is $O(N)/O(N-1)\simeq S^{N-1}$.

</details>

### Exercise 2: Order of limits in a two-state model

Suppose a finite-volume system has two almost-degenerate states $|+\rangle$ and $|-\rangle$ with

$$
\langle+|\phi|+\rangle=v,
\qquad
\langle-|\phi|-\rangle=-v,
$$

and a symmetric ground state

$$
|S\rangle=\frac{1}{\sqrt2}(|+\rangle+|-\rangle).
$$

Ignoring exponentially small overlaps, compute $\langle S|\phi|S\rangle$. What does this teach you about finite volume?

<details><summary><strong>Solution</strong></summary>

Using orthogonality and ignoring cross terms,

$$
\langle S|\phi|S\rangle
=\frac12\left(\langle+|\phi|+\rangle+\langle-|\phi|-\rangle\right)
=\frac12(v-v)=0.
$$

The symmetric finite-volume state hides the broken order parameter. A tiny source selects either $|+\rangle$ or $|-\rangle$, and the infinite-volume limit prevents tunneling between them. This is why the phase-defining limit is

$$
\lim_{h\to0}\lim_{V\to\infty},
$$

not the reverse.

</details>

### Exercise 3: Charge commutator test for U(1)

Let a complex scalar field have $U(1)$ charge $+1$, so that

$$
[Q,\phi]=\phi.
$$

Using this volume's convention $\delta\phi=i[Q,\phi]$, show that a state with $\langle\phi\rangle=v\ne0$ breaks the $U(1)$ symmetry.

<details><summary><strong>Solution</strong></summary>

The infinitesimal variation is

$$
\delta\phi=i[Q,\phi]=i\phi.
$$

Taking the expectation value gives

$$
\langle\delta\phi\rangle=i\langle\phi\rangle=iv.
$$

If $v\ne0$, this is nonzero. Therefore the order parameter is not invariant under the $U(1)$ generator, and the state breaks the symmetry.

</details>

### Exercise 4: Why a gauge-charged VEV is not enough

In scalar QED, a charged scalar transforms as

$$
\phi(x)\mapsto e^{i\alpha(x)}\phi(x)
$$

under a gauge transformation. Explain why $\langle\phi\rangle$ is not a gauge-invariant order parameter.

<details><summary><strong>Solution</strong></summary>

A physical local observable must be invariant under gauge transformations. Since $\phi(x)$ changes by a position-dependent phase, its expectation value is gauge-dependent. In an unfixed gauge, averaging over gauge-equivalent configurations makes

$$
\langle\phi(x)\rangle=0
$$

under broad assumptions. In a fixed gauge, a nonzero $\langle\phi\rangle$ can be a useful perturbative shorthand, but the physical Higgs phase must be diagnosed by gauge-invariant information such as the spectrum, screening behavior, Wilson-line behavior, or gauge-invariant composite operators.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially “Secret Symmetry,” “Soft Pions,” and “Classical Lumps and Their Quantum Descendants.”
- Mark Srednicki, *Quantum Field Theory*, §§30–32.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 28.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters on effective actions, symmetries, and spontaneous symmetry breaking.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, Chs. 5 and 8.
- C. P. Burgess, *Introduction to Effective Field Theory*, Chs. 4 and 14.
- L. D. Landau and E. M. Lifshitz, *Statistical Physics*. Classic thermodynamic and phase-transition order-parameter language.
- J. Goldstone, A. Salam, and S. Weinberg, “Broken Symmetries,” *Physical Review* **127** (1962) 965–970.
- S. Elitzur, “Impossibility of Spontaneously Breaking Local Symmetries,” *Physical Review D* **12** (1975) 3978–3982.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” *Journal of High Energy Physics* **2015**. Modern extension of order-parameter logic to extended charged operators and higher-form symmetries.

## Version history

- 2026-06-17: First polished draft. Added source-based definition, order-of-limits criterion, long-distance correlator test, examples, effective-potential caveats, renormalization caveats, gauge-invariant diagnostics, generalized order-parameter preview, and exercises with solutions.
