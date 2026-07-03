---
title: "Anomalous Dimensions"
description: "Defines anomalous dimensions for fields and composite operators, derives their sign conventions from renormalization factors, and explains how they become scaling dimensions at fixed points."
sidebar:
  label: "Anomalous Dimensions"
  order: 3
level: Graduate
status: "Polished draft"
source: "Coleman, Dilatations; Wilson and Kogut 1974; Srednicki §§27–29; Schwartz ch. 23; Weinberg Vol. II ch. 18; Zinn-Justin, RG and composite-operator chapters."
topics:
  - anomalous dimensions
  - field renormalization
  - composite operators
  - operator mixing
  - scaling dimensions
  - Callan–Symanzik equation
canonicalTopics:
  - anomalous-dimension
  - field-renormalization
  - operator-mixing
  - scaling-dimension
  - composite-operator-renormalization
researchStatus:
  established:
    - "Anomalous dimensions are standard RG data extracted from the scale dependence of field and operator renormalization factors. At fixed points, eigenvalues of anomalous-dimension matrices contribute to physical scaling dimensions."
  active:
    - "High-loop anomalous dimensions, large EFT operator-mixing matrices, strongly coupled CFT spectra, lattice determinations, and scheme-independent characterizations away from fixed points remain active research tools and research topics."
---

## Summary

An **anomalous dimension** is the quantum correction to how a field or local operator scales. It is called anomalous because engineering dimensional analysis does not determine it.

For a scalar field with

$$
\phi_0=Z_\phi^{1/2}\phi,
$$

this volume defines

$$
\gamma_\phi(g)
\equiv
\frac12\left.\mu\frac{d\log Z_\phi}{d\mu}\right|_{\text{bare}}.
$$

With this convention, the Callan–Symanzik equation for a renormalized $n$-point Green function contains

$$
+n\gamma_\phi.
$$

For local composite operators,

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R},
$$

the anomalous-dimension matrix is

$$
\gamma_a{}^b
=(Z^{-1})_a{}^c
\left.\mu\frac{d Z_c{}^b}{d\mu}\right|_{\text{bare}}.
$$

The renormalized operators then run as

$$
\left.\mu\frac{d}{d\mu}\mathcal O_{a,R}\right|_{\text{bare}}
=-\gamma_a{}^b\mathcal O_{b,R}.
$$

At a fixed point $g_*$, anomalous dimensions become part of scaling dimensions. For a scalar field with no mixing,

$$
\Delta_\phi=\frac{d-2}{2}+\gamma_\phi(g_*).
$$

For a multiplet of operators, one diagonalizes the appropriate engineering-dimension plus anomalous-dimension matrix.

:::note[Anomalous does not mean optional]
The word is historical. An anomalous dimension is not a mistake, a convention artifact, or a small decoration. At an interacting fixed point it is part of the physical scaling data.
:::

## Prerequisites

You should know [Conventions and Notation](/renormalization-rg-eft/conventions/), especially the sign convention for anomalous dimensions, and [Callan–Symanzik Equation](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/). You should also know [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/), and the motivation for operator mixing from [Composite Operator Renormalization Preview](/renormalization-rg-eft/regularization-counterterms/composite-operator-renormalization-preview/).

The page uses scalar notation first. Spinor fields, gauge fields, tensor operators, EFT operator bases, currents, and stress tensors follow the same logic with more indices and additional symmetry constraints.

## Core idea

Classical dimensional analysis gives the first approximation to scaling. In $d$ spacetime dimensions,

$$
[x]=-1,
\qquad
[\partial_\mu]=1,
\qquad
[\phi]_{\mathrm{eng}}=\frac{d-2}{2}
$$

for a scalar with canonical kinetic term. A local operator built from fields and derivatives has an engineering dimension obtained by adding these ingredients.

Quantum theory adds a new ingredient: local operators probe arbitrarily short distances. Products of fields at nearby points are singular. To make fields and operator insertions finite, one introduces renormalization factors. Their scale dependence is measured by anomalous dimensions.

The conceptual equation is

$$
\text{scaling dimension at a fixed point}
=
\text{engineering dimension}
+
\text{anomalous dimension}.
$$

Away from a fixed point, the anomalous dimension is still a crucial RG function,

$$
\gamma=\gamma(g(\mu)),
$$

but it is not by itself a single universal scaling exponent. A universal exponent emerges when the flow is controlled by a fixed point.

