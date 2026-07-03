---
title: "Degenerate Vacua"
description: "Explains how symmetry-related vacua become distinct phases in QFT, why finite-volume ground states can remain symmetric, and how sources, superselection, cluster decomposition, and domain walls diagnose spontaneous symmetry breaking."
sidebar:
  label: "Degenerate Vacua"
  order: 2
level: Graduate
status: "Polished draft"
source: "Coleman on secret symmetry and classical lumps; Srednicki §§30–32; Schwartz Ch. 28; Weinberg Vol. II on effective actions; Altland–Simons on broken symmetry and collective phenomena."
topics:
  - degenerate vacua
  - spontaneous symmetry breaking
  - infinite-volume limit
  - superselection sectors
  - cluster decomposition
  - vacuum manifold
  - domain walls
  - effective potential
canonicalTopics:
  - degenerate-vacua
  - vacuum-manifold
  - symmetry-related-vacua
  - superselection-sector
  - source-selection
  - cluster-decomposition
  - domain-wall
researchStatus:
  established:
    - "In an infinite-volume QFT, symmetry-related broken vacua can define distinct pure phases even though a finite-volume system may have a unique symmetric ground state."
    - "For ordinary internal symmetry breaking, the unbroken subgroup is the stabilizer of the order parameter and the connected vacuum manifold is locally modeled by G/H."
  active:
    - "Modern refinements involve generalized symmetries, categorical defects, topological order, mixed states, finite-volume quantum devices, and gauge-invariant definitions of phases where no local order parameter exists."
---

## Summary

A **degenerate vacuum** is one member of a set of lowest-energy states that are physically distinct in the infinite-volume theory. In spontaneous symmetry breaking, these vacua are often related by an exact symmetry of the theory:

$$
|\Omega_\theta\rangle = U(g_\theta)|\Omega_0\rangle,
$$

but one selected vacuum need not be invariant under the full symmetry group.

This sounds paradoxical only if one imports too much finite-dimensional quantum mechanics intuition. In a finite double-well quantum-mechanical problem, the exact ground state is usually the symmetric superposition of wavefunctions localized in the two wells. In an infinite-volume field theory, tunneling between macroscopically distinct field configurations is suppressed so strongly that the broken vacua become orthogonal superselection sectors. A local observer inside one sector sees one phase, not the symmetric average over all phases.

The clean broken-phase definition uses a source and an order of limits:

$$
\boxed{
\langle\mathcal O\rangle_{\text{broken}}
=
\lim_{h\to0}\lim_{V\to\infty}\langle\mathcal O\rangle_{h,V}.
}
$$

If the source is removed before the infinite-volume limit, the answer can instead be the symmetric finite-volume state. This order of limits is the difference between a symmetry-broken phase and a quantum-mechanical cat state.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A diagram comparing the correct and reversed order of limits for degenerate vacua: at finite volume and zero source the exact state can be symmetric, a small source selects one well, the infinite-volume limit makes the two phases orthogonal, and only then can the source be removed. The reversed path returns the symmetric finite-volume state.](/figures/symmetry-anomalies-topology/degenerate-vacua-order-of-limits.svg)

<figcaption>

Degenerate vacua in QFT are phase data, not merely minima drawn on a potential. A tiny source selects a branch; the infinite-volume limit makes different branches orthogonal; removing the source afterward leaves a pure broken phase. Reversing the order of limits usually restores the symmetric finite-volume answer.

</figcaption>
</figure>

This page explains why degenerate vacua are real, how they are selected, how they differ from accidental degeneracy, and why they are the stage on which Goldstone modes, domain walls, anomaly matching, and low-energy effective theories appear.

## Prerequisites

Read [Order Parameters](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/order-parameters/) first. You should also know [What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/), [Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/), [Selection Rules](/symmetry-anomalies-topology/ordinary-global-symmetries/selection-rules/), and [Conserved Charges](/symmetry-anomalies-topology/noether-currents-ward-identities/conserved-charges/).

