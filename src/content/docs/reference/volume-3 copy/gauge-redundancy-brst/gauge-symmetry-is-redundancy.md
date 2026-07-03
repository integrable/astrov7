---
title: "Gauge Symmetry Is Redundancy"
description: "Explains why gauge symmetry identifies equivalent descriptions rather than acting as an ordinary physical global symmetry, and how this distinction controls observables, constraints, and gauge fixing."
sidebar:
  label: "Gauge Symmetry Is Redundancy"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki §§69–74; Weinberg Vol. II Ch. 15; Coleman, ‘Secret Symmetry’; Henneaux–Teitelboim on gauge constraints."
topics:
  - gauge redundancy
  - gauge orbit
  - gauge invariant observables
  - Gauss law
  - gauge fixing
  - physical configuration space
canonicalTopics:
  - gauge-redundancy
  - gauge-orbit
  - gauge-invariant-observable
  - gauss-law
  - gauge-fixing
researchStatus:
  established:
    - "Gauge transformations with trivial boundary action are redundancies of description, not ordinary physical symmetries acting on distinct states."
    - "Gauge-invariant observables live on the quotient of field space by gauge orbits, and perturbative gauge fixing is a coordinate choice on that quotient."
  active:
    - "Boundaries, edge modes, large gauge transformations, higher-form symmetries, and nonperturbative gauge fixing refine the simple quotient picture."
---

## Summary

A gauge symmetry is not a physical symmetry in the same sense as baryon number, flavor $SU(N)$, or spatial rotations. A physical global symmetry maps one physical state to another physical state. A gauge transformation, at least when it is trivial at the boundary, maps one description of a physical state to another description of the **same** physical state.

The slogan is:

$$
\text{gauge transformation} = \text{change of coordinates on redundant field space}.
$$

If $\mathcal F$ is the space of fields and $\mathcal G$ is the group of allowed gauge transformations that are treated as redundancies, the physical configuration space is not $\mathcal F$ but roughly

$$
\mathcal F_{\rm phys}\simeq \mathcal F/\mathcal G.
$$

The word “roughly” is doing honest work. The quotient can have singularities, disconnected sectors, boundary strata, nontrivial bundles, and Gribov-copy problems. Still, the quotient picture is the right first mental model: gauge theory has more variables than physical degrees of freedom.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Gauge orbits in field space, a gauge-fixing slice intersecting the orbits, and a quotient map to physical configuration space.](/figures/symmetry-anomalies-topology/gauge-orbit-quotient.svg)

<figcaption>

