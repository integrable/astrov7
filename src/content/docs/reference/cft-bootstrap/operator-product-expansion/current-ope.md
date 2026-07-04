---
title: "Current OPE"
description: "Derives the operator product expansion of conserved global-symmetry currents with local operators and explains how charges, representations, Ward identities, and current normalization appear in CFT data."
sidebar:
  label: "Current OPE"
  order: 8
level: Graduate
status: "Polished draft"
source: "Di Francesco et al. 1997; Osborn and Petkou 1994; Rychkov 2016; Simmons-Duffin 2017; Poland et al. 2019"
topics:
  - conformal field theory
  - operator product expansion
  - conserved currents
  - Ward identities
  - global symmetries
  - current normalization
canonicalTopics:
  - current-ope
  - conserved-current-multiplets
  - ward-identity-normalization
  - global-symmetry-cft-data
researchStatus:
  established:
    - "For ordinary continuous global symmetries, the leading singularity in the OPE of a conserved current with a local operator is fixed by the charge representation of that operator."
    - "Current-current and current-operator OPEs are standard parts of conformal representation theory and bootstrap kinematics."
  active:
    - "Current-sector bootstrap studies, current four-point functions, anomalies, defects, and generalized symmetries remain active research directions, especially in strongly coupled and non-Lagrangian CFTs."
---

## Summary

A continuous ordinary global symmetry in a CFT is represented by a conserved spin-one current $J_\mu^a$ with scaling dimension

$$
\Delta_J=d-1,
\qquad
\partial^\mu J_\mu^a=0.
$$

Here $a$ is an adjoint index of the global symmetry algebra. The current is not merely another spin-one operator. Its flux through a small sphere is a charge operator, and that charge has a fixed action on local operators. This fixes the leading singular part of the current OPE.

With the convention

$$
[Q^a,\mathcal O_i]=(T^a)_i{}^j\mathcal O_j,
\qquad
Q^a=\int_{S^{d-1}}dS_\mu\,J_\mu^a,
$$

the Euclidean current OPE is

$$
J_\mu^a(x)\mathcal O_i(0)
\sim
{1\over S_d}{x_\mu\over |x|^d}(T^a)_i{}^j\mathcal O_j(0)+\cdots,
\qquad
S_d={2\pi^{d/2}\over \Gamma(d/2)}.
$$

The dots contain less singular terms: descendants of $\mathcal O_i$ and other operators allowed by spin, dimension, and symmetry. The leading term is protected by the Ward identity. It is one of the cleanest places where abstract CFT data meet concrete group representation theory.

<figure class="doc-figure" style="--figure-width: 40rem;">

![The current OPE as charge flux through a small sphere](/figures/cft-bootstrap/current-ope-charge-flow.svg)

<figcaption>

The singular part of $J_\mu^a(x)\mathcal O_i(0)$ is fixed by shrinking a charge sphere around $\mathcal O_i$. The flux of the current acts by the representation matrix $T^a$.

</figcaption>
</figure>

## Prerequisites

You should know [OPE Basics](/cft-bootstrap/operator-product-expansion/ope-basics/), [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/), [Radial Ordering](/cft-bootstrap/operator-product-expansion/radial-ordering/), [Conserved Currents and Short Multiplets](/cft-bootstrap/operators-states-radial-quantization/conserved-currents-and-short-multiplets/), and [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/).

The page uses Euclidean CFT notation. Lorentzian current commutators and factors of $i$ depend on Hermitian-generator conventions. We fix the representation by the radial-quantization commutator $[Q^a,\mathcal O_i]=(T^a)_i{}^j\mathcal O_j$.

## Core idea

A conserved current is a local representative of a global charge. The charge is topological in correlators away from insertions: the integration surface can move without changing the answer until it crosses a charged operator. Therefore a small sphere surrounding a local operator knows the representation of that operator.

For an ordinary global symmetry, define

$$
Q^a(\Sigma)=\int_\Sigma dS_\mu\,J_\mu^a,
$$

where $\Sigma$ is a closed codimension-one surface. Current conservation implies that $Q^a(\Sigma)$ is invariant under smooth deformations of $\Sigma$ that do not cross operator insertions. If $\Sigma$ encloses $\mathcal O_i$, then