The background-field chapter is useful because phase selection is naturally described by sources. The next page, [Goldstone Theorem](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-theorem/), uses the nonzero order-parameter commutator introduced here.

## Core idea

A symmetry-broken phase is not defined by a drawing of a classical potential. It is defined by a state, a symmetry action, and an infinite-volume limiting procedure.

Let $G$ be an internal global symmetry and let $\mathcal O_i$ be an operator whose expectation value is

$$
v_i=\langle\Omega|\mathcal O_i|\Omega\rangle.
$$

If $v_i$ is not invariant under all of $G$, then the state $|\Omega\rangle$ preserves only the stabilizer subgroup

$$
H=\{g\in G\mid D(g)v=v\}.
$$

The symmetry-related vacua are then, at least locally near the identity,

$$
\mathcal M_{\text{vac}}\simeq G/H.
$$

This is the **vacuum manifold** of the broken phase. The notation should not be overread. In a full QFT, the vacuum manifold is not merely the set of minima of a bare potential; it is the set of pure infinite-volume ground states related by the symmetry and distinguished by local or extended observables.

The key facts are:

- finite volume can hide degeneracy;
- a source selects a phase;
- infinite volume makes different phases orthogonal;
- local observables cannot mix superselection sectors;
- continuous vacuum manifolds imply flat directions, which lead to Goldstone physics under the assumptions of the Goldstone theorem.

## Setup and conventions

We use the volume's mostly-minus Lorentzian convention. For a real scalar example, write

$$
\mathcal L=\frac12\partial_\mu\phi\,\partial^\mu\phi - V(\phi),
\qquad
V(\phi)=\frac{\lambda}{4}(\phi^2-v^2)^2,
\qquad \lambda>0.
$$

This normalization is chosen for readability. Some texts use $\lambda(\phi^2-v^2)^2/24$ or other factors; none of the symmetry statements depend on this choice.

The $\mathbb Z_2$ symmetry acts as

$$
\phi\mapsto -\phi.
$$

The classical minima are

$$
\phi=+v,
\qquad
\phi=-v.
$$

For a continuous example, take a complex scalar field with a $U(1)$ symmetry,

$$
\Phi\mapsto e^{-i\alpha}\Phi,
$$

and potential

$$
V(\Phi)=\frac{\lambda}{4}\left(2\Phi^\dagger\Phi-v^2\right)^2.
$$

The minima obey

$$
\Phi=\frac{v}{\sqrt2}e^{-i\theta},
\qquad
\theta\sim \theta+2\pi.
$$

The vacuum manifold is a circle:

$$
\mathcal M_{\text{vac}}\simeq U(1)/\{1\}\simeq S^1.
$$

:::note[Convention-sensitive source note]
This page uses a source $h$ that favors a positive order parameter through a Hamiltonian deformation $H_h=H-h\int d^{d-1}\mathbf x\,\mathcal O$. With this thermodynamic convention, $\langle\mathcal O\rangle_h=-\partial f/\partial h$. In Lorentzian path-integral notation, the corresponding action source is often written with the opposite sign convention. Always check whether the source is added to the action or subtracted from the Hamiltonian.
:::

## What counts as a vacuum?

In a relativistic QFT, a vacuum is usually a translation-invariant state of lowest energy density. The words **energy density** matter. In infinite volume, total energies are infinite, but energy differences per unit volume are meaningful.

For a finite spatial volume $V$, a Hamiltonian may have a unique normalized ground state $|0,V\rangle$. If the Hamiltonian commutes with the symmetry operator $U(g)$ and the ground state is nondegenerate, then

$$
U(g)|0,V\rangle=e^{i\alpha(g)}|0,V\rangle.
$$

In that situation a symmetry-odd operator has zero expectation value:

$$
\langle0,V|\phi|0,V\rangle=0.
$$

