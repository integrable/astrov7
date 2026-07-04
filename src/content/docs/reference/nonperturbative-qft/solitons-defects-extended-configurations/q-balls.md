---
title: "Q-Balls"
description: "Explains Q-balls as nontopological solitons stabilized by conserved global charge, including the rotating ansatz, existence condition, thin-wall estimate, and stability caveats."
sidebar:
  label: "Q-Balls"
  order: 7
level: Graduate
status: "Polished draft"
source: "Coleman, Q-balls; Lee and Pang; Kusenko; Manton and Sutcliffe."
topics:
  - Q-balls
  - nontopological solitons
  - conserved charge
  - scalar field theory
  - semiclassical solitons
  - thin-wall approximation
canonicalTopics:
  - nonperturbative-qft
  - solitons
  - q-balls
  - nontopological-solitons
researchStatus:
  established:
    - "Classical Q-balls are standard nontopological solitons in scalar theories with a conserved global charge and an attractive enough potential."
  active:
    - "Gauged Q-balls, multifield Q-balls, supersymmetric Q-balls, cosmological formation, quantum corrections, and decay channels remain active and model-dependent."
---

## Summary

A **Q-ball** is a nontopological soliton. Unlike a kink, vortex, monopole, or Skyrmion, it is not protected by a winding number or homotopy class. Its stability comes from an ordinary conserved Noether charge $Q$.

The simplest setup is a complex scalar field with a global $U(1)$ symmetry. Write

$$
\Phi(x)=\frac{1}{\sqrt2}f(r)e^{i\omega t},
$$

where $f(r)$ is localized and $\omega$ is a constant frequency. The configuration is not static as a field, but $U(1)$-invariant observables such as the energy density and charge density are time-independent. Its charge is

$$
Q=\omega\int d^d x\,f^2(r),
$$

and its energy is

$$
E
=
\int d^d x\,
\left[
\frac12(\nabla f)^2+\frac12\omega^2 f^2+U(f)
\right]
$$

in the normalization used on this page.

The basic stability test is energetic:

$$
E(Q)<mQ,
$$

where $m$ is the mass of the elementary scalar quantum carrying one unit of charge. If this inequality holds and the $U(1)$ charge is exactly conserved, the lump cannot decay into $Q$ free scalar particles.

A standard existence condition is that the potential be sufficiently attractive:

$$
\min_{f>0}\frac{2U(f)}{f^2}<m^2,
$$

where $U(f)=\frac12m^2 f^2+O(f^3)$ near the origin. This says that a finite-density region of field can store charge at lower energy per charge than a gas of free quanta.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A Q-ball existence window and a localized scalar profile with rotating internal phase.](/figures/nonperturbative-qft/q-ball-charge-stabilization.svg)

<figcaption>

A Q-ball exists when the potential is attractive enough that $\omega_0^2=\min_{f>0}2U(f)/f^2$ lies below $m^2$, allowing a frequency window $\omega_0^2<\omega^2<m^2$. The radial amplitude $f(r)$ is localized, while the phase $e^{i\omega t}$ stores the Noether charge.

</figcaption>
</figure>

The slogan is useful but must be read carefully: **a Q-ball is a lump of charge whose energy per charge is lower than that of free particles.** The phrase “nontopological” does not mean “not nonperturbative.” It means the soliton is stabilized dynamically and by charge conservation, not by topology.

## Prerequisites

You should know [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/), [Kinks](/nonperturbative-qft/solitons-defects-extended-configurations/kinks/), and [Skyrmions](/nonperturbative-qft/solitons-defects-extended-configurations/skyrmions/). You should also know Noether's theorem for a global $U(1)$ symmetry and the basic variational idea of minimizing energy subject to a constraint.

The useful contrast is:

| Soliton type | Stabilizing label | Boundary behavior |
|---|---|---|
| Kink | Topological sector | Different vacua at $x=-\infty$ and $x=+\infty$ |
| Vortex | Winding number or flux | Phase winds around $S^1_\infty$ |
| Monopole | Magnetic/topological charge | Map $S^2_\infty\to\mathcal M_{\rm vac}$ |
| Skyrmion | Degree of compactified-space map | Map $S^d\to\mathcal M$ |
| Q-ball | Noether charge $Q$ | Field returns to the same vacuum at infinity |

## Core idea

A Q-ball answers a different question from a topological soliton. For a topological soliton, we ask:

> Can this field configuration be continuously deformed to the vacuum without leaving the finite-energy configuration space?

