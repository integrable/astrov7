---
title: "Gauging Global Symmetries"
description: "Explains gauging as summing or integrating over background symmetry fields, including anomaly tests, gauge-field choices, finite-group gauging, residual symmetries, and common misconceptions."
sidebar:
  label: "Gauging Global Symmetries"
  order: 5
level: Graduate
status: "Polished draft"
source: "Srednicki §§57, 69–74 on gauge fields and BRST; Weinberg Vol. II Chs. 15–17 on gauge theory and external fields; Gaiotto–Kapustin–Seiberg–Willett on gauging global symmetries by summing over backgrounds."
topics:
  - gauging
  - global symmetries
  - background fields
  - gauge redundancy
  - finite group gauging
  - anomaly obstruction
  - orbifolds
canonicalTopics:
  - gauging-global-symmetry
  - anomaly-obstruction-to-gauging
  - finite-group-gauging
  - gauge-field-path-integral
  - orbifold
  - residual-symmetry
researchStatus:
  established:
    - "Gauging an anomaly-free global symmetry means promoting its background field to a summed-over dynamical gauge field, with gauge redundancy and appropriate local or topological action."
  active:
    - "Modern generalizations include gauging higher-form symmetries, finite higher-group backgrounds, non-invertible gauging operations, relative QFT, and symmetry TFT boundary-condition changes."
---

## Summary

To **gauge** a global symmetry is to stop treating its background field as a fixed probe and instead sum over it as part of the quantum theory.

For a continuous symmetry group $G$, the background generating functional is

$$
Z_{\mathcal T}[A].
$$

Gauging schematically produces a new theory

$$
Z_{\mathcal T/G}
=\sum_{[P\to M]}
\int_{\mathcal A(P)/\mathcal G(P)}\mathcal D A\;
Z_{\mathcal T}[P,A]\,e^{iS_{\text{gauge}}[P,A]+iS_{\text{top}}[P,A]}.
$$

For a finite group $G$, there is no Lie-algebra-valued gauge field. Gauging means summing over flat $G$-bundles:

$$
Z_{\mathcal T/G}(M)
=\sum_{[P\to M]}
\frac{1}{|\operatorname{Aut}(P)|}\,Z_{\mathcal T}[M;P]e^{iS_{\text{top}}[P]}.
$$

<figure class="doc-figure" style="--figure-width: 52rem;">

![A diagram showing gauging as a sequence: start with a background-field functional, choose global form and anomaly-free data, then sum over backgrounds to obtain a new theory with gauge redundancy and new operators.](/figures/symmetry-anomalies-topology/gauging-global-symmetry-sum.svg)

<figcaption>

Gauging starts from the background-field functional $Z[A]$, checks that it is gauge invariant as a function of background data, chooses global and topological data, and then sums over gauge-equivalence classes of backgrounds. The output is a new QFT, not merely the old QFT with a notation change.

</figcaption>
</figure>

This page explains the operation in ordinary zero-form language. Later pages will generalize it to finite symmetries, higher-form symmetries, quotienting, orbifolds, dualities, and symmetry TFT.

## Prerequisites

Read the previous three pages in this chapter:

- [Sources and Background Fields](/symmetry-anomalies-topology/background-fields-and-gauging/sources-and-background-fields/),
- [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/),
- [Global Form of Symmetry Groups](/symmetry-anomalies-topology/background-fields-and-gauging/global-form-of-symmetry-groups/).

You should also be comfortable with [Ward Identities: Path-Integral Form](/symmetry-anomalies-topology/noether-currents-ward-identities/ward-identities-path-integral-form/) and [Background Fields versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/).

Gauge fixing, Faddeev–Popov ghosts, BRST symmetry, and the physical Hilbert space of gauge theories are developed later in the Gauge Redundancy and BRST chapter. This page explains the conceptual operation before the quantization technology.

## Core idea

A background field is a source. A gauged field is summed over.