This is not a contradiction with spontaneous symmetry breaking. It says only that finite volume is too small to define the broken phase without a source or boundary condition. The exact finite-volume state can be a symmetric superposition of states localized near the different classical minima.

In infinite volume, the Hilbert-space representation itself can split into inequivalent sectors. The two limits

$$
\lim_{V\to\infty}\lim_{h\to0}
\qquad\text{and}\qquad
\lim_{h\to0}\lim_{V\to\infty}
$$

need not agree. Broken symmetry lives in this noncommutativity of limits.

## The double well: quantum mechanics versus field theory

The simplest warning comes from the double well in ordinary quantum mechanics:

$$
H=\frac{p^2}{2}+\frac{\lambda}{4}(x^2-v^2)^2.
$$

There are wavepackets localized near $x=+v$ and $x=-v$, but they are not exact ground states. The exact low-energy eigenstates are approximately

$$
|S\rangle\simeq \frac{|+\rangle+|-\rangle}{\sqrt2},
\qquad
|A\rangle\simeq \frac{|+\rangle-|-\rangle}{\sqrt2},
$$

with an exponentially small but nonzero energy splitting from tunneling. The true ground state is symmetric.

A scalar field theory is closer to infinitely many coupled double wells, one at each spatial point. A transition from the $+v$ phase to the $-v$ phase requires a coherent macroscopic rearrangement of the field. In a finite box, the tunneling splitting is typically exponentially small in spatial volume:

$$
\Delta E(V)\sim e^{-cV}
$$

for some positive constant $c$ in a gapped phase. More geometrically, the Euclidean tunneling configuration contains an interface whose action grows with the size of the system.

Thus

$$
\lim_{V\to\infty}\Delta E(V)=0.
$$

The two states $|\Omega_+\rangle$ and $|\Omega_-\rangle$ become exactly degenerate and orthogonal in the infinite-volume limit:

$$
\langle\Omega_+|\Omega_-\rangle=0.
$$

The symmetry still exists. It maps one representation sector to another:

$$
U(\mathbb Z_2)|\Omega_+\rangle=|\Omega_-\rangle.
$$

But a local experiment performed inside the $+$ phase does not average over the $-$ phase. That is why the order parameter can be nonzero.

## Source selection and the phase-defining limit

Let $\mathcal O$ be an order parameter and add a uniform source:

$$
H_h=H-h\int d^{d-1}\mathbf x\,\mathcal O(\mathbf x).
$$

For finite $V$ and nonzero $h$, the degeneracy is lifted. In the Ising-like scalar example, $h>0$ selects the phase with

$$
\langle\phi\rangle>0,
$$

while $h<0$ selects the phase with

$$
\langle\phi\rangle<0.
$$

The broken expectation value is defined by

$$
\langle\mathcal O\rangle_+
=
\lim_{h\to0^+}\lim_{V\to\infty}\langle\mathcal O\rangle_{h,V}.
$$

The symmetric expectation value is often

$$
\lim_{V\to\infty}\lim_{h\to0}\langle\mathcal O\rangle_{h,V}=0.
$$

The two answers refer to different physical preparations. One is a pure broken phase selected by an infinitesimal source. The other is the symmetric finite-volume state continued to infinite volume.

At finite temperature, the same logic appears in the free-energy density

$$
f(h)=-\frac{1}{\beta V}\log Z(h).
$$

At finite $V$, $f(h)$ is usually analytic at $h=0$. In the thermodynamic limit, $f(h)$ can develop a cusp, and

$$
m(h)=-\frac{\partial f}{\partial h}
$$

can jump at $h=0$. The jump is the thermodynamic signature of degenerate phases.

## Cluster decomposition and cat states

A pure vacuum phase should satisfy cluster decomposition: widely separated local experiments become statistically independent. For a scalar operator,

