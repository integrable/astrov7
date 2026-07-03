---
title: "Phi-Four Beta Function"
description: "Derive the one-loop beta function of real scalar phi-four theory from the minimal-subtraction coupling counterterm and interpret the running, Landau pole, and Wilson–Fisher continuation."
sidebar:
  label: "Phi-Four Beta Function"
  order: 2
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§27–29; Coleman 1985, Dilatations; Coleman 2019, renormalization lectures; Schwartz 2014, ch. 23; Wilson and Kogut 1974; Zinn-Justin 2021."
topics:
  - phi-four beta function
  - running couplings
  - minimal subtraction
  - Wilson–Fisher fixed point
  - Landau pole
  - one-loop RG
canonicalTopics:
  - phi-four-beta-function
  - scalar-coupling-running
  - one-loop-rg
researchStatus:
  established:
    - "The one-loop beta function of real scalar phi-four theory is a standard perturbative result and the starting point for the Wilson–Fisher epsilon expansion."
  active:
    - "High-loop scalar beta functions, resummation, conformal bootstrap comparisons, and nonperturbative definitions of scalar theories remain important in critical phenomena and mathematical QFT."
---

## Summary

The one-loop coupling counterterm in real scalar $\phi^4$ theory determines the leading beta function. With the interaction normalized as

$$
\mathcal L_{\text{int}}=-\frac{\lambda}{4!}\phi^4
$$

and the volume convention

$$
\beta_\lambda=\left.\mu\frac{d\lambda}{d\mu}\right|_{\text{bare fixed}},
$$

the four-dimensional one-loop result is

$$
\boxed{
\beta_\lambda=\frac{3\lambda^2}{16\pi^2}+O(\lambda^3)
}
$$

for one real scalar field. The positive sign means that, in perturbation theory, the coupling grows toward the ultraviolet and decreases toward the infrared.

In $d=4-2\epsilon$, the same calculation gives

$$
\beta_\lambda=-2\epsilon\lambda+\frac{3\lambda^2}{16\pi^2}+O(\lambda^3),
$$

so for $\epsilon>0$ there is a perturbative fixed point at

$$
\lambda_*=\frac{32\pi^2}{3}\epsilon+O(\epsilon^2).
$$

This is the first glimpse of the Wilson–Fisher fixed point. In exactly four dimensions, the same positive beta function leads to a perturbative Landau-pole scale rather than an ultraviolet-complete weakly coupled theory.

:::note[What this page adds]
The previous page computed the one-loop counterterm. This page turns that counterterm into RG flow by differentiating the bare coupling at fixed bare data.
:::

## Prerequisites

You should know [Phi-Four One-Loop Renormalization](/renormalization-rg-eft/model-calculation-library/phi-four-one-loop-renormalization/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/), and [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/).

We use

$$
d=4-2\epsilon,
\qquad
\frac{1}{\bar\epsilon}=\frac{1}{\epsilon}-\gamma_E+\log4\pi.
$$

If a source uses $d=4-\epsilon$ instead, the engineering term is $-\epsilon\lambda$ rather than $-2\epsilon\lambda$, and the fixed-point value differs by the corresponding factor of two.

## The key input: the coupling counterterm

The one-loop four-point calculation gives a local logarithmic divergence proportional to $\lambda^2\phi^4$. In an MS-like scheme, the pole part is summarized by

$$
\delta\lambda
=
\frac{3\lambda^2}{32\pi^2}\frac{1}{\bar\epsilon}+O(\lambda^3),
$$

using the counterterm-Lagrangian convention of the previous page:

$$
\mathcal L_{\text{ct}}
\supset
-\frac{\mu^{2\epsilon}\delta\lambda}{4!}\phi^4.
$$

For deriving the beta function, it is safest to write the bare coupling in a sign-explicit convention. We define

$$
\lambda_0
=
\mu^{2\epsilon}
\left[
\lambda
+
\frac{3\lambda^2}{32\pi^2}\frac{1}{\bar\epsilon}
+O(\lambda^3)
\right].
$$

