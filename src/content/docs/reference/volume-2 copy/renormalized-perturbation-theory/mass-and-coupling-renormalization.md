---
title: "Mass and Coupling Renormalization"
description: "How mass parameters and interaction strengths are defined, shifted by counterterms, related to physical measurements, and evolved by renormalization group equations."
sidebar:
  label: "Mass and Coupling Renormalization"
  order: 8
level: Graduate
status: "Polished draft"
source: "Srednicki §§13–18 and §§27–29; Schwartz chs. 18–23; Weinberg Vol. I ch. 12 and Vol. II ch. 18; Coleman, renormalization lectures; Zinn-Justin, renormalization chapters."
topics:
  - mass renormalization
  - coupling renormalization
  - counterterms
  - pole mass
  - running parameters
  - beta functions
canonicalTopics:
  - mass-renormalization
  - coupling-renormalization
  - running-couplings
  - pole-mass
researchStatus:
  established:
    - "Mass and coupling renormalization are standard ingredients of perturbative QFT: local counterterms define finite scheme-dependent parameters, while physical observables are independent of the scheme when computed consistently."
  active:
    - "Precision mass definitions, threshold schemes, renormalon-sensitive pole masses, unstable particles, gauge dependence, and high-order coupling conversions remain active technical topics."
---

## Summary

**Mass renormalization** and **coupling renormalization** are the parts of renormalized perturbation theory that tell us what the symbols $m$ and $g$ mean after loop corrections are included.

At tree level, a Lagrangian parameter can look like a direct physical property. In an interacting quantum field theory, this identification is usually too naive. A mass parameter may be a bare regulator-dependent number, a running scheme-dependent number, a pole location, a threshold mass, or a parameter extracted from a chosen low-energy observable. A coupling may be a bare coefficient, a running $\overline{\mathrm{MS}}$ coordinate, an on-shell charge, a momentum-subtraction coupling, or a Wilson coefficient in an EFT.

The organizing equations are simple. One writes bare parameters in terms of renormalized parameters and counterterms, for example

$$
m_0^2=m^2+\delta m^2,
\qquad
\lambda_0=\mu^{2\epsilon}(\lambda+\delta\lambda),
$$

or equivalently

$$
m_0^2=Z_{m^2}m^2,
\qquad
\lambda_0=\mu^{2\epsilon}Z_\lambda\lambda,
$$

when multiplicative notation is appropriate. The counterterms cancel regulator dependence. The finite parts of the counterterms are fixed by a renormalization scheme. The resulting parameters are finite but not automatically physical observables.

The slogan is:

$$
\text{masses and couplings are definitions until an observable tells you how they are measured.}
$$

<figure class="doc-figure" style="--figure-width: 56rem; --caption-width: 55rem;">

![Map from bare regulated action through two-point and interaction sectors to mass and coupling counterterms, scheme definitions, and finite observables](/figures/renormalization-rg-eft/mass-coupling-renormalization-map.svg)

<figcaption>

Mass and coupling renormalization split the same bare local action into two complementary tasks. Two-point functions define mass and field-normalization counterterms, while interaction vertices or amplitudes define coupling counterterms. The resulting coordinates $m(\mu)$ and $g(\mu)$ are scheme dependent; observables are not.

</figcaption>
</figure>

## Prerequisites

You should know [Renormalized Lagrangian](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-lagrangian/), [Renormalization Conditions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalization-conditions/), [Counterterm Schemes](/renormalization-rg-eft/renormalized-perturbation-theory/counterterm-schemes/), [On-Shell Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/on-shell-scheme/), [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/), and [Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/).

For the local origin of these counterterms, review [Divergences as Local Operators](/renormalization-rg-eft/why-renormalization/divergences-as-local-operators/) and [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/). For the distinction between measured and scheme-defined quantities, review [Physical Parameters](/renormalization-rg-eft/why-renormalization/physical-parameters/).

We use the mostly-minus convention and write dimensional regularization near four dimensions as

$$
d=4-2\epsilon.
$$

## Core idea

A parameter in a Lagrangian is the coefficient of a local operator. Loop corrections change how that coefficient must be related to measured quantities.

