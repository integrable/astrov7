---
title: "Diagram Generation Workflows"
description: "A reproducible workflow for turning a Lagrangian or rule set into checked Feynman diagrams, amplitudes, and topology data."
sidebar:
  label: "Diagram Generation"
  order: 2
level: Advanced
status: "Polished draft"
source: "QGRAF; FeynArts/FormCalc/LoopTools; FeynRules/UFO; MadGraph5_aMC@NLO; FORM; FeynCalc; Srednicki; Weinberg; Schwartz."
topics:
  - computational perturbative QFT
  - Feynman diagrams
  - diagram generation
  - amplitude workflows
  - validation
canonicalTopics:
  - diagram-generation-workflows
  - automated-feynman-diagrams
  - model-to-amplitude-pipelines
researchStatus:
  established:
    - "Automated diagram generation is standard infrastructure for perturbative QFT calculations when the model, process, expansion order, and conventions are specified precisely."
  active:
    - "Interoperability, high-multiplicity processes, loop-level model support, finite-field reconstruction, GPU-aware kernels, and reproducible metadata remain active development areas."
---

## Summary

Diagram generation is the computational task of enumerating the Feynman graphs that contribute to a specified Green function, amplitude, decay, or cross section. It is not the same thing as doing the calculation. A diagram generator produces graph data and often amplitude expressions; the physicist still has to specify the theory, expansion order, external states, gauge fixing, counterterms, and validation checks.

The stable workflow is

$$
\text{model}
\longrightarrow
\text{Feynman rules}
\longrightarrow
\text{topologies}
\longrightarrow
\text{field assignments}
\longrightarrow
\text{amplitudes}
\longrightarrow
\text{checks}.
$$

Each arrow hides convention-sensitive choices. A generated diagram set is only meaningful relative to a precise model file, process definition, coupling order, gauge, field basis, and treatment of identical particles. Diagram generation is therefore a reproducibility problem as much as a combinatorics problem.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 58rem;">

![Diagram generation workflow from model data to rules, diagrams, amplitudes, and validation checks](/figures/perturbative-qft/diagram-generation-workflows.svg)

<figcaption>

A diagram-generation workflow should carry metadata and validation checks alongside the graph list. The central chain produces diagrams and amplitudes; the lower row records choices that make the output reproducible rather than merely printable.

</figcaption>
</figure>

This page explains how to design such workflows. It treats tool names as examples, not as a permanent ranking. Packages change; the checks do not.

## Prerequisites

You should know [Perturbative Expansion](/perturbative-qft/diagrammatics-feynman-rules/perturbative-expansion/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/), [Vertices and Propagators](/perturbative-qft/diagrammatics-feynman-rules/vertices-and-propagators/), [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/), [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/), and [Symbolic Amplitude Tools](/perturbative-qft/computational-perturbative-qft/symbolic-amplitude-tools/).

## Core idea

A diagram is a decorated graph. The decorations are the physics:

| Graph datum | Physical meaning |
|---|---|
| external legs | specified incoming and outgoing fields or operator insertions |
| vertices | interaction terms, including counterterms and composite-operator insertions |
| internal lines | propagating fields allowed by the model |
| orientations and arrows | charge flow, fermion-number flow, ghost flow, or color-flow bookkeeping |
| momentum routing | independent loop momenta and conservation at vertices |
| labels | flavor, color, Lorentz, spinor, helicity, generation, and gauge indices |
| automorphisms | overcounting and symmetry-factor information |

A diagram generator performs two logically separate tasks. First, it enumerates graph topologies compatible with the requested number of external legs and loop order. Second, it decorates those topologies with fields and vertices allowed by the theory. Some tools merge these steps, but separating them conceptually makes mistakes easier to find.

The generated object may be one of several things:

| Output | What it is good for | What it is not yet |
|---|---|---|
| topology list | graph classification and loop-family planning | a physical amplitude |
| diagram list | complete contribution inventory | simplified algebra |
| analytic amplitude | symbolic checks and reduction | numerical prediction |
| squared matrix element | phase-space integration | showered event sample |
| code kernel | numerical evaluation | a documented calculation by itself |

