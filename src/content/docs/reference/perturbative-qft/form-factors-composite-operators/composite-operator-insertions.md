---
title: "Composite Operator Insertions"
description: "How local composite operators are inserted into perturbative Green functions, how source vertices are assigned, and why operator renormalization and contact terms matter."
sidebar:
  label: "Composite Operator Insertions"
  order: 1
level: Graduate
status: "Polished draft"
source: "Collins; Weinberg, Vols. I–II; Srednicki, perturbation theory and renormalization chapters; Zinn-Justin, functional and operator-renormalization chapters; Schwartz, renormalized perturbation theory and unitarity chapters."
topics:
  - composite operators
  - operator insertions
  - source methods
  - operator renormalization
  - contact terms
canonicalTopics:
  - composite-operator-insertions
  - local-operator-sources
  - operator-renormalization
  - insertion-vertices
researchStatus:
  established:
    - "Composite-operator insertions, source differentiation, contact terms, and operator mixing are standard parts of perturbative QFT and renormalized perturbation theory."
  active:
    - "In gauge theories and effective field theories, operator bases, scheme choices, evanescent operators, equations-of-motion operators, and mixing matrices remain active technical areas."
---

## Summary

A **composite operator** is a local product of fields and derivatives evaluated at the same spacetime point. Examples include

$$
\phi^2(x),
\qquad
\overline\psi(x)\gamma^\mu\psi(x),
\qquad
F_{\mu\nu}(x)F^{\mu\nu}(x),
\qquad
T^{\mu\nu}(x).
$$

Composite operators are the local probes of QFT. They define currents, stress tensors, densities, order parameters, effective-field-theory interactions, Wilson-coefficient bases, form factors, and the short-distance operators that appear in the operator product expansion.

The perturbative way to insert a local operator $\mathcal O_a(x)$ is to couple it to a source $K_a(x)$,

$$
S \longmapsto S+\int d^4x\,K_a(x)\mathcal O_a(x),
$$

then differentiate the generating functional with respect to $K_a$. Diagrammatically, this produces a special local vertex: an **operator insertion**. It is drawn like an interaction vertex, but it is not automatically an interaction in the Hamiltonian and it is not automatically an external particle.

<figure class="doc-figure" style="--figure-width: 48rem; --caption-width: 54rem;">

![Composite operator insertion as a local source vertex carrying momentum into a Green function](/figures/perturbative-qft/composite-operator-insertions.svg)

<figcaption>

A composite operator insertion is a local vertex associated with a source derivative. The source momentum $q$ and the line momenta meeting the insertion obey one momentum-conservation delta function. The insertion is local, but it need not correspond to a new asymptotic particle.

</figcaption>
</figure>

The central caveat is that products of fields at the same point are singular. In an interacting continuum theory, a composite operator usually needs its own renormalization and can mix with other operators carrying the same quantum numbers. That is not a minor footnote; it is the reason operator bases, anomalous dimensions, contact terms, and scheme dependence appear throughout modern perturbative QFT.

## Prerequisites

You should know [Generating Functional Diagrams](/perturbative-qft/diagrammatics-feynman-rules/generating-functional-diagrams/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Vertices and Propagators](/perturbative-qft/diagrammatics-feynman-rules/vertices-and-propagators/), [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/), [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/), and [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/).

For later uses, it helps to know [LSZ Reduction](/perturbative-qft/from-correlators-to-s-matrix/lsz-reduction/) and [Amputated Correlators](/perturbative-qft/from-correlators-to-s-matrix/amputated-correlators/), because form factors are obtained by applying LSZ to Green functions with one operator insertion.

## Core idea

Ordinary perturbation theory answers questions like: what happens when fields interact through terms already present in the action? Composite-operator insertions answer a slightly different question:

```txt
What is the response of the theory to a local probe?
```

A source $K(x)$ coupled to $\mathcal O(x)$ lets us probe that response. For example, if $\mathcal O=J^\mu$ is a conserved current, $K_\mu$ is an external gauge-like source. If $\mathcal O=T^{\mu\nu}$ is the stress tensor, $K_{\mu\nu}$ is related to a background metric perturbation. If $\mathcal O=\phi^2$ is a scalar density, $K$ probes how the theory responds to a local mass deformation.

There are three levels of meaning that should not be mixed:

| Object | What it means |
|---|---|
| local operator $\mathcal O(x)$ | a field-theoretic observable or local probe |
| source term $\int K\mathcal O$ | a device for generating insertions or coupling to a background |
| dynamical interaction term | part of the action being integrated over or used in the S-matrix |

The same expression may play more than one role in different contexts. The operator $\phi^4/4!$ is a composite operator when used as a probe, but $-\lambda\phi^4/4!$ is an interaction term when it appears in the Lagrangian. The difference is not pedantry. It changes which coupling factors and which source derivatives appear in the diagrammatic rules.

## Setup and conventions

We use the site-wide perturbative QFT conventions. The scalar examples below use

$$
\mathcal L
=
\frac12\partial_\mu\phi\,\partial^\mu\phi
-
\frac12m^2\phi^2
-
\frac{\lambda}{4!}\phi^4.
$$

For a set of local operators $\mathcal O_a$, introduce sources $K_a$ by

$$
Z[J,K]
=
\frac{1}{\mathcal N}
\int\mathcal D\phi\,
\exp\left\{
 iS[\phi]
 +i\int d^4x\,J(x)\phi(x)
 +i\int d^4x\,K_a(x)\mathcal O_a(x)
\right\}.
$$

Then

$$
\left.\frac{1}{i}\frac{\delta Z[J,K]}{\delta K_a(x)}\right|_{K=0}
$$

inserts $\mathcal O_a(x)$ into the source-generated correlation functions. For connected correlators, use $W=-i\log Z$ instead of $Z$.

A momentum-space insertion carries one momentum-conservation delta function. If all momenta are drawn as entering the insertion, the reduced insertion vertex is accompanied by

$$
(2\pi)^4\delta^{(4)}\!\left(q+\sum_i p_i\right),
$$

where $q$ is the source momentum and $p_i$ are the momenta carried by the fields attached to the insertion. Other sign conventions are common. What matters is to state which momentum is being assigned to the source and then keep the delta function consistent.

## Source vertices versus operator insertions

A source-coupled term in the exponent contributes an interaction-like factor. For

$$
\Delta S_K=\int d^4x\,K(x)\frac{\phi(x)^2}{2},
$$

the source vertex in the expanded path integral carries a factor $iK$ times the combinatorial factor coming from $\phi^2/2$. After differentiating with $(1/i)\delta/\delta K$, the local operator insertion itself has the two-scalar insertion rule

$$
\frac{\phi^2}{2}\quad \leadsto \quad 1
$$

for the two scalar legs attached to that operator.

This distinction is useful enough to state explicitly:

| Calculation | Local factor |
|---|---|
| source vertex inside $\exp(i\int K\mathcal O)$ | $i$ times the operator polynomial, with $K$ included |
| differentiated operator insertion | the operator polynomial, with $K$ removed |
| interaction term in $\mathcal L_{\rm int}$ | the usual interaction vertex, including the coupling and sign from the action |

For the interaction $\mathcal L_{\rm int}=-\lambda\phi^4/4!$, the quartic scattering vertex is $-i\lambda$. For the inserted operator $\mathcal O=\phi^4/4!$, the four-scalar insertion rule is $1$. These are different questions, even though the monomial is the same.

## Elementary insertion rules

For scalar operators built from $\phi$ and derivatives, insertion rules are obtained by Fourier transforming the fields and applying the derivatives. With the site-wide Fourier convention, a derivative acting on a field of incoming momentum $p$ contributes $-ip_\mu$.

For a single local insertion with all scalar momenta entering the insertion, the simplest tree-level rules are:

| Inserted operator | Attached scalar legs | Insertion polynomial |
|---|---:|---:|
| $\phi$ | 1 | $1$ |
| $\phi^2/2$ | 2 | $1$ |
| $\phi^3/3!$ | 3 | $1$ |
| $\phi^4/4!$ | 4 | $1$ |
| $\partial_\mu\phi\,\partial^\mu\phi/2$ | 2 | $-p_1\cdot p_2$ |
| $\phi\Box\phi/2$ | 2 | $-p_2^2/2-p_1^2/2$ after symmetrizing |

The factorials in the operator definition are chosen so that the Wick-contraction multiplicities cancel in the same way they do for ordinary scalar interaction vertices.

