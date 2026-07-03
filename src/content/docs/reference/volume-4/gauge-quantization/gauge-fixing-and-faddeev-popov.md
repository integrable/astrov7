---
title: "Gauge Fixing and Faddeev–Popov"
description: "Derives the Faddeev–Popov method from gauge-orbit overcounting, constructs covariant gauges for Yang–Mills theory, and explains why non-Abelian ghosts appear."
sidebar:
  label: "Gauge Fixing and Faddeev–Popov"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §71; Weinberg Vol. II §§15.4–15.6; Coleman lectures on the Faddeev–Popov prescription; Schwartz Ch. 25; Zee Part VII.1."
topics:
  - gauge fixing
  - Faddeev–Popov method
  - gauge orbits
  - Yang–Mills path integral
  - ghost determinant
  - covariant gauge
canonicalTopics:
  - faddeev-popov-method
  - gauge-fixing
  - gauge-orbit
  - faddeev-popov-determinant
  - yang-mills-path-integral
researchStatus:
  established:
    - "The Faddeev–Popov method gives the standard perturbative path-integral quantization of Yang–Mills theory in a local gauge patch."
  active:
    - "Global gauge fixing, Gribov copies, boundary conditions, and nonperturbative definitions of gauge-fixed path integrals require additional care beyond the local perturbative construction."
---

## Summary

The Yang–Mills path integral cannot be obtained by naively integrating over all gauge potentials $A_\mu^a$. Gauge-related configurations describe the same physical field configuration, so

$$
\int \mathcal D A\, e^{iS_{\mathrm{YM}}[A]}
$$

contains an infinite overcounting by the volume of the gauge group. The same redundancy also makes the quadratic gauge-field operator non-invertible, so a propagator is not defined until the redundancy is handled.

The Faddeev–Popov method inserts a clever form of $1$ into the path integral:

$$
1
=
\Delta_{\mathrm{FP}}[A]
\int \mathcal D\alpha\,
\delta\!\bigl(G(A^\alpha)-f\bigr),
$$

where $G^a(A)=0$ is a gauge condition and $A^\alpha$ is the gauge transform of $A$. The determinant

$$
\Delta_{\mathrm{FP}}[A]
=
\det\!\left(\frac{\delta G^a(A^\alpha)}{\delta\alpha^b}\right)
$$

is the Jacobian measuring how the gauge condition changes as one moves along a gauge orbit.

For covariant Yang–Mills gauge fixing,

$$
G^a(A)=\partial^\mu A_\mu^a,
$$

the Faddeev–Popov operator is

$$
M^{ab}[A]=\partial^\mu D_\mu^{ab}[A],
$$

with the adjoint covariant derivative, in this volume’s convention,

$$
(D_\mu c)^a=\partial_\mu c^a-gf^{abc}A_\mu^b c^c.
$$

The determinant $\det M[A]$ depends on $A_\mu$ in a non-Abelian theory. Representing it by anticommuting ghost fields gives the standard gauge-fixed Yang–Mills Lagrangian,

$$
\mathcal L_{\mathrm{YM},\xi}
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2
-\bar c^a\partial^\mu D_\mu^{ab}c^b.
$$

<figure class="doc-figure" style="--figure-width: 52rem;">

![The Faddeev–Popov method replaces integration over every point on each gauge orbit by integration over a gauge slice plus a Jacobian.](/figures/gauge-theories-standard-model/faddeev-popov-gauge-slice.svg)

<figcaption>

The Faddeev–Popov determinant is the Jacobian for trading redundant integration along gauge orbits for a gauge condition $G(A)=f$. Perturbatively one assumes the slice intersects each nearby orbit once. In non-Abelian theory the Jacobian depends on $A_\mu$, and its Grassmann representation produces ghost fields.

</figcaption>
</figure>

## Prerequisites

You should know [Non-Abelian Gauge Transformations](/gauge-theories-standard-model/yang-mills/non-abelian-gauge-transformations/), [Yang–Mills Action](/gauge-theories-standard-model/yang-mills/yang-mills-action/), and [Non-Abelian Field Strength](/gauge-theories-standard-model/yang-mills/non-abelian-field-strength/). The key convention is

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
\psi\mapsto U^{-1}\psi,
$$

so that

$$
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

You should also know the Abelian prototype from [Gauge Fixing in QED](/gauge-theories-standard-model/qed/gauge-fixing-in-qed/). The QED page explains why gauge fixing is needed to invert the photon kinetic operator. This page explains the new non-Abelian feature: the gauge-fixing Jacobian is field-dependent and cannot be ignored.

