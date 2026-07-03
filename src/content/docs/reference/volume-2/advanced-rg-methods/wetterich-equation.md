---
title: "Wetterich Equation"
description: "The effective-average-action flow equation of functional RG, including its regulator setup, derivation, one-loop-exact structure, truncations, and relation to Wilsonian RG."
sidebar:
  label: "Wetterich Equation"
  order: 30
level: Advanced
status: "Polished draft"
source: "Wetterich 1993; Morris; Berges, Tetradis, and Wetterich; Rosten; Zinn-Justin 2021; Wilson and Kogut 1974."
topics:
  - Wetterich equation
  - functional renormalization group
  - effective average action
  - infrared regulator
  - local potential approximation
canonicalTopics:
  - wetterich-equation
  - functional-renormalization-group
  - effective-average-action
researchStatus:
  established:
    - "The Wetterich equation is an exact flow equation for the effective average action and is the standard starting point for many functional RG calculations."
  active:
    - "Its predictive power depends on truncation quality, regulator choice, symmetry preservation, analytic continuation, and error diagnostics, all of which remain active methodological topics."
---

## Summary

The **Wetterich equation** is an exact flow equation for the **effective average action** $\Gamma_k$. It is one of the main forms of the functional renormalization group. Instead of flowing a Wilsonian action by removing high-momentum modes, it flows a scale-dependent 1PI-like action by suppressing low-momentum fluctuations with an infrared regulator $R_k$.

The equation is

$$
\partial_t\Gamma_k[\varphi]
=\frac12\operatorname{Tr}\!\left[
\left(\Gamma_k^{(2)}[\varphi]+R_k\right)^{-1}\partial_tR_k
\right],
\qquad
 t\equiv\log k.
$$

Here $\Gamma_k^{(2)}$ is the second functional derivative of $\Gamma_k$ with respect to the average field $\varphi$. The trace sums over momenta, positions, and any internal indices.

The equation has the shape of a one-loop formula, but it is exact: the propagator inside the trace is the full, field-dependent, scale-dependent inverse Hessian of $\Gamma_k$, not the bare propagator.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 56rem;">

![Wetterich equation workflow: an IR regulator suppresses low modes, the modified Legendre transform defines the effective average action, and the scale derivative localizes the trace near p approximately k.](/figures/renormalization-rg-eft/wetterich-equation-regulator-trace.svg)

<figcaption>

The Wetterich equation flows the effective average action $\Gamma_k$. The regulator $R_k$ suppresses low-momentum fluctuations, while $\partial_tR_k$ localizes the trace near the scale $p\sim k$. As $k\to0$, the regulator is removed and $\Gamma_k$ becomes the ordinary 1PI effective action.

</figcaption>
</figure>

:::note[The slogan]
The Wetterich equation is a scale-by-scale version of the 1PI effective action. At large $k$, fluctuations below $k$ are frozen. As $k$ is lowered, more fluctuations are released. At $k=0$, all fluctuations have been included.
:::

## Prerequisites

You should know [Exact RG Equations](/renormalization-rg-eft/advanced-rg-methods/exact-rg-equations/), [Polchinski Equation](/renormalization-rg-eft/advanced-rg-methods/polchinski-equation/), [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/), and [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/). You should also be comfortable with the ordinary 1PI effective action, Legendre transforms, functional derivatives, and Euclidean path integrals.

This page uses Euclidean notation and bosonic fields for clarity. Fermions, gauge fields, ghosts, and composite operators add signs, indices, constraints, and regulator subtleties, but not a different conceptual core.

## Core idea

The ordinary 1PI effective action $\Gamma[\varphi]$ includes the effect of all quantum fluctuations. That is powerful, but it does not tell us how fluctuations at different scales build up the answer.

The effective average action $\Gamma_k[\varphi]$ interpolates between a microscopic action and the full effective action:

$$
\Gamma_{k\approx\Lambda}\approx S_\Lambda,
\qquad
\Gamma_{k\to0}=\Gamma.
$$

The parameter $k$ is an infrared scale. Modes with momenta $p^2\ll k^2$ are suppressed by a regulator term, while modes with $p^2\gg k^2$ are essentially unaffected. Lowering $k$ gradually includes more infrared fluctuations.

