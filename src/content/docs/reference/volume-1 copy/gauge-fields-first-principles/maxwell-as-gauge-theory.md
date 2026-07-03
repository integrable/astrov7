---
title: "Maxwell as Gauge Theory"
description: "Electromagnetism as the simplest Abelian gauge theory: gauge potential, field strength, Maxwell action, equations of motion, Bianchi identity, conserved current coupling, and gauge fixing preview."
sidebar:
  label: "Maxwell as Gauge Theory"
  order: 2
---

## Summary

Maxwell theory is the simplest local gauge theory. Its fundamental local potential is a one-form $A_\mu(x)$, but the gauge-invariant field strength is

$$
\boxed{F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.}
$$

The gauge redundancy is

$$
\boxed{A_\mu\mapsto A_\mu+\partial_\mu\alpha.}
$$

The source-free Maxwell action is

$$
\boxed{S[A]=-\frac14\int d^4x\,F_{\mu\nu}F^{\mu\nu}.}
$$

Coupling to a conserved external current gives

$$
S[A,j]=\int d^4x\left(-\frac14F_{\mu\nu}F^{\mu\nu}-j_\mu A^\mu\right),
$$

with equation of motion

$$
\boxed{\partial_\mu F^{\mu\nu}=j^\nu.}
$$

The other pair of Maxwell equations is not a separate dynamical equation. It is the Bianchi identity following from $F=dA$:

$$
\boxed{\partial_\lambda F_{\mu\nu}+\partial_\mu F_{\nu\lambda}+\partial_\nu F_{\lambda\mu}=0.}
$$

This page is not mainly about photon quantization. That was the role of [Maxwell Field](/foundations/free-fields/maxwell-field/). Here the point is structural: electromagnetism is a theory of a connection $A$, a curvature $F$, gauge-invariant dynamics, and coupling to conserved charge. Coleman develops this connection by showing that preserving gauge invariance of the massless vector theory is tied to current conservation and minimal coupling (Coleman 2019, ch. 27). Srednicki derives Maxwell's equations from the Maxwell Lagrangian and later treats the path integral as an integral over gauge orbits rather than over independent vector-field components (Srednicki 2007, §§54 and 57). Weinberg's discussion of electrodynamics shows why a massless helicity-one field requires gauge invariance and why the photon couples consistently to a conserved current (Weinberg 1995, Vol. I, ch. 8).

<figure class="doc-figure" style="--figure-width: 52rem;">

![Maxwell theory as an Abelian gauge theory](/figures/foundations/maxwell-gauge-theory-map.svg)

<figcaption>

Maxwell theory starts from a gauge potential $A$, whose curvature $F=dA$ is gauge invariant. The action built from $F^2$ gives $d{*F}={*j}$, while $F=dA$ automatically gives $dF=0$. Gauge fixing is a choice of representative for computations, not a change of electromagnetic physics.

</figcaption>
</figure>

## Prerequisites

You should know [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/), [Maxwell Field](/foundations/free-fields/maxwell-field/), [Proca Field](/foundations/free-fields/proca-field/), [Constraints](/foundations/classical-field-theory/constraints/), [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/), and [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/).

:::note[Conventions]
We use the mostly-minus metric and define

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
\qquad
\mathcal L_\text{Maxwell}=-\frac14F_{\mu\nu}F^{\mu\nu}.
$$

For charged matter of charge $q$, qft.org uses

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\Phi\mapsto e^{-iq\alpha}\Phi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

This page uses $\mathcal L_\text{int}=-j_\mu A^\mu$, so the sourced equation is $\partial_\mu F^{\mu\nu}=j^\nu$.
:::

:::note[Scope]
This page treats Abelian Maxwell theory. Quantized photon polarizations, propagators, and LSZ details are covered in [Maxwell Field](/foundations/free-fields/maxwell-field/) and [Polarizations](/foundations/free-fields/polarizations/). Gauge fixing, charged matter, non-Abelian fields, and BRST get their own pages in this subgroup.
:::

## The gauge potential

The electromagnetic potential is a one-form,

$$
A=A_\mu dx^\mu.
$$

In ordinary vector notation it packages the scalar and vector potentials. In relativistic notation, it is the field that couples locally to charged matter.

The potential is not unique. The transformation

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha
$$

leaves the field strength unchanged. In differential-form notation,

$$
A\mapsto A+d\alpha,
\qquad
F=dA.
$$

Since $d^2=0$,

