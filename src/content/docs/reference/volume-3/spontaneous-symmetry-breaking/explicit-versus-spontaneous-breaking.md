---
title: "Explicit Versus Spontaneous Breaking"
description: "Compares explicit and spontaneous symmetry breaking using actions, states, Ward identities, order of limits, pseudo-Goldstone masses, spurions, and diagnostic examples."
sidebar:
  label: "Explicit Versus Spontaneous Breaking"
  order: 7
level: Graduate
status: "Polished draft"
source: "Coleman on secret symmetry and soft pions; Srednicki §§30–32; Schwartz Ch. 28; Weinberg Vol. II; Burgess on symmetry and EFT; Altland–Simons on broken symmetry and collective phenomena."
topics:
  - explicit symmetry breaking
  - spontaneous symmetry breaking
  - pseudo-Goldstone bosons
  - Ward identities
  - source limits
  - spurions
  - order parameters
canonicalTopics:
  - explicit-symmetry-breaking
  - spontaneous-symmetry-breaking
  - pseudo-goldstone-boson
  - symmetry-breaking-source
  - spurion
  - ward-identity
  - order-of-limits
researchStatus:
  established:
    - "Explicit breaking is breaking by the dynamics, while spontaneous breaking is breaking by the state or phase of an exactly symmetric theory."
    - "Small explicit breaking lifts vacuum degeneracy and gives pseudo-Goldstone modes parametrically small masses controlled by Ward identities and EFT spurions."
  active:
    - "The same distinction becomes subtler for gauge redundancy, anomalies, open systems, spacetime symmetries, finite volume, generalized symmetries, and non-invertible symmetries."
---

## Summary

A symmetry can fail in two very different ways.

In **explicit symmetry breaking**, the dynamics is not invariant. The action, Hamiltonian, regulator, boundary condition, source, or quantum measure contains a term that violates the symmetry. Infinitesimally,

$$
\delta_A S\ne0,
$$

and the corresponding current has a nonzero divergence,

$$
\partial_\mu j_A^\mu = B_A,
$$

where $B_A$ is the breaking operator.

In **spontaneous symmetry breaking**, the dynamics is invariant but the state is not. The action and current obey

$$
\delta_A S=0,
\qquad
\partial_\mu j_A^\mu=0,
$$

but the selected vacuum is not invariant:

$$
Q_A|\Omega\rangle\ne0
$$

in the infinite-volume sense appropriate to a broken phase.

<figure class="doc-figure" style="--figure-width: 56rem;">

![A diagram comparing explicit and spontaneous symmetry breaking. Explicit breaking changes the action and gives a breaking operator in the Ward identity. Spontaneous breaking keeps the action symmetric but selects a non-invariant state after taking the infinite-volume limit before removing the source. Small explicit breaking on top of spontaneous breaking lifts the vacuum manifold and gives pseudo-Goldstone masses.](/figures/symmetry-anomalies-topology/explicit-spontaneous-breaking-limits.svg)

<figcaption>

Explicit breaking is a property of the dynamics; spontaneous breaking is a property of the state or phase. The clean diagnostic uses both the Ward identity and the order of limits. A small source can diagnose spontaneous breaking, but if it remains nonzero it also explicitly breaks the symmetry.

</figcaption>
</figure>

The most important diagnostic is the order of limits. If $h$ is a small symmetry-breaking source and $V$ is the spatial volume, then a spontaneous order parameter is detected by

$$
\lim_{h\to0^+}\lim_{V\to\infty}\langle\mathcal O\rangle_h\ne0,
$$

while in finite volume the symmetry is restored when the source is removed first:

$$
\lim_{V\to\infty}\lim_{h\to0^+}\langle\mathcal O\rangle_h=0
$$

for an order parameter charged under the symmetry.

A compact slogan:

$$
\text{explicit breaking: the equations choose a direction},
$$

while

$$
\text{spontaneous breaking: the phase chooses a direction}.
$$

## Prerequisites

Read [Order Parameters](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/order-parameters/), [Degenerate Vacua](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/degenerate-vacua/), [Goldstone Theorem](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-theorem/), and [Goldstone Modes](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-modes/) first.

For the Ward-identity language, you should know [Noether Currents](/symmetry-anomalies-topology/noether-currents-ward-identities/noether-currents/), [Current Conservation in Correlation Functions](/symmetry-anomalies-topology/noether-currents-ward-identities/current-conservation-in-correlation-functions/), and [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/).

