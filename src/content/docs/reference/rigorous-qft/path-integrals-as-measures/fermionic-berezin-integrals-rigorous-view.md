---
title: "Fermionic Berezin Integrals: Rigorous View"
description: "Explains finite-dimensional Berezin integration, Grassmann Gaussian identities, and why fermionic path integrals are algebraic rather than probability measures."
sidebar:
  label: "Fermionic Berezin Integrals"
  order: 8
level: Graduate
status: "Polished draft"
source: "Berezin superanalysis; Osterwalder–Schrader Euclidean Fermi fields; standard QFT fermionic path integrals; CAR algebra viewpoint."
topics:
  - Berezin integration
  - Grassmann variables
  - fermionic path integrals
  - determinants
  - Pfaffians
  - CAR algebra
canonicalTopics:
  - berezin-integral
  - grassmann-algebra
  - fermionic-path-integral
  - gaussian-grassmann-integral
  - determinant
  - pfaffian
researchStatus:
  established:
    - "Finite-dimensional Berezin integration is a precise algebraic operation, and finite-cutoff fermionic path integrals are rigorous elements of finite Grassmann algebra."
  active:
    - "Continuum fermionic QFT still requires cutoff removal, positivity or Hilbert-space reconstruction, and gauge/anomaly control; Berezin integration alone does not solve these problems."
---

## Summary

Fermionic path integrals are not probability measures. They are algebraic integrals over Grassmann generators. This is a feature, not a defect: anticommuting variables are exactly what is needed to encode fermionic antisymmetry, determinants, Pfaffians, and the signs of Fermi statistics.

For Grassmann generators $\theta_1,\ldots,\theta_N$,

$$
\theta_i\theta_j=-\theta_j\theta_i,
\qquad
\theta_i^2=0,
$$

and every element of the finite Grassmann algebra has a finite expansion

$$
F(\theta)=\sum_{I\subset\{1,\ldots,N\}}F_I\theta_I.
$$

Berezin integration is the linear functional that extracts the top coefficient, after an ordering convention has been fixed:

$$
\int d\theta_N\cdots d\theta_1\,\theta_1\theta_2\cdots\theta_N=1.
$$

The rigorous moral is simple:

$$
\text{bosonic Euclidean integral} \sim \text{measure},
\qquad
\text{fermionic Euclidean integral} \sim \text{exterior-algebra functional}.
$$

In a cutoff theory with finitely many fermionic modes, this is completely precise. The hard continuum questions come later: convergence of correlation functions, compatibility with CAR algebras or Osterwalder–Schrader reconstruction, anomaly control, and interaction with bosonic or gauge-field measures.

## Prerequisites

You should know [Finite-Dimensional Measures](/rigorous-qft/path-integrals-as-measures/finite-dimensional-measures/), [Gaussian Random Fields](/rigorous-qft/path-integrals-as-measures/gaussian-random-fields/), and [Continuum Limit of Measures](/rigorous-qft/path-integrals-as-measures/continuum-limit-of-measures/). For the operator side, it helps to know [Hilbert Space and Fields](/rigorous-qft/wightman-axiomatic-qft/hilbert-space-and-fields/) and [States and GNS Representation](/rigorous-qft/algebraic-qft/states-and-gns-representation/).

## Core idea

A bosonic Gaussian integral over ordinary commuting variables produces inverse quadratic forms in correlations and determinant factors in normalization. A fermionic Gaussian Berezin integral produces the same inverse quadratic form in contractions, but the normalization is a determinant in the numerator rather than the denominator.

<figure class="doc-figure" style="--figure-width: 55rem;">

![A flowchart from Grassmann generators to exterior algebra, Berezin integration, and determinant or Pfaffian Gaussian identities.](/figures/rigorous-qft/berezin-integral-algebra.svg)

<figcaption>

Berezin integration is a finite-dimensional algebraic operation. It extracts the top exterior-degree coefficient and turns quadratic fermionic actions into determinants or Pfaffians. It is not integration against a positive measure on a sample space.

