---
title: "Operator Mixing"
description: "Why local operators with the same quantum numbers form vector spaces under renormalization, and how to organize a mixing problem before computing anomalous dimensions."
sidebar:
  label: "Operator Mixing"
  order: 3
level: Graduate
status: "Polished draft"
source: "Coleman 1985, Dilatations; Wilson and Kogut 1974; Weinberg 1996, ch. 18; Zinn-Justin 2021; Collins 1984; Schwartz 2014, chs. 19 and 23."
topics:
  - operator mixing
  - composite operators
  - renormalization
  - symmetry sectors
  - operator bases
canonicalTopics:
  - operator-mixing
  - composite-operator-renormalization
  - operator-basis
researchStatus:
  established:
    - "Operator mixing is a standard consequence of composite-operator renormalization: renormalization acts linearly on the vector space of operators with compatible quantum numbers."
  active:
    - "Choosing efficient operator bases and computing high-order mixing matrices remain active in EFT, QCD, conformal perturbation theory, lattice matching, and bootstrap-adjacent fixed-point studies."
---

## Summary

**Operator mixing** is the statement that renormalization usually does not preserve a single local operator. It preserves a **sector** of local operators with the same exact labels, and it acts on that sector by a matrix.

If $\mathcal O$ and $\widetilde{\mathcal O}$ are unrelated operators, there is no reason they should mix. But if $\mathcal O_1,\mathcal O_2,\ldots$ have the same Lorentz representation, internal charges, gauge-invariant or BRST cohomology class, discrete quantum numbers, and compatible power counting, then a divergent insertion of one can require counterterms proportional to the others. The renormalized operator is therefore not usually one bare monomial with a hat on it. It is a chosen finite linear combination.

The schematic relation is

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R},
$$

where $a,b$ label a basis of operators in one sector. The matrix $Z_a{}^b$ contains the counterterms needed to make correlation functions with one insertion finite. Its logarithmic scale dependence gives the anomalous-dimension matrix.

<figure class="doc-figure" style="--figure-width: 50rem; --caption-width: 54rem;">

![A schematic map of operator mixing: exact quantum-number sectors select operator vectors, the renormalization matrix acts within each sector, and diagonalization at a fixed point gives scaling operators.](/figures/renormalization-rg-eft/operator-mixing-blocks.svg)

<figcaption>

Operator mixing is block structured. Exact labels such as spin, charges, gauge or BRST class, parity, and translation quantum numbers split local operators into sectors. Within a sector, renormalization is a matrix problem. At a fixed point, diagonalizing the anomalous-dimension matrix gives scaling operators.

</figcaption>
</figure>

:::note[The slogan]
Renormalization does not ask, "Which monomial did you write first?" It asks, "Which vector space of local operators has the same quantum numbers?"
:::

## Prerequisites

You should know [Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/) and [Anomalous Dimensions of Operators](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimensions-of-operators/). You should also know why composite operators need extra renormalization, as previewed in [Composite Operator Renormalization Preview](/renormalization-rg-eft/regularization-counterterms/composite-operator-renormalization-preview/).

The next page, [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/), turns the conceptual statement of this page into the precise matrix notation used for operator renormalization.

## Core idea

A local operator insertion creates new short-distance singularities. For example, in a correlation function

$$
\langle \mathcal O_a(x)\phi(y_1)\phi(y_2)\rangle,
$$

the points $y_i$ can approach $x$, and fields inside $\mathcal O_a$ can also contract with each other at the same point. These singularities are local in $x$. Locality says that the counterterms needed to subtract them must also be local operators at $x$.

The crucial point is that the counterterm does not have to be proportional to the original operator. It only has to have the same exact labels. If $\mathcal O_a$ and $\mathcal O_b$ carry the same labels, then the renormalized insertion of $\mathcal O_a$ can require a subtraction proportional to $\mathcal O_b$.

Thus an operator is not renormalized in splendid isolation. A **sector** is renormalized:

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

This is the first conceptual upgrade from "an operator has an anomalous dimension" to "a vector space of operators has an anomalous-dimension matrix." Multiplicative renormalization is the special case where the matrix is diagonal, or where a one-dimensional sector has been chosen.

