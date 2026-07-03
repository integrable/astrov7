---
title: "Global versus Gauge Symmetry"
description: "Distinguishes physical global symmetries from gauge redundancies, including charges, Gauss law, boundary symmetries, residual gauge transformations, and large-transformation caveats."
sidebar:
  label: "Global versus Gauge Symmetry"
  order: 7
level: Graduate
status: "Polished draft"
source: "Srednicki §§22, 54, 58, 67–75; Weinberg Vol. II Ch. 15; Coleman, Aspects of Symmetry, Secret Symmetry; Gaiotto–Kapustin–Seiberg–Willett 2015 for generalized-symmetry perspective."
topics:
  - global symmetry
  - gauge symmetry
  - gauge redundancy
  - Gauss law
  - boundary symmetry
canonicalTopics:
  - global-symmetry
  - gauge-redundancy
  - gauss-law
  - boundary-symmetry
researchStatus:
  established:
    - "Proper gauge transformations are redundancies of description, while genuine global symmetries act on physical states or observables and can carry conserved charges."
  active:
    - "Boundaries, asymptotic symmetries, higher-form symmetries, non-invertible symmetries, and global forms of gauge groups refine the global-versus-gauge distinction in modern QFT."
---

## Summary

A **global symmetry** maps physical states to physical states and can produce conserved charges, selection rules, degeneracies, or order parameters. A **proper gauge transformation** changes only the representative used to describe the same physical state.

That difference is easy to say and surprisingly easy to blur. The same formula

$$
\psi(x)\mapsto U^{-1}(x)\psi(x)
$$

can describe a redundancy, a physical symmetry, or a boundary charge depending on which transformations are allowed, which ones are quotiented out, and what boundary conditions are imposed.

The practical rule is:

$$
\text{global symmetry acts on physical states; proper gauge symmetry acts within a description of one state.}
$$

<figure class="doc-figure" style="--figure-width: 46rem;">

![Proper gauge transformations, boundary transformations, and large transformations have different physical roles.](/figures/gauge-theories-standard-model/global-vs-gauge-transformations.svg)

<figcaption>

Not every transformation written as $U(x)$ has the same status. Compactly supported transformations are usually proper gauge redundancies. Transformations that act at a boundary can carry charges. Large transformations can label global sectors, theta angles, or anomaly-sensitive data.

</figcaption>
</figure>

The slogan has a boundary caveat:

$$
\text{gauge at one boundary condition can become global at another.}
$$

This page explains the distinction before quantization, BRST, Higgs physics, confinement, and anomalies make it more subtle.

## Prerequisites

You should know [Gauge Redundancy Revisited](/gauge-theories-standard-model/gauge-principle/gauge-redundancy-revisited/), [Local Symmetry and Covariant Derivatives](/gauge-theories-standard-model/gauge-principle/local-symmetry-and-covariant-derivatives/), [Minimal Coupling](/gauge-theories-standard-model/gauge-principle/minimal-coupling/), and [Matter Representations](/gauge-theories-standard-model/gauge-principle/matter-representations/).

You should also know the elementary Noether statement: a continuous physical global symmetry usually gives a conserved current and charge. This page explains why gauge symmetry modifies that story rather than simply giving infinitely many ordinary Noether charges.

## Core idea

Start with a space of field configurations $\mathcal C$. Gauge theory says that many points of $\mathcal C$ describe the same physical configuration. Proper gauge transformations form a group $\mathcal G_0$ acting on $\mathcal C$, and the physical configuration space is locally

$$
\mathcal C_{\mathrm{phys}}=\mathcal C/\mathcal G_0.
$$

A proper gauge transformation moves along a gauge orbit. It does not move to a new physical point.

By contrast, a global symmetry acts on the physical configuration space itself:

$$
\mathcal C_{\mathrm{phys}}\longrightarrow \mathcal C_{\mathrm{phys}}.
$$

It can relate different states, rotate charged operators, produce multiplets, and generate conserved charges.

The hard part is deciding which transformations belong to $\mathcal G_0$. That is not determined by the local Lie algebra alone. It depends on boundary conditions, allowed gauge transformations, global topology, and sometimes the operator algebra one wants to include.

## Setup and terminology

A local gauge transformation is a spacetime-dependent group-valued function

$$
U(x)\in G.
$$

For a matter field in representation $R$,

$$
\psi(x)\mapsto U_R^{-1}(x)\psi(x).
$$

For the gauge connection,

$$
A_\mu\mapsto A_\mu^U
=U^{-1}A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

