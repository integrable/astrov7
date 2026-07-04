---
title: "Gauge Fixing as a Lagrangian Submanifold"
description: "Explains BV gauge fixing as the choice of a Lagrangian submanifold or gauge-fixing fermion, and separates perturbative gauge fixing from global quotient problems."
sidebar:
  label: "Gauge Fixing as a Lagrangian Submanifold"
  order: 8
level: Advanced
status: "Polished draft"
source: "Batalin–Vilkovisky; Schwarz; Henneaux–Teitelboim; Gomis–París–Samuel; perturbative algebraic QFT literature"
topics:
  - gauge fixing
  - Lagrangian submanifold
  - gauge-fixing fermion
  - Faddeev-Popov ghosts
  - Gribov ambiguity
canonicalTopics:
  - gauge-fixing
  - lagrangian-submanifold
  - bv-formalism
  - gauge-fixing-fermion
  - gribov-ambiguity
researchStatus:
  established:
    - "In finite-dimensional BV theory, gauge fixing is geometrically the choice of a Lagrangian submanifold, and the quantum master equation gives independence under suitable deformations."
  active:
    - "For local QFT, gauge fixing is usually perturbative and local in field space; global gauge slices can fail, and nonperturbative gauge fixing requires additional analytic and topological input."
---

## Summary

In the BV formalism, **gauge fixing is not an extra physical law**. It is a choice of representative for doing calculations. Geometrically, one starts with an odd symplectic field–antifield space and chooses a Lagrangian submanifold $\mathcal L$ on which to integrate or evaluate the gauge-fixed action:

$$
\text{BV field space }(\mathcal F_{\mathrm{BV}},\omega_{\mathrm{BV}})
\quad\longrightarrow\quad
\text{gauge-fixing Lagrangian } \mathcal L\subset\mathcal F_{\mathrm{BV}}.
$$

In Darboux coordinates $\Phi^A,\Phi_A^*$, a common way to specify $\mathcal L$ is by a **gauge-fixing fermion** $\Psi(\Phi)$ of ghost number $-1$:

$$
\Phi_A^*=\frac{\delta\Psi}{\delta\Phi^A}.
$$

Substituting this relation into the BV action gives the gauge-fixed action

$$
S_\Psi(\Phi)
=
S_{\mathrm{BV}}\!\left(
\Phi,\Phi^*=\frac{\delta\Psi}{\delta\Phi}
\right).
$$

For Yang–Mills theory, a Lorenz-type gauge-fixing fermion produces the familiar gauge-fixing term, auxiliary $b$-field term, and Faddeev–Popov ghost term. The BV point is that this is a coordinate expression for the geometric choice of $\mathcal L$.

:::caution[Status]
The finite-dimensional BV statement “different Lagrangian submanifolds give the same integral” is a clean theorem under suitable compactness and convergence assumptions. In local QFT, the corresponding statement is perturbative and renormalized. Globally, non-Abelian gauge theories can have Gribov ambiguities: a single smooth gauge slice meeting each gauge orbit exactly once need not exist.
:::

## Prerequisites

Read [BV Formalism](/rigorous-qft/bv-brst-gauge-theory/bv-formalism/), [Classical Master Equation](/rigorous-qft/bv-brst-gauge-theory/classical-master-equation/), [Quantum Master Equation](/rigorous-qft/bv-brst-gauge-theory/quantum-master-equation/), and [Observables as Cohomology](/rigorous-qft/bv-brst-gauge-theory/observables-as-cohomology/) first. The role of renormalized products is explained in [Local Covariant Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/local-covariant-time-ordered-products/).

## Core idea

A gauge theory has too many variables. If one tries to integrate over all field configurations, the integral contains an infinite gauge-orbit volume. A traditional Faddeev–Popov treatment introduces a gauge condition

$$
G(A)=0
$$

and inserts a determinant that compensates for the change of variables from fields to gauge orbits plus gauge representatives.

BV reorganizes this story. Instead of saying “choose a gauge condition” as an external operation, BV enlarges the field space to a field–antifield space with an odd symplectic form. Gauge fixing becomes the intrinsic geometric operation of choosing a Lagrangian submanifold.

<figure class="doc-figure" style="--figure-width: 52rem;">

![Gauge fixing in BV theory as choosing a Lagrangian submanifold](/figures/rigorous-qft/gauge-fixing-lagrangian-submanifold.svg)

<figcaption>

