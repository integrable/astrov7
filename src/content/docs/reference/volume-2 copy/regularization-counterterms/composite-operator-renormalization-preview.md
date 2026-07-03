---
title: "Composite-Operator Renormalization Preview"
description: "Why local products of fields require their own counterterms, source renormalization, operator mixing, and anomalous dimensions."
sidebar:
  label: "Composite Operators Preview"
  order: 8
level: Graduate
status: "Polished draft"
source: "Coleman, dilatations and renormalization lectures; Srednicki §§21–29; Schwartz chs. 19 and 23; Weinberg Vol. II ch. 18; Zinn-Justin, composite operators and short-distance expansion."
topics:
  - composite operators
  - operator renormalization
  - operator mixing
  - anomalous dimensions
  - contact terms
  - OPE preview
canonicalTopics:
  - composite-operator-renormalization
  - operator-mixing
  - anomalous-dimension-matrix
  - local-operator-basis
researchStatus:
  established:
    - "Local composite operators generally require their own renormalization and can mix with all operators compatible with the symmetries and power counting."
  active:
    - "Operator bases and mixing remain technically central in EFTs, gauge theories, conformal perturbation theory, lattice-continuum matching, collider factorization, and curved-spacetime QFT."
---

## Summary

A **composite operator** is a local object built from products of fields and derivatives at the same spacetime point, such as

$$
\phi^2(x),
\qquad
\phi^4(x),
\qquad
\bar\psi\psi(x),
\qquad
F_{\mu\nu}F^{\mu\nu}(x),
\qquad
T_{\mu\nu}(x).
$$

Composite operators are not automatically finite just because the elementary fields, masses, and couplings have been renormalized. The reason is brutally simple: a product at one point probes shorter distances than an ordinary separated-point correlator. Even if

$$
\langle \phi(x_1)\cdots\phi(x_n)\rangle_R
$$

is finite for distinct $x_i$, the object

$$
\langle \phi^2(y)\phi(x_1)\cdots\phi(x_n)\rangle
$$

can have new UV divergences localized near $y$.

The standard cure is to renormalize a basis of local operators:

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R},
\qquad
\mathcal O_{a,R}=(Z^{-1})_a{}^b\mathcal O_{b,0}.
$$

The matrix $Z_a{}^b$ allows **operator mixing**. A bare operator rarely renormalizes in splendid isolation; it can mix with all local operators with the same quantum numbers that are allowed by locality, symmetries, power counting, equations of motion, and contact-term conventions.

<figure class="doc-figure" style="--figure-width: 54rem; --caption-width: 55rem;">

![A bare composite insertion has UV subgraphs that shrink to the insertion point; local subtractions produce a renormalized operator basis with possible mixing into other operators, EOM operators, total derivatives, and contact terms](/figures/renormalization-rg-eft/composite-operator-mixing.svg)

<figcaption>

A composite insertion has its own short-distance singularities. Renormalization replaces a bare local insertion by a finite renormalized operator basis. Mixing with operators of the same symmetry, equation-of-motion operators, total derivatives, and contact terms is not a nuisance; it is the local-operator version of counterterm logic.

</figcaption>
</figure>

This page is a preview because full operator renormalization deserves an entire chapter. The goal here is to explain why the issue exists, how the source method organizes it, and how it connects to anomalous dimensions, the operator product expansion, and effective field theory.

## Prerequisites

You should know [Renormalization of Correlation Functions](/renormalization-rg-eft/regularization-counterterms/renormalization-of-correlation-functions/), [Counterterms](/renormalization-rg-eft/regularization-counterterms/counterterms/), and [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/). The operator convention follows [Conventions and Notation](/renormalization-rg-eft/conventions/):

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R},
\qquad
\gamma_a{}^b=(Z^{-1})_a{}^c\left.\mu\frac{dZ_c{}^b}{d\mu}\right|_{\text{bare}}.
$$

With this convention,

$$
\left.\mu\frac{d}{d\mu}\mathcal O_{a,R}\right|_{\text{bare}}
=-\gamma_a{}^b\mathcal O_{b,R}.
$$

## Core idea