For a Q-ball, the answer is usually yes if we ignore charge. The field goes to the vacuum at infinity and carries no winding. Instead we ask:

> Among all field configurations with fixed conserved charge $Q$, is the lowest-energy configuration a localized lump rather than a cloud of free particles?

If the answer is yes, a Q-ball exists.

This makes Q-balls closer in spirit to bound states than to vortices or monopoles, but they are still solitons in the semiclassical sense: for large charge, the lump can be treated as a classical field configuration with a collective profile, radius, and fluctuation spectrum.

The conserved charge does two jobs:

1. It prevents the configuration from simply disappearing into the vacuum.
2. It can energetically favor a coherent lump over many separated quanta.

The second point is dynamical. It depends on the scalar potential.

## Setup and conventions

Take a complex scalar field $\Phi$ in $D=d+1$ spacetime dimensions, with Lagrangian

$$
\mathcal L
=
\partial_\mu\Phi^*\partial^\mu\Phi-U(|\Phi|),
$$

and global symmetry

$$
\Phi\mapsto e^{i\alpha}\Phi.
$$

For formulas it is convenient to write

$$
\Phi=\frac{1}{\sqrt2}f e^{i\theta},
$$

and to define $U(f)$ as the potential evaluated on amplitude $f$. Near the vacuum $f=0$,

$$
U(f)=\frac12m^2f^2+O(f^3),
$$

so $m$ is the mass of the elementary scalar quantum.

The Noether current is

$$
j^\mu
=-i\left(\Phi^*\partial^\mu\Phi-\Phi\partial^\mu\Phi^*\right).
$$

For the rotating ansatz

$$
\Phi(t,\mathbf x)=\frac{1}{\sqrt2}f(\mathbf x)e^{i\omega t},
$$

one gets

$$
Q=\int d^d x\,j^0
=\omega\int d^d x\,f^2(\mathbf x).
$$

The energy is

$$
E
=
\int d^d x\,
\left[
\frac12(\dot f^2+f^2\dot\theta^2)
+\frac12(\nabla f)^2
+\frac12f^2(\nabla\theta)^2
+U(f)
\right].
$$

For the Q-ball ansatz, $f$ is time-independent and $\theta=\omega t$, so

$$
E
=
\int d^d x\,
\left[
\frac12(\nabla f)^2+\frac12\omega^2f^2+U(f)
\right].
$$

We mostly consider spherically symmetric profiles,

$$
f(\mathbf x)=f(r),
\qquad
r=|\mathbf x|,
$$

with

$$
f'(0)=0,
\qquad
f(\infty)=0.
$$

The second condition is the key nontopological feature: the field approaches the same vacuum at infinity.

## Fixed-charge minimization

A Q-ball is found by minimizing energy at fixed $Q$. Introduce a Lagrange multiplier $\omega$ and vary

$$
E_\omega
=
E-\omega Q.
$$

Equivalently, after completing the square in time derivatives, the minimizing time dependence is

$$
\Phi(t,\mathbf x)=e^{i\omega t}\Phi_0(\mathbf x).
$$

For the radial ansatz, the profile equation is

$$
f''(r)+\frac{d-1}{r}f'(r)
=
\frac{dU}{df}-\omega^2 f.
$$

This is often interpreted as a bounce equation in an effective potential

$$
U_\omega(f)=U(f)-\frac12\omega^2f^2.
$$

The radial equation can be written as

$$
f''+\frac{d-1}{r}f'=\frac{dU_\omega}{df}.
$$

The mechanical analogy is useful. Think of $r$ as time and $f(r)$ as the position of a particle moving in the inverted potential $-U_\omega(f)$ with friction $(d-1)f'/r$. The Q-ball profile begins near some nonzero $f(0)$ and rolls to $f=0$ as $r\to\infty$.

For this to happen, $U_\omega(f)$ must be negative somewhere. Since

$$
U_\omega(f)=U(f)-\frac12\omega^2f^2,
$$

this requires

$$
\omega^2>\min_{f>0}\frac{2U(f)}{f^2}.
$$

At the same time, localization at infinity requires $f=0$ to be stable in the linearized tail. Near $f=0$,

$$
U_\omega(f)\simeq \frac12(m^2-\omega^2)f^2,
$$

so one needs

$$
\omega^2<m^2.
$$

Therefore a Q-ball frequency lies in the window

