---
title: "Defects Versus Operators"
description: "Explains the relation between classical defects, extended operator insertions, defect Hilbert spaces, and topological symmetry operators in nonperturbative QFT."
sidebar:
  label: "Defects Versus Operators"
  order: 10
level: Advanced
status: "Polished draft"
source: "Gaiotto, Kapustin, Seiberg, and Willett; Shifman; Manton and Sutcliffe; Srednicki; Polyakov; Nakahara."
topics:
  - defects
  - extended operators
  - disorder operators
  - topological defects
  - higher-form symmetries
  - Wilson lines
  - "’t Hooft lines"
  - defect Hilbert spaces
canonicalTopics:
  - nonperturbative-qft
  - defects
  - extended-operators
  - higher-form-symmetries
  - topological-defects
researchStatus:
  established:
    - "Classical defect configurations, extended operator insertions, and defect Hilbert spaces are related but distinct notions; the distinction is essential in gauge theories and theories with higher-form symmetries."
  active:
    - "Strongly coupled defect dynamics, noninvertible defects, defect operator algebras, and categorical descriptions of topological defects remain active research areas."
---

## Summary

The word **defect** is annoyingly overloaded, but the overload is useful. In nonperturbative QFT, it can mean at least three closely related things:

1. a **classical field configuration** with nontrivial boundary behavior, such as a kink, vortex, domain wall, or monopole;
2. an **operator insertion** supported on a submanifold, such as a Wilson line, ’t Hooft line, twist operator, surface operator, or disorder operator;
3. a **modification of the theory along a submanifold**, giving a new Hilbert space, interface, boundary condition, or defect sector.

Those meanings are not interchangeable. A classical vortex is a field configuration. A Wilson loop is an operator. A domain wall can be a classical solution, an interface, or a state in a sector with different boundary conditions. A symmetry defect can be a topological operator. The correct interpretation depends on how the object is inserted, what boundary conditions are imposed, whether it is dynamical or external, and whether auxiliary choices such as branch cuts or Dirac surfaces are physical.

<figure class="doc-figure" style="--figure-width: 58rem;">

![A schematic dictionary relating classical defect configurations, operator insertions, Hilbert-space defect sectors, and symmetry/topology data.](/figures/nonperturbative-qft/defects-versus-operators-dictionary.svg)

<figcaption>

A defect can be a field configuration, an insertion $V(C)$ in the path integral, an operator acting at fixed time, or a modification of the Hilbert space when stretched along time. Topological symmetry operators $U_g(M)$ detect charged defects by linking or crossing them.

</figcaption>
</figure>

This page is a dictionary. Its goal is to prevent category errors before the next chapter starts using instantons, theta sectors, and fermion zero modes. Nonperturbative QFT has plenty of genuine difficulty; we do not need extra chaos from calling four different things “the defect” without saying which one we mean.

## Prerequisites

You should know [Finite-Energy Boundary Conditions](/nonperturbative-qft/solitons-defects-extended-configurations/finite-energy-boundary-conditions/), [Domain Walls](/nonperturbative-qft/solitons-defects-extended-configurations/domain-walls/), [Vortices](/nonperturbative-qft/solitons-defects-extended-configurations/vortices/), [Monopoles](/nonperturbative-qft/solitons-defects-extended-configurations/monopoles/), [Wilson Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/wilson-loop-diagnostics/), and [’t Hooft Loop Diagnostics](/nonperturbative-qft/order-parameters-diagnostics/thooft-loop-diagnostics/).

It also helps to have seen the language of higher-form symmetries: a $q$-form symmetry has charged $q$-dimensional operators and topological symmetry operators of codimension $q+1$. This page uses the idea, but does not assume the full formalism.

## Core idea

The cleanest distinction is this:

$$
\begin{array}{ccl}
\text{configuration} &:& \text{a field history or field profile being integrated over},\\
\text{operator} &:& \text{a prescribed insertion in the path integral or Hilbert space},\\
\text{defect theory} &:& \text{a modified QFT living on or across a submanifold}.
\end{array}
$$

