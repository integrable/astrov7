---
title: "Yukawa Theory at One Loop"
description: "A worked model calculation for one-loop renormalization in pseudoscalar Yukawa theory, including field counterterms, the Yukawa beta function, and the coupled scalar quartic beta function."
sidebar:
  label: "Yukawa Theory at One Loop"
  order: 4
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§51–52; Coleman 2019, renormalization lectures; Schwartz 2014, chs. 18–23; Weinberg 1995, Vol. I, ch. 12."
topics:
  - Yukawa theory
  - one-loop renormalization
  - beta functions
  - scalar quartic coupling
  - fermion loops
  - anomalous dimensions
canonicalTopics:
  - yukawa-theory
  - yukawa-beta-function
  - one-loop-renormalization
researchStatus:
  established:
    - "The one-loop renormalization of simple Yukawa theory is a standard calculation illustrating fermion loops, vertex renormalization, and coupled beta functions."
  active:
    - "Yukawa systems remain important in Higgs physics, critical Gross–Neveu–Yukawa models, asymptotic-safety studies, and EFT matching, where field content and symmetry determine the detailed beta functions."
---

## Summary

Yukawa theory is the simplest laboratory where scalar and fermion renormalization interact. The model contains a real scalar $\phi$, a Dirac fermion $\psi$, and a Yukawa interaction. To avoid scalar tadpoles and cubic scalar counterterms, it is convenient to use a parity-invariant pseudoscalar version,

$$
\mathcal L
=
\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
+\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12M^2\phi^2
+i g\,\phi\,\bar\psi\gamma^5\psi
-\frac{\lambda}{4!}\phi^4
+\mathcal L_{\text{ct}}.
$$

The factor of $i$ is conventional for a Hermitian pseudoscalar coupling. The one-loop beta functions in four dimensions are

$$
\boxed{
\beta_g=\frac{5g^3}{16\pi^2}+O(g^5,g^3\lambda)
}
$$

and

$$
\boxed{
\beta_\lambda
=
\frac{1}{16\pi^2}
\left(
3\lambda^2+8\lambda g^2-48g^4
\right)
+\cdots .
}
$$

The $3\lambda^2$ term is the scalar fish-diagram contribution familiar from $\phi^4$ theory. The $8\lambda g^2$ term comes from scalar wavefunction renormalization and mixed scalar–fermion renormalization. The $-48g^4$ term comes from the fermion box diagram and is the first sign that fermions can destabilize a scalar potential unless additional physics or couplings intervene.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 55rem;">

![One-loop renormalization map for Yukawa theory: scalar and fermion self-energies, Yukawa vertex correction, and fermion box feed into Z factors and beta functions.](/figures/renormalization-rg-eft/yukawa-one-loop-renormalization-map.svg)

<figcaption>

The one-loop Yukawa calculation has four bookkeeping channels: scalar self-energy, fermion self-energy, Yukawa vertex correction, and the four-scalar vertex. Together they determine $Z_\phi$, $Z_\psi$, $Z_g$, $Z_\lambda$, and the coupled beta functions for $g$ and $\lambda$.

</figcaption>
</figure>

:::note[Why this model is chosen]
A scalar Yukawa interaction $g\phi\bar\psi\psi$ is perfectly legitimate, but it allows parity-even operators $\phi$ and $\phi^3$ unless an extra symmetry forbids them. The pseudoscalar choice makes the one-loop lesson cleaner: the required renormalizable interactions are the kinetic terms, masses, Yukawa coupling, and $\phi^4$ coupling.
:::

## Prerequisites

You should know [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/), [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), and [Phi-Four Beta Function](/renormalization-rg-eft/model-calculation-library/phi-four-beta-function/).

We use the mostly-minus metric and $p\!\!\!/\equiv\gamma^\mu p_\mu$. For the beta-function derivation it is simplest to use

$$
d=4-\varepsilon.
$$

Thus the Yukawa coupling has engineering dimension $\varepsilon/2$, while the quartic scalar coupling has engineering dimension $\varepsilon$.

## The model and counterterms

The renormalized Lagrangian is

