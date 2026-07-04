---
title: "Loop Expansion"
description: "A precise explanation of loop order as graph topology, independent momentum integration, and the semiclassical expansion of QFT amplitudes and effective actions."
sidebar:
  label: "Loop Expansion"
  order: 1
level: Graduate
status: "Polished draft"
source: "Srednicki 2007, §§14–20; Weinberg 1995, Vol. I, chs. 6, 9, and 12; Coleman 2019, chs. 15–16 and 32; Schwartz 2014, chs. 15–19; Zinn-Justin 2021, chs. 7–9"
topics:
  - loop expansion
  - Feynman diagrams
  - effective action
  - semiclassical expansion
  - perturbation theory
canonicalTopics:
  - loop-expansion
  - loop-order
  - independent-loop-momentum
  - hbar-expansion
  - effective-action-loop-expansion
researchStatus:
  established:
    - "Loop order is a standard organization of perturbative QFT diagrams, equivalent to counting independent internal momentum integrations and, after restoring ħ, to the semiclassical expansion of connected and one-particle-irreducible quantities."
  active:
    - "Modern perturbative calculations combine loop expansion with regularization, renormalization, unitarity methods, infrared factorization, automation, and sometimes resummation or nonperturbative information."
---

## Summary

A **loop expansion** organizes perturbative QFT by the number of independent internal momenta in a diagram. For a connected graph with $I$ internal lines and $V$ vertices,

$$
{L=I-V+1.}
$$

The integer $L$ is the graph's loop number. A tree diagram has $L=0$, a one-loop diagram has one unconstrained internal momentum integral, and an $L$-loop diagram has $L$ independent loop momentum integrations.

A typical momentum-space contribution has the schematic form

$$
\mathcal M_\Gamma
=\frac{1}{S_\Gamma}
\left(\prod_{v\in\Gamma} \text{vertex factors}\right)
\int\prod_{r=1}^{L_\Gamma}\frac{d^d\ell_r}{(2\pi)^d}
\left(\prod_{a\in\Gamma}\text{propagators}\right)
\times \text{numerator}.
$$

The same word “loop” also has a semiclassical meaning. If we temporarily restore $\hbar$, then tree diagrams are the leading stationary-phase contribution, one-loop terms are the Gaussian fluctuation determinant, and higher loops come from interactions among fluctuations. For the effective action,

$$
\Gamma[\varphi]
=S[\varphi]
+\frac{i\hbar}{2}\operatorname{Tr}\log S^{(2)}[\varphi]
+O(\hbar^2)
$$

schematically in Lorentzian signature. Euclidean formulas have the corresponding Euclidean signs. This page explains how these three viewpoints — graph topology, loop momentum integrals, and the $\hbar$ expansion — fit together.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Tree, one-loop, and two-loop graphs illustrate loop order as the number of independent internal momenta](/figures/perturbative-qft/loop-expansion-layers.svg)

<figcaption>

Loop order counts independent internal momenta after momentum-conserving vertex delta functions have been used. The same grading appears in the semiclassical expansion of the effective action: the classical action gives tree-level physics, the Gaussian determinant gives one-loop physics, and higher interactions among fluctuations give higher-loop corrections.

</figcaption>
</figure>

## Prerequisites

You should know [Conventions and Notation](/perturbative-qft/conventions/), [Perturbative Expansion](/perturbative-qft/diagrammatics-feynman-rules/perturbative-expansion/), [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/), [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/), [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/), and [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/).

For the path-integral viewpoint, review [Scalar Field Path Integral](/foundations/path-integral-formalism/scalar-field-path-integral/), [Sources and Generating Functionals](/foundations/path-integral-formalism/sources-and-generating-functionals/), and [Effective Action](/foundations/interactions-and-wick-expansion/effective-action/).

## Core idea

The loop expansion is a bookkeeping system for quantum corrections.

At tree level, internal momenta are fixed by external kinematics. There are propagators, but no independent integration variables. Tree diagrams already describe nontrivial scattering, exchange forces, and classical nonlinear response.

At loop level, the diagram contains internal momenta not fixed by external momenta. Those momenta are integrated over all values. This is where ultraviolet divergences, threshold branch cuts, absorptive parts, anomalous dimensions, and scheme dependence first become unavoidable.

The practical slogan is

$$
\text{tree} = \text{classical propagation and exchange},
\qquad
\text{loops} = \text{quantum fluctuations integrated over virtual momenta}.
$$

