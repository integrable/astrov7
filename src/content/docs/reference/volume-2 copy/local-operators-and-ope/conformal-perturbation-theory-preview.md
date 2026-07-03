---
title: "Conformal Perturbation Theory Preview"
description: "A preview of how a fixed-point CFT is deformed by local operators, how integrated OPE singularities generate beta functions, and why this organizes nearby RG flows."
sidebar:
  label: "Conformal Perturbation Theory Preview"
  order: 7
level: Advanced
status: "Polished draft"
source: "Wilson and Kogut 1974; Coleman 1985, Dilatations; Zinn-Justin 2021; Cardy, scaling and RG; Rychkov, CFT lectures."
topics:
  - conformal perturbation theory
  - deformations of fixed points
  - operator product expansion
  - beta functions
  - relevant and marginal operators
canonicalTopics:
  - conformal-perturbation-theory
  - deformed-cft
  - integrated-ope
researchStatus:
  established:
    - "Perturbing a fixed point by local operators and using the fixed-point OPE to organize nearby RG flows is a standard method in QFT, statistical field theory, and CFT."
  active:
    - "Nonperturbative convergence, resonances, degenerate operator mixing, Lorentzian questions, defects, boundaries, and applications to strongly coupled CFTs remain active research topics."
---

## Summary

**Conformal perturbation theory** studies a QFT obtained by deforming a fixed-point CFT by local operators:

$$
S=S_*+\delta S,
\qquad
\delta S=
\sum_i \lambda^i \mu^{d-\Delta_i}
\int d^d x\,\mathcal O_i(x).
$$

Here $S_*$ is the fixed-point action, $\mathcal O_i$ are scaling operators of dimension $\Delta_i$, $\lambda^i$ are dimensionless couplings, and $\mu$ is the renormalization scale. The method computes deformed correlation functions by expanding in $\lambda^i$ and evaluating integrated CFT correlators.

The central point is that divergences in these integrated correlators come from short-distance collisions of the perturbing operators. Those collisions are controlled by the fixed-point OPE,

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ij}{}^k(x)\mathcal O_k(0),
$$

so the fixed-point CFT data determine the leading RG flow away from the fixed point.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![A fixed-point CFT is deformed by integrated local operators; OPE collisions generate counterterms and beta functions.](/figures/renormalization-rg-eft/conformal-perturbation-flow.svg)

<figcaption>

Conformal perturbation theory starts with fixed-point data, perturbs by integrated local operators, and uses short-distance OPE collisions to determine counterterms and beta functions. The calculation is perturbative in the distance from the fixed point, not necessarily in a microscopic Lagrangian coupling.

</figcaption>
</figure>

:::note[Why this is only a preview]
This page uses conformal language as a local tool inside the Renormalization, RG, and EFT volume. The full theory of conformal symmetry, conformal blocks, and bootstrap constraints belongs in the CFT and Bootstrap volume.
:::

## Prerequisites