$$
\mathcal L_{\text{ren}}
=
\bar\psi(i\gamma^\mu\partial_\mu-m)\psi
+\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12M^2\phi^2
+i g\,\phi\,\bar\psi\gamma^5\psi
-\frac{\lambda}{4!}\phi^4.
$$

The counterterm Lagrangian has the form

$$
\begin{aligned}
\mathcal L_{\text{ct}}
={}&
(Z_\psi-1)\bar\psi i\gamma^\mu\partial_\mu\psi
-(Z_m-1)m\bar\psi\psi  \\
&+\frac12(Z_\phi-1)\partial_\mu\phi\,\partial^\mu\phi
-\frac12(Z_M-1)M^2\phi^2  \\
&+i(Z_g-1)g\,\phi\bar\psi\gamma^5\psi
-\frac{(Z_\lambda-1)\lambda}{4!}\phi^4 .
\end{aligned}
$$

In dimensional regularization, the bare and renormalized couplings are related by

$$
g_0=\mu^{\varepsilon/2} Z_\phi^{-1/2}Z_\psi^{-1}Z_g\,g,
$$

and

$$
\lambda_0=\mu^\varepsilon Z_\phi^{-2}Z_\lambda\,\lambda.
$$

These relations are more important than the individual $Z$ factors. The beta functions follow from the pole parts of the combinations that multiply $g$ and $\lambda$.

## The one-loop diagrams

At one loop, four kinds of diagrams appear.

| Diagram type | What it renormalizes | Physical role |
|---|---|---|
| Fermion loop with two scalar legs | scalar two-point function | contributes to $Z_\phi$ and $M^2$ renormalization |
| Scalar–fermion loop with two fermion legs | fermion two-point function | contributes to $Z_\psi$ and $m$ renormalization |
| Triangle correction to $\phi\bar\psi\psi$ | Yukawa vertex | contributes to $Z_g$ |
| Fermion box with four scalar legs | scalar quartic vertex | contributes to $Z_\lambda$ and to the $-g^4$ term in $\beta_\lambda$ |

The closed fermion loop carries an extra minus sign. This is not a decorative convention; it is the algebraic consequence of anticommuting fermion fields in the path integral or Wick expansion.

The pole parts may be organized as

$$
\ln\!\left(Z_\phi^{-1/2}Z_\psi^{-1}Z_g\right)
=
\frac{1}{\varepsilon}
\left[
\frac{5g^2}{16\pi^2}
\right]
+\cdots ,
$$

and

$$
\ln\!\left(Z_\phi^{-2}Z_\lambda\right)
=
\frac{1}{\varepsilon}
\left[
\frac{3\lambda}{16\pi^2}
+\frac{g^2}{2\pi^2}
-\frac{3g^4}{\pi^2\lambda}
\right]
+\cdots .
$$

The ellipses denote higher-order pole contributions. These two formulas are the compact summary of the one-loop calculation.

:::tip[Do not overinterpret individual Z factors]
The split among $Z_\phi$, $Z_\psi$, $Z_g$, and $Z_\lambda$ depends on field normalizations and scheme conventions. The combinations entering $g_0$ and $\lambda_0$ are what determine the beta functions.
:::

## Yukawa beta function

Let

$$
G_1(g,\lambda)=\frac{5g^2}{16\pi^2}
$$

be the coefficient of the simple pole in

$$
\ln\!\left(Z_\phi^{-1/2}Z_\psi^{-1}Z_g\right).
$$

The bare coupling is

$$
g_0
=
\mu^{\varepsilon/2}g\,
\exp\left[\frac{G_1(g,\lambda)}{\varepsilon}+\cdots\right].
$$

Since $g_0$ is independent of $\mu$,

$$
0=\mu\frac{d}{d\mu}\log g_0.
$$

Write

$$
\mu\frac{dg}{d\mu}
=
-\frac{\varepsilon}{2}g+\beta_g(g,\lambda),
$$

and

$$
\mu\frac{d\lambda}{d\mu}
=
-\varepsilon\lambda+\beta_\lambda(g,\lambda).
$$

Keeping the finite part as $\varepsilon\to0$ gives

$$
\beta_g
=
g\left(
\frac12 g\frac{\partial}{\partial g}
+\lambda\frac{\partial}{\partial\lambda}
\right)G_1.
$$