$$
Q^a(\Sigma)\mathcal O_i=(T^a)_i{}^j\mathcal O_j.
$$

The OPE must reproduce this statement locally. The only leading vector singularity whose flux through a small sphere is independent of the radius is

$$
{x_\mu\over |x|^d}.
$$

Indeed,

$$
\int_{S_r^{d-1}}dS_\mu\,{x^\mu\over |x|^d}=S_d,
$$

so the normalization $1/S_d$ makes the integrated OPE equal to the charge action.

That is the whole trick. It is delightfully unglamorous and completely load-bearing.

## Setup and conventions

We consider an ordinary continuous global symmetry group $G$ with Lie algebra generators $T^a$ acting on local operators. The current satisfies

$$
\partial^\mu J_\mu^a=0,
\qquad
\Delta_J=d-1,
\qquad
\ell_J=1.
$$

The area of the unit $(d-1)$-sphere is

$$
S_d={2\pi^{d/2}\over \Gamma(d/2)}.
$$

For compact unitary symmetries, one often chooses Hermitian matrices $t^a$ obeying

$$
[t^a,t^b]=i f^{ab}{}_c t^c.
$$

Some CFT and bootstrap formulas instead use anti-Hermitian generators. The OPE formulas below are written in the commutator convention

$$
[Q^a,\mathcal O_i]=(T^a)_i{}^j\mathcal O_j.
$$

If your infinitesimal symmetry variation is $\delta\mathcal O_i=i\epsilon^a(t^a)_i{}^j\mathcal O_j$ with Hermitian $t^a$, then translate once between $T^a$ and $t^a$ and keep that choice fixed. The physics is the charge action, not the placement of $i$.

## Derivation from a small sphere

Insert $J_\mu^a(x)$ near $\mathcal O_i(0)$ inside an arbitrary correlator

$$
\langle J_\mu^a(x)\mathcal O_i(0)X\rangle,
$$

where $X$ denotes other operators outside a small ball around the origin. The leading singularity must have vector index $\mu$ and must integrate to something finite as the sphere radius $r$ shrinks. The tensor $x_\mu/|x|^d$ has precisely this property.

Suppose

$$
J_\mu^a(x)\mathcal O_i(0)
\sim
A{x_\mu\over |x|^d}(T^a)_i{}^j\mathcal O_j(0)+\cdots.
$$

Integrating over a small sphere gives

$$
\int_{S_r^{d-1}}dS^\mu\,J_\mu^a(x)\mathcal O_i(0)
\sim
A\int_{S_r^{d-1}}dS^\mu {x_\mu\over |x|^d}(T^a)_i{}^j\mathcal O_j(0).
$$

Since $x^\mu=r n^\mu$ and $dS^\mu=n^\mu r^{d-1}d\Omega$, the integral is

$$
\int_{S_r^{d-1}}dS^\mu {x_\mu\over |x|^d}=\int d\Omega=S_d.
$$

Matching the charge action forces

$$
A={1\over S_d}.
$$

Thus

$$
J_\mu^a(x)\mathcal O_i(0)
\sim
{1\over S_d}{x_\mu\over |x|^d}(T^a)_i{}^j\mathcal O_j(0)+\cdots.
$$

This leading coefficient is not a tunable OPE coefficient. Once the current and charge normalization are fixed, it is fixed.

## Charged scalar example

Let $G=U(1)$ and let $\mathcal O_q$ have charge $q$:

$$
[Q,\mathcal O_q]=q\mathcal O_q.
$$

Then

$$
J_\mu(x)\mathcal O_q(0)
\sim
{q\over S_d}{x_\mu\over |x|^d}\mathcal O_q(0)+\cdots.
$$

This formula is a local form of Gauss's law for global charge. Surround the operator by a tiny sphere, integrate the current flux, and the answer is $q$ times the operator.

For a neutral operator $\mathcal O_0$ the leading charge singularity is absent:

$$
J_\mu(x)\mathcal O_0(0)
\not\sim
{x_\mu\over |x|^d}\mathcal O_0(0).
$$

A neutral scalar may still have less singular terms in its current OPE if symmetry and spin allow them, but it is not charged under the integrated current.

## Non-Abelian representations

For a non-Abelian symmetry, local operators organize into representations of $G$. If $\mathcal O_i$ is a component of a multiplet in representation $R$, then the current OPE mixes the components:

$$
J_\mu^a(x)\mathcal O_i(0)
\sim
{1\over S_d}{x_\mu\over |x|^d}(T_R^a)_i{}^j\mathcal O_j(0)+\cdots.
$$

This is why CFT correlators with global symmetry carry two kinds of structure.

| Structure | What fixes it |
|---|---|
| Spacetime tensor dependence | Conformal symmetry and spin. |
| Representation indices | Group theory. |
| Overall dynamical coefficients | CFT data, except where Ward identities fix them. |

The current OPE is special because its leading representation action is not dynamical. The theory can change $C_J$, the current two-point normalization, but the charge action on operators is fixed once the current normalization is tied to $Q^a$.

## Current normalization and central charge

A conserved current has a conformally fixed two-point function up to a coefficient. In common $d$-dimensional conventions,

$$
\langle J_\mu^a(x)J_\nu^b(0)\rangle
={C_J\delta^{ab}\over |x|^{2(d-1)}}I_{\mu\nu}(x),
$$

where

$$
I_{\mu\nu}(x)=\delta_{\mu\nu}-2{x_\mu x_\nu\over x^2}.
$$

There is a small but important convention issue. If one freely rescales

$$
J_\mu^a\to \alpha J_\mu^a,
$$

then $C_J$ scales by $\alpha^2$, and the flux $Q^a$ also scales. A physical normalization of $C_J$ requires a choice of charge normalization, usually fixed by the representation matrices $T^a$ acting on operators. Once that choice is made, $C_J$ is meaningful CFT data.

In bootstrap problems, one often sets a two-point normalization for $J$ and then treats the Ward identity as fixing certain three-point coefficients in terms of $C_J$ and representation data. Both descriptions are equivalent; just do not mix them mid-calculation. That road leads to factor-of-$C_J$ goblins.

## Current in the OPE of charged operators

The current can also appear in the OPE of two charged operators. For example, if $\mathcal O_i$ and $\mathcal O_j^\dagger$ transform in conjugate representations, their product can contain the adjoint representation, so $J_\mu^a$ may appear:

$$
\mathcal O_i(x)\mathcal O_j^\dagger(0)
\supset
\lambda_{\mathcal O\mathcal O^\dagger J}\,\mathcal D_\mu(x,\partial)J^\mu_a(0)(T^a)_i{}^j+
\text{descendants}.
$$

The differential operator $\mathcal D_\mu(x,\partial)$ is fixed by conformal symmetry. The coefficient is related by Ward identities to the charge of $\mathcal O$ and to the current normalization. In unit-normalized bootstrap conventions, this is often expressed as a fixed relation between $\lambda_{\mathcal O\mathcal O^\dagger J}$, the charge matrices, and $C_J$.

The practical lesson is simple: whenever a conserved current appears in an OPE, ask whether its coefficient is an independent OPE coefficient or a Ward-fixed coefficient. For the symmetry current, the leading charge action is fixed.

## Current-current OPE

The OPE of two currents contains several universal pieces. Schematically,

$$
J_\mu^a(x)J_\nu^b(0)
\sim
\delta^{ab}C_J{I_{\mu\nu}(x)\over |x|^{2(d-1)}}\mathbf 1
+ f^{ab}{}_c\,\text{current term}
+ \text{stress tensor term}
+ \cdots.
$$

The identity term is controlled by $C_J$. The current term encodes the Lie algebra action of charges on currents. The stress-tensor term is constrained by conformal Ward identities. The remaining terms are ordinary CFT data: scalar singlets, symmetric tensors, antisymmetric tensors, parity-odd structures when allowed, and so on.

This OPE is central in current bootstrap problems. Four-point functions such as

$$
\langle JJJJ\rangle
$$

probe the current sector of the theory, including $C_J$, charged operator spectra, parity structures, anomaly-related data, and stress-tensor exchange.

## Two-dimensional current OPEs

In two dimensions, conserved currents split into holomorphic and antiholomorphic pieces in many important examples. A holomorphic current $J^a(z)$ satisfies

$$
\bar\partial J^a(z)=0.
$$

The current OPE with a primary field is

$$
J^a(z)\phi_i(w,\bar w)
\sim
{(T^a)_i{}^j\phi_j(w,\bar w)\over z-w}+\text{regular}.
$$

