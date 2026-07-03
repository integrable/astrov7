---
title: "Background Fields versus Dynamical Gauge Fields"
description: "Separates nondynamical background gauge fields from fluctuating dynamical gauge fields, emphasizing path integrals, Gauss laws, operator content, and the meaning of gauging."
sidebar:
  label: "Background vs Dynamical"
  order: 3
level: Graduate
status: "Polished draft"
source: "Srednicki on QED, nonabelian gauge theory, Ward identities, and BRST; Weinberg Vol. II on gauge theory, external fields, and background-field gauge; Schwartz on gauge invariance and background fields."
topics:
  - background fields
  - dynamical gauge fields
  - gauging
  - gauge redundancy
  - Gauss law
  - charged operators
  - BRST
canonicalTopics:
  - background-versus-dynamical-field
  - gauging-global-symmetry
  - gauge-redundancy
  - gauss-law-constraint
  - gauge-invariant-operator
researchStatus:
  established:
    - "The distinction between external source fields and dynamical gauge fields is foundational in path-integral and canonical QFT."
  active:
    - "Modern work refines this distinction through edge modes, asymptotic symmetries, higher-form gauging, topological gauge fields, and relative QFT."
---

## Summary

The same symbol $A_\mu$ can play two very different roles.

As a **background field**, $A_\mu$ is a fixed external source:

$$
Z[A]=\int \mathcal D\phi\,e^{iS[\phi;A]}.
$$

The path integral does **not** integrate over $A_\mu$. Functional derivatives of $W[A]$ insert currents and response functions.

As a **dynamical gauge field**, $a_\mu$ is part of the quantum system:

$$
Z_{\text{gauge}}
=\int \frac{\mathcal D a}{\operatorname{Vol}(\mathcal G)}\,\mathcal D\phi\,
e^{iS[\phi,a]+iS_{\text{gauge}}[a]+iS_{\text{ct}}[a]}.
$$

Now the gauge transformation is a redundancy of the dynamical description. One must quotient by gauge transformations, impose Gauss-law constraints, and use gauge-invariant observables.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A two-column comparison between a fixed background field and a dynamical gauge field, showing path-integral role, symmetry meaning, Ward identity or Gauss law, and operator consequences.](/figures/symmetry-anomalies-topology/background-versus-dynamical-gauge-field.svg)

<figcaption>

A background field is an input to the QFT and generates response. A dynamical gauge field is summed over, quotiented by gauge redundancy, and changes the physical Hilbert space and operator content. The same one-form notation can hide very different physics.

</figcaption>
</figure>

This distinction is the conceptual hinge of gauging:

$$
\text{global symmetry background}
\quad\xrightarrow{\text{sum/integrate over backgrounds}}\quad
\text{dynamical gauge redundancy}.
$$

## Prerequisites

Read [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/) together with this page. That page explains how a global symmetry is probed; the later Gauge Redundancy and BRST chapter explains why a true gauge symmetry is not an ordinary physical symmetry.

You should also know the operator meaning of charged local operators from [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/) and the charge-surface viewpoint from [Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/).

## Core idea

A background field asks a question. A dynamical gauge field is part of the answer.

When $A_\mu$ is a background for a global symmetry, it tells the QFT what external symmetry environment it is living in. You can vary it to measure the current,

$$
\frac{\delta W[A]}{\delta A_\mu^a(x)}=\langle j_a^\mu(x)\rangle_A,
$$

and you can demand background gauge covariance to organize Ward identities.

When $a_\mu$ is dynamical, its gauge transformations are redundancies of the variables used to describe the QFT. The field $a_\mu$ fluctuates. It can have propagators, topological sectors, constraints, ghosts after gauge fixing, and gauge-invariant line operators. Most importantly, it changes which operators are genuine physical operators.

The slogan is:

$$
\text{background gauge covariance constrains }W[A],
\qquad
\text{dynamical gauge redundancy constrains }\mathcal H_{\text{phys}}.
$$

## Setup and conventions

Use $A$ for a nondynamical background connection and $a$ for a dynamical gauge field when both appear. This is only notation; the physical distinction is whether the path integral sums over the field.

A background-field partition function has the form

$$
Z[A]=\int \mathcal D\phi\,e^{iS[\phi;A]}.
$$