Here $\lambda_0$ is independent of the arbitrary renormalization scale $\mu$. The renormalized coupling $\lambda(\mu)$ changes with $\mu$ so that $\lambda_0$ remains fixed.

Because $1/\bar\epsilon$ differs from $1/\epsilon$ only by finite constants, the pole coefficient that determines the one-loop beta function is the coefficient of $1/\epsilon$. The finite $-\gamma_E+\log4\pi$ part is part of the $\overline{\mathrm{MS}}$ coordinate choice.

## Derivation from fixed bare coupling

Let

$$
a\equiv\frac{3}{32\pi^2}.
$$

Then to one-loop order,

$$
\lambda_0
=
\mu^{2\epsilon}\left(\lambda+a\frac{\lambda^2}{\epsilon}\right)
$$

where replacing $1/\bar\epsilon$ by $1/\epsilon$ is enough for the beta-function coefficient. Differentiate at fixed $\lambda_0$:

$$
0=
\mu\frac{d\lambda_0}{d\mu}.
$$

This gives

$$
0=
2\epsilon\mu^{2\epsilon}
\left(\lambda+a\frac{\lambda^2}{\epsilon}\right)
+
\mu^{2\epsilon}
\beta_\lambda
\left(1+2a\frac{\lambda}{\epsilon}\right)
+O(\lambda^3).
$$

Now write the beta function in the form

$$
\beta_\lambda=-2\epsilon\lambda+b\lambda^2+O(\lambda^3).
$$

The leading term $-2\epsilon\lambda$ is just engineering dimension: in $d=4-2\epsilon$, the quartic coupling has mass dimension $2\epsilon$. Substituting this ansatz gives

$$
0=
2\epsilon\lambda+2a\lambda^2
+
(-2\epsilon\lambda+b\lambda^2)
\left(1+2a\frac{\lambda}{\epsilon}\right)
+O(\lambda^3).
$$

The term $(-2\epsilon\lambda)(2a\lambda/\epsilon)$ is essential. It contributes at order $\lambda^2$:

$$
0=
2\epsilon\lambda+2a\lambda^2
-2\epsilon\lambda+b\lambda^2-4a\lambda^2
+O(\lambda^3).
$$

Therefore

$$
b=2a=\frac{3}{16\pi^2}.
$$

Thus

$$
\beta_\lambda=-2\epsilon\lambda+\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

In four dimensions, $\epsilon=0$, so

$$
\beta_\lambda=\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

:::tip[The common missing term]
When differentiating the pole term, do not set the leading engineering part of $\beta_\lambda$ to zero too early. The product

$$
(-2\epsilon\lambda)\left(2a\frac{\lambda}{\epsilon}\right)
$$

is finite as $\epsilon\to0$ and contributes to the one-loop beta function.
:::

## Running in four dimensions

At one loop in $d=4$,

$$
\frac{d\lambda}{d\log\mu}
=
\frac{3\lambda^2}{16\pi^2}.
$$

Separating variables gives

$$
\int_{\lambda(\mu_0)}^{\lambda(\mu)}\frac{d\lambda}{\lambda^2}
=
\frac{3}{16\pi^2}
\int_{\mu_0}^{\mu}d\log\mu,
$$

so

$$
-\frac{1}{\lambda(\mu)}+\frac{1}{\lambda(\mu_0)}
=
\frac{3}{16\pi^2}\log\frac{\mu}{\mu_0}.
$$

Equivalently,

$$
\frac{1}{\lambda(\mu)}
=
\frac{1}{\lambda(\mu_0)}
-
\frac{3}{16\pi^2}\log\frac{\mu}{\mu_0}.
$$

For positive $\lambda(\mu_0)$, the denominator decreases as $\mu$ increases. The one-loop expression predicts a pole at

$$
\mu_L
=
\mu_0\exp\left[\frac{16\pi^2}{3\lambda(\mu_0)}\right].
$$

This is the perturbative Landau pole. It does not mean that an actual physical scattering amplitude must literally diverge there. It means that the weak-coupling one-loop description cannot define an ultraviolet-complete scalar theory by itself.

