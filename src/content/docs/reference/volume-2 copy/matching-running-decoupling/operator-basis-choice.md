---
title: "Operator Basis Choice"
description: "How EFT operator bases are chosen, transformed, and used without mistaking basis-dependent Wilson coefficients for physical observables."
sidebar:
  label: "Operator Basis Choice"
  order: 9
level: Graduate
status: "Polished draft"
source: "Burgess 2020, chs. 2–4; Weinberg Vol. II, renormalization group methods; Schwartz 2014, chs. 22–23 and 31–36; Manohar EFT lectures; Grzadkowski et al. 2010; Jenkins, Manohar, and Trott SMEFT anomalous-dimension papers."
topics:
  - operator bases
  - Wilson coefficients
  - redundant operators
  - field redefinitions
  - evanescent operators
  - EFT matching
canonicalTopics:
  - operator-basis-choice
  - redundant-operators
  - wilson-coefficient-basis-dependence
researchStatus:
  established:
    - "Physical predictions are invariant under complete and consistent changes of operator basis, while Wilson coefficients and anomalous-dimension matrices are basis dependent."
  active:
    - "Automated basis construction, evanescent-operator schemes, high-order anomalous dimensions, and cross-basis translation for large EFTs such as SMEFT remain active technical areas."
---

## Summary

An **operator basis** is a choice of coordinates for the local terms in an effective Lagrangian. It is not part of the physical content by itself.

At a fixed order in an EFT expansion, one first writes all local operators allowed by the light fields and symmetries. Then one removes redundancies: total derivatives, integration-by-parts identities, equations-of-motion operators, algebraic identities, Fierz identities, Bianchi identities, and sometimes dimension-specific identities. What remains is a finite-dimensional vector space of physical operator classes. A basis is a choice of representatives for that vector space.

The EFT Lagrangian is written schematically as

$$
\mathcal L_{\text{EFT}}
=
\mathcal L_{\text{leading}}
+
\sum_i C_i(\mu)\mathcal O_i(\mu).
$$

The basis-dependent pieces are $C_i$ and $\mathcal O_i$ separately. The physical object is the product of coefficients and matrix elements:

$$
\mathcal A
=
\sum_i C_i(\mu)\langle f|\mathcal O_i(\mu)|i\rangle.
$$

Changing the basis changes the coordinates. It should not change the amplitude, decay rate, cross section, correlation function, or low-energy theorem. If it does, something has been lost: a redundant operator was used incorrectly, an evanescent convention was mismatched, a matrix element was not transformed, or the calculation was truncated inconsistently.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Operator basis choice as a quotient by redundancies, followed by dual transformations of operators and Wilson coefficients that leave observables invariant](/figures/renormalization-rg-eft/operator-basis-choice-map.svg)

<figcaption>

An operator basis is a coordinate choice on the quotient of local operators by redundancies. Operators and Wilson coefficients transform dually, so $C_i\mathcal O_i$ and physical observables are unchanged when the basis is changed consistently.

</figcaption>
</figure>

## Prerequisites

You should know [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/), [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/), [Redundant Operators](/renormalization-rg-eft/local-operators-and-ope/redundant-operators/), and [Equations-of-Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/).

For the EFT workflow, review [Matching](/renormalization-rg-eft/effective-field-theory/matching/), [Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/), [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/), [Matching S-Matrix Elements](/renormalization-rg-eft/matching-running-decoupling/matching-s-matrix-elements/), and [Renormalization Group Evolution](/renormalization-rg-eft/matching-running-decoupling/renormalization-group-evolution/).

## Core idea

The local terms in an EFT are like vectors. A basis is a coordinate system. Wilson coefficients are the dual coordinates.

Suppose two operator bases are related by

$$
\mathcal O'_a=R_a{}^i\mathcal O_i,
$$

where $R$ is an invertible matrix inside the chosen finite operator space. If the Lagrangian is written as

$$
\mathcal L_{\text{EFT}}\supset C_i\mathcal O_i
=C'_a\mathcal O'_a,
$$

then the coefficients must transform inversely:

$$
C'_a=C_i(R^{-1})^i{}_a.
$$

Equivalently, with column vectors of operators and row vectors of coefficients,

$$
\mathcal O'=R\mathcal O,
\qquad
C'=CR^{-1}.
$$

This is the whole moral of the page in one line:

$$
C\mathcal O=C'\mathcal O'.
$$

The subtlety is that EFT bases are not usually obtained by a simple finite rotation among obvious monomials. One first has to decide which monomials represent the same operator class.

## Setup and conventions

