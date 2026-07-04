---
title: "Lightcone Bootstrap"
description: "How crossing symmetry in a lightcone limit forces large-spin double-twist operators and universal asymptotic CFT data."
sidebar:
  label: "Lightcone Bootstrap"
  order: 1
level: Advanced
status: "Polished draft"
source: "Fitzpatrick, Kaplan, Poland, and Simmons-Duffin; Komargodski and Zhiboedov; Simmons-Duffin TASI lectures; Poland, Rychkov, and Vichi 2019."
topics:
  - lightcone bootstrap
  - analytic conformal bootstrap
  - large spin
  - double-twist operators
  - crossing symmetry
canonicalTopics:
  - lightcone-bootstrap
  - large-spin-double-twist
  - analytic-crossing-limits
researchStatus:
  established:
    - "In unitary CFTs with suitable assumptions, crossing symmetry implies large-spin double-twist families whose twists approach sums of external operator dimensions plus even integers."
  active:
    - "Current research extends lightcone bootstrap ideas to finite spin, spinning correlators, defects, nonunitary theories, Lorentzian inversion, thermal systems, and holographic regimes."
---

## Summary

The **lightcone bootstrap** is the analytic argument that crossing symmetry forces universal large-spin operators in any sufficiently nice unitary CFT. For two scalar primaries $\mathcal O_1$ and $\mathcal O_2$, the OPE contains large-spin families whose dimensions approach

$$
\Delta_{n,\ell}
=\Delta_1+\Delta_2+2n+\ell+\gamma_{n,\ell},
\qquad
\gamma_{n,\ell}\to0
\quad
(\ell\to\infty).
$$

These are called **double-twist operators**:

$$
[\mathcal O_1\mathcal O_2]_{n,\ell}.
$$

In large-$N$ theories they are often literally double-trace operators. In a generic CFT, the name means something more general: they are asymptotic families whose twist approaches

$$
\tau_{n}=\Delta_{n,\ell}-\ell
\to
\Delta_1+\Delta_2+2n.
$$

The lightcone bootstrap explains why large-spin CFT data are universal. Identity exchange in one channel forces mean-field-like double-twist data in the crossed channel. Low-twist operators beyond the identity then generate anomalous dimensions and OPE-coefficient corrections.

The slogan is

$$
\text{crossing near the lightcone}
\quad\Longrightarrow\quad
\text{large-spin double-twist spectrum}.
$$

## Prerequisites

Read [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/), [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/), [Operator Product Expansion](/cft-bootstrap/operator-product-expansion/), [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), and [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/) first.

You should know the scalar cross-ratios

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z),
$$

and the definition of twist:

$$
\tau=\Delta-\ell.
$$

The page uses Euclidean formulas as the starting point, but the physics is Lorentzian in spirit: the key singular limits are lightlike OPE limits.

## Core idea

Consider a four-point function of scalar primaries. One OPE channel may be dominated by the identity operator. Crossing symmetry says that the same singular behavior must be reproduced in the crossed channel.

But the crossed channel cannot reproduce the identity singularity with one ordinary finite-spin operator. Instead, it needs an infinite tower of large-spin operators. Their twists must accumulate near specific values.

For identical scalars $\phi$, the first tower has

$$
\tau_{0,\ell}\to2\Delta_\phi
\qquad
\ell\to\infty.
$$

More generally, there are towers

$$
\tau_{n,\ell}\to2\Delta_\phi+2n,
\qquad
n=0,1,2,\ldots .
$$

This is the same spectrum as generalized free field at leading large spin. Interactions appear through anomalous dimensions

$$
\gamma_{n,\ell}
$$

that vanish as $\ell$ becomes large.

The surprising part is not that generalized free fields have double-twist operators. The surprising part is that crossing forces similar large-spin families in generic unitary CFTs.

## Setup and conventions

For identical scalar primaries $\phi$ of dimension $\Delta_\phi$, write

$$
\langle\phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}\mathcal G(z,\bar z),
$$

with

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z).
$$

The $12\to34$ channel conformal block expansion is

$$
\mathcal G(z,\bar z)
=\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(z,\bar z).
$$

Identical-scalar crossing can be written as

$$
\mathcal G(z,\bar z)
=\left(\frac{z\bar z}{(1-z)(1-\bar z)}\right)^{\Delta_\phi}
\mathcal G(1-z,1-\bar z).
$$

Equivalently,

$$
[(1-z)(1-\bar z)]^{\Delta_\phi}\mathcal G(z,\bar z)
=(z\bar z)^{\Delta_\phi}\mathcal G(1-z,1-\bar z).
$$

The lightcone bootstrap studies this equation in limits where one pair of points becomes null-separated.

## The lightcone limit

A basic lightcone limit is

$$
z\to0,
\qquad
\bar z\text{ fixed}.
$$