</figcaption>
</figure>

For complex fermions with independent generators $\psi_i$ and $\bar\psi_i$, the basic identity is

$$
\int
\prod_{i=1}^N d\bar\psi_i\,d\psi_i
\exp\bigl(-\bar\psi A\psi\bigr)
=
\det A,
$$

with the ordering convention specified below. For real or Majorana fermions, an antisymmetric matrix $A$ gives

$$
\int d\xi_{2n}\cdots d\xi_1
\exp\left(\frac12\xi^T A\xi\right)
=
\operatorname{pf}(A),
\qquad
\operatorname{pf}(A)^2=\det A.
$$

These identities are the algebraic reason that integrating out fermions in a cutoff theory gives determinants or Pfaffians of Dirac-type operators.

## Setup and conventions

A finite Grassmann algebra over $\mathbb C$ with generators $\theta_1,\ldots,\theta_N$ is the exterior algebra

$$
\Lambda_N
=
\bigwedge \mathbb C^N.
$$

The generators anticommute:

$$
\theta_i\theta_j=-\theta_j\theta_i.
$$

In particular, $\theta_i^2=0$. A standard ordered monomial is

$$
\theta_I
=
\theta_{i_1}\theta_{i_2}\cdots\theta_{i_k},
\qquad
I=\{i_1< i_2<\cdots<i_k\}.
$$

Every element has a unique expansion

$$
F=\sum_I F_I\theta_I.
$$

The Berezin integral is defined by

$$
\int d\theta_N\cdots d\theta_1\,F
=
F_{\{1,\ldots,N\}}.
$$

Thus Berezin integration is not a limiting procedure, and it is not a positive functional. It is coefficient extraction.

For complex fermions, we use independent generators $\psi_i$ and $\bar\psi_i$. They are not complex conjugates inside the algebra; the bar is a label indicating the variable paired with $\psi_i$. We choose the integration order so that the Gaussian identity

$$
\int
\prod_{i=1}^N d\bar\psi_i\,d\psi_i
\exp\bigl(-\bar\psi A\psi\bigr)
=
\det A
$$

holds. Different books choose different orders. A different order changes signs in intermediate formulas, but not the invariant content once the convention is used consistently.

## Berezin integration as differentiation

For one generator,

$$
F(\theta)=a+b\theta.
$$

The Berezin integral is

$$
\int d\theta\,F(\theta)=b.
$$

This is the same operation as differentiation with respect to $\theta$:

$$
\frac{\partial}{\partial\theta}(a+b\theta)=b.
$$

For many variables, one must track signs. The left derivative is determined by

$$
\frac{\partial}{\partial\theta_i}\theta_j
=
\delta_{ij}
$$

and the graded Leibniz rule

$$
\frac{\partial}{\partial\theta_i}(FG)
=
\left(\frac{\partial F}{\partial\theta_i}\right)G
+(-1)^{|F|}F
\left(\frac{\partial G}{\partial\theta_i}\right)
$$

when $F$ is homogeneous of Grassmann parity $|F|$. The right derivative has a different sign convention. This is one of the main reasons sign errors are common in fermionic path integrals.

## The finite-dimensional Gaussian identities

### Complex fermions and determinants

Let

$$
\bar\psi A\psi
=
\sum_{i,j=1}^N \bar\psi_i A_{ij}\psi_j.
$$

Because Grassmann variables are nilpotent, the exponential is a finite polynomial:

$$
\exp(-\bar\psi A\psi)
=
\sum_{k=0}^{N}\frac{(-\bar\psi A\psi)^k}{k!}.
$$

Only the top-degree term contributes to the integral. Expanding that top term gives the determinant:

$$
\int
\prod_{i=1}^N d\bar\psi_i\,d\psi_i
\exp(-\bar\psi A\psi)
=
\det A.
$$

The source identity is even more useful. Introduce Grassmann sources $\eta_i$ and $\bar\eta_i$. Then