$$
\lim_{|\mathbf x|\to\infty}
\langle\Omega|\phi(\mathbf x)\phi(0)|\Omega\rangle
=\langle\Omega|\phi|\Omega\rangle^2.
$$

In the $+$ broken phase,

$$
\langle\Omega_+|\phi|\Omega_+\rangle=v,
$$

so the long-distance two-point function tends to $v^2$.

Now form the symmetric cat state

$$
|S\rangle=\frac{|\Omega_+\rangle+|\Omega_-\rangle}{\sqrt2},
$$

assuming the cross terms vanish in infinite volume. Then

$$
\langle S|\phi|S\rangle=0,
$$

but

$$
\lim_{|\mathbf x|\to\infty}\langle S|\phi(\mathbf x)\phi(0)|S\rangle=v^2.
$$

This violates cluster decomposition because

$$
v^2\ne 0^2.
$$

That is why the symmetric cat state is not the right pure vacuum for local physics inside a broken phase. It is a superposition of macroscopically different phases, not a single thermodynamic phase.

This is a useful diagnostic: when a state restores the one-point function but retains long-range order in two-point functions, ask whether it is a phase-averaged or cat-like state rather than a pure phase.

## Discrete broken symmetry

For a discrete internal symmetry, degenerate vacua can exist without Goldstone modes. The $\mathbb Z_2$ scalar theory has two broken vacua,

$$
\mathcal M_{\text{vac}}=\{+v,-v\}.
$$

There is no continuous direction along which the order parameter can vary without changing the potential. Therefore there is no symmetry-enforced massless particle.

Instead, the characteristic extended object is a **domain wall**. In one spatial dimension, a domain wall is a kink interpolating between the two vacua:

$$
\phi(x\to-\infty)=-v,
\qquad
\phi(x\to+\infty)=+v.
$$

In higher dimensions, the wall is a codimension-one interface. Its tension is finite because the field only changes significantly near the wall. The existence and stability of such walls depend on the disconnected components of the vacuum manifold. For the $\mathbb Z_2$ example,

$$
\pi_0(\mathcal M_{\text{vac}})\ne0,
$$

which is the topological statement that there are disconnected choices at spatial infinity.

Discrete breaking is therefore organized by degenerate vacua, domain walls, and tunneling suppression, not by Goldstone bosons.

## Continuous broken symmetry

For a continuous internal symmetry, the set of vacua typically forms a manifold. If $G$ is broken to $H$, then

$$
\mathcal M_{\text{vac}}\simeq G/H.
$$

The complex scalar example breaks

$$
U(1)\to \{1\},
$$

so

$$
\mathcal M_{\text{vac}}\simeq S^1.
$$

An $O(N)$ vector model with order parameter

$$
\langle\phi^i\rangle=v\delta^{iN}
$$

breaks

$$
O(N)\to O(N-1),
$$

and the vacuum manifold is

$$
O(N)/O(N-1)\simeq S^{N-1}.
$$

The tangent directions to $G/H$ at the selected vacuum are the broken-generator directions. In a Lorentz-invariant relativistic QFT with an exact continuous internal symmetry, these directions produce massless Goldstone modes under the assumptions of Goldstone's theorem.

The vacuum degeneracy and the Goldstone theorem are logically distinct:

$$
\text{degenerate continuous vacua}
\quad\Longrightarrow\quad
\text{flat order-parameter directions},
$$

while

$$
\text{broken continuous internal symmetry + locality + spectral assumptions}
\quad\Longrightarrow\quad
\text{massless excitations}.
$$

The next page makes the second implication precise.

## Effective potential and convexity

The phrase “the potential has a Mexican hat” is pedagogically useful but technically treacherous.

The classical potential of the complex scalar model has a circle of minima. Perturbatively, one often studies a nonconvex effective potential near one chosen branch. This gives the familiar picture of radial and angular fluctuations.

However, the exact Legendre effective potential in infinite volume is convex. In a theory with two discrete broken vacua, the exact effective potential can develop a flat region between the two order-parameter values. For a continuous broken symmetry, it is flat along the vacuum manifold.

