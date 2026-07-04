---
title: "Moduli of Saddles"
description: "Explains the moduli space of semiclassical saddle solutions, its tangent zero modes, quotient by gauge redundancies, induced measure, boundaries, and effective dynamics."
sidebar:
  label: "Moduli of Saddles"
  order: 5
level: Graduate
status: "Polished draft"
source: "Coleman; Mariño, ch. 4; Shifman, chs. 4–5 and 10–11; Nakahara."
topics:
  - moduli space
  - saddle points
  - collective coordinates
  - zero modes
  - gauge quotient
  - semiclassical measure
canonicalTopics:
  - nonperturbative-qft
  - semiclassical-methods
  - moduli-of-saddles
  - collective-coordinates
  - gauge-quotient
researchStatus:
  established:
    - "The local tangent space to a smooth moduli space of saddles is the space of normalizable bosonic zero modes modulo gauge redundancies."
  active:
    - "Singular moduli spaces, noncompact size moduli, quasi-moduli, wall crossing, and quantum-corrected moduli-space dynamics are model-dependent and often research-level topics."
---

## Summary

A **moduli space of saddles** is the space of classical solutions that contribute to a given semiclassical expansion, after quotienting by redundancies. If $\theta_s(\gamma)$ is a family of Euclidean saddles, the parameters $\gamma^a$ are **moduli** only when they label genuinely distinct saddle configurations in the same path integral.

The local picture is

$$
\mathcal M_s
=
\{\theta:\delta S_E[\theta]=0\text{ with chosen boundary data}\}/\text{redundancies}.
$$

At a smooth point $[\theta_s]\in\mathcal M_s$, tangent vectors are zero modes modulo gauge directions:

$$
T_{[\theta_s]}\mathcal M_s
\simeq
\frac{\ker\Delta_s\cap\text{normalizable modes}}{\text{infinitesimal gauge directions}}.
$$

The induced metric

$$
G_{ab}=(\partial_a\theta_s,\partial_b\theta_s)
$$

gives the bosonic moduli measure

$$
d\mu_{\mathcal M}
=
\frac{d^k\gamma}{(2\pi\hbar)^{k/2}}\sqrt{\det G(\gamma)},
$$

locally and away from singularities. This is the geometric version of the collective-coordinate Jacobian.

<figure class="doc-figure" style="--figure-width: 50rem;">

![A schematic moduli space of saddles obtained by quotienting a solution family by gauge redundancies, with tangent zero modes, normal fluctuations, boundaries, and singular points.](/figures/nonperturbative-qft/moduli-of-saddles-quotient.svg)

<figcaption>

A moduli space of saddles is not merely a list of parameters. One first fixes the boundary-value problem, then quotients by redundancies. Tangent directions are physical zero modes; normal directions contribute determinants; boundaries and singular points often signal infrared effects, coincident saddles, or breakdown of a naive semiclassical approximation.

</figcaption>
</figure>

This page is about the geometry behind collective coordinates. The previous page explained how zero modes appear. This page explains what they are coordinates **of**.

## Prerequisites

You should know [Saddle-Point Expansion](/nonperturbative-qft/semiclassical-methods/saddle-point-expansion/), [Collective Coordinates](/nonperturbative-qft/semiclassical-methods/collective-coordinates/), and [Zero Modes](/nonperturbative-qft/semiclassical-methods/zero-modes/). For gauge examples, review [Wilson Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/wilson-loop-diagnostics/) and [Topological Susceptibility](/nonperturbative-qft/order-parameters-diagnostics/topological-susceptibility/).

The mathematical language of tangent spaces, quotients, and metrics is used in a practical way. No algebraic geometry is assumed.

## Core idea

A semiclassical contribution is local in field space but often global in ordinary space. A saddle may be localized at any position, have any phase, choose an internal orientation, or come in a multi-soliton family. If these choices cost no action, the path integral should integrate over them.

The correct object is not the parameter list chosen by the author of a paper. It is the solution space with redundancies removed.

A useful schematic formula is