The current-current OPE becomes the affine current algebra OPE

$$
J^a(z)J^b(w)
\sim
{k\kappa^{ab}\over (z-w)^2}
+{i f^{ab}{}_cJ^c(w)\over z-w}
+\text{regular}.
$$

Here $k$ is the level and $\kappa^{ab}$ is an invariant quadratic form. This is stronger than the generic $d$-dimensional current story: the holomorphic current modes generate an infinite-dimensional affine Lie algebra. The full development belongs in [Current Algebras and WZW Models](/cft-bootstrap/current-algebras-wzw/), but the local charge-action idea is already visible in the simple pole.

## Selection rules from the current OPE

Current conservation implies global Ward identities. In a correlator of charged local operators,

$$
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle,
$$

the integrated current can be moved through the correlator. If the sphere is pushed past every insertion and shrunk away at infinity, the sum of charge actions must vanish:

$$
\sum_{r=1}^n T_r^a\,
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle=0.
$$

For $U(1)$ charged scalar operators this reduces to the familiar rule

$$
\left(\sum_{r=1}^n q_r\right)
\langle \mathcal O_{q_1}(x_1)\cdots\mathcal O_{q_n}(x_n)\rangle=0.
$$

Thus the correlator vanishes unless total charge is zero. For non-Abelian symmetry, the correlator must be an invariant tensor in the product representation.

## Bootstrap role

The current OPE enters the conformal bootstrap in several ways.

First, global symmetry decomposes OPEs into representation channels. For example, if $\phi_i$ is in a representation $R$, then

$$
R\otimes R
=\bigoplus_\mathcal R \mathcal R,
$$

and the four-point function decomposes into conformal blocks labeled by both spacetime quantum numbers and global-symmetry representations.

Second, the current itself is a protected exchanged operator. It has

$$
\Delta=d-1,
\qquad
\ell=1,
$$

and belongs to the adjoint representation of the global symmetry. Its OPE coefficient with charged external operators is Ward-fixed once $C_J$ and charge normalization are chosen.

Third, bounds on $C_J$ and on the spectrum of charged operators are often sensitive probes of a CFT. In many numerical studies, the current sector helps distinguish possible universality classes, test symmetry enhancement, or constrain gauge-theory fixed points.

Fourth, current correlators are the gateway to anomaly and response data. In even dimensions, some parity-odd or anomalous structures require special care; in odd dimensions, contact terms and Chern–Simons-like response coefficients can appear.

## Common pitfalls

**Treating the leading current OPE coefficient as arbitrary.** The coefficient of $x_\mu|x|^{-d}(T^a\mathcal O)$ is fixed by the charge normalization. Other terms in the OPE may be dynamical, but this one is not.

**Forgetting the sphere area.** If the OPE contains $x_\mu/|x|^d$, the flux integral gives $S_d$. The factor $1/S_d$ is not decoration.

**Mixing Hermitian and anti-Hermitian generator conventions.** Decide whether $[Q^a,\mathcal O]=T^a\mathcal O$ or $\delta\mathcal O=i\epsilon^a t^a\mathcal O$ is your primitive convention. Translate once. Then stop translating.

**Confusing current normalization with charge normalization.** A two-point coefficient $C_J$ is meaningful only after the current is normalized as the current whose flux gives the chosen charges.

**Assuming all spin-one primaries are currents.** A spin-one primary is conserved only if it has $\Delta=d-1$ and satisfies the shortening condition. A generic spin-one primary with $\Delta>d-1$ is not a symmetry current.

**Assuming the two-dimensional affine story holds in all dimensions.** The simple-pole $J^a(z)\phi(w)$ and level-$k$ current algebra are special to holomorphic two-dimensional currents.

## Relations to other pages

