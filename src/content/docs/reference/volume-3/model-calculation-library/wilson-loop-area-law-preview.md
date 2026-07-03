---
title: "Wilson-Loop Area Law: Preview"
description: "A model calculation showing how a rectangular Wilson loop diagnoses confinement through an area law and how this relates to one-form symmetry."
sidebar:
  label: "Wilson-Loop Area Law"
  order: 11
level: Graduate
status: "Polished draft"
source: "Srednicki §§82–83; Polyakov Chs. 3, 5, 7; Gaiotto–Kapustin–Seiberg–Willett 2015; Altland–Simons Chs. 8 and 10."
topics:
  - Wilson loop
  - area law
  - confinement
  - one-form symmetry
  - center symmetry
  - lattice gauge theory
canonicalTopics:
  - wilson-loop
  - area-law
  - confinement-diagnostic
  - one-form-symmetry
  - model-calculation
researchStatus:
  established:
    - "The Wilson-loop area law is a standard diagnostic of confinement in pure gauge theory and in strong-coupling lattice gauge theory."
  active:
    - "Which line operators are genuine and which area/perimeter laws are meaningful can depend on matter content, global form of the gauge group, generalized symmetries, and continuum limits."
---

## Summary

A Wilson loop is the phase picked up by a heavy external color source transported around a closed curve. In a gauge theory with connection $A=A_\mu dx^\mu$, the Wilson loop in representation $R$ is

$$
W_R(C)=\frac{1}{\dim R}\operatorname{tr}_R\,\mathcal P
\exp\left(-i\oint_C A\right),
$$

using the convention that $D=d+iA$ and $A=A^aT^a$ with Hermitian generators. The minus sign is the parallel-transport sign for this covariant derivative convention.

For a large rectangular Euclidean loop $C_{R,T}$ of spatial size $R$ and Euclidean time extent $T$, the expectation value behaves as

$$
\langle W(C_{R,T})\rangle\sim e^{-T V(R)}
$$

when $T\gg R$. Thus the Wilson loop extracts the static potential $V(R)$ between a heavy probe charge and anticharge.

The **area law** is

$$
\langle W(C)\rangle\sim e^{-\sigma\,\operatorname{Area}(C)}
$$

for large loops, where $\operatorname{Area}(C)$ means the minimal spanning area and $\sigma$ is the string tension. For a rectangle,

$$
\operatorname{Area}(C_{R,T})=RT,
$$

so

$$
V(R)\sim \sigma R.
$$

This is the Wilson-loop diagnostic of confinement: separating two heavy external charges costs energy growing linearly with distance.

<figure class="doc-figure" style="--figure-width: 42rem;">

![A rectangular Wilson loop whose expectation value is controlled by the minimal surface spanning the loop.](/figures/symmetry-anomalies-topology/wilson-loop-area-law.svg)

<figcaption>

A large rectangular Wilson loop $C_{R,T}$ measures the static potential $V(R)$. An area law $\langle W(C_{R,T})\rangle\sim e^{-\sigma RT}$ implies a linearly rising potential $V(R)\sim\sigma R$.

</figcaption>
</figure>

This page is a preview calculation. It does not prove confinement in continuum Yang–Mills theory. It explains the logic of the diagnostic, how the area law appears in strong-coupling lattice gauge theory, and how the same statement is rephrased using one-form symmetry.

## Prerequisites

You should know Wilson lines, gauge-invariant line operators, center symmetry, and the idea of one-form symmetry. The relevant earlier pages are the Wilson-line and line-operator pages in the Defects and Extended Operators chapter, and the Center Symmetry and Generalized Symmetry Breaking pages in the Higher-Form and Generalized Symmetries chapter.

We use mostly-minus Lorentzian conventions elsewhere, but the rectangular-loop extraction is cleanest in Euclidean time. Euclidean time is denoted by $\tau$, and $T$ is the Euclidean time extent of the rectangle.

## Core idea

A heavy external charge is not a dynamical particle in the theory. It is a probe. If the probe transforms in representation $R$ of the gauge group, its worldline couples to the gauge field through a Wilson line,

$$
W_R(\gamma)=\mathcal P\exp\left(-i\int_\gamma A_R\right).
$$

A closed worldline gives a gauge-invariant Wilson loop after taking the trace. A rectangular loop creates a heavy probe and antiprobe, propagates them for Euclidean time $T$, and then annihilates them.

The path integral with the rectangular Wilson loop inserted has a spectral decomposition,

$$
\langle W(C_{R,T})\rangle
=\sum_n c_n(R)e^{-T E_n(R)}.
$$