Because $G_1$ depends only on $g^2$ at this order,

$$
\beta_g
=
g\left(\frac12 g\frac{\partial}{\partial g}\right)
\frac{5g^2}{16\pi^2}
=
\frac{5g^3}{16\pi^2}.
$$

Thus, in $d=4-\varepsilon$,

$$
\mu\frac{dg}{d\mu}
=
-\frac{\varepsilon}{2}g+\frac{5g^3}{16\pi^2}+\cdots ,
$$

and in four dimensions,

$$
\boxed{
\beta_g=\frac{5g^3}{16\pi^2}+\cdots .
}
$$

The positive sign means that the simple Yukawa coupling grows toward the ultraviolet in perturbation theory.

## Quartic beta function

Now define

$$
L_1(g,\lambda)
=
\frac{3\lambda}{16\pi^2}
+\frac{g^2}{2\pi^2}
-\frac{3g^4}{\pi^2\lambda},
$$

the simple-pole coefficient in

$$
\ln\!\left(Z_\phi^{-2}Z_\lambda\right).
$$

The same fixed-bare-coupling argument gives

$$
\beta_\lambda
=
\lambda\left(
\frac12 g\frac{\partial}{\partial g}
+\lambda\frac{\partial}{\partial\lambda}
\right)L_1.
$$

Apply the differential operator term by term:

$$
\lambda\left(\lambda\frac{\partial}{\partial\lambda}\right)
\frac{3\lambda}{16\pi^2}
=
\frac{3\lambda^2}{16\pi^2},
$$

$$
\lambda\left(\frac12 g\frac{\partial}{\partial g}\right)
\frac{g^2}{2\pi^2}
=
\frac{\lambda g^2}{2\pi^2},
$$

and

$$
\lambda\left(
\frac12 g\frac{\partial}{\partial g}
+\lambda\frac{\partial}{\partial\lambda}
\right)
\left(-\frac{3g^4}{\pi^2\lambda}\right)
=
-\frac{3g^4}{\pi^2}.
$$

Putting the terms over a common denominator,

$$
\boxed{
\beta_\lambda
=
\frac{1}{16\pi^2}
\left(
3\lambda^2+8\lambda g^2-48g^4
\right)
+\cdots .
}
$$

In $d=4-\varepsilon$, include the engineering term:

$$
\mu\frac{d\lambda}{d\mu}
=
-\varepsilon\lambda
+
\frac{1}{16\pi^2}
\left(
3\lambda^2+8\lambda g^2-48g^4
\right)
+\cdots .
$$

## Anatomy of the quartic beta function

Each term in $\beta_\lambda$ has a distinct origin.

The scalar-loop term

$$
\frac{3\lambda^2}{16\pi^2}
$$

is the same one-loop fish contribution that appears in real $\phi^4$ theory.

The mixed term

$$
\frac{8\lambda g^2}{16\pi^2}
$$

comes from the fact that the quartic vertex is made from four scalar fields, and the scalar field itself is renormalized by a fermion loop. Depending on conventions, this contribution may be distributed between explicit vertex and wavefunction renormalization, but the beta-function coefficient is fixed.

The fermion-box term

$$
-\frac{48g^4}{16\pi^2}
$$

comes from a closed fermion loop with four external scalar legs. Its negative sign is the most important qualitative feature. Fermions tend to drive scalar quartic couplings downward. In realistic theories, gauge interactions, additional scalars, thresholds, and higher-order terms decide whether this tendency leads to instability, metastability, or a stable trajectory.

## Flow of the ratio lambda over g squared

Because $g$ runs, it is often useful to study the ratio

$$
\rho\equiv\frac{\lambda}{g^2}.
$$

Using the four-dimensional one-loop equations,

$$
\frac{d\rho}{d\log\mu}
=
\frac{g^2}{16\pi^2}
\left(
3\rho^2-2\rho-48
\right)
+\cdots .
$$

The fixed ratios solve

$$
3\rho^2-2\rho-48=0,
$$

so

$$
\rho_\pm=\frac{1\pm\sqrt{145}}{3}.
$$

Numerically,

$$
\rho_+\approx4.35,
\qquad
\rho_-\approx-3.68.
$$