The safest attitude is: a generator gives a candidate answer to a well-posed combinatorics problem. Physics validation comes next.

## Setup and conventions

We use the conventions of the Perturbative QFT and Scattering volume. This page does not restate metric, Fourier, state-normalization, or propagator conventions. A workflow should, however, record whether the software uses the same conventions or requires a translation.

Before generating diagrams, fix the following data.

| Input | Examples of choices that must be explicit |
|---|---|
| theory definition | fields, masses, parameters, interactions, gauge group, representations |
| field basis | gauge basis, mass basis, chiral basis, flavor basis, effective-operator basis |
| gauge fixing | Feynman gauge, $R_\xi$ gauge, background-field gauge, axial gauge, unitary gauge |
| ghost sector | ghost fields, ghost vertices, ghost counterterms where relevant |
| external state definition | particle labels, incoming/outgoing convention, helicity or spin-sum basis |
| expansion order | loop order, powers of couplings, EFT order, number of extra emissions |
| renormalization setup | counterterms, scheme, regulator, input parameters |
| diagram restrictions | resonance filters, flavor restrictions, topology exclusions, on-shell cuts |

Defaults are dangerous. A package default is a convention, not a law of nature. If the default is not recorded, the calculation is already decaying into folklore.

## What is being generated

There are three common targets.

### Green-function diagrams

For a time-ordered correlator,

$$
G_n(x_1,\ldots,x_n)
=
\langle0|T\{\phi(x_1)\cdots\phi(x_n)\}|0\rangle,
$$

the external legs are operator insertions. They need not be on shell, and they include external propagators unless the correlator has been amputated. Diagram generation for Green functions is usually closest to Wick's theorem: list contraction patterns produced by the interaction expansion.

### Amplitude diagrams

For an S-matrix amplitude, the external legs represent asymptotic states. External propagators are amputated by LSZ, external particles are placed on shell, and spinors or polarization vectors appear. A generator may output either the full $i\mathcal M$ or pieces that still need external-state factors.

### Observable-level diagrams

For a cross section or decay rate, the object is not just an amplitude. One must include squared amplitudes, interference terms, phase space, cuts, measurement functions, real emissions, subtraction terms, counterterms, and sometimes parton distributions or fragmentation functions. Diagram generation is only the first layer.

These targets should not be blurred. A correlator diagram, an amputated amplitude diagram, and a real-emission contribution to an infrared-safe observable are related, but they are not the same computational object.

## Model input

A model input should define the theory in a way that can be inspected by a human and parsed by software. At minimum it should include:

| Item | Why it matters |
|---|---|
| fields and quantum numbers | determines allowed propagators and vertices |
| parameters | controls coupling orders and numerical input |
| Lagrangian or vertex list | determines the interaction rules |
| gauge fixing | determines propagators, ghosts, and gauge-parameter checks |
| counterterms | required for renormalized loop calculations |
| restrictions | prevents impossible or unwanted flavor and generation assignments |
| mass and width conventions | affects propagators, resonance treatment, and complex-mass schemes |

There are two healthy ways to start.

The first is **Lagrangian-first**. One enters the fields and Lagrangian, then derives vertices automatically. This is powerful for new models and EFTs, but it puts pressure on field normalization, integration by parts, hermitian conjugates, gauge fixing, and basis changes.

The second is **rule-first**. One enters a vetted list of propagators and vertices. This is often clearer for focused analytic calculations, especially when the relevant counterterms are known. The price is that the relation to the underlying Lagrangian can become less transparent.

A mature workflow often uses both: derive rules from a model file, export them, inspect them, and then use a frozen rule file for production calculations.

## Process input

A process request is not just a string such as `e+ e- > mu+ mu-`. It should specify the mathematical object being computed.

| Question | Example |
|---|---|
| Which external particles? | $e^-e^+\to\mu^-\mu^+$, with all fermions incoming or physical in/out convention recorded |
| Which perturbative order? | leading order in $e$, NLO QCD, one loop in $\lambda$, dimension-six interference only |
| Which diagrams are included? | all diagrams, only connected diagrams, only one-particle-irreducible diagrams, no resonant diagrams |
| Which external-state treatment? | helicities fixed, spins summed, polarizations physical, ghosts excluded from asymptotic states |
| Which flavor assumptions? | diagonal Yukawas, massless first generations, CKM included, flavor-changing vertices forbidden |
| Which kinematic assumptions? | massless limit, high-energy limit, threshold expansion, off-shell current |