This page uses the conventions of [Conventions and Notation](/renormalization-rg-eft/conventions/). Operators are local, renormalized composite operators built from light fields. Wilson coefficients are renormalized coefficients. Unless stated otherwise, the EFT is organized as

$$
\mathcal L_{\text{EFT}}
=\mathcal L_{\le d}
+
\sum_{\Delta>d}\frac{C_i(\mu)}{M^{\Delta_i-d}}\mathcal O_i(\mu),
$$

where $M$ is the heavy scale or EFT breakdown scale. The coefficients $C_i$ are dimensionless in this convention.

A relation between operators is called **redundant** if it changes the Lagrangian by something that does not change the chosen class of physical observables at the order being computed. Common examples are:

| Redundancy | Schematic form | Meaning |
|---|---|---|
| Total derivative | $\partial_\mu J^\mu$ | drops from the action without boundary contributions |
| Integration by parts | $A\partial_\mu B\sim -B\partial_\mu A$ | redistributes derivatives among fields |
| Equation of motion | $F_a(\phi)E_a(\phi)$ | removed by a local field redefinition |
| Algebraic identity | tensor, spinor, group identity | two written monomials are not independent |
| Fierz identity | four-fermion rearrangement | different spinor contractions span the same space |
| Bianchi identity | $D_{[\mu}F_{\nu\rho]}=0$ | gauge-field derivatives are constrained |
| Dimension-specific identity | Schouten or four-dimensional gamma identity | valid only in a specified dimension |

The symbol $\sim$ in basis discussions means "equal in the chosen quotient space," not equal as pointwise functions.

## From generating list to basis

A practical basis construction has four layers.

First, choose the **fields and symmetries**. The allowed monomials depend on the light degrees of freedom, gauge group, global symmetries, spacetime symmetries, baryon or lepton number assignments, flavor assumptions, and whether discrete symmetries such as $C$, $P$, $T$, or CP are imposed.

Second, choose the **power counting**. In a relativistic EFT, one often groups operators by mass dimension. In chiral perturbation theory, one groups by derivatives, quark masses, and loops. In heavy-particle EFTs, one may count residual momenta and powers of $1/M$. "Dimension six" is not a universal synonym for "next-to-leading order."

Third, generate a large list of allowed local monomials:

$$
\{Q_A\}_{\text{allowed}}.
$$

This list is intentionally redundant. It is safer to generate too much and quotient carefully than to silently miss an allowed structure.

Fourth, quotient by relations:

$$
\text{operator space}
=
\frac{\text{allowed local monomials}}
{\text{IBP, EOM, algebraic identities, symmetry identities}}.
$$

A basis is then a set of representatives

$$
\{\mathcal O_i\}
$$

for this quotient.

:::note[The basis is not the monomial list]
The raw monomial list is usually not a basis. It is a generating set. The basis appears only after redundancies are removed.
:::

## Total derivatives and integration by parts

Total derivatives normally do not affect local scattering observables in flat spacetime without boundary contributions:

$$
\int d^d x\,\partial_\mu J^\mu=0.
$$

Therefore operators differing by a total derivative represent the same bulk interaction. For example,

$$
\partial_\mu(A B)=
(\partial_\mu A)B+A(\partial_\mu B)
$$

implies

$$
(\partial_\mu A)B\sim -A(\partial_\mu B).
$$

This simple identity is the source of many nontrivial basis reductions. It lets one move derivatives from one field to another, eliminate terms with derivatives on products, and choose canonical derivative placements.

There are caveats. Boundary terms matter when boundaries, defects, asymptotic charges, topological terms, or finite-volume subtleties are part of the problem. A total derivative in a bulk EFT may also encode a nontrivial topological theta term. Basis reduction is never allowed to erase boundary or topological data that the problem is actually asking about.

## Equations of motion and field redefinitions

Let $S_0[\phi]$ be the leading action and define the leading equation-of-motion functional

$$
E_a(x)\equiv \frac{\delta S_0}{\delta\phi^a(x)}.
$$

An operator of the form

$$
\Delta\mathcal L=F^a(\phi,\partial\phi,\ldots)E_a
$$

is redundant in ordinary on-shell EFT observables because it can be removed by a local field redefinition,

$$
\phi^a\longrightarrow \phi^a-F^a.
$$

To first order in $F$,

$$
S_0[\phi-F]
=S_0[\phi]-\int d^d x\,F^aE_a+O(F^2).
$$

Thus adding $F^aE_a$ can be undone by shifting the field. At higher orders, the field redefinition generates compensating changes in other operators. This is why basis changes must be done order by order in the EFT expansion.