Before gauging, a theory $\mathcal T$ with global symmetry $G$ assigns a partition function to each background $G$-field:

$$
(P,A)\quad\longmapsto\quad Z_{\mathcal T}[P,A].
$$

Here $P\to M$ is a principal $G$-bundle and $A$ is a connection when $G$ is continuous. If $G$ is finite, $P$ is a flat discrete background.

Gauging constructs a new theory by summing over these backgrounds. This operation has three immediate consequences.

First, transformations that were global symmetries of $\mathcal T$ become gauge redundancies of $\mathcal T/G$.

Second, charged local operators of $\mathcal T$ are no longer automatically genuine local operators of $\mathcal T/G$. Gauge-invariant composites survive as local operators; charged fields may become endpoints of line operators or disappear from the gauge-invariant local spectrum.

Third, the new theory can have new topological sectors, new line operators, and new symmetries. Gauging is not erasing symmetry; it changes the symmetry structure.

A good working definition is therefore:

$$
\boxed{\text{gauging }G=\text{summing over anomaly-free }G\text{-backgrounds with chosen gauge dynamics}.}
$$

Do not read this as “replace a constant parameter by a function.” That is only a local mnemonic for introducing a connection. The quantum operation is the path integral over background data.

## Setup and conventions

We distinguish three objects:

$$
A\quad\text{fixed background field},
$$

$$
a\quad\text{dynamical gauge field},
$$

$$
\mathcal G(P)\quad\text{group of gauge transformations of }P.
$$

For a continuous compact group $G$, the schematic gauged partition function is

$$
Z_{\mathcal T/G}(M)
=\sum_{[P\to M]}
\int_{\mathcal A(P)/\mathcal G(P)}\mathcal D a\;
Z_{\mathcal T}[P,a]\,e^{iS_{\text{dyn}}[a]+iS_{\text{top}}[P,a]}.
$$

Here $S_{\text{dyn}}$ might include a Yang–Mills or Maxwell term, such as

$$
S_{\text{YM}}=-\frac{1}{2g^2}\int_M \operatorname{tr}(F\wedge *F)
$$

in mostly-minus Lorentzian conventions. The normalization of $\operatorname{tr}$ and $g$ is convention-dependent and belongs to the gauge-theory volume when one computes scattering amplitudes or beta functions.

For a finite group $G$, one often writes

$$
Z_{\mathcal T/G}(M)
=\frac{1}{|G|}\sum_{\text{flat }G\text{ backgrounds}}Z_{\mathcal T}[M;A]
$$

on simple manifolds, but the invariant formula uses the groupoid cardinality

$$
\sum_{[P\to M]}\frac{1}{|\operatorname{Aut}(P)|}.
$$

The factor $|\operatorname{Aut}(P)|^{-1}$ is the finite-group analogue of dividing by the volume of the gauge group.

:::note[Source note]
The compact formula “gauge by summing over backgrounds” is especially common in the generalized-symmetry literature. In continuum gauge theory, the same operation is usually accompanied by a gauge kinetic term, gauge fixing, ghosts, and renormalization. These are not competing definitions; they emphasize different parts of the same construction.
:::

## The anomaly test

A global symmetry can be gauged only if the background-field functional is gauge invariant, possibly after adding local counterterms and choosing the correct higher-dimensional inflow interpretation.

If

$$
Z_{\mathcal T}[A^g]=Z_{\mathcal T}[A],
$$

then the integrand is a function on gauge-equivalence classes of backgrounds. Summing over gauge orbits makes sense.

If instead

$$
Z_{\mathcal T}[A^g]=Z_{\mathcal T}[A]e^{i\mathcal A[g,A]},
$$

and the phase $\mathcal A[g,A]$ cannot be removed by a local counterterm, then the symmetry has an anomaly. The attempted gauged path integral depends on the representative chosen on a gauge orbit, so the quotient is not well-defined.

This is why anomalies are often described as **obstructions to gauging**.