Ordinary renormalization makes correlators of elementary fields finite when all insertion points remain separated. Composite-operator renormalization asks for more: define what it means to insert a local product of fields at a point.

The difference is visible already in a free scalar theory. At separated points,

$$
\langle \phi(x)\phi(y)\rangle
$$

is a well-defined distribution. But the naive composite field

$$
\phi^2(x)
$$

would require multiplying two distributions at the same point. In perturbation theory, this becomes a new source of UV singularities. The singularity is not necessarily cured by multiplying by $Z_\phi^{-1}$, because loops can attach directly to the insertion point.

The practical slogan is

$$
\text{renormalizing fields does not automatically renormalize products of fields at one point.}
$$

Composite operators matter because they are everywhere in QFT. Mass terms, currents, stress tensors, order parameters, decay operators, EFT interactions, OPE terms, parton-distribution operators, and lattice observables are all local operators. A theory without well-defined local operators would be a pretty sad field theory: all stage, no actors.

## Setup and conventions

Let $\{\mathcal O_a\}$ be a basis of local operators with chosen quantum numbers. Examples include

$$
\phi^2,
\qquad
\phi^4,
\qquad
(\partial\phi)^2,
\qquad
\Box\phi^2,
\qquad
\mathbf 1.
$$

A correlator with one bare operator insertion is

$$
G_{a,0}^{(n)}(y;x_1,\ldots,x_n)
=\langle T\{\mathcal O_{a,0}(y)\phi_0(x_1)\cdots\phi_0(x_n)\}\rangle_0.
$$

The renormalized insertion is defined by

$$
G_{a,R}^{(n)}(y;x_1,\ldots,x_n)
=(Z^{-1})_a{}^b Z_\phi^{-n/2}
G_{b,0}^{(n)}(y;x_1,\ldots,x_n)
+\text{contact terms},
$$

where the contact terms are supported when $y$ collides with one of the $x_i$ or when two other insertion points collide. At fully separated points, the matrix renormalization is the main issue. At coincident points, contact terms are part of the definition.

The word **basis** is important. Operators are only defined modulo choices: total derivatives, integration by parts, equations of motion, symmetry relations, and finite scheme changes can all reshuffle the basis. This is not a failure of the formalism. It is the ordinary coordinate freedom of local operator space.

## Why new divergences appear

Suppose a diagram contains a local insertion $\mathcal O_a(y)$. Loop momenta can become large in a subgraph attached to the insertion while the external points remain far away. At long distances, that hard subgraph shrinks to $y$. Locality then says its divergence must be equivalent to a sum of local insertions at $y$:

$$
\text{divergent insertion of }\mathcal O_a
\sim
\sum_b c_a{}^b\mathcal O_b(y).
$$

This is the operator version of the counterterm argument. The only difference is that the counterterm is not merely a term in the action; it is a subtraction attached to an insertion.

For example, in an interacting scalar theory, an insertion of $\phi^2(y)$ can receive loop corrections localized at $y$. The divergent part has the same symmetry as $\phi^2$ and is absorbed by a renormalization constant $Z_{\phi^2}$. In more complicated cases, the insertion can mix with several operators:

$$
\mathcal O_{1,0}=Z_1{}^1\mathcal O_{1,R}+Z_1{}^2\mathcal O_{2,R}+Z_1{}^3\mathcal O_{3,R}+\cdots.
$$

The dots are not aesthetic fog. They mean that the chosen basis must be large enough to include every local operator that can be generated by short-distance singularities.

## The source method

The cleanest way to renormalize composite operators is to couple them to sources. Add to the action

$$
\Delta S_0=\int d^d x\,J_0^a(x)\mathcal O_{a,0}(x).
$$

The generating functional now produces correlators with operator insertions by differentiating with respect to $J_0^a$. Renormalization is organized by rewriting the source term in renormalized variables:

$$
\int d^d x\,J_0^a\mathcal O_{a,0}
=\int d^d x\,J_R^a\mathcal O_{a,R}.
$$

If

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R},
$$

then the source transforms with the inverse matrix in the appropriate index placement:

$$
J_R^b=J_0^aZ_a{}^b.
$$

