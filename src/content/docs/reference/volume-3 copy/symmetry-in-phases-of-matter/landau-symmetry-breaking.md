---
title: "Landau Symmetry Breaking"
description: "Explains the Landau order-parameter paradigm for phases, including residual symmetry, vacuum manifolds, domain walls, Goldstone modes, defects, and its limitations."
sidebar:
  label: "Landau Symmetry Breaking"
  order: 1
level: Graduate
status: "Polished draft"
source: "Landau–Lifshitz; Coleman, Aspects of Symmetry; Altland–Simons Ch. 5; Wilson–Kogut; standard QFT and critical phenomena references."
topics:
  - Landau theory
  - order parameter
  - spontaneous symmetry breaking
  - vacuum manifold
  - Goldstone modes
  - domain walls
canonicalTopics:
  - landau-symmetry-breaking
  - order-parameter
  - residual-symmetry
  - vacuum-manifold
  - goldstone-mode
researchStatus:
  established:
    - "Landau symmetry breaking is the standard local-order-parameter paradigm for many phases and phase transitions."
  active:
    - "Modern phases of matter require additional diagnostics beyond Landau order, including topology, anomalies, long-range entanglement, generalized symmetries, and subsystem symmetry."
---

## Summary

Landau symmetry breaking is the idea that many phases are distinguished by the expectation value of an **order parameter**. The microscopic theory has a symmetry group $G$, but the chosen state preserves only a subgroup $H\subset G$. The order parameter transforms under $G$, and its nonzero value tells us which part of the symmetry is hidden by the state.

A ferromagnet is the clean example. The Hamiltonian may be rotationally invariant, but the magnetized state chooses a direction. The order parameter is the magnetization

$$
\mathbf M=\langle \mathbf S\rangle.
$$

For a relativistic scalar field with a $\mathbb Z_2$ symmetry, the analogous order parameter is

$$
\langle\phi\rangle.
$$

If the potential has two minima, the symmetry $\phi\mapsto-\phi$ is a symmetry of the theory but not of either chosen vacuum.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Landau effective potential with a symmetric phase and a broken phase; the broken phase has degenerate minima related by symmetry.](/figures/symmetry-anomalies-topology/landau-order-parameter-landscape.svg)

<figcaption>

Landau theory replaces a phase question by an effective potential for an order parameter. In the symmetric phase the minimum is invariant. In the broken phase the minima form symmetry-related choices, and choosing one vacuum hides part or all of the symmetry.

</figcaption>
</figure>

The paradigm is enormously successful. It explains ferromagnets, superfluids, crystals, charge-density waves, chiral symmetry breaking, and many thermal or quantum phase transitions. It also has sharp limits: it does not classify SPT phases, topological order, SET phases, many gauge-theory phases, or fracton-style orders. This page teaches the paradigm and its failure modes.

## Prerequisites

You should know what a global symmetry is, what spontaneous symmetry breaking means, and how a scalar effective potential is interpreted. Useful earlier pages are [What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/), [Continuous and Discrete Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/continuous-and-discrete-symmetries/), and the Spontaneous Symmetry Breaking chapter.

No detailed statistical mechanics is required, but it helps to know that a phase transition is a nonanalytic change in long-distance behavior in the thermodynamic limit.

## Core idea

Landau theory starts with a symmetry group $G$ and an order parameter $\Phi$. The order parameter is a field or expectation value transforming in some representation of $G$:

$$
\Phi\mapsto g\cdot\Phi.
$$

A phase is characterized by the expectation value

$$
\Phi_0=\langle\Phi\rangle.
$$

The subgroup preserving the chosen value is

$$
H=\{g\in G\mid g\cdot\Phi_0=\Phi_0\}.
$$

The symmetry-breaking pattern is written

$$
G\longrightarrow H.
$$

The space of symmetry-related classical vacua is often

$$
\mathcal M_{\rm vac}\simeq G/H,
$$

at least locally and when the order parameter fully captures the degeneracy. For continuous internal symmetries in Lorentz-invariant systems, broken generators typically produce Goldstone modes. For discrete symmetries, there are degenerate vacua and domain walls, but no Goldstone bosons.

This is the basic Landau dictionary:

| Object | Landau meaning |
|---|---|
| $G$ | Symmetry of the theory or Hamiltonian. |
| $\Phi$ | Order parameter transforming under $G$. |
| $\Phi_0$ | Chosen expectation value in a phase. |
| $H$ | Residual symmetry preserving $\Phi_0$. |
| $G/H$ | Vacuum manifold for symmetry-related minima. |
| Broken discrete symmetry | Degenerate vacua and domain walls. |
| Broken continuous symmetry | Goldstone modes and possible topological defects. |

## Setup and conventions

The order parameter may be a scalar, vector, tensor, matrix, spinor bilinear, condensate, density wave amplitude, or more general local observable. We denote it by $\Phi$ or $\varphi$ depending on context.

A simple Landau effective potential for a real order parameter is

$$
V(\varphi)=\frac{r}{2}\varphi^2+\frac{u}{4}\varphi^4,
\qquad u>0.
$$

The theory has a $\mathbb Z_2$ symmetry

$$
\varphi\mapsto-\varphi.
$$

If $r>0$, the unique minimum is

$$
\varphi_0=0,
$$

and the symmetry is unbroken. If $r<0$, the minima are

$$
\varphi_0=\pm\sqrt{-r/u},
$$

and each chosen minimum breaks $\mathbb Z_2$.

For a continuous $O(N)$ vector order parameter,

$$
\boldsymbol\varphi=(\varphi_1,\ldots,\varphi_N),
$$

a standard potential is

$$
V(\boldsymbol\varphi)=\frac{r}{2}\boldsymbol\varphi^2+\frac{u}{4}(\boldsymbol\varphi^2)^2.
$$

When $r<0$, the minima satisfy

$$
\boldsymbol\varphi^2=-r/u.
$$

Choosing a direction breaks

$$
O(N)\longrightarrow O(N-1),
$$

and the vacuum manifold is

$$
O(N)/O(N-1)\simeq S^{N-1}.
$$

:::note[Source note]
Landau theory is often written directly in Euclidean statistical-mechanics language, while QFT treatments often write an effective action for fields. The same long-distance idea is being used: write the most general local functional of the order parameter allowed by symmetry and analyze its minima and fluctuations.
:::

## Effective free energy and symmetry constraints

Landau theory writes an effective free energy or Euclidean effective action for the order parameter:

$$
F[\Phi]=\int d^dx\left[\frac{1}{2}K(\partial_i\Phi)^2+V(\Phi)+\cdots\right].
$$

The dots denote higher-derivative terms and higher powers allowed by symmetry. The key rule is:

$$
F[g\cdot\Phi]=F[\Phi]
\qquad \text{for all }g\in G.
$$

This rule is powerful. If $\Phi$ is odd under $\mathbb Z_2$, the potential cannot contain a term proportional to $\Phi$ or $\Phi^3$ unless the symmetry is explicitly broken. If $\boldsymbol\Phi$ is a vector under $O(N)$, the potential can depend on $\boldsymbol\Phi^2$, but not on a single component unless a direction is explicitly chosen.

The coefficient $r$ is the tuning parameter. In thermal transitions it is often proportional to $T-T_c$. In quantum phase transitions it can be controlled by pressure, magnetic field, coupling strength, density, disorder, or another microscopic parameter.

Mean-field Landau theory predicts the order parameter exponent

$$
\Phi_0\sim (-r)^{1/2}
$$

for $r<0$. Fluctuations can change critical exponents, and the renormalization group explains when mean-field theory is reliable. Landau theory gives the symmetry and order-parameter structure; the RG gives the universal critical behavior.

## Residual symmetry and vacuum manifolds

The unbroken subgroup $H$ matters as much as the original group $G$. The symmetry-breaking pattern

$$
G\to H
$$

controls low-energy fluctuations, possible defects, and selection rules in the broken phase.

For a ferromagnet with rotational symmetry $SO(3)$ and magnetization direction $\hat n$, the unbroken subgroup is rotations about $\hat n$:

$$
SO(3)\to SO(2).
$$

The vacuum manifold is

$$
SO(3)/SO(2)\simeq S^2.
$$

For the $O(N)$ vector model,

$$
O(N)\to O(N-1),
\qquad
\mathcal M_{\rm vac}\simeq S^{N-1}.
$$

For a complex scalar with $U(1)$ symmetry,

$$
\phi\mapsto e^{i\alpha}\phi,
$$

a potential of the form

$$
V(|\phi|)=r|\phi|^2+u|\phi|^4
$$

has a circle of minima for $r<0$:

$$
|\phi|=\sqrt{-r/(2u)}.
$$