The obstruction statement is stronger than “the current is not conserved.” For an ordinary internal global symmetry, an anomaly means that the partition function fails to be an honest gauge-invariant function of the background symmetry data. Local current nonconservation is one expression of that failure.

There are three common outcomes:

1. The anomaly vanishes, and gauging is possible.
2. The anomaly can be shifted by local counterterms but not removed; different schemes reveal different parts of a mixed anomaly.
3. The anomaly is cancelled by adding extra degrees of freedom or by putting the theory on the boundary of a higher-dimensional invertible theory, the anomaly-inflow picture.

Only the first outcome gives an ordinary standalone gauged theory in the same dimension with no extra input.

## Continuous gauging: from global symmetry to gauge theory

Consider a matter theory with global $G$ symmetry. Coupling to a background field gives

$$
S[\phi;A]=S[\phi;0]+\int d^dx\,A_\mu^a j_a^\mu+O(A^2).
$$

Gauging replaces the fixed $A$ by a dynamical gauge field $a$ and integrates over it:

$$
Z=\int \frac{\mathcal D a}{\operatorname{Vol}(\mathcal G)}\mathcal D\phi\;
\exp\left(iS[\phi;a]+iS_{\text{gauge}}[a]\right).
$$

For a complex scalar with global $U(1)$ symmetry, this produces scalar QED:

$$
\mathcal L= (D_\mu\phi)^*D^\mu\phi -m^2|\phi|^2-\lambda |\phi|^4-\frac{1}{4e^2}f_{\mu\nu}f^{\mu\nu},
$$

with

$$
D_\mu=\partial_\mu-ia_\mu.
$$

For a nonabelian symmetry, the gauge field is a connection

$$
a=a_\mu^aT_a dx^\mu,
$$

with curvature

$$
F=da-ia\wedge a
$$

in the convention $D=d-ia$. The Yang–Mills term gives the gauge field local dynamics.

This construction changes the physical operator algebra. The field $\phi$ itself is no longer a gauge-invariant local operator. Operators such as $|\phi|^2$ remain local. Wilson lines become part of the theory's extended-operator spectrum.

This is the conceptual reason gauge symmetry is not a physical symmetry of states in the same way a global symmetry is. After gauging, the local gauge transformation is a redundancy used to describe the new dynamical field.

## Finite-group gauging: projection plus twisted sectors

Finite-group gauging is the cleanest place to see that gauging is not just “make the parameter local.” A finite group has no infinitesimal parameter and no Noether current. Yet it can be gauged.

For a finite internal symmetry $G$, a background is a flat $G$-bundle. On a lattice or triangulation, this can be represented by group elements on links, with flatness constraints around plaquettes. In continuum language, it is a principal $G$-bundle with locally constant transition functions.

On a thermal circle in quantum mechanics, gauging $G$ gives

$$
Z_{\mathcal T/G}(S^1_\beta)
=\frac{1}{|G|}\sum_{g\in G}\operatorname{Tr}_{\mathcal H}\left(U_g e^{-\beta H}\right).
$$

This is the trace over the $G$-invariant subspace:

$$
Z_{\mathcal T/G}(S^1_\beta)=\operatorname{Tr}_{\mathcal H^G}(e^{-\beta H}),
$$

because

$$
\Pi_G=\frac{1}{|G|}\sum_{g\in G}U_g
$$

is the projector onto invariant states.

In a spatially extended QFT, that projection is not the whole story. One must also sum over nontrivial spatial bundles, often called **twisted sectors**. In two-dimensional CFT language, the torus orbifold partition function takes the schematic form

$$
Z_{\mathcal T/G}(T^2)
=\frac{1}{|G|}\sum_{\substack{g,h\in G\\ gh=hg}}Z_{g,h},
$$

where $g$ and $h$ are commuting holonomies around the two cycles of the torus.

Projection without twisted sectors is not gauging a finite symmetry in a local QFT. It is only the Hilbert-space part of the operation in a particular channel.

