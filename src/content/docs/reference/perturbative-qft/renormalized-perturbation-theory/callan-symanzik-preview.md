---
title: "Callan–Symanzik Preview"
description: "A first perturbative look at the Callan–Symanzik equation: how explicit scale dependence, running parameters, and anomalous dimensions cancel in renormalized Green functions and amplitudes."
sidebar:
  label: "Callan–Symanzik Preview"
  order: 10
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§27–29; Coleman 2019, ch. 50; Weinberg 1995, Vol. I, ch. 12 and Vol. II, ch. 18; Schwartz 2014, ch. 23; Zinn-Justin 2021, chs. 9–10"
topics:
  - Callan–Symanzik equation
  - renormalization group
  - beta functions
  - anomalous dimensions
  - RG improvement
canonicalTopics:
  - callan-symanzik-equation
  - renormalization-group-equation
  - beta-function
  - anomalous-dimension
  - rg-improvement
researchStatus:
  established:
    - "The Callan–Symanzik equation is the standard renormalization-group equation expressing bare-scale independence of renormalized Green functions and vertex functions."
  active:
    - "Modern applications involve operator mixing, gauge dependence, effective field theories, multi-scale processes, conformal data, and infrared factorization beyond the scalar preview given here."
---

## Summary

The **Callan–Symanzik equation** says that the arbitrary renormalization scale $\mu$ introduced during renormalization is not a new physical parameter. Renormalized Green functions may depend explicitly on $\mu$, and renormalized couplings, masses, and fields may depend implicitly on $\mu$, but the bare theory does not.

For renormalized one-particle-irreducible $n$-point vertex functions in a scalar theory, the qft.org convention on this page is

$$
\left[
\mu\frac{\partial}{\partial\mu}
+\beta_\lambda\frac{\partial}{\partial\lambda}
+\beta_{m^2}\frac{\partial}{\partial m^2}
-n\gamma_\phi
\right]
\Gamma_R^{(n)}(p_i;m^2,\lambda,
\mu)
=0.
$$

Here

$$
\beta_\lambda
=\mu\frac{d\lambda}{d\mu}\bigg|_{\rm bare},
\qquad
\beta_{m^2}
=\mu\frac{dm^2}{d\mu}\bigg|_{\rm bare},
\qquad
\gamma_\phi
=\frac12\mu\frac{d\ln Z_\phi}{d\mu}\bigg|_{\rm bare}.
$$

For connected renormalized Green functions of elementary fields, the anomalous-dimension term has the opposite sign in this convention. This sign flip is not physics; it comes from whether external field factors multiply or divide the object being differentiated.

This page is a preview because the full renormalization group belongs to the Renormalization, RG, and EFT volume. Here the goal is narrower: understand how the equation organizes renormalized perturbative amplitudes, running couplings, anomalous dimensions, and leading logarithms.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![The Callan-Symanzik equation balances explicit scale logarithms, running parameters, and anomalous field scaling](/figures/perturbative-qft/callan-symanzik-preview.svg)

<figcaption>

The Callan–Symanzik equation balances three sources of scale dependence: explicit logarithms such as $\ln(p^2/\mu^2)$, implicit scale dependence of renormalized parameters through beta functions, and field scaling through anomalous dimensions. The result is a controlled way to move between renormalization scales, improve perturbation theory, and read scaling behavior near fixed points.

</figcaption>
</figure>

## Prerequisites

You should know [Bare and Renormalized Parameters](/perturbative-qft/renormalized-perturbation-theory/bare-and-renormalized-parameters/), [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/), [Wavefunction Renormalization](/perturbative-qft/renormalized-perturbation-theory/wavefunction-renormalization/), [Mass Renormalization](/perturbative-qft/renormalized-perturbation-theory/mass-renormalization/), [Coupling Renormalization](/perturbative-qft/renormalized-perturbation-theory/coupling-renormalization/), and [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/).

For the loop origin of the logarithms, review [Dimensional Regularization](/perturbative-qft/loop-expansion-regularization/dimensional-regularization/), [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/), and [Vertex Corrections](/perturbative-qft/loop-expansion-regularization/vertex-corrections/).

