---
title: "Constraints"
description: "Primary and secondary constraints, first-class and second-class constraints, gauge redundancy, Dirac brackets, degree-of-freedom counting, and the Maxwell/Proca contrast."
sidebar:
  label: "Constraints"
  order: 6
level: Graduate
status: "Polished draft"
topics:
  - constraints
  - Hamiltonian field theory
  - gauge redundancy
  - Dirac brackets
  - Maxwell theory
  - Proca theory
canonicalTopics:
  - constrained-Hamiltonian-systems
  - first-class-constraints
  - second-class-constraints
  - gauge-redundancy
  - Dirac-bracket
---

## Summary

A **constraint** is a relation among canonical variables that must hold on the physical phase space. Constraints appear when the Legendre map from velocities to momenta is singular: some velocities cannot be solved in terms of fields and momenta.

For fields on an equal-time slice,

$$
\phi^A(t,\mathbf x),\qquad \pi_A(t,\mathbf x),
$$

a constraint is written schematically as

$$
\chi_a(\phi,\pi)\approx 0.
$$

The symbol $\approx$ means **weak equality**: impose the relation on the constraint surface, but do not set it to zero before taking Poisson brackets.

The two classifications you should remember are:

| Type | What it means | What it does |
|---|---|---|
| primary | comes directly from the definition of the momenta | signals a singular Legendre map |
| secondary | comes from preserving earlier constraints in time | often gives Gauss-law-type equations |
| first class | has weakly vanishing Poisson brackets with all constraints | generates gauge redundancy, after the right combination is formed |
| second class | has an invertible constraint-bracket matrix | removes variables and requires Dirac brackets |

For $N$ configuration variables, $F$ first-class constraints, and $S$ second-class constraints, the number of physical configuration-space degrees of freedom is

$$
\boxed{N_{\rm phys}=N-F-\frac{S}{2}.}
$$

Maxwell theory has two physical photon polarizations. Proca theory has three physical massive-vector polarizations. The difference is not a detail of notation; it is a difference in constraint structure.

## What to know before reading

Read [Hamiltonian Field Theory](/foundations/classical-field-theory/hamiltonian-field-theory/) first. You should be comfortable with canonical momenta, Hamiltonian density, functional derivatives, and equal-time Poisson brackets. The action principle in [Fields, Actions, and Equations](/foundations/classical-field-theory/fields-actions-equations/) and the current/charge viewpoint in [Noether's Theorem](/foundations/classical-field-theory/noether-theorem/) are also useful.

We use the qft.org conventions from [Conventions and Normalizations](/foundations/conventions-and-normalizations/):

$$
\eta_{\mu\nu}=\operatorname{diag}(+1,-1,-1,-1),
\qquad \hbar=c=1.
$$

:::note[Scope]
This is a first pass through classical bosonic constraints. Fermions require graded brackets. Gauge theories with boundaries require extra care, because some transformations that look like gauge redundancy in the bulk become physical symmetries with boundary charges.
:::

## Core idea

In an unconstrained theory, the canonical variables are independent coordinates on phase space:

$$
\phi^A(\mathbf x),\qquad \pi_A(\mathbf x).
$$

In a constrained theory, they are not. The physical configurations lie on a constraint surface

$$
C=\{(\phi,\pi):\chi_a(\phi,\pi)=0\}.
$$

In gauge theories, even this surface is too large. Points connected by gauge transformations describe the same physical state, so the physical phase space is closer to

$$
\boxed{\Gamma_{\rm phys}=C/\text{gauge orbits}.}
$$

This is the clean Hamiltonian version of the slogan:

$$
\text{global symmetry relates states,}\qquad
\text{gauge symmetry relates descriptions.}
$$

That one sentence prevents a lot of future pain.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Constraint surface, gauge orbits, and reduced phase space](/figures/foundations/constraint-surface-gauge-orbits.svg)

<figcaption>

Constraints restrict the full phase space to a surface. First-class constraints generate gauge orbits on that surface; the physical phase space identifies points on the same orbit. Second-class constraints instead remove directions and replace Poisson brackets by Dirac brackets.

</figcaption>
</figure>

## Weak equality

Dirac's notation separates identities from relations valid only after imposing constraints:

$$
\chi_a\approx 0.
$$

The rule is simple:

$$
\boxed{\text{compute Poisson brackets first, impose constraints second.}}
$$

For example, from $\chi\approx0$ one must not conclude that

$$
\{\chi,F\}=0.
$$

The bracket may be nonzero before restriction to the constraint surface. Those brackets are exactly what decide whether a constraint generates gauge redundancy, fixes a Lagrange multiplier, or changes the bracket structure.