## Setup and conventions

This page uses the volume convention

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R},
$$

where repeated operator labels are summed. Bare operators carry the subscript $0$, and renormalized operators carry the subscript $R$. The inverse relation is

$$
\mathcal O_{a,R}=(Z^{-1})_a{}^b\mathcal O_{b,0}.
$$

The anomalous-dimension matrix associated with this choice is

$$
\gamma_a{}^b
=
(Z^{-1})_a{}^c
\bigg.
\mu\frac{dZ_c{}^b}{d\mu}
\bigg|_{\text{bare data fixed}}.
$$

Therefore

$$
\bigg.
\mu\frac{d}{d\mu}\mathcal O_{a,R}
\bigg|_{\text{bare}}
=
-\gamma_a{}^b\mathcal O_{b,R}.
$$

Later pages on Wilson coefficients will use the transpose equation for coefficients. If a deformation is written as

$$
\delta S=\int d^d x\,C^a(\mu)\mathcal O_{a,R},
$$

then the scale dependence of $C^a$ is the dual flow that keeps $\delta S$ independent of the arbitrary scale $\mu$.

Throughout this page, "same quantum numbers" includes all exact labels that the regulator and scheme respect. If a regulator breaks a symmetry, additional subtractions may appear and symmetry-restoring counterterms may be needed. A clean operator-mixing calculation therefore begins by choosing a regulator and scheme that preserve as much exact structure as possible.

## What can mix with what?

Operator mixing is constrained before any loop integral is evaluated. The constraints are often more important than the integrals.

| Constraint | Consequence |
|---|---|
| Lorentz or rotation representation | Scalars mix with scalars, vectors with vectors, symmetric traceless tensors with symmetric traceless tensors, and so on. |
| Internal global charges | Operators in different charge sectors cannot mix. |
| Gauge invariance or BRST cohomology | Physical gauge-invariant operators mix with operators in the same cohomological class, with gauge-variant, BRST-exact, and equation-of-motion subtleties depending on the problem. |
| Discrete symmetries | Parity, charge conjugation, time reversal, flavor exchange, and other exact labels split sectors. |
| Translation invariance | Total momentum is conserved; total derivatives form structured subsectors. |
| Engineering dimension and power counting | In mass-independent schemes, mixing is usually block diagonal by engineering dimension; with masses or cutoffs, lower-dimension counterterms can appear with powers of the mass or cutoff. |
| Equations of motion and field redefinitions | Operators can be equivalent for on-shell observables but distinct in off-shell correlators or contact terms. |
| Evanescent structures | In dimensional regularization, operators that vanish in integer dimension can still affect finite physical mixing. |

The table hides a subtle word: **exact**. A symmetry forbids mixing only if it is respected by the regulator, by the subtraction scheme, and by the operator definition. Classical symmetries broken by anomalies do not forbid quantum mixing. Accidental low-order symmetries do not necessarily survive at higher order.

## A simple mental model: mixing as linear algebra

Suppose $\mathcal O_1$ and $\mathcal O_2$ are two scalar operators with the same internal quantum numbers. Imagine computing their inserted Green functions in a regulated theory. The divergent parts have the schematic form

$$
\langle\mathcal O_1\rangle_{\text{div}}
=A_{11}\mathcal O_1+A_{12}\mathcal O_2,
\qquad
\langle\mathcal O_2\rangle_{\text{div}}
=A_{21}\mathcal O_1+A_{22}\mathcal O_2.
$$

The coefficients $A_{ab}$ are not observable by themselves. They are the divergent local pieces that tell us what counterterms must be introduced. The renormalized operators are finite combinations of the regulated ones:

$$
\begin{pmatrix}
\mathcal O_{1,R}\\
\mathcal O_{2,R}
\end{pmatrix}
=
\begin{pmatrix}
1 & 0\\
0 & 1
\end{pmatrix}
\begin{pmatrix}
\mathcal O_{1,0}\\
\mathcal O_{2,0}
\end{pmatrix}
+\text{subtractions}.
$$

Equivalently, one packages the subtractions into $Z$ and writes $\mathcal O_0=Z\mathcal O_R$.