## Setup and conventions

The elementary field convention is

$$
\phi_0=Z_\phi^{1/2}\phi_R.
$$

Usually we suppress the subscript $R$. The bare and renormalized separated-point Green functions are related by

$$
G_0^{(n)}(x_1,\ldots,x_n)
=Z_\phi^{n/2}G_R^{(n)}(x_1,\ldots,x_n).
$$

The field anomalous dimension is

$$
\gamma_\phi
=\frac12\left.\mu\frac{d\log Z_\phi}{d\mu}\right|_{\text{bare}}.
$$

This derivative is taken at fixed bare parameters and fixed regulator. The $\mu$ dependence enters through the renormalized couplings and masses inside $Z_\phi$.

For a massless single-coupling theory, the separated-point Callan–Symanzik equation is

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta(g)\frac{\partial}{\partial g}
+n\gamma_\phi(g)
\right)G_R^{(n)}=0.
$$

For a 1PI vertex function $\Gamma_R^{(n)}$, the field term has the opposite sign:

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta(g)\frac{\partial}{\partial g}
-n\gamma_\phi(g)
\right)\Gamma_R^{(n)}=0.
$$

The sign difference is not mysterious. Ordinary Green functions include external fields. A 1PI vertex is amputated.

## Field anomalous dimensions

The field anomalous dimension measures the scale dependence of field normalization. In perturbation theory it comes from the momentum-dependent part of the self-energy.

For a scalar two-point function, write schematically

$$
G_R^{(2)}(p)^{-1}=p^2-m^2-\Sigma_R(p^2).
$$

A divergent or scale-dependent coefficient of $p^2$ requires a kinetic counterterm and contributes to $Z_\phi$. A momentum-independent divergent correction shifts the mass instead. Thus mass renormalization and field renormalization are physically distinct.

In four-dimensional $\lambda\phi^4$ theory, the one-loop tadpole is momentum independent. It renormalizes the mass but not the kinetic term. Therefore

$$
\gamma_\phi=O(\lambda^2)
$$

in that theory. This is a useful sanity check: not every loop divergence produces a field anomalous dimension.

For gauge fields and fermions in gauge-fixed perturbation theory, field anomalous dimensions can be gauge-dependent. That does not make them useless; they are needed to renormalize Green functions and to check identities. But they should not automatically be interpreted as directly observable numbers.

## Composite operators and mixing

A composite operator is a local product of fields and derivatives, such as

$$
\phi^2,
\qquad
\phi^4,
\qquad
\bar\psi\psi,
\qquad
\bar\psi\gamma^\mu\psi,
\qquad
F_{\mu\nu}F^{\mu\nu}.
$$

Even after the Lagrangian parameters and elementary fields are renormalized, insertions of such operators can create new short-distance singularities. The renormalized operator basis is defined by

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R}.
$$

Operators with the same quantum numbers can mix. In vector notation,

$$
\mathcal O_0=Z\mathcal O_R,
\qquad
\gamma=Z^{-1}\mu\frac{dZ}{d\mu}.
$$

The renormalized operators satisfy

$$
\mu\frac{d\mathcal O_R}{d\mu}=-\gamma\mathcal O_R.
$$

The minus sign is just the statement that the bare operator is fixed while the renormalized basis changes.

Mixing is not a technical annoyance. It is the generic situation. In EFT, weak decays, deep inelastic scattering, critical phenomena, and CFT perturbation theory, the anomalous-dimension matrix is the main object that tells which local structures turn into which other local structures under changes of scale.

## Scaling dimensions at fixed points

At a fixed point,

$$
\beta^i(g_*)=0.
$$

For a field with no mixing, the Callan–Symanzik equation becomes

$$
\left(\mu\frac{\partial}{\partial\mu}
+n\gamma_\phi^*\right)G_R^{(n)}=0,
\qquad
\gamma_\phi^*=\gamma_\phi(g_*).
$$

Combining this RG equation with ordinary dimensional analysis gives

$$
G_R^{(n)}(\lambda x_1,\ldots,\lambda x_n)
=
\lambda^{-n\Delta_\phi}
G_R^{(n)}(x_1,\ldots,x_n),
$$

where

$$
\Delta_\phi=\frac{d-2}{2}+\gamma_\phi^*.
$$

For a scalar two-point function,

