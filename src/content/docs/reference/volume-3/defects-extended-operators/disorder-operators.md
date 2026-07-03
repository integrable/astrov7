---
title: "Disorder Operators"
description: "Disorder operators as path-integral modifications, branch-cut endpoints, dual order parameters, and probes of phases, defects, and generalized symmetry."
sidebar:
  label: "Disorder Operators"
  order: 5
level: Advanced
status: "Polished draft"
source: "Kadanoff–Ceva; Fradkin review; Polyakov Chs. 3–7; Srednicki §§82–93; Gaiotto–Kapustin–Seiberg–Willett."
topics:
  - disorder operators
  - order-disorder duality
  - Kadanoff-Ceva construction
  - branch cuts
  - dual order parameters
  - gauge theory defects
  - monopole operators
  - generalized symmetries
canonicalTopics:
  - disorder-operator
  - order-disorder-duality
  - kadanoff-ceva-disorder-operator
  - defect-endpoint
  - monopole-operator
researchStatus:
  established:
    - "Disorder operators are standard QFT observables defined by prescribing singularities, branch cuts, twisted couplings, or topological defects in the path integral."
    - "The Kadanoff–Ceva disorder operator in the two-dimensional Ising model is the canonical example: a pair of insertions is defined by flipping couplings along a path between dual-lattice points."
  active:
    - "Modern work uses disorder operators to diagnose generalized symmetries, dualities, topological phases, entanglement structure, and strongly coupled phases beyond ordinary Landau order."
---

## Summary

An order operator measures a field configuration. A disorder operator changes the class of field configurations being summed over.

That slogan is slightly too cute, but it is the right starting point. The magnetization operator $\sigma(x)$ in the Ising model is an order operator: it is a local function of the spin at $x$. A Kadanoff–Ceva disorder operator $\mu(\tilde x)$ is different. A pair $\mu(\tilde x)\mu(\tilde y)$ is defined by drawing a path $\Gamma$ on the dual lattice from $\tilde x$ to $\tilde y$ and flipping the sign of the Ising couplings on all bonds crossed by $\Gamma$. The correlator is the ratio of the modified partition function to the original one:

$$
\langle \mu(\tilde x)\mu(\tilde y)\rangle=\frac{Z[\Gamma]}{Z}.
$$

The drawn path is auxiliary. Moving it without crossing an order operator is a change of variables, so the physical insertions are the endpoints. This is the model example of a disorder operator: the local insertion is defined by a topological or singular prescription in its neighborhood, rather than by a polynomial in microscopic fields.

<figure class="doc-figure" style="--figure-width: 62rem;">

![Disorder operator diagram contrasting ordinary order insertions, which multiply each configuration by a functional, with disorder insertions, which modify boundary conditions, singular data, or sectors in the path integral.](/figures/symmetry-anomalies-topology/disorder-operator-path-integral.svg)

<figcaption>

An order insertion multiplies each configuration by a functional. A disorder insertion changes which configurations, boundary conditions, singularities, or sectors are summed over. Ising seams, magnetic flux insertions, and dual order parameters are three standard faces of the same idea.

</figcaption>
</figure>

Disorder operators are not rare creatures hiding in solvable lattice models. ’t Hooft lines, monopole operators, vortex creation operators, twist fields, branch-point twist fields, and many surface defects are all disorder operators in this broad sense. They are indispensable because some phases have no simple local order parameter, while their dual defects or fluxes have clean long-distance behavior.

## Prerequisites

You should know [Order Parameters](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/order-parameters/), [Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/), [’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/), and [Surface Operators](/symmetry-anomalies-topology/defects-extended-operators/surface-operators/). It helps to have seen [Gauging Finite Symmetries: Preview](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-finite-symmetries-preview/) and [Topological Charge Conservation](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/topological-charge-conservation/).

## Setup and conventions

The word "operator" has two uses in this page.

In Hamiltonian language, an operator acts on the Hilbert space. In Euclidean path-integral language, an operator insertion is a local, extended, or defect-like instruction that changes the integral. For ordinary local fields these descriptions match in familiar ways. For disorder operators the path-integral definition is often the cleaner one.

We use the following vocabulary.

An **order operator** is defined directly as a function, functional, or local composite of the fundamental variables. Examples include $\sigma_i$ in the Ising model, $\phi(x)$ in a scalar theory, and a Wilson loop $\operatorname{Tr}_R P\exp(i\oint A)$ in a gauge field.