## Core idea

Renormalization introduces an arbitrary scale $\mu$. A minimal-subtraction amplitude might contain

$$
\ln\frac{-s-i\epsilon}{\mu^2},
$$

while the coupling appearing in the same amplitude is really $\lambda(\mu)$. Changing $\mu$ moves contributions between explicit logarithms and the numerical value of the renormalized coupling. The physics does not change if the calculation is done consistently.

The Callan–Symanzik equation is the differential statement of this consistency.

A useful slogan is:

```txt
explicit scale logs
+
running parameters
+
field anomalous dimensions
=
no new physical scale dependence.
```

At fixed order in perturbation theory, this cancellation is imperfect because higher-order terms have been dropped. The leftover scale dependence of a truncated answer is useful: it estimates, roughly and imperfectly, the size of missing higher-order logarithms.

## Setup and conventions

Take a renormalized scalar theory with

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
m_0^2=Z_{m^2}m^2,
\qquad
\lambda_0=\mu^{2\epsilon}Z_\lambda\lambda,
$$

in dimensional regularization with

$$
d=4-2\epsilon.
$$

The bare quantities $\phi_0$, $m_0^2$, and $\lambda_0$ do not depend on the arbitrary scale $\mu$ when the bare theory is held fixed. The renormalized parameters do depend on $\mu$:

$$
\beta_\lambda
=\mu\frac{d\lambda}{d\mu}\bigg|_{\lambda_0,m_0^2},
\qquad
\beta_{m^2}
=\mu\frac{dm^2}{d\mu}\bigg|_{\lambda_0,m_0^2}.
$$

The field anomalous dimension is defined here by

$$
\gamma_\phi
=\frac12\mu\frac{d\ln Z_\phi}{d\mu}\bigg|_{\lambda_0,m_0^2}.
$$

This convention is paired with the 1PI equation

$$
\left[
\mu\partial_\mu
+\beta_\lambda\partial_\lambda
+\beta_{m^2}\partial_{m^2}
-n\gamma_\phi
\right]
\Gamma_R^{(n)}=0.
$$

Some books define $\gamma_\phi$ with the opposite sign. Always check the definition before comparing formulas.

## Derivation from bare-scale independence

Let $\Gamma_0^{(n)}$ be a bare 1PI vertex function and $\Gamma_R^{(n)}$ the corresponding renormalized vertex function. Since

$$
\phi_0=Z_\phi^{1/2}\phi,
$$

functional derivatives with respect to the renormalized field bring factors of $Z_\phi^{1/2}$. Thus

$$
\Gamma_R^{(n)}
=
Z_\phi^{n/2}\Gamma_0^{(n)}.
$$

Equivalently,

$$
\Gamma_0^{(n)}
=
Z_\phi^{-n/2}\Gamma_R^{(n)}.
$$

Now differentiate this equation with respect to $\mu$ while holding bare quantities fixed:

$$
0=
\mu\frac{d}{d\mu}\left[Z_\phi^{-n/2}\Gamma_R^{(n)}\right]_{\rm bare}.
$$

The derivative acts on explicit $\mu$ dependence, on $\lambda(\mu)$, on $m^2(\mu)$, and on $Z_\phi$. Using the definition of $\gamma_\phi$ gives

$$
\left[
\mu\partial_\mu
+\beta_\lambda\partial_\lambda
+\beta_{m^2}\partial_{m^2}
-n\gamma_\phi
\right]
\Gamma_R^{(n)}=0.
$$

For connected Green functions $G_R^{(n)}$, the field-renormalization relation is instead

$$
G_0^{(n)}=Z_\phi^{n/2}G_R^{(n)},
$$

so the corresponding equation is

$$
\left[
\mu\partial_\mu
+\beta_\lambda\partial_\lambda
+\beta_{m^2}\partial_{m^2}
+n\gamma_\phi
\right]
G_R^{(n)}=0.
$$

That sign difference is a common source of confusion.