This inverse relation is natural. Operators and sources are dual coordinates. If one changes the operator basis by $Z$, the source basis changes oppositely so that the integrated coupling remains the same.

The source method has three advantages:

| Advantage | Why it matters |
|---|---|
| It treats operator insertions systematically | differentiating with respect to $J$ generates all insertion correlators |
| It exposes mixing | source counterterms form matrices, not isolated constants |
| It tracks contact terms | local source-dependent counterterms encode coincident-point ambiguities |

For nonlinear or repeated insertions, the source action may require terms quadratic or higher in sources, such as

$$
\int d^d x\,C_{ab}J^aJ^b.
$$

Such terms do not affect one separated insertion, but they are necessary for defining correlators with multiple composite insertions when the insertion points collide.

## Operator mixing

Operator mixing is not optional bureaucracy. It is forced whenever several operators have the same quantum numbers.

A local operator can mix only with operators compatible with the exact constraints of the problem. Typical constraints are:

| Constraint | Consequence |
|---|---|
| Lorentz symmetry | scalar operators mix with scalars, vectors with vectors, tensors with tensors |
| internal symmetries | charges and representations must match |
| gauge symmetry or BRST cohomology | physical gauge-invariant operators mix within the appropriate cohomology class |
| spacetime dimension and power counting | high-dimension operators generally do not mix into lower-dimension ones without dimensionful coefficients |
| equations of motion | EOM operators can appear in off-shell bases and contact terms |
| total derivatives | matter for local correlators and momentum transfer, but may integrate to boundary terms |

In a mass-independent scheme such as $\overline{\mathrm{MS}}$ for a massless theory, the mixing matrix is often block triangular when operators are ordered by engineering dimension. In cutoff schemes or massive theories, power divergences and dimensionful parameters can make lower-dimensional operators appear more visibly. The precise triangular structure is therefore scheme and setup dependent, but the symmetry constraints are not.

A useful symbolic picture is

$$
\begin{pmatrix}
\mathcal O_{1,0}\\
\mathcal O_{2,0}\\
\mathcal O_{3,0}
\end{pmatrix}
=
\begin{pmatrix}
Z_1{}^1 & Z_1{}^2 & Z_1{}^3\\
Z_2{}^1 & Z_2{}^2 & Z_2{}^3\\
Z_3{}^1 & Z_3{}^2 & Z_3{}^3
\end{pmatrix}
\begin{pmatrix}
\mathcal O_{1,R}\\
\mathcal O_{2,R}\\
\mathcal O_{3,R}
\end{pmatrix}.
$$

Diagonalizing this matrix is not always the right goal. In EFT, for instance, one often wants a basis adapted to symmetries and power counting, not a basis that diagonalizes one-loop mixing. In CFT, by contrast, diagonalizing the anomalous-dimension matrix near a fixed point identifies scaling operators.

## Example: the operator φ²

In scalar $\phi^4$ theory, the operator $\phi^2$ is important because it couples to the mass parameter:

$$
\mathcal L\supset -\frac12m^2\phi^2.
$$

Formally, differentiating a correlator with respect to $m^2$ inserts $\phi^2$:

$$
\frac{\partial}{\partial m^2}
\langle \phi(x_1)\cdots\phi(x_n)\rangle
\sim
-\frac{i}{2}\int d^d y\,
\langle \phi^2(y)\phi(x_1)\cdots\phi(x_n)\rangle,
$$

with Euclidean conventions changing the factor of $i$ and some signs. But the right side is meaningful only after $\phi^2$ is renormalized.

A multiplicatively renormalized notation is often written

$$
[\phi^2]_R=Z_{\phi^2}^{-1}\phi_0^2,
$$

when no mixing needs to be displayed. More generally one should allow

$$
\phi_0^2=Z_{\phi^2}{}^{\phi^2}[\phi^2]_R+Z_{\phi^2}{}^{\mathbf 1}\mathbf 1+\text{contact conventions}.
$$

The identity operator appears because vacuum expectation values and coincident contractions can generate additive constants. In dimensional regularization with minimal subtraction and no mass scale, many such powerlike mixings are hidden or absent; in cutoff schemes they can be explicit.