$$
\langle \phi(x)\phi(0)\rangle
\propto
\frac{1}{|x|^{2\Delta_\phi}}.
$$

In statistical-physics notation the same correlator is often written

$$
\langle \phi(x)\phi(0)\rangle
\sim
\frac{1}{|x|^{d-2+\eta}}.
$$

Therefore

$$
\eta=2\gamma_\phi^*.
$$

This is one of the cleanest bridges between perturbative field renormalization and measurable critical exponents.

## Operator scaling and diagonalization

For composite operators, the fixed-point scaling problem is matrix-valued. Suppose the operators have the same engineering dimension and mix through

$$
\gamma_a{}^b(g_*).
$$

Then scaling operators are eigenvectors of

$$
\Delta_{\mathrm{eng}}\mathbf 1+\gamma(g_*),
$$

and the eigenvalues are the corresponding scaling dimensions.

If the operator basis contains different engineering dimensions, total derivatives, equations-of-motion operators, or redundant operators, the bookkeeping is more delicate. Symmetries and power counting determine which mixing entries are allowed. The physically meaningful objects are scaling operators and their dimensions, not arbitrary basis components.

Conserved currents provide important checks. At a unitary conformal fixed point, a conserved spin-one current has

$$
\Delta_J=d-1,
$$

and the stress tensor has

$$
\Delta_T=d.
$$

These dimensions are protected by conservation laws. If the current is no longer conserved, the protection can disappear.

## Operator insertions in Callan–Symanzik equations

Consider a correlator with one renormalized composite-operator insertion:

$$
G_{a,R}^{(n;1)}(x_1,\ldots,x_n;y)
=
\langle\phi(x_1)\cdots\phi(x_n)\mathcal O_{a,R}(y)\rangle.
$$

At separated points, the Callan–Symanzik equation has the schematic form

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+n\gamma_\phi
\right)
G_{a,R}^{(n;1)}
+
\gamma_a{}^bG_{b,R}^{(n;1)}=0.
$$

For several insertions, one anomalous-dimension matrix acts on each insertion. When insertion points collide, contact terms appear. These contact terms encode the local operator algebra and are closely related to the operator product expansion.

This is why anomalous dimensions are not merely exponents on two-point functions. They are the RG representation theory of local operators.

## Wilson coefficients and the transpose matrix

Suppose an EFT contains

$$
\mathcal L_{\mathrm{EFT}}
\supset
\sum_a C^a(\mu)\mathcal O_{a,R}(\mu).
$$

If

$$
\mu\frac{d\mathcal O_{a,R}}{d\mu}
=-\gamma_a{}^b\mathcal O_{b,R},
$$

then scale independence of the product $C^a\mathcal O_{a,R}$ implies

$$
\mu\frac{dC^b}{d\mu}=C^a\gamma_a{}^b.
$$

In column-vector notation this is often written

$$
\mu\frac{dC}{d\mu}=\gamma^T C.
$$

The transpose is a common source of mistakes. Operators and Wilson coefficients run oppositely because their product is what appears in the action.

## Minimal subtraction and pole bookkeeping

In minimal subtraction schemes, anomalous dimensions are extracted from pole parts of renormalization factors. For example, let

$$
\log Z_\phi(g,\epsilon)
=
\frac{A_1(g)}{\epsilon}
+\frac{A_2(g)}{\epsilon^2}
+\cdots.
$$

For a coupling written as

$$
g_0=\mu^{\kappa\epsilon}Z_g(g,\epsilon)g,
$$

the $d$-dimensional beta function begins as

$$
\mu\frac{dg}{d\mu}=-\kappa\epsilon g+\beta_{4d}(g).
$$

Thus

$$
\gamma_\phi
=\frac12
\left(-\kappa\epsilon g+\beta_{4d}(g)\right)
\frac{\partial}{\partial g}\log Z_\phi.
$$

The finite anomalous dimension arises when the explicit $\epsilon$ multiplies the pole terms and RG consistency cancels higher-pole singularities. Shortcut formulas are efficient in calculations, but the invariant definition is better for understanding:

$$
\gamma=\text{fixed-bare logarithmic derivative of }Z.
$$

:::caution[Do not memorize a pole shortcut without conventions]
The sign and coefficient in a pole formula depend on how the coupling is normalized, whether one uses $g$, $g^2$, $\lambda$, or $\alpha$, and where powers of $\mu$ are placed. The fixed-bare definition is the safe convention.
:::

