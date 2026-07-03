---
title: "Gauge Fixing Preview"
description: "Why gauge fixing is needed in gauge theory: gauge orbits, Lorenz, Coulomb, axial, and covariant gauges, Faddeev–Popov determinants, photon propagators, ghost preview, and gauge-independent observables."
sidebar:
  label: "Gauge Fixing Preview"
  order: 4
---

## Summary

Gauge fixing is not an extra physical assumption. It is a way to choose coordinates on a redundant description.

In Maxwell theory, the potential

$$
A_\mu
$$

has a gauge redundancy

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

All potentials related this way describe the same field strength

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

That redundancy is a feature, not a bug, but it becomes a technical obstacle in quantization. The quadratic Maxwell action has zero modes along gauge directions, so its kinetic operator has no inverse on the full space of vector fields. The path integral also overcounts: it integrates over every point on each gauge orbit, not once over each physical history.

A **gauge condition** such as

$$
\partial_\mu A^\mu=0,
\qquad
\nabla\cdot\mathbf A=0,
\qquad
n^\mu A_\mu=0
$$

selects representatives of gauge orbits. The Faddeev–Popov construction makes this precise by inserting a delta functional for the gauge condition together with a Jacobian determinant. Coleman introduces the idea by saying that the naive gauge-field path integral counts the same physical history infinitely many times, so one must modify the integral to count each history once (Coleman 2019, chs. 30–31). In QED Lorenz gauge, the determinant is field-independent and ghosts decouple; in non-Abelian Yang–Mills theory, the determinant depends on the gauge field and becomes the ghost sector (Srednicki 2007, §§71–72; Weinberg 1996, §§15.5–15.7).

<figure class="doc-figure" style="--figure-width: 55rem;">

![Gauge fixing, gauge slices, and Faddeev–Popov determinants](/figures/foundations/gauge-fixing-slice-fp.svg)

<figcaption>

Gauge fixing chooses a slice through field-configuration space. The Faddeev–Popov determinant is the Jacobian for replacing an integral over redundant gauge directions by an integral over representatives. In Abelian Lorenz gauge $\Delta_\text{FP}=\det\Box$ is field-independent; in Yang–Mills theory $\Delta_\text{FP}=\det(\partial_\mu D^\mu)$ depends on $A_\mu$ and gives interacting ghosts.

</figcaption>
</figure>

## Prerequisites

You should know [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/), [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/), [Charged Matter](/foundations/gauge-fields-first-principles/charged-matter/), [Maxwell Field](/foundations/free-fields/maxwell-field/), [Constraints](/foundations/classical-field-theory/constraints/), [Path Integral Measure](/foundations/path-integral-formalism/path-integral-measure/), and [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/).

:::note[Conventions]
We use the mostly-minus metric and

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
\qquad
\mathcal L_\text{Maxwell}=-\frac14F_{\mu\nu}F^{\mu\nu}.
$$

The gauge condition

$$
\partial_\mu A^\mu=0
$$

is the **Lorenz** gauge condition, named after Ludvig Lorenz. It is Lorentz covariant, but the name is not “Lorentz gauge.”
:::

:::note[Scope]
This page explains the first layer of gauge fixing. It does not develop BRST cohomology, Slavnov–Taylor identities, background-field gauge, Gribov copies, gauge fixing in the Higgs mechanism, or nonperturbative gauge fixing. Those belong later.
:::

## The non-invertible Maxwell kernel

Start from

$$
S[A]=-\frac14\int d^4x\,F_{\mu\nu}F^{\mu\nu}.
$$

Using

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu
$$

and integrating by parts, the quadratic action can be written as

$$
S[A]=\frac12\int d^4x\,
A_\mu\left(g^{\mu\nu}\partial^2-\partial^\mu\partial^\nu\right)A_\nu.
$$

In momentum space, the kernel is proportional to

$$
K^{\mu\nu}(k)=-(k^2g^{\mu\nu}-k^\mu k^\nu).
$$

It has a zero direction:

$$
K^{\mu\nu}(k)k_\nu=0.
$$

This is just gauge redundancy in linear algebra form. A mode proportional to $k_\mu$ is the Fourier transform of a pure gauge fluctuation,

$$
A_\mu=\partial_\mu\alpha.
$$

Since $F_{\mu\nu}=0$ for a pure gauge field, the Maxwell action cannot see this direction. Therefore the kinetic operator cannot be inverted on the full space of $A_\mu$ fields. No inverse means no propagator until the redundant direction is removed or controlled.

## Gauge orbits and slices

The set

