---
title: "Anomalous-Dimension Matrix"
description: "How the renormalization matrix of composite operators produces operator RG equations, Wilson-coefficient running, scaling operators, and scheme-dependent matrix data."
sidebar:
  label: "Anomalous-Dimension Matrix"
  order: 5
level: Graduate
status: "Polished draft"
source: "Coleman 1985, Dilatations; Wilson and Kogut 1974; Weinberg 1996, ch. 18; Zinn-Justin 2021; Collins 1984; Schwartz 2014, ch. 23."
topics:
  - anomalous-dimension matrix
  - operator mixing
  - Wilson coefficients
  - scaling operators
  - scheme dependence
canonicalTopics:
  - anomalous-dimension-matrix
  - composite-operator-renormalization
  - operator-rg-equations
researchStatus:
  established:
    - "The anomalous-dimension matrix is the standard RG generator obtained from the scale dependence of a composite-operator renormalization matrix."
  active:
    - "Large operator bases, evanescent sectors, high-loop mixing, nonperturbative renormalization, and scheme conversion remain active in QCD, EFT, lattice field theory, critical phenomena, and conformal perturbation theory."
---

## Summary

The **anomalous-dimension matrix** is the matrix that tells a whole sector of local operators how to run under the renormalization group. If the bare and renormalized operator bases are related by

$$
\boldsymbol{\mathcal O}_0=Z\boldsymbol{\mathcal O}_R,
$$

then this volume defines

$$
\gamma
\equiv
Z^{-1}\left.\mu\frac{dZ}{d\mu}\right|_{\text{bare data fixed}},
$$

or in components,

$$
\gamma_a{}^b
=
(Z^{-1})_a{}^c
\left.\mu\frac{dZ_c{}^b}{d\mu}\right|_{\text{bare data fixed}}.
$$

With this convention, renormalized operators obey

$$
\left.\mu\frac{d}{d\mu}\boldsymbol{\mathcal O}_R\right|_{\text{bare}}
=-\gamma\boldsymbol{\mathcal O}_R.
$$

If an action deformation is written as

$$
\delta S=\int d^d x\, C_R^a(\mu)\mathcal O_{a,R}(x),
$$

then the Wilson coefficients live in the dual vector space and run with the transpose matrix:

$$
\mu\frac{dC_R}{d\mu}=\gamma^T C_R
$$

when the displayed operators carry no additional explicit engineering scaling. This transpose is a common source of operator-mixing mistakes, so it is worth fixing the convention before doing any calculation.

:::note[What this page adds]
[Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/) defined $Z$. This page differentiates $Z$, derives the RG equations, explains operator-versus-coefficient conventions, and shows how scaling operators emerge at a fixed point.
:::

## Prerequisites

You should know [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/) and [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/). It is also useful to have read [Anomalous Dimensions of Operators](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimensions-of-operators/), [Callan–Symanzik Equation](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/), and [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/).

The page uses the volume convention

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R}.
$$

If you use the opposite convention, $\mathcal O_R=Z\mathcal O_0$, then several signs and inverses move. The physics does not change, but the formulas do.

## Core idea

Renormalization turns a sector of local operators into a vector bundle over coupling space. The renormalization matrix $Z$ chooses a finite frame for that bundle. The anomalous-dimension matrix $\gamma$ is the connection-like object that tells the frame how to change when the renormalization scale changes.

That geometric wording is useful, but the calculation is simple. Bare operators are independent of the arbitrary renormalization scale. Renormalized operators are not. Therefore differentiating

$$
\boldsymbol{\mathcal O}_0=Z\boldsymbol{\mathcal O}_R
$$

at fixed bare data gives an RG equation for $\boldsymbol{\mathcal O}_R$. That equation is matrix-valued because renormalization can rotate one local operator into another operator with the same exact labels.

The conceptual chain is

$$
\text{local operator basis}
\longrightarrow
Z\text{ matrix}
\longrightarrow
\gamma=Z^{-1}\mu\frac{dZ}{d\mu}
\longrightarrow
\text{operator and coefficient RG equations}.
$$

At a fixed point, the same matrix becomes part of the dilatation operator. Diagonalizing it identifies scaling operators and their dimensions. Away from a fixed point, it controls running and mixing rather than fixed power-law scaling.

## Setup and conventions

