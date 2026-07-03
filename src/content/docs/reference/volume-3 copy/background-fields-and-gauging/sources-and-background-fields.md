---
title: "Sources and Background Fields"
description: "Explains how nondynamical sources and background fields generate operator insertions, current correlators, Ward identities, and response functions."
sidebar:
  label: "Sources and Background Fields"
  order: 1
level: Graduate
status: "Polished draft"
source: "Weinberg Vol. II ch. 16; Schwartz chs. 14 and 34; Srednicki §22; Coleman on currents and Ward identities."
topics:
  - sources
  - background fields
  - generating functionals
  - current correlators
  - Ward identities
  - response functions
canonicalTopics:
  - source-coupling
  - background-field
  - connected-generating-functional
  - current-source
  - stress-tensor-source
researchStatus:
  established:
    - "Nondynamical sources and background fields are the standard way to define connected correlators, current insertions, stress-tensor insertions, and response functions."
  active:
    - "For generalized, non-invertible, and categorical symmetries, the correct notion of background data is more subtle than an ordinary classical gauge field."
---

## Summary

A source is a nondynamical field coupled to an operator. It is a probe you vary, not a degree of freedom you integrate over. In Lorentzian conventions, the basic example is

$$
Z[J]
=\int\mathcal D\Phi\,
\exp\!\left(iS[\Phi]+i\int d^dx\,J^i(x)\mathcal O_i(x)\right)
\equiv e^{iW[J]}.
$$

With this convention,

$$
\frac{\delta W[J]}{\delta J^i(x)}=\langle\mathcal O_i(x)\rangle_J.
$$

Repeated functional derivatives of $W$ give connected correlation functions. This is the first reason sources are useful.

A background field is a source with extra structure. A background gauge field $A_\mu^a$ couples to a global symmetry current $j_a^\mu$ and transforms under background gauge transformations. A background metric $g_{\mu\nu}$ couples to the stress tensor. A spurion is a source for a coupling or mass parameter that is assigned a transformation law so that explicit breaking can be tracked cleanly.

The second reason sources are useful is subtler: they organize contact terms and Ward identities. Instead of trying to remember every delta function in current correlators, one writes invariance of $W[J,A,g]$ under transformations of the sources. Differentiating that functional identity generates the local Ward identities, including their contact terms.

<figure class="doc-figure" style="--figure-width: 38rem;">

![A diagram showing operator sources, symmetry backgrounds, and metric backgrounds feeding into the connected generator W, whose functional derivatives produce one-point functions and whose background variations produce Ward identities or anomalies.](/figures/symmetry-anomalies-topology/source-functional-derivatives.svg)

<figcaption>

Sources are book-keeping devices with teeth. Functional derivatives of $W$ insert operators, while background transformations of $W$ encode Ward identities. A nonzero local remainder in $\delta_\lambda W$ is explicit breaking or an anomaly, depending on whether it can be removed by local counterterms.

</figcaption>
</figure>

## Prerequisites

You should know the [Conventions and Notation](/symmetry-anomalies-topology/conventions/), especially the normalization $Z=e^{iW}$ and $\langle j_a^\mu\rangle_A=\delta W/\delta A_\mu^a$. You should also know the Noether chapter through [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/) and [Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/).

No gauge fixing or BRST machinery is needed on this page. The fields introduced here are background probes. They become gauge-theory variables only on later pages.

## Core idea

The source viewpoint replaces the phrase “insert an operator” by a derivative operation:

$$
\mathcal O_i(x)
\quad\leftrightarrow\quad
\frac{\delta}{\delta J^i(x)}.
$$

That sounds like formalism for its own sake, but it solves three real problems.

First, it makes correlation functions reproducible. If $W[J]$ is the connected generator, then connected correlators are defined by functional differentiation at $J=0$.

Second, it separates physical long-distance data from contact-term choices. Local counterterms made purely from sources change coincident-point correlators but not separated-point correlators. This is exactly the ambiguity that shows up in current improvements and contact terms.