$$
\{A_\mu+\partial_\mu\alpha\;|\;\alpha\text{ allowed}\}
$$

is the gauge orbit through $A_\mu$. A gauge condition $G[A]=0$ tries to choose one representative on each orbit. This is the same idea as choosing one coordinate representative for a point in a quotient space.

Common gauge choices include:

| Gauge | Condition | What it makes transparent |
|---|---:|---|
| Coulomb gauge | $\nabla\cdot\mathbf A=0$ | The two transverse photon polarizations and the Coulomb interaction. |
| Lorenz gauge | $\partial_\mu A^\mu=0$ | Lorentz covariance of formulas. |
| Feynman gauge | ξ = 1 in the covariant family | The simplest photon propagator. |
| Landau gauge | ξ = 0 in the covariant family | Transverse propagators in covariant perturbation theory. |
| Axial gauge | $n^\mu A_\mu=0$ | A representative fixed by a chosen vector $n^\mu$. |

A gauge condition is a computational choice. The potential, propagator, and intermediate Green functions may look different in different gauges. Gauge-invariant observables must agree.

## Coulomb gauge

Coulomb gauge is

$$
\nabla\cdot\mathbf A=0.
$$

It separates the spatial vector potential into transverse and longitudinal parts,

$$
\mathbf A=\mathbf A_T+\mathbf A_L,
\qquad
\nabla\cdot\mathbf A_T=0,
\qquad
\nabla\times\mathbf A_L=0.
$$

The condition removes the longitudinal part of $\mathbf A$. The scalar potential $A_0$ is then constrained by Gauss's law rather than being an independent radiative degree of freedom.

This gauge is physically clear but not manifestly Lorentz covariant. That is fine: gauge fixing can hide spacetime symmetry in intermediate expressions. The final gauge-invariant predictions still respect the symmetries of the theory.

## Covariant ξ gauges

For perturbative QFT, it is often convenient to add a gauge-fixing term

$$
\boxed{
\mathcal L_\text{gf}=-\frac1{2\xi}(\partial_\mu A^\mu)^2.
}
$$

The gauge-fixed quadratic Lagrangian becomes

$$
\mathcal L_0+\mathcal L_\text{gf}
=\frac12 A_\mu
\left[g^{\mu\nu}\partial^2-
\left(1-\frac1\xi\right)\partial^\mu\partial^\nu\right]A_\nu.
$$

Now the operator is invertible, with photon propagator

$$
\boxed{
D_{\mu\nu}^{(\xi)}(k)
=\frac{-i}{k^2+i\epsilon}
\left[g_{\mu\nu}-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}\right].
}
$$

Special cases are

$$
\xi=1:
\qquad
D_{\mu\nu}(k)=\frac{-ig_{\mu\nu}}{k^2+i\epsilon}
\qquad\text{Feynman gauge},
$$

and

$$
\xi=0:
\qquad
k^\mu D_{\mu\nu}(k)=0
\qquad\text{Landau gauge}.
$$

The parameter $\xi$ is not a physical coupling. It labels a choice of gauge-fixed description.

## The Faddeev–Popov insertion

The path integral version of gauge fixing starts with the formal identity

$$
1=\Delta_\text{FP}[A]
\int\mathcal D\alpha\,\delta(G[A^\alpha]),
$$

where

$$
A_\mu^\alpha=A_\mu+\partial_\mu\alpha.
$$

The determinant is chosen so the identity is true:

$$
\boxed{
\Delta_\text{FP}[A]
=\det\left(\frac{\delta G[A^\alpha]}{\delta\alpha}\right).
}
$$

Inserting this into the gauge-field path integral and factoring out the gauge-group volume gives

$$
\boxed{
Z=\mathcal N\int\mathcal DA\,
\Delta_\text{FP}[A]\,\delta(G[A])\,e^{iS[A]}.
}
$$

The determinant is a Jacobian. It compensates for how the gauge slice cuts the gauge orbits.

## Abelian Lorenz gauge

Choose

$$
G[A]=\partial_\mu A^\mu-f.
$$

Then

$$
G[A^\alpha]
=\partial_\mu A^\mu+\partial^2\alpha-f,
$$

so

$$
\frac{\delta G[A^\alpha](x)}{\delta\alpha(y)}
=\partial_x^2\delta^{(4)}(x-y).
$$

Thus

$$
\Delta_\text{FP}=\det(\partial^2).
$$

This determinant is independent of $A_\mu$. In normalized QED correlation functions it is absorbed into the overall normalization.

If represented using Grassmann ghost fields,

