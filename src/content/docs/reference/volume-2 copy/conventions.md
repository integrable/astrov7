---
title: "Conventions and Notation"
description: "Notation for regulators, renormalized parameters, beta functions, anomalous dimensions, Wilsonian actions, and EFT coefficients."
sidebar:
  label: "Conventions and Notation"
  order: 10
level: Graduate
status: "Polished draft"
source: "Srednicki §§27–29; Schwartz chs. 18–23 and app. B; Weinberg Vol. I ch. 12 and Vol. II ch. 18; Wilson and Kogut 1974; Burgess chs. 1–3."
topics:
  - renormalization conventions
  - RG scales
  - beta functions
  - anomalous dimensions
  - Wilsonian actions
  - EFT coefficients
canonicalTopics:
  - renormalization
  - renormalization-group
  - effective-field-theory
researchStatus:
  established:
    - "The conventions on this page are standard graduate-level QFT and EFT conventions, with sign choices stated explicitly."
  active:
    - "Later pages add specialized conventions for gauge theories, curved spacetime, functional RG, and advanced EFT applications."
---

## Summary

This page fixes the notation used in this volume. It does not replace the general [Conventions and Normalizations](/foundations/conventions-and-normalizations/) page, which fixes the metric, Fourier convention, state normalization, spinor conventions, and Euclidean-continuation dictionary used across the site. Here we add the extra bookkeeping needed for renormalization, RG flow, and effective field theory.

The default spacetime convention remains

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
\qquad \hbar=c=1,
\qquad e^{-ip\cdot x}\text{ for plane waves}.
$$

The most important convention in this volume is the distinction between four different scales:

| Symbol | Meaning | Typical use |
|---|---|---|
| $\Lambda$ | UV cutoff or Wilsonian cutoff | labels which high-momentum modes remain explicit |
| $\mu$ | renormalization scale | labels the convention used to define renormalized parameters |
| $Q$ or $E$ | physical momentum or energy scale | labels the process, probe, or correlation function |
| $M$ | heavy mass or matching scale | labels a threshold where degrees of freedom are integrated out |

A cutoff $\Lambda$ is part of a regulated or Wilsonian definition. A renormalization scale $\mu$ is part of a subtraction convention. A physical scale $Q$ is set by the problem. A heavy scale $M$ belongs to the spectrum or to the EFT expansion. Treating all four as “the cutoff” is the fastest way to manufacture fake paradoxes.

:::note[Default beta-function sign]
For a dimensionless renormalized coupling $g(\mu)$, this volume defines

$$
\beta_g(g)\equiv \left.\mu\frac{dg}{d\mu}\right|_{\text{bare parameters fixed}}.
$$

Increasing $\mu$ means moving toward the ultraviolet in the usual renormalized perturbation theory convention.
:::

## Prerequisites

You should know the basic path-integral and Feynman-diagram language, the meaning of a local Lagrangian, and the distinction between a parameter in a Lagrangian and a measured observable. The conceptual pages in Why Renormalization? do not assume fluency with dimensional regularization or Wilsonian RG; those are introduced as needed.

For loop-calculation details, use the Perturbative QFT conventions and regularization pages. This volume cares less about the mechanics of evaluating integrals and more about what the scale dependence means.

## Core idea

Renormalization uses several descriptions of the same physics:

$$
\text{bare parameters},\qquad
\text{renormalized parameters},\qquad
\text{Wilsonian couplings},\qquad
\text{physical observables},\qquad
\text{EFT Wilson coefficients}.
$$

These are not rival ontologies. They are different coordinate systems adapted to different tasks.

A bare parameter belongs to a regulated definition. A renormalized parameter belongs to a scheme and a scale. A Wilsonian coupling belongs to an action with a cutoff. A physical observable belongs to an experiment, correlation function, or S-matrix element. An EFT coefficient belongs to a low-energy expansion after heavy or short-distance information has been compressed into local operators.

Thus a statement such as

$$
\mu\frac{dg}{d\mu}=\beta_g(g)
$$

does not mean that nature changes when we change the symbol $\mu$. It means that, at fixed bare definition or fixed physical prediction, the renormalized coordinate $g(\mu)$ changes when we change the subtraction convention.

## Dimensions and operators

Unless otherwise stated, $d$ denotes spacetime dimension. In dimensional regularization near four dimensions we write

$$
d=4-2\epsilon.
$$

Mass dimension is denoted by square brackets:

$$
[x^\mu]=-1,
\qquad [\partial_\mu]=1,
\qquad [d^d x]=-d,
\qquad [S]=0,
\qquad [\mathcal L]=d.
$$