Third, it turns symmetry into a statement about background data. A nonanomalous global symmetry is not only a conservation equation at zero source. It is the statement that $W$ can be defined consistently as a functional of background fields and transforms in a controlled way.

## Setup and conventions

Let $\Phi^I$ denote all dynamical fields. The index $I$ is schematic: it includes field species, internal indices, spinor indices, and spacetime dependence when convenient.

For local operators $\mathcal O_i$, introduce sources $J^i(x)$ by

$$
S_J[\Phi;J]
=S[\Phi]+\int d^dx\,J^i(x)\mathcal O_i(x).
$$

The Lorentzian source-dependent partition functional is

$$
Z[J]=\int\mathcal D\Phi\,e^{iS_J[\Phi;J]},
\qquad
Z[J]=e^{iW[J]}.
$$

Therefore

$$
\frac{\delta W[J]}{\delta J^i(x)}
=\langle\mathcal O_i(x)\rangle_J.
$$

For two derivatives,

$$
\frac{\delta^2 W[J]}{\delta J^i(x)\delta J^j(y)}
=i\Big(
\langle\mathcal O_i(x)\mathcal O_j(y)\rangle_J
-\langle\mathcal O_i(x)\rangle_J\langle\mathcal O_j(y)\rangle_J
\Big),
$$

up to the usual time-ordering implicit in the Lorentzian path integral. Thus connected correlators are obtained from derivatives of $W$, with factors of $i$ determined by the convention $Z=e^{iW}$.

:::note[Source note]
Some books define $W_{\text{there}}[J]=-i\log Z[J]$; with $Z=e^{iW}$ this is the same $W$. In Euclidean signature one often writes $Z_E[J]=e^{W_E[J]}$ with $e^{-S_E+\int J\mathcal O}$, so the explicit factors of $i$ disappear. The safest translation is to compare the one-point function formula, not the name of $W$.
:::

## Three kinds of external data

The word “source” is broad. In this chapter we will distinguish three useful kinds of external data.

| External datum | Couples to | Main use |
|---|---|---|
| Ordinary source $J^i(x)$ | Local operator $\mathcal O_i(x)$ | Generate correlation functions and deformations. |
| Background gauge field $A_\mu^a(x)$ | Global current $j_a^\mu(x)$ | Test Ward identities, anomalies, global form, and gauging. |
| Background metric $g_{\mu\nu}(x)$ | Stress tensor $T^{\mu\nu}(x)$ | Define stress-tensor correlators, trace identities, and gravitational response. |

A source does not have to come from a symmetry. A spacetime-dependent mass $m^2(x)$ is a source for $-\frac12\phi^2(x)$ in the real scalar theory. A Yukawa matrix treated as spacetime-dependent is a source for a fermion bilinear. A background gauge field is special because it comes with a transformation law.

### Ordinary operator sources

Suppose the theory contains a scalar operator $\mathcal O$. Add

$$
\Delta S=\int d^dx\,J(x)\mathcal O(x).
$$

Then

$$
\langle\mathcal O(x)\rangle_J=\frac{\delta W[J]}{\delta J(x)}.
$$

Setting $J$ to a nonzero physical value can also define a deformation of the theory. For example, if $\mathcal O$ is relevant, then $J\mathcal O$ can drive an RG flow. The same symbol $J$ can therefore play two roles: a temporary book-keeping source for differentiating, or an actual coupling that changes the theory.

Those roles should not be mixed casually. When $J$ is a book-keeping source, one usually differentiates and then sets $J=0$. When $J$ is a physical deformation, the theory itself depends on $J$.

### Background gauge fields

For an ordinary continuous global symmetry, the background gauge field is

$$
A=A_\mu^aT_a\,dx^\mu,
$$

with Hermitian generators. The conventions of this volume are

$$
D=d-iA,
\qquad
F=dA-iA\wedge A.
$$

