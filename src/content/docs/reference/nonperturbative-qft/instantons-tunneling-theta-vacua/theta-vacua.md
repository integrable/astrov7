---
title: "Theta Vacua"
description: "Explains theta vacua as Bloch-like superpositions of gauge-theory winding sectors and derives the sector-sum form of the theta-dependent path integral."
sidebar:
  label: "Theta Vacua"
  order: 5
level: Advanced
status: "Polished draft"
source: "Srednicki chs. 93–94; Mariño ch. 4; Shifman ch. 5; Coleman; Weinberg Vol. II."
topics:
  - theta vacua
  - topological sectors
  - large gauge transformations
  - Chern–Simons number
  - theta angle
  - Yang–Mills theory
  - CP symmetry
canonicalTopics:
  - nonperturbative-qft
  - theta-vacua
  - instantons
  - topological-charge
  - yang-mills-theory
researchStatus:
  established:
    - "In Yang–Mills theory with integer topological charge, the theta angle labels superselection sectors and weights Euclidean sectors by e^{i theta Q}."
  active:
    - "Theta dependence at strong coupling, at large N, and in theories with nontrivial global form or massless matter requires additional dynamical and global input."
---

## Summary

A theta vacuum is the gauge-theory analog of a Bloch wave in a periodic potential. Instead of choosing one winding sector $|n\rangle$, the physical energy eigenstates are superpositions

$$
|\theta\rangle
=
\sum_{n\in\mathbb Z} e^{-in\theta}|n\rangle,
$$

where $n$ labels pure-gauge vacua, often measured by Chern–Simons number. Large gauge transformations shift $n$ by an integer, so the label $\theta$ is an angle:

$$
\theta\sim\theta+2\pi.
$$

In the Euclidean path integral, the same physics appears as a sum over topological-charge sectors,

$$
Z(\theta)
=
\sum_{Q\in\mathbb Z} e^{i\theta Q}Z_Q
=
\int \mathcal DA\,\exp\left[-S_{E,\mathrm{YM}}[A]+i\theta Q[A]\right].
$$

This page explains why these formulas are not decorative notation. They say that the global topology of gauge-field configuration space changes the Hilbert space and the vacuum energy. The theta angle is locally coupled to a total derivative, but globally it is visible because the path integral contains disconnected sectors.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Theta vacua as Bloch-like superpositions of winding sectors.](/figures/nonperturbative-qft/theta-vacua-sector-sum.svg)

<figcaption>

Theta vacua are Bloch-like superpositions of winding sectors. A large gauge transformation shifts $|n\rangle\mapsto |n+k\rangle$, while $|\theta\rangle$ only picks up a phase. In the path integral, the same label weights topological sectors by $e^{i\theta Q}$.

</figcaption>
</figure>

The most important caution is that there are two related, but not identical, uses of the word “sector.” The states $|n\rangle$ label classical pure-gauge vacua or Chern–Simons-number representatives. The Euclidean sectors $Z_Q$ label histories whose topological charge is $Q$. Instantons relate them by changing $n$ as Euclidean time evolves.

## Prerequisites

You should know [Instantons in Quantum Mechanics](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-quantum-mechanics/), [Instantons in Field Theory](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-in-field-theory/), [Yang–Mills Instantons](/nonperturbative-qft/instantons-tunneling-theta-vacua/yang-mills-instantons/), and [Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/). You should also know the role of [Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/) as the curvature of the vacuum energy at $\theta=0$.

The analogy with a particle in a periodic potential is worth keeping in your head. Replace the coordinate $q$ by the gauge-field configuration $A_i(\mathbf x)$, replace the integer well label by Chern–Simons number, and replace ordinary tunneling paths by Yang–Mills instantons.

## Core idea

Pure Yang–Mills theory has many classical zero-energy configurations. In temporal gauge, $A_0=0$, a vacuum configuration has vanishing magnetic field and hence is a pure gauge,

$$
A_i=iU\partial_iU^{-1}
$$

up to the convention-dependent placement of $i$ and $g$. If space is compactified by adding the point at infinity, a time-independent gauge transformation defines a map

$$
U:S^3\to G.
$$

