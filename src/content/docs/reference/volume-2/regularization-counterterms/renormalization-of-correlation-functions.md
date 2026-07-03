---
title: "Renormalization of Correlation Functions"
description: "How field, parameter, source, and counterterm renormalization make Green functions finite and scheme-defined at separated points."
sidebar:
  label: "Renormalized Correlators"
  order: 7
level: Graduate
status: "Polished draft"
source: "Coleman, renormalization lectures; Srednicki §§13–29; Schwartz chs. 18–23; Weinberg Vol. I ch. 12 and Vol. II ch. 18; Zinn-Justin, renormalization chapters."
topics:
  - renormalized correlation functions
  - field renormalization
  - Green functions
  - 1PI functions
  - Callan–Symanzik equation
canonicalTopics:
  - renormalized-green-functions
  - field-renormalization
  - connected-correlation-functions
  - one-particle-irreducible-functions
researchStatus:
  established:
    - "Renormalized correlation functions are standard scheme-defined objects obtained by expressing bare Green functions in terms of renormalized fields, parameters, and counterterms."
  active:
    - "Subtleties remain important for gauge-dependent correlators, unstable particles, composite operators, contact terms, curved backgrounds, real-time systems, and nonperturbative definitions."
---

## Summary

A **renormalized correlation function** is a Green function written in terms of renormalized fields and renormalized parameters, with counterterms chosen so that the result is finite and scheme-defined.

For a scalar field with

$$
\phi_0=Z_\phi^{1/2}\phi,
$$

the basic relation for separated-point $n$-point functions is

$$
G_R^{(n)}(x_1,\ldots,x_n)
=Z_\phi^{-n/2}G_0^{(n)}(x_1,\ldots,x_n),
$$

where the bare parameters inside $G_0^{(n)}$ are expressed in terms of the renormalized parameters, the regulator, and the scheme. Equivalently,

$$
G_0^{(n)}=Z_\phi^{n/2}G_R^{(n)}.
$$

This formula is compact, but it hides the main conceptual point. Correlators are not renormalized by sprinkling magic factors of $Z_\phi$ onto divergent integrals. They are renormalized by defining the entire regulated theory in terms of local counterterms and renormalized parameters. Field-strength renormalization then fixes the normalization of the interpolating field used in the correlator.

The physically important slogan is

$$
\text{renormalized correlators are finite coordinates on observable content, not observables by themselves.}
$$

Elementary field correlators depend on field normalization, gauge choice if gauge fields are involved, and renormalization scheme. Scattering amplitudes, critical exponents, spectral densities in physical channels, and other properly defined observables are extracted from them after additional work.

## Prerequisites

You should know [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), [Bare versus Renormalized](/renormalization-rg-eft/why-renormalization/bare-versus-renormalized/), [Regulator Dependence](/renormalization-rg-eft/why-renormalization/regulator-dependence/), and [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/). The conventions are those of [Conventions and Notation](/renormalization-rg-eft/conventions/): mostly-minus metric, natural units, $d=4-2\epsilon$ in dimensional regularization, and

$$
\gamma_\phi\equiv \frac12\left.\mu\frac{d\log Z_\phi}{d\mu}\right|_{\text{bare}}.
$$

This page discusses ordinary correlation functions of elementary fields. Correlators containing local composite operators require additional renormalization and are treated in [Composite-Operator Renormalization Preview](/renormalization-rg-eft/regularization-counterterms/composite-operator-renormalization-preview/).

## Core idea

A correlation function asks: if fields are inserted at spacetime points $x_1,\ldots,x_n$, what does the quantum theory assign to their product?

For a bare regulated scalar theory,

$$
G_0^{(n)}(x_1,\ldots,x_n)
=\langle 0|T\{\phi_0(x_1)\cdots\phi_0(x_n)\}|0\rangle_0.
$$

The subscript $0$ reminds us that the expectation value is computed using the bare regulated action. Loop diagrams contributing to this object can be UV divergent. The counterterm program removes those divergences by rewriting the bare action as

$$
\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}},
$$

with bare parameters held fixed while renormalized parameters depend on the scheme and scale. Field-strength renormalization then relates the bare field $\phi_0$ to the renormalized field $\phi$.