The source normalization is

$$
Z[A]=e^{iW[A]},
\qquad
\langle j_a^\mu(x)\rangle_A
=\frac{\delta W[A]}{\delta A_\mu^a(x)}.
$$

At linear order, this means

$$
S[A]=S[0]+\int d^dx\,A_\mu^a j_a^\mu+O(A^2).
$$

The $O(A^2)$ terms are not optional decoration. They are often required by background gauge invariance.

For a complex scalar of charge $q$, the background-coupled action is obtained by replacing

$$
\partial_\mu\phi\longrightarrow D_\mu\phi=(\partial_\mu-iqA_\mu)\phi.
$$

Expanding the kinetic term gives

$$
(D_\mu\phi)^*(D^\mu\phi)
=\partial_\mu\phi^*\partial^\mu\phi
+A_\mu j^\mu
+q^2A_\mu A^\mu\phi^*\phi,
$$

where

$$
j^\mu=iq\left(\phi^*\partial^\mu\phi-\partial^\mu\phi^*\phi\right).
$$

The quadratic term in $A$ is part of the source coupling. If one kept only $A_\mu j^\mu$, the background-field theory would not be gauge invariant.

:::note[Source note]
The sign of the current in this example follows from $D_\mu=\partial_\mu-iqA_\mu$ and $S[A]=S[0]+\int A_\mu j^\mu+O(A^2)$. References using $D_\mu=\partial_\mu+iqA_\mu$ or $Z=e^{-W_E}$ will display corresponding sign changes.
:::

### Background metric

The background metric is the source for the stress tensor. Schematically,

$$
\delta W[g]
=\frac12\int d^dx\,\sqrt{|g|}\,
\langle T^{\mu\nu}\rangle_g\,\delta g_{\mu\nu}.
$$

Equivalently, in this convention,

$$
\langle T^{\mu\nu}(x)\rangle_g
=\frac{2}{\sqrt{|g|}}\frac{\delta W[g]}{\delta g_{\mu\nu}(x)}.
$$

Some references vary $g^{\mu\nu}$ instead of $g_{\mu\nu}$ and therefore differ by a sign and index placement. In Lorentzian signature one also has to choose $\sqrt{-g}$ versus $\sqrt{|g|}$ notation. Later stress-tensor pages will restate the metric convention before using it.

The metric source is the correct home for stress-tensor contact terms, trace anomalies, gravitational anomalies, and response to curvature. It is also the clean way to define $T^{\mu\nu}$ for theories where the canonical stress tensor is not the most useful object.

## Source counterterms and contact terms

The functional $W[J,A,g]$ is not unique. One may add local functionals of the sources,

$$
W[J,A,g]\longrightarrow W[J,A,g]+W_{\mathrm{ct}}[J,A,g],
$$

without changing separated-point physics. Examples include

$$
\int d^dx\,J^2,
\qquad
\int d^dx\,F_{\mu\nu}F^{\mu\nu},
\qquad
\int d^dx\,\sqrt{|g|}\,R^2.
$$

Differentiating such terms produces contact terms. For example,

$$
\frac{\delta^2}{\delta J(x)\delta J(y)}\int d^dz\,J(z)^2
=2\delta^{(d)}(x-y).
$$

This is why contact terms are often scheme-dependent. They are real parts of the local QFT data, but not all of them are invariant under changes of source counterterms.

An anomaly is different. A genuine anomaly is a local variation of $W$ that cannot be removed by adding a local counterterm compatible with the required structures. This distinction becomes central in the anomaly chapters.

## Background transformations and Ward identities

Let $A$ be a background gauge field for a global symmetry group $G$. In the conventions of this volume,

$$
A\longrightarrow A^g=gAg^{-1}+ig\,dg^{-1}.
$$

Infinitesimally, with $g=e^{i\lambda}$,

$$
\delta_\lambda A=D\lambda=d\lambda-i[A,\lambda].
$$