For a scalar theory, the basic local terms include

$$
\frac12\partial_\mu\phi\,\partial^\mu\phi,
\qquad
\frac12m^2\phi^2,
\qquad
\frac{\lambda}{4!}\phi^4.
$$

The first term fixes the normalization of the field, the second fixes a mass-like relevant deformation, and the third fixes a quartic interaction strength. Once loops are allowed, the same local structures are generated by short-distance fluctuations. Therefore their coefficients must be adjusted:

$$
\mathcal L_0
=
\mathcal L_{\text{ren}}
+
\mathcal L_{\text{ct}}.
$$

For real $\phi^4$ theory this becomes

$$
\mathcal L_{\text{ren}}
=\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4,
$$

and

$$
\mathcal L_{\text{ct}}
=\frac12\delta Z\,\partial_\mu\phi\,\partial^\mu\phi
-\frac12\delta m^2\phi^2
-\frac{\delta\lambda}{4!}\phi^4.
$$

Wavefunction renormalization handles the kinetic term. This page focuses on the mass counterterm $\delta m^2$ and the coupling counterterm $\delta\lambda$.

The conceptual point is not that a particle literally changes its mass every time a loop is drawn. The point is that the parameter called $m$ must be defined by a convention, and the quantum corrections to any chosen convention are local and computable order by order.

## Setup and conventions

Let $\Gamma_R^{(n)}$ denote a renormalized one-particle-irreducible $n$-point vertex function. A mass parameter is usually fixed by a condition on $\Gamma_R^{(2)}$, while a coupling is fixed by a condition on $\Gamma_R^{(n)}$ for the interaction of interest.

For a scalar field, a common convention is to write the renormalized inverse propagator denominator as

$$
D_R^{-1}(p^2)
=
p^2-m^2-\Pi_R(p^2),
$$

where $\Pi_R(p^2)$ is the renormalized self-energy. With the counterterm convention above,

$$
\Pi_R(p^2)
=
\Pi_{\text{loop}}(p^2)
+
\delta Z(p^2-m^2)
-
\delta m^2.
$$

Different books place signs differently in the definition of $\Pi$. The safe rule is to inspect the inverse propagator: the physical pole occurs where the denominator vanishes.

For the four-point coupling in scalar theory, the renormalized vertex is written schematically as

$$
\Gamma_R^{(4)}
=
-\lambda+
\Gamma_{\text{loop}}^{(4)}
-\delta\lambda,
$$

up to the usual factors of $i$ and sign conventions. Again, the invariant statement is not the isolated sign of $\delta\lambda$ in a particular Feynman-rule table. The invariant statement is that a local four-point counterterm cancels the local ultraviolet part of the four-point loop correction and implements the chosen definition of $\lambda$.

## Mass as a coefficient of a relevant operator

The mass term is the coefficient of a relevant operator. In four-dimensional scalar theory,

$$
[\phi]=1,
\qquad
[\phi^2]=2,
\qquad
[m^2]=2.
$$

Because $m^2$ has positive mass dimension, it is sensitive to short-distance physics in a way that dimensionless couplings are not. A hard cutoff calculation may produce terms schematically of the form

$$
\Pi_{\text{loop}}(0)
\sim
A\Lambda^2
+
B m^2\log\frac{\Lambda^2}{\mu^2}
+
\cdots.
$$

The quadratic piece is regulator dependent and local. It is absorbed into $\delta m^2$. Dimensional regularization with minimal subtraction does not display the same term as a visible $\Lambda^2$, but this does not mean scalar mass sensitivity has disappeared from physics. It means the regulator language has changed.

In a scheme that defines a running scalar mass $m^2(\mu)$, the renormalization group equation often has the multiplicative form

$$
\mu\frac{d m^2}{d\mu}=\beta_{m^2}(g,m^2).
$$

In a mass-independent scheme and near a theory with no other dimensionful parameters, this frequently becomes

$$
\mu\frac{d m^2}{d\mu}=\gamma_{m^2}(g)m^2.
$$

That equation is a statement about the running coordinate $m^2(\mu)$. It should not be confused with a statement that a pole mass is changing while the particle propagates.

