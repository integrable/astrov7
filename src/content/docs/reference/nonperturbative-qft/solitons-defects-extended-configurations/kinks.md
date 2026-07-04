---
title: "Kinks"
description: "Kinks are finite-energy solitons in one spatial dimension that interpolate between disconnected vacua."
sidebar:
  label: "Kinks"
  order: 2
level: Graduate
status: "Polished draft"
source: "Coleman, Classical Lumps and Their Quantum Descendants; Shifman, ch. 2; Zee, ch. V.6; Srednicki, ch. 92; Rajaraman."
topics:
  - kinks
  - solitons
  - domain walls
  - finite-energy boundary conditions
  - topological sectors
  - zero modes
  - semiclassical quantization
canonicalTopics:
  - nonperturbative-qft
  - kinks
  - solitons
  - topological-defects
  - finite-energy-boundary-conditions
researchStatus:
  established:
    - "Classical kink solutions, their topological sectors, translational zero modes, and semiclassical quantization are textbook-standard in one-dimensional scalar field theory."
  active:
    - "Kinks remain useful in active work on defects, fermion zero modes, supersymmetric solitons, integrable models, noninvertible symmetries, and real-time dynamics in low dimensions."
---

## Summary

A **kink** is a static finite-energy field configuration in one spatial dimension that interpolates between two different vacua. In the simplest real scalar model,

$$
\mathcal L
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac{\lambda}{4}\left(\phi^2-v^2\right)^2,
\qquad \lambda>0,
$$

the two vacua are $\phi=\pm v$. The kink and antikink are

$$
\phi_K(x;X)=v\tanh\!\left[\frac{m}{2}(x-X)\right],
\qquad
\phi_{\bar K}(x;X)=-v\tanh\!\left[\frac{m}{2}(x-X)\right],
$$

where

$$
m^2=V''(v)=2\lambda v^2.
$$

The parameter $X$ is the kink center. It is not a small fluctuation amplitude; it is a collective coordinate associated with broken translation symmetry.

A kink is the codimension-one defect in its most economical form. In $1+1$ dimensions it has finite total energy and behaves as a particle. In higher dimensions the same profile, extended along extra spatial directions, becomes a domain wall with finite tension but infinite total energy in infinite volume.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A double-well potential and the corresponding kink profile interpolating from minus v to plus v.](/figures/nonperturbative-qft/kink-double-well-profile.svg)

<figcaption>

The $\phi^4$ kink is a finite-energy path through field space. The field begins at one minimum, crosses the barrier region over a width of order $m^{-1}$, and ends at the other minimum. The center $X$ is arbitrary because translations are a symmetry.

</figcaption>
</figure>

The core lesson is that topology enters through boundary conditions. The kink is stable not because the peak of the potential is high, but because a configuration with

$$
\phi(-\infty)=-v,
\qquad
\phi(+\infty)=+v
$$

cannot be continuously deformed into the vacuum configuration while preserving finite energy and the same boundary data.

## Prerequisites

You should know [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/), [Degenerate Vacua](/nonperturbative-qft/vacuum-structure-phases/degenerate-vacua/), [Discrete Vacua](/nonperturbative-qft/vacuum-structure-phases/discrete-vacua/), [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/), and [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/).

It is also useful to have seen ordinary one-dimensional tunneling and the mechanical analogy between static field profiles and particle trajectories in an inverted potential.

## Core idea

Perturbative particles are small oscillations around one vacuum. A kink is a different kind of object: it is a whole field profile connecting one vacuum at the left end of space to another vacuum at the right end.

The finite-energy condition forces

$$
\phi(x)\to \phi_-\in\mathcal M_{\text{vac}}
\quad (x\to-\infty),
\qquad
\phi(x)\to \phi_+\in\mathcal M_{\text{vac}}
\quad (x\to+\infty).
$$

In one spatial dimension, spatial infinity has two components. The boundary is $S^0$, two points. Therefore codimension-one sectors are controlled by which connected component of the vacuum manifold is chosen at each end.

For a double well,

$$
\mathcal M_{\text{vac}}=\{-v,+v\},
$$

so there are four basic boundary sectors:

| Sector | Boundary condition | Interpretation |
|---|---|---|
| $(-,-)$ | $\phi(-\infty)=-v$, $\phi(+\infty)=-v$ | vacuum sector around $-v$ |
| $(+,+)$ | $\phi(-\infty)=+v$, $\phi(+\infty)=+v$ | vacuum sector around $+v$ |
| $(-,+)$ | $\phi(-\infty)=-v$, $\phi(+\infty)=+v$ | kink sector |
| $(+,-)$ | $\phi(-\infty)=+v$, $\phi(+\infty)=-v$ | antikink sector |

A kink is therefore not “a large perturbative particle.” It is a state in a different connected component of finite-energy configuration space.

## Setup and conventions

We use the mostly-minus metric and write the Lagrangian as

$$
\mathcal L
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-V(\phi),
\qquad
V(\phi)=\frac{\lambda}{4}(\phi^2-v^2)^2.
$$

For a static configuration $\phi(x)$ in one spatial dimension,

$$
E[\phi]
=
\int_{-\infty}^{+\infty}dx
\left[\frac12\left(\frac{d\phi}{dx}\right)^2+V(\phi)\right].
$$

We shift the potential so that the vacua have zero energy density:

$$
V(\pm v)=0.
$$

The mass of the elementary scalar excitation around either vacuum is

$$
m^2=V''(\pm v)=2\lambda v^2.
$$

Some books instead write the potential using a mass parameter $\mu$ as $V=\lambda(\phi^2-\mu^2/\lambda)^2/4$. In that notation the physical small-oscillation mass is $m=\sqrt{2}\mu$. This is a small notation swamp; check which $m$ is being used before comparing kink masses.

## Definition

A **kink sector** in a one-dimensional scalar field theory is a connected component of finite-energy configurations with different limiting vacua at $x=-\infty$ and $x=+\infty$.

For a real scalar with isolated vacua, a kink from vacuum $a$ to vacuum $b$ is a static solution obeying

$$
\phi(x\to-\infty)=\phi_a,
\qquad
\phi(x\to+\infty)=\phi_b,
\qquad
\phi_a\ne\phi_b.
$$

The classical kink is the minimum-energy configuration in that sector. Quantum mechanically, the kink sector becomes a Hilbert-space sector whose low-energy states are built by quantizing the kink’s collective coordinates and fluctuations.

For the double-well model, define the topological charge

$$
Q
=
\frac{\phi(+\infty)-\phi(-\infty)}{2v}.
$$

Then

$$
Q=+1\quad\text{for a kink},
\qquad
Q=-1\quad\text{for an antikink},
\qquad
Q=0\quad\text{for the two vacuum sectors}.
$$

This $Q$ is not a Noether charge of a continuous symmetry. It is a boundary label.

## The phi-four kink

The static Euler–Lagrange equation is

$$
\frac{d^2\phi}{dx^2}
=
\frac{dV}{d\phi}
=
\lambda\phi(\phi^2-v^2).
$$

The kink solution can be found by solving this second-order equation directly, but the first-order route is cleaner. Since $V\ge0$, the energy can be written as a square plus a boundary term:

$$
E
=
\int dx\left[
\frac12\left(\frac{d\phi}{dx}\mp\sqrt{2V(\phi)}\right)^2
\pm \frac{d\phi}{dx}\sqrt{2V(\phi)}
\right].
$$

In the kink sector $\phi$ runs from $-v$ to $+v$, and along this interval

$$
\sqrt{2V(\phi)}
=
\sqrt{\frac{\lambda}{2}}(v^2-\phi^2).
$$

The energy is minimized when the square vanishes:

$$
\frac{d\phi}{dx}
=
\sqrt{\frac{\lambda}{2}}(v^2-\phi^2).
$$

Integrating gives

$$
\int\frac{d\phi}{v^2-\phi^2}
=
\sqrt{\frac{\lambda}{2}}(x-X),
$$

so

$$
\phi_K(x;X)
=
v\tanh\!\left[v\sqrt{\frac{\lambda}{2}}(x-X)\right]
=
v\tanh\!\left[\frac{m}{2}(x-X)\right].
$$

The antikink is obtained by reversing the sign or reversing $x-X$.

The characteristic thickness is therefore

$$
\ell_K\sim m^{-1}.
$$

The kink is not infinitely sharp. A very sharp step would have too much gradient energy; a very broad step would pay too much potential energy over a large region. The kink balances these two costs.

## Bogomolnyi bound and kink mass

The same square completion gives the classical kink mass. For the kink,