$$
\int
\prod_i d\bar\psi_i\,d\psi_i
\exp\bigl(
-\bar\psi A\psi
+\bar\eta\psi
+\bar\psi\eta
\bigr)
=
\det A\,
\exp(\bar\eta A^{-1}\eta).
$$

Correlation functions are obtained by differentiating with respect to the sources. For example, with normalized expectation,

$$
\langle \psi_i\bar\psi_j\rangle
=
(A^{-1})_{ij}
$$

up to the sign determined by the chosen source-derivative order. This "up to sign convention" is not evasive: the convention must be fixed once and then used consistently.

### Real fermions and Pfaffians

For real Grassmann generators $\xi_1,\ldots,\xi_{2n}$ and an antisymmetric matrix $A^T=-A$,

$$
\frac12\xi^T A\xi
=
\sum_{i<j} A_{ij}\xi_i\xi_j.
$$

The Gaussian Berezin integral is

$$
\int d\xi_{2n}\cdots d\xi_1
\exp\left(\frac12\xi^T A\xi\right)
=
\operatorname{pf}(A).
$$

For two generators,

$$
A=\begin{pmatrix}0&a\\-a&0\end{pmatrix},
\qquad
\frac12\xi^TA\xi=a\xi_1\xi_2,
$$

so

$$
\int d\xi_2d\xi_1\,e^{a\xi_1\xi_2}=a.
$$

This is the Pfaffian of $A$. Majorana fermions and real fermionic systems naturally produce Pfaffians rather than determinants.

## Why this is not measure theory

A probability measure $\mu$ on a space $X$ gives a positive functional:

$$
F\geq0
\quad\Longrightarrow\quad
\int_X F\,d\mu\geq0.
$$

Berezin integration has no such property. There is no ordinary point set whose points are Grassmann numbers and whose positive measure realizes the Berezin integral as expectation. The integral

$$
\int d\theta\,(a+b\theta)=b
$$

throws away the scalar part and keeps the nilpotent coefficient. This cannot be a positive measure on an ordinary measurable space.

The right analogy is exterior algebra, not probability. Fermionic path integrals are rigorous because finite exterior algebras are rigorous. They become subtle in QFT because one must take continuum and infinite-volume limits, not because the finite-dimensional algebra is vague.

## Fermionic fields at cutoff

On a finite lattice, a Dirac field is a finite collection of Grassmann generators

$$
\psi_{x,\alpha,c},
\qquad
\bar\psi_{x,\alpha,c},
$$

where $x$ labels lattice sites, $\alpha$ labels spinor components, and $c$ labels internal indices such as color. A lattice fermion action has the schematic form

$$
S_F(\bar\psi,\psi;A)
=
\sum_{x,y}\bar\psi_x D_{xy}[A]\psi_y,
$$

where $D[A]$ is a finite matrix depending on a background bosonic or gauge field $A$. The fermionic integral is then

$$
\int D\bar\psi D\psi\,
\exp\bigl(-\bar\psi D[A]\psi\bigr)
=
\det D[A].
$$

If fermionic observables are inserted, one obtains minors or inverse matrix elements. For instance, schematically,

$$
\frac{1}{\det D[A]}
\int D\bar\psi D\psi\,
\psi_x\bar\psi_y
\exp\bigl(-\bar\psi D[A]\psi\bigr)
=
D[A]^{-1}_{xy}
$$

with the sign determined by the ordering convention.

After integrating out the finite Grassmann algebra, one is left with an ordinary bosonic integral weighted by $\det D[A]$ or by a Pfaffian. That remaining integral may or may not be a positive measure. If the determinant is complex or changes sign, one has a sign problem for numerical probability methods. The sign problem is not caused by an ill-defined Grassmann integral; it arises after the exact algebraic fermion integral has produced a nonpositive bosonic weight.

## Relation to CAR algebras and Fock space

The Hilbert-space description of fermions uses the canonical anticommutation relations:

$$
\{a_i,a_j^\dagger\}=\delta_{ij},
\qquad
\{a_i,a_j\}=\{a_i^\dagger,a_j^\dagger\}=0.
$$