The word “gauge transformation” is often used for all such maps. For conceptual work it is better to separate at least three classes.

| Transformation type | Typical condition | Physical role |
|---|---|---|
| Proper gauge transformation | Trivial at the boundary, continuously connected to the identity | Redundancy; quotient it out. |
| Global or asymptotic transformation | Nontrivial constant or function at the boundary, or acts faithfully on gauge-invariant states | Physical symmetry with charge or selection rule. |
| Large transformation | Not continuously connected to the identity, or topologically nontrivial | Can identify sectors, quantize terms, shift theta angles, or reveal anomalies. |

The table is a guide, not a universal theorem. Gauge theory is where innocent-looking boundary conditions grow teeth.

## A first comparison

Consider a complex scalar field with a global $U(1)$ symmetry but no dynamical gauge field:

$$
\phi(x)\mapsto e^{-iq\alpha}\phi(x),
\qquad
\alpha=\text{constant}.
$$

This is a physical global symmetry. Noether's theorem gives a conserved current $j^\mu$, and the charge

$$
Q=\int_\Sigma d^3x\,j^0
$$

acts on states. Local operators can carry charge:

$$
[Q,\phi]=-q\phi
$$

up to the sign convention for the charge operator.

Now make the symmetry local and introduce a dynamical gauge field:

$$
\phi(x)\mapsto e^{-iq\alpha(x)}\phi(x),
\qquad
A_\mu(x)\mapsto A_\mu(x)+\partial_\mu\alpha(x).
$$

The local phase of $\phi$ is now partly a coordinate choice on field space. The field $\phi(x)$ itself is no longer a gauge-invariant local observable. Gauge-invariant local operators include combinations such as

$$
\phi^\dagger\phi,
\qquad
F_{\mu\nu},
\qquad
(D_\mu\phi)^\dagger D^\mu\phi.
$$

This is the conceptual flip:

$$
\text{global }U(1): \phi\text{ can be a charged local operator},
$$

but

$$
\text{gauged }U(1): \phi\text{ is not by itself a gauge-invariant local observable}.
$$

Charged objects can still exist, but in a gauge theory they must be treated with Gauss law and dressing. In electrodynamics, a charged state is accompanied by an electric field extending to infinity or to other charges. The charge is detected by flux, not by a gauge-variant local field alone.

## Noether theorem versus gauge redundancy

For an ordinary continuous global symmetry, a transformation with constant parameter $\epsilon$ gives a current conservation law

$$
\partial_\mu j^\mu=0
$$

on the equations of motion. The associated charge

$$
Q=\int_\Sigma d^3x\,j^0
$$

acts on the physical Hilbert space.

For a local gauge redundancy, the parameter is an arbitrary function. Noether's second theorem says that this produces identities among equations of motion and constraints, not one independent physical charge at each point.

In canonical language, gauge theory has a Gauss-law constraint. Schematically,

$$
\mathcal G^a=D_iE^{ia}-\rho^a\approx 0,
$$

where $E^{ia}$ is the canonical electric field and $\rho^a$ is the matter charge density.

A smeared gauge generator has the form

$$
G[\alpha]=\int_\Sigma d^3x\,\alpha^a(x)\mathcal G^a(x)
\quad +\quad \text{boundary term}.
$$

If $\alpha$ vanishes at the boundary, the boundary term is absent, and $G[\alpha]$ annihilates physical states:

$$
G[\alpha]\,|\text{phys}\rangle=0.
$$

Such transformations are proper gauge redundancies.

If $\alpha$ does not vanish at the boundary, the boundary term can survive. In Abelian gauge theory on an asymptotically flat spatial slice, a constant boundary value gives the electric charge measured by electric flux:

$$
Q_{\mathrm{electric}}
=\oint_{S^2_\infty}\mathbf E\cdot d\mathbf S
$$

up to the conventional normalization of electric charge. This is no longer merely a redundancy. It is an asymptotic symmetry charge.

:::note[Bulk constraint, boundary charge]
The same local gauge parameter can generate no physical motion in the bulk and a real charge at the boundary. This is why gauge theory forces one to state boundary conditions before making sweeping claims about “gauge transformations.”
:::

## Proper gauge transformations

A proper gauge transformation is one that is treated as a redundancy of description. In most local discussions, these are transformations that are continuously connected to the identity and vanish sufficiently fast at the boundary.

If $\mathcal O$ is a genuine observable, it must be invariant under proper gauge transformations:

$$
\mathcal O[\Phi^g]=\mathcal O[\Phi],
\qquad
g\in\mathcal G_0.
$$

Equivalently, an observable is a function on the quotient