$$
\det(\partial^2)
=\int\mathcal D\bar c\,\mathcal Dc\,
\exp\left(i\int d^4x\,\bar c\,\partial^2 c\right),
$$

the ghosts are free and decoupled. This is why elementary QED perturbation theory usually has no ghost lines.

## Gaussian averaging over the gauge condition

The delta functional imposes

$$
\partial\cdot A=f.
$$

Since the result is independent of the chosen function $f$, we can average over $f$ with a Gaussian weight,

$$
\exp\left[-\frac{i}{2\xi}\int d^4x\,f^2\right].
$$

The delta functional then sets $f=\partial\cdot A$, giving

$$
\exp\left[-\frac{i}{2\xi}\int d^4x\,(\partial\cdot A)^2\right].
$$

This is precisely the covariant gauge-fixing term

$$
\mathcal L_\text{gf}=-\frac1{2\xi}(\partial\cdot A)^2.
$$

This derivation explains why covariant gauges are not arbitrary vandalism done to the Maxwell action. They are a controlled way of slicing gauge orbits in the path integral.

## What changes in Yang–Mills theory

For a non-Abelian gauge field, an infinitesimal gauge transformation has the schematic form

$$
\delta A_\mu^a=D_\mu^{ab}\alpha^b,
$$

where $D_\mu^{ab}$ contains $A_\mu^a$ itself. For the Lorenz-type condition

$$
G^a[A]=\partial_\mu A^{a\mu}-f^a,
$$

the Faddeev–Popov operator is

$$
\frac{\delta G^a[A^\alpha]}{\delta\alpha^b}
=\partial_\mu D^{ab\mu}[A].
$$

Therefore

$$
\Delta_\text{FP}[A]=\det(\partial_\mu D^\mu[A])
$$

depends on the gauge field. It is not an ignorable constant. Representing the determinant with Grassmann variables produces interacting ghosts,

$$
\mathcal L_\text{gh}
=-\partial_\mu\bar c^aD^{ab\mu}c^b
$$

up to sign conventions and integrations by parts.

Ghosts are not particles in the physical spectrum. They are auxiliary fields that encode the gauge-fixing Jacobian. Their loop contributions are essential for gauge independence and unitarity in non-Abelian perturbation theory.

## Gauge-dependent objects and physical objects

The gauge-field propagator depends on $\xi$, and that is allowed because $A_\mu$ itself is gauge dependent. The longitudinal part of the covariant-gauge propagator is proportional to $k_\mu k_\nu$. When a photon connects conserved currents,

$$
k_\mu J^\mu(k)=0,
$$

that longitudinal contribution drops out. More generally, Ward identities and their non-Abelian Slavnov–Taylor generalizations enforce the cancellation of unphysical gauge dependence in physical quantities.

Gauge-invariant objects include

$$
F_{\mu\nu}F^{\mu\nu},
\qquad
\bar\psi\psi,
\qquad
\bar\psi\gamma^\mu D_\mu\psi,
\qquad
\text{Wilson loops}.
$$

Gauge-dependent objects, such as $A_\mu$ propagators, can be very useful. They are tools, not observables.

## Common pitfalls

**Gauge fixing is not a physical symmetry breaking.** It selects representatives of gauge orbits. It does not create new physics.

**Lorenz gauge is not the same word as Lorentz symmetry.** It is Lorentz covariant, but named after Lorenz.

**Ghosts are not optional in non-Abelian loop calculations.** They represent the Faddeev–Popov determinant and cancel unphysical gauge-mode effects.

**The gauge parameter ξ is not measurable.** A calculation may depend on $\xi$ halfway through. A physical observable may not.

**A local gauge slice need not be globally perfect.** Perturbative gauge fixing assumes a good local slice. Global obstructions and Gribov copies are real nonperturbative issues.

## Relations to nearby pages

- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) explains gauge orbits and gauge-invariant observables.
- [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/) gives the Abelian gauge theory before quantization.
- [Charged Matter](/foundations/gauge-fields-first-principles/charged-matter/) explains minimal coupling and the current conservation needed for gauge independence.
- [Non-Abelian Preview](/foundations/gauge-fields-first-principles/non-abelian-preview/) explains why the Faddeev–Popov determinant becomes dynamical for Yang–Mills fields.
- [BRST Preview](/foundations/gauge-fields-first-principles/brst-preview/) will describe the symmetry that survives gauge fixing.

## Exercises

### Exercise 1: Null direction of the Maxwell kernel

Show that

$$
K^{\mu\nu}(k)=-(k^2g^{\mu\nu}-k^\mu k^\nu)
$$