That slogan is useful, but it should not be over-literal. Internal lines are propagators, not observed particles. Loop momenta are integration variables, not measured momenta. A loop diagram is a term in an expansion, not a little movie of particles orbiting in spacetime.

## Setup and conventions

We use qft.org scattering conventions. For a real scalar field,

$$
\mathcal L
=\frac12\partial_\mu\phi\,\partial^\mu\phi
-\frac12m^2\phi^2
-\frac{\lambda}{4!}\phi^4,
$$

the scalar propagator and quartic vertex are

$$
\frac{i}{p^2-m^2+i\epsilon},
\qquad
-i\lambda.
$$

In $d$ spacetime dimensions, each independent loop momentum is integrated with

$$
\int_\ell \equiv \int\frac{d^d\ell}{(2\pi)^d}.
$$

The dimension $d$ may be physical, such as $d=4$, or analytically continued in dimensional regularization. The loop expansion by itself does not choose a regulator. Once a loop integral diverges, a regulator and a renormalization prescription become part of the calculation.

## Loop number as graph topology

For a connected graph, assign one momentum variable to each internal line. That gives $I$ internal momentum variables. Each vertex imposes a momentum-conservation delta function, but one overall delta function remains as conservation of total external momentum rather than fixing an internal variable. Therefore only $V-1$ of the vertex constraints fix internal momenta. The number left over is

$$
L=I-(V-1)=I-V+1.
$$

For a graph with $C$ connected components, the general formula is

$$
L=I-V+C.
$$

This is the first Betti number of the graph: the number of independent cycles. In perturbative QFT it is also the number of independent loop momentum integrations.

:::note[Loops are not just circles in a drawing]
A diagram may be drawn in many equivalent ways. The loop number is not the number of visually round shapes on the page. It is the number $I-V+C$, or equivalently the number of independent internal momenta after all delta functions have been used.
:::

## Loop number versus coupling order

Loop order and coupling order are related, but they are not the same concept. The relation depends on the interaction vertices.

In scalar $\phi^4$ theory, every quartic vertex has four half-edges. For a connected graph with $E$ external legs,

$$
4V=2I+E.
$$

Together with $L=I-V+1$, this gives

$$
V=L+\frac{E}{2}-1.
$$

Therefore a connected $E$-point graph in $\lambda\phi^4$ theory carries the coupling factor

$$
\lambda^V=
\lambda^{L+E/2-1}.
$$

For four-point scattering, $E=4$, so

$$
V=L+1,
\qquad
\mathcal M_{2\to2}^{\phi^4}
=\mathcal M^{(0)}+\mathcal M^{(1)}+\mathcal M^{(2)}+\cdots,
$$

with

$$
\mathcal M^{(L)}=O(\lambda^{L+1}).
$$

Thus the tree contact diagram is $O(\lambda)$, the one-loop bubble diagrams are $O(\lambda^2)$, and two-loop four-point diagrams are $O(\lambda^3)$.

In scalar $\phi^3$ theory, instead,

$$
3V=2I+E,
\qquad
V=2L+E-2.
$$

For four-point scattering, tree level already has two cubic vertices, so it is $O(g^2)$, while the one-loop correction is $O(g^4)$.

The lesson is simple:

$$
\text{loop order is topological; coupling order is dynamical.}
$$

They often march together in simple theories, but one should not identify them blindly.

## Loop expansion from momentum-space diagrams

After Fourier transforming a diagram, every internal line initially receives a momentum variable. Every vertex produces a delta function imposing momentum conservation. The delta functions remove many internal momenta and leave precisely $L$ independent momenta. The contribution then has the form

$$
\mathcal M_\Gamma
=(2\pi)^d\delta^{(d)}\!\left(\sum p_{\rm ext}\right)
\,i\mathcal A_\Gamma,
$$

where the stripped amplitude contribution is schematically

$$
\mathcal A_\Gamma
=\frac{1}{S_\Gamma}
\int\prod_{r=1}^{L}\frac{d^d\ell_r}{(2\pi)^d}
\,N_\Gamma(\ell_r,p_a)
\prod_{j=1}^{I}
\frac{i}{q_j(\ell_r,p_a)^2-m_j^2+i\epsilon}
\prod_v (-ig_v).
$$

Here $S_\Gamma$ is the symmetry factor, $N_\Gamma$ contains numerator factors from spin, polarization, derivative interactions, or gauge vertices, and $q_j$ are linear combinations of loop and external momenta.