For $G=SU(N)$ with $N\ge2$,

$$
\pi_3(SU(N))\simeq\mathbb Z.
$$

Thus pure-gauge vacua come in winding classes. We denote the corresponding states by

$$
|n\rangle,
\qquad n\in\mathbb Z.
$$

A large gauge transformation of winding number $k$ shifts the label,

$$
\mathcal U_k|n\rangle=|n+k\rangle.
$$

The Yang–Mills Hamiltonian is invariant under gauge transformations, including large ones. Therefore its matrix elements in the $|n\rangle$ basis depend only on the difference of labels:

$$
\langle n'|H|n\rangle=h_{n'-n}.
$$

This is exactly the structure of a tight-binding Hamiltonian in a periodic crystal. The energy eigenstates are not position eigenstates in one well. They are Bloch waves. In gauge theory, the Bloch waves are the theta vacua.

## Setup and conventions

We use the gauge conventions already fixed in this chapter. The Euclidean topological charge is

$$
Q[A]
=
\frac{1}{16\pi^2}\int d^4x\,\operatorname{tr}F_{\mu\nu}\widetilde F_{\mu\nu}
=
\frac{1}{8\pi^2}\int\operatorname{tr}F\wedge F.
$$

For smooth finite-action $SU(N)$ fields on $\mathbb R^4$ with standard boundary conditions,

$$
Q\in\mathbb Z.
$$

The Euclidean Yang–Mills action with theta angle is written

$$
S_E[A;\theta]
=
S_{E,\mathrm{YM}}[A]-i\theta Q[A],
$$

so a sector of charge $Q$ contributes the phase

$$
e^{i\theta Q}.
$$

With these conventions,

$$
Z(\theta)
=
\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q,
\qquad
Z_Q=\int_Q\mathcal DA\,e^{-S_{E,\mathrm{YM}}[A]}.
$$

Because $Q$ is an integer,

$$
Z(\theta+2\pi)=Z(\theta).
$$

The vacuum energy density is extracted from a large Euclidean four-volume $V_4$ by

$$
\mathcal E(\theta)
=
-\lim_{V_4\to\infty}\frac{1}{V_4}\log Z(\theta),
$$

with the usual understanding that disconnected vacuum-bubble normalization and infrared limits must be handled consistently.

## Large gauge transformations and Bloch states

The defining property of the theta vacuum is its transformation under a large gauge transformation. Start with

$$
|\theta\rangle
=
\sum_{n\in\mathbb Z}e^{-in\theta}|n\rangle.
$$

Then

$$
\mathcal U_k|\theta\rangle
=
\sum_{n\in\mathbb Z}e^{-in\theta}|n+k\rangle.
$$

Let $m=n+k$. Then $n=m-k$, so

$$
\mathcal U_k|\theta\rangle
=
\sum_{m\in\mathbb Z}e^{-i(m-k)\theta}|m\rangle
=
e^{ik\theta}|\theta\rangle.
$$

Thus $|\theta\rangle$ is an eigenstate of large gauge transformations:

$$
\mathcal U_k|\theta\rangle=e^{ik\theta}|\theta\rangle.
$$

Since $e^{ik(\theta+2\pi)}=e^{ik\theta}$ for integer $k$, the label is periodic:

$$
\theta\sim\theta+2\pi.
$$

This is the most compact Hamiltonian definition of a theta sector. It also explains why $|n\rangle$ itself is not the best candidate for the physical vacuum once tunneling is allowed. Tunneling mixes neighboring $n$ sectors, just as a periodic potential mixes wavefunctions localized in different wells.

## Hamiltonian diagonalization

Because

$$
\langle n'|H|n\rangle=h_{n'-n},
$$

the theta states diagonalize the Hamiltonian in the winding-sector direction. Acting on $|\theta\rangle$ gives

$$
H|\theta\rangle
=
\sum_{m,n}h_{m-n}e^{-in\theta}|m\rangle.
$$

Set $r=m-n$. Then $n=m-r$, and the coefficient of $|m\rangle$ is