A **disorder operator** is defined by modifying boundary conditions, singularities, transition functions, couplings, defects, or background fields. Examples include Kadanoff–Ceva disorder fields, ’t Hooft lines, monopole operators, vortex creation operators, and twist fields.

A **cut** or **seam** is auxiliary data used to draw the modification. The true operator is usually the endpoint or boundary of the cut, or the specified singularity along a submanifold.

:::note[Convention-sensitive source note]
Different communities use "disorder operator" with different breadth. In lattice statistical mechanics it often means the dual of an order parameter, as in Kadanoff–Ceva. In gauge theory it often means an operator defined by singular boundary conditions, as for ’t Hooft operators. In CFT it may overlap with twist fields. This page uses the broader QFT meaning: an observable defined by modifying the allowed field configurations or background data near its support.
:::

## The Kadanoff–Ceva construction

The cleanest first example is the two-dimensional ferromagnetic Ising model on a square lattice,

$$
Z=\sum_{\{\sigma\}}\exp\left(K\sum_{\langle ij\rangle}\sigma_i\sigma_j\right),
\qquad \sigma_i=\pm 1,
$$

where $K=J/T$. Let $\tilde x$ and $\tilde y$ be dual-lattice sites. Choose a dual-lattice path $\Gamma$ from $\tilde x$ to $\tilde y$. The path crosses a collection of direct-lattice bonds. Define $Z[\Gamma]$ by flipping the sign of the coupling on those bonds:

$$
Z[\Gamma]
=\sum_{\{\sigma\}}\exp\left(K\sum_{\langle ij\rangle}\tau_{ij}\sigma_i\sigma_j\right),
$$

where

$$
\tau_{ij}=\begin{cases}
-1,& \langle ij\rangle \text{ crosses }\Gamma,\\
+1,& \text{otherwise.}
\end{cases}
$$

Then define

$$
\langle \mu(\tilde x)\mu(\tilde y)\rangle=\frac{Z[\Gamma]}{Z}.
$$

The notation suggests that $\mu(\tilde x)$ is a local operator at the dual-lattice point $\tilde x$. But the definition used an entire path $\Gamma$. The magic is that the path is not physical. If $\Gamma$ is deformed to another path $\Gamma'$ with the same endpoints, the changed set of signs can be undone by flipping spins inside the region swept between the two paths. Thus the correlator depends only on the endpoints, not on the drawn seam.

This is the basic pattern repeated all over QFT:

$$
\text{local insertion}
\quad\Longleftrightarrow\quad
\text{endpoint of an auxiliary topological cut}.
$$

The line looks nonlocal. The endpoint is local.

## The background-field version

The same construction can be written more invariantly using a background $\mathbb Z_2$ gauge field. Put $\tau_{ij}=\pm 1$ on links and write

$$
Z[\tau]=\sum_{\{\sigma\}}
\exp\left(K\sum_{\langle ij\rangle}\tau_{ij}\sigma_i\sigma_j\right).
$$

A local spin redefinition

$$
\sigma_i\mapsto \lambda_i\sigma_i,
\qquad
\tau_{ij}\mapsto \lambda_i\tau_{ij}\lambda_j,
\qquad \lambda_i=\pm 1,
$$

leaves the partition function invariant. The gauge-invariant data are the plaquette fluxes

$$
\prod_{\langle ij\rangle\in \partial p}\tau_{ij}.
$$

A disorder insertion at a dual plaquette is a plaquette with flux $-1$. A pair of insertions must be connected by a string of negative links, but the location of the string is gauge choice; only the endpoints are gauge-invariant.

This notation reveals the structural meaning. A disorder operator couples the system to a singular or topologically nontrivial background for a symmetry. In this case the symmetry is the ordinary spin-flip $\mathbb Z_2$ symmetry. Later, generalized symmetries use the same idea with higher-form backgrounds.

## Order-disorder duality

The Ising model has Kramers–Wannier duality. Roughly, low-temperature domain-wall loops in one description map to high-temperature expansion loops in the dual description. The dual coupling $K^*$ satisfies

$$
e^{-2K^*}=\tanh K.
$$

Under this duality, the spin order operator maps to the disorder operator:

$$
\langle \sigma(x)\sigma(y)\rangle_{K}
=
\langle \mu(\tilde x)\mu(\tilde y)\rangle_{K^*}
$$