Berezin variables are not the same as creation and annihilation operators. They are algebraic variables used to package matrix elements, coherent-state overlaps, and antisymmetric contractions. In finite dimensions, coherent-state methods relate fermionic traces and transition amplitudes to Berezin integrals.

In infinite systems, the CAR-algebra viewpoint can be more intrinsic. A quasi-free fermionic state is determined by its two-point function, and higher correlations follow from a determinant or Pfaffian Wick rule. The Grassmann path integral is then a compact calculational representation of the same algebraic structure, provided the cutoff and limiting procedures are controlled.

This is parallel to the bosonic story but not identical. Bosonic Gaussian measures are actual probability measures on distribution spaces. Fermionic Gaussian functionals are algebraic quasi-free functionals on exterior or CAR algebras.

## Euclidean fermions and positivity

For bosonic Euclidean fields, reflection positivity is a positivity condition on functions supported in positive Euclidean time. Fermions require additional sign, adjoint, and time-reflection structure. Naively reflecting a fermionic field does not produce an ordinary positive measure statement because the fields anticommute.

There are rigorous Euclidean Fermi-field frameworks, but their positivity condition is not simply "the measure is positive." One must encode the correct conjugation, reflection, and CAR structure. In mixed boson–fermion models, the fermions are often integrated out to produce determinants or Pfaffians, while the final Hilbert-space positivity is checked through a more refined Osterwalder–Schrader or operator-algebraic construction.

This is why the phrase "fermionic Euclidean measure" should be used carefully. At finite cutoff one has a Grassmann algebra and a Berezin functional. To get a physical fermionic QFT, one still needs a reconstruction theorem or an equivalent Hilbert-space construction.

## Infinite-dimensional fermionic path integrals

Physicists often write

$$
\int D\bar\psi D\psi\,
\exp\left[-\int \bar\psi D\psi\,d^dx\right].
$$

Rigorous interpretation begins by replacing the field by finitely many modes, lattice sites, or test-function coefficients. Then the integral is a finite Berezin integral. The continuum expression is shorthand for a limiting process:

$$
\begin{gathered}
\text{finite Grassmann algebra at cutoff}\\
\longrightarrow
\text{determinants, Pfaffians, and fermion correlators}\\
\longrightarrow
\text{renormalized continuum limit, if it exists.}
\end{gathered}
$$

There is no countably additive probability measure over infinitely many anticommuting coordinates analogous to a Gaussian measure on $\mathcal S'(\mathbb R^d)$. Instead, one uses compatible finite-dimensional Grassmann algebras, CAR algebras, quasi-free states, determinant identities, or perturbative formal power series.

In perturbative QFT, the finite-dimensional formulas are used formally mode by mode and organized by Feynman rules. In constructive fermionic models, one proves bounds on determinants, truncated expectations, or RG expansions. In lattice gauge theory, one keeps the lattice finite, performs finite-dimensional Grassmann integration exactly, and then studies the remaining bosonic or gauge-field problem.

## Fermions coupled to bosons

A Yukawa-type Euclidean cutoff action has the schematic form

$$
S(\phi,\bar\psi,\psi)
=
S_B(\phi)+\bar\psi D(\phi)\psi.
$$

At finite cutoff,

$$
\int D\bar\psi D\psi\,
\exp\bigl[-S_B(\phi)-\bar\psi D(\phi)\psi\bigr]
=
\exp[-S_B(\phi)]\det D(\phi).
$$

The fermions have been integrated out exactly. The remaining question is whether

$$
\exp[-S_B(\phi)]\det D(\phi)
$$

defines an integrable, positive, reflection-positive, and renormalizable bosonic weight. Sometimes it does. Sometimes the determinant is complex. Sometimes anomalies obstruct desired symmetries. Sometimes additional counterterms are required.

For Majorana fermions, the corresponding expression is a Pfaffian:

$$
\int D\xi\,
\exp\left(-\frac12\xi A(\phi)\xi\right)
=
\operatorname{pf}(A(\phi)).
$$

The sign of this Pfaffian can carry important physics.

## Common pitfalls

**Calling Berezin integration a probability integral.** It is a linear functional on an exterior algebra. It does not integrate positive functions over a sample space.

**Thinking Grassmann variables are small real numbers.** They are nilpotent algebra generators. The expansion in a Grassmann variable terminates because $\theta^2=0$, not because $\theta$ is infinitesimal.

**Forgetting that order matters.** Reordering Grassmann variables changes signs. Integration-order conventions determine signs in determinant, Pfaffian, and source formulas.

**Treating $\bar\psi$ as literal complex conjugation.** In Euclidean finite-dimensional Berezin integrals, $\psi$ and $\bar\psi$ are independent generators. Reality conditions require additional structure.

**Assuming determinant positivity.** Integrating out fermions gives determinants or Pfaffians, but these need not be positive. A nonpositive determinant affects both numerical simulation and reflection-positivity arguments.

**Confusing formal continuum notation with finite algebra.** The rigorous algebra lives at finite cutoff. The continuum path integral is a shorthand for a limiting problem.

**Ignoring anomalies.** A formal Grassmann measure may transform with a nontrivial Jacobian under a symmetry. This is the path-integral face of anomalies.

## Relations to other pages

This page complements [Finite-Dimensional Measures](/rigorous-qft/path-integrals-as-measures/finite-dimensional-measures/). Bosonic finite-dimensional integrals are measure-theoretic; fermionic finite-dimensional integrals are exterior-algebraic.

It also complements [Continuum Limit of Measures](/rigorous-qft/path-integrals-as-measures/continuum-limit-of-measures/). The continuum issue for fermions is not the construction of an infinite-dimensional Grassmann measure; it is the convergence and reconstruction of fermionic correlation functions or CAR-algebra states.

For gauge theories, this page is a prerequisite for BV-BRST and anomalies. For operator-algebraic foundations, compare the CAR algebra with the local-net viewpoint in [Algebraic QFT](/rigorous-qft/algebraic-qft/). For ordinary physics computations, compare with the fermionic path-integral treatments in the Foundations and Perturbative QFT volumes.

## Research status

Finite-dimensional Berezin integration is fully rigorous and elementary once exterior algebras are known. Free fermionic fields are rigorously understood through CAR algebras, quasi-free states, Euclidean Fermi fields, and Wightman-type constructions.

Interacting fermionic models can often be treated perturbatively, on a lattice, or in low-dimensional constructive settings. Nonperturbative continuum gauge theories with chiral fermions are subtler: one must control the regulator, continuum limit, gauge invariance, anomalies, and positivity or unitarity. Berezin integration supplies the finite-cutoff algebra, but it does not by itself solve the continuum construction.

The honest status statement is: fermionic path integrals are not mathematically vague at finite cutoff; the unresolved issues are the same high-level QFT issues as elsewhere — renormalization, continuum limits, gauge symmetry, anomalies, and reconstruction.

## Exercises

### Exercise 1: One complex fermion pair

With the convention used on this page, show that

$$
\int d\bar\psi\,d\psi\,e^{-\bar\psi a\psi}=a.
$$

<details><summary><strong>Solution</strong></summary>

Since $(\bar\psi a\psi)^2=0$,

$$
e^{-\bar\psi a\psi}=1-\bar\psi a\psi.
$$

Using the integration order convention chosen so that

$$
\int d\bar\psi\,d\psi\,(-\bar\psi\psi)=1,
$$

we obtain

$$
\int d\bar\psi\,d\psi\,e^{-\bar\psi a\psi}
=
-a\int d\bar\psi\,d\psi\,\bar\psi\psi
=a.
$$

A different convention shifts the sign into the definition of the ordered measure. The determinant formula is the invariant convention-fixing statement.

</details>

### Exercise 2: Two real generators and the Pfaffian

Let $\xi_1,\xi_2$ be real Grassmann generators and