The exact flow equation says:

$$
\text{change how strongly low modes are suppressed}
\quad\Longrightarrow\quad
\text{change }\Gamma_k\text{ by a trace over modes near }k.
$$

This makes the Wetterich equation especially useful near critical points, where the long-distance modes are precisely the dangerous ones.

## Regulator setup

Start with a Euclidean action $S[\phi]$ and add a quadratic infrared regulator

$$
\Delta S_k[\phi]
=\frac12\phi\cdot R_k\cdot\phi.
$$

For a translation-invariant scalar regulator, this means

$$
\Delta S_k[\phi]
=\frac12\int\frac{d^d p}{(2\pi)^d}
\phi(p)R_k(p^2)\phi(-p).
$$

A good regulator satisfies three qualitative conditions:

$$
R_k(p^2)>0\quad p^2\ll k^2,
$$

so low modes acquire an extra mass-like suppression;

$$
R_k(p^2)\to0\quad p^2\gg k^2,
$$

so high modes are not distorted; and

$$
R_k(p^2)\to0\quad k\to0,
$$

so the full effective action is recovered in the infrared.

A common parametrization is

$$
R_k(p^2)=Z_k k^2 r(p^2/k^2),
$$

where $r(y)$ is a dimensionless shape function. Different choices of $r$ are different RG schemes. Exact results are regulator independent; finite truncations are not.

## Definition of the effective average action

Define the regulated generating functional

$$
Z_k[J]
=\int\mathcal D\phi\,
\exp\!\left[-S[\phi]-\Delta S_k[\phi]+J\cdot\phi\right],
$$

and

$$
W_k[J]=\log Z_k[J].
$$

The average field is

$$
\varphi(x)=\frac{\delta W_k[J]}{\delta J(x)}.
$$

The effective average action is a modified Legendre transform:

$$
\Gamma_k[\varphi]
=J\cdot\varphi-W_k[J]-\Delta S_k[\varphi],
$$

where $J$ is eliminated in favor of $\varphi$.

The subtraction of $\Delta S_k[\varphi]$ is essential. Without it, the regulator would remain as a trivial quadratic term in the Legendre transform. With the subtraction, $\Gamma_k$ behaves like a scale-dependent effective action for the modes already integrated in.

The source-field relation becomes

$$
\frac{\delta\Gamma_k}{\delta\varphi}=J-R_k\varphi.
$$

Differentiating once more gives the key inverse relation

$$
W_k^{(2)}=
\left(\Gamma_k^{(2)}+R_k\right)^{-1},
$$

where $W_k^{(2)}$ is the connected two-point function in the regulated theory.

## The Wetterich equation

At fixed average field, the exact flow is

$$
\partial_t\Gamma_k[\varphi]
=\frac12\operatorname{Tr}\!\left[
\left(\Gamma_k^{(2)}[\varphi]+R_k\right)^{-1}\partial_tR_k
\right].
$$

The trace means, for a scalar field,

$$
\operatorname{Tr}A
=\int\frac{d^d p}{(2\pi)^d}A(p,-p),
$$

with additional sums over field components when present.

The equation is often written as

$$
\partial_t\Gamma_k
=\frac12\operatorname{Tr}\left(G_k\partial_tR_k\right),
\qquad
G_k=(\Gamma_k^{(2)}+R_k)^{-1}.
$$

The factor $\partial_tR_k$ localizes the flow to modes whose momenta are near $k$. This is the smooth functional-RG analogue of integrating out a momentum shell.

## Sketch of the derivation

Differentiate $W_k[J]$ with respect to $t=\log k$ at fixed source:

$$
\partial_t W_k[J]
=-\left\langle\partial_t\Delta S_k[\phi]\right\rangle
=-\frac12\left\langle\phi\cdot\partial_tR_k\cdot\phi\right\rangle.
$$

Split the expectation value into connected and disconnected parts:

$$
\langle\phi\phi\rangle
=W_k^{(2)}+\varphi\varphi.
$$

Therefore

$$
\partial_t W_k[J]
=-\frac12\operatorname{Tr}\left(W_k^{(2)}\partial_tR_k\right)
-\frac12\varphi\cdot\partial_tR_k\cdot\varphi.
$$