## Examples and interpretation

### Scalar critical phenomena

Near the Wilson–Fisher fixed point, the anomalous dimension of the order-parameter field determines the critical exponent $\eta$:

$$
\eta=2\gamma_\phi^*.
$$

The composite operator $\phi^2$ is related to the temperature-like perturbation, and its scaling dimension determines the correlation-length exponent $\nu$. Thus anomalous dimensions turn RG equations into measurable critical exponents.

### Gauge-invariant operators

In gauge theory, operators such as

$$
F_{\mu\nu}F^{\mu\nu},
\qquad
\bar\psi\psi,
\qquad
\bar\psi\gamma^\mu D^\nu\psi+\cdots
$$

can have anomalous dimensions that control physical scaling, OPEs, parton evolution, and EFT running. Elementary gauge-fixed fields may have gauge-dependent anomalous dimensions, but gauge-invariant operator scaling data at fixed points are physical.

### EFT operator bases

In weak decays, SMEFT, heavy-quark EFT, soft-collinear EFT, and many condensed-matter EFTs, anomalous-dimension matrices run Wilson coefficients from a high matching scale to a lower measurement scale:

$$
C(M)
\longrightarrow C(\mu)
\longrightarrow \text{observable}.
$$

The matrix may be large, but the conceptual structure is exactly the one developed here.

## Common pitfalls

**Thinking anomalous dimensions are always physical.** Field anomalous dimensions can depend on gauge and scheme. Scaling dimensions of gauge-invariant operators at fixed points are more directly physical.

**Forgetting operator mixing.** If operators have the same quantum numbers, renormalization usually mixes them. A single anomalous-dimension number may be only a basis-dependent fragment of a matrix.

**Confusing signs for operators and coefficients.** Operators run with $-\gamma$ in this convention. Wilson coefficients run with the transpose sign needed to keep $C^a\mathcal O_a$ invariant.

**Using $\gamma(g)$ as a scaling dimension away from a fixed point.** Away from a fixed point, $\gamma$ is a running function along an RG trajectory. A universal exponent requires fixed-point control.

**Ignoring contact terms.** Operator insertions at coincident points generate local terms. These matter for Ward identities, OPEs, stress tensors, and curved-spacetime applications.

**Suppressing engineering dimensions.** The anomalous part does not replace engineering dimension. The full fixed-point dimension is engineering plus anomalous, after the correct operator basis is chosen.

## Relations to other pages

[Callan–Symanzik Equation](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/) explains where anomalous dimensions enter RG equations for Green functions. [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/) gives the companion flow of couplings. [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/) shows how beta functions are integrated between scales.

[Wavefunction Renormalization](/renormalization-rg-eft/renormalized-perturbation-theory/wavefunction-renormalization/) explains the $Z_\phi$ factors behind field anomalous dimensions. [Composite Operator Renormalization Preview](/renormalization-rg-eft/regularization-counterterms/composite-operator-renormalization-preview/) motivates the operator-mixing matrices used here. [Local Operators and OPE](/renormalization-rg-eft/local-operators-and-ope/) later develops operator mixing, anomalous-dimension matrices, redundant operators, and OPEs in full.

[Fixed Points and Critical Phenomena](/renormalization-rg-eft/fixed-points-critical-phenomena/) uses fixed-point anomalous dimensions to define critical exponents and universality classes. [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/) uses anomalous-dimension matrices to run Wilson coefficients.

## Research status

The definition and perturbative calculation of anomalous dimensions are standard. Field, mass, coupling, and composite-operator anomalous dimensions are routine ingredients in QFT, statistical field theory, and EFT.

Active work includes high-loop anomalous dimensions in gauge theories and critical models, large EFT anomalous-dimension matrices, resummation of operator mixing, anomalous dimensions in conformal bootstrap, integrability-based spectral data, nonperturbative lattice determinations, and scheme-independent descriptions of scaling away from weak coupling.

## Exercises

### Exercise 1: Derive the operator running sign

Assume

$$
\mathcal O_0=Z_\mathcal O\mathcal O_R,
\qquad
\gamma_\mathcal O=Z_\mathcal O^{-1}\left.\mu\frac{dZ_\mathcal O}{d\mu}\right|_{\text{bare}}.
$$

Show that

$$
\left.\mu\frac{d\mathcal O_R}{d\mu}\right|_{\text{bare}}
=-\gamma_\mathcal O\mathcal O_R.
$$