$$
\omega_0<\omega<m,
\qquad
\omega_0^2\equiv \min_{f>0}\frac{2U(f)}{f^2}.
$$

This window exists only if

$$
\omega_0^2<m^2.
$$

That is the standard Q-ball existence condition.

## Thin-wall estimate

The thin-wall limit is the cleanest way to see the physics. It applies when the charge is large and the Q-ball radius is large compared with the wall thickness. Approximate

$$
f(r)\simeq
\begin{cases}
 f_0, & r<R,\\
 0, & r>R,
\end{cases}
$$

and ignore the surface term at first. If $V$ is the volume of the ball,

$$
Q\simeq \omega f_0^2 V.
$$

The energy is approximately

$$
E
\simeq
\frac12\omega^2f_0^2V+U(f_0)V.
$$

Eliminating $\omega$ in favor of $Q$ gives

$$
E(V,f_0)
\simeq
\frac{Q^2}{2f_0^2V}+U(f_0)V.
$$

At fixed $Q$ and $f_0$, minimizing over $V$ gives

$$
V_\star
=
\frac{Q}{\sqrt{2U(f_0)f_0^2}},
$$

and

$$
E
\simeq
Q\sqrt{\frac{2U(f_0)}{f_0^2}}.
$$

Thus the energy per charge is minimized by choosing $f_0$ to minimize

$$
\frac{2U(f_0)}{f_0^2}.
$$

If this minimum is less than $m^2$, then

$$
\frac{E}{Q}<m,
$$

so the Q-ball is stable against decay into free scalar particles, at least in this idealized large-$Q$ approximation.

The surface term raises the energy by an amount scaling like the area. In three spatial dimensions,

$$
E(Q)
\simeq
\omega_0 Q+\sigma R^2+\cdots,
\qquad
R\sim Q^{1/3}
$$

in the thin-wall regime. The leading term is proportional to $Q$, while the wall correction is subleading at large $Q$.

## Thick-wall regime

As $\omega\to m$ from below, the profile becomes small and diffuse. This is the **thick-wall** regime. The Q-ball is no longer well approximated by a constant-density interior plus a sharp surface. Instead the whole object is a smooth, low-amplitude lump.

Whether small-$Q$ Q-balls exist and are stable depends sensitively on the potential. Large-$Q$ existence is often controlled by the minimum of $2U(f)/f^2$, but small Q-balls care about detailed nonlinearities, gradient energy, quantum corrections, and available decay channels.

This is a common pattern in soliton physics. A large charge or large winding number may create a semiclassical control parameter. At small charge, the same words may describe a much less controlled object.

## Stability conditions

There are several distinct meanings of stability. Keeping them separate avoids a lot of confusion.

**Stability against free-particle emission.** If the elementary scalar quanta have mass $m$, then a Q-ball with charge $Q$ cannot decay into $Q$ free quanta when

$$
E(Q)<mQ.
$$

This is the most basic condition.

**Stability against fission.** A large Q-ball could split into two smaller Q-balls of charges $Q_1$ and $Q_2$. Stability against such fission requires

$$
E(Q_1+Q_2)<E(Q_1)+E(Q_2)
$$

for relevant charge partitions. In a smooth approximation this is related to the concavity of $E(Q)$.

**Classical linear stability.** One should also check the fluctuation spectrum around the rotating solution. The time-dependent background mixes particle and antiparticle fluctuations, and the stability condition is not just the positivity of a static Hessian.

**Stability against other sectors.** If the scalar has interactions that violate the global charge, or if it couples to lighter charged particles, the Q-ball may decay. Even when charge is conserved, it can sometimes emit light fermions or convert charge into other sectors. Then the Q-ball is metastable rather than absolutely stable.

The safest statement is: a Q-ball is stabilized by an exact or sufficiently long-lived conserved charge, provided its fixed-charge energy is lower than the competing states with the same charge.

## Gauged Q-balls

If the $U(1)$ symmetry is gauged rather than global, the story changes. The conserved charge becomes electric charge, and the lump carries a gauge field. The Coulomb energy grows with charge and can prevent arbitrarily large gauged Q-balls from existing.

Schematic comparison:

| Global Q-ball | Gauged Q-ball |
|---|---|
| Global $U(1)$ charge | Electric charge |
| No Coulomb repulsion | Coulomb energy matters |
| Large-$Q$ thin-wall limit often possible | Large charge can be obstructed |
| Phase rotation is physical through Noether charge | Gauge choice can move phase into $A_0$ |

