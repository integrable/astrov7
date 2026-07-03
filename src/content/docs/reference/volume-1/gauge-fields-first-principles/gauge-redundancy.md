---
title: "Gauge Redundancy"
description: "Gauge symmetry as redundancy rather than an ordinary physical symmetry: gauge orbits, gauge-invariant observables, constraints, gauge fixing, and the boundary between redundancy and global charge."
sidebar:
  label: "Gauge Redundancy"
  order: 1
---

## Summary

A **gauge symmetry** is not an ordinary symmetry between physically distinct states. It is a redundancy in the variables used to describe a physical system. The physical configuration is not one field configuration, but an equivalence class of field configurations:

$$
\boxed{\text{physical configuration}=\frac{\text{field configurations}}{\text{gauge transformations}}.}
$$

For the Abelian gauge field of electromagnetism,

$$
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x),
$$

and the field strength

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu
$$

is unchanged. If a charged field has charge $q$, with qft.org's default convention

$$
D_\mu=\partial_\mu+iqA_\mu,
$$

the combined transformation

$$
\Phi(x)\mapsto e^{-iq\alpha(x)}\Phi(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x)
$$

makes the covariant derivative transform as

$$
D_\mu\Phi\mapsto e^{-iq\alpha(x)}D_\mu\Phi.
$$

That is the local-gauge mechanism in its smallest form: the derivative of a charged field fails to transform covariantly, and the gauge potential supplies the compensating term. Coleman stresses the conceptual point sharply: gauge invariance is not a physical symmetry like isospin; Lorenz gauge, Coulomb gauge, and other gauges are different descriptions of the same electromagnetic field configuration, not different experimentally testable systems (Coleman 2019, ch. 27). Srednicki's path-integral treatment makes the same point in another language: if an action is constant along redundant directions, the functional integral over all fields overcounts gauge-equivalent configurations and must be gauge-fixed or divided by the gauge volume (Srednicki 2007, §§57 and 71). Weinberg's massless spin-one analysis explains why this redundancy is not optional: a Lorentz-covariant description of helicity-one particles requires gauge freedom in the potential (Weinberg 1995, Vol. I, §§5.9 and 8.1).

<figure class="doc-figure" style="--figure-width: 49rem;">

![Gauge orbits, representatives, and gauge-invariant observables](/figures/foundations/gauge-redundancy-orbits.svg)

<figcaption>

Gauge-related field configurations lie on the same orbit in configuration space. A gauge condition chooses one representative from each orbit, while a genuine observable is constant along each orbit. Quantization must avoid counting all points on an orbit as distinct physical states.

</figcaption>
</figure>

## Prerequisites

You should know [Constraints](/foundations/classical-field-theory/constraints/), [Maxwell Field](/foundations/free-fields/maxwell-field/), [Internal Symmetries](/foundations/symmetry-and-spacetime/internal-symmetries/), [Currents and Charges](/foundations/symmetry-and-spacetime/currents-and-charges/), [Ward Identities](/foundations/symmetry-and-spacetime/ward-identities/), and [Path Integral Measure](/foundations/path-integral-formalism/path-integral-measure/).

:::note[Conventions]
For Abelian gauge theory, qft.org uses

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\Phi\mapsto e^{-iq\alpha}\Phi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

Then $D_\mu\Phi$ transforms like $\Phi$:

$$
D_\mu\Phi\mapsto e^{-iq\alpha}D_\mu\Phi.
$$

Some books use $D_\mu=\partial_\mu-iqA_\mu$ and $A_\mu\mapsto A_\mu-\partial_\mu\alpha$. The physics is the same after the sign convention for charge and $A_\mu$ is changed consistently.
:::

:::note[Assumptions]
This page is about ordinary local gauge redundancy in flat-spacetime QFT. Boundary charges, large gauge transformations, Wilson lines, ghosts, BRST cohomology, topological sectors, and generalized symmetries are only previewed. They become central later.
:::

## The core distinction

A global symmetry acts on physical states. A gauge transformation changes the description.

A global internal symmetry might rotate two fields into one another:

$$
\Phi_i(x)\mapsto D_i{}^j(g)\Phi_j(x),
\qquad g\in G,
$$

with the same group element at every spacetime point. If the symmetry is exact, it gives a conserved charge. The transformed state is usually a different physical state with the same energy or scattering probabilities.

A gauge transformation is different. It may look mathematically similar,

$$
\Phi(x)\mapsto e^{-iq\alpha(x)}\Phi(x),
$$