$$
Z_{\mathcal M}
\sim
\int_{\mathcal M_s}d\mu_{\mathcal M}
\,e^{-S_E[\theta_s]/\hbar}
\left(\det{}^{\prime}\Delta_s\right)^{-1/2}
\left(1+O(\hbar)\right).
$$

If $S_E$ is constant on $\mathcal M_s$, then the exponential can be pulled out. If quantum corrections or weak interactions lift the moduli, $S_E$ must be replaced by an effective action on $\mathcal M_s$.

## What counts as a modulus

A parameter $\gamma$ is a modulus if all of the following are true:

1. $\theta_s(\gamma)$ solves the same saddle equations.
2. It obeys the same boundary conditions or belongs to the same finite-volume path integral.
3. It is not removable by a redundancy, such as a small gauge transformation.
4. The corresponding tangent vector is normalizable, unless the problem explicitly treats a nonlocal collective coordinate.
5. It is integrated over in the semiclassical approximation.

A coupling constant is not a modulus. A source is not a modulus. A boundary condition is not a modulus. A gauge parameter is not a physical modulus. This sounds fussy, but it prevents several classic semiclassical faceplants.

For example, the instanton center $x_0$ is a modulus because translating an instanton gives another solution in the same theory. The gauge coupling $g$ is not a modulus because changing $g$ changes the theory. A pure gauge transformation that approaches the identity at infinity is not a modulus because it does not change the physical configuration. A global gauge orientation may be a modulus if it changes the embedding of the instanton in a way not quotiented by the allowed gauge group.

## Local tangent space

Let $\mathcal F$ be the field configuration space and let $\mathcal S\subset\mathcal F$ be the set of solutions to the saddle equations. At a smooth solution $\theta_s$, the tangent space to $\mathcal S$ is the kernel of the linearized equations:

$$
T_{\theta_s}\mathcal S=\ker\Delta_s.
$$

If the theory has gauge symmetry, infinitesimal gauge transformations form directions

$$
\delta_\omega\theta_s=\mathcal G_{\theta_s}\omega,
$$

where $\mathcal G_{\theta_s}$ is the linearized gauge action. These directions should be divided out. Locally,

$$
T_{[\theta_s]}\mathcal M_s
\simeq
\frac{\ker\Delta_s}{\operatorname{im}\mathcal G_{\theta_s}},
$$

with the additional restriction that tangent vectors obey the chosen gauge-fixing condition and are normalizable.

In a background gauge, one imposes an orthogonality condition of the schematic form

$$
\mathcal G_{\theta_s}^{\dagger}Z=0.
$$

For gauge fields this often becomes

$$
D_s^\mu Z_\mu=0.
$$

The physical zero modes are not arbitrary derivatives of a parametrized solution. They are derivatives projected into this slice.

## Induced metric and measure

The field-space inner product induces a metric on the moduli space. If $\theta_s(\gamma)$ is a local coordinate patch, define

$$
Z_a=\frac{\partial\theta_s}{\partial\gamma^a}
$$

after projection orthogonal to gauge directions. The metric is

$$
G_{ab}(\gamma)=(Z_a,Z_b).
$$

For a scalar field in flat Euclidean space,

$$
G_{ab}=\int d^dx\,
\frac{\partial\phi_s(x;\gamma)}{\partial\gamma^a}
\frac{\partial\phi_s(x;\gamma)}{\partial\gamma^b}.
$$

For gauge fields, one uses the gauge-field kinetic inner product, including group traces and any coupling-dependent normalization. For fermionic moduli in supersymmetric problems, the measure is a Berezin measure and the metric is replaced by the appropriate supermetric or Berezinian.

The local bosonic measure is

$$
d\mu_{\mathcal M}
=
\frac{d^k\gamma}{(2\pi\hbar)^{k/2}}\sqrt{\det G(\gamma)}.
$$

This expression is coordinate-invariant: under a change of coordinates $\gamma\mapsto\gamma'$, the factor $d^k\gamma\sqrt{\det G}$ transforms as a volume form.

The full one-loop expression normally contains determinant ratios:

$$
Z_{\mathcal M}
\sim
\int_{\mathcal M_s}d\mu_{\mathcal M}\,
 e^{-S_E[\theta_s]/\hbar}
\left(\frac{\det\Delta_{\mathrm{ref}}}{\det{}^{\prime}\Delta_s}\right)^{1/2}
\times
\text{ghosts}\times\text{fermions}.
$$

The reference determinant and normalization depend on the observable and on how vacuum amplitudes are divided out.

## Examples

### Kink center

A static kink in one spatial dimension has a center $z_0$:

$$
\phi_k(z-z_0).
$$

The moduli space for one isolated kink is

$$
\mathcal M_{\mathrm{kink}}\simeq\mathbb R,
$$

at least before putting the system in a box. The tangent zero mode is

$$
Z_{z_0}=-\partial_z\phi_k.
$$

In Lorentzian dynamics, $z_0(t)$ becomes the position of a massive particle. The leading effective Lagrangian is

$$
L_{\mathrm{eff}}
=
-M_k+\frac12M_k\dot z_0^2+\cdots,
$$

where $M_k$ is the kink mass. The translational modulus has become the center-of-mass degree of freedom.

### Euclidean instanton center

A localized Euclidean instanton has a center $x_0$. In infinite flat space,

$$
\mathcal M_{\mathrm{center}}\simeq\mathbb R^d.
$$

The integral over $x_0$ produces a spacetime-volume factor in vacuum amplitudes. This is not a mistake. It reflects the fact that the instanton event can occur anywhere. When extracting an intensive quantity, such as an energy shift or vacuum energy density, this volume factor cancels against the total spacetime volume.

### Yang–Mills instanton moduli

A charge-one Yang–Mills instanton in four Euclidean dimensions has moduli that include a center $x_0^\mu$, a size $\rho$, and gauge-orientation data. In $SU(2)$ this gives eight bosonic collective coordinates:

$$
4\text{ centers}+1\text{ size}+3\text{ orientations}.
$$

For $SU(N)$, the embedding of the instantonic $SU(2)$ into $SU(N)$ adds more orientation moduli. These moduli are physical only after correctly quotienting by gauge transformations and imposing the gauge condition on zero modes.

The size modulus $\rho$ is famously subtle. In a classically scale-invariant theory, the classical action is independent of $\rho$, but the integral over $\rho$ can diverge in the infrared or ultraviolet depending on the theory and regulator. The existence of a classical modulus does not guarantee a well-behaved semiclassical integral.

### Multi-soliton and multi-instanton moduli

A two-soliton configuration may have two positions, a relative phase, and internal orientations. At large separation these look like independent one-soliton moduli. At short separation the moduli space can be curved, singular, or require a different coordinate patch.

Multi-instanton moduli spaces are even more delicate. Coincident instantons often lie at singular loci of naive parameterizations. A good moduli-space description must account for the quotient structure and for possible boundary strata. In practical physics, one often works in a dilute-gas region where the saddles are well separated and the approximate moduli are easier to interpret.

## Boundaries and singularities

A moduli space need not be compact or smooth. Its boundaries and singularities are often where the simple semiclassical approximation breaks.

| Feature | Physical meaning | Typical consequence |
|---|---|---|
| Translation to infinity | Saddle moves out of the region of interest. | Volume factors or cluster decomposition. |
| Size $\rho\to 0$ | UV region of the saddle. | Sensitivity to running couplings or UV completion. |
| Size $\rho\to\infty$ | IR spreading of the saddle. | Infrared divergence or breakdown of dilute approximation. |
| Coincident saddles | Multiple defects overlap. | Singular coordinates or strong interactions. |
| Quotient fixed point | Stabilizer subgroup grows. | Orbifold-like singularity. |
| Non-normalizable direction | Boundary data changes. | Not integrated as an ordinary modulus. |

A clean semiclassical page should never simply write $\int_{\mathcal M}d\mu$ and walk away. It should ask whether the integral converges and what happens near the edges.

## Exact moduli versus quasi-moduli

