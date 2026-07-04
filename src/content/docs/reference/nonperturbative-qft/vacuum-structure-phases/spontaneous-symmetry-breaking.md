---
title: "Spontaneous Symmetry Breaking"
description: "Explains spontaneous symmetry breaking as a property of vacuum states, source limits, order parameters, Goldstone directions, and unbroken subgroups."
sidebar:
  label: "Spontaneous Symmetry Breaking"
  order: 4
level: Graduate
status: "Polished draft"
source: "Coleman; Srednicki; Schwartz; Weinberg; Zinn-Justin; Shifman; Fradkin; Altland–Simons."
topics:
  - spontaneous symmetry breaking
  - vacuum structure
  - order parameters
  - Goldstone modes
  - source selection
  - cluster decomposition
  - gauge redundancy
canonicalTopics:
  - nonperturbative-qft
  - vacuum-structure
  - spontaneous-symmetry-breaking
  - order-parameters
  - goldstone-modes
researchStatus:
  established:
    - "Spontaneous symmetry breaking is a state-level phenomenon: the dynamics has a symmetry, but a pure infinite-volume vacuum need not be invariant under it."
  active:
    - "In strongly coupled gauge theories, topological phases, and theories with generalized symmetries, identifying the most useful symmetry-breaking diagnostics can require nonlocal operators and boundary-sensitive data."
---

## Summary

**Spontaneous symmetry breaking** occurs when the equations, Hamiltonian, or path integral have a symmetry, but a chosen pure vacuum state does not. If $G$ is a global symmetry of the theory and $|\tilde\Omega\rangle$ is a pure vacuum, the unbroken subgroup is

$$
H_{\tilde\Omega}=
\{g\in G\mid U(g)|\tilde\Omega\rangle=e^{i\alpha(g)}|\tilde\Omega\rangle\}.
$$

When $H_{\tilde\Omega}\subsetneq G$, the symmetry is spontaneously broken in that vacuum. The symmetry is not absent; it acts by moving one pure vacuum to another:

$$
|\tilde\Omega_g\rangle=U(g)|\tilde\Omega\rangle,
\qquad
\tilde\Omega_g\sim \tilde\Omega_{gh}\quad(h\in H_{\tilde\Omega}).
$$

Thus the symmetry-related vacua are locally modeled by the coset

$$
\mathcal M_{\rm sym}\simeq G/H,
$$

subject to the usual quantum caveats about infrared fluctuations, anomalies, gauge redundancy, and additional accidental degeneracies.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A finite-volume symmetric state becomes a source-selected infinite-volume broken phase with tangent Goldstone directions.](/figures/nonperturbative-qft/spontaneous-symmetry-breaking-manifold.svg)

<figcaption>

A small source or boundary condition selects a direction before the infinite-volume limit. After the source is removed, the chosen pure phase preserves only $H$; tangent directions along $G/H$ are Goldstone directions under the standard Lorentz-invariant assumptions.

</figcaption>
</figure>

The word “spontaneous” means that no explicit symmetry-breaking term has been added to the Hamiltonian. In practice one often introduces a tiny source to select a vacuum, takes the infinite-volume limit, and then removes the source. That limiting procedure is not a trick; it is part of the nonperturbative definition of the broken phase.

## Prerequisites

You should know [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/), [Degenerate Vacua](/nonperturbative-qft/vacuum-structure-phases/degenerate-vacua/), and [Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/). The pages [Finite-Volume Definition](/nonperturbative-qft/nonperturbative-definitions/finite-volume-definition/) and [Reflection Positivity](/nonperturbative-qft/nonperturbative-definitions/reflection-positivity/) explain why the order of limits and Euclidean state reconstruction matter.

This page uses ordinary global symmetries first. Gauge redundancy, higher-form symmetries, and topological phases require extra care and are only signposted here.

## Core idea

A symmetry can be realized in two different ways on a vacuum.

| Realization | State-level statement | Typical diagnostic |
|---|---|---|
| Unbroken | The vacuum is invariant under the symmetry. | Charged local order parameters have zero VEV. |
| Broken | The symmetry maps the vacuum to a different pure vacuum. | Some operator, boundary condition, or long-distance correlator distinguishes the vacua. |

For an internal global symmetry $G$, let $\omega$ denote the vacuum state as a linear functional on observables:

$$
\omega(A)=\langle\Omega|A|\Omega\rangle.
$$

The symmetry acts on observables by

$$
g\cdot A=U(g)^{-1}AU(g).
$$

The vacuum preserves $g$ if

$$
\omega(g\cdot A)=\omega(A)
\qquad\text{for all physical observables }A.
$$

This formulation is often cleaner than staring at a classical potential. It works for local operators, extended operators, lattice Hamiltonians, continuum path integrals, and algebraic descriptions. It also makes the central warning obvious: breaking is a property of the **state**, not merely of the Lagrangian.

## Setup and conventions

We use the conventions of [Conventions for Nonperturbative QFT](/nonperturbative-qft/conventions/). Unless otherwise stated, $G$ is an exact global internal symmetry represented by unitary operators $U(g)$ on the Hilbert space, or equivalently by an action on the Euclidean path integral.

A source $h^i$ coupled to a renormalized operator multiplet $\mathcal O_i$ is written schematically as

$$
H_L(h)=H_L-\int_{\Sigma_L}d^{d-1}x\,h^i\mathcal O_i(x),
$$

or in Euclidean language as

$$
Z[h]=\int \mathcal D\Phi\,
\exp\left[-S_E[\Phi]+\int d^dx\,h^i\mathcal O_i(x)\right].
$$

The source-selected expectation value is

$$
v_i(h)=\frac{1}{\beta V_L}\frac{\partial}{\partial h^i}\log Z_{\beta,L}(h).
$$

A broken vacuum is obtained by an ordered limit such as

$$
v_i^{(+)}
=\lim_{h\to0^+}\lim_{L\to\infty}\lim_{\beta\to\infty}v_i(h),
$$

where the direction $h\to0^+$ means that the source approaches zero inside a chosen chamber of source space. Reversing the limits can return a symmetric finite-volume state instead of a pure broken vacuum.

## Definition

Let $G$ be a global symmetry of a QFT. A pure vacuum state $\omega$ **spontaneously breaks** $G$ to $H$ if

$$
H=\{g\in G\mid \omega(g\cdot A)=\omega(A)\text{ for all observables }A\}
$$

is a proper subgroup of $G$. The broken symmetry orbit is the set of states

$$
\omega_g(A)=\omega(g^{-1}\cdot A),
\qquad g\in G.
$$

If $h\in H$, then $\omega_h=\omega$, so the symmetry-related orbit is naturally parameterized by $G/H$ when the group action is faithful on the vacuum orbit.

This definition separates three ideas that are often blurred together.

| Idea | Correct statement |
|---|---|
| Symmetry of the dynamics | $H$ or $S_E$ is invariant under $G$. |
| Symmetry of a vacuum | A specific state $\omega$ is invariant only under $H\subseteq G$. |
| Family of related vacua | Acting with $G$ on one vacuum produces other vacua in the same symmetry orbit. |

In a theory with a useful local order parameter $\mathcal O_i$, spontaneous symmetry breaking can be detected by

$$
v_i=\omega(\mathcal O_i)\ne0
$$

with $v_i$ not invariant under all of $G$. But the order parameter is a diagnostic, not the definition. Some phases require extended operators or boundary data; some charged local VEVs vanish for reasons unrelated to unbroken symmetry; and gauge-variant VEVs are not physical observables.

## The source-limit definition

The most robust operational definition uses a small explicit breaking source, then removes it after the thermodynamic limit.

For a discrete $\mathbb Z_2$ example, couple a scalar order parameter to $h\phi$:

$$
H_L(h)=H_L-h\int_{\Sigma_L}d^{d-1}x\,\phi(x).
$$

At finite volume and $h=0$, the exact ground state can be symmetric, so

$$
\langle\phi\rangle_{L,h=0}=0.
$$

For $h>0$, the source selects the positive phase. The broken VEV is

$$
\langle\phi\rangle_+
=\lim_{h\downarrow0}\lim_{L\to\infty}\langle\phi\rangle_{L,h}.
$$

For $h<0$, the other pure vacuum is selected:

$$
\langle\phi\rangle_-
=\lim_{h\uparrow0}\lim_{L\to\infty}\langle\phi\rangle_{L,h}.
$$

A compact diagnostic of symmetry breaking is therefore the discontinuity of the infinite-volume order parameter as the source crosses zero:

$$
\lim_{h\downarrow0}\lim_{L\to\infty}\langle\phi\rangle_{L,h}
\ne
\lim_{h\uparrow0}\lim_{L\to\infty}\langle\phi\rangle_{L,h}.
$$

This is why finite-volume analyticity and spontaneous symmetry breaking are compatible. At finite $L$, the free energy is usually analytic in $h$. The nonanalyticity appears only after the infinite-volume limit.

## Order parameters and stabilizers

Suppose a multiplet of operators $\mathcal O_i$ transforms in a representation $R$ of $G$:

$$
U(g)^{-1}\mathcal O_i U(g)=R_i{}^j(g)\mathcal O_j.
$$

In a vacuum with one-point function

$$
v_i=\langle\mathcal O_i\rangle,
$$

the unbroken subgroup detected by this order parameter is the stabilizer

$$
H_v=\{g\in G\mid R_i{}^j(g)v_j=v_i\}.
$$

For an $O(N)$ vector order parameter,

$$
\langle\phi^a\rangle=vn^a,
\qquad n^an^a=1,
$$

the stabilizer of a nonzero vector $n^a$ is $O(N-1)$, so the symmetry-breaking pattern is

$$
O(N)\longrightarrow O(N-1),
\qquad
\mathcal M_{\rm sym}\simeq O(N)/O(N-1)\simeq S^{N-1}.
$$

This is a good first description of the symmetry orbit. The full vacuum structure may be richer: there may be additional disconnected components, topological sectors, accidental degeneracies, theta labels, or flat directions not generated by $G$.

## Continuous symmetries and Goldstone directions

When a continuous internal global symmetry is spontaneously broken, the orbit $G/H$ has tangent directions. Infinitesimally, if $T_a$ is a broken generator, then

$$
\delta_a v_i=i(T_a)_i{}^jv_j\ne0.
$$

These directions are not ordinary massive fluctuations around the vacuum. They cost no potential energy at zero momentum because moving along the symmetry orbit gives another vacuum with the same energy density.

Under the standard assumptions of relativistic QFT in sufficiently high dimension—locality, unitarity, a conserved current, a Poincaré-invariant vacuum, and suitable infrared behavior—each broken continuous internal generator gives a massless Goldstone mode. The diagnostic commutator is

$$
\langle\Omega|[Q_a,\mathcal O_i(0)]|\Omega\rangle
=(T_a)_i{}^jv_j,
$$

where $Q_a$ is the symmetry charge, understood carefully as a large-volume smeared charge in a broken phase. A nonzero right-hand side requires spectral weight at arbitrarily low energy.

For a simple $O(N)$ scalar model, one writes fluctuations around a chosen vacuum as

$$
\phi^a(x)=\big(v_R+\rho(x)\big)n^a+\pi^a(x),
\qquad n_a\pi^a=0.
$$

The field $\rho$ is a radial fluctuation. The $N-1$ transverse fields $\pi^a$ are the Goldstone directions in the simplest weakly coupled description.

This counting is not a theorem without hypotheses. In nonrelativistic systems the counting of Goldstone modes is modified; in $1+1$-dimensional relativistic QFT, continuous internal symmetries cannot be spontaneously broken under the usual assumptions; in gauge theories, would-be Goldstone modes can be absent from the physical spectrum through the Higgs mechanism.

## Discrete symmetries and walls

Discrete symmetries have no infinitesimal generators, so they produce no Goldstone bosons. They can still be spontaneously broken.

The canonical example is a $\mathbb Z_2$-invariant scalar theory with two pure vacua

$$
\langle\phi\rangle_+=+v_R,
\qquad
\langle\phi\rangle_-=-v_R.
$$

The symmetry maps one vacuum to the other. The unbroken subgroup of either pure vacuum is trivial, while the mixed symmetric state preserves the symmetry but is not a pure phase.

Discrete broken vacua are often separated by domain walls. A wall configuration satisfies boundary conditions such as

$$
\phi(x_\perp\to-\infty)=\phi_-,
\qquad
\phi(x_\perp\to+\infty)=\phi_+,
$$

and has a finite tension per unit area. The wall is a physical object because the two sides approach different superselection sectors at spatial infinity. This is the cleanest setting in which “several vacua” becomes something you can literally draw.