At large $T$, the lowest-energy state dominates:

$$
\langle W(C_{R,T})\rangle\sim e^{-T V(R)}.
$$

Here $V(R)$ is the static potential between the heavy sources, up to an additive self-energy constant. The large-$R$ behavior of $V(R)$ distinguishes phases.

| Wilson-loop behavior | Static potential | Interpretation |
|---|---|---|
| $e^{-\sigma RT}$ | $V(R)\sim\sigma R$ | confinement of the probe charge |
| $e^{-\mu(2R+2T)}$ | $V(R)$ saturates after self-energy subtraction | screening or Higgs-like behavior |
| $e^{-T\,c/R}$ times perimeter terms | $V(R)\sim c/R$ | Coulomb behavior |

The area law is therefore not a decorative asymptotic formula. It is a statement about the energy cost of separating external charges.

## Setup and conventions

Let $G$ be a compact gauge group, and let $R$ be a representation of $G$. We normalize the Wilson loop by

$$
W_R(C)=\frac{1}{\dim R}\operatorname{tr}_R\,\mathcal P
\exp\left(-i\oint_C A\right).
$$

The normalization gives $W_R(C)=1$ when $A=0$. In a nonabelian theory the path-ordering symbol $\mathcal P$ is essential because matrices $A_\mu(x)$ at different points need not commute.

The expectation value is computed in the Euclidean path integral,

$$
\langle W_R(C)\rangle
=
\frac{1}{Z}\int \mathcal D A\,e^{-S_E[A]}W_R(C).
$$

For a rectangular loop,

$$
C_{R,T}:\qquad 0\le x\le R,\qquad 0\le \tau\le T.
$$

The static potential is extracted as

$$
V_R(R_{\rm sep})
=
-\lim_{T\to\infty}\frac{1}{T}\log\langle W_R(C_{R_{\rm sep},T})\rangle,
$$

after subtracting perimeter divergences if necessary.

:::note[Source note: perimeter divergences]
Continuum Wilson loops have short-distance divergences associated with the length of the curve and with cusps. The area-law statement concerns the large-loop behavior after the usual ultraviolet perimeter/cusp factors are separated from the infrared physics.
:::

## From area law to a linear potential

Assume that for large rectangles,

$$
\langle W_R(C_{R,T})\rangle
\sim \exp[-\sigma_R RT-\mu_R(2R+2T)+\cdots].
$$

The first term is the area term. The second term is a perimeter term, often dominated by ultraviolet self-energy. Then

$$
-\frac{1}{T}\log\langle W_R(C_{R,T})\rangle
=
\sigma_R R+2\mu_R+\frac{2\mu_R R}{T}+\cdots.
$$

Taking $T\to\infty$ gives

$$
V_R(R)=\sigma_R R+2\mu_R+\cdots.
$$

The additive constant $2\mu_R$ is not the confining force; it is the self-energy of the heavy sources. The physical long-distance force is

$$
F(R)=-\frac{dV}{dR}\sim -\sigma_R.
$$

The string tension $\sigma_R$ is the energy per unit length of the flux tube connecting the probes.

## Strong-coupling lattice intuition

The cleanest elementary derivation of an area law appears in strong-coupling lattice gauge theory.

On a hypercubic lattice, link variables $U_\ell\in G$ live on links, and plaquette variables are products around elementary squares,

$$
U_p=\prod_{\ell\in\partial p}U_\ell.
$$

For Wilson’s lattice action,

$$
S=-\frac{\beta}{N}\sum_p\operatorname{Re}\operatorname{tr}U_p
$$

for $G=SU(N)$, the strong-coupling regime is small $\beta$. Expanding the Boltzmann factor in powers of $\beta$, the expectation value of a Wilson loop is nonzero only when enough plaquette factors are inserted to soak up the group integrals on every link of the loop.

The leading nonzero contribution is a tiling of the minimal surface bounded by the loop. If the loop encloses $A_{\rm lat}$ plaquettes, the leading behavior is schematically

$$
\langle W(C)\rangle\propto \left(\text{constant}\times\beta\right)^{A_{\rm lat}}
=
\exp[-\sigma a^2 A_{\rm lat}],
$$

where $a$ is the lattice spacing. Since

$$
a^2A_{\rm lat}\approx \operatorname{Area}(C),
$$

this is an area law.

This derivation is not a continuum proof of confinement. Strong-coupling lattice gauge theory gives a controlled phase of the lattice theory; reaching the continuum limit requires taking $\beta$ large for asymptotically free nonabelian gauge theory. The strong-coupling derivation is nevertheless invaluable because it shows exactly why a flux-sheet picture produces an area law.