In Lorentzian kinematics, $z$ and $\bar z$ can vary independently, and $z\to0$ corresponds to a lightlike OPE limit. In Euclidean kinematics, $z$ and $\bar z$ are complex conjugates, so this limit is best understood by analytic continuation.

In the $12\to34$ channel, an exchanged operator of dimension $\Delta$ and spin $\ell$ contributes at small $z$ like

$$
G_{\Delta,\ell}(z,
\bar z)\sim z^{\tau/2}\,k_{\Delta+\ell}(\bar z)+\cdots,
$$

where

$$
\tau=\Delta-\ell.
$$

Thus the leading lightcone behavior is controlled by the lowest twist operators.

The identity has twist zero and gives the strongest singular or leading contribution. Other low-twist operators give subleading corrections.

This is why twist, not dimension alone, is the natural organizing variable in analytic bootstrap.

## Crossing and the need for large spin

Take the crossing equation and examine the region

$$
z\to0,
\qquad
\bar z\to1.
$$

In one channel, the identity contribution is simple. In the crossed channel, the factor

$$
(1-ar z)^{-\Delta_\phi}
$$

must be reproduced by a sum over conformal blocks.

A finite number of finite-spin blocks cannot reproduce the required singularity. The crossed-channel sum needs infinitely many operators with arbitrarily large spin.

The result is that the $\phi\times\phi$ OPE must contain operators whose twists approach

$$
2\Delta_\phi+2n.
$$

These are the double-twist families:

$$
[\phi\phi]_{n,\ell}.
$$

At large spin,

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell+\gamma_{n,\ell},
$$

with

$$
\gamma_{n,\ell}\to0.
$$

This is the lightcone bootstrap theorem in its most learner-friendly form.

## Double-twist operators

The schematic form of a double-twist operator is

$$
[\phi\phi]_{n,\ell}\sim
\phi\,\partial_{\mu_1}\cdots\partial_{\mu_\ell}(\partial^2)^n\phi
-\text{traces and descendants}.
$$

In generalized free field, this schematic expression is close to literal. In an interacting CFT, the true primary can mix with other operators of the same quantum numbers. The universal statement is asymptotic:

$$
\tau_{n,\ell}	o2\Delta_\phi+2n
\qquad
(\ell\to\infty).
$$

For non-identical scalar primaries $\mathcal O_1$ and $\mathcal O_2$, crossing implies families

$$
[\mathcal O_1\mathcal O_2]_{n,\ell}
$$

with

$$
\Delta_{n,\ell}	o\Delta_1+\Delta_2+2n+\ell.
$$

Spin selection rules depend on whether the external operators are identical and on global-symmetry representations.

## Identity exchange and mean-field data

The leading lightcone result comes from identity exchange. For identical scalars, identity exchange in one channel forces the leading large-spin data to match generalized free field:

$$
\Delta_{n,\ell}^{(0)}=2\Delta_\phi+2n+\ell.
$$

The corresponding OPE coefficients also approach their generalized-free values:

$$
a_{n,\ell}	o a_{n,\ell}^{\rm GFF}
$$

in the appropriate large-spin limit.

This is why generalized free field appears so often in analytic bootstrap. It is not merely a special model. It is the universal zeroth-order approximation to large-spin double-twist data.

Interactions show up as corrections:

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell+\gamma_{n,\ell},
$$

and

$$
a_{n,\ell}=a_{n,\ell}^{\rm GFF}\left(1+\delta a_{n,\ell}+\cdots\right).
$$

The identity gives the skeleton. Nontrivial operators bend the skeleton.

## Corrections from low-twist exchange

Suppose the lowest non-identity operator exchanged in the crossed channel has twist

$$
\tau_m.
$$

Then it produces corrections to double-twist data at large spin. Schematically, the anomalous dimension behaves like

$$
\gamma_{n,\ell}\sim -\frac{\text{positive coefficient}}{J^{\tau_m}}
$$

in many unitary identical-scalar setups, where $J$ is the conformal spin. The exact coefficient depends on dimensions, spins, OPE coefficients, and normalization conventions.

The conformal spin is often defined by

$$
J^2=\left(\ell+\Delta_\phi+n+\frac{\gamma_{n,\ell}}2\right)
\left(\ell+\Delta_\phi+n-1+\frac{\gamma_{n,\ell}}2\right)
$$

for identical scalars, up to convention and subleading refinements.

The sign and magnitude of $\gamma_{n,\ell}$ carry physical information. For example, stress-tensor exchange produces universal attractive corrections in many contexts, related to causality and energy positivity.

The qualitative rule is:

$$
\text{lower twist exchange}\quad\Rightarrow\quad\text{larger large-spin correction}.
$$

## Physical picture on the cylinder

Radial quantization maps the CFT to a theory on

$$
\mathbb R\times S^{d-1}.
$$

