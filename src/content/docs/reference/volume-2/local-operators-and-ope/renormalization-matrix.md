---
title: "Renormalization Matrix"
description: "The matrix relation between bare and renormalized composite-operator bases, including conventions, counterterm extraction, scheme changes, and finite inserted correlators."
sidebar:
  label: "Renormalization Matrix"
  order: 4
level: Graduate
status: "Polished draft"
source: "Collins 1984; Zinn-Justin 2021; Weinberg 1996, ch. 18; Coleman 1985, Dilatations; Schwartz 2014, chs. 19 and 23."
topics:
  - renormalization matrix
  - composite operators
  - operator basis
  - anomalous-dimension matrix
  - Wilson coefficients
canonicalTopics:
  - renormalization-matrix
  - composite-operator-renormalization
  - operator-basis
researchStatus:
  established:
    - "The renormalization matrix relating bare and renormalized operator bases is the standard bookkeeping device for composite-operator counterterms and anomalous dimensions."
  active:
    - "High-order and nonperturbative determinations of renormalization matrices remain active in EFT, lattice matching, flavor physics, QCD factorization, and critical phenomena."
---

## Summary

A **renormalization matrix** is the matrix that relates a bare basis of local composite operators to a renormalized basis. With the conventions of this volume,

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R}.
$$

Equivalently,

$$
\mathcal O_{a,R}=(Z^{-1})_a{}^b\mathcal O_{b,0}.
$$

The matrix $Z_a{}^b$ is chosen so that correlation functions with an insertion of $\mathcal O_{a,R}$ are finite after the usual field and parameter renormalizations have also been performed. It is not itself an observable. It depends on the operator basis, regulator, subtraction scheme, and finite normalization convention.

The anomalous-dimension matrix is derived from $Z$ by

$$
\gamma_a{}^b
=
(Z^{-1})_a{}^c
\bigg.
\mu\frac{dZ_c{}^b}{d\mu}
\bigg|_{\text{bare data fixed}},
$$

so that

$$
\bigg.
\mu\frac{d}{d\mu}\mathcal O_{a,R}
\bigg|_{\text{bare}}
=
-\gamma_a{}^b\mathcal O_{b,R}.
$$

The renormalization matrix is therefore the bridge between divergent inserted correlators and finite RG data.

:::note[The bookkeeping rule]
The matrix $Z$ renormalizes operators. The transpose inverse or transpose appears when one changes Wilson coefficients. Most sign and transpose mistakes in EFT running come from not fixing this convention at the start.
:::

## Prerequisites

You should know [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/) and [Anomalous Dimensions of Operators](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimensions-of-operators/). It is useful to have read [Renormalization of Correlation Functions](/renormalization-rg-eft/regularization-counterterms/renormalization-of-correlation-functions/) and [Renormalized Green Functions](/renormalization-rg-eft/renormalized-perturbation-theory/renormalized-green-functions/).

This page fixes notation. The next page, [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/), uses this notation to derive operator and Wilson-coefficient RG equations.

## Core idea

Field renormalization makes correlation functions of elementary fields finite. Composite-operator renormalization makes correlation functions with local operator insertions finite.

For elementary fields one often writes

$$
\phi_0=Z_\phi^{1/2}\phi_R.
$$

For composite operators, the corresponding relation is usually matrix-valued:

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R}.
$$

The reason is local. When one inserts $\mathcal O_a(x)$ into a Green function, new UV singularities occur as other fields approach $x$ or as fields inside the composite collide. Locality says that the singular part can be subtracted by local operators at $x$. Symmetry says which local operators are allowed. Linear algebra packages the result into $Z_a{}^b$.

The matrix $Z$ answers a concrete question:

> What linear combination of renormalized operators must be called the bare operator so that all inserted correlation functions are finite after subtraction?

This is not a philosophical decoration. It is the object from which anomalous dimensions, scaling operators, Wilson-coefficient running, scheme conversion, and operator matching are extracted.