The next page, [Discrete Vacua](/nonperturbative-qft/vacuum-structure-phases/discrete-vacua/), studies this case more carefully.

## Cluster decomposition and pure phases

A pure gapped vacuum should satisfy cluster decomposition for local operators:

$$
\lim_{|x-y|\to\infty}
\left(
\langle A(x)B(y)\rangle_\Omega
-
\langle A(x)\rangle_\Omega\langle B(y)\rangle_\Omega
\right)=0.
$$

This condition distinguishes a pure broken vacuum from a symmetric mixture. In a $\mathbb Z_2$-broken theory, the mixed state

$$
\omega_{\rm mix}=\frac12\omega_++\frac12\omega_-
$$

has

$$
\omega_{\rm mix}(\phi)=0,
$$

but

$$
\lim_{|x-y|\to\infty}\omega_{\rm mix}(\phi(x)\phi(y))=v_R^2.
$$

Thus the connected correlator does not decay to zero. The mixture is symmetric, but it is not a pure vacuum phase.

This point is not philosophical hair-splitting. In a broken phase, using the mixed state can make a valid order parameter look zero while long-distance correlations still reveal the broken structure.

## Gauge redundancy is different

A local gauge redundancy is not a physical global symmetry acting faithfully on the Hilbert space of gauge-invariant states. Therefore a gauge-variant VEV is not, by itself, a physical order parameter.

For example, writing

$$
\langle\phi\rangle\ne0
$$

in a gauge-fixed Higgs model may be a convenient perturbative description, but it is not a gauge-invariant statement of spontaneous breaking of a physical local symmetry. Physical statements should be phrased in terms of gauge-invariant operators, spectra, line operators, response to external probes, or the realization of genuine global symmetries.

This does not mean the Higgs mechanism is fake. It means the slogan “the gauge symmetry is spontaneously broken” is a dangerous shorthand. The gauge-fixed language is often useful, but the nonperturbative phase diagnosis must be gauge-invariant.

## Common pitfalls

**Treating a classical minimum as the definition of a vacuum.** A classical minimum is a saddle for semiclassical expansion. The quantum vacuum is a state or Euclidean state-selection limit, and quantum effects can shift, split, connect, or remove classical minima.

**Forgetting the order of limits.** At finite volume, exact symmetry often forces charged VEVs to vanish. Broken pure vacua are obtained by selecting a phase and then taking the infinite-volume limit before removing the source.

**Confusing a mixed symmetric state with an unbroken pure phase.** A symmetric average over broken vacua can have zero order parameter. It typically fails cluster decomposition and should not be mistaken for a single pure vacuum.

**Breaking a gauge redundancy.** Gauge-dependent VEVs are useful in calculations but not physical order parameters. Ask instead for gauge-invariant spectra, line operators, global symmetries, and long-distance response.

**Overcounting Goldstone modes.** The simple rule “one Goldstone per broken generator” assumes a relativistic system with the usual hypotheses. Nonrelativistic systems, gauge theories, low-dimensional systems, and systems with constraints require separate analysis.

## Relations to other pages

- [Vacuum Expectation Values](/nonperturbative-qft/vacuum-structure-phases/vacuum-expectation-values/) explains how sources select one-point functions.
- [Degenerate Vacua](/nonperturbative-qft/vacuum-structure-phases/degenerate-vacua/) explains why broken vacua become distinct in the infinite-volume limit.
- [Superselection Sectors](/nonperturbative-qft/vacuum-structure-phases/superselection-sectors/) explains why local finite-energy operations cannot connect different pure broken vacua.
- [Discrete Vacua](/nonperturbative-qft/vacuum-structure-phases/discrete-vacua/) specializes the general mechanism to a finite set of vacua and domain walls.
- [Nonperturbative Observables](/nonperturbative-qft/what-is-nonperturbative-qft/nonperturbative-observables/) explains why some phases require observables beyond local VEVs.

## Research status

The state-level definition of spontaneous symmetry breaking, source selection, cluster decomposition, and Goldstone’s theorem under standard assumptions are textbook-standard. The careful distinction between global symmetry and gauge redundancy is also settled, although gauge-fixed language remains common and useful in calculations.

