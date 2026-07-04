---
title: "Semiclassical Quantization"
description: "Explains how collective coordinates and small oscillations around solitons or other saddles become quantum states and semiclassical spectra."
sidebar:
  label: "Semiclassical Quantization"
  order: 8
level: Graduate
status: "Polished draft"
source: "Coleman; Rajaraman; Dashen–Hasslacher–Neveu; Shifman; Weinberg; Zinn-Justin."
topics:
  - semiclassical quantization
  - collective coordinates
  - soliton spectra
  - moduli-space dynamics
  - zero modes
  - one-loop corrections
canonicalTopics:
  - nonperturbative-qft
  - semiclassical-methods
  - semiclassical-quantization
  - soliton-quantization
researchStatus:
  established:
    - "Quantization of normalizable collective coordinates and nonzero fluctuation modes is the standard semiclassical route from classical solitons to quantum particle states."
  active:
    - "For gauge solitons, noncompact moduli spaces, radiation modes, curved moduli spaces, and strongly coupled backgrounds, the effective quantum mechanics can require additional renormalization, constraints, or nonadiabatic corrections."
---

## Summary

**Semiclassical quantization** turns a classical nontrivial field configuration into quantum states. The basic move is to separate the slow coordinates that move a saddle along a family of equivalent or nearly equivalent solutions from the fast fluctuation modes transverse to that family.

For a static soliton or saddle family $\bar\phi(\boldsymbol x;q)$ with collective coordinates $q^a(t)$, one writes schematically

$$
\phi(t,\boldsymbol x)
=
\bar\phi(\boldsymbol x;q(t))
+
\text{nonzero fluctuations}.
$$

Substituting into the action gives an effective quantum mechanics on the moduli space $\mathcal M$,

$$
L_{\text{eff}}
=
-M_{\text{cl}}
+\frac12 g_{ab}(q)\dot q^a\dot q^b
-V_{\text{lift}}(q)
+\text{oscillators}
+\text{higher corrections},
$$

where the moduli-space metric is induced from the field-space kinetic term,

$$
g_{ab}(q)
=
\int d^{d-1}x\,
\frac{\partial\bar\phi}{\partial q^a}
\frac{\partial\bar\phi}{\partial q^b}
$$

for a single real scalar with canonical normalization. Quantization then gives a particle moving on $\mathcal M$, together with quantized small oscillations around the soliton.

<figure class="doc-figure" style="--figure-width: 54rem;">

![A schematic semiclassical quantization pipeline: a classical saddle family defines a moduli space, its tangent zero modes induce a metric, and quantization produces wavefunctions on moduli space plus transverse oscillator excitations.](/figures/nonperturbative-qft/semiclassical-quantization-moduli-space.svg)

<figcaption>

Semiclassical quantization separates motion along a saddle family from transverse fluctuations. The tangent directions $\partial_a\bar\phi$ become collective coordinates $q^a$, while the nonzero eigenmodes of the Hessian become harmonic oscillators. The leading quantum dynamics is a particle on $\mathcal M$ with metric $g_{ab}$.

</figcaption>
</figure>

The phrase “quantize the soliton” therefore means two things at once: quantize its collective coordinates, such as position, phase, orientation, or size, and quantize the nonzero fluctuation modes around it. Both are needed for the spectrum.

## Prerequisites

You should know [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/), [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/), [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/), and [Moduli of Saddles](/nonperturbative-qft/semiclassical-methods/moduli-of-saddles/). For one-loop mass shifts, review [Fluctuation Determinants](/nonperturbative-qft/semiclassical-methods/fluctuation-determinants/).

For physical examples, later pages on kinks, domain walls, vortices, monopoles, Skyrmions, and instantons will provide concrete applications.

## Core idea

Perturbation theory around the vacuum starts with a trivial classical solution and quantizes its small oscillations. Semiclassical quantization around a soliton starts with a nontrivial classical solution and asks what quantum states live near it.