## What choices are part of gauging?

The phrase “gauge the symmetry” hides choices. A careful gauging operation specifies at least the following data.

**1. The group and global form.**

One must know whether the group is $SU(2)$ or $SO(3)$, $U(1)$ with which charge lattice, or a quotient such as

$$
\frac{SU(N)\times U(1)}{\mathbb Z_N}.
$$

**2. The backgrounds to be summed over.**

For continuous groups this means principal $G$-bundles with connections. For finite groups this means flat $G$-bundles. For spin-sensitive theories, one may also need spin, spin-$c$, or related tangential structures.

**3. The anomaly cancellation condition.**

The background partition function must be gauge invariant, or be made gauge invariant by adding appropriate extra data.

**4. Local dynamics for continuous gauge fields.**

In dimensions where a gauge kinetic term is available, one chooses a coupling and action. In some dimensions one may instead have a topological gauge field, such as pure Chern–Simons theory in three dimensions.

**5. Topological terms.**

There may be theta angles, Chern–Simons levels, Dijkgraaf–Witten actions, discrete theta terms, or other invertible factors weighting different bundles.

**6. Operator completeness and allowed defects.**

The gauged theory has a new set of genuine local and extended operators. Different choices of allowed line operators can correspond to distinct theories even when the local Lagrangian looks the same.

This list is why “gauging” is a construction, not a punctuation mark.

## Example: gauging a scalar U(1)

Start with a complex scalar field

$$
\mathcal L_0=\partial_\mu\phi^*\partial^\mu\phi-m^2|\phi|^2-\lambda |\phi|^4
$$

with global $U(1)$ symmetry

$$
\phi\mapsto e^{i\alpha}\phi.
$$

The background coupling is obtained by

$$
\partial_\mu\phi\mapsto D_\mu\phi=(\partial_\mu-iA_\mu)\phi,
$$

where $A_\mu$ is a fixed background.

Gauging promotes $A_\mu$ to a dynamical field $a_\mu$ and adds gauge-field dynamics:

$$
\mathcal L= (D_\mu\phi)^*D^\mu\phi-m^2|\phi|^2-\lambda |\phi|^4-\frac{1}{4e^2}f_{\mu\nu}f^{\mu\nu}.
$$

The local transformation

$$
\phi(x)\mapsto e^{i\alpha(x)}\phi(x),
\qquad
 a_\mu(x)\mapsto a_\mu(x)+\partial_\mu\alpha(x)
$$

is now a redundancy. The field $\phi$ is not a gauge-invariant local observable. The operator $|\phi|^2$ is.

If the theory contains no charge-$1$ dynamical matter and all charges are multiples of $n$, then the faithful global form and allowed flux sectors require extra care. Gauging the wrong charge normalization changes the theory.

## Example: finite symmetry and orbifolds

Let a two-dimensional QFT have a finite internal symmetry $G$. Gauging $G$ is often called orbifolding. The result is not obtained merely by keeping $G$-invariant operators. One must also include twisted sectors.

On a spatial circle, the original Hilbert space has a sector with periodic boundary conditions. A $g$-twisted sector has fields obeying

$$
\phi(x+L)=g\cdot \phi(x).
$$

The orbifold Hilbert space has the schematic form

$$
\mathcal H_{\mathcal T/G}=\bigoplus_{[g]}\mathcal H_g^{C(g)},
$$

where $[g]$ denotes conjugacy classes and $C(g)$ is the centralizer of $g$. This formula is schematic because fermionic theories, discrete torsion, noncompact targets, and anomalous symmetries require refinements.

The important physical point is durable: finite gauging includes twisted sectors because the gauge field can have nontrivial holonomy around spatial cycles.

## Gauging a subgroup

One often gauges a subgroup $H\subset G$ of a larger global symmetry. The leftover ordinary symmetry is not always the naive quotient $G/H$.