Now differentiate the modified Legendre transform at fixed $\varphi$:

$$
\Gamma_k[\varphi]=J\cdot\varphi-W_k[J]-\frac12\varphi\cdot R_k\cdot\varphi.
$$

The terms involving $\partial_t J$ cancel because this is a Legendre transform. The remaining terms give

$$
\partial_t\Gamma_k
=\frac12\operatorname{Tr}\left(W_k^{(2)}\partial_tR_k\right).
$$

Finally use

$$
W_k^{(2)}=(\Gamma_k^{(2)}+R_k)^{-1},
$$

and obtain the Wetterich equation.

## Why it looks one-loop but is exact

The equation resembles a one-loop determinant because it contains a trace of an inverse quadratic operator. Indeed, if $\Gamma_k^{(2)}$ is replaced by the second derivative of the bare action, integrating the flow reproduces a one-loop effective action.

The exact equation is stronger. The inverse operator is built from $\Gamma_k^{(2)}$, not from $S^{(2)}$:

$$
G_k=(\Gamma_k^{(2)}+R_k)^{-1}.
$$

This means the propagator in the loop already contains all scale-dependent self-interactions included in $\Gamma_k$. The one-loop shape is exact because the flow differentiates only the quadratic regulator, but the propagator inside the loop is fully dressed.

This is the little trick that makes the equation so useful and so treacherous. Useful, because it packages infinitely many diagrams into one compact trace. Treacherous, because the exactness disappears once $\Gamma_k$ is approximated by a small ansatz.

## Local potential approximation

For a scalar theory, a common first truncation is the **local potential approximation**:

$$
\Gamma_k[\varphi]
=\int d^d x\left[
\frac12(\partial\varphi)^2+U_k(\varphi)
\right].
$$

For a constant field, the Hessian is

$$
\Gamma_k^{(2)}(p,-p;\varphi)
=p^2+U_k''(\varphi).
$$

The Wetterich equation becomes

$$
\partial_t U_k(\varphi)
=\frac12\int\frac{d^d p}{(2\pi)^d}
\frac{\partial_tR_k(p^2)}{p^2+R_k(p^2)+U_k''(\varphi)}.
$$

This single equation already contains the running of all polynomial couplings in the potential. Expanding

$$
U_k(\varphi)=\frac12m_k^2\varphi^2+\frac{\lambda_k}{4!}\varphi^4+\frac{g_{6,k}}{6!}\varphi^6+\cdots
$$

gives flow equations for $m_k^2$, $\lambda_k$, $g_{6,k}$, and so on.

A derivative expansion improves this by allowing

$$
\Gamma_k[\varphi]
=\int d^d x\left[
\frac12 Z_k(\varphi)(\partial\varphi)^2+U_k(\varphi)+O(\partial^4)
\right].
$$

Then the anomalous dimension is extracted from

$$
\eta_k=-\partial_t\log Z_k.
$$

## Dimensionless flow and fixed points

To study fixed points, introduce dimensionless variables. For a scalar field,

$$
\tilde\varphi=k^{(2-d)/2}Z_k^{1/2}\varphi,
\qquad
u_k(\tilde\varphi)=k^{-d}U_k(\varphi).
$$

Then a fixed point is a scale-independent solution of the dimensionless flow equation:

$$
\partial_t\nu_k(\tilde\varphi)=0.
$$

The flow has three ingredients:

$$
\partial_t\nu
=\text{canonical scaling}
+\text{field anomalous scaling}
+\text{threshold contribution from the trace}.
$$

The threshold contribution depends on the regulator shape in finite truncations. Critical exponents are obtained by linearizing around the fixed-point solution and diagonalizing the resulting stability operator.

This is why the Wetterich equation is so popular in critical phenomena: it turns fixed-point physics into a functional differential equation that can be solved numerically after a controlled ansatz is chosen.

## Regulator choices and threshold functions

A widely used example is the optimized or Litim-type regulator,

$$
R_k(p^2)=Z_k(k^2-p^2)\theta(k^2-p^2),
$$

for bosonic scalar modes. It makes many momentum integrals simple because, for $p^2<k^2$,

$$
Z_kp^2+R_k(p^2)=Z_kk^2.
$$