A dynamical gauge theory has the schematic form

$$
Z=\int \frac{\mathcal D a}{\operatorname{Vol}(\mathcal G)}\,\mathcal D\phi\,e^{iS[\phi,a]}.
$$

If the gauge field has a Maxwell or Yang–Mills kinetic term in four dimensions,

$$
S_{\text{gauge}}[a]
=-\frac{1}{2g^2}\int \operatorname{tr}(f\wedge *f),
$$

then it has local propagating gauge-boson degrees of freedom after gauge fixing. In other dimensions, or for topological actions such as Chern–Simons and BF theory, a dynamical gauge field may have no local propagating modes but is still dynamical because the theory sums over it.

:::note[Convention-sensitive naming note]
The phrase “background field” is also used in the **background field method**, where a dynamical gauge field is split as $a_\mu=\bar a_\mu+\alpha_\mu$ for calculation. That is a computational split inside a gauge theory. It is related but not identical to a background field for a global symmetry.
:::

## The path-integral distinction

For a background field, $A$ is an argument of the functional:

$$
Z[A].
$$

Changing $A$ changes the question. Differentiating with respect to $A$ inserts the current. Gauge-transforming $A$ checks whether the source description is redundant in the right way.

For a dynamical gauge field, $a$ is an integration variable:

$$
Z=\int \frac{\mathcal D a}{\operatorname{Vol}(\mathcal G)}\cdots.
$$

Gauge-transforming $a$ moves along a redundant orbit in the integration space. The division by $\operatorname{Vol}(\mathcal G)$ is schematic; perturbatively one gauge-fixes and introduces Faddeev–Popov ghosts, BRST symmetry, or equivalent machinery.

The difference can be summarized as follows.

| Feature | Background field $A$ | Dynamical gauge field $a$ |
|---|---|---|
| Path integral | Held fixed | Integrated or summed over |
| Gauge transformations | Redundancy of source description | Redundancy of dynamical variables |
| Main output | $W[A]$, currents, response, Ward identities | Physical Hilbert space, gauge-invariant observables, phases |
| Gauge fixing | Not needed for $A$ itself | Required in redundant variables |
| Charged local operators | Can be genuine operators charged under global $G$ | Usually not gauge-invariant physical local operators |
| Anomaly role | Failure of background gauge invariance | Obstruction to defining the gauged theory |

The phrase “usually” in the operator row hides boundary subtleties. With boundaries or asymptotic regions, gauge transformations that do not vanish at the boundary can act as physical global symmetries.

## The canonical distinction: Gauss law

In canonical quantization, a dynamical gauge field imposes a constraint. For abelian gauge theory coupled to matter, the schematic Gauss law is

$$
(\partial_iE^i-\rho)|\text{phys}\rangle=0.
$$

For nonabelian gauge theory,

$$
\big((D_iE^i)^a-\rho^a\big)|\text{phys}\rangle=0.
$$

This equation is not an equation of motion for a background source. It is a constraint selecting physical states. It says that gauge transformations connected to the identity act trivially on physical states, except possibly at boundaries.

Integrating the abelian Gauss law over a compact spatial slice $\Sigma$ gives

$$
\int_\Sigma d^{d-1}x\,\rho
=\int_\Sigma d^{d-1}x\,\partial_iE^i
=\int_{\partial\Sigma} *E.
$$

On a closed compact space with no boundary, the right-hand side vanishes. Thus physical states have zero total gauge charge. In a theory with a global $U(1)$ symmetry, by contrast, charged states are perfectly ordinary sectors of the Hilbert space.

This is one of the sharpest operational differences:

$$
\text{global charge labels states},
\qquad
\text{gauge charge is constrained by Gauss law}.
$$

## Charged operators before and after gauging

Consider a complex scalar field $\phi$ with global $U(1)$ symmetry. Before gauging, $\phi(x)$ is a genuine local operator carrying charge $q$:

$$
e^{i\alpha Q}\phi(x)e^{-i\alpha Q}=e^{iq\alpha}\phi(x).
$$

Coupling to a background $A$ does not destroy this statement. It lets correlation functions of charged operators be computed in a fixed external field, with appropriate parallel transport or source insertions when needed.

After gauging, the local field $\phi(x)$ is not gauge invariant:

$$
\phi(x)\mapsto e^{iq\lambda(x)}\phi(x).
$$

Therefore $\phi(x)$ alone is not a genuine physical local operator of the gauged theory. One can build gauge-invariant composites such as

$$
\phi^*(x)\phi(x),
$$

or nonlocal dressed charged operators such as

$$
\Phi_\gamma(x)=\phi(x)\exp\left(iq\int_\gamma a\right),
$$

where the path $\gamma$ must end at a boundary, at infinity, or on another charged insertion, depending on the theory and boundary conditions.

This is not a small technicality. Gauging changes the operator algebra. It can convert charged local operators into line-attached objects, introduce Wilson lines, create flux sectors, and change which defects are genuine.

## Scalar QED as the basic example

Start with an ungauged complex scalar,

$$
\mathcal L_0=\partial_\mu\phi^*\partial^\mu\phi-m^2|\phi|^2-\lambda|\phi|^4.
$$

It has a global $U(1)$ symmetry. A background field gives

$$
\mathcal L[\phi;A]=(D_\mu\phi)^*D^\mu\phi-m^2|\phi|^2-\lambda|\phi|^4,
\qquad
D_\mu=\partial_\mu-iqA_\mu,
$$

and

$$
Z[A]=\int \mathcal D\phi\,e^{i\int d^dx\,\mathcal L[\phi;A]}.
$$

The background $A$ probes the global current. The charged field $\phi$ remains a charged local operator of the original theory.

Scalar QED instead has a dynamical gauge field $a$:

$$
Z_{\text{scalar QED}}
=\int \frac{\mathcal D a}{\operatorname{Vol}(\mathcal G)}\,\mathcal D\phi\,
\exp\left(i\int d^dx\left[-\frac{1}{4e^2}f_{\mu\nu}f^{\mu\nu}
+(D_\mu\phi)^*D^\mu\phi-m^2|\phi|^2-\lambda|\phi|^4\right]\right),
$$

where now

$$
D_\mu=\partial_\mu-iq a_\mu.
$$

The local phase rotation is no longer a physical global symmetry acting faithfully on local charged operators. It is a redundancy. Physical local operators must be gauge invariant.

## Gauging as an operation

The transition from background to dynamical is the operation of gauging. Very schematically,

$$
Z[A]
\quad\leadsto\quad
Z_{\text{gauged}}
=\int \frac{\mathcal D A}{\operatorname{Vol}(\mathcal G)}\,
Z[A]e^{iS_{\text{gauge}}[A]+iS_{\text{ct}}[A]}.
$$

This formula suppresses many details: gauge fixing, global topology, boundary conditions, discrete theta terms, counterterms, flux sums, and possible spin-structure dependence. Still, it captures the essential point. Gauging is not just allowing the symmetry parameter to depend on spacetime. Gauging is summing over the corresponding background fields, modulo gauge redundancy.

For finite groups, the same idea becomes a sum rather than a functional integral:

$$
Z_{\text{gauged}}
=\sum_{[A]\in \operatorname{Bun}_G(M)}
\frac{1}{|\operatorname{Aut}(A)|}\,Z[A]e^{iS_{\text{top}}[A]}.
$$

Here $A$ denotes a flat finite-group background, and $S_{\text{top}}[A]$ may include discrete torsion or Dijkgraaf–Witten terms.

The operation makes sense only if the original background dependence is consistent. An anomalous $Z[A]$ cannot be integrated over gauge orbits in the same dimension unless additional anomaly-canceling data are supplied.

## Dynamical gauge fields can still have background symmetries

The background-versus-dynamical distinction is a role, not a species of field.

A theory can have a dynamical gauge field for one symmetry and a background field for another. For example, QCD has a dynamical color gauge field $a_{\text{color}}$ and can be coupled to nondynamical flavor backgrounds $A_{\text{flavor}}$:

$$
Z[A_{\text{flavor}}]
=\int \frac{\mathcal D a_{\text{color}}}{\operatorname{Vol}(\mathcal G_{\text{color}})}\,\mathcal Dq\,\mathcal D\bar q\,
e^{iS[q,\bar q,a_{\text{color}};A_{\text{flavor}}]}.
$$