The same visual graph can represent different contributions under different process definitions. For example, a photon line can be an internal propagator, an external on-shell photon, or an off-shell current insertion. The diagram is not the calculation; the process definition gives it meaning.

## Topologies and field assignments

For a connected graph with $E$ external legs, $I$ internal lines, $V$ vertices, and $L$ loops,

$$
L=I-V+1.
$$

If the theory has vertices of valence $r$ and $V_r$ such vertices, then

$$
E+2I=\sum_r rV_r.
$$

These two equations are useful sanity checks before any package is launched.

For example, in a cubic scalar theory, a connected tree-level four-point graph has $E=4$, $L=0$, and only cubic vertices. The equations give

$$
I=V-1,
\qquad
4+2I=3V,
$$

so $V=2$ and $I=1$. The three diagrams are the familiar $s$-, $t$-, and $u$-channel exchanges.

In a quartic scalar theory, a connected tree-level four-point graph has $E=4$, $L=0$, and one quartic vertex:

$$
V_4=1,
\qquad
I=0.
$$

There is a single contact topology. A generator that produces more diagrams may be distinguishing external label orderings; a generator that produces fewer diagrams may have hidden an identical-particle convention.

Field assignment is the next layer. A topology says “two trivalent vertices connected by an internal line.” A field assignment says “the internal line is a scalar,” “the two vertices are Yukawa vertices,” or “one of these assignments is forbidden by charge conservation.” Good tools should expose which assignments were accepted and why the others were rejected.

## Symmetry factors and automorphisms

The diagram-generation problem contains graph isomorphism in disguise. Two labeled construction histories may lead to the same physical graph. The quotient by these redundancies produces symmetry factors.

For a generated diagram, ask:

| Question | Why it matters |
|---|---|
| Are external legs labeled or identical? | changes automorphism group and phase-space factors |
| Are vertices distinguishable? | affects whether Dyson-expansion factorials cancel |
| Are internal lines identical? | affects graph automorphisms |
| Are there tadpoles or bubbles? | self-contractions often carry residual factors |
| Are counterterm vertices distinct from ordinary vertices? | they usually carry different coupling order and should not be merged accidentally |

Many generators output diagrams in a convention where symmetry factors have already been absorbed into Feynman rules or combinatorial weights. Others output raw graphs. Never infer the convention from a pretty picture. Inspect the algebraic weight.

A useful validation is to reproduce a small Wick-contraction count by hand. If the tool's weight differs, either the tool is using a different convention or the input model is not what you think it is.

## Momentum routing

Momentum routing is arbitrary, but it should be systematic. A generator typically assigns momenta to internal lines and imposes conservation at vertices. The result may contain redundant delta functions or a chosen set of independent loop momenta.

For a connected momentum-space graph, vertex conservation fixes all internal momenta up to $L$ independent loop momenta. A clean output separates

$$
(2\pi)^4\delta^{(4)}\!\left(\sum p_{\rm in}-\sum p_{\rm out}\right)
$$

from the stripped amplitude. This separation prevents a classic bug: accidentally treating the overall momentum-conservation delta function as another internal constraint.

At loop level, the routing should be compatible with downstream loop reduction. It is often worth choosing integral families before simplifying the amplitude too aggressively. A beautiful expression with many shifted loop momenta can be worse than a slightly uglier one that maps cleanly to a small number of families.

## Fermions, ghosts, and arrows

Fermion signs are not graphical decoration. They come from anticommuting fields. A diagram generator must track:

| Object | Bookkeeping role |
|---|---|
| fermion arrows | spinor-index contraction and fermion-number flow |
| external fermion ordering | signs from reordering external fields |
| closed fermion loops | extra minus sign |
| Majorana fermions | orientation conventions become subtler |
| ghosts | anticommuting scalar fields with directed ghost number flow |