The finite object is not usually $G_0^{(n)}$ itself. It is

$$
G_R^{(n)}=Z_\phi^{-n/2}G_0^{(n)}
$$

after the bare parameters have been expressed in terms of renormalized ones. In perturbation theory this operation appears as a combination of ordinary loop graphs, counterterm graphs, and external field-normalization factors.

Why is this enough? Because UV divergences in ordinary elementary-field correlators are local. They can be absorbed into local terms in the action and into a local rescaling of the field. Once that is done, separated-point correlators have a regulator-independent limit order by order.

:::note[Separated points first]
This page primarily discusses correlators at distinct spacetime points. Coincident limits are more singular. Products such as $\phi^2(x)$, $\phi^4(x)$, currents, and stress tensors are composite operators, not automatic byproducts of ordinary field renormalization.
:::

## Setup and conventions

Consider a scalar theory with a source coupled to the bare field:

$$
Z_0[J_0]
=\int\mathcal D\phi_0\,
\exp\left\{iS_0[\phi_0]+i\int d^d x\,J_0(x)\phi_0(x)\right\}.
$$

With

$$
\phi_0=Z_\phi^{1/2}\phi,
$$

it is natural to define the renormalized source by

$$
J=Z_\phi^{1/2}J_0,
$$

so that

$$
\int d^d x\,J_0\phi_0=\int d^d x\,J\phi.
$$

The connected generating functional is

$$
W[J]=-i\log Z[J]
$$

in Lorentzian conventions. Connected correlators are obtained by functional differentiation with respect to the renormalized source $J$.

The relation between bare and renormalized fields gives

$$
\frac{\delta}{\delta J(x)}
=Z_\phi^{-1/2}\frac{\delta}{\delta J_0(x)}.
$$

Therefore every external elementary-field insertion contributes a factor $Z_\phi^{-1/2}$ to the renormalized Green function:

$$
G_R^{(n)}(x_1,\ldots,x_n)
=Z_\phi^{-n/2}G_0^{(n)}(x_1,\ldots,x_n).
$$

This is a definition of field normalization, not an independent dynamical law. The dynamics enters through the counterterms and the relation between bare and renormalized parameters.

## Bare and renormalized Green functions

Let the bare action depend on bare parameters $g_0^i$ and the regulator. The same theory can be coordinatized by renormalized parameters $g^i(\mu)$ through relations of the form

$$
g_0^i=\mu^{d_i\epsilon}Z^i(g,\epsilon)g^i(\mu),
$$

where the power of $\mu$ is fixed by dimensional analysis. For example, in four-dimensional $\phi^4$ theory continued to $d=4-2\epsilon$,

$$
\lambda_0=\mu^{2\epsilon}Z_\lambda\lambda(\mu).
$$

The renormalized $n$-point function is then more explicitly

$$
G_R^{(n)}(x_1,\ldots,x_n;g(\mu),\mu)
=Z_\phi^{-n/2}(g,\epsilon)
G_0^{(n)}(x_1,\ldots,x_n;g_0,\epsilon).
$$

The right side is computed with the regulator in place. The left side is finite after the regulator is removed, order by order, if the theory is renormalized in the chosen sense.

In momentum space, translational invariance gives

$$
\widetilde G_R^{(n)}(p_1,\ldots,p_n)
=(2\pi)^d\delta^{(d)}\!\left(\sum_{a=1}^n p_a\right)
G_R^{(n)}(p_1,\ldots,p_{n-1}),
$$

where the delta function is often stripped off. The same field-strength relation holds for the stripped functions.

The phrase "finite Green function" usually means finite after this overall momentum-conservation delta function has been removed and after ordinary infrared issues have been handled. UV renormalization does not by itself solve infrared divergences.

## Field-strength renormalization

The field-strength factor $Z_\phi$ is often introduced through the kinetic term:

$$
\mathcal L_0
=\frac12 Z_\phi\partial_\mu\phi\,\partial^\mu\phi
-\frac12 Z_{m^2}m^2\phi^2
-\frac{\mu^{2\epsilon}Z_\lambda\lambda}{4!}\phi^4+\cdots.
$$