## Running coupling example

In four-dimensional $\phi^4$ theory, the one-loop beta function in qft.org's conventions is

$$
\beta_\lambda
=
\mu\frac{d\lambda}{d\mu}
=
\frac{3\lambda^2}{16\pi^2}+O(\lambda^3).
$$

Keeping only this leading term, define

$$
b=\frac{3}{16\pi^2}.
$$

Then

$$
\frac{d\lambda}{d\ln\mu}=b\lambda^2.
$$

Separate variables:

$$
\frac{d\lambda}{\lambda^2}=b\,d\ln\mu.
$$

Integrating from $\mu_0$ to $\mu$ gives

$$
-\frac{1}{\lambda(\mu)}+
\frac{1}{\lambda(\mu_0)}
=
b\ln\frac{\mu}{\mu_0},
$$

or

$$
\frac{1}{\lambda(\mu)}
=
\frac{1}{\lambda(\mu_0)}
-
\frac{3}{16\pi^2}\ln\frac{\mu}{\mu_0}
+O(\lambda^0).
$$

This formula should not be extrapolated recklessly to arbitrarily high scales. It is a one-loop perturbative solution. Its real use here is to show how the same renormalized theory is described by different coupling values at different subtraction scales.

## Leading logarithm check

A massless amplitude often contains logarithms of the form

$$
L=\ln\frac{-s-i\epsilon}{\mu^2}.
$$

Suppose, schematically, that a four-point amplitude is

$$
\mathcal M(s,
\mu)
=
-\lambda(\mu)
-\frac{b}{2}\lambda^2(\mu)L
+O(\lambda^3),
$$

where $b$ is the one-loop coefficient in

$$
\beta_\lambda=b\lambda^2+O(\lambda^3).
$$

Act with the amplitude version of the RG operator at this order:

$$
\left(\mu\partial_\mu+
\beta_\lambda\partial_\lambda\right)
\mathcal M.
$$

The explicit scale derivative gives

$$
\mu\partial_\mu\mathcal M
=
-b\lambda^2\frac12\mu\partial_\mu L
=
-b\lambda^2\frac12(-2)
=
b\lambda^2,
$$

while the running of the tree term gives

$$
\beta_\lambda\partial_\lambda(-\lambda)
=
-b\lambda^2.
$$

The terms cancel through order $\lambda^2$:

$$
\left(\mu\partial_\mu+
\beta_\lambda\partial_\lambda\right)
\mathcal M
=O(\lambda^3).
$$

This is the simplest perturbative meaning of the Callan–Symanzik equation: the coefficient of a one-loop logarithm is tied to the one-loop beta function.

:::note[Why this was schematic]
Real amplitudes may contain several invariants, masses, spins, color factors, infrared logarithms, and external anomalous dimensions. The cancellation pattern survives, but the equation becomes vector-valued in couplings and matrix-valued in operator bases.
:::

## Method of characteristics

The Callan–Symanzik equation is a first-order differential equation. It can be solved by following the running parameters along RG trajectories.

Define running quantities by

$$
\frac{d\bar\lambda}{d\ln\bar\mu}=\beta_\lambda(\bar\lambda),
\qquad
\frac{d\bar m^2}{d\ln\bar\mu}=\beta_{m^2}(\bar m^2,\bar\lambda),
$$

with boundary conditions

$$
\bar\lambda(\mu)=\lambda,
\qquad
\bar m^2(\mu)=m^2.
$$

For the 1PI vertex equation used here, the formal solution is

$$
\Gamma_R^{(n)}(p_i;m^2,\lambda,
\mu)
=
\exp\left[-n\int_{\mu}^{Q}d\ln\bar\mu\,\gamma_\phi(\bar\mu)\right]
\Gamma_R^{(n)}(p_i;\bar m^2(Q),\bar\lambda(Q),Q).
$$

The scale $Q$ is arbitrary. A useful choice is a physical scale in the problem, such as

$$
Q^2\sim |s|,
\qquad
Q\sim m,
\qquad
Q\sim |\mathbf p|,
$$