BV gauge fixing chooses a Lagrangian submanifold $\mathcal L_\Psi$ in the field–antifield space. A gauge-fixing fermion $\Psi$ gives the graph $\Phi^*_A=\delta\Psi/\delta\Phi^A$. The quantum master equation is the formal reason that cohomology-class observables are independent of allowed deformations of $\mathcal L_\Psi$.

</figcaption>
</figure>

The slogan is:

$$
\text{gauge condition}
\quad\leadsto\quad
\text{gauge-fixing fermion}
\quad\leadsto\quad
\text{Lagrangian submanifold}.
$$

## Setup and conventions

Let $\mathcal F_{\mathrm{BV}}$ be a graded field–antifield space with coordinates

$$
\Phi^A=(\text{fields, ghosts, nonminimal variables}),
\qquad
\Phi_A^*=(\text{their antifields}).
$$

The BV symplectic form is odd and has the local Darboux shape

$$
\omega_{\mathrm{BV}}
=
\sum_A
\delta \Phi_A^*\wedge \delta\Phi^A,
$$

with graded signs suppressed. The corresponding BV antibracket is

$$
(F,G)
=
\sum_A\left(
\frac{\partial_rF}{\partial\Phi^A}
\frac{\partial_lG}{\partial\Phi_A^*}
-
\frac{\partial_rF}{\partial\Phi_A^*}
\frac{\partial_lG}{\partial\Phi^A}
\right),
$$

again schematically suppressing the parity signs.

A submanifold $\mathcal L\subset\mathcal F_{\mathrm{BV}}$ is Lagrangian when the symplectic form restricts to zero and $\mathcal L$ has half the dimension in the graded symplectic sense:

$$
\omega_{\mathrm{BV}}\big|_{\mathcal L}=0.
$$

In Darboux coordinates, the simplest Lagrangian is the antifield-zero submanifold

$$
\Phi_A^*=0.
$$

More generally, if $\Psi(\Phi)$ is an odd functional of ghost number $-1$, then

$$
\mathcal L_\Psi:
\qquad
\Phi_A^*=\frac{\delta\Psi}{\delta\Phi^A}
$$

is Lagrangian. This is the standard BV gauge-fixing construction.

## Why the submanifold is Lagrangian

The graph of $d\Psi$ is Lagrangian for the same reason that the graph of an exact one-form is Lagrangian in ordinary cotangent-bundle symplectic geometry.

Restrict the BV symplectic form to the graph

$$
\Phi_A^*=\frac{\delta\Psi}{\delta\Phi^A}.
$$

Then

$$
\delta\Phi_A^*
=
\sum_B
\frac{\delta^2\Psi}{\delta\Phi^B\delta\Phi^A}
\,\delta\Phi^B.
$$

Substituting into $\omega_{\mathrm{BV}}$ gives a graded antisymmetrization of the second variation of $\Psi$. Since the second variation is graded symmetric in the appropriate sense, the antisymmetrized expression vanishes:

$$
\omega_{\mathrm{BV}}\big|_{\mathcal L_\Psi}=0.
$$

Thus a gauge-fixing fermion does not merely prescribe a formula for antifields. It gives a legitimate Lagrangian submanifold of the BV phase space.

## Nonminimal variables

A minimal BV action contains original fields, ghosts, and their antifields. It often does not contain enough variables to write a convenient covariant gauge condition. One adds a nonminimal BRST doublet, usually an antighost $\bar c$ and an auxiliary field $b$:

$$
s\bar c=b,
\qquad
sb=0.
$$

Because $(\bar c,b)$ is a BRST doublet, it does not change the physical cohomology under standard hypotheses. It does, however, allow a gauge-fixing fermion with ghost number $-1$.

For Yang–Mills theory, a common choice is

$$
\Psi
=
\int d^dx\,
\bar c^a
\left(
\partial^\mu A^a_\mu+\frac{\alpha}{2}b^a
\right).
$$

The parameter $\alpha$ labels a family of covariant gauges. The Landau-gauge limit is $\alpha=0$, while $\alpha=1$ is the Feynman-gauge choice in many perturbative conventions.

## Example: Yang–Mills Lorenz gauge

Let the minimal BRST transformations be

$$
sA^a_\mu=(D_\mu c)^a,
\qquad
sc^a=-\frac12 f^a{}_{bc}c^b c^c.
$$

Add the nonminimal pair

$$
s\bar c^a=b^a,
\qquad
sb^a=0.
$$

The gauge-fixing fermion

$$
\Psi
=
\int d^dx\,
\bar c^a
\left(
\partial^\mu A^a_\mu+\frac{\alpha}{2}b^a
\right)
$$