Equivalently,

$$
\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}},
$$

with

$$
\mathcal L_{\text{ct}}
\supset
\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi.
$$

This counterterm cancels the divergent part of the coefficient of $p^2$ in the two-point 1PI function. In a theory where the one-loop self-energy is momentum independent, such as $\phi^4$ theory in four dimensions at one loop, $\delta Z$ can vanish at that order. In theories with momentum-dependent self-energies at one loop, such as Yukawa theory or QED, field-strength renormalization is needed immediately.

Field-strength renormalization has two related meanings:

| Meaning | What it controls |
|---|---|
| Counterterm meaning | cancellation of divergent $p^2$ dependence in the inverse propagator |
| Normalization meaning | relation between the field used in correlators and the residue of a propagating pole |

These meanings coincide in simple perturbative examples but should not be confused. In an on-shell scheme for a stable particle, one may choose $Z_\phi$ so that the exact propagator has residue one at the pole. In a minimal-subtraction scheme, $Z_\phi$ cancels pole parts and the pole residue is a derived finite quantity.

## Connected and 1PI functions

The full Green functions $G^{(n)}$ contain connected and disconnected pieces. Connected correlators are generated by $W[J]$. For elementary fields, the same external factor applies:

$$
G_{R,c}^{(n)}=Z_\phi^{-n/2}G_{0,c}^{(n)}.
$$

The one-particle-irreducible effective action $\Gamma[\varphi]$ is the Legendre transform of $W[J]$. If

$$
\varphi_0=Z_\phi^{1/2}\varphi,
$$

then

$$
\Gamma_R[\varphi]=\Gamma_0[Z_\phi^{1/2}\varphi]
$$

up to the same rewriting of bare parameters in terms of renormalized ones. Taking $n$ functional derivatives gives

$$
\Gamma_R^{(n)}=Z_\phi^{n/2}\Gamma_0^{(n)}.
$$

This is the inverse relation to the one for connected Green functions. The reason is simple: connected functions are derivatives with respect to sources, while 1PI functions are derivatives with respect to classical fields.

For the two-point function, the relation between the connected propagator and the 1PI inverse propagator is schematically

$$
G_R^{(2)}(p)=\frac{i}{\Gamma_R^{(2)}(p)+i\epsilon},
$$

with sign conventions depending on whether one includes factors of $i$ in $\Gamma^{(2)}$. What matters structurally is that the 1PI two-point function is the inverse kernel of the connected two-point function.

## Renormalization conditions on correlators

Counterterms are fixed by a scheme. Many schemes can be expressed as conditions on renormalized correlation functions.

In an on-shell scheme for a stable scalar particle, one may impose

$$
\Gamma_R^{(2)}(p^2=m_{\text{phys}}^2)=0,
$$

and

$$
\left.\frac{d\Gamma_R^{(2)}}{dp^2}\right|_{p^2=m_{\text{phys}}^2}=1.
$$

The first condition fixes the pole location. The second fixes the pole residue. A coupling can be fixed by a condition on a four-point function at specified external momenta, for example

$$
\Gamma_R^{(4)}(p_i)\big|_{\text{subtraction point}}=-\lambda.
$$

In a Euclidean momentum-subtraction scheme, the subtraction point is often chosen away from physical thresholds, such as a symmetric point with

$$
p_i^2=\kappa^2,
\qquad
p_i\cdot p_j=-\frac{\kappa^2}{3}\quad(i\ne j)
$$

for a four-point function with $\sum_i p_i=0$.

In MS or $\overline{\mathrm{MS}}$, by contrast, the conditions are not physical momentum conditions. The scheme subtracts pole parts in $\epsilon$, or the combination $1/\bar\epsilon$, and leaves finite parts determined by that convention. The renormalized parameters $m(\mu)$ and $\lambda(\mu)$ are then not directly equal to pole masses or scattering amplitudes without a conversion calculation.

The practical difference is this:

| Scheme type | How correlators are normalized |
|---|---|
| On-shell | by pole positions, residues, and physical amplitudes |
| Momentum subtraction | by values of Green functions at chosen off-shell momenta |
| MS/$\overline{\mathrm{MS}}$ | by subtracting only specified pole parts in dimensional regularization |