## Core idea

Gauge fixing is a way to integrate over physical configurations while using redundant variables.

The variable $A_\mu^a(x)$ is convenient because it is local and Lorentz covariant. It is also redundant. A whole gauge orbit

$$
\mathcal O_A=\{A^U:U(x)\in G\}
$$

represents one physical gauge field configuration, modulo global and boundary subtleties. A path integral over all $A_\mu$ therefore counts every physical configuration infinitely many times.

A gauge condition $G(A)=0$ tries to choose one representative from each orbit. In finite-dimensional language, field space is like a manifold, gauge orbits are redundant directions, and a gauge condition is a slice transverse to those directions. The Faddeev–Popov determinant is the Jacobian that corrects the measure when we replace “integrate over everything” by “integrate over the slice and divide out the orbits.”

The method has two separate jobs:

1. remove the infinite overcounting by gauge transformations;
2. make the quadratic operator invertible so propagators exist.

In perturbation theory these jobs are aligned. The same covariant gauge-fixing term that divides the gauge orbit also supplies the missing longitudinal inverse of the gauge-field kinetic operator.

## Gauge orbits and the naive path integral

Start with pure Yang–Mills theory,

$$
S_{\mathrm{YM}}[A]
=
\int d^4x\,\left(-\frac14F_{\mu\nu}^aF^{a\mu\nu}\right).
$$

For a compact gauge group $G$, the formal unfixed partition function would be

$$
Z_{\mathrm{naive}}
=
\int \mathcal D A\,e^{iS_{\mathrm{YM}}[A]}.
$$

This expression is too large. Since

$$
S_{\mathrm{YM}}[A^U]=S_{\mathrm{YM}}[A],
$$

the integrand is constant along every gauge orbit. The path integral contains a factor like

$$
\operatorname{Vol}(\mathcal G),
$$

where $\mathcal G$ is the group of local gauge transformations. This factor is infinite in the continuum and physically meaningless.

One can write the desired object schematically as

$$
Z
=\frac{1}{\operatorname{Vol}(\mathcal G)}
\int\mathcal D A\,e^{iS_{\mathrm{YM}}[A]}.
$$

But this expression is not yet a calculational formula. Dividing by an infinite group volume does not by itself produce a propagator or Feynman rules. The Faddeev–Popov trick turns this quotient into a local-looking field integral.

## The finite-dimensional model

Before field theory, imagine an ordinary integral over variables $x^i$ with a redundancy. The variables are coordinates on a space $X$, and a group $\mathcal G$ moves points along gauge orbits. The action $S(x)$ is constant along each orbit. We want an integral over the quotient $X/\mathcal G$.

Let $G(x)=0$ be a gauge condition: a surface meant to intersect each orbit once. For a group parameter $\alpha$, write $x^\alpha$ for the transformed point. Insert

$$
1
=
\Delta_{\mathrm{FP}}(x)
\int d\alpha\,\delta\!\bigl(G(x^\alpha)\bigr).
$$

The determinant is chosen so that the identity is true. If $G$ has one component for each gauge direction, then locally

$$
\Delta_{\mathrm{FP}}(x)
=
\left|\det\left(\frac{\partial G(x^\alpha)}{\partial\alpha}\right)_{\alpha=0}\right|.
$$

This is just the multidimensional delta-function rule. If $G(x^\alpha)$ changes rapidly along the orbit, the delta function catches a small range of $\alpha$; if it changes slowly, it catches a larger range. The determinant compensates for that change of variables.

The path-integral formula is the same idea with $x$ replaced by $A_\mu^a(x)$, $d\alpha$ replaced by $\mathcal D\alpha$, and the finite determinant replaced by a functional determinant.

## The Faddeev–Popov identity

Let $G^a(A)(x)$ be a gauge-fixing functional with one Lie-algebra component at each spacetime point. We choose it so that, at least locally near the configurations of interest, every gauge orbit intersects the surface

$$
G^a(A)(x)=f^a(x)
$$

once.

The Faddeev–Popov identity is

$$
1
=
\Delta_{\mathrm{FP}}[A]
\int\mathcal D\alpha\,
\delta\!\bigl(G(A^\alpha)-f\bigr).
$$

Here $\alpha=\alpha^aT^a$ is the infinitesimal gauge parameter. The determinant is

$$
\Delta_{\mathrm{FP}}[A]
=
\det M[A],
$$

where

