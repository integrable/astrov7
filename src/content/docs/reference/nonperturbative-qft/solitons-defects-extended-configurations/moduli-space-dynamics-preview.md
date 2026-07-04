---
title: "Moduli-Space Dynamics"
description: "Explains the moduli-space approximation for slowly moving solitons: collective coordinates, zero-mode metrics, geodesic motion, forces, and validity limits."
sidebar:
  label: "Moduli-Space Dynamics"
  order: 9
level: Advanced
status: "Polished draft"
source: "Manton and Sutcliffe; Shifman; Rajaraman; Coleman; Atiyah and Hitchin."
topics:
  - moduli spaces
  - collective coordinates
  - soliton dynamics
  - geodesic approximation
  - zero modes
  - BPS solitons
  - monopoles
  - vortices
canonicalTopics:
  - nonperturbative-qft
  - solitons
  - moduli-space-dynamics
  - collective-coordinates
  - bps-solitons
researchStatus:
  established:
    - "The moduli-space approximation is a standard low-velocity approximation for solitons with normalizable zero modes, especially BPS solitons with no static force."
  active:
    - "Precise moduli-space metrics, quantum mechanics on singular moduli spaces, non-Abelian defects, wall crossing, radiation corrections, and strongly coupled defect dynamics remain active and model-dependent."
---

## Summary

**Moduli-space dynamics** is the low-energy approximation in which a slowly moving soliton remains close to a family of static solutions. Instead of solving the full field equations at every time, we let the collective coordinates become time-dependent:

$$
\Phi(t,\mathbf x)
\approx
\Phi_{\rm cl}(\mathbf x;X^a(t)).
$$

The parameters $X^a$ are **moduli**: positions, phases, sizes, orientations, separations, or other coordinates labeling degenerate static solutions. Inserting the ansatz into the field-theory action gives an effective mechanical system,

$$
L_{\rm eff}
=
-M
+
\frac12g_{ab}(X)\dot X^a\dot X^b
+\cdots,
$$

where the metric is computed from zero-mode overlaps,

$$
g_{ab}(X)
=
\int d^n x\,
\delta_a\Phi^I\,G_{IJ}\,\delta_b\Phi^J
+\text{gauge-field terms}.
$$

At leading order, the soliton moves along geodesics on its moduli space:

$$
\ddot X^a+\Gamma^a_{bc}(X)\dot X^b\dot X^c=0.
$$

<figure class="doc-figure" style="--figure-width: 58rem;">

![A schematic moduli space with a path of collective coordinates, tangent zero modes, and the induced low-energy Lagrangian.](/figures/nonperturbative-qft/moduli-space-geodesic-dynamics.svg)

<figcaption>

A family of static solitons defines a moduli space $\mathcal M$. Tangent vectors to $\mathcal M$ are normalizable zero modes. Their inner products define $g_{ab}$, and slow motion becomes geodesic motion on $\mathcal M$ at leading order.

</figcaption>
</figure>

This approximation is a workhorse of nonperturbative QFT because it turns an infinite-dimensional field problem into finite-dimensional geometry. The price is that it assumes slow motion, normalizable moduli, and negligible radiation. The approximation is powerful, not omnipotent; it is a precision scalpel, not a physics leaf blower.

## Prerequisites

You should know [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/), [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/), [Moduli of Saddles](/nonperturbative-qft/semiclassical-methods/moduli-of-saddles/), [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/), and [BPS Bounds](/nonperturbative-qft/solitons-defects-extended-configurations/bps-bounds-preview/).

Concrete examples from [Kinks](/nonperturbative-qft/solitons-defects-extended-configurations/kinks/), [Vortices](/nonperturbative-qft/solitons-defects-extended-configurations/vortices/), [Monopoles](/nonperturbative-qft/solitons-defects-extended-configurations/monopoles/), and [Skyrmions](/nonperturbative-qft/solitons-defects-extended-configurations/skyrmions/) make the abstract formulas less floaty.

## Core idea

A soliton is a field configuration. Its full motion is governed by field equations with infinitely many degrees of freedom. But a slowly moving stable soliton should not immediately excite all fluctuation modes. Its lowest-energy motion is usually motion along the directions that cost no static energy: translations, global phases, gauge orientations, relative separations, and other moduli.

A static solution family is written

$$
\Phi_{\rm cl}(\mathbf x;X^a),
\qquad
X^a\in\mathcal M,
$$