A kink in a scalar theory is often introduced as a static classical solution. If one quantizes the kink’s collective coordinate, the kink becomes a particle-like state in a topological sector. In a Euclidean path integral, one may force a kink by imposing boundary conditions at temporal infinity. In a two-dimensional formulation, one may also use a disorder operator or twist field that changes boundary conditions across a line. These are related descriptions, not identical definitions.

A Wilson line is different. It is not usually a classical solution. It is an insertion

$$
W_R(C)
=
\frac{1}{\dim R}\operatorname{tr}_R\,\mathcal P\exp\!\left(-i\oint_C A\right),
$$

supported on a curve $C$. If $C$ runs along Euclidean time, it describes an external heavy probe charge. If $C$ lies in a time slice, it acts as an extended operator on the Hilbert space. If $C$ is closed in Euclidean spacetime, it is an observable whose large-size behavior can diagnose phases.

The physics changes when we change the role.

## Setup and conventions

Work in $d$ Euclidean spacetime dimensions unless stated otherwise. A defect or extended operator supported on a $q$-dimensional submanifold $C_q$ will be denoted

$$
V(C_q).
$$

A topological symmetry operator supported on a closed codimension-$(q+1)$ manifold $M_{d-q-1}$ will be denoted

$$
U_g(M_{d-q-1}),
$$

where $g$ labels an element of a symmetry group. Topological means that $M_{d-q-1}$ can be deformed without changing correlation functions, except when it crosses charged operators.

A path integral with a prescribed defect can be written schematically as

$$
\langle \mathcal O\rangle_D
=
\frac{1}{Z_D}
\int_{\mathcal C_D}\mathcal D\Phi\,
\mathcal O[\Phi] \exp\!\left[-S_E[\Phi]-S_D[\Phi|_D]\right].
$$

Here $D$ denotes the defect support, $S_D$ denotes possible defect-localized terms, and $\mathcal C_D$ indicates that the allowed fields may obey singularity, monodromy, flux, or boundary conditions near $D$. This notation is deliberately broad: some defects are best described by an insertion, others by a restricted field space, and many by both.

In Lorentzian signature, a defect extended along time defines a defect Hilbert space or a sector,

$$
\mathcal H_D,
$$

while a defect placed at a fixed time defines an operator acting on the ordinary Hilbert space,

$$
\widehat V(C_q):\mathcal H\to\mathcal H.
$$

Those are different statements. Confusing them is a reliable way to produce fog.

## Three meanings of defect

### Classical defect configuration

A **classical defect configuration** is a solution or approximate solution of the field equations with nontrivial boundary behavior. Typical examples are:

| Object | Spatial codimension | Classical description | Quantum role |
|---|---:|---|---|
| Kink | 1 | Field interpolates between two vacua. | Particle-like state in $1+1$ dimensions. |
| Domain wall | 1 | Interface between vacua. | Wall state, interface, or background defect. |
| Vortex/string | 2 | Winding around the defect core. | Flux tube, line defect, or string-like excitation. |
| Monopole | 3 | Magnetic flux through $S^2_\infty$. | Particle-like state, disorder insertion, or magnetic sector. |
| Skyrmion | $n$ in $n$ spatial dimensions | Map from compactified space into a target. | Soliton state carrying topological charge. |

The defining feature is that the defect is part of the field configuration being integrated over or quantized. Its support, size, profile, zero modes, and fluctuations are dynamical unless one freezes them by hand.

### Operator insertion

An **operator defect** is a prescribed insertion in a correlation function. A local operator is supported at a point. A line operator is supported on a curve. A surface operator is supported on a surface. The path integral is not merely “over configurations that happen to contain a defect”; the definition of the observable includes the defect support.

For example, in a gauge theory,

$$
\langle W_R(C)\rangle
=
\frac{1}{Z}\int \mathcal DA\,
\frac{1}{\dim R}\operatorname{tr}_R\,\mathcal P\exp\!\left(-i\oint_C A\right)e^{-S_E[A]}.
$$

The Wilson loop is an insertion. It may be interpreted as the worldline of a heavy external charge, but unless one adds dynamical heavy matter to the theory, the heavy particle is not part of the fluctuating field content.