up to the usual boundary-condition and thermodynamic-limit qualifications.

This is more than a computational trick. It says that what looks ordered in one description can look like defect condensation in another. In the low-temperature Ising phase,

$$
\langle \sigma\rangle\ne 0,
\qquad
\langle \mu\rangle=0.
$$

In the high-temperature disordered phase,

$$
\langle \sigma\rangle=0,
\qquad
\langle \mu\rangle\ne 0.
$$

At criticality, both $\sigma$ and $\mu$ become scaling operators. In the continuum Ising CFT,

$$
h_\sigma=\bar h_\sigma=h_\mu=\bar h_\mu=\frac{1}{16},
$$

so the scaling dimension is

$$
\Delta_\sigma=\Delta_\mu=\frac{1}{8}.
$$

The equality of dimensions is not an accident; it is the fixed-point shadow of order-disorder duality.

## Monodromy with order operators

The disorder operator is local, but it is not mutually local with every operator. If a spin operator $\sigma(x)$ crosses the Kadanoff–Ceva seam, its correlation function changes sign. Equivalently, carrying $\sigma$ around $\mu$ gives a monodromy:

$$
\sigma\text{ around }\mu
\quad\Longrightarrow\quad
\sigma\mapsto -\sigma.
$$

This statement is the continuum residue of the branch cut. The seam can be moved, but it cannot be removed once an order operator winds around an endpoint.

This is why disorder operators are best understood with the full defect network, not just by asking whether they are local in the naive sense. Locality in QFT is really a statement about all possible operator exchanges, braidings, and cuts.

In two-dimensional Ising language, the product of an order and a disorder field at nearby primal/dual sites produces a fermionic field. Schematically,

$$
\psi \sim \sigma\mu.
$$

This relation is the seed of many later constructions: Jordan–Wigner fermions in the quantum Ising chain, parafermions in $\mathbb Z_N$ clock models, and bosonization-like dualities.

## Disorder operators in gauge theory

The previous pages already introduced two standard gauge-theory disorder operators.

An [’t Hooft line](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/) in four-dimensional gauge theory is defined by imposing magnetic flux through a small sphere linking the line:

$$
\frac{1}{2\pi}\int_{S^2_{\rm link}}F=m.
$$

A [surface operator](/symmetry-anomalies-topology/defects-extended-operators/surface-operators/) can be defined by imposing a prescribed monodromy around a codimension-two surface:

$$
A\sim \alpha\,d\varphi+\cdots.
$$

Neither operator is merely a polynomial in local fields. They are instructions about which gauge bundles, singularities, or holonomies are allowed near the support of the defect.

In three-dimensional gauge theories, monopole operators are local disorder operators. Around a point insertion $x$, impose magnetic flux through a small linking sphere:

$$
\frac{1}{2\pi}\int_{S^2_x}F=m.
$$

The operator is local because the linking sphere surrounds a point. But its definition is topological and singular. The path integral sums over fields on the punctured space with prescribed flux at the puncture.

This is the same grammar as Kadanoff–Ceva: remove a small neighborhood of the insertion, impose nontrivial boundary data on the linking sphere, and integrate over everything else.

## Codimension and linking spheres

Disorder operators are naturally classified by their support and by the linking manifold that detects their boundary condition.

For an operator supported on a submanifold $D^p\subset M^d$, the transverse linking sphere has dimension

$$
S^{d-p-1}_{\rm link}.
$$

Examples:

| spacetime dimension | support | linking sphere | example |
|---:|---:|---:|---|
| $d=2$ | point | $S^1$ | Ising disorder field, twist field |
| $d=3$ | point | $S^2$ | monopole operator |
| $d=3$ | line | $S^1$ | vortex line |
| $d=4$ | line | $S^2$ | ’t Hooft line |
| $d=4$ | surface | $S^1$ | surface operator with monodromy |

This table is a little theorem disguised as a cheat sheet: the local definition of a disorder operator is usually data on the linking sphere.

That data can be a group element, a conjugacy class, a magnetic charge, a background-bundle transition function, a holonomy, a branch-cycle permutation, a spin-structure modification, or a higher-form flux.

## Disorder as an order parameter for dual phases

Disorder operators often diagnose phases more cleanly than ordinary order operators.

In an ordered Ising phase, a pair of disorder insertions creates a domain-wall-like seam with a tension. The two-point function decays exponentially:

$$
\langle \mu(\tilde x)\mu(\tilde y)\rangle
\sim e^{-T_{\rm wall}|\tilde x-\tilde y|}.
$$

In the disordered phase, domain walls proliferate. The extra seam costs only endpoint-local energy at long distance, so

$$
\langle \mu(\tilde x)\mu(\tilde y)\rangle
\to |\langle \mu\rangle|^2.
$$

In gauge theory the analogous statements are encoded by Wilson and ’t Hooft loop expectation values. Very schematically:

| phase | Wilson loop | ’t Hooft loop |
|---|---|---|
| confinement of electric charges | area law | perimeter law |
| Higgs/screening of electric charges | perimeter law | area-like or nontrivial dual behavior |
| Coulomb phase | power-law behavior | power-law behavior |

The exact statement depends on spacetime dimension, matter content, global form, center symmetry, and whether line operators are genuine. The moral is robust: disorder operators expose dual condensates and topological response that local order parameters may miss.

## Relation to twist operators

Every twist operator is a disorder operator in the broad sense used here. A twist insertion forces fields to return transformed after going around it:

$$
\mathcal O(e^{2\pi i}z)=g\cdot \mathcal O(z).
$$

The next page treats this case separately because twist operators have their own standard vocabulary: symmetry defects, branch cuts, orbifolds, replica twists, branch-point twist fields, and conical singularities.

For now, note the shared pattern:

$$
\text{disorder operator}
\quad = \quad
\text{endpoint, boundary, or singular core of a cut/defect/background}.
$$

## Relation to generalized symmetries

Modern generalized-symmetry language turns many disorder operators into charged operators, symmetry generators, or endpoints of topological defects.

For an ordinary finite symmetry $G$, a codimension-one topological symmetry defect $U_g(\Sigma)$ acts on local operators when swept across them. If $U_g(\Sigma)$ can end on a codimension-two object, that endpoint is a twist/disorder defect. If it cannot end, the obstruction may be a sign of an anomaly, a selection rule, or a missing charged object.

For a $q$-form symmetry, the charged operators have dimension $q$. The symmetry operators have codimension $q+1$. A disorder operator may be defined by imposing a singular background for this higher-form symmetry or by creating the endpoint of a higher-form symmetry defect.

This is why disorder operators are not merely historical curiosities from the Ising model. They are one of the practical languages in which generalized symmetry becomes visible.

## Common pitfalls

**Pitfall 1: thinking the cut is the operator.**

The cut is usually an auxiliary convention. The physical operator is the endpoint, boundary, or prescribed singularity. If moving the cut changes correlators, it should do so only when the move crosses charged operators or nontrivial topology.

**Pitfall 2: assuming every disorder operator is local.**

Some disorder operators are local, such as the two-dimensional Ising $\mu$ field or a three-dimensional monopole operator. Others are extended, such as ’t Hooft lines and surface operators. The support dimension matters.

**Pitfall 3: confusing disorder with randomness.**

A disorder operator is not necessarily about quenched disorder or random couplings. The word means that the operator creates a defect, flux, branch cut, or dual disturbance.

**Pitfall 4: using gauge-noninvariant language as if it were physical.**

In gauge theory, a singular gauge potential is not itself the invariant definition. The invariant data are fluxes, holonomies, bundle transition functions, cocharacters, and allowed line/operator spectra.

**Pitfall 5: forgetting global form.**

The allowed disorder operators depend on the global structure of the symmetry or gauge group. The Lie algebra alone does not determine which magnetic charges, twist defects, or line operators are genuine.

## Relation to nearby pages

[’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/) are magnetic disorder line operators. [Surface Operators](/symmetry-anomalies-topology/defects-extended-operators/surface-operators/) generalize this to codimension-two monodromy defects. [Twist Operators](/symmetry-anomalies-topology/defects-extended-operators/twist-operators/) are the symmetry-branch-cut case.

[Higher-Form Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/higher-form-symmetries/) recasts many disorder operators as charged extended operators or as generators/endpoints of topological defects. [Gauging Finite Symmetries: Preview](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-finite-symmetries-preview/) explains why twisted sectors are forced when one sums over background bundles.

In the opposite direction, [Order Parameters](/symmetry-anomalies-topology/spontaneous-symmetry-breaking/order-parameters/) explains ordinary Landau order. Disorder operators become powerful precisely when Landau order is not the whole story.