## Core idea

A symmetry is first a statement about dynamics. If a transformation $g\in G$ maps allowed histories to allowed histories with the same quantum weight, then $G$ is a symmetry of the theory. In Lagrangian language, this means the action and measure are invariant, up to harmless boundary terms.

A vacuum is a state. It can preserve all, part, or none of the symmetry of the dynamics. If the dynamics has symmetry $G$ but the vacuum is invariant only under a subgroup $H$, then the symmetry is spontaneously broken:

$$
G\longrightarrow H.
$$

This is why the phrase “broken symmetry” is slightly dangerous. It does not say what is broken.

The three clean questions are:

1. Is the action or quantum measure invariant?
2. Is the state invariant?
3. Are we taking the infinite-volume and zero-source limits in the right order?

The answers distinguish explicit breaking, spontaneous breaking, approximate symmetry, and pseudo-Goldstone physics.

## Setup and conventions

Let a continuous transformation with local parameter $\epsilon^A(x)$ act on fields as

$$
\delta\Phi^i(x)=\epsilon^A(x)(T_A\Phi)^i(x).
$$

A localized variation of the action takes the form

$$
\delta S
=
-\int d^d x\,\partial_\mu\epsilon^A(x)\,j_A^\mu(x)
+
\int d^d x\,\epsilon^A(x)\,B_A(x),
$$

where $j_A^\mu$ is the Noether current and $B_A$ is the explicit-breaking operator. Integrating by parts gives the operator equation, up to equations of motion and contact-term conventions,

$$
\partial_\mu j_A^\mu=B_A.
$$

If $B_A=0$, the symmetry is exact at the level of the dynamics. The vacuum can still break it spontaneously. If $B_A\ne0$, the symmetry is explicitly broken.

:::note[Source note: signs in Ward identities]
The sign in $\partial_\mu j_A^\mu=B_A$ depends on whether one defines $\delta S$ with $-\partial_\mu\epsilon\,j^\mu$ or $+\partial_\mu\epsilon\,j^\mu$, and on Lorentzian versus Euclidean conventions. The invariant content is that the local Ward identity contains a non-contact insertion of the explicit-breaking operator $B_A$.
:::

In correlation functions, the Ward identity becomes schematically

$$
\partial_\mu\langle T\,j_A^\mu(x)\mathcal X\rangle
=
-i\sum_k\delta^{(d)}(x-x_k)
\langle T\,\mathcal O_1\cdots \delta_A\mathcal O_k\cdots\rangle
+
\langle T\,B_A(x)\mathcal X\rangle,
$$

where $\mathcal X=\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)$. Contact terms encode the transformation of inserted operators; the non-contact term $B_A$ encodes explicit breaking.

For anomalous symmetries there is an additional quantum contribution to the right-hand side. That case belongs in the Anomalies chapter, but it is useful to remember the pattern:

$$
\partial_\mu j_A^\mu
=
B_A+\mathcal A_A.
$$

Here $\mathcal A_A$ is not a classical explicit-breaking term in the Lagrangian; it is a failure of the quantum measure or regulator to preserve the symmetry.

## Explicit breaking

Explicit breaking means the transformation is not a symmetry of the dynamics.

The simplest example is an $O(N)$ scalar with a linear source:

$$
\mathcal L
=
\frac12\partial_\mu\Phi^I\partial^\mu\Phi^I
-
\frac\lambda4(\Phi^I\Phi^I-v^2)^2
+h\Phi^N.
$$

For $h=0$, the theory has $O(N)$ symmetry. For $h\ne0$, the source picks out the $N$th direction and reduces the symmetry to $O(N-1)$.

The breaking is explicit because the Lagrangian itself contains a preferred direction. No subtle infinite-volume limit is needed to see it.

Another example is a mass term that breaks chiral symmetry. A massless Dirac fermion can have independent rotations of left- and right-handed components. The term

$$
-m\bar\psi\psi
=-m(\bar\psi_L\psi_R+\bar\psi_R\psi_L)
$$

couples left and right components and explicitly breaks axial chiral symmetry.

Explicit breaking can be small, large, soft, hard, relevant, irrelevant, controlled by a spurion, or generated by boundary conditions. But the diagnostic is the same: the transformation does not leave the dynamics invariant.