$$
\mathcal C/\mathcal G_0,
$$

not on the redundant configuration space $\mathcal C$.

For non-Abelian gauge theory, the field strength transforms covariantly:

$$
F_{\mu\nu}\mapsto U^{-1}F_{\mu\nu}U.
$$

Therefore $F_{\mu\nu}^a$ itself is not gauge invariant as a color-labelled object. But traces such as

$$
\operatorname{tr}(F_{\mu\nu}F^{\mu\nu})
$$

are invariant.

This is why physical statements in gauge theory are built from gauge-invariant combinations: traces, singlet contractions, Wilson loops, boundary fluxes, or properly dressed charged operators.

## Physical global symmetries

A physical global symmetry acts on gauge-invariant observables or physical states. It is not quotiented out as a redundancy.

Examples include:

| Theory | Gauge redundancy | Possible physical global symmetry |
|---|---|---|
| Scalar QED | Local electromagnetic $U(1)$ | Spacetime symmetries; possible flavor rotations among fields of equal charge. |
| QCD with quarks | Local color $SU(3)$ | Baryon number, flavor symmetry in mass-degenerate limits, approximate chiral symmetries. |
| Electroweak theory | Local $SU(2)_L\times U(1)_Y$ | Accidental baryon and lepton numbers at the renormalizable level, with anomaly caveats. |
| Pure Yang–Mills | Local gauge redundancy | Center higher-form symmetry, depending on global form and line operators. |

The key test is not whether the transformation looks constant. The key test is whether it acts nontrivially on physical gauge-invariant data.

A color rotation of all quark fields by a constant element of $SU(3)_c$ is still a gauge transformation if it is included in the gauge redundancy. It is not an ordinary global flavor symmetry. By contrast, rotating two quark flavors into each other can be a genuine global symmetry if their masses and gauge representations match.

## Boundary and asymptotic symmetries

Gauge theories are especially sensitive to boundaries. On a spatial region with boundary $\partial\Sigma$, a transformation that does not vanish on $\partial\Sigma$ may act on boundary data. It can then have a nonzero charge.

The prototype is electromagnetism. The Gauss-law constraint says

$$
\nabla\cdot\mathbf E=\rho.
$$

Integrating over a region $\Sigma$ gives

$$
\int_\Sigma d^3x\,\rho
=
\oint_{\partial\Sigma}\mathbf E\cdot d\mathbf S.
$$

Thus total charge in a region is measured by electric flux through the boundary. A charged state cannot be described as a purely local excitation independent of its gauge field.

This fact has several consequences:

| Consequence | Meaning |
|---|---|
| Charged operators need dressing | A charged insertion must be accompanied by gauge-field data, such as a Wilson line or Coulomb dressing. |
| Boundary conditions matter | The same formal $U(x)$ may be proper gauge or physical asymptotic symmetry depending on boundary behavior. |
| Subsystems have edge data | Dividing space into regions in gauge theory introduces boundary degrees of freedom or constraints. |
| Charges are often surface terms | Gauss law converts bulk charge into boundary flux. |

The modern study of asymptotic symmetries, soft theorems, edge modes, and entanglement in gauge theory develops this point far beyond the first classical discussion.

## Large gauge transformations

Not every gauge transformation is continuously deformable to the identity. A transformation can be topologically nontrivial. Such transformations are called **large gauge transformations**.

Large transformations can matter even when local formulas are unchanged. They can:

- constrain the quantization of Chern–Simons levels;
- shift theta-angle representatives;
- distinguish topological sectors of gauge fields;
- affect the definition of the path-integral measure;
- expose global anomalies;
- change which bundles and line operators are allowed.

For example, instanton sectors in non-Abelian gauge theory are not visible from the local expression for $D_\mu$ alone. They require global information about gauge fields and gauge transformations.

This page does not classify large gauge transformations. It flags the conceptual point: “gauge redundancy” is not exhausted by infinitesimal local formulas, and global topology can leave observable traces.

## Gauge fixing and residual transformations

Gauge fixing chooses a representative on each gauge orbit, at least locally. For example, Lorenz gauge imposes

$$
\partial_\mu A^\mu=0.
$$

A gauge transformation in Abelian theory preserves Lorenz gauge if

$$
\Box\alpha=0.
$$

These are called residual gauge transformations. But “residual” does not automatically mean “physical.” Some residual transformations are still redundancies. Some may be tied to boundary symmetries. The distinction depends on whether they act nontrivially on physical data after the proper gauge redundancy has been quotiented out.

This is a common trap:

$$
\text{preserves a gauge condition}
\not\Rightarrow
\text{physical global symmetry}.
$$

Gauge fixing is a coordinate choice on the redundant space. It cannot by itself create a physical symmetry.

## Higgs mechanism warning

A gauge symmetry cannot be spontaneously broken in the same sense as an ordinary global symmetry. A gauge-variant expectation value such as

$$
\langle\phi\rangle
$$

is not by itself a gauge-invariant observable.

In practical perturbation theory, one often chooses a gauge in which a scalar field has a nonzero vacuum expectation value. That is a useful coordinate choice. The physical statements are gauge-invariant: the spectrum contains massive vector bosons, certain scalar excitations, and gauge-invariant correlation functions with characteristic long-distance behavior.

A global symmetry can break and produce physically distinct vacua. A gauge redundancy is not a physical symmetry to be broken. The Higgs mechanism is real physics, but the phrase “spontaneously broken gauge symmetry” should be read with care.

Later pages on the Abelian Higgs model, non-Abelian Higgs mechanism, and electroweak symmetry breaking will make this precise.

## Relation to generalized symmetries

Modern QFT broadens the notion of global symmetry. A $q$-form global symmetry acts on $q$-dimensional charged operators rather than ordinary local operators. Wilson lines, 't Hooft lines, surface operators, and defects become part of the symmetry story.

This does not erase the distinction between gauge redundancy and global symmetry. It sharpens it.

For example, pure $SU(N)$ Yang–Mills theory has no ordinary global color symmetry. Color is gauged. But it can have a center one-form global symmetry acting on Wilson lines, depending on the global form of the gauge group and matter content.

Thus a gauge theory can have:

$$
\text{local gauge redundancy}
\quad + \quad
\text{ordinary global symmetries}
\quad + \quad
\text{higher-form global symmetries}.
$$

They are different structures. Mixing them up is a reliable way to make nonsense sound profound. A true occupational hazard.

## Common pitfalls

**Calling gauge redundancy a physical symmetry.** Proper gauge transformations do not relate different physical states. They relate different descriptions of the same state.

**Assuming constant means global.** A constant transformation in a gauge group can still be part of the gauge redundancy. Whether it is physical depends on boundary conditions and on which transformations are quotiented out.

**Forgetting Gauss law.** Gauge charge is constrained by the gauge field. In electromagnetism, total charge is measured by electric flux. Charged states are not created by undressed local gauge-variant fields.

**Treating residual gauge transformations as physical automatically.** Preserving a gauge condition is not the same as acting on the physical Hilbert space.

**Saying gauge symmetry is broken without qualification.** Gauge fixing can make a field expectation value look nonzero. Gauge-invariant statements about the Higgs phase require observables, spectra, and correlations.

**Confusing color with flavor.** Color $SU(3)$ is gauged in QCD. Flavor rotations among quark species are possible global symmetries when the Lagrangian permits them.

**Ignoring boundaries.** Boundary conditions can turn would-be gauge transformations into physical charges. This is not a technicality; it is where electric charge lives.

## Relations to other pages

[Gauge Redundancy Revisited](/gauge-theories-standard-model/gauge-principle/gauge-redundancy-revisited/) gives the orbit-space viewpoint. This page adds the contrast with physical global symmetries, Noether charges, Gauss law, and boundary transformations.

[Matter Representations](/gauge-theories-standard-model/gauge-principle/matter-representations/) explains how fields transform under gauge groups. This page explains why those transformations are not automatically physical symmetries.

The next natural page is Gauge-Invariant Observables, where the criterion “descend to the quotient” becomes a toolkit: local singlets, Wilson loops, boundary charges, and dressed charged operators.

Later chapters revisit the distinction in more advanced forms: Faddeev–Popov gauge fixing and BRST symmetry in gauge quantization, center symmetry in confinement, anomaly constraints in the Standard Model, and generalized global symmetries in modern gauge theory.

## Research status

The basic distinction between proper gauge redundancy and physical global symmetry is established. The refined boundary and global questions are active across several communities.

Important modern developments include asymptotic symmetries and soft charges, edge modes in gauge-theory entanglement, generalized global symmetries, non-invertible symmetries, global forms of gauge groups, and anomalies involving higher-form symmetries. These developments do not overturn the elementary distinction. They make the phrase “which transformations are redundancies?” a serious structural question.

## Exercises

### Exercise 1: Gauge-invariant combinations in scalar QED

Let

$$
\phi\mapsto e^{-iq\alpha(x)}\phi,
\qquad
A_\mu\mapsto A_\mu+\partial_\mu\alpha.
$$

