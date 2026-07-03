---
title: "Callan–Symanzik Equation"
description: "Derives the Callan–Symanzik equation for renormalized correlation functions from fixed bare quantities and explains beta functions, anomalous dimensions, scaling, and contact-term caveats."
sidebar:
  label: "Callan–Symanzik Equation"
  order: 1
level: Graduate
status: "Polished draft"
source: "Coleman, Dilatations; Srednicki §§27–29; Schwartz ch. 23; Weinberg Vol. II ch. 18; Zinn-Justin, RG and composite-operator chapters."
topics:
  - Callan–Symanzik equation
  - renormalization group equations
  - anomalous dimensions
  - beta functions
  - scaling
  - renormalized correlation functions
canonicalTopics:
  - callan-symanzik-equation
  - renormalization-group-equation
  - anomalous-dimension
  - scaling-equation
researchStatus:
  established:
    - "The Callan–Symanzik equation is the standard renormalization group equation expressing the independence of bare correlation functions from the arbitrary renormalization scale."
  active:
    - "Extensions involving gauge fixing, composite operators, curved spacetime, finite temperature, nonequilibrium contours, conformal manifolds, and nonperturbative definitions require additional structure and careful conventions."
---

## Summary

The **Callan–Symanzik equation** is the renormalization group equation for renormalized correlation functions. It says that the arbitrary scale $\mu$ introduced by renormalization cannot affect the bare definition of the theory. When bare quantities are held fixed, a change in $\mu$ must be compensated by changes in renormalized couplings, masses, fields, and operators.

For a massless theory with one scalar field and one dimensionless coupling, the separated-point equation is

$$
\left[
\mu\frac{\partial}{\partial\mu}
+\beta(g)\frac{\partial}{\partial g}
+n\gamma_\phi(g)
\right]
G_R^{(n)}(x_1,\ldots,x_n;g,\mu)=0.
$$

Here

$$
G_R^{(n)}(x_1,\ldots,x_n)
=\langle \phi(x_1)\cdots\phi(x_n)\rangle_R,
$$

and this volume uses

$$
\beta(g)=\left.\mu\frac{dg}{d\mu}\right|_{\text{bare}},
\qquad
\gamma_\phi(g)=\frac12\left.\mu\frac{d\log Z_\phi}{d\mu}\right|_{\text{bare}}.
$$

The slogan is

$$
\text{explicit }\mu\text{ dependence}
+\text{running parameters}
+\text{field rescaling}
=0.
$$

The equation is not merely a device for removing divergences. It is the bridge from renormalized perturbation theory to scale dependence, anomalous scaling, fixed points, large-log resummation, and effective field theory running.

:::note[What is held fixed?]
The derivative that defines the Callan–Symanzik equation is taken at fixed bare parameters and fixed regulator definition. This is not the same as differentiating a measured observable while changing the physical energy of an experiment.
:::

## Prerequisites

You should know [Conventions and Notation](/renormalization-rg-eft/conventions/), especially the sign convention for $\beta_g$, and [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/). It is also helpful to have read [Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/), [Mass and Coupling Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/mass-and-coupling-renormalization/), and [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/).

The page uses scalar notation for clarity. The same logic applies to spinors, gauge fields, composite operators, operator bases, and EFT Wilson coefficients, with matrix-valued anomalous dimensions and additional indices.

## Core idea

A renormalized Green function depends on $\mu$ in two ways.

First, it can depend **explicitly** on $\mu$ through logarithms such as

$$
\log\frac{p^2}{\mu^2},
\qquad
\log\frac{m^2}{\mu^2},
\qquad
\log(\mu^2 x^2).
$$

Second, it depends **implicitly** on $\mu$ through the renormalized parameters used to describe the same bare theory:

$$
g=g(\mu),
\qquad
m=m(\mu),
\qquad
Z_\phi=Z_\phi(\mu).
$$

The bare theory does not know which subtraction scale we chose. Therefore the total derivative of a bare correlation function with respect to $\mu$ must vanish. The Callan–Symanzik equation is just this statement written in renormalized variables.

This is why the equation is so powerful. A logarithm found in a one-loop calculation determines how a coupling must run. A field-strength counterterm determines an anomalous dimension. At a fixed point, the same equation turns into a scaling law for correlation functions.

## Setup and conventions

For one scalar field, write