## Flux-tube interpretation

A Wilson loop insertion creates electric flux sourced by the external probes. In a confining phase, the flux does not spread out like the Coulomb electric field. It is squeezed into a tube. If the tube has tension $\sigma$, a pair of probes separated by $R$ costs energy approximately

$$
E(R)=\sigma R.
$$

The Euclidean worldsheet swept by this tube during time $T$ has area $RT$, hence the path-integral weight

$$
e^{-\sigma RT}.
$$

This is the physical picture behind the area law.

The same picture explains why a Wilson loop is more useful than a local operator for diagnosing confinement. Confinement is not merely a statement about a local condensate. It is a statement about the long-distance energy cost of an extended electric flux configuration.

## Screening and string breaking

The Wilson-loop area law diagnoses confinement of **external probe charges**. If the theory contains dynamical matter in representation $R$, then a probe charge in $R$ can be screened by pair creation. The flux tube can break.

For example, in QCD with dynamical fundamental quarks, a fundamental external quark and antiquark can be screened by creating light quark-antiquark pairs. At very large separation, the static potential no longer grows forever; it saturates into two heavy-light mesons. The fundamental Wilson loop then fails to show an asymptotic area law in the strict infinite-distance limit.

This is not a contradiction. It means that “confinement” needs sharper language once dynamical matter is present. In pure Yang–Mills theory, the center one-form symmetry gives that language. In theories with fundamental matter, that symmetry is explicitly broken.

:::caution[Area law is representation-dependent]
In a nonabelian gauge theory, Wilson loops with zero $N$-ality can be screened by gluons even in pure Yang–Mills theory. The sharp center-symmetry diagnostic uses representations charged under the center, such as the fundamental representation of $SU(N)$.
:::

## One-form symmetry formulation

In pure $SU(N)$ Yang–Mills theory, Wilson lines are charged under a $\mathbb Z_N$ center one-form symmetry. A center-symmetry surface operator $U_z(\Sigma)$ acts on a Wilson loop $W_R(C)$ by a linking phase,

$$
U_z(\Sigma) W_R(C)
=
z^{\,\ell(\Sigma,C)\,k_R}
W_R(C) U_z(\Sigma),
$$

where $z\in\mathbb Z_N$, $\ell(\Sigma,C)$ is the linking number, and $k_R$ is the $N$-ality of $R$.

In this language:

- an area law for center-charged Wilson loops is the unbroken realization of the electric one-form center symmetry;
- a perimeter law is the spontaneously broken realization of the one-form symmetry;
- dynamical fundamental matter explicitly breaks the center one-form symmetry because fundamental Wilson lines can end on dynamical particles.

This is the modern version of the old confinement diagnostic. It does not replace the Wilson-loop calculation; it explains why the Wilson loop is the right object.

## Finite temperature and Polyakov loops

At finite temperature, Euclidean time is a circle of circumference

$$
\beta_{\rm therm}=\frac{1}{T_{\rm phys}}.
$$

The Polyakov loop is a Wilson line wrapping the Euclidean thermal circle:

$$
P_R(\mathbf x)=\frac{1}{\dim R}\operatorname{tr}_R\,\mathcal P
\exp\left(-i\int_0^{\beta_{\rm therm}} A_\tau(\tau,\mathbf x)d\tau\right).
$$

In pure Yang–Mills theory, the expectation value $\langle P_R\rangle$ is an order parameter for center symmetry at finite temperature. Roughly,

$$
\langle P_R\rangle=0
$$

signals an infinite free energy for an isolated center-charged probe, while

$$
\langle P_R\rangle\neq0
$$

signals deconfinement in the center-symmetry sense.

The zero-temperature rectangular Wilson loop and the finite-temperature Polyakov loop are related diagnostics, but they are not the same observable.

## Common pitfalls

**Calling every area law “proof of confinement.”** A lattice strong-coupling area law is a controlled calculation in that regime, not a proof of continuum Yang–Mills confinement.

**Ignoring perimeter and cusp divergences.** Continuum Wilson loops contain ultraviolet factors depending on length and cusps. The long-distance area coefficient is the confinement diagnostic.

**Forgetting representation dependence.** A Wilson loop in a representation screenable by dynamical fields or by gluons may not diagnose the same long-distance physics as a center-charged Wilson loop.

**Confusing string tension with fundamental-string tension.** The flux tube in a confining gauge theory may have an effective string description at long distances, but it is not automatically a fundamental string.

**Using the Wilson loop as the only definition of confinement.** With dynamical matter, Higgs phases, higher-form symmetry breaking, and gauge-group global forms, confinement has several inequivalent diagnostics.

