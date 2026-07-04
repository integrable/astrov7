---
title: "Local Operators as Observables"
description: "Explains how local operators function as the observable probes of a conformal field theory, how they are normalized, and why they replace particles as the central objects of CFT."
sidebar:
  label: "Local Operators as Observables"
  order: 4
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Rychkov 2017; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019"
topics:
  - local operators
  - observables
  - correlation functions
  - sources
  - composite operators
  - scaling operators
  - order parameters
  - gauge-invariant operators
  - operator product expansion
canonicalTopics:
  - local-operators-as-observables
  - local-operator-spectrum
  - correlation-functions-as-observables
  - composite-operator-renormalization
  - cft-data
researchStatus:
  established:
    - "Local gauge-invariant operators and their separated-point correlation functions are the basic local observables of an ordinary CFT."
    - "At a conformal fixed point, local operators can be organized into scaling operators, and in a conformal theory into primary operators and descendants."
  active:
    - "Modern CFT increasingly studies extended operators, defects, generalized symmetries, and nonlocal observables alongside the local operator algebra."
---

## Summary

Local operators are the basic local probes of a conformal field theory. In a particle-scattering problem one asks for amplitudes between asymptotic particle states. In a CFT one usually asks for correlation functions of local operators:

$$
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle.
$$

These correlation functions are the experimental, numerical, and mathematical observables that the CFT formalism tries to determine.

A local operator is not necessarily a fundamental field in a Lagrangian. It can be a composite operator, an order parameter, a conserved current, the stress tensor, a monopole operator, a chiral primary, or an operator known only abstractly through its quantum numbers. The slogan is

$$
\text{CFT observables are organized by local operators, not by microscopic fields}.
$$

In a conformal theory, local operators can be grouped into conformal multiplets. Primary operators are the independent entries in the local spectrum; descendants are their derivatives, fixed by symmetry. This is why [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/) is usually stated in terms of primary dimensions, spins, symmetry representations, and OPE coefficients.

:::note[The practical test]
If a quantity can be inserted at a point, has well-defined separated-point correlation functions, and transforms in a definite way under the symmetries of the theory, it is a candidate local operator. If it is gauge-dependent, regulator-dependent without renormalization, or only meaningful after attaching a line or surface, extra care is needed.
:::

## Prerequisites

You should know the basic role of [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/) and the convention choices in [Conventions and Notation](/cft-bootstrap/conventions/). It is also useful to have seen local composite operators and source functionals in ordinary QFT.

This page does not require the detailed representation theory of conformal multiplets. Those details are developed in [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/), [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/), and [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/).

## Core idea

A quantum field theory is not only a rule for time evolution. It is also a rule for assigning expectation values to observables. In a local QFT, the most refined observables are local operators, inserted at spacetime points.

In Euclidean signature, the basic object is the collection of Schwinger functions

$$
G_n(x_1,\ldots,x_n)
=
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle.
$$

At separated points, these functions are constrained by conformal symmetry. For example, scalar primary two-point functions take the form

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{C_{ij}}{|x|^{\Delta_i+\Delta_j}}
$$

only if the dimensions match appropriately; in an orthonormal basis this becomes

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{\delta_{ij}}{|x|^{2\Delta_i}}.
$$

The operators are not passive labels. They are the objects multiplied by the OPE:

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k C_{ij}{}^k(x,\partial)\mathcal O_k(0).
$$

Thus a CFT is locally observed through its operator algebra. Correlators are measurements of that algebra.

## Setup and conventions

This page uses Euclidean flat-space notation unless stated otherwise. The coordinate dimension is $d$. Operators are assumed to be renormalized local operators, not bare cutoff-dependent expressions.

A scalar primary operator has scaling dimension $\Delta$ and transforms under a scale transformation $x\mapsto \lambda x$ as

$$
\mathcal O(x)
\mapsto
\lambda^{-\Delta}\mathcal O(\lambda^{-1}x)
$$

in the active convention, or equivalently correlation functions obey the usual covariant scaling law. The sign convention is less important than the invariant statement:

$$
\langle \mathcal O(\lambda x)\mathcal O(0)\rangle
=
\lambda^{-2\Delta}
\langle \mathcal O(x)\mathcal O(0)\rangle.
$$

For real scalar primaries, this volume usually uses the orthonormal two-point convention

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=
\frac{\delta_{ij}}{|x|^{2\Delta_i}}.
$$

If a different normalization is used, OPE coefficients change. Operator normalizations are part of the convention data, not universal physics by themselves.

## What local means

The word “local” has two related meanings.

First, a local operator is supported at one spacetime point. Examples include

$$
\phi(x),\qquad \phi^2(x),\qquad \overline\psi\psi(x),\qquad
J_\mu(x),\qquad T_{\mu\nu}(x),\qquad \operatorname{tr}F_{\mu\nu}F^{\mu\nu}(x).
$$

Second, a local operator is part of a local algebra: products of nearby local operators can be expanded in local operators. This is the OPE.

There is a subtlety hiding here. In continuum QFT, local operators are operator-valued distributions. Their products at exactly coincident points are usually singular. The CFT statements are statements about separated points or about carefully renormalized composite operators.

The safe rule is:

$$
\text{local operator products are first defined at separated points, then expanded as distributions.}
$$

This is why contact terms can matter in Ward identities but are usually invisible in ordinary separated-point bootstrap equations.

## Operators are not always fundamental fields

A Lagrangian may contain fields such as $\phi$, $\psi$, or $A_\mu$. These fields are useful variables, but they are not automatically physical local observables.

| Object | May be a local observable? | Comment |
|---|---:|---|
| Fundamental scalar $\phi$ | Often yes | In scalar CFTs, $\phi$ may be a genuine local operator. |
| Gauge field $A_\mu$ | Usually no | It is gauge-dependent; gauge-invariant operators are physical. |
| Field strength $F_{\mu\nu}$ | Yes in Abelian gauge theory | In non-Abelian theories, traces or gauge-covariant insertions require care. |
| Composite $\phi^2$ | Yes after renormalization | Its scaling dimension is generally not twice that of $\phi$. |
| Stress tensor $T_{\mu\nu}$ | Yes | It implements spacetime symmetries through Ward identities. |
| Wilson line | Not local | It is an extended operator supported on a curve. |
| Disorder or monopole operator | Sometimes yes | It can be local but may be defined by a singular boundary condition or topological construction. |

The last two entries are important. A theory can have physical observables that are not ordinary local expressions in the microscopic fields. Conversely, a microscopic field can fail to be a physical observable because it is gauge-dependent.

This distinction is one reason the conformal bootstrap is powerful. It works directly with operator data and does not require knowing a privileged microscopic set of fields.

## Sources and how operators are measured

One clean way to define a local operator is to couple it to a source. Given a theory with action $S_*$, deform it by

$$
S[J]=S_*+\int d^d x\,J(x)\mathcal O(x).
$$

Then correlation functions are obtained by differentiating the generating functional:

$$
\langle \mathcal O(x_1)\cdots \mathcal O(x_n)\rangle
=
\left.
\frac{\delta^n \log Z[J]}{\delta J(x_1)\cdots \delta J(x_n)}
\right|_{J=0}
$$

up to the sign convention chosen in the Euclidean source term.

This source viewpoint explains several facts at once.

A deformation by a scalar operator changes the theory:

$$
S=S_*+g\int d^d x\,\mathcal O(x).
$$

If $\mathcal O$ has dimension $\Delta$, the coupling has dimension

$$
[g]=d-\Delta.
$$

Thus the same local operator can be both an observable at the fixed point and a direction in theory space. Relevant, irrelevant, and marginal deformations are classified by local operators.

The source viewpoint also explains why currents and the stress tensor are special. A background gauge field $A_\mu$ couples to a conserved current,

$$
\int d^d x\,A_\mu J^\mu,
$$

while a background metric $g_{\mu\nu}$ couples to the stress tensor,

$$
\delta S
=\frac12\int d^d x\,\sqrt g\,T^{\mu\nu}\delta g_{\mu\nu}.
$$

