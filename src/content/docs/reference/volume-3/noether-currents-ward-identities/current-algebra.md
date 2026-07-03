---
title: "Current Algebra"
description: "Explains how conserved currents realize symmetry algebras locally through equal-time commutators, Ward-identity contact terms, Schwinger terms, and two-dimensional current OPEs."
sidebar:
  label: "Current Algebra"
  order: 8
level: Graduate
status: "Polished draft"
source: "Coleman lectures on current algebra and soft pions; Coleman Aspects of Symmetry; Srednicki §22 and §§67–68; Weinberg Vol. I on symmetries and Vol. II on gauge identities; standard CFT normalization caveats for affine current algebras."
topics:
  - current algebra
  - Noether currents
  - equal-time commutators
  - Ward identities
  - Schwinger terms
  - Kac–Moody algebra
canonicalTopics:
  - current-algebra
  - equal-time-current-commutator
  - schwinger-term
  - affine-current-algebra
researchStatus:
  established:
    - "Integrated nonanomalous charges realize the Lie algebra of the symmetry, while local current commutators refine this algebra by distributional contact terms."
  active:
    - "In interacting theories, current-algebra contact terms are best organized by background fields, anomalies, defects, and operator-product data; their scheme-independent parts remain important in modern symmetry and anomaly theory."
---

## Summary

Current algebra is the local version of symmetry algebra.

The global charges satisfy

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c
$$

for a Lie algebra with structure constants $f_{ab}{}^c$. Current algebra asks for the more local statement: what are the equal-time commutators, or operator products, of the current densities $j_a^\mu(x)$ themselves?

At the simplest level,

$$
[j_a^0(t,\mathbf x),j_b^0(t,\mathbf y)]
=if_{ab}{}^c j_c^0(t,\mathbf x)\delta^{(d-1)}(\mathbf x-\mathbf y)
+\text{Schwinger terms}.
$$

The first term integrates to the global charge algebra. The extra terms are local distributions, often derivatives of delta functions. They are invisible in naive separated-point conservation laws but essential in local Ward identities, anomalies, and two-dimensional current algebras.

<figure class="doc-figure" style="--figure-width: 43rem;">

![A hierarchy showing global charge algebra, equal-time current commutators, Ward-identity contact terms, and OPE or affine current algebra data.](/figures/symmetry-anomalies-topology/current-algebra-hierarchy.svg)

<figcaption>

Current algebra refines the charge algebra. Integrated charges give $[Q_a,Q_b]=if_{ab}{}^cQ_c$. Local current densities contain more data: contact terms, improvement ambiguities, Schwinger terms, and, in two-dimensional CFT, affine OPE coefficients such as the level $k$.

</figcaption>
</figure>

## Prerequisites

Read [Symmetry Algebras](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-algebras/), [Conserved Charges](/symmetry-anomalies-topology/noether-currents-ward-identities/conserved-charges/), and [Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/) first.

This page assumes ordinary internal continuous symmetries. Gauge constraints, BRST currents, stress tensors, supersymmetry currents, higher-form currents, and non-invertible defects all have analogous but more structured versions.

## Core idea

The equation

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c
$$

is an integrated statement. Since

$$
Q_a(t)=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x),
$$

one might hope that the local densities simply obey

$$
[j_a^0(t,\mathbf x),j_b^0(t,\mathbf y)]
\stackrel{?}{=}if_{ab}{}^c j_c^0(t,\mathbf x)\delta^{(d-1)}(\mathbf x-\mathbf y).
$$

This is the right first guess. But it is not the whole story. Quantum fields are operator-valued distributions, so equal-time products of local currents are singular. The correct local algebra can include additional distributions whose integrals are boundary terms or central terms.

Thus current algebra is not just “the Lie algebra with an $x$ attached.” It is the local operator algebra compatible with:

- the integrated charge algebra,
- the action of charges on local operators,
- Ward-identity contact terms,
- locality and covariance,
- current improvements and renormalization scheme choices,
- possible anomaly or central-extension data.

That little list is where much of twentieth-century QFT education went to hide. We will unpack it gently.

## Setup and conventions

We use Hermitian charges and the pullback convention

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
\delta_a\mathcal O=i[Q_a,\mathcal O].
$$

The charges obey

$$
[Q_a,Q_b]=if_{ab}{}^cQ_c.
$$

Because this is a pullback action on operators, the infinitesimal variations satisfy

$$
[\delta_a,\delta_b]\mathcal O=-f_{ab}{}^c\delta_c\mathcal O.
$$