The positive fixed ratio is the physically relevant one for a stable tree-level scalar potential. This ratio analysis is often more transparent than drawing trajectories in the $(g,\lambda)$ plane, because $g$ grows monotonically toward the ultraviolet at one loop while $\rho$ captures the relative scalar-versus-Yukawa balance.

## Mass terms and threshold sensitivity

The masses also renormalize. Their precise beta functions depend on the mass definitions and subtraction scheme, but the qualitative lessons are robust.

The fermion mass is protected by chiral symmetry in the limit $m\to0$. If the theory has a symmetry that forbids $m\bar\psi\psi$, then radiative corrections to the fermion mass are proportional to the symmetry-breaking parameter.

The scalar mass is not similarly protected by the pseudoscalar Yukawa coupling alone. Fermion loops contribute to the scalar two-point function. In a mass-independent MS scheme, running masses receive logarithmic beta functions. In a cutoff or threshold-matching language, heavy fermions can give additive finite contributions to scalar masses. This is the same structural reason scalar naturalness is delicate in Higgs-like theories.

Thus the Yukawa model is not merely a calculation exercise. It is a small version of the logic behind Higgs-sector renormalization, vacuum stability, and naturalness.

## The scalar versus pseudoscalar choice

The beta functions above were written for a pseudoscalar interaction

$$
i g\phi\bar\psi\gamma^5\psi.
$$

For many one-loop UV questions, a scalar Yukawa interaction

$$
g\phi\bar\psi\psi
$$

has closely related logarithmic structure. However, unless an extra symmetry such as $\phi\to-\phi$ is imposed, scalar Yukawa theory permits additional local operators:

$$
\phi,\qquad \phi^3.
$$

Renormalization then forces one to include tadpole and cubic counterterms. That is not conceptually hard, but it obscures the clean lesson of this page. The pseudoscalar version keeps parity as a simple selection rule and lets us focus on the Yukawa and quartic couplings.

## Common pitfalls

**Forgetting the quartic coupling.** Yukawa theory with a scalar field is not closed under renormalization unless the scalar self-interactions allowed by symmetry are included. The $\phi^4$ term is required even if one sets it to zero at tree level.

**Dropping wavefunction renormalization.** Vertex diagrams alone do not give the beta function. The bare coupling contains $Z_\phi^{-1/2}Z_\psi^{-1}Z_g$.

**Missing the closed-fermion-loop sign.** The negative $-48g^4$ contribution to $\beta_\lambda$ is tied to the fermion loop. Lose that sign and the qualitative physics changes.

**Comparing scalar and pseudoscalar models without symmetry bookkeeping.** A scalar Yukawa interaction generally allows tadpoles and cubic terms. The pseudoscalar model avoids them by parity.

**Treating $\lambda=0$ as stable under RG.** Even if $\lambda$ is set to zero at one scale, the fermion box generates quartic running through the $-48g^4$ term.

**Confusing a beta function with vacuum stability.** The sign of $\beta_\lambda$ is not by itself the stability criterion. Stability depends on the effective potential, the scale range, thresholds, higher-order corrections, and the field values being probed.

## Relations to other pages

This page follows [Phi-Four One-Loop Renormalization](/renormalization-rg-eft/model-calculation-library/phi-four-one-loop-renormalization/) and [Phi-Four Beta Function](/renormalization-rg-eft/model-calculation-library/phi-four-beta-function/) by adding fermions. It illustrates [Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), and [Radiative Stability](/renormalization-rg-eft/naturalness-power-counting/radiative-stability/).

It also prepares for [Standard Model Effective Field Theory](/renormalization-rg-eft/major-efts/standard-model-effective-field-theory/), [Mass and Coupling Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/mass-and-coupling-renormalization/), and later gauge-theory pages where Yukawa couplings mix with gauge and scalar interactions.

## Research status

The one-loop beta functions of simple Yukawa theory are established textbook results. The same structures remain active in modern contexts: top-Yukawa effects in Higgs vacuum stability, Gross–Neveu–Yukawa critical points, asymptotically safe gauge–Yukawa systems, and EFT threshold matching all use the same logic with richer field content and symmetry.

The main lesson is durable: once scalars and fermions interact, renormalization is coupled. One cannot understand scalar self-interactions, fermion masses, or vacuum stability by looking at only one vertex.