## Pole mass and running mass

A stable particle's pole mass is defined by the pole of its exact propagator. For a scalar field,

$$
D_R^{-1}(m_{\text{pole}}^2)=0.
$$

Using the convention above,

$$
m_{\text{pole}}^2-m^2-\Pi_R(m_{\text{pole}}^2)=0.
$$

In an on-shell scheme, one chooses the renormalized mass parameter to equal the pole mass:

$$
m^2=m_{\text{pole}}^2,
$$

and imposes

$$
\Pi_R(m^2)=0.
$$

One often also imposes a residue condition

$$
\Pi_R'(m^2)=0,
$$

which fixes the wavefunction counterterm in the same scheme.

In a minimal-subtraction scheme, by contrast, the parameter $m^2(\mu)$ is usually not the pole mass. It is a running parameter. The pole mass, if well defined, is computed from it:

$$
m_{\text{pole}}^2
=
m^2(\mu)+\Pi_R(m_{\text{pole}}^2;\mu).
$$

The explicit $\mu$ dependence in the loop correction cancels the implicit $\mu$ dependence of $m^2(\mu)$ order by order in a physical prediction.

:::note[Stable particles only]
A pole mass is cleanest for stable particles. For unstable particles, the pole moves off the real axis on an analytically continued sheet. Gauge dependence, width effects, and threshold behavior then require more care. This is not just pedantry; it matters in precision electroweak theory and hadron physics.
:::

## Additive and multiplicative mass renormalization

Mass renormalization can be written additively,

$$
m_0^2=m^2+\delta m^2,
$$

or multiplicatively,

$$
m_0^2=Z_{m^2}m^2.
$$

The additive form is always conceptually safe: the local operator $\phi^2$ has a coefficient, and loops shift that coefficient.

The multiplicative form is convenient when symmetries and the chosen scheme imply that $m^2=0$ is stable under radiative corrections. For example, in dimensional regularization with a mass-independent subtraction scheme, a scalar $\phi^4$ theory often has multiplicative running for $m^2$. But in a Wilsonian or hard-cutoff view, a scalar mass term is generically additively sensitive to heavy physics unless protected by symmetry.

Fermion masses behave differently. A Dirac mass term is

$$
-m\bar\psi\psi.
$$

If the massless theory has a chiral symmetry forbidding $\bar\psi\psi$, then loops cannot generate an additive fermion mass without breaking that symmetry. The natural renormalization is multiplicative:

$$
m_0=Z_m m.
$$

This is the seed of technical naturalness: a small parameter is stable when setting it to zero increases the symmetry.

## Coupling as a definition of an interaction strength

A coupling is the coefficient of an interaction operator. For a local Lagrangian,

$$
\mathcal L\supset -g\mathcal O.
$$

The engineering dimension of $g$ is

$$
[g]=d-\Delta_{\mathcal O}^{\text{eng}}.
$$

If $g$ is dimensionless in four dimensions, then in $d=4-2\epsilon$ one inserts a power of $\mu$ so that the renormalized coupling remains dimensionless. For scalar $\phi^4$ theory,

$$
\lambda_0=\mu^{2\epsilon}(\lambda+\delta\lambda)
=
\mu^{2\epsilon}Z_\lambda\lambda.
$$

For a gauge or Yukawa coupling in four dimensions, the corresponding factor is commonly $\mu^\epsilon$.

The coupling can be defined by a physical measurement or by a subtraction convention. For instance, a four-point scalar coupling might be defined by

$$
\Gamma_R^{(4)}(p_i\text{ at a chosen point})=-\lambda.
$$

QED can define the electric charge through a low-momentum scattering process, through the Thomson limit, through a momentum-subtraction condition, or through an $\overline{\mathrm{MS}}$ running parameter. These definitions agree at leading order but differ beyond tree level.

The coupling is therefore not a sacred number. It is a coordinate chosen so that calculations can be organized.

## Coupling counterterms from vertex functions

A coupling counterterm is fixed by the divergent local part of an appropriate vertex function. In scalar $\phi^4$ theory, the one-loop four-point diagrams produce local ultraviolet divergences proportional to $\phi^4$. These are canceled by $\delta\lambda$.