This is a useful reminder that “same ansatz plus gauge field” is not a small technical modification. Gauging changes the energetics and sometimes the existence window.

## Why Q-balls are nonperturbative

Q-balls are not invisible because of an $e^{-1/g^2}$ factor in the same way instantons are. Their nonperturbative nature is more structural: they are coherent classical configurations with charge of order many quanta. Perturbation theory around the vacuum describes scattering of a few elementary particles; it does not naturally reorganize itself into the lowest-energy finite-density lump at fixed $Q$.

For large charge, a Q-ball can be treated semiclassically. The field amplitude and radius are collective quantities. The expansion is not an ordinary weak-field expansion around $\Phi=0$ but an expansion around a nontrivial, time-dependent saddle at fixed charge.

In that sense, Q-balls sit between solitons and many-body bound states. They are classical field lumps, but their protection is Noether charge rather than topology.

## Common pitfalls

**Thinking nontopological means unstable.** Nontopological means the configuration is not protected by a homotopy class. It can still be stable if charge conservation and energetics forbid decay.

**Forgetting the time-dependent phase.** A Q-ball is stationary, not usually static. The field rotates in internal $U(1)$ space as $e^{i\omega t}$, while the energy density and charge density remain time-independent.

**Using the existence condition without fixing normalization.** The formula

$$
\min_{f>0}\frac{2U(f)}{f^2}<m^2
$$

assumes $\Phi=f e^{i\theta}/\sqrt2$ and $U(f)\simeq \frac12m^2f^2$ near $f=0$. With a different definition of the amplitude, factors of $2$ move around.

**Assuming all Q-balls are absolutely stable.** Stability can fail because of fission, quantum corrections, charge-violating interactions, lighter charged particles, gauge-field repulsion, or coupling to fermions.

**Calling every charged lump a Q-ball.** A Q-ball is the energy-minimizing or at least locally stable localized configuration at fixed charge. A generic wave packet carrying charge is not a soliton.

## Relations to other pages

- [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/) explains the boundary condition $f(\infty)=0$ and why Q-balls have no topological winding at infinity.
- [Skyrmions](/nonperturbative-qft/solitons-defects-extended-configurations/skyrmions/) gives the opposite paradigm: stability from compactified-space topology rather than Noether charge.
- [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/) explains how classical soliton backgrounds become quantum states.
- [One-Loop Determinants Around Saddles](/nonperturbative-qft/semiclassical-methods/one-loop-determinants-around-saddles/) is the natural next step for quantum corrections to Q-ball energies.
- [False-Vacuum Decay](/nonperturbative-qft/semiclassical-methods/false-vacuum-decay/) uses similar Euclidean bounce intuition, but the Q-ball profile is a fixed-charge stationary saddle rather than a tunneling bounce.
- Later finite-density and real-time pages revisit the broad lesson: fixed charge, finite density, and real-time phases can reorganize the semiclassical expansion.

## Research status

**Established.** Classical global Q-balls in scalar theories with a conserved $U(1)$ charge are standard nontopological solitons. The rotating ansatz, frequency window, thin-wall limit, and energy-per-charge criterion are textbook material.

**Model-dependent.** Existence and stability depend on the scalar potential, number of fields, charge assignments, dimensionality, and whether the symmetry is global or gauged. Small-Q behavior is especially sensitive to details.

**Active.** Q-balls continue to appear in studies of supersymmetric flat directions, Affleck–Dine baryogenesis, dark-matter candidates, gauged solitons, boson-star-like objects, finite-density phases, and quantum corrections to soliton stability. In these applications, the classical Q-ball page is only the starting point; the hard part is the model-specific spectrum and decay physics.

## Exercises

### Exercise 1: Derive the rotating ansatz

For a complex scalar with global $U(1)$ charge

$$
Q=-i\int d^d x\,(\Phi^*\dot\Phi-\dot\Phi^*\Phi),
$$

minimize energy at fixed $Q$ using a Lagrange multiplier $\omega$. Show that the minimizing time dependence has the form

$$
\Phi(t,\mathbf x)=e^{i\omega t}\Phi_0(\mathbf x).
$$

<details>
<summary><strong>Solution</strong></summary>

Consider

$$
E_\omega=E-\omega Q.
$$

The time-derivative part can be completed into a square:

$$
|\dot\Phi|^2
+i\omega(\Phi^*\dot\Phi-\dot\Phi^*\Phi)
=
|\dot\Phi-i\omega\Phi|^2-\omega^2|\Phi|^2.
$$