For fields with spin, gauge indices, or flavor indices, the insertion polynomial carries the corresponding tensor structure. For example, the Dirac bilinear

$$
\mathcal O^\mu(x)=\overline\psi(x)\gamma^\mu\psi(x)
$$

has a two-fermion insertion carrying $\gamma^\mu$ with spinor indices contracted along the fermion line. If the same bilinear appears as a QED interaction $-e\overline\psi\gamma^\mu A_\mu\psi$, the photon vertex instead carries the usual coupling and factor from the interaction term.

## Worked example: the φ² insertion

Consider the free scalar theory and the operator

$$
\mathcal O(y)=\frac{1}{2}\phi(y)^2.
$$

The connected three-point object with one insertion and two elementary fields is

$$
G_{\mathcal O,2}(y;x_1,x_2)
=
\left\langle0\middle|T\left\{\frac12\phi(y)^2\phi(x_1)\phi(x_2)\right\}\middle|0\right\rangle_{\rm conn}.
$$

There are two contractions connecting the two fields at $y$ to $x_1$ and $x_2$. The factor $1/2$ cancels this factor of $2$, so

$$
G_{\mathcal O,2}(y;x_1,x_2)
=
D_F(y-x_1)D_F(y-x_2).
$$

In momentum space, the corresponding reduced insertion is just $1$. The full expression still contains the momentum-conservation delta function at the insertion.

This example is boring in exactly the right way. It shows the basic rule before loops, counterterms, or operator mixing complicate the story.

## Integrated insertions from differentiating couplings

An insertion can also be generated by differentiating with respect to a coupling. In scalar $\phi^4$ theory,

$$
\frac{\partial S}{\partial\lambda}
=
-\int d^4x\,\frac{\phi(x)^4}{4!}.
$$

For a normalized correlation function, differentiating with respect to $\lambda$ inserts the interaction monomial and subtracts the disconnected vacuum response. Schematically,

$$
\frac{\partial}{\partial\lambda}
\langle T\{\Phi\}\rangle
=
-i\int d^4x\,
\left\langle T\left\{\frac{\phi(x)^4}{4!}\Phi\right\}\right\rangle_{\rm conn\;to\;\Phi},
$$

where $\Phi$ denotes the product of external fields. The phrase “connected to $\Phi$” reminds us that vacuum bubbles cancel in normalized correlators.

This is the perturbative origin of many useful identities. Differentiating with respect to a mass inserts $-\phi^2/2$ in the action. Differentiating with respect to a background metric inserts the stress tensor. Differentiating with respect to a background gauge field inserts a current.

## Renormalization and mixing

Composite operators are usually more singular than elementary fields because their fields meet at one point. In a regulated theory, introduce bare operators $\mathcal O_i^B$ and renormalized operators $\mathcal O_i^R$ by

$$
\mathcal O_i^B
=
Z_{ij}\,\mathcal O_j^R.
$$

The matrix $Z_{ij}$ is generally not diagonal. Operators with the same quantum numbers can mix. In an effective field theory, this is the familiar statement that the operator basis renormalizes as a basis, not as a list of isolated monomials.

The associated anomalous-dimension matrix is

$$
\gamma
=
Z^{-1}\mu\frac{dZ}{d\mu},
$$

so that the renormalized operators obey

$$
\mu\frac{d}{d\mu}\mathcal O_i^R
=
-\gamma_{ij}\mathcal O_j^R.
$$

The minus sign is a consequence of holding the bare operator fixed while changing the renormalization scale.

Operator mixing is constrained by symmetries and dimensions. A scalar $Z_2$-even operator can mix only with scalar $Z_2$-even operators. A vector current can mix only with operators carrying the same Lorentz and internal quantum numbers. In a mass-independent scheme such as minimal subtraction, mixing is often triangular when operators are ordered by canonical dimension, up to subtleties from total derivatives, equations of motion, and evanescent operators.

### Identity, total derivatives, and equations of motion

Three special classes deserve early warning.

The **identity operator** can mix with scalar operators through vacuum divergences. This matters for vacuum energy, pressure, trace anomalies, and thermodynamic quantities.

**Total derivatives** do not affect zero-momentum integrated matrix elements between momentum eigenstates, but they do affect off-forward matrix elements and operator bases with momentum transfer.