$$
M^{ab}(x,y;A)
=
\left.
\frac{\delta G^a(A^\alpha)(x)}{\delta\alpha^b(y)}
\right|_{\alpha=0}.
$$

In a formal derivation, one inserts this identity into the quotient path integral. Since $S[A]$, $\mathcal D A$, and $\Delta_{\mathrm{FP}}[A]$ are gauge invariant under the assumptions of perturbation theory, the integral over $\alpha$ factors out as $\operatorname{Vol}(\mathcal G)$ and cancels the same group volume in the denominator.

The result is an integral over $A_\mu$ with a delta function imposing the gauge condition:

$$
Z_f
=
\int\mathcal D A\,
\Delta_{\mathrm{FP}}[A]\,
\delta\!\bigl(G(A)-f\bigr)
\,e^{iS_{\mathrm{YM}}[A]}.
$$

This still imposes a sharp gauge condition. Covariant gauges arise by averaging over the arbitrary function $f^a(x)$ with a Gaussian weight.

## Covariant gauge averaging

Choose the Lorenz-type gauge functional

$$
G^a(A)=\partial^\mu A_\mu^a.
$$

Instead of fixing $G^a(A)=0$ sharply, average over $f^a$ with

$$
\exp\!\left[-\frac{i}{2\xi}\int d^4x\, f^a f^a\right].
$$

The delta function sets $f^a=\partial^\mu A_\mu^a$, producing

$$
\exp\!\left[-\frac{i}{2\xi}\int d^4x\,
(\partial^\mu A_\mu^a)^2\right].
$$

Thus the gauge-fixed Yang–Mills path integral becomes

$$
Z_\xi
=
\int\mathcal D A\,
\Delta_{\mathrm{FP}}[A]
\exp\left\{i\int d^4x\left[
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2
\right]\right\}.
$$

If matter fields are present, include their action and integrate over them as usual. The gauge-fixing and Faddeev–Popov factors depend only on the gauge redundancy, not on whether the gauge field is coupled to scalars or fermions.

The parameter $\xi$ labels the covariant gauge:

| Gauge | Choice | Practical use |
|---|---:|---|
| Feynman gauge | $\xi=1$ | Simplifies the gauge-field propagator numerator. |
| Landau gauge | $\xi\to0$ | Makes the propagator transverse. |
| General covariant gauge | finite $\xi$ | Tracks gauge-parameter cancellation in physical results. |

The value of $\xi$ is not a physical coupling. Proper physical observables cannot depend on it.

## Computing the Faddeev–Popov operator

Now compute $M[A]$ for the covariant gauge condition.

With

$$
U(x)=e^{ig\alpha(x)},
$$

the infinitesimal transformation of the gauge field is

$$
\delta A_\mu^a
=
\partial_\mu\alpha^a-gf^{abc}A_\mu^b\alpha^c.
$$

This is the adjoint covariant derivative acting on $\alpha$:

$$
\delta A_\mu^a=(D_\mu\alpha)^a,
\qquad
(D_\mu\alpha)^a
=\partial_\mu\alpha^a-gf^{abc}A_\mu^b\alpha^c.
$$

Therefore

$$
\delta G^a(A)
=
\partial^\mu\delta A_\mu^a
=
\partial^\mu(D_\mu\alpha)^a.
$$

So the Faddeev–Popov operator is

$$
\boxed{
M^{ab}[A]
=
\partial^\mu D_\mu^{ab}[A]
}
$$

where

$$
D_\mu^{ab}[A]c^b
=
\partial_\mu c^a-gf^{abc}A_\mu^b c^c.
$$

This is the single most important formula on the page. In Abelian gauge theory, $f^{abc}=0$, so $M=\Box$ and the determinant is independent of $A_\mu$. In non-Abelian gauge theory, $M[A]$ contains $A_\mu$, so the determinant contributes interactions.

## Ghosts as the determinant

A determinant of an ordinary bosonic operator can be represented by anticommuting variables. In field theory this becomes

$$
\det M[A]
=
\int\mathcal D\bar c\,\mathcal D c\,
\exp\left\{i\int d^4x\,
\mathcal L_{\mathrm{gh}}
\right\},
$$

where the ghost and antighost fields $c^a,\bar c^a$ are Grassmann-valued Lorentz scalars in the adjoint representation. With our convention, we use

$$
\boxed{
\mathcal L_{\mathrm{gh}}
=
-\bar c^a\partial^\mu D_\mu^{ab}c^b.
}
$$

After integrating by parts,