For the one-loop four-point bubble in $\phi^4$ theory, one channel contains the integral

$$
\mathcal A_{\rm bubble}(P)
=\frac{(-i\lambda)^2}{2}
\int\frac{d^d\ell}{(2\pi)^d}
\frac{i}{\ell^2-m^2+i\epsilon}
\frac{i}{(P-\ell)^2-m^2+i\epsilon},
$$

where $P$ is the momentum flowing through that channel. The factor $1/2$ is the symmetry factor for the identical internal scalar lines in this bubble graph.

The integral is a one-loop integral because exactly one momentum, $\ell$, remains unfixed. Its ultraviolet behavior and its imaginary part are separate questions. Loop number tells us the structure of the integral; regularization, analytic continuation, and unitarity tell us how to interpret it.

## Loop expansion from the path integral

The loop expansion has a second, deeper interpretation as the stationary-phase expansion of the path integral. Restore $\hbar$ temporarily:

$$
Z[J]
=\int\mathcal D\phi\,
\exp\left\{\frac{i}{\hbar}\left(S[\phi]+\int d^dx\,J\phi\right)\right\}.
$$

Let $\phi_{\rm cl}$ solve the sourced classical equation of motion,

$$
\left.\frac{\delta S}{\delta\phi(x)}\right|_{\phi_{\rm cl}}+J(x)=0,
$$

and write

$$
\phi=\phi_{\rm cl}+\eta.
$$

Expanding the action gives

$$
S[\phi]+\int J\phi
=S[\phi_{\rm cl}]+\int J\phi_{\rm cl}
+\frac12\int \eta S^{(2)}[\phi_{\rm cl}]\eta
+\frac{1}{3!}\int S^{(3)}[\phi_{\rm cl}]\eta^3+\frac{1}{4!}\int S^{(4)}[\phi_{\rm cl}]\eta^4+\cdots.
$$

The linear term vanishes because $\phi_{\rm cl}$ obeys the sourced equation of motion. The Gaussian integral over $\eta$ produces a determinant,

$$
\left(\det S^{(2)}[\phi_{\rm cl}]\right)^{-1/2},
$$

which becomes a trace logarithm in the effective action. Schematically,

$$
\Gamma[\varphi]
=S[\varphi]
+\frac{i\hbar}{2}\operatorname{Tr}\log S^{(2)}[\varphi]
+O(\hbar^2).
$$

This is why one-loop effects are often described as Gaussian fluctuations around the classical background. Higher-loop terms come from treating the cubic, quartic, and higher fluctuation interactions perturbatively.

The $\hbar$ counting can be seen by rescaling fluctuation fields as

$$
\eta=\sqrt{\hbar}\,\xi.
$$

The quadratic action becomes independent of $\hbar$, while an $n$-point fluctuation vertex carries a power $\hbar^{n/2-1}$. Combining these factors across a connected graph gives one net power of $\hbar$ for each loop. Up to overall conventions for connected versus 1PI generating functionals,

$$
L\text{-loop contribution}\sim O(\hbar^L).
$$

In ordinary particle-physics units we set $\hbar=1$, so this grading is hidden. It is still conceptually useful: loops are quantum fluctuations around the classical saddle.

## Trees and classical field theory

Tree diagrams are not “no physics.” They are the field-theoretic expression of classical nonlinear response.

For example, solving the classical equation of motion perturbatively in a source generates tree diagrams. In a scalar theory, the classical solution has the schematic expansion

$$
\phi_{\rm cl}
=GJ+G\left(\text{interaction of }GJ\text{ with }GJ\right)+\cdots,
$$

where $G$ is the appropriate Green function. Iterating the classical equation produces branching structures but no closed momentum integrations. That is tree level.

This point is especially important in gauge theory and gravity. Tree-level Yang–Mills amplitudes and tree-level graviton amplitudes are rich, highly constrained, and physically measurable. “Loop correction” means quantum correction relative to this leading classical scattering structure, not “the first interesting thing.”

## Loops and exact quantities

The loop expansion approximates exact quantities. For a two-point function, one often writes the exact scalar propagator as

$$
G(p)=\frac{i}{p^2-m^2-\Sigma(p^2)+i\epsilon},
$$

where $\Sigma(p^2)$ is the self-energy. The self-energy itself has a loop expansion,