This is just linear algebra, but it changes how one thinks. The phrase "the anomalous dimension of $\mathcal O_1$" is meaningful only if $\mathcal O_1$ is a multiplicatively renormalized operator or an eigenoperator of the mixing problem. Before diagonalization, the invariant object is the matrix acting on the sector.

## Symmetry sectors

A practical mixing calculation begins by listing operators in a sector. A sector is specified by labels such as

$$
(\text{spin},\text{internal representation},\text{charge conjugation},\text{parity},\text{dimension},\text{gauge/BRST class}).
$$

For example, in a scalar theory with $\phi\to-\phi$ symmetry, even scalar operators do not mix with odd scalar operators. In a theory with an internal $O(N)$ symmetry, singlet operators do not mix with vector or tensor operators. In a gauge theory, gauge-invariant scalar operators such as

$$
F_{\mu\nu}F^{\mu\nu}
$$

live in a different sector from gauge-variant monomials, though a full off-shell BRST treatment may include BRST-exact and equation-of-motion operators to make the subtraction problem close.

Conservation laws are also powerful. A conserved current $J^\mu$ may be protected from acquiring an anomalous dimension, but this statement depends on the exact symmetry and on the normalization of the charge. If a current is not exactly conserved, or if one studies a larger basis of currents with the same quantum numbers, mixing can reappear.

The stress tensor is similar. The properly normalized conserved stress tensor is protected because it generates translations. But operators with the same spin and dimension can still appear in improvement transformations, trace relations, or contact terms.

## Power counting and triangular structure

Power counting tells us which entries of the mixing matrix can occur. The cleanest statement occurs in a massless theory renormalized in a mass-independent scheme such as MS or $\overline{\text{MS}}$. Operators with different engineering dimensions usually do not mix through logarithmic UV poles, so the anomalous-dimension matrix is block diagonal by engineering dimension:

$$
\gamma=
\begin{pmatrix}
\gamma_{\Delta_1} & 0 & 0 & \cdots\\
0 & \gamma_{\Delta_2} & 0 & \cdots\\
0 & 0 & \gamma_{\Delta_3} & \cdots\\
\vdots & \vdots & \vdots & \ddots
\end{pmatrix}.
$$

This statement has caveats. Mass parameters can convert dimension differences into powers of $m$. Cutoff schemes can display power divergences. Lattice regularization can allow mixings that are absent in dimensional regularization if lattice symmetries are smaller than continuum symmetries. EFT expansions also organize operators by powers of a heavy scale, so the finite matching and the logarithmic running have to be kept conceptually distinct.

The safest general statement is:

$$
\text{symmetries decide the allowed sectors; power counting decides how large or suppressed the allowed mixings can be.}
$$

In many operator bases, the matrix is triangular after one orders operators by dimension or by the number of equations-of-motion factors. Triangularity is useful because the running of one block can be solved before another. But it is a property of a chosen basis and scheme, not a substitute for the full renormalization problem.

## Example: scalar even operators

Consider a real scalar theory with $\phi\to-\phi$. The scalar even operators begin as

$$
\mathbf 1,
\qquad
\phi^2,
\qquad
\partial_\mu\phi\,\partial^\mu\phi,
\qquad
\phi^4,
\qquad
\partial^2\phi^2,
\qquad
\phi^6,
\ldots
$$

The identity operator can appear in vacuum counterterms. The operator $\phi^2$ is the mass deformation. The operators $\partial_\mu\phi\,\partial^\mu\phi$ and $\phi^4$ are dimension-four scalar even operators in $d=4$. Total derivatives such as $\partial^2\phi^2$ matter for local operator identities and off-shell correlation functions, though their spacetime integrals can vanish under suitable boundary conditions.

A naive student might ask: "Which of these is the operator $\phi^4$ after renormalization?" The right answer is: choose a basis and define a renormalized operator by specifying subtractions. If one wants a scaling operator at a fixed point, one then diagonalizes the anomalous-dimension matrix in the appropriate sector.

At the Wilson–Fisher fixed point, for instance, the energy operator and the leading even scalar are not simply "whatever monomial looks like $\phi^2$" in an arbitrary microscopic realization. They are scaling operators in the continuum fixed-point theory. The microscopic lattice energy density flows to that scaling operator plus irrelevant corrections and identity pieces.

