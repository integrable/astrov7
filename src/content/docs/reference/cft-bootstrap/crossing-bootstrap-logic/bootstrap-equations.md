---
title: "Bootstrap Equations"
description: "How crossing symmetry, conformal blocks, unitarity, and assumptions become equations and positivity problems for CFT data."
sidebar:
  label: "Bootstrap Equations"
  order: 2
level: Graduate
status: "Polished draft"
source: "Rattazzi–Rychkov–Tonni–Vichi 2008; Rychkov 2016; Simmons-Duffin 2017; Poland–Rychkov–Vichi 2019; Rychkov–Su 2024"
topics:
  - bootstrap equations
  - crossing vectors
  - linear functionals
  - positivity
  - conformal data
canonicalTopics:
  - bootstrap-equations
  - crossing-vectors
  - numerical-bootstrap-logic
  - positivity-and-unitarity
researchStatus:
  established:
    - "Four-point crossing equations can be written as sums of conformal-block vectors weighted by OPE data."
    - "In unitary identical-correlator problems, squared OPE coefficients are nonnegative, allowing exclusion arguments by positive linear functionals."
  active:
    - "Optimal choices of correlators, assumptions, truncations, rigorous certificates, and spectrum extraction methods remain active parts of the numerical bootstrap program."
---

## Summary

Bootstrap equations are crossing symmetry written as equations for CFT data. The input is the list of possible primary operators, their dimensions and spins, their global-symmetry representations, and their OPE coefficients. The output is not usually a closed-form solution. It is a system of consistency constraints.

For the four-point function of an identical scalar primary $\phi$, the basic equation is

$$
F_{\mathbf 1}(U,V)
+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2
F_{\Delta,\ell}(U,V)=0,
\qquad
\lambda_{\phi\phi\mathcal O}^2\ge0
$$

in a unitary CFT. Here

$$
F_{\Delta,\ell}(U,V)
=
V^{\Delta_\phi}G_{\Delta,
\ell}(U,V)
-
U^{\Delta_\phi}G_{\Delta,
\ell}(V,U).
$$

The bootstrap question is whether the fixed identity vector $F_{\mathbf 1}$ can be cancelled by a positive sum of allowed non-identity crossing vectors. If not, the assumed spectrum is impossible.

## Prerequisites

You should know [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/), [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/), [Casimir Equation](/cft-bootstrap/conformal-blocks/casimir-equation/), [OPE Coefficients](/cft-bootstrap/operator-product-expansion/ope-coefficients/), and [Unitarity and Reflection Positivity](/cft-bootstrap/what-is-a-cft/unitarity-and-reflection-positivity/).

This page explains the conceptual form of the equations. It does not yet teach semidefinite programming, SDPB input generation, derivative-basis engineering, or numerical precision control. Those belong in [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/).

## Core idea

A bootstrap equation has three layers.

| Layer | Data | Meaning |
|---|---|---|
| Kinematics | Conformal blocks and tensor structures | Fixed by conformal symmetry. |
| Dynamics | Dimensions, spins, representations, OPE coefficients | The CFT data to be solved or constrained. |
| Consistency | Crossing, unitarity, symmetry, gaps | The rules the data must obey. |

For identical scalars, the equation is a positive-sum problem:

$$
-F_{\mathbf 1}
\in
\operatorname{Cone}\{F_{\Delta,\ell}\text{ allowed by assumptions}\}.
$$

Here the cone is made of all finite positive linear combinations of allowed crossing vectors, with closure understood in the appropriate function space.

<figure class="doc-figure" style="--figure-width: 42rem;">

![Bootstrap equation as a vector cone](/figures/cft-bootstrap/bootstrap-vector-cone.svg)

<figcaption>

For identical scalar crossing, the non-identity operators generate a positive cone of crossing vectors. The equation is solvable only if $-F_{\mathbf 1}$ lies in this cone. A positive linear functional can separate an excluded assumption from the cone.

</figcaption>
</figure>

This cone picture is the conceptual reason that numerical bootstrap bounds are possible. A linear functional can certify that a proposed set of assumptions is inconsistent.

## Setup and conventions

We use the scalar four-point convention

$$
\langle \phi_1\phi_2\phi_3\phi_4\rangle
=
\frac{1}{(x_{12}^2x_{34}^2)^{\Delta_\phi}}\mathcal G(U,V),
$$

