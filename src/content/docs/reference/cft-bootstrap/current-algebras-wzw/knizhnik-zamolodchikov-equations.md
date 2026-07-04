---
title: "Knizhnik–Zamolodchikov Equations"
description: "How affine current algebra and the Sugawara construction turn WZW correlation functions into first-order differential equations for chiral conformal blocks."
sidebar:
  label: "KZ Equations"
  order: 9
level: Graduate
status: "Polished draft"
source: "Knizhnik and Zamolodchikov 1984; Di Francesco, Mathieu, and Senechal ch. 15; Ginsparg lectures; standard WZW literature."
topics:
  - Knizhnik–Zamolodchikov equations
  - WZW models
  - affine Lie algebras
  - conformal blocks
  - current algebra
canonicalTopics:
  - knizhnik-zamolodchikov-equations
  - wzw-conformal-blocks
  - current-algebra-ward-identities
researchStatus:
  established:
    - "The KZ equations are the standard first-order differential equations satisfied by chiral conformal blocks of WZW models."
  active:
    - "Their monodromy, quantum-group interpretation, boundary versions, logarithmic extensions, and relations to geometric representation theory remain important research tools."
---

## Summary

The **Knizhnik–Zamolodchikov equations** are differential equations for chiral conformal blocks in WZW models. For affine primary fields in representations $R_i$ inserted at points $z_i$, a chiral conformal block $\mathcal F(z_1,\ldots,z_n)$ satisfies

$$
(k+h^\vee)\partial_{z_i}\mathcal F
=\sum_{j\ne i}\frac{\Omega_{ij}}{z_i-z_j}\mathcal F,
\qquad
\Omega_{ij}=\kappa_{ab}t_i^a t_j^b.
$$

Here $k$ is the affine level, $h^\vee$ is the dual Coxeter number, $t_i^a$ acts on the finite-dimensional representation carried by the $i$th primary, and $\kappa_{ab}$ is the current-algebra metric.

The equations come from two ingredients:

1. The Sugawara stress tensor expresses $T(z)$ in terms of currents.
2. Current Ward identities express current insertions in terms of Lie-algebra generators acting on primary fields.

The result is powerful: WZW conformal blocks are not arbitrary functions. They are flat sections of a connection on the space of insertion points. Their monodromy encodes braiding and fusing data, and their number of independent local solutions is controlled by WZW fusion rules.

## Prerequisites

Read [WZW Primary Fields](/cft-bootstrap/current-algebras-wzw/wzw-primary-fields/), [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/), [Currents and Kac–Moody OPEs](/cft-bootstrap/current-algebras-wzw/currents-and-kac-moody-opes/), and [WZW Fusion Rules](/cft-bootstrap/current-algebras-wzw/wzw-fusion-rules/) first.

You should know the current-primary OPE

$$
J^a(z)\Phi_i(w,\bar w)
\sim
\frac{t_i^a\Phi_i(w,\bar w)}{z-w},
$$

and the Sugawara stress tensor

$$
T(z)=\frac{1}{2(k+h^\vee)}\kappa_{ab}:J^aJ^b:(z).
$$

## Core idea

In a generic two-dimensional CFT, Virasoro symmetry constrains correlation functions but rarely gives simple first-order equations. In a WZW model, the current algebra is stronger. The stress tensor is quadratic in currents, so a derivative with respect to an insertion point can be rewritten as an insertion of currents. Current Ward identities then turn those currents into Lie-algebra generators acting on other fields.

The schematic chain is

$$
\partial_{z_i}\Phi_i
\sim L_{-1}\Phi_i
\sim J_{-1}^aJ_0^a\Phi_i
\sim \sum_{j\ne i}\frac{t_i^a t_j^a}{z_i-z_j}\Phi_i.
$$

This is the KZ equation. It is first order in each position variable, but matrix-valued because the tensor product

$$
R_1\otimes R_2\otimes\cdots\otimes R_n
$$

can contain several invariant tensors or several fusion channels.

The slogan is

$$
\text{current algebra} + \text{Sugawara}
\quad\Longrightarrow\quad
\text{first-order equations for WZW blocks}.
$$

## Setup and conventions