Use

$$
=
$$

for identities on the full phase space and

$$
\approx
$$

for equations that hold only on the constraint surface.

## Singular Legendre maps

Start from a Lagrangian density

$$
\mathcal L=\mathcal L(\phi^A,\dot\phi^A,\partial_i\phi^A)
$$

and define

$$
\pi_A=\frac{\partial\mathcal L}{\partial\dot\phi^A}.
$$

The Legendre map is locally invertible when the velocity Hessian

$$
W_{AB}=\frac{\partial^2\mathcal L}{\partial\dot\phi^A\partial\dot\phi^B}
$$

is nonsingular. If $W$ has zero directions, some velocities do not appear independently in the momenta. The definitions of the momenta then produce primary constraints.

Maxwell theory gives the standard first warning. With

$$
\mathcal L=-\frac14F_{\mu\nu}F^{\mu\nu},
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu,
$$

the velocity $\dot A_0$ does not appear. Therefore

$$
\boxed{\pi^0=\frac{\partial\mathcal L}{\partial\dot A_0}=0}
$$

is a primary constraint. It is not an equation of motion. It is a statement about which canonical variables are really independent.

## The Dirac algorithm

The constrained Hamiltonian procedure is a bookkeeping algorithm.

Start with the primary constraints

$$
\phi_a\approx0.
$$

Construct the canonical Hamiltonian $H_C$ by Legendre transforming as far as possible. Add the primary constraints with arbitrary multipliers:

$$
\boxed{
H_T=H_C+\int d^3\mathbf x\,u^a(\mathbf x)\phi_a(\mathbf x).
}
$$

This is the **total Hamiltonian**. Now demand that the primary constraints remain true in time:

$$
\dot\phi_a(\mathbf x)=\{\phi_a(\mathbf x),H_T\}\approx0.
$$

This condition may:

1. be automatically satisfied;
2. determine some multiplier $u^a$;
3. produce a new constraint.

New constraints produced by time preservation are secondary constraints. Repeat the process until no new constraints appear.

The labels primary and secondary record **how** constraints were found. The deeper classification is first class versus second class.

## First-class and second-class constraints

Let the complete set of constraints be

$$
\chi_a\approx0.
$$

A constraint is **first class** if its Poisson bracket with every constraint vanishes weakly:

$$
\{\chi_a,\chi_b\}\approx0
\qquad\text{for all }b.
$$

First-class constraints are associated with gauge redundancy. In actual gauge theories the generator of a gauge transformation is often a tuned combination of first-class constraints, sometimes with time derivatives of the gauge parameter.

A set of constraints is **second class** when the constraint-bracket matrix

$$
C_{ab}(\mathbf x,\mathbf y)=\{\chi_a(\mathbf x),\chi_b(\mathbf y)\}
$$

is invertible on the constraint surface. Second-class constraints do not generate gauge redundancy; they remove variables and change the canonical bracket.

| Constraint type | Geometric role | What to do before quantizing |
|---|---|---|
| first class | tangent to gauge orbits | quotient by gauge or fix gauge |
| second class | cuts down phase space | replace Poisson brackets by Dirac brackets |

## Dirac brackets

For second-class constraints, the original Poisson bracket is not the physical bracket. If $C_{ab}$ is invertible, let $C^{ab}$ denote the inverse kernel:

$$
\int d^3\mathbf z\,
C_{ac}(\mathbf x,\mathbf z)C^{cb}(\mathbf z,\mathbf y)
=\delta_a{}^b\delta^{(3)}(\mathbf x-\mathbf y).
$$

The Dirac bracket is

$$
\boxed{
\{F,G\}_D
=\{F,G\}
-\int d^3\mathbf x\,d^3\mathbf y\,
\{F,\chi_a(\mathbf x)\}C^{ab}(\mathbf x,\mathbf y)
\{\chi_b(\mathbf y),G\}.
}
$$

Its defining virtue is

$$
\{F,\chi_a\}_D=0
$$

for every $F$. After switching to the Dirac bracket, second-class constraints can be imposed strongly:

$$
\chi_a=0.
$$

Canonical quantization of a second-class system uses the Dirac bracket, not the naive Poisson bracket:

$$
\{F,G\}_D\quad\longrightarrow\quad \frac1i[\widehat F,\widehat G].
$$

## Counting degrees of freedom

For a finite-dimensional system with $N$ configuration variables, the unconstrained phase space has dimension $2N$. Each second-class constraint removes one phase-space dimension. Each first-class constraint removes two: one from the constraint itself and one from quotienting by the corresponding gauge direction.

Therefore