All three are legitimate if used consistently. They are different coordinate systems on the same theory space.

## Separated points and contact terms

For ordinary elementary-field correlators, renormalization usually guarantees finiteness at separated insertion points:

$$
x_i\ne x_j\quad\text{for }i\ne j.
$$

Coincident limits are a different story. Even in a free theory,

$$
\langle \phi(x)\phi(y)\rangle
$$

is singular as $x\to y$. The singularity is not a failure of the free theory. It reflects the fact that quantum fields are distributions, so products of fields at the same point require definition.

This matters because functional derivatives of correlators, Ward identities, and composite observables often generate contact terms. For example, differentiating a correlator with respect to a mass parameter formally inserts

$$
\int d^d x\,\phi^2(x),
$$

but $\phi^2(x)$ is not automatically a finite operator. Similarly, differentiating with respect to the metric inserts the stress tensor, whose definition includes improvement terms and contact terms.

The clean separation is:

| Object | Renormalization needed |
|---|---|
| elementary-field correlator at separated points | field, mass, coupling, and vacuum counterterms |
| product of fields at the same point | composite-operator renormalization |
| correlator with collisions among insertion points | contact-term counterterms and OPE data |
| integrated insertion | both operator renormalization and possible boundary/contact care |

This is why the next page treats composite operators separately. The page you are reading gets the ordinary Green functions finite; it does not define every local observable in the theory.

## Callan–Symanzik equation from fixed bare correlators

The renormalization group equation follows from a simple fact: the bare correlation function does not know about the arbitrary scale $\mu$ once the bare parameters are held fixed.

Start from

$$
G_0^{(n)}=Z_\phi^{n/2}G_R^{(n)}.
$$

Differentiate at fixed bare parameters:

$$
0=
\left.\mu\frac{d}{d\mu}G_0^{(n)}\right|_{\text{bare}}.
$$

Using

$$
\gamma_\phi=\frac12\left.\mu\frac{d\log Z_\phi}{d\mu}\right|_{\text{bare}},
$$

and defining beta functions by

$$
\beta^i(g)=\left.\mu\frac{dg^i}{d\mu}\right|_{\text{bare}},
$$

one obtains the homogeneous form

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+n\gamma_\phi
\right)G_R^{(n)}=0,
$$

for a massless theory away from contact terms. With masses, include their running:

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+\beta_{m^2}\frac{\partial}{\partial m^2}
+n\gamma_\phi
\right)G_R^{(n)}=0.
$$

This equation does not say the correlator is independent of physical momentum. It says that explicit $\mu$ dependence is compensated by implicit $\mu$ dependence of renormalized parameters and fields.

In a fixed-order calculation, this compensation is only true up to neglected higher-order terms. That is why residual $\mu$ dependence is often used as a diagnostic of perturbative uncertainty.

## Example: the scalar two-point function

For a scalar field, write the renormalized 1PI two-point function schematically as

$$
\Gamma_R^{(2)}(p^2)
=p^2-m^2-\Pi_R(p^2),
$$

where $\Pi_R$ is the renormalized self-energy in the chosen convention. The connected two-point function has the form

$$
G_R^{(2)}(p)
=\frac{i}{p^2-m^2-\Pi_R(p^2)+i\epsilon}.
$$

A loop calculation may produce divergent pieces of the form

$$
\Pi_{\text{loop}}(p^2)
=A_{\text{div}}+B_{\text{div}}p^2+\Pi_{\text{finite}}(p^2).
$$

The local counterterms contribute

$$
\Pi_{\text{ct}}(p^2)
=-\delta m^2+\delta Z\,p^2,
$$

up to sign conventions for the definition of $\Pi$. Choosing $\delta m^2$ and $\delta Z$ cancels $A_{\text{div}}$ and $B_{\text{div}}$.

The finite part can then be fixed in different ways. An on-shell scheme chooses it so that the pole and residue have specified physical meanings. A minimal-subtraction scheme chooses it by the pole-subtraction rule. A momentum-subtraction scheme chooses it by the value of $\Gamma_R^{(2)}$ and its derivative at an off-shell subtraction point.