Let $\Phi_i(z_i,\bar z_i)$ be WZW primary fields. We focus on the holomorphic chiral blocks and suppress antiholomorphic dependence. The $i$th field transforms in a finite-dimensional representation $R_i$ of $\mathfrak g$ with matrices $t_i^a$.

The current OPE is

$$
J^a(z)J^b(w)
\sim
\frac{k\kappa^{ab}}{(z-w)^2}
+\frac{i f^{ab}{}_cJ^c(w)}{z-w}.
$$

The current-primary OPE is

$$
J^a(z)\Phi_i(z_i)
\sim
\frac{t_i^a\Phi_i(z_i)}{z-z_i}.
$$

Define the two-site quadratic operator

$$
\Omega_{ij}=\kappa_{ab}t_i^a t_j^b.
$$

It acts on the tensor product of finite representation spaces. In a basis of invariant tensors or intermediate fusion channels, $\Omega_{ij}$ becomes a matrix.

The KZ equations are

$$
\left[(k+h^\vee)\partial_{z_i}
-\sum_{j\ne i}\frac{\Omega_{ij}}{z_i-z_j}\right]\mathcal F=0.
$$

Some sources put the terms on the other side or absorb signs into generator conventions. The physical content is unchanged after a consistent convention translation.

## Chiral blocks are vector-valued

A full sphere correlator of primary fields is a scalar after all internal indices are contracted. A chiral conformal block is usually a vector in the space of invariant tensors or conformal blocks.

For insertions in representations $R_1,\ldots,R_n$, the global symmetry Ward identity says the correlator must be invariant:

$$
\sum_i t_i^a\mathcal F=0.
$$

Thus $\mathcal F$ lives in

$$
\operatorname{Inv}(R_1\otimes\cdots\otimes R_n),
$$

or in a closely related space of chiral intertwiners. If this space has dimension larger than one, the KZ equations are a coupled system.

This is why the KZ equation should be read as a matrix equation:

$$
\partial_{z_i}\mathcal F=A_i(z)\mathcal F,
\qquad
A_i(z)=\frac{1}{k+h^\vee}\sum_{j\ne i}\frac{\Omega_{ij}}{z_i-z_j}.
$$

Different bases of conformal blocks give different matrices $A_i$, but the same flat connection.

## Derivation from Sugawara

For an affine primary $|\lambda\rangle$, positive current modes vanish:

$$
J^a_n|\lambda\rangle=0,
\qquad n>0.
$$

The Sugawara formula implies the descendant relation

$$
L_{-1}|\lambda\rangle
=\frac{1}{k+h^\vee}\kappa_{ab}J^a_{-1}J^b_0|\lambda\rangle.
$$

In field language,

$$
\partial_z\Phi_i(z)
=\frac{1}{k+h^\vee}\kappa_{ab}(J^a_{-1}J^b_0\Phi_i)(z).
$$

The zero mode $J_0^b$ acts on the primary by the finite generator $t_i^b$. The mode $J^a_{-1}$ is represented by a contour integral of $J^a(u)/(u-z_i)$ around $z_i$.

In a correlator, deform that contour away from $z_i$. It picks up residues from the current-primary OPE with all other insertions:

$$
J^a(u)\Phi_j(z_j)
\sim
\frac{t_j^a\Phi_j(z_j)}{u-z_j}.
$$

The result is

$$
(k+h^\vee)\partial_{z_i}\mathcal F
=\sum_{j\ne i}\frac{\kappa_{ab}t_i^b t_j^a}{z_i-z_j}\mathcal F.
$$

Relabeling contracted indices gives

$$
(k+h^\vee)\partial_{z_i}\mathcal F
=\sum_{j\ne i}\frac{\Omega_{ij}}{z_i-z_j}\mathcal F.
$$

This is the KZ equation.

## Flatness

The KZ equations define a connection

$$
\nabla_i=(k+h^\vee)\partial_{z_i}
-\sum_{j\ne i}\frac{\Omega_{ij}}{z_i-z_j}.
$$

Consistency requires

$$
[\nabla_i,\nabla_j]=0.
$$

This flatness follows from Lie-algebra identities. The key commutator relations among the $\Omega_{ij}$ are consequences of the invariant tensor $\kappa_{ab}$ and the Jacobi identity of $\mathfrak g$.