## Example: four-fermion operators

Four-fermion operators are a classic source of operator mixing. Schematically, in a theory with fermions one may write many operators with the same total quantum numbers:

$$
(\bar\psi\Gamma_A\psi)(\bar\psi\Gamma_B\psi),
$$

where $\Gamma_A,\Gamma_B$ are matrices in spinor, flavor, and color space. Fierz identities may relate some of these structures in exactly four dimensions, while dimensional regularization can introduce evanescent operators that vanish when $\epsilon\to0$ but affect finite mixing through products of poles and $O(\epsilon)$ terms.

The lesson is not that four-fermion mixing is uniquely treacherous. The lesson is that **basis choice is part of the calculation**. One must specify:

- the physical operator basis;
- the evanescent operator basis, if dimensional regularization is used;
- the subtraction scheme;
- the convention for Wilson coefficients;
- whether the calculation concerns off-shell Green functions, on-shell amplitudes, or matrix elements in a particular external state.

Weak effective Hamiltonians, flavor physics, DGLAP evolution, and SMEFT running are all large-scale examples of this same linear algebra.

## Example: currents and protected operators

Some operators do not renormalize in the same way as generic composites because they are tied to exact symmetries. If $J^\mu$ is the exactly conserved current for a global symmetry, then the charge

$$
Q=\int d^{d-1}\mathbf x\,J^0
$$

must generate the symmetry on the Hilbert space. This fixes the normalization of the current, up to improvement terms and convention choices. In many common schemes this implies no anomalous dimension for the conserved current.

But the protected statement belongs to the conserved current, not to every vector operator that looks similar. Operators with the same spin and charges can mix before one identifies the conserved combination. If the symmetry is explicitly broken, anomalous, or only approximate, the protection disappears or changes form.

This is why operator mixing and Ward identities should be studied together. Ward identities do not merely simplify diagrams. They identify protected directions inside operator space.

## Equation-of-motion and total-derivative operators

Operator bases often contain operators that vanish by classical equations of motion or differ by total derivatives. Examples include structures of the form

$$
\mathcal O_{\text{EOM}}=F(\phi)\frac{\delta S}{\delta\phi}
$$

and

$$
\mathcal O_{\text{td}}=\partial_\mu V^\mu.
$$

For on-shell S-matrix elements, such operators may be removable by field redefinitions or vanish after integration by parts. In local correlation functions, however, they can produce contact terms. In renormalization calculations, they may be required for closure of the operator basis.

A careful basis distinction is therefore:

| Kind of operator | Typical role |
|---|---|
| Physical or cohomologically nontrivial operators | Affect separated gauge-invariant correlators or on-shell observables. |
| Equation-of-motion operators | Often removable from on-shell bases but important for off-shell closure and contact terms. |
| Total derivatives | Often vanish after spacetime integration but contribute to momentum-dependent insertions and descendants. |
| BRST-exact operators | Do not represent physical gauge-invariant observables but may appear in gauge-fixed renormalization. |
| Evanescent operators | Vanish in the target integer dimension but can affect finite scheme conversion. |

Good notation does not pretend all of these are the same. Good physics does not pretend they are always independent.

## Mixing and the OPE

The operator product expansion says that nearby products of operators can be expanded in local operators:

$$
\mathcal O_a(x)\mathcal O_b(0)
\sim
\sum_c C_{ab}{}^c(x,\mu)\mathcal O_{c,R}(0).
$$

Operator mixing affects both sides of this equation. The operator basis on the right is scheme dependent away from fixed points. The coefficients $C_{ab}{}^c$ transform oppositely so that the product as a whole is unchanged. At a fixed point, one often chooses a scaling basis, where operators have definite dimensions and the OPE takes its cleanest form.

This is why the OPE is not merely a fancy Taylor expansion. The local operators appearing in it are renormalized composite operators. Their normalization, mixing, anomalous dimensions, and scheme dependence must be under control before the coefficients can be interpreted.

In CFT language, the data are usually packaged into scaling dimensions and OPE coefficients. In EFT language, the same issue appears as operator bases and Wilson coefficients. In both languages, mixing is the warning label on the sentence "choose a basis."

