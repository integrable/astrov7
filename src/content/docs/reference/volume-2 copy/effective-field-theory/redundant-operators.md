---
title: "Redundant Operators"
description: "How EFT operator lists are quotiented by integration by parts, equations of motion, identities, field redefinitions, and gauge redundancies."
sidebar:
  label: "Redundant Operators"
  order: 10
level: Graduate
status: "Polished draft"
source: "Burgess 2020, chs. 2–3; Georgi EFT lectures; Weinberg Vol. I; Arzt 1995; Grzadkowski et al. 2010 for SMEFT basis logic; Manohar EFT lectures."
topics:
  - effective field theory
  - redundant operators
  - equations of motion
  - integration by parts
  - operator bases
  - Wilson coefficients
canonicalTopics:
  - redundant-operators
  - eft-operator-basis
  - eom-redundancy
  - integration-by-parts
researchStatus:
  established:
    - "Redundant operators can be removed from EFT bases without changing physical observables, provided the corresponding coefficient and source transformations are handled consistently."
  active:
    - "Efficient operator-basis construction and basis conversion remain active in SMEFT, HEFT, gravitational EFT, Hilbert-series methods, amplitudes bases, evanescent-operator schemes, and automated matching tools."
---

## Summary

An EFT begins with a large list of all local operators allowed by the light fields, symmetries, and power counting:

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\le d}
+
\sum_i C_i\mathcal O_i.
$$

But the first list is almost never a basis. Some operators are **redundant**: they can be removed or related using total derivatives, integration by parts, algebraic identities, Bianchi identities, Fierz identities, equations of motion, field redefinitions, and gauge or BRST-exact structures.

The physical EFT data are not the raw list of operators. They are equivalence classes:

$$
\{\text{local operators allowed by symmetry}\}
\Big/
\{\text{redundancies}\}.
$$

Choosing an operator basis means choosing one representative for each equivalence class. Wilson coefficients are coordinates in that basis.

:::note[Redundant does not mean useless]
A redundant operator is not "wrong." It is a valid term in a Lagrangian, but it does not label an independent physical direction once the rest of the EFT is transformed consistently.
:::

## Prerequisites

You should know [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/), [Locality and Symmetry in EFT](/renormalization-rg-eft/effective-field-theory/locality-and-symmetry-in-eft/), [Power Counting](/renormalization-rg-eft/effective-field-theory/power-counting/), and [Matching](/renormalization-rg-eft/effective-field-theory/matching/).

Useful background includes [Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/), [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/), [Equations-of-Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/), and [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/).

## Core idea

An EFT operator basis is like a coordinate chart. A bad coordinate chart can describe the same physics with too many coordinates.

Suppose the raw operator list contains

$$
\mathcal O_1,
\mathcal O_2,
\mathcal O_3,
\mathcal O_E,
\partial_\mu K^\mu.
$$

If

$$
\mathcal O_E=F\,E_\phi
$$

is proportional to an equation of motion, and $\partial_\mu K^\mu$ is a total derivative that does not affect the relevant boundary conditions, then the physical basis may contain only

$$
\mathcal O_1,
\mathcal O_2,
\mathcal O_3,
$$

with shifted Wilson coefficients. Removing $\mathcal O_E$ and $\partial_\mu K^\mu$ is not throwing away physics. It is choosing a smaller coordinate system for the same physical predictions.

The short slogan is

$$
\text{basis reduction is quotienting, not forgetting.}
$$

## Setup and conventions

We write a local EFT as

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_0
+\sum_{\Delta>d}\frac{C_i}{M^{\Delta_i-d}}\mathcal O_i.
$$

Here $\mathcal L_0$ is the leading theory, $M$ is the heavy scale or organizing scale, and $\mathcal O_i$ are local operators built from light fields and derivatives.

Two Lagrangians are equivalent for a chosen class of observables if their difference can be removed by transformations that leave those observables invariant:

$$
\mathcal L
\sim
\mathcal L'
\quad\Longleftrightarrow\quad
\mathcal A_{\mathcal L}=\mathcal A_{\mathcal L'}
$$

for the amplitudes, spectra, responses, or correlation functions under discussion, with sources and boundary terms treated consistently.

For on-shell scattering in flat spacetime, the most common redundancies are:

| Redundancy | Typical form | Usual effect |
|---|---|---|
| total derivative | $\partial_\mu K^\mu$ | no contribution if boundary terms vanish |
| integration by parts | $A\partial_\mu B\sim -(\partial_\mu A)B$ | relates derivative placements |
| algebraic identity | gamma, Fierz, tensor, group identities | reduces overcomplete monomials |
| Bianchi identity | $D_{[\mu}F_{\nu\rho]}=0$ | removes gauge-field tensor redundancies |
| equation of motion | $F E_\phi$ | removable by field redefinition |
| BRST-exact term | $sX$ | trivial in physical BRST cohomology under suitable assumptions |

The words "usual" and "suitable" are intentional. Boundary observables, off-shell correlators, anomalies, nontrivial topology, and source-dependent questions can change the redundancy relation.

## Total derivatives and integration by parts

If the action contains

$$
\int d^d x\,\partial_\mu K^\mu,
$$

then by Gauss's theorem this is a boundary contribution:

$$
\int d^d x\,\partial_\mu K^\mu
=
\int_{\partial\mathcal M} d\Sigma_\mu K^\mu.
$$

For ordinary flat-space scattering with fields vanishing sufficiently fast at infinity, this term does not affect the $S$-matrix. Therefore total derivatives are usually removed from EFT bases.

Integration by parts is the local version of the same statement. For example,

$$
\int d^d x\,A\partial_\mu B
=
-\int d^d x\,(\partial_\mu A)B
+\int d^d x\,\partial_\mu(AB).
$$

Thus the two local operators

$$
A\partial_\mu B
\qquad\text{and}\qquad
-(\partial_\mu A)B
$$

are equivalent in an action when the total derivative can be dropped.

:::warning[Boundaries are not decorative]
On manifolds with boundaries, defects, interfaces, horizons, or finite regions, total derivatives can be physical. In such problems, the boundary EFT must be specified rather than silently discarded.
:::

## Algebraic identities

Many redundant operators are redundant before dynamics enters. Examples include:

$$
[\gamma^\mu,\gamma^\nu]=2\gamma^{\mu\nu},
\qquad
\gamma^\mu\gamma_\mu=d,
$$

Fierz identities for fermion bilinears, group-theory trace identities, Schouten identities, and symmetry or antisymmetry of tensors.

For gauge fields, the Bianchi identity

$$
D_\mu\widetilde F^{\mu\nu}=0
$$

in four dimensions, or equivalently

$$
D_{[\mu}F_{\nu\rho]}=0,
$$

relates operators with covariant derivatives acting on field strengths. Such identities are not optional simplifications; they are part of the definition of a nonredundant local basis.

A useful workflow is:

$$
\text{raw monomials}
\longrightarrow
\text{algebraic identities}
\longrightarrow
\text{IBP classes}
\longrightarrow
\text{EOM quotient}
\longrightarrow
\text{basis representatives}.
$$

## Equations-of-motion redundancy

Let $E_\phi=0$ be the leading equation of motion. An operator of the form

$$
\mathcal O_E=F E_\phi
$$

is called an EOM operator. By [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/), it can be removed at that order by

$$
\phi\to\phi+\frac{1}{M^n}F.
$$

This is the most important redundancy in practical EFT bases.

The subtle point is that one normally uses the **leading-order** equations of motion to reduce operators at a fixed higher order. For example, if

$$
\mathcal L
=
\mathcal L_0+\frac{1}{M^2}\mathcal L_2+\frac{1}{M^4}\mathcal L_4+\cdots,
$$

then one can use the EOM from $\mathcal L_0$ to remove EOM-proportional operators in $\mathcal L_2$. Doing so generates effects in $\mathcal L_4$ and beyond, which must be kept if the calculation reaches that order.

## A simple scalar example

Consider a real scalar EFT in four dimensions with

$$
\mathcal L_0
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4.
$$

The leading equation of motion is

$$
(\Box+m^2)\phi+\frac{\lambda}{3!}\phi^3=0.
$$

Suppose the dimension-six list contains

$$
\mathcal O_A=\phi^3\Box\phi,
\qquad
\mathcal O_B=\phi^6.
$$

Using the EOM,

$$
\phi^3\Box\phi
= -m^2\phi^4-\frac{\lambda}{3!}\phi^6
\quad\text{up to the EOM relation}.
$$

If $m\ne0$, the first term has lower engineering dimension but appears multiplied by the dimension-six coefficient; it shifts a lower-dimension coupling by a power-suppressed amount. The second shifts the coefficient of $\phi^6$.

The correct conclusion is not "set $\mathcal O_A$ to zero." The correct conclusion is:

$$
C_A\mathcal O_A+C_B\mathcal O_B
\quad\sim\quad
C_B'\mathcal O_B+\text{parameter shifts},
$$

with coefficients transformed consistently.

## Redundancy versus equations of motion inside correlators

The classical-looking statement

$$
E_\phi=0
$$

is not an operator identity inside arbitrary correlation functions. In the path integral, Schwinger–Dyson equations imply contact terms. Schematically,

$$
\left\langle E_\phi(x)\,\phi(x_1)\cdots\phi(x_n)\right\rangle
=\text{contact terms at }x=x_i.
$$

Therefore EOM operators can affect contact terms and off-shell Green functions. Their redundancy is cleanest for on-shell amplitudes and for observables whose source sector has been transformed consistently.

This is why EFT basis discussions must state what is being computed. A basis for on-shell scattering can be smaller than a basis for arbitrary off-shell source-dependent correlation functions.

## Gauge and BRST redundancies

In gauge theories, the physical operator space is not merely the space of gauge-invariant-looking monomials modulo ordinary equations of motion. Gauge fixing introduces ghosts and BRST symmetry. Physical local operators are represented by BRST cohomology classes:

$$
s\mathcal O=0,
\qquad
\mathcal O\sim\mathcal O+sX,
$$

where $s$ is the BRST differential.

This language prevents a common mistake: treating gauge-dependent or gauge-fixing operators as if they represented independent physical deformations. In a gauge-invariant EFT basis, one usually writes operators from gauge-covariant building blocks, then quotients by covariant IBP, Bianchi identities, EOM relations, and algebraic identities.

For example, in a gauge theory an operator containing

$$
D_\mu F^{\mu\nu}
$$

can often be related by the gauge-field equation of motion to matter currents. Removing it shifts matter-current operators. In a non-Abelian theory, this must be done covariantly.

## Wilson coefficients under basis changes

Suppose two operator lists are related by

$$
\mathcal O_a^{\text{old}}
=R_a{}^i\mathcal O_i^{\text{new}}
+\text{redundant terms}.
$$

Then

$$
\sum_a C_{\text{old}}^a\mathcal O_a^{\text{old}}
\sim
\sum_i C_{\text{new}}^i\mathcal O_i^{\text{new}},
$$

where

$$
C_{\text{new}}^i=C_{\text{old}}^a R_a{}^i
$$

for this simple linear relation. More generally, field redefinitions can make the transformation nonlinear in coefficients, especially beyond leading order.

This is why published Wilson coefficients are meaningless without a basis declaration. Saying

$$
C_i=3.1\times10^{-2}
$$

is incomplete until the operator normalization, scheme, scale, and basis are known.

## Evanescent operators

In dimensional regularization, one sometimes encounters **evanescent operators**: operators that vanish by four-dimensional identities but not in $d=4-2\epsilon$ dimensions.

They are tempting to call redundant. That temptation is dangerous.

An evanescent operator may multiply a $1/\epsilon$ pole and leave a finite contribution after renormalization. Therefore, at loop level, evanescent operators can affect scheme conversions and anomalous dimensions. They do not represent new four-dimensional observables, but they can be essential for consistent intermediate calculations.

The practical rule is:

$$
\text{do not remove evanescent operators by four-dimensional identities inside a }d\text{-dimensional loop calculation without a scheme prescription.}
$$

## Operator bases in practice

A good EFT operator basis should be:

| Criterion | Meaning |
|---|---|
| complete | spans all physical deformations through the target order |
| independent | no basis element is redundant under the chosen equivalence relation |
| symmetry-respecting | makes exact symmetries and selection rules visible |
| power-counted | assigns each operator a clear order in the expansion |
| scheme-aware | states dimensional-regularization, evanescent, and normalization conventions |
| usable | supports matching, running, and observable calculations without hidden translation rules |

No basis is uniquely best. A basis optimized for matching may not be the best basis for running. A basis optimized for amplitudes may hide symmetries that are visible in a Lagrangian basis. A basis optimized for phenomenology may choose operator combinations close to measured observables.

## Common pitfalls

**Counting the raw operator list as physical.** The first list contains redundancies. Count equivalence classes, not monomials.

**Saying EOM operators vanish.** They vanish on shell in a specific sense; they can contribute contact terms and shift other coefficients.

**Dropping total derivatives in boundary problems.** Total derivatives can become boundary actions, defect terms, or topological terms.

**Using four-dimensional identities in dimensional regularization too early.** Evanescent operators can leave finite effects through poles.

**Forgetting coefficient transformations.** Removing a redundant operator changes the coordinates of the EFT. A coefficient table must be transformed with the basis.

**Confusing basis dependence with physical ambiguity.** Different bases describe the same observables. The ambiguity is in coordinates, not in predictions.

## Relations to other pages

This page is the EFT counterpart of [Redundant Operators](/renormalization-rg-eft/local-operators-and-ope/redundant-operators/) in the Local Operators and OPE chapter. The present page emphasizes Wilson coefficients, EFT bases, matching, and observable calculations.

The mechanism is explained in [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/). The operator-level subtleties are developed in [Equations-of-Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/), [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), and [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/).

For applications, redundancy choices matter in [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), [Decoupling Theorem](/renormalization-rg-eft/effective-field-theory/decoupling-theorem/), and later pages on major EFTs.

## Research status

The conceptual status of redundant operators is settled: physical predictions are invariant under changes of local operator basis when transformations are performed consistently.

The technical frontier is still lively. Large EFTs require systematic basis construction, often using Hilbert series, amplitude methods, integration-by-parts algorithms, Fierz reduction, flavor symmetries, and computer algebra. Loop-level calculations require careful treatment of evanescent operators, scheme dependence, anomalous-dimension matrices, and basis conversions. Gauge and gravitational EFTs add BRST/BV and field-redefinition subtleties.

## Exercises

### Exercise 1: Integration by parts relation

Show that for scalar fields in flat spacetime,

$$
\phi^2\partial_\mu\phi\partial^\mu\phi
\sim
-\frac13\phi^3\Box\phi,
$$

where $\sim$ means equality inside the action up to a total derivative.

<details><summary><strong>Solution</strong></summary>

Use

$$
\partial_\mu(\phi^3\partial^\mu\phi)
=3\phi^2\partial_\mu\phi\partial^\mu\phi+
\phi^3\Box\phi.
$$

Therefore

$$
\phi^2\partial_\mu\phi\partial^\mu\phi
=\frac13\partial_\mu(\phi^3\partial^\mu\phi)
-\frac13\phi^3\Box\phi.
$$

Inside an action with no boundary contribution, the total derivative can be dropped, giving

$$
\phi^2\partial_\mu\phi\partial^\mu\phi
\sim
-\frac13\phi^3\Box\phi.
$$

</details>

### Exercise 2: EOM reduction with a mass

Using the free scalar equation of motion $(\Box+m^2)\phi=0$, reduce

$$
\mathcal O=\phi^3\Box\phi
$$

inside an on-shell EFT basis. What is the interpretation of the result?

<details><summary><strong>Solution</strong></summary>

The free EOM gives

$$
\Box\phi=-m^2\phi.
$$

Therefore

$$
\phi^3\Box\phi
\sim
-m^2\phi^4.
$$

The operator does not disappear into nothing. It shifts the coefficient of the lower-dimension operator $\phi^4$ by an amount proportional to the power-suppressed coefficient multiplying $\mathcal O$. In a mass-independent counting one must track whether $m$ is treated as small, comparable to the low scale, or part of the leading theory.

</details>

### Exercise 3: Coefficients under a linear basis change

Suppose

$$
\mathcal O_1^{\text{old}}=\mathcal O_A,
\qquad
\mathcal O_2^{\text{old}}=\mathcal O_A+2\mathcal O_B.
$$

If

$$
\Delta\mathcal L=C_1\mathcal O_1^{\text{old}}+C_2\mathcal O_2^{\text{old}},
$$

find the coefficients of $\mathcal O_A$ and $\mathcal O_B$ in the new basis.

<details><summary><strong>Solution</strong></summary>

Substitute the old operators:

$$
\Delta\mathcal L
=C_1\mathcal O_A+C_2(\mathcal O_A+2\mathcal O_B).
$$

Therefore

$$
\Delta\mathcal L
=(C_1+C_2)\mathcal O_A+2C_2\mathcal O_B.
$$

The new coefficients are

$$
C_A=C_1+C_2,
\qquad
C_B=2C_2.
$$

A basis change is therefore also a coefficient transformation.

</details>

## References

- C. P. Burgess, *Introduction to Effective Field Theory*, especially chapters on effective actions, redundant interactions, matching, and power counting.
- Howard Georgi, EFT lectures, for the practical logic of writing all operators and removing redundancies.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, for field redefinitions and effective interactions.
- C. Arzt, "Reduced Effective Lagrangians," *Physics Letters B* **342** (1995) 189–195.
- B. Grzadkowski, M. Iskrzynski, M. Misiak, and J. Rosiek, "Dimension-Six Terms in the Standard Model Lagrangian," *Journal of High Energy Physics* **10** (2010) 085.
- Aneesh V. Manohar, EFT lecture notes, for operator bases, matching, and running.
- Henning, Lu, Melia, and Murayama, Hilbert-series papers on systematic operator counting.

## Version history

- 2026-06-18: First polished draft. Added the quotient view of EFT bases, IBP/EOM/algebraic/BRST redundancies, evanescent-operator caveats, coefficient transformations, and exercises.