depending on the kinematics. Choosing $Q$ near the characteristic scale makes logarithms small in the remaining perturbative expansion. This is called **RG improvement**.

## Fixed points and anomalous scaling

A fixed point is a point in coupling space where

$$
\beta_i(g_*)=0.
$$

At a fixed point, the Callan–Symanzik equation becomes a scaling equation. In a massless scalar theory at a fixed point, the connected two-point function scales as

$$
G_R^{(2)}(x)
\sim
\frac{1}{|x|^{2\Delta_\phi}},
$$

where

$$
\Delta_\phi
=
\frac{d-2}{2}+\gamma_\phi^*.
$$

Here $\gamma_\phi^*$ is the anomalous dimension evaluated at the fixed point. The engineering dimension $(d-2)/2$ is corrected by interactions.

This is one of the reasons the Callan–Symanzik equation belongs conceptually to the renormalization-group story, not merely to the bookkeeping of ultraviolet divergences. It explains both running away from fixed points and scaling at fixed points.

## Amplitudes versus Green functions

For off-shell Green functions and 1PI vertices, anomalous dimensions appear explicitly because the elementary field normalization is arbitrary and scheme-dependent.

Physical scattering amplitudes between stable asymptotic particles are different. LSZ residue factors convert field-normalized Green functions into state-normalized matrix elements. In a massive theory without infrared subtleties, a physical amplitude expressed in terms of physical input parameters obeys a scale-independence statement of the form

$$
\left[
\mu\partial_\mu+
\sum_i\beta_i\partial_{g_i}
+\sum_a\beta_{m_a}\partial_{m_a}
\right]
\mathcal M_{\rm phys}=0,
$$

with no separate external $n\gamma_\phi$ term after the LSZ normalization has been included.

In massless gauge theories, the story is subtler. Exclusive amplitudes can have infrared divergences, and the useful RG equations often act on hard functions, jet functions, soft functions, PDFs, or infrared-safe observables rather than on a naive $S$-matrix element.

## What this preview does not cover

This page deliberately avoids several important generalizations:

| Topic | What changes |
|---|---|
| several couplings | $\beta_i$ becomes a vector field on coupling space |
| operator insertions | anomalous dimensions become matrices |
| gauge theories | Ward or Slavnov–Taylor identities constrain renormalization constants |
| EFTs | irrelevant operators run and mix under renormalization |
| mass thresholds | beta functions change across effective descriptions |
| infrared factorization | hard, soft, and collinear functions obey coupled RG equations |
| CFT | fixed-point data replace perturbative running as the primary language |

Those are not exceptions to the Callan–Symanzik idea. They are what the idea grows into.

## Common pitfalls

**Thinking $\mu$ is a physical cutoff.** In dimensional regularization and minimal subtraction, $\mu$ is a renormalization scale, not a literal maximum momentum.

**Holding the wrong quantities fixed.** Beta functions are defined by changing $\mu$ while holding bare parameters fixed. Holding renormalized parameters fixed gives only explicit scale dependence, not the RG flow.

**Mixing sign conventions for $\gamma_\phi$.** Different books define anomalous dimensions with different signs. Also, connected Green functions and 1PI vertices carry opposite field-factor signs.

**Forgetting masses.** In a massive theory, the CS equation contains mass-running terms. Dropping them is justified only in a massless theory, a high-energy approximation, or a special scheme and limit.

**Calling every logarithm an ultraviolet logarithm.** Some logarithms are ultraviolet and governed by renormalization. Others are infrared, threshold, or collinear logarithms. Their RG equations may involve different functions.

**Overusing one-loop running.** A one-loop beta function is a local perturbative statement in coupling space. It should not be blindly extrapolated beyond weak coupling.

## Relations to other pages