An operator of dimension $\Delta$ creates a state of energy $\Delta$. A double-twist operator behaves like a two-particle state made from two primary excitations with orbital angular momentum $\ell$.

At large spin, the two constituents are far apart on the sphere. Their interaction becomes weak, so the energy approaches the sum of the individual energies plus orbital excitation:

$$
\Delta_{n,\ell}\approx \Delta_1+\Delta_2+2n+\ell.
$$

The anomalous dimension

$$
\gamma_{n,\ell}
$$

is the interaction energy of this two-particle state.

This physical picture is especially vivid in holographic CFTs: large-spin double-twist operators are two-particle states in global AdS separated by a large impact parameter.

## Relation to large-N CFT

In large-$N$ CFTs, generalized free field appears at leading order in the $1/N$ expansion. Double-trace operators have dimensions

$$
\Delta_{n,\ell}^{(0)}=\Delta_1+\Delta_2+2n+\ell.
$$

Connected correlators at order $1/N^p$ shift these dimensions:

$$
\Delta_{n,\ell}=\Delta_{n,\ell}^{(0)}+rac{1}{N^p}\gamma_{n,\ell}^{(1)}+\cdots .
$$

The lightcone bootstrap explains the large-spin behavior of these shifts. In holographic theories, the same corrections can be computed from AdS exchange or contact diagrams.

Large-$N$ is not required for the lightcone bootstrap theorem. It simply makes the double-twist interpretation more literal and often gives a controlled perturbation series.

In a generic CFT, the double-twist families still exist asymptotically, but they need not be isolated at low spin and need not correspond to simple products of fields.

## Relation to the Lorentzian inversion formula

The lightcone bootstrap originally gave powerful asymptotic results by matching singularities. The Lorentzian inversion formula refines and systematizes this logic.

Instead of extracting large-spin data by hand, the inversion formula reconstructs CFT data from a double discontinuity:

$$
\operatorname{dDisc}\,\mathcal G(z,
\bar z).
$$

The inversion formula implies analyticity in spin under suitable conditions and explains why large-spin families are controlled by crossed-channel singularities.

The lightcone bootstrap is therefore the conceptual doorway. The Lorentzian inversion formula is the sharper machine behind many modern calculations.

A good learning order is:

$$
\text{lightcone crossing argument}
\quad\to\quad
\text{large-spin perturbation theory}
\quad\to\quad
\text{Lorentzian inversion formula}.
$$

## Example: stress-tensor correction

Every local CFT has a stress tensor with

$$
\Delta_T=d,
\qquad
\ell_T=2,
\qquad
\tau_T=d-2.
$$

Stress-tensor exchange therefore gives a universal large-spin correction of order

$$
\gamma_{n,\ell}^{(T)}\sim -\frac{1}{J^{d-2}}
$$

up to a positive coefficient fixed by $\Delta_\phi$, $C_T$, and conventions.

This correction is universal because the stress tensor is universal. Its OPE coefficient with two scalars is fixed by a Ward identity in terms of $\Delta_\phi$ and $C_T$.

Thus lightcone bootstrap connects low-twist protected data to high-spin asymptotic data:

$$
T_{\mu\nu}\text{ exchange}
\quad\Rightarrow\quad
\text{universal attraction of large-spin double-twist states}.
$$

The exact formula belongs on the anomalous-dimensions page, because it depends on conformal block normalization and the chosen definition of $J$.

## Example: conserved current exchange

If $\phi$ is charged under a global symmetry, the conserved current $J_\mu^a$ may appear in crossed channels. It has

$$
\Delta_J=d-1,
\qquad
\ell_J=1,
\qquad
\tau_J=d-2.
$$

Like the stress tensor, it gives large-spin corrections of order

$$
\frac{1}{J^{d-2}}.
$$

The sign and group-theory factors depend on the representation channel. In some channels current exchange is effectively attractive; in others it is repulsive.

This is a useful warning: anomalous dimensions are not just numbers. In theories with global symmetry, each representation sector has its own large-spin data.

## Common pitfalls

**Do not confuse twist with dimension.** The lightcone limit is organized by $\tau=\Delta-\ell$, not by $\Delta$ alone.

**Do not think double-twist means literal product in every CFT.** It means an asymptotic large-spin family with additive twist.

**Do not extrapolate large-spin formulas blindly to spin zero.** Sometimes it works surprisingly well; sometimes it lies with confidence.

**Do not forget operator mixing.** At finite spin or in theories with degeneracies, schematic $[\phi\phi]_{n,\ell}$ labels can mix with other operators.

**Do not ignore global symmetry.** Large-spin families appear in representation sectors, and group theory affects signs and coefficients.

**Do not treat Euclidean and Lorentzian limits as identical.** The lightcone bootstrap relies on analytic continuation and Lorentzian causal structure.