$$
\mathcal L_{\mathrm{gh}}
=
(\partial^\mu\bar c^a)(D_\mu c)^a.
$$

Using

$$
(D_\mu c)^a=\partial_\mu c^a-gf^{abc}A_\mu^b c^c,
$$

this becomes

$$
\mathcal L_{\mathrm{gh}}
=
(\partial^\mu\bar c^a)(\partial_\mu c^a)
-gf^{abc}(\partial^\mu\bar c^a)A_\mu^b c^c.
$$

The first term gives the ghost propagator. The second term gives a ghost–gauge-boson vertex. There is no ghost mass term in ordinary Yang–Mills covariant gauges, and there is no direct ghost–ghost–gauge–gauge vertex in this simple gauge.

Ghost fields are strange but not mysterious. They are not introduced because nature contains scalar particles with the wrong statistics. They are introduced because a determinant sits in the gauge-fixed measure, and Grassmann integrals are the efficient way to compute that determinant diagrammatically.

## The gauge-fixed Yang–Mills action

Combining the Yang–Mills, gauge-fixing, and ghost terms gives

$$
\boxed{
\mathcal L_{\mathrm{YM},\xi}
=
-\frac14F_{\mu\nu}^aF^{a\mu\nu}
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2
-\bar c^a\partial^\mu D_\mu^{ab}c^b.
}
$$

Matter terms are added by replacing ordinary derivatives with covariant derivatives in the appropriate representations:

$$
\mathcal L
=
\mathcal L_{\mathrm{YM},\xi}
+\mathcal L_{\mathrm{matter}}.
$$

The gauge-fixed quadratic gauge-field operator is now invertible, giving the covariant-gauge propagator

$$
D_{\mu\nu}^{ab}(k)
=
\frac{-i\delta^{ab}}{k^2+i\epsilon}
\left[\eta_{\mu\nu}-(1-\xi)\frac{k_\mu k_\nu}{k^2+i\epsilon}\right],
$$

with the usual convention-dependent placement of the $i\epsilon$ in the longitudinal term. This is the non-Abelian analogue of the QED photon propagator, with the additional color factor $\delta^{ab}$.

The ghost propagator has the schematic form

$$
\frac{i\delta^{ab}}{k^2+i\epsilon},
$$

up to the momentum-flow conventions used for ghost arrows. The ghost–gauge-boson vertex is proportional to $gf^{abc}$ and to the ghost momentum entering through $\partial^\mu\bar c^a$.

The next page derives these ghost rules in a more diagrammatic form. For now the important point is structural: non-Abelian gauge fixing forces a new interacting sector in perturbation theory.

## Abelian limit

Set $f^{abc}=0$. Then

$$
(D_\mu c)^a\to \partial_\mu c^a,
\qquad
M[A]\to\Box.
$$

For ordinary QED there is only one generator, so

$$
\Delta_{\mathrm{FP}}[A]=\det(\Box),
$$

which is independent of $A_\mu$. This determinant is an overall constant in correlation functions of the photon and matter fields. It can be absorbed into the normalization of $Z$.

This is why one usually does not draw ghost loops in QED. It is not because QED has no gauge fixing. It is because the Abelian ghost fields decouple in Lorenz-type gauges.

The non-Abelian case differs because

$$
M[A]
=
\partial^\mu\partial_\mu\delta^{ab}
-g f^{acb}\partial^\mu A_\mu^c
-g f^{acb}A_\mu^c\partial^\mu
$$

as an operator acting on ghost fields, with equivalent forms depending on integration by parts and index placement. The dependence on $A_\mu$ means the determinant participates in the dynamics.

## Why ghosts are required

Ghosts are easy to misunderstand because they do not appear as external particles. Their job is internal consistency.

In a covariant gauge, the gauge-field propagator includes unphysical polarizations. If one computed non-Abelian loop diagrams using only the gauge-boson propagator and self-interactions, those unphysical modes would contribute incorrectly. Ghost loops subtract precisely the pieces associated with gauge redundancy.

This is why ghosts affect real physical predictions even though ghosts are not observed as particles. For example, in the one-loop Yang–Mills beta function, ghost loops are part of the gauge-sector contribution. Dropping them gives a result that violates gauge invariance and misses the correct structure behind asymptotic freedom.

A helpful way to say it is:

$$
\text{ghosts are not particles in the spectrum; they are particles in the bookkeeping of the quotient.}
$$

BRST symmetry makes that bookkeeping precise. It pairs unphysical gauge-field modes with ghosts and organizes cancellations so that physical observables live in a cohomology rather than in the full gauge-fixed Fock space.