## Research status

The foundational examples are settled: Kadanoff–Ceva disorder fields, ’t Hooft operators, monopole operators, vortex creation operators, and branch cuts in orbifolds are standard tools.

The active frontier is not whether disorder operators exist. It is how to organize them in strongly coupled theories: line and surface operator categories, noninvertible defects, higher-form and higher-group symmetries, dualities, topological phases, fermionic systems, and entanglement diagnostics. In many modern papers, the most illuminating observable is not a local field but a defect operator whose definition asks a topological question of the path integral.

## Exercises

### Exercise 1: Path independence in the Ising construction

Let $\Gamma$ and $\Gamma'$ be two paths on the dual square lattice with the same endpoints. Show that the corresponding disorder correlators are equal when there are no spin insertions in the region swept between the two paths.

<details><summary><strong>Solution</strong></summary>

The two choices differ by flipping the sign of $\tau_{ij}$ on the boundary of a region $R$ of the direct lattice. Perform the change of variables

$$
\sigma_i\mapsto -\sigma_i
$$

for all sites $i$ inside $R$, leaving spins outside $R$ unchanged. Bonds with one endpoint inside and one outside acquire an extra minus sign; these are precisely the bonds whose $\tau_{ij}$ differs between $\Gamma$ and $\Gamma'$. Since the spin sum is over all configurations, the change of variables leaves the partition function invariant. Therefore $Z[\Gamma]=Z[\Gamma']$.

If a spin insertion lies inside $R$, the same spin redefinition changes the sign of that insertion. This is the origin of the monodromy between $\sigma$ and $\mu$.

</details>

### Exercise 2: Monodromy of the order operator

Use the previous exercise to argue that taking an Ising spin operator $\sigma$ around a disorder operator $\mu$ changes the correlator by a sign.

<details><summary><strong>Solution</strong></summary>

Moving the disorder seam across a spin insertion $\sigma_i$ is equivalent to a spin redefinition on a region containing $i$. The Boltzmann weights are unchanged, but $\sigma_i\mapsto -\sigma_i$. Thus a closed motion of $\sigma$ around the endpoint of the seam detects whether the spin has crossed the seam once. Crossing once gives a factor $-1$.

Equivalently, the disorder insertion creates a $\mathbb Z_2$ branch point for the order field:

$$
\sigma\mapsto -\sigma.
$$

</details>

### Exercise 3: Linking sphere of a monopole operator

In three-dimensional compact $U(1)$ gauge theory, define a local monopole operator $M_m(x)$ by

$$
\frac{1}{2\pi}\int_{S^2_x}F=m.
$$

Why is this a local disorder operator rather than a line operator?

<details><summary><strong>Solution</strong></summary>

The support is the point $x$. The two-sphere $S^2_x$ is a small sphere linking the point in three-dimensional spacetime. The operator is defined by a boundary condition on fields near $x$, not by a line integral along an extended curve. It is therefore local in its support but disorder-like in its definition.

The same logic in four spacetime dimensions gives an ’t Hooft line, because a line has transverse linking sphere $S^2$.

</details>

### Exercise 4: Disorder condensation

Explain why a disorder operator can have a nonzero expectation value in a phase with no ordinary order parameter.

<details><summary><strong>Solution</strong></summary>

A disorder expectation value measures the long-distance cost of inserting a defect. If the phase is a condensate of such defects, adding one more distant pair costs only finite endpoint energy. Then

$$
\langle \mu(x)\mu(y)\rangle\to |\langle\mu\rangle|^2
$$

at large separation. This can happen even if every local field charged under the original symmetry has zero expectation value. The disorder operator is an order parameter for a dual description, not necessarily for the original microscopic variables.

</details>

## References

- L. P. Kadanoff and H. Ceva, "Determination of an Operator Algebra for the Two-Dimensional Ising Model," *Physical Review B* **3**, 3918 (1971).
- E. Fradkin, "Disorder Operators and their Descendants," arXiv:1610.05780.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on strong coupling, instantons, topology of gauge fields, and loop dynamics.
- M. Srednicki, *Quantum Field Theory*, §§82–93.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, "Generalized Global Symmetries," arXiv:1412.5148.
- J. B. Kogut, "An Introduction to Lattice Gauge Theory and Spin Systems," *Reviews of Modern Physics* **51**, 659 (1979).

## Version history

- 2026-06-19: Initial polished draft.