**Do not assume identity exchange is the full answer.** It gives leading mean-field-like data; low-twist non-identity operators produce the physically interesting corrections.

## Relations to other pages

This page starts the [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/) chapter. It prepares [Large-Spin Perturbation Theory](/cft-bootstrap/analytic-bootstrap/large-spin-perturbation-theory/), [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/), [Anomalous Dimensions from Crossing](/cft-bootstrap/analytic-bootstrap/anomalous-dimensions-from-crossing/), and [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/).

It connects backward to [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/) and [Mean-Field Theory CFT](/cft-bootstrap/higher-dimensional-cft/mean-field-theory-cft/), because identity exchange reproduces mean-field large-spin data.

It also connects to [Conformal Collider Bounds](/cft-bootstrap/higher-dimensional-cft/conformal-collider-bounds/) and [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/), because stress-tensor exchange controls universal large-spin corrections.

## Research status

The existence of large-spin double-twist families in unitary CFTs under standard assumptions is established. Lightcone bootstrap is now a basic tool of analytic CFT.

Active work concerns refinements: finite-spin reconstruction, spinning correlators, multiple operators and mixing, nonunitary systems, defects and boundaries, thermal lightcone limits, Lorentzian inversion, Regge behavior, and applications to holographic CFT and quantum gravity constraints.

## Exercises

### Exercise 1

For a symmetric traceless operator with dimension $\Delta$ and spin $\ell$, define the twist and explain why it matters in the lightcone limit.

<details><summary><strong>Solution</strong></summary>

The twist is

$$
\tau=\Delta-\ell.
$$

In a scalar conformal block, the leading small-$z$ behavior in a lightcone OPE limit is controlled by

$$
z^{\tau/2}.
$$

Therefore operators of smaller twist dominate the lightcone expansion, even if their full dimensions are large.

</details>

### Exercise 2

What double-twist dimensions are forced at large spin in the OPE of two identical scalars of dimension $\Delta_\phi$?

<details><summary><strong>Solution</strong></summary>

Crossing forces large-spin families

$$
[\phi\phi]_{n,\ell}
$$

with dimensions approaching

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell+\gamma_{n,\ell},
$$

where

$$
\gamma_{n,\ell}\to0
\qquad
\ell\to\infty.
$$

Equivalently, their twists approach

$$
\tau_{n,\ell}\to2\Delta_\phi+2n.
$$

</details>

### Exercise 3

Why can a finite number of finite-spin operators not reproduce the crossed-channel identity singularity?

<details><summary><strong>Solution</strong></summary>

The crossed-channel identity produces a strong singular behavior as one cross-ratio approaches the crossed OPE limit. A finite number of finite-spin conformal blocks has only a limited set of powers and angular structures. It cannot reproduce the full singular dependence required by crossing. An infinite tower of increasingly large-spin operators is needed, and their summed contribution reproduces the crossed-channel singularity.

</details>

### Exercise 4

What is the physical interpretation of $\gamma_{n,\ell}$ on the cylinder?

<details><summary><strong>Solution</strong></summary>

On the cylinder $\mathbb R\times S^{d-1}$, a double-twist operator behaves like a two-particle state with orbital angular momentum $\ell$. The leading dimension

$$
\Delta_1+\Delta_2+2n+\ell
$$

is the noninteracting energy. The anomalous dimension

$$
\gamma_{n,\ell}
$$

is the interaction energy. At large spin, the two constituents are far apart on the sphere, so the interaction becomes weak and $\gamma_{n,\ell}\to0$.

</details>

### Exercise 5

Why does stress-tensor exchange give corrections of order $1/J^{d-2}$?

<details><summary><strong>Solution</strong></summary>

The stress tensor has dimension

$$
\Delta_T=d
$$

and spin

$$
\ell_T=2.
$$

Therefore its twist is

$$
\tau_T=d-2.
$$

In large-spin lightcone bootstrap, an exchanged operator of twist $\tau_m$ gives leading corrections that scale like

$$
J^{-\tau_m}.
$$

For the stress tensor this becomes

$$
J^{-(d-2)}.
$$

</details>

## References

- A. L. Fitzpatrick, J. Kaplan, D. Poland, and D. Simmons-Duffin, “The analytic bootstrap and AdS superhorizon locality,” *Journal of High Energy Physics* **2013**.
- Z. Komargodski and A. Zhiboedov, “Convexity and liberation at large spin,” *Journal of High Energy Physics* **2013**.
- L. F. Alday, “Large spin perturbation theory for conformal field theories,” *Physical Review Letters* **119** (2017).
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” 2016.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).

## Version history

- 2026-07-01: First polished draft. Added lightcone crossing setup, double-twist theorem, identity and low-twist exchange logic, cylinder interpretation, large-$N$ and inversion-formula connections, examples, pitfalls, exercises, and references.