## What the construction assumes

The derivation above is local in field space. It assumes that the gauge condition $G(A)=f$ intersects each gauge orbit once, at least in the neighborhood of the field configurations that dominate perturbation theory.

This assumption is valid enough for perturbation theory around $A_\mu=0$ with ordinary boundary conditions. It is not a global theorem. Non-Abelian gauge theories can have Gribov copies: distinct gauge-related configurations satisfying the same gauge condition. Then the simple Faddeev–Popov gauge slice intersects an orbit more than once.

For perturbative Standard Model calculations, the local Faddeev–Popov construction is the right tool. For nonperturbative questions about confinement, topology, finite volume, and global gauge fixing, one must be more careful. That is why gauge fixing is both a workhorse and a trapdoor. Locally it is clean. Globally it can bite.

## Gauge independence and gauge dependence

The gauge-fixed action depends on $\xi$ and on the choice of $G(A)$. Intermediate quantities therefore depend on gauge fixing. This is expected.

Gauge-dependent quantities include:

| Quantity | Gauge dependence? | Reason |
|---|---|---|
| $A_\mu$ propagator | Yes | $A_\mu$ is not gauge invariant. |
| Ghost propagator | Yes | Ghosts are gauge-fixing variables. |
| Off-shell Green functions of $A_\mu$ | Usually yes | Off-shell gauge fields are not physical observables. |
| Pole masses of stable physical particles | No | Physical spectrum is gauge independent when defined correctly. |
| Gauge-invariant S-matrix elements | No | BRST/Slavnov–Taylor identities enforce cancellation. |
| Wilson-loop expectation values | No, after proper definition | The operator is gauge invariant, though calculation may use a gauge. |

A common beginner mistake is to demand that every intermediate expression be gauge invariant. That is too strong. Gauge fixing is allowed to break manifest gauge invariance in intermediate formulas. The physical requirement is that gauge-invariant observables do not depend on the arbitrary gauge choice.

## Relation to canonical quantization

The Faddeev–Popov method is a path-integral way to implement the quotient by gauge redundancy. Canonical quantization sees the same issue as constraints.

In Yang–Mills theory, the momentum conjugate to $A_0^a$ vanishes. This is a primary constraint. The equation of motion for $A_0^a$ enforces Gauss’s law, a secondary constraint. Physical states must satisfy the quantum version of Gauss’s law, and gauge transformations are generated by constraints.

The path-integral method hides much of this Hamiltonian structure but makes Lorentz covariance and Feynman rules efficient. BRST quantization is the bridge: it keeps a covariant gauge-fixed path integral while encoding the constraint structure cohomologically.

## Common pitfalls

**Pitfall 1: “Gauge fixing chooses a physical representative.”**

A gauge representative is not physical by itself. It is a coordinate choice on the space of gauge orbits. Physical statements must not depend on which representative is chosen.

**Pitfall 2: “The determinant is just a normalization.”**

It is a normalization in Abelian Lorenz gauge. It is not a normalization in non-Abelian gauge theory because $M[A]$ depends on $A_\mu$.

**Pitfall 3: “Ghosts violate spin-statistics.”**

The spin-statistics theorem applies to physical asymptotic particles in a positive-norm Hilbert space. Faddeev–Popov ghosts are auxiliary Grassmann fields in a gauge-fixed representation of a constrained system, not physical scalar particles in the spectrum.

**Pitfall 4: “Landau gauge means $\partial\cdot A=0$ exactly inside every formula.”**

Landau gauge is the $\xi\to0$ limit of covariant gauge fixing. It enforces transversality in the propagator, but quantum field theory still requires a careful limiting prescription.

**Pitfall 5: “Faddeev–Popov solves gauge fixing globally.”**

The perturbative derivation is local. Non-Abelian gauge fields can have Gribov copies, and global gauge-fixing issues are part of the nonperturbative story.

## Exercises

### Exercise 1: Abelian determinant

For QED, take

$$
A_\mu^\lambda=A_\mu+\partial_\mu\lambda,
\qquad
G(A)=\partial^\mu A_\mu.
$$

Show that the Faddeev–Popov operator is $M=\Box$ and that the determinant is independent of $A_\mu$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
G(A^\lambda)
=\partial^\mu A_\mu+\partial^\mu\partial_\mu\lambda
=G(A)+\Box\lambda.
$$

Therefore

$$
M(x,y)
=
\frac{\delta G(A^\lambda)(x)}{\delta\lambda(y)}
=\Box_x\delta^{(4)}(x-y).
$$