Ghosts deserve special caution. They are internal fields introduced by gauge fixing, not physical external particles. In non-Abelian gauge theories, omitting ghost loops usually breaks unitarity and gauge-parameter cancellation. In Abelian QED with linear covariant gauge fixing, ghosts decouple in the usual formulation, but that is a property of that gauge-fixed theory, not a universal feature of gauge theory.

## Gauge-theory completeness checks

Gauge theories punish incomplete diagram sets. A single graph is rarely gauge invariant. The simplest diagnostic is to replace a polarization vector by the corresponding momentum and check that the physical amplitude vanishes when all required diagrams are included.

For example, in QED Compton scattering, the two tree diagrams are separately not gauge invariant. The sum is. Schematically,

$$
\mathcal M^{\mu\nu}
=
(-ie)^2\bar u(p')
\left[
\gamma^\nu\frac{i(p\!\!\!/+k\!\!\!/+m)}{(p+k)^2-m^2+i\epsilon}\gamma^\mu
+
\gamma^\mu\frac{i(p\!\!\!/-k'\!\!\!/+m)}{(p-k')^2-m^2+i\epsilon}\gamma^\nu
\right]u(p),
$$

where $\mu$ and $\nu$ label the photon legs. Contracting with an external photon momentum gives cancellations between the two terms after using the external Dirac equations. A generator that keeps only one diagram has not computed Compton scattering; it has computed a gauge-dependent fragment.

This is a general lesson. Validation should be designed around complete gauge-invariant subsets whenever possible.

## Counterterm and effective-operator diagrams

At loop order, the generated set must include counterterm diagrams at the same perturbative order as the loop diagrams they renormalize. In an EFT, it may also include insertions of higher-dimensional operators.

A process at a fixed order is usually organized by a power-counting rule. For example, an EFT amplitude might be expanded as

$$
\mathcal M
=
\mathcal M_{\rm SM}^{(0)}
+
\mathcal M_{\rm SM}^{(1)}
+
\sum_i \frac{C_i}{\Lambda^2}\mathcal M_i^{(0)}
+
\sum_i \frac{C_i}{\Lambda^2}\mathcal M_i^{(1)}
+\cdots.
$$

A generator must know which terms are requested. “One loop” is not a complete order specification if several couplings or EFT suppressions are present. A good workflow records both loop order and coupling order.

Counterterm vertices should be visibly distinct from ordinary vertices. Otherwise it becomes too easy to double count finite renormalizations or omit scheme-dependent pieces.

## A reproducible diagram-generation workflow

A practical workflow should look like this.

### Step 1: freeze the model input

Record the model file, rule file, parameter card, gauge choice, field basis, and any restrictions. For a Lagrangian-derived model, keep a human-readable export of the vertices.

### Step 2: generate a small benchmark first

Before the target process, generate a known process. Examples include scalar $2\to2$ scattering, $e^-e^+\to\mu^-\mu^+$, QED Compton scattering, or a known one-loop self-energy. Compare diagram counts and signs.

### Step 3: request the target process with explicit order filters

Specify external states, loop order, coupling order, EFT order, allowed particle content, and exclusions. Avoid broad filters such as “all diagrams” unless that is truly the desired object.

### Step 4: inspect diagram counts by topology and field content

Do not jump directly to the final amplitude. First count diagrams by topology, loop order, internal particle species, and counterterm content. Unexpected diagrams are often more informative than final algebra.

### Step 5: assign momenta and export amplitudes

Use a momentum convention compatible with downstream algebra and loop reduction. Store the momentum-routing convention and external-state ordering.

### Step 6: run algebraic simplification in layers

Simplify Lorentz algebra, spinor algebra, color algebra, and integral-family mappings separately when possible. This makes failures local. All-at-once simplification is how expressions go into the swamp and come back wearing someone else's hat.

### Step 7: validate before numerical use

Run Ward identities, gauge-parameter cancellation, crossing checks, known limits, pole-structure checks, and independent comparisons. Record which checks passed.

## Validation checklist

| Check | Useful for | Failure often means |
|---|---|---|
| diagram count in toy model | generator setup | wrong model import or process definition |
| vertex list inspection | model input | missing hermitian conjugates, wrong symmetry factors |
| charge and quantum-number conservation | field assignments | illegal vertices or missing restrictions |
| Ward identity | gauge theories | incomplete diagrams, wrong signs, missing ghosts |
| gauge-parameter cancellation | loop gauge theory | missing counterterms or incomplete gauge-invariant subset |
| crossing symmetry | external-state conventions | wrong all-incoming convention or fermion ordering |
| mass dimension | algebra output | wrong coupling order or normalization |
| UV pole structure | loop amplitudes | missing counterterms or wrong regulator |
| IR factorization | massless gauge theories | missing real-emission or subtraction terms |
| independent implementation | serious results | package-specific convention mismatch or bug |

The most trustworthy workflows keep a validation notebook or log next to the generated expressions. The log should include package versions and command files. Reproducibility is not an aesthetic choice; it is how future-you avoids becoming an archaeologist of your own calculation.

## Common pitfalls

**Generating diagrams before defining the object.** A graph list for a Green function, an amputated amplitude, and an observable are different things.

**Trusting default gauges.** Gauge choices affect propagators, ghosts, counterterms, and intermediate expressions. Defaults must be recorded.

**Confusing visual diagrams with algebraic weights.** The same drawing can carry different symmetry factors, signs, coupling powers, or external-state conventions.

**Omitting counterterm diagrams.** Loop diagrams without counterterm diagrams are usually not renormalized amplitudes.

**Filtering diagrams too aggressively.** Removing “small” or “uninteresting” diagrams can break gauge invariance or unitarity.

**Letting package syntax define the physics.** A process string is an interface, not a specification. The physical assumptions should be written in ordinary language too.

**Skipping known limits.** If a generated result cannot reproduce a textbook limit, it is not ready for a new-physics claim.

## Relations to other pages

- [Symbolic Amplitude Tools](/perturbative-qft/computational-perturbative-qft/symbolic-amplitude-tools/) gives the broader software map in which diagram generation sits.
- [Loop Reduction Workflows](/perturbative-qft/computational-perturbative-qft/loop-reduction-workflows/) explains what happens after generated loop amplitudes are mapped to integral families.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) gives the hand-derived rules that automated tools must reproduce.
- [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/) explains the combinatorics behind graph weights.
- [Counterterm Insertions](/perturbative-qft/loop-expansion-regularization/counterterm-insertions/) explains the extra vertices needed in renormalized perturbation theory.
- [QED Ward Identity](/perturbative-qft/gauge-theory-perturbation-theory/qed-ward-identity/) and [Gauge-Parameter Independence](/perturbative-qft/gauge-theory-perturbation-theory/gauge-parameter-independence/) explain two core validation checks.