For a scalar field with canonical kinetic term,

$$
\mathcal L_{\text{kin}}=\frac12\partial_\mu\phi\,\partial^\mu\phi,
$$

the engineering dimension is

$$
[\phi]_{\text{eng}}=\frac{d-2}{2}.
$$

For a Dirac field with kinetic term $\bar\psi i\gamma^\mu\partial_\mu\psi$,

$$
[\psi]_{\text{eng}}=\frac{d-1}{2}.
$$

A general local Lagrangian is written schematically as

$$
\mathcal L=\sum_i g_i\mathcal O_i,
$$

where $\mathcal O_i$ is a local operator. If $\mathcal O_i$ has engineering dimension $\Delta_i^{\text{eng}}$, then

$$
[g_i]=d-\Delta_i^{\text{eng}}.
$$

Near an interacting fixed point, the important dimension is the full scaling dimension

$$
\Delta_i=\Delta_i^{\text{eng}}+\gamma_i.
$$

The classification is always relative to a fixed point:

| Operator | Condition | Coupling under IR flow |
|---|---:|---|
| relevant | $\Delta_i<d$ | grows |
| marginal | $\Delta_i=d$ | decided by beta functions beyond linear order |
| irrelevant | $\Delta_i>d$ | shrinks |

The word “irrelevant” does not mean physically unimportant. It means suppressed near a chosen long-distance scaling regime. In EFT, irrelevant operators are often exactly where the new-physics information lives.

## Regulators

A regulator makes intermediate expressions well defined. It is not the same thing as renormalization.

| Symbol | Meaning |
|---|---|
| $\Lambda$ | hard UV cutoff, lattice cutoff, or Wilsonian cutoff |
| $a$ | lattice spacing, usually $a\sim \Lambda^{-1}$ |
| $\epsilon$ | dimensional-regularization parameter |
| $\mu$ | renormalization scale inserted to define renormalized parameters |
| $\bar\mu$ | modified scale used in $\overline{\mathrm{MS}}$ conventions |

A cutoff calculation may produce terms such as

$$
A\Lambda^2+BQ^2\log\frac{\Lambda^2}{Q^2}+\text{finite}.
$$

A dimensionally regularized calculation may instead produce

$$
\frac{BQ^2}{\epsilon}+BQ^2\log\frac{\mu^2}{Q^2}+\text{finite}.
$$

The lesson is not that every $1/\epsilon$ pole literally equals a power of a hard cutoff. The lesson is that different regulators expose the same need: short-distance sensitivity must be represented by local terms allowed by the symmetries.

## Dimensional regularization and subtraction schemes

In $d=4-2\epsilon$, powers of $\mu$ are inserted so that renormalized couplings keep their four-dimensional dimensions. For example, in scalar $\phi^4$ theory,

$$
\mathcal L\supset -\frac{\mu^{2\epsilon}\lambda}{4!}\phi^4.
$$

For gauge and Yukawa couplings, one commonly inserts $\mu^\epsilon$. For a general operator, the required power follows from dimensional analysis.

We use

$$
\frac{1}{\bar\epsilon}\equiv \frac{1}{\epsilon}-\gamma_E+\log(4\pi),
$$

where $\gamma_E$ is Euler's constant. Minimal subtraction, MS, subtracts pole terms in $1/\epsilon$. Modified minimal subtraction, $\overline{\mathrm{MS}}$, subtracts the common $1/\bar\epsilon$ combination. When a finite convention matters, the page will state the scheme explicitly.

## Bare and renormalized quantities

Bare quantities carry a subscript $0$. Renormalized quantities usually have no subscript, or carry $R$ when clarity requires it.

For a scalar theory, we write

$$
\phi_0=Z_\phi^{1/2}\phi,
\qquad
m_0^2=Z_{m^2}m^2,
\qquad
\lambda_0=\mu^{2\epsilon}Z_\lambda\lambda.
$$

A renormalized Lagrangian is often split as

$$
\mathcal L_0=\mathcal L_{\text{ren}}+\mathcal L_{\text{ct}}.
$$

For example,

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

Counterterms are local because UV divergences come from short-distance regions. Locality is the hero hiding under the paperwork.

## Beta functions

For dimensionless renormalized couplings $g^i(\mu)$,

$$
\beta^i(g)\equiv \left.\mu\frac{dg^i}{d\mu}\right|_{\text{bare}}.
$$

Equivalently, with $t=\log\mu$,

$$
\frac{dg^i}{dt}=\beta^i(g).
$$

With this convention, one Dirac fermion in QED gives