but the local function $\alpha(x)$ is not labeling a family of new physical systems. It is labeling different representatives of the same physical configuration, provided it is a small gauge transformation compatible with the boundary conditions.

A good slogan is:

$$
\boxed{\text{global symmetry moves you in physical state space; gauge redundancy moves you within a description.}}
$$

This distinction prevents a common mistake. Gauge invariance is often called a “local symmetry,” and that language is deeply entrenched. But it is safer to remember that the local part is redundancy. Only transformations that survive as nontrivial actions at boundaries, or global transformations acting on charged sectors, become physical symmetries with charges.

## Gauge orbits

Let $\mathcal C$ be the space of all field configurations. A gauge group $\mathcal G$ acts on $\mathcal C$. For a configuration $\varphi\in\mathcal C$, its **gauge orbit** is

$$
\mathcal O_\varphi=\{\varphi^g:g\in\mathcal G\}.
$$

The physical configuration is the orbit $\mathcal O_\varphi$, not a chosen point on it.

For electromagnetism, the orbit through $A_\mu$ is

$$
\mathcal O_A=\{A_\mu+\partial_\mu\alpha: \alpha \text{ allowed}\}.
$$

The field strength is constant along this orbit:

$$
F_{\mu\nu}[A+\partial\alpha]=F_{\mu\nu}[A].
$$

So $F_{\mu\nu}$ descends from the space of potentials to the quotient space of gauge orbits.

A **gauge-invariant observable** $\mathcal O$ is one satisfying

$$
\mathcal O[\varphi^g]=\mathcal O[\varphi].
$$

Equivalently, it is constant along gauge orbits. This is the gauge-theory analog of a function on the quotient.

## Gauge fixing

A **gauge condition** chooses a representative from each orbit, at least locally. Examples in electromagnetism include

$$
\partial_\mu A^\mu=0
\qquad\text{(Lorenz gauge)},
$$

and

$$
\nabla\cdot\mathbf A=0
\qquad\text{(Coulomb gauge)}.
$$

These conditions are not new laws of nature. They are coordinate choices on field space.

The analogy with coordinates is useful but not perfect. A good coordinate chart intersects each physical point once. A gauge condition tries to intersect each gauge orbit once. It may fail globally, or intersect the same orbit more than once. In non-Abelian gauge theory this becomes the Gribov problem. In this foundations group, the important first lesson is simpler: gauge fixing is required because otherwise one is counting infinitely many descriptions of the same physical configuration.

In the path integral, the schematic problem is

$$
\int \mathcal D A\,e^{iS[A]}
=\left(\text{gauge-group volume}\right)
\int \frac{\mathcal D A}{\mathcal G}\,e^{iS[A]}.
$$

The gauge-group volume is usually infinite. Perturbative quantization replaces the quotient by a gauge-fixing procedure. Schematically,

$$
\int \mathcal D A\,e^{iS[A]}
\quad\leadsto\quad
\int \mathcal D A\,\delta(G[A])\,\Delta_\text{FP}[A]e^{iS[A]},
$$

where $G[A]=0$ is the gauge condition and $\Delta_\text{FP}$ is the Faddeev–Popov determinant. For Abelian free electromagnetism, this determinant is simple. For non-Abelian gauge theory it becomes dynamical ghost fields.

That is the path-integral face of redundancy.

## The Hamiltonian face

Gauge redundancy also appears in Hamiltonian field theory as constraints.

In Maxwell theory,

$$
\mathcal L=-\frac14F_{\mu\nu}F^{\mu\nu}-j_\mu A^\mu,
$$

the time derivative of $A_0$ does not appear. Therefore the canonical momentum conjugate to $A_0$ vanishes:

$$
\Pi^0=0.
$$

This is a primary constraint. Consistency of the time evolution gives Gauss's law,

$$
\nabla\cdot\mathbf E=\rho,
$$

or, in constraint language,

$$
\mathcal G(\mathbf x)=\partial_iE^i(\mathbf x)-\rho(\mathbf x)\approx0.
$$

The symbol $\approx0$ means the expression vanishes on the physical constraint surface. The constraint generates gauge transformations. For a smearing function $\alpha(\mathbf x)$ that vanishes appropriately at the boundary, the generator

$$
G[\alpha]=\int d^3\mathbf x\,\alpha(\mathbf x)\bigl(\partial_iE^i-\rho\bigr)
$$

acts as

$$
\delta_\alpha A_i=\partial_i\alpha,
\qquad
\delta_\alpha\Phi=-iq\alpha\Phi.
$$