If the nonanomalous theory also has sources $J^i$ for operators $\mathcal O_i$, then the sources must transform contragrediently so that the source term $J^i\mathcal O_i$ is invariant. The functional statement of symmetry is

$$
W[A,J]=W[A+\delta_\lambda A,J+\delta_\lambda J].
$$

Expanding gives

$$
0=\int d^dx\,
\frac{\delta W}{\delta A_\mu^a}\delta_\lambda A_\mu^a
+\int d^dx\,
\frac{\delta W}{\delta J^i}\delta_\lambda J^i.
$$

Using

$$
\frac{\delta W}{\delta A_\mu^a}=\langle j_a^\mu\rangle_{A,J},
\qquad
\frac{\delta W}{\delta J^i}=\langle\mathcal O_i\rangle_{A,J},
$$

and integrating by parts produces the Ward identity in the presence of sources. Its precise sign depends on the representation convention for $J^i$, but its structure is universal:

$$
D_\mu\langle j_a^\mu\rangle_{A,J}
=\text{source terms from the transformation of }J.
$$

Now differentiate this equation with respect to $J$ and set $J=0$. The source terms become the contact terms telling the current how to act on operator insertions. In this way, the background-field identity packages the local Ward identities of the previous chapter.

If the theory has an anomaly, the functional identity becomes

$$
\delta_\lambda W[A,J]
=\int_{M_d}\lambda^a\mathcal A_a[A,J].
$$

Then the Ward identity has an additional local term. Whether that term is removable by a counterterm is the central question of anomaly theory.

## Spurions and explicit breaking

A spurion is a source assigned an artificial transformation law. The point is not to pretend the symmetry is really unbroken. The point is to keep track of how it is broken.

For example, suppose a theory with fermions has a mass matrix $M$ and would have a larger flavor symmetry if $M=0$. One may assign $M$ a transformation law so that the mass term is formally invariant. Then all low-energy terms must be built from fields and $M$ in invariant combinations.

This trick is extremely useful in effective field theory. It tells you which symmetry-breaking operators are allowed and how their coefficients depend on the symmetry-breaking parameters. In QCD, treating the quark mass matrix as a spurion is the efficient way to organize chiral perturbation theory.

Spurions are also useful in anomaly discussions. A parameter that transforms under a symmetry can sometimes cancel the variation of another term. This is the seed of Green–Schwarz-like mechanisms, axion couplings, and Wess–Zumino terms.

## Background fields versus dynamical fields

A background field is held fixed when computing $Z[A]$:

$$
Z[A]=\int\mathcal D\Phi\,e^{iS[\Phi;A]}.
$$

A dynamical field is integrated over:

$$
Z_{\mathrm{gauge}}
=\int\frac{\mathcal DA}{\mathrm{gauge}}\int\mathcal D\Phi\,e^{iS[\Phi,A]}.
$$

That fraction symbol hides serious work: gauge fixing, BRST or another definition of the quotient, a choice of bundles, boundary conditions, and topological sectors.

The conceptual difference is just as important as the technical difference. A background gauge transformation is a redundancy of the description of sources and charged operators together. A dynamical gauge transformation is a redundancy among field configurations being summed over. Confusing these two is one of the fastest ways to misread anomaly statements.

## Example dictionary

Here are common source couplings in QFT.

| Operator or response | Source | Typical variation |
|---|---|---|
| Scalar operator $\mathcal O$ | Scalar source $J$ | $\delta W/\delta J=\langle\mathcal O\rangle$ |
| Conserved current $j_a^\mu$ | Background gauge field $A_\mu^a$ | $\delta W/\delta A_\mu^a=\langle j_a^\mu\rangle$ |
| Stress tensor $T^{\mu\nu}$ | Metric $g_{\mu\nu}$ | $2\delta W/\delta g_{\mu\nu}\sim\langle T^{\mu\nu}\rangle$ |
| Marginal operator $\mathcal O_I$ | Coupling $\lambda^I(x)$ | Local RG and conformal perturbation theory |
| Relevant operator | Mass or deformation parameter | RG flows and order parameters |
| One-form symmetry current | Two-form background $B_2$ | Surface operators and line-operator selection rules |
| Finite symmetry | Flat bundle or cochain | Orbifolds, twisted sectors, and discrete anomalies |