The phrase "use the equations of motion" is therefore slightly dangerous. One is not setting an operator to zero inside every correlator. One is using a field redefinition to choose a convenient coordinate system for on-shell or properly matched observables.

## Off-shell and on-shell bases

The allowed redundancies depend on the observable class.

For **on-shell S-matrix matching**, EOM operators do not affect the physical amplitude after external-leg reduction, so one often removes them aggressively. This is efficient for amplitudes and phenomenology.

For **off-shell Green-function matching**, EOM operators and contact terms can appear explicitly. One may still remove them by field redefinitions, but then sources and composite operators also transform. If those transformations are ignored, off-shell correlators appear to disagree even though the physics is unchanged.

For **background-field matching**, the natural basis is often gauge-covariant. It may include structures that are convenient at the level of the effective action before they are reduced to a minimal on-shell basis.

For **lattice or nonperturbative matching**, the basis must be compatible with the regulator symmetries. A continuum identity that relies on exact Lorentz symmetry, chirality, or dimension-specific gamma algebra may not hold in the same form at finite lattice spacing.

The safe statement is:

$$
\text{basis choice depends on the question, but physical predictions do not.}
$$

## Coefficients, matrix elements, and invariant predictions

Suppose an observable is computed as

$$
\mathcal A=C_i\langle\mathcal O_i\rangle.
$$

Under a basis change $\mathcal O'=R\mathcal O$, the matrix elements transform as

$$
\langle\mathcal O'_a\rangle=R_a{}^i\langle\mathcal O_i\rangle,
$$

and the coefficients transform as

$$
C'=CR^{-1}.
$$

Therefore

$$
C'\langle\mathcal O'\rangle
=CR^{-1}R\langle\mathcal O\rangle
=C\langle\mathcal O\rangle.
$$

This is why a table of Wilson coefficients is not meaningful unless it states the basis, normalization, scheme, scale, flavor convention, and evanescent convention when relevant.

For large EFTs, especially SMEFT-like theories, a coefficient name is not a physical observable. It is a coordinate label. Asking whether "the coefficient of an operator" is large or small only makes sense after the basis has been specified.

## Anomalous dimensions under a basis change

Operator bases also affect anomalous-dimension matrices. Suppose operators obey

$$
\mu\frac{d}{d\mu}\mathcal O_i
=-\gamma_i{}^j\mathcal O_j.
$$

For a scale-independent basis transformation $\mathcal O'=R\mathcal O$,

$$
\gamma'=R\gamma R^{-1}.
$$

If the transformation itself depends on $\mu$, then

$$
\gamma'=R\gamma R^{-1}
-\mu\frac{dR}{d\mu}R^{-1}.
$$

The coefficient evolution transforms dually. This is the RG version of the same statement: changing basis changes matrices, not physics.

A common practical consequence is that anomalous-dimension entries cannot be compared between papers unless the operator normalization and basis conventions agree. A zero in one basis may become a nonzero entry in another basis, while eigenvalues and observable evolution remain consistent when all pieces are transformed.

## Evanescent operators

Dimensional regularization introduces a special complication. Some operators vanish algebraically in exactly four dimensions but are nonzero in $d=4-2\epsilon$. These are **evanescent operators**.

A schematic example is

$$
E_a\to 0\quad\text{as }d\to4,
$$

but loop diagrams can contain terms of the form

$$
\frac{1}{\epsilon}E_a.
$$

When multiplied by $O(\epsilon)$ differences between $d$-dimensional and four-dimensional identities, such terms can leave finite contributions to physical four-dimensional operators. This means evanescent operators are not optional bookkeeping in multi-loop matching and running. They are part of the scheme.

The correct workflow is not to pretend evanescent operators are physical. It is to state the evanescent convention and use it consistently through matching, renormalization, and basis conversion.

:::tip[Evanescent operators are scheme data]
If two calculations disagree by finite terms, check the evanescent-operator convention before declaring a physics disagreement. The goblin may be hiding in $d$-dimensional gamma algebra.
:::

## Basis choice in matching

Matching determines short-distance coefficients by comparing the full theory and EFT. The chosen basis determines where the answer lands.

A typical matching equation is

$$
\mathcal A_{\text{full}}(Q\ll M)
=
\sum_i C_i(\mu)\mathcal A_i^{\text{EFT}}(Q,\mu)
+O\left(\frac{Q^{N+1}}{M^{N+1}}\right).
$$

If a redundant operator is kept, the matching may produce a coefficient for it. One can either keep the redundant basis and later show that observables are invariant, or remove the operator immediately by a field redefinition and shift the coefficients of other operators.