So the canonical statement is:

$$
\boxed{\text{gauge transformations are generated by constraints, not by ordinary physical charges.}}
$$

This statement needs a boundary caveat. If $\alpha$ does not vanish at infinity, then integrations by parts can leave a surface term. That surface term is the global charge measured at infinity. In QED, the global electric charge is real physics. The local gauge transformations that die off at the boundary are redundancy.

## Why gauge redundancy is useful

If gauge transformations are redundant, why introduce them at all? Because they allow a local, Lorentz-covariant description of particles and interactions that would otherwise be hard or impossible to write.

The photon is the clean example. A massless spin-one particle has two physical helicities, but a Lorentz vector $A_\mu$ has four components. Gauge redundancy lets us use the Lorentz-covariant field $A_\mu$ while removing the extra descriptive components. Weinberg's construction of massless helicity-one fields shows that a four-vector potential does not transform as an honest four-vector under Lorentz transformations; it transforms as a four-vector plus a gauge transformation. The field strength $F_{\mu\nu}$ is the honest tensor.

Gauge redundancy also makes locality manageable. The electric and magnetic fields are gauge invariant, but coupling to charged matter is most simply written through the potential:

$$
D_\mu\Phi=(\partial_\mu+iqA_\mu)\Phi.
$$

The potential is not directly gauge invariant, but it is the local connection that tells nearby charged fields how to compare their phases. That is the geometric content hiding inside the elementary formula.

## Gauge-invariant versus gauge-covariant

A quantity can transform nicely without being invariant.

For the Abelian charged scalar,

$$
\Phi\mapsto e^{-iq\alpha}\Phi
$$

is not gauge invariant. The covariant derivative satisfies

$$
D_\mu\Phi\mapsto e^{-iq\alpha}D_\mu\Phi.
$$

So $D_\mu\Phi$ is **gauge-covariant**. It transforms like the field itself. From covariant objects one can build invariant local terms, for example

$$
(D_\mu\Phi)^\dagger D^\mu\Phi,
\qquad
\Phi^\dagger\Phi,
\qquad
F_{\mu\nu}F^{\mu\nu}.
$$

This distinction is everywhere in gauge theory:

| Word | Meaning |
| --- | --- |
| invariant | unchanged by gauge transformations |
| covariant | transforms homogeneously in a representation |
| gauge-fixed | written after choosing a representative |
| physical observable | independent of the representative |

Gauge-fixed fields such as $A_\mu$ in Feynman gauge or Coulomb gauge are excellent computational tools. They are not, by themselves, gauge-invariant observables.

## The local symmetry trap

The phrase “local symmetry” invites a dangerous mental picture: one imagines performing a different physical symmetry operation at each point of spacetime. That is not what gauge redundancy means.

An ordinary global symmetry parameter $\alpha$ gives a conserved current by Noether's theorem. If one now replaces $\alpha$ by $\alpha(x)$ and compensates with a gauge field, the local transformation no longer generates an independent local charge density of physical symmetries. Instead, it expresses an identity among equations of motion and constraints. This is Noether's second theorem rather than the ordinary charge-counting form of Noether's first theorem.

For Maxwell theory, local gauge invariance gives the redundancy

$$
A_\mu\sim A_\mu+\partial_\mu\alpha.
$$

The electric charge comes from the global part that survives at spatial infinity, not from treating every $\alpha(x)$ as a new physical symmetry.

This is why Coleman says that gauge invariance is not a symmetry in the same sense as isospin. You do not test gauge invariance by doing the same experiment in Lorenz gauge and Coulomb gauge and comparing cross sections. The gauges were never different experiments.

## Small, large, and boundary gauge transformations

The cleanest first-pass rule is:

$$
\text{gauge transformations that vanish at the boundary are redundancy.}
$$

But real gauge theory has more structure.

A transformation that approaches a nontrivial constant at spatial infinity can act on charged states. In QED, this is how the ordinary global electric charge appears. More generally, boundary conditions can turn some would-be gauge transformations into asymptotic symmetries.

A transformation that cannot be smoothly deformed to the identity may be a **large gauge transformation**. Such transformations can label topological sectors, affect theta angles, and matter in nonperturbative gauge theory.

Thus “gauge equals redundancy” is the right local lesson, but not the whole global story. The more precise statement is:

$$
\boxed{\text{pure gauge directions are redundancy; boundary and topology can carry physical data.}}
$$

## Why this page belongs before Maxwell as gauge theory

