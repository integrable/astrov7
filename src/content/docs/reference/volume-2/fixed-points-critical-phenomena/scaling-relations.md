---
title: "Scaling Relations"
description: "Derives the standard relations among critical exponents from the homogeneity of the singular free energy and explains when those relations can fail."
sidebar:
  label: "Scaling Relations"
  order: 5
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Coleman 1985, Dilatations; Weinberg 1996, ch. 18; Zinn-Justin 2021; Cardy 1996; Goldenfeld 1992."
topics:
  - scaling relations
  - hyperscaling
  - Rushbrooke relation
  - Widom relation
  - Fisher relation
  - critical exponents
canonicalTopics:
  - scaling-relations
  - hyperscaling
  - critical-exponent-identities
  - dangerous-irrelevant-variables
researchStatus:
  established:
    - "The standard scaling relations follow from the homogeneity of the singular free energy and the scaling form of correlation functions, with well-known caveats for hyperscaling and dangerous irrelevant variables."
  active:
    - "Modern applications refine these relations in systems with long-range forces, quenched disorder, anisotropic scaling, gauge constraints, multicriticality, nonequilibrium dynamics, and dangerously irrelevant operators."
---

## Summary

**Scaling relations** are algebraic relations among critical exponents. They are not numerical coincidences. They express the assumption that near a continuous phase transition the singular physics is controlled by a fixed point with a small number of relevant scaling fields.

For the standard Ising-like exponents, the most commonly used relations are

$$
\alpha+2\beta_{\mathrm{mag}}+\gamma=2,
$$

$$
\gamma=\beta_{\mathrm{mag}}(\delta-1),
$$

$$
\gamma=\nu(2-\eta),
$$

and, when ordinary hyperscaling applies,

$$
2-\alpha=d\nu.
$$

The first is often called the Rushbrooke relation, the second the Widom relation, the third the Fisher relation, and the fourth the Josephson hyperscaling relation. The names are useful historically, but the real point is simpler:

$$
\text{a fixed-point scaling law leaves fewer independent exponents than naive thermodynamics suggests.}
$$

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Map from the homogeneous singular free energy to critical exponents and scaling relations](/figures/renormalization-rg-eft/critical-exponent-scaling-relations.svg)

<figcaption>

The standard exponent identities follow from one homogeneity law for the singular free-energy density, plus the scaling dimension of the order-parameter field. Hyperscaling additionally assumes that the singular free energy is controlled by one correlation volume, $f_s\sim \xi^{-d}$.

</figcaption>
</figure>

:::note[One sentence to remember]
Scaling relations are the algebra of fixed-point homogeneity; hyperscaling is the extra statement that one correlation volume carries order-one singular free energy.
:::

## Prerequisites

You should know [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), and [Scale Invariance](/renormalization-rg-eft/fixed-points-critical-phenomena/scale-invariance/).

The useful mathematical idea is a homogeneous function. If $F(x,y)$ obeys

$$
F(x,y)=b^{-d}F(b^{y_t}x,b^{y_h}y),
$$

then choosing $b$ to set one argument to order one turns scaling into power laws.

## Core idea

A list of six exponents,

$$
\alpha,
\quad
\beta_{\mathrm{mag}},
\quad
\gamma,
\quad
\delta,
\quad
\nu,
\quad
\eta,
$$

looks like six independent numbers. Near an ordinary critical point, however, most of them are determined by two pieces of fixed-point data: the thermal eigenvalue $y_t$ and the magnetic eigenvalue $y_h$.

The reason is that the critical point is not an arbitrary singularity. It is an RG fixed point. Close to it, the singular free-energy density has a scaling form:

$$
f_s(u_t,u_h)=b^{-d}f_s(b^{y_t}u_t,b^{y_h}u_h).
$$

Here $u_t$ is the thermal scaling field, $u_h$ is the magnetic scaling field, and $b>1$ is the coarse-graining factor. From this one formula, differentiating with respect to $u_h$ and choosing $b$ appropriately gives $\alpha$, $\beta_{\mathrm{mag}}$, $\gamma$, and $\delta$. The scaling of the correlation length gives $\nu$. The scaling of the two-point function gives $\eta$.

