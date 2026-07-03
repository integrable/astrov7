---
title: "Anomalous Dimensions of Operators"
description: "How composite-operator renormalization changes engineering dimensions into scaling dimensions and why anomalous dimensions are operator data."
sidebar:
  label: "Anomalous Dimensions of Operators"
  order: 2
level: Graduate
status: "Polished draft"
source: "Coleman 1985, Dilatations; Wilson and Kogut 1974; Weinberg 1996, ch. 18; Zinn-Justin 2021; Collins 1984; Rychkov 2017."
topics:
  - anomalous dimensions
  - composite operators
  - scaling dimensions
  - operator renormalization
  - fixed points
canonicalTopics:
  - anomalous-dimensions
  - local-operators
  - scaling-operators
researchStatus:
  established:
    - "Anomalous dimensions of local operators are standard RG data obtained from composite-operator renormalization and operator mixing."
  active:
    - "Computing anomalous dimensions nonperturbatively or at high perturbative order remains central in critical phenomena, QCD, EFT, CFT, bootstrap, lattice matching, and gauge-theory phenomenology."
---

## Summary

An **anomalous dimension** is the quantum correction to the scaling behavior of a field or local operator. Engineering dimensions come from units and kinetic terms. Anomalous dimensions come from renormalization.

For a multiplicatively renormalized local operator,

$$
\mathcal O_0=Z_{\mathcal O}\mathcal O_R,
$$

this volume defines

$$
\gamma_{\mathcal O}
\equiv
\left.\mu\frac{d\log Z_{\mathcal O}}{d\mu}\right|_{\text{bare data fixed}}.
$$

Then the renormalized operator obeys

$$
\left.\mu\frac{d}{d\mu}\mathcal O_R\right|_{\text{bare}}
=-\gamma_{\mathcal O}\mathcal O_R.
$$

At a fixed point, if the operator is a scaling operator, its full scaling dimension is

$$
\Delta_{\mathcal O}
=
\Delta_{\mathcal O}^{\text{eng}}+\gamma_{\mathcal O,*},
$$

where $\gamma_{\mathcal O,*}$ is evaluated at the fixed point. For operator multiplets, $\gamma$ is a matrix and the scaling operators are its eigenvectors.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 54rem;">

![A map from engineering dimensions through operator renormalization and anomalous dimensions to scaling dimensions at a fixed point.](/figures/renormalization-rg-eft/operator-dimension-renormalization-map.svg)

<figcaption>

Engineering dimensions are the classical starting coordinates. Composite-operator renormalization introduces $Z$ factors and anomalous dimensions. At a fixed point, diagonalizing the anomalous-dimension matrix gives scaling operators with full dimensions $\Delta=\Delta^{\mathrm{eng}}+\gamma_*$. Away from a fixed point, anomalous dimensions govern RG running rather than fixed power-law scaling.

</figcaption>
</figure>

:::note[The most common misconception]
An anomalous dimension is not a small mistake in dimensional analysis. It is real quantum scaling data. The word "anomalous" is historical: it means "not visible in the classical engineering count."
:::

## Prerequisites

You should know [Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), and [Renormalization of Correlation Functions](/renormalization-rg-eft/regularization-counterterms/renormalization-of-correlation-functions/). It is also useful to have read [Composite Operator Renormalization Preview](/renormalization-rg-eft/regularization-counterterms/composite-operator-renormalization-preview/).

This page focuses on local operators. Field anomalous dimensions are included as examples, but the deeper point is that **every local operator can have its own renormalization problem**.

## Core idea

Classically, the dimension of an operator is determined by counting fields and derivatives. Quantum mechanically, products of fields at one point are singular. When a local operator is inserted into correlation functions, new ultraviolet singularities can appear at the insertion point. Removing those singularities requires operator renormalization.

This renormalization changes how the operator responds to a change of scale. That change is its anomalous dimension.

The conceptual chain is

$$
\text{singular local insertion}
\longrightarrow
\text{operator renormalization}
\longrightarrow
\text{anomalous dimension}
\longrightarrow
\text{full scaling dimension at a fixed point}.
$$

For a field $\phi$ at a critical point, the two-point function may scale as

