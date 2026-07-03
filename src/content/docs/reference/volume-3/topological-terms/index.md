---
title: "Topological Terms"
description: "Chapter overview for theta terms, total derivatives, Wess–Zumino terms, Wess–Zumino–Witten terms, Chern–Simons terms, BF terms, topological response, and coupling quantization in QFT."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Coleman, Aspects of Symmetry; Srednicki §§93–94; Zee; Polyakov; Altland–Simons Ch. 8; standard Chern–Simons, Wess–Zumino, and topological-response references."
topics:
  - topological terms
  - theta terms
  - total derivatives
  - Wess Zumino terms
  - Wess Zumino Witten terms
  - Chern Simons theory
  - BF theory
  - topological response
  - large gauge transformations
canonicalTopics:
  - topological-terms
  - theta-terms
  - wess-zumino-terms
  - chern-simons-terms
  - bf-terms
  - topological-response
researchStatus:
  established:
    - "Topological terms are local action terms whose quantum effect is controlled by global sectors, quantized periods, boundaries, or background topology rather than by ordinary local equations of motion."
    - "Theta, Wess–Zumino, Wess–Zumino–Witten, Chern–Simons, and BF terms are standard tools for encoding instanton weights, anomaly matching, topological response, and global information in QFT."
  active:
    - "Modern applications refine these terms using global-form data, spin and Pin structures, higher-form backgrounds, non-invertible defects, symmetry TFT, and condensed-matter response theory."
---

Topological Terms is the chapter in the Symmetry, Anomalies, and Topology volume where the action stops being only a local equation-of-motion machine. Some terms are invisible in perturbation theory around a topologically trivial field configuration, but visible to the path integral because field space has disconnected components, nontrivial bundles, boundaries, or quantized periods.

The chapter exists because many of the most important pieces of QFT data are phases. A theta angle weights instanton sectors. A Wess–Zumino term remembers an extension into one higher dimension. A Chern–Simons term turns a connection into a topological response. A BF term records linking and higher-form gauge structure. These are not decorative additions; they are often the difference between two physically distinct quantum theories with the same local classical equations.

The guiding slogan is:

$$
\text{topological term}=\text{local density whose quantum meaning is global}.
$$

<figure class="doc-figure" style="--figure-width: 60rem;">

![Roadmap diagram showing how local topological densities lead to quantized periods, path-integral phases, boundary inflow, and physical response, with branches to theta, Wess–Zumino, Chern–Simons, BF, and response terms.](/figures/symmetry-anomalies-topology/topological-terms-roadmap.svg)

<figcaption>

A topological term is read in two passes. Locally it may be a closed form, a total derivative, or a term with no metric dependence. Globally it assigns phases to sectors, bundles, extensions, links, or boundaries. The quantization conditions are part of the definition, not optional tidiness.

</figcaption>
</figure>

This chapter is intentionally placed after anomalies and ’t Hooft anomalies. Topological terms are not only examples of interesting actions; they are also the language in which many anomalies, inflow mechanisms, and topological responses are written.

## Prerequisites

You should know the volume [Conventions and Notation](/symmetry-anomalies-topology/conventions/), especially the differential-form convention $F=dA-iA\wedge A$, the instanton normalization

$$
k=\frac{1}{8\pi^2}\int_{X_4}\operatorname{tr}(F\wedge F),
$$

and the Chern–Simons three-form normalization used there.

The most useful earlier pages are [Background Fields for Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-for-global-symmetries/), [Gauging Global Symmetries](/symmetry-anomalies-topology/background-fields-and-gauging/gauging-global-symmetries/), [Large Gauge Transformations](/symmetry-anomalies-topology/gauge-redundancy-brst/large-gauge-transformations/), [Anomaly Polynomial](/symmetry-anomalies-topology/anomalies/anomaly-polynomial/), [Descent Equations](/symmetry-anomalies-topology/anomalies/descent-equations/), and [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/).