For $\mu<\mu_0$, the coupling decreases. Thus $\lambda=0$ is an infrared fixed point for positive coupling in four dimensions.

## Interpretation of the sign

The positive beta function has two complementary readings.

In perturbative particle-physics language, increasing $\mu$ probes shorter distances. The renormalized quartic coupling grows toward the ultraviolet:

$$
\mu\uparrow
\quad\Longrightarrow\quad
\lambda(\mu)\uparrow.
$$

In Wilsonian language, lowering the cutoff flows toward the infrared. The same positive beta function means that the quartic coupling is marginally irrelevant in four dimensions for positive $\lambda$:

$$
\Lambda\downarrow
\quad\Longrightarrow\quad
\lambda(\Lambda)\downarrow.
$$

These are not contradictory statements. They use opposite directions of RG time. The volume convention uses $t=\log\mu$, which increases toward the ultraviolet.

## The Wilson–Fisher continuation

In $d=4-2\epsilon$, the beta function is

$$
\beta_\lambda=-2\epsilon\lambda+\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

There are two perturbative zeros:

$$
\lambda_*=0
$$

and

$$
\lambda_*=\frac{32\pi^2}{3}\epsilon+O(\epsilon^2).
$$

For $\epsilon>0$, the second zero is weakly coupled when $\epsilon\ll1$. This is the perturbative origin of the Wilson–Fisher fixed point. It describes a nontrivial critical theory below four dimensions.

The linearized beta function at the nonzero fixed point is

$$
\left.\frac{d\beta_\lambda}{d\lambda}\right|_{\lambda_*}
=
-2\epsilon+\frac{6\lambda_*}{16\pi^2}+O(\epsilon^2)
=
2\epsilon+O(\epsilon^2).
$$

With the convention $t=\log\mu$, this positive derivative means that the quartic perturbation is unstable toward the ultraviolet but attractive toward the infrared along the quartic direction. The mass term remains a relevant perturbation that must be tuned to reach the critical point.

:::note[Why this belongs in the model library]
The full Wilson–Fisher calculation also needs the mass beta function, field anomalous dimension, and critical exponents. This page isolates the coupling-flow part. The Wilson–Fisher model page will assemble the full critical-phenomena interpretation.
:::

## Mass running from the same calculation

The previous page also found the one-loop mass counterterm

$$
\delta m^2=\frac{\lambda m^2}{32\pi^2}\frac{1}{\bar\epsilon}+O(\lambda^2).
$$

The corresponding one-loop running of the renormalized mass parameter is

$$
\beta_{m^2}
\equiv
\left.\mu\frac{d m^2}{d\mu}\right|_{\text{bare fixed}}
=
\frac{\lambda}{16\pi^2}m^2+O(\lambda^2).
$$

There is no additive $\mu^2$ term in MS-like dimensional regularization. That does not mean scalar masses are automatically natural. It means that MS tracks logarithmic running of the renormalized coordinate. Heavy thresholds, if present, can still generate finite additive contributions proportional to heavy masses. That distinction is one of the central lessons of the naturalness chapter.

## Scheme dependence

The one-loop coefficient

$$
\frac{3}{16\pi^2}
$$

is universal under ordinary analytic redefinitions of the coupling. Suppose we define a new coupling

$$
\lambda'=\lambda+c\lambda^2+O(\lambda^3).
$$

Then

$$
\beta_{\lambda'}=\frac{d\lambda'}{d\lambda}\beta_\lambda
=
(1+2c\lambda+\cdots)
\left(\frac{3\lambda^2}{16\pi^2}+O(\lambda^3)\right).
$$

Since $\lambda^2=\lambda'^2+O(\lambda'^3)$, the coefficient of $\lambda'^2$ is unchanged. Higher-loop coefficients can depend on the scheme, and finite definitions of the coupling can change the appearance of the running at finite order.

A momentum-subtraction scheme would define the quartic coupling by a condition such as

$$
\Gamma_R^{(4)}(s_0,t_0,u_0)=-\lambda_{\text{MOM}}(\mu)
$$

at a chosen Euclidean symmetric point. This differs from $\overline{\mathrm{MS}}$ by finite terms, but the leading one-loop beta coefficient agrees.