Flatness means that the conformal block can be analytically continued along paths in configuration space, and the result depends only on the homotopy class of the path. The nontrivial monodromy around singular loci

$$
z_i=z_j
$$

is the origin of braid-group representations carried by WZW conformal blocks.

This monodromy is not a bug. It is exactly the chiral data needed to build local nonchiral correlators and to relate WZW models to quantum groups and Chern–Simons theory.

## Three-point functions

For three primary insertions on the sphere, global conformal invariance fixes all position dependence. The KZ equation is then equivalent to the statement that the three-point tensor is an invariant intertwiner.

The global Ward identity is

$$
(t_1^a+t_2^a+t_3^a)\mathcal F=0.
$$

The number of independent chiral three-point blocks is the fusion coefficient

$$
N_{\lambda_1\lambda_2}{}^{\lambda_3^*}.
$$

Thus the KZ equation does not add new position dependence for three points. Its real power starts at four points, where conformal symmetry leaves a cross-ratio.

## Four-point reduction

Put four insertions at

$$
z_1=0,
\qquad
z_2=z,
\qquad
z_3=1,
\qquad
z_4=\infty.
$$

After factoring out the known global conformal dependence, the KZ system reduces to an ordinary differential equation in the cross-ratio $z$. In a common convention, it takes the schematic form

$$
(k+h^\vee)\frac{d}{dz}\mathcal F(z)
=\left(\frac{\Omega_{21}}{z}+\frac{\Omega_{23}}{z-1}\right)\mathcal F(z).
$$

The matrices $\Omega_{21}$ and $\Omega_{23}$ act on the finite-dimensional invariant-tensor space. Diagonalizing the operator relevant to the $z\to0$ OPE channel identifies the allowed intermediate representations in

$$
R_1\times R_2.
$$

The local behavior near $z=0$ is governed by the conformal weights of the intermediate affine primaries:

$$
\mathcal F_\nu(z)\sim
z^{h_\nu-h_1-h_2}(\text{constant tensor}+\cdots).
$$

This is how the differential equation knows about fusion channels.

## SU(2) example: four spin-one-half fields

For $SU(2)_k$, take four chiral primary fields in the spin-$1/2$ representation. The tensor product contains two invariant pairings, corresponding roughly to the two possible intermediate spins in the $12$ channel:

$$
\frac12\times\frac12=0+1
$$

when $k\ge2$. Thus the KZ equation becomes a two-component first-order system. Its solutions can be written in terms of hypergeometric functions after choosing a suitable basis.

At level $k=1$, the spin-$1$ channel is not integrable. The fusion rule becomes

$$
\frac12\times\frac12=0,
$$

so only one physical WZW fusion channel remains.

This is a useful calibration point. The finite tensor product suggests two possible intermediate spins, but the affine level removes one of them at $k=1$. The KZ equation must be interpreted together with the integrable representation content and the chosen local CFT.

## Abelian limit

For a single $U(1)$ current,

$$
J(z)J(w)\sim\frac{k}{(z-w)^2},
$$

and a primary of charge $q_i$ has

$$
J(z)\Phi_{q_i}(w)\sim\frac{q_i\Phi_{q_i}(w)}{z-w}.
$$

The KZ equation becomes scalar:

$$
k\partial_{z_i}\mathcal F
=\sum_{j\ne i}\frac{q_iq_j}{z_i-z_j}\mathcal F.
$$

Its solution is

$$
\mathcal F(z_1,\ldots,z_n)
=\prod_{i<j}(z_i-z_j)^{q_iq_j/k},
$$

provided the total charge is zero:

$$
\sum_i q_i=0.
$$

This is the standard free-boson vertex-operator correlator. The nonabelian KZ equation is a matrix-valued generalization of this elementary charge-pairing formula.

## Monodromy, braiding, and fusing

Because KZ equations have singularities when insertions collide, their solutions have nontrivial analytic continuation. Taking one insertion around another acts on the vector space of conformal blocks by a braid matrix.

Changing the OPE channel acts by a fusing matrix. For four points, this is the change of basis between blocks adapted to

$$
(12)\to(34)
$$

and blocks adapted to

$$
(23)\to(14).
$$

The KZ connection therefore produces representations of braid groups and supplies the analytic data behind WZW crossing symmetry.

For compact WZW models, these braiding and fusing structures are closely related to quantum groups with deformation parameter schematically