<details><summary><strong>Solution</strong></summary>

Differentiate the bare operator at fixed bare data:

$$
0=
\left.\mu\frac{d\mathcal O_0}{d\mu}\right|_{\text{bare}}
=
\left(\mu\frac{dZ_\mathcal O}{d\mu}\right)\mathcal O_R
+Z_\mathcal O\left.\mu\frac{d\mathcal O_R}{d\mu}\right|_{\text{bare}}.
$$

Multiplying by $Z_\mathcal O^{-1}$ gives

$$
0=\gamma_\mathcal O\mathcal O_R
+
\left.\mu\frac{d\mathcal O_R}{d\mu}\right|_{\text{bare}}.
$$

Therefore

$$
\left.\mu\frac{d\mathcal O_R}{d\mu}\right|_{\text{bare}}
=-\gamma_\mathcal O\mathcal O_R.
$$

</details>

### Exercise 2: Fixed-point two-point scaling

At a fixed point, a scalar operator $\mathcal O$ has dimension $\Delta$. Use translation, rotation, and scale invariance to show that

$$
\langle\mathcal O(x)\mathcal O(0)\rangle
=\frac{A}{|x|^{2\Delta}}
$$

for separated points.

<details><summary><strong>Solution</strong></summary>

Translation invariance makes the correlator a function of $x$. Rotation invariance makes it a function of $|x|$. Scale invariance requires

$$
\langle\mathcal O(\lambda x)\mathcal O(0)\rangle
=\lambda^{-2\Delta}
\langle\mathcal O(x)\mathcal O(0)\rangle.
$$

The functions of $|x|$ satisfying this homogeneity condition are proportional to $|x|^{-2\Delta}$. Therefore

$$
\langle\mathcal O(x)\mathcal O(0)\rangle
=\frac{A}{|x|^{2\Delta}}.
$$

The constant $A$ depends on the normalization of $\mathcal O$.

</details>

### Exercise 3: Wilson coefficients run with the transpose matrix

Let

$$
\mu\frac{d\mathcal O_{a,R}}{d\mu}
=-\gamma_a{}^b\mathcal O_{b,R}.
$$

Demand that $C^a\mathcal O_{a,R}$ be independent of $\mu$. Derive the RG equation for $C^a$.

<details><summary><strong>Solution</strong></summary>

Differentiate:

$$
0=\mu\frac{d}{d\mu}\left(C^a\mathcal O_{a,R}\right)
=
\left(\mu\frac{dC^a}{d\mu}\right)\mathcal O_{a,R}
-C^a\gamma_a{}^b\mathcal O_{b,R}.
$$

Relabel the dummy index in the first term so that both terms multiply $\mathcal O_{b,R}$:

$$
0=
\left(\mu\frac{dC^b}{d\mu}-C^a\gamma_a{}^b\right)\mathcal O_{b,R}.
$$

Thus

$$
\mu\frac{dC^b}{d\mu}=C^a\gamma_a{}^b.
$$

In column-vector notation, $\mu dC/d\mu=\gamma^T C$.

</details>

### Exercise 4: Why conserved currents are protected

A spin-one current $J^\mu$ is conserved at a unitary conformal fixed point. Explain why its scaling dimension is not arbitrary.

<details><summary><strong>Solution</strong></summary>

The conservation equation is

$$
\partial_\mu J^\mu=0.
$$

In a unitary CFT, local operators organize into representations of the conformal algebra. A conserved spin-one current saturates a unitarity bound, and the conservation equation shortens the representation. This fixes

$$
\Delta_J=d-1.
$$

If the current is not conserved, the shortening condition is absent and the dimension can shift.

</details>

## References

- Sidney Coleman, "Dilatations" in *Aspects of Symmetry*, for scale transformations, anomalous dimensions, and the Callan–Symanzik equation.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for anomalous dimensions, fixed points, and critical phenomena.
- Mark Srednicki, *Quantum Field Theory*, especially the renormalization group and effective field theory sections.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter 23 and related renormalization chapters.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for RG methods and operator renormalization.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for composite operators, anomalous dimensions, and critical exponents.

## Version history

- 2026-06-17: First polished draft. Fixed field and operator anomalous-dimension conventions, explained fixed-point scaling dimensions, and connected operator running to EFT Wilson coefficients.