This contains no $A_\mu$. Hence $\det M=\det\Box$ is an overall constant in the QED path integral and can be absorbed into the normalization.

</details>

### Exercise 2: Non-Abelian Faddeev–Popov operator

Using

$$
\delta A_\mu^a=\partial_\mu\alpha^a-gf^{abc}A_\mu^b\alpha^c,
$$

and $G^a(A)=\partial^\mu A_\mu^a$, derive

$$
M^{ab}[A]=\partial^\mu D_\mu^{ab}[A].
$$

<details><summary><strong>Solution</strong></summary>

The variation of the gauge condition is

$$
\delta G^a(A)
=\partial^\mu\delta A_\mu^a.
$$

Substitute the infinitesimal gauge transformation:

$$
\delta G^a(A)
=\partial^\mu\left(\partial_\mu\alpha^a-gf^{abc}A_\mu^b\alpha^c\right).
$$

Define the adjoint covariant derivative acting on $\alpha$ by

$$
(D_\mu\alpha)^a=\partial_\mu\alpha^a-gf^{abc}A_\mu^b\alpha^c.
$$

Then

$$
\delta G^a(A)=\partial^\mu(D_\mu\alpha)^a,
$$

so the functional derivative with respect to $\alpha^b$ is the operator

$$
M^{ab}[A]=\partial^\mu D_\mu^{ab}[A].
$$

</details>

### Exercise 3: Ghost interaction

Starting from

$$
\mathcal L_{\mathrm{gh}}
=(\partial^\mu\bar c^a)(D_\mu c)^a,
\qquad
(D_\mu c)^a=\partial_\mu c^a-gf^{abc}A_\mu^b c^c,
$$

identify the free ghost term and the ghost–gauge-boson interaction.

<details><summary><strong>Solution</strong></summary>

Substitute the adjoint covariant derivative:

$$
\mathcal L_{\mathrm{gh}}
=(\partial^\mu\bar c^a)\partial_\mu c^a
-gf^{abc}(\partial^\mu\bar c^a)A_\mu^b c^c.
$$

The free term is

$$
(\partial^\mu\bar c^a)\partial_\mu c^a,
$$

which gives the ghost propagator. The interaction term is

$$
-gf^{abc}(\partial^\mu\bar c^a)A_\mu^b c^c,
$$

which gives the ghost–gauge-boson vertex. The derivative on $\bar c^a$ means the vertex carries a ghost momentum, with the precise sign depending on the momentum-flow convention.

</details>

### Exercise 4: Why the gauge-field propagator needed help

Show that the unfixed Yang–Mills quadratic operator around $A_\mu^a=0$ has a zero mode proportional to $k_\mu$ in momentum space.

<details><summary><strong>Solution</strong></summary>

The quadratic part of pure Yang–Mills around $A_\mu^a=0$ is the same as one Maxwell field for each adjoint index:

$$
\mathcal L_2
=\frac12A_\mu^a
\left(\eta^{\mu\nu}\Box-\partial^\mu\partial^\nu\right)A_\nu^a.
$$

In momentum space,

$$
K_0^{\mu\nu}(k)
=-k^2\eta^{\mu\nu}+k^\mu k^\nu.
$$

Contract with $k_\nu$:

$$
K_0^{\mu\nu}(k)k_\nu
=-k^2k^\mu+k^\mu k^2=0.
$$

Thus the longitudinal direction $A_\nu^a(k)\propto k_\nu\alpha^a(k)$ is a zero mode. The quadratic operator is not invertible before gauge fixing.

</details>

## References

### Standard first pass

- Srednicki, *Quantum Field Theory*, §71, for the path integral of non-Abelian gauge theory and its Faddeev–Popov construction.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 25, for Yang–Mills gauge invariance, Wilson lines, gluon propagators, and the perturbative setup.
- Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, Ch. 31, for the Faddeev–Popov prescription starting from a finite-dimensional analogy.

### Deeper references

- Weinberg, *The Quantum Theory of Fields*, Vol. II, §§15.4–15.6, for constraints, gauge choices, the DeWitt–Faddeev–Popov method, and ghost fields.
- Zee, *Quantum Field Theory in a Nutshell*, Part VII.1, for a compact intuitive treatment of quantizing Yang–Mills theory.
- Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, Chs. 21 and 26, for functional methods, ghost fields, and BRST/Zinn-Justin identities.

## Version history

- **2026-06-17:** Initial polished draft.