The pole of the propagator, when it is isolated and stable, is physical. The off-shell shape of $G_R^{(2)}(p)$ is generally scheme and field-definition dependent.

## What is and is not physical

Correlation functions are central to QFT, but not every correlator is directly observable.

A few guideposts:

| Quantity | Status |
|---|---|
| pole mass of a stable particle | physical, under suitable assumptions |
| pole residue of a chosen elementary field | field-normalization dependent unless tied to an external-state convention |
| off-shell Green function | scheme and field-definition dependent |
| S-matrix element | physical in theories with suitable asymptotic states |
| critical exponent | physical and scheme independent |
| anomalous dimension of an elementary gauge field | often gauge and scheme dependent |
| anomalous dimension of a gauge-invariant scaling operator at a fixed point | physical when the operator is properly identified |

This is not a demotion of Green functions. Green functions are the workbench. They encode poles, cuts, OPEs, Ward identities, spectral densities, response functions, and amplitudes. But one must ask how the chosen Green function is tied to an observable or a universal quantity.

The most common beginner mistake is to treat the renormalized field $\phi$ as if it were uniquely defined by nature. It is not. Fields are coordinates used to describe local excitations and operators. Changing coordinates can change off-shell correlators while leaving physical observables unchanged.

## Common pitfalls

**Thinking $Z_\phi$ makes every local product finite.** It does not. $Z_\phi$ renormalizes external elementary-field insertions. Operators such as $\phi^2$, $\phi^4$, currents, and stress tensors require their own definitions.

**Forgetting that 1PI functions scale oppositely from connected functions.** Connected $n$-point functions carry $Z_\phi^{-n/2}$; 1PI $n$-point functions carry $Z_\phi^{n/2}$.

**Confusing a renormalization condition with a measurement.** A condition such as $\Gamma_R^{(4)}=-\lambda$ at a subtraction point defines $\lambda$ in a scheme. It becomes connected to experiment only after matching to a measured observable.

**Treating $\mu$ as a physical knob.** The renormalization scale is a bookkeeping scale. Physical predictions do not depend on it when computed exactly and expressed in terms of physical inputs.

**Ignoring contact terms.** Ward identities, composite insertions, and coincident-point limits often differ by contact terms. Dropping them blindly can break symmetries or produce wrong operator equations.

**Assuming off-shell Green functions are invariant.** Field redefinitions and scheme changes can alter off-shell correlators. The invariant content is extracted through poles, cuts, physical matrix elements, RG invariants, and universal data.

## Relations to other pages

[Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/) explains the local terms that cancel UV dependence. This page explains how those counterterms make ordinary Green functions finite. [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/) explains why a finite set of such counterterms suffices in familiar renormalizable theories.

The next page, [Composite-Operator Renormalization Preview](/renormalization-rg-eft/regularization-counterterms/composite-operator-renormalization-preview/), explains why local operator insertions need additional counterterms. Later chapters use renormalized Green functions to build the [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/), [Renormalization Conditions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalization-conditions/), [Callan–Symanzik Equation](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/), and [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/).

In the Perturbative QFT and Scattering volume, the same objects appear as connected correlators, amputated functions, LSZ residues, and renormalized amplitudes. In the CFT and Bootstrap volume, renormalized local operators and their correlators become the primary data of a fixed-point theory.

## Research status

The perturbative renormalization of ordinary correlation functions in local QFT is established textbook material. The main conceptual points on this page are stable: fields require normalization, parameters require renormalization, connected and 1PI functions have inverse $Z$ factors, and RG equations follow from fixed bare quantities.

The subtle and active directions are not about whether this framework works in ordinary examples. They concern how best to define and compute Green functions in gauge theories, real-time finite-density systems, theories without particle states, curved spacetime, nonperturbative lattice-to-continuum limits, and theories with large operator bases. In those settings, one must be especially careful about gauge dependence, contact terms, sources, Ward identities, analytic continuation, and what counts as an observable.

## Exercises

### Exercise 1: Connected versus 1PI field factors