**Equations-of-motion operators** can vanish inside some on-shell matrix elements but still matter in off-shell Green functions, renormalization, and basis reduction. Dropping them too early is a classic EFT foot-gun.

## Contact terms

Composite insertions can collide with other local fields. When $x$ approaches one of the field points $x_i$, the time-ordered product can develop contact terms supported on delta functions such as $\delta^{(4)}(x-x_i)$.

These terms are not always nuisances. They are essential in Ward identities. For a symmetry current $J^\mu$, the local Ward identity has the schematic form

$$
\partial_\mu\left\langle T\{J^\mu(x)\Phi_1(x_1)\cdots\Phi_n(x_n)\}\right\rangle
=
\text{contact terms from the symmetry variation of the }\Phi_i,
$$

possibly plus anomaly terms. Without the contact terms, the integrated charge would not act correctly on local operators.

Contact terms are also scheme dependent. Changing the renormalization prescription for a local operator can change terms supported at coincident points without changing separated-point physics. This is one reason local composite-operator equations should specify whether they are meant inside separated correlators, integrated matrix elements, or distributional identities.

## Insertions in 1PI language

A useful object is the one-particle-irreducible vertex with one operator insertion. Starting from $W[J,K]$, perform the Legendre transform with respect to the elementary source $J$ but not necessarily with respect to $K$. Differentiating the effective action with respect to $K$ gives 1PI vertices with one insertion of $\mathcal O$.

For example,

$$
\Gamma_{\mathcal O}^{(n)}(x;y_1,\ldots,y_n)
=
\left.
\frac{\delta^{n+1}\Gamma[\varphi,K]}
{\delta K(x)\delta\varphi(y_1)\cdots\delta\varphi(y_n)}
\right|_{K=0,\varphi=0}
$$

is the 1PI insertion vertex with $n$ elementary external fields. This object is often the right language for renormalizing local operators, computing anomalous dimensions, and matching EFT operator coefficients.

It is also the bridge to form factors: attach external propagators to get Green functions with an insertion, or amputate and put external legs on shell to get matrix elements of the local operator.

## Common pitfalls

**Treating an insertion as a new particle.** A local operator insertion is a local probe. It can be coupled to a background source, and that source can sometimes be promoted to a dynamical field, but the operator insertion itself is not automatically an asymptotic particle.

**Using interaction vertex factors for operator insertions.** The operator $\phi^4/4!$ and the interaction $-\lambda\phi^4/4!$ produce different local factors. The latter includes the coupling and the sign from the action.

**Assuming normal ordering renormalizes everything.** Normal ordering removes a particular class of free-field contractions. It is not a general replacement for composite-operator renormalization in an interacting theory.

**Ignoring contact terms.** Ward identities, stress tensors, current algebra, and OPEs all depend on contact terms. Dropping them can make exact symmetry statements look false.

**Diagonalizing the operator basis too early.** Operators usually mix. The meaningful object may be an anomalous-dimension matrix, not a single anomalous dimension.

**Dropping equations-of-motion operators without saying where.** They can be redundant for on-shell S-matrix elements but relevant for off-shell correlators, matching, and renormalization.

## Relations to other pages

- [Generating Functional Diagrams](/perturbative-qft/diagrammatics-feynman-rules/generating-functional-diagrams/) explains source differentiation for ordinary fields.
- [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) explains how local counterterm vertices appear in diagrams.
- [Renormalized Amplitudes](/perturbative-qft/renormalized-perturbation-theory/renormalized-amplitudes/) explains how renormalized diagrams combine into finite physical amplitudes.
- [Form Factors](/perturbative-qft/form-factors-composite-operators/form-factors/) applies LSZ to operator-insertion Green functions.
- [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/) is an example where current insertions and contact terms enforce gauge invariance.
- [Callan–Symanzik Preview](/perturbative-qft/renormalized-perturbation-theory/callan-symanzik-preview/) explains how anomalous dimensions enter scale dependence.

## Research status

**Established.** Source methods, insertion vertices, operator mixing, contact terms, and anomalous dimensions are standard tools in perturbative QFT, EFT, current algebra, and renormalized perturbation theory.

**Active.** In modern EFT and gauge theory, constructing nonredundant operator bases, handling evanescent operators, tracking scheme dependence, and computing high-loop anomalous-dimension matrices are active technical subjects.