Smooth regulators, exponential regulators, compact-support regulators, and spectrally adjusted regulators are also common. The exact flow is regulator independent in the sense that different choices describe the same physics. Truncated flows are not. A serious functional-RG calculation should check stability under regulator variation or use optimization criteria with caution.

Regulator choices also interact with symmetries. A regulator that breaks a symmetry may require modified Ward identities or symmetry-restoring conditions. In gauge theories, this is not a minor technicality; it is often the central difficulty.

## Relation to the Polchinski equation

The Polchinski equation and the Wetterich equation organize RG flow in different functionals.

The Polchinski equation uses a Wilsonian action $S_\Lambda$ and asks how the action changes as the cutoff is lowered. The Wetterich equation uses an effective average action $\Gamma_k$ and asks how the 1PI effective action is built as infrared modes are released.

The relation is roughly:

$$
S_\Lambda
\quad\text{is a Wilsonian action for remaining modes},
$$

while

$$
\Gamma_k
\quad\text{is a scale-dependent 1PI action for average fields}.
$$

Under suitable regulator choices and convexity assumptions, the two formulations can be related by modified Legendre transforms. In practice, they lead to different approximations. Polchinski's equation is natural for Wilsonian locality and perturbative renormalizability. The Wetterich equation is natural for effective potentials, critical exponents, nonperturbative truncations, and systems with strong infrared fluctuations.

## Gauge theories and fermions

For fermions, the trace becomes a supertrace. Bosonic and fermionic fields contribute with opposite signs:

$$
\partial_t\Gamma_k
=\frac12\operatorname{STr}\!\left[
(\Gamma_k^{(2)}+R_k)^{-1}\partial_tR_k
\right].
$$

The supertrace includes a minus sign for Grassmann fields.

Gauge theories require more care. A regulator $R_k$ generally breaks ordinary gauge invariance because it separates modes by momentum relative to a background structure. Common strategies include:

- background-field methods, preserving background gauge invariance;
- modified Ward or Slavnov–Taylor identities;
- gauge-invariant truncation ansatzes;
- flow equations for gauge-invariant observables;
- careful treatment of ghosts and gauge fixing.

The equation remains a powerful tool, but gauge symmetry is a constraint, not a decorative afterthought.

## Common pitfalls

**One-loop form does not mean one-loop approximation.** The trace has a one-loop shape, but it contains the full $\Gamma_k^{(2)}$.

**Exact flow does not mean exact truncation.** The equation is exact before you choose an ansatz. Local potential approximation, derivative expansion, and vertex truncations are approximations.

**The regulator is not physical.** Universal results should not depend on $R_k$. Residual regulator dependence is a truncation artifact.

**The scale $k$ is not automatically a physical momentum.** It is an RG coarse-graining scale. Choosing $k$ near a physical scale often improves perturbative logarithms, but $k$ itself is not an observable.

**Convexity matters in the infrared.** The full effective potential is convex under standard assumptions. Intermediate $U_k$ need not be. Apparent nonconvex structures at finite $k$ require careful interpretation.

**Analytic continuation is hard.** The Euclidean Wetterich equation is not automatically a real-time spectral function machine. Real-time and finite-density applications need dedicated methods.

## Relations to other pages

This page specializes the overview in [Exact RG Equations](/renormalization-rg-eft/advanced-rg-methods/exact-rg-equations/). For the Wilsonian counterpart, read [Polchinski Equation](/renormalization-rg-eft/advanced-rg-methods/polchinski-equation/). For background-field gauge applications, read [Background Field Method](/renormalization-rg-eft/gauge-theories-and-rg/background-field-method/). For fixed-point interpretation, use [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/) and [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/). For practical nonperturbative projections, continue to [Nonperturbative RG Preview](/renormalization-rg-eft/advanced-rg-methods/nonperturbative-rg-preview/).

## Research status

The Wetterich equation is an established exact functional identity and a standard formulation of functional RG. It is widely used in critical phenomena, scalar theories, low-energy QCD models, gravity-inspired truncations, finite-temperature systems, and nonequilibrium-adjacent developments.

The active frontier is not the formal equation itself but the reliability of truncations: derivative expansions, vertex expansions, regulator optimization, symmetry-preserving schemes, gauge theories, fermionic systems, real-time observables, finite-density problems, and numerical uncertainty estimates.

