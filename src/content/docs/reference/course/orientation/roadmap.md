---
title: "Learning Roadmap"
description: "A practical reading path through AdS/CFT Foundations, from the basic dictionary to black holes, entanglement, finite density, AdS3/CFT2, and quantum gravity."
sidebar:
  label: "Roadmap"
  order: 50
---

AdS/CFT is easy to summarize and hard to learn in the right order. The sentence

$$
\text{bulk gravity in AdS}
\quad\longleftrightarrow\quad
\text{boundary quantum field theory}
$$

is too compressed to be a learning plan. A good route has to separate several questions that are often mixed together:

- What exactly is being claimed?
- Why does a large-$N$ gauge theory have anything to do with strings?
- What is special about Anti-de Sitter geometry?
- Why do boundary values of bulk fields become sources?
- How do divergent on-shell actions become finite CFT observables?
- Why do black holes compute thermal physics?
- Why do areas compute entanglement?
- Which statements belong to full quantum AdS/CFT, and which belong only to the classical gravity limit?

This page is a map through those questions. It is meant to prevent two common disasters: learning beautiful applications before the dictionary is stable, and learning formal dictionary entries without knowing which physical problems they solve.

<figure class="doc-figure" style="--figure-width: 56rem;">

![A roadmap of the AdS/CFT Foundations course, showing the conceptual spine from orientation through holographic renormalization and later branches into correlators, thermal physics, entanglement, applications, AdS3/CFT2, and quantum gravity.](/figures/course/course-roadmap.svg)

<figcaption>

A practical route through AdS/CFT Foundations. The upper row is the minimal conceptual spine. The lower row contains research branches that become much easier after the basic dictionary and holographic renormalization are in place.

</figcaption>
</figure>

## The spine of the course

The core route is

$$
\text{Orientation}
\to
\text{CFT and large }N
\to
\text{AdS geometry}
\to
\text{D-branes and strings}
\to
\text{the dictionary}
\to
\text{holographic renormalization}.
$$

Everything later in the course depends on this route. Black branes, Witten diagrams, Wilson loops, entanglement wedges, conductivity, BTZ black holes, and bulk reconstruction are not disconnected tricks. They are different uses of the same central idea:

$$
Z_{\mathrm{CFT}}[J]
=
Z_{\mathrm{bulk}}[\Phi \to J]
\approx
\exp\!\left(-S_{\text{ren,on-shell}}[J]\right).
$$

The approximation on the right is the classical saddle-point approximation. The first equality is the deeper statement. The course repeatedly returns to the difference between these two facts.

The fastest honest way through the foundations is not to learn every application immediately. It is to build the machinery that makes the applications meaningful:

$$
\text{field-theory observables}
\quad\longleftrightarrow\quad
\text{bulk boundary-value problems}.
$$

Once that translation is reliable, the branches become much easier to read.

## Phase 0: Orientation

The Orientation unit explains what kind of claim AdS/CFT is. This is worth doing carefully because many later confusions begin as small imprecisions here.

Read these pages first:

- [Why Holography?](/course/orientation/why-holography/)
- [What the Duality Claims](/course/orientation/what-the-duality-claims/)
- [Regimes of Validity](/course/orientation/regimes-of-validity/)
- [Conventions and Units](/course/orientation/conventions-and-units/)

After this unit, you should be able to say the following without hesitation:

$$
\text{AdS/CFT is an equivalence of quantum theories, not merely an analogy.}
$$

You should also know which version of the equivalence you are using in a calculation. For example,

$$
Z_{\mathrm{CFT}}[J]
\approx
\exp\!\left(-S_{\text{on-shell}}[J]\right)
$$

is not the full correspondence. It is the saddle-point form of the correspondence in a regime where the bulk is well approximated by classical gravity.

### Checkpoint

You are ready to move on when you can explain these distinctions.

| Phrase | Meaning |
|---|---|
| full AdS/CFT | equality between a boundary quantum theory and a bulk quantum gravity/string theory |
| classical gravity limit | large-$N$, strong-coupling corner where the bulk path integral is dominated by a saddle |
| top-down construction | a dual pair derived from a controlled string/M-theory setup |
| bottom-up model | a gravitational model designed to capture selected field-theory features, not automatically guaranteed to have a complete UV dual |
| holographic dictionary | the map between boundary observables and bulk boundary conditions, fields, and geometries |