Both are valid. The bad options are:

- keeping redundant coefficients and interpreting them as observables;
- removing redundant operators from the Lagrangian but forgetting the induced shifts in other coefficients;
- matching in one basis and running in another without applying the conversion matrix;
- comparing matrix elements computed in a different operator normalization.

## Choosing a good basis

A good basis is not simply the shortest list. A good basis is useful for the calculation and transparent about its assumptions.

Common criteria include:

| Criterion | Why it matters |
|---|---|
| Symmetry manifestness | Ward identities and selection rules are easier to check. |
| Minimality | No coefficient multiplies an operator already represented by others. |
| Power-counting clarity | Truncation errors are easier to state. |
| Flavor transparency | Phenomenological assumptions are visible. |
| RG convenience | Anomalous-dimension blocks may simplify. |
| Matching convenience | Heavy-field effects may land in simple coefficients. |
| Observable convenience | Matrix elements may be easier to compute. |
| Literature compatibility | Results can be compared with standard bases. |

These criteria can conflict. A basis that is excellent for matching may be awkward for low-energy matrix elements. A basis that makes gauge symmetry manifest may not be minimal for on-shell amplitudes. A basis that diagonalizes a one-loop anomalous-dimension matrix may obscure flavor structure. There is no royal road; there are only documented choices.

## A minimal scalar example

Consider an EFT for one real scalar field, and suppose the leading action is $S_0[\phi]$. At some order in $1/M$, imagine the Lagrangian contains

$$
\Delta\mathcal L
=\frac{a}{M^2}F(\phi)\frac{\delta S_0}{\delta\phi}.
$$

This term is proportional to the leading equation of motion. The field redefinition

$$
\phi\longrightarrow \phi-\frac{a}{M^2}F(\phi)
$$

removes it from the action to this order, while shifting other higher-order terms. Therefore $a$ is not an invariant coefficient. A basis that includes this operator and a basis that removes it can give the same S-matrix.

If one instead computes off-shell correlators of the field $\phi$, the correlators change under the field redefinition because the interpolating field has changed. That is not a paradox. Fields are coordinates on configuration space; the S-matrix and properly defined observables are invariant.

## A practical checklist

When presenting an EFT result, state:

1. the light fields and symmetry assumptions;
2. the power-counting order;
3. the operator basis and normalization;
4. which redundancies were removed and how;
5. the renormalization scheme and scale;
6. the evanescent-operator convention if dimensional regularization is used beyond leading order;
7. the basis for anomalous-dimension matrices;
8. the relation to any standard basis used for comparison;
9. whether the matched objects are on-shell amplitudes, off-shell correlators, background-field effective actions, or nonperturbative matrix elements.

The shortest way to lose trust in an EFT table is to omit item 3. The second shortest is to omit item 6 in a calculation where it matters.

## Common pitfalls

**Confusing a coefficient with an observable.** A Wilson coefficient is basis, scheme, and scale dependent. It becomes physically meaningful only inside a complete prediction.

**Using EOM reduction inside contact terms without care.** EOM operators can change local contact terms and source couplings. This matters for off-shell matching and composite-operator correlators.

**Comparing anomalous-dimension matrices entry by entry across bases.** Matrix entries are coordinate dependent. Compare transformed matrices, eigen-data under stated assumptions, or physical evolution.

**Forgetting induced shifts from field redefinitions.** Removing one operator usually shifts others at the same or higher order.

**Dropping evanescent operators too early.** Operators that vanish in four dimensions can influence finite pieces through $1/\epsilon$ poles in dimensional regularization.

**Using a beautiful minimal basis that nobody can match to.** A basis should serve its users. Sometimes a redundant-looking intermediate basis is better for calculation, provided the final translation is documented.

## Relations to other pages

[Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/) explains why renormalization generally couples operators in the same symmetry sector. [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/) and [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/) explain the $Z$ and $\gamma$ matrices that depend on basis choices.

[Field Redefinitions](/renormalization-rg-eft/effective-field-theory/field-redefinitions/) and [Redundant Operators](/renormalization-rg-eft/effective-field-theory/redundant-operators/) explain the physical reason EOM operators can be removed. [Matching S-Matrix Elements](/renormalization-rg-eft/matching-running-decoupling/matching-s-matrix-elements/) explains the on-shell version of this logic, while [Matching Correlation Functions](/renormalization-rg-eft/matching-running-decoupling/matching-correlation-functions/) explains why off-shell matching needs extra bookkeeping.

The next chapter, [Naturalness and Power Counting](/renormalization-rg-eft/naturalness-power-counting/), uses operator bases to discuss which terms are expected to appear with which sizes.

