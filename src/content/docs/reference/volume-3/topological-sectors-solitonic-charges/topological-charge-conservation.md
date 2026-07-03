---
title: "Topological Charge Conservation"
description: "Explains why topological charges are conserved, including homotopy classes, closed topological currents, pullbacks of closed forms, boundary flux, singular events, defect endpoints, gauge caveats, and instanton-related exceptions."
sidebar:
  label: "Topological Charge Conservation"
  order: 9
level: Graduate
status: "Polished draft"
source: "Nakahara Chs. 4, 6, 10, and 11; Frankel on differential forms and Stokes's theorem; Srednicki §§92–93; Polyakov Chs. 4 and 6; Coleman on solitons and instantons; Gaiotto–Kapustin–Seiberg–Willett on generalized symmetries."
topics:
  - topological charge
  - topological currents
  - conservation laws
  - homotopy classes
  - Stokes theorem
  - solitons
  - defects
  - instantons
canonicalTopics:
  - topological-charge
  - topological-current
  - homotopy-invariance
  - closed-current
  - defect-endpoint
  - boundary-flux
researchStatus:
  established:
    - "Topological charges are conserved when time evolution is a continuous deformation inside a fixed configuration space with fixed boundary conditions and no singularities or endpoint sources."
    - "Many topological charges admit identically conserved currents built from pullbacks of closed forms or from Bianchi identities."
  active:
    - "In gauge theories, generalized symmetries, anomalous systems, and theories with boundaries, the precise conservation statement depends on global form, allowed defects, background fields, boundary conditions, and whether charged objects can end."
---

## Summary

A topological charge is conserved because a continuous time evolution cannot change a topological class unless something leaves the assumed configuration space. The cleanest slogan is

$$
\text{topological conservation} = \text{homotopy invariance} + \text{boundary conditions}.
$$

In current language, a topological charge is often written as

$$
Q(\Sigma)=\int_\Sigma J,
$$

where $J$ is a closed form or conserved current:

$$
dJ=0
\qquad\text{or}\qquad
\partial_\mu j^\mu=0.
$$

Then Stokes's theorem gives surface independence:

$$
Q(\Sigma_2)-Q(\Sigma_1)=\int_M dJ=0,
$$

provided the region $M$ between $\Sigma_1$ and $\Sigma_2$ has no boundary flux, singularities, or endpoint sources.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Diagram showing a closed topological current, deformation invariance of a linking surface, and ways topological charge can change through boundary flux, endpoints, or singular events.](/figures/symmetry-anomalies-topology/topological-charge-conservation.svg)

<figcaption>

Topological charges are conserved by deformation invariance. They can change only if the assumptions fail: charge crosses a boundary, a defect has an endpoint, a singular event occurs, or the physical configuration space has been enlarged.

</figcaption>
</figure>

This is not the same mechanism as an ordinary Noether charge. A Noether current is conserved because of an equation of motion and a continuous symmetry. A topological current is often conserved identically, or by a Bianchi identity, before using the dynamical equations of motion.

## Prerequisites

You should know [Topology of Field Configurations](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/topology-of-field-configurations/), [Homotopy Classification](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/homotopy-classification/), [Winding Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/winding-number/), [Vortices](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/vortices/), [Monopoles](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/monopoles/), [Instanton Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/instanton-number/), and [Domain Walls](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/domain-walls/).

Useful structural background includes [Noether Currents](/symmetry-anomalies-topology/noether-currents-ward-identities/noether-currents/), [Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/), and [Background Fields for Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/background-fields-for-higher-form-symmetries/).

## Core idea

Topological charge conservation can be explained in two equivalent languages.

The first language is homotopy. A static finite-energy field configuration is a map from a compactified space or linking sphere into a target space. Time evolution gives a one-parameter family of maps. If the family is continuous and the boundary conditions are fixed, then the maps at early and late time are homotopic. Homotopic maps have the same topological invariant.

The second language is currents. Many topological invariants can be written as integrals of closed differential forms. If

$$
dJ=0,
$$

then the charge

$$
Q(\Sigma)=\int_\Sigma J
$$

is unchanged when $\Sigma$ is deformed without crossing a source or boundary.

These are the same idea. Homotopy invariance is the global statement; closed-current conservation is the local differential statement.

## Setup and conventions