Exact moduli come from exact degeneracies of the classical action. Quasi-moduli are parameters that become moduli only in an approximation.

A common example is the separation $R$ between an instanton and anti-instanton. At large $R$ the pair is approximately a two-saddle configuration, but it is not generally an exact solution for arbitrary $R$. The interaction produces an effective potential

$$
S_{I\bar I}(R)=2S_I+V_{I\bar I}(R)+\cdots.
$$

Then $R$ should be treated as a quasi-collective coordinate, with an effective integral

$$
\int dR\,J(R)\,e^{-S_{I\bar I}(R)/\hbar},
$$

not as an exact zero-mode Gaussian replacement.

The same issue appears for constrained instantons, finite-temperature calorons, nearly BPS solitons, weakly broken symmetries, and collective coordinates lifted by quantum corrections. The more a calculation depends on quasi-moduli, the more important it is to state the approximation.

## Effective dynamics on moduli space

For Lorentzian solitons, moduli can become slowly varying functions of time. Insert

$$
\theta(x,t)=\theta_s(x;\gamma(t))
$$

into the action and expand in time derivatives. The leading low-energy effective action is often geodesic motion on moduli space:

$$
L_{\mathrm{eff}}
=
-M+\frac12G_{ab}(\gamma)\dot\gamma^a\dot\gamma^b+\cdots.
$$

This is not merely a trick. It is the field-theoretic origin of moduli-space quantum mechanics. Quantizing this effective system gives spin, flavor, electric charge, bound states, and multiplet structure in many soliton problems.

For Euclidean instantons, the moduli are usually integrated rather than time-evolved. For BPS solitons, the same geometry can appear in both ways: as an instanton measure in Euclidean calculations and as a low-energy sigma model for slow soliton motion.

## Gauge quotient in practice

Gauge theories require two separate operations:

$$
\text{solve equations}\quad\text{and}\quad\text{divide by gauge redundancy}.
$$

Doing them in the wrong order can produce fake moduli.

A practical approach is:

1. choose a representative saddle $A_s(\gamma)$;
2. differentiate with respect to candidate moduli;
3. add a compensating gauge transformation so that the zero mode satisfies background gauge;
4. compute the inner products of the gauge-fixed zero modes;
5. divide by residual gauge transformations that act trivially on physical data;
6. integrate over the remaining physical coordinates.

In equations, the corrected zero mode has the form

$$
Z_{a\mu}=\partial_a A_{s\mu}-D_{s\mu}\omega_a,
$$

with

$$
D_s^\mu Z_{a\mu}=0.
$$

The correction $D_s\omega_a$ is not optional bookkeeping. It determines the metric and hence the measure.

## How moduli integrals fail

When a moduli integral diverges, the divergence is usually telling you something physical.

A translation divergence usually reflects spacetime volume. A global orientation divergence reflects a finite or infinite group volume that must be normalized consistently. A large-size instanton divergence can signal infrared physics beyond semiclassical control. A small-size divergence may signal UV sensitivity and the need for renormalization or for a UV completion. A coincident-defect divergence may mean the dilute-gas approximation has left its domain.

The right response is not always “regularize and continue.” Sometimes the correct conclusion is that the saddle expansion does not define the observable by itself.

## Common mistakes

**Mistake 1: confusing coordinates with geometry.** A bad coordinate patch can make a smooth moduli space look singular, and a good-looking parameter list can hide a quotient singularity.

**Mistake 2: forgetting the quotient.** Gauge-equivalent solutions are not distinct saddles. Integrating over them double-counts.

**Mistake 3: assuming every zero mode gives a finite factor.** Noncompact moduli spaces often produce divergent integrals. The divergence must be interpreted.

**Mistake 4: treating quasi-moduli as exact moduli.** If the action varies along the parameter, include the effective potential.

**Mistake 5: ignoring boundaries.** Many important semiclassical effects are controlled by the edge of moduli space, not its generic points.

**Mistake 6: using the moduli-space approximation outside its speed limit.** Lorentzian moduli dynamics assumes slow motion compared with massive fluctuation scales.