This is not a contradiction. It reflects two different questions:

1. **Which homogeneous expectation values can be produced by a source?** The exact Legendre effective potential answers this and is convex.
2. **What is the local physics around a chosen pure phase?** The branch effective potential or constrained effective potential answers this and can display the familiar nonconvex shape.

When studying particles and low-energy fields, one expands around a selected pure vacuum. When studying thermodynamic stability and Legendre transforms, convexity is mandatory.

:::note[Source note on effective potentials]
Coleman's treatment of “secret symmetry” emphasizes the practical expansion around a selected vacuum and the absence of asymmetric counterterms when the underlying theory is symmetric. Modern effective-action language adds the convexity warning: the exact Legendre effective potential is not always the same object as the branch potential drawn in introductory symmetry-breaking diagrams.
:::

## Accidental degeneracy is not the same thing

Not every degeneracy is spontaneous symmetry breaking. A theory may have two unrelated vacua with equal energy because of fine tuning rather than symmetry. Then there is no group action relating them and no symmetry-protected selection rule.

Compare:

$$
\text{symmetry-related degeneracy:}
\qquad
|\Omega_2\rangle=U(g)|\Omega_1\rangle,
$$

versus

$$
\text{accidental degeneracy:}
\qquad
E_{\Omega_1}=E_{\Omega_2}\quad\text{with no symmetry reason.}
$$

Accidental degeneracy is fragile. A small generic perturbation lifts it. Symmetry-related degeneracy is stable as long as the symmetry and phase remain intact.

There are also **topological sectors**, where states are distinguished by boundary conditions, winding numbers, fluxes, or line-operator data rather than by an ordinary local order parameter. These can be robust, but the organizing principle is topology or generalized symmetry rather than ordinary Landau degeneracy. Later chapters on topological sectors, defects, higher-form symmetries, and TQFT refine this distinction.

## Boundary conditions and superselection

In infinite volume, different broken vacua behave as superselection sectors for local observables. A local operator supported in a bounded region cannot change the order parameter at spatial infinity. Thus it cannot map $|\Omega_+\rangle$ to $|\Omega_-\rangle$ with nonzero amplitude in the infinite-volume limit.

Boundary conditions make this vivid. If the field is forced to approach $+v$ at spatial infinity, finite-energy configurations live in the $+$ sector. If it is forced to approach $-v$, they live in the $-$ sector. To interpolate between the two sectors, one must insert a domain wall or change the boundary condition.

For continuous symmetry breaking, choosing a point on $G/H$ at infinity selects a vacuum orientation. Slowly varying orientations correspond to Goldstone fields. Singular or topologically nontrivial maps into $G/H$ can produce vortices, skyrmions, monopoles, or other solitonic sectors, depending on the homotopy groups of the vacuum manifold.

The moral is:

$$
\text{vacuum degeneracy} + \text{boundary conditions}
\quad\Longrightarrow\quad
\text{sectors, defects, and low-energy fields}.
$$

## Gauge caveat

Local gauge symmetry is not spontaneously broken in the same sense as a global symmetry. A gauge transformation is a redundancy of description, so two configurations related only by a gauge transformation are not distinct physical vacua.

This is why the statement

$$
\langle\Phi\rangle\ne0
$$

for a gauge-charged Higgs field is not a gauge-invariant order parameter. In a fixed gauge it is a useful computational signal, but the physical phase should be diagnosed by gauge-invariant observables: spectra, screening, confinement behavior, line operators, boundary/global symmetries, and response to background fields.

There can still be genuine degeneracy in gauge theories, but it must be phrased in terms of physical global symmetries, topological sectors, higher-form symmetries, boundary conditions, or gauge-invariant operator algebras. The Higgs-mechanism preview later in this chapter returns to this point.

## Common pitfalls