$$
F\mapsto d(A+d\alpha)=dA+d^2\alpha=F.
$$

This is the first reason Maxwell theory is a gauge theory: the local variable $A$ is a connection-like object, while the local gauge-invariant curvature is $F$.

## The field strength

The field strength is

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

It is antisymmetric:

$$
F_{\mu\nu}=-F_{\nu\mu}.
$$

In four dimensions, an antisymmetric tensor has six independent components. These are the three electric-field components and three magnetic-field components. With the qft.org convention used in the free-field pages,

$$
E^i=F^{i0},
\qquad
F^{ij}=-\epsilon^{ijk}B^k.
$$

The invariant action density is

$$
-\frac14F_{\mu\nu}F^{\mu\nu}
=\frac12(\mathbf E^2-\mathbf B^2).
$$

The field strength is not just a convenient abbreviation. It is the curvature of the Abelian gauge connection. Locally, $F=0$ means $A$ is pure gauge:

$$
F=0
\quad\Rightarrow\quad
A=d\alpha
$$

on a simply connected patch. Globally, the statement can fail in the presence of nontrivial topology; this is the beginning of Aharonov–Bohm physics, Wilson loops, and magnetic monopoles.

## Maxwell action and equations

Start from

$$
S[A,j]=\int d^4x\left(-\frac14F_{\mu\nu}F^{\mu\nu}-j_\mu A^\mu\right).
$$

Vary $A_\mu$. Since

$$
\delta F_{\mu\nu}=\partial_\mu\delta A_\nu-\partial_\nu\delta A_\mu,
$$

and $F^{\mu\nu}$ is antisymmetric,

$$
\delta\left(-\frac14F_{\mu\nu}F^{\mu\nu}\right)
=-\frac12F^{\mu\nu}\delta F_{\mu\nu}
=-F^{\mu\nu}\partial_\mu\delta A_\nu.
$$

After integrating by parts,

$$
\delta S
=\int d^4x\,\left(\partial_\mu F^{\mu\nu}-j^\nu\right)\delta A_\nu
+\text{boundary term}.
$$

For variations vanishing at the boundary, the Euler–Lagrange equation is

$$
\boxed{\partial_\mu F^{\mu\nu}=j^\nu.}
$$

This contains Gauss's law and the Ampère–Maxwell equation.

The Bianchi identity is automatic:

$$
\partial_\lambda F_{\mu\nu}
+\partial_\mu F_{\nu\lambda}
+\partial_\nu F_{\lambda\mu}=0.
$$

In form notation,

$$
\boxed{dF=0,\qquad d{*F}={*j}.}
$$

The first equation is kinematic, because $F=dA$. The second is dynamical, because it follows from the action.

## Current conservation from gauge invariance

The source coupling changes under a gauge transformation as

$$
\delta S_\text{int}
=-\int d^4x\,j_\mu\partial^\mu\alpha.
$$

Integrating by parts gives

$$
\delta S_\text{int}
=\int d^4x\,(\partial_\mu j^\mu)\alpha
-\int_{\partial M}d\Sigma_\mu\,j^\mu\alpha.
$$

For gauge parameters that vanish at the boundary, gauge invariance for arbitrary $\alpha(x)$ requires

$$
\boxed{\partial_\mu j^\mu=0.}
$$

The same condition follows from the equation of motion:

$$
\partial_\nu j^\nu
=\partial_\nu\partial_\mu F^{\mu\nu}=0,
$$

because $\partial_\nu\partial_\mu$ is symmetric while $F^{\mu\nu}$ is antisymmetric.

So Maxwell theory ties three statements together:

$$
\text{gauge invariance}
\quad\Longleftrightarrow\quad
\text{consistent source coupling}
\quad\Longrightarrow\quad
\text{current conservation}.
$$

The first arrow should be read carefully: gauge invariance requires a conserved source, and conserved sources are what make the gauge-dependent part of $A_\mu$ physically harmless.

## Maxwell equations in vector language

Using the conventions above, the sourced equations become

$$
\nabla\cdot\mathbf E=\rho,
$$

and

$$
\nabla\times\mathbf B-\partial_t\mathbf E=\mathbf j.
$$

The Bianchi identity becomes

$$
\nabla\cdot\mathbf B=0,
$$

and

$$
\nabla\times\mathbf E+\partial_t\mathbf B=0.
$$

The covariant form is usually cleaner in QFT because Lorentz transformations are manifest and because gauge theory generalizes naturally through the language of connections and curvatures.