- [Minimal Subtraction](/perturbative-qft/renormalized-perturbation-theory/minimal-subtraction/) explains how pole coefficients lead to beta functions.
- [Coupling Renormalization](/perturbative-qft/renormalized-perturbation-theory/coupling-renormalization/) derives the one-loop $\phi^4$ beta function used here.
- [Wavefunction Renormalization](/perturbative-qft/renormalized-perturbation-theory/wavefunction-renormalization/) defines $Z_\phi$ and motivates anomalous dimensions.
- [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/) explains how scale dependence appears in finite amplitudes.
- [One-Loop Bubble Integrals](/perturbative-qft/loop-expansion-regularization/one-loop-bubble-integrals/) shows where logarithms such as $\ln(P^2/\mu^2)$ arise.
- [Inclusive Observables](/perturbative-qft/phase-space-cross-sections-decays/inclusive-observables/) and later infrared pages explain why massless observable RG equations require more structure.

## Research status

- **Established:** The Callan–Symanzik equation is a standard consequence of bare-scale independence and field renormalization.
- **Convention-dependent:** Signs of anomalous dimensions and the placement of field-renormalization factors depend on definitions of $Z_\phi$, connected functions, and 1PI vertices.
- **Active:** Modern applications involve multi-scale processes, operator mixing, conformal data, effective field theory matching, factorization, gauge-theory identities, and nonperturbative RG methods.
- **Preview:** This page is intentionally perturbative and scalar-theory-oriented. The conceptual home for the full RG story is the Renormalization, RG, and EFT volume.

## Exercises

### Exercise 1: Derive the sign of the anomalous-dimension term for 1PI vertices

Assume

$$
\Gamma_R^{(n)}=Z_\phi^{n/2}\Gamma_0^{(n)}
$$

and

$$
\gamma_\phi=\frac12\mu\frac{d\ln Z_\phi}{d\mu}\bigg|_{\rm bare}.
$$

Show that the Callan–Symanzik equation for $\Gamma_R^{(n)}$ contains $-n\gamma_\phi$.

<details>
<summary><strong>Solution</strong></summary>

Rewrite the relation as

$$
\Gamma_0^{(n)}=Z_\phi^{-n/2}\Gamma_R^{(n)}.
$$

The bare vertex is independent of $\mu$ at fixed bare parameters:

$$
0=
\mu\frac{d}{d\mu}\left(Z_\phi^{-n/2}\Gamma_R^{(n)}\right)_{\rm bare}.
$$

Using

$$
\mu\frac{d}{d\mu}Z_\phi^{-n/2}
=
-n\gamma_\phi Z_\phi^{-n/2},
$$

we find

$$
0=Z_\phi^{-n/2}
\left[
\mu\frac{d}{d\mu}\Gamma_R^{(n)}
-n\gamma_\phi\Gamma_R^{(n)}
\right].
$$

Expanding the total derivative of $\Gamma_R^{(n)}$ into explicit $\mu$ dependence plus running of $\lambda$ and $m^2$ gives

$$
\left[
\mu\partial_\mu
+\beta_\lambda\partial_\lambda
+\beta_{m^2}\partial_{m^2}
-n\gamma_\phi
\right]
\Gamma_R^{(n)}=0.
$$

</details>

### Exercise 2: Connected functions have the opposite sign

Starting from

$$
G_0^{(n)}=Z_\phi^{n/2}G_R^{(n)},
$$

show that the connected Green-function equation contains $+n\gamma_\phi$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate at fixed bare parameters:

$$
0=\mu\frac{d}{d\mu}
\left(Z_\phi^{n/2}G_R^{(n)}\right)_{\rm bare}.
$$

Since

$$
\mu\frac{d}{d\mu}Z_\phi^{n/2}
=n\gamma_\phi Z_\phi^{n/2},
$$

we get

$$
0=Z_\phi^{n/2}
\left[
\mu\frac{d}{d\mu}G_R^{(n)}
+n\gamma_\phi G_R^{(n)}
\right].
$$

Expanding the total derivative gives

$$
\left[
\mu\partial_\mu
+\beta_\lambda\partial_\lambda
+\beta_{m^2}\partial_{m^2}
+n\gamma_\phi
\right]G_R^{(n)}=0.
$$

</details>

### Exercise 3: One-loop running in φ⁴ theory