## Setup and conventions

Let $\mathcal O_{a,0}$ be a column vector of bare operators and $\mathcal O_{a,R}$ a column vector of renormalized operators in the same sector. We write

$$
\boldsymbol{\mathcal O}_0=Z\boldsymbol{\mathcal O}_R,
$$

or in components,

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R}.
$$

Here the lower label $a$ names the bare operator being expressed, and the upper label $b$ names the renormalized operator appearing in the linear combination. This placement is notation, not tensor geometry. Its purpose is to make products readable.

The inverse relation is

$$
\boldsymbol{\mathcal O}_R=Z^{-1}\boldsymbol{\mathcal O}_0,
\qquad
\mathcal O_{a,R}=(Z^{-1})_a{}^b\mathcal O_{b,0}.
$$

The identity matrix is implicit at tree level:

$$
Z=\mathbf 1+\delta Z.
$$

In dimensional regularization with minimal subtraction, $Z$ has the form

$$
Z_a{}^b(g,\epsilon)
=
\delta_a{}^b
+
\sum_{k>0}
\frac{Z_{a,k}{}^b(g)}{\epsilon^k},
$$

where $d=4-2\epsilon$ in the usual four-dimensional convention. In $\overline{\text{MS}}$, the same statement is made after absorbing the standard $\gamma_E-\log4\pi$ constants into the subtraction convention.

In cutoff schemes, the entries of $Z$ can include logarithms and powers of the cutoff. In momentum-subtraction schemes, $Z$ can include finite parts fixed by chosen normalization conditions. None of these choices changes the need for a matrix.

## Inserted correlation functions

Let

$$
G_{a,0}^{(n)}(x;y_1,\ldots,y_n)
=
\langle
\mathcal O_{a,0}(x)
\phi_0(y_1)
\cdots
\phi_0(y_n)
\rangle
$$

be a bare correlation function with one operator insertion. If $\phi_0=Z_\phi^{1/2}\phi_R$, then the renormalized inserted correlator is

$$
G_{a,R}^{(n)}(x;y_1,\ldots,y_n)
=
(Z^{-1})_a{}^b
Z_\phi^{-n/2}
G_{b,0}^{(n)}(x;y_1,\ldots,y_n),
$$

up to additional field, parameter, and contact-term conventions that must be stated in detailed calculations.

This formula is the operational definition of the renormalization matrix. The entries of $Z$ are fixed by requiring $G_{a,R}^{(n)}$ to be finite for a sufficient set of external insertions. "Sufficient" means enough external probes to distinguish all operators in the basis.

For multiple insertions, further singularities occur when operator insertion points collide with each other. Those singularities are the domain of the OPE and multi-local renormalization. A single-insertion renormalization matrix is the first layer, not the whole story of all possible coincident operator products.

## Extracting the matrix from counterterms

Suppose a one-loop calculation of inserted Green functions gives the divergent local structure

$$
G_{a,0}^{\text{div}}
=
A_a{}^b G_{b,\text{tree}},
$$

where $G_{b,\text{tree}}$ denotes the tree-level insertion pattern of $\mathcal O_b$. A minimal counterterm choice is then schematically

$$
\delta Z_a{}^b=-A_a{}^b.
$$

The sign depends on whether one writes bare operators in terms of renormalized operators or renormalized operators in terms of bare ones. With this volume's convention

$$
\boldsymbol{\mathcal O}_0=Z\boldsymbol{\mathcal O}_R,
$$

one checks the sign by substituting into the inserted correlator and demanding cancellation of the pole.

At higher loops,

$$
Z=\mathbf 1+\delta Z^{(1)}+\delta Z^{(2)}+\cdots,
$$

where $\delta Z^{(L)}$ is of $L$-loop order. Higher-loop poles include both new primitive divergences and subdivergences already predicted by lower-loop counterterms. A good calculation checks that the pole structure of $Z$ is consistent with locality and RG equations.