## Why the action uses F, not A

A local mass term for the vector potential,

$$
\frac12m^2A_\mu A^\mu,
$$

is Lorentz invariant but not gauge invariant:

$$
A_\mu A^\mu
\mapsto
(A_\mu+\partial_\mu\alpha)(A^\mu+\partial^\mu\alpha).
$$

That is the Proca theory, not Maxwell gauge theory. It describes a massive spin-one field with three physical polarizations. Maxwell theory describes a massless gauge field with two physical helicities.

The simplest gauge-invariant local kinetic term built from $A_\mu$ and two derivatives is $F_{\mu\nu}F^{\mu\nu}$. In four dimensions there is also

$$
F_{\mu\nu}\widetilde F^{\mu\nu},
\qquad
\widetilde F^{\mu\nu}=\frac12\epsilon^{\mu\nu\rho\sigma}F_{\rho\sigma},
$$

but for Abelian Maxwell theory on topologically simple spacetime this is a total derivative. It affects boundary and topological physics rather than the local Maxwell equations.

Thus the ordinary Maxwell action is the minimal local gauge-invariant two-derivative action for a free Abelian gauge field.

## The connection viewpoint

For a charged field, a local phase convention can vary from point to point:

$$
\Phi(x)\mapsto e^{-iq\alpha(x)}\Phi(x).
$$

The ordinary derivative sees the arbitrary local phase:

$$
\partial_\mu\Phi
\mapsto e^{-iq\alpha}(\partial_\mu\Phi-iq(\partial_\mu\alpha)\Phi).
$$

The extra term prevents $\partial_\mu\Phi$ from transforming like $\Phi$. The gauge potential fixes this:

$$
D_\mu\Phi=(\partial_\mu+iqA_\mu)\Phi.
$$

Under

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
$$

the covariant derivative transforms homogeneously:

$$
D_\mu\Phi\mapsto e^{-iq\alpha}D_\mu\Phi.
$$

This is the local comparison role of a gauge connection. The potential $A_\mu$ tells the theory how to compare phases of charged fields at neighboring spacetime points. The curvature $F_{\mu\nu}$ measures the failure of those comparisons to be path independent.

The next page, Charged Matter, develops this construction in detail.

## Hamiltonian structure and Gauss law

The Maxwell Lagrangian contains no time derivative of $A_0$. Thus $A_0$ is not an ordinary propagating field component. It acts as a Lagrange multiplier enforcing Gauss's law.

In canonical variables,

$$
E^i=F^{i0}
$$

is the momentum conjugate to $A_i$ up to the convention fixed by index placement, while

$$
\Pi^0=0
$$

is a primary constraint. The secondary constraint is

$$
\partial_iE^i-\rho=0.
$$

This is the Hamiltonian version of gauge theory's redundancy. The unphysical component $A_0$ enforces a constraint; it does not describe an independent photon polarization.

After imposing constraints and fixing gauge, the free photon has two physical helicities. That is why this page cross-links back to [Maxwell Field](/foundations/free-fields/maxwell-field/), where the free-particle interpretation is developed.

## Gauge fixing preview

The Maxwell kinetic operator is not invertible before gauge fixing. The reason is physical: if $A_\mu$ and $A_\mu+\partial_\mu\alpha$ describe the same configuration, then the action is flat along gauge orbits.

To define a propagator, one adds a gauge-fixing term. A common covariant family is

$$
\mathcal L_\text{gf}
=-\frac{1}{2\xi}(\partial_\mu A^\mu)^2.
$$

The resulting photon propagator is gauge dependent. In momentum space,

$$
D_F^{\mu\nu}(p)
=\frac{-i}{p^2+i\epsilon}
\left[\eta^{\mu\nu}-(1-\xi)\frac{p^\mu p^\nu}{p^2+i\epsilon}\right].
$$

In Feynman gauge, $\xi=1$, this reduces to

$$
D_F^{\mu\nu}(p)=\frac{-i\eta^{\mu\nu}}{p^2+i\epsilon}.
$$

The $\xi$ dependence cancels in gauge-invariant observables when the theory is consistently coupled to conserved currents and quantized with the correct gauge-fixing procedure. This cancellation is the perturbative shadow of gauge redundancy.

## Maxwell theory as the template for non-Abelian gauge theory

The Abelian theory has the chain

$$
A\quad\longrightarrow\quad F=dA
\quad\longrightarrow\quad
S=-\frac14\int F^2.
$$