$$
\langle \phi(x)\phi(0)\rangle
\sim
\frac{1}{|x|^{d-2+\eta}}.
$$

The engineering exponent for a free scalar would be $d-2$. The correction $\eta$ is the standard critical exponent associated with the anomalous dimension of the field:

$$
\Delta_\phi=\frac{d-2+\eta}{2}
=\frac{d-2}{2}+\frac{\eta}{2}.
$$

Thus

$$
\gamma_{\phi,*}=\frac{\eta}{2}
$$

for this convention at the fixed point. The exact value of $\eta$ is dynamical data of the universality class.

## Setup and conventions

We use the composite-operator convention fixed in [Conventions and Notation](/renormalization-rg-eft/conventions/):

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R}.
$$

The anomalous-dimension matrix is

$$
\gamma_a{}^b
\equiv
(Z^{-1})_a{}^c
\left.\mu\frac{dZ_c{}^b}{d\mu}\right|_{\text{bare data fixed}}.
$$

Differentiating the bare operator at fixed bare data gives

$$
0=\left.\mu\frac{d}{d\mu}\mathcal O_{a,0}\right|_{\text{bare}}
=
\left.\mu\frac{dZ_a{}^b}{d\mu}\right|_{\text{bare}}\mathcal O_{b,R}
+Z_a{}^b
\left.\mu\frac{d}{d\mu}\mathcal O_{b,R}\right|_{\text{bare}}.
$$

Multiplying by $Z^{-1}$ gives

$$
\left.\mu\frac{d}{d\mu}\mathcal O_{a,R}\right|_{\text{bare}}
=-\gamma_a{}^b\mathcal O_{b,R}.
$$

For one operator with no mixing, this reduces to

$$
\left.\mu\frac{d}{d\mu}\mathcal O_R\right|_{\text{bare}}
=-\gamma_{\mathcal O}\mathcal O_R.
$$

The minus sign in the running of $\mathcal O_R$ is not optional. It follows from the convention $\mathcal O_0=Z_{\mathcal O}\mathcal O_R$.

## Composite operators require renormalization

Even if the parameters and elementary fields in the Lagrangian have been renormalized, a composite operator insertion may still be divergent. Consider a schematic scalar composite operator

$$
\mathcal O(x)=\phi^2(x).
$$

The correlation function

$$
\langle \phi^2(x)\phi(y_1)\cdots\phi(y_n)\rangle
$$

has short-distance singularities as the fields inside $\phi^2(x)$ collide with each other and as $x$ approaches other insertions. The singularities local to the insertion are not removed merely by renormalizing the mass, coupling, and field in the action. One must define a renormalized operator

$$
[\phi^2]_R=Z_{\phi^2}^{-1}\phi_0^2
$$

up to possible mixing with other operators carrying the same quantum numbers.

This is why a composite operator is not just a formal product of renormalized fields. It is a new renormalized insertion.

:::tip[Square brackets]
Many texts write $[\mathcal O]$ to indicate a renormalized composite operator. This volume usually writes $\mathcal O_R$ when the distinction matters. Both notations are reminders that local products need definitions.
:::

## Multiplicative renormalization

Start with the simplest case: one operator that renormalizes into itself.

Let

$$
\mathcal O_0=Z_{\mathcal O}(g,\epsilon)\mathcal O_R.
$$

In a minimal-subtraction-like scheme, $Z_{\mathcal O}$ contains pole terms such as

$$
Z_{\mathcal O}
=1+\frac{a_1(g)}{\epsilon}
+\frac{a_2(g)}{\epsilon^2}
+\cdots.
$$

The anomalous dimension is

$$
\gamma_{\mathcal O}
=
\left.\mu\frac{d\log Z_{\mathcal O}}{d\mu}\right|_{\text{bare}}.
$$

The $\mu$ dependence enters through the running couplings and through explicit factors such as $\mu^{2\epsilon}$ in the bare-renormalized relation. The finite anomalous dimension is extracted from the counterterm structure.

A renormalized correlation function with one insertion obeys an RG equation of the schematic form

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+n\gamma_\phi
+\gamma_{\mathcal O}
\right)
\langle \mathcal O_R(x)\phi_R(x_1)\cdots\phi_R(x_n)\rangle
=0,
$$