Disorder operators are often defined by singular behavior around their support. A magnetic line operator, for example, may require the gauge field to have a prescribed magnetic flux around the line. In such cases the operator is defined by a boundary condition in field space rather than by multiplying the integrand by an ordinary function.

### Defect theory or interface

A **defect theory** modifies the QFT along a submanifold. It may carry its own degrees of freedom, couplings, anomaly inflow, boundary condition, or topological field theory. A codimension-one defect may separate two different bulk theories,

$$
\text{QFT}_L \quad | \quad \text{defect} \quad | \quad \text{QFT}_R.
$$

A boundary condition is a special case with one side removed. A topological interface is a special case that can be moved without changing correlation functions, unless it crosses operators.

From the Hamiltonian viewpoint, a defect stretched along time changes the Hilbert space. A line defect in $d$ spacetime dimensions gives a quantum-mechanical defect sector. A surface defect gives a lower-dimensional QFT coupled to the bulk. A boundary gives a boundary Hilbert space or boundary state.

## Fixed-time operators versus time-like defects

The same Euclidean-looking support can mean different things depending on its relation to time.

Suppose spacetime is $M_{d-1}\times \mathbb R_\tau$.

If $C_q$ lies inside one time slice,

$$
C_q\subset M_{d-1}\times\{\tau_0\},
$$

then $V(C_q)$ acts on states:

$$
|\Psi_+\rangle
=
\widehat V(C_q)|\Psi_-\rangle.
$$

If $D_q$ includes the Euclidean time direction,

$$
D_q=\mathbb R_\tau\times C_{q-1},
$$

then it defines time evolution in a modified sector. The Hilbert space is not necessarily the same $\mathcal H$ with an operator inserted; it may be a different Hilbert space $\mathcal H_D$.

This distinction is especially important for line operators. A Wilson loop wrapping the Euclidean time circle is a thermal probe. A Wilson line extending along time represents a heavy external source. A Wilson line lying in a spatial slice is an extended operator acting on the Hilbert space. Same formula, different physics. Tiny notation change, big conceptual bill.

## Genuine operators and attached topological data

An operator is often called **genuine** if it can be defined on its support alone, without choosing an auxiliary higher-dimensional surface, branch cut, or framing data. If auxiliary data are required, one must ask whether changing that data changes the correlation function.

A simple schematic distinction is:

$$
\text{genuine }V(C)
\quad\text{versus}\quad
\text{surface-attached }V(C,\Sigma),\qquad \partial\Sigma=C.
$$

In an Ising-like system, a disorder operator can be described by a branch cut ending on the insertion. In a gauge theory, an ’t Hooft line is often described using a Dirac surface ending on the line. The operator is genuine only if the dependence on the auxiliary choice is invisible or topological under the rules of the theory.

This is where global form and matter content matter. In pure $SU(N)$ Yang–Mills theory, the fundamental Wilson line is a genuine line operator. The status of magnetic line operators depends on the chosen global form and allowed line spectrum. In a $PSU(N)=SU(N)/\mathbb Z_N$ theory, the allowed genuine lines differ. The same local Lagrangian density can therefore correspond to different theories once the spectrum of genuine line operators is specified.

This is not pedantry. It affects one-form symmetries, theta parameters, confinement diagnostics, duality maps, and the classification of phases.

## How symmetry operators detect defects

For an ordinary global symmetry, the symmetry operator is supported on a codimension-one surface. Moving that surface past a local operator tells you the charge of the local operator.

For a $q$-form symmetry, the charged objects are $q$-dimensional operators. The symmetry operator is supported on a closed codimension-$(q+1)$ manifold. In favorable abelian cases, the linking relation has the schematic form

$$
U_g(M_{d-q-1})V(C_q)
=
\chi_g(V)^{\operatorname{Link}(M,C)}
V(C_q)U_g(M_{d-q-1}),
$$

where $\chi_g(V)$ is the character by which $V$ transforms. The important words are **linking** and **topological**. The charged operator is detected not by local contact with a current, but by whether the symmetry defect links or crosses it.