Let spacetime have dimension $D=d+1$. A conserved ordinary current $j^\mu$ can be repackaged as a $d$-form

$$
J=*j.
$$

Then

$$
\partial_\mu j^\mu=0
\qquad\Longleftrightarrow\qquad
dJ=0.
$$

The charge on a spatial slice $\Sigma_d$ is

$$
Q(\Sigma_d)=\int_{\Sigma_d} J.
$$

If $\Sigma_1$ and $\Sigma_2$ bound a spacetime region $M$ and there is no side boundary contribution, Stokes's theorem gives

$$
Q(\Sigma_2)-Q(\Sigma_1)
=\int_{\Sigma_2}J-\int_{\Sigma_1}J
=\int_{\partial M}J
=\int_M dJ
=0.
$$

When there is a side boundary $B$, the same calculation gives

$$
Q(\Sigma_2)-Q(\Sigma_1)=-\int_B J.
$$

So a conserved current does not say charge cannot leave the room. It says charge cannot disappear in the bulk unless there is a source.

:::note[Convention-sensitive source note]
Signs in the Stokes formula depend on the orientation assigned to $M$, $\Sigma_1$, $\Sigma_2$, and any side boundary. This page uses the convention $\partial M=\Sigma_2\sqcup(-\Sigma_1)\sqcup B$, so the displayed side-flux sign follows from moving the $B$ term to the other side.
:::

## Topological versus Noether conservation

Noether conservation has the schematic form

$$
\text{continuous symmetry} \quad\Rightarrow\quad \partial_\mu j^\mu=0
\quad \text{on shell}.
$$

The phrase “on shell” matters. The equations of motion are used.

Topological conservation often has the form

$$
\partial_\mu j^\mu_{\rm top}=0
$$

as an identity for smooth fields satisfying the target-space constraint. No continuous symmetry need be present. The current is usually built from antisymmetrized derivatives, so its divergence vanishes by $d^2=0$ or by antisymmetry.

This is why topological charges can survive deformations of the Lagrangian that preserve the configuration space and boundary conditions. Their conservation does not depend on a special continuous symmetry of the action.

That said, the boundary between the two ideas can blur. Magnetic flux conservation in Maxwell theory is topological from the Bianchi identity $dF=0$, but in the modern language it is also the conservation law of a one-form symmetry. In dual variables, a topological current can become a Noether current. Physics enjoys moving furniture around.

## Example: kink charge in 1+1 dimensions

For a real scalar with vacua $\phi=\pm v$, define

$$
j^\mu_{\rm kink}={1\over2v}\epsilon^{\mu\nu}\partial_\nu\phi,
\qquad
\epsilon^{01}=+1.
$$

Then

$$
\partial_\mu j^\mu_{\rm kink}
={1\over2v}\epsilon^{\mu\nu}\partial_\mu\partial_\nu\phi=0.
$$

The charge is

$$
Q=\int_{-\infty}^{+\infty}dx\,j^0
={1\over2v}\int_{-\infty}^{+\infty}dx\,{d\phi\over dx}
={\phi(+\infty)-\phi(-\infty)\over2v}.
$$

A kink has $Q=+1$, an anti-kink has $Q=-1$, and a configuration with the same vacuum at both ends has $Q=0$.

This current is conserved for any smooth $\phi$. The quantization of $Q$, however, also uses boundary conditions: $\phi(\pm\infty)$ must lie in the vacuum set $\{-v,+v\}$.

## Example: sigma-model topological charge in 2+1 dimensions

Let

$$
\mathbf n(x)=(n^1,n^2,n^3),
\qquad
\mathbf n\cdot\mathbf n=1.
$$

A standard topological current in $2+1$ dimensions is

$$
j^\mu={1\over8\pi}\epsilon^{\mu\nu\rho}
\epsilon_{abc}n^a\partial_\nu n^b\partial_\rho n^c.
$$

The charge on a spatial slice is

$$
Q={1\over4\pi}\int d^2x\,
\mathbf n\cdot(\partial_1\mathbf n\times\partial_2\mathbf n).
$$

If $\mathbf n\to \mathbf n_0$ at spatial infinity, then space compactifies to $S^2$. The field is a map

$$
S^2_{\rm space}\to S^2_{\rm target},
$$

and

$$
Q\in\pi_2(S^2)=\mathbb Z.
$$