## Exercises

### Exercise 1: Derive the Yukawa beta function from G one

Let

$$
G_1(g,\lambda)=\frac{5g^2}{16\pi^2}.
$$

Use

$$
\beta_g
=
g\left(
\frac12 g\frac{\partial}{\partial g}
+\lambda\frac{\partial}{\partial\lambda}
\right)G_1
$$

to derive the one-loop beta function for $g$.

<details><summary><strong>Solution</strong></summary>

Since $G_1$ has no $\lambda$ dependence at this order,

$$
\beta_g
=
g\left(
\frac12 g\frac{\partial}{\partial g}
\right)
\frac{5g^2}{16\pi^2}.
$$

The derivative is

$$
\frac{\partial}{\partial g}g^2=2g.
$$

Therefore

$$
\beta_g
=
g\left(\frac12 g\right)
\frac{10g}{16\pi^2}
=
\frac{5g^3}{16\pi^2}.
$$

</details>

### Exercise 2: Derive the quartic beta function from L one

Let

$$
L_1(g,\lambda)
=
\frac{3\lambda}{16\pi^2}
+\frac{g^2}{2\pi^2}
-\frac{3g^4}{\pi^2\lambda}.
$$

Show that

$$
\beta_\lambda
=
\lambda\left(
\frac12 g\frac{\partial}{\partial g}
+\lambda\frac{\partial}{\partial\lambda}
\right)L_1
=
\frac{1}{16\pi^2}(3\lambda^2+8\lambda g^2-48g^4).
$$

<details><summary><strong>Solution</strong></summary>

Apply the operator

$$
D=\frac12 g\frac{\partial}{\partial g}
+\lambda\frac{\partial}{\partial\lambda}.
$$

For the first term,

$$
D\left(\frac{3\lambda}{16\pi^2}\right)
=
\frac{3\lambda}{16\pi^2}.
$$

For the second term,

$$
D\left(\frac{g^2}{2\pi^2}\right)
=
\frac{g^2}{2\pi^2}.
$$

For the third term,

$$
D\left(-\frac{3g^4}{\pi^2\lambda}\right)
=
-\frac{3g^4}{\pi^2\lambda},
$$

because the $g^4$ part contributes a factor $2$ and the $1/\lambda$ part contributes a factor $-1$. Multiplying by $\lambda$ gives

$$
\beta_\lambda
=
\frac{3\lambda^2}{16\pi^2}
+\frac{\lambda g^2}{2\pi^2}
-\frac{3g^4}{\pi^2}.
$$

Putting terms over $16\pi^2$ gives

$$
\beta_\lambda
=
\frac{1}{16\pi^2}
(3\lambda^2+8\lambda g^2-48g^4).
$$

</details>

### Exercise 3: Fixed ratios

Using

$$
\frac{d\rho}{d\log\mu}
=
\frac{g^2}{16\pi^2}
(3\rho^2-2\rho-48),
\qquad
\rho=\frac{\lambda}{g^2},
$$

find the fixed ratios $\rho_\pm$.

<details><summary><strong>Solution</strong></summary>

Set the polynomial to zero:

$$
3\rho^2-2\rho-48=0.
$$

The quadratic formula gives

$$
\rho
=
\frac{2\pm\sqrt{4+576}}{6}
=
\frac{2\pm\sqrt{580}}{6}
=
\frac{1\pm\sqrt{145}}{3}.
$$

Thus

$$
\rho_+=\frac{1+\sqrt{145}}{3}\approx4.35,
\qquad
\rho_-=\frac{1-\sqrt{145}}{3}\approx-3.68.
$$

Only the positive fixed ratio corresponds to a positive tree-level quartic coupling.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, sections 51–52, for one-loop corrections and beta functions in pseudoscalar Yukawa theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, for renormalized perturbation theory, counterterms, and RG equations.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, for the pedagogical counterterm logic behind fermion and scalar loop calculations.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, for general renormalization structure and scheme-aware perturbation theory.

## Version history

- 2026-06-19: First polished draft. Added pseudoscalar Yukawa setup, pole-combination method, one-loop beta functions, ratio flow, exercises, and figure.