## A two-operator example

Consider a sector with two scalar operators $\mathcal O_1$ and $\mathcal O_2$. The most general matrix is

$$
\begin{pmatrix}
\mathcal O_{1,0}\\
\mathcal O_{2,0}
\end{pmatrix}
=
\begin{pmatrix}
Z_1{}^1 & Z_1{}^2\\
Z_2{}^1 & Z_2{}^2
\end{pmatrix}
\begin{pmatrix}
\mathcal O_{1,R}\\
\mathcal O_{2,R}
\end{pmatrix}.
$$

If the off-diagonal entries vanish, then the operators are multiplicatively renormalized in this basis:

$$
\mathcal O_{1,0}=Z_1{}^1\mathcal O_{1,R},
\qquad
\mathcal O_{2,0}=Z_2{}^2\mathcal O_{2,R}.
$$

But this is a special situation. In general, the finite operator called $\mathcal O_{1,R}$ is defined only after one inverts the matrix:

$$
\mathcal O_{1,R}=(Z^{-1})_1{}^1\mathcal O_{1,0}+(Z^{-1})_1{}^2\mathcal O_{2,0}.
$$

At a fixed point, one may diagonalize the anomalous-dimension matrix and define scaling operators

$$
\widehat{\mathcal O}_I=v_I{}^a\mathcal O_{a,R}.
$$

The matrix $Z$ itself need not be diagonal in the scaling basis at all scales. What becomes diagonal at the fixed point is the action of dilatations or the anomalous-dimension matrix in a suitable basis.

## Operator matrices and coefficient matrices

A common source of mistakes is the distinction between operators and their coefficients. Suppose a deformation is written

$$
\delta S=\int d^d x\,C_R^a\mathcal O_{a,R}.
$$

Using $\mathcal O_0=Z\mathcal O_R$, we have

$$
\mathcal O_R=Z^{-1}\mathcal O_0.
$$

Therefore

$$
C_R^T\mathcal O_R
=C_R^T Z^{-1}\mathcal O_0.
$$

If the same deformation is written in the bare basis as

$$
\delta S=C_0^T\mathcal O_0,
$$

then

$$
C_0=Z^{-T}C_R,
\qquad
C_R=Z^T C_0.
$$

This transpose is not optional. Operators live in a vector space; coefficients live in the dual vector space. If the renormalized operators obey

$$
\mu\frac{d}{d\mu}\boldsymbol{\mathcal O}_R
=
-\gamma\boldsymbol{\mathcal O}_R,
$$

then scale independence of $C_R^T\mathcal O_R$ gives

$$
\mu\frac{d}{d\mu}C_R=\gamma^T C_R.
$$

Many EFT anomalous-dimension matrices are quoted for coefficients rather than for operators. Before comparing formulas, identify which convention is being used.

## Scheme dependence and finite renormalization

A finite change of renormalized operator basis is written

$$
\boldsymbol{\mathcal O}_R'=F\boldsymbol{\mathcal O}_R,
$$

where $F$ is finite and invertible. Since

$$
\boldsymbol{\mathcal O}_0
=
Z\boldsymbol{\mathcal O}_R
=
Z F^{-1}\boldsymbol{\mathcal O}_R',
$$

the new renormalization matrix is

$$
Z'=Z F^{-1}.
$$

The anomalous-dimension matrix transforms as

$$
\gamma'
=
F\gamma F^{-1}
-
\mu\frac{dF}{d\mu}F^{-1}.
$$

If $F$ is independent of the running couplings, this is a similarity transformation. If $F$ depends on couplings, the derivative term is essential. This is the operator version of scheme dependence.

Physical quantities do not depend on this choice when coefficients, matrix elements, and operator definitions are transformed consistently. Truncated perturbative calculations, however, can appear to depend on scheme because neglected higher-order terms are different in different coordinates.

## Minimal subtraction form