## Exercises

### Exercise 1: Coordinate invariance of the moduli measure

Show that $d^k\gamma\sqrt{\det G(\gamma)}$ is invariant under a smooth change of coordinates $\gamma^a\mapsto\gamma'^a(\gamma)$.

<details><summary><strong>Solution</strong></summary>

Let

$$
J^a{}_{b}=\frac{\partial\gamma^a}{\partial\gamma'^b}.
$$

The metric transforms as

$$
G'_{ab}=J^c{}_{a}J^d{}_{b}G_{cd},
$$

so

$$
\det G'=(\det J)^2\det G.
$$

The coordinate volume transforms as

$$
d^k\gamma=|\det J|\,d^k\gamma'.
$$

Equivalently,

$$
d^k\gamma'\sqrt{\det G'}
=d^k\gamma'|\det J|\sqrt{\det G}
=d^k\gamma\sqrt{\det G}.
$$

Thus the moduli-space volume form is coordinate-invariant.

</details>

### Exercise 2: Kink moduli-space metric

Let $\phi_k(z-z_0)$ be a kink with mass

$$
M_k=\int dz\left[\frac12(\partial_z\phi_k)^2+V(\phi_k)-V(\phi_{\mathrm{vac}})\right].
$$

For a BPS or first-order kink satisfying $\frac12(\partial_z\phi_k)^2=V(\phi_k)-V(\phi_{\mathrm{vac}})$, show that the metric on the one-dimensional moduli space is $G_{z_0z_0}=M_k$.

<details><summary><strong>Solution</strong></summary>

The tangent vector is

$$
Z_{z_0}=\frac{\partial\phi_k(z-z_0)}{\partial z_0}=-\partial_z\phi_k.
$$

Therefore

$$
G_{z_0z_0}=\int dz\,Z_{z_0}^2
=\int dz\,(\partial_z\phi_k)^2.
$$

For a first-order kink,

$$
\frac12(\partial_z\phi_k)^2=V(\phi_k)-V(\phi_{\mathrm{vac}}),
$$

so

$$
M_k=\int dz\left[\frac12(\partial_z\phi_k)^2+\frac12(\partial_z\phi_k)^2\right]
=\int dz\,(\partial_z\phi_k)^2.
$$

Hence

$$
G_{z_0z_0}=M_k.
$$

</details>

### Exercise 3: Gauge quotient tangent space

Suppose a gauge-field saddle has a candidate deformation $\partial_aA_{s\mu}$. Explain why the physical zero mode is generally $Z_{a\mu}=\partial_aA_{s\mu}-D_{s\mu}\omega_a$ rather than $\partial_aA_{s\mu}$.

<details><summary><strong>Solution</strong></summary>

Gauge-equivalent fluctuations should not be counted as physical tangent directions. To define the tangent vector to the quotient space, one chooses a gauge slice, often background gauge:

$$
D_s^\mu Z_{a\mu}=0.
$$

The raw derivative $\partial_aA_{s\mu}$ need not lie in this slice. Adding an infinitesimal gauge transformation $-D_{s\mu}\omega_a$ moves it along the gauge orbit without changing the physical deformation. The function $\omega_a$ is chosen so that the corrected tangent vector satisfies the gauge condition. This corrected vector is the one that enters the moduli-space metric and the semiclassical measure.

</details>

## References

- Coleman, *Aspects of Symmetry*, for semiclassical reasoning, soliton quantization, and false-vacuum decay.
- Mariño, *Instantons and Large N*, especially ch. 4, for Yang–Mills instanton moduli, zero modes, and determinant measures.
- Shifman, *Advanced Topics in Quantum Field Theory*, chs. 4–5 and 10–11, for monopole, instanton, vortex, and supersymmetric moduli-space examples.
- Nakahara, *Geometry, Topology and Physics*, for quotient spaces, bundles, and index-theorem background.
- Frankel, *The Geometry of Physics*, for differential-geometric language used in gauge theory and moduli-space constructions.

## Version history

- 2026-06-26: Initial polished draft.