$$
\phi_0=Z_\phi^{1/2}\phi,
$$

where $\phi_0$ is the bare regulated field and $\phi$ is the renormalized field. At separated points, the bare and renormalized $n$-point functions are related by

$$
G_0^{(n)}(x_1,\ldots,x_n;g_0,\Lambda)
=Z_\phi^{n/2}
G_R^{(n)}(x_1,\ldots,x_n;g,\mu),
$$

where $\Lambda$ denotes whatever regulator data are being used. In dimensional regularization one may replace the cutoff notation by the regulator parameter $\epsilon$ and the bare coupling relation, for example

$$
g_0=\mu^{\kappa\epsilon}Z_g(g,\epsilon)g.
$$

The number $\kappa$ depends on the engineering dimension of the coupling in $d=4-2\epsilon$. For $\lambda\phi^4/4!$ in four dimensions, $\kappa=2$ if one writes $\lambda_0=\mu^{2\epsilon}Z_\lambda\lambda$.

For several couplings $g^i$, define

$$
\beta^i(g)=\left.\mu\frac{dg^i}{d\mu}\right|_{\text{bare}}.
$$

For mass parameters, the least ambiguous notation is

$$
\beta_{m_a}(g,m)=\left.\mu\frac{dm_a}{d\mu}\right|_{\text{bare}},
$$

or, for a squared scalar mass,

$$
\beta_{m^2}(g,m^2)=\left.\mu\frac{d m^2}{d\mu}\right|_{\text{bare}}.
$$

Some books define a mass anomalous dimension with an extra minus sign. When signs matter, this volume displays the mass term explicitly rather than hiding it inside a symbol.

## Derivation for separated-point Green functions

Start from

$$
G_0^{(n)}=Z_\phi^{n/2}G_R^{(n)}.
$$

The bare Green function does not depend on the arbitrary subtraction scale $\mu$ when bare quantities are held fixed:

$$
0=
\left.\mu\frac{d}{d\mu}G_0^{(n)}\right|_{\text{bare}}.
$$

Using the chain rule gives

$$
0=
\left.\mu\frac{d}{d\mu}
\left(Z_\phi^{n/2}G_R^{(n)}\right)\right|_{\text{bare}}.
$$

The derivative of $Z_\phi^{n/2}$ is

$$
\left.\mu\frac{d}{d\mu}Z_\phi^{n/2}\right|_{\text{bare}}
=n\gamma_\phi Z_\phi^{n/2}.
$$

The derivative of $G_R^{(n)}$ has three pieces: explicit $\mu$ dependence, coupling dependence, and mass dependence. Therefore

$$
\left[
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+\beta_{m_a}\frac{\partial}{\partial m_a}
+n\gamma_\phi
\right]
G_R^{(n)}=0,
$$

again away from coincident-point contact terms. For a single squared scalar mass, write instead

$$
\left[
\mu\frac{\partial}{\partial\mu}
+\beta(g)\frac{\partial}{\partial g}
+\beta_{m^2}(g,m^2)\frac{\partial}{\partial m^2}
+n\gamma_\phi(g)
\right]
G_R^{(n)}=0.
$$

In the massless limit, the mass term drops out and we recover the compact form displayed in the summary.

:::tip[The equation is a chain rule with physics inside]
The formal derivation is short because the hard work is hidden in the existence of local counterterms and finite renormalized Green functions. The content is not the chain rule alone; it is the fact that the chain rule closes on a finite set of local parameters and field normalizations.
:::

## Momentum-space form

For momentum-space connected Green functions, use

$$
G_R^{(n)}(p_1,\ldots,p_n)
=\int \prod_{a=1}^n d^d x_a\,
e^{i\sum_a p_a\cdot x_a}
G_R^{(n)}(x_1,\ldots,x_n),
$$

with the overall momentum-conservation delta function treated according to the page's convention. The RG equation at fixed external momenta is formally the same:

$$
\left[
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+\beta_{m_a}\frac{\partial}{\partial m_a}
+n\gamma_\phi
\right]
G_R^{(n)}(p_1,\ldots,p_n)=0.
$$

When the momentum-conservation delta function has been stripped off, the same equation applies to the reduced function, provided one keeps the convention for the stripped object fixed.

For one-particle-irreducible vertex functions, the field-renormalization sign is reversed. If

$$
\Gamma_R^{(n)}=Z_\phi^{n/2}\Gamma_0^{(n)},
$$