This makes Wilson loops, ’t Hooft loops, surface operators, and twist defects natural order parameters for generalized symmetries. It also explains why loop operators are so central in confinement: their long-distance behavior diagnoses whether a one-form symmetry is broken, unbroken, explicitly broken, or screened.

## Classical defects versus quantum insertions

A classical solution does not automatically define a good quantum operator. Several checks are needed.

First, the object must have a well-defined ultraviolet description. A line or surface insertion can require local counterterms supported on the defect. Wilson loops have perimeter divergences. Cusped Wilson loops have cusp anomalous dimensions. Surface operators can have their own renormalization.

Second, the object must be gauge invariant or gauge covariant in a controlled way. A field profile that looks like a monopole in one gauge may require bundle data or singular transition functions to become a gauge-invariant statement.

Third, the object must have a Hilbert-space interpretation. Some finite-energy solitons are states. Some disorder operators create states in sectors with prescribed flux. Some Euclidean saddles, such as instantons, are not Lorentzian particles at all; they are tunneling events in Euclidean spacetime.

Fourth, stability matters. A classically stable defect may decay quantum mechanically if its charge can end on another object, if boundary conditions allow unwinding, or if the theory contains dynamical matter that screens the relevant charge.

## A compact dictionary

| Phrase | Best first interpretation | Typical notation | Main caveat |
|---|---|---|---|
| Local operator | Insertion at a point. | $\mathcal O(x)$ | May require renormalization and mixing. |
| Line operator | Insertion on a curve. | $V(C)$, $W_R(C)$, $T_m(C)$ | May need framing, surface attachment, or endpoint data. |
| Surface operator | Insertion or defect on a surface. | $V(\Sigma)$ | Often has defect-localized counterterms and anomalies. |
| Topological defect | Operator or interface deformable without changing correlators. | $U_g(M)$ | Can fail at boundaries, endpoints, or anomaly inflow. |
| Disorder operator | Insertion defined by singularity or monodromy. | $\mu(x)$, $T_m(C)$ | Auxiliary branch cuts or Dirac surfaces must be handled. |
| Soliton state | Quantum state from a classical finite-energy solution. | $|\text{soliton}\rangle$ | Exists in a sector, not necessarily from a local operator. |
| Interface | Codimension-one modification between theories or phases. | $D_{12}$ | May carry its own degrees of freedom. |
| Boundary condition | Defect at the edge of spacetime. | $B$ | Boundary anomalies and boundary operators matter. |
| Instanton | Euclidean finite-action saddle. | $\Phi_{\rm inst}$ | Not a particle-like operator in Lorentzian time. |

## Example: kink sectors and disorder insertions

In a scalar theory with two vacua $\phi=\pm v$ in $1+1$ dimensions, a kink state is produced by boundary conditions

$$
\phi(x\to -\infty)=-v,
\qquad
\phi(x\to +\infty)=+v.
$$

The kink is a finite-energy configuration in a topological sector. It is not created from the vacuum by a polynomial local operator such as $\phi(x)$, because such an operator does not change the boundary condition at spatial infinity.

A disorder insertion can instead be defined to change the sign of the order parameter across a cut. In Euclidean language, the endpoint of the cut behaves like a local disorder operator, while the cut is an auxiliary defect line. Whether the endpoint is a genuine local operator depends on the topological nature of the cut and on the theory’s operator algebra.

The moral is useful far beyond the Ising model: charged sectors often require nonlocal insertions, boundary-condition changes, or defect lines. Local fields do not create every state.

## Example: Wilson and ’t Hooft lines

In a gauge theory, Wilson and ’t Hooft lines are the basic electric and magnetic probes.

A Wilson line in representation $R$ is

$$
W_R(C)=\frac{1}{\dim R}\operatorname{tr}_R\,\mathcal P\exp\!\left(-i\oint_C A\right).
$$

It couples to electric charge. Its large-loop behavior diagnoses confinement, screening, or Coulomb behavior, depending on the theory and matter content.