## Physical meaning and limitations

The beta function describes how the renormalized coordinate $\lambda(\mu)$ changes when the arbitrary subtraction scale changes at fixed bare theory. It is not itself a directly measured observable. Physical quantities are independent of $\mu$ when computed to all orders.

At finite perturbative order, choosing $\mu$ near the characteristic external scale reduces large logarithms. For example, a four-point amplitude contains finite terms with logarithms of the form

$$
\lambda^2\log\frac{-s}{\mu^2},
\qquad
\lambda^2\log\frac{-t}{\mu^2},
\qquad
\lambda^2\log\frac{-u}{\mu^2}.
$$

The running of $\lambda(\mu)$ compensates this explicit $\mu$ dependence. RG improvement is the art of using that compensation to resum logarithms when scales are widely separated.

The one-loop Landau pole should also be read carefully. It is a perturbative warning, not a theorem that the path integral explodes at exactly $\mu_L$. Nonperturbative questions about scalar theories in four dimensions are subtler and connect to triviality, lattice continuum limits, and rigorous QFT.

## Common pitfalls

**Dropping the engineering term too early.** In $d=4-2\epsilon$, the term $-2\epsilon\lambda$ contributes indirectly to the finite one-loop coefficient when differentiating the pole term.

**Confusing $1/\epsilon$ with $1/\bar\epsilon$.** The finite $-\gamma_E+\log4\pi$ part distinguishes MS from $\overline{\mathrm{MS}}$. The one-loop beta coefficient is determined by the pole coefficient.

**Forgetting the coupling normalization.** The formula

$$
\beta_\lambda=\frac{3\lambda^2}{16\pi^2}
$$

assumes the interaction is $-\lambda\phi^4/4!$. Other normalizations change the coefficient.

**Interpreting the beta function as an observable.** The beta function is scheme-dependent beyond universal leading data. Observables are scheme-independent when computed consistently.

**Thinking dimensional regularization removes naturalness issues.** MS running does not display quadratic divergences. Heavy thresholds can still produce additive scalar mass sensitivity.

**Calling the Wilson–Fisher fixed point four-dimensional.** The perturbative fixed point shown here is at $d=4-2\epsilon$ with $\epsilon>0$. In exactly four dimensions, the one-loop nonzero zero disappears.

## Relations to other pages

This page is the direct sequel to [Phi-Four One-Loop Renormalization](/renormalization-rg-eft/model-calculation-library/phi-four-one-loop-renormalization/). It uses the same coupling counterterm but changes the question from "which divergence is canceled?" to "how does the renormalized coupling run?"

It also concretely illustrates [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Landau Poles](/renormalization-rg-eft/renormalization-group-equations/landau-poles/), [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/), and [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/). The continuation to $d<4$ prepares for [Wilson–Fisher Epsilon Expansion](/renormalization-rg-eft/model-calculation-library/wilson-fisher-epsilon-expansion/) and the critical-phenomena chapters.

## Research status

The one-loop beta function is textbook material. What remains deep is the global question it points toward: how scalar theories behave nonperturbatively in four dimensions, how continuum limits are defined, how perturbative series encode critical exponents after resummation, and how RG, lattice, conformal bootstrap, and rigorous methods compare.

For practical high-energy EFT, the lesson is also durable: beta functions are extracted from local logarithmic UV sensitivity and control the scale dependence of renormalized parameters. For statistical field theory, the same calculation is the gateway to universal critical exponents.

## Exercises

### Exercise 1: Derive the one-loop beta function

Let

$$
\lambda_0=
\mu^{2\epsilon}
\left(\lambda+a\frac{\lambda^2}{\epsilon}\right),
\qquad
 a=\frac{3}{32\pi^2}.
$$

Holding $\lambda_0$ fixed, derive

$$
\beta_\lambda=-2\epsilon\lambda+\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

<details><summary><strong>Solution</strong></summary>

Differentiate at fixed $\lambda_0$:

$$
0=2\epsilon\left(\lambda+a\frac{\lambda^2}{\epsilon}\right)
+\beta_\lambda\left(1+2a\frac{\lambda}{\epsilon}\right).
$$