It is tempting to start gauge theory by writing $F_{\mu\nu}$ and the Maxwell action. That works technically, but it hides the big conceptual move. Gauge theory is not merely the study of vector fields. It is the study of fields with redundant descriptions, plus rules for extracting the gauge-invariant content.

The next page applies this principle to electromagnetism:

$$
A \longrightarrow F=dA \longrightarrow S[A] \longrightarrow \partial_\mu F^{\mu\nu}=j^\nu.
$$

After that, charged matter, gauge fixing, non-Abelian gauge theory, and BRST will all be refinements of the same idea.

## Common pitfalls

**Pitfall 1: Saying gauge symmetry creates conserved charges just like global symmetry.**  
Local gauge redundancy gives constraints and identities. Physical charges come from global or boundary transformations.

**Pitfall 2: Treating gauge-fixed fields as observables.**  
Gauge-fixed fields are useful variables. Gauge-invariant or properly dressed quantities are the observables.

**Pitfall 3: Thinking a gauge choice changes the physics.**  
A gauge choice changes the representative, not the physical configuration.

**Pitfall 4: Forgetting boundary conditions.**  
The distinction between redundancy and symmetry depends on allowed transformations at the boundary.

**Pitfall 5: Using “gauge invariance” as a magic phrase.**  
Gauge invariance is powerful because it encodes redundancy, locality, Lorentz covariance, constraints, and current conservation. The word alone is not the explanation.

## Exercises

### Exercise 1: Field strength is gauge invariant

For Abelian gauge theory, let

$$
A_\mu' = A_\mu+\partial_\mu\alpha.
$$

Show that $F_{\mu\nu}'=F_{\mu\nu}$.

<details>
<summary><strong>Solution</strong></summary>

Compute

$$
F'_{\mu\nu}
=\partial_\mu A'_\nu-\partial_\nu A'_\mu.
$$

Substitute the transformed potential:

$$
F'_{\mu\nu}
=\partial_\mu(A_\nu+\partial_\nu\alpha)
-\partial_\nu(A_\mu+\partial_\mu\alpha).
$$

Thus

$$
F'_{\mu\nu}
=F_{\mu\nu}
+\partial_\mu\partial_\nu\alpha
-\partial_\nu\partial_\mu\alpha.
$$

Ordinary partial derivatives commute, so the last two terms cancel:

$$
\boxed{F'_{\mu\nu}=F_{\mu\nu}.}
$$

</details>

### Exercise 2: Covariant derivative of a charged scalar

Use

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\Phi'=e^{-iq\alpha}\Phi,
\qquad
A_\mu'=A_\mu+\partial_\mu\alpha.
$$

Show that

$$
D_\mu'\Phi'=e^{-iq\alpha}D_\mu\Phi.
$$

<details>
<summary><strong>Solution</strong></summary>

Start with

$$
D_\mu'\Phi'=(\partial_\mu+iqA_\mu')e^{-iq\alpha}\Phi.
$$

Using the product rule,

$$
\partial_\mu(e^{-iq\alpha}\Phi)
=e^{-iq\alpha}\partial_\mu\Phi-iq(\partial_\mu\alpha)e^{-iq\alpha}\Phi.
$$

The gauge-field term is

$$
iq(A_\mu+\partial_\mu\alpha)e^{-iq\alpha}\Phi.
$$

The $-iq\partial_\mu\alpha$ term from differentiating the phase cancels the $+iq\partial_\mu\alpha$ term from $A_\mu'$. Therefore

$$
D_\mu'\Phi'
=e^{-iq\alpha}(\partial_\mu+iqA_\mu)\Phi
=e^{-iq\alpha}D_\mu\Phi.
$$

</details>

### Exercise 3: Gauge invariance of scalar kinetic terms

Using the result of Exercise 2, show that

$$
(D_\mu\Phi)^\dagger D^\mu\Phi
$$

is gauge invariant.

<details>
<summary><strong>Solution</strong></summary>

The covariant derivative transforms as

$$
D_\mu\Phi\mapsto e^{-iq\alpha}D_\mu\Phi.
$$

Its Hermitian conjugate transforms as

$$
(D_\mu\Phi)^\dagger\mapsto e^{+iq\alpha}(D_\mu\Phi)^\dagger.
$$

Therefore

$$
(D_\mu\Phi)^\dagger D^\mu\Phi
\mapsto
(e^{+iq\alpha}(D_\mu\Phi)^\dagger)(e^{-iq\alpha}D^\mu\Phi)
=(D_\mu\Phi)^\dagger D^\mu\Phi.
$$

</details>

### Exercise 4: Gauge invariance requires current conservation

Let

$$
S_\text{int}=-\int d^4x\,j_\mu A^\mu.
$$

Under $A_\mu\mapsto A_\mu+\partial_\mu\alpha$, show that $S_\text{int}$ is invariant for arbitrary $\alpha$ vanishing at the boundary only if $\partial_\mu j^\mu=0$.

<details>
<summary><strong>Solution</strong></summary>

The variation is

$$
\delta S_\text{int}
=-\int d^4x\,j_\mu\partial^\mu\alpha.
$$

Integrating by parts,

$$
\delta S_\text{int}
=\int d^4x\,(\partial^\mu j_\mu)\alpha
-\int_{\partial M} d\Sigma_\mu\,j^\mu\alpha.
$$

If $\alpha$ vanishes at the boundary, the surface term is zero. For the remaining integral to vanish for arbitrary local $\alpha(x)$, we need

$$
\boxed{\partial_\mu j^\mu=0.}
$$

</details>

### Exercise 5: A finite-dimensional gauge-volume analogy

Consider the integral

$$
Z=\int_{-\infty}^{\infty}dx\,dy\,e^{-S(x)},
$$

where the action does not depend on $y$. Explain why the integral over $y$ is redundant, and write a gauge-fixed version that chooses $y=0$.

<details>
<summary><strong>Solution</strong></summary>

Since $S$ depends only on $x$, all points with the same $x$ and different $y$ have the same weight. The variable $y$ labels redundant descriptions.

The integral factorizes as

$$
Z=\left(\int_{-\infty}^{\infty}dy\right)
\left(\int_{-\infty}^{\infty}dx\,e^{-S(x)}\right).
$$

The first factor is an infinite redundant volume. A gauge-fixed version chooses one point on each redundant line, for example $y=0$:

$$
Z_\text{gf}=\int dx\,dy\,\delta(y)e^{-S(x)}
=\int dx\,e^{-S(x)}.
$$

This is the finite-dimensional shadow of gauge fixing in a path integral.

</details>

### Exercise 6: Boundary charge from Gauss's law

Let

$$
G[\alpha]=\int d^3\mathbf x\,\alpha(\mathbf x)(\partial_iE^i-\rho).
$$

Integrate the first term by parts. What happens if $\alpha$ approaches a constant $\alpha_\infty$ at spatial infinity?

<details>
<summary><strong>Solution</strong></summary>

The first term is

$$
\int d^3\mathbf x\,\alpha\partial_iE^i
=\oint_{S_\infty}dS_i\,\alpha E^i
-\int d^3\mathbf x\,(\partial_i\alpha)E^i.
$$

If $\alpha$ vanishes at infinity, the surface term is zero and $G[\alpha]$ generates a pure gauge redundancy.

If $\alpha\to\alpha_\infty$ at infinity, the surface term becomes

$$
\alpha_\infty\oint_{S_\infty}dS_i\,E^i.
$$

Using Gauss's law, this is

$$
\alpha_\infty Q,
\qquad
Q=\int d^3\mathbf x\,\rho.
$$

Thus a transformation that survives at infinity can measure or generate a physical global charge. Boundary behavior is what distinguishes pure redundancy from a physical asymptotic symmetry.

</details>

## Sources and further reading

- H. Weyl, “Elektron und Gravitation,” *Zeitschrift für Physik* **56** (1929), for the early gauge principle in its modern phase-symmetry form.
- C. N. Yang and R. Mills, “Conservation of Isotopic Spin and Isotopic Gauge Invariance,” *Physical Review* **96** (1954), for the original non-Abelian generalization.
- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* **25** (1967), for the path-integral gauge-fixing determinant.
- M. Srednicki, *Quantum Field Theory*, §§57 and 71, for Abelian and non-Abelian gauge redundancy in the path integral.
- S. Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, ch. 27, for the distinction between gauge invariance and ordinary internal symmetry, and ch. 31 for Faddeev–Popov gauge fixing.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, §§5.9 and 8.1–8.6, for massless spin-one fields, gauge invariance, constraints, and electrodynamics.
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*, for the constrained-Hamiltonian view of gauge theories.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for BRST and gauge fixing in the functional formalism.

## Version history

- **2026-05-23:** Initial qft.org page on gauge redundancy, gauge orbits, gauge-invariant observables, gauge fixing, Hamiltonian constraints, boundary charges, and the global-versus-gauge distinction.