Let $\boldsymbol{\mathcal O}_R$ denote a column vector of renormalized local operators in one mixing sector:

$$
\boldsymbol{\mathcal O}_R
=
\begin{pmatrix}
\mathcal O_{1,R}\\
\mathcal O_{2,R}\\
\vdots
\end{pmatrix}.
$$

The bare basis is related to it by

$$
\boldsymbol{\mathcal O}_0=Z(g,\epsilon,\mu)\boldsymbol{\mathcal O}_R.
$$

The matrix $Z$ may depend on the renormalized couplings $g^i(\mu)$, the regulator, and the subtraction scheme. In dimensional regularization with an MS-like scheme it is usually a pole matrix,

$$
Z=
\mathbf 1+
\sum_{k\ge 1}\frac{Z_k(g)}{\epsilon^k},
$$

where $d=4-2\epsilon$ for four-dimensional examples. In cutoff or momentum-subtraction schemes, $Z$ can contain logarithms, powers, and finite parts.

The anomalous-dimension matrix is

$$
\gamma(g)
=
Z^{-1}
\left.\mu\frac{dZ}{d\mu}\right|_{\text{bare}}.
$$

The derivative is taken at fixed bare parameters and fixed bare operator basis. Equivalently, if $Z$ depends on $\mu$ only through running couplings,

$$
\gamma
=
Z^{-1}\beta^i(g,\epsilon)\frac{\partial Z}{\partial g^i},
$$

where $\beta^i(g,\epsilon)=\mu dg^i/d\mu|_{\text{bare}}$ includes the dimension-dependent $\epsilon$ terms before the limit $\epsilon\to0$ is taken.

This formula is the safest one. In minimal-subtraction calculations, it is often simplified to a formula involving the simple-pole matrix $Z_1(g)$, but the precise sign and numerical factor depend on the coupling convention.

## Derivation of the operator RG equation

Differentiate the bare-renormalized relation at fixed bare data:

$$
0
=
\left.\mu\frac{d}{d\mu}\boldsymbol{\mathcal O}_0\right|_{\text{bare}}
=
\left(\left.\mu\frac{dZ}{d\mu}\right|_{\text{bare}}\right)\boldsymbol{\mathcal O}_R
+Z\left.\mu\frac{d}{d\mu}\boldsymbol{\mathcal O}_R\right|_{\text{bare}}.
$$

Multiplying by $Z^{-1}$ gives

$$
\left.\mu\frac{d}{d\mu}\boldsymbol{\mathcal O}_R\right|_{\text{bare}}
=-Z^{-1}\left(\left.\mu\frac{dZ}{d\mu}\right|_{\text{bare}}\right)\boldsymbol{\mathcal O}_R.
$$

Therefore

$$
\left.\mu\frac{d}{d\mu}\boldsymbol{\mathcal O}_R\right|_{\text{bare}}
=-\gamma\boldsymbol{\mathcal O}_R.
$$

In components,

$$
\left.\mu\frac{d}{d\mu}\mathcal O_{a,R}\right|_{\text{bare}}
=-\gamma_a{}^b\mathcal O_{b,R}.
$$

This sign is not optional. It follows from holding the bare operator fixed. If $Z$ increases with $\mu$, the renormalized operator must compensate.

## Inserted Callan–Symanzik equations

For a renormalized correlation function with one operator insertion,

$$
G_{a,R}^{(n)}(x;y_1,\ldots,y_n)
=
\langle \mathcal O_{a,R}(x)\phi_R(y_1)\cdots\phi_R(y_n)\rangle,
$$

the RG equation schematically has the form

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
+n\gamma_\phi
\right)G_{a,R}^{(n)}
+
\gamma_a{}^b G_{b,R}^{(n)}
=0,
$$

for a single scalar field species, away from explicit mass terms and contact terms.

The sign of the matrix term is consistent with the operator equation. Since the operator itself runs as $-\gamma\mathcal O_R$, moving that running into the differential operator on the correlator produces the plus sign shown above.

For multiple field species, use the appropriate field anomalous-dimension matrices. For composite operators with derivatives, conserved currents, gauge constraints, or equation-of-motion terms, contact terms must be handled explicitly.

## Wilson coefficients live in the dual space

Operator mixing is only half the story. In an effective action or deformed action, operators appear with coefficients:

$$
\delta S
=
\int d^d x\,C_R^a\mathcal O_{a,R}.
$$