satisfies $K^{\mu\nu}k_\nu=0$.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
K^{\mu\nu}k_\nu
=-(k^2k^\mu-k^\mu k^\nu k_\nu)
=-(k^2k^\mu-k^\mu k^2)=0.
$$

The longitudinal mode is a zero mode, so the ungauge-fixed quadratic operator cannot be inverted.

</details>

### Exercise 2: Abelian Faddeev–Popov determinant

For $G[A]=\partial_\mu A^\mu-f$ and $A_\mu^\alpha=A_\mu+\partial_\mu\alpha$, derive

$$
\Delta_\text{FP}=\det(\partial^2).
$$

<details>
<summary><strong>Solution</strong></summary>

Since

$$
G[A^\alpha]=\partial\cdot A+\partial^2\alpha-f,
$$

we have

$$
\frac{\delta G[A^\alpha](x)}{\delta\alpha(y)}
=\partial_x^2\delta^{(4)}(x-y).
$$

The determinant of this operator is $\det(\partial^2)$, independent of $A_\mu$.

</details>

### Exercise 3: Feynman gauge propagator

Set $\xi=1$ in

$$
D_{\mu\nu}^{(\xi)}(k)
=\frac{-i}{k^2+i\epsilon}
\left[g_{\mu\nu}-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}\right].
$$

<details>
<summary><strong>Solution</strong></summary>

For $\xi=1$, the longitudinal term vanishes:

$$
D_{\mu\nu}^{(1)}(k)=\frac{-ig_{\mu\nu}}{k^2+i\epsilon}.
$$

</details>

### Exercise 4: Longitudinal exchange between conserved currents

Show that a term proportional to $k_\mu k_\nu$ in the photon propagator gives no contribution between conserved currents.

<details>
<summary><strong>Solution</strong></summary>

The contribution has the form

$$
J^\mu(k)k_\mu k_\nu J'^\nu(-k)
=(k_\mu J^\mu)(k_\nu J'^\nu).
$$

Each factor vanishes by current conservation, so the longitudinal contribution is zero.

</details>

### Exercise 5: Residual gauge freedom in Lorenz gauge

If $\partial\cdot A=0$, what condition must $\alpha$ satisfy for $A_\mu+\partial_\mu\alpha$ also to obey Lorenz gauge?

<details>
<summary><strong>Solution</strong></summary>

Require

$$
\partial_\mu(A^\mu+\partial^\mu\alpha)=0.
$$

Since $\partial\cdot A=0$, this gives

$$
\boxed{\partial^2\alpha=0.}
$$

Boundary conditions are needed to remove such residual transformations.

</details>

### Exercise 6: Why non-Abelian ghosts interact

Suppose $\delta A_\mu^a=D_\mu^{ab}\alpha^b$, with $D_\mu^{ab}$ depending on $A_\mu$. Show why the ghost action contains interactions.

<details>
<summary><strong>Solution</strong></summary>

For $G^a[A]=\partial_\mu A^{a\mu}-f^a$,

$$
\delta G^a=\partial_\mu D^{ab\mu}\alpha^b.
$$

The Faddeev–Popov determinant is

$$
\det(\partial_\mu D^{ab\mu}[A]).
$$

Since this operator depends on $A_\mu$, the Grassmann representation of the determinant contains terms involving $\bar c$, $c$, and $A_\mu$. Those are ghost-gauge-field interactions.

</details>

## Sources and further reading

- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* **25** (1967), for the original gauge-fixing construction.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chs. 30–31 and 47, for the gauge-orbit overcounting argument, the finite-dimensional analogy, QED gauge fixing, and the non-Abelian extension.
- M. Srednicki, *Quantum Field Theory*, §§57, 71, and 72, for Abelian and non-Abelian path-integral gauge fixing, ghosts, and covariant-gauge Feynman rules.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 8, and Vol. II, §§15.5–15.7, for electrodynamics, Faddeev–Popov–DeWitt gauge fixing, ghosts, and BRST symmetry.
- A. Zee, *Quantum Field Theory in a Nutshell*, chs. III.4 and VII.1, for a concise path-integral explanation of gauge fixing.
- M. Peskin and D. Schroeder, *An Introduction to Quantum Field Theory*, chs. 9 and 15, for practical covariant gauges and ghost Feynman rules.

## Version history

- **2026-05-23:** Initial qft.org page on gauge fixing, covariant gauges, the Faddeev–Popov determinant, Abelian ghost decoupling, and the non-Abelian ghost preview.