## Exercises

### Exercise 1: Derive the inverse relation

Starting from

$$
\Gamma_k[\varphi]=J\cdot\varphi-W_k[J]-\frac12\varphi\cdot R_k\cdot\varphi,
$$

show that

$$
W_k^{(2)}=(\Gamma_k^{(2)}+R_k)^{-1}.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate the modified Legendre transform with respect to $\varphi$:

$$
\frac{\delta\Gamma_k}{\delta\varphi}=J-R_k\varphi.
$$

Differentiate again:

$$
\frac{\delta J}{\delta\varphi}=\Gamma_k^{(2)}+R_k.
$$

But by definition

$$
\varphi=\frac{\delta W_k}{\delta J},
$$

so

$$
\frac{\delta\varphi}{\delta J}=W_k^{(2)}.
$$

The matrices $\delta J/\delta\varphi$ and $\delta\varphi/\delta J$ are inverses. Therefore

$$
W_k^{(2)}=(\Gamma_k^{(2)}+R_k)^{-1}.
$$

</details>

### Exercise 2: Recover the one-loop effective action

Assume $\Gamma_k^{(2)}$ on the right-hand side can be approximated by $S^{(2)}$, independent of $k$. Show that integrating the Wetterich equation gives a one-loop determinant.

<details><summary><strong>Solution</strong></summary>

With $\Gamma_k^{(2)}\approx S^{(2)}$, the flow is

$$
\partial_t\Gamma_k
\approx
\frac12\operatorname{Tr}\left[(S^{(2)}+R_k)^{-1}\partial_tR_k\right].
$$

Since $S^{(2)}$ is treated as $k$ independent,

$$
\partial_t\operatorname{Tr}\log(S^{(2)}+R_k)
=\operatorname{Tr}\left[(S^{(2)}+R_k)^{-1}\partial_tR_k\right].
$$

Therefore

$$
\partial_t\Gamma_k
\approx
\frac12\partial_t\operatorname{Tr}\log(S^{(2)}+R_k).
$$

Integrating over $t$ gives

$$
\Gamma\approx S+\frac12\operatorname{Tr}\log S^{(2)}
$$

up to regulator-dependent endpoint and normalization terms. This is the ordinary one-loop effective action.

</details>

### Exercise 3: Local potential flow for a constant field

Use the ansatz

$$
\Gamma_k[\varphi]
=\int d^d x\left[\frac12(\partial\varphi)^2+U_k(\varphi)\right]
$$

and a constant background field to derive

$$
\partial_t U_k(\varphi)
=\frac12\int\frac{d^d p}{(2\pi)^d}
\frac{\partial_tR_k(p^2)}{p^2+R_k(p^2)+U_k''(\varphi)}.
$$

<details><summary><strong>Solution</strong></summary>

For a constant background field, the second functional derivative of the ansatz is diagonal in momentum:

$$
\Gamma_k^{(2)}(p,-p;\varphi)=p^2+U_k''(\varphi).
$$

Insert this into the Wetterich equation:

$$
\partial_t\Gamma_k
=\frac12\int\frac{d^d p}{(2\pi)^d}
\frac{\partial_tR_k(p^2)}{p^2+R_k(p^2)+U_k''(\varphi)}.
$$

For a constant field, the left-hand side is

$$
\partial_t\Gamma_k=\int d^d x\,\partial_tU_k(\varphi).
$$

Dividing by the spacetime volume gives the stated flow equation for $U_k$.

</details>

## References

- C. Wetterich, "Exact Evolution Equation for the Effective Potential," *Physics Letters B* **301** (1993) 90–94.
- T. R. Morris, reviews and lectures on derivative expansions and exact renormalization group methods.
- J. Berges, N. Tetradis, and C. Wetterich, "Non-Perturbative Renormalization Flow in Quantum Field Theory and Statistical Physics."
- O. J. Rosten, "Fundamentals of the Exact Renormalization Group."
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for functional methods and critical applications.
- K. G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.

## Version history

- 2026-06-19: First polished draft. Added regulator setup, derivation, local-potential approximation, regulator caveats, relation to Polchinski flow, and exercises.