For the first pass, it is enough to know differential forms, Stokes’ theorem, compact gauge fields, and the idea that a path integral can sum over topological sectors. Later pages use characteristic classes, spin structures, finite-group cohomology, and higher-form gauge fields.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | Theta Terms | The canonical example: an integer topological charge $Q$ is weighted by the phase $e^{i\theta Q}$. |
| 2 | Total Derivatives That Matter | Why a total derivative can change a quantum theory on nontrivial spacetime, with boundaries, or across sectors. |
| 3 | Wess–Zumino Terms | How a term defined by extending fields into one higher dimension can encode quantized global information. |
| 4 | Wess–Zumino–Witten Terms | The anomaly-matching version of Wess–Zumino terms, especially for chiral symmetry breaking. |
| 5 | Chern–Simons Terms | The odd-dimensional gauge term whose level quantization, boundary variation, and link invariants are central to QFT. |
| 6 | BF Theory Terms | The topological coupling $B\wedge F$, higher-form gauge fields, linking phases, and discrete gauge theory previews. |
| 7 | Topological Response | How background topological terms encode measurable response in phases of matter and QFT. |
| 8 | Quantization of Couplings | Why coefficients of topological terms are often integer, periodic, or spin-structure dependent. |
| 9 | Periodicity and Large Gauge Transformations | How large transformations identify couplings, shift actions, and create nontrivial periodic parameter spaces. |
| 10 | Witten Effect: Preview | The theta-angle shift of electric charge on magnetic monopoles and its modern higher-form interpretation. |
| 11 | Eta Invariants: Preview | The spectral asymmetry language behind parity anomalies, fermionic phases, and global anomaly inflow. |

A reader who mainly wants anomaly applications should read Theta Terms, Wess–Zumino–Witten Terms, Chern–Simons Terms, and Eta Invariants. A reader focused on phases of matter should read Chern–Simons Terms, BF Theory Terms, Topological Response, and Quantization of Couplings.

## Landmarks

The first landmark is that **locally trivial need not mean globally trivial**. If

$$
\omega_d=d\alpha_{d-1},
$$

then $\int_{M_d}\omega_d$ vanishes on a contractible field patch with no boundary. But QFT rarely gives us only that patch. Nontrivial bundles, singular gauge choices, winding sectors, and boundaries can make the same integral quantized, periodic, or physically measurable.

The second landmark is that **the path integral sees phases, not only equations of motion**. A topological charge $Q\in\mathbb Z$ produces

$$
Z(\theta)=\sum_{Q\in\mathbb Z}e^{i\theta Q}Z_Q,
$$

so two theories with the same local Euler–Lagrange equations may differ because they weight sectors differently.

The third landmark is **quantization of coefficients**. If a term is not strictly invariant but changes by $2\pi k$ under a large gauge transformation or a different extension, then $e^{iS}$ is still invariant only when the coefficient obeys a quantization law. This is the basic reason Chern–Simons levels, Wess–Zumino levels, BF coefficients, and some response coefficients are discrete.

The fourth landmark is **boundary inflow**. On a manifold with boundary, a bulk topological term can fail to be invariant by a boundary variation. That failure is not a bug if it is canceled by anomalous boundary degrees of freedom. This is the same logic that later becomes symmetry TFT and relative QFT.

The fifth landmark is **global form and spin data**. The same local Lie algebra can allow different bundles and line operators. The same differential form can have different allowed periods on spin and non-spin manifolds. Topological terms are usually where these distinctions become impossible to ignore.

## Common confusions

**“A total derivative cannot matter.”** It cannot change classical local equations on a closed topologically trivial field patch. That is a much weaker statement than “it cannot matter in QFT.” Theta terms and Chern–Simons boundary terms are the counterexamples you should keep in your pocket.

**“Topological term means metric-independent theory.”** A QFT may contain one topological term while the full theory is very metric dependent. Yang–Mills theory with a theta term is not a TQFT. Chern–Simons theory without a Yang–Mills kinetic term is much closer to a TQFT.