$$
\beta_e=\frac{e^3}{12\pi^2}+O(e^5),
$$

while pure $SU(N)$ Yang–Mills gives

$$
\beta_g=-\frac{11N}{48\pi^2}g^3+O(g^5).
$$

The signs say that perturbative QED grows toward the UV, while pure Yang–Mills weakens toward the UV.

For a dimensionful coupling $g_i$ multiplying an operator of scaling dimension $\Delta_i$, define the dimensionless coupling

$$
\tilde g_i(\mu)=\mu^{\Delta_i-d}g_i(\mu).
$$

Near a fixed point,

$$
\mu\frac{d\tilde g_i}{d\mu}=(\Delta_i-d)\tilde g_i+\cdots.
$$

Thus a relevant perturbation with $\Delta_i<d$ grows toward the IR, even though the dimensionless coupling decreases as $\mu$ is taken toward the UV.

## Anomalous dimensions

For fields, we use

$$
\phi_0=Z_\phi^{1/2}\phi,
$$

and define

$$
\gamma_\phi\equiv \frac12\left.\mu\frac{d\log Z_\phi}{d\mu}\right|_{\text{bare}}.
$$

With this sign convention, a renormalized scalar $n$-point function obeys the massless homogeneous Callan–Symanzik form

$$
\left(\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+n\gamma_\phi\right)G_R^{(n)}=0,
$$

away from contact terms. Pages with masses display the mass terms separately.

For composite operators, we write

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R}.
$$

The anomalous-dimension matrix is

$$
\gamma_a{}^b=(Z^{-1})_a{}^c\left.\mu\frac{dZ_c{}^b}{d\mu}\right|_{\text{bare}}.
$$

Therefore

$$
\left.\mu\frac{d}{d\mu}\mathcal O_{a,R}\right|_{\text{bare}}
=-\gamma_a{}^b\mathcal O_{b,R}.
$$

The minus sign is not optional; it follows from differentiating the bare operator at fixed bare definition.

## Scheme dependence

A change of renormalization scheme is a change of coordinates on coupling space:

$$
g^i\longrightarrow g^{\prime i}(g).
$$

Beta functions transform as vector fields:

$$
\beta^{\prime i}(g')=\frac{\partial g^{\prime i}}{\partial g^j}\beta^j(g).
$$

Individual coefficients in a perturbative beta function can be scheme dependent. Fixed-point existence, critical exponents, and physical observables are invariant when computed consistently. Perturbative truncations can hide this invariance, so comparisons between schemes should be made with some humility.

## Wilsonian conventions

A Wilsonian effective action at cutoff $\Lambda$ is written schematically as

$$
e^{iS_\Lambda[\phi_<]}
=\int_{|p|>\Lambda}\mathcal D\phi_>\,e^{iS[\phi_<+\phi_>]}.
$$

In Euclidean signature, replace $iS$ by $-S_E$. The formula is schematic because the precise split into high- and low-momentum modes depends on the regulator.

We write

$$
S_\Lambda=\sum_i g_i(\Lambda)\int d^d x\,\mathcal O_i(x),
$$

and

$$
\tilde g_i(\Lambda)=\Lambda^{\Delta_i-d}g_i(\Lambda).
$$

For Wilsonian RG it is often convenient to use the IR time

$$
\ell=\log\frac{\Lambda_0}{\Lambda},
$$

which increases as the cutoff is lowered. Near a fixed point,

$$
\frac{d\tilde g_i}{d\ell}=(d-\Delta_i)\tilde g_i+\cdots.
$$

This looks sign-reversed relative to $t=\log\mu$ because $\ell$ flows toward the IR while $t$ flows toward the UV.

## EFT notation

An EFT below a heavy scale $M$ is written as

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\text{light}}
+\sum_i\frac{C_i(\mu)}{M^{\Delta_i-d}}\mathcal O_i.
$$

Here $\mathcal O_i$ are local operators built from light fields and $C_i(\mu)$ are dimensionless Wilson coefficients. The scale $M$ is a physical threshold or organizing scale. The scale $\mu$ is a renormalization convention. They are often chosen near each other during matching, but they are not the same object.

Matching fixes the EFT coefficients by requiring that the EFT and the more microscopic theory agree at low energy:

$$
\mathcal A_{\text{full}}(Q\ll M)
=\mathcal A_{\text{EFT}}(Q;C_i(\mu),\mu)
+O\!\left(\frac{Q^{n+1}}{M^{n+1}}\right).
$$

Running then evolves the coefficients between scales. In a fixed operator basis one often writes

$$
\mu\frac{dC_i}{d\mu}=\gamma_i{}^j C_j+\cdots,
$$