Assume $\phi_0=Z_\phi^{1/2}\phi$ and $J=Z_\phi^{1/2}J_0$. Show that connected $n$-point functions satisfy $G_{R,c}^{(n)}=Z_\phi^{-n/2}G_{0,c}^{(n)}$, while 1PI functions satisfy $\Gamma_R^{(n)}=Z_\phi^{n/2}\Gamma_0^{(n)}$.

<details><summary><strong>Solution</strong></summary>

Connected correlators are derivatives with respect to the source. Since

$$
J=Z_\phi^{1/2}J_0,
$$

we have

$$
\frac{\delta}{\delta J}=Z_\phi^{-1/2}\frac{\delta}{\delta J_0}.
$$

Taking $n$ derivatives gives

$$
G_{R,c}^{(n)}=Z_\phi^{-n/2}G_{0,c}^{(n)}.
$$

For 1PI functions, use the classical field. Since

$$
\varphi_0=\frac{\delta W}{\delta J_0}=Z_\phi^{1/2}\varphi,
$$

we may write

$$
\Gamma_R[\varphi]=\Gamma_0[Z_\phi^{1/2}\varphi].
$$

Each derivative with respect to $\varphi$ brings a factor $Z_\phi^{1/2}$, so

$$
\Gamma_R^{(n)}=Z_\phi^{n/2}\Gamma_0^{(n)}.
$$

</details>

### Exercise 2: Callan–Symanzik sign check

Starting from $G_0^{(n)}=Z_\phi^{n/2}G_R^{(n)}$ and

$$
\gamma_\phi=\frac12\mu\frac{d\log Z_\phi}{d\mu}\bigg|_{\text{bare}},
$$

derive the sign of the $n\gamma_\phi$ term in the homogeneous Callan–Symanzik equation for a massless theory.

<details><summary><strong>Solution</strong></summary>

At fixed bare parameters,

$$
0=\mu\frac{d}{d\mu}G_0^{(n)}
=\mu\frac{d}{d\mu}\left(Z_\phi^{n/2}G_R^{(n)}\right).
$$

The derivative of $Z_\phi^{n/2}$ is

$$
\mu\frac{d}{d\mu}Z_\phi^{n/2}
=n\gamma_\phi Z_\phi^{n/2}.
$$

The derivative of $G_R^{(n)}$ at fixed bare parameters becomes

$$
\left(\mu\frac{\partial}{\partial\mu}+\beta^i\frac{\partial}{\partial g^i}\right)G_R^{(n)}.
$$

Therefore

$$
0=Z_\phi^{n/2}
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+n\gamma_\phi
\right)G_R^{(n)}.
$$

After dividing by $Z_\phi^{n/2}$, the $n\gamma_\phi$ term has a plus sign.

</details>

### Exercise 3: Pole residue and field normalization

Suppose a scalar propagator near an isolated stable pole behaves as

$$
G^{(2)}(p)\simeq \frac{iR}{p^2-m_{\text{phys}}^2+i\epsilon}+\text{regular}.
$$

Show that rescaling the field by $\phi\to a\phi$ rescales the residue but not the pole location.

<details><summary><strong>Solution</strong></summary>

The two-point function contains two field insertions. Under $\phi\to a\phi$,

$$
G^{(2)}(p)\to a^2G^{(2)}(p).
$$

Therefore the pole term becomes

$$
\frac{iR}{p^2-m_{\text{phys}}^2+i\epsilon}
\to
\frac{ia^2R}{p^2-m_{\text{phys}}^2+i\epsilon}.
$$

The residue changes from $R$ to $a^2R$, while the denominator and hence the pole location are unchanged. This is why the pole mass is physical under suitable assumptions, but the residue of a chosen elementary field depends on field normalization.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the renormalization lectures on counterterms, propagator normalization, and Green functions.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on exact propagators, loop corrections, higher-order perturbation theory, renormalization schemes, and the renormalization group.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 18–23.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, especially chapter 12, and Vol. II, especially the renormalization-group methods chapter.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on renormalization, RG equations, and correlation functions.

## Version history

- 2026-06-17: First polished draft. Added separated-point Green-function renormalization, field-strength factors, connected versus 1PI normalization, renormalization conditions, contact-term caveats, and the Callan–Symanzik derivation from fixed bare correlators.