## Research status

The conceptual status is settled: basis choices are coordinate choices, and physical predictions are invariant under consistent transformations.

The technical frontier is still busy. Modern EFTs can contain thousands of operators once flavor, baryon number, CP, derivatives, and high mass dimension are included. Automated Hilbert-series methods, amplitude-basis methods, on-shell bases, evanescent-operator handling, multi-loop anomalous dimensions, lattice-to-continuum matching, and cross-basis translation tables are active parts of current EFT infrastructure.

For large EFTs, the physics is not usually hard because "basis choice" is mysterious. It is hard because the bookkeeping is enormous and every convention has to be made explicit.

## Exercises

### Exercise 1: Dual transformation of coefficients

Let $\mathcal O'_a=R_a{}^i\mathcal O_i$, where $R$ is invertible. Derive the transformation law for the coefficients if

$$
C_i\mathcal O_i=C'_a\mathcal O'_a.
$$

<details><summary><strong>Solution</strong></summary>

In column-vector notation, $\mathcal O'=R\mathcal O$, so $\mathcal O=R^{-1}\mathcal O'$. The Lagrangian term is

$$
C\mathcal O=C R^{-1}\mathcal O'.
$$

Therefore

$$
C'=C R^{-1}.
$$

In indices,

$$
C'_a=C_i(R^{-1})^i{}_a.
$$

The coefficients transform in the dual representation so that the scalar $C_i\mathcal O_i$ is invariant.

</details>

### Exercise 2: Removing an EOM operator

Let $S_0[\phi]$ be a leading action and let

$$
\Delta S=\frac{1}{M^2}\int d^d x\,F(\phi)\frac{\delta S_0}{\delta\phi}.
$$

Show that $\Delta S$ can be removed to order $1/M^2$ by a field redefinition.

<details><summary><strong>Solution</strong></summary>

Use the local field redefinition

$$
\phi\longrightarrow \phi-\frac{1}{M^2}F(\phi).
$$

Expanding $S_0$ to first order in $1/M^2$ gives

$$
S_0\left[\phi-\frac{1}{M^2}F\right]
=
S_0[\phi]
-
\frac{1}{M^2}\int d^d x\,F(\phi)\frac{\delta S_0}{\delta\phi}
+O(M^{-4}).
$$

This cancels $\Delta S$ to the order being considered. At order $M^{-4}$ and beyond, the same field redefinition generates additional terms that must be included if the EFT is pushed to that order.

</details>

### Exercise 3: Transforming an anomalous-dimension matrix

Suppose

$$
\mu\frac{d}{d\mu}\mathcal O=-\gamma\mathcal O,
\qquad
\mathcal O'=R\mathcal O,
$$

where $R$ is independent of $\mu$. Show that $\gamma'=R\gamma R^{-1}$.

<details><summary><strong>Solution</strong></summary>

Differentiate $\mathcal O'=R\mathcal O$:

$$
\mu\frac{d}{d\mu}\mathcal O'
=R\mu\frac{d}{d\mu}\mathcal O
=-R\gamma\mathcal O.
$$

Since $\mathcal O=R^{-1}\mathcal O'$, this becomes

$$
\mu\frac{d}{d\mu}\mathcal O'
=-R\gamma R^{-1}\mathcal O'.
$$

Comparing with $\mu d\mathcal O'/d\mu=-\gamma'\mathcal O'$ gives

$$
\gamma'=R\gamma R^{-1}.
$$

</details>

## References

- C. P. Burgess, *Introduction to Effective Field Theory*, for redundant interactions, field redefinitions, power counting, and matching logic.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the renormalization group and nonrenormalizable-interaction discussions.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapters on nonrenormalizable theories, the renormalization group, HQET, and SCET.
- Aneesh Manohar, EFT lectures and reviews, for practical operator-basis, matching, and anomalous-dimension methods.
- B. Grzadkowski, M. Iskrzynski, M. Misiak, and J. Rosiek, "Dimension-Six Terms in the Standard Model Lagrangian," for the Warsaw-basis organization of SMEFT dimension-six operators.
- E. E. Jenkins, A. V. Manohar, and M. Trott, SMEFT anomalous-dimension papers, for large-scale operator mixing and basis-aware RG evolution.
- H. Georgi, classic EFT lectures, for the physical interpretation of basis choice, power counting, and low-energy operator expansions.

## Version history

- 2026-06-18: First polished draft. Added quotient-space view of operator bases, field-redefinition logic, basis transformations, anomalous-dimension transformations, evanescent-operator caveats, practical checklist, and exercises.