Which of the following are gauge invariant?

$$
\phi,
\qquad
\phi^\dagger\phi,
\qquad
A_\mu,
\qquad
F_{\mu\nu},
\qquad
(D_\mu\phi)^\dagger D^\mu\phi.
$$

<details><summary><strong>Solution</strong></summary>

The field $\phi$ is not gauge invariant because it transforms by a phase. The combination $\phi^\dagger\phi$ is invariant because the phases cancel.

The gauge potential $A_\mu$ is not gauge invariant because it shifts by $\partial_\mu\alpha$. The field strength

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu
$$

is invariant because the second derivatives of $\alpha$ cancel.

The covariant derivative transforms like the field:

$$
D_\mu\phi\mapsto e^{-iq\alpha}D_\mu\phi.
$$

Therefore

$$
(D_\mu\phi)^\dagger D^\mu\phi
$$

is invariant.

</details>

### Exercise 2: Total charge on a compact space

In Abelian gauge theory on a compact spatial slice with no boundary, integrate Gauss law

$$
\nabla\cdot\mathbf E=\rho
$$

over all space. What constraint follows for the total charge?

<details><summary><strong>Solution</strong></summary>

Integrating gives

$$
\int d^3x\,\rho
=
\int d^3x\,\nabla\cdot\mathbf E.
$$

The right-hand side is a boundary integral by the divergence theorem:

$$
\int d^3x\,\nabla\cdot\mathbf E
=
\oint_{\partial\Sigma}\mathbf E\cdot d\mathbf S.
$$

If the spatial slice has no boundary, the boundary term vanishes. Therefore

$$
Q_{\mathrm{total}}=\int d^3x\,\rho=0.
$$

On a compact space without boundary, the total gauge charge must vanish. This is a direct expression of Gauss law.

</details>

### Exercise 3: Constant color rotations

In QCD, quarks transform under local color $SU(3)_c$. Is a constant color rotation an ordinary global flavor symmetry?

<details><summary><strong>Solution</strong></summary>

No. A constant color rotation is still a gauge transformation if it is included in the gauge redundancy. It rotates color labels, which are not physical labels of gauge-invariant local states.

A flavor symmetry rotates different quark species, such as $u$ and $d$, when their gauge representations and masses allow it. Flavor acts on physical gauge-invariant operators. Color is gauged; flavor may be global.

Boundary conditions can add nuance, but in ordinary QCD without treating color rotations at a boundary as physical asymptotic symmetries, constant color rotations are gauge redundancy, not global flavor symmetry.

</details>

### Exercise 4: Residual gauge transformations in Lorenz gauge

In Abelian gauge theory, Lorenz gauge is

$$
\partial_\mu A^\mu=0.
$$

A gauge transformation $A_\mu\mapsto A_\mu+\partial_\mu\alpha$ preserves this gauge if $\Box\alpha=0$. Explain why this condition alone does not prove that such transformations are physical global symmetries.

<details><summary><strong>Solution</strong></summary>

The condition $\Box\alpha=0$ says only that the transformed gauge potential still satisfies the chosen gauge condition. Gauge fixing is a coordinate choice on the space of gauge orbits. A transformation can preserve that coordinate condition and still move along the same gauge orbit.

To decide whether the transformation is physical, one must ask whether it acts nontrivially on gauge-invariant observables or physical states after proper gauge transformations have been quotiented out. Boundary behavior is crucial. If $\alpha$ vanishes appropriately at the boundary, the transformation is typically still a redundancy. If it has nontrivial boundary data, it may generate an asymptotic charge.

</details>

## References

- Srednicki, *Quantum Field Theory*, §§54, 58, and 67–75, for Maxwell theory, QED Ward identities, non-Abelian gauge theory, gauge fixing, BRST, and anomalies.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, Ch. 15, for gauge invariance, constraints, quantization, Faddeev–Popov ghosts, and BRST symmetry.
- Coleman, *Aspects of Symmetry*, “Secret Symmetry,” for a classic discussion of gauge fields, the Higgs phenomenon, and why gauge symmetry differs from ordinary symmetry.
- Henneaux and Teitelboim, *Quantization of Gauge Systems*, for the canonical constraint viewpoint.
- Gaiotto, Kapustin, Seiberg, and Willett, “Generalized Global Symmetries,” for the modern higher-form symmetry perspective.

## Version history

- **2026-06-17:** Initial polished draft distinguishing proper gauge redundancy, physical global symmetry, boundary charges, residual gauge transformations, and large-transformation caveats.