An ’t Hooft line is defined magnetically: it prescribes a singular magnetic flux around the line. In a small two-sphere linking the line, the gauge field has a magnetic charge. This is more like a boundary condition than an ordinary multiplication by a function of fields.

The two lines can have nontrivial linking algebra. In simple abelianized language, an electric charge $e$ transported around magnetic charge $m$ produces a phase

$$
\exp(2\pi i\,\langle e,m\rangle).
$$

In nonabelian gauge theory, the precise allowed electric and magnetic charges depend on the global form of the gauge group and on the chosen set of genuine line operators. This data is part of the definition of the quantum theory.

## Example: symmetry walls

For an ordinary discrete global symmetry $G$, one can draw a codimension-one topological defect $U_g(M_{d-1})$ implementing the symmetry element $g$. It is topological because it can move freely unless it crosses a charged operator.

If a local operator $\mathcal O_i(x)$ transforms as

$$
\mathcal O_i\mapsto R_i{}^j(g)\mathcal O_j,
$$

then moving the symmetry wall across $x$ inserts that representation matrix:

$$
U_g(S^{d-1}_x)\mathcal O_i(x)
=
R_i{}^j(g)\mathcal O_j(x).
$$

This picture generalizes to higher-form symmetries, where the symmetry defect links extended operators rather than enclosing local operators. It is one of the cleanest modern ways to organize Wilson lines, ’t Hooft lines, magnetic symmetries, center symmetries, and confinement diagnostics.

## Limitations and caveats

**Not every classical defect is a stable quantum object.** Quantum fluctuations, pair creation, dynamical matter, boundary conditions, and anomalies can change the story.

**Not every extended operator is topological.** Most Wilson loops are metric-dependent. A topological line can be moved freely; a generic physical line cannot.

**Not every defect is genuine.** Some require attached surfaces or endpoint operators. The allowed set of genuine operators is theory data.

**Gauge symmetry is redundancy, not a physical global symmetry.** Charged operators under gauge transformations are not physical observables unless completed by Wilson lines, boundary data, dressing, or other gauge-invariant constructions.

**A Euclidean saddle is not automatically an operator.** Instantons are saddle configurations contributing to path integrals. Their effects can often be represented by induced local or multilocal interactions after integrating over zero modes, but the instanton itself is not simply a particle insertion.

## Common mistakes

**Mistake 1: “The soliton is the operator.”** Usually the soliton is a state or field configuration. An operator that creates it may be nonlocal, disorder-like, or defined only after specifying boundary conditions.

**Mistake 2: “A defect line is topological because I drew it thin.”** Thin in a diagram does not mean topological. A Wilson line in a confining gauge theory is certainly thin on paper, but its expectation value depends on its geometry.

**Mistake 3: “The Lagrangian determines all line operators.”** The local Lagrangian does not always determine the global form of the gauge group, allowed bundles, or genuine line spectrum. Those choices can define distinct theories.

**Mistake 4: “Auxiliary surfaces are unphysical, so ignore them.”** The right question is whether changing the auxiliary surface changes correlation functions. If it does, the surface is not harmless.

**Mistake 5: “A defect extended in time is just an operator insertion.”** It may instead define a new Hilbert space, a superselection sector, a boundary condition, or a coupled lower-dimensional system.

## Research status

- **Established:** The distinction between classical configurations, operator insertions, and Hilbert-space sectors is standard and indispensable in semiclassical soliton physics, gauge theory, lattice gauge theory, and the modern theory of higher-form symmetries.
- **Established:** Wilson, ’t Hooft, Polyakov, twist, and disorder operators are nonperturbative probes whose long-distance behavior diagnoses phases and symmetry realization.
- **Active:** Defects in strongly coupled CFTs, noninvertible topological defects, categorical symmetry, defect fusion, and anomaly inflow are active research areas.
- **Caveat:** The same word “defect” is used differently in high-energy theory, condensed matter, statistical mechanics, and mathematics. Always ask: field configuration, insertion, interface, or sector?

## Exercises

### Exercise 1: Fixed-time operator or defect Hilbert space?