If $H$ is a normal subgroup of $G$, then $G/H$ often acts on the gauged theory. If $H$ is not normal, the group that acts naturally is related to the normalizer

$$
N_G(H)=\{g\in G\mid gHg^{-1}=H\},
$$

and the ordinary residual symmetry is often

$$
N_G(H)/H,
$$

subject to anomaly and operator subtleties.

Even when ordinary residual symmetry disappears, gauging can create new generalized symmetries. For example, finite abelian gauging in $d$ dimensions often produces a dual $(d-2)$-form “quantum symmetry.” Continuous gauge theories can have electric and magnetic higher-form symmetries depending on the matter content and global form.

This is one of the first hints that gauging is better understood as a transformation of the full symmetry structure, not merely as removing a subgroup.

## Gauging versus quotienting

Physicists use “quotient” in several related but distinct ways.

For a classical configuration space $X$ with group action $G$, the quotient $X/G$ identifies configurations related by $G$. A sigma model with target $X/G$ is one kind of quotient theory.

Gauging a finite symmetry in a QFT is more than taking invariant local functions on $X$. It includes gauge bundles, holonomies, twisted sectors, and possible topological weights. In two-dimensional sigma models, this is why an orbifold is not merely the naive geometric quotient of the target space.

For continuous gauge theories, the path integral does divide by gauge redundancy, but it also integrates over gauge fields. In canonical language, it imposes Gauss-law constraints and changes the Hilbert space.

Thus

$$
\text{gauging} \neq \text{just taking invariant operators}
$$

in a local QFT with nontrivial spacetime topology or extended operators.

## Gauge fixing is not gauging

Gauge fixing appears after gauging. It is not the operation of gauging.

The logical order is:

$$
\text{global symmetry}
\quad\longrightarrow\quad
\text{background fields}
\quad\longrightarrow\quad
\text{sum over backgrounds}
\quad\longrightarrow\quad
\text{gauge redundancy}
\quad\longrightarrow\quad
\text{gauge fixing for computation}.
$$

For continuous groups, the quotient

$$
\mathcal A(P)/\mathcal G(P)
$$

is hard to integrate over directly. Perturbation theory replaces it by a gauge-fixed integral with ghosts or equivalent constraints. That computational replacement should not be confused with the conceptual construction.

The Gauge Redundancy and BRST chapter will explain why BRST symmetry appears after gauge fixing and how physical states are described cohomologically.

## What happens to charged operators?

Suppose $\mathcal O_q(x)$ has charge $q$ under a global $U(1)$ symmetry. Before gauging,

$$
U(\alpha)\mathcal O_q(x)U(\alpha)^{-1}=e^{iq\alpha}\mathcal O_q(x).
$$

After gauging, a local gauge transformation can vary independently near $x$. A charged local operator is not gauge invariant, so it is not a genuine local operator of the gauged theory.

There are several possible replacements:

- neutral composites, such as $\mathcal O_q^\dagger\mathcal O_q$,
- charged operators dressed by Wilson lines extending to a boundary or another charged insertion,
- disorder operators that create prescribed gauge-field singularities,
- line, surface, or boundary operators that carry the appropriate gauge charge.

In gauge theories with dynamical matter, many Wilson lines can break or end on matter fields. In pure gauge theories, line operators can be stable probes of confinement, screening, and higher-form symmetry.

The operator lesson is:

$$
\text{gauging changes what “local observable” means.}
$$

## What happens to states?

On a spatial manifold $\Sigma$, the Hilbert space of the gauged theory is not usually just the $G$-invariant subspace of the original Hilbert space.

For a finite group, one has to include twisted bundles over $\Sigma$:

$$
\mathcal H_{\mathcal T/G}(\Sigma)
\simeq
\bigoplus_{[P\to\Sigma]}\mathcal H_{\mathcal T}(\Sigma;P)^{\operatorname{Aut}(P)},
$$

again schematically.