In vector notation this is

$$
\delta S=\int d^d x\, C_R^T\boldsymbol{\mathcal O}_R.
$$

If the bare deformation is fixed, the product $C_R^T\boldsymbol{\mathcal O}_R$ must be independent of the arbitrary scale $\mu$. Therefore

$$
0
=
\mu\frac{d}{d\mu}
\left(C_R^T\boldsymbol{\mathcal O}_R\right)
=
\left(\mu\frac{dC_R}{d\mu}\right)^T\boldsymbol{\mathcal O}_R
-C_R^T\gamma\boldsymbol{\mathcal O}_R.
$$

Since this must hold for arbitrary insertions,

$$
\mu\frac{dC_R}{d\mu}=\gamma^T C_R.
$$

This equation is the basic source of anomalous-dimension matrices in EFT. Many papers quote $\gamma$ as the coefficient-running matrix rather than the operator-running matrix. In this volume, unless stated otherwise,

$$
\mu\frac{d}{d\mu}\boldsymbol{\mathcal O}_R=-\gamma\boldsymbol{\mathcal O}_R,
\qquad
\mu\frac{d}{d\mu}C_R=\gamma^T C_R.
$$

When coefficients are made dimensionless by extracting powers of $\mu$ or a heavy scale, classical scaling terms must be added. For example, if $\mathcal O_a$ has engineering dimension $\Delta_a^{\text{eng}}$, the dimensionless coefficient $\widetilde C^a$ typically obeys a classical term proportional to $d-\Delta_a^{\text{eng}}$ in addition to the anomalous term.

## Fixed points and scaling operators

At a fixed point $g_*$, all beta functions vanish:

$$
\beta^i(g_*)=0.
$$

If the anomalous-dimension matrix is evaluated at the fixed point, it becomes a constant matrix,

$$
\gamma_*\equiv \gamma(g_*).
$$

If the operator basis has a common engineering dimension and $\gamma_*$ is diagonalizable, choose left eigenvectors $v_I{}^a$ satisfying

$$
v_I{}^a\gamma_a{}^b=\gamma_I v_I{}^b.
$$

Then

$$
\widehat{\mathcal O}_I=v_I{}^a\mathcal O_{a,R}
$$

runs multiplicatively:

$$
\mu\frac{d}{d\mu}\widehat{\mathcal O}_I
=-\gamma_I\widehat{\mathcal O}_I.
$$

The full scaling dimension is

$$
\Delta_I
=
\Delta^{\text{eng}}+\gamma_I.
$$

If the sector contains operators of different engineering dimensions, the fixed-point dilatation matrix is not just $\gamma_*$. One must include the engineering-dimension matrix:

$$
\Delta_a{}^b
=
\Delta_{\text{eng},a}\delta_a{}^b+\gamma_{*,a}{}^b,
$$

in a basis where the engineering part is diagonal. Scaling operators are eigenvectors of this full matrix.

The lesson is simple: anomalous dimensions are not attached to names of monomials. They are attached to eigenoperators of the dilatation operator.

## A triangular two-operator example

Suppose two operators obey

$$
\mu\frac{d}{d\mu}
\begin{pmatrix}
\mathcal O_{1,R}\\
\mathcal O_{2,R}
\end{pmatrix}
=
-
\begin{pmatrix}
\gamma_1 & \kappa\\
0 & \gamma_2
\end{pmatrix}
\begin{pmatrix}
\mathcal O_{1,R}\\
\mathcal O_{2,R}
\end{pmatrix}.
$$

Then

$$
\mu\frac{d\mathcal O_{2,R}}{d\mu}=-\gamma_2\mathcal O_{2,R},
$$

so $\mathcal O_2$ runs multiplicatively. But

$$
\mu\frac{d\mathcal O_{1,R}}{d\mu}
=-\gamma_1\mathcal O_{1,R}-\kappa\mathcal O_{2,R}.
$$

The first operator feeds into the second under scale evolution. For the coefficients,

$$
\mu\frac{d}{d\mu}
\begin{pmatrix}
C_1\\
C_2
\end{pmatrix}
=
\begin{pmatrix}
\gamma_1 & 0\\
\kappa & \gamma_2
\end{pmatrix}
\begin{pmatrix}
C_1\\
C_2
\end{pmatrix}.
$$