with

$$
U=z\bar z,
\qquad
V=(1-z)(1-\bar z).
$$

For identical scalars,

$$
\mathcal G(U,V)
=
\sum_{\mathcal O\in\phi\times\phi}
\lambda_{\phi\phi\mathcal O}^2G_{\Delta,
\ell}(U,V).
$$

The identity block is

$$
G_{0,0}(U,V)=1,
\qquad
\lambda_{\phi\phi\mathbf 1}=1
$$

if the scalar is two-point normalized as

$$
\langle \phi(x)\phi(0)\rangle=\frac{1}{(x^2)^{\Delta_\phi}}.
$$

The crossing vector is

$$
F_{\Delta,\ell}(U,V)
=
V^{\Delta_\phi}G_{\Delta,
\ell}(U,V)
-
U^{\Delta_\phi}G_{\Delta,
\ell}(V,U).
$$

The identity vector is

$$
F_{\mathbf 1}(U,V)=V^{\Delta_\phi}-U^{\Delta_\phi}.
$$

Thus

$$
F_{\mathbf 1}(U,V)
+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2F_{\Delta,\ell}(U,V)=0.
$$

This is the prototype bootstrap equation.

## What the equation means

The equation is not one equation in two numbers. It is an equality of functions. In principle, it is equivalent to infinitely many scalar equations obtained by testing against functionals or expanding around points.

For example, one can apply derivatives at the crossing-symmetric point

$$
z=\bar z=\frac12.
$$

A typical derivative functional has the form

$$
\alpha[f]
=
\sum_{m,n}a_{mn}
\left.
\partial_z^m\partial_{\bar z}^n f(z,\bar z)
\right|_{z=\bar z=1/2}.
$$

Applying $\alpha$ to the crossing equation gives

$$
\alpha(F_{\mathbf 1})
+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2\alpha(F_{\Delta,\ell})=0.
$$

If $\lambda^2\ge0$, this becomes a positivity problem: can a positive sum of numbers $\alpha(F_{\Delta,\ell})$ cancel $\alpha(F_{\mathbf 1})$? A single functional may exclude a proposed spectrum if all terms have the same sign.

Numerical bootstrap uses a finite-dimensional family of such functionals. Increasing the number of derivatives usually strengthens the bounds, but it also increases computational cost and numerical sensitivity.

## Exclusion by a linear functional

Suppose the assumptions say that all non-identity operators appearing in $\phi\times\phi$ lie in an allowed set $\mathcal A$. For example, $\mathcal A$ may include all even-spin operators above the unitarity bound, plus a gap assumption such as

$$
\Delta_{\text{first scalar}}\ge\Delta_*.
$$

If there exists a linear functional $\alpha$ such that

$$
\alpha(F_{\mathbf 1})>0
$$

and

$$
\alpha(F_{\Delta,\ell})\ge0
\qquad
\text{for every }(\Delta,
\ell)\in\mathcal A,
$$

then the assumed CFT data are impossible. Indeed, applying $\alpha$ to crossing gives

$$
0
=
\alpha(F_{\mathbf 1})
+
\sum_{\mathcal O\ne\mathbf 1}
\lambda_{\phi\phi\mathcal O}^2\alpha(F_{\Delta,\ell}),
$$

but every term on the right is nonnegative and the identity term is strictly positive. Contradiction.

This is the cleanest bootstrap logic:

```txt
assumptions about the spectrum
        ↓
allowed crossing vectors
        ↓
try to find a separating functional
        ↓
functional found     → assumptions excluded
no functional found  → assumptions not excluded at this search strength
```

The second outcome is deliberately weaker. Failure to find a functional is not proof of existence. It may mean the assumptions are allowed, or it may mean the search space was too small.

## Bounds from moving assumptions

To get a numerical bound, vary one assumption until exclusion fails. For example, ask whether a unitary CFT with scalar $\phi$ of dimension $\Delta_\phi$ can have no scalar in $\phi\times\phi$ below $\Delta_*$. If a separating functional exists for a given $\Delta_*$, that gap is impossible.

The largest excluded gap gives an upper bound on the first scalar dimension:

$$
\Delta_{\text{first scalar}}
\le
\Delta_{\max}(\Delta_\phi).
$$