The vacuum manifold is $S^1$, and the phase of $\phi$ is the Goldstone direction.

The topology of $G/H$ predicts defects. Connected components give domain walls; nontrivial $\pi_1$ gives vortices; nontrivial $\pi_2$ gives monopole-like textures in suitable dimensions. This is the bridge from Landau theory to the topology of field configurations.

## Discrete symmetry breaking

For a discrete symmetry, the broken phase has several isolated vacua. The simplest example is

$$
\mathbb Z_2:\quad \varphi\mapsto-\varphi.
$$

When the potential has minima at $\pm v$, the vacuum manifold is two points:

$$
\mathcal M_{\rm vac}=\{+v,-v\}.
$$

There is no continuous flat direction and therefore no Goldstone boson. But there are domain walls. In one spatial direction, a domain wall is a configuration satisfying

$$
\varphi(x\to-\infty)=-v,
\qquad
\varphi(x\to+\infty)=+v.
$$

The wall is topologically stable if the boundary conditions force the field to connect different components of the vacuum manifold.

Discrete symmetry breaking is central in Ising models, lattice gauge theories, charge-density waves, nematic phases, and many statistical systems. It is also the cleanest setting for understanding the difference between explicit breaking and spontaneous breaking. A small term

$$
\Delta V=-h\varphi
$$

explicitly breaks $\mathbb Z_2$ and selects one of the two vacua. The degeneracy is gone.

## Continuous symmetry breaking and Goldstone modes

When a continuous global symmetry is broken, the vacuum manifold has continuous directions. Fluctuations along those directions cost no potential energy at leading order. In Lorentz-invariant systems, these become massless Goldstone modes.

For the $O(N)$ model with $r<0$, choose

$$
\boldsymbol\varphi_0=(0,\ldots,0,v).
$$

Write fluctuations as

$$
\boldsymbol\varphi(x)=(\pi_1(x),\ldots,\pi_{N-1}(x),v+\sigma(x)).
$$

The fields $\pi_a$ are Goldstone modes, while $\sigma$ is the radial or amplitude mode. At tree level, the Goldstone fields are massless and the radial mode is massive.

In nonrelativistic systems, Goldstone counting can be subtler because broken charges may have nonzero expectation values in their commutators. Ferromagnets and antiferromagnets are the classic contrast. The symmetry-breaking pattern is still Landau data, but the dispersion relations and number of low-energy modes require the full dynamical structure.

## Order parameters and correlation functions

The order parameter is not only an expectation value. It also controls long-distance correlation functions.

In a symmetric phase,

$$
\langle\Phi\rangle=0,
$$

and connected correlations typically decay exponentially away from criticality:

$$
\langle\Phi(x)\Phi(0)\rangle_c\sim e^{-|x|/\xi}.
$$

Here $\xi$ is the correlation length. Near a continuous transition,

$$
\xi\to\infty,
$$

and the system becomes scale invariant at long distances.

In a broken phase,

$$
\langle\Phi\rangle\neq0,
$$

and the two-point function approaches a constant:

$$
\langle\Phi(x)\Phi(0)\rangle\to |\langle\Phi\rangle|^2
$$

at large separation, up to fluctuations and finite-volume caveats. This long-distance limit is called long-range order.

For continuous broken symmetry in low dimensions, fluctuations can destroy long-range order. The Coleman–Mermin–Wagner theorem is the famous warning: continuous symmetries cannot be spontaneously broken in sufficiently low dimensions under standard assumptions. Landau mean-field intuition must then be replaced by more careful infrared physics.

## Explicit, spontaneous, and approximate breaking

There are three different ideas that often get mixed.

**Explicit breaking** means the Hamiltonian or action does not have the symmetry. Adding $-h\varphi$ to a $\mathbb Z_2$-symmetric potential explicitly breaks the symmetry.

**Spontaneous breaking** means the theory has the symmetry but the chosen state does not. The degenerate vacua at $\varphi=\pm v$ are the elementary example.

**Approximate breaking** means the theory has a small term that breaks the symmetry weakly. Then Goldstone bosons can become pseudo-Goldstone bosons, with masses controlled by the breaking parameter.

A reliable phase diagnosis must say which of the three is present. A nonzero expectation value is not enough by itself: it must be an expectation value of an operator that transforms nontrivially under an actual symmetry of the theory.

## Landau theory and renormalization group