For a continuous gauge theory, Gauss-law constraints select gauge-invariant states, but the gauge field also supplies new degrees of freedom and topological sectors. On compact spaces, electric flux sectors, magnetic flux sectors, theta angles, and boundary conditions can all matter.

Therefore “gauging means projecting to singlets” is only a partial statement. It is correct for the simplest quantum-mechanical trace over a time-circle background. It is incomplete for a local QFT on a general space.

## Common pitfalls

**Pitfall 1: Thinking every classical symmetry can be gauged quantum mechanically.**

Quantum anomalies can obstruct gauging even when the classical action admits a background coupling.

**Pitfall 2: Gauging the Lie algebra rather than the group.**

The global form controls which bundles and line operators are included. Gauging $SU(2)$ and gauging $SO(3)$ are generally different operations.

**Pitfall 3: Projecting to invariant operators and forgetting twisted sectors.**

Finite-group gauging includes nontrivial bundles. Orbifolds require twisted sectors.

**Pitfall 4: Confusing gauge fixing with gauging.**

Gauge fixing is a computational method for a theory that already has gauge redundancy. Gauging is the construction that creates that redundancy by summing over symmetry backgrounds.

**Pitfall 5: Assuming gauging simply removes symmetry.**

Gauging changes symmetry. It may produce residual ordinary symmetries, dual higher-form symmetries, topological sectors, and new defects.

## Relations to other pages

This page completes the basic conceptual arc of the Background Fields and Gauging chapter:

$$
\text{sources}\to\text{backgrounds}\to\text{global form}\to\text{gauging}.
$$

The next planned pages, **Gauging Finite Symmetries: Preview** and **Quotienting by Symmetry**, will specialize the finite-group story, connect it to orbifolds and Dijkgraaf–Witten terms, and compare geometric quotients, invariant sectors, and true gauging.

Later, the Anomalies chapter will make precise the obstruction

$$
Z[A^g]\neq Z[A],
$$

and the Gauge Redundancy and BRST chapter will explain gauge fixing, ghosts, and cohomological physical states. The Higher-Form and Generalized Symmetries chapter will revisit gauging as a symmetry-changing operation for extended operators.

## Research status

The basic operation of gauging anomaly-free ordinary symmetries is established. It underlies gauge theory, orbifolds, Standard Model construction, sigma models, lattice gauge theory, and topological field theory.

The modern research frontier is not whether gauging exists, but how broadly the idea generalizes. Current work treats gauging higher-form symmetries, mixed higher-group symmetries, finite categorical symmetries, non-invertible defects, duality defects, and boundary-condition changes in symmetry TFT. In these settings, “gauging” may no longer mean summing over ordinary group-valued bundles, but the old lesson survives: one sums over suitable topological background data only when the anomaly and operator data allow it.

## Exercises

### Exercise 1: Projection from finite-group gauging in quantum mechanics

Let a finite group $G$ commute with a Hamiltonian $H$ on a Hilbert space $\mathcal H$. Show that

$$
\frac{1}{|G|}\sum_{g\in G}\operatorname{Tr}_{\mathcal H}(U_g e^{-\beta H})
=\operatorname{Tr}_{\mathcal H^G}(e^{-\beta H}),
$$

where $\mathcal H^G$ is the invariant subspace.

<details><summary><strong>Solution</strong></summary>

Define

$$
\Pi_G=\frac{1}{|G|}\sum_{g\in G}U_g.
$$

Because $U_gU_h=U_{gh}$,

$$
\Pi_G^2=\frac{1}{|G|^2}\sum_{g,h}U_{gh}
=\frac{1}{|G|}\sum_{k}U_k=\Pi_G.
$$

Also $\Pi_G$ acts as the identity on $G$-invariant states and kills nontrivial irreducible components. Since $[H,U_g]=0$, we have $[H,\Pi_G]=0$, and

$$
\frac{1}{|G|}\sum_{g\in G}\operatorname{Tr}(U_g e^{-\beta H})
=\operatorname{Tr}(\Pi_G e^{-\beta H})
=\operatorname{Tr}_{\mathcal H^G}(e^{-\beta H}).
$$