The important lesson is not the exact one-loop coefficient. It is the logic: if $m^2$ runs, the operator conjugate to $m^2$ also has a renormalization. Couplings and operators are dual pieces of the same RG geometry.

## Example: φ⁴ and coupling derivatives

The quartic operator is coupled to $\lambda$:

$$
\mathcal L\supset -\frac{\lambda}{4!}\phi^4.
$$

Differentiating with respect to $\lambda$ formally inserts

$$
-\frac{i}{4!}\int d^d y\,\phi^4(y).
$$

But $\phi^4$ can mix with other scalar operators compatible with the symmetry, especially when masses and total derivatives are included. A schematic renormalized operator might take the form

$$
[\phi^4]_R
=a_1\phi_0^4+a_2m^2\phi_0^2+a_3m^4\mathbf 1+a_4\Box\phi_0^2+\cdots,
$$

where the coefficients encode the chosen renormalization scheme and basis. In a minimal-subtraction massless calculation, this structure simplifies. In an EFT or cutoff calculation, the larger tower is often unavoidable.

This is why EFT anomalous-dimension calculations are mostly bookkeeping with teeth. The physics is in the allowed operator basis and the mixing matrix.

## Protected and unprotected operators

Not all composite operators renormalize in the same way.

Some operators are protected by symmetries. A conserved current $J^\mu$ associated with an exact global symmetry often has constrained renormalization because its charge

$$
Q=\int d^{d-1}x\,J^0
$$

must generate the symmetry. Similarly, the stress tensor $T_{\mu\nu}$ is constrained by translation invariance and conservation equations. Gauge-invariant operators in supersymmetric theories may be protected by shortening conditions or nonrenormalization theorems.

Other operators are unprotected. Scalar operators such as $\phi^2$, $\bar\psi\psi$, or four-fermion operators usually acquire anomalous dimensions and mix with other operators.

A useful split is:

| Operator type | Typical behavior |
|---|---|
| conserved currents | dimensions and normalizations constrained by Ward identities |
| stress tensor | constrained by spacetime Ward identities; improvement/contact terms matter |
| exactly marginal operators | constrained by conformal perturbation theory and scheme choices |
| generic scalar operators | usually acquire anomalous dimensions and mix |
| EOM operators | vanish in certain physical matrix elements but affect off-shell correlators and contact terms |
| total derivatives | important when momentum flows through the insertion |

"Protected" does not mean "requires no thought." It means the renormalization is constrained by identities that must be preserved.

## Anomalous dimensions of operators

Given

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R},
$$

define the anomalous-dimension matrix by

$$
\gamma_a{}^b
=(Z^{-1})_a{}^c
\left.\mu\frac{dZ_c{}^b}{d\mu}\right|_{\text{bare}}.
$$

Holding the bare operator fixed gives

$$
\left.\mu\frac{d}{d\mu}\mathcal O_{a,R}\right|_{\text{bare}}
=-\gamma_a{}^b\mathcal O_{b,R}.
$$

For a correlator with one insertion and $n$ elementary scalar fields, the Callan–Symanzik equation has the schematic form

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+n\gamma_\phi
\right)G_{a,R}^{(n)}
+\gamma_a{}^bG_{b,R}^{(n)}=0,
$$

away from contact terms and with mass terms suppressed for compactness.

At a fixed point, the matrix $\gamma_a{}^b$ helps determine scaling operators. If an eigenoperator $\mathcal O_A$ has engineering dimension $\Delta_A^{\text{eng}}$ and anomalous contribution $\gamma_A^*$, its scaling dimension is conventionally written

$$
\Delta_A=\Delta_A^{\text{eng}}+\gamma_A^*.
$$

The precise extraction can involve sign conventions, operator normalizations, and mixing with descendants. The invariant statement is that scaling operators diagonalize dilatations at the fixed point, and their dimensions are physical data of the fixed-point theory.

## Contact terms and coincident insertions

A correlator with a composite insertion has several kinds of short-distance singularities:

1. UV subgraphs can shrink to the insertion point $y$.
2. The insertion point $y$ can collide with an elementary-field point $x_i$.
3. Two or more composite insertions can collide with each other.
4. Integrated insertions can turn contact terms into finite contributions.