then the corresponding equation is

$$
\left[
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+\beta_{m_a}\frac{\partial}{\partial m_a}
-n\gamma_\phi
\right]
\Gamma_R^{(n)}=0.
$$

This sign difference is one of the most common places where readers accidentally mix connected Green functions and 1PI vertices.

## Relation to scaling

The Callan–Symanzik equation by itself tracks dependence on the arbitrary scale $\mu$. To get a physical scaling law, combine it with dimensional analysis.

For a massless scalar theory at a fixed point $g_*$, where

$$
\beta^i(g_*)=0,
$$

the equation becomes

$$
\left[
\mu\frac{\partial}{\partial\mu}
+n\gamma_\phi^*
\right]G_R^{(n)}=0.
$$

Dimensional analysis says that under $x_a\to \lambda x_a$, a separated-point scalar correlator has the engineering factor $\lambda^{-n\Delta_\phi^{\text{eng}}}$, but the dimensionless argument $\mu x$ also changes. Using the fixed-point Callan–Symanzik equation gives

$$
G_R^{(n)}(\lambda x_1,\ldots,\lambda x_n;g_*,\mu)
=\lambda^{-n(\Delta_\phi^{\text{eng}}+\gamma_\phi^*)}
G_R^{(n)}(x_1,\ldots,x_n;g_*,\mu),
$$

again away from contact terms and assuming no operator mixing. Thus the scaling dimension of the field is

$$
\Delta_\phi=\Delta_\phi^{\text{eng}}+\gamma_\phi^*.
$$

This is one reason anomalous dimensions matter. They are not optional finite renormalizations. At a fixed point, they become part of the observable scaling data of the theory.

## A simple large-log example

Suppose a renormalized two-point or four-point function contains a perturbative term of the form

$$
F(Q,g,\mu)=F_0(g)+g^2 A\log\frac{Q^2}{\mu^2}+O(g^3),
$$

where $Q$ is a physical momentum scale. The logarithm is not itself a disaster. But if $Q\gg \mu$ or $Q\ll \mu$, the logarithm can become large enough to ruin fixed-order perturbation theory.

The Callan–Symanzik equation explains what to do. The explicit logarithm must be accompanied by implicit running of $g(\mu)$ so that the physical answer is independent of the arbitrary scale $\mu$. Choosing $\mu\sim Q$ moves the large logarithm into the running coupling, where the RG equation can resum the leading logarithmic terms.

This logic underlies the practical rule

$$
\text{choose }\mu\text{ near the characteristic physical scale, then run parameters between scales.}
$$

The rule is useful, but it should not be misunderstood: $\mu$ is a convention, not the energy of nature's stopwatch.

## Composite-operator insertions

The previous equations apply to Green functions built from elementary renormalized fields. Local composite operators require their own renormalization. If

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R},
$$

then define

$$
\gamma_a{}^b=(Z^{-1})_a{}^c
\left.\mu\frac{dZ_c{}^b}{d\mu}\right|_{\text{bare}}.
$$

For a correlator with one operator insertion,

$$
G_{a,R}^{(n;1)}(x_1,\ldots,x_n;y)
=\langle \phi(x_1)\cdots\phi(x_n)\mathcal O_{a,R}(y)\rangle,
$$

the separated-point Callan–Symanzik equation becomes schematically

$$
\left[
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+n\gamma_\phi
\right]
G_{a,R}^{(n;1)}
+\gamma_a{}^b G_{b,R}^{(n;1)}=0,
$$

with mass terms added when present. For multiple insertions, one gets one anomalous-dimension matrix acting on each insertion, plus possible contact terms when insertion points collide.

This is the starting point for operator mixing, EFT anomalous-dimension matrices, and the operator product expansion.

## The inhomogeneous version

The word "Callan–Symanzik equation" is used in two closely related ways.

In the cleanest separated-point massless form, the equation is homogeneous:

$$
\left(\mu\partial_\mu+\beta\partial_g+n\gamma_\phi\right)G_R^{(n)}=0.
$$

In theories with relevant mass parameters, composite insertions, identity-operator mixing, vacuum-energy terms, or coincident points, the equation can acquire inhomogeneous local terms. Schematically,

$$
\left(\mu\partial_\mu+\beta^i\partial_{g^i}+n\gamma_\phi\right)G_R^{(n)}
=\text{local contact terms}.
$$