The current is identically conserved for smooth maps into $S^2$. If the constraint $\mathbf n^2=1$ fails at a point, the argument can fail; that point is a possible event where topological charge is created or destroyed in an enlarged theory.

## Example: Skyrmion baryon current in 3+1 dimensions

For a chiral field

$$
U(x)\in SU(2),
$$

define

$$
L_\mu=U^{-1}\partial_\mu U.
$$

A common convention for the Skyrmion current is

$$
B^\mu=-{1\over24\pi^2}\epsilon^{\mu\nu\rho\sigma}
\operatorname{tr}(L_\nu L_\rho L_\sigma).
$$

Then

$$
\partial_\mu B^\mu=0
$$

for smooth $U$. The charge

$$
B=\int d^3x\,B^0
$$

is the degree of

$$
U:S^3_{\rm space}\to SU(2)\simeq S^3.
$$

In the chiral effective theory of QCD, this degree is interpreted as baryon number. That interpretation is physical input, not just topology: the same integer is present mathematically in any model with the same target-space topology.

## Pullback of a closed form

A compact way to generate topological currents is this. Let

$$
\Phi:M\to X
$$

be a field valued in a target space $X$. Let $\omega$ be a closed $p$-form on $X$:

$$
d_X\omega=0.
$$

Then the pullback

$$
J=\Phi^*\omega
$$

is closed on spacetime:

$$
d_M J=d_M\Phi^*\omega=\Phi^*(d_X\omega)=0.
$$

Charges are integrals over $p$-cycles:

$$
Q(C_p)=\int_{C_p}\Phi^*\omega.
$$

If $\omega$ has integral periods, these charges are quantized on closed cycles. The $O(3)$ sigma-model charge uses the normalized area form on $S^2$. The Skyrmion charge uses the normalized volume form on $S^3\simeq SU(2)$.

This is the differential-form heart of many “topological current” formulas. The current looks complicated in components because the pullback of a volume form has many antisymmetrized derivatives.

## Bianchi identities and magnetic charges

Gauge theory supplies another family of topological conservation laws. In ordinary electromagnetism without magnetic monopoles,

$$
dF=0.
$$

This is the Bianchi identity. It implies conservation of magnetic flux. In four spacetime dimensions, the two-form current

$$
J_m={1\over2\pi}F
$$

is closed:

$$
dJ_m=0.
$$

The magnetic charge through a closed two-surface $S^2$ is

$$
Q_m={1\over2\pi}\int_{S^2}F.
$$

If magnetic monopoles are allowed, then

$$
dF=2\pi J_{\rm monopole},
$$

schematically. The monopole worldline is a source for magnetic flux. Again, charge conservation did not fail mysteriously. The current became non-closed because an allowed charged object was included.

This is the bridge to higher-form symmetries: a closed $(d-p)$-form current defines a $p$-form symmetry, and its charge is measured on a linking surface.

## How topological charge can change

A topological charge is conserved only relative to assumptions. The most common failure modes are the following.

### Boundary flux

If a soliton leaves the spatial region, the charge inside the region changes:

$$
Q(t_2)-Q(t_1)=-\int_{B}J.
$$

This is ordinary conservation with flux through a boundary.

### Singular configurations

A winding number is conserved under smooth deformations. If the field becomes singular, or if the field leaves the vacuum manifold or target constraint, the homotopy classification may no longer apply.

For example, the phase winding of a superfluid vortex is protected only where the order parameter is nonzero. At the vortex core, the order parameter can vanish and the phase is undefined. This is not a bug; it is exactly how the topology is physically realized.

### Defect endpoints

If a defect is allowed to end on another defect, the corresponding current is not closed at the endpoint. A string ending on a wall, or a flux tube ending on a monopole, is a source relation between defects.

A schematic conservation equation is

$$
dJ_{\rm string}=J_{\rm endpoint}.
$$

The precise degrees of the forms depend on spacetime dimension and on the defect dimension.

### Enlarged configuration space

A charge may be conserved in an effective theory but not in the microscopic theory. For instance, a nonlinear sigma model constrains the field to a target manifold. A UV completion may include radial modes that allow the field to pass through the origin, where the target-space description breaks down. Then the sigma-model winding can unwind.

This is why one should always ask: conserved in which theory, with which allowed configurations?

### Explicit breaking or lifted vacua