Use the ansatz

$$
\beta_\lambda=-2\epsilon\lambda+b\lambda^2+O(\lambda^3).
$$

Then

$$
0=2\epsilon\lambda+2a\lambda^2
-2\epsilon\lambda+b\lambda^2-4a\lambda^2+O(\lambda^3),
$$

so $b=2a$. Since $a=3/(32\pi^2)$,

$$
\beta_\lambda=-2\epsilon\lambda+\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

</details>

### Exercise 2: Solve the one-loop running

Solve

$$
\frac{d\lambda}{d\log\mu}=b\lambda^2,
\qquad b=\frac{3}{16\pi^2},
$$

with initial condition $\lambda(\mu_0)=\lambda_0^{(R)}$.

<details><summary><strong>Solution</strong></summary>

Separate variables:

$$
\frac{d\lambda}{\lambda^2}=b\,d\log\mu.
$$

Integrating from $\mu_0$ to $\mu$ gives

$$
-\frac{1}{\lambda(\mu)}+\frac{1}{\lambda_0^{(R)}}
=b\log\frac{\mu}{\mu_0}.
$$

Thus

$$
\lambda(\mu)=
\frac{\lambda_0^{(R)}}{1-b\lambda_0^{(R)}\log(\mu/\mu_0)}.
$$

The denominator vanishes at

$$
\mu_L=\mu_0\exp\left[\frac{1}{b\lambda_0^{(R)}}\right]
=
\mu_0\exp\left[\frac{16\pi^2}{3\lambda_0^{(R)}}\right].
$$

</details>

### Exercise 3: Fixed point below four dimensions

Using

$$
\beta_\lambda=-2\epsilon\lambda+\frac{3\lambda^2}{16\pi^2},
$$

find the nonzero fixed point and the derivative of the beta function there.

<details><summary><strong>Solution</strong></summary>

Set $\beta_\lambda=0$:

$$
\lambda\left(-2\epsilon+\frac{3\lambda}{16\pi^2}\right)=0.
$$

The nonzero fixed point is

$$
\lambda_*=\frac{32\pi^2}{3}\epsilon.
$$

The derivative is

$$
\beta'_\lambda(\lambda)
=-2\epsilon+\frac{6\lambda}{16\pi^2},
$$

so

$$
\beta'_\lambda(\lambda_*)
=-2\epsilon+\frac{6}{16\pi^2}\frac{32\pi^2}{3}\epsilon
=2\epsilon.
$$

</details>

### Exercise 4: Coupling redefinition

Let

$$
\lambda'=\lambda+c\lambda^2+O(\lambda^3).
$$

Show that the coefficient of $\lambda^2$ in the one-loop beta function is unchanged.

<details><summary><strong>Solution</strong></summary>

The transformed beta function is

$$
\beta_{\lambda'}=\frac{d\lambda'}{d\lambda}\beta_\lambda.
$$

Since

$$
\frac{d\lambda'}{d\lambda}=1+2c\lambda+O(\lambda^2)
$$

and

$$
\beta_\lambda=b\lambda^2+O(\lambda^3),
$$

we get

$$
\beta_{\lambda'}=b\lambda^2+O(\lambda^3).
$$

But $\lambda^2=\lambda'^2+O(\lambda'^3)$, so

$$
\beta_{\lambda'}=b\lambda'^2+O(\lambda'^3).
$$

Thus the one-loop coefficient is invariant under this analytic coupling redefinition.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially the sections on other renormalization schemes, the renormalization group, and effective field theory.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," for the Callan–Symanzik and RG interpretation of scale dependence.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the renormalization lectures leading from counterterms to RG equations.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapter on the renormalization group.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the fixed-point and critical-phenomena interpretation.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for higher-loop scalar-field RG, critical exponents, and resummation.

## Version history

- 2026-06-19: First polished draft. Derived the one-loop beta function from the coupling counterterm, solved the running, discussed the Landau pole, Wilson–Fisher continuation, mass running, scheme dependence, and exercises.