$$
q=\exp\left(\frac{\pi i}{k+h^\vee}\right).
$$

This relation is one bridge between WZW models, knot invariants, and Chern–Simons theory.

## Full correlators versus chiral blocks

The KZ equations govern chiral conformal blocks, not automatically full local correlators. A full Euclidean correlator is assembled from holomorphic and antiholomorphic blocks:

$$
\mathcal G(z_i,\bar z_i)=
\sum_{\alpha,\bar\alpha}
M_{\alpha\bar\alpha}\,
\mathcal F_\alpha(z_i)\overline{\mathcal F}_{\bar\alpha}(\bar z_i).
$$

The matrix $M_{\alpha\bar\alpha}$ is constrained by locality, crossing, and the modular invariant of the full theory. In a diagonal WZW model, the pairing is often simple, but even there one must choose a single-valued combination of chiral blocks.

Thus:

$$
\text{KZ equations solve chiral blocks;}
\qquad
\text{locality assembles full correlators.}
$$

Forgetting this distinction leads to wrong claims about monodromy and branch cuts.

## Relation to BPZ equations

The KZ equations are to WZW models what BPZ equations are to Virasoro minimal models: both arise from special null or descendant relations and both turn symmetry into differential equations for correlators.

| Feature | BPZ equations | KZ equations |
|---|---|---|
| Main symmetry | Virasoro | Affine current algebra |
| Input relation | Null vector in a degenerate Virasoro module | Sugawara relation between $L_{-1}$ and current modes |
| Typical order | Higher-order scalar equations | First-order matrix equations |
| Main examples | Minimal models | WZW models |
| Blocks controlled | Virasoro blocks | Affine current-algebra blocks |

This analogy is useful, but it should not be pushed too literally. BPZ equations depend on special degenerate Virasoro fields. KZ equations hold broadly for WZW affine primary correlators because the stress tensor is Sugawara.

## Common pitfalls

**Do not apply KZ equations to arbitrary CFTs.** They require affine current algebra and a Sugawara stress tensor of the WZW type.

**Do not treat chiral blocks as full correlators.** KZ solutions can have monodromy. Full local correlators must combine left and right blocks into single-valued expressions.

**Do not forget the denominator $k+h^\vee$.** The dual Coxeter shift is the same quantum shift that appears in the Sugawara construction.

**Do not ignore tensor indices.** The KZ equation is generally matrix-valued. The operators $\Omega_{ij}$ act on finite representation spaces or invariant tensors.

**Do not use ordinary tensor-product channels without integrability.** Local behavior must be interpreted through the WZW fusion rules at level $k$.

**Do not compare signs without checking current conventions.** Hermitian versus anti-Hermitian generators and choices of $z_i-z_j$ versus $z_j-z_i$ can move signs around.

## Relations to other pages

This page uses [Currents and Kac–Moody OPEs](/cft-bootstrap/current-algebras-wzw/currents-and-kac-moody-opes/) for current Ward identities, [Sugawara Construction](/cft-bootstrap/current-algebras-wzw/sugawara-construction/) for the relation between $L_{-1}$ and current modes, and [WZW Primary Fields](/cft-bootstrap/current-algebras-wzw/wzw-primary-fields/) for the definition of affine primaries.

It follows [WZW Fusion Rules](/cft-bootstrap/current-algebras-wzw/wzw-fusion-rules/), because the local solutions of the KZ equations are organized by allowed fusion channels. It also connects back to [Null-Vector Differential Equations](/cft-bootstrap/minimal-models-rational-cft/null-vector-differential-equations/) as the current-algebra analogue of BPZ equations.

Later pages on [Cosets and GKO Construction](/cft-bootstrap/current-algebras-wzw/cosets-gko-construction/), boundary CFT, and Chern–Simons/WZW correspondence use the monodromy and fusion data of KZ conformal blocks.

## Research status

The KZ equations for WZW conformal blocks are established and central in affine CFT. Their relation to braid groups, quantum groups, and Chern–Simons theory is part of the standard rational-CFT toolkit.

Active work uses KZ-type equations and their descendants in geometric representation theory, logarithmic and nonsemisimple CFT, boundary and defect settings, supersymmetric gauge theory, quantum Hall wavefunctions, and higher-dimensional constructions of chiral algebras.