Raw field space contains gauge orbits: $A$, $A^g$, and $A^{g'}$ are different field coordinates for the same physical configuration. Gauge fixing chooses a local slice through the orbits; the true physical data are points in the quotient $\mathcal F/\mathcal G$.

</figcaption>
</figure>

This page fixes the conceptual reset needed before gauge fixing, Faddeev–Popov ghosts, BRST symmetry, anomalies, and the Higgs mechanism. The point is simple but merciless: if a transformation is redundancy, then “breaking it,” “charging under it,” and “observing it” do not mean what they mean for an ordinary global symmetry.

## Prerequisites

You should know the volume [Conventions and Notation](/symmetry-anomalies-topology/conventions/), especially the gauge-field sign conventions. The pages [What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/), [Background Fields versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/), [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/), and [Quotienting by Symmetry](/symmetry-anomalies-topology/background-fields-and-gauging/quotienting-by-symmetry/) provide the nearest conceptual background.

You should also be comfortable with classical electromagnetism, path integrals, constrained Hamiltonian systems at a basic level, and Lie-algebra-valued gauge fields.

## Core idea

The fastest way to detect gauge redundancy is to ask whether two field configurations that look different produce the same physical measurements.

In electrodynamics, the vector potential $A_\mu$ is not unique. With the conventions of this volume,

$$
\psi(x)\mapsto e^{-iq\alpha(x)}\psi(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x),
$$

and

$$
D_\mu\psi=(\partial_\mu+iqA_\mu)\psi
$$

transforms covariantly:

$$
D_\mu\psi\mapsto e^{-iq\alpha}D_\mu\psi.
$$

The field strength

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu
$$

is invariant. A local experiment that measures electromagnetic fields cannot distinguish $A$ from $A+d\alpha$. The two potentials are different coordinates on the same physical electromagnetic configuration.

The same pattern holds in non-Abelian gauge theory, but the geometry is richer. Write

$$
A_\mu=A_\mu^aT^a,
\qquad
[T^a,T^b]=if^{abc}T^c,
$$

with Hermitian generators, and use

$$
D_\mu=\partial_\mu+igA_\mu.
$$

For a finite gauge transformation $U(x)$ acting on matter as $\psi\mapsto U^{-1}\psi$, the connection transforms as

$$
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U,
$$

and the curvature transforms covariantly:

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U.
$$

Gauge-invariant local operators are built from traces or invariant contractions, such as

$$
\operatorname{tr} F_{\mu\nu}F^{\mu\nu},
\qquad
\bar\psi\psi,
\qquad
\bar\psi F_{\mu\nu}\psi
$$

when the representation indices are contracted appropriately.

:::note[Convention-sensitive source note]
The finite transformation above follows the convention $D_\mu=\partial_\mu+igA_\mu$ and matter transformation $\psi\mapsto U^{-1}\psi$. Many books choose $D_\mu=\partial_\mu-igA_\mu$ or $\psi\mapsto U\psi$, which moves signs between $A_\mu^U$, $F_{\mu\nu}$, and the infinitesimal transformation law. The invariant content is the same.
:::

## Redundancy is not ordinary symmetry

An ordinary internal global symmetry acts on physical states. For example, if a complex scalar theory has a global $U(1)$ symmetry,

$$
\phi(x)\mapsto e^{-i\alpha}\phi(x),
$$

then states can carry a conserved charge. Operators can have nonzero charge. Correlators obey charge-selection rules. A charged local operator is a perfectly good local operator.

A gauge redundancy is different. If the phase is made local and $A_\mu$ is dynamical, then

$$
\phi(x)\mapsto e^{-iq\alpha(x)}\phi(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x),
$$

is not a family of physically different transformations for compactly supported $\alpha$. It is an equivalence relation on descriptions.

This distinction has immediate consequences.

| Feature | Global symmetry | Gauge redundancy |
|---|---|---|
| Acts on physical states? | Yes | Not for transformations treated as redundancy |
| Charged local operators? | Usually yes | Not gauge-invariant by themselves |
| Conserved charge? | Physical generator on Hilbert space | Constraint, unless boundary terms survive |
| Can be spontaneously broken? | Yes, with order parameters and Goldstone logic | Not as a redundancy; gauge-invariant diagnostics are needed |
| Can have an anomaly? | A ’t Hooft anomaly may be allowed | A gauge anomaly is an inconsistency |
| Background field? | Can couple to one | The gauge field is already part of the description if gauged |

This table is not semantic fussing. It protects the theory from nonsense. Saying “the gauge symmetry is spontaneously broken” is a useful shorthand in perturbative Higgs calculations, but literally the redundancy is not a physical symmetry that can break. What changes in the Higgs mechanism is the spectrum, the realization of gauge-invariant operators, and the convenient choice of variables.

## Gauge orbits and physical configuration space

Let $\mathcal F$ be a space of field configurations. A gauge transformation $g\in\mathcal G$ sends a field $\Phi$ to another field $\Phi^g$. The gauge orbit through $\Phi$ is

$$
\mathcal O_\Phi=\{\Phi^g\mid g\in\mathcal G\}.
$$

A physical observable is a function on field space that is constant on gauge orbits:

$$
\mathcal O[\Phi^g]=\mathcal O[\Phi].
$$

Equivalently, it is a function on the quotient $\mathcal F/\mathcal G$.

In electrodynamics without charged matter, examples include

$$
F_{\mu\nu}(x),
\qquad
F_{\mu\nu}(x)F^{\mu\nu}(x),
\qquad
\int_\Sigma \star F.
$$

In non-Abelian gauge theory, examples include

$$
\operatorname{tr}F_{\mu\nu}F^{\mu\nu}(x),
\qquad
\operatorname{tr}F_{\mu\nu}\widetilde F^{\mu\nu}(x),
\qquad
W_R(C)=\operatorname{tr}_R\,P\exp\left(-ig\oint_C A_\mu dx^\mu\right),
$$

where the sign in the Wilson line is matched to the covariant-derivative convention. Other sign choices are common.

The quotient viewpoint also explains why gauge fixing is useful. Instead of integrating over every point in every gauge orbit, one tries to pick one representative per orbit. A gauge condition such as

$$
\partial^\mu A_\mu=0
$$

is a proposed local slice through field space. The Faddeev–Popov determinant corrects the measure for the change of variables from fields to “orbit plus representative.”

The whole procedure would be trivial if $\mathcal F/\mathcal G$ were a smooth finite-dimensional manifold and every orbit met the gauge-fixing slice once. In real gauge theory, none of those assumptions is globally guaranteed.

## Gauss law: redundancy as a constraint

The Hamiltonian viewpoint makes the redundancy physical-looking and then removes it again.

In Maxwell theory coupled to charge density $\rho$, the canonical electric field obeys Gauss law,

$$
\nabla\cdot\mathbf E=\rho.
$$

This is not an equation of motion in the same sense as the wave equation for propagating modes. It is a constraint on allowed physical states. Smeared with a function $\alpha(\mathbf x)$ on a spatial slice $\Sigma$, it gives

$$
G[\alpha]
=\int_\Sigma d^3\mathbf x\,\alpha(\mathbf x)\bigl(\nabla\cdot\mathbf E-\rho\bigr).
$$

After an integration by parts,

$$
G[\alpha]
=\int_{\partial\Sigma}\alpha\,\mathbf E\cdot d\mathbf S
-\int_\Sigma d^3\mathbf x\,\mathbf E\cdot\nabla\alpha
-\int_\Sigma d^3\mathbf x\,\alpha\rho.
$$

If $\alpha$ vanishes at the boundary, $G[\alpha]$ generates a pure redundancy and must vanish on physical states:

$$
G[\alpha]\,|\text{phys}\rangle=0.
$$

If $\alpha$ does not vanish at the boundary, the surface term can survive. Then the transformation may carry a physical charge measured at infinity. This is the first hint that “gauge transformation” is not one thing: compactly supported gauge transformations, boundary transformations, and large transformations have different physical roles.

The non-Abelian version replaces ordinary derivatives by covariant derivatives. Schematically,

$$
\mathcal G^a=(D_iE^i)^a-\rho^a,
$$

and physical states satisfy the corresponding constraint, again with boundary qualifications.

:::note[Boundary-sensitive source note]
The statement “gauge transformations are redundancies” means transformations included in the gauge group being quotiented, usually those acting trivially at the boundary. Transformations with nontrivial asymptotic action can become physical symmetries with charges. This is why the next page separates local, global, boundary, and large transformations carefully.
:::

## Gauge-variant fields can still be useful

A gauge-variant field is not automatically meaningless. It is often an efficient coordinate on field space.

The vector potential $A_\mu$ is gauge-variant, but it is the natural variable in the Lagrangian

$$
S_{\rm Maxwell}=-\frac14\int d^4x\,F_{\mu\nu}F^{\mu\nu}.
$$

The quark field $q_i(x)$ is gauge-variant under color, but it is the natural variable in the QCD Lagrangian. Gauge fixing allows one to compute gauge-invariant quantities using gauge-variant propagators and vertices. That is not hypocrisy; it is coordinate computation.

A familiar analogy is ordinary vector calculus in curvilinear coordinates. The components of a vector depend on coordinates, but tensorial statements do not. Gauge theory is more radical because the redundant directions are infinite-dimensional and interact with locality, topology, and quantization.

Gauge-variant elementary fields can also be pieces of gauge-invariant composite or dressed objects. For example, in an Abelian theory a charged field can be dressed by a Wilson line or Coulombic electromagnetic field so that the combined operator is gauge-invariant, though typically nonlocal or boundary-sensitive. This is one reason charged particles in gauge theory are subtler than charged local operators in a purely global-symmetry theory.

## The photon example: two physical polarizations

A massless vector field $A_\mu$ has four components in four-dimensional spacetime. A physical photon has two helicity states. Gauge redundancy explains the mismatch.

The gauge transformation

$$
A_\mu\mapsto A_\mu+\partial_\mu\alpha
$$

removes one component, and Gauss law removes another. In momentum space, a polarization vector $\varepsilon_\mu(k)$ has an equivalence

$$
\varepsilon_\mu(k)\sim \varepsilon_\mu(k)+c\,k_\mu
$$

for on-shell photons. Physical amplitudes are insensitive to the replacement $\varepsilon_\mu\to\varepsilon_\mu+c k_\mu$. This is the scattering-theory face of gauge redundancy.

For non-Abelian gauge bosons, the same counting works perturbatively around the trivial vacuum, but interactions force one to handle the redundancy systematically. Faddeev–Popov ghosts and BRST symmetry are the standard covariant bookkeeping devices.

## Why gauge anomalies are fatal

A global symmetry may have a ’t Hooft anomaly. That means it cannot be coupled to a background field in a fully gauge-invariant way, but the theory can still exist as a quantum theory with that global symmetry realized anomalously.

A gauge anomaly is different. Gauge symmetry is a redundancy, so an anomaly in the gauge symmetry means the redundancy cannot be consistently imposed. The path integral would depend on the representative of a gauge orbit, or the physical Hilbert space would fail to be consistently defined.

In BRST language, a gauge anomaly appears as a failure of the quantum effective action to satisfy the BRST identity. Schematically,

$$
s\Gamma\neq0.
$$

The anomaly page will make this precise. The conceptual point belongs here: anomalous global symmetry is physical structure; anomalous gauge redundancy is inconsistency unless it is canceled by additional degrees of freedom or inflow from a larger system.

## The Higgs mechanism without broken redundancy

The Higgs mechanism is often described as “spontaneous breaking of gauge symmetry.” This phrase is efficient but dangerous.

In a gauge theory, local gauge-variant expectation values such as

$$
\langle \phi(x)\rangle
$$

are not gauge-invariant diagnostics. A gauge choice can make such a quantity look nonzero, but the underlying redundancy is not a physical symmetry that breaks. What is gauge-invariant is the spectrum, the mass gap, the behavior of correlation functions, Wilson lines, and the phase structure.

In the Abelian Higgs model, the gauge-invariant content includes a massive vector excitation and a scalar radial excitation. In a convenient gauge, one says that the phase of the scalar is “eaten” by the gauge field. The honest statement is that the redundant variables reorganize so that the physical spectrum contains a massive spin-one particle.

This is not pedantry. It prevents false conclusions such as “Goldstone’s theorem predicts a physical massless boson whenever a gauge symmetry is broken.” Goldstone’s theorem applies to physical global symmetries under its assumptions, not to redundancies.

## How to tell whether a transformation is physical

Given a transformation, ask these questions.

| Question | Why it matters |
|---|---|
| Does it act trivially at the boundary? | If yes, it is usually part of the redundancy quotient. |
| Is it connected to the identity? | If no, it may be a large gauge transformation with topological consequences. |
| Does it change gauge-invariant local operators? | If yes, it is not merely a redundancy. |
| Does it change line operators, boundary data, or superselection sectors? | Then it can carry physical information even if local fields look equivalent. |
| Is it included in the gauge group being summed over? | Different choices can define different global forms of a theory. |
| Is the corresponding charge a constraint or a boundary charge? | Constraints vanish on physical states; boundary charges label physical sectors. |

The next page applies this checklist systematically.

## Common pitfalls

**“Gauge symmetry is a very large physical symmetry.”** Gauge redundancy is not physical largeness. It is descriptive overcounting. The physical content lives in gauge-invariant observables, physical states, and boundary/topological data.

**“A gauge transformation changes the fields, so it must change the state.”** Fields are coordinates. Coordinates can change while the point they describe stays fixed.

**“Gauge fixing chooses the real gauge.”** Gauge fixing chooses a coordinate chart. Good calculations give gauge-invariant answers for gauge-invariant questions.

**“The gauge potential is unphysical, so it should never appear.”** Gauge-variant variables are often the best variables for calculation. They just cannot be mistaken for observables by themselves.

**“All gauge-invariant operators are local.”** Wilson loops, ’t Hooft lines, surface operators, and dressed charged operators are gauge-invariant but extended or boundary-sensitive.

**“The Higgs field expectation value is an observable.”** The gauge-fixed expectation value is a useful diagnostic inside a chosen description. Gauge-invariant phase diagnostics require more care.

**“A gauge anomaly is like an ordinary anomaly.”** A global anomaly can be a feature. A gauge anomaly is a failure of consistency unless canceled or interpreted as boundary inflow from a higher-dimensional system.

**“The quotient $\mathcal F/\mathcal G$ is always a smooth space.”** It can have singular strata, topological sectors, reducible connections, Gribov copies, and boundary complications.

## Relations to other pages

- [Local versus Global Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/local-versus-global-transformations/) sharpens the boundary, residual, and large-transformation distinctions introduced here.
- Gauge Fixing will explain how to choose local representatives on gauge orbits.
- Faddeev–Popov Ghosts will derive the determinant that appears when one changes variables from raw fields to gauge orbits plus representatives.
- BRST Symmetry will replace the informal quotient by a nilpotent differential in the gauge-fixed theory.
- BRST Cohomology will identify physical operators as cohomology classes.
- The Anomalies chapter will distinguish allowed ’t Hooft anomalies of global symmetries from fatal gauge anomalies.
- The Defects and Extended Operators chapter will treat Wilson lines, ’t Hooft lines, and other gauge-invariant extended observables.
- The Higher-Form and Generalized Symmetries chapter will explain why gauge theories often have higher-form global symmetries acting on line operators.

## Research status

The core distinction between gauge redundancy and physical global symmetry is established. It is part of the standard formulation of classical and quantum gauge theory.

The refinements remain highly active. Boundaries can turn would-be gauge transformations into physical edge symmetries. Large gauge transformations and global forms of gauge groups affect line operators, theta terms, anomalies, and dualities. Nonperturbative gauge fixing is obstructed by Gribov copies. Modern BV-BRST language gives a systematic formalism for gauge theories with complicated gauge algebras, boundaries, and derived structures.

A safe working rule is:

$$
\text{small gauge transformation} = \text{redundancy},
\qquad
\text{boundary or large transformation} = \text{check the definition of the theory}.
$$

## Exercises

### Exercise 1: Abelian covariance

Using

$$
D_\mu=\partial_\mu+iqA_\mu,
\qquad
\psi\mapsto e^{-iq\alpha}\psi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha,
$$

show that $D_\mu\psi$ transforms in the same way as $\psi$.

<details><summary><strong>Solution</strong></summary>

Compute

$$
D'_\mu\psi'
=(\partial_\mu+iqA'_\mu)(e^{-iq\alpha}\psi).
$$

Using $A'_\mu=A_\mu+\partial_\mu\alpha$,

$$
D'_\mu\psi'
=e^{-iq\alpha}\partial_\mu\psi
-iq(\partial_\mu\alpha)e^{-iq\alpha}\psi
+iq(A_\mu+\partial_\mu\alpha)e^{-iq\alpha}\psi.
$$

The two terms proportional to $\partial_\mu\alpha$ cancel, leaving

$$
D'_\mu\psi'=e^{-iq\alpha}(\partial_\mu+iqA_\mu)\psi
=e^{-iq\alpha}D_\mu\psi.
$$

So $D_\mu\psi$ transforms covariantly.

</details>

### Exercise 2: Field strength is orbit-invariant

Show that the Abelian field strength $F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu$ is invariant under $A_\mu\mapsto A_\mu+\partial_\mu\alpha$.

<details><summary><strong>Solution</strong></summary>

The transformed field strength is

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
-\partial_\nu\partial_\mu\alpha
=F_{\mu\nu},
$$

assuming ordinary smooth functions so that partial derivatives commute. This is why $F_{\mu\nu}$ descends to the quotient by Abelian gauge transformations.

</details>

### Exercise 3: Gauge-invariant mass term?

For a complex scalar of charge $q$, decide whether the following terms are gauge-invariant:

$$
A_\mu A^\mu,
\qquad
|\phi|^2,
\qquad
|D_\mu\phi|^2.
$$

<details><summary><strong>Solution</strong></summary>

The term $A_\mu A^\mu$ is not gauge-invariant in ordinary Maxwell theory because $A_\mu\mapsto A_\mu+\partial_\mu\alpha$ changes it.

The term $|\phi|^2=\phi^*\phi$ is gauge-invariant because the phases cancel:

$$
\phi^*\phi\mapsto e^{iq\alpha}\phi^*e^{-iq\alpha}\phi=\phi^*\phi.
$$

The term $|D_\mu\phi|^2$ is also gauge-invariant because $D_\mu\phi$ transforms with the same phase as $\phi$.

This exercise is the seed of the Higgs mechanism: a direct vector mass term is not gauge-invariant, but a gauge-invariant scalar kinetic term can produce a vector mass after expanding around a suitable vacuum in a convenient gauge.

</details>

### Exercise 4: Boundary term in Gauss law

Let $\Sigma$ be a spatial region with boundary. Starting from

$$
G[\alpha]=\int_\Sigma d^3\mathbf x\,\alpha\,\nabla\cdot\mathbf E,
$$

integrate by parts and identify when a boundary term survives.

<details><summary><strong>Solution</strong></summary>

Using the divergence theorem,

$$
\int_\Sigma \alpha\,\nabla\cdot\mathbf E
=\int_\Sigma \nabla\cdot(\alpha\mathbf E)
-\int_\Sigma \mathbf E\cdot\nabla\alpha.
$$

Therefore

$$
G[\alpha]
=\int_{\partial\Sigma}\alpha\,\mathbf E\cdot d\mathbf S
-\int_\Sigma d^3\mathbf x\,\mathbf E\cdot\nabla\alpha.
$$

If $\alpha$ vanishes on $\partial\Sigma$, the boundary term is zero. If $\alpha$ approaches a nonzero value at the boundary, the boundary term survives and can be a physical charge. This is the simplest reason compactly supported gauge transformations and boundary gauge transformations must be distinguished.

</details>

## References

- L. D. Faddeev and V. N. Popov, “Feynman Diagrams for the Yang–Mills Field,” *Physics Letters B* **25** (1967) 29–30.
- C. Becchi, A. Rouet, and R. Stora, classic papers on BRST symmetry.
- I. V. Tyutin, “Gauge Invariance in Field Theory and Statistical Physics in Operator Formalism,” Lebedev preprint (1975).
- Mark Srednicki, *Quantum Field Theory*, sections on non-Abelian gauge theory, gauge-field path integrals, and BRST symmetry.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, Ch. 15. Gauge invariance, constraints, Faddeev–Popov, ghosts, BRST, and BV.
- Sidney Coleman, *Aspects of Symmetry*, “Secret Symmetry,” especially the discussion of gauge fields, functional integrals, and the Faddeev–Popov Ansatz.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, chapters on electrodynamics, Faddeev–Popov quantization, Ward identities, and gauge constraints.
- M. Henneaux and C. Teitelboim, *Quantization of Gauge Systems*. Standard reference for constraints, gauge generators, BRST, and Hamiltonian quantization.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chapters on gauge fields, BRST symmetry, and the Zinn-Justin equation.
- Michael E. Peskin and Daniel V. Schroeder, *An Introduction to Quantum Field Theory*, chapters on gauge invariance and non-Abelian gauge theory.

## Version history

- 2026-06-17: Initial polished draft. Added quotient-field-space viewpoint, Abelian and non-Abelian convention notes, Gauss-law constraint discussion, observable diagnostics, Higgs-mechanism warning, exercises, and references.