These terms do not contradict the RG idea. They say that products of fields at coincident points have local ambiguities. For separated noncoincident insertions, the contact terms vanish.

## Callan–Symanzik versus a scale Ward identity

In a classically scale-invariant theory, there is a current associated with dilatations. Quantum renormalization can spoil the naive conservation law. In flat spacetime, the trace of the stress tensor contains terms of the form

$$
T^\mu{}_{\mu}
=\beta^i\mathcal O_i+\text{mass terms}+\text{total derivatives}+\text{anomalies}.
$$

This local trace relation is closely related to the Callan–Symanzik equation. Insertions of $T^\mu{}_{\mu}$ generate scale transformations of correlation functions, while the beta functions describe the failure of classical scale invariance at the quantum level.

At a fixed point, $\beta^i=0$, and the trace may vanish up to improvement terms and anomalies depending on dimension, background, and operator choices. This is the bridge from RG to conformal field theory, but the full CFT analysis belongs elsewhere.

## Common pitfalls

**Forgetting what is held fixed.** The Callan–Symanzik equation differentiates at fixed bare parameters. Differentiating at fixed renormalized coupling gives only explicit $\mu$ dependence and misses the point.

**Confusing connected correlators and 1PI vertices.** The field-anomalous-dimension term has opposite sign for ordinary Green functions and 1PI vertex functions. Check whether the object has external propagators or is an amputated 1PI vertex.

**Thinking $\mu$ is the physical energy.** The scale $\mu$ is arbitrary. Choosing $\mu\sim Q$ is a calculational strategy, not a definition of $Q$.

**Ignoring masses.** Relevant parameters bring additional terms such as $\beta_{m^2}\partial_{m^2}$. Dropping them is legitimate only in a massless limit or in a regime where the mass dependence has been specified.

**Using fixed-point formulas away from a fixed point.** The statement $\Delta=\Delta_{\text{eng}}+\gamma^*$ is a fixed-point statement. Away from a fixed point, $\gamma(g(\mu))$ is a running quantity, not a single scaling dimension.

**Suppressing contact terms too early.** Contact terms vanish at separated points, but they matter for Ward identities, composite operators, stress tensors, curved backgrounds, and local RG equations.

## Relations to other pages

[Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/) explains the vector field $\beta^i(g)$ that appears in the Callan–Symanzik equation. [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/) develops $\gamma_\phi$ and operator anomalous dimensions in more detail. [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/) solves the coupling-flow equation and explains scale choices in perturbation theory.

[Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/) provides the correlator objects to which the equation applies. [Composite Operator Renormalization Preview](/renormalization-rg-eft/regularization-counterterms/composite-operator-renormalization-preview/) explains why operator insertions require matrix renormalization. [Local Operators and OPE](/renormalization-rg-eft/local-operators-and-ope/) later turns these matrix equations into the language of operator mixing and short-distance expansions.

[Wilsonian Renormalization](/renormalization-rg-eft/wilsonian-renormalization/) gives the complementary cutoff-based viewpoint. The Callan–Symanzik equation describes how renormalized coordinates change with $\mu$ at fixed bare theory; Wilsonian RG describes how an effective action changes when degrees of freedom are integrated out.

## Research status

The basic Callan–Symanzik equation for renormalized perturbation theory is settled. It is a standard consequence of local renormalizability and fixed bare quantities.

Active work concerns difficult versions of the same idea: high-loop anomalous dimensions, operator mixing in large EFT bases, gauge-invariant and gauge-dependent RG equations, local RG and Weyl consistency conditions, RG in curved spacetime, conformal manifolds, nonequilibrium and finite-temperature correlators, and nonperturbative definitions of scale dependence.

## Exercises

### Exercise 1: Derive the sign of the field term

Assume

$$
G_0^{(n)}=Z_\phi^{n/2}G_R^{(n)},
\qquad
\gamma_\phi=\frac12\left.\mu\frac{d\log Z_\phi}{d\mu}\right|_{\text{bare}}.
$$

Derive the sign of the $n\gamma_\phi$ term in the Callan–Symanzik equation for $G_R^{(n)}$.

<details><summary><strong>Solution</strong></summary>

Differentiate the bare relation at fixed bare parameters:

$$
0=\left.\mu\frac{d}{d\mu}G_0^{(n)}\right|_{\text{bare}}
=\left.\mu\frac{d}{d\mu}\left(Z_\phi^{n/2}G_R^{(n)}\right)\right|_{\text{bare}}.
$$

The derivative of the prefactor is

$$
\left.\mu\frac{d}{d\mu}Z_\phi^{n/2}\right|_{\text{bare}}
=n\gamma_\phi Z_\phi^{n/2}.
$$

The derivative of $G_R^{(n)}$ gives

$$
\left(\mu\partial_\mu+\beta^i\partial_{g^i}+\cdots\right)G_R^{(n)}.
$$

After dividing by $Z_\phi^{n/2}$,

$$
\left(\mu\partial_\mu+\beta^i\partial_{g^i}+\cdots+n\gamma_\phi\right)G_R^{(n)}=0.
$$

Thus the sign is plus for ordinary renormalized Green functions with this convention.

</details>

### Exercise 2: Why 1PI vertices have the opposite sign

Let $\Gamma_R^{(n)}=Z_\phi^{n/2}\Gamma_0^{(n)}$. Show that the Callan–Symanzik equation for $\Gamma_R^{(n)}$ contains $-n\gamma_\phi$.

<details><summary><strong>Solution</strong></summary>

Rewrite the relation as

$$
\Gamma_0^{(n)}=Z_\phi^{-n/2}\Gamma_R^{(n)}.
$$

Differentiate at fixed bare quantities:

$$
0=\left.\mu\frac{d}{d\mu}\left(Z_\phi^{-n/2}\Gamma_R^{(n)}\right)\right|_{\text{bare}}.
$$

Since

$$
\left.\mu\frac{d}{d\mu}Z_\phi^{-n/2}\right|_{\text{bare}}
=-n\gamma_\phi Z_\phi^{-n/2},
$$

we get

$$
\left(\mu\partial_\mu+\beta^i\partial_{g^i}+\cdots-n\gamma_\phi\right)\Gamma_R^{(n)}=0.
$$

</details>

### Exercise 3: Scaling at a fixed point

For a massless scalar theory at a fixed point $g_*$, show that the Callan–Symanzik equation and dimensional analysis imply

$$
G_R^{(n)}(\lambda x_1,\ldots,\lambda x_n)
=\lambda^{-n(\Delta_\phi^{\text{eng}}+\gamma_\phi^*)}
G_R^{(n)}(x_1,\ldots,x_n)
$$

for separated points.

<details><summary><strong>Solution</strong></summary>

At the fixed point, $\beta^i(g_*)=0$, so

$$
\left(\mu\partial_\mu+n\gamma_\phi^*\right)G_R^{(n)}=0.
$$

Therefore changing $\mu\to \lambda\mu$ gives

$$
G_R^{(n)}(x_i;\lambda\mu)=\lambda^{-n\gamma_\phi^*}G_R^{(n)}(x_i;\mu).
$$

Dimensional analysis gives

$$
G_R^{(n)}(\lambda x_i;\mu)
=\lambda^{-n\Delta_\phi^{\text{eng}}}G_R^{(n)}(x_i;\lambda\mu).
$$

Combining the two equations yields

$$
G_R^{(n)}(\lambda x_i;\mu)
=\lambda^{-n(\Delta_\phi^{\text{eng}}+\gamma_\phi^*)}G_R^{(n)}(x_i;\mu).
$$

</details>

## References

- Sidney Coleman, "Dilatations" in *Aspects of Symmetry*, for the relation between scale transformations, anomalous dimensions, and Callan–Symanzik equations.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on renormalization schemes, the renormalization group, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the renormalization group chapter and the derivation of RG equations from counterterms.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for sliding scales, RG equations, asymptotic behavior, mass effects, and minimal subtraction.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for renormalization of correlation functions, composite operators, RG equations, and critical scaling.
- Curtis G. Callan Jr., "Broken Scale Invariance in Scalar Field Theory," *Physical Review D* **2** (1970) 1541–1547.
- Kurt Symanzik, "Small Distance Behaviour in Field Theory and Power Counting," *Communications in Mathematical Physics* **18** (1970) 227–246.

## Version history

- 2026-06-17: First polished draft. Derived the separated-point Callan–Symanzik equation, fixed sign conventions for Green functions and 1PI vertices, added mass and composite-operator terms, and connected the equation to scaling and large logarithms.