The first surprise is that some fluctuations are not oscillators. If the classical solution can be translated, rotated, globally rephased, or moved along a moduli space without changing its energy, the corresponding fluctuation has zero frequency. Treating a zero-frequency oscillator as an ordinary harmonic oscillator is wrong. It should be replaced by a collective coordinate.

The second surprise is that a soliton usually behaves as a particle, even though it is made of fields. The center of a kink, vortex, monopole, or Skyrmion is a coordinate. Once that coordinate is quantized, the soliton has momentum, wave packets, scattering states, and sometimes internal spin or charge states.

The clean separation is

$$
\text{zero modes}
\longrightarrow
\text{collective-coordinate quantum mechanics},
$$

while

$$
\text{positive nonzero modes}
\longrightarrow
\text{harmonic oscillators and one-loop shifts}.
$$

A negative mode is different again: it signals an instability or a bounce contribution to decay, not a stable quantum level.

## Setup and conventions

Consider a Lorentzian scalar theory in $D=d$ spacetime dimensions with Lagrangian

$$
L
=
\int d^{d-1}x
\left[
\frac12 \dot\phi^2
-\frac12(\nabla\phi)^2
-V(\phi)
\right].
$$

A static classical solution $\bar\phi(\boldsymbol x;q)$ depends on parameters $q^a$. These parameters may include the center of a soliton, an internal phase, an orientation, or a family of classically degenerate shapes. We assume for now that they are genuine normalizable moduli, not gauge redundancies.

The tangent vectors to the family are

$$
Z_a(\boldsymbol x;q)
=
\frac{\partial\bar\phi(\boldsymbol x;q)}{\partial q^a}.
$$

For a canonical scalar field, the induced metric is

$$
g_{ab}(q)
=
\int d^{d-1}x\,Z_a(\boldsymbol x;q)Z_b(\boldsymbol x;q).
$$

If the theory has several fields, gauge fields, fermions, or curved target-space metric, this formula is replaced by the corresponding field-space inner product. The principle is the same: the kinetic term of the field theory induces the kinetic term of the collective coordinates.

To avoid double counting, fluctuations $\eta$ transverse to the moduli must obey an orthogonality condition such as

$$
(\eta,Z_a)=0.
$$

The precise condition depends on the gauge choice and on how the coordinates $q^a$ are introduced. Its job is simple: do not count the same field deformation once as a collective coordinate and again as an oscillator.

## From moduli to a quantum Hamiltonian

Insert the slowly moving ansatz

$$
\phi(t,\boldsymbol x)=\bar\phi(\boldsymbol x;q(t))
$$

into the kinetic term. Since

$$
\dot\phi
=
\dot q^a\frac{\partial\bar\phi}{\partial q^a},
$$

we get

$$
\frac12\int d^{d-1}x\,\dot\phi^2
=
\frac12g_{ab}(q)\dot q^a\dot q^b.
$$

If the family consists of exactly degenerate static solutions with energy $M_{\text{cl}}$, the leading effective Lagrangian is

$$
L_{\mathcal M}
=
-M_{\text{cl}}
+\frac12g_{ab}(q)\dot q^a\dot q^b.
$$

If the would-be moduli are lifted by small effects, one adds an effective potential,

$$
L_{\mathcal M}
=
-M_{\text{cl}}
+\frac12g_{ab}(q)\dot q^a\dot q^b
-V_{\text{lift}}(q).
$$

Canonical quantization gives momenta

$$
p_a=g_{ab}(q)\dot q^b,
$$

and the classical moduli Hamiltonian

$$
H_{\mathcal M}
=
M_{\text{cl}}
+\frac12g^{ab}(q)p_ap_b
+V_{\text{lift}}(q).
$$

Quantum mechanically, the natural leading operator is the Laplace–Beltrami operator on moduli space,

$$
H_{\mathcal M}
=
M_{\text{ren}}
-\frac{\hbar^2}{2}\Delta_{\mathcal M}
+V_{\text{eff}}(q)+\cdots,
$$

where