$$
\dim\Gamma_{\rm phys}=2N-S-2F,
$$

and hence

$$
\boxed{N_{\rm phys}=N-F-\frac S2.}
$$

For fields, apply the count per spatial point or per momentum mode, with the usual warnings about boundaries, zero modes, and global constraints.

| Theory | Configuration variables | First class | Second class | Physical degrees of freedom |
|---|---:|---:|---:|---:|
| Maxwell field | $A_\mu$: 4 | 2 | 0 | 2 |
| Proca field | $A_\mu$: 4 | 0 | 2 | 3 |

The photon has two polarizations. A massive spin-one particle has three. This is why the massless limit of a massive vector field is structurally delicate.

## Example: Proca field

The massive vector field has

$$
\mathcal L_{\rm Proca}
=-\frac14F_{\mu\nu}F^{\mu\nu}
+\frac12m^2A_\mu A^\mu-J_\mu A^\mu.
$$

Using $A_\mu$ as the canonical field,

$$
\pi^0=0,
\qquad
\pi^i=F^{i0}.
$$

Thus

$$
\chi_1\equiv\pi^0\approx0
$$

is primary. The field equation is

$$
\partial_\mu F^{\mu\nu}+m^2A^\nu=J^\nu.
$$

Its $\nu=0$ component gives the secondary constraint

$$
\chi_2\equiv\partial_i\pi^i+m^2A^0-J^0\approx0.
$$

The bracket

$$
\{\pi^0(\mathbf x),\chi_2(\mathbf y)\}
=-m^2\delta^{(3)}(\mathbf x-\mathbf y)
$$

is invertible for $m\neq0$, so these constraints are second class. The count is

$$
N_{\rm phys}=4-0-\frac22=3.
$$

The longitudinal polarization is physical.

## Example: Maxwell theory

Now set $m=0$:

$$
\mathcal L_{\rm Maxwell}=-\frac14F_{\mu\nu}F^{\mu\nu}-J_\mu A^\mu.
$$

Again,

$$
\pi^0\approx0.
$$

Time preservation gives Gauss's law:

$$
\Gamma\equiv\partial_i\pi^i-J^0\approx0.
$$

For a conserved external current, no further constraint is produced. The constraint brackets vanish weakly, so the two constraints are first class. The degree-of-freedom count is

$$
N_{\rm phys}=4-2=2.
$$

The gauge transformation is generated by a specific combination of the first-class constraints:

$$
G[\alpha]=\int d^3\mathbf x\,
\left(\dot\alpha\,\pi^0-\alpha\,\Gamma\right).
$$

Using canonical brackets,

$$
\{A_0,G[\alpha]\}=\dot\alpha,
\qquad
\{A_i,G[\alpha]\}=\partial_i\alpha.
$$

Thus

$$
\boxed{\delta A_\mu=\partial_\mu\alpha.}
$$

The field strength is unchanged. The potentials have more variables than the physical electromagnetic field.

## Gauge fixing

A first-class system has redundant coordinates. To quantize it directly, one commonly adds gauge-fixing conditions

$$
G_a\approx0
$$

so that each gauge orbit is represented once, at least locally. The combined set

$$
\chi_a\approx0,
\qquad
G_a\approx0
$$

is then second class, and one can use Dirac brackets or the equivalent path-integral determinant.

For Maxwell theory:

| Gauge condition | Comment |
|---|---|
| $A_0=0$ | temporal gauge; leaves residual gauge freedom |
| $\partial_iA_i=0$ | Coulomb gauge; makes transverse photons manifest |
| $\partial_\mu A^\mu=0$ | Lorenz gauge; covariant, naturally handled with indefinite metric or BRST methods |

Gauge fixing is a coordinate choice on the space of physical configurations. Bad gauges can miss configurations, intersect an orbit more than once, or leave residual gauge freedom. In non-Abelian gauge theory this becomes the Gribov problem.

## Path-integral viewpoint

The phase-space path integral for an unconstrained system is schematically

$$
Z=\int\mathcal Dq\,\mathcal Dp\,
\exp\left[i\int dt\,(p_I\dot q^I-H)\right].
$$

For constrained systems, the integral is not over the naive phase space. Second-class constraints contribute delta functions and a determinant. First-class constraints require division by gauge volume, usually implemented by gauge fixing and a Faddeev–Popov determinant.

This is why ghosts and determinants are not aesthetic decorations. They are the path-integral translation of a Hamiltonian fact: the naive variables overcount physical configurations.

## Boundary charges and edge modes

Gauss's law is a bulk constraint, but boundaries can turn part of a gauge transformation into a physical symmetry. For electromagnetism on a region $\Sigma$,