**Thinking finite-volume uniqueness forbids spontaneous breaking.** It does not. Finite-volume uniqueness is common. Broken phases are defined by the source-selected infinite-volume limit.

**Averaging over vacua and calling the result “the vacuum.”** The average may be symmetric, but it is not a pure thermodynamic phase if it violates cluster decomposition.

**Equating classical minima with quantum vacua.** Classical minima are a guide. Quantum vacua are states of the full theory, corrected by fluctuations, renormalization, anomalies, boundary conditions, and sometimes topology.

**Forgetting accidental degeneracy.** Degeneracy alone does not imply a broken symmetry. Ask which symmetry relates the states.

**Forgetting convexity of the exact effective potential.** The branch potential used for perturbative particle physics and the exact Legendre effective potential answer different questions.

**Treating gauge-related configurations as different vacua.** Gauge-related configurations are the same physical configuration. Only gauge-invariant distinctions count.

## Relations to other pages

[Order Parameters](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/order-parameters/) explains how to detect a broken phase using one-point functions, long-distance correlators, sources, and nonlocal diagnostics.

[Goldstone Theorem](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-theorem/) uses the nonzero broken-generator commutator to prove that continuous internal breaking forces massless spectral weight.

[Selection Rules](/symmetry-anomalies-topology/ordinary-global-symmetries/selection-rules/) explains how unbroken symmetries constrain matrix elements. In a broken phase, selection rules are organized by the unbroken subgroup $H$, not the full group $G$ acting linearly on the chosen vacuum.

[Background Fields versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/) is the place to repair confusion between global symmetry breaking and gauge redundancy.

The later chapters on Topological Sectors, Defects and Extended Operators, Higher-Form Symmetries, and Symmetry in Phases of Matter generalize the idea of vacuum degeneracy beyond local Landau order parameters.

## Research status

The basic infinite-volume picture of ordinary spontaneous symmetry breaking is established and used throughout QFT, statistical mechanics, condensed matter physics, and particle physics.

Several frontiers refine the same idea rather than replacing it. Modern phases can be distinguished by generalized symmetries, long-range entanglement, defect fusion, higher-form order parameters, boundary anomalies, mixed-state order, or categorical symmetry data. In such phases, the phrase “degenerate vacua” may refer to topological ground-state degeneracy, symmetry-breaking degeneracy, boundary-condition sectors, or superselection sectors; the diagnostic must say which one is meant.

For relativistic QFT, another active boundary is the rigorous construction of infinite-volume sectors and the precise relation between algebraic superselection theory, Euclidean path integrals, and physicists' source-selected vacua.

## Exercises

### Exercise 1: Cat states and clustering

Assume two orthogonal infinite-volume states $|+\rangle$ and $|-\rangle$ obey

$$
\langle+|\phi|+\rangle=v,
\qquad
\langle-|\phi|-\rangle=-v,
\qquad
\langle+|\phi|-\rangle=0.
$$

Assume each pure phase clusters. For

$$
|S\rangle=\frac{|+\rangle+|-\rangle}{\sqrt2},
$$

compute $\langle S|\phi|S\rangle$ and the long-distance limit of $\langle S|\phi(x)\phi(0)|S\rangle$. Does $|S\rangle$ cluster?

<details><summary><strong>Solution</strong></summary>

The one-point function is

$$
\langle S|\phi|S\rangle
=\frac12(v-v)=0.
$$

The cross terms vanish by the superselection assumption. At long distance, clustering within each pure phase gives

$$
\lim_{|x|\to\infty}\langle+|\phi(x)\phi(0)|+\rangle=v^2,
$$

and similarly for $|-\rangle$. Therefore

$$
\lim_{|x|\to\infty}\langle S|\phi(x)\phi(0)|S\rangle
=\frac12(v^2+v^2)=v^2.
$$

Since

$$
v^2\ne \langle S|\phi|S\rangle^2=0,
$$