away from mass terms and contact terms. The $n\gamma_\phi$ term comes from the $n$ external elementary fields; the $\gamma_{\mathcal O}$ term comes from the inserted operator.

This equation is a compact way to say that the arbitrary scale $\mu$ cannot affect the bare correlator. Its dependence must be compensated by running couplings, field renormalization, and operator renormalization.

## From anomalous dimension to scaling dimension

At a fixed point,

$$
\beta^i(g_*)=0.
$$

For a scaling operator with no mixing, the two-point function takes the form

$$
\langle \mathcal O(x)\mathcal O(0)\rangle
\sim
\frac{1}{|x|^{2\Delta_{\mathcal O}}}
$$

in Euclidean signature, up to normalization and tensor structures.

The engineering dimension tells us the classical part of the exponent. The anomalous dimension shifts it:

$$
\Delta_{\mathcal O}
=\Delta_{\mathcal O}^{\text{eng}}+\gamma_{\mathcal O,*}.
$$

Here $\gamma_{\mathcal O,*}$ means the anomalous dimension evaluated at the fixed point.

Away from a fixed point, it is usually better not to call $\Delta_{\mathcal O}(\mu)$ a literal scaling dimension. The anomalous dimension still exists, but it describes running under RG rather than exact power-law scaling.

The distinction is important:

$$
\text{fixed point}
\quad\Rightarrow\quad
\text{scale-invariant power laws},
$$

whereas

$$
\text{RG trajectory}
\quad\Rightarrow\quad
\text{running and logarithmic scale dependence}.
$$

## Operator mixing

Most operators do not renormalize alone. If several operators have the same symmetries and compatible dimensions, renormalization can mix them:

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R}.
$$

Then

$$
\left.\mu\frac{d}{d\mu}\mathcal O_{a,R}\right|_{\text{bare}}
=-\gamma_a{}^b\mathcal O_{b,R}.
$$

At a fixed point, scaling operators are eigenvectors of the dilatation/RG action. If $v_A{}^a$ is an eigenvector of $\gamma_a{}^b(g_*)$, then

$$
\mathcal O_A=v_A{}^a\mathcal O_{a,R}
$$

has a definite anomalous dimension,

$$
\gamma_a{}^b(g_*)v_A{}^a=\gamma_A v_A{}^b,
$$

up to index-placement conventions. The full scaling dimension is then

$$
\Delta_A=\Delta_A^{\text{eng}}+\gamma_A
$$

when the operators in the mixing block share the same engineering dimension. More generally, one diagonalizes the full linearized RG action, including the engineering-dimension part.

The next pages develop mixing more carefully. The essential point here is that anomalous dimensions are often matrix data, not numbers.

## A scalar example: field anomalous dimension

At the Gaussian fixed point, a scalar field in $d$ dimensions has engineering dimension

$$
\Delta_\phi^{\text{eng}}=\frac{d-2}{2}.
$$

At an interacting critical point, the two-point function often scales as

$$
\langle \phi(x)\phi(0)\rangle
\sim
\frac{1}{|x|^{d-2+\eta}}.
$$

Therefore

$$
\Delta_\phi=\frac{d-2+\eta}{2}.
$$

The anomalous part is

$$
\gamma_{\phi,*}=\frac{\eta}{2}.
$$

In the Wilson–Fisher fixed point near four dimensions, $\eta$ begins at order $\varepsilon_{\text{crit}}^2$, not at order $\varepsilon_{\text{crit}}$. This is one reason the field anomalous dimension is numerically small in the first terms of the $\epsilon$ expansion, while composite operators such as $\phi^2$ receive corrections already at first order.

## A scalar example: the energy operator

In the Ising universality class, the operator often called the energy operator is the scaling operator associated with tuning the temperature-like perturbation. In the Landau–Ginzburg description it is related to $\phi^2$, but the scaling operator is not merely the unrenormalized product $\phi^2$.

At a critical fixed point, the RG eigenvalue $y_t$ of the temperature-like perturbation is related to the correlation-length exponent by

$$
y_t=\frac{1}{\nu}.
$$

The corresponding operator dimension is