This sign was fixed in the [Symmetry Algebras](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-algebras/) page. The physical content is independent of this bookkeeping choice.

A local current algebra is an algebra of distributions. Equal-time commutators should always be understood after smearing against smooth test functions $\epsilon^a(\mathbf x)$ and $\eta^b(\mathbf y)$.

:::note[Convention-sensitive source note]
Current algebra normalizations vary wildly across subfields. Particle-physics current algebra often uses equal-time commutators of $j^0_a$. Two-dimensional CFT often uses holomorphic currents $J_a(z)$ and OPE coefficients. Condensed-matter treatments may normalize densities and levels differently. This page fixes the integrated charge convention and states local central terms schematically unless a normalization is explicitly specified.
:::

## From charge algebra to density algebra

Let

$$
Q_a=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x).
$$

If the local density algebra contains

$$
[j_a^0(t,\mathbf x),j_b^0(t,\mathbf y)]
=if_{ab}{}^c j_c^0(t,\mathbf x)\delta^{(d-1)}(\mathbf x-\mathbf y),
$$

then integrating over $\mathbf x$ and $\mathbf y$ gives

$$
[Q_a,Q_b]
=if_{ab}{}^c\int d^{d-1}\mathbf x\,j_c^0(t,\mathbf x)
=if_{ab}{}^cQ_c.
$$

This is why the delta function is forced. It localizes the second charge density at the point of the first, leaving one integral over the current.

But the converse is not unique. The integrated algebra does not determine the local algebra completely. We can add a term $S_{ab}(\mathbf x,\mathbf y)$ satisfying

$$
\int d^{d-1}\mathbf x\,d^{d-1}\mathbf y\,S_{ab}(\mathbf x,\mathbf y)=0
$$

on the spatial slice. A derivative of a delta function has this property on a compact space or with suitable boundary conditions:

$$
S_{ab}(\mathbf x,\mathbf y)\sim \partial_i^x\delta^{(d-1)}(\mathbf x-\mathbf y)\,K_{ab}^i(\mathbf y).
$$

Such terms can matter profoundly in local Ward identities even though they do not alter the naive integrated algebra.

## Currents acting on local operators

Current algebra also includes the action of current density on a local operator. For an operator $\mathcal O(y)$,

$$
[Q_a,\mathcal O(y)]=-i\delta_a\mathcal O(y).
$$

The local version is

$$
[j_a^0(t,\mathbf x),\mathcal O(t,\mathbf y)]
=-i\delta^{(d-1)}(\mathbf x-\mathbf y)\delta_a\mathcal O(t,\mathbf y)
+\text{derivative contact terms}.
$$

Integrating over $\mathbf x$ gives the charge action. Derivative terms vanish after integration if they are pure spatial boundary terms.

This equation is the operator seed of the Ward identity