Landau theory by itself is a mean-field theory. It identifies candidate phases and symmetry-breaking patterns. It does not always compute the correct critical exponents.

The renormalization group refines the story. Near a continuous transition, the long-distance physics is controlled by an RG fixed point. The order parameter and symmetry determine the universality class together with dimension, locality, range of interactions, and relevant perturbations.

For example, many microscopically different systems can flow to the same $O(N)$ Wilson–Fisher fixed point. They share critical exponents and scaling functions because the irrelevant microscopic details die away under coarse graining.

The conceptual division is:

$$
\text{Landau theory: phases and allowed operators},
\qquad
\text{RG: long-distance universality and exponents}.
$$

This is why Landau theory remains useful even when mean-field numerical predictions fail.

## Defects from broken symmetry

The topology of the order-parameter manifold predicts possible defects.

If $\pi_0(\mathcal M_{\rm vac})$ is nontrivial, there are domain walls. If $\pi_1(\mathcal M_{\rm vac})$ is nontrivial, there can be vortices. If $\pi_2(\mathcal M_{\rm vac})$ is nontrivial, there can be monopole-like textures. If higher homotopy groups are nontrivial, there can be higher-dimensional textures or solitons in suitable dimensions.

For a broken $U(1)$ symmetry,

$$
\mathcal M_{\rm vac}\simeq S^1,
$$

so

$$
\pi_1(S^1)=\mathbb Z.
$$

This integer is the vortex winding number. In a superfluid, vortices are not optional decorations: they are central to the phase structure and to the Berezinskii–Kosterlitz–Thouless transition in two dimensions.

:::note[Source note]
The defect classification by homotopy is a classical, semiclassical diagnostic. Quantum effects, gauge fields, endpoints, screening, and anomaly constraints can modify which defects are stable or genuine operators.
:::

## Where Landau theory fails

Landau theory is not wrong. It is incomplete.

It fails as a classification principle whenever two phases have the same local symmetry realization but differ by global quantum data. Examples include:

| Phenomenon | Why Landau order is insufficient |
|---|---|
| SPT phase | No intrinsic topological order and no symmetry breaking, but nontrivial boundary/anomaly response. |
| Intrinsic topological order | Long-range entanglement, anyons, topological degeneracy, no local order parameter needed. |
| SET phase | Same topological order can have different symmetry fractionalization or anyon permutation. |
| Deconfined gauge phase | Extended operators and higher-form symmetry diagnose phase structure better than local fields. |
| Fracton order | Subsystem symmetry and restricted mobility do not fit ordinary Landau order alone. |

A famous lesson of modern condensed matter and QFT is that two gapped phases can have the same unbroken symmetry group and the same expectation values of all local order parameters, yet be distinct. The missing data may be entanglement, anomaly, boundary behavior, response action, defect fusion, or higher-form symmetry realization.

## Common pitfalls

**“The order parameter is the phase.”** The order parameter diagnoses one aspect of the phase. It may miss topology, entanglement, symmetry fractionalization, and anomaly data.

**“A nonzero expectation value always means spontaneous symmetry breaking.”** It must transform nontrivially under a genuine symmetry. A gauge-variant expectation value is not by itself a physical local order parameter.

**“Discrete symmetry breaking has Goldstone modes.”** No. Broken discrete symmetry gives degenerate vacua and domain walls, not Goldstone bosons.

**“Mean-field exponents are Landau theory.”** Mean-field exponents are one approximation inside the Landau framework. The symmetry and order-parameter analysis can remain correct even when RG changes the exponents.

**“The vacuum manifold is always exactly $G/H$.”** This is often locally true for symmetry-related minima, but accidental degeneracy, gauge redundancy, constraints, and quantum corrections can change the physical vacuum space.

**“All phases with the same unbroken subgroup are the same.”** They can differ by SPT response, intrinsic topological order, symmetry enrichment, or anomaly data.

## Relations to other pages

This page is the entry point to [Symmetry in Phases of Matter](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/). The Spontaneous Symmetry Breaking chapter develops Goldstone’s theorem, cosets, nonlinear sigma models, and pseudo-Goldstone modes in more detail.

The [Topological Sectors and Solitonic Charges](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/) chapter develops vortices, monopoles, instantons, winding numbers, and textures. The [Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/) chapter turns those configurations into operators and defects. The [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) chapter explains why extended order parameters are natural diagnostics of gauge-theory and topological phases.