$$
\Delta_\epsilon=d-y_t=d-\frac{1}{\nu}.
$$

This is a clean example of how operator dimensions, RG eigenvalues, and critical exponents are the same information written in different languages.

At the Gaussian fixed point, the operator $\phi^2$ has engineering dimension $d-2$. At an interacting fixed point, the full scaling dimension differs:

$$
\Delta_{\phi^2}
=d-2+\gamma_{\phi^2,*}.
$$

Near $d=4-\varepsilon_{\text{crit}}$ for the Wilson–Fisher fixed point, the leading result for the Ising case is schematically

$$
\Delta_{\phi^2}=2-\frac{2}{3}\varepsilon_{\text{crit}}+O(\varepsilon_{\text{crit}}^2),
$$

which differs from the engineering value $d-2=2-\varepsilon_{\text{crit}}$. The difference is the anomalous contribution.

## Protected dimensions

Not every operator dimension is freely renormalized. Symmetry can protect dimensions.

A conserved current in a unitary CFT has dimension

$$
\Delta_J=d-1.
$$

The stress tensor has dimension

$$
\Delta_T=d.
$$

These are not merely engineering guesses. Conservation equations such as

$$
\partial_\mu J^\mu=0,
\qquad
\partial_\mu T^{\mu\nu}=0
$$

shorten the representation of the conformal algebra and fix the dimensions under the usual assumptions.

Similarly, in supersymmetric theories, chiral or BPS operators can have dimensions tied to symmetry charges. This protection belongs to supersymmetry and CFT material, but it is useful to remember here: anomalous dimensions are dynamical, but dynamics can be constrained by symmetry.

## Gauge dependence and physical operators

The anomalous dimension of an elementary field can be gauge dependent. For example, the renormalization of $A_\mu$ or $\psi$ in a gauge-fixed theory can depend on the gauge choice. This does not make field renormalization useless; it is part of perturbative bookkeeping. But it does mean that the anomalous dimension of a gauge-variant field is not usually a standalone physical observable.

Gauge-invariant local operators, such as

$$
F_{\mu\nu}F^{\mu\nu},
\qquad
\bar\psi\psi,
\qquad
\bar\psi\gamma^\mu D^\nu\psi,
$$

have a more direct observable status, though their anomalous dimensions can still depend on scheme and basis away from fixed points. At a fixed point, dimensions of genuine scaling operators are physical CFT data.

The safest hierarchy is:

$$
\text{gauge-variant field anomalous dimensions}
\quad\text{are bookkeeping-sensitive,}
$$

$$
\text{gauge-invariant scaling dimensions at fixed points}
\quad\text{are physical data.}
$$

## Scheme dependence

Away from a fixed point, anomalous dimensions depend on the renormalization scheme and operator basis. If we redefine operators by a finite matrix,

$$
\mathcal O'_a=R_a{}^b(g)\mathcal O_b,
$$

then the anomalous-dimension matrix changes. Schematically,

$$
\gamma' = R\gamma R^{-1}-\mu\frac{dR}{d\mu}R^{-1},
$$

with index placement depending on the convention. The second term appears because the change of basis can itself depend on running couplings.

At a fixed point, the eigenvalues associated with genuine scaling operators are invariant under ordinary nonsingular changes of basis. This is why critical exponents and CFT scaling dimensions are universal even though intermediate $Z$ factors are not.

The practical rule is:

$$
Z\text{ factors are scheme data};
\qquad
\Delta\text{ of scaling operators at fixed points is physical data}.
$$

## Relation to Wilson coefficients

In EFT, local operators appear with Wilson coefficients:

$$
\mathcal L_{\text{EFT}}\supset C_a(\mu)\mathcal O_a(\mu).
$$

The product of coefficient and operator must be independent of the arbitrary scale $\mu$. If operators run as

$$
\mu\frac{d}{d\mu}\mathcal O_a=-\gamma_a{}^b\mathcal O_b,
$$

then Wilson coefficients run with the transpose matrix in the complementary way:

$$
\mu\frac{d}{d\mu}C_a=C_b\gamma_a{}^b+\cdots,
$$

where the dots denote beta-function effects, basis conventions, and possible inhomogeneous terms depending on the EFT setup.