Let spacetime be $M_{d-1}\times\mathbb R_\tau$. A line insertion $L$ is supported either on a closed curve $C\subset M_{d-1}$ at fixed Euclidean time or on $\mathbb R_\tau\times\{p\}$ for a point $p\in M_{d-1}$. Explain the Hilbert-space interpretation in the two cases.

<details>
<summary><strong>Solution</strong></summary>

If $L$ is supported on a curve $C$ at fixed time, it is an operator $\widehat L(C)$ acting on the Hilbert space $\mathcal H$ associated with $M_{d-1}$.

If $L$ is supported on $\mathbb R_\tau\times\{p\}$, it is present throughout time evolution. It defines a modified sector or defect Hilbert space $\mathcal H_L$, usually interpreted as the Hilbert space of the QFT in the presence of a static external defect at $p$.

</details>

### Exercise 2: Linking and a one-form charge

Assume a four-dimensional theory has a $\mathbb Z_N$ one-form symmetry generated by topological surface operators $U_k(M_2)$, with $k\in\mathbb Z_N$. A line operator $V(C)$ has charge $q\in\mathbb Z_N$ if

$$
U_k(M_2)V(C)
=
\exp\!\left(\frac{2\pi i kq}{N}\operatorname{Link}(M_2,C)\right)
V(C)U_k(M_2).
$$

What happens if $M_2$ is deformed without crossing $C$? What happens if it crosses $C$ once?

<details>
<summary><strong>Solution</strong></summary>

If $M_2$ is deformed without crossing $C$, the linking number does not change, so the correlation function is unchanged. This is the topological nature of the symmetry operator.

If $M_2$ crosses $C$ once, the linking number changes by $\pm1$, depending on orientation. The correlation function is multiplied by

$$
\exp\!\left(\pm\frac{2\pi i kq}{N}\right).
$$

That phase is the one-form charge of the line operator.

</details>

### Exercise 3: Why a local scalar cannot create a kink sector

In a $1+1$ dimensional scalar theory with vacua $\phi=\pm v$, define kink boundary conditions by

$$
\phi(-\infty)=-v,
\qquad
\phi(+\infty)=+v.
$$

Explain why acting on the vacuum with a polynomial local operator $P(\phi(x))$ cannot create a single kink state in infinite volume.

<details>
<summary><strong>Solution</strong></summary>

A polynomial local operator changes the field only in a bounded region around its insertion. It does not change the boundary condition at spatial infinity. The vacuum sector has the same vacuum at both infinities, while the kink sector has different vacua at the two ends. Since the sector label is determined by boundary data at infinity, a local polynomial cannot change it. Creating a single kink requires boundary-condition-changing, disorder-like, or nonlocal data.

</details>

## References

### Standard first pass

- M. Shifman, *Advanced Topics in Quantum Field Theory*, especially the discussions of phases of gauge theories, kinks, domain walls, vortices, monopoles, Skyrmions, instantons, and one-form anomalies.
- M. Srednicki, *Quantum Field Theory*, for Wilson loops, lattice theory, confinement, solitons, monopoles, instantons, theta vacua, and quarks with theta vacua.
- N. Manton and P. Sutcliffe, *Topological Solitons*, for classical solitons, moduli spaces, and soliton dynamics.

### Modern symmetry language

- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for higher-form symmetries, charged extended operators, symmetry defects, and the distinction between genuine and surface-attached operators.
- E. Witten, “Dyons of Charge $e\theta/2\pi$,” for theta angles and electric-magnetic charge structure.
- A. Kapustin and N. Seiberg, “Coupling a QFT to a TQFT and Duality,” for global aspects of gauge theories and line operators.

### Geometry and topology background

- M. Nakahara, *Geometry, Topology and Physics*, for homotopy, bundles, monopoles, instantons, and topological classification.
- A. M. Polyakov, *Gauge Fields and Strings*, for strong-coupling, instanton, confinement, loop, and gauge-string perspectives.

## Version history

- **2026-06-27:** Initial polished draft. Added as the closing page of the Solitons, Defects, and Extended Field Configurations chapter.