Thus $J_\mu$ and $T_{\mu\nu}$ are the local operators that measure responses to background symmetry fields.

## Scaling operators and mixing

Away from a fixed point, local operators with the same quantum numbers can mix under renormalization. At a fixed point, one tries to choose a basis that diagonalizes dilatations:

$$
D\mathcal O_i=\Delta_i\mathcal O_i.
$$

These are scaling operators. In a conformal theory they further organize into primary operators and descendants.

The distinction matters in examples. In a scalar theory, the bare expression $\phi^2$ is not automatically a scaling operator. It may mix with other operators of the same symmetries, including the identity through additive renormalization. The scaling operator usually denoted $\epsilon$ in the Ising CFT is the renormalized, fixed-point operator that plays the role of the energy density; it is not merely the unrenormalized lattice or continuum expression before taking the scaling limit.

The diagonalization problem is the operator version of finding normal modes. The fixed point supplies the linear operator $D$, and the CFT operator spectrum consists of its eigenoperators.

## Primaries and descendants

A primary operator is a local operator that is not a derivative descendant of another local operator. More precisely, in radial quantization it is annihilated by the special conformal generators at the origin:

$$
[K_\mu,\mathcal O(0)]=0.
$$

Descendants are obtained by acting with translations:

$$
P_{\mu_1}\cdots P_{\mu_n}\mathcal O(0)
\quad\leftrightarrow\quad
\partial_{\mu_1}\cdots\partial_{\mu_n}\mathcal O(0).
$$

The primary is the independent observable; the descendants are its local derivative probes. This is why the CFT spectrum is normally listed by primary operators.

For example, if $\mathcal O$ is a scalar primary, then

$$
\partial_\mu\mathcal O,
\qquad
\partial_\mu\partial_\nu\mathcal O,
\qquad
\partial^2\mathcal O
$$

are local operators too, but their correlation functions are obtained by differentiating those of $\mathcal O$. They are not new CFT data.

## Local operators in gauge theories

In a gauge theory, gauge redundancy is not a physical symmetry. A local physical operator must be gauge-invariant, or else be understood as a gauge-fixed or gauge-covariant auxiliary object rather than a physical observable.

For a non-Abelian gauge theory, typical local gauge-invariant operators include

$$
\operatorname{tr}F_{\mu\nu}F^{\mu\nu},
\qquad
\operatorname{tr}F_{\mu\nu}\widetilde F^{\mu\nu},
\qquad
\overline\psi\psi,
\qquad
\overline\psi\gamma^\mu D_\mu\psi,
$$

with representation indices contracted appropriately. Wilson lines, 't Hooft lines, surface operators, and interfaces are physical probes too, but they are extended operators, not local ones.

Some local operators in gauge theories are not simple polynomials in fields. Three-dimensional gauge theories, for example, can have monopole operators defined by imposing magnetic flux through a small sphere surrounding the insertion. They are local because the insertion is at a point, even though their definition uses a boundary condition rather than an ordinary polynomial in fields.

This is a useful warning: “local” does not mean “elementary expression in the Lagrangian variables.” It means localized insertion with well-defined correlation functions and symmetry transformation properties.

## Order parameters and universality

At a critical point, physically important local operators often arise as scaling limits of lattice observables.

In the Ising universality class, two famous scalar operators are

$$
\sigma
\quad\text{and}\quad
\epsilon.
$$

The spin operator $\sigma$ is the scaling limit of the magnetization density. It is odd under the global $\mathbb Z_2$ symmetry. The energy operator $\epsilon$ is the scaling limit of the local energy-density perturbation. It is even under $\mathbb Z_2$.

Their dimensions determine critical exponents. In $d$ dimensions, if $\epsilon$ is the leading relevant even scalar, then the correlation-length exponent is related to its dimension by

$$
\frac1\nu=d-\Delta_\epsilon.
$$

The important point is that the continuum CFT does not remember every microscopic lattice detail. It remembers the scaling operators and their correlation functions. This is universality in operator language.

## Locality, OPE, and measurement at short distance

The OPE is the statement that local measurements become locally expandable at short distance. For scalar operators,