## Research status

- **Established:** Diagram generation from specified Feynman rules is a standard, mature part of perturbative QFT automation. The core combinatorics of graph topology, field assignment, symmetry factors, and momentum routing is textbook-stable.
- **Active:** Large process generation, loop-level automation, EFT model support, counterterm generation, color and helicity optimization, GPU-aware event generation, finite-field workflows, and reproducible metadata standards continue to evolve.
- **Convention-dependent:** Generated amplitudes depend on field basis, gauge fixing, regulator, renormalization scheme, external-state normalization, all-incoming conventions, and package-specific definitions of signs and factors of $i$.

## Exercises

### Exercise 1: Cubic four-point tree graphs

In a scalar theory with a cubic interaction, use

$$
L=I-V+1,
\qquad
E+2I=3V,
$$

to determine the number of vertices and internal lines in a connected tree-level four-point graph. What are the three physical channels?

<details>
<summary><strong>Solution</strong></summary>

Tree level means $L=0$, so

$$
I=V-1.
$$

For $E=4$ and cubic vertices,

$$
4+2I=3V.
$$

Substitute $I=V-1$:

$$
4+2(V-1)=3V
\quad\Rightarrow\quad
2+2V=3V
\quad\Rightarrow\quad
V=2.
$$

Then $I=1$. The graph consists of two cubic vertices connected by one internal line. With four labeled external legs, the three inequivalent pairings give the $s$-, $t$-, and $u$-channel exchange diagrams.

</details>