## Spontaneous breaking

Spontaneous breaking means the dynamics is symmetric but the chosen phase is not.

For the $O(N)$ model with $h=0$, the potential is invariant under all $O(N)$ rotations. The classical minima satisfy

$$
\Phi^I\Phi^I=v^2,
$$

so they form a sphere. Choosing

$$
\langle\Phi^I\rangle=v\delta^{IN}
$$

preserves only $O(N-1)$. The symmetry of the theory is $O(N)$; the symmetry of this vacuum is $O(N-1)$.

At finite volume, tunneling and quantum averaging can restore the symmetry of the exact ground state. A true broken phase is defined by the infinite-volume limit, where different vacua become superselection sectors and the system can remain in one of them.

The practical diagnostic uses a small source $h$ that selects a direction:

$$
\langle\Phi^N\rangle_h\ne0.
$$

Then take the thermodynamic limit first and remove the source second:

$$
\langle\Phi^N\rangle_{\text{SSB}}
=
\lim_{h\to0^+}\lim_{V\to\infty}\langle\Phi^N\rangle_h.
$$

If this limit is nonzero, the symmetry is spontaneously broken.

This is not pedantry. It is the difference between a magnet that remembers its direction after the external field is removed and a finite molecule that merely polarizes while the field is applied.

## The order of limits

The order of limits is the cleanest way to separate explicit and spontaneous breaking.

Let $h$ be a source for a charged order parameter $\mathcal O$. The generating functional is

$$
Z[h]=\int\mathcal D\Phi\,e^{iS+i\int d^d x\,h\mathcal O}.
$$

At finite volume, if the measure and action are invariant and $h=0$, the expectation value of a charged operator vanishes:

$$
\langle\mathcal O\rangle_{V,h=0}=0.
$$

Removing the source first therefore gives

$$
\lim_{V\to\infty}\lim_{h\to0}\langle\mathcal O\rangle_{V,h}=0.
$$

But taking $V\to\infty$ first can produce multiple superselection sectors. The source selects one sector, and after the source is removed the order parameter can remain nonzero:

$$
\lim_{h\to0^+}\lim_{V\to\infty}\langle\mathcal O\rangle_{V,h}\ne0.
$$

The source $h$ has two roles:

- while $h\ne0$, it explicitly breaks the symmetry;
- in the double limit, it serves as a diagnostic tool for spontaneous breaking.

Many beginner confusions come from mixing these two roles.

## Small explicit breaking and pseudo-Goldstone modes

Suppose $G\to H$ is spontaneously broken when $h=0$. The exact Goldstone modes are massless because the vacuum manifold is exactly flat.

Now add a small explicit-breaking term. The vacuum manifold is no longer exactly flat; it acquires a shallow potential. The Goldstone fields become **pseudo-Goldstone bosons**.

For the $O(N)$ example,

$$
\mathcal L
=
\frac12\partial_\mu\Phi^I\partial^\mu\Phi^I
-
\frac\lambda4(\Phi^2-v^2)^2
+h\Phi^N.
$$

Parameterize the low-energy field as

$$
\Phi^I\simeq F n^I,
\qquad
n^I n^I=1.
$$

The source contributes the potential

$$
V_h(n)=-hF n^N.
$$

Using local pion coordinates

$$
n^a=\frac{\pi^a}{F},
\qquad
n^N=\sqrt{1-\frac{\pi^a\pi^a}{F^2}},
$$

we find

$$
V_h(\pi)
=-hF+
\frac{h}{2F}\pi^a\pi^a+O(\pi^4).
$$

Therefore the pseudo-Goldstone mass is

$$
m_\pi^2=\frac{h}{F}.
$$

This result is simple but profound: small explicit breaking gives a small mass because the mass must vanish when the breaking parameter vanishes.

:::note[Source note: sign of $h$]
The sign of the source term is conventional. Here $+h\Phi^N$ in the Lorentzian Lagrangian corresponds to a potential contribution $-h\Phi^N$, so for $h>0$ the vacuum points toward positive $\Phi^N$. Reversing the sign of the source reverses the selected vacuum direction, not the physical logic.
:::

The same idea appears in chiral symmetry breaking in QCD. In the idealized massless theory, pions are Goldstone bosons of approximate chiral symmetry breaking. Small quark masses explicitly break chiral symmetry and make the pions light but not massless. The low-energy relation has the schematic form