$$
\Delta_{\mathcal M}
=
\frac{1}{\sqrt g}\partial_a
\left(\sqrt g\,g^{ab}\partial_b\right),
\qquad
g=\det(g_{ab}).
$$

The Hilbert space inner product is

$$
\langle\Psi_1|\Psi_2\rangle
=
\int_{\mathcal M} d^nq\sqrt g\,
\Psi_1(q)^\ast\Psi_2(q).
$$

The ellipsis hides operator-ordering terms, curvature couplings, Berry connections, fermion zero-mode effects, and corrections from integrating out nonzero modes. The Laplace–Beltrami form is the standard first answer, not a magic exemption from checking the measure.

## Translation: the soliton as a particle

The simplest collective coordinate is the center $X$ of a one-dimensional kink,

$$
\bar\phi(x;X)=\bar\phi_0(x-X).
$$

The zero mode is

$$
Z_X(x)=\frac{\partial\bar\phi(x;X)}{\partial X}
=-\frac{d\bar\phi_0(x-X)}{dx}.
$$

The induced metric is

$$
g_{XX}
=
\int dx\,\left(\frac{d\bar\phi_0}{dx}\right)^2.
$$

The classical mass is

$$
M_{\text{cl}}
=
\int dx\left[
\frac12\left(\frac{d\bar\phi_0}{dx}\right)^2
+V(\bar\phi_0)-V(\phi_{\text{vac}})
\right].
$$

For a BPS-like kink satisfying

$$
\frac12\left(\frac{d\bar\phi_0}{dx}\right)^2
=
V(\bar\phi_0)-V(\phi_{\text{vac}}),
$$

one finds

$$
g_{XX}=M_{\text{cl}}.
$$

Thus

$$
L_X
=
-M_{\text{cl}}+\frac12M_{\text{cl}}\dot X^2,
$$

and quantization gives

$$
H_X
=
M_{\text{cl}}+\frac{P^2}{2M_{\text{cl}}}
$$

at nonrelativistic order. A fully Lorentz-invariant treatment restores the relativistic dispersion relation

$$
E(P)=\sqrt{M^2+P^2}
$$

for the exact one-soliton particle. The moduli-space Lagrangian gives the small-velocity expansion of this relation.

## Internal moduli and rotors

Some solitons have internal collective coordinates. A common example is a global phase $\alpha$ with period $2\pi$. If

$$
L_\alpha
=
\frac12 I\dot\alpha^2,
$$

then

$$
p_\alpha=I\dot\alpha.
$$

Because $\alpha$ is an angle, quantum wavefunctions obey

$$
\Psi(\alpha+2\pi)=\Psi(\alpha),
$$

so

$$
\Psi_n(\alpha)=e^{in\alpha},
\qquad
p_\alpha=\hbar n,
\qquad
n\in\mathbb Z.
$$

The energy levels are

$$
E_n
=
M+\frac{\hbar^2 n^2}{2I}+\text{corrections}.
$$

This is the simplest version of how a continuous classical orientation becomes a tower of charged quantum states.

For a non-Abelian orientation, the moduli space may be a group manifold or a quotient. Quantization becomes rigid-rotor quantization. Wavefunctions are functions on the group or coset, and energy eigenstates fall into representations. In Skyrmion physics, monopole dynamics, and non-Abelian vortex dynamics, this representation-theoretic structure is often as important as the classical soliton profile.

The warning is that not every apparent internal orientation is physical. If the orientation is a gauge copy, it must be divided out. If it is a gauge transformation that acts nontrivially at infinity, it may instead label a physical charge. The boundary condition decides.

## Small oscillations and one-loop levels

Now include transverse fluctuations,

$$
\phi(t,\boldsymbol x)
=
\bar\phi(\boldsymbol x;q(t))+\eta_\perp(t,\boldsymbol x).
$$

At fixed $q$, the quadratic Hamiltonian for positive modes is a sum of oscillators. If

$$
\Delta_s u_n=\omega_n^2u_n,
\qquad
\omega_n^2>0,
$$

then