## Relations to other pages

The Wilson-line page defines the operator. The Center Symmetry page explains why $N$-ality matters. The Generalized Symmetry Breaking page explains why area and perimeter laws are order parameters for higher-form symmetry realization. The One-Form Symmetry in Maxwell Theory page gives the Coulomb-phase comparison, where Wilson and ’t Hooft lines have long-range interactions rather than a confining area law.

## Research status

The Wilson-loop area law is a standard, settled diagnostic in pure gauge theory and lattice gauge theory. The hard problem is proving the expected continuum area law and mass gap for four-dimensional pure Yang–Mills theory.

The modern generalized-symmetry refinement is also settled at the conceptual level: area and perimeter laws are statements about how one-form symmetries are realized. In theories with dynamical matter, quotient gauge groups, boundaries, or mixed anomalies, identifying the correct genuine line operators is part of the physics.

## Exercises

### Exercise 1: Extracting the potential

Suppose

$$
\langle W(C_{R,T})\rangle=A(R)e^{-T V(R)}+\text{excited terms}
$$

with excited terms suppressed by $e^{-T\Delta E}$. Show that

$$
V(R)=-\lim_{T\to\infty}\frac{1}{T}\log\langle W(C_{R,T})\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Write

$$
\langle W(C_{R,T})\rangle
=
A(R)e^{-T V(R)}
\left[1+O(e^{-T\Delta E})\right].
$$

Then

$$
-\frac{1}{T}\log\langle W(C_{R,T})\rangle
=
V(R)-\frac{1}{T}\log A(R)
-\frac{1}{T}\log\left[1+O(e^{-T\Delta E})\right].
$$

Taking $T\to\infty$ removes the last two terms and gives $V(R)$.

</details>

### Exercise 2: Area law implies linear confinement

Assume

$$
\langle W(C_{R,T})\rangle\sim e^{-\sigma RT-\mu(2R+2T)}.
$$

Use the previous result to find the large-$R$ static potential.

<details><summary><strong>Solution</strong></summary>

Compute

$$
-\frac{1}{T}\log\langle W(C_{R,T})\rangle
=
\sigma R+2\mu+\frac{2\mu R}{T}.
$$

Taking $T\to\infty$ gives

$$
V(R)=\sigma R+2\mu.
$$

The constant $2\mu$ is a self-energy contribution. The force at large $R$ is controlled by the string tension $\sigma$.

</details>

### Exercise 3: Perimeter law

If

$$
\langle W(C_{R,T})\rangle\sim e^{-\mu(2R+2T)}
$$

with no area term, what does the rectangular loop imply about $V(R)$ after subtracting self-energies?

<details><summary><strong>Solution</strong></summary>

The potential extracted from the loop is

$$
V(R)=2\mu
$$

before self-energy subtraction. After subtracting the heavy-probe self-energies, there is no linearly growing term. This is a perimeter-law behavior, compatible with screening or a Higgs-like phase rather than confinement of the probe charge.

</details>

### Exercise 4: N-ality

Explain why in pure $SU(N)$ Yang–Mills theory the fundamental Wilson loop is charged under the $\mathbb Z_N$ one-form center symmetry, while an adjoint Wilson loop is not.

<details><summary><strong>Solution</strong></summary>

The center of $SU(N)$ consists of elements $z=e^{2\pi i k/N}1$. In the fundamental representation, $z$ acts as multiplication by $z$, so the fundamental has nonzero $N$-ality. In the adjoint representation, center elements act trivially because the adjoint action is conjugation,

$$
X\mapsto zXz^{-1}=X.
$$

Thus adjoint Wilson loops are neutral under the center one-form symmetry, while fundamental Wilson loops are charged.

</details>

## References

- M. Srednicki, *Quantum Field Theory*, §§82–83 for Wilson loops, lattice theory, confinement, and chiral symmetry breaking.
- A. M. Polyakov, *Gauge Fields and Strings*, Chs. 3, 5, and 7 for strong-coupling expansion, confinement analogies, and loop dynamics.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the one-form symmetry interpretation of Wilson-loop area and perimeter laws.
- A. Altland and B. Simons, *Condensed Matter Field Theory*, Chs. 8 and 10 for topological field theory and gauge-theory perspectives.
- M. Creutz, *Quarks, Gluons and Lattices*, for classic lattice strong-coupling intuition.

## Version history

- 2026-06-23: Polished draft. Added rectangular-loop potential extraction, strong-coupling area-law sketch, center one-form symmetry interpretation, screening caveats, finite-temperature Polyakov-loop preview, and exercises.