where $\mathcal M$ is the moduli space. The tangent vectors are

$$
\delta_a\Phi
=
\frac{\partial\Phi_{\rm cl}}{\partial X^a}
$$

up to gauge projection. These tangent vectors solve the linearized static equations with zero eigenvalue, so they are zero modes.

The approximation says

$$
\text{slow soliton motion}
\quad\approx\quad
\text{motion on }\mathcal M.
$$

The shape of $\mathcal M$ is physical. If $\mathcal M$ is flat, motion is free. If it is curved, solitons scatter even without an ordinary potential. In BPS systems, much of the interesting dynamics is encoded in this curvature.

## Setup and conventions

Let the fields collectively be $\Phi^I$, with Lagrangian

$$
L
=
\int d^n x\,
\left[
\frac12G_{IJ}(\Phi)\dot\Phi^I\dot\Phi^J
-\mathcal E_{\rm static}(\Phi)
\right].
$$

Assume there is a family of static solutions

$$
\Phi_{\rm cl}(\mathbf x;X),
$$

all with the same static energy $M$. Promote the parameters to slowly varying collective coordinates,

$$
X^a\mapsto X^a(t),
$$

and set

$$
\Phi(t,\mathbf x)=\Phi_{\rm cl}(\mathbf x;X(t)).
$$

Then

$$
\dot\Phi^I
=
\frac{\partial\Phi_{\rm cl}^I}{\partial X^a}\dot X^a
=
\delta_a\Phi^I\dot X^a.
$$

Substitution into the kinetic energy gives

$$
L_{\rm eff}
=
-M+\frac12g_{ab}(X)\dot X^a\dot X^b+\text{higher corrections},
$$

with

$$
g_{ab}(X)
=
\int d^n x\,
G_{IJ}(\Phi_{\rm cl})\,
\delta_a\Phi^I\delta_b\Phi^J.
$$

In a gauge theory, $\delta_a\Phi$ must be replaced by a gauge-orthogonal variation. Otherwise the metric counts gauge redundancy as physical motion. Symbolically,

$$
\delta_a\Phi
=
\frac{\partial\Phi_{\rm cl}}{\partial X^a}-\delta_{\Omega_a}\Phi_{\rm cl},
$$

where $\Omega_a$ is chosen so that $\delta_a\Phi$ obeys a background gauge condition. This is not decorative paperwork; without it, the moduli-space metric is wrong.

## Deriving the geodesic equation

Start from

$$
L_{\rm eff}
=
\frac12g_{ab}(X)\dot X^a\dot X^b-M.
$$

The Euler–Lagrange equations are

$$
\frac{d}{dt}\left(g_{ab}\dot X^b\right)
-
\frac12\partial_a g_{bc}\dot X^b\dot X^c=0.
$$

Expanding the time derivative gives

$$
g_{ab}\ddot X^b
+\partial_cg_{ab}\dot X^c\dot X^b
-\frac12\partial_a g_{bc}\dot X^b\dot X^c=0.
$$

Multiplying by $g^{ad}$ gives

$$
\ddot X^d+\Gamma^d_{bc}\dot X^b\dot X^c=0,
$$

where

$$
\Gamma^d_{bc}
=
\frac12g^{da}\left(
\partial_bg_{ac}+\partial_cg_{ab}-\partial_ag_{bc}
\right).
$$

Thus the leading dynamics is geodesic motion on $\mathcal M$. The field theory supplies the metric; ordinary mechanics supplies the equation.

## Examples

| Soliton | Typical moduli | Leading dynamics |
|---|---|---|
| Kink in $1+1$ dimensions | Center $X$ | Free particle motion $L=M\dot X^2/2-M$. |
| Domain wall | Position and transverse shape modes | Nambu–Goto-type worldvolume dynamics at long wavelength. |
| BPS vortices | Positions of $N$ vortices, sometimes internal orientations | Geodesic motion on the vortex moduli space. |
| BPS monopoles | Center of mass, phases, relative positions, gauge orientations | Geodesic motion on monopole moduli space; two-monopole scattering is encoded geometrically. |
| Skyrmion | Position, spatial rotations, isorotations | Rigid-body quantum mechanics for collective orientations, plus vibrational corrections. |
| Instanton | Center, size, gauge orientation | Moduli integration in Euclidean path integrals, not ordinary real-time soliton motion. |