## How to organize a mixing calculation

A practical operator-mixing calculation usually follows this workflow.

1. **State the observable or deformation.** Are you computing inserted Green functions, matrix elements, an EFT anomalous-dimension matrix, or fixed-point scaling operators?
2. **Choose a regulator and scheme.** Dimensional regularization with MS, a hard cutoff, a lattice regulator, and a momentum-subtraction scheme expose different finite and power-sensitive details.
3. **List all operators in the sector.** Include all operators allowed by exact symmetries and power counting at the required order.
4. **Remove or classify redundancies.** Decide how to treat total derivatives, equations of motion, BRST-exact terms, Bianchi identities, integration by parts, and Fierz identities.
5. **Compute divergent inserted correlators.** Use enough external states or sources to distinguish all operators in the basis.
6. **Extract the $Z$ matrix.** Choose counterterms that make the renormalized operator insertions finite.
7. **Compute the anomalous-dimension matrix.** Use the $\mu$ dependence of $Z$ at fixed bare data.
8. **Transform Wilson coefficients if needed.** Coefficients run with the transpose dual matrix.
9. **Diagonalize only when useful.** At fixed points, diagonalization gives scaling operators. Away from fixed points, a convenient non-diagonal basis may be better.

The workflow is not glamorous. It is how one prevents basis mistakes from masquerading as physics.

## Common pitfalls

**Thinking an operator name uniquely defines an operator.** The phrase $\phi^4$ names a bare monomial, a normal-ordered operator, an MS-renormalized operator, a lattice operator, or a scaling operator only after a definition is supplied.

**Forgetting operators that vanish by equations of motion.** EOM operators can be removed from some on-shell bases, but they are often needed for off-shell renormalization and contact terms.

**Using four-dimensional identities too early.** In dimensional regularization, identities involving gamma matrices, Levi-Civita tensors, Fierz rearrangements, and chirality may require evanescent operators.

**Assuming different dimensions never mix.** In mass-independent schemes this is often true for logarithmic anomalous dimensions. With masses, cutoffs, lattice regulators, or power-divergent subtractions, dimension-separated mixing can matter.

**Calling a matrix entry physical.** The entries of $Z$ and $\gamma$ depend on the basis and scheme. Eigenvalues at fixed points, critical exponents, properly transformed Wilson-coefficient evolution, and physical matrix elements are the invariant objects.

**Ignoring symmetry restoration.** A regulator that breaks a symmetry can generate mixings that the target theory should not have. One must add counterterms or choose a better regulator.

**Diagonalizing too soon.** The basis that diagonalizes one-loop mixing may not be the most useful basis for matching, symmetry, higher loops, or physical matrix elements.

## Relations to other pages

[Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/) gives the classical power count that limits possible mixing. [Anomalous Dimensions of Operators](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimensions-of-operators/) explains why dimensions become quantum data. This page explains why that data is usually matrix-valued.

The next page, [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/), fixes the precise notation for $Z_a{}^b$. [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/) will derive the RG equations for operators and Wilson coefficients.

For EFT, operator mixing becomes the running of Wilson coefficients. For CFT, it becomes the diagonalization problem that produces scaling operators. For gauge theory, it is tied to Ward identities, BRST cohomology, and anomaly constraints. For lattice QFT, it is central to matching lattice operators to continuum schemes.

## Research status

The conceptual framework of operator mixing is established. What remains difficult is not the idea but the execution: choosing complete nonredundant bases, preserving symmetries, handling evanescent operators, computing high-loop matrices, matching across schemes, and extracting nonperturbative operator data.

In modern research, operator mixing appears in many forms: SMEFT anomalous dimensions, weak effective Hamiltonians, twist-two operators and parton evolution, lattice-to-continuum matching, critical exponents in statistical systems, conformal perturbation theory, bootstrap studies of operator spectra, and operator algebras in gauge theories with generalized symmetries.

The recurring lesson is that local operators are not merely decorations of a Lagrangian. They are the coordinates in which short-distance physics, RG flow, and observables are related.

## Exercises

### Exercise 1: Symmetry sectors in a scalar theory