- [Conserved Currents and Short Multiplets](/cft-bootstrap/operators-states-radial-quantization/conserved-currents-and-short-multiplets/) explains why conserved currents sit at unitarity bounds.
- [Current Correlators](/cft-bootstrap/correlation-functions/current-correlators/) studies current two- and three-point functions.
- [Conformal Ward Identities for Correlators](/cft-bootstrap/correlation-functions/conformal-ward-identities-for-correlators/) derives the integrated Ward identities in correlator form.
- [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/) explains normalization dependence and index raising.
- [Stress-Tensor OPE](/cft-bootstrap/operator-product-expansion/stress-tensor-ope/) is the spin-two analogue, with conformal transformations replacing internal symmetry transformations.
- [Current Algebras and WZW Models](/cft-bootstrap/current-algebras-wzw/) develops the two-dimensional affine-current enhancement.
- [Generalized Global Symmetries](/symmetry-anomalies-topology/generalized-global-symmetries/) treats higher-form analogues, where charged objects need not be local operators.

## Research status

The leading current OPE and its Ward-identity interpretation are established. They are part of the basic representation theory of local CFTs with ordinary continuous global symmetry.

Active work uses current OPEs and current correlators in more demanding settings: bootstrapping conserved currents and stress tensors directly, diagnosing symmetry enhancement, constraining gauge-theory fixed points, studying parity-odd structures and contact terms, incorporating anomalies, and extending the logic to defects and generalized symmetries.

## Exercises

### Exercise 1: Fix the coefficient by flux

Assume

$$
J_\mu(x)\mathcal O_q(0)
\sim
Aq{x_\mu\over |x|^d}\mathcal O_q(0).
$$

Use $Q=\int_{S_r^{d-1}}dS^\mu J_\mu$ and $[Q,\mathcal O_q]=q\mathcal O_q$ to determine $A$.

<details><summary><strong>Solution</strong></summary>

On the sphere $x^\mu=r n^\mu$ and $dS^\mu=n^\mu r^{d-1}d\Omega$, so

$$
\int_{S_r^{d-1}}dS^\mu {x_\mu\over |x|^d}
=
\int d\Omega=S_d.
$$

The integrated OPE gives

$$
Q\mathcal O_q\sim A q S_d\mathcal O_q.
$$

Matching $q\mathcal O_q$ gives

$$
A={1\over S_d}.
$$

</details>

### Exercise 2: Charge selection rule

Let $\mathcal O_{q_r}$ be scalar operators of $U(1)$ charge $q_r$. Show that their correlator vanishes unless $\sum_r q_r=0$, assuming the vacuum is neutral and there are no charged insertions at infinity.

<details><summary><strong>Solution</strong></summary>

Insert the charge operator on a surface enclosing all operators. Since the vacuum is neutral and the surface can be moved to infinity, the total charge action must vanish:

$$
0=\left\langle [Q,\mathcal O_{q_1}\cdots\mathcal O_{q_n}]\right\rangle.
$$

Using $[Q,\mathcal O_{q_r}]=q_r\mathcal O_{q_r}$ gives

$$
0=\left(\sum_{r=1}^n q_r\right)
\langle \mathcal O_{q_1}\cdots\mathcal O_{q_n}\rangle.
$$

Therefore the correlator can be nonzero only if $\sum_r q_r=0$.

</details>

### Exercise 3: Two-dimensional charge action

Suppose a holomorphic current obeys

$$
J^a(z)\phi_i(w,\bar w)
\sim
{(T^a)_i{}^j\phi_j(w,\bar w)\over z-w}.
$$

Define

$$
J_0^a={1\over 2\pi i}\oint_w dz\,J^a(z).
$$

Show that $J_0^a$ acts on $\phi_i$ by $T^a$.

<details><summary><strong>Solution</strong></summary>

The contour integral extracts the residue of the simple pole:

$$
J_0^a\phi_i(w,\bar w)
={1\over 2\pi i}\oint_w dz\,J^a(z)\phi_i(w,\bar w)
=(T^a)_i{}^j\phi_j(w,\bar w).
$$

Thus the zero mode of the current implements the global symmetry generator on the field.

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997.
- H. Osborn and A. C. Petkou, "Implications of conformal invariance in field theories for general dimensions", *Annals of Physics* 231, 1994.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, 2016.
- D. Simmons-Duffin, "The Conformal Bootstrap", TASI lectures, 2017.
- D. Poland, S. Rychkov, and A. Vichi, "The Conformal Bootstrap: Theory, Numerical Techniques, and Applications", 2019.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, "Generalized Global Symmetries", 2015.

## Version history

- 2026-06-27: First polished draft. Fixes the Ward-normalized current OPE, explains charge-flux normalization, and connects current OPE data to bootstrap conventions.