</details>

### Exercise 2: Why an anomalous symmetry cannot be gauged

Suppose

$$
Z[A^g]=Z[A]e^{i\mathcal A[g,A]},
$$

where $\mathcal A[g,A]$ cannot be removed by any local counterterm. Explain why

$$
\int_{\mathcal A/\mathcal G}\mathcal D A\,Z[A]
$$

is not a well-defined quotient integral.

<details><summary><strong>Solution</strong></summary>

A quotient integral assigns one value to each gauge orbit. But $A$ and $A^g$ are two representatives of the same orbit. If the integrand changes by a nontrivial phase under $A\mapsto A^g$, then the value assigned to the orbit depends on the representative chosen.

If the phase could be removed by a local counterterm, this would be a convention issue. The exercise assumes it cannot be removed. Hence the obstruction is physical, and the symmetry cannot be gauged as an ordinary standalone symmetry in the same dimension.

</details>

### Exercise 3: Twisted sectors on a torus

For a finite group $G$, explain why flat $G$-bundles on a two-torus are labelled, up to conjugation, by commuting pairs $(g,h)$.

<details><summary><strong>Solution</strong></summary>

A flat $G$-bundle is specified by a homomorphism from the fundamental group of the torus to $G$, modulo conjugation. Since

$$
\pi_1(T^2)=\langle a,b\mid ab=ba\rangle,
$$

such a homomorphism assigns group elements

$$
a\mapsto g,
\qquad
b\mapsto h,
$$

subject to the relation

$$
gh=hg.
$$

Changing the trivialization of the bundle conjugates both holonomies simultaneously:

$$
(g,h)\mapsto (kgk^{-1},khk^{-1}).
$$

Thus flat bundles are labelled by commuting pairs modulo simultaneous conjugation.

</details>

### Exercise 4: Charged operators after gauging

A local operator $\mathcal O_q(x)$ has charge $q\neq0$ under a global $U(1)$ symmetry. Explain why it is not a genuine local operator after gauging the $U(1)$ symmetry.

<details><summary><strong>Solution</strong></summary>

After gauging, the transformation parameter becomes a local gauge redundancy. Near $x$ one may perform a gauge transformation with parameter $\alpha(x)$, under which

$$
\mathcal O_q(x)\mapsto e^{iq\alpha(x)}\mathcal O_q(x).
$$

A genuine local observable must be invariant under gauge redundancies. Since $q\neq0$, $\mathcal O_q$ is not gauge invariant and therefore is not a genuine local operator of the gauged theory.

It may appear in gauge-invariant composites, or as the endpoint of a Wilson line if the theory and boundary conditions allow such dressed operators.

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, especially §§57, 69–74, and 78. Gauge fields, nonabelian gauge theory, Faddeev–Popov ghosts, BRST symmetry, and background-field gauge.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapters 15–17. Nonabelian gauge theory, external fields, BRST symmetry, and renormalization of gauge theories.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapters 8, 14, 25, 30, and 34. Gauge invariance, path-integral identities, Yang–Mills theory, anomalies, and background fields.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” 2015. A modern formulation of global symmetries, background fields, and gauging by summing over backgrounds.
- Edward Witten, “On Holomorphic Factorization of WZW and Coset Models,” 1986. Classic source for gauging in two-dimensional current-algebra and coset contexts.
- Robbert Dijkgraaf and Edward Witten, “Topological Gauge Theories and Group Cohomology,” 1990. Classic finite-group gauge theory and discrete topological action reference.
- Ofer Aharony, Nathan Seiberg, and Yuji Tachikawa, “Reading between the Lines of Four-Dimensional Gauge Theories,” 2013. Global form, line operators, and discrete choices in gauging.

## Version history

- **2026-06-17:** Initial polished page on gauging ordinary global symmetries by summing over background fields.