The last two entries are previews. Higher-form and finite symmetries require background fields that are not simply one-form gauge potentials for Noether currents.

## Common pitfalls

**“The source is physical, so I should integrate over it.”** Not unless you are gauging or otherwise making it dynamical. A source is usually held fixed and varied only to generate insertions.

**“The current coupling is always just $A_\mu j^\mu$.”** That is only the linear term. The full background coupling can contain $A^2$ terms, curvature terms, and local counterterms required by covariance or gauge invariance.

**“Contact terms are mistakes.”** They are the functional derivatives of local source terms. Some are scheme-dependent, but Ward identities are wrong without them.

**“Background gauge invariance means the theory has a gauge redundancy.”** No. Background gauge invariance is a property of how sources and charged operators are described. A dynamical gauge redundancy appears only after one sums over gauge fields and quotients by gauge transformations.

**“An anomalous background variation means the theory is inconsistent.”** Only if the anomalous field is dynamical. For a global symmetry background, the anomalous variation is an ’t Hooft anomaly: physical, useful, and RG-invariant.

**“The source uniquely defines the operator.”** Composite operators mix under renormalization. Specifying a source scheme is part of specifying the renormalized operator, especially at coincident points.

## Relations to other pages

- [Noether Currents](/symmetry-anomalies-topology/noether-currents-ward-identities/noether-currents/) explains how a current is extracted by localizing a continuous symmetry parameter.
- [Improved Currents and Ambiguities](/symmetry-anomalies-topology/noether-currents-ward-identities/improved-currents-and-ambiguities/) explains why currents are not unique before one specifies a background coupling.
- [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/) derives the same functional identity by changing variables in the path integral.
- [Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/) explains the distributional terms produced by differentiating source-space Ward identities.
- The next page, Background Fields for Global Symmetries, specializes this source language to background gauge fields for internal symmetries.
- Later anomaly pages use $\delta_\lambda W[A]$ as the definition of the anomaly functional.

## Research status

For ordinary local operators, Noether currents, and stress tensors, the source formalism is standard. The main subtlety is not whether sources exist, but how much of the local contact-term data is scheme-dependent.

For gauge and gravitational anomalies, background fields are the modern standard diagnostic. The hard work is identifying which local variations can be removed by counterterms and which define genuine anomaly classes.

For higher-form, subsystem, non-invertible, and categorical symmetries, “background field” can mean higher gauge fields, topological defects, bulk topological field theories, or categorical data rather than an ordinary one-form connection. Those refinements are active research topics and will be treated with more care in later chapters.

## Exercises

### Exercise 1: Connected two-point function from $W$

Let

$$
Z[J]=\int\mathcal D\Phi\,e^{iS+i\int J\mathcal O}=e^{iW[J]}.
$$

Show that

$$
\frac{\delta^2 W}{\delta J(x)\delta J(y)}\bigg|_{J=0}
=i\langle\mathcal O(x)\mathcal O(y)\rangle_{\mathrm{conn}}.
$$

<details>
<summary><strong>Solution</strong></summary>

First,

$$
\frac{\delta W}{\delta J(x)}=\langle\mathcal O(x)\rangle_J.
$$

Differentiate again. The derivative of the expectation value brings down $i\mathcal O(y)$ from the exponential and subtracts the derivative of the normalization. Therefore

$$
\frac{\delta}{\delta J(y)}\langle\mathcal O(x)\rangle_J
=i\left(\langle\mathcal O(x)\mathcal O(y)\rangle_J
-\langle\mathcal O(x)\rangle_J\langle\mathcal O(y)\rangle_J\right).
$$