In an MS-like scheme, $Z$ subtracts only pole terms. For a one-coupling problem one can write

$$
Z=\mathbf 1
+\frac{Z_1(g)}{\epsilon}
+\frac{Z_2(g)}{\epsilon^2}
+\frac{Z_3(g)}{\epsilon^3}
+\cdots.
$$

The anomalous-dimension matrix is finite as $\epsilon\to0$. This finiteness is a nontrivial check on the pole structure. Higher poles are not independent arbitrary data; RG consistency relates them to lower poles and beta functions.

For a dimensionless coupling $g$ in $d=4-2\epsilon$, the bare coupling typically has the form

$$
g_0=\mu^{p\epsilon}Z_g(g,\epsilon)g,
$$

where $p$ depends on the coupling. Holding bare quantities fixed gives

$$
\mu\frac{d}{d\mu}Z(g,\epsilon)
=
\beta_g(g,\epsilon)\frac{\partial Z}{\partial g}.
$$

The explicit $-\epsilon$ part of $\beta_g(g,\epsilon)$ combines with the pole part of $Z$ to leave a finite anomalous dimension in the physical limit. The detailed formula depends on the normalization of $g$ and on whether one expands in $g$, $g^2$, $\alpha/(4\pi)$, or another loop-counting variable. The invariant lesson is that the coefficient of the simple pole contains the anomalous-dimension data in MS-like schemes, after the coupling convention is fixed.

## Contact terms and basis closure

Composite-operator renormalization has more structure than ordinary field renormalization because insertions have positions. When an equation-of-motion operator is inserted into a separated correlator, it may vanish or reduce to contact terms. When the insertion collides with another field, those contact terms matter.

For example, a schematic equation-of-motion operator

$$
\chi(x)=F(\phi(x))\frac{\delta S}{\delta\phi(x)}
$$

satisfies identities of the form

$$
\langle
\chi(x)
\phi(y_1)
\cdots
\phi(y_n)
\rangle
=
\text{contact terms supported at }x=y_i.
$$

If the goal is an on-shell S-matrix element, one may remove such operators from a reduced basis. If the goal is an off-shell Green-function renormalization matrix, one often needs them for closure.

Total derivatives behave similarly. The integral of $\partial_\mu V^\mu$ may vanish under suitable boundary conditions, but the local operator is not zero. It contributes to momentum-space insertions and to descendant relations.

The renormalization matrix is therefore only meaningful after the basis has been specified, including what has been done with:

- total derivatives;
- equation-of-motion operators;
- BRST-exact operators;
- Bianchi identities and algebraic identities;
- integration by parts;
- evanescent operators;
- flavor and index symmetries.

## Evanescent operators

Dimensional regularization introduces a special basis issue. Some operators vanish in the target integer dimension but are nonzero in $d=4-2\epsilon$. These are called **evanescent operators**.

They matter because a term of order $\epsilon$ multiplying a pole can leave a finite contribution:

$$
O(\epsilon)\times \frac{1}{\epsilon}=O(1).
$$

Therefore evanescent operators can affect finite matching and higher-loop anomalous dimensions of physical operators. This is especially important in four-fermion operator bases, chiral theories, and calculations involving gamma-matrix identities that are dimension-specific.

A careful renormalization matrix may have a block form

$$
Z=
\begin{pmatrix}
Z_{PP} & Z_{PE}\\
Z_{EP} & Z_{EE}
\end{pmatrix},
$$

where $P$ labels physical operators and $E$ labels evanescent operators. The physical answer is obtained only after a prescription is given for defining and subtracting the evanescent sector.

## Conserved currents and protected matrices

If an operator is tied to an exact symmetry, its renormalization matrix is constrained. For a conserved current $J^\mu$ associated with an exact global symmetry, the charge

$$
Q=\int d^{d-1}\mathbf x\,J^0
$$

must generate the symmetry. This can fix the normalization of $J^\mu$ and forbid an anomalous dimension for the conserved current.