$$
\mathcal O_i(x)\mathcal O_j(0)
\sim
\sum_k
\lambda_{ijk}|x|^{\Delta_k-\Delta_i-\Delta_j}
\mathcal O_k(0)
+\text{descendants}.
$$

This has a direct physical interpretation. If two detectors are placed very close compared with all other length scales in a correlator, their combined effect can be replaced by a sum of single local probes.

For example, in an Ising-like CFT,

$$
\sigma(x)\sigma(0)
\sim
\frac{1}{|x|^{2\Delta_\sigma}}\mathbf 1
+\lambda_{\sigma\sigma\epsilon}|x|^{\Delta_\epsilon-2\Delta_\sigma}\epsilon(0)
+\cdots.
$$

The identity term says that nearby identical spin probes have a universal singular self-correlation. The $\epsilon$ term says that at the next level of resolution, the nearby pair can excite the local energy-density operator.

The OPE turns local operators into an algebra. The bootstrap asks which such algebras can be consistent.

## Contact terms and separated points

Most CFT formulas are formulas at separated points:

$$
x_i\neq x_j.
$$

At coincident points, distributions can have contact terms supported at $x_i=x_j$. A simple schematic example is

$$
\langle T_{\mu\nu}(x)\mathcal O(y)\mathcal O(z)\rangle
\supset
\delta^{(d)}(x-y)\,\cdots+
\delta^{(d)}(x-z)\,\cdots.
$$

Contact terms are not optional garbage. They encode Ward identities, anomalies, scheme choices, and response to background fields. But they are not usually part of the ordinary separated-point local CFT data used in the simplest bootstrap equations.

A good habit is to ask:

$$
\text{Am I discussing separated-point data, or contact-term data?}
$$

Many apparent contradictions disappear once that question is answered.

## Local operators in the bootstrap

The conformal bootstrap treats local operators as the unknowns of a consistency problem.

The input for a simple scalar bootstrap problem might be:

- a scalar primary $\phi$ of dimension $\Delta_\phi$;
- a list of possible operators in $\phi\times\phi$;
- unitarity or reflection-positivity constraints;
- global-symmetry selection rules;
- crossing symmetry of $\langle \phi\phi\phi\phi\rangle$.

The four-point function can be decomposed into conformal blocks:

$$
\langle \phi\phi\phi\phi\rangle
=
\sum_{\mathcal O\in \phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2
G_{\Delta,\ell}(u,v),
$$

where $u$ and $v$ are cross-ratios, and $G_{\Delta,\ell}$ is the contribution of one primary operator and all of its descendants.

Thus numerical bootstrap is not a search over Lagrangians. It is a search over possible local operator spectra and OPE coefficients.

## Examples

### Free scalar CFT

In $d>2$, the free massless scalar has equation of motion

$$
\partial^2\phi=0
$$

and dimension

$$
\Delta_\phi=\frac{d-2}{2}.
$$

Local operators include normal-ordered composites such as

$$
:\!\phi^2\!:,
\qquad
:\!\phi^4\!:,
\qquad
:\!\partial_\mu\phi\partial^\mu\phi\!:.
$$

The equation of motion makes $\partial^2\phi$ a null descendant rather than an independent operator. This is a first example of how dynamics enters the local operator spectrum.

### Ising CFT

The Ising CFT has a global $\mathbb Z_2$ symmetry. Its low-lying scalar primaries are usually denoted

$$
\sigma\quad\text{and}\quad \epsilon,
$$

with

$$
\sigma\mapsto -\sigma,
\qquad
\epsilon\mapsto \epsilon.
$$

The symmetry forces selection rules such as

$$
\sigma\times\sigma\sim \mathbf 1+\epsilon+\cdots,
\qquad
\sigma\times\epsilon\sim \sigma+\cdots.
$$

The operators are observable because their correlation functions describe universal spin and energy correlations near the critical point.

### Conserved currents

If a CFT has a continuous global symmetry, it has a conserved current

$$
\partial^\mu J_\mu^a=0.
$$

The charge

$$
Q^a=\int_{\Sigma} d\Sigma^\mu\,J_\mu^a
$$

acts on local operators by symmetry transformations. The current itself is a local operator, while the charge is an integrated operator. A local current therefore packages both a local observable and a global generator.

### Stress tensor

The stress tensor is the local operator that measures response to geometry. Its conservation and tracelessness are

$$
\partial^\mu T_{\mu\nu}=0,
\qquad
T^\mu{}_{\mu}=0
$$

at separated points in flat-space CFT, up to anomaly and contact-term qualifications. The stress tensor controls how local operators transform under conformal transformations through Ward identities.

## Common pitfalls

### Confusing fields with observables

A field in a Lagrangian is a coordinate on theory space or field-configuration space. It may or may not define a physical local observable. Gauge fields are the standard trap: $A_\mu$ is useful, but local physical operators must be gauge-invariant.

### Forgetting composite-operator renormalization

The expression $\phi^2(x)$ is singular before renormalization. A local composite operator is not just a product typed at the same point. It is a renormalized insertion with a specified scheme and mixing convention.

### Assuming dimensions add

In an interacting CFT,

$$
\Delta_{\phi^2}\neq 2\Delta_\phi
$$

in general. Composite scaling dimensions include anomalous dimensions and operator mixing.

### Treating descendants as independent data

Descendants are local operators, but their correlation functions are fixed by those of primaries. The independent local CFT data is normally the primary spectrum plus OPE coefficients.

### Ignoring contact terms

Separated-point correlators do not determine every contact term. Ward identities, anomalies, and response coefficients may require contact-term information beyond the simplest bootstrap data.

### Calling every physical observable local

Wilson loops, line defects, interfaces, boundary condition changing operators, and surface defects are observables, but not ordinary bulk local operators. They deserve their own language.

## Relations to other pages

This page is the operator-theoretic companion to [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/). Conformal data tells you what numbers define the theory; this page explains what kind of objects those numbers describe.

For the symmetry organization of local operators, go next to [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/) and [Conformal Multiplets](/cft-bootstrap/operators-states-radial-quantization/conformal-multiplets/). For the algebra of local measurements, go to [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/). For the way local operators determine four-point functions, go to [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) and [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/).

Extended probes belong later in [Boundary, Defect, and Interface CFT](/cft-bootstrap/boundary-defect-interface-cft/) and in the broader symmetry volumes when generalized symmetries are needed.

## Research status

The local operator viewpoint is established. It is the common language of 2D CFT, higher-dimensional CFT, critical phenomena, conformal bootstrap, and AdS/CFT.

Several frontiers extend it. Defect CFT studies local operators living on submanifolds. Generalized global symmetry studies extended charged operators. Non-invertible symmetry and categorical symmetry refine the algebraic structure of topological defect operators. Gauge theories and dualities often reveal local operators that are invisible or non-polynomial in one description but simple in another.

The conservative lesson for this volume is simple: local operator data is central, but it is not the whole universe of observables.

## Exercises

### Exercise 1: Scaling of a two-point function

Let $\mathcal O$ be a scalar scaling operator with

$$
\langle \mathcal O(x)\mathcal O(0)\rangle=\frac{C}{|x|^{2\Delta}}.
$$

Show that this has the correct scaling under $x\mapsto \lambda x$.

<details>
<summary><strong>Solution</strong></summary>

Under $x\mapsto \lambda x$,

$$
\frac{C}{|\lambda x|^{2\Delta}}
=
\lambda^{-2\Delta}\frac{C}{|x|^{2\Delta}}.
$$

This matches the fact that the correlator contains two insertions of an operator of dimension $\Delta$. Each insertion contributes one factor of $\lambda^{-\Delta}$.

</details>

### Exercise 2: Source differentiation

Suppose

$$
Z[J]=\int D\Phi\,e^{-S_*+\int d^d x\,J(x)\mathcal O(x)}.
$$

Show that

$$
\left.\frac{\delta \log Z[J]}{\delta J(x)}\right|_{J=0}
=\langle \mathcal O(x)\rangle.
$$

<details>
<summary><strong>Solution</strong></summary>

Differentiate $Z[J]$:

$$
\frac{\delta Z[J]}{\delta J(x)}
=
\int D\Phi\,\mathcal O(x)e^{-S_*+\int J\mathcal O}.
$$

Then

$$
\frac{\delta \log Z[J]}{\delta J(x)}
=
\frac{1}{Z[J]}\frac{\delta Z[J]}{\delta J(x)}
=\langle \mathcal O(x)\rangle_J.
$$

Setting $J=0$ gives the desired expectation value in the undeformed theory.

If the source term is written with a minus sign instead, the right-hand side acquires the corresponding minus sign. That is a convention, not physics.

</details>

### Exercise 3: Gauge-invariant local operators

In a non-Abelian gauge theory, explain why $A_\mu^a(x)$ is not a physical local observable, while $\operatorname{tr}F_{\mu\nu}F^{\mu\nu}(x)$ can be.

<details>
<summary><strong>Solution</strong></summary>

The gauge potential $A_\mu^a$ changes under a gauge transformation. Gauge-related configurations represent the same physical configuration, so a gauge-dependent insertion cannot be a physical observable by itself.

The field strength transforms covariantly,

$$
F_{\mu\nu}\mapsto gF_{\mu\nu}g^{-1}.
$$

Taking the trace removes the conjugation:

$$
\operatorname{tr}(gF_{\mu\nu}g^{-1}gF^{\mu\nu}g^{-1})
=
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}).
$$