$|S\rangle$ violates cluster decomposition. It is not a pure broken phase.

</details>

### Exercise 2: Stabilizer and vacuum manifold of the O(N) model

Let $\phi^i$ transform as a vector of $O(N)$ and suppose

$$
\langle\phi^i\rangle=v\delta^{iN}.
$$

Find the unbroken subgroup and the vacuum manifold. How many continuous broken directions are there?

<details><summary><strong>Solution</strong></summary>

The unbroken transformations are those that leave the $N$th axis fixed. They rotate only the first $N-1$ components, so

$$
H=O(N-1).
$$

The vacuum manifold is

$$
O(N)/O(N-1)\simeq S^{N-1}.
$$

Its dimension is

$$
\dim O(N)-\dim O(N-1)
=\frac{N(N-1)}{2}-\frac{(N-1)(N-2)}{2}=N-1.
$$

Thus there are $N-1$ continuous broken directions.

</details>

### Exercise 3: Why a finite-volume free energy can hide a phase transition

Suppose the finite-volume partition function $Z_V(h)$ is analytic and positive near $h=0$, and define

$$
f_V(h)=-\frac{1}{\beta V}\log Z_V(h).
$$

Explain why $m_V(h)=-\partial f_V/\partial h$ cannot jump at $h=0$ for finite $V$, and why a jump can nevertheless appear after $V\to\infty$.

<details><summary><strong>Solution</strong></summary>

If $Z_V(h)$ is analytic and nonzero near $h=0$, then $\log Z_V(h)$ is analytic there, so $f_V(h)$ and $m_V(h)$ are analytic. An analytic function cannot have a jump discontinuity.

The infinite-volume limit need not preserve analyticity uniformly. The sequence $f_V(h)$ can converge to a function $f(h)$ with a cusp at $h=0$. Then

$$
m(h)=-\frac{\partial f}{\partial h}
$$

can jump. This nonanalyticity is the thermodynamic signature of distinct phases selected by the sign of $h$.

</details>

### Exercise 4: Domain walls from disconnected vacua

Consider a real scalar in one spatial dimension with finite-energy boundary conditions. Explain why a configuration with

$$
\phi(-\infty)=-v,
\qquad
\phi(+\infty)=+v
$$

cannot be continuously deformed into the trivial $+v$ vacuum while preserving the boundary conditions and finite energy.

<details><summary><strong>Solution</strong></summary>

Finite energy requires the field to approach a vacuum at spatial infinity. The specified boundary conditions fix different disconnected components of the vacuum set at the two ends. Any deformation preserving the boundary conditions must still interpolate from $-v$ to $+v$ somewhere. It cannot become the constant $+v$ configuration, because that would change the left boundary value. The obstruction is the disconnectedness of

$$
\mathcal M_{\text{vac}}=\{-v,+v\}.
$$

The interpolating configuration is a domain wall or kink.

</details>

## References

- Sidney Coleman, **Aspects of Symmetry**, especially “Secret Symmetry: An Introduction to Spontaneous Symmetry Breakdown and Gauge Fields” and “Classical Lumps and Their Quantum Descendants.”
- Mark Srednicki, **Quantum Field Theory**, §§30–32.
- Matthew D. Schwartz, **Quantum Field Theory and the Standard Model**, Ch. 28.
- Steven Weinberg, **The Quantum Theory of Fields**, Vol. II, chapters on effective actions and spontaneously broken symmetries.
- Alexander Altland and Ben Simons, **Condensed Matter Field Theory**, Ch. 5.
- Jean Zinn-Justin, **Quantum Field Theory and Critical Phenomena**, chapters on symmetry breaking and critical phenomena.

## Version history

- 2026-06-17: First polished draft. Added source-selected infinite-volume definition, finite-volume tunneling discussion, cluster-decomposition test, discrete and continuous examples, domain-wall interpretation, effective-potential convexity warning, gauge caveat, and exercises with solutions.