### Exercise 2: Quartic contact diagram

In scalar $\phi^4$ theory, use the same graph identities with $E=4$, $L=0$, and quartic vertices to show that the tree-level connected four-point contribution has one vertex and no internal line.

<details>
<summary><strong>Solution</strong></summary>

For a connected tree graph, $L=0$ gives $I=V-1$. With only quartic vertices,

$$
E+2I=4V.
$$

Setting $E=4$ and $I=V-1$ gives

$$
4+2(V-1)=4V,
$$

so

$$
2+2V=4V
\quad\Rightarrow\quad
V=1.
$$

Then $I=0$. The diagram is the single four-point contact graph.

</details>

### Exercise 3: Why both Compton diagrams are needed

Explain why a diagram generator for QED Compton scattering must include both electron-exchange orderings at tree level.

<details>
<summary><strong>Solution</strong></summary>

The two diagrams correspond to the two possible orderings of photon emission and absorption along the fermion line. Each term contains a different internal fermion propagator. Gauge invariance is a statement about the sum: replacing an external photon polarization by its momentum produces terms that cancel between the two diagrams after using the external Dirac equations.

If one ordering is omitted, the cancellation is lost. The remaining expression is a gauge-dependent fragment, not the Compton amplitude. A correct process request must therefore include both diagrams unless one is deliberately studying a non-gauge-invariant intermediate object.

</details>

### Exercise 4: Minimal metadata record

Design a metadata header for a generated one-loop amplitude in a gauge theory. List at least eight entries that should be recorded.

<details>
<summary><strong>Solution</strong></summary>

A useful header could include:

| Entry | Example |
|---|---|
| model file | `model-name`, commit hash, or version |
| process | external states and all-incoming convention |
| loop order | one loop |
| coupling order | e.g. $g_s^4 e^2$ or NLO QCD |
| gauge | Feynman gauge or $R_\xi$ gauge with value of $\xi$ |
| regulator | dimensional regularization, $d=4-2\epsilon$ |
| renormalization scheme | on-shell, $\overline{\rm MS}$, complex-mass scheme, etc. |
| counterterm set | file or table of renormalization constants |
| external-state basis | helicities, spin sums, polarization convention |
| momentum routing | loop-momentum definitions and external ordering |
| software versions | generator, algebra system, reduction tools |
| validation checks | Ward identities, UV poles, known limits |

The exact format is less important than making the assumptions machine-readable and human-auditable.

</details>

## References

- P. Nogueira, “Automatic Feynman graph generation,” *Journal of Computational Physics* **105** (1993), for QGRAF.
- T. Hahn, “Generating Feynman diagrams and amplitudes with FeynArts 3,” *Computer Physics Communications* **140** (2001), and related FeynArts/FormCalc/LoopTools documentation.
- T. Hahn, “Generating and calculating one-loop Feynman diagrams with FeynArts, FormCalc, and LoopTools,” for a classic automated one-loop workflow.
- A. Alloul, N. D. Christensen, C. Degrande, C. Duhr, and B. Fuks, “FeynRules 2.0 — A complete toolbox for tree-level phenomenology,” for Lagrangian-to-rule generation.
- C. Degrande, C. Duhr, B. Fuks, D. Grellscheid, O. Mattelaer, and T. Reiter, “UFO — The Universal FeynRules Output,” for a model interchange format.
- J. Alwall et al., “The automated computation of tree-level and next-to-leading order differential cross sections, and their matching to parton shower simulations,” for MadGraph5_aMC@NLO.
- J. A. M. Vermaseren, “New features of FORM,” for large-scale symbolic manipulation in perturbative calculations.
- R. Mertig, M. Böhm, and A. Denner, and later FeynCalc documentation, for symbolic QFT algebra workflows.
- M. Srednicki, *Quantum Field Theory*, especially the perturbation-theory and Feynman-rule chapters.
- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, ch. 6, for the covariant derivation of Feynman rules.
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 7, 13, 26, and 27, for practical diagrammatic calculations and gauge-theory examples.

## Version history

- **2026-06-13:** Initial polished draft. Added a workflow map, validation checklist, scalar and QED examples, and solved exercises.
