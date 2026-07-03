---
title: "Charges and Hilbert Space"
description: "Explains how continuous global symmetries produce conserved charges, how those charges act on states and operators, and how Hilbert spaces decompose into symmetry sectors."
sidebar:
  label: "Charges and Hilbert Space"
  order: 7
level: Graduate
status: "Polished draft"
source: "Coleman lectures, Weinberg Vol. I, Srednicki §§22–24, standard current algebra and Hilbert-space representation theory."
topics:
  - conserved charges
  - Hilbert space
  - charge sectors
  - symmetry generators
  - current algebra
  - superselection
canonicalTopics:
  - conserved-charge
  - hilbert-space-symmetry-sector
  - charge-operator
  - symmetry-generator
researchStatus:
  established:
    - "For exact non-anomalous continuous internal symmetries, conserved charges generate the Hilbert-space symmetry action and organize states into representations."
  active:
    - "In gauge theories, theories with boundaries, infinite-volume broken phases, generalized symmetries, and non-invertible symmetries, the correct Hilbert-space decomposition can be subtle."
---

## Summary

A continuous global symmetry acts on the Hilbert space by unitary operators. Near the identity,

$$
U(\alpha)=e^{-i\alpha^aQ_a},
$$

where the Hermitian operators $Q_a$ are the conserved charges.

For an exact internal symmetry with conserved currents $j_a^\mu$,

$$
\partial_\mu j_a^\mu=0,
$$

the charge on a time slice is

$$
Q_a(t)=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x),
$$

assuming boundary fluxes vanish. Conservation gives $dQ_a/dt=0$.

The same $Q_a$ act on states and operators. In the convention used in this volume,

$$
U(\alpha)^\dagger\mathcal O_iU(\alpha)
=\mathcal O_i+i\alpha^a[Q_a,\mathcal O_i]+O(\alpha^2),
$$

so if $\mathcal O_q$ has $U(1)$ charge $q$,

$$
[Q,\mathcal O_q]=q\mathcal O_q.
$$

Acting on a charge-$Q$ state, such an operator shifts the charge:

$$
\mathcal O_q:\mathcal H_Q\to\mathcal H_{Q+q}.
$$

This page explains charges as Hilbert-space generators, charge sectors, representation multiplets, and the common caveats that appear in QFT.

<figure class="doc-figure" style="--figure-width: 46rem;">

![A Hilbert-space charge-sector ladder showing that a charged operator maps between sectors while neutral symmetric observables preserve each charge sector.](/figures/symmetry-anomalies-topology/charge-sector-ladder.svg)

<figcaption>

A charged operator $\mathcal O_q$ maps $\mathcal H_Q$ to $\mathcal H_{Q+q}$. Neutral, symmetry-invariant observables commute with $Q$ and act within each charge sector.

</figcaption>
</figure>


## Prerequisites

You should know [Continuous and Discrete Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/continuous-and-discrete-symmetries/), [Symmetry Groups and Representations](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-groups-and-representations/), [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/), and [Symmetry Defects and Topological Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-defects-and-topological-operators/).

We assume basic quantum mechanics: unitary operators, Hermitian generators, commutators, and simultaneous eigenspaces for commuting observables.

## Core idea

The Hilbert-space picture of symmetry is:

$$
\text{symmetry} \Rightarrow \text{operators }U(g)\text{ commuting with time evolution}.
$$

For a continuous symmetry, differentiating $U(g)$ near the identity gives charges. These charges are observables. They label states, generate transformations, constrain matrix elements, and organize the Hilbert space into sectors.

For an internal symmetry,

$$
[H,Q_a]=0.
$$

So if $|E\rangle$ is an energy eigenstate, then $Q_a|E\rangle$ is another state with the same energy, provided the state lies in the domain of $Q_a$. This is the source of symmetry multiplets and degeneracies.

The complementary spacetime picture is the previous page: $Q_a$ exponentiates to a topological operator on a Cauchy surface. The same object is a charge in canonical language and a symmetry defect in path-integral language.

## Setup and conventions

For a continuous internal symmetry with parameters $\alpha^a$, write

$$
U(\alpha)=e^{-i\alpha^aQ_a},
$$

where $Q_a^\dagger=Q_a$. The operator pullback convention is

$$
\mathcal O\mapsto U(\alpha)^\dagger\mathcal O U(\alpha).
$$

Expanding to first order gives

$$
U(\alpha)^\dagger\mathcal O U(\alpha)
=
\mathcal O+i\alpha^a[Q_a,\mathcal O]+O(\alpha^2).
$$