$$
\sum_r h_r e^{-i(m-r)\theta}
=
e^{-im\theta}\sum_r h_r e^{ir\theta}.
$$

Therefore

$$
H|\theta\rangle
=E(\theta)|\theta\rangle,
\qquad
E(\theta)=\sum_{r\in\mathbb Z}h_r e^{ir\theta}.
$$

If the leading tunneling only connects neighboring sectors, one writes

$$
h_{+1}=h_{-1}=-K,
\qquad K>0,
$$

and obtains

$$
E(\theta)=E_0-2K\cos\theta+\cdots.
$$

This formula is schematic but extremely useful. It says that the theta angle can affect the vacuum energy even though the theta density is locally a total derivative. The effect comes from tunneling through the global topology of field space.

## Path-integral form of the same statement

Now rewrite the same physics in Euclidean language. Suppose the gauge field begins at Euclidean time $\tau=-\infty$ in a representative with Chern–Simons label $n_-$ and ends at $\tau=+\infty$ in a representative with label $n_+$. A finite-action history has

$$
Q=n_+-n_-.
$$

Let $Z_{n_+\leftarrow n_-}$ be the path integral with those boundary conditions. Since the action is invariant under simultaneous large gauge transformations of the endpoints, it depends only on

$$
Q=n_+-n_-.
$$

The theta-to-theta transition amplitude is obtained by summing over endpoint sectors with the Bloch phases:

$$
Z_{\theta'\leftarrow\theta}
=
\sum_{n_+,n_-}e^{in_+\theta'}e^{-in_-\theta}Z_{n_+\leftarrow n_-}.
$$

Because $Z_{n_+\leftarrow n_-}$ depends only on $n_+-n_-$, the sum over the common shift enforces

$$
\theta'=\theta
$$

modulo $2\pi$. Theta is conserved: it labels a superselection sector. Dropping the overall delta function, the remaining amplitude is

$$
Z(\theta)
=
\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q.
$$

The Hamiltonian and path-integral pictures are the same. The Hamiltonian picture emphasizes Bloch states and large gauge transformations. The Euclidean picture emphasizes topological charge and sector sums.

## Theta terms as total derivatives

In Yang–Mills theory,

$$
\operatorname{tr}F\wedge F=d\omega_3(A),
$$

where $\omega_3(A)$ is the Chern–Simons three-form. Therefore the theta term does not change the local classical Yang–Mills equations on a topologically trivial variation with fixed boundary data.

That fact is sometimes misread as “theta is unphysical.” The correct statement is subtler:

$$
\text{locally total derivative}
\not\Rightarrow
\text{globally irrelevant}.
$$

A total derivative can distinguish histories with different boundary winding. The theta term changes the relative phase between sectors. In a theory with no allowed nonzero $Q$ sectors, theta would be invisible. In Yang–Mills theory with standard instanton sectors, it is part of the quantum definition.

This is also why the topological susceptibility matters. At $\theta=0$ in a CP-invariant theory,

$$
\chi_{\rm top}
=
\left.\frac{\partial^2\mathcal E(\theta)}{\partial\theta^2}\right|_{\theta=0}
=
\frac{\langle Q^2\rangle_{\theta=0}}{V_4},
$$

assuming $\langle Q\rangle_{\theta=0}=0$ and standard Euclidean normalization. This quantity measures how strongly the vacuum responds to theta.

## CP and special values of theta

The theta term is odd under orientation reversal. In Lorentzian language, the Yang–Mills theta density is proportional to

$$
\mathbf E^a\cdot\mathbf B^a,
$$

which violates $P$ and $CP$ unless the theta angle is at a special value. With $2\pi$ periodicity, the obvious CP-invariant points are

$$
\theta=0,
\qquad
\theta=\pi
\quad (\mathrm{mod}\ 2\pi).
$$

At $\theta=0$, CP usually acts within the same vacuum sector without drama. At $\theta=\pi$, CP maps $\theta$ to $-\theta$, which is equivalent to $\pi$ only after using $2\pi$ periodicity. This can lead to interesting possibilities: CP may be unbroken, spontaneously broken, or involved in a phase transition depending on the theory, matter content, and global structure. There is no one-line universal answer for all gauge theories.

For QCD-like theories with fermion masses, the physically meaningful CP-violating parameter is not just the bare theta angle. A chiral rotation can move phase between the theta term and the quark mass matrix. With the sign convention used in this chapter, the invariant phase is conventionally described as the appropriate combination of $\theta$ and $\arg\det M$; many particle-physics texts define a parameter called $\bar\theta$ with a sign depending on how the theta term and chiral rotation are normalized. The invariant content is what matters.

A massless quark can make theta unobservable in the idealized theory, because an anomalous chiral rotation can remove it. In the path integral, the corresponding statement is tied to fermion zero modes: nonzero-$Q$ sectors have zero modes that can make the fermion determinant vanish unless masses or operator insertions soak them up. This is the bridge to the later pages on fermion zero modes and anomalies.

## Common pitfalls

**Choosing one $|n\rangle$ as the physical vacuum.** The $|n\rangle$ states are useful semiclassical representatives. Once tunneling between neighboring sectors is included, the Hamiltonian is diagonalized by $|\theta\rangle$, not by a single $|n\rangle$.

**Forgetting that theta is periodic.** In the standard $SU(N)$ story with integer $Q$, the sector weight $e^{i\theta Q}$ implies $2\pi$ periodicity. If the allowed topological charges are modified by global-form choices, background fields, boundaries, or defects, the periodicity and meaning of theta may need refinement.

**Saying that the theta term is zero because it is a total derivative.** The theta density is locally a total derivative, but its integral is a topological charge. A total derivative can affect quantum amplitudes when the path integral sums over globally distinct histories.

**Mixing up $n$ and $Q$.** The label $n$ usually refers to a vacuum representative or Chern–Simons number on a spatial slice. The integer $Q$ labels a Euclidean history and equals the change $n_+-n_-$ for finite-action tunneling trajectories.

**Assuming the dilute instanton formula is exact.** The expression $E(\theta)=E_0-2K\cos\theta$ is the leading nearest-neighbor or dilute-gas picture. Strongly coupled Yang–Mills can have a more complicated $\theta$ dependence while preserving the same periodicity and CP constraints.

**Ignoring matter.** Dynamical fermions, especially massless fermions, can change the physical theta dependence. Fermion zero modes are not a small correction to this story; they can decide whether a topological sector contributes at all.

## Relations to other pages

[Instanton Number](/nonperturbative-qft/instantons-tunneling-theta-vacua/instanton-number/) provides the definition of $Q$ and explains why it is an integer under the standard assumptions.

[Tunneling Between Vacua](/nonperturbative-qft/instantons-tunneling-theta-vacua/tunneling-between-vacua/) explains how instantons generate the off-diagonal matrix elements that make $|\theta\rangle$ the right basis.

[Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/) explains how the curvature of $\mathcal E(\theta)$ near $\theta=0$ is measured by fluctuations of $Q$.

[Yang–Mills Instantons](/nonperturbative-qft/instantons-tunneling-theta-vacua/yang-mills-instantons/) supplies the semiclassical saddle whose charge-one contribution carries the factor $e^{-8\pi^2/g^2+i\theta}$.

[Fermion Zero Modes](/nonperturbative-qft/instantons-tunneling-theta-vacua/fermion-zero-modes/) and [Instantons and Anomalies](/nonperturbative-qft/instantons-tunneling-theta-vacua/instantons-and-anomalies/) explain how chiral rotations, zero modes, and the anomaly modify theta dependence in theories with fermions.

## Research status

**Established.** The construction of theta vacua as eigenstates of large gauge transformations and the sector-sum formula $Z(\theta)=\sum_Q e^{i\theta Q}Z_Q$ are standard for Yang–Mills theory under the usual finite-action and global assumptions.

**Dynamical.** The exact function $\mathcal E(\theta)$ is a dynamical observable. Semiclassical instantons give a controlled approximation only in regimes where instantons are dilute and their size integrals are controlled.

**Global and active.** Gauge-group global form, background higher-form gauge fields, boundaries, defects, fractional instanton number, and large-N branch structure refine the simple $2\pi$-periodic story. The basic lesson remains: theta dependence is global data, not a local perturbative vertex in disguise.

## Exercises

### Exercise 1: Large gauge transformations on theta vacua

Assume

$$
\mathcal U_k|n\rangle=|n+k\rangle,
\qquad
|\theta\rangle=\sum_{n\in\mathbb Z}e^{-in\theta}|n\rangle.
$$

Show that $|\theta\rangle$ is an eigenstate of $\mathcal U_k$ and find the eigenvalue.

<details><summary><strong>Solution</strong></summary>

Apply $\mathcal U_k$:

$$
\mathcal U_k|\theta\rangle
=
\sum_{n\in\mathbb Z}e^{-in\theta}|n+k\rangle.
$$

Let $m=n+k$, so $n=m-k$. Then

$$
\mathcal U_k|\theta\rangle
=
\sum_{m\in\mathbb Z}e^{-i(m-k)\theta}|m\rangle
=
e^{ik\theta}\sum_{m\in\mathbb Z}e^{-im\theta}|m\rangle.
$$

Therefore

$$
\mathcal U_k|\theta\rangle=e^{ik\theta}|\theta\rangle.
$$

</details>

### Exercise 2: Theta periodicity from sector sums

Assume

$$
Z(\theta)=\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q.
$$

Show that $Z(\theta+2\pi)=Z(\theta)$.

<details><summary><strong>Solution</strong></summary>

We compute

$$
Z(\theta+2\pi)
=
\sum_{Q\in\mathbb Z}e^{i(\theta+2\pi)Q}Z_Q
=
\sum_{Q\in\mathbb Z}e^{i\theta Q}e^{2\pi iQ}Z_Q.
$$

Since $Q$ is an integer,

$$
e^{2\pi iQ}=1.
$$

Hence

$$
Z(\theta+2\pi)=Z(\theta).
$$

</details>

### Exercise 3: Nearest-neighbor mixing and the cosine band

Suppose the only nonzero Hamiltonian matrix elements between winding sectors are

$$
\langle n|H|n\rangle=E_0,
\qquad
\langle n+1|H|n\rangle=
\langle n|H|n+1\rangle=-K,
$$

with $K>0$. Show that

$$
H|\theta\rangle=(E_0-2K\cos\theta)|\theta\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Using

$$
|\theta\rangle=\sum_n e^{-in\theta}|n\rangle,
$$

the diagonal term gives

$$
E_0\sum_n e^{-in\theta}|n\rangle=E_0|\theta\rangle.
$$

The off-diagonal terms give

$$
-K\sum_n e^{-in\theta}(|n+1\rangle+|n-1\rangle).
$$

In the first sum set $m=n+1$, so $e^{-in\theta}=e^{-i(m-1)\theta}=e^{i\theta}e^{-im\theta}$. In the second set $m=n-1$, so $e^{-in\theta}=e^{-i(m+1)\theta}=e^{-i\theta}e^{-im\theta}$. Thus the off-diagonal part is

$$
-K(e^{i\theta}+e^{-i\theta})|\theta\rangle=-2K\cos\theta\,|\theta\rangle.
$$

Therefore

$$
H|\theta\rangle=(E_0-2K\cos\theta)|\theta\rangle.
$$

</details>

## References

- M. Srednicki, *Quantum Field Theory*, chapters 93–94, for a clean treatment of winding sectors, theta vacua, instanton-mediated tunneling, and quarks with theta.
- M. Mariño, *Instantons and Large N*, chapter 4, for topological charge, theta vacua, Yang–Mills instantons, and large-N theta dependence.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapter 5, for BPST instantons, tunneling in Yang–Mills theory, and Chern–Simons-number interpretation.
- S. Coleman, *Aspects of Symmetry*, for the classic physical perspective on instantons and tunneling.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, for theta terms, anomalies, and gauge-theory applications.
- A. M. Polyakov, *Gauge Fields and Strings*, for topology of gauge fields and qualitative effects of instantons.

## Version history

- **2026-06-27:** Initial polished draft. Added after Instanton Number as the conceptual page on Bloch-like theta sectors and theta-weighted path-integral sums.