Scaling relations are therefore consistency conditions. If measured or computed exponents violate a relation, at least one of the assumptions behind that relation has failed — or the data have not yet reached the asymptotic scaling regime.

## Setup and conventions

This page uses the same notation as [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/):

| Symbol | Meaning |
|---|---|
| $u_t$ | thermal scaling field, proportional to $\tau=(T-T_c)/T_c$ near the fixed point |
| $u_h$ | magnetic scaling field, proportional to the source $h$ near the fixed point |
| $y_t$ | RG eigenvalue of $u_t$ in IR convention |
| $y_h$ | RG eigenvalue of $u_h$ in IR convention |
| $d$ | Euclidean dimension of the critical statistical field theory |
| $M$ | order parameter, $M=-\partial f_s/\partial h$ up to sign conventions |
| $\chi$ | susceptibility, $\chi=\partial M/\partial h$ |

The magnetization exponent is written $\beta_{\mathrm{mag}}$ to avoid confusion with RG beta functions.

The standard exponent definitions are

$$
C_{\text{sing}}\sim |u_t|^{-\alpha},
\qquad
M(u_t,0)\sim (-u_t)^{\beta_{\mathrm{mag}}},
\qquad
\chi(u_t,0)\sim |u_t|^{-\gamma},
$$

$$
M(0,u_h)\sim \operatorname{sgn}(u_h)|u_h|^{1/\delta},
\qquad
\xi(u_t,0)\sim |u_t|^{-\nu},
\qquad
G_c(r)\sim \frac{1}{r^{d-2+\eta}}.
$$

Signs and amplitudes are omitted because the exponent relations only use powers.

## Homogeneity of the singular free energy

The singular part of the free-energy density obeys

$$
f_s(u_t,u_h)=b^{-d}f_s(b^{y_t}u_t,b^{y_h}u_h).
$$

This formula says that after coarse graining by $b$, the free energy per unit volume picks up the volume factor $b^{-d}$, while the scaling fields transform by their RG eigenvalues.

Choose

$$
b=|u_t|^{-1/y_t}.
$$

Then

$$
f_s(u_t,0)
=|u_t|^{d/y_t}f_s(\pm1,0).
$$

Thus

$$
f_s(u_t,0)\sim |u_t|^{d/y_t}.
$$

Since the heat capacity involves two thermal derivatives,

$$
C_{\text{sing}}\sim |u_t|^{d/y_t-2}.
$$

Comparing with $C_{\text{sing}}\sim |u_t|^{-\alpha}$ gives

$$
\alpha=2-\frac{d}{y_t}.
$$

The correlation length obeys

$$
\xi(u_t,u_h)=b\,\xi(b^{y_t}u_t,b^{y_h}u_h).
$$

The same choice of $b$ gives

$$
\xi(u_t,0)\sim |u_t|^{-1/y_t},
$$

so

$$
\nu=\frac{1}{y_t}.
$$

These two formulas immediately imply hyperscaling:

$$
2-\alpha=d\nu.
$$

But this is the relation with the most important caveats, because it assumes the singular free-energy density scales as an ordinary density controlled by the fixed point.

## Exponents from derivatives of the free energy

The order parameter is one derivative of the free-energy density with respect to the magnetic scaling field:

$$
M(u_t,u_h)=-\frac{\partial f_s}{\partial u_h}.
$$

Differentiating the homogeneity law gives

$$
M(u_t,u_h)=b^{-d+y_h}M(b^{y_t}u_t,b^{y_h}u_h).
$$

At zero field, choose $b=|u_t|^{-1/y_t}$. Then

$$
M(u_t,0)\sim |u_t|^{(d-y_h)/y_t},
$$

so

$$
\beta_{\mathrm{mag}}=\frac{d-y_h}{y_t}.
$$

The susceptibility is a second magnetic derivative:

$$
\chi(u_t,u_h)=\frac{\partial M}{\partial u_h}.
$$

Therefore

$$
\chi(u_t,u_h)=b^{-d+2y_h}\chi(b^{y_t}u_t,b^{y_h}u_h).
$$

At zero field,

$$
\chi(u_t,0)\sim |u_t|^{(d-2y_h)/y_t}.
$$

Since $\chi\sim |u_t|^{-\gamma}$,

$$
\gamma=\frac{2y_h-d}{y_t}.
$$

At $u_t=0$, choose

$$
b=|u_h|^{-1/y_h}.
$$

Then

$$
M(0,u_h)\sim |u_h|^{(d-y_h)/y_h}.
$$

Since $M(0,u_h)\sim |u_h|^{1/\delta}$,

$$
\delta=\frac{y_h}{d-y_h}.
$$

So the thermodynamic exponents are

$$
\alpha=2-\frac{d}{y_t},
\qquad
\beta_{\mathrm{mag}}=\frac{d-y_h}{y_t},
\qquad
\gamma=\frac{2y_h-d}{y_t},
\qquad
\delta=\frac{y_h}{d-y_h}.
$$

The scaling relations are now just algebra.

## Rushbrooke relation

The Rushbrooke relation is

$$
\alpha+2\beta_{\mathrm{mag}}+\gamma=2.
$$

Using the RG expressions,

$$
\alpha+2\beta_{\mathrm{mag}}+\gamma
=
\left(2-\frac{d}{y_t}\right)
+2\left(\frac{d-y_h}{y_t}\right)
+\left(\frac{2y_h-d}{y_t}\right).
$$

The terms proportional to $1/y_t$ cancel:

$$
-\frac{d}{y_t}+\frac{2d-2y_h}{y_t}+\frac{2y_h-d}{y_t}=0.
$$

Therefore

$$
\alpha+2\beta_{\mathrm{mag}}+\gamma=2.
$$

This relation says that the singular heat capacity, spontaneous order parameter, and susceptibility cannot be assigned arbitrary powers if they all come from the same homogeneous free energy.

## Widom relation

The Widom relation is

$$
\gamma=\beta_{\mathrm{mag}}(\delta-1).
$$

Using

$$
\delta=\frac{y_h}{d-y_h},
$$

we find

$$
\delta-1
=\frac{y_h}{d-y_h}-1
=\frac{2y_h-d}{d-y_h}.
$$

Thus

$$
\beta_{\mathrm{mag}}(\delta-1)
=\frac{d-y_h}{y_t}\frac{2y_h-d}{d-y_h}
=\frac{2y_h-d}{y_t}
=\gamma.
$$

This relation is often easiest to remember from the scaling equation of state:

$$
M(u_t,u_h)=|u_t|^{\beta_{\mathrm{mag}}}\mathcal M_\pm\!\left(\frac{u_h}{|u_t|^{\beta_{\mathrm{mag}}\delta}}\right).
$$

The combination $u_h/|u_t|^{\beta_{\mathrm{mag}}\delta}$ is fixed by RG homogeneity.

## Fisher relation

The Fisher relation connects the susceptibility exponent to the correlation-function exponent:

$$
\gamma=\nu(2-\eta).
$$

At criticality,

$$
G_c(r)\sim \frac{1}{r^{d-2+\eta}}.
$$

Away from criticality, the susceptibility is the integral of the connected correlation function:

$$
\chi\sim \int_{|r|\lesssim \xi} d^d r\,G_c(r).
$$

Using the critical power law up to the cutoff scale $\xi$ gives

$$
\chi\sim \int^{\xi} dr\,r^{d-1}\frac{1}{r^{d-2+\eta}}
=\int^{\xi}dr\,r^{1-\eta}
\sim \xi^{2-\eta},
$$

provided the long-distance singularity dominates. Since

$$
\xi\sim |u_t|^{-\nu},
$$

we obtain

$$
\chi\sim |u_t|^{-\nu(2-\eta)}.
$$