The next pages in this chapter explain what Landau theory misses: SPT phases, SET phases, topological order, anomaly-boundary correspondence, higher-form symmetry in matter, fracton previews, and response theory.

## Research status

Landau symmetry breaking is settled and remains indispensable. It is still the first diagnostic for many phases and phase transitions.

The active frontier is not whether Landau theory is useful. It is how to combine it with modern data: entanglement structure, topological order, generalized symmetry, crystalline and subsystem symmetry, anomaly constraints, and response theory. Many real systems involve several layers at once: ordinary symmetry breaking plus topological response, topological order plus symmetry enrichment, or gauge structure plus higher-form symmetry.

## Exercises

### Exercise 1: Minima of the Z₂ Landau potential

For

$$
V(\varphi)=\frac{r}{2}\varphi^2+\frac{u}{4}\varphi^4,
\qquad u>0,
$$

find the minima for $r>0$ and $r<0$. Which phase breaks $\mathbb Z_2$?

<details><summary><strong>Solution</strong></summary>

The extrema satisfy

$$
\frac{dV}{d\varphi}=r\varphi+u\varphi^3=\varphi(r+u\varphi^2)=0.
$$

For $r>0$, the only real minimum is

$$
\varphi=0,
$$

so the symmetry $\varphi\mapsto-\varphi$ is unbroken. For $r<0$, there are two minima

$$
\varphi=\pm\sqrt{-r/u}.
$$

Choosing either minimum breaks $\mathbb Z_2$ spontaneously.

</details>

### Exercise 2: Residual symmetry of the O(N) vector model

Let $\boldsymbol\varphi_0=(0,\ldots,0,v)$ be a chosen vacuum of the $O(N)$ vector model. Show that the unbroken group is $O(N-1)$.

<details><summary><strong>Solution</strong></summary>

An element of $O(N)$ preserves $\boldsymbol\varphi_0$ if it leaves the last basis vector fixed. It can still rotate and reflect the first $N-1$ components among themselves. Those transformations form $O(N-1)$. Thus the symmetry breaking pattern is

$$
O(N)\to O(N-1).
$$

The vacuum manifold is

$$
O(N)/O(N-1)\simeq S^{N-1}.
$$

</details>

### Exercise 3: Goldstone count in the relativistic O(N) model

Using dimensions of Lie groups, count the number of broken generators in

$$
O(N)\to O(N-1).
$$

<details><summary><strong>Solution</strong></summary>

The dimension of $O(N)$ is

$$
\frac{N(N-1)}{2}.
$$

The dimension of $O(N-1)$ is

$$
\frac{(N-1)(N-2)}{2}.
$$

The difference is

$$
\frac{N(N-1)-(N-1)(N-2)}{2}=N-1.
$$

In a Lorentz-invariant theory under standard assumptions, there are $N-1$ Goldstone modes.

</details>

### Exercise 4: Why SPT phases evade Landau order

Explain why a gapped SPT phase can have no local order parameter distinguishing it from a trivial symmetric product state, even though it is not a trivial phase when symmetry is enforced.

<details><summary><strong>Solution</strong></summary>

A local Landau order parameter detects spontaneous symmetry breaking. An SPT phase is short-range entangled and preserves the protecting symmetry, so it need not have any nonzero local operator expectation value that transforms nontrivially. Its distinction from a trivial phase appears in symmetry-protected boundary behavior, response to background fields, or anomaly/inflow data. If the protecting symmetry is broken or ignored, the SPT can often be deformed to a trivial product state.

</details>

## References

- L. D. Landau and E. M. Lifshitz, *Statistical Physics*, for the original order-parameter and symmetry-breaking paradigm.
- S. Coleman, *Aspects of Symmetry*, especially “Secret Symmetry,” for spontaneous symmetry breaking in QFT.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, Chs. 5–6, for spacetime and internal symmetries and conservation laws.
- K. G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” for the RG refinement of Landau critical phenomena.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for the field-theoretic treatment of critical phenomena.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, especially the chapters on broken symmetry, RG, and topological field theory.
- N. Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*, for a compact modern treatment of Landau theory and universality.
- X.-G. Wen, *Quantum Field Theory of Many-Body Systems*, for the limitations of Landau order and the emergence of topological order.

## Version history

- **2026-06-23:** Initial polished draft. Added Landau order-parameter framework, residual symmetry, vacuum manifolds, Goldstone/domain-wall diagnostics, RG relation, defect topology, limitations, and exercises.