$$
m_\pi^2\propto m_q,
$$

with the proportionality controlled by the chiral condensate and the pion decay constant.

## Spurions

A **spurion** is a bookkeeping device that lets us treat an explicitly breaking parameter as if it transformed under the symmetry.

Suppose the Lagrangian contains a term

$$
\Delta\mathcal L=h_i\mathcal O^i.
$$

If $\mathcal O^i$ transforms in a representation of $G$, then a fixed constant $h_i$ may break $G$. But we can temporarily assign $h_i$ the inverse transformation law so that $h_i\mathcal O^i$ is formally invariant.

Then we build the effective action using $G$ invariance, treating $h_i$ as a background field. At the end, we set $h_i$ to its physical constant value. This method organizes all explicit-breaking effects consistently.

Spurions are especially useful because they answer the question:

$$
\text{Which symmetry-breaking terms are allowed at low energy?}
$$

The answer is: all terms invariant under the combined transformation of fields and spurions.

In chiral perturbation theory, the quark mass matrix is treated as a spurion. In magnets, an external magnetic field can be treated as a spurion. In lattice models, anisotropies can be treated as spurions for rotational symmetry. In EFT, spurions are not decorative notation; they are how approximate symmetry becomes predictive.

## Ward identities and the mass of pseudo-Goldstone bosons

The Ward identity sees explicit breaking directly. If

$$
\partial_\mu j_A^\mu=B_A,
$$

then current conservation no longer forces a massless pole. Instead, the divergence of the current can interpolate with a light pseudo-Goldstone state.

For a pseudo-Goldstone state $|\pi_B(p)\rangle$, define

$$
\langle\Omega|j_A^\mu(0)|\pi_B(p)\rangle
=iF_{AB}p^\mu.
$$

Taking the divergence gives

$$
\langle\Omega|\partial_\mu j_A^\mu(0)|\pi_B(p)\rangle
=F_{AB}m_{\pi_B}^2
$$

up to sign conventions for on-shell momentum and state normalization. Therefore

$$
F_{AB}m_{\pi_B}^2
\sim
\langle\Omega|B_A(0)|\pi_B\rangle.
$$

This is the Ward-identity reason pseudo-Goldstone masses are controlled by the explicit-breaking operator.

When $B_A\to0$, the mass goes to zero, provided the spontaneous-breaking order parameter remains nonzero and the assumptions of Goldstone’s theorem continue to hold.

## Explicit breaking versus anomalies

An anomaly is often described as a symmetry that is present classically but broken quantum mechanically. That is useful, but one must be precise.

For an anomalous current,

$$
\partial_\mu j_A^\mu=\mathcal A_A,
$$

where $\mathcal A_A$ comes from the regulator or path-integral measure rather than from a classical term in the action.

For example, an axial current of fermions can obey

$$
\partial_\mu j_5^\mu
\propto
F_{\mu\nu}\widetilde F^{\mu\nu}
$$

in a background gauge field. This resembles explicit breaking in the Ward identity, but its origin is different: no regulator can preserve all the desired symmetries simultaneously.

For this chapter, the practical rule is:

- explicit breaking is put into the dynamics by terms, sources, boundary conditions, or regulators;
- spontaneous breaking is a property of the state;
- anomalies are quantum obstructions and get their own chapter.

Do not use “anomaly” as a fancy synonym for “small explicit breaking.”

## Examples and diagnostics

| System | Exact or approximate symmetry | Explicit breaking? | Spontaneous breaking? | Low-energy consequence |
|---|---|---|---|---|
| Ising magnet at zero field below $T_c$ | $\mathbb Z_2$ spin flip | No | Yes | Two pure phases, domain walls |
| Ising magnet with magnetic field | $\mathbb Z_2$ spin flip | Yes | Not as an exact symmetry | Unique preferred phase |
| $O(N)$ model at $h=0$ | $O(N)$ | No | $O(N)\to O(N-1)$ possible | $N-1$ Goldstone modes |
| $O(N)$ model with small $h$ | $O(N)$ approximate | Yes | Approximate remnant | Pseudo-Goldstone masses |
| QCD with massless light quarks | Chiral symmetry idealization | No for the idealized symmetry, ignoring anomaly subtleties | Yes | Goldstone pions in the idealized limit |
| QCD with small quark masses | Chiral symmetry approximate | Yes | Approximate chiral breaking | Light pions |
| Gauge redundancy with Higgs field | Gauge redundancy | Not a physical global symmetry | Not spontaneous breaking of a physical gauge symmetry | Higgs mechanism; no Goldstone particle in spectrum |