$$
\eta_\perp(t,\boldsymbol x)=\sum_n Q_n(t)u_n(\boldsymbol x),
$$

and the transverse Hamiltonian contains

$$
H_\perp
=
\sum_n\hbar\omega_n
\left(a_n^\dagger a_n+\frac12\right).
$$

The one-loop soliton mass is therefore morally

$$
M_{\text{1-loop}}
=
M_{\text{cl}}
+\frac{\hbar}{2}\sum_n^{\text{soliton}}\omega_n
-\frac{\hbar}{2}\sum_n^{\text{vacuum}}\omega_n
+M_{\text{ct}}.
$$

The subtraction and counterterm are not optional decoration. Both sums are divergent in QFT. A meaningful mass shift compares the soliton fluctuation spectrum to the vacuum spectrum and uses the same renormalization scheme that defines the underlying theory.

A typical stable semiclassical spectrum has the form

$$
E
=
M_{\text{ren}}
+E_{\mathcal M}
+\sum_n\hbar\omega_n N_n
+O(\hbar^2),
$$

where $E_{\mathcal M}$ is the energy of the collective-coordinate quantum mechanics and $N_n$ are occupation numbers of nonzero modes.

## Fermion zero modes and multiplets

Fermions change the story in a beautiful way. A classical bosonic soliton may support fermion zero modes satisfying a Dirac equation in the soliton background. Expanding a fermion field in zero modes gives finite-dimensional Grassmann degrees of freedom. Upon canonical quantization, these become creation and annihilation operators or a Clifford algebra.

For example, if a soliton has fermionic zero-mode operators $c_i,c_i^\dagger$ with

$$
\{c_i,c_j^\dagger\}=\delta_{ij},
$$

then acting with $c_i^\dagger$ builds a multiplet of soliton states. The resulting states can differ by fermion number, spin, flavor, or other global charges. This is how fermion zero modes turn a single classical background into a family of quantum states.

In Euclidean instanton calculations, fermion zero modes also imply selection rules: a path integral vanishes unless operator insertions or mass terms soak up the Grassmann zero modes. In soliton quantization, the same zero modes become part of the soliton Hilbert space.

## Gauge constraints and quotienting

Gauge theories require one more layer of discipline. A zero mode generated by an infinitesimal gauge transformation

$$
\delta A_i=D_i\epsilon
$$

is not automatically a physical collective coordinate. If $\epsilon$ vanishes fast enough at infinity and preserves the boundary conditions, this deformation is usually a gauge redundancy. It should be removed by gauge fixing and by the Faddeev–Popov procedure.

By contrast, gauge transformations that approach a nontrivial global transformation at infinity can act as physical symmetries. They may generate electric charge, magnetic charge, flavor quantum numbers, or orientation moduli. The physical moduli space is therefore often a quotient,

$$
\mathcal M_{\text{phys}}
=
\frac{\text{solutions}}{\text{gauge transformations that are redundancies}}.
$$

The effective quantum mechanics must also impose Gauss-law constraints. In practice this means that allowed wavefunctions are not arbitrary functions on a naive parameter space. They must transform correctly under residual gauge symmetries and obey any constraints inherited from the field theory.

## Validity conditions

Semiclassical quantization is controlled when several separations hold.

First, the soliton action or mass should be large in units of the fluctuation scale. In weak-coupling examples one often has

$$
M_{\text{cl}}\sim \frac{1}{g^2},
$$

so loop corrections are parametrically smaller.

Second, the collective coordinates should vary slowly. If $q^a(t)$ changes on the same time scale as the massive fluctuation modes, integrating out those modes is no longer adiabatic.

Third, the moduli should be normalizable. Non-normalizable deformations often change boundary conditions or couplings rather than describing dynamical quantum coordinates.

Fourth, the background should be stable for ordinary energy levels. A negative mode means the saddle is not a stable soliton state. It may still be physically important as a bounce for false-vacuum decay.

Finally, radiation and multi-soliton effects should be small. A single-soliton quantum mechanics does not automatically include particle production, radiation damping, or strongly overlapping soliton interactions.