Therefore

$$
\gamma=\nu(2-\eta).
$$

Equivalently, using $y_h=(d+2-\eta)/2$ and $\nu=1/y_t$,

$$
\gamma=\frac{2y_h-d}{y_t}=\nu(2-\eta).
$$

## Josephson hyperscaling

Josephson hyperscaling is

$$
2-\alpha=d\nu.
$$

A physical way to derive it is to say that the singular free-energy density is of order one per correlation volume:

$$
f_s\sim \xi^{-d}.
$$

Since

$$
\xi\sim |u_t|^{-\nu},
$$

we get

$$
f_s\sim |u_t|^{d\nu}.
$$

But the heat-capacity exponent says

$$
f_s\sim |u_t|^{2-\alpha},
$$

because two thermal derivatives lower the power by two. Hence

$$
2-\alpha=d\nu.
$$

This relation is powerful, but less universally safe than Rushbrooke, Widom, or Fisher. It assumes that the singular free energy is governed by the correlation length in $d$ dimensions without extra dangerous dependence on irrelevant couplings.

## Derived relations

Combining the standard relations gives several useful forms:

$$
2\beta_{\mathrm{mag}}+\gamma=d\nu,
$$

$$
\beta_{\mathrm{mag}}=\frac{\nu}{2}(d-2+\eta),
$$

$$
\delta=\frac{d+2-\eta}{d-2+\eta}.
$$

These relations are not independent once the two-eigenvalue scaling form is assumed. They are different projections of the same underlying homogeneity.

For example,

$$
\beta_{\mathrm{mag}}=\frac{d-y_h}{y_t},
\qquad
\nu=\frac1{y_t},
\qquad
\eta=d+2-2y_h.
$$

Since

$$
d-y_h=\frac{d-2+\eta}{2},
$$

we get

$$
\beta_{\mathrm{mag}}
=\nu\frac{d-2+\eta}{2}.
$$

The formula for $\delta$ follows by dividing $y_h$ by $d-y_h$.

## What can fail?

Scaling relations are conditional statements. They hold when their assumptions hold.

### Above the upper critical dimension

For short-range scalar $\phi^4$ theory, the upper critical dimension is $d_c=4$. Above it, mean-field exponents are

$$
\alpha=0,
\qquad
\beta_{\mathrm{mag}}=\frac12,
\qquad
\gamma=1,
\qquad
\delta=3,
\qquad
\nu=\frac12,
\qquad
\eta=0.
$$

Rushbrooke and Widom still work:

$$
0+2\left(\frac12\right)+1=2,
\qquad
1=\frac12(3-1).
$$

Fisher also works:

$$
1=\frac12(2-0).
$$

But hyperscaling gives

$$
2-\alpha=2,
\qquad
d\nu=\frac d2.
$$

These agree only at $d=4$. For $d>4$, the quartic coupling is irrelevant at the Gaussian fixed point but remains dangerously irrelevant for some thermodynamic quantities. The singular free-energy density does not obey the naive $f_s\sim \xi^{-d}$ rule.

### Dangerously irrelevant variables

An irrelevant coupling usually dies under RG flow and only corrects scaling. A **dangerously irrelevant** coupling dies at the fixed point but appears in the denominator or normalization of an observable, so setting it to zero too early gives the wrong answer.

The classic example is the quartic coupling in Landau theory above four dimensions. It is irrelevant at the Gaussian fixed point, but the ordered-phase magnetization depends on it:

$$
M^2\sim -\frac{\tau}{u}.
$$

The coupling $u$ flows to zero, yet the order parameter is singular in $u$. This is why the naive hyperscaling picture fails.

### Long-range interactions and anisotropic scaling

If the fixed point has long-range interactions, the two-point function may not have the short-range form $r^{-(d-2+\eta)}$. If the system has anisotropic scaling, such as

$$
t\to b^z t,
\qquad
\mathbf x\to b\mathbf x,
$$