The most important habit is to ask, before every calculation: **which version of the duality am I using?**

## Phase 1: Field theory first

AdS/CFT is a statement about quantum field theory as much as it is a statement about gravity. The boundary theory supplies the nonperturbative definition. For this reason, the course begins the technical development on the field-theory side.

The essential pages are:

- [QFT Data and Generating Functionals](/course/cft-large-n/qft-data-and-generating-functionals/)
- [Conformal Symmetry: The Minimum You Need](/course/cft-large-n/conformal-symmetry-minimum/)
- [Radial Quantization and the Cylinder](/course/cft-large-n/radial-quantization-and-the-cylinder/)
- [Large-$N$ Gauge Theory](/course/cft-large-n/large-n-gauge-theory/)
- [Single-Trace Operators and Factorization](/course/cft-large-n/single-trace-and-factorization/)
- [$\mathcal N=4$ Super-Yang–Mills](/course/cft-large-n/n4-super-yang-mills/)

The first major goal is to understand why large-$N$ gauge theories are natural candidates for holographic duals. In a matrix gauge theory, the 't Hooft coupling is

$$
\lambda = g_{\mathrm{YM}}^2 N.
$$

The large-$N$ expansion organizes diagrams by topology:

$$
\mathcal A_g \sim N^{2-2g},
$$

where $g$ is the genus of the associated double-line diagram. This is the first hint that a large-$N$ gauge theory may reorganize itself as a string theory, with an effective string coupling controlled by $1/N$ in a suitable 't Hooft limit.

The second major goal is to understand how operators behave at large $N$. Single-trace operators are the boundary objects that most directly create single-particle bulk states:

$$
\mathcal O(x)
=
\frac{1}{N}\operatorname{Tr}\!\left(F^2(x)\right),
\qquad
\mathcal O_I(x)
=
\frac{1}{N}\operatorname{Tr}\!\left(\Phi^{(i_1}\cdots \Phi^{i_k)}(x)\right),
$$

with normalization conventions varying from author to author. Multi-trace operators then correspond, roughly, to multiparticle states.

### What to focus on

Do not try to learn all of CFT before studying AdS/CFT. The minimum needed here is more modest:

- how sources generate correlation functions;
- what scaling dimensions are;
- how conformal symmetry constrains two- and three-point functions;
- how radial quantization turns local operators into states;
- how large-$N$ factorization creates weakly interacting sectors.

A very useful mental model is

$$
\text{large-}N\text{ factorization}
\quad\Longleftrightarrow\quad
\text{weak bulk interactions}.
$$

This is not a proof of the duality, but it explains why a classical bulk theory can emerge from a strongly coupled quantum field theory.

## Phase 2: Learn AdS as a spacetime

The next unit develops the bulk geometry. Anti-de Sitter spacetime is not chosen randomly. It is maximally symmetric, has a conformal boundary, and has exactly the right isometry group to match the conformal group of the boundary theory:

$$
\operatorname{Isom}(\mathrm{AdS}_{d+1})
\simeq
SO(2,d).
$$

For a $d$-dimensional Lorentzian CFT, $SO(2,d)$ is also the conformal group of flat Minkowski space, up to global and discrete subtleties.

The essential pages are:

- [AdS as a Spacetime](/course/ads-geometry/ads-as-a-spacetime/)
- [Coordinate Systems](/course/ads-geometry/coordinate-systems/)
- [The Conformal Boundary](/course/ads-geometry/conformal-boundary/)
- [Global AdS and the Cylinder](/course/ads-geometry/global-ads-and-the-cylinder/)
- [Isometries and Conformal Symmetry](/course/ads-geometry/isometries-and-conformal-symmetry/)
- [Fields in AdS](/course/ads-geometry/fields-in-ads/)
- [Black Holes and Black Branes](/course/ads-geometry/black-holes-and-black-branes/)