## Common pitfalls

**Quantizing gauge copies.** A gauge orientation is physical only if it survives the quotient by gauge redundancy. Otherwise it is overcounting.

**Double-counting zero modes.** If a deformation is described by $q^a(t)$, remove it from the oscillator determinant and impose an orthogonality condition on $\eta_\perp$.

**Forgetting the measure.** On a curved moduli space, the inner product contains $\sqrt g$. The kinetic operator is not just $-g^{ab}\partial_a\partial_b$ in arbitrary coordinates.

**Using the classical mass in all quantum formulas.** The physical mass includes one-loop and higher corrections. Translation-mode quantization should use the renormalized mass when comparing to physical dispersion.

**Assuming every modulus stays flat.** Quantum effects, explicit symmetry breaking, boundaries, or interactions with other solitons can lift classical moduli.

**Confusing Euclidean instantons with Lorentzian soliton particles.** Instantons contribute to amplitudes and tunneling. Stable solitons appear as states in the Hilbert space. The mathematics overlaps, but the interpretation differs.

## Relations to other pages

This page is the bridge from semiclassical path integrals to the later soliton chapter. It uses the collective-coordinate measure of [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/) and the moduli-space geometry of [Moduli of Saddles](/nonperturbative-qft/semiclassical-methods/moduli-of-saddles/), but changes the question from “How do I integrate over a saddle contribution?” to “What quantum states live near this classical configuration?”

The one-loop oscillator part connects directly to [One-Loop Determinants Around Saddles](/nonperturbative-qft/semiclassical-methods/one-loop-determinants-around-saddles/). The distinction between zero modes, nonzero modes, and negative modes connects back to [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/) and [False-Vacuum Decay](/nonperturbative-qft/semiclassical-methods/false-vacuum-decay/).

Later, the pages on kinks, vortices, monopoles, Skyrmions, and BPS bounds will provide concrete examples of the abstract construction used here.

## Research status

**Established.** Collective-coordinate quantization of stable solitons, normal-mode quantization around classical backgrounds, and one-loop soliton mass calculations are standard semiclassical techniques. In many low-dimensional and supersymmetric examples, the method gives sharp quantitative results.

**Approximate.** The moduli-space approximation assumes slow motion and a separation between moduli and massive modes. It can fail when moduli-space motion radiates, when solitons overlap, or when the gap to transverse modes becomes small.

**Active.** Quantization on singular moduli spaces, soliton dynamics with gauge and gravitational fields, quantum corrections to moduli-space metrics, and semiclassical quantization in strongly coupled or real-time settings remain technically subtle.

## Exercises

### Exercise 1: Kink center metric

Let $\bar\phi(x;X)=\bar\phi_0(x-X)$ be a kink in one spatial dimension. Show that the induced metric for $X$ is

$$
g_{XX}=\int dx\left(\frac{d\bar\phi_0}{dx}\right)^2.
$$

If the kink satisfies