Color gauge transformations are redundancies of the dynamical variables. Flavor background gauge transformations express Ward identities and anomaly tests for the global flavor symmetry.

This is why the same page may contain both kinds of transformations. One must always ask:

$$
\text{Is this field integrated over?}
$$

If yes, it is dynamical. If no, it is a background source.

## External electromagnetic fields and QED

Electromagnetism is a classic source of language trouble.

In ordinary QED, the electromagnetic gauge field is dynamical. The path integral includes $\mathcal D a_\mu$, and physical local operators must be gauge invariant.

In many applications, one studies matter in an external electromagnetic field $A_\mu^{\text{ext}}$. Then $A_\mu^{\text{ext}}$ is a background source. If the photon is also dynamical, one may write

$$
a_\mu=A_\mu^{\text{ext}}+\alpha_\mu
$$

and integrate over the fluctuation $\alpha_\mu$. This is a background-field split of a dynamical field, not the same as gauging a global flavor symmetry from scratch.

The diagnostic remains simple:

$$
\int \mathcal D A_\mu^{\text{ext}}?
$$

If the answer is no, it is an external background in that calculation.

## Boundaries and edge modes

On a closed spatial slice, Gauss law removes total gauge charge. With boundaries, the story changes because the integrated Gauss law becomes a boundary flux statement:

$$
Q_{\text{matter}}=\int_{\partial\Sigma} *E.
$$

Gauge transformations that are nontrivial at the boundary may act as physical symmetries on boundary degrees of freedom. This is why edge modes, asymptotic symmetries, soft charges, and boundary conditions are not decorative details in gauge theory. They determine which transformations are redundancies and which are physical symmetries.

This subtlety does not erase the background-versus-dynamical distinction. It refines it: a dynamical gauge field can produce physical global symmetry charges at boundaries or infinity.

## Topological dynamical gauge fields

A dynamical gauge field need not propagate photons or gluons. In Chern–Simons theory, BF theory, and finite gauge theory, the gauge field is integrated or summed over but may have no local degrees of freedom.

For example, a three-dimensional Chern–Simons path integral has the schematic form

$$
Z_{\text{CS}}(M)=\int \frac{\mathcal D a}{\operatorname{Vol}(\mathcal G)}\,e^{i\frac{k}{4\pi}\int_M\operatorname{tr}\left(a\wedge da-\frac{2i}{3}a\wedge a\wedge a\right)}.
$$

There are no local propagating gauge bosons, but $a$ is still dynamical because the theory sums over gauge-equivalence classes of connections. The observables are topological line operators, not ordinary local charged fields.

So do not use "has a kinetic term" as the definition of dynamical. Use "is summed or integrated over."

## Common pitfalls

**Saying “the global symmetry becomes local” as the definition of gauging.** Localizing the parameter is only the diagnostic step. Gauging means introducing or summing over gauge fields and quotienting by gauge redundancy.

**Thinking a background field must be small.** Background fields can be arbitrary external configurations, including nontrivial holonomies and bundles, as long as the QFT is defined on them.

**Thinking a dynamical gauge field must have propagating particles.** Topological gauge fields are dynamical if the path integral sums over them.

**Using charged local fields as physical operators after gauging.** A charged field may be useful in gauge-fixed perturbation theory, but physical local operators must be gauge invariant.

**Forgetting the quotient by gauge transformations.** Integrating over $a_\mu$ without dividing by redundant gauge orbits overcounts configurations and leads to ill-defined perturbation theory.

**Confusing background-field method with background fields for global symmetries.** The former is a computational split of a dynamical field. The latter is a source for a global symmetry current or defect.

**Ignoring anomalies before gauging.** If $Z[A]$ is not a well-defined gauge-invariant functional of the background, the gauged path integral is not well-defined without additional anomaly-canceling structure.

## Relations to other pages

- [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/) explains the source side of the distinction.
- **Gauge Symmetry Is Redundancy** develops the conceptual meaning of dynamical gauge redundancy later in the volume.
- **Gauge Fixing** explains how redundant variables are handled in perturbation theory later in the volume.
- **BRST Symmetry** gives the cohomological organization of gauge-fixed dynamical gauge theories later in the volume.
- **Gauging Global Symmetries** continues the operation from $Z[A]$ to a new gauged theory later in this chapter.
- **Obstruction to Gauging** treats anomalies as failures of the gauging operation later in the volume.
- **Wilson Lines** and **’t Hooft Lines** explain extended operators created by dynamical gauge fields later in the volume.