The simplest case is a single kink:

$$
\phi_{\rm cl}(x;X)=\phi_K(x-X).
$$

Then

$$
\dot\phi=-\phi_K'(x-X)\dot X.
$$

The metric is

$$
g_{XX}
=
\int dx\,(\phi_K')^2.
$$

For a BPS kink, this equals the kink mass $M$, so

$$
L_{\rm eff}=-M+\frac12M\dot X^2+\cdots.
$$

This is just the nonrelativistic expansion of a relativistic particle with mass $M$. Good: the approximation passes its first sanity check.

## BPS systems and no-force motion

BPS systems are where moduli-space dynamics becomes especially sharp. If a family of multi-soliton configurations all saturate the same BPS bound, their static energy is independent of separation. That means there is no potential on $\mathcal M$ at the BPS level:

$$
V_{\rm eff}(X)=M_{\rm BPS}.
$$

The leading nontrivial dynamics is then kinetic:

$$
L_{\rm eff}
=
-M_{\rm BPS}+\frac12g_{ab}(X)\dot X^a\dot X^b.
$$

For BPS monopoles, this idea is extraordinarily powerful. The moduli space of $k$ monopoles has dimension $4k$ in the simplest $SU(2)$ theory: three position coordinates and one phase-like coordinate for each monopole, after separating global redundancies appropriately. The metric on this space controls low-energy monopole scattering.

For BPS vortices, the moduli include vortex positions in the plane. The absence of static forces at critical coupling means that separated vortices form a continuous family of degenerate solutions. Their slow motion is again governed by a metric, not by an ordinary potential.

This is the conceptual punchline:

$$
\text{BPS no-force condition}
\quad\Longrightarrow\quad
\text{interaction appears as moduli-space geometry}.
$$

## Lifted moduli and effective potentials

Not every collective coordinate remains exactly flat. Perturb the theory away from a BPS point, add a small mass term, introduce finite volume, turn on weak explicit symmetry breaking, or include quantum corrections, and the effective Lagrangian becomes

$$
L_{\rm eff}
=
\frac12g_{ab}(X)\dot X^a\dot X^b
-
V_{\rm eff}(X).
$$

A coordinate that was once a modulus may become a **quasi-modulus**. It changes the energy slowly but not exactly zero. Examples include:

- separation between vortices away from critical coupling;
- instanton size in a theory where scale invariance is broken;
- Skyrmion orientation when symmetry-breaking terms are added;
- wall separation when an equality of tensions is slightly violated;
- internal orientation modes lifted by masses or twisted boundary conditions.

This is often still useful. A weakly lifted modulus gives a controlled low-energy coordinate with a potential. But the word “modulus” should then be used with a warning label.

## Quantization on moduli space

After deriving the classical moduli-space Lagrangian, one can quantize it. The rough rule is

$$
\text{field-theory soliton sector}
\quad\leadsto\quad
\text{quantum mechanics on }\mathcal M.
$$

For a bosonic moduli space with metric $g_{ab}$, the Hamiltonian is schematically

$$
H
=
M
-
\frac12\Delta_{\mathcal M}
+\cdots,
$$

where $\Delta_{\mathcal M}$ is the Laplace–Beltrami operator, up to ordering and measure conventions. If there are fermion zero modes, supersymmetric quantum mechanics on $\mathcal M$ often appears.

This is how collective-coordinate quantization turns classical solitons into quantum multiplets. For example:

- a kink center becomes a particle position;
- Skyrmion orientations become spin and isospin quantum numbers;
- monopole phase coordinates are related to electric charge and dyons;
- fermion zero modes generate degeneracies and selection rules.

The phrase “quantum mechanics on moduli space” sounds harmless, but global issues matter: identifications, orbifold singularities, spin structures, fermion bundles, Berry phases, and boundary behavior can change the spectrum.

## Gauge constraints and normalizability

Two tests decide whether a parameter is a physical modulus.

First, the tangent vector must be normalizable:

$$
\|\delta_a\Phi\|^2
=
g_{aa}<\infty.
$$

If the norm diverges in infinite volume, the parameter is not a finite-energy collective coordinate of a localized object. Global symmetry rotations can fail this test when they disturb fields all the way to infinity.

Second, in gauge theory, the parameter must not be pure gauge. A gauge transformation that dies off suitably at infinity is redundancy, not dynamics. A gauge transformation that approaches a nontrivial global transformation at infinity can sometimes become a physical modulus or charge, depending on the boundary conditions.

This is why gauge-theory moduli spaces require care. The same-looking deformation can be:

| Deformation | Physical status |
|---|---|
| Small gauge transformation | Redundancy; quotient it out. |
| Large or boundary gauge transformation | May label charge, sector, or physical orientation. |
| Normalizable zero mode | Physical collective coordinate. |
| Nonnormalizable zero mode | Usually a change of background or coupling, not a soliton coordinate. |
| Approximate zero mode | Quasi-modulus with an effective potential. |

## Validity of the approximation

The moduli-space approximation is an expansion in small velocities and small accelerations compared with the mass scale of nonzero fluctuations. A useful slogan is

$$
|\dot X|\ll 1,
\qquad
\omega_{\rm motion}\ll m_{\rm gap}^{\rm fluctuation}.
$$

The omitted terms include

$$
O(\dot X^4),
\qquad
O(\ddot X),
\qquad
\text{radiation},
\qquad
\text{massive-mode excitation},
\qquad
\text{quantum-loop corrections}.
$$

The approximation can fail when solitons collide violently, when a modulus reaches a singular region, when massless radiation is important, when the moduli are nonnormalizable, or when there is no gap separating zero modes from other fluctuations.

For BPS systems, the approximation is often better than expected because static forces cancel. For non-BPS systems, a potential and radiation effects usually appear earlier.

## Common pitfalls

**A parameter in an ansatz is not automatically a modulus.** It must label exact static solutions of the same energy, at least before any deliberate lifting.

**Gauge rotations must be projected.** Differentiating a gauge-equivalent family can produce pure gauge zero modes. Physical moduli live on the quotient, with an appropriate background gauge condition.

**Nonnormalizable modes are not soliton coordinates.** Changing the vacuum at infinity, a coupling, or a boundary condition may look like a deformation, but it is not a finite-energy motion of the soliton.

**Geodesic motion is not the full field evolution.** The approximation neglects radiation and massive-mode excitation. It is a low-velocity approximation, not an exact theorem about all soliton scattering.

**Flat potential does not mean flat metric.** BPS solitons can have no static force and still scatter nontrivially because their moduli-space metric is curved.

**Singularities require interpretation.** Coincident solitons, small instantons, or enhanced-symmetry loci can produce singular moduli-space coordinates. The singularity may be physical, removable by better variables, or resolved by quantum effects.

## Relations to other pages

This page is the dynamical continuation of [BPS Bounds](/nonperturbative-qft/solitons-defects-extended-configurations/bps-bounds-preview/). BPS saturation often explains why a multi-soliton family has no static potential; moduli-space dynamics explains how such solitons move.

It also refines the semiclassical machinery introduced in [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/), [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/), [Moduli of Saddles](/nonperturbative-qft/semiclassical-methods/moduli-of-saddles/), and [Semiclassical Quantization](/nonperturbative-qft/semiclassical-methods/semiclassical-quantization/).

Concrete applications appear in [Kinks](/nonperturbative-qft/solitons-defects-extended-configurations/kinks/), [Vortices](/nonperturbative-qft/solitons-defects-extended-configurations/vortices/), [Monopoles](/nonperturbative-qft/solitons-defects-extended-configurations/monopoles/), and [Skyrmions](/nonperturbative-qft/solitons-defects-extended-configurations/skyrmions/). Instanton moduli will return in the Instantons, Tunneling, and Theta Vacua chapter, where moduli are integrated over in Euclidean path integrals rather than evolved in real time.

## Research status

The moduli-space approximation is established for many semiclassical solitons, especially kinks, BPS vortices, BPS monopoles, Skyrmions, and instantons. It is one of the cleanest ways to pass from classical soliton solutions to low-energy quantum dynamics.

Active topics include exact metrics on complicated moduli spaces, singularity resolution, moduli-space quantum mechanics with fermions and Berry phases, non-Abelian vortex dynamics, monopole and dyon spectra, wall crossing, defects in strongly coupled theories, and corrections from radiation and massive modes.

The most durable lesson is geometric: once a soliton has zero modes, its low-energy physics is often encoded not just in its mass, but in the metric, topology, and global structure of the space of solutions.

## Exercises

### Exercise 1: Translation modulus of a kink

Let

$$
\phi(t,x)=\phi_K(x-X(t)).
$$

Show that the kinetic term gives

$$
L_{\rm kin}=\frac12g_{XX}\dot X^2,
\qquad
g_{XX}=\int dx\,(\phi_K')^2.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate the ansatz with respect to time:

$$
\dot\phi(t,x)=-\phi_K'(x-X(t))\dot X.
$$

The kinetic term is

$$
L_{\rm kin}
=
\frac12\int dx\,\dot\phi^2
=
\frac12\dot X^2\int dx\,(\phi_K')^2.
$$

Therefore

$$
g_{XX}=\int dx\,(\phi_K')^2.
$$

For a BPS kink this equals the kink mass in the standard normalization.

</details>

### Exercise 2: Geodesic equation from the moduli Lagrangian

Starting from

$$
L=\frac12g_{ab}(X)\dot X^a\dot X^b,
$$

derive

$$
\ddot X^a+\Gamma^a_{bc}\dot X^b\dot X^c=0.
$$

<details><summary><strong>Solution</strong></summary>

The canonical derivative is

$$
\frac{\partial L}{\partial \dot X^a}=g_{ab}\dot X^b.
$$

Thus

$$
\frac{d}{dt}\frac{\partial L}{\partial \dot X^a}
=
g_{ab}\ddot X^b+\partial_cg_{ab}\dot X^c\dot X^b.
$$

Also

$$
\frac{\partial L}{\partial X^a}
=
\frac12\partial_ag_{bc}\dot X^b\dot X^c.
$$

The Euler–Lagrange equation gives

$$
g_{ab}\ddot X^b+\partial_cg_{ab}\dot X^c\dot X^b
-\frac12\partial_ag_{bc}\dot X^b\dot X^c=0.
$$

Multiplying by $g^{ad}$ and symmetrizing the $b,c$ terms gives

$$
\ddot X^d+\Gamma^d_{bc}\dot X^b\dot X^c=0,
$$

with

$$
\Gamma^d_{bc}=\frac12g^{da}(\partial_bg_{ac}+\partial_cg_{ab}-\partial_ag_{bc}).
$$

</details>

### Exercise 3: A lifted separation modulus

Suppose two solitons have an approximate relative coordinate $R$ with effective Lagrangian

$$
L=\frac12\mu\dot R^2-V_0e^{-mR},
$$

where $V_0>0$. Is $R$ an exact modulus? What force acts at large $R$?

<details><summary><strong>Solution</strong></summary>

It is not an exact modulus because the energy depends on $R$ through

$$
V_{\rm eff}(R)=V_0e^{-mR}.
$$

The force is

$$
F_R=-\frac{dV_{\rm eff}}{dR}=mV_0e^{-mR}.
$$

With this sign convention, positive $F_R$ pushes toward larger $R$, so the interaction is repulsive. The exponential form is typical of massive-field exchange at distances large compared with the core size.

</details>

### Exercise 4: Why a flat potential can still scatter

Explain in one or two equations how two BPS solitons can have no static potential but still scatter nontrivially.

<details><summary><strong>Solution</strong></summary>

No static potential means

$$
L_{\rm eff}=\frac12g_{ab}(X)\dot X^a\dot X^b-M,
$$

with no $V(X)$. But if $g_{ab}(X)$ is not constant, the geodesic equation contains Christoffel terms,

$$
\ddot X^a+\Gamma^a_{bc}\dot X^b\dot X^c=0.
$$

The nonzero connection can bend trajectories on moduli space. Thus scattering can be geometric even when there is no ordinary potential energy.

</details>

## References

- N. Manton and P. Sutcliffe, *Topological Solitons*, for the moduli-space approximation, monopoles, vortices, Skyrmions, and soliton dynamics.
- R. Rajaraman, *Solitons and Instantons*, for collective coordinates and elementary soliton quantization.
- S. Coleman, *Aspects of Symmetry*, for the semiclassical logic behind collective coordinates and soliton quantization.
- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the chapters on kinks, vortices, monopoles, supersymmetric solitons, and central charges.
- M. Atiyah and N. Hitchin, *The Geometry and Dynamics of Magnetic Monopoles*, for the classic geometric treatment of monopole moduli-space dynamics.

## Version history

- **2026-06-27:** Initial polished preview page, added after BPS Bounds in the solitons and defects chapter.