The last row is a trap worth emphasizing. Gauge redundancy is not a physical symmetry that can be spontaneously broken in the same sense as a global symmetry. The Higgs mechanism is real, but the slogan “spontaneously broken gauge symmetry” should be handled with care. A later page gives the precise version.

## Approximate symmetry

In realistic QFT, many symmetries are approximate. Approximate symmetry means the action can be written as

$$
S=S_0+\epsilon S_1,
$$

where $S_0$ has a symmetry and $S_1$ breaks it. If $\epsilon$ is small, the symmetry remains useful.

Approximate symmetries are powerful because they organize small numbers. If setting $\epsilon=0$ increases the symmetry of the theory, then small $\epsilon$ is technically natural in the sense that quantum corrections to symmetry-breaking effects are proportional to symmetry-breaking parameters.

This is why pseudo-Goldstone bosons can naturally be light. Their masses are not small by accident; they are small because they are controlled by parameters whose vanishing restores symmetry.

But approximate symmetry is not the same as spontaneous symmetry breaking. One can have:

- exact symmetry with no spontaneous breaking;
- exact symmetry with spontaneous breaking;
- approximate symmetry with no spontaneous breaking;
- approximate symmetry with approximate spontaneous breaking and pseudo-Goldstone modes.

The words matter because the infrared physics differs.

## Common pitfalls

**Saying “the symmetry is broken” without saying where.** Always ask whether the breaking is in the action, the measure, the source, the boundary condition, or the state.

**Using a small source and forgetting to remove it.** A source can diagnose spontaneous breaking only through the double limit. At nonzero source, the symmetry is explicitly broken.

**Expecting Goldstone bosons for explicitly broken symmetries.** Exact Goldstone bosons require an exact continuous global symmetry that is spontaneously broken. Small explicit breaking gives pseudo-Goldstone modes instead.

**Confusing gauge redundancy with global symmetry.** Gauge redundancy is a description, not a physical operation acting on distinct states. The Higgs mechanism must be phrased using gauge-invariant observables or a gauge-fixed description with care.

**Confusing anomalies with ordinary explicit breaking.** An anomaly appears as a breaking term in a quantum Ward identity, but its origin is the measure/regulator and its implications are different.

**Ignoring finite volume.** Finite systems can show sharp crossovers and long-lived aligned states, but exact spontaneous symmetry breaking is an infinite-volume phenomenon.

## Relations to other pages

[Goldstone Theorem](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-theorem/) proves why exact spontaneous breaking gives massless modes. [Goldstone Modes](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/goldstone-modes/) explains their dynamics, while [Nonlinear Sigma Models Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/nonlinear-sigma-models-preview/) shows how their interactions are organized.

[Pseudo-Goldstone Bosons](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/pseudo-goldstone-bosons/) will develop the mass formulas and EFT power counting more systematically. [Higgs Mechanism Preview](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/higgs-mechanism-preview/) explains why local gauge redundancy changes the Goldstone story.

The Anomalies chapter explains anomalous Ward identities. The Background Fields and Gauging chapter explains sources and spurions in a broader framework.

## Research status

The conceptual distinction between explicit and spontaneous breaking is settled and foundational. The source-limit diagnostic is standard in statistical mechanics, condensed matter, and QFT.

The active subtleties appear when the assumptions are weakened: finite volume, finite temperature, open systems, long-range interactions, gauge theories, anomalous symmetries, subsystem symmetries, higher-form symmetries, non-invertible symmetries, and phases where no local order parameter exists. In these settings, the basic question remains the same — dynamics or state? — but the correct diagnostic may involve extended operators, boundary conditions, algebraic sectors, or background fields rather than a simple local expectation value.

## Exercises

### Exercise 1: Source-selected Ising order parameter

Consider a finite Ising system with spin-flip symmetry at zero magnetic field. Explain why $\langle M\rangle=0$ at finite volume when $h=0$, even below the critical temperature. Then explain how