The arrow has transposed. If a high-scale matching calculation generates only $C_1$, RG evolution can generate $C_2$ when $\kappa\ne0$. This is the algebra behind many EFT statements of the form "operator $\mathcal O_1$ mixes into operator $\mathcal O_2$."

## Solving the matrix RG equation

If $\gamma$ is approximately constant over the range of scales, the operator equation has the formal solution

$$
\boldsymbol{\mathcal O}_R(\mu)
=
\exp\left[-\gamma\log\frac{\mu}{\mu_0}\right]
\boldsymbol{\mathcal O}_R(\mu_0).
$$

The coefficient equation is

$$
C_R(\mu)
=
\exp\left[\gamma^T\log\frac{\mu}{\mu_0}\right]
C_R(\mu_0).
$$

If $\gamma$ depends on running couplings, matrices at different scales need not commute. The solution is then a path-ordered exponential:

$$
\boldsymbol{\mathcal O}_R(\mu)
=
P\exp\left[-\int_{\log\mu_0}^{\log\mu}dt\,\gamma(g(t))\right]
\boldsymbol{\mathcal O}_R(\mu_0),
$$

and

$$
C_R(\mu)
=
P\exp\left[\int_{\log\mu_0}^{\log\mu}dt\,\gamma^T(g(t))\right]
C_R(\mu_0),
$$

with the ordering convention stated whenever noncommuting matrices matter.

In many one-loop applications, $\gamma(g(t))$ is proportional to a fixed matrix times a scalar running coupling. Then the ordering is harmless. In multi-coupling or higher-loop problems, it may not be.

## Minimal subtraction and the simple pole

In MS-like schemes, anomalous dimensions are extracted from pole terms. Let

$$
Z=\mathbf 1+\frac{Z_1(g)}{\epsilon}+\frac{Z_2(g)}{\epsilon^2}+\cdots.
$$

Then

$$
\gamma
=
\lim_{\epsilon\to0}
Z^{-1}\beta^i(g,\epsilon)\frac{\partial Z}{\partial g^i}.
$$

This expression is finite if the counterterms are consistent with locality and RG invariance. The finite result is determined by the simple-pole data, while higher poles are constrained by lower-order information.

For a one-coupling example with

$$
g_0=\mu^{\kappa\epsilon}Z_g(g,\epsilon)g,
$$

and with $Z$ expanded as above, the leading MS-like extraction has the schematic form

$$
\gamma(g)=-\kappa g\frac{\partial Z_1(g)}{\partial g}
$$

up to the exact definition of $g$ and the loop-counting variable. If the coupling variable is $a=g^2/(16\pi^2)$ rather than $g$, or if the bare coupling carries $\mu^{2\epsilon}$ rather than $\mu^\epsilon$, the factor changes. The invariant formula with $\beta^i(g,\epsilon)$ is the one to trust.

:::tip[Practical check]
A computed $\gamma$ must be finite as $\epsilon\to0$. If poles remain in $\gamma$, either the operator basis is not closed, the subdivergences were not subtracted consistently, or the convention for $Z$ has been applied incorrectly.
:::

## Scheme changes

A finite change of renormalized operator basis is

$$
\boldsymbol{\mathcal O}_R'=F(g)\boldsymbol{\mathcal O}_R,
$$

where $F$ is finite and invertible. The anomalous-dimension matrix transforms as

$$
\gamma'
=
F\gamma F^{-1}
-
\mu\frac{dF}{d\mu}F^{-1}.
$$

If $F$ depends on running couplings, then

$$
\mu\frac{dF}{d\mu}=\beta^i\frac{\partial F}{\partial g^i}.
$$

At a fixed point, if $F(g_*)$ is finite and nonsingular, the derivative term vanishes because $\beta^i(g_*)=0$, and the transformation is a similarity transformation:

$$
\gamma_*'=F(g_*)\gamma_*F(g_*)^{-1}.
$$

Therefore eigenvalues of $\gamma_*$ are scheme independent. Away from a fixed point, the entries of $\gamma$ are scheme dependent. Physical predictions remain invariant only after operators, coefficients, matrix elements, and matching conditions are transformed together.

## Protected directions and conservation laws

Some rows or eigenvectors of $\gamma$ are constrained by exact symmetries. A conserved current associated with an exact global symmetry has protected dimension