$$
\Gamma[\alpha]=\int_\Sigma d^3\mathbf x\,\alpha(\partial_i\pi^i-J^0).
$$

Integrating by parts gives

$$
\Gamma[\alpha]
=-\int_\Sigma d^3\mathbf x\,(\partial_i\alpha)\pi^i
+\int_{\partial\Sigma}dS_i\,\alpha\pi^i
-\int_\Sigma d^3\mathbf x\,\alpha J^0.
$$

If $\alpha$ vanishes at the boundary, the surface term is absent. If $\alpha$ approaches a nonzero value at infinity, the surface term can be a physical charge. This is the seed of asymptotic symmetries, edge modes, and the modern boundary-sensitive view of gauge theory.

## What this page is not doing

This page is intentionally not a full course in constrained quantization. It does not develop the general theorem relating first-class constraints to gauge transformations, the Castellani construction, BRST cohomology, BV quantization, Gribov regions, chiral bosons, or the gravitational constraint algebra.

The goal here is humbler and more useful: make the first encounter with constraints clean enough that gauge theory no longer feels like arbitrary rule patching.

## Common pitfalls

### Setting constraints to zero too early

Weak equality means constraints are imposed after Poisson brackets are computed. Setting them to zero too soon erases the information needed to classify them.

### Thinking all constraints are gauge constraints

Second-class constraints do not generate gauge redundancy. They remove variables and require Dirac brackets. Proca theory is the standard warning.

### Counting fields instead of physical degrees of freedom

The four components of $A_\mu$ are not four photon polarizations. Constraints and gauge redundancy reduce Maxwell theory to two physical modes.

### Treating gauge fixing as new physics

A gauge condition is a choice of representative on each gauge orbit, not a new law of nature.

### Ignoring boundaries

Gauge transformations that vanish at the boundary are usually redundancies. Transformations with nontrivial boundary behavior can carry physical charges.

## Relation to nearby pages

- [Hamiltonian Field Theory](/foundations/classical-field-theory/hamiltonian-field-theory/) explains the regular Legendre transform and canonical Poisson brackets.
- [Stress Tensor](/foundations/classical-field-theory/stress-tensor/) identifies the Hamiltonian and momentum as spacetime-translation charges.
- [Linearization and Normal Modes](/foundations/classical-field-theory/linearization-and-normal-modes/) explains how unconstrained quadratic systems decompose into oscillators.
- [Gauge Redundancy](/foundations/gauge-fields-first-principles/gauge-redundancy/) revisits first-class constraints from the conceptual side of gauge theory.
- [Maxwell as Gauge Theory](/foundations/gauge-fields-first-principles/maxwell-as-gauge-theory/) applies Gauss's law and gauge fixing to electromagnetism.
- [Canonical Commutation Relations](/foundations/canonical-quantization/canonical-commutation-relations/) explains how Poisson brackets become quantum commutators.
- [Gauge Fixing Preview](/foundations/gauge-fields-first-principles/gauge-fixing-preview/) connects constraints to Faddeev–Popov and BRST language.

## Research status

- **Established:** Primary constraints, secondary constraints, first-class and second-class constraints, Dirac brackets, degree-of-freedom counting, Maxwell theory, and Proca theory are textbook-standard.
- **Active:** Boundaries, asymptotic symmetries, edge modes, non-Abelian gauge copies, gravitational constraints, anomalies, and global phase-space structure remain active in modern research.
- **Speculative:** None at the level of this page. Speculation enters in particular applications or proposed fundamental theories.

## Exercises

### Exercise 1: Singular Legendre map

Consider the mechanical Lagrangian

$$
L(q_1,q_2,\dot q_1,\dot q_2)=\frac12(\dot q_1-q_2)^2.
$$

Find the canonical momenta and identify the primary constraint.

<details>
<summary><strong>Solution</strong></summary>

The momenta are

$$
p_1=\frac{\partial L}{\partial\dot q_1}=\dot q_1-q_2,
\qquad
p_2=\frac{\partial L}{\partial\dot q_2}=0.
$$

Thus

$$
\boxed{p_2\approx0}
$$

is a primary constraint. The velocity $\dot q_2$ does not appear in the Lagrangian.

</details>

### Exercise 2: Maxwell primary constraint

For

$$
\mathcal L=-\frac14F_{\mu\nu}F^{\mu\nu},
$$

show that the momentum conjugate to $A_0$ vanishes.

<details>
<summary><strong>Solution</strong></summary>

The field strength components containing time derivatives are

$$
F_{0i}=\dot A_i-\partial_iA_0.
$$