then the effective scaling dimension of spacetime and the free-energy density changes. Quantum critical points with $z\ne1$, Lifshitz points, driven systems, and nonequilibrium fixed points require modified scaling forms.

### Multiple relevant fields and multicriticality

At a multicritical point, more than one thermal-like relevant direction may be present. Then a single reduced temperature $\tau$ is not enough to describe all approaches to criticality. Exponents can depend on the path used to approach the fixed point unless the path is specified in terms of scaling fields.

### Constraints and Fisher renormalization

If an experiment or model imposes a constraint, such as fixed density rather than fixed chemical potential, the measured exponent can be a transformed exponent. This phenomenon is often called Fisher renormalization of exponents. The fixed-point data are not wrong; the thermodynamic path has changed.

## Equalities, inequalities, and data checks

Historically, some exponent relations were first understood as inequalities from thermodynamic stability and convexity. Scaling turns some of them into equalities when the fixed-point homogeneity assumptions hold.

In practice, scaling relations are useful checks. If numerical or experimental exponents do not satisfy them, possible explanations include:

- the asymptotic critical regime has not been reached;
- corrections to scaling are large;
- the wrong universality class is being assumed;
- a constraint changes the measured exponents;
- hyperscaling fails because of a dangerously irrelevant variable;
- the system has long-range, anisotropic, disordered, or nonequilibrium scaling;
- the quoted uncertainties are underestimated.

The best attitude is neither blind trust nor panic. A violated relation is a diagnostic. It tells you which assumption to inspect.

## Common pitfalls

**Using scaling relations without checking their assumptions.** Rushbrooke, Widom, Fisher, and Josephson hyperscaling do not all have identical status. Hyperscaling is especially sensitive to dangerously irrelevant variables and upper-critical-dimension effects.

**Treating $\tau$ and $u_t$ as exactly the same.** The reduced temperature $\tau$ is usually proportional to the thermal scaling field near the fixed point, but nonlinear mixing with other couplings can matter away from the asymptotic region.

**Forgetting that $\beta_{\mathrm{mag}}$ is not a beta function.** The exponent $\beta_{\mathrm{mag}}$ is a critical exponent. An RG beta function is a vector field on coupling space.

**Believing mean-field theory satisfies all scaling laws in every dimension.** Mean-field exponents satisfy several scaling relations but violate hyperscaling above $d_c=4$ for short-range scalar models.

**Confusing hyperscaling with universality.** Hyperscaling can fail while universality still exists. Above the upper critical dimension, mean-field exponents are universal in the appropriate sense, but naive hyperscaling is not valid.

## Relations to other pages

[Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/) defines the exponents used here. [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/) explains why the relevant eigenvalues $y_t$ and $y_h$ control them. Later pages on universality classes will explain why the same exponent relations and exponent values appear in different microscopic systems.

Later pages on the Wilson–Fisher fixed point and epsilon expansion will compute exponents perturbatively near $d=4$. A later page on crossover and dangerously irrelevant operators will return to the most important caveats.

## Research status

The standard scaling relations are settled within their domains of validity. They are among the central outputs of the Wilsonian RG picture of critical phenomena.

The active work is in identifying when the simple assumptions must be generalized. Modern examples include long-range interacting systems, disordered systems, deconfined critical points, gauge-matter criticality, fracton and subsystem-symmetric systems, nonequilibrium universality classes, multicritical points, and theories above or at an upper critical dimension. In these cases the task is not to abandon scaling, but to find the correct scaling variables, dimensions, dangerously irrelevant couplings, and finite-size forms.

## Exercises

### Exercise 1: Rushbrooke from homogeneity

Use

$$
\alpha=2-\frac{d}{y_t},
\qquad
\beta_{\mathrm{mag}}=\frac{d-y_h}{y_t},
\qquad
\gamma=\frac{2y_h-d}{y_t}
$$

to prove

$$
\alpha+2\beta_{\mathrm{mag}}+\gamma=2.
$$

<details><summary><strong>Solution</strong></summary>

Substitute the expressions:

$$
\alpha+2\beta_{\mathrm{mag}}+\gamma
=
\left(2-\frac{d}{y_t}\right)
+2\left(\frac{d-y_h}{y_t}\right)
+\left(\frac{2y_h-d}{y_t}\right).
$$

The numerator of the $1/y_t$ part is

$$
-d+2d-2y_h+2y_h-d=0.
$$

Therefore

$$
\alpha+2\beta_{\mathrm{mag}}+\gamma=2.
$$

</details>

### Exercise 2: Widom from the critical isotherm

Using

$$
\beta_{\mathrm{mag}}=\frac{d-y_h}{y_t},
\qquad
\gamma=\frac{2y_h-d}{y_t},
\qquad
\delta=\frac{y_h}{d-y_h},
$$

prove

$$
\gamma=\beta_{\mathrm{mag}}(\delta-1).
$$

<details><summary><strong>Solution</strong></summary>

First compute

$$
\delta-1
=\frac{y_h}{d-y_h}-1
=\frac{2y_h-d}{d-y_h}.
$$

Then

$$
\beta_{\mathrm{mag}}(\delta-1)
=\frac{d-y_h}{y_t}\frac{2y_h-d}{d-y_h}
=\frac{2y_h-d}{y_t}
=\gamma.
$$

</details>

### Exercise 3: Mean-field hyperscaling failure

Mean-field theory gives

$$
\alpha=0,
\qquad
\nu=\frac12.
$$

For which dimension $d$ does Josephson hyperscaling hold? What happens for $d>4$ in short-range scalar models?

<details><summary><strong>Solution</strong></summary>

Josephson hyperscaling says

$$
2-\alpha=d\nu.
$$

With mean-field values,

$$
2=\frac d2.
$$

Therefore hyperscaling holds only for

$$
d=4.
$$

For $d>4$, short-range scalar models are above their upper critical dimension. The quartic coupling is irrelevant at the Gaussian fixed point but dangerously irrelevant for thermodynamic quantities such as the order parameter. Mean-field exponents can be correct while the naive hyperscaling relation fails.

</details>

### Exercise 4: Finite-size scaling of the susceptibility

Assume that at criticality in a finite box of size $L$, the correlation length is cut off by $L$. Use the Fisher relation idea $\chi\sim \xi^{2-\eta}$ to show that

$$
\chi_L(0)\sim L^{2-\eta}.
$$

Then use $\gamma=\nu(2-\eta)$ to rewrite this as

$$
\chi_L(0)\sim L^{\gamma/\nu}.
$$

<details><summary><strong>Solution</strong></summary>

At infinite volume, the susceptibility scales as

$$
\chi\sim \xi^{2-\eta}.
$$

At criticality in a finite box, the system cannot develop correlations larger than $L$, so the finite size replaces $\xi$ as the infrared cutoff:

$$
\xi\sim L.
$$

Therefore

$$
\chi_L(0)\sim L^{2-\eta}.
$$

Using Fisher's relation,

$$
\gamma=\nu(2-\eta),
$$

we have

$$
2-\eta=\frac{\gamma}{\nu}.
$$

Thus

$$
\chi_L(0)\sim L^{\gamma/\nu}.
$$

</details>

## References

- Kenneth G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974), for the Wilsonian derivation of scaling and exponent relations.
- Sidney Coleman, “Dilatations,” in *Aspects of Symmetry*, for scaling, anomalous dimensions, and the RG interpretation of scale dependence.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for RG methods and critical phenomena from a field-theory viewpoint.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for detailed exponent calculations, scaling relations, and caveats.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for a clear derivation of scaling relations and hyperscaling.
- Nigel Goldenfeld, *Lectures on Phase Transitions and the Renormalization Group*, for physical explanations, scaling equations of state, and examples.

## Version history

- 2026-06-17: First polished draft. Derived Rushbrooke, Widom, Fisher, and Josephson hyperscaling relations; clarified hyperscaling caveats and dangerous irrelevant variables; added exercises with solutions.