$$
\Delta_J=d-1.
$$

The stress tensor has protected dimension

$$
\Delta_T=d.
$$

These statements mean that the corresponding properly normalized operators have zero anomalous dimension. In a mixed sector, the protected current or stress tensor may be a particular linear combination, not the first operator one happened to write.

For example, if

$$
J^\mu=v^a\mathcal O_a^\mu,
$$

is exactly conserved and normalized as the generator of a symmetry, then

$$
v^a\gamma_a{}^b=0
$$

in the convention where $J^\mu=v^T\boldsymbol{\mathcal O}_R$.

Gauge theories add further structure. Gauge-invariant operators, BRST-exact operators, and equation-of-motion operators can mix in intermediate off-shell calculations, while physical matrix elements depend only on the appropriate cohomology class.

## Degeneracies and Jordan blocks

Not every anomalous-dimension matrix is diagonalizable in every basis. When two operators have equal or nearly equal dimensions, perturbative diagonalization can require care. If the fixed-point dilatation matrix has a Jordan block, correlation functions can acquire logarithmic scaling:

$$
\langle \mathcal O_1(x)\mathcal O_2(0)\rangle
\sim
\frac{\log |x|}{|x|^{2\Delta}}.
$$

Such logarithmic behavior is familiar in logarithmic CFTs and can also appear as a warning sign in perturbative calculations with incomplete diagonalization or degenerate perturbation theory.

In ordinary unitary CFTs, the dilatation operator is strongly constrained, and scaling operators are usually chosen to diagonalize two-point functions and dilatations simultaneously. In nonunitary theories, gauge-fixed sectors, statistical models with replicas, and logarithmic theories, the matrix structure can be more subtle.

## Common pitfalls

**Confusing operator running with coefficient running.** Operators run with $-\gamma$ in this convention. Coefficients run with $+\gamma^T$ after the product $C^T\mathcal O$ is held fixed.

**Comparing matrices without comparing conventions.** Some authors define $\gamma$ with the opposite sign, use $\mathcal O_R=Z\mathcal O_0$, or quote the coefficient-running matrix. Translate before comparing entries.

**Diagonalizing $Z$ instead of the dilatation matrix.** $Z$ is a subtraction matrix. Scaling dimensions come from the anomalous-dimension matrix, together with engineering dimensions at a fixed point.

**Forgetting engineering dimensions.** If the basis contains operators of different engineering dimensions, the full scaling matrix is not just $\gamma_*$. Classical scaling must be included.

**Treating scheme-dependent entries as observables.** Matrix entries away from fixed points depend on basis and scheme. Eigenvalues at fixed points and physical predictions are the meaningful data.

**Dropping evanescent operators too early.** Operators that vanish in four dimensions can change higher-loop anomalous dimensions and finite matching through $\epsilon\times1/\epsilon$ effects.

**Ignoring contact terms.** Local operator insertions have contact singularities. The anomalous-dimension matrix for separated correlators may not contain all information needed for local Ward identities or multi-insertion products.

## Relations to other pages

This page follows [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/) and prepares [OPE and Short-Distance Expansion](/renormalization-rg-eft/local-operators-and-ope/ope-and-short-distance-expansion/). The OPE uses the same operator basis and anomalous-dimension data, but organizes products of nearby operators rather than single insertions.

The coefficient-running equation is the same structure used in [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Running in EFT](/renormalization-rg-eft/effective-field-theory/running-in-eft/), and [Renormalization Group Evolution](/renormalization-rg-eft/matching-running-decoupling/renormalization-group-evolution/). At fixed points, diagonalizing $\gamma_*$ connects directly to [Scale Invariance](/renormalization-rg-eft/fixed-points-critical-phenomena/scale-invariance/) and to CFT scaling operators.

## Research status

The formalism is settled. The hard work is computational and structural. Modern applications include high-loop QCD anomalous dimensions, weak effective Hamiltonians, SMEFT operator mixing, SCET anomalous dimensions, lattice-to-continuum matching, conformal perturbation theory, critical exponents, evanescent-operator schemes, and nonperturbative determinations of scaling dimensions.

The conceptual rule remains stable across these applications: an anomalous-dimension matrix is not a table of mystical dimensions. It is the RG generator associated with a chosen basis of local operators.

## Exercises

### Exercise 1: Derive the sign of operator running