You should know [Scale Invariance](/renormalization-rg-eft/fixed-points-critical-phenomena/scale-invariance/), [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [OPE and Short-Distance Expansion](/renormalization-rg-eft/local-operators-and-ope/ope-and-short-distance-expansion/), and [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/).

The page assumes Euclidean notation when discussing integrated correlators. Lorentzian continuation adds causal and ordering subtleties that are not the point here.

## Core idea

Near a fixed point, a QFT can be described by turning on local operators of the fixed-point theory. Instead of starting from a microscopic Lagrangian and discovering the fixed point later, conformal perturbation theory starts at the fixed point and asks what happens when one moves away from it.

The fixed point supplies three kinds of input:

| Fixed-point datum | Role in the perturbation |
|---|---|
| scaling dimensions $\Delta_i$ | determine the linearized relevance of couplings |
| OPE coefficients $C_{ij}{}^k$ | determine short-distance collisions of perturbations |
| correlation functions | determine perturbative corrections to observables |

This changes the mental picture of perturbation theory. The expansion parameter is not necessarily a small coupling in a free Lagrangian. It is a small coordinate displacement away from a fixed point in theory space.

The slogan is

$$
\text{nearby QFT}
=
\text{fixed-point CFT}
+
\text{integrated local perturbations}.
$$

This is especially powerful when the fixed point is interacting, because one can use CFT data rather than elementary Feynman rules as the starting point.

## Setup and conventions

Let $S_*$ be a Euclidean CFT in $d$ dimensions. Choose a basis of scalar scaling operators $\mathcal O_i$ with dimensions $\Delta_i$. We perturb by

$$
S=S_*+
\sum_i \lambda^i \mu^{d-\Delta_i}
\int d^d x\,\mathcal O_i(x).
$$

The sign convention here is important: the perturbation is added to the Euclidean action. If another page writes $S=S_* - \int g\,\mathcal O$, the sign of some formulas below changes. The linear term in the beta function is unaffected by this bookkeeping once the coupling definition is translated.

The dimensionless couplings $\lambda^i$ have UV-time beta functions

$$
\beta^i(\lambda)
\equiv
\mu\frac{d\lambda^i}{d\mu}.
$$

At leading order, dimensional analysis gives

$$
\beta^i=(\Delta_i-d)\lambda^i+O(\lambda^2).
$$

Thus a relevant operator with $\Delta_i<d$ has negative beta function in UV time. As $\mu$ is lowered toward the IR, its dimensionless coupling grows.

We mostly discuss scalar deformations. Spinful deformations, current deformations, stress-tensor deformations, defect deformations, and boundary deformations obey the same philosophy but require more indices and more careful symmetry constraints.

## Deformed correlators as integrated CFT correlators

Let $X$ denote a product of spectator operators. In the deformed theory,

$$
\langle X\rangle_\lambda
=
\frac{\left\langle X\exp(-\delta S)\right\rangle_*}{\left\langle \exp(-\delta S)\right\rangle_*}.
$$

Expanding to first order gives

$$
\langle X\rangle_\lambda
=
\langle X\rangle_*
-
\sum_i \lambda^i\mu^{d-\Delta_i}
\int d^d x\,
\langle \mathcal O_i(x)X\rangle_*
+O(\lambda^2),
$$

where disconnected vacuum terms are removed by the denominator. At second order,

$$
\Delta^{(2)}\langle X\rangle
=
\frac12
\lambda^i\lambda^j
\mu^{2d-\Delta_i-\Delta_j}
\int d^d x\,d^d y\,
\langle \mathcal O_i(x)\mathcal O_j(y)X\rangle_{*,\text{conn}}
+
\cdots.
$$

This formula is simple and dangerous. The integrals may diverge when a perturbing operator approaches another perturbing operator, when a perturbing operator approaches a spectator insertion, or when the integration region goes to infinity. The first two are UV singularities controlled by the OPE. The last is an IR issue. Conformal perturbation theory is cleanest when IR divergences are regulated by finite volume, by working with local short-distance counterterms, or by using a deformation whose IR behavior is under control.

## First-order correction to a two-point function

Consider a scalar operator $A$ in a CFT deformed by a single scalar operator $\mathcal O$. The first-order correction to the two-point function is

$$
\Delta\langle A(x)A(0)\rangle
=
-
\lambda \mu^{d-\Delta}
\int d^d y\,
\langle \mathcal O(y)A(x)A(0)\rangle_*.
$$

Conformal symmetry fixes the scalar three-point function up to a coefficient:

$$
\langle \mathcal O(y)A(x)A(0)\rangle_*
=
\frac{C_{OAA}}
{|y-x|^{\Delta}\,|y|^{\Delta}\,|x|^{2\Delta_A-\Delta}}.
$$

The integral over $y$ can diverge near $y=0$ or $y=x$. Those are precisely the regions where the perturbing operator collides with $A$. The relevant OPE is

$$
\mathcal O(y)A(0)
\sim
\sum_B C_{OA}{}^B(y)B(0).
$$

If the OPE contains $A$ itself, the perturbation changes the normalization and scaling behavior of the $A$ two-point function. This is how anomalous dimensions and operator mixing appear in conformal perturbation theory.

## OPE collisions and counterterms

The essential UV event in conformal perturbation theory is a collision of integrated perturbing operators. At second order,

$$
\frac12\lambda^i\lambda^j
\mu^{2d-\Delta_i-\Delta_j}
\int d^d x\,d^d y\,
\mathcal O_i(x)\mathcal O_j(y)
$$

contains the short-distance region $x\to y$. Let $r=x-y$. The OPE gives

$$
\mathcal O_i(y+r)\mathcal O_j(y)
\sim
\sum_k
\frac{C_{ij}{}^k}{|r|^{\Delta_i+\Delta_j-\Delta_k}}
\mathcal O_k(y)
+
\cdots.
$$

The radial integral over $r$ contains

$$
\int_a dr\,r^{d-1}
\frac{1}{r^{\Delta_i+\Delta_j-\Delta_k}}
=
\int_a dr\,r^{d-1-\Delta_i-\Delta_j+\Delta_k},
$$

where $a$ is a short-distance cutoff. This integral has a logarithmic divergence when

$$
\Delta_i+\Delta_j-\Delta_k=d.
$$

Logarithmic divergences require counterterms proportional to

$$
\int d^d y\,\mathcal O_k(y),
$$

which means the coupling $\lambda^k$ runs.

This is the operator version of the Wilsonian statement that short-distance physics generates all local terms allowed by symmetry. Here the short-distance physics is not a loop diagram. It is an OPE singularity integrated over coincident insertion points.

## Beta functions from CFT data

With the convention

$$
S=S_*+
\sum_i\lambda^i\mu^{d-\Delta_i}\int d^d x\,\mathcal O_i(x),
$$

the schematic beta function near the fixed point is

$$
\beta^k
=(\Delta_k-d)\lambda^k
+
\frac12 S_{d-1}C_{ij}{}^k\lambda^i\lambda^j
+
O(\lambda^3),
$$

when the OPE normalization and operator basis are chosen so that

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\frac{C_{ij}{}^k}{|x|^{\Delta_i+\Delta_j-\Delta_k}}
\mathcal O_k(0).
$$

Here

$$
S_{d-1}=\frac{2\pi^{d/2}}{\Gamma(d/2)}
$$

is the area of the unit $(d-1)$-sphere. The factor $1/2$ reflects the second-order expansion of $e^{-\delta S}$; when $i$ and $j$ are treated as ordered labels, the same information may be distributed differently. The formula is schematic because finite counterterms, resonances, degeneracies, descendants, total derivatives, and scheme choices can modify the coordinate expression for the beta functions.

The invariant statement is cleaner:

$$
\text{OPE singularities of perturbing operators determine the local RG flow near the fixed point.}
$$

This is why fixed-point data are dynamical data. They do not merely classify the CFT at one point. They tell nearby theories how to flow.

## Relevant, marginal, and irrelevant deformations

The first-order term

$$
\beta^i=(\Delta_i-d)\lambda^i+\cdots
$$

classifies perturbations near the fixed point.

| Deformation | Condition | Meaning near the fixed point |
|---|---:|---|
| relevant | $\Delta_i<d$ | grows toward the IR and usually drives the theory away from the fixed point |
| marginal | $\Delta_i=d$ | decided by higher-order terms in $\beta^i$ |
| irrelevant | $\Delta_i>d$ | shrinks toward the IR but affects short-distance corrections |

For a marginal deformation, the quadratic OPE term is often decisive. If

$$
\beta^\lambda=b\lambda^2+O(\lambda^3),
$$

then $b$ helps decide whether the deformation is marginally relevant, marginally irrelevant, or possibly exactly marginal after higher-order and symmetry constraints are considered.

An exactly marginal deformation satisfies

$$
\beta^i(\lambda)=0
$$

along a finite-dimensional family of theories. Such a family is called a conformal manifold. Establishing exact marginality is much stronger than finding a classically marginal operator. One must show that all quantum obstructions vanish.

## Operator mixing under a deformation

Perturbing a CFT also changes the scaling behavior of operators. Suppose $A_a$ is a set of operators with the same fixed-point quantum numbers. Under the deformation, they can mix:

$$
A_a^{\text{bare}}=Z_a{}^b(\lambda,\mu,a)A_{b,R}.
$$

The anomalous-dimension matrix near the fixed point can be extracted from integrated correlators of the perturbing operator with $A_a$. Schematically,

$$
\gamma_a{}^b(\lambda)
=\lambda^i \gamma_{i,a}{}^b+O(\lambda^2),
$$

where the first coefficient is controlled by the OPE

$$
\mathcal O_i(x)A_a(0)
\sim
\frac{C_{ia}{}^b}{|x|^d}A_b(0)+\cdots
$$

in the logarithmic case. If several operators are degenerate in dimension and quantum numbers, conformal perturbation theory requires diagonalizing the mixing matrix, not simply perturbing each operator separately.

This is the same logic as degenerate perturbation theory in quantum mechanics. The unperturbed CFT basis may not be the basis of scaling operators after the deformation.

## Example: mass deformation as a relevant perturbation

A free massless scalar in $d$ dimensions has the Gaussian fixed-point action

$$
S_*=
\frac12\int d^d x\,\partial_\mu\phi\partial^\mu\phi.
$$

The operator $\phi^2$ has engineering dimension

$$
\Delta_{\phi^2}=d-2
$$

at the Gaussian fixed point. The deformation

$$
\delta S=\frac12 m^2\int d^d x\,\phi^2
$$

is relevant because

$$
\Delta_{\phi^2}<d.
$$

The dimensionless coupling is

$$
\lambda_m(\mu)=\frac{m^2}{\mu^2},
$$

and the linear beta function is

$$
\mu\frac{d\lambda_m}{d\mu}=-2\lambda_m.
$$

As $\mu$ is lowered toward the IR, $\lambda_m$ grows. Physically, the mass becomes important at distances of order $m^{-1}$, and the flow leaves the massless fixed point.

This example is simple but conceptually useful: a relevant perturbation is not small at all scales. It is small near the UV fixed point but becomes large when the RG flow reaches the scale generated by the perturbation.

## Example: nearly marginal deformations

Suppose an operator has dimension

$$
\Delta=d-\epsilon,
\qquad 0<\epsilon\ll1.
$$

Then the beta function may take the form

$$
\beta_\lambda=-\epsilon\lambda+A\lambda^2+O(\lambda^3).
$$

If $A>0$, there is a perturbative fixed point at

$$
\lambda_*=
\frac{\epsilon}{A}+O(\epsilon^2).
$$

This is the fixed-point logic behind many epsilon-expansion calculations: a classically or nearly marginal deformation becomes interacting at a small coupling proportional to the parameter controlling its near-marginality.

The important lesson is not the specific coefficient. The lesson is the mechanism:

$$
\text{linear relevance}+
\text{OPE self-interaction}
\longrightarrow
\text{nearby interacting fixed point}.
$$

## Relation to Wilsonian RG

Conformal perturbation theory and Wilsonian RG describe the same local physics from different sides.

In Wilsonian language, lowering the cutoff integrates out short-distance modes and generates local operators. In conformal perturbation theory, integrated operator insertions collide at short distances and generate local counterterms. The dictionary is:

| Wilsonian language | Conformal perturbation language |
|---|---|
| cutoff shell | short-distance region of integrated insertions |
| generated local term | OPE channel $\mathcal O_i\mathcal O_j\to\mathcal O_k$ |
| beta function | counterterm required by logarithmic OPE collision |
| relevant direction | operator with $\Delta<d$ |
| fixed point | undeformed CFT or new zero of beta functions |

The CFT formulation has the advantage that the input data are intrinsic: scaling dimensions and OPE coefficients. The Wilsonian formulation has the advantage that it keeps the coarse-graining picture physically vivid.

## Common pitfalls

**Calling every fixed-point perturbation conformal perturbation theory.** The phrase usually means a controlled expansion around a CFT using integrated local operators. A generic relevant deformation may quickly become strongly coupled in the IR, even if the UV expansion is clean.

**Ignoring IR divergences.** The UV singularities are controlled by the OPE. Infinite-volume IR divergences are a separate issue and often require finite volume, a mass scale, or a carefully chosen observable.

**Treating marginal as exactly marginal.** Marginal at first order means $\Delta=d$. Exactly marginal means the beta function vanishes after all quantum corrections and mixing effects are included.

**Forgetting operator mixing.** A deformation can mix all operators with compatible quantum numbers. Degenerate sectors must be diagonalized.

**Comparing beta-function coefficients without comparing conventions.** The coefficient involving $C_{ij}{}^k$ depends on the normalization of operators, the sign convention in the Euclidean action, and the definition of dimensionless couplings.

**Assuming the OPE coefficient alone is the whole story.** Descendants, contact terms, total derivatives, redundant operators, and scheme choices matter when turning OPE data into precise beta functions.

## Relations to other pages

This page sits between fixed-point RG and the OPE. [Scale Invariance](/renormalization-rg-eft/fixed-points-critical-phenomena/scale-invariance/) explains the fixed-point starting point. [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/) explains the first-order classification of perturbations. [OPE and Short-Distance Expansion](/renormalization-rg-eft/local-operators-and-ope/ope-and-short-distance-expansion/) explains the local expansion used when integrated operators collide. [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/) explains how operator mixing becomes matrix RG.

The next conceptual issue is redundancy: not every local deformation is a physically distinct deformation. Field redefinitions, total derivatives, and equations-of-motion operators can move within the same physical theory.

## Research status

Conformal perturbation theory is a standard tool in two-dimensional CFT, statistical field theory, epsilon expansions, conformal manifolds, and deformations of strongly coupled theories. Its local UV structure is well understood: fixed-point OPE data determine the singularities of integrated perturbations.

Active directions include conformal perturbation theory with boundaries and defects, nonperturbative convergence questions, Lorentzian versions, resonant mixing, marginal deformations, supersymmetric constraints, numerical-bootstrap input for deformed theories, and applications to RG flows without weakly coupled Lagrangians.

## Exercises

### Exercise 1: Linear beta function

Let

$$
S=S_*+
\lambda\mu^{d-\Delta}\int d^d x\,\mathcal O(x).
$$

Assume the dimensionful coefficient multiplying $\int\mathcal O$ is fixed. Derive

$$
\beta_\lambda=(\Delta-d)\lambda
$$

at zeroth order in interactions among perturbations.

<details><summary><strong>Solution</strong></summary>

Let $g$ be the dimensionful coupling, so

$$
g=\lambda(\mu)\mu^{d-\Delta}.
$$

Holding $g$ fixed gives

$$
0=\mu\frac{dg}{d\mu}
=
\mu^{d-\Delta}
\left(
\mu\frac{d\lambda}{d\mu}+(d-\Delta)\lambda
\right).
$$

Therefore

$$
\mu\frac{d\lambda}{d\mu}=(\Delta-d)\lambda.
$$

For a relevant operator, $\Delta<d$, the coupling decreases toward the UV and grows toward the IR.

</details>

### Exercise 2: When does an OPE collision give a logarithm?

Suppose

$$
\mathcal O_i(x)\mathcal O_j(0)
\supset
\frac{C_{ij}{}^k}{|x|^{\Delta_i+\Delta_j-\Delta_k}}
\mathcal O_k(0).
$$

Show that integrating over the relative separation $x$ produces a logarithmic short-distance divergence precisely when

$$
\Delta_i+\Delta_j-\Delta_k=d.
$$

<details><summary><strong>Solution</strong></summary>

The short-distance radial integral is proportional to

$$
\int_a dr\,r^{d-1}
\frac{1}{r^{\Delta_i+\Delta_j-\Delta_k}}
=
\int_a dr\,r^{d-1-\Delta_i-\Delta_j+\Delta_k}.
$$

A logarithm appears when the exponent of $r$ is $-1$:

$$
d-1-\Delta_i-\Delta_j+\Delta_k=-1.
$$

This is equivalent to

$$
\Delta_i+\Delta_j-\Delta_k=d.
$$

The resulting logarithm requires a local counterterm proportional to $\int d^d x\,\mathcal O_k(x)$.

</details>

### Exercise 3: A perturbative fixed point from a nearly marginal operator

Assume one coupling has beta function

$$
\beta_\lambda=-\epsilon\lambda+A\lambda^2+O(\lambda^3),
\qquad
0<\epsilon\ll1.
$$

Find the nonzero fixed point to first order in $\epsilon$ and determine the linearized eigenvalue there.

<details><summary><strong>Solution</strong></summary>

A fixed point satisfies

$$
0=-\epsilon\lambda_*+A\lambda_*^2+O(\lambda_*^3).
$$

Besides $\lambda_*=0$, the perturbative fixed point is

$$
\lambda_*=
\frac{\epsilon}{A}+O(\epsilon^2).
$$

The linearized eigenvalue in UV time is

$$
\left.\frac{d\beta}{d\lambda}\right|_{\lambda_*}
=-\epsilon+2A\lambda_*+O(\epsilon^2)
=
\epsilon+O(\epsilon^2).
$$

With UV time $t=\log\mu$, a positive eigenvalue means deviations grow toward the UV and shrink toward the IR.

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations" and the discussion of scaling, anomalous dimensions, Callan–Symanzik equations, and the OPE.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on RG, composite operators, and critical phenomena.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for a compact treatment of scaling, perturbations, and RG around fixed points.
- Slava Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, for CFT data and deformation-adjacent background.
- Paul Ginsparg, *Applied Conformal Field Theory*, for two-dimensional CFT conventions and perturbative deformations.

## Version history

- 2026-06-17: First polished draft. Introduced conformal perturbation theory as a preview page, with fixed-point deformations, integrated correlators, OPE collisions, beta functions, and pitfalls.