The first kind is handled by operator renormalization. The other kinds require contact-term conventions and sometimes source counterterms. For two operator insertions, one may need terms quadratic in sources:

$$
\Delta S_J\supset \frac12\int d^d x\,C_{ab}J^aJ^b.
$$

Such terms are invisible in ordinary separated one-insertion correlators, but they matter for local Ward identities and for defining products of composite operators.

This is one reason the operator product expansion is the natural language for short distances. As $x\to y$,

$$
\mathcal O_a(x)\mathcal O_b(y)
\sim
\sum_c C_{ab}{}^c(x-y)\mathcal O_c(y).
$$

The singular coefficient functions $C_{ab}{}^c$ encode how products of local operators resolve into the local operator basis. Composite-operator renormalization is the perturbative machinery behind that statement.

## Relation to EFT operator bases

Effective field theory is largely the art of choosing and renormalizing a local operator basis. One writes

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\text{light}}
+\sum_a C_a(\mu)\mathcal O_{a,R}.
$$

The coefficients $C_a(\mu)$ are Wilson coefficients. Since the operators run, the coefficients must run oppositely so that the action is independent of the arbitrary scale:

$$
\mu\frac{d}{d\mu}\left(C_a\mathcal O_{a,R}\right)=0.
$$

Using

$$
\mu\frac{d}{d\mu}\mathcal O_{a,R}=-\gamma_a{}^b\mathcal O_{b,R},
$$

one obtains a coefficient RG equation of the schematic form

$$
\mu\frac{dC_b}{d\mu}=C_a\gamma_a{}^b,
$$

up to transpose conventions and additional coupling dependence. This is the origin of anomalous-dimension matrices in weak decays, SMEFT, SCET, heavy-quark effective theory, and many other EFTs.

The slogan is

$$
\text{operator mixing tells Wilson coefficients how to run.}
$$

## Common pitfalls

**Writing $[\phi^2]_R=\phi_R^2$ without qualification.** This is usually false. The product of two renormalized fields at the same point still needs its own subtraction.

**Forgetting mixing.** If several operators share the same quantum numbers, a single $Z_O$ is usually too naive. The correct object is a matrix.

**Dropping EOM operators too early.** Equations-of-motion operators may vanish in certain on-shell matrix elements, but they can be required for off-shell renormalization, contact terms, and basis transformations.

**Confusing finite basis changes with physics.** Changing the operator basis changes anomalous-dimension matrices and Wilson coefficients. Physical amplitudes and scaling dimensions do not change when the transformation is handled consistently.

**Ignoring contact terms.** Composite operators are local. Their products have contact singularities. Ward identities and source variations often depend exactly on those terms.

**Assuming gauge-invariant operators are automatically easy.** Gauge invariance restricts mixing, but it does not remove the need for operator renormalization. In gauge theories, BRST, ghosts, EOM operators, and gauge-fixing choices can all enter intermediate calculations.

## Relations to other pages

[Renormalization of Correlation Functions](/renormalization-rg-eft/regularization-counterterms/renormalization-of-correlation-functions/) explains why ordinary separated-point Green functions need field and parameter renormalization. This page explains why local operator insertions need additional renormalization.

The full treatment belongs in the later chapter [Local Operators and OPE](/renormalization-rg-eft/local-operators-and-ope/), especially the pages on engineering dimensions, anomalous dimensions of operators, operator mixing, renormalization matrices, anomalous-dimension matrices, EOM operators, redundant operators, and the OPE.

The EFT chapter uses the same machinery for Wilson coefficients and matching. The CFT and Bootstrap volume uses the fixed-point version: scaling operators, dimensions, OPE coefficients, and conformal multiplets. The Symmetry, Anomalies, and Topology volume uses protected currents, stress tensors, anomaly operators, and defect operators. The Gauge Theories and Standard Model volume uses composite operators in currents, hadronic matrix elements, weak decays, and SMEFT.

## Research status

Composite-operator renormalization is established and indispensable. In ordinary perturbative QFT, the rules are systematic: introduce sources, include every allowed counterterm, compute the mixing matrix, and extract anomalous dimensions.