$$
A=\begin{pmatrix}0&a\\-a&0\end{pmatrix}.
$$

Compute

$$
\int d\xi_2d\xi_1
\exp\left(\frac12\xi^TA\xi\right).
$$

<details><summary><strong>Solution</strong></summary>

First,

$$
\frac12\xi^TA\xi
=
\frac12\bigl(\xi_1a\xi_2+\xi_2(-a)\xi_1\bigr)
=a\xi_1\xi_2,
$$

because $\xi_2\xi_1=-\xi_1\xi_2$. Since $(\xi_1\xi_2)^2=0$,

$$
\exp(a\xi_1\xi_2)=1+a\xi_1\xi_2.
$$

Thus

$$
\int d\xi_2d\xi_1\,e^{a\xi_1\xi_2}=a.
$$

This equals $\operatorname{pf}(A)$.

</details>

### Exercise 3: Why the fermionic Gaussian gives a determinant

Explain in words why the integral

$$
\int
\prod_i d\bar\psi_i\,d\psi_i
\exp(-\bar\psi A\psi)
$$

must be a homogeneous polynomial of degree $N$ in the entries of $A$, and why antisymmetry suggests a determinant.

<details><summary><strong>Solution</strong></summary>

Only the top Grassmann degree contributes to the Berezin integral. Each factor $\bar\psi_i A_{ij}\psi_j$ contributes one $\bar\psi$ and one $\psi$, so the top term must use $N$ such factors. Hence the result is homogeneous of degree $N$ in the entries of $A$.

To survive integration, every $\bar\psi_i$ and every $\psi_j$ must appear exactly once. The possible pairings are labeled by permutations. Reordering anticommuting variables produces the sign of the permutation. The sum over products of matrix entries with permutation signs is precisely the determinant.

</details>

## References

### Standard first pass

- Felix A. Berezin, *Introduction to Superanalysis*, edited by A. A. Kirillov, Springer, 1987. DOI: [10.1007/978-94-017-1963-6](https://doi.org/10.1007/978-94-017-1963-6).
- Bryce DeWitt, *Supermanifolds*, second edition, Cambridge University Press, 1992. DOI: [10.1017/CBO9780511564000](https://doi.org/10.1017/CBO9780511564000).
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, fifth edition, Oxford University Press, 2021. DOI: [10.1093/oso/9780198834625.001.0001](https://doi.org/10.1093/oso/9780198834625.001.0001).
- Mark Srednicki, *Quantum Field Theory*, Cambridge University Press, 2007, chapters on fermionic path integrals and functional determinants.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, Cambridge University Press, 2014, chapter on path integrals and fermionic path integrals.

### Deeper references

- Konrad Osterwalder and Robert Schrader, "Feynman-Kac Formula for Euclidean Fermi and Bose Fields," *Physical Review Letters* **29** (1972), 1423–1425. DOI: [10.1103/PhysRevLett.29.1423](https://doi.org/10.1103/PhysRevLett.29.1423).
- Konrad Osterwalder and Robert Schrader, "Euclidean Fermi Fields and a Feynman-Kac Formula for Boson-Fermion Models," *Helvetica Physica Acta* **46** (1973), 277–302. DOI: [10.5169/seals-114501](https://doi.org/10.5169/seals-114501).
- Pierre Deligne and John W. Morgan, "Notes on Supersymmetry (following Joseph Bernstein)," in *Quantum Fields and Strings: A Course for Mathematicians*, Volume 1, American Mathematical Society, 1999. AMS page: [bookstore.ams.org/view?ProductCode=QFT%2F1%2F2](https://bookstore.ams.org/view?ProductCode=QFT%2F1%2F2).
- Ola Bratteli and Derek W. Robinson, *Operator Algebras and Quantum Statistical Mechanics 2*, second edition, Springer, 1997. DOI: [10.1007/978-3-662-09089-3](https://doi.org/10.1007/978-3-662-09089-3).

## Version history

- **2026-06-30:** Initial polished draft.