Thus the infinitesimal variation is

$$
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

For a $U(1)$-charged operator, define $q$ by

$$
U(\alpha)^\dagger\mathcal O_qU(\alpha)=e^{i\alpha q}\mathcal O_q.
$$

Then

$$
[Q,\mathcal O_q]=q\mathcal O_q.
$$

A state with charge $Q_0$ obeys

$$
Q|Q_0,r\rangle=Q_0|Q_0,r\rangle,
$$

where $r$ labels all other quantum numbers. It transforms as

$$
U(\alpha)|Q_0,r\rangle=e^{-i\alpha Q_0}|Q_0,r\rangle.
$$

:::note[Convention-sensitive formula]
Many texts use $U(\alpha)=e^{+i\alpha Q}$ or use $U\mathcal O U^{-1}$ instead of $U^\dagger\mathcal O U$. Either choice flips some signs. The invariant content is the triad: the finite transformation of operators, the phase of charge eigenstates, and the commutator $[Q,\mathcal O_q]$ in the chosen convention.
:::

## From current conservation to conserved charge

Let $j^\mu$ be a conserved current:

$$
\partial_\mu j^\mu=0.
$$

On a constant-time slice, define

$$
Q(t)=\int d^{d-1}\mathbf x\,j^0(t,\mathbf x).
$$

Then

$$
\frac{dQ}{dt}
=\int d^{d-1}\mathbf x\,\partial_0 j^0
=-\int d^{d-1}\mathbf x\,\partial_i j^i.
$$

If space has no boundary, or if the current flux through the boundary vanishes, then

$$
\frac{dQ}{dt}=0.
$$

More generally,

$$
\frac{dQ}{dt}=-\int_{\partial\text{space}}dS_i\,j^i.
$$

So a charge is conserved only after boundary conditions are specified. This is not a technicality: boundaries, defects, reservoirs, and asymptotic regions can explicitly break a symmetry or allow charge to leak.

For a nonabelian continuous symmetry, currents $j_a^\mu$ give charges

$$
Q_a=\int d^{d-1}\mathbf x\,j_a^0.
$$

For a non-anomalous symmetry, the integrated charges obey the Lie algebra

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c.
$$

Local current commutators can contain contact terms, and in two dimensions they may have central extensions. The integrated global charges close on the symmetry algebra when the symmetry is exact and boundary terms are under control.

## Charges generate transformations

A charge is not just a label. It generates transformations.

For a small parameter $\alpha$,

$$
U(\alpha)^\dagger\mathcal O U(\alpha)
=\mathcal O+i\alpha[Q,\mathcal O]+O(\alpha^2).
$$

Therefore if

$$
[Q,\mathcal O_q]=q\mathcal O_q,
$$

then

$$
U(\alpha)^\dagger\mathcal O_q U(\alpha)=e^{i\alpha q}\mathcal O_q.
$$

The same $Q$ acts on states by

$$
U(\alpha)|\psi\rangle=e^{-i\alpha Q}|\psi\rangle.
$$

If $|\psi\rangle$ has charge $Q_\psi$, then

$$
U(\alpha)|\psi\rangle=e^{-i\alpha Q_\psi}|\psi\rangle.
$$

Now act with $\mathcal O_q$:

$$
Q\mathcal O_q|\psi\rangle
=\mathcal O_qQ|\psi\rangle+[Q,\mathcal O_q]|\psi\rangle
=(Q_\psi+q)\mathcal O_q|\psi\rangle.
$$

So $\mathcal O_q$ shifts the charge of a state by $q$.

This is the Hilbert-space version of the wall-crossing rule. A local operator linked by a symmetry wall transforms by its charge; a charged operator inserted on a state changes that state’s charge sector.

## Hilbert-space sectors for abelian symmetries

For a compact $U(1)$ symmetry, the Hilbert space decomposes into charge sectors:

$$
\mathcal H=\bigoplus_{q\in\Lambda}\mathcal H_q.
$$

Here $\Lambda$ is the charge lattice allowed by the theory. In a simple normalization it may be $\mathbb Z$, but quotients and global-form choices can change which charges occur.

A neutral operator preserves each sector:

$$
[Q,\mathcal A_0]=0
\quad\Longrightarrow\quad
\mathcal A_0:\mathcal H_q\to\mathcal H_q.
$$

A charged operator maps between sectors:

$$
\mathcal O_r:\mathcal H_q\to\mathcal H_{q+r}.
$$