In an MS-type scheme, $\delta\lambda$ contains only pole terms. Schematically,

$$
\delta\lambda
=
\sum_{L\ge1}\sum_{k=1}^{L}\frac{a_{Lk}(\lambda)}{\epsilon^k}.
$$

In a physical momentum-subtraction scheme, $\delta\lambda$ contains the pole part plus a finite part chosen so that the vertex equals the specified value at a specified momentum configuration.

The same logic applies to other couplings:

| Coupling type | Typical vertex used to define it | Subtlety |
|---|---|---|
| scalar quartic $\lambda$ | four-scalar 1PI vertex | channel and subtraction-point dependence |
| Yukawa coupling $y$ | scalar–fermion–fermion vertex | chiral structure and flavor matrices |
| gauge coupling $g$ | gauge–matter vertex or gauge self-interaction | Ward or Slavnov–Taylor identities relate many definitions |
| EFT coefficient $C_i$ | low-energy amplitude or operator matrix element | operator mixing and basis dependence |

In gauge theories, coupling renormalization is constrained by gauge symmetry. In QED, Ward identities relate charge renormalization to field renormalization. In non-Abelian gauge theory, background-field gauge can make the coupling renormalization especially transparent, but the physical beta function is not a property of one diagram alone.

## A scalar one-loop benchmark

For real $\phi^4$ theory in four dimensions, with

$$
\mathcal L_{\text{int}}=-\frac{\lambda}{4!}\phi^4,
$$

the one-loop $\overline{\mathrm{MS}}$ renormalization group functions are commonly written

$$
\mu\frac{d\lambda}{d\mu}
=
\frac{3\lambda^2}{16\pi^2}+O(\lambda^3),
$$

and

$$
\mu\frac{d m^2}{d\mu}
=
\frac{\lambda}{16\pi^2}m^2+O(\lambda^2).
$$

The field anomalous dimension vanishes at this order:

$$
\gamma_\phi=0+O(\lambda^2).
$$

This example is useful because it separates the three basic renormalizations:

| Quantity | First nonzero correction in four-dimensional $\phi^4$ theory | What causes it |
|---|---:|---|
| $m^2$ | one loop | tadpole self-energy |
| $\lambda$ | one loop | four-point bubble diagrams |
| $Z_\phi$ | two loops | momentum-dependent self-energy |

The exact coefficients depend on the normalization of the interaction. The qualitative pattern does not.

## Running parameters and physical predictions

A running parameter is a way of storing information at a chosen scale. Suppose a prediction depends on a physical momentum scale $Q$ and a renormalization scale $\mu$:

$$
\mathcal A(Q)=\mathcal A(Q;g(\mu),m(\mu),\mu).
$$

The exact observable cannot depend on the arbitrary bookkeeping scale:

$$
\mu\frac{d}{d\mu}\mathcal A(Q)=0.
$$

Perturbative truncations leave residual $\mu$ dependence. That residual dependence is not a new force of nature; it is an estimate of the size of omitted higher-order terms, provided the scale variation is used sensibly.

The practical art is to choose $\mu$ near the characteristic physical scale of the process so that logarithms are not large:

$$
\log\frac{Q^2}{\mu^2}
$$

should not sabotage a fixed-order expansion. The renormalization group then allows one to move parameters between scales, resumming logarithms that would otherwise appear order by order.

## Multiple couplings and mixing

Realistic theories have many couplings. Let $g^i$ denote coordinates on a space of interactions:

$$
\mathcal L=\sum_i g^i\mathcal O_i.
$$

Then the beta functions form a vector field:

$$
\mu\frac{d g^i}{d\mu}=\beta^i(g).
$$

Changing scheme is a coordinate change

$$
g^i\to g^{\prime i}(g),
$$

so the beta functions transform as