If a topological classification used exact degenerate vacua and an explicit perturbation lifts those vacua, then the old domain-wall charge may no longer label stable sectors. The wall may feel pressure and disappear dynamically.

### Gauge quotient and global form

Gauge-equivalent configurations are not distinct physical configurations. A topological charge computed before quotienting by gauge redundancy can overcount. Conversely, the global form of the gauge group can refine which bundles, line operators, and fluxes are allowed.

### Euclidean tunneling and instantons

Instantons do not usually violate a topological conservation law inside a fixed Euclidean configuration. Rather, they describe finite-action Euclidean histories connecting different classical Lorentzian sectors, such as vacua with different Chern–Simons number. The gauge-invariant Euclidean instanton number is itself a topological charge of the whole four-dimensional configuration:

$$
k={1\over8\pi^2}\int\operatorname{tr}(F\wedge F).
$$

So the right statement is not “instantons violate topology.” The right statement is that Euclidean spacetime topology can mediate transitions between quantities that looked separately conserved in a lower-dimensional or semiclassical description.

## Quantization is separate from conservation

A current can be conserved without its charge being quantized. Quantization requires global input: compact target spaces, integral cohomology classes, flux quantization, boundary conditions, or bundle topology.

For example,

$$
j^\mu={1\over2v}\epsilon^{\mu\nu}\partial_\nu\phi
$$

is identically conserved for any smooth real scalar. But

$$
Q={\phi(+\infty)-\phi(-\infty)\over2v}
$$

is an integer only if the endpoints are restricted to $\pm v$.

Likewise, $dF=0$ says magnetic flux is conserved, while Dirac quantization says the allowed fluxes are quantized. These are related but distinct statements.

## Topological charges and generalized symmetries

Modern QFT often treats topological charge conservation as a generalized symmetry. A $p$-form global symmetry has topological charge operators supported on codimension-$(p+1)$ surfaces. These surfaces can be deformed freely unless they cross charged operators.

For ordinary particle-number symmetry, the charge is measured on a codimension-one time slice. For a one-form symmetry in four dimensions, the charge can be measured on a two-dimensional surface linking a line operator. The common feature is topological deformability of the charge operator.

Thus many older topological conservation laws have a modern reinterpretation:

$$
\text{closed current}
\quad\Longleftrightarrow\quad
\text{topological charge operator}
\quad\Longleftrightarrow\quad
\text{generalized symmetry}.
$$

Not every topological charge automatically defines a nontrivial global symmetry of the quantum theory. One must check which operators are genuine, which defects are dynamical, what the boundary conditions are, and whether gauging or summing over sectors removes the charge.

## Common pitfalls

**Mistake 1: Treating topological conservation as magic.**  It is Stokes's theorem, homotopy invariance, or a Bianchi identity, plus assumptions.

**Mistake 2: Forgetting boundary flux.**  Conservation in a closed system does not imply conservation inside an open subregion.

**Mistake 3: Ignoring singularities.**  Winding cannot change through smooth deformations, but it can change if the field becomes undefined or leaves the target space.

**Mistake 4: Confusing conservation with quantization.**  A current may be closed while its charge is not integer-valued. Quantization needs global input.

**Mistake 5: Overcounting gauge copies.**  Topological classes of fields before quotienting by gauge transformations may not be physical sectors.

**Mistake 6: Saying instantons break topology.**  Instantons are themselves topological Euclidean configurations. They can mediate transitions between semiclassical sectors, but the total Euclidean topological number remains meaningful.

## Relations to other pages

[Domain Walls](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/domain-walls/) provide the simplest current $j^\mu\propto\epsilon^{\mu\nu}\partial_\nu\phi$.

[Vortices](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/vortices/) illustrate conservation by phase winding and show how the order parameter can vanish at a core.

[Monopoles](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/monopoles/) connect topological charge to magnetic flux, bundle data, and Bianchi identities.

[Instanton Number](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/instanton-number/) explains how Euclidean topological charge labels tunneling histories and theta-sector weights.

[Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) generalizes the same surface-deformation logic to charged extended operators.

## Research status

The basic conservation logic is settled: smooth deformation preserves homotopy class, and closed currents give surface-independent charges by Stokes's theorem.