Assume

$$
\boldsymbol{\mathcal O}_0=Z\boldsymbol{\mathcal O}_R
$$

and

$$
\gamma=Z^{-1}\mu\frac{dZ}{d\mu}
$$

at fixed bare data. Derive the RG equation for $\boldsymbol{\mathcal O}_R$.

<details><summary><strong>Solution</strong></summary>

Differentiate the bare-renormalized relation at fixed bare data:

$$
0=\mu\frac{d}{d\mu}\boldsymbol{\mathcal O}_0
=\left(\mu\frac{dZ}{d\mu}\right)\boldsymbol{\mathcal O}_R
+Z\mu\frac{d}{d\mu}\boldsymbol{\mathcal O}_R.
$$

Multiplying by $Z^{-1}$ gives

$$
\mu\frac{d}{d\mu}\boldsymbol{\mathcal O}_R
=-Z^{-1}\left(\mu\frac{dZ}{d\mu}\right)\boldsymbol{\mathcal O}_R.
$$

Using the definition of $\gamma$,

$$
\mu\frac{d}{d\mu}\boldsymbol{\mathcal O}_R
=-\gamma\boldsymbol{\mathcal O}_R.
$$

</details>

### Exercise 2: Coefficients run with the transpose

Let

$$
\delta S=C^T\boldsymbol{\mathcal O}_R
$$

and suppose the renormalized operator vector obeys

$$
\mu\frac{d}{d\mu}\boldsymbol{\mathcal O}_R=-\gamma\boldsymbol{\mathcal O}_R.
$$

Demand $\mu d(\delta S)/d\mu=0$. Derive the RG equation for $C$.

<details><summary><strong>Solution</strong></summary>

We compute

$$
0=\mu\frac{d}{d\mu}\left(C^T\boldsymbol{\mathcal O}_R\right)
=\left(\mu\frac{dC}{d\mu}\right)^T\boldsymbol{\mathcal O}_R
+C^T\left(-\gamma\boldsymbol{\mathcal O}_R\right).
$$

Thus

$$
\left(\mu\frac{dC}{d\mu}\right)^T=C^T\gamma.
$$

Transposing gives

$$
\mu\frac{dC}{d\mu}=\gamma^T C.
$$

</details>

### Exercise 3: Diagonalizing a two-operator sector

Let

$$
\gamma=
\begin{pmatrix}
\gamma_1 & \kappa\\
0 & \gamma_2
\end{pmatrix},
\qquad \gamma_1\ne\gamma_2.
$$

Find a left eigenvector with eigenvalue $\gamma_1$ and a left eigenvector with eigenvalue $\gamma_2$.

<details><summary><strong>Solution</strong></summary>

A left eigenvector $v=(v_1,v_2)$ satisfies

$$
v\gamma=\lambda v.
$$

For $\lambda=\gamma_1$,

$$
(v_1\gamma_1,\,v_1\kappa+v_2\gamma_2)
=(\gamma_1 v_1,\,\gamma_1 v_2).
$$

The first equation is automatic. The second gives

$$
v_1\kappa+v_2\gamma_2=\gamma_1v_2,
$$

so

$$
v_2=\frac{\kappa}{\gamma_1-\gamma_2}v_1.
$$

One choice is

$$
v^{(1)}=\left(1,\frac{\kappa}{\gamma_1-\gamma_2}\right).
$$

For $\lambda=\gamma_2$, the first component equation gives

$$
v_1\gamma_1=\gamma_2v_1,
$$

so $v_1=0$ because $\gamma_1\ne\gamma_2$. A choice is

$$
v^{(2)}=(0,1).
$$

The corresponding scaling operators are the left-eigenvector combinations of the operator column.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," for scale transformations, anomalous dimensions, and Callan–Symanzik equations.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for operator dimensions, fixed points, and RG linearization.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for composite operators, renormalization matrices, and critical exponents.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially renormalization group methods and renormalized operators.
- John Collins, *Renormalization*, for systematic treatment of operator mixing and anomalous dimensions.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the renormalization group and EFT-motivated operator running.

## Version history

- 2026-06-17: First polished draft. Derived the anomalous-dimension matrix from $\mathcal O_0=Z\mathcal O_R$, fixed operator and coefficient running conventions, and recorded fixed-point, scheme-change, and MS-extraction caveats.