$$
M_K
=
\int_{-v}^{+v}d\phi\,\sqrt{2V(\phi)}
=
\sqrt{\frac{\lambda}{2}}\int_{-v}^{+v}d\phi\,(v^2-\phi^2).
$$

Thus

$$
M_K
=
\frac{2\sqrt{2}}{3}\sqrt{\lambda}\,v^3
=
\frac{m^3}{3\lambda}.
$$

Equivalently, since the first-order equation implies

$$
\frac12(\phi_K')^2=V(\phi_K),
$$

the energy density is split equally between gradient and potential energy:

$$
\mathcal E_K(x)
=
(\phi_K')^2
=
\frac{m^2v^2}{4}\operatorname{sech}^4\!\left[\frac{m}{2}(x-X)\right].
$$

The bound is “Bogomolnyi-like” even though the simple real scalar kink need not be supersymmetric. In supersymmetric theories, analogous first-order equations often become BPS equations protected by an algebraic central charge. That stronger structure belongs to later pages.

## Mechanical analogy

The static equation

$$
\phi''=\frac{dV}{d\phi}
$$

is the Newton equation for a particle with coordinate $\phi$ moving in the inverted potential $-V(\phi)$, with $x$ playing the role of time. The kink is a zero-energy trajectory that starts at the top of one hill of $-V$ and arrives at the top of another hill.

Multiplying the static equation by $\phi'$ gives

$$
\frac{d}{dx}\left[\frac12(\phi')^2-V(\phi)\right]=0.
$$

Finite energy requires $\phi'\to0$ and $V\to0$ at both ends, so the constant is zero:

$$
\frac12(\phi')^2=V(\phi).
$$

This is the first integral of the kink equation. It also explains why the first-order equation is available in this one-field example.

## Topological charge and conservation

For the double well, the topological charge

$$
Q=\frac{\phi(+\infty)-\phi(-\infty)}{2v}
$$

cannot change under a smooth finite-energy deformation that keeps the same vacuum set at infinity. To change $Q$, one end of space would have to move from one vacuum to the other. That would require an infinite region to leave its vacuum boundary condition, costing infinite energy in the infinite-line idealization.

A local conservation-law version can be written by defining the current

$$
j^\mu=\frac{1}{2v}\epsilon^{\mu\nu}\partial_\nu\phi
\qquad (\mu,\nu=0,1).
$$

Then

$$
\partial_\mu j^\mu=0
$$

identically, not by the equations of motion. The corresponding charge is

$$
\int dx\,j^0
=
\frac{\phi(+\infty)-\phi(-\infty)}{2v}.
$$

This is useful, but it should not mislead you. The current is a total derivative; its charge is boundary data.

## Fluctuations and zero modes

Write a small fluctuation around the kink as

$$
\phi(t,x)=\phi_K(x;X)+\eta(t,x).
$$

To quadratic order, normal modes satisfy

$$
\left[-\frac{d^2}{dx^2}+V''(\phi_K(x))\right]\eta_n(x)=\omega_n^2\eta_n(x).
$$

For the double-well kink,

$$
V''(\phi_K(x))
=
m^2\left[1-\frac32\operatorname{sech}^2\!\left(\frac{m}{2}(x-X)\right)\right].
$$

There is always a translational zero mode,

$$
\eta_0(x)\propto \frac{d\phi_K}{dx},
\qquad
\omega_0=0.
$$

This zero mode is not an instability. It says that shifting the kink center $X$ costs no energy. In the path integral or canonical quantization, this mode must be removed from the Gaussian determinant and replaced by integration over the collective coordinate $X$.

The $\phi^4$ kink also has a bound “shape mode” with

$$
\omega^2=\frac34m^2,
$$

plus continuum modes beginning at $\omega^2=m^2$. The exact mode spectrum is model-dependent; the existence of the translational zero mode is universal for an isolated kink in a translation-invariant theory.

## Quantum interpretation

In $1+1$ dimensions the kink behaves as a massive particle. Semiclassically, its rest mass is the classical kink energy plus loop corrections,

$$
M_{\text{kink}}
=
M_K+\Delta M_{1\text{-loop}}+\cdots.
$$

The expansion is controlled when the kink is heavy compared with the elementary quanta. In the double-well model, $M_K\sim m^3/\lambda$, so weak coupling gives a parametrically heavy soliton.

The one-kink Hilbert space is built by quantizing:

1. the center-of-mass coordinate $X$;
2. any additional internal collective coordinates;
3. nonzero fluctuation modes around the kink.

A kink and an antikink can annihilate because their total topological charge can be zero. Multi-kink physics is therefore richer than the one-soliton sector: there can be scattering, bound states, resonances, and confinement of kinks if the vacuum degeneracy is explicitly lifted.

## The sine-Gordon comparison

The sine-Gordon model gives the other canonical kink example:

$$
\mathcal L
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac{\mu^2}{\beta^2}\left(1-\cos\beta\phi\right).
$$

Its vacua are

$$
\phi_n=\frac{2\pi n}{\beta},
\qquad n\in\mathbb Z.
$$

A sine-Gordon soliton interpolates between neighboring vacua. Unlike the $\phi^4$ model, sine-Gordon theory is integrable in $1+1$ dimensions, so its exact quantum spectrum and scattering can be studied far beyond elementary semiclassics. For this reason, the sine-Gordon kink deserves its own model-calculation page later.

## Common pitfalls

**Calling every lump a kink.** A kink is tied to boundary conditions between distinct vacua in one spatial dimension. A generic localized bump in the vacuum sector is not a kink, even if it is large.

**Forgetting that the kink is a sector.** The kink is not merely a solution inside the perturbative vacuum Hilbert space. It lives in a sector with different boundary data, so perturbation theory around one vacuum does not produce it as a finite collection of elementary quanta.

**Confusing topological charge with a Noether charge.** The double-well kink charge is a boundary charge. It is conserved because finite-energy deformations cannot change the endpoints, not because a continuous internal symmetry rotates the kink.

**Using the wrong mass parameter.** Many references define the double-well potential with different symbols. Always check whether $m$ denotes the curvature mass of small oscillations or a parameter inside the potential.

**Ignoring the zero mode in determinants.** The translational zero mode makes the naive fluctuation determinant vanish. It must be excluded and replaced by a collective-coordinate measure.

**Assuming topological stability survives explicit breaking.** If one vacuum is lifted above the other, a kink-like interface feels a pressure difference. The object becomes a wall separating true and false vacuum, not a static topologically protected kink between degenerate vacua.

## Relations to other pages

- [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/) explains why the endpoint data classify one-dimensional sectors.
- [Discrete Vacua](/nonperturbative-qft/vacuum-structure-phases/discrete-vacua/) describes the vacuum structure that makes double-well kinks possible.
- [Domain Walls](/nonperturbative-qft/solitons-defects-extended-configurations/domain-walls/) extends the kink profile into higher dimensions and replaces mass by tension.
- [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/) explains why $d\phi_K/dx$ must be handled separately from ordinary fluctuations.
- [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/) gives the general method for quantizing $X$ and other moduli.
- [False-Vacuum Decay](/nonperturbative-qft/semiclassical-methods/false-vacuum-decay/) uses wall tension when a metastable phase decays by bubble nucleation.

## Research status

The classical and semiclassical theory of kinks in scalar field theory is established. The main textbook results are the finite-energy boundary classification, explicit solutions in special models, zero modes, fluctuation spectra, and one-loop quantization.

Kinks also remain active as building blocks in modern problems: fermion zero modes and charge fractionalization, supersymmetric BPS solitons, integrable scattering, confined kinks after explicit symmetry breaking, real-time non-equilibrium dynamics, and generalized defect lines in low-dimensional QFT. The elementary double-well formulas on this page are settled; the research frontiers arise when kinks interact with gapless modes, gauge fields, supersymmetry, topology, or strong coupling.

## Exercises

### Exercise 1: Derive the kink profile

Starting from

$$
\frac{d\phi}{dx}
=
\sqrt{\frac{\lambda}{2}}(v^2-\phi^2),
$$

derive

$$
\phi_K(x;X)=v\tanh\!\left[\frac{m}{2}(x-X)\right].
$$

<details>
<summary><strong>Solution</strong></summary>

Separate variables:

$$
\frac{d\phi}{v^2-\phi^2}=\sqrt{\frac{\lambda}{2}}dx.
$$

Using

$$
\int\frac{d\phi}{v^2-\phi^2}
=\frac{1}{2v}\ln\frac{v+\phi}{v-\phi},
$$

we get

$$
\frac{1}{2v}\ln\frac{v+\phi}{v-\phi}
=\sqrt{\frac{\lambda}{2}}(x-X).
$$

Multiplying both sides by $2v$ gives

$$
\ln\frac{v+\phi}{v-\phi}=2v\sqrt{\frac{\lambda}{2}}(x-X)=m(x-X).
$$

Therefore

$$
\frac{v+\phi}{v-\phi}=e^{m(x-X)},
$$

which gives

$$
\phi=v\frac{e^{m(x-X)}-1}{e^{m(x-X)}+1}
=v\tanh\!\left[\frac{m}{2}(x-X)\right].
$$

</details>

### Exercise 2: Compute the classical kink mass

Use the first-order equation to show that

$$
M_K=\frac{m^3}{3\lambda}.
$$

<details>
<summary><strong>Solution</strong></summary>

The square completion gives

$$
M_K=\int_{-v}^{+v}d\phi\,\sqrt{2V(\phi)}.
$$

For $V=\lambda(\phi^2-v^2)^2/4$ and $-v\le\phi\le v$,

$$
\sqrt{2V}=\sqrt{\frac{\lambda}{2}}(v^2-\phi^2).
$$

Therefore

$$
M_K
=\sqrt{\frac{\lambda}{2}}\left[v^2\phi-\frac{\phi^3}{3}\right]_{-v}^{+v}
=\sqrt{\frac{\lambda}{2}}\frac{4v^3}{3}
=\frac{2\sqrt2}{3}\sqrt\lambda\,v^3.
$$

Since $m^2=2\lambda v^2$,

$$
\frac{m^3}{3\lambda}=\frac{(2\lambda v^2)^{3/2}}{3\lambda}
=\frac{2\sqrt2}{3}\sqrt\lambda\,v^3.
$$

</details>

### Exercise 3: Verify the zero mode

Show that

$$
\eta_0(x)=\frac{d\phi_K}{dx}
$$

solves the fluctuation equation with $\omega^2=0$.

<details>
<summary><strong>Solution</strong></summary>

The static kink equation is

$$
-\phi_K''+V'(\phi_K)=0.
$$

Differentiate with respect to $x$:

$$
-\frac{d^2}{dx^2}\phi_K'+V''(\phi_K)\phi_K'=0.
$$

Thus

$$
\left[-\frac{d^2}{dx^2}+V''(\phi_K)\right]\phi_K'=0,
$$

which is the fluctuation equation with $\omega^2=0$.

</details>

### Exercise 4: Why a kink cannot unwind locally

Suppose $\phi_s(x)$ is a continuous one-parameter family of finite-energy configurations with fixed boundary values $\phi_s(-\infty)=-v$ and $\phi_s(+\infty)=+v$. Show that the topological charge $Q$ is independent of $s$.

<details>
<summary><strong>Solution</strong></summary>

The charge is

$$
Q_s=\frac{\phi_s(+\infty)-\phi_s(-\infty)}{2v}.
$$

The boundary values are fixed for every $s$, so

$$
Q_s=\frac{(+v)-(-v)}{2v}=1
$$

for all $s$. A deformation can change the local shape of the kink but cannot change its endpoint data without leaving the fixed finite-energy sector.

</details>

## References

### Standard first pass

- R. Rajaraman, *Solitons and Instantons*, for the classic pedagogical treatment of kinks, sine-Gordon solitons, fluctuation spectra, and semiclassical quantization.
- S. Coleman, *Aspects of Symmetry*, especially “Classical Lumps and Their Quantum Descendants,” for the physics of soliton quantization and the relation between classical lumps and quantum states.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, chapter 2, for kinks and domain walls in modern QFT language.
- A. Zee, *Quantum Field Theory in a Nutshell*, ch. V.6, for the kink as a clean nonperturbative phenomenon and the Bogomolnyi inequality.
- M. Srednicki, *Quantum Field Theory*, ch. 92, for solitons and monopoles in a standard QFT sequence.

### Deeper references

- N. Manton and P. Sutcliffe, *Topological Solitons*, for a modern geometric and dynamical treatment of solitons and moduli.
- R. Dashen, B. Hasslacher, and A. Neveu, classic papers on semiclassical quantization of solitons.
- E. J. Weinberg, *Classical Solutions in Quantum Field Theory*, for a broad reference on solitons, instantons, monopoles, and related objects.

## Version history

- **2026-06-26:** Initial polished page, added with Domain Walls.