The active frontier is not the existence of the method; it is the complexity of applying it well. Modern problems involve huge EFT bases, evanescent operators in dimensional regularization, scheme conversion, lattice-continuum matching, gauge-invariant nonlocal operators, light-ray operators, defect operators, curved-background sources, nonperturbative anomalous dimensions, and operator mixing in theories without a weakly coupled Lagrangian. In those settings, notation discipline is not pedantry. It is survival gear.

## Exercises

### Exercise 1: Why $Z_\phi$ is not enough

Let $\phi_0=Z_\phi^{1/2}\phi$. A student claims that $\phi_0^2=Z_\phi\phi^2$, so $Z_\phi^{-1}\phi_0^2$ must be the finite renormalized operator $[\phi^2]_R$. Explain why this argument is incomplete.

<details><summary><strong>Solution</strong></summary>

The relation $\phi_0=Z_\phi^{1/2}\phi$ defines the normalization of separated elementary-field insertions. It does not define the product of two fields at the same spacetime point.

The operator $\phi^2(x)$ has additional UV singularities from contractions and loop subgraphs localized at $x$. These singularities are not necessarily removed by the external-field factor $Z_\phi^{-1}$. A separate operator renormalization is needed:

$$
[\phi^2]_R=Z_{\phi^2}^{-1}\phi_0^2+\text{possible mixing and contact terms}.
$$

Only in special cases or at special orders does $Z_{\phi^2}$ coincide with a simple power of $Z_\phi$.

</details>

### Exercise 2: Source and operator inverse transformation

Suppose $\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R}$. Show how the renormalized source must be related to the bare source so that

$$
\int d^d x\,J_0^a\mathcal O_{a,0}
=
\int d^d x\,J_R^a\mathcal O_{a,R}.
$$

<details><summary><strong>Solution</strong></summary>

Substitute the operator relation:

$$
\int d^d x\,J_0^a\mathcal O_{a,0}
=
\int d^d x\,J_0^a Z_a{}^b\mathcal O_{b,R}.
$$

Comparing with

$$
\int d^d x\,J_R^b\mathcal O_{b,R},
$$

we identify

$$
J_R^b=J_0^aZ_a{}^b.
$$

Equivalently, if one solves for the bare source in terms of the renormalized source, it transforms with the inverse matrix. Operators and sources are dual coordinates.

</details>

### Exercise 3: RG equation for Wilson coefficients

Let an EFT contain $\sum_a C_a(\mu)\mathcal O_{a,R}$. Suppose

$$
\mu\frac{d}{d\mu}\mathcal O_{a,R}=-\gamma_a{}^b\mathcal O_{b,R}.
$$

Derive the schematic RG equation for $C_a$ required by scale independence of the product.

<details><summary><strong>Solution</strong></summary>

Demand

$$
0=\mu\frac{d}{d\mu}\left(C_a\mathcal O_{a,R}\right).
$$

Then

$$
0=\left(\mu\frac{dC_a}{d\mu}\right)\mathcal O_{a,R}
+C_a\left(\mu\frac{d}{d\mu}\mathcal O_{a,R}\right).
$$

Using the operator RG equation gives

$$
0=\left(\mu\frac{dC_b}{d\mu}\right)\mathcal O_{b,R}
-C_a\gamma_a{}^b\mathcal O_{b,R}.
$$

Therefore, assuming the basis is independent,

$$
\mu\frac{dC_b}{d\mu}=C_a\gamma_a{}^b.
$$

Depending on whether coefficients are treated as row or column vectors, the same equation is often written with a transpose.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations" and "Renormalization and Symmetry," for scale transformations, anomalous dimensions, and operator language.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, especially the renormalization lectures and discussion of Green functions.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on the quantum action, renormalization schemes, RG, and EFT.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially chapters 19, 21, 22, and 23.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for RG methods and renormalized operators.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the treatment of composite operators, RG equations, critical exponents, and the short-distance expansion.

## Version history

- 2026-06-17: First polished draft. Added source method, operator mixing, contact-term caveats, anomalous-dimension conventions, examples from $\phi^2$ and $\phi^4$, and links to EFT and OPE usage.