$$
\lim_{h\to0^+}\lim_{V\to\infty}\langle M\rangle_h
$$

can be nonzero.

<details><summary><strong>Solution</strong></summary>

At finite volume and $h=0$, the Hamiltonian is invariant under spin flip $M\to -M$. If the Gibbs state or ground state is chosen symmetrically, configurations with magnetization $M$ and $-M$ have equal weight, so the expectation value cancels:

$$
\langle M\rangle=0.
$$

Below the critical temperature, the probability distribution has peaks near positive and negative magnetization. A small positive field $h$ favors the positive peak. If the thermodynamic limit is taken first, the barrier between the two phases becomes infinite, and the system remains in the selected phase as $h\to0^+$. Therefore the double limit can be nonzero.

</details>

### Exercise 2: Pseudo-Goldstone mass in the $O(N)$ model

Starting from

$$
V_h(n)=-hF n^N,
\qquad n^I n^I=1,
$$

with

$$
n^a=\frac{\pi^a}{F},
\qquad
n^N=\sqrt{1-\frac{\pi^a\pi^a}{F^2}},
$$

show that $m_\pi^2=h/F$.

<details><summary><strong>Solution</strong></summary>

Expand the square root:

$$
n^N
=
1-rac{\pi^a\pi^a}{2F^2}+O(\pi^4).
$$

Then

$$
V_h
=
-hF\left(1-rac{\pi^a\pi^a}{2F^2}+O(\pi^4)\right)
=
-hF+rac{h}{2F}\pi^a\pi^a+O(\pi^4).
$$

A canonically normalized scalar potential contains

$$
V\supset \frac12m_\pi^2\pi^a\pi^a.
$$

Thus

$$
m_\pi^2=\frac{h}{F}.
$$

</details>

### Exercise 3: Ward identity with explicit breaking

Suppose

$$
\partial_\mu j^\mu=B.
$$

Explain why the charge

$$
Q(t)=\int d^{d-1}\mathbf x\,j^0(t,\mathbf x)
$$

is not conserved when $\int d^{d-1}\mathbf x\,B\ne0$, assuming no boundary flux.

<details><summary><strong>Solution</strong></summary>

Using

$$
\partial_\mu j^\mu=\partial_0j^0+\partial_i j^i=B,
$$

integrate over space:

$$
\frac{dQ}{dt}
+
\int d^{d-1}\mathbf x\,\partial_i j^i
=
\int d^{d-1}\mathbf x\,B.
$$

If there is no boundary flux, the spatial divergence integrates to zero. Therefore

$$
\frac{dQ}{dt}=\int d^{d-1}\mathbf x\,B.
$$

The charge is conserved only if the spatial integral of the breaking operator vanishes.

</details>

### Exercise 4: Spurion transformation

Let $\mathcal O^i$ transform as a vector under $O(N)$:

$$
\mathcal O^i\to R^i_{\ j}\mathcal O^j.
$$

A term $h_i\mathcal O^i$ with fixed $h_i$ explicitly breaks $O(N)$. What transformation law should be assigned to $h_i$ if one wants to treat it as a spurion and make $h_i\mathcal O^i$ formally invariant?

<details><summary><strong>Solution</strong></summary>

We need

$$
h_i\mathcal O^i
\longrightarrow
h'_i R^i_{\ j}\mathcal O^j
=
h_j\mathcal O^j.
$$

Thus

$$
h'_i R^i_{\ j}=h_j.
$$

Equivalently,

$$
h'_i=h_j(R^{-1})^j_{\ i}.
$$

So the spurion transforms in the dual representation. Once invariant terms are classified, one sets $h_i$ back to its fixed physical value.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially “Soft pions” and “Secret symmetry.”
- M. Srednicki, *Quantum Field Theory*, sections on spontaneous symmetry breaking and continuous symmetries.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter on spontaneous symmetry breaking and anomalies.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters on effective Lagrangians, chiral dynamics, and symmetry breaking.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapters on symmetries, nonlinear realizations, and anomaly matching.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, chapters on broken symmetry, collective phenomena, and response.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chapters on field theory with symmetries and critical phenomena.

## Version history

- 2026-06-17: Initial polished draft. Added the action/state distinction, Ward-identity diagnostic, order-of-limits test, pseudo-Goldstone mass example, spurion method, anomaly caveat, diagnostic table, and exercises.