$$
\partial_\mu^x\langle T\,j_a^\mu(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=-i\sum_k\delta^{(d)}(x-x_k)
\langle T\,\mathcal O_1\cdots\delta_a\mathcal O_k\cdots\mathcal O_n\rangle+\cdots.
$$

Thus current algebra and Ward identities are not separate subjects. They are the equal-time and spacetime-distribution versions of the same local symmetry structure.

## Currents transform in the adjoint representation

The currents themselves are operators. For a nonabelian internal symmetry, the current $j_b^\mu$ typically transforms in the adjoint representation:

$$
\delta_a j_b^\mu = -f_{ab}{}^c j_c^\mu
$$

with the pullback convention of this volume. Equivalently,

$$
i[Q_a,j_b^\mu]=-f_{ab}{}^c j_c^\mu.
$$

So

$$
[Q_a,j_b^\mu]=i f_{ab}{}^c j_c^\mu.
$$

The corresponding local equal-time commutator is schematically

$$
[j_a^0(t,\mathbf x),j_b^\mu(t,\mathbf y)]
=if_{ab}{}^c j_c^\mu(t,\mathbf y)\delta^{(d-1)}(\mathbf x-\mathbf y)
+\text{Schwinger terms}.
$$

The $\mu=0$ component gives the density-density algebra above. The spatial components are equally important in Ward identities for current insertions.

## Schwinger terms

A Schwinger term is a local central or extension term in an equal-time current commutator. It is usually a derivative of a delta function, so it can vanish after integration while still changing the local algebra.

A schematic example is

$$
[j_a^0(t,\mathbf x),j_b^i(t,\mathbf y)]
=if_{ab}{}^c j_c^i(t,\mathbf y)\delta^{(d-1)}(\mathbf x-\mathbf y)
+i\kappa_{ab}\partial_y^i\delta^{(d-1)}(\mathbf x-\mathbf y)+\cdots.
$$

The coefficient $\kappa_{ab}$ is not determined by the classical Noether theorem. It is quantum local data. In many settings it is tied to anomalies, levels, or regularization choices.

The word “central” should be handled with care. A term proportional to the identity operator is central in the operator algebra. A derivative-of-delta term can still integrate to zero on a closed slice. In two dimensions, such terms become the familiar central extensions of affine current algebras.

## Two-dimensional current algebra

Two-dimensional conformal field theory gives the cleanest laboratory. Let $J_a(z)$ be holomorphic currents for a compact Lie algebra with invariant metric $\kappa_{ab}$. A common normalization is

$$
J_a(z)J_b(0)
\sim \frac{k\,\kappa_{ab}}{z^2}
+\frac{i f_{ab}{}^cJ_c(0)}{z}
+\text{regular}.
$$

The coefficient $k$ is the level. The $1/z$ term encodes the Lie algebra. The $1/z^2$ term is the local central extension.

Expanding on a circle,

$$
J_a(z)=\sum_{n\in\mathbb Z}J_{a,n}z^{-n-1},
$$

the OPE implies the affine Lie algebra

$$
[J_{a,m},J_{b,n}]
=if_{ab}{}^cJ_{c,m+n}+k\,m\,\kappa_{ab}\delta_{m+n,0}.
$$

The zero modes $J_{a,0}$ satisfy the ordinary Lie algebra:

$$
[J_{a,0},J_{b,0}]=if_{ab}{}^cJ_{c,0}.
$$

So the two-dimensional story perfectly illustrates the general pattern:

$$
\text{local current algebra} = \text{global Lie algebra} + \text{local extension data}.
$$

The CFT volume develops this in detail. Here the point is conceptual: local current algebra contains more information than the global symmetry group.

## Ward identities with current insertions

Now insert a current into a Ward identity. Since $j_b^\nu$ is itself charged, the divergence of a current-current correlator has a contact term when the two currents collide:

$$
\partial_\mu^x\langle T\,j_a^\mu(x)j_b^\nu(y)\mathcal X\rangle
= -i\delta^{(d)}(x-y)\langle T\,\delta_a j_b^\nu(y)\mathcal X\rangle
-i\sum_k\delta^{(d)}(x-x_k)\langle T\,j_b^\nu(y)\mathcal X_k^{(a)}\rangle
+\cdots.
$$

Using

$$
\delta_a j_b^\nu=-f_{ab}{}^c j_c^\nu,
$$

the first contact term becomes

$$
+i f_{ab}{}^c\delta^{(d)}(x-y)
\langle T\,j_c^\nu(y)\mathcal X\rangle,
$$

up to the sign conventions already fixed. The dots contain possible Schwinger terms, improvement terms, anomaly terms, and local counterterm contributions.

This formula is often the most efficient way to infer current algebra from Ward identities. Conversely, equal-time current algebra is what makes the current-insertion Ward identity consistent with the charge algebra.

## Background-field organization

A clean modern way to package current algebra is to couple the global symmetry to a background field $A_\mu^a$ and study the generating functional $W[A]$. The current is the response to the background source:

$$
\langle j_a^\mu(x)\rangle_A=\frac{\delta W[A]}{\delta A_\mu^a(x)}
$$

up to the source sign convention.

For a nonanomalous symmetry, background gauge invariance gives

$$
D_\mu\langle j^\mu\rangle_A=0.
$$

Taking functional derivatives of this identity with respect to $A$ generates Ward identities for current correlators. Every time a derivative hits the covariant derivative $D_\mu$, it produces a local term proportional to the structure constants. Every time a derivative hits a local counterterm in $W[A]$, it produces a scheme-dependent contact term. If background gauge invariance fails by an anomaly, the failure appears as an additional local functional.

This viewpoint has two advantages. First, it keeps signs and contact terms systematic. Second, it separates three kinds of data:

$$
\text{representation contact terms},\qquad
\text{counterterm scheme contact terms},\qquad
\text{anomaly or level data}.
$$

## Current algebra and soft theorems

Historically, current algebra was powerful because it derived physical constraints without knowing the full dynamics. Equal-time commutators of currents, together with partial conservation laws and analyticity assumptions, led to relations among amplitudes.

The soft-pion tradition is the classic example. Axial and vector currents obey approximate current algebra. Combining their commutators with LSZ-type reduction and low-energy limits gives constraints on pion emission and scattering. The modern language is different, but the logic is familiar:

$$
\text{symmetry current} + \text{current algebra} + \text{soft limit}
\Longrightarrow \text{amplitude constraint}.
$$

This chapter does not derive soft theorems in detail. The planned soft-theorem preview page will explain the bridge from Ward identities to low-energy particle emission.

## Canonical current algebra can miss quantum terms

A tempting method is to compute current commutators using canonical equal-time commutators of the fundamental fields. This often gives the Lie-algebra term correctly. But it can miss Schwinger terms.

The reason is simple: currents are composite operators. A product such as

$$
j_a^0(t,\mathbf x)j_b^i(t,\mathbf y)
$$

is singular as $\mathbf x\to\mathbf y$. Defining the commutator requires a regulator and a subtraction prescription. Different regulators can shift local terms, and regulator-invariant remnants can encode anomaly or level data.

So canonical algebra is a useful starting point, not a complete definition of renormalized current algebra.

## Gauge currents and global currents

Do not confuse current algebra for a physical global symmetry with the constraint algebra of a gauge redundancy.

A global charge acts on physical states and gauge-invariant local operators. Its current algebra gives Ward identities and selection rules.

A gauge generator is a constraint. In a gauge theory, the local Gauss-law operator annihilates physical states, up to boundary charges and global transformations. The algebra of gauge transformations is essential, but it is not automatically a global symmetry algebra acting faithfully on gauge-invariant observables.

The boundary caveat matters. In gauge theories on manifolds with boundary or asymptotic regions, transformations that do not vanish at the boundary can become physical global symmetries with genuine charges. Their current or charge algebra may acquire boundary central terms.

## What current algebra does for you

Current algebra is useful because it tells you how local symmetry data propagates into physics.

It gives:

| Object | What current algebra controls |
|---|---|
| Local operators | Their transformation under charge densities. |
| Currents | How current insertions transform into one another. |
| Ward identities | Which contact terms appear when currents collide. |
| Selection rules | Which correlators and amplitudes are allowed. |
| Soft limits | How charge conservation constrains low-energy emission. |
| Two-dimensional CFT | The affine algebra, level, and current OPE. |
| Anomalies | Schwinger terms and consistency conditions. |
| Boundaries | Boundary charge algebras and possible central extensions. |

The integrated symmetry group is the headline. Current algebra is the footnote that quietly runs the show.

## Common pitfalls

**Assuming current densities obey the same algebra as charges with no extra terms.** Delta-function Lie-algebra terms are only the leading local structure. Schwinger terms and improvements can also appear.

**Forgetting that current commutators are distributions.** Equal-time current algebra makes sense after smearing. Products at the same point are not ordinary operator products.

**Treating Schwinger terms as mistakes.** They can be required by quantum consistency and are often tied to anomaly or level data.

**Confusing scheme-dependent contact terms with invariant levels.** Local counterterms can shift some current-current contact terms. Quantized levels and anomaly coefficients are more rigid.

**Mixing pullback and pushforward conventions.** With $\mathcal O\mapsto U^\dagger\mathcal O U$, the operator variations close with a sign relative to the charge commutator. Keep the convention fixed.

**Calling gauge redundancy current algebra a physical symmetry algebra.** Gauge constraints become physical only after specifying the observable algebra and boundary conditions.

## Relations to other pages

[Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/) explains the distributional terms that current algebra produces in Ward identities.

[Charges Acting on Local Operators](/symmetry-anomalies-topology/noether-currents-ward-identities/charges-acting-on-local-operators/) uses the current-density commutator with a local operator to derive representation-theoretic transformation laws.

The anomaly chapters explain when local extensions in current algebra are symptoms of genuine anomaly data rather than removable contact terms.

The CFT volume develops affine current algebra, Kac–Moody algebras, and current OPEs in their natural home.

The gauge-redundancy and BRST chapters explain why gauge constraints require a different algebraic interpretation from physical global currents.

## Research status

The basic current algebra of ordinary conserved currents is established. The subtleties are local and quantum: composite-operator definitions, regularization, Schwinger terms, anomalies, and boundary conditions.

Modern treatments usually prefer background fields, operator products, and topological defect language over bare canonical commutators. This does not make old current algebra obsolete. It clarifies what old current algebra was measuring: the local symmetry action, its contact terms, and its possible central extensions.

For generalized symmetries, the analogue of current algebra is often better expressed in terms of topological operators and their fusion, braiding, and junction data. That is the same philosophy at a higher categorical altitude. Tiny slogan: local algebra grows up and becomes defect algebra.

## Exercises

### Exercise 1: Integrating the density algebra

Assume

$$
[j_a^0(t,\mathbf x),j_b^0(t,\mathbf y)]
=if_{ab}{}^cj_c^0(t,\mathbf x)\delta^{(d-1)}(\mathbf x-\mathbf y).
$$

Show that $[Q_a,Q_b]=if_{ab}{}^cQ_c$.

<details><summary><strong>Solution</strong></summary>

Using

$$
Q_a=\int d^{d-1}\mathbf x\,j_a^0(t,\mathbf x),
$$

we have

$$
[Q_a,Q_b]
=\int d^{d-1}\mathbf x\,d^{d-1}\mathbf y\,[j_a^0(t,\mathbf x),j_b^0(t,\mathbf y)].
$$

Substitute the assumed local algebra:

$$
[Q_a,Q_b]
=if_{ab}{}^c\int d^{d-1}\mathbf x\,d^{d-1}\mathbf y\,
 j_c^0(t,\mathbf x)\delta^{(d-1)}(\mathbf x-\mathbf y).
$$

The $\mathbf y$ integral gives one, so

$$
[Q_a,Q_b]
=if_{ab}{}^c\int d^{d-1}\mathbf x\,j_c^0(t,\mathbf x)
=if_{ab}{}^cQ_c.
$$

</details>

### Exercise 2: A derivative Schwinger term

Suppose in one spatial dimension

$$
[j_a^0(t,x),j_b^0(t,y)]
=if_{ab}{}^cj_c^0(t,x)\delta(x-y)
+i k_{ab}\partial_x\delta(x-y).
$$

Show that the derivative term does not change $[Q_a,Q_b]$ on a circle.

<details><summary><strong>Solution</strong></summary>

The derivative contribution to the integrated commutator is

$$
i k_{ab}\int dx\,dy\,\partial_x\delta(x-y).
$$

For fixed $y$,

$$
\int_{S^1} dx\,\partial_x\delta(x-y)=0
$$

because the circle has no boundary. Therefore the derivative term gives zero after integrating over $x$ and $y$.

The global charge algebra is unchanged, but the local current algebra is different. This is exactly the point of a Schwinger term.

</details>

### Exercise 3: Current transformation from the charge algebra

Assume $j_b^\mu$ transforms in the adjoint representation with the pullback convention,

$$
\delta_a j_b^\mu=-f_{ab}{}^cj_c^\mu.
$$

Using $\delta_a\mathcal O=i[Q_a,\mathcal O]$, find $[Q_a,j_b^\mu]$.

<details><summary><strong>Solution</strong></summary>

Set $\mathcal O=j_b^\mu$. Then

$$
i[Q_a,j_b^\mu]=-f_{ab}{}^cj_c^\mu.
$$

Divide by $i$:

$$
[Q_a,j_b^\mu]=i f_{ab}{}^cj_c^\mu.
$$

This is the integrated form of the current-current commutator.

</details>

### Exercise 4: Zero modes of the affine algebra

Given

$$
[J_{a,m},J_{b,n}]
=if_{ab}{}^cJ_{c,m+n}+k\,m\,\kappa_{ab}\delta_{m+n,0},
$$

show that the zero modes satisfy the ordinary Lie algebra.

<details><summary><strong>Solution</strong></summary>

Set $m=n=0$. Then

$$
[J_{a,0},J_{b,0}]
=if_{ab}{}^cJ_{c,0}+k\cdot 0\cdot\kappa_{ab}\delta_{0,0}.
$$

The central term vanishes because it is proportional to $m=0$. Hence

$$
[J_{a,0},J_{b,0}]
=if_{ab}{}^cJ_{c,0}.
$$

The ordinary global symmetry algebra is the zero-mode part of the affine current algebra.

</details>

## References

- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the lectures on symmetries, conservation laws, and current algebra.
- Sidney Coleman, *Aspects of Symmetry*, especially “Soft Pions,” for classic current commutators and their use in amplitude constraints.
- Mark Srednicki, *Quantum Field Theory*, §22 and §§67–68. Useful for continuous currents and Ward identities.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I for symmetry generators and Vol. II for nonabelian and background-field identities.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the Ward–Takahashi and anomaly discussions.
- Philippe Di Francesco, Pierre Mathieu, and David Sénéchal, *Conformal Field Theory*. Standard reference for affine current algebra and two-dimensional current OPEs.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*. Useful for local identities, composite operators, and renormalized currents.

## Version history

- **2026-06-17:** Initial polished page explaining current algebra, equal-time current commutators, Schwinger terms, Ward-identity contact terms, and two-dimensional affine current algebra.