$$
\Sigma(p^2)=\Sigma^{(1)}(p^2)+\Sigma^{(2)}(p^2)+\cdots,
$$

plus counterterm contributions once renormalization is introduced.

For an amplitude,

$$
\mathcal M
=\mathcal M^{\rm tree}
+\mathcal M^{\rm 1-loop}
+\mathcal M^{\rm 2-loop}
+\cdots.
$$

This is a formal asymptotic expansion in weak coupling and, conceptually, in $\hbar$. It is not usually a convergent series. In many QFTs, perturbation theory is asymptotic, and nonperturbative effects such as instantons, confinement, bound states, or tunneling are invisible at any finite loop order.

## Regularization enters immediately

Loop integrals usually probe arbitrarily large momentum. A one-loop integral may behave at large $\ell$ like

$$
\int^{\infty}d^d\ell\,\frac{1}{\ell^2},
\qquad
\int^{\infty}d^d\ell\,\frac{1}{\ell^4},
\qquad
\text{or worse},
$$

depending on the graph. Such integrals can be ultraviolet divergent. They may also contain infrared singularities when massless particles are present.

The loop expansion therefore leads naturally to two questions:

| Question | First home in this chapter |
|---|---|
| Which diagrams can diverge by large-momentum counting? | [Superficial Degree of Divergence](/perturbative-qft/loop-expansion-regularization/superficial-degree-of-divergence/) |
| How do we make divergent integrals well defined temporarily? | cutoff and dimensional regularization pages |
| How do divergences become physical finite predictions? | renormalized perturbation theory pages |
| How do infrared singularities cancel in observables? | infrared physics and factorization pages |

A regulator is not an optional decoration. It is part of a controlled loop calculation.

## Common pitfalls

**Equating loops with powers of coupling.** In simple scalar examples, loop order and coupling order are closely related. In general, loop number counts independent internal momentum integrations. Coupling order depends on the vertices.

**Calling every internal line a loop.** A tree diagram may contain internal lines. A loop exists only when an internal momentum remains unfixed after all vertex momentum-conservation constraints are used.

**Forgetting symmetry factors.** The loop integral is not the whole graph. The contribution also includes symmetry factors, signs, numerator algebra, group factors, and counterterm insertions.

**Treating a loop momentum as a physical particle momentum.** Loop momentum is integrated over. It is not an observed momentum and need not satisfy an on-shell condition unless a cut or residue calculation places an internal line on shell.

**Assuming loop expansions converge.** Perturbative loop expansions are often asymptotic. They can be spectacularly useful without being convergent.

**Ignoring the regulator.** A divergent loop integral is not a number. It is an expression that requires a regulator, a subtraction prescription, and a statement of which renormalized quantity is being computed.

## Relations to other pages

- [Perturbative Expansion](/perturbative-qft/diagrammatics-feynman-rules/perturbative-expansion/) explains how interactions generate a series of diagrams.
- [Momentum-Space Feynman Rules](/perturbative-qft/diagrammatics-feynman-rules/momentum-space-feynman-rules/) derives the momentum integrals and vertex delta functions that leave $L$ loop momenta.
- [Symmetry Factors](/perturbative-qft/diagrammatics-feynman-rules/symmetry-factors/) explains the factor $S_\Gamma$ that divides graph overcounting.
- [One-Particle-Irreducible Diagrams](/perturbative-qft/diagrammatics-feynman-rules/one-particle-irreducible-diagrams/) organizes loop corrections to propagators, vertices, and the effective action.
- [Counterterm Diagrams Preview](/perturbative-qft/diagrammatics-feynman-rules/counterterm-diagrams-preview/) introduces how local counterterm vertices enter loop calculations.
- [Superficial Degree of Divergence](/perturbative-qft/loop-expansion-regularization/superficial-degree-of-divergence/) explains the first diagnostic for ultraviolet divergences.
- [Optical Theorem and Rates](/perturbative-qft/phase-space-cross-sections-decays/optical-theorem-and-rates/) connects loop imaginary parts to inclusive rates through unitarity.

## Research status

- **Established:** Loop order, graph topology, momentum-space loop integration, and the one-loop effective action are textbook-standard pieces of perturbative QFT.
- **Active:** High-order loop calculations remain an active research area because multi-loop amplitudes require advanced integral reduction, special functions, unitarity methods, numerical algorithms, infrared subtraction, and automation.
- **Approximate:** The loop expansion is generally an asymptotic weak-coupling expansion, not an exact nonperturbative definition of the theory.
- **Convention-dependent:** Factors of $i$, signs in the trace logarithm, and the placement of $\hbar$ depend on Lorentzian versus Euclidean conventions and on the normalization of generating functionals.