They contain $\dot A_i$ but not $\dot A_0$. The purely spatial components $F_{ij}$ also contain no $\dot A_0$. Therefore

$$
\boxed{\pi^0=\frac{\partial\mathcal L}{\partial\dot A_0}=0.}
$$

</details>

### Exercise 3: Degree-of-freedom counts

Use

$$
N_{\rm phys}=N-F-\frac S2
$$

to count physical degrees of freedom for Proca theory and Maxwell theory.

<details>
<summary><strong>Solution</strong></summary>

For Proca theory, $N=4$, $F=0$, and $S=2$, so

$$
N_{\rm phys}=4-0-\frac22=3.
$$

For Maxwell theory, $N=4$, $F=2$, and $S=0$, so

$$
N_{\rm phys}=4-2=2.
$$

</details>

### Exercise 4: Dirac bracket kills second-class constraints

Let $\chi_a$ be second-class constraints with invertible matrix $C_{ab}=\{\chi_a,\chi_b\}$. Show that

$$
\{F,\chi_c\}_D=0.
$$

<details>
<summary><strong>Solution</strong></summary>

Using the Dirac bracket,

$$
\{F,\chi_c\}_D
=\{F,\chi_c\}-\{F,\chi_a\}C^{ab}\{\chi_b,\chi_c\}.
$$

Since $\{\chi_b,\chi_c\}=C_{bc}$ and $C^{ab}C_{bc}=\delta^a{}_c$,

$$
\{F,\chi_c\}_D
=\{F,\chi_c\}-\{F,\chi_a\}\delta^a{}_c=0.
$$

</details>

### Exercise 5: Gauge generator for Maxwell theory

Take

$$
G[\alpha]=\int d^3\mathbf x\,(\dot\alpha\,\pi^0-\alpha\,\Gamma),
\qquad
\Gamma=\partial_i\pi^i-J^0.
$$

Using

$$
\{A_\mu(\mathbf x),\pi^\nu(\mathbf y)\}=\delta_\mu{}^\nu\delta^{(3)}(\mathbf x-\mathbf y),
$$

show that $G[\alpha]$ generates $\delta A_\mu=\partial_\mu\alpha$.

<details>
<summary><strong>Solution</strong></summary>

For the time component,

$$
\delta A_0(\mathbf x)=\{A_0(\mathbf x),G[\alpha]\}=\dot\alpha(\mathbf x).
$$

For the spatial component,

$$
\delta A_i(\mathbf x)
=-\int d^3\mathbf y\,\alpha(\mathbf y)
\{A_i(\mathbf x),\partial_j\pi^j(\mathbf y)\}.
$$

Since

$$
\{A_i(\mathbf x),\partial_j\pi^j(\mathbf y)\}=\partial_{y^i}\delta^{(3)}(\mathbf x-\mathbf y),
$$

integration by parts gives

$$
\delta A_i(\mathbf x)=\partial_i\alpha(\mathbf x).
$$

Thus $\delta A_\mu=\partial_\mu\alpha$.

</details>

## References

### Primary references

- P. A. M. Dirac, "Generalized Hamiltonian Dynamics," *Canadian Journal of Mathematics* **2** (1950), 129–148.
- P. A. M. Dirac, *Lectures on Quantum Mechanics*, Belfer Graduate School of Science, Yeshiva University (1964).
- L. D. Faddeev and V. N. Popov, "Feynman Diagrams for the Yang–Mills Field," *Physics Letters B* **25** (1967), 29–30.

### Standard textbook treatments

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §7.6, for constraints and Dirac brackets.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 26 for the vector-field example and ch. 31 for Faddeev–Popov gauge fixing.
- M. Srednicki, *Quantum Field Theory*, §§54–57, for Maxwell theory, Coulomb gauge, and photon quantization.
- A. Zee, *Quantum Field Theory in a Nutshell*, 2nd ed., Parts I.5 and III.4, for a physics-first view of vector fields and gauge invariance.

### For mathematical precision

- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*, Princeton University Press (1992).
- A. Hanson, T. Regge, and C. Teitelboim, *Constrained Hamiltonian Systems*, Accademia Nazionale dei Lincei (1976).
- D. M. Gitman and I. V. Tyutin, *Quantization of Fields with Constraints*, Springer (1990).

## Version history

- **2026-06-08:** Revised for the Classical Field Theory chapter index pass: tightened the reader path, reduced repeated motivation, clarified weak equality, separated first-class and second-class roles, and made the Maxwell/Proca contrast more explicit.
- **2026-05-22:** Initial qft.org page on constraints, Dirac brackets, gauge redundancy, Maxwell theory, Proca theory, and degree-of-freedom counting.