$$
\frac12(\bar\phi_0')^2=V(\bar\phi_0)-V(\phi_{\text{vac}}),
$$

show that $g_{XX}=M_{\text{cl}}$.

<details>
<summary><strong>Solution</strong></summary>

The tangent vector is

$$
Z_X(x)=\partial_X\bar\phi(x;X)=-\bar\phi_0'(x-X).
$$

The induced metric is the field-space norm of this tangent vector:

$$
g_{XX}=\int dx\,Z_X^2
=\int dx\left(\bar\phi_0'(x-X)\right)^2.
$$

Changing variables $y=x-X$ gives

$$
g_{XX}=\int dy\left(\bar\phi_0'(y)\right)^2.
$$

The classical kink mass is

$$
M_{\text{cl}}
=\int dy\left[\frac12(\bar\phi_0')^2
+V(\bar\phi_0)-V(\phi_{\text{vac}})\right].
$$

Using the first-order relation gives

$$
M_{\text{cl}}
=\int dy\left[\frac12(\bar\phi_0')^2+\frac12(\bar\phi_0')^2\right]
=\int dy(\bar\phi_0')^2
=g_{XX}.
$$

</details>

### Exercise 2: Quantization of an angular modulus

A soliton has one internal modulus $\alpha\sim\alpha+2\pi$ with effective Lagrangian

$$
L=\frac12I\dot\alpha^2-M.
$$

Quantize the coordinate $\alpha$ and find the energy levels.

<details>
<summary><strong>Solution</strong></summary>

The conjugate momentum is

$$
p_\alpha=I\dot\alpha.
$$

The Hamiltonian is

$$
H=M+\frac{p_\alpha^2}{2I}.
$$

Since $\alpha$ is periodic, wavefunctions obey

$$
\Psi(\alpha+2\pi)=\Psi(\alpha),
$$

so the normalized eigenfunctions are Fourier modes,

$$
\Psi_n(\alpha)=\frac{1}{\sqrt{2\pi}}e^{in\alpha},
\qquad n\in\mathbb Z.
$$

With $p_\alpha=-i\hbar\partial_\alpha$, the eigenvalues are

$$
p_\alpha=\hbar n.
$$

Therefore

$$
E_n=M+\frac{\hbar^2 n^2}{2I}.
$$

</details>

### Exercise 3: Why zero modes are not oscillator modes

Suppose a fluctuation mode has eigenvalue $\omega^2=0$. Explain why the harmonic oscillator formula

$$
E_n=\hbar\omega\left(n+\frac12\right)
$$

is not the correct quantization of this direction.

<details>
<summary><strong>Solution</strong></summary>

The oscillator formula assumes a quadratic restoring potential. For a mode coordinate $Q$, the oscillator Hamiltonian is

$$
H=\frac12P^2+\frac12\omega^2Q^2.
$$

If $\omega=0$, the Hamiltonian is instead

$$
H=\frac12P^2,
$$

which describes free motion along a flat direction, not a bound oscillator. In a soliton problem this flat direction is usually a collective coordinate, such as the position $X$ of the soliton. It should be quantized as a coordinate on moduli space, with momentum eigenstates or wave packets, rather than as a zero-frequency oscillator.

</details>

### Exercise 4: Laplace–Beltrami operator on a circle

Let the moduli space be a circle of radius $R$ with coordinate $\alpha\sim\alpha+2\pi$ and metric

$$
ds^2=R^2d\alpha^2.
$$

Compute $\Delta_{\mathcal M}$ and recover the rotor spectrum.

<details>
<summary><strong>Solution</strong></summary>

Here

$$
g_{\alpha\alpha}=R^2,
\qquad
g^{\alpha\alpha}=\frac{1}{R^2},
\qquad
\sqrt g=R.
$$

Thus

$$
\Delta_{\mathcal M}
=\frac1R\partial_\alpha
\left(R\frac{1}{R^2}\partial_\alpha\right)
=\frac{1}{R^2}\partial_\alpha^2.
$$

The quantum Hamiltonian is

$$
H=M-\frac{\hbar^2}{2}\Delta_{\mathcal M}
=M-\frac{\hbar^2}{2R^2}\partial_\alpha^2.
$$

On $\Psi_n=e^{in\alpha}/\sqrt{2\pi}$, this gives

$$
E_n=M+\frac{\hbar^2n^2}{2R^2}.
$$

This matches the angular-modulus result with $I=R^2$.

</details>

## References

- S. Coleman, *Aspects of Symmetry*, especially the lectures on solitons, instantons, and semiclassical methods.
- R. Rajaraman, *Solitons and Instantons*, for classic semiclassical quantization of kinks, solitons, and instantons.
- R. Dashen, B. Hasslacher, and A. Neveu, classic papers on semiclassical bound states and soliton quantization.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, for modern treatments of kinks, walls, vortices, monopoles, and supersymmetric solitons.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. II, for solitons and semiclassical aspects of quantum fields.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional-integral and semiclassical methods.

## Version history

- **2026-06-26:** Initial polished draft.