For a non-Abelian gauge group, the same chain survives but becomes nonlinear:

$$
A_\mu=A_\mu^aT^a,
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu+ig[A_\mu,A_\nu],
$$

up to sign conventions for $g$ and the generators. The action becomes

$$
S_\text{YM}=-\frac12\int d^4x\,\mathrm{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

Unlike Maxwell theory, non-Abelian gauge fields carry the gauge charge themselves. This is why Yang–Mills theory has self-interactions even without matter. The non-Abelian story belongs later, but the template begins here.

## Common pitfalls

**Pitfall 1: Thinking the potential is fake.**  
The potential is gauge-dependent, not useless. It is the local variable that couples to charged matter and makes Lorentz-covariant quantization possible.

**Pitfall 2: Thinking the field strength is everything globally.**  
Locally, $F$ captures the electromagnetic field. Globally, gauge potentials can carry holonomy data even when $F$ vanishes locally.

**Pitfall 3: Adding a photon mass without changing the theory.**  
The term $m^2A_\mu A^\mu/2$ breaks Maxwell gauge invariance and changes the physical degrees of freedom.

**Pitfall 4: Confusing Lorenz gauge with Lorentz invariance.**  
Lorenz gauge is the condition $\partial_\mu A^\mu=0$, named after Ludvig Lorenz. Lorentz invariance is spacetime symmetry.

**Pitfall 5: Treating the photon propagator as an observable.**  
The propagator depends on gauge fixing. Gauge-invariant amplitudes and physical cross sections do not.

## Exercises

### Exercise 1: Derive the Maxwell equations from the action

Starting from

$$
S[A,j]=\int d^4x\left(-\frac14F_{\mu\nu}F^{\mu\nu}-j_\mu A^\mu\right),
$$

show that the Euler–Lagrange equation is

$$
\partial_\mu F^{\mu\nu}=j^\nu.
$$

<details>
<summary><strong>Solution</strong></summary>

The variation of the field strength is

$$
\delta F_{\mu\nu}=\partial_\mu\delta A_\nu-\partial_\nu\delta A_\mu.
$$

Therefore

$$
\delta S
=-\frac12\int d^4x\,F^{\mu\nu}\delta F_{\mu\nu}
-\int d^4x\,j^\nu\delta A_\nu.
$$

Using antisymmetry of $F^{\mu\nu}$,

$$
-\frac12F^{\mu\nu}\delta F_{\mu\nu}
=-F^{\mu\nu}\partial_\mu\delta A_\nu.
$$

Integrating by parts gives

$$
\delta S
=\int d^4x\,(\partial_\mu F^{\mu\nu}-j^\nu)\delta A_\nu
+\text{boundary term}.
$$

For arbitrary variations vanishing at the boundary,

$$
\boxed{\partial_\mu F^{\mu\nu}=j^\nu.}
$$

</details>

### Exercise 2: Derive the Bianchi identity

Use

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu
$$

to show that

$$
\partial_\lambda F_{\mu\nu}+\partial_\mu F_{\nu\lambda}+\partial_\nu F_{\lambda\mu}=0.
$$

<details>
<summary><strong>Solution</strong></summary>

Substitute the definition:

$$
\partial_\lambda F_{\mu\nu}
=\partial_\lambda\partial_\mu A_\nu
-\partial_\lambda\partial_\nu A_\mu,
$$

$$
\partial_\mu F_{\nu\lambda}
=\partial_\mu\partial_\nu A_\lambda
-\partial_\mu\partial_\lambda A_\nu,
$$

$$
\partial_\nu F_{\lambda\mu}
=\partial_\nu\partial_\lambda A_\mu
-\partial_\nu\partial_\mu A_\lambda.
$$

Adding these expressions, every term cancels with another because partial derivatives commute. Hence

$$
\boxed{\partial_\lambda F_{\mu\nu}+\partial_\mu F_{\nu\lambda}+\partial_\nu F_{\lambda\mu}=0.}
$$

</details>

### Exercise 3: Source coupling and current conservation

Show that the interaction

$$
S_\text{int}=-\int d^4x\,j_\mu A^\mu
$$

is gauge invariant under $A_\mu\mapsto A_\mu+\partial_\mu\alpha$ if $\partial_\mu j^\mu=0$ and $\alpha$ vanishes at the boundary.

<details>
<summary><strong>Solution</strong></summary>

The variation is

$$
\delta S_\text{int}
=-\int d^4x\,j_\mu\partial^\mu\alpha.
$$

Integrating by parts,

$$
\delta S_\text{int}
=\int d^4x\,(\partial^\mu j_\mu)\alpha
-\int_{\partial M}d\Sigma_\mu\,j^\mu\alpha.
$$

If $\alpha$ vanishes on the boundary and $\partial_\mu j^\mu=0$, both terms vanish. Therefore the coupling is gauge invariant.

</details>

### Exercise 4: Photon mass term is not gauge invariant

Show that

$$
\frac12m^2A_\mu A^\mu
$$

is not invariant under $A_\mu\mapsto A_\mu+\partial_\mu\alpha$ for general $\alpha$.

<details>
<summary><strong>Solution</strong></summary>

Under the transformation,

$$
A_\mu A^\mu
\mapsto
(A_\mu+\partial_\mu\alpha)(A^\mu+\partial^\mu\alpha).
$$

Expanding,

$$
A_\mu A^\mu
\mapsto
A_\mu A^\mu
+2A^\mu\partial_\mu\alpha
+\partial_\mu\alpha\partial^\mu\alpha.
$$

The extra terms do not vanish for a general local function $\alpha(x)$. Thus

$$
\boxed{\frac12m^2A_\mu A^\mu\text{ is not Maxwell-gauge invariant.}}
$$

</details>

### Exercise 5: Covariant derivative and local phase rotations

Using qft.org's convention

$$
D_\mu=\partial_\mu+iqA_\mu,
$$

verify that $D_\mu\Phi$ transforms like $\Phi$ under

$$
\Phi\mapsto e^{-iq\alpha}\Phi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
D_\mu'\Phi'
=(\partial_\mu+iqA_\mu+iq\partial_\mu\alpha)e^{-iq\alpha}\Phi.
$$

The derivative term gives

$$
e^{-iq\alpha}\partial_\mu\Phi-iq(\partial_\mu\alpha)e^{-iq\alpha}\Phi.
$$

The extra gauge-field term gives

$$
+iq(\partial_\mu\alpha)e^{-iq\alpha}\Phi,
$$

which cancels the derivative of the phase. Thus

$$
\boxed{D_\mu'\Phi'=e^{-iq\alpha}D_\mu\Phi.}
$$

</details>

### Exercise 6: Gauge-fixed photon propagator and conserved currents

Let a conserved current satisfy $p_\mu j^\mu(p)=0$. Show that the gauge-dependent part of the covariant photon propagator,

$$
D_F^{\mu\nu}(p)
=\frac{-i}{p^2+i\epsilon}
\left[\eta^{\mu\nu}-(1-\xi)\frac{p^\mu p^\nu}{p^2+i\epsilon}\right],
$$

drops out of the current-current exchange $j_\mu D_F^{\mu\nu}j'_\nu$ when both currents are conserved.

<details>
<summary><strong>Solution</strong></summary>

The gauge-dependent term is proportional to

$$
j_\mu p^\mu p^\nu j'_\nu.
$$

If both currents are conserved in momentum space,

$$
p_\mu j^\mu=0,
\qquad
p_\nu j'^{\nu}=0.
$$

Therefore

$$
j_\mu p^\mu p^\nu j'_\nu
=(p\cdot j)(p\cdot j')=0.
$$

So the $\xi$-dependent piece does not contribute to conserved-current exchange.

</details>

## Sources and further reading

- J. C. Maxwell, “A Dynamical Theory of the Electromagnetic Field,” *Philosophical Transactions of the Royal Society* **155** (1865), for the classical origin of Maxwell theory.
- H. Weyl, “Elektron und Gravitation,” *Zeitschrift für Physik* **56** (1929), for the local phase-gauge viewpoint.
- M. Srednicki, *Quantum Field Theory*, §§54–57, for Maxwell's equations, Coulomb-gauge quantization, photon LSZ, and the photon path integral.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 26–31, for vector fields, gauge invariance, minimal coupling, massive photons, and Faddeev–Popov quantization.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 8, for electrodynamics in the canonical and covariant-gauge formalisms.
- J. D. Jackson, *Classical Electrodynamics*, for the classical field equations, potentials, gauges, and boundary-value theory.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, chs. 9 and 15, for QED and gauge fixing in perturbation theory.

## Version history

- **2026-05-23:** Initial qft.org page on Maxwell theory as an Abelian gauge theory, including the potential, curvature, action, equations of motion, Bianchi identity, conserved-current coupling, gauge fixing, and non-Abelian preview.