Setting $J=0$ gives the connected correlator with the displayed factor of $i$.

</details>

### Exercise 2: Why the $A^2$ term is needed

For a charged scalar with

$$
D_\mu\phi=(\partial_\mu-iqA_\mu)\phi,
$$

expand $(D_\mu\phi)^*(D^\mu\phi)$ and identify the terms linear and quadratic in $A$.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
(D_\mu\phi)^*=\partial_\mu\phi^*+iqA_\mu\phi^*.
$$

Then

$$
\begin{aligned}
(D_\mu\phi)^*(D^\mu\phi)
&=(\partial_\mu\phi^*+iqA_\mu\phi^*)
(\partial^\mu\phi-iqA^\mu\phi)\\
&=\partial_\mu\phi^*\partial^\mu\phi
+iqA_\mu\phi^*\partial^\mu\phi
-iqA_\mu(\partial^\mu\phi^*)\phi
+q^2A_\mu A^\mu\phi^*\phi.
\end{aligned}
$$

The linear term is $A_\mu j^\mu$ with

$$
j^\mu=iq(\phi^*\partial^\mu\phi-\partial^\mu\phi^*\phi),
$$

and the quadratic term is $q^2A_\mu A^\mu\phi^*\phi$. Keeping the linear term alone would not reproduce the covariant kinetic term.

</details>

### Exercise 3: A local counterterm creates a contact term

Let

$$
W_{\mathrm{ct}}[J]=c\int d^dz\,J(z)^2.
$$

Compute its contribution to the two-point function generated by $\delta^2 W/\delta J(x)\delta J(y)$.

<details>
<summary><strong>Solution</strong></summary>

Differentiate once:

$$
\frac{\delta W_{\mathrm{ct}}}{\delta J(x)}=2cJ(x).
$$

Differentiate again:

$$
\frac{\delta^2 W_{\mathrm{ct}}}{\delta J(x)\delta J(y)}=2c\delta^{(d)}(x-y).
$$

This contributes only at coincident points. It is a contact term controlled by the local source counterterm.

</details>

### Exercise 4: Background variation gives a Ward identity

Assume a $U(1)$ background field transforms as $\delta_\lambda A_\mu=\partial_\mu\lambda$ and the nonanomalous functional satisfies $\delta_\lambda W[A]=0$ on a spacetime without boundary. Show that $\partial_\mu\langle j^\mu\rangle_A=0$.

<details>
<summary><strong>Solution</strong></summary>

Using $\langle j^\mu\rangle_A=\delta W/\delta A_\mu$,

$$
0=\delta_\lambda W[A]
=\int d^dx\,\langle j^\mu(x)\rangle_A\partial_\mu\lambda(x).
$$

Integrating by parts and dropping boundary terms gives

$$
0=-\int d^dx\,\lambda(x)\partial_\mu\langle j^\mu(x)\rangle_A.
$$

Since $\lambda(x)$ is arbitrary,

$$
\partial_\mu\langle j^\mu(x)\rangle_A=0.
$$

In the presence of charged operator sources or anomalies, the right-hand side is modified by source terms or anomaly terms.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §22. Compact source for currents, continuous symmetries, and current Ward identities.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 16. Standard reference for external-field methods and effective actions.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters 14 and 34. Useful for generating functionals, Schwinger–Dyson/Ward–Takahashi identities, and background-field methods.
- Sidney Coleman, *Aspects of Symmetry*. Classic reference for current algebra, Ward identities, soft-pion reasoning, and symmetry-breaking source logic.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Detailed functional-source treatment of field theory, renormalization, and composite operators.
- C. P. Burgess, *Introduction to Effective Field Theory*. Useful for spurions, symmetry breaking, and EFT source logic.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.” Modern reference for background fields and gauging in generalized symmetry.

## Version history

- **2026-06-17:** Initial polished page on sources and background fields.