## Exercises

### Exercise 1: Derive the connected graph identity

A connected momentum-space graph has $I$ internal lines and $V$ vertices. Explain why the number of independent loop momenta is

$$
L=I-V+1.
$$

<details>
<summary><strong>Solution</strong></summary>

Assign one momentum variable to each internal line, giving $I$ variables. Momentum conservation at every vertex gives $V$ delta functions. However, one linear combination of those delta functions enforces total external momentum conservation; it does not fix an internal momentum. Therefore only $V-1$ constraints remove internal variables. The number left is

$$
L=I-(V-1)=I-V+1.
$$

Equivalently, choose a spanning tree of the connected graph. A tree connecting all vertices has $V-1$ internal edges. Every additional internal edge creates one independent cycle. Thus

$$
L=I-(V-1).
$$

</details>

### Exercise 2: Coupling order in φ⁴ theory

For connected diagrams in scalar $\phi^4$ theory, show that

$$
V=L+\frac{E}{2}-1,
$$

where $E$ is the number of external legs. What is the coupling order of an $L$-loop four-point diagram?

<details>
<summary><strong>Solution</strong></summary>

Each quartic vertex contributes four half-edges. Internal lines use two half-edges and external lines use one, so

$$
4V=2I+E.
$$

Using $L=I-V+1$, we have $I=L+V-1$. Substitute this into the half-edge equation:

$$
4V=2(L+V-1)+E.
$$

Therefore

$$
2V=2L-2+E,
$$

and hence

$$
V=L+\frac{E}{2}-1.
$$

Each vertex contributes one power of $\lambda$, so the graph is $O(\lambda^V)$. For $E=4$,

$$
V=L+1,
$$

so an $L$-loop four-point diagram is $O(\lambda^{L+1})$.

</details>

### Exercise 3: Cubic theory counting

In scalar $\phi^3$ theory, derive

$$
V=2L+E-2.
$$

Use this to find the coupling order of tree-level and one-loop four-point diagrams.

<details>
<summary><strong>Solution</strong></summary>

For cubic vertices,

$$
3V=2I+E.
$$

Again $I=L+V-1$. Therefore

$$
3V=2(L+V-1)+E,
$$

so

$$
V=2L+E-2.
$$

For $E=4$, this gives

$$
V=2L+2.
$$

Tree level has $L=0$, so $V=2$ and the diagram is $O(g^2)$. One loop has $L=1$, so $V=4$ and the diagram is $O(g^4)$.

</details>

### Exercise 4: One-loop effective action

Starting from the Gaussian fluctuation integral

$$
\int\mathcal D\eta\,
\exp\left\{\frac{i}{2\hbar}\eta A\eta\right\}
\propto (\det A)^{-1/2},
$$

explain why the one-loop effective action contains a trace logarithm.

<details>
<summary><strong>Solution</strong></summary>

Use

$$
\det A=\exp(\operatorname{Tr}\log A).
$$

Then

$$
(\det A)^{-1/2}
=\exp\left[-\frac12\operatorname{Tr}\log A\right].
$$

In Lorentzian signature, the path integral weight is $e^{i\Gamma/\hbar}$. Matching the determinant contribution to this exponential gives the schematic one-loop term

$$
\Gamma_{\rm 1-loop}
=\frac{i\hbar}{2}\operatorname{Tr}\log A,
$$

up to field-independent normalization constants and the precise $i\epsilon$ prescription. For QFT, $A$ is the second functional derivative of the action around the background field,

$$
A=S^{(2)}[\varphi].
$$

</details>

## References

- Mark Srednicki, *Quantum Field Theory*, §§14–20, for loop corrections, perturbation theory to all orders, and one-loop scattering in scalar theory.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chs. 6, 9, and 12, for Feynman rules, path-integral derivations, and renormalization power counting.
- Sidney Coleman, *Lectures on Quantum Field Theory*, chs. 15–16 and 32, for renormalization, loop expansion, and generating functionals.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chs. 15–19, for loop calculations, counterterms, and renormalized perturbation theory.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, chs. 7–9, for functional methods, loop expansion, and power counting.

## Version history

- **2026-06-12:** Initial polished draft for the Perturbative QFT and Scattering volume.