This is one of the main reasons anomalous dimensions matter in practice. They resum logarithms between the matching scale and the measurement scale.

For example, weak effective Hamiltonians, parton distribution evolution, SMEFT running, heavy-quark EFTs, and critical scaling laws all use the same idea: local operators run, so their coefficients must run in the compensating direction.

## The OPE viewpoint

The operator product expansion has the schematic form

$$
\mathcal O_a(x)\mathcal O_b(0)
\sim
\sum_c C_{ab}{}^c(x,\mu,g)\mathcal O_c(0).
$$

The anomalous dimensions of the operators constrain the scale dependence of the coefficient functions. At a fixed point, if the operators are scaling operators, the leading power behavior is controlled by the dimensions:

$$
C_{ab}{}^c(x)
\sim
\frac{\lambda_{ab}{}^c}{|x|^{\Delta_a+\Delta_b-\Delta_c}}
$$

up to tensor structures and normalization conventions.

Thus anomalous dimensions are not merely properties of individual operators. They are part of the algebraic short-distance structure of the theory.

## Common pitfalls

**Anomalous dimensions are not anomalies in the chiral-anomaly sense.** The word "anomalous" here means quantum correction to classical scaling. It is related to scale breaking, but it is not the same object as a gauge or global anomaly.

**A running anomalous dimension is not always a scaling dimension.** Exact scaling dimensions are defined at fixed points. Along an RG trajectory, $\gamma(g(\mu))$ governs running and logarithms.

**Composite operators need their own renormalization.** Renormalizing the Lagrangian parameters and elementary fields does not automatically make every local insertion finite.

**Operator mixing is not optional.** If operators share the same quantum numbers, renormalization can mix them. Ignoring mixing can produce wrong anomalous dimensions and wrong Wilson-coefficient running.

**Field anomalous dimensions can be gauge dependent.** Gauge-variant objects can have useful anomalous dimensions, but they should not be confused with gauge-invariant observable data.

**The sign convention must be checked.** Some books define $\gamma$ with the opposite sign or define $\mathcal O_R=Z\mathcal O_0$ instead of $\mathcal O_0=Z\mathcal O_R$. Always identify the convention before comparing formulas.

**Protected does not mean unrenormalized in every representation.** A conserved current may have protected scaling dimension, but its normalization, contact terms, or improvement terms can still require care.

## Relations to other pages

[Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/) gives the classical part of the dimension. This page explains the quantum correction.

[Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/) develops the fact that anomalous dimensions are usually matrix data.

[Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/) explains the $Z_a{}^b$ matrix more systematically, including basis choices and divergences.

[Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/) focuses on the matrix RG equation and its use in Wilson-coefficient evolution.

[OPE and Short-Distance Expansion](/renormalization-rg-eft/local-operators-and-ope/ope-and-short-distance-expansion/) explains how anomalous dimensions appear in the scale dependence of OPE coefficients.

[Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/) translates operator dimensions into statistical-physics exponents such as $\eta$ and $\nu$.

## Research status

The formal role of anomalous dimensions is settled. They are standard RG data associated with operator renormalization. What remains highly active is their computation and interpretation in difficult theories.

Perturbative anomalous dimensions are computed to high loop order in QCD, SMEFT, critical $O(N)$ models, supersymmetric theories, and many EFTs. Nonperturbative anomalous dimensions are extracted from lattice simulations, conformal bootstrap, large-$N$ methods, integrability, functional RG, and duality. In modern CFT language, the scaling dimensions of local operators are part of the intrinsic data defining the theory.

## Exercises

### Exercise 1: Sign from the renormalization constant

Assume a multiplicatively renormalized operator obeys

$$
\mathcal O_0=Z_{\mathcal O}\mathcal O_R.
$$

Using

$$
\gamma_{\mathcal O}=\mu\frac{d\log Z_{\mathcal O}}{d\mu},
$$

derive the RG equation for $\mathcal O_R$ at fixed bare operator.

<details><summary><strong>Solution</strong></summary>

Differentiate the bare relation at fixed $\mathcal O_0$:

$$
0=\mu\frac{d}{d\mu}\left(Z_{\mathcal O}\mathcal O_R\right)
=\left(\mu\frac{dZ_{\mathcal O}}{d\mu}\right)\mathcal O_R
+Z_{\mathcal O}\mu\frac{d\mathcal O_R}{d\mu}.
$$

Divide by $Z_{\mathcal O}$:

$$
0=\mu\frac{d\log Z_{\mathcal O}}{d\mu}\mathcal O_R
+\mu\frac{d\mathcal O_R}{d\mu}.
$$

Therefore

$$
\mu\frac{d\mathcal O_R}{d\mu}
=-\gamma_{\mathcal O}\mathcal O_R.
$$

</details>

### Exercise 2: Field anomalous dimension and η

At a critical point, suppose

$$
\langle \phi(x)\phi(0)\rangle
\sim
\frac{1}{|x|^{d-2+\eta}}.
$$

Show that

$$
\Delta_\phi=\frac{d-2}{2}+\frac{\eta}{2}.
$$

<details><summary><strong>Solution</strong></summary>

For a scalar scaling operator of dimension $\Delta_\phi$, the two-point function behaves as

$$
\langle \phi(x)\phi(0)\rangle
\sim
\frac{1}{|x|^{2\Delta_\phi}}.
$$

Comparing with

$$
\frac{1}{|x|^{d-2+\eta}},
$$

we get

$$
2\Delta_\phi=d-2+\eta.
$$

Therefore

$$
\Delta_\phi=\frac{d-2+\eta}{2}
=\frac{d-2}{2}+\frac{\eta}{2}.
$$

The anomalous part is $\eta/2$.

</details>

### Exercise 3: Matrix running of two operators

Let two renormalized operators obey

$$
\mu\frac{d}{d\mu}
\begin{pmatrix}
\mathcal O_1\\
\mathcal O_2
\end{pmatrix}
=-
\begin{pmatrix}
a & b\\
0 & c
\end{pmatrix}
\begin{pmatrix}
\mathcal O_1\\
\mathcal O_2
\end{pmatrix}.
$$

At a fixed point with $a\ne c$, what are the anomalous dimensions of the scaling operators?

<details><summary><strong>Solution</strong></summary>

At a fixed point, scaling operators are eigenvectors of the anomalous-dimension matrix. The matrix is triangular:

$$
\gamma=
\begin{pmatrix}
a & b\\
0 & c
\end{pmatrix}.
$$

The eigenvalues of a triangular matrix are its diagonal entries. Therefore the anomalous dimensions are

$$
\gamma_A=a,
\qquad
\gamma_B=c.
$$

The off-diagonal entry $b$ affects the eigenvectors, hence the operator combinations that scale diagonally, but not the eigenvalues when $a\ne c$.

</details>

### Exercise 4: Temperature exponent and operator dimension

At a critical point, the temperature-like coupling has RG eigenvalue $y_t=1/\nu$. Show that the corresponding operator has dimension

$$
\Delta_\epsilon=d-\frac{1}{\nu}.
$$

<details><summary><strong>Solution</strong></summary>

If an operator $\epsilon(x)$ has scaling dimension $\Delta_\epsilon$, then the coupling $t$ in

$$
S\supset t\int d^d x\,\epsilon(x)
$$

has RG eigenvalue

$$
y_t=d-\Delta_\epsilon.
$$

By definition,

$$
y_t=\frac{1}{\nu}.
$$

Therefore

$$
d-\Delta_\epsilon=\frac{1}{\nu},
$$

so

$$
\Delta_\epsilon=d-\frac{1}{\nu}.
$$

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," for scale transformations, anomalous dimensions, Callan–Symanzik equations, and OPE logic.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially chapter 18 on renormalization group methods and renormalized operators.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for composite operators, anomalous dimensions, critical exponents, and short-distance expansions.
- John Collins, *Renormalization*, for systematic composite-operator renormalization and mixing.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for scaling operators and critical phenomena.
- Slava Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, for the CFT interpretation of scaling dimensions and OPE data.

## Version history

- 2026-06-17: First polished draft. Added convention-fixed definitions, connection to scaling dimensions, operator mixing preview, examples, scheme-dependence caveats, OPE relation, and exercises.