## Exercises

### Exercise 1

Derive the abelian KZ equation and solve it for charges $q_i$.

<details><summary><strong>Solution</strong></summary>

For a $U(1)$ current,

$$
J(z)J(w)\sim\frac{k}{(z-w)^2},
\qquad
J(z)\Phi_{q_i}(w)\sim\frac{q_i\Phi_{q_i}(w)}{z-w}.
$$

The KZ equation is

$$
k\partial_{z_i}\mathcal F
=\sum_{j\ne i}\frac{q_iq_j}{z_i-z_j}\mathcal F.
$$

The function

$$
\mathcal F=\prod_{i<j}(z_i-z_j)^{q_iq_j/k}
$$

satisfies this because differentiating its logarithm gives

$$
\partial_{z_i}\log\mathcal F
=\sum_{j\ne i}\frac{q_iq_j}{k(z_i-z_j)}.
$$

Thus it solves the equation. On the sphere, charge neutrality $\sum_iq_i=0$ is also required for a nonzero correlator.

</details>

### Exercise 2

Show that the KZ equation is translation invariant: summing the equations over all $i$ gives a global translation statement.

<details><summary><strong>Solution</strong></summary>

Sum

$$
(k+h^\vee)\partial_{z_i}\mathcal F
=\sum_{j\ne i}\frac{\Omega_{ij}}{z_i-z_j}\mathcal F
$$

over $i$. The right-hand side cancels pairwise because

$$
\frac{\Omega_{ij}}{z_i-z_j}+\frac{\Omega_{ji}}{z_j-z_i}=0,
$$

and $\Omega_{ij}=\Omega_{ji}$. Hence

$$
(k+h^\vee)\sum_i\partial_{z_i}\mathcal F=0.
$$

Therefore

$$
\sum_i\partial_{z_i}\mathcal F=0,
$$

which is the statement that the chiral block depends only on relative positions, as expected from translation invariance.

</details>

### Exercise 3

For $SU(2)_1$, why does a four spin-one-half correlator have fewer physical fusion channels than the ordinary finite tensor product suggests?

<details><summary><strong>Solution</strong></summary>

The ordinary finite tensor product is

$$
\frac12\otimes\frac12=0+1.
$$

But in $SU(2)_1$, integrable primary labels satisfy

$$
j=0,\frac12.
$$

The spin-$1$ representation is not integrable at level one. The WZW fusion rule is therefore

$$
\frac12\times\frac12=0.
$$

Thus only the vacuum channel is an allowed WZW primary channel in that OPE. The KZ equation must be interpreted with the level-one integrable spectrum, not the unrestricted finite tensor product.

</details>

### Exercise 4

Explain the role of $\Omega_{ij}$ in the KZ equation.

<details><summary><strong>Solution</strong></summary>

The operator

$$
\Omega_{ij}=\kappa_{ab}t_i^a t_j^b
$$

is the invariant two-body Lie-algebra coupling between the representation at $z_i$ and the representation at $z_j$. It acts on the tensor product of representation spaces. In a basis of invariant tensors or intermediate channels, it becomes a matrix.

The KZ equation says that the derivative with respect to $z_i$ is a sum of pairwise interactions between insertion $i$ and every other insertion:

$$
(k+h^\vee)\partial_{z_i}\mathcal F
=\sum_{j\ne i}\frac{\Omega_{ij}}{z_i-z_j}\mathcal F.
$$

Thus $\Omega_{ij}$ is the algebraic part of the logarithmic connection.

</details>

## References

- V. G. Knizhnik and A. B. Zamolodchikov, “Current algebra and Wess–Zumino model in two dimensions,” *Nuclear Physics B* **247** (1984).
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- P. Ginsparg, “Applied Conformal Field Theory,” Les Houches lectures, 1988.
- G. Moore and N. Seiberg, “Classical and quantum conformal field theory,” *Communications in Mathematical Physics* **123** (1989).
- V. Chari and A. Pressley, *A Guide to Quantum Groups*, Cambridge University Press, 1994.

## Version history

- 2026-06-30: First polished draft. Added KZ equation statement, Sugawara derivation, flatness, four-point reduction, abelian solution, monodromy discussion, BPZ comparison, exercises, and references.