but the placement of indices and signs depends on the operator-renormalization convention. Operator-mixing pages state the matrix convention before using it.

## Common pitfalls

**Confusing $\Lambda$ and $\mu$.** A cutoff limits or organizes degrees of freedom. A renormalization scale labels a subtraction convention.

**Treating bare parameters as observables.** Bare parameters are regulator-dependent coordinates. Measured quantities are extracted from correlation functions, S-matrix elements, spectra, or thermodynamic observables.

**Calling every divergence a pathology.** A UV divergence usually says that short-distance local information has not yet been specified in the low-energy description.

**Thinking nonrenormalizable means useless.** In EFT, higher-dimension operators are useful precisely because they organize suppressed effects in powers of $Q/M$.

**Comparing beta functions without conventions.** Always check the coupling definition, scheme, and RG-time direction before comparing signs or coefficients.

## Relations to other pages

Why Renormalization? explains why these objects are needed. Regularization and Counterterms explains how regulators expose local counterterms. Renormalized Perturbation Theory explains how $Z$ factors enter loop calculations. Renormalization Group Equations develops beta functions, anomalous dimensions, and Callan–Symanzik equations. Wilsonian Renormalization explains $S_\Lambda$. Effective Field Theory explains Wilson coefficients, matching, running, decoupling, and power counting.

## Research status

The conventions here are standard. The only delicate points are not physics controversies but notation choices: signs of anomalous dimensions, definitions of $\overline{\mathrm{MS}}$, normalization of operators, and the direction of RG time. Pages that use a different convention will say so explicitly.

## Exercises

### Exercise 1: Engineering relevance

Let $S\supset g\int d^d x\,\mathcal O(x)$, where $\mathcal O$ has scaling dimension $\Delta$. Define $\tilde g(\Lambda)=\Lambda^{\Delta-d}g(\Lambda)$. Show that under IR Wilsonian time $\ell=\log(\Lambda_0/\Lambda)$,

$$
\frac{d\tilde g}{d\ell}=(d-\Delta)\tilde g.
$$

<details><summary><strong>Solution</strong></summary>

Under $x\to bx$ with $b=e^\ell$, the measure contributes $b^d$ and the operator contributes $b^{-\Delta}$. Therefore the coefficient of the dimensionless perturbation is multiplied by $b^{d-\Delta}$. Hence

$$
\tilde g(\ell)=e^{(d-\Delta)\ell}\tilde g(0),
$$

and differentiating gives the stated flow.

</details>

### Exercise 2: The factor in phi-four theory

In $d=4-2\epsilon$, show that the coefficient of $\phi^4$ has mass dimension $2\epsilon$ if $[\phi]=(d-2)/2$.

<details><summary><strong>Solution</strong></summary>

Since $[\phi]=1-\epsilon$,

$$
[\phi^4]=4-4\epsilon.
$$

The Lagrangian density has dimension $4-2\epsilon$, so the coefficient has dimension

$$
(4-2\epsilon)-(4-4\epsilon)=2\epsilon.
$$

Writing the interaction as $\mu^{2\epsilon}\lambda\phi^4/4!$ keeps $\lambda$ dimensionless.

</details>

### Exercise 3: The sign of the Callan–Symanzik field term

Assume $G_0^{(n)}=Z_\phi^{n/2}G_R^{(n)}$ and $\gamma_\phi=\frac12\mu d\log Z_\phi/d\mu$ at fixed bare parameters. Derive the sign of the $n\gamma_\phi$ term in the massless Callan–Symanzik equation.

<details><summary><strong>Solution</strong></summary>

Differentiate the bare correlator:

$$
0=\mu\frac{d}{d\mu}G_0^{(n)}
=\mu\frac{d}{d\mu}\left(Z_\phi^{n/2}G_R^{(n)}\right).
$$

Using the definition of $\gamma_\phi$ gives

$$
0=Z_\phi^{n/2}\left(\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+n\gamma_\phi\right)G_R^{(n)}.
$$

After dividing by $Z_\phi^{n/2}$, the field term appears with a plus sign.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," "Renormalization and Symmetry," and "Asymptotic Freedom."
- Mark Srednicki, *Quantum Field Theory*, especially §§27–29.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 18–23 and appendix B.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I chapter 12 and Vol. II chapter 18.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on renormalization, RG, and critical behavior.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially chapters 1–3.

## Version history

- 2026-06-16: First polished draft. Fixed scale notation, beta-function sign, anomalous-dimension conventions, Wilsonian RG-time convention, and EFT coefficient notation for the volume.