**“The coefficient can be any real number.”** Sometimes yes, as with a continuous theta angle modulo periodicity. Sometimes no, as with a Chern–Simons level on a closed three-manifold. The allowed coefficient depends on the allowed field configurations and large transformations.

**“Theta equals pi is just another point.”** It can be, but often it is special because orientation reversal sends $\theta\mapsto-\theta$ and periodicity identifies $-\pi$ with $\pi$. This is why CP or time-reversal questions frequently sharpen at $\theta=\pi$.

**“The differential form formula fixes the answer.”** The form formula fixes the local density. The quantum theory also needs global normalization: which bundles are allowed, what the periods are, which manifolds are included, and whether the theory is bosonic, spin, spin${}_c$, or Pin.

**“Wess–Zumino terms are optional decorations.”** In many effective field theories they are forced by anomaly matching. Removing them would give the wrong symmetry realization.

## Boundaries

This chapter explains topological terms as action terms and response functionals. It is not the canonical home for every object they touch.

The topology of field configurations, instanton number, vortices, monopoles, skyrmions, and domain walls are developed in the next chapter, Topological Sectors and Solitonic Charges.

Wilson lines, ’t Hooft lines, disorder operators, surface operators, boundaries, interfaces, and defect fusion belong to the Defects and Extended Operators chapter.

Higher-form backgrounds, gauging higher-form symmetries, and center symmetry belong to the Higher-Form and Generalized Symmetries chapter.

A full treatment of Chern–Simons theory, BF theory, Dijkgraaf–Witten theory, and cohomological TQFT as standalone theories belongs to the Topological Quantum Field Theory chapter. This chapter focuses on how topological terms appear inside ordinary QFTs and effective actions.

Detailed condensed-matter phases, quantum Hall systems, and topological order belong to the Matter, Statistical Physics, and Quantum Information volume, though this chapter supplies much of the shared language.

## Where to go next

After this chapter, the most natural continuation is [Topological Sectors and Solitonic Charges](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/). Theta terms are much easier to understand once instantons, winding number, monopoles, and topological charge have their own page-level homes.

For symmetry constraints, continue to [Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/) and [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/). For anomaly applications, return to [Anomaly Inflow: Preview](/symmetry-anomalies-topology/thooft-anomalies-anomaly-matching/anomaly-inflow-preview/) and then read the later Symmetry TFT chapter.

For physical examples outside this volume, the closest destinations are Yang–Mills theta vacua in gauge theory, nonlinear sigma models in matter and critical phenomena, Chern–Simons response in quantum Hall physics, and axion couplings in effective field theory.

## References

- Sidney Coleman, *Aspects of Symmetry*, especially “Classical Lumps and Their Quantum Descendants” and “The Uses of Instantons.”
- Mark Srednicki, *Quantum Field Theory*, §§93–94, for instantons, theta vacua, and quark-mass dependence of the QCD theta angle.
- A. Zee, *Quantum Field Theory in a Nutshell*, for physically motivated discussions of topology, monopoles, anomalies, sigma models, and Chern–Simons terms.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on instantons, topology of gauge fields, loop dynamics, and gauge/string viewpoints.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, Ch. 8, for theta, Wess–Zumino, and Chern–Simons terms in matter-oriented field theory.
- Edward Witten, “Quantum Field Theory and the Jones Polynomial,” *Communications in Mathematical Physics* **121** (1989), for Chern–Simons theory as a topological quantum field theory.
- Edward Witten, “Dyons of Charge $e\theta/2\pi$,” *Physics Letters B* **86** (1979), for the Witten effect.
- Edward Witten, “Global Aspects of Current Algebra,” *Nuclear Physics B* **223** (1983), for Wess–Zumino–Witten terms and anomaly matching.

## Version history

- 2026-06-18: Initial polished draft for the improved Symmetry, Anomalies, and Topology plan.