Solve

$$
\frac{d\lambda}{d\ln\mu}=b\lambda^2
$$

with boundary condition $\lambda(\mu_0)=\lambda_{\mu_0}$.

<details>
<summary><strong>Solution</strong></summary>

Separate variables:

$$
\frac{d\lambda}{\lambda^2}=b\,d\ln\mu.
$$

Integrate:

$$
\int_{\lambda_{\mu_0}}^{\lambda(\mu)}\frac{d\lambda}{\lambda^2}
=b\int_{\mu_0}^{\mu}d\ln\mu'.
$$

Thus

$$
-\frac{1}{\lambda(\mu)}+\frac{1}{\lambda_{\mu_0}}
=b\ln\frac{\mu}{\mu_0}.
$$

So

$$
\lambda(\mu)
=
\frac{\lambda_{\mu_0}}{1-b\lambda_{\mu_0}\ln(\mu/\mu_0)}.
$$

For $b>0$, the one-loop solution grows with $\mu$ until perturbation theory fails.

</details>

### Exercise 4: Leading-log cancellation

Let

$$
\mathcal M=-\lambda-\frac{b}{2}\lambda^2L+O(\lambda^3),
\qquad
L=\ln\frac{-s-i\epsilon}{\mu^2},
$$

and

$$
\beta_\lambda=b\lambda^2+O(\lambda^3).
$$

Show that

$$
(\mu\partial_\mu+\beta_\lambda\partial_\lambda)\mathcal M=O(\lambda^3).
$$

<details>
<summary><strong>Solution</strong></summary>

First,

$$
\mu\partial_\mu L=-2.
$$

Therefore

$$
\mu\partial_\mu\mathcal M
=-\frac{b}{2}\lambda^2(-2)+O(\lambda^3)
=b\lambda^2+O(\lambda^3).
$$

Next,

$$
\partial_\lambda\mathcal M=-1+O(\lambda),
$$

so

$$
\beta_\lambda\partial_\lambda\mathcal M
=b\lambda^2(-1)+O(\lambda^3)
=-b\lambda^2+O(\lambda^3).
$$

Adding both contributions gives

$$
(\mu\partial_\mu+\beta_\lambda\partial_\lambda)\mathcal M
=O(\lambda^3).
$$

</details>

### Exercise 5: Fixed-point scaling dimension

At a fixed point, suppose a scalar field has anomalous dimension $\gamma_\phi^*$. What is its scaling dimension in $d$ spacetime dimensions?

<details>
<summary><strong>Solution</strong></summary>

The engineering dimension of a scalar field in $d$ dimensions is

$$
\Delta_{\phi,{\rm eng}}=\frac{d-2}{2}.
$$

At an interacting fixed point, the anomalous dimension shifts this value:

$$
\Delta_\phi
=\frac{d-2}{2}+\gamma_\phi^*.
$$

A two-point function then scales as

$$
G^{(2)}(x)\sim \frac{1}{|x|^{2\Delta_\phi}}.
$$

</details>

## References

- C. G. Callan, “Broken Scale Invariance in Scalar Field Theory,” *Physical Review D* **2** (1970), 1541–1547.
- K. Symanzik, “Small Distance Behavior in Field Theory and Power Counting,” *Communications in Mathematical Physics* **18** (1970), 227–246.
- M. Srednicki, *Quantum Field Theory*, §§27–29, for renormalization schemes, beta functions, and RG equations in a calculation-first sequence.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 50, for a direct lecture-style treatment of the renormalization group equation.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 12 and Vol. II, ch. 18, for renormalization and RG methods in a general QFT framework.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, ch. 23, for running couplings and RG equations in perturbative applications.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 9–10, for the field-theoretic RG and minimal-subtraction structure.

## Version history

- **2026-06-13:** Initial polished draft. Added Callan–Symanzik convention lock, derivation from bare-scale independence, connected-versus-1PI sign comparison, one-loop running example, leading-log cancellation, fixed-point preview, solved exercises, and a compact scale-dependence map figure.