## Research status

The background-versus-dynamical distinction is settled and foundational. It is part of the everyday language of source functionals, gauge theory, response theory, and anomalies.

The research frontier lies in situations where the boundary between redundancy and symmetry becomes subtle: gauge theories with boundaries, asymptotic symmetries, higher-form symmetries, topological gauge fields, gauging non-invertible symmetries, and quantum-gravity constraints on global symmetries.

## Exercises

### Exercise 1: Why a charged scalar is no longer a local observable

In scalar QED, a local gauge transformation acts as

$$
\phi(x)\mapsto e^{iq\lambda(x)}\phi(x),
\qquad
 a_\mu(x)\mapsto a_\mu(x)+\partial_\mu\lambda(x).
$$

Show that $\phi(x)$ is not gauge invariant, while $\phi^*(x)\phi(x)$ is.

<details><summary><strong>Solution</strong></summary>

The field transforms as

$$
\phi(x)\mapsto e^{iq\lambda(x)}\phi(x),
\qquad
\phi^*(x)\mapsto e^{-iq\lambda(x)}\phi^*(x).
$$

Therefore

$$
\phi^*(x)\phi(x)\mapsto
 e^{-iq\lambda(x)}e^{iq\lambda(x)}\phi^*(x)\phi(x)
=\phi^*(x)\phi(x).
$$

The phase of $\phi$ alone is gauge dependent, so $\phi(x)$ is not a physical local operator of the gauged theory. The composite $\phi^*\phi$ is gauge invariant and can be a physical local operator.

</details>

### Exercise 2: Total charge from Gauss law

For abelian gauge theory on a compact spatial slice $\Sigma$ with no boundary, use Gauss law

$$
\partial_iE^i=\rho
$$

to show that the total gauge charge of a physical state vanishes.

<details><summary><strong>Solution</strong></summary>

Integrate Gauss law over $\Sigma$:

$$
Q=\int_\Sigma d^{d-1}x\,\rho
=\int_\Sigma d^{d-1}x\,\partial_iE^i.
$$

By the divergence theorem,

$$
Q=\int_{\partial\Sigma} *E.
$$

If $\Sigma$ is compact and has no boundary, $\partial\Sigma=\varnothing$, so the boundary integral vanishes. Hence $Q=0$ on physical states. This is why gauge charge is not like an ordinary global charge on a closed compact space.

</details>

### Exercise 3: Gauging requires anomaly-free background dependence

Suppose a background partition function transforms as

$$
Z[A^g]=Z[A]e^{i\mathcal A[g,A]},
$$

where $\mathcal A[g,A]$ cannot be removed by a local counterterm. Explain why the schematic gauged integral

$$
\int \frac{\mathcal D A}{\operatorname{Vol}(\mathcal G)}Z[A]
$$

is not well-defined.

<details><summary><strong>Solution</strong></summary>

The integral is supposed to sum over gauge-equivalence classes of $A$. If two representatives $A$ and $A^g$ of the same gauge orbit give different phases for the integrand, then the value assigned to that orbit depends on the representative chosen.

Because $\mathcal A[g,A]$ is assumed nonremovable by local counterterms, this is not a scheme artifact. The quotient by gauge transformations is inconsistent. Therefore the symmetry cannot be gauged in the same dimension unless extra degrees of freedom or inflow cancel the anomalous phase.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially §§57, 69–74, and 78. Gauge fields, nonabelian gauge theory, Faddeev–Popov ghosts, BRST symmetry, and background-field gauge.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters 15–17. Nonabelian gauge theory, BRST, external field methods, and renormalization of gauge theories.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters 8, 14, 25, and 34. Gauge invariance, path-integral Ward identities, Yang–Mills theory, and background fields.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” 2015. A modern formulation of global symmetry backgrounds and gauging by summing over classical fields.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapters 2–4. Effective actions, Wilson actions, symmetries, gauge backgrounds, and anomaly matching.

## Version history

- **2026-06-17:** Initial polished page distinguishing background fields from dynamical gauge fields.