**Convention-dependent.** The factors of $i$ assigned to a source vertex depend on whether one is discussing the source-coupled action, the differentiated operator insertion, a Euclidean generating functional, or an interaction vertex. This page has separated those roles to minimize confusion.

## Exercises

### Exercise 1: Free scalar φ² insertion

In the free real scalar theory, compute the connected correlator

$$
\left\langle0\middle|T\left\{\frac12\phi(y)^2\phi(x_1)\phi(x_2)\right\}\middle|0\right\rangle_{\rm conn}.
$$

<details>
<summary><strong>Solution</strong></summary>

The two fields at $y$ must contract with the external fields at $x_1$ and $x_2$. There are two Wick contractions,

$$
\phi(y)_1\to\phi(x_1),\qquad \phi(y)_2\to\phi(x_2),
$$

and the same contraction with $x_1$ and $x_2$ interchanged. The factor $1/2$ in the operator cancels this multiplicity. Therefore

$$
\left\langle0\middle|T\left\{\frac12\phi(y)^2\phi(x_1)\phi(x_2)\right\}\middle|0\right\rangle_{\rm conn}
=
D_F(y-x_1)D_F(y-x_2).
$$

</details>

### Exercise 2: Coupling differentiation

For

$$
\mathcal L_{\rm int}=-\frac{\lambda}{4!}\phi^4,
$$

show why differentiating a normalized correlator with respect to $\lambda$ inserts $-i\int d^4x\,\phi^4(x)/4!$, keeping only the part connected to the original external fields.

<details>
<summary><strong>Solution</strong></summary>

In the path integral,

$$
\frac{\partial}{\partial\lambda}e^{iS}
=
i\frac{\partial S}{\partial\lambda}e^{iS}
=
-i\int d^4x\,\frac{\phi(x)^4}{4!}e^{iS}.
$$

For an unnormalized numerator, this inserts the integrated operator into every diagram. For a normalized correlator, the derivative also acts on the denominator $Z[0]$. That subtraction cancels the vacuum diagrams disconnected from the original external fields. The surviving contribution is the insertion connected to the correlator being differentiated.

</details>

### Exercise 3: Symmetry restriction on mixing

In a theory with a $Z_2$ symmetry $\phi\mapsto-\phi$, explain why $\phi^2$ can mix with the identity operator but not with $\phi$.

<details>
<summary><strong>Solution</strong></summary>

The operator $\phi^2$ is even under $Z_2$, and the identity operator is also even. Therefore symmetry does not forbid mixing between them. The operator $\phi$ is odd under $Z_2$. A counterterm proportional to $\phi$ would violate the $Z_2$ symmetry, so it is forbidden as long as the regulator and renormalization prescription preserve the symmetry.

</details>

### Exercise 4: Derivative insertion rule

Using $\partial_\mu e^{-ip\cdot x}=-ip_\mu e^{-ip\cdot x}$, derive the two-scalar insertion polynomial for

$$
\mathcal O(x)=\frac12\partial_\mu\phi(x)\partial^\mu\phi(x).
$$

<details>
<summary><strong>Solution</strong></summary>

Attach two incoming scalar momenta $p_1$ and $p_2$ to the insertion. Each derivative acting on a field contributes $-ip_\mu$. The two possible assignments of the two fields cancel the factor $1/2$. Thus the insertion polynomial is

$$
(-ip_1)_\mu(-ip_2)^\mu
=
-p_1\cdot p_2.
$$

</details>

## References

- J. Collins, *Renormalization*, for composite-operator renormalization, operator mixing, and scheme dependence.
- S. Weinberg, *The Quantum Theory of Fields*, Vols. I–II, for external fields, currents, renormalized operators, and operator product methods.
- M. Srednicki, *Quantum Field Theory*, for perturbation theory, counterterms, currents, and renormalized Green functions.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for generating functionals, vertex functions, renormalized operators, and short-distance expansions.
- M. Schwartz, *Quantum Field Theory and the Standard Model*, for renormalized perturbation theory, Ward identities, unitarity, and operator-based applications.

## Version history

- **2026-06-13:** Initial polished draft for QFT.org, separating source vertices, differentiated insertions, renormalized composite operators, and contact terms.