sets the antifields equal to

$$
A^{*\mu}_a
=
-\partial^\mu\bar c_a,
\qquad
\bar c_a^*
=
\partial^\mu A^a_\mu+\frac{\alpha}{2}b^a,
$$

and, up to conventions,

$$
c_a^*=0,
\qquad
b_a^*=\frac{\alpha}{2}\bar c_a.
$$

Substituting into the nonminimal BV action gives the gauge-fixed contribution

$$
S_{\mathrm{gf+gh}}
=
\int d^dx\,
\left[
b^a\,\partial^\mu A^a_\mu
+\frac{\alpha}{2}b^a b^a
-\bar c^a\,\partial^\mu(D_\mu c)^a
\right].
$$

Eliminating $b$ by its algebraic equation of motion gives

$$
S_{\mathrm{gf}}
=
-\frac{1}{2\alpha}
\int d^dx\,
(\partial^\mu A^a_\mu)^2
$$

up to the overall Lorentzian or Euclidean sign convention for the action. The ghost term is the Faddeev–Popov determinant written as a Grassmann integral.

The lesson is that the familiar covariant gauge-fixed Yang–Mills action is not an ad hoc modification. It is the BV master action restricted to a particular Lagrangian submanifold.

## Gauge independence and the master equation

In finite-dimensional BV theory, the quantum master equation implies gauge-fixing independence. Suppose

$$
\Delta e^{iS/\hbar}=0
$$

and suppose $\mathcal O$ is a compatible quantum observable:

$$
\Delta\left(\mathcal Oe^{iS/\hbar}\right)=0.
$$

Then the BV Stokes theorem implies that the integral

$$
\int_{\mathcal L}
\mathcal O\,e^{iS/\hbar}
$$

is unchanged under suitable deformations of $\mathcal L$. This is the geometric version of gauge independence.

In local QFT, one should read this statement perturbatively. The functional integral is formal, $\Delta$ is singular, and products of fields at coincident points require renormalization. A rigorous perturbative statement must be made in a renormalized algebra of functionals, often with a quantum BV operator, master Ward identity, or scale-dependent effective BV formalism.

The conceptual message survives:

$$
\text{cohomology-class observables}
\quad\text{should not depend on}
\quad
\text{allowed gauge-fixing choices}.
$$

## Relation to Faddeev–Popov gauge fixing

The Faddeev–Popov method starts from a gauge condition $G(A)=0$ and inserts

$$
1=
\Delta_{\mathrm{FP}}[A]\int Dg\,
\delta(G(A^g)).
$$

The determinant $\Delta_{\mathrm{FP}}$ is then written using ghosts. This method is efficient when the gauge algebra is irreducible, the gauge condition is convenient, and one works locally near a background.

BV is more flexible. It handles open gauge algebras, reducible gauge symmetries, higher-stage ghosts, and systematic deformation theory. It also separates two roles that are often conflated:

| Object | Role |
|---|---|
| Gauge condition $G=0$ | A concrete slice or representative condition. |
| Faddeev–Popov determinant | The Jacobian for changing variables along gauge orbits. |
| Gauge-fixing fermion $\Psi$ | A generator for the Lagrangian submanifold $\mathcal L_\Psi$. |
| Nonminimal doublet $(\bar c,b)$ | Auxiliary variables that implement a convenient gauge without changing cohomology. |
| BV master equation | The compatibility condition for gauge symmetry, equations of motion, and gauge independence. |

In ordinary Yang–Mills perturbation theory, the BV construction reproduces the Faddeev–Popov gauge-fixed action. In more complicated gauge theories, BV is often the cleaner starting point.

## Perturbative locality versus global slices

Gauge fixing has a local and a global meaning.

The **local perturbative** meaning is enough for many Feynman diagram calculations. One expands around a background field, chooses a local complement to the gauge directions, and inverts the kinetic operator on that complement. This gives propagators and vertices.

The **global** meaning would require a slice that meets every gauge orbit exactly once. For non-Abelian gauge theories, such a global slice can fail to exist. Gribov copies are multiple points on the same gauge orbit satisfying the same gauge condition. Singer's theorem shows that, for standard non-Abelian gauge theories over suitable compact manifolds, the obstruction is not just a bad choice of Coulomb gauge; it is topological.

This is why one must not say that a covariant gauge condition literally parameterizes the full nonperturbative quotient. It usually gives a perturbative coordinate choice, not a global solution of the quotient problem.

## Gauge-fixing fermion as a canonical transformation