In matrix language, this means there is a protected direction in operator space. The protected direction may be a particular linear combination of candidate currents. Other vector operators in the same broad spin sector need not be protected.

For gauge theories, Ward identities, Slavnov–Taylor identities, and BRST cohomology impose stronger and subtler constraints. A gauge-invariant operator basis used for physical matrix elements may be smaller than the off-shell basis needed for intermediate renormalization. The matrix notation does not replace these identities; it gives them a place to act.

## Relation to scaling operators

The renormalization matrix $Z$ is not the scaling matrix. It is a subtraction matrix. The anomalous-dimension matrix derived from it controls scaling. At a fixed point $g_*$, the RG equation becomes linear with constant coefficients:

$$
\mu\frac{d}{d\mu}\boldsymbol{\mathcal O}_R
=
-\gamma_*\boldsymbol{\mathcal O}_R.
$$

If $\gamma_*$ is diagonalizable, choose eigenvectors $v_I{}^a$ such that

$$
v_I{}^a\gamma_a{}^b=\gamma_I v_I{}^b.
$$

Then

$$
\widehat{\mathcal O}_I=v_I{}^a\mathcal O_{a,R}
$$

has scaling dimension

$$
\Delta_I=\Delta_I^{\text{eng}}+\gamma_I,
$$

assuming the engineering dimensions in the sector are appropriately aligned. When the sector contains operators of different engineering dimensions, one must include the engineering scaling matrix as well.

This is the bridge to CFT. A CFT is naturally described by scaling operators, not arbitrary Lagrangian monomials. The renormalization matrix is one way of finding them perturbatively near a fixed point.

## Common pitfalls

**Confusing $Z$ with $\gamma$.** The renormalization matrix subtracts divergences and depends strongly on scheme. The anomalous-dimension matrix is derived from its scale dependence.

**Forgetting the inverse.** If $\mathcal O_0=Z\mathcal O_R$, then $\mathcal O_R=Z^{-1}\mathcal O_0$. Inserted renormalized correlators use $Z^{-1}$, not $Z$.

**Forgetting the transpose for coefficients.** Coefficients live in the dual vector space. If operators run with $-\gamma$, coefficients run with $+\gamma^T$ in the convention used here.

**Treating a finite basis change as physics.** A finite redefinition $\mathcal O_R'=F\mathcal O_R$ changes $Z$ and $\gamma$. Physical predictions are unchanged only if coefficients and matrix elements are transformed consistently.

**Ignoring contact terms.** EOM and total-derivative operators may vanish in one context and be essential in another. The intended observable must be stated.

**Dropping evanescent operators without a prescription.** Operators that vanish as $\epsilon\to0$ can still modify finite results through pole multiplication.

**Using too few external probes.** A calculation that cannot distinguish two basis operators cannot determine the full matrix.

## Relations to other pages

This page formalizes [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/). It prepares [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/), where the RG flow of operators and Wilson coefficients is derived.

The same matrix logic appears in [Counterterm Schemes](/renormalization-rg-eft/renormalized-perturbation-theory/counterterm-schemes/), [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/), and [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/). In EFT chapters, $Z$ matrices for operators become anomalous-dimension matrices for Wilson coefficients. In CFT, diagonalizing $\gamma_*$ identifies scaling operators and their dimensions.

## Research status

The matrix formalism is standard. Active work focuses on difficult sectors: high-loop anomalous dimensions, large operator bases, evanescent-operator prescriptions, gauge-invariant lattice renormalization, nonperturbative renormalization schemes, EFT basis automation, and scheme conversion for precision phenomenology.

Conceptually, the important point is settled: a local operator basis is a coordinate system. The renormalization matrix is the transition function between a regulator-dependent bare coordinate system and a finite renormalized one. Physics appears only after correlators, coefficients, and basis choices are combined consistently.

## Exercises

### Exercise 1: Inverting a one-loop renormalization matrix