This is how many classic bootstrap plots are read. A curve is not the spectrum of a theory. It is the boundary between assumptions that have been excluded and assumptions that have not been excluded within a specified numerical setup.

Kinks often appear on such boundaries. They are important clues, but not automatic identifications. A kink becomes convincing only when it is stable under stronger numerics, agrees with other correlators or known data, and yields a sensible extremal spectrum.

## Equality constraints and known operators

Sometimes a theory has an operator whose dimension is known or treated as an external parameter. Then the bootstrap equation can separate that operator from the rest of the sum.

For example, suppose a scalar $\epsilon$ appears in $\phi\times\phi$. Then

$$
F_{\mathbf 1}
+
\lambda_{\phi\phi\epsilon}^2F_{\Delta_\epsilon,0}
+
\sum_{\mathcal O\ne\mathbf 1,
\epsilon}
\lambda_{\phi\phi\mathcal O}^2F_{\Delta,\ell}=0.
$$

One can ask for allowed regions in the $(\Delta_\phi,\Delta_\epsilon)$ plane, or bound $\lambda_{\phi\phi\epsilon}$ at fixed dimensions. This is already more informative than a one-dimensional gap bound.

In mixed-correlator systems, low-lying operators can appear in several OPEs. The same OPE coefficient, or related coefficients, must be used consistently across different correlators. This sharing of data is why mixed-correlator bootstrap is so powerful.

## Global symmetry equations

If $\phi_i$ transforms under a global symmetry, the four-point function decomposes into irreducible representations. For an $O(N)$ vector $\phi_i$, the product decomposes schematically as

$$
\mathbf N\otimes\mathbf N
=
S\oplus T\oplus A,
$$

where $S$ is the singlet, $T$ is symmetric traceless, and $A$ is antisymmetric. The crossing equation becomes

$$
\sum_{\mathcal O\in S}
\lambda_{S,\mathcal O}^2\vec F^{\,S}_{\Delta,
\ell}
+
\sum_{\mathcal O\in T}
\lambda_{T,\mathcal O}^2\vec F^{\,T}_{\Delta,
\ell}
+
\sum_{\mathcal O\in A}
\lambda_{A,\mathcal O}^2\vec F^{\,A}_{\Delta,
\ell}
=0.
$$

The vectors encode both spacetime conformal blocks and group-theory crossing matrices. Spin selection rules depend on the symmetry channel. For identical bosonic scalars, symmetric internal channels pair with even spacetime spin, while antisymmetric channels pair with odd spacetime spin.

This is a first example of a vectorial bootstrap equation. Instead of one function $F_{\Delta,\ell}$, each operator contributes a vector of functions.

## Mixed correlator equations

Single-correlator equations are powerful, but many important results require mixed correlators. Suppose we study two scalar primaries $\sigma$ and $\epsilon$. Then a bootstrap system can include

$$
\langle \sigma\sigma\sigma\sigma\rangle,
\qquad
\langle \sigma\sigma\epsilon\epsilon\rangle,
\qquad
\langle \epsilon\epsilon\epsilon\epsilon\rangle.
$$

Operators appearing in both $\sigma\times\sigma$ and $\epsilon\times\epsilon$ have OPE coefficient vectors such as

$$
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O}\\
\lambda_{\epsilon\epsilon\mathcal O}
\end{pmatrix}.
$$

Their contribution to crossing involves a positive semidefinite matrix

$$
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O}\\
\lambda_{\epsilon\epsilon\mathcal O}
\end{pmatrix}
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O} &
\lambda_{\epsilon\epsilon\mathcal O}
\end{pmatrix}.
$$

This is the origin of semidefinite programming in mixed-correlator bootstrap. Positivity is no longer just $\lambda^2\ge0$; it is positivity of coefficient matrices.

## Fermions, currents, and spinning operators

For spinning external operators, a correlator has several tensor structures. Crossing becomes a matrix or vector equation over these structures. Conservation constraints can remove or relate structures. Parity, time-reversal, and dimension-specific identities can further refine the basis.

The conceptual form remains the same:

$$
\sum_{\mathcal O}
\text{OPE data}\times\text{crossing vector or matrix for }\mathcal O=0.
$$