Changing the gauge-fixing fermion can be viewed as an odd canonical transformation in the BV phase space. If

$$
\Psi\longmapsto \Psi+\delta\Psi,
$$

then the Lagrangian submanifold changes from $\mathcal L_\Psi$ to $\mathcal L_{\Psi+\delta\Psi}$. Under the finite-dimensional hypotheses of the BV theorem, integrals of quantum-closed observables do not change.

This is a powerful way to understand gauge-parameter independence. For example, changing $\alpha$ in the Yang–Mills fermion

$$
\Psi_\alpha
=
\int d^dx\,
\bar c^a
\left(
\partial^\mu A^a_\mu+\frac{\alpha}{2}b^a
\right)
$$

changes the representative used in perturbation theory. It should not change expectation values of physical cohomology classes, although it can change propagators, intermediate Green functions, and gauge-dependent composite operators.

## Common pitfalls

**Gauge fixing chooses a physical state.** It does not. It chooses a computational representative or a Lagrangian submanifold. Physical information should be extracted from gauge-independent cohomology classes.

**The antighost is the antifield of the ghost.** The antighost $\bar c$ is a nonminimal field used for gauge fixing. The ghost antifield $c^*$ is a BV antifield. They have different mathematical roles.

**Setting antifields to zero is always the right gauge.** The antifield-zero submanifold can be useful in simple finite-dimensional examples, but covariant QFT gauge fixing usually requires a nontrivial gauge-fixing fermion and nonminimal variables.

**Faddeev–Popov and BV are unrelated methods.** Faddeev–Popov gauge fixing is recovered from BV after a particular choice of nonminimal variables and gauge-fixing fermion. BV is the more invariant framework.

**A local gauge condition solves the global quotient.** It usually does not. Perturbative gauge fixing is local in field space; global Gribov and boundary effects require extra analysis.

**Gauge-parameter independence applies to every Green function.** Gauge-dependent Green functions and unphysical field components can depend on $\alpha$. The independence statement applies to physical cohomology classes under the hypotheses of the formalism.

## Relations to other pages

[Observables as Cohomology](/rigorous-qft/bv-brst-gauge-theory/observables-as-cohomology/) explains which quantities are expected to be independent of gauge fixing. [Quantum Master Equation](/rigorous-qft/bv-brst-gauge-theory/quantum-master-equation/) explains the measure-compatibility condition behind finite-dimensional BV gauge independence. [Ghosts, Antifields, and Cohomology](/rigorous-qft/bv-brst-gauge-theory/ghosts-antifields-and-cohomology/) explains why the antighost–$b$ pair does not change physical cohomology.

The Perturbative Algebraic QFT chapter supplies the renormalized formal-series setting in which the singular BV Laplacian is replaced by well-defined perturbative structures. The Algebraic QFT and Locally Covariant QFT chapters give complementary ways to speak about observables without relying on a global functional integral.

## Research status

BV gauge fixing is a standard and powerful perturbative tool. Its finite-dimensional geometric content is mathematically clean, and its local QFT versions are central in perturbative gauge theory, deformation theory, and modern formulations of gauge-theoretic field theories.

The main caveat is global and nonperturbative. A gauge-fixing fermion gives a local perturbative slice, not necessarily a global cross-section of the gauge quotient. Non-Abelian gauge theory, boundary charges, reducible symmetries, topological sectors, and nonperturbative path integrals require additional tools.

## Exercises

### Exercise 1: the graph of a gauge-fixing fermion is Lagrangian

In Darboux coordinates $(q^i,p_i)$ with symplectic form $\omega=dp_i\wedge dq^i$, show that the graph $p_i=\partial\Psi/\partial q^i$ is Lagrangian. Then explain the BV analogy.

<details><summary><strong>Solution</strong></summary>

On the graph,

$$
dp_i=\frac{\partial^2\Psi}{\partial q^j\partial q^i}dq^j.
$$

Therefore

$$
\omega\big|_{\mathrm{graph}(d\Psi)}
=
\frac{\partial^2\Psi}{\partial q^j\partial q^i}
dq^j\wedge dq^i.
$$

The coefficient is symmetric in $i,j$, while $dq^j\wedge dq^i$ is antisymmetric. Hence the restriction vanishes. The graph has half the dimension of the cotangent bundle, so it is Lagrangian.

In BV theory, $\Phi^*_A=\delta\Psi/\delta\Phi^A$ is the graded version of the same construction, with the usual parity signs.

</details>

### Exercise 2: recover the ghost operator in Lorenz gauge