For fixed spatial profile, the square is minimized by

$$
\dot\Phi=i\omega\Phi.
$$

Therefore

$$
\Phi(t,\mathbf x)=e^{i\omega t}\Phi_0(\mathbf x).
$$

The multiplier $\omega$ becomes the internal rotation frequency.

</details>

### Exercise 2: Frequency window

Using

$$
U_\omega(f)=U(f)-\frac12\omega^2f^2,
$$

explain why a localized Q-ball requires

$$
\omega_0<\omega<m,
\qquad
\omega_0^2=\min_{f>0}\frac{2U(f)}{f^2}.
$$

<details>
<summary><strong>Solution</strong></summary>

For the profile to have a nonzero interior, the effective potential must be negative somewhere:

$$
U_\omega(f)<0
$$

for some $f>0$. This means

$$
U(f)-\frac12\omega^2f^2<0,
$$

or

$$
\omega^2>\frac{2U(f)}{f^2}
$$

for some $f$. Therefore

$$
\omega^2>\omega_0^2,
\qquad
\omega_0^2=\min_{f>0}\frac{2U(f)}{f^2}.
$$

At large $r$, the profile is small, and

$$
U_\omega(f)\simeq\frac12(m^2-\omega^2)f^2.
$$

A localized exponentially decaying tail requires $m^2-\omega^2>0$, so $\omega<m$. Combining the two conditions gives

$$
\omega_0<\omega<m.
$$

</details>

### Exercise 3: Thin-wall energy per charge

In the thin-wall approximation, take $f=f_0$ in a volume $V$ and $f=0$ outside. Ignore surface energy. Show that

$$
E\simeq Q\sqrt{\frac{2U(f_0)}{f_0^2}}.
$$

<details>
<summary><strong>Solution</strong></summary>

Inside the ball,

$$
Q=\omega f_0^2 V,
$$

and

$$
E=\frac12\omega^2f_0^2V+U(f_0)V.
$$

Eliminate $\omega$:

$$
\omega=\frac{Q}{f_0^2V}.
$$

Then

$$
E(V)=\frac{Q^2}{2f_0^2V}+U(f_0)V.
$$

Minimize with respect to $V$:

$$
-\frac{Q^2}{2f_0^2V^2}+U(f_0)=0,
$$

so

$$
V_\star=\frac{Q}{\sqrt{2U(f_0)f_0^2}}.
$$

Substituting back gives

$$
E=Q\sqrt{\frac{2U(f_0)}{f_0^2}}.
$$

</details>

### Exercise 4: Why a Q-ball is not topologically protected

Suppose $f(r)$ is a Q-ball profile with $f(\infty)=0$. Explain why this boundary condition does not define a nontrivial map from spatial infinity to a vacuum manifold.

<details>
<summary><strong>Solution</strong></summary>

At spatial infinity the field approaches the same vacuum value in every direction:

$$
\Phi(\infty)=0.
$$

Thus the map from the sphere at infinity to the vacuum manifold is constant. There is no winding around $S^1_\infty$, no map $S^2_\infty\to\mathcal M_{\rm vac}$ with nonzero degree, and no compactified-space topological charge. If charge conservation is ignored, the lump can be continuously deformed toward the vacuum by reducing the amplitude. Its stability comes from fixed $Q$, not topology.

</details>

## References

- S. Coleman, “Q-Balls,” *Nuclear Physics B* **262** (1985), for the original existence theorem and basic properties of Q-balls.
- T. D. Lee and Y. Pang, “Nontopological Solitons,” *Physics Reports* **221** (1992), for a classic review of nontopological solitons.
- A. Kusenko, “Small Q-balls,” *Physics Letters B* **404** (1997), and related work on Q-balls in supersymmetric theories.
- N. Manton and P. Sutcliffe, *Topological Solitons*, for general soliton methods and contrasts between topological and nontopological stabilization.
- A. Kusenko and M. Shaposhnikov, “Supersymmetric Q-balls as dark matter,” *Physics Letters B* **418** (1998), for cosmological applications in supersymmetric models.
- S. R. Coleman, *Aspects of Symmetry*, for the broader semiclassical style and nonperturbative field-configuration viewpoint, even though Q-balls themselves are in the separate Coleman paper.

## Version history

- **2026-06-26:** Initial polished page, added after Skyrmions in the Solitons, Defects, and Extended Field Configurations chapter.
