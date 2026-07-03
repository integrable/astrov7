---
title: "c-, F-, and a-Theorem Preview"
description: "A status-aware preview of RG monotonicity theorems in two, three, and four dimensions, including what they say, what they do not say, and how they constrain RG flow."
sidebar:
  label: "c-, F-, and a-Theorem Preview"
  order: 60
level: Advanced
status: "Polished draft"
source: "Zamolodchikov 1986; Cardy 1988; Komargodski and Schwimmer 2011; Casini and Huerta 2012; Casini, Huerta, and Myers 2011; Coleman 1985, Dilatations; Osborn 1991; Zinn-Justin 2021"
topics:
  - RG monotonicity
  - c-theorem
  - F-theorem
  - a-theorem
  - trace anomaly
  - entanglement entropy
  - local renormalization group
canonicalTopics:
  - rg-monotonicity
  - c-theorem
  - f-theorem
  - a-theorem
researchStatus:
  established:
    - "In two dimensions there is a local c-function that decreases along unitary Lorentz-invariant RG flows and equals the Virasoro central charge at conformal fixed points; in four dimensions the a-anomaly decreases between unitary conformal fixed points connected by RG flow; in three dimensions the sphere free energy/finite entanglement term decreases under broad assumptions."
  active:
    - "The sharpest assumptions behind monotonicity, the best higher-dimensional generalizations, and the relation between monotonicity, scale versus conformal invariance, defects, boundaries, nonunitarity, and nonrelativistic systems remain active research themes."
---

## Summary

The renormalization group organizes QFTs as flows in theory space. A natural question is whether RG flow is **irreversible**: once high-energy degrees of freedom are coarse-grained away, can the theory ever return to where it started?

In some dimensions and under important assumptions, the answer is controlled by monotonic quantities:

| Dimension | Name | Fixed-point value | Monotonic statement |
|---:|---|---|---|
| $d=2$ | $c$-theorem | Virasoro central charge $c$ | $c_{\mathrm{UV}}>c_{\mathrm{IR}}$ for nontrivial unitary flows |
| $d=3$ | $F$-theorem | $F=-\log |Z_{S^3}|$ | $F_{\mathrm{UV}}>F_{\mathrm{IR}}$ |
| $d=4$ | $a$-theorem | Euler trace-anomaly coefficient $a$ | $a_{\mathrm{UV}}>a_{\mathrm{IR}}$ |

These statements are not interchangeable slogans. The quantities $c$, $F$, and $a$ are different objects, defined in different ways, with different proofs and caveats. Their common message is that **unitary local RG flow has an arrow**.

The most useful mental picture is:

<figure class="doc-figure" style="--figure-width: 47rem; --caption-width: 54rem;">

![RG monotonicity map for the c-, F-, and a-theorem](/figures/renormalization-rg-eft/rg-monotonicity-theorems.svg)

<figcaption>

In dimensions $2$, $3$, and $4$, different quantities play the role of a monotone measure of RG flow: the two-dimensional central charge $c$, the three-dimensional sphere free energy $F$, and the four-dimensional Euler anomaly $a$. Each decreases from UV to IR along ordinary unitary flows, though the precise definition and proof depend strongly on the dimension.

</figcaption>
</figure>

This page is a preview. It gives enough structure to use these theorems correctly in RG reasoning; it does not prove them in full technical detail.

## Prerequisites