Consider a real scalar theory in $d=4$ with $\phi\to-\phi$. Classify the following scalar operators as even or odd and list which can mix with which by the $\mathbb Z_2$ symmetry alone:

$$
\phi,
\quad
\phi^2,
\quad
\phi^3,
\quad
\phi^4,
\quad
\partial_\mu\phi\,\partial^\mu\phi,
\quad
\phi\partial^2\phi.
$$

<details><summary><strong>Solution</strong></summary>

Under $\phi\to-\phi$, operators with an odd number of $\phi$ fields are odd, while operators with an even number are even. Derivatives do not change the $\mathbb Z_2$ parity.

Thus

$$
\phi,
\quad
\phi^3
$$

are odd, while

$$
\phi^2,
\quad
\phi^4,
\quad
\partial_\mu\phi\partial^\mu\phi,
\quad
\phi\partial^2\phi
$$

are even. The $\mathbb Z_2$ symmetry forbids odd-even mixing. It does not by itself decide which even operators mix with each other; spin, dimension counting, total derivatives, equations of motion, and the chosen scheme must also be considered.

</details>

### Exercise 2: Why multiplicative renormalization is special

Suppose a sector contains two operators $\mathcal O_1$ and $\mathcal O_2$ with the same exact quantum numbers. Explain why writing

$$
\mathcal O_{1,0}=Z_1\mathcal O_{1,R}
$$

without including $\mathcal O_{2,R}$ is a nontrivial assumption.

<details><summary><strong>Solution</strong></summary>

If $\mathcal O_1$ and $\mathcal O_2$ have the same exact quantum numbers, then locality and symmetry allow a divergent insertion of $\mathcal O_1$ to generate a counterterm proportional to $\mathcal O_2$. The most general renormalization relation in the two-dimensional sector is

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

Writing only $\mathcal O_{1,0}=Z_1\mathcal O_{1,R}$ assumes either that the off-diagonal entries vanish in the chosen basis and scheme, or that $\mathcal O_1$ has already been chosen as an eigenoperator. That is additional information, not automatic notation.

</details>

### Exercise 3: Coefficients run oppositely

Let $\mathcal O_0=Z\mathcal O_R$ be a column-vector relation and let a deformation be written as

$$
\delta S=C_R^T\mathcal O_R.
$$

If $\mu d\mathcal O_R/d\mu=-\gamma\mathcal O_R$, show that $\mu dC_R/d\mu=\gamma^T C_R$ makes $\delta S$ independent of $\mu$.

<details><summary><strong>Solution</strong></summary>

Differentiate

$$
\delta S=C_R^T\mathcal O_R
$$

with respect to $\log\mu$:

$$
\frac{d}{d\log\mu}\delta S
=
\left(\frac{dC_R}{d\log\mu}\right)^T\mathcal O_R
+C_R^T\frac{d\mathcal O_R}{d\log\mu}.
$$

Using

$$
\frac{d\mathcal O_R}{d\log\mu}=-\gamma\mathcal O_R,
$$

we get

$$
\frac{d}{d\log\mu}\delta S
=
\left(\frac{dC_R}{d\log\mu}\right)^T\mathcal O_R
-C_R^T\gamma\mathcal O_R.
$$

This vanishes for arbitrary $\mathcal O_R$ if

$$
\frac{dC_R}{d\log\mu}=\gamma^T C_R.
$$

The transpose appears because operators form a vector space while coefficients live in the dual space.

</details>

## References

- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," for anomalous dimensions, Callan–Symanzik equations, and OPE logic.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for composite operators, short-distance expansions, and critical exponents.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the renormalization group and renormalized-operator discussions.
- John Collins, *Renormalization*, for systematic composite-operator renormalization, mixing, and scheme dependence.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, for renormalized perturbation theory, RG equations, and operator running in practical examples.
- A. J. Buras, "Weak Hamiltonian, CP violation and rare decays," for a classic phenomenological view of operator mixing in weak effective Hamiltonians.

## Version history

- 2026-06-17: First polished draft. Added the sector viewpoint, symmetry constraints, power-counting caveats, examples, workflow, exercises, and the operator-mixing block figure.