The active issues are in the interpretation. In strongly coupled QFT, one must decide which defects are genuine, which are dynamical, whether topological sectors are summed over, which background fields are allowed, and whether a putative charge survives gauging, boundaries, anomalies, or quantum effects. These questions are central in generalized symmetry, topological order, anomaly inflow, and modern phase classification.

## Exercises

### Exercise 1: Kink current conservation

For

$$
j^\mu={1\over2v}\epsilon^{\mu\nu}\partial_\nu\phi,
$$

show that $\partial_\mu j^\mu=0$ identically.

<details><summary><strong>Solution</strong></summary>

Compute

$$
\partial_\mu j^\mu
={1\over2v}\epsilon^{\mu\nu}\partial_\mu\partial_\nu\phi.
$$

The derivative $\partial_\mu\partial_\nu\phi$ is symmetric in $\mu,\nu$ for smooth $\phi$, while $\epsilon^{\mu\nu}$ is antisymmetric. Their contraction vanishes.

</details>

### Exercise 2: Kink charge from boundary values

Use the same current to show that

$$
Q={\phi(+\infty)-\phi(-\infty)\over2v}.
$$

<details><summary><strong>Solution</strong></summary>

With $\epsilon^{01}=+1$,

$$
j^0={1\over2v}\partial_x\phi.
$$

Therefore

$$
Q=\int dx\,j^0
={1\over2v}\int dx\,{d\phi\over dx}
={\phi(+\infty)-\phi(-\infty)\over2v}.
$$

</details>

### Exercise 3: Pullback conservation

Let $\omega$ be a closed form on $X$ and $\Phi:M\to X$. Show that $J=\Phi^*\omega$ is closed.

<details><summary><strong>Solution</strong></summary>

The exterior derivative commutes with pullback:

$$
d(\Phi^*\omega)=\Phi^*(d\omega).
$$

Since $d\omega=0$,

$$
dJ=d(\Phi^*\omega)=0.
$$

</details>

### Exercise 4: Charge change through a side boundary

Let $M$ be the spacetime region between two spatial slices $\Sigma_1$ and $\Sigma_2$, with side boundary $B$. If $dJ=0$, show that

$$
Q(\Sigma_2)-Q(\Sigma_1)=-\int_B J
$$

using the orientation convention $\partial M=\Sigma_2\sqcup(-\Sigma_1)\sqcup B$.

<details><summary><strong>Solution</strong></summary>

Stokes's theorem gives

$$
0=\int_M dJ=\int_{\partial M}J.
$$

With the stated orientation,

$$
\int_{\partial M}J
=\int_{\Sigma_2}J-\int_{\Sigma_1}J+\int_BJ.
$$

Thus

$$
Q(\Sigma_2)-Q(\Sigma_1)=-\int_BJ.
$$

</details>

### Exercise 5: Conservation versus quantization

Explain why the kink current is conserved for any smooth real scalar field, but the kink charge is integer-valued only after imposing double-well boundary conditions.

<details><summary><strong>Solution</strong></summary>

The current conservation follows from antisymmetry and smoothness:

$$
\epsilon^{\mu\nu}\partial_\mu\partial_\nu\phi=0.
$$

No potential or boundary condition was used. But the value of the charge is

$$
Q={\phi(+\infty)-\phi(-\infty)\over2v}.
$$

This is an integer only when the finite-energy boundary conditions force $\phi(\pm\infty)$ to be chosen from $\{-v,+v\}$. Without those boundary conditions, the same conserved current can have arbitrary real charge.

</details>

## References

- M. Nakahara, *Geometry, Topology and Physics*, especially homotopy groups, de Rham cohomology, fiber bundles, monopoles, and instantons.
- T. Frankel, *The Geometry of Physics*, especially differential forms, Stokes's theorem, Chern classes, and gauge fields.
- M. Srednicki, *Quantum Field Theory*, §§92–93.
- A. M. Polyakov, *Gauge Fields and Strings*, chapters on instantons, compact gauge fields, and topology of gauge fields.
- S. Coleman, *Aspects of Symmetry*, lectures on solitons, false vacuum decay, and symmetries.
- D. Tong, *TASI Lectures on Solitons*.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries.”

## Version history

- 2026-06-18: First polished draft. Added homotopy and closed-current formulations, examples from kinks, sigma models, Skyrmions, magnetic flux, failure modes, generalized-symmetry bridge, exercises, and figure.