What changes is the amount of bookkeeping. Spinning bootstrap problems require careful choices of tensor bases, block normalizations, and reflection-positive inner products. The formulas get heavier, but the logic does not mutate into a different species.

## Truncation and numerical meaning

The exact bootstrap equation is infinite-dimensional in several ways:

- infinitely many operators can appear;
- conformal blocks are functions of continuous variables;
- the set of possible dimensions is continuous before constraints are imposed;
- derivative or functional spaces are infinite-dimensional.

Numerical bootstrap makes finite choices. A typical computation chooses:

| Choice | Meaning |
|---|---|
| External data | Which correlators and external dimensions are included. |
| Assumptions | Symmetry sectors, gaps, known operators, and selection rules. |
| Functional basis | Which derivatives or other functionals are allowed. |
| Spin cutoff or tail treatment | How high-spin contributions are handled. |
| Block approximation | How conformal blocks and derivatives are evaluated. |
| Precision | Numerical arithmetic and tolerances. |

A bound should always be interpreted with these choices in mind. Strong computations test stability as the derivative order, precision, spin treatment, and block approximations are improved.

## What counts as a solution?

A full solution of a CFT would give all local operator dimensions, spins, global representations, OPE coefficients, and enough consistency data to reconstruct all correlators. A bootstrap equation for one four-point function is far less than that.

Still, one four-point equation can do remarkable work. It can:

- rule out spectra with too-large gaps;
- bound OPE coefficients;
- reveal kinks suggesting special CFTs;
- produce extremal spectra on boundary points;
- constrain central charges through stress-tensor exchange;
- constrain current two-point coefficients through current exchange;
- provide consistency checks for perturbative, lattice, or holographic estimates.

Mixed-correlator systems can go further by isolating small islands of allowed data. Even then, the output is conditional: it depends on the assumptions used to define the system.

## Common pitfalls

| Pitfall | Repair |
|---|---|
| Calling the bootstrap equation linear in the CFT data. | It is linear in OPE coefficient products once the spectrum is fixed; finding the spectrum is nonlinear. |
| Forgetting the identity. | The identity term is fixed and usually moved to the other side conceptually. It is what the other operators must cancel. |
| Treating “not excluded” as “exists.” | Not excluded means no contradiction was found in the chosen search space. |
| Assuming positivity without checking the setup. | Positivity needs unitarity or reflection positivity and the right basis of correlators. |
| Ignoring degeneracies. | If several primaries have the same quantum numbers and dimensions, OPE data form vectors or matrices. |
| Overinterpreting a kink. | A kink is evidence, not a proof of a specific CFT. Look for stability and independent checks. |
| Hiding assumptions. | Every gap, symmetry, external-dimension value, and normalization choice should be explicit. |
| Comparing different papers without matching conventions. | Blocks, OPE coefficients, current normalizations, and stress-tensor normalizations vary across the literature. |

## Relations to other pages

- [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) derives the functional equation before block expansion.
- [Conformal Data from OPE](/cft-bootstrap/operator-product-expansion/conformal-data-from-ope/) explains why spectra and OPE coefficients define the dynamical data.
- [Conformal Partial Waves](/cft-bootstrap/conformal-blocks/conformal-partial-waves/) gives the projector interpretation of block contributions.
- [Scalar Conformal Blocks](/cft-bootstrap/conformal-blocks/scalar-conformal-blocks/) supplies the simplest $G_{\Delta,
\ell}$ functions used here.
- [Positivity and Unitarity](/cft-bootstrap/crossing-bootstrap-logic/positivity-and-unitarity/) develops the reflection-positive argument behind $\lambda^2\ge0$ and matrix positivity.
- [Linear Functionals](/cft-bootstrap/numerical-bootstrap/linear-functionals/) turns the exclusion logic into an algorithmic method.
- [Semidefinite Programming](/cft-bootstrap/numerical-bootstrap/semidefinite-programming/) explains the computational form of mixed-correlator positivity.

## Research status

The formulation of four-point bootstrap equations is established and widely used. The single-correlator identical-scalar equation is now a standard entry point into higher-dimensional CFT.

Active work focuses on stronger systems and sharper interpretation: mixed correlators, spinning correlators, conserved currents, stress tensors, defects, supersymmetry, nonunitary models, rigorous numerical certificates, navigator methods, extremal spectra, and hybrid analytic-numerical approaches. The equations are old; the art of extracting everything they know is still young enough to be interesting.