You should know the ideas of [fixed points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [linearized RG flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [scale invariance](/renormalization-rg-eft/fixed-points-critical-phenomena/scale-invariance/), [beta functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), and [local RG](/renormalization-rg-eft/advanced-rg-methods/local-renormalization-group/). It also helps to have seen [anomalous dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/) and the [operator product expansion](/renormalization-rg-eft/local-operators-and-ope/ope-and-short-distance-expansion/).

The essential background fact is that at a conformal fixed point the stress tensor has special correlation functions, and in curved spacetime the expectation value of its trace can contain geometric anomaly terms.

## Core idea

An RG flow is a one-parameter family of descriptions. With $t=\log\mu$,

$$
\frac{dg^i}{dt}=\beta^i(g).
$$

A monotonicity theorem says that there exists a quantity $M(g)$ such that, along physical RG flow from UV to IR,

$$
M_{\mathrm{UV}}\ge M_{\mathrm{IR}},
$$

with equality only in special cases.

One must be careful with the direction of RG time. Since $t=\log\mu$ increases toward the UV, a quantity that **decreases toward the IR** often satisfies

$$
\frac{dM}{dt}\ge 0.
$$

Equivalently, with IR time $\ell=-t$,

$$
\frac{dM}{d\ell}\le 0.
$$

A common local form is a gradient-like relation

$$
\partial_i M = G_{ij}\beta^j+\cdots,
$$

so that

$$
\frac{dM}{dt}
=
\beta^i\partial_i M
=
G_{ij}\beta^i\beta^j+\cdots.
$$

If $G_{ij}$ is positive and the omitted terms are controlled, monotonicity follows. The actual theorems are subtler than this cartoon, but the cartoon captures the dream: **irreversibility follows from positivity**.

:::note[The slogan, with caveats]
The slogan is “degrees of freedom decrease along RG flow.” The caveat is that $c$, $F$, and $a$ are not literal particle counts. They are precise observables or anomaly coefficients that coincide with useful notions of size at fixed points.
:::

## Two dimensions: the c-theorem

In two-dimensional unitary Lorentz-invariant QFT, Zamolodchikov constructed a function $C(g,\mu)$ with three properties:

1. $C$ decreases from UV to IR.
2. At a conformal fixed point, $C$ equals the central charge $c$.
3. The rate of change is controlled by positive stress-tensor two-point data.

At a two-dimensional CFT, the holomorphic stress tensor satisfies

$$
T(z)T(0)
\sim
\frac{c/2}{z^4}
+\frac{2T(0)}{z^2}
+\frac{\partial T(0)}{z}
+\cdots.
$$

The coefficient $c$ measures the normalization of stress-tensor fluctuations. It also appears in the curved-background trace anomaly. With common Euclidean conventions,

$$
\langle T^i{}_i\rangle
=
-\frac{c}{24\pi}R,
$$

up to sign conventions for $T_{ij}$ and curvature. The important point is invariant: at a fixed point, $c$ is a universal number.

For a massive deformation of a two-dimensional CFT that flows to a trivial gapped theory,

$$
c_{\mathrm{UV}}>0,
\qquad
c_{\mathrm{IR}}=0.
$$

For a flow from one nontrivial CFT to another,

$$
c_{\mathrm{UV}}>c_{\mathrm{IR}}.
$$

This result gives a powerful ordering principle for two-dimensional critical theories. It rules out RG cycles, forbids flows from smaller to larger central charge, and turns many proposed phase diagrams into consistency checks.

## Three dimensions: the F-theorem

Odd-dimensional CFTs have no local Weyl anomaly of the same type as even-dimensional CFTs. In three dimensions, the useful fixed-point quantity is instead the finite part of the Euclidean partition function on the round three-sphere:

$$
F\equiv -\log |Z_{S^3}|.
$$

The $F$-theorem states, under standard assumptions of unitarity and locality, that

$$
F_{\mathrm{UV}}>F_{\mathrm{IR}}
$$

for nontrivial RG flows between three-dimensional fixed points.

There is also an entanglement interpretation. For a disk region in flat three-dimensional spacetime, the vacuum entanglement entropy has the schematic form

$$
S(R)
=
\alpha\frac{R}{\epsilon}
-
F
+\cdots
$$

at a CFT, where $\epsilon$ is a UV cutoff. The area-law coefficient $\alpha$ is not universal. The constant term $F$ is universal. This is one reason the $F$-theorem is often viewed as a statement about entanglement decreasing under coarse graining.

For a free real scalar and a free Dirac fermion in three dimensions, $F$ is positive. A massive deformation flows to a trivial gapped theory with $F_{\mathrm{IR}}=0$, modulo topological field theory subtleties. For flows to interacting CFTs, the theorem supplies nonperturbative inequalities. In supersymmetric theories, localization often computes $Z_{S^3}$ exactly enough to test these inequalities sharply.

:::caution[Topological theories and finite terms]
A gapped infrared theory need not be completely trivial. If the IR contains a topological field theory, the constant term in entanglement or the sphere partition function can carry topological information. Always state what is meant by “trivial IR.”
:::

## Four dimensions: the a-theorem

In four-dimensional CFT, the trace anomaly on a curved background has the schematic form

$$
\langle T^\mu{}_\mu\rangle
=
\frac{1}{(4\pi)^2}
\left(
c\,W_{\mu\nu\rho\sigma}W^{\mu\nu\rho\sigma}
-
a\,E_4
+
b\,\Box R
\right),
$$

where $W_{\mu\nu\rho\sigma}$ is the Weyl tensor and

$$
E_4
=
R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
-
4R_{\mu\nu}R^{\mu\nu}
+
R^2
$$

is the Euler density. The coefficient $b$ is scheme dependent because it can be shifted by a local $R^2$ counterterm. The coefficients $a$ and $c$ are CFT data.

The four-dimensional monotonic quantity is $a$, not $c$:

$$
a_{\mathrm{UV}}>a_{\mathrm{IR}}.
$$

The modern proof uses the dilaton effective action. If an RG flow breaks conformal symmetry between a UV and IR fixed point, one can introduce a compensating scalar field $\tau$, the dilaton, to keep track of Weyl transformations. The anomaly mismatch

$$
\Delta a = a_{\mathrm{UV}}-a_{\mathrm{IR}}
$$

appears as a universal Wess–Zumino term in the dilaton effective action. Unitarity and analyticity of the dilaton scattering amplitude imply

$$
\Delta a>0
$$

for a nontrivial flow.

This is a deep result. It says that four-dimensional unitary RG flow cannot wander forever in a way that would bring $a$ back to its starting value, unless the apparent motion is a redundancy rather than physical coarse graining.

## Why different dimensions use different quantities

The dimension dependence is not an accident. Conformal field theories have universal stress-tensor data in all dimensions, but not every such datum is monotone.

In two dimensions, the central charge $c$ plays several roles at once: it normalizes the stress-tensor two-point function, appears in the Weyl anomaly, and decreases along RG flow.

In four dimensions, the stress-tensor two-point coefficient is usually called $c$, but it is **not** the monotone in general. The monotone is the Euler-anomaly coefficient $a$.

In three dimensions, there is no local Weyl anomaly on a closed odd-dimensional manifold. The useful quantity is instead the finite part of the sphere free energy or the corresponding finite entanglement term.

A compact way to remember the pattern is:

$$
\begin{array}{ccl}
d=2 &:& \text{local anomaly and stress-tensor normalization coincide in }c,\\
d=3 &:& \text{sphere free energy }F\text{ is the useful finite quantity},\\
d=4 &:& \text{Euler anomaly }a\text{ is monotone, not the }c\text{ anomaly}.
\end{array}
$$

Do not extrapolate the name. The letter is less important than the definition.

## What these theorems forbid

Monotonicity theorems forbid several tempting but wrong pictures of RG flow.

First, they forbid ordinary periodic RG cycles in the space of physical theories. If a flow returns to the same physical theory after finite RG time, a strictly decreasing quantity could not return to its original value.

Second, they constrain “duality cascades” and repeated-looking flows. If the theory seems to repeat, either the effective number of degrees of freedom must decrease in a precise way, or the repetition is a change of variables, a large gauge transformation, a duality identification, or an artifact of a truncation.

Third, they constrain flows between candidate fixed points. If a proposed flow has

$$
a_{\mathrm{IR}}>a_{\mathrm{UV}}
$$

in four dimensions, or analogous inequalities in two or three dimensions, something is wrong: the flow direction, the fixed-point identification, the normalization, the assumptions, or the calculation.

Fourth, they constrain emergent sectors. If a UV theory splits into decoupled IR sectors,

$$
\mathcal T_{\mathrm{IR}}
=
\mathcal T_1\otimes \mathcal T_2,
$$

then additive quantities obey

$$
M_{\mathrm{IR}}=M_1+M_2.
$$

The UV value must still be large enough to supply the sum.

## What these theorems do not say

They do not say that the Hilbert-space dimension literally decreases. A continuum QFT has infinitely many states in any nontrivial volume. The theorem concerns universal fixed-point data, not a finite-dimensional state count.

They do not say that every coupling decreases. Relevant couplings usually grow toward the IR. Irrelevant couplings shrink. Marginal couplings can do either. The monotone is a global measure along the flow, not each coordinate.

They do not say that perturbation theory always knows the answer. Some monotonicity statements are nonperturbative; perturbative beta functions can obscure the theorem if variables are badly chosen or if a truncation is inconsistent.

They do not say that all dimensions have a simple $c$-function. Higher-dimensional generalizations are subtle. There are candidate quantities, entropic constructions, local RG formulae, and holographic analogues, but each has assumptions.

They do not say that nonunitary theories obey the same constraints. Nonunitary statistical systems, logarithmic CFTs, gauge-fixed descriptions before restricting to the physical sector, and theories with ghosts require separate care.

## Relation to local RG

The local renormalization group upgrades couplings to spacetime-dependent sources $g^i(x)$ and studies Weyl transformations of the generating functional,

$$
\Delta_\sigma W
=
\int d^d x\,\sqrt g\,\sigma(x)
\left(
2g_{\mu\nu}\frac{\delta W}{\delta g_{\mu\nu}}
-
\beta^i\frac{\delta W}{\delta g^i}
+\cdots
\right).
$$

Wess–Zumino consistency,

$$
[\Delta_{\sigma_1},\Delta_{\sigma_2}]W=0,
$$

imposes nontrivial relations among beta functions, anomaly coefficients, and operator mixing. In two and four dimensions, these relations are closely related to gradient-like formulae for monotonic quantities.

This perspective is valuable because it separates three notions that are often blurred:

| Object | Meaning |
|---|---|
| beta function | coordinate expression for flow in coupling space |
| anomaly coefficient | fixed-point datum in a curved-background generating functional |
| monotone function | quantity that changes with a definite sign along physical RG flow |

At a fixed point these may collapse into a simple statement. Away from a fixed point they are distinct.

## Holographic intuition

In holographic examples, a $d$-dimensional RG flow is often represented by a $(d+1)$-dimensional domain-wall geometry. The radial coordinate plays the role of scale. Under appropriate energy conditions in the bulk, one can construct a function that decreases from the boundary UV region to the interior IR region.

This is not a proof of the field-theory theorem in general. It is, however, a useful intuition: monotonicity is tied to positivity, causality, and the impossibility of creating short-distance degrees of freedom by coarse graining.

## Common pitfalls

**Using the wrong letter.** In four dimensions, the monotone is $a$, not the stress-tensor two-point coefficient usually called $c$.

**Ignoring assumptions.** Unitarity, locality, Lorentz invariance, reflection positivity, existence of fixed points, and the absence of accidental subtleties matter.

**Treating a scheme-dependent quantity as universal.** The $\Box R$ coefficient in the four-dimensional trace anomaly can be shifted by local counterterms. It is not the $a$-theorem quantity.

**Confusing free energy with thermodynamic free energy.** In the $F$-theorem, $F=-\log |Z_{S^3}|$ is a Euclidean sphere quantity for the CFT, not an ordinary finite-temperature free energy density.

**Assuming every RG trajectory is a gradient flow.** Monotonicity does not necessarily mean the beta-function vector field is globally the gradient of a scalar in a simple coordinate system.

**Forgetting redundancies.** Some apparent cyclic or recurrent flows are motion along field redefinitions or flavor rotations. Monotonicity constrains physical theory space, not arbitrary coordinates before quotienting by redundancies.

## Relations to other pages

This page belongs after [Local Renormalization Group](/renormalization-rg-eft/advanced-rg-methods/local-renormalization-group/) and [Conformal Perturbation Theory](/renormalization-rg-eft/advanced-rg-methods/conformal-perturbation-theory/). It prepares the reader for [Limit Cycles and Exotic RG Flows](/renormalization-rg-eft/advanced-rg-methods/limit-cycles-and-exotic-rg-flows/), where recurrent trajectories are discussed under the shadow of monotonicity.

For fixed-point background, see [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/) and [Scale Invariance](/renormalization-rg-eft/fixed-points-critical-phenomena/scale-invariance/). For the operator viewpoint, see [Anomalous Dimensions of Operators](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimensions-of-operators/) and [OPE and Short-Distance Expansion](/renormalization-rg-eft/local-operators-and-ope/ope-and-short-distance-expansion/).

## Research status

The two-dimensional $c$-theorem is a mature theorem and a foundational part of two-dimensional QFT. The four-dimensional $a$-theorem is also established for unitary flows between conformal fixed points, with the dilaton-scattering proof giving a particularly physical route. The three-dimensional $F$-theorem has strong proofs and many checks, especially through entanglement and supersymmetric localization.

The frontier is not whether these famous results are useful. It is how far their logic extends. Active directions include monotonicity with boundaries and defects, nonrelativistic systems, nonunitary theories, higher-form symmetries, generalized entanglement measures, higher-dimensional analogues, local RG refinements, and the relation between monotonicity and the precise conditions under which scale invariance implies conformal invariance.

## Exercises

### Exercise 1: Direction of the inequality

Suppose an RG flow in four dimensions runs from a UV CFT with $a_{\mathrm{UV}}=7/90$ to an IR CFT with $a_{\mathrm{IR}}=1/90$. Is this compatible with the $a$-theorem? What if the labels UV and IR are swapped?

<details><summary><strong>Solution</strong></summary>

The $a$-theorem requires

$$
a_{\mathrm{UV}}>a_{\mathrm{IR}}
$$

for a nontrivial unitary flow between four-dimensional conformal fixed points. Since

$$
\frac{7}{90}>\frac{1}{90},
$$

the first assignment is compatible with monotonicity. If the labels are swapped, the flow would require

$$
\frac{1}{90}>\frac{7}{90},
$$

which is impossible under the theorem's assumptions. One of the assumptions, the flow direction, or the fixed-point identification would have to be wrong.

</details>

### Exercise 2: A gradient-flow cartoon

Assume there is a scalar function $M(g)$ and a positive-definite metric $G_{ij}$ such that

$$
\partial_i M=G_{ij}\beta^j.
$$

Show that $M$ increases with $t=\log\mu$ and therefore decreases toward the IR.

<details><summary><strong>Solution</strong></summary>

Along RG flow,

$$
\frac{dM}{dt}
=
\frac{dg^i}{dt}\partial_i M
=
\beta^iG_{ij}\beta^j.
$$

Since $G_{ij}$ is positive definite,

$$
\beta^iG_{ij}\beta^j\ge 0,
$$

with equality only if $\beta^i=0$. Thus $M$ is nondecreasing as $t=\log\mu$ increases toward the UV. Equivalently, along IR time $\ell=-t$,

$$
\frac{dM}{d\ell}
=
-\frac{dM}{dt}
\le 0.
$$

So $M$ decreases toward the IR.

</details>

### Exercise 3: Why periodic physical flows clash with monotonicity

Let $g^i(t)$ be a periodic RG trajectory in physical coupling space with period $T$:

$$
g^i(t+T)=g^i(t).
$$

Suppose there is a strictly monotone function $M$ along every nontrivial physical flow. Explain why this is impossible.

<details><summary><strong>Solution</strong></summary>

Since the trajectory is periodic in physical coupling space,

$$
M(g(t+T))=M(g(t)).
$$

But strict monotonicity along a nontrivial physical RG flow would imply either

$$
M(g(t+T))>M(g(t))
$$

if measured toward the UV, or

$$
M(g(t+T))<M(g(t))
$$

if measured toward the IR. Either way, $M$ cannot return to its original value after one period. Therefore a genuine periodic trajectory in physical theory space is incompatible with strict monotonicity. If an apparent cycle exists, it must evade at least one assumption: it may be nonunitary, nonlocal, not relativistic, only a coordinate artifact, a motion along redundancies, or outside the theorem's domain.

</details>

## References

- A. B. Zamolodchikov, “Irreversibility of the Flux of the Renormalization Group in a 2D Field Theory,” *JETP Letters* **43** (1986) 730–732.
- J. L. Cardy, “Is There a c-Theorem in Four Dimensions?,” *Physics Letters B* **215** (1988) 749–752.
- Z. Komargodski and A. Schwimmer, “On Renormalization Group Flows in Four Dimensions,” *Journal of High Energy Physics* **1112** (2011) 099.
- H. Osborn, “Weyl Consistency Conditions and a Local Renormalization Group Equation for General Renormalizable Field Theories,” *Nuclear Physics B* **363** (1991) 486–526.
- H. Casini and M. Huerta, “On the RG Running of the Entanglement Entropy of a Circle,” for the entropic route to the three-dimensional $F$-theorem.
- H. Casini, M. Huerta, and R. C. Myers, “Towards a Derivation of Holographic Entanglement Entropy,” for the sphere-entanglement/free-energy map.
- D. L. Jafferis, “The Exact Superconformal R-Symmetry Extremizes $Z$,” for the role of $S^3$ partition functions in three-dimensional supersymmetric theories.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for RG, critical phenomena, and field-theoretic scaling.
- S. Coleman, *Aspects of Symmetry*, especially “Dilatations,” for scale transformations, anomalous dimensions, and the Callan–Symanzik viewpoint.

## Version history

- 2026-06-19: First polished draft. Added dimension-by-dimension monotonicity map, theorem statements, caveats, local RG relation, exercises, and references.