Let

$$
Z=
\begin{pmatrix}
1+\frac{a}{\epsilon} & \frac{b}{\epsilon}\\
0 & 1+\frac{c}{\epsilon}
\end{pmatrix}
+O(g^4),
$$

where $a,b,c=O(g^2)$. Find $Z^{-1}$ to order $g^2$.

<details><summary><strong>Solution</strong></summary>

Write $Z=\mathbf 1+A$, where

$$
A=
\begin{pmatrix}
\frac{a}{\epsilon} & \frac{b}{\epsilon}\\
0 & \frac{c}{\epsilon}
\end{pmatrix}
+O(g^4).
$$

To order $g^2$,

$$
Z^{-1}=\mathbf 1-A+O(g^4).
$$

Therefore

$$
Z^{-1}=
\begin{pmatrix}
1-\frac{a}{\epsilon} & -\frac{b}{\epsilon}\\
0 & 1-\frac{c}{\epsilon}
\end{pmatrix}
+O(g^4).
$$

Products such as $ac/\epsilon^2$ are of order $g^4$ and are omitted at this order.

</details>

### Exercise 2: Coefficient transformation under finite basis change

Let $\mathcal O_R'=F\mathcal O_R$ and let $\delta S=C_R^T\mathcal O_R=C_R^{\prime T}\mathcal O_R'$. Show that

$$
C_R'=F^{-T}C_R.
$$

<details><summary><strong>Solution</strong></summary>

Since $\mathcal O_R'=F\mathcal O_R$, we have $\mathcal O_R=F^{-1}\mathcal O_R'$. Then

$$
C_R^T\mathcal O_R
=C_R^T F^{-1}\mathcal O_R'.
$$

Comparing with

$$
C_R^{\prime T}\mathcal O_R',
$$

we obtain

$$
C_R^{\prime T}=C_R^T F^{-1}.
$$

Transposing gives

$$
C_R'=F^{-T}C_R.
$$

</details>

### Exercise 3: Protected current as an eigenvector

Suppose a two-dimensional vector-operator sector has anomalous-dimension matrix

$$
\gamma=
\begin{pmatrix}
a & b\\
c & d
\end{pmatrix}.
$$

An exact conserved current is known to be the combination

$$
J^\mu=v_1\mathcal O_1^\mu+v_2\mathcal O_2^\mu.
$$

What condition must $v=(v_1,v_2)$ satisfy if the current has zero anomalous dimension in this convention?

<details><summary><strong>Solution</strong></summary>

The renormalized operators obey

$$
\mu\frac{d}{d\mu}\mathcal O_R=-\gamma\mathcal O_R.
$$

The combination $J=v^T\mathcal O_R$ has zero anomalous dimension if

$$
\mu\frac{dJ}{d\mu}=0.
$$

Using the operator equation,

$$
\mu\frac{dJ}{d\mu}
=-v^T\gamma\mathcal O_R.
$$

Thus the protected vector must satisfy

$$
v^T\gamma=0.
$$

Equivalently, $v$ is a left eigenvector of $\gamma$ with eigenvalue zero.

</details>

## References

- John Collins, *Renormalization*, for systematic operator renormalization, mixing matrices, and scheme dependence.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for composite operators, renormalization matrices, and short-distance expansions.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially renormalization group methods and renormalized operators.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," for anomalous dimensions and Callan–Symanzik equations.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially renormalized perturbation theory and RG equations.
- Andrzej J. Buras, "Weak Hamiltonian, CP violation and rare decays," for operator renormalization matrices in weak effective Hamiltonians.
- Iain W. Stewart, lectures on effective field theory, for modern Wilson-coefficient and anomalous-dimension matrix conventions.

## Version history

- 2026-06-17: First polished draft. Fixed the convention $\mathcal O_0=Z\mathcal O_R$, derived inserted-correlator and coefficient transformations, and recorded scheme-change and evanescent-operator caveats.