## Exercises

### Exercise 1: Move the identity to the other side

Starting from

$$
F_{\mathbf 1}
+
\sum_{\mathcal O\ne\mathbf 1}p_{\mathcal O}F_{\mathcal O}=0,
\qquad
p_{\mathcal O}\ge0,
$$

show that the bootstrap equation is equivalent to a cone-membership statement.

<details><summary><strong>Solution</strong></summary>

Move the identity term to the right:

$$
\sum_{\mathcal O\ne\mathbf 1}p_{\mathcal O}F_{\mathcal O}
=
-F_{\mathbf 1}.
$$

Since all coefficients $p_{\mathcal O}$ are nonnegative, the left side lies in the positive cone generated by the non-identity crossing vectors. Thus crossing is solvable only if

$$
-F_{\mathbf 1}
\in
\operatorname{Cone}\{F_{\mathcal O}:\mathcal O\ne\mathbf 1\}.
$$

</details>

### Exercise 2: Functional contradiction

Assume there is a linear functional $\alpha$ with

$$
\alpha(F_{\mathbf 1})>0,
\qquad
\alpha(F_{\mathcal O})\ge0
$$

for every allowed non-identity operator. Prove that the assumed spectrum is inconsistent.

<details><summary><strong>Solution</strong></summary>

Apply $\alpha$ to crossing:

$$
0
=
\alpha(F_{\mathbf 1})
+
\sum_{\mathcal O\ne\mathbf 1}p_{\mathcal O}\alpha(F_{\mathcal O}).
$$

The first term is strictly positive. Every term in the sum is nonnegative because $p_{\mathcal O}\ge0$ and $\alpha(F_{\mathcal O})\ge0$. Therefore the right side is strictly positive, contradicting equality to zero. No CFT satisfying the assumptions can exist.

</details>

### Exercise 3: Derivative functionals

Why does evaluating the crossing equation only at $z=\bar z=1/2$ not usually give a useful exclusion problem, while derivatives around that point can?

<details><summary><strong>Solution</strong></summary>

For identical scalar crossing, the antisymmetric crossing vectors often vanish at the symmetric point because $U=V$ there. Evaluating only the value can therefore lose the constraint. Derivatives probe how the two channel expansions differ near the symmetric point. A finite set of derivatives gives a finite-dimensional projection of the full functional equation, and a sufficiently rich set of derivatives can detect contradictions invisible to the value alone.

</details>

### Exercise 4: Positivity in a mixed system

Suppose an operator $\mathcal O$ appears in both $\sigma\times\sigma$ and $\epsilon\times\epsilon$. Explain why its OPE data naturally form a positive semidefinite matrix.

<details><summary><strong>Solution</strong></summary>

The relevant OPE coefficient vector is

$$
\vec\lambda_{\mathcal O}
=
\begin{pmatrix}
\lambda_{\sigma\sigma\mathcal O}\\
\lambda_{\epsilon\epsilon\mathcal O}
\end{pmatrix}.
$$

Its contribution to crossing contains the outer product

$$
\vec\lambda_{\mathcal O}\vec\lambda_{\mathcal O}^{\,T}.
$$

For any real vector $v$,

$$
v^T(\vec\lambda\vec\lambda^{\,T})v
=(v\cdot\vec\lambda)^2\ge0.
$$

Thus the coefficient matrix is positive semidefinite. This is the matrix version of the positivity $\lambda^2\ge0$ in a single identical-correlator bootstrap problem.

</details>

## References

- R. Rattazzi, V. S. Rychkov, E. Tonni, and A. Vichi, “Bounding scalar operator dimensions in 4D CFT,” 2008.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, lectures on bootstrap equations and numerical logic.
- D. Simmons-Duffin, “The Conformal Bootstrap,” TASI lectures, sections on reflection positivity, crossing, and semidefinite programming.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” sections on crossing relations and numerical methods.
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” review of recent software, algorithms, navigator methods, skydive, and applications.

## Version history

- 2026-06-28: First polished draft. Added the identical-scalar bootstrap equation, identity separation, cone picture, functional-exclusion proof, gap-bound logic, global-symmetry and mixed-correlator extensions, pitfalls, exercises, and a vector-cone figure.