$$
\beta^{\prime i}(g')=
\frac{\partial g^{\prime i}}{\partial g^j}\beta^j(g).
$$

This geometric statement is more durable than any one convention. The coefficients of a perturbative beta function may be scheme-dependent, but the flow's physical content must be read through scheme-invariant questions: fixed points, critical exponents, universal ratios, and observable predictions.

In EFTs, coupling renormalization usually becomes operator-coefficient renormalization. If

$$
\mathcal L_{\text{EFT}}\supset \sum_i C_i(\mu)\mathcal O_i,
$$

then loops can mix operators:

$$
\mu\frac{dC_i}{d\mu}=\gamma_i{}^j C_j+\cdots.
$$

The anomalous-dimension matrix depends on the operator basis, but physical amplitudes do not.

## Common pitfalls

**Treating the running mass as the measured mass.** A running mass $m(\mu)$ is a scheme-dependent coordinate. A pole mass or threshold mass is defined by an observable procedure.

**Treating the pole mass as always ideal.** Pole masses are natural for stable particles in simple theories. In QCD and for unstable particles, pole definitions can be plagued by confinement, infrared sensitivity, renormalons, widths, and gauge subtleties.

**Saying dimensional regularization removes scalar mass sensitivity.** Dimensional regularization hides power divergences; it does not make relevant operators irrelevant or remove sensitivity to heavy thresholds.

**Comparing couplings without comparing schemes.** A number called $g$ in one scheme need not equal a number called $g$ in another scheme. The conversion is a finite renormalization.

**Believing counterterms are arbitrary after observables are fixed.** Counterterms include scheme freedom, but once a scheme and input observables are chosen, the remaining predictions are constrained.

**Forgetting symmetries.** Symmetries can forbid mass terms, relate coupling counterterms, and protect small parameters. Ignoring them is the fastest route to fake naturalness problems or fake cancellations.

## Relations to other pages

[Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/) explains the companion renormalization of fields and pole residues. [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/) explains how these parameter and field renormalizations make correlation functions finite. [Renormalized S-Matrix](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-s-matrix/) applies the same logic to on-shell amplitudes.

The next chapter, Renormalization Group Equations, turns the scale dependence of $m(\mu)$ and $g(\mu)$ into the Callan–Symanzik equation, beta functions, anomalous dimensions, running couplings, running masses, and RG-improved perturbation theory.

The Effective Field Theory chapter returns to mass and coupling renormalization from a low-energy viewpoint, where higher-dimension operators and Wilson coefficients are treated on the same footing as familiar renormalizable couplings.

## Research status

The conceptual structure of mass and coupling renormalization is settled. The difficult parts are not the existence of $\delta m^2$ or $\delta g$; they are precision definitions and conversions in complicated theories.

Important active or technically delicate areas include:

| Topic | Why it is delicate |
|---|---|
| quark masses | confinement prevents direct pole-particle interpretation |
| pole masses in QCD | infrared renormalons limit intrinsic perturbative precision |
| unstable particles | complex poles and gauge-invariant width definitions are subtle |
| heavy thresholds | matching and decoupling must be done consistently |
| flavor matrices | masses and couplings become matrices with basis dependence |
| EFT coefficients | operator mixing and redundant operators complicate running |
| high-order Standard Model running | multi-loop conversions and threshold corrections matter numerically |

The mature lesson is not that physical parameters are impossible to define. It is that one must say **which** definition is being used.

## Exercises

### Exercise 1: Pole condition at first order

Let the renormalized scalar propagator denominator be

$$
D_R^{-1}(p^2)=p^2-m^2-\Pi_R(p^2).
$$

Assume $\Pi_R$ is first order in a small coupling. Show that, to first order,

$$
m_{\text{pole}}^2=m^2+\Pi_R(m^2)+O(\Pi_R^2).
$$

<details><summary><strong>Solution</strong></summary>

The pole is defined by

$$
0=m_{\text{pole}}^2-m^2-\Pi_R(m_{\text{pole}}^2).
$$

Write

$$
m_{\text{pole}}^2=m^2+\delta m_{\text{pole}}^2,
$$

where $\delta m_{\text{pole}}^2$ is first order. Then

$$
0=\delta m_{\text{pole}}^2-\Pi_R(m^2+\delta m_{\text{pole}}^2).
$$

Expanding the self-energy,

$$
\Pi_R(m^2+\delta m_{\text{pole}}^2)
=
\Pi_R(m^2)+\delta m_{\text{pole}}^2\Pi_R'(m^2)+\cdots.
$$

The derivative term is second order, since both $\delta m_{\text{pole}}^2$ and $\Pi_R'$ are first order. Therefore

$$
\delta m_{\text{pole}}^2=\Pi_R(m^2)+O(\Pi_R^2),
$$

which gives the desired result.

</details>

### Exercise 2: Multiplicative running mass

Suppose a running scalar mass satisfies

$$
\mu\frac{d m^2}{d\mu}=\gamma_{m^2}m^2,
$$

where $\gamma_{m^2}$ is constant over the range of scales considered. Solve for $m^2(\mu)$ in terms of $m^2(\mu_0)$.

<details><summary><strong>Solution</strong></summary>

Write the equation as

$$
\frac{d\log m^2}{d\log\mu}=\gamma_{m^2}.
$$

Integrating from $\mu_0$ to $\mu$ gives

$$
\log\frac{m^2(\mu)}{m^2(\mu_0)}
=
\gamma_{m^2}\log\frac{\mu}{\mu_0}.
$$

Therefore

$$
m^2(\mu)=m^2(\mu_0)\left(\frac{\mu}{\mu_0}\right)^{\gamma_{m^2}}.
$$

If $\gamma_{m^2}$ depends on running couplings, the same formula is replaced by an exponential of an integral along the RG flow.

</details>

### Exercise 3: Two coupling definitions

Suppose two renormalization schemes define couplings $g$ and $g'$ related by

$$
g'=g+a g^3+O(g^5).
$$

If

$$
\beta_g=b_1g^3+b_2g^5+O(g^7),
$$

show that the first beta-function coefficient is unchanged in the primed scheme.

<details><summary><strong>Solution</strong></summary>

The beta function transforms as

$$
\beta_{g'}=\frac{dg'}{dg}\beta_g.
$$

Since

$$
\frac{dg'}{dg}=1+3ag^2+O(g^4),
$$

we have

$$
\beta_{g'}=(1+3ag^2)(b_1g^3+b_2g^5+O(g^7))
=b_1g^3+(b_2+3ab_1)g^5+O(g^7).
$$

To express this in terms of $g'$, invert the relation:

$$
g=g'-a g'^3+O(g'^5).
$$

Then

$$
g^3=g'^3+O(g'^5).
$$

Therefore the leading term is

$$
\beta_{g'}=b_1g'^3+O(g'^5),
$$

so $b_1$ is unchanged.

</details>

### Exercise 4: Why the scalar mass is special

In four dimensions, compare the engineering dimensions of $\phi^2$, $\phi^4$, and $\phi^6$ for a scalar with $[\phi]=1$. Which coefficients have positive, zero, and negative mass dimension?

<details><summary><strong>Solution</strong></summary>

The operator dimensions are

$$
[\phi^2]=2,
\qquad
[\phi^4]=4,
\qquad
[\phi^6]=6.
$$

Since $[\mathcal L]=4$, the corresponding coefficient dimensions are

$$
[g_{\phi^2}]=4-2=2,
$$

$$
[g_{\phi^4}]=4-4=0,
$$

and

$$
[g_{\phi^6}]=4-6=-2.
$$

Thus the scalar mass-squared coefficient is relevant, the quartic coupling is classically marginal in four dimensions, and the $\phi^6$ coupling is classically irrelevant. This is why scalar masses are especially sensitive to short-distance physics.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, sections on loop corrections, renormalization schemes, the renormalization group, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters on mass renormalization, renormalized perturbation theory, renormalizability, nonrenormalizable theories, and the renormalization group.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapter 12, and Vol. II, chapter 18.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on determination of counterterms, renormalization, and QED renormalization.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations" and "Renormalization and Symmetry."
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chapters on renormalization and RG.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapters on effective actions, power counting, matching, and hierarchies of scale.

## Version history

- 2026-06-17: First polished draft. Added mass definitions, coupling definitions, scalar benchmark, scheme dependence, RG interpretation, exercises, and links to surrounding renormalized-perturbation-theory pages.