For Yang–Mills theory, take $G^a(A)=\partial^\mu A^a_\mu$ and $\delta_\epsilon A^a_\mu=(D_\mu\epsilon)^a$. Compute the linearized change of $G^a$ under a gauge transformation.

<details><summary><strong>Solution</strong></summary>

The variation is

$$
\delta_\epsilon G^a(A)
=
\partial^\mu\delta_\epsilon A^a_\mu
=
\partial^\mu(D_\mu\epsilon)^a.
$$

Thus the Faddeev–Popov operator for this gauge is

$$
M^a{}_b
=
\partial^\mu D_\mu{}^a{}_b.
$$

The corresponding ghost term is, up to sign conventions,

$$
-\int d^dx\,
\bar c_a\,\partial^\mu D_\mu{}^a{}_b\,c^b.
$$

This is exactly the ghost term produced by the BV gauge-fixing fermion for Lorenz gauge.

</details>

### Exercise 3: why physical observables should not depend on the gauge fermion

In the finite-dimensional BV model, suppose $\mathcal O e^{iS/\hbar}$ is $\Delta$-closed. Explain why a small deformation of the Lagrangian submanifold should not change $\int_{\mathcal L}\mathcal O e^{iS/\hbar}$.

<details><summary><strong>Solution</strong></summary>

A small deformation of $\mathcal L$ sweeps out a thin region $B$ in the BV field space. The difference of the two integrals is the integral over the boundary of $B$:

$$
\int_{\mathcal L_1}\mathcal O e^{iS/\hbar}
-
\int_{\mathcal L_0}\mathcal O e^{iS/\hbar}.
$$

BV Stokes's theorem identifies this boundary integral with the integral of $\Delta(\mathcal O e^{iS/\hbar})$ over $B$. If

$$
\Delta(\mathcal O e^{iS/\hbar})=0,
$$

then the difference vanishes, assuming the usual compactness or decay conditions. In local QFT this is a formal model for the corresponding renormalized Ward identity.

</details>

## References

### Standard references

- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* **25** (1967), 29–30. [doi:10.1016/0370-2693(67)90067-6](https://doi.org/10.1016/0370-2693(67)90067-6).
- I. A. Batalin and G. A. Vilkovisky, “Gauge Algebra and Quantization,” *Physics Letters B* **102** (1981), 27–31. [doi:10.1016/0370-2693(81)90205-7](https://doi.org/10.1016/0370-2693(81)90205-7).
- I. A. Batalin and G. A. Vilkovisky, “Quantization of Gauge Theories with Linearly Dependent Generators,” *Physical Review D* **28** (1983), 2567–2582. [doi:10.1103/PhysRevD.28.2567](https://doi.org/10.1103/PhysRevD.28.2567).
- A. Schwarz, “Geometry of Batalin–Vilkovisky Quantization,” *Communications in Mathematical Physics* **155** (1993), 249–260. [arXiv:hep-th/9205088](https://arxiv.org/abs/hep-th/9205088), [doi:10.1007/BF02097392](https://doi.org/10.1007/BF02097392).
- J. Gomis, J. París, and S. Samuel, “Antibracket, Antifields and Gauge-Theory Quantization,” *Physics Reports* **259** (1995), 1–145. [arXiv:hep-th/9412228](https://arxiv.org/abs/hep-th/9412228), [doi:10.1016/0370-1573(94)00112-G](https://doi.org/10.1016/0370-1573(94)00112-G).

### Global and perturbative-QFT references

- V. N. Gribov, “Quantization of Non-Abelian Gauge Theories,” *Nuclear Physics B* **139** (1978), 1–19. [doi:10.1016/0550-3213(78)90175-X](https://doi.org/10.1016/0550-3213(78)90175-X).
- I. M. Singer, “Some Remarks on the Gribov Ambiguity,” *Communications in Mathematical Physics* **60** (1978), 7–12. [doi:10.1007/BF01609471](https://doi.org/10.1007/BF01609471).
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*, Princeton University Press, 1992. [doi:10.1515/9780691213866](https://doi.org/10.1515/9780691213866).
- K. Fredenhagen and K. Rejzner, “Batalin–Vilkovisky Formalism in Perturbative Algebraic Quantum Field Theory,” *Communications in Mathematical Physics* **317** (2013), 697–725. [arXiv:1110.5232](https://arxiv.org/abs/1110.5232), [doi:10.1007/s00220-012-1601-1](https://doi.org/10.1007/s00220-012-1601-1).

## Version history

- **2026-07-01:** Initial polished draft.