What remains subtle is not the basic definition but its application in complicated theories. Strongly coupled gauge theories, higher-form symmetries, mixed anomalies, topological phases, finite-density systems, and theories without weakly coupled quasiparticles often require diagnostics beyond a local order parameter.

## Exercises

### Exercise 1: Stabilizer of an order parameter

Let $\phi^a$ transform in the vector representation of $O(N)$, and suppose a vacuum has

$$
\langle\phi^a\rangle=vn^a,
\qquad n^an^a=1,
\qquad v\ne0.
$$

Show that the subgroup preserving this VEV is isomorphic to $O(N-1)$.

<details>
<summary><strong>Solution</strong></summary>

An element $R\in O(N)$ preserves the VEV if

$$
R^a{}_b n^b=n^a.
$$

Choose an orthonormal basis with $n=(1,0,\ldots,0)$. Then $R$ must leave the first basis vector fixed. Orthogonality implies that the remaining $(N-1)$-dimensional subspace is rotated by an arbitrary element of $O(N-1)$. Therefore the stabilizer is $O(N-1)$.

</details>

### Exercise 2: Source discontinuity

In a $\mathbb Z_2$-broken phase, suppose the infinite-volume order parameter satisfies

$$
\lim_{h\downarrow0}\langle\phi\rangle_h=+v_R,
\qquad
\lim_{h\uparrow0}\langle\phi\rangle_h=-v_R.
$$

Explain why this is compatible with analyticity of the finite-volume partition function at $h=0$.

<details>
<summary><strong>Solution</strong></summary>

At finite volume, tunneling mixes the two wells and the exact ground state is often symmetric at $h=0$. The finite-volume free energy is analytic in $h$, so the expectation value varies smoothly through zero. The discontinuity appears only after taking $L\to\infty$, where the tunneling splitting vanishes and the two phases become distinct. Thus finite-volume analyticity and infinite-volume nonanalyticity are compatible because the limits do not commute.

</details>

### Exercise 3: Mixed state and cluster decomposition

Let $\omega_\pm$ be pure broken vacua with

$$
\omega_\pm(\phi)=\pm v_R,
\qquad
\lim_{|x-y|\to\infty}\omega_\pm(\phi(x)\phi(y))=v_R^2.
$$

For the mixed state $\omega_{\rm mix}=\frac12\omega_++\frac12\omega_-$, compute the long-distance connected two-point function of $\phi$.

<details>
<summary><strong>Solution</strong></summary>

First,

$$
\omega_{\rm mix}(\phi)=\frac12v_R+\frac12(-v_R)=0.
$$

The long-distance two-point function is

$$
\lim_{|x-y|\to\infty}\omega_{\rm mix}(\phi(x)\phi(y))
=\frac12v_R^2+\frac12v_R^2=v_R^2.
$$

Therefore the connected correlator tends to

$$
v_R^2-0=v_R^2,
$$

so cluster decomposition fails.

</details>

### Exercise 4: No Goldstone boson for a discrete symmetry

Why does spontaneous breaking of a $\mathbb Z_2$ symmetry not imply a massless Goldstone boson?

<details>
<summary><strong>Solution</strong></summary>

Goldstone’s theorem uses a continuous symmetry current and an infinitesimal broken generator. A discrete symmetry has no conserved Noether current and no infinitesimal generator tangent to a vacuum manifold. A broken $\mathbb Z_2$ symmetry gives distinct vacua and domain walls, but not a continuous zero-energy direction and therefore not a Goldstone boson.

</details>

## References

### Standard first pass

- S. Coleman, *Aspects of Symmetry*, especially “Secret symmetry: an introduction to spontaneous symmetry breakdown and gauge fields.”
- M. Srednicki, *Quantum Field Theory*, chapters on the quantum action, spontaneous symmetry breaking, and spontaneous breaking of continuous symmetries.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter 28 on spontaneous symmetry breaking.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for order parameters, sources, effective actions, and critical phenomena.

### Deeper references

- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, for symmetry realization, current algebra, and Goldstone modes.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapter 1 for phases of gauge theories and spontaneous symmetry breaking.
- E. Fradkin, *Field Theories of Condensed Matter Physics*, for condensed-matter phases, discrete and continuous order parameters, and dual descriptions.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, for broken symmetry, collective modes, and low-dimensional examples.

## Version history

- **2026-06-26:** Initial polished draft.