The most important coordinate system for first calculations is the Poincaré patch:

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2 + \eta_{\mu\nu}dx^\mu dx^\nu
\right),
\qquad
z>0.
$$

The conformal boundary is at $z=0$. Moving toward larger $z$ moves inward into the bulk and, from the boundary point of view, toward lower energy scales. This is the first version of the UV/IR relation.

### What to focus on

Learn AdS geometry operationally. You should be able to:

- move between Poincaré and global intuition;
- identify the conformal boundary;
- understand why a boundary metric is defined only up to Weyl rescaling;
- solve the leading near-boundary behavior of a scalar field;
- compute the temperature of an AdS black brane from horizon regularity.

The scalar field exercise is especially important. Near $z=0$, solutions behave as

$$
\phi(z,x)
\sim
z^{d-\Delta}\phi_{(0)}(x)
+
z^\Delta A(x),
$$

where the two powers encode the source and response data of the dual field theory.

## Phase 3: Understand where the canonical example comes from

The string-theory origin of AdS/CFT is not optional historical decoration. It explains why the duality has the form it has.

The essential pages are:

- [Open and Closed Strings](/course/string-origin/open-and-closed-strings/)
- [D-Branes for Field Theorists](/course/string-origin/d-branes-for-field-theorists/)
- [D3-Branes: Two Descriptions](/course/string-origin/d3-branes-two-descriptions/)
- [Near-Horizon Geometry](/course/string-origin/near-horizon-geometry/)
- [The Decoupling Limit](/course/string-origin/decoupling-limit/)
- [The Parameter Map](/course/string-origin/parameter-map/)
- [Why Classical Gravity Emerges](/course/string-origin/why-classical-gravity-emerges/)

The key physical system is a stack of $N$ coincident D3-branes. There are two descriptions of the same system:

$$
\text{open strings on D3-branes}
\quad\leadsto\quad
\mathcal N=4\; SU(N)\; \text{SYM},
$$

and

$$
\text{closed strings sourced by D3-branes}
\quad\leadsto\quad
\mathrm{AdS}_5 \times S^5.
$$

The near-horizon D3-brane metric contains the factor

$$
ds^2
=
\frac{r^2}{L^2}dx_{1,3}^2
+
\frac{L^2}{r^2}dr^2
+
L^2d\Omega_5^2,
$$

which is $\mathrm{AdS}_5\times S^5$ in appropriate coordinates.

The parameter map is the real prize:

$$
L^4 = 4\pi g_s N \alpha'^2,
\qquad
\lambda = g_{\mathrm{YM}}^2N,
\qquad
\frac{L^4}{\alpha'^2}\sim \lambda.
$$

It explains why large $N$ is not enough by itself. A weakly curved classical gravity dual also requires large 't Hooft coupling.

### What to focus on

The exact details of string quantization can wait. The indispensable string-theory facts are:

- open strings give gauge fields on D-branes;
- closed strings include gravitons;
- D-branes are both places where open strings end and sources for closed-string fields;
- the low-energy limit can isolate brane dynamics and near-horizon geometry;
- the same brane system has two complementary low-energy descriptions.

That is enough to understand why the canonical duality is plausible and why its parameters scale the way they do.

## Phase 4: Build the basic dictionary

This is the heart of the course. The dictionary turns the duality from a grand claim into a calculational framework.

The essential pages are:

- [Statement of the Correspondence](/course/dictionary/statement-of-the-correspondence/)
- [The GKPW Prescription](/course/dictionary/gkpw-prescription/)
- [Scalar Two-Point Functions](/course/dictionary/scalar-two-point-functions/)
- [The Mass-Dimension Relation](/course/dictionary/mass-dimension-relation/)
- [Alternate Quantization and the BF Bound](/course/dictionary/alternate-quantization-and-bf-bound/)
- [One-Point Functions and VEVs](/course/dictionary/one-point-functions-and-vevs/)
- [Spin, Symmetry, and Conserved Currents](/course/dictionary/spin-symmetry-and-conserved-currents/)
- [The Stress Tensor and the Metric](/course/dictionary/stress-tensor-and-the-metric/)

The first working equation is

$$
Z_{\mathrm{CFT}}[\phi_{(0)}]
=
Z_{\mathrm{bulk}}[\phi \to \phi_{(0)}].
$$

In the saddle-point approximation,

$$
Z_{\mathrm{bulk}}[\phi \to \phi_{(0)}]
\approx
\exp\!\left(-S_{\text{on-shell}}[\phi_{(0)}]\right).
$$

Then boundary correlators are obtained by differentiating with respect to sources:

$$
\langle \mathcal O(x_1)\cdots \mathcal O(x_n)\rangle_c
=
\frac{\delta^n W[\phi_{(0)}]}{\delta \phi_{(0)}(x_1)\cdots \delta \phi_{(0)}(x_n)}
\bigg|_{\phi_{(0)}=0},
\qquad
W = \log Z_{\mathrm{CFT}}.
$$

For a scalar field, the mass-dimension relation is

$$
m^2L^2=\Delta(\Delta-d).
$$

This equation is a perfect example of the dictionary: a geometric quantity in the bulk, $m^2L^2$, becomes spectral data in the boundary CFT, namely the operator dimension $\Delta$.

### What to focus on

The most common mistake at this stage is to memorize a table of correspondences without learning the variational logic behind it. The table matters, but the logic matters more.

For example:

| Bulk object | Boundary object |
|---|---|
| scalar field $\phi$ | scalar operator $\mathcal O$ |
| boundary value of $\phi$ | source for $\mathcal O$ |
| normalizable response | expectation value of $\mathcal O$ |
| bulk gauge field $A_M$ | conserved current $J^\mu$ |
| bulk metric $g_{MN}$ | stress tensor $T_{\mu\nu}$ |
| bulk horizon | thermal entropy and dissipation |

The table is a compressed form of a variational statement. The course will keep unpacking it.

## Phase 5: Make the dictionary finite

The on-shell action in AdS usually diverges. This is not a technical annoyance to sweep away. It is one of the clearest places where the radial direction becomes the energy scale.

The essential pages are:

- [Why Renormalization Is Needed](/course/holographic-renormalization/why-renormalization-is-needed/)
- [Near-Boundary Expansion](/course/holographic-renormalization/near-boundary-expansion/)
- [Counterterms and the Renormalized Action](/course/holographic-renormalization/counterterms-and-renormalized-action/)
- [One-Point Functions from Variation](/course/holographic-renormalization/one-point-functions-from-variation/)
- [Ward Identities and Anomalies](/course/holographic-renormalization/ward-identities-and-anomalies/)
- [Radial Hamiltonian Viewpoint](/course/holographic-renormalization/radial-hamiltonian-viewpoint/)
- [A Practical Recipe](/course/holographic-renormalization/practical-recipe/)

The renormalized action is defined by cutting off the spacetime near the boundary, adding local counterterms, and removing the cutoff:

$$
S_{\mathrm{ren}}
=
\lim_{\epsilon\to 0}
\left(
S_{\mathrm{bulk}}^{z\ge \epsilon}
+
S_{\mathrm{GHY}}^{z=\epsilon}
+
S_{\mathrm{ct}}^{z=\epsilon}
\right).
$$

After this step, expectation values are computed by variation:

$$
\langle \mathcal O\rangle
=
\frac{1}{\sqrt{g_{(0)}}}
\frac{\delta S_{\mathrm{ren}}}{\delta \phi_{(0)}}.
$$

This is where many calculations become honest. Without renormalization, source-response language is often too crude.

### What to focus on

A practical holographic calculation usually follows this pattern:

1. choose a bulk action and boundary conditions;
2. solve the equations of motion near the boundary;
3. identify the source coefficients;
4. regulate the on-shell action at $z=\epsilon$;
5. add local counterterms on the cutoff surface;
6. vary the renormalized action;
7. remove the cutoff;
8. interpret the finite answer in field-theory terms.

This is the computational backbone for much of the rest of the course.

## After the core: choose a branch

Once the dictionary and renormalization are in place, the course branches. The branches can be read in different orders, depending on your goals.

### Branch A: Correlators and probes

Read this branch to learn how CFT data is encoded in bulk interactions.

Main topics:

- Witten diagrams;
- three-point functions and cubic bulk couplings;
- four-point functions and bulk locality;
- heavy operators and geodesic approximations;
- Wilson loops;
- probe branes and flavor.

The guiding idea is

$$
\text{bulk interaction vertices}
\quad\Longleftrightarrow\quad
\text{CFT OPE and correlator data}.
$$

This branch is especially useful before reading modern papers on conformal bootstrap, bulk locality, effective field theory in AdS, and stringy corrections.

### Branch B: Thermal and real-time holography

Read this branch for black holes, hydrodynamics, transport, and quasinormal modes.

Main topics:

- black branes and thermal CFTs;
- Hawking–Page transition;
- Euclidean free energy;
- Lorentzian prescription;
- retarded Green's functions;
- quasinormal modes;
- hydrodynamics;
- shear viscosity.

The first dictionary entries are

$$
T_{\mathrm{CFT}} = T_{\mathrm{Hawking}},
\qquad
S_{\mathrm{CFT}} = \frac{\mathrm{Area}_{\mathrm{horizon}}}{4G_N}.
$$

The real-time version is subtler than the Euclidean one. Do not assume that all Lorentzian correlators follow from a naive Wick rotation of the Euclidean on-shell action. Horizon boundary conditions matter.

### Branch C: Entanglement and geometry

Read this branch for quantum information, emergent geometry, and black-hole information.

Main topics:

- entanglement entropy in QFT;
- Ryu–Takayanagi surfaces;
- HRT surfaces;
- entanglement wedges;
- relative entropy and linearized gravity;
- quantum extremal surfaces;
- islands.

The first formula is

$$
S_A
=
\frac{\operatorname{Area}(\gamma_A)}{4G_N},
$$

where $\gamma_A$ is an appropriate bulk surface anchored to the boundary region $A$.

This branch is conceptually powerful, but it is easy to misuse without the core dictionary. Entanglement surfaces are not merely pretty geometric objects; they are part of a precise map between boundary quantum information and bulk gravitational observables.

### Branch D: AdS$_3$/CFT$_2$

Read this branch for the cleanest low-dimensional laboratory.

Main topics:

- why AdS$_3$ gravity is special;
- Brown–Henneaux central charge;
- BTZ black holes;
- Cardy formula;
- Virasoro symmetry;
- boundary gravitons.

The central result is

$$
c = \frac{3L}{2G_3}.
$$

AdS$_3$/CFT$_2$ is often the best place to test ideas because the boundary theory has infinite-dimensional conformal symmetry and the bulk has no local propagating gravitons in pure Einstein gravity.

### Branch E: Applications and beyond

Read this branch for finite density, AdS/CMT, bottom-up models, confinement models, and less supersymmetric examples.

Main topics:

- what counts as a holographic CFT;
- other AdS backgrounds;
- RG flows and domain walls;
- confinement models;
- chemical potential and bulk gauge fields;
- Reissner–Nordstrom AdS;
- AdS$_2$ throats;
- holographic conductivity;
- holographic superconductors;
- fermion spectral functions;
- bottom-up model building.

Finite density begins with the boundary behavior of a bulk gauge field:

$$
A_t(z\to 0)
=
\mu - \rho z^{d-2} + \cdots,
$$

where $\mu$ is the chemical potential and $\rho$ is the charge density, up to conventions.

The important attitude in this branch is disciplined modeling. A gravitational construction can be useful even when it is not derived from a known string compactification, but one should keep track of which claims are universal, which are model-dependent, and which are only phenomenological.

### Branch F: Bulk quantum gravity from CFT

Read this branch for the deepest structural questions.

Main topics:

- bulk effective field theory;
- large-$N$ factorization and Fock space;
- bulk reconstruction;
- quantum error correction;
- black-hole information;
- stringy and quantum corrections;
- open problems.

The guiding idea is

$$
\text{the boundary CFT is not coupled to quantum gravity; it is the quantum gravity theory in different variables.}
$$

This branch should not be read as science fiction after the technical material. It is one of the main reasons the technical material matters.

## Suggested routes by goal

### Route 1: Minimal working dictionary

This is the shortest route that still gives a serious foundation:

1. Orientation.
2. QFT generating functionals.
3. Conformal symmetry minimum.
4. Large-$N$ gauge theory.
5. Single-trace operators and factorization.
6. AdS geometry and conformal boundary.
7. Fields in AdS.
8. D3-brane two-description argument.
9. Near-horizon and decoupling limits.
10. GKPW prescription.
11. Scalar two-point functions.
12. Mass-dimension relation.
13. First pass through holographic renormalization.

This route is enough to begin computing simple correlators and to understand what many introductory AdS/CFT papers are doing.

### Route 2: Black holes and strongly coupled plasma

Take the minimal working dictionary, then add:

1. black holes and black branes;
2. Euclidean gravity and thermodynamics;
3. black branes and thermal CFTs;
4. retarded Green's functions;
5. quasinormal modes;
6. hydrodynamics from gravity;
7. shear viscosity.

This route is good for thermal field theory, transport, quark-gluon plasma motivation, and AdS/CMT-style calculations.

### Route 3: Entanglement and emergent spacetime

Take the minimal working dictionary, then add:

1. global AdS and the cylinder;
2. entanglement entropy in QFT;
3. RT formula;
4. HRT formula;
5. entanglement wedges;
6. relative entropy and linearized gravity;
7. quantum extremal surfaces and islands;
8. quantum error correction.

This route is good for students interested in quantum information, gravitational constraints from entanglement, and the black-hole information problem.

### Route 4: AdS/CMT and finite density

Take the minimal working dictionary, then add:

1. thermal states and density matrices;
2. black branes;
3. bulk gauge fields and chemical potential;
4. Reissner–Nordstrom AdS;
5. AdS$_2$ throats;
6. holographic conductivity;
7. holographic superconductors;
8. fermions and spectral functions;
9. bottom-up models and their limitations.

This route is good for condensed-matter-inspired applications. It requires comfort with real-time Green's functions.

### Route 5: AdS$_3$/CFT$_2$

Take the orientation, CFT minimum, and AdS geometry pages, then add:

1. radial quantization and the cylinder;
2. why AdS$_3$ is special;
3. Brown–Henneaux central charge;
4. BTZ black holes;
5. Cardy formula;
6. Virasoro symmetry and boundary gravitons;
7. RT formula in AdS$_3$.

This route is efficient because two-dimensional CFT gives more exact control than higher-dimensional CFT.

### Route 6: Reading modern quantum-gravity papers

Take the minimal working dictionary and entanglement branch, then add:

1. bulk effective field theory;
2. large-$N$ factorization and Fock space;
3. bulk reconstruction;
4. quantum error correction;
5. black-hole information in AdS/CFT;
6. stringy and quantum corrections;
7. open problems and research map.

This route is conceptually demanding. It is much easier after doing at least a few explicit source-response and black-brane calculations.

## How to read a technical page

Most pages in this course follow a similar pattern:

1. **Motivation.** Why the topic matters for holography.
2. **Setup.** Definitions, conventions, and assumptions.
3. **Derivation.** The main calculation or argument.
4. **Dictionary checkpoint.** The boundary/bulk translation extracted from the page.
5. **Common confusions.** Traps that repeatedly catch readers.
6. **Exercises.** Short calculations with solutions.

The derivations are not ornamental. AdS/CFT is full of formulas that look simple only after many choices have been made. When a page derives a result, the point is not just to obtain the answer; the point is to expose the assumptions under which the answer is true.

A good habit is to keep a personal dictionary notebook. For every page, write one line of the form

$$
\text{boundary statement}
\quad\Longleftrightarrow\quad
\text{bulk statement}.
$$

Examples:

$$
\text{operator dimension }\Delta
\quad\Longleftrightarrow\quad
\text{bulk mass }m^2L^2=\Delta(\Delta-d),
$$

$$
\text{temperature}
\quad\Longleftrightarrow\quad
\text{horizon regularity},
$$

$$
\text{entanglement entropy}
\quad\Longleftrightarrow\quad
\text{area of an extremal surface}.
$$

## What to postpone

Some topics are important but should not be learned too early.

### Full string quantization

Useful, but not needed for the first pass. The course introduces only the string facts needed for the D3-brane argument and the parameter map.

### Detailed supersymmetry representation theory

$\mathcal N=4$ SYM is supersymmetric, but the foundational dictionary can be learned without mastering the full representation theory of the superconformal algebra.

### The complete conformal bootstrap

CFT data and operator product expansions matter, but a full bootstrap course is not a prerequisite for this foundations course.

### Islands and replica wormholes

These are exciting, but they are late-stage topics. They make much more sense after RT/HRT, quantum extremal surfaces, thermal AdS black holes, and the meaning of a boundary nonperturbative definition are clear.

### Bottom-up model building

Bottom-up models are most useful after you understand what a controlled top-down dictionary looks like. Otherwise it is too easy to mistake a useful model for a complete duality.

## Common wrong reading strategies

### Reading only review papers before doing calculations

Reviews are invaluable, but passive reading can create a false sense of understanding. The first scalar two-point function, the first black-brane temperature calculation, and the first holographic counterterm calculation are worth doing by hand.

### Starting with the most modern topic

Modern topics often have the clearest motivation but the densest prerequisites. For example, entanglement wedges and quantum error correction use the same basic dictionary as scalar correlators and stress-tensor one-point functions. The modern picture is not a replacement for the old dictionary; it grows from it.

### Treating all holographic models as equally controlled

Some gravitational models come from precise string-theory constructions. Some are effective models. Some are phenomenological. The course will repeatedly ask: which regime is under control, and which approximation is being used?

### Confusing Euclidean and Lorentzian prescriptions

Euclidean calculations are often simpler. Real-time calculations involve causal boundary conditions, especially at horizons. The retarded Green's function is not obtained by guessing signs in the Euclidean answer.

### Ignoring normalization conventions

Many holographic formulas differ by factors of $2$, $\pi$, $L$, $G_N$, $N^2$, or $i$. These factors often depend on action normalizations and source conventions. Conceptual understanding comes first, but precision eventually matters.

## A compact semester plan

A one-semester graduate reading course could use the following rhythm.

| Weeks | Topics | Main outcome |
|---|---|---|
| 1–2 | Orientation, CFT sources, conformal minimum | understand what the duality claims and how QFT generating functionals work |
| 3–4 | large $N$, single traces, $\mathcal N=4$ SYM | understand why weak bulk interactions can emerge |
| 5–6 | AdS geometry, boundary, fields | understand the radial direction and near-boundary behavior |
| 7–8 | D3-branes, near-horizon limit, parameter map | understand the canonical origin of AdS$_5$/CFT$_4$ |
| 9–10 | GKPW, scalar correlators, mass-dimension relation | compute the first holographic correlators |
| 11–12 | holographic renormalization | obtain finite one-point functions and Ward identities |
| 13 | black branes or Witten diagrams | apply the dictionary to a first research branch |
| 14 | entanglement or quantum gravity outlook | connect the foundations to modern questions |

This schedule is only a guide. A research group can slow down substantially around holographic renormalization or real-time correlators; those topics reward patience.

## Dictionary checkpoint

The roadmap itself has a dictionary lesson:

$$
\text{course order}
\quad\Longleftrightarrow\quad
\text{logical dependence of the duality}.
$$

Large-$N$ field theory explains why weakly coupled bulk degrees of freedom can exist. AdS geometry explains where the boundary data lives. The D-brane construction explains the canonical example and the parameter map. The GKPW prescription explains how sources compute correlators. Holographic renormalization makes the answers finite. The later branches are applications and refinements of this structure.

## Exercises

### Exercise 1: Choose the right branch

For each research goal, identify the most relevant branch after the core dictionary:

1. computing the conductivity of a strongly coupled finite-density system;
2. understanding why BTZ black-hole entropy agrees with a CFT formula;
3. studying how a boundary region reconstructs part of the bulk;
4. computing a CFT three-point coefficient from a cubic bulk interaction;
5. understanding the pole structure of thermal retarded correlators.

<details>
<summary><strong>Solution</strong></summary>

1. Conductivity at finite density belongs to the Applications and Beyond branch, with input from Thermal and Real-Time Holography.
2. BTZ entropy belongs to the AdS$_3$/CFT$_2$ branch.
3. Boundary-region reconstruction belongs to the Bulk Quantum Gravity branch, with essential input from Entanglement and Geometry.
4. Three-point coefficients from cubic bulk interactions belong to the Correlators and Probes branch.
5. Thermal retarded poles belong to the Thermal and Real-Time branch, especially the pages on retarded Green's functions and quasinormal modes.

</details>

### Exercise 2: Diagnose the missing prerequisite

A student says: “I understand RT surfaces, but I do not understand why their areas are divided by $4G_N$ or why large $N$ matters.” Which earlier topics should they revisit?

<details>
<summary><strong>Solution</strong></summary>

They should revisit the regimes of validity, large-$N$ factorization, and the relation between bulk Newton's constant and the number of boundary degrees of freedom. The factor $1/G_N$ measures the effective number of degrees of freedom in the classical bulk limit. In many canonical examples, quantities such as central charges or entropy coefficients scale like a positive power of $N$, often $N^2$ for four-dimensional adjoint gauge theories. RT is a classical area formula, so it is naturally the leading large-$N$ contribution to the entropy.

</details>

### Exercise 3: Classical gravity or full duality?

Consider the formula

$$
Z_{\mathrm{CFT}}[J]
\approx
\exp\!\left(-S_{\text{ren,on-shell}}[J]\right).
$$

Is this the exact statement of AdS/CFT? Explain what approximations are being used.

<details>
<summary><strong>Solution</strong></summary>

This is not the exact statement. The exact statement is an equality between the boundary CFT generating functional and the full bulk quantum gravity or string theory partition function with specified boundary conditions:

$$
Z_{\mathrm{CFT}}[J]
=
Z_{\mathrm{bulk}}[\Phi\to J].
$$

The expression involving $\exp(-S_{\text{ren,on-shell}})$ assumes that the bulk path integral is dominated by a classical saddle. This requires a regime where quantum bulk loops and stringy corrections are suppressed, such as large $N$ and large 't Hooft coupling in the canonical AdS$_5$/CFT$_4$ example.

</details>

### Exercise 4: Build a two-week crash route

Design a two-week route for a student who needs to understand scalar two-point functions from AdS/CFT as quickly as possible. Keep only the minimum prerequisites.

<details>
<summary><strong>Solution</strong></summary>

A minimal route is:

1. What the Duality Claims.
2. Regimes of Validity.
3. QFT Data and Generating Functionals.
4. Conformal Symmetry Minimum.
5. AdS as a Spacetime.
6. Coordinate Systems.
7. Conformal Boundary.
8. Fields in AdS.
9. GKPW Prescription.
10. Scalar Two-Point Functions.
11. Mass-Dimension Relation.
12. Why Holographic Renormalization Is Needed.
13. Counterterms and Renormalized Action.

This route omits many important subjects, including the D3-brane derivation and black holes. It is acceptable only as a crash route to a specific calculation. For conceptual mastery, the string-origin and large-$N$ pages should be added back.

</details>

## Further reading

The course is self-contained, but these references explain why the roadmap is organized this way:

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, [Gauge Theory Correlators from Non-Critical String Theory](https://arxiv.org/abs/hep-th/9802109).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).
- K. Skenderis, [Lecture Notes on Holographic Renormalization](https://arxiv.org/abs/hep-th/0209067).
- D. T. Son and A. O. Starinets, [Minkowski-Space Correlators in AdS/CFT Correspondence](https://arxiv.org/abs/hep-th/0205051).
- S. Ryu and T. Takayanagi, [Holographic Derivation of Entanglement Entropy from AdS/CFT](https://arxiv.org/abs/hep-th/0603001).
- V. E. Hubeny, M. Rangamani, and T. Takayanagi, [A Covariant Holographic Entanglement Entropy Proposal](https://arxiv.org/abs/0705.0016).

Do not read these as prerequisites before starting. Use them as anchors while the course develops the same ideas in a more pedagogical order.