For a finite abelian symmetry such as $\mathbb Z_N$, there is no Hermitian Noether charge obtained from a current, but there are still sectors labeled by characters. If an operator has charge $r\in\mathbb Z_N$, then it maps

$$
\mathcal H_q\to\mathcal H_{q+r\,\mathrm{mod}\,N}.
$$

So “charge sectors” are not limited to continuous symmetries. What is special about continuous symmetries is the existence of infinitesimal generators and currents.

## Hilbert-space sectors for nonabelian symmetries

For a compact nonabelian symmetry group $G$, one should not expect to diagonalize every generator at once. Instead, the Hilbert space decomposes into irreducible representations:

$$
\mathcal H\simeq\bigoplus_{R\in\widehat G}\mathcal K_R\otimes V_R.
$$

Here $V_R$ is an irreducible representation of $G$, and $\mathcal K_R$ is a multiplicity space carrying the remaining quantum numbers: momentum, energy level, particle content, radial-quantization level, degeneracy, or other labels.

This formula is schematic in infinite-volume QFT, where continuous spectra may require direct integrals. The representation idea is still correct: the symmetry organizes states into multiplets.

For $SU(2)$, states in a multiplet are labeled by

$$
|j,m;r\rangle,
$$

where $j$ labels the irreducible representation, $m=-j,-j+1,\dots,j$ labels states inside the multiplet, and $r$ denotes everything else. The generators obey

$$
[Q_i,Q_j]=i\epsilon_{ij}{}^kQ_k.
$$

An operator in representation $R$ maps a state in representation $S$ into representations appearing in the tensor product

$$
R\otimes S.
$$

This is the nonabelian replacement for “charge addition.”

## Vacuum, singlets, and selection rules

If the vacuum is invariant under $G$, then

$$
U(g)|\Omega\rangle=|\Omega\rangle.
$$

For a continuous symmetry this implies

$$
Q_a|\Omega\rangle=0,
$$

assuming the charge operator is well-defined on the vacuum.

A vacuum-invariant correlator must be a singlet. For $U(1)$,

$$
\langle\Omega|\mathcal O_{q_1}\cdots\mathcal O_{q_n}|\Omega\rangle\ne0
\quad\Longrightarrow\quad
\sum_i q_i=0.
$$

For nonabelian $G$, the tensor product of the operator representations must contain the trivial representation.

This is not a separate postulate. It follows because the same unitary symmetry acts on the bra, the ket, and the operators, and the vacuum contributes no nontrivial representation index.

## Symmetric observables and superselection

One must distinguish charge sectors from superselection sectors.

If we restrict attention to **symmetric observables** $\mathcal A_0$ satisfying

$$
[Q,\mathcal A_0]=0,
$$

then matrix elements between different charge sectors vanish:

$$
\langle q'|\mathcal A_0|q\rangle=0
\qquad(q'\ne q).
$$

In this restricted algebra, charge sectors cannot be mixed.

But if the theory contains genuine charged local operators, those operators can connect charge sectors:

$$
\langle q+r|\mathcal O_r|q\rangle
$$

may be nonzero.

Thus ordinary global-charge sectors are representation sectors, not automatically absolute superselection sectors of the full operator algebra. Superselection becomes stronger when only neutral observables are allowed, or in gauge theories where Gauss-law constraints prevent gauge-charged local operators from being physical.

:::caution[Gauge charge is different]
A gauge transformation is redundancy, not an ordinary global symmetry. Gauge-charged fields can be useful variables, but physical local operators must be gauge-invariant. Electric charge in a gauge theory is tied to flux at infinity and Gauss’s law, so its Hilbert-space sectors are more subtle than the ordinary global $U(1)$ sectors discussed here.
:::

## Finite volume, infinite volume, and domains

In a finite spatial volume with good boundary conditions, charges are often honest operators on the Hilbert space. In infinite volume, several new issues appear.

First, the total integral

$$
Q=\int d^{d-1}\mathbf x\,j^0
$$

may fail to converge on states with nonzero charge density. One may need finite-volume regulators, local charge operators, or smeared charges.

Second, a charge operator can be unbounded. Like the Hamiltonian, it is not defined on every vector in the Hilbert space. Statements such as $[Q,\mathcal O]=q\mathcal O$ are first established on a suitable dense domain or inside regulated correlation functions.

Third, long-range fields and massless particles can affect the definition of charged states. In gauge theories, charged states may require dressing by asymptotic fields. In theories with Goldstone modes, broken charges may fail to exist as ordinary operators acting on the chosen infinite-volume vacuum.

These subtleties are not reasons to abandon charges. They are reasons to treat global integrals with care and to use local Ward identities and topological-operator language when they are sharper.

## Spontaneous symmetry breaking

In spontaneous symmetry breaking, the theory has the symmetry but the chosen vacuum does not.

If $G$ is broken to a subgroup $H$, then for $g\notin H$,

$$
U(g)|\Omega\rangle
$$

is a different vacuum in the infinite-volume limit. The operator algebra still carries an action of $G$, but the vacuum is not a singlet under the full group.

For a broken continuous symmetry, the formal charge

$$
Q_a=\int d^{d-1}\mathbf x\,j_a^0
$$

may fail to be a well-defined operator on the broken vacuum. This failure is connected to the existence of long-wavelength Goldstone modes. The local current and Ward identities still make sense, but the global charge acting on the vacuum can be infrared divergent.

A common slogan is:

$$
\text{unbroken charge annihilates the vacuum; broken charge moves the vacuum}.
$$

The second clause is formal in infinite volume. A more precise statement is that local order parameters transform nontrivially and their expectation values distinguish the degenerate vacua.

## Explicit breaking and anomalies

If the symmetry is explicitly broken, then the current is not conserved:

$$
\partial_\mu j^\mu\ne0.
$$

Then

$$
\frac{dQ}{dt}\ne0,
$$

and the would-be charge does not commute with the Hamiltonian.

If the symmetry is anomalous, the classical current may be conserved but the quantum theory fails to preserve the symmetry. In operator language, the charge may fail to generate a consistent symmetry of the quantum Hilbert space. In path-integral language, the measure or regulator is not invariant. In background-field language, the obstruction appears when trying to couple the symmetry to nondynamical gauge fields.

For an ordinary global symmetry, an anomaly does not necessarily mean the symmetry is absent as a global symmetry. It may mean that it cannot be gauged, or that its Ward identities contain anomalous terms. The anomaly chapters make these distinctions precise.

## Boundaries and asymptotic symmetries

Charges are sensitive to boundaries. If space has a boundary,

$$
\frac{dQ}{dt}=-\int_{\partial\text{space}}dS_i\,j^i.
$$

There are three common possibilities.

First, the boundary condition kills the flux and preserves the charge.

Second, the boundary condition breaks the symmetry, so the charge is not conserved.

Third, boundary degrees of freedom carry compensating charge. Then the conserved charge is a sum of bulk and boundary terms:

$$
Q_\mathrm{total}=Q_\mathrm{bulk}+Q_\mathrm{boundary}.
$$

In gauge theories and gravity, surface charges at infinity are often the most important charges. Those belong to later chapters on gauge redundancy, asymptotic symmetries, and gravity, but the moral begins here: a charge is not defined by a density alone. It is defined by a density, a region, and boundary conditions.

## Common pitfalls

**Forgetting boundary flux.** Current conservation implies charge conservation only after boundary terms vanish or are included.

**Calling every sector a superselection sector.** Symmetric observables preserve charge sectors, but charged local operators can connect ordinary global-charge sectors if they are genuine operators in the theory.

**Confusing gauge charge with global charge.** Gauge redundancy does not act as a physical global symmetry on the Hilbert space. Gauge-invariant charges are often boundary or flux data.

**Assuming nonabelian charges are simultaneously diagonal.** Nonabelian symmetry organizes states into multiplets, not common eigenstates of all generators.

**Ignoring domains of unbounded operators.** Total charges in infinite-volume QFT require regulators, domains, or local formulations.

**Treating spontaneous breaking as explicit breaking.** In spontaneous breaking, the operator algebra still has the symmetry. The vacuum or phase does not.

## Relations to other pages

[Symmetry Defects and Topological Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-defects-and-topological-operators/) gives the spacetime version of the same object: the charge exponentiated on a Cauchy surface is a topological symmetry wall.

[Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/) explains the commutator action $[Q,\mathcal O]$. [Selection Rules](/symmetry-anomalies-topology/ordinary-global-symmetries/selection-rules/) turns charge conservation into vanishing rules for matrix elements and correlators. [Symmetry Algebras](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-algebras/) develops the Lie-algebra structure of the charges.

The [Noether Currents and Ward Identities](/symmetry-anomalies-topology/noether-currents-ward-identities/) chapter derives the currents, charge conservation, and contact terms. [Spontaneous Symmetry Breaking](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/) explains what changes when the vacuum is not invariant. [Gauge Redundancy and BRST](/symmetry-anomalies-topology/gauge-redundancy-brst/) explains why gauge generators are constraints rather than ordinary global charges.

## Research status

The Hilbert-space charge picture for ordinary continuous global symmetries is established textbook QFT.

The subtleties remain important in research. Infinite-volume limits, massless particles, boundaries, gauge constraints, anomalous symmetries, higher-form charges, edge modes, and non-invertible defects all force refinements of the simple formula $Q=\int j^0$. Modern work often replaces “a charge acting on the whole Hilbert space” by a more local or topological statement: a symmetry operator supported on a surface acts on the objects it links.

## Exercises

### Exercise 1: Charge shifting

Let $Q|Q_0\rangle=Q_0|Q_0\rangle$ and let $[Q,\mathcal O_q]=q\mathcal O_q$. Show that $\mathcal O_q|Q_0\rangle$ has charge $Q_0+q$, assuming it is nonzero.

<details><summary><strong>Solution</strong></summary>

Compute

$$
Q\mathcal O_q|Q_0\rangle
=\mathcal O_qQ|Q_0\rangle+[Q,\mathcal O_q]|Q_0\rangle.
$$

Using the assumptions,

$$
Q\mathcal O_q|Q_0\rangle
=Q_0\mathcal O_q|Q_0\rangle+q\mathcal O_q|Q_0\rangle
=(Q_0+q)\mathcal O_q|Q_0\rangle.
$$

So $\mathcal O_q|Q_0\rangle$ lies in the charge-$Q_0+q$ sector.

</details>

### Exercise 2: Boundary flux

Let $Q(t)=\int_V d^{d-1}\mathbf x\,j^0$ over a spatial region $V$. If $\partial_\mu j^\mu=0$, derive the formula for $dQ/dt$ in terms of the flux through $\partial V$.

<details><summary><strong>Solution</strong></summary>

Start with

$$
\frac{dQ}{dt}=\int_V d^{d-1}\mathbf x\,\partial_0j^0.
$$

Current conservation gives

$$
\partial_0j^0=-\partial_i j^i.
$$

Therefore

$$
\frac{dQ}{dt}=-\int_V d^{d-1}\mathbf x\,\partial_i j^i.
$$

By the divergence theorem,

$$
\frac{dQ}{dt}=-\int_{\partial V}dS_i\,j^i.
$$

The charge in $V$ is conserved only if the net flux through the boundary vanishes.

</details>

### Exercise 3: Neutral operators preserve charge sectors

Suppose $[Q,\mathcal A_0]=0$. Show that $\langle q'|\mathcal A_0|q\rangle=0$ if $q'\ne q$.

<details><summary><strong>Solution</strong></summary>

Use $Q|q\rangle=q|q\rangle$ and $\langle q'|Q=q'\langle q'|$. Since $[Q,\mathcal A_0]=0$,

$$
0=\langle q'|[Q,\mathcal A_0]|q\rangle.
$$

Expanding the commutator gives

$$
0=(q'-q)\langle q'|\mathcal A_0|q\rangle.
$$

If $q'\ne q$, then

$$
\langle q'|\mathcal A_0|q\rangle=0.
$$

</details>

### Exercise 4: Nonabelian tensor-product rule

Let $\mathcal O_i$ transform as an $SU(2)$ doublet and let $|j,m\rangle$ be a state in spin-$j$ representation. Which representations can appear in $\mathcal O_i|j,m\rangle$?

<details><summary><strong>Solution</strong></summary>

An $SU(2)$ doublet has spin $1/2$. Acting with it on a spin-$j$ state gives representations in

$$
\frac12\otimes j=(j+\tfrac12)\oplus(j-\tfrac12),
$$

where the $j-1/2$ term is absent if $j=0$. Therefore $\mathcal O_i|j,m\rangle$ can lie in spin $j+1/2$ and, for $j>0$, spin $j-1/2$ multiplets.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on spacetime symmetries and internal symmetries.
- Sidney Coleman, *Aspects of Symmetry*, especially lectures on unitary symmetry, currents, soft pions, and spontaneous symmetry breakdown.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapters on symmetries, Wigner’s theorem, projective representations, and quantum fields.
- Mark Srednicki, *Quantum Field Theory*, sections 22–24 on continuous, discrete, and nonabelian symmetries.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on Noether’s theorem, Ward–Takahashi identities, and gauge invariance.
- A. Zee, *Quantum Field Theory in a Nutshell*, chapters on symmetry, symmetry breaking, and group-theoretic organization.

## Version history

- **2026-06-17:** First polished draft for the Ordinary Global Symmetries chapter.