Thus $\operatorname{tr}F_{\mu\nu}F^{\mu\nu}$ is gauge-invariant and can define a physical local operator after renormalization.

</details>

### Exercise 4: A simple selection rule

In an Ising-like CFT with $\mathbb Z_2$ symmetry, $\sigma$ is odd and $\epsilon$ is even. Explain why the OPE $\sigma\times\sigma$ cannot contain $\sigma$.

<details>
<summary><strong>Solution</strong></summary>

The product of two odd operators is even:

$$
(-)\times(-)=+.
$$

Every term in the OPE must have the same total $\mathbb Z_2$ charge as the product on the left. Since $\sigma$ is odd, it cannot appear in $\sigma\times\sigma$. The OPE may contain even operators such as $\mathbf 1$, $\epsilon$, and higher even primaries.

</details>

### Exercise 5: Descendants are not new data

Let $\mathcal O$ be a scalar primary. Why is $\partial_\mu\mathcal O$ a local operator but not an independent primary datum?

<details>
<summary><strong>Solution</strong></summary>

The derivative $\partial_\mu\mathcal O$ is local because it is supported at the same point as $\mathcal O$ and can be inserted in correlation functions by differentiating:

$$
\langle \partial_\mu\mathcal O(x)\cdots\rangle
=
\partial_\mu\langle \mathcal O(x)\cdots\rangle.
$$

But its correlation functions are fixed once those of $\mathcal O$ are known. In representation-theory language, $\partial_\mu\mathcal O$ is a descendant obtained by acting with the translation generator $P_\mu$. Therefore it is not a new primary operator and does not require a new independent OPE coefficient beyond the primary data.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. Standard reference for local fields, OPEs, Ward identities, radial quantization, and two-dimensional examples.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, Springer, 2017. Clear modern account of local operators, primary operators, CFT data, OPEs, and bootstrap in higher dimensions.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982. Pedagogical introduction to local operator data and crossing equations.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405. Review of how local operator spectra and OPE coefficients enter numerical bootstrap.
- K. G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974). Classic source for the fixed-point and scaling-operator viewpoint.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, 5th ed., Oxford University Press, 2021. Detailed treatment of fields, composite operators, RG, and critical phenomena.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” *Journal of High Energy Physics* **2015** (2015), arXiv:1412.5148. Modern reference for the extended-operator generalization of symmetry.

## Version history

- **2026-06-27:** Initial polished draft explaining local operators as observables, source couplings, scaling operators, gauge-invariant local probes, order parameters, OPE locality, contact terms, bootstrap use, examples, pitfalls, and exercises.
