---
title: "Open Problems and Research Map"
description: "A research-oriented map of open directions in AdS/CFT, from bulk locality and reconstruction to black-hole interiors, wormholes, cosmology, complexity, and finite-N quantum gravity."
sidebar:
  order: 70
---

This course has built AdS/CFT from the ground up: large-$N$ gauge theory, AdS geometry, D-branes, the GKP/Witten dictionary, holographic renormalization, correlators, black branes, entanglement, AdS$_3$/CFT$_2$, applications, and the emergence of bulk quantum gravity from CFT data.

This final page is not a list of unsolved slogans. It is a research map. The point is to separate what is well understood from what is still structurally incomplete, and to show how a graduate student can enter the subject without being buried under folklore.

The organizing question is:

$$
\text{What does a complete nonperturbative CFT definition teach us about quantum gravity?}
$$

A useful answer has several layers:

$$
\text{CFT data}
\longrightarrow
\text{bulk effective field theory}
\longrightarrow
\text{black holes and horizons}
\longrightarrow
\text{nonperturbative quantum gravity}.
$$

Each arrow is partly understood. Each arrow is also where many open problems live.

## What is already solid?

Before discussing open problems, it is worth naming what is not merely speculative.

In controlled examples, AdS/CFT gives an exact equivalence between a non-gravitational quantum theory and a quantum theory of gravity in asymptotically AdS spacetime. In the canonical example,

$$
\mathcal N=4\; SU(N)\; \text{SYM}
\quad
\longleftrightarrow
\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5 .
$$

In the large-$N$, large-$\lambda$ regime, the bulk reduces to classical supergravity. The classical equations, black branes, Witten diagrams, holographic renormalization, RT/HRT surfaces, QES corrections, and real-time prescriptions are not decorative analogies. They are calculational limits of a sharper quantum statement.

But “there is a CFT” does not automatically mean that every bulk question is solved in the form we want. AdS/CFT often gives an answer in principle while leaving a hard problem of translation.

For example, exact boundary unitarity tells us that black-hole evolution in AdS is unitary. That does not by itself give a local semiclassical description of the interior at all times, a microscopic basis of black-hole states, or a simple rule for summing over gravitational saddles. Those are different levels of understanding.

## The map at a glance

<figure class="doc-figure" style="--figure-width: 58rem;">

![Research map for open problems in AdS/CFT](/figures/course/open-problems-research-map.svg)

<figcaption>

A research map for the final unit. The central theme is the emergence and limitation of bulk quantum gravity from boundary CFT data. The arrows are not a linear curriculum: progress usually comes from moving back and forth between CFT consistency, bulk effective theory, black-hole physics, and non-AdS aspirations.

</figcaption>
</figure>

The cleanest research questions usually live at an interface:

- between CFT data and local bulk EFT;
- between semiclassical reconstruction and exact finite-$N$ operators;
- between Euclidean gravitational saddles and factorization in a fixed CFT;
- between black-hole entropy formulas and microscopic Hilbert-space accounting;
- between AdS holography and cosmological or flat-space observables.

The rest of the page turns these interfaces into concrete problem families.

## 1. Which CFTs have local bulk duals?

The course repeatedly used a simple rule of thumb:

$$
\text{large } N
+
\text{sparse light single-trace spectrum}
\quad
\Longrightarrow
\quad
\text{semiclassical local bulk EFT}.
$$

This is a powerful criterion, but it is not the end of the story.

A CFT is specified by its spectrum and OPE coefficients,

$$
\{\Delta_i,\ell_i,C_{ijk}\},
$$

subject to crossing symmetry, unitarity, reflection positivity, Ward identities, and other consistency conditions. A bulk effective theory is specified by fields, masses, couplings, gauge redundancies, higher-derivative terms, and a cutoff. The research program is to understand the map

$$
\{\Delta_i,\ell_i,C_{ijk}\}_{\mathrm{CFT}}
\quad
\longleftrightarrow
\quad
\mathcal L_{\mathrm{bulk}}^{\mathrm{EFT}}
$$

as sharply as possible.

### What is known

Large-$N$ factorization gives weak bulk interactions. A large gap $\Delta_{\mathrm{gap}}$ to higher-spin or stringy single-trace operators allows interactions to be organized in a derivative expansion. In Mellin space, local AdS interactions behave more like polynomial scattering amplitudes, which makes bulk locality visible in CFT correlators.

For four-point functions, the basic pattern is:

$$
\text{crossing}+\text{large }N+\text{gap}
\quad
\Rightarrow
\quad
\text{contact and exchange Witten diagrams at low energy}.
$$

The boundary bootstrap then becomes a way to ask which bulk EFTs are compatible with exact CFT consistency.

### What remains open

A few representative questions:

1. **Necessity and sufficiency.** Exactly which CFT conditions are necessary and sufficient for a local weakly curved bulk dual?
2. **Sharp locality.** How does approximate bulk locality fail at finite $N$, finite gap, or near black-hole horizons?
3. **Emergent gauge redundancy.** How precisely do bulk diffeomorphism and gauge redundancy arise from the boundary operator algebra?
4. **String scale from CFT data.** Can one systematically extract the full stringy tower and worldsheet structure from boundary correlators?
5. **Classification.** Is there a useful classification of holographic CFTs, analogous to universality classes in ordinary critical phenomena?

A useful research attitude is: do not ask only whether a CFT “has a gravity dual.” Ask what kind of bulk description it has, at what scale, in which code subspace, and with what error terms.

## 2. What exactly is a bulk point?

At leading order in $1/N$, a free bulk scalar can be reconstructed as a smeared boundary operator:

$$
\phi(X)
=
\int_{\partial \mathrm{AdS}} d^d x\,K(X|x)\mathcal O(x)+O(1/N).
$$

Interactions require multi-trace corrections. Gauge fields and gravitons require dressing. Subregion reconstruction requires entanglement wedges. At finite $N$, the very phrase “local bulk operator” becomes approximate.

The deeper question is:

$$
\text{What boundary object is a local bulk event?}
$$

The answer depends on the regime.

In semiclassical EFT, a bulk point is operationally meaningful if probes can resolve it without creating a black hole or exciting stringy physics. In the CFT, this locality must be encoded nonlocally in operator algebras, OPE data, modular flow, and code-subspace structure.

### Open directions

- **Bulk locality beyond perturbation theory.** HKLL reconstruction is perturbative. What replaces it nonperturbatively?
- **Gravitational dressing.** Gauge-invariant bulk observables must be dressed to the boundary or to relational structures. How unique or state-dependent is this dressing?
- **Entanglement wedge reconstruction.** The equivalence between bulk reconstruction and quantum error correction is powerful, but making it explicit in interacting, time-dependent, finite-$N$ systems remains hard.
- **Operator-algebra subtleties.** In gravity, local algebras do not factorize in the naive way. The correct algebraic description of subregions is still an active interface between QFT, gravity, and quantum information.
- **Interior reconstruction.** Behind-horizon reconstruction is especially delicate because the semiclassical interior can depend on the state and on the code subspace.

The clean slogan is:

$$
\text{bulk locality is real, but approximate and encoded.}
$$

The research problem is to quantify “approximate” and make “encoded” explicit.

## 3. How should we understand black-hole interiors?

AdS/CFT tells us that black holes are states or ensembles of states in an ordinary quantum system. That is a profound statement, but the interior remains subtle.

For the eternal AdS black hole, the two-sided geometry is dual to the thermofield-double state,

$$
|\mathrm{TFD}\rangle
=
\frac{1}{\sqrt{Z(\beta)}}
\sum_n e^{-\beta E_n/2}|n\rangle_L |n\rangle_R .
$$

For one-sided black holes, the geometry should be encoded in a single CFT state. Before the Page time, semiclassical effective theory often gives a useful interior. After the Page time, the island formula and entanglement-wedge reconstruction imply that parts of the interior can be encoded in radiation degrees of freedom.

The open problem is not simply “is information lost?” In AdS/CFT, the boundary answer is no. The sharper questions are:

1. What is the microscopic origin of the smooth interior?
2. How does interior reconstruction depend on state, time, and code subspace?
3. What happens to semiclassical locality at times of order the Page time, scrambling time, or recurrence time?
4. How do singularities appear in the exact boundary theory?
5. Can one construct a precise boundary diagnostic for the late-time interior?

The tension is that the same bulk region can sometimes be reconstructed from different boundary regions. This is not ordinary redundancy. It is quantum-error-correcting redundancy, and it becomes most dramatic for black-hole interiors.

## 4. What is the gravitational path integral computing?

The semiclassical gravitational path integral often instructs us to sum over saddles:

$$
Z_{\mathrm{grav}}[J]
\sim
\sum_{\mathcal M:\,\partial\mathcal M=J}
\exp\left(-I_E[\mathcal M]
ight).
$$

This formula is useful. It computes thermodynamics, saddles behind the Hawking–Page transition, replica geometries, and island contributions. But it is also dangerous if treated as a complete definition without specifying contour, boundary conditions, ensemble, and microscopic theory.

A fixed ordinary CFT obeys factorization. For two independent copies,

$$
Z_{\mathrm{CFT}\times \mathrm{CFT}}[J_1,J_2]
=
Z_{\mathrm{CFT}}[J_1]Z_{\mathrm{CFT}}[J_2].
$$

Euclidean wormholes connecting two asymptotic boundaries appear to threaten this factorization. In lower-dimensional models such as JT gravity, wormholes are closely related to ensemble averages. In ordinary fixed AdS/CFT dual pairs, the interpretation is less straightforward.

### Open directions

- **Contour problem.** What is the correct nonperturbative integration cycle for gravitational path integrals?
- **Factorization.** How do connected Euclidean saddles coexist with factorization in a fixed CFT?
- **Baby universes.** Are baby-universe Hilbert spaces bookkeeping devices, physical sectors, or artifacts of incomplete definitions?
- **Lorentzian versus Euclidean.** Which Euclidean saddles are legitimate contributions to Lorentzian observables?
- **Replica wormholes.** What is the most microscopic derivation of replica wormhole contributions in top-down AdS/CFT examples?

The conservative lesson is: the path integral is a powerful semiclassical expansion, but AdS/CFT forces us to ask what exact quantum object it approximates.

## 5. What is the microscopic meaning of horizons and entropy?

The Bekenstein–Hawking entropy formula

$$
S_{\mathrm{BH}}=\frac{A}{4G_N}
$$

is one of the strongest clues that geometry counts quantum states. In AdS/CFT, black-hole entropy is boundary thermal entropy. That is a huge success.

But a research-level understanding asks for more:

- Which CFT states look like a given semiclassical black-hole geometry?
- How does coarse-grained entropy differ from fine-grained entropy in gravitational language?
- Which bulk observables distinguish typical microstates from the ensemble geometry?
- How do small black holes, string-scale black holes, fuzzball-like structures, and high-energy string states fit into one Hilbert-space story?
- Can we describe singularity resolution without leaving the CFT language?

There is a hierarchy of entropies that should not be conflated:

$$
S_{\mathrm{thermal} }
\neq
S_{\mathrm{entanglement} }
\neq
S_{\mathrm{coarse\,grained} }
\neq
S_{\mathrm{fine\,grained} }
$$

unless a specific argument says otherwise.

The Page curve and island formula give a major advance for fine-grained radiation entropy:

$$
S(R)
=
\min_{I}\,\mathrm{ext}_{I}\left[
\frac{\mathrm{Area}(\partial I)}{4G_N}+S_{\mathrm{bulk}}(R\cup I)
\right].
$$

But this formula should not be mistaken for a complete local movie of information escaping. It gives an entropy prescription and an entanglement-wedge statement. The microscopic real-time mechanism remains a rich research subject.

## 6. What survives beyond classical AdS?

The cleanest course pages focused on the regime

$$
N\gg 1,
\qquad
\lambda\gg 1,
\qquad
\Delta_{\mathrm{gap}}\gg 1.
$$

But quantum gravity is not only classical Einstein gravity.

There are at least four important correction regimes:

$$
\begin{array}{ccl}
1/N^2 &:& \text{bulk loops},\\
1/\lambda &:& \alpha' \text{ or stringy corrections},\\
1/\Delta_{\mathrm{gap}} &:& \text{higher-derivative EFT corrections},\\
e^{-N},e^{-\sqrt\lambda} &:& \text{nonperturbative effects}.
\end{array}
$$

Some open questions are computational: extracting higher-derivative terms from CFT data, computing finite-coupling corrections to transport, or organizing loop corrections to holographic entropy. Others are conceptual: understanding how the bulk description reorganizes when the string scale is comparable to the AdS scale.

One particularly important frontier is the stringy regime of $
cal N=4$ SYM at finite $\lambda$. The bulk is no longer a small correction to Einstein gravity; it is a genuinely stringy AdS background. Questions that are easy in classical gravity can become hard worldsheet or integrability problems.

Another frontier is finite $N$. At finite $N$, exact trace relations, finite Hilbert-space effects at fixed energy, nonperturbative spectral discreteness, and black-hole microstate physics all matter. The semiclassical bulk may still be an excellent approximation for many questions, but it cannot be the final description.

## 7. Can AdS/CFT teach us about flat space and cosmology?

AdS has a timelike boundary and a natural Hamiltonian. Cosmology does not. This is one reason AdS/CFT is technically controlled while de Sitter and flat-space holography remain less complete.

Still, there are several important research programs.

### Flat-space limits

One can try to recover flat-space scattering from AdS by taking

$$
L_{\mathrm{AdS}}\to\infty
$$

while focusing on local bulk processes whose size is much smaller than $L_{\mathrm{AdS}}$. In this limit, CFT correlators should encode an $S$-matrix-like object. Mellin amplitudes, wavepacket methods, and celestial transforms are all parts of this story.

Open questions include:

- What boundary observables best capture flat-space scattering?
- How does black-hole formation and evaporation appear in flat-space limits?
- Can one define flat-space quantum gravity holographically without embedding it in AdS first?

### de Sitter and cosmology

de Sitter space has spacelike future infinity, cosmological horizons, and no globally timelike boundary where an ordinary unitary Hamiltonian evolution obviously lives. This makes the dictionary much harder.

Questions include:

- What are the correct observables in quantum cosmology?
- Is there a microscopic dual of de Sitter quantum gravity?
- How should horizon entropy be counted?
- Can lessons from AdS entanglement, islands, and QEC survive in cosmology?
- What does string theory allow or forbid for long-lived de Sitter vacua?

Here the right attitude is cautious. AdS/CFT provides tools and constraints, but it is not yet a solved theory of our universe.

## 8. What are the right observables?

In ordinary QFT, local gauge-invariant operators are often the basic observables. In quantum gravity, exact local observables are obstructed by diffeomorphism invariance. In AdS/CFT, boundary correlators are exact observables, while local bulk fields are approximate, dressed, and code-subspace dependent.

This leads to a broad research question:

$$
\text{Which observables are fundamental, and which are emergent?}
$$

Examples:

- boundary correlation functions;
- modular Hamiltonians and relative entropy;
- Wilson loops and defect operators;
- entanglement entropy and generalized entropy;
- spectral statistics and late-time thermal correlators;
- scattering observables in flat-space limits;
- complexity-like quantities;
- algebraic centers and edge modes;
- relational bulk observables.

Complexity is especially intriguing because it appears sensitive to spacetime regions that are not captured by ordinary entanglement entropy. The conjectures

$$
\mathcal C \sim \frac{\mathrm{Vol}}{G_N L}
\qquad\text{or}\qquad
\mathcal C \sim \frac{I_{\mathrm{WDW}}}{\pi}
$$

suggest that quantum computational complexity may diagnose the growth of black-hole interiors. But these formulas are less settled than RT, HRT, or QES. They are research proposals, not dictionary entries of the same status.

## 9. How do singularities appear in the CFT?

Classical general relativity predicts singularities inside black holes and in cosmology. A complete theory of quantum gravity should replace or reinterpret them.

AdS/CFT offers a nonperturbative description of the boundary time evolution, so singularities cannot signal a breakdown of the whole quantum theory. But it remains hard to say exactly what replaces the local bulk description.

Open directions include:

- boundary diagnostics of spacelike singularities;
- CFT signatures of crunching AdS cosmologies;
- stringy resolution of orbifold and conifold singularities;
- role of black-hole interiors in typical high-energy states;
- whether singularity resolution is visible in finite-time boundary correlators or only in more nonlocal observables.

A good rule is:

$$
\text{CFT unitarity resolves the evolution problem, not automatically the geometric interpretation problem.}
$$

## 10. What should a beginning researcher actually work on?

The field is too large to “learn all of AdS/CFT” before beginning research. A better plan is to choose an interface and learn outward from it.

### Path A: CFT data to bulk EFT

Prerequisites: conformal bootstrap, large-$N$ perturbation theory, Witten diagrams, Mellin amplitudes.

Typical questions:

- Which CFT bounds imply bulk causality or positivity?
- How do higher-derivative bulk couplings appear in anomalous dimensions?
- How do loop-level bulk effects appear in CFT data?

### Path B: Reconstruction and quantum error correction

Prerequisites: HKLL, RT/HRT, QES, modular flow, operator algebras, basic quantum information.

Typical questions:

- Can one explicitly reconstruct operators in time-dependent backgrounds?
- How does reconstruction change beyond leading order in $1/N$?
- What is the algebraic structure of gravitational subregions?

### Path C: Black holes and information

Prerequisites: thermal AdS/CFT, QNMs, entanglement wedges, islands, replica methods.

Typical questions:

- What is the microscopic meaning of island saddles?
- How do wormholes coexist with factorization?
- Which boundary observables detect the interior?

### Path D: Stringy and finite-coupling holography

Prerequisites: $
cal N=4$ SYM, integrability or string perturbation theory, supergravity spectra.

Typical questions:

- How do stringy corrections modify transport and chaos?
- Can one compute nonprotected correlators at intermediate coupling?
- How do string worldsheets encode bulk locality?

### Path E: Beyond AdS

Prerequisites: asymptotic symmetries, scattering theory, cosmology, celestial amplitudes, de Sitter geometry.

Typical questions:

- What is the correct holographic observable for flat space?
- Can celestial or Carrollian structures become a complete dictionary?
- What part of the AdS entanglement story survives in cosmology?

## A practical research heuristic

When reading a paper, ask five questions.

1. **What is the regime?** Classical gravity, stringy correction, bulk loop, exact CFT, bottom-up model?
2. **What is the observable?** Correlator, entropy, spectrum, Wilson loop, complexity, partition function?
3. **What is controlled?** Large $N$, large gap, supersymmetry, integrability, effective theory, numerics?
4. **What is being inferred?** A dictionary entry, a universal theorem, a model calculation, or a conjectural analogy?
5. **What would falsify or sharpen it?** Crossing constraints, Ward identities, positivity, exact CFT data, top-down embedding?

These questions prevent a lot of holographic confusion.

## Dictionary checkpoint

The course ends with a mature version of the dictionary:

| Boundary statement | Bulk interpretation |
|---|---|
| exact CFT Hilbert space | nonperturbative quantum gravity in AdS |
| large-$N$ factorization | weakly interacting bulk fields |
| large spectral gap | local bulk EFT below the gap |
| CFT crossing and unitarity | bulk causality, positivity, and consistency constraints |
| modular/entanglement data | entanglement wedges and gravitational equations |
| finite $N$ | quantum gravity corrections and nonperturbative effects |
| thermal CFT spectrum | black-hole microstates |
| CFT factorization | constraint on gravitational wormhole sums |
| lack of exact bulk locality | diffeomorphism invariance and finite-$N$ encoding |

The main lesson is not that the bulk is an illusion. The lesson is subtler: the bulk is an emergent, extraordinarily useful, but regime-dependent language for organizing exact boundary quantum dynamics.

## Common confusions

### “AdS/CFT solves quantum gravity, so there are no open problems.”

No. AdS/CFT gives a nonperturbative definition in controlled AdS examples. It does not automatically translate every gravitational question into a simple boundary calculation, nor does it give a complete theory of de Sitter cosmology or flat-space holography.

### “If information is unitary in the CFT, the black-hole interior is fully understood.”

Boundary unitarity is a crucial constraint, but a local semiclassical description of the interior is a separate emergent question. The island and QEC stories sharpen the encoding, but many details remain open.

### “Wormholes mean the dual theory must be an ensemble average.”

Sometimes ensemble averaging is the right interpretation, especially in simple lower-dimensional models. But fixed AdS/CFT dual pairs should factorize. The general lesson is not “all wormholes are wrong” or “all holography is an ensemble”; the hard question is how the gravitational path integral is completed in each microscopic theory.

### “A bottom-up model with a nice black hole is automatically a consistent quantum gravity.”

No. A bottom-up model can be useful and even predictive in a limited regime, but consistency as a full quantum gravity requires more: UV completion, spectrum constraints, absence of forbidden global symmetries, causality, positivity, and embedding into a complete microscopic theory or a clearly defined effective domain.

### “Finite $N$ is just a small correction.”

For some observables and time scales, yes. For black-hole microstates, spectral discreteness, late-time correlators, factorization, and nonperturbative effects, finite $N$ can qualitatively change the answer.

## Exercises

### Exercise 1: Classify the problem

For each question below, classify it as primarily about CFT data, bulk EFT, reconstruction, black holes, path integrals, or beyond-AdS holography. Some questions have more than one correct label.

1. Which four-point functions are compatible with a local quartic bulk interaction?
2. How can an operator behind a black-hole horizon be reconstructed from boundary degrees of freedom?
3. Why do Euclidean wormhole saddles not violate factorization in a fixed CFT?
4. How can a flat-space scattering amplitude be extracted from CFT correlators?
5. How does a finite-$\lambda$ correction change $\eta/s$?

<details>
<summary><strong>Solution</strong></summary>

1. CFT data and bulk EFT. The relevant tools are crossing symmetry, large-$N$ perturbation theory, Witten diagrams, Mellin amplitudes, and higher-derivative bulk interactions.
2. Reconstruction, quantum error correction, and black holes. The relevant concepts are entanglement wedges, code subspaces, state dependence, and interior reconstruction.
3. Gravitational path integrals and black-hole information. This is the factorization problem: a fixed CFT factorizes, while some semiclassical wormhole saddles appear connected.
4. Beyond-AdS holography and CFT data. This belongs to the flat-space limit of AdS/CFT, often formulated using wavepackets or Mellin amplitudes.
5. Stringy and quantum corrections to bulk EFT. At finite $\lambda$, higher-derivative terms such as $\alpha'^3 R^4$ corrections can modify transport coefficients.

</details>

### Exercise 2: Why a large gap matters

Explain why large $N$ alone is not enough to guarantee a local Einstein gravity dual.

<details>
<summary><strong>Solution</strong></summary>

Large $N$ suppresses connected correlators and suggests weak bulk interactions, but it does not guarantee that the only light single-trace operator of spin greater than two is absent. If there is an infinite tower of light higher-spin or stringy operators with dimensions of order one, the bulk cannot be well described by a local low-energy Einstein theory with a finite number of light fields.

A large gap $\Delta_{\mathrm{gap}}$ separates the low-energy bulk fields from stringy or higher-spin excitations. Below that gap, one can organize the bulk dynamics as an effective field theory with higher-derivative corrections suppressed by powers of $1/\Delta_{\mathrm{gap}}$.

</details>

### Exercise 3: Factorization as a boundary constraint

Suppose two decoupled identical CFTs have sources $J_1$ and $J_2$. Write the factorization condition for their partition function. Why is this condition nontrivial from the bulk point of view?

<details>
<summary><strong>Solution</strong></summary>

For two decoupled theories,

$$
Z_{\mathrm{CFT}\times\mathrm{CFT}}[J_1,J_2]
=
Z_{\mathrm{CFT}}[J_1]Z_{\mathrm{CFT}}[J_2].
$$

From the bulk point of view, one might try to sum over all Euclidean geometries with the prescribed asymptotic boundaries. Some of these geometries can connect the two boundaries, producing a contribution that looks non-factorized. The problem is to understand whether such saddles are absent, canceled, interpreted as ensemble-averaged contributions, or completed by additional microscopic data in a fixed AdS/CFT dual pair.

</details>

### Exercise 4: An honest open problem

Choose one of the following slogans and rewrite it as a precise research question.

1. “Spacetime comes from entanglement.”
2. “Black holes are quantum error-correcting codes.”
3. “The radial direction is the RG scale.”
4. “de Sitter holography should exist.”

<details>
<summary><strong>Solution</strong></summary>

Possible precise versions are:

1. Which class of entanglement measures, modular Hamiltonians, or relative entropies determines the bulk metric in a given code subspace, and with what assumptions?
2. For a specified AdS black-hole background and code subspace, which boundary regions can reconstruct which interior operators, and what are the finite-$N$ error bounds?
3. Given an Einstein-scalar domain wall dual to a relevant deformation, how do holographic beta functions compare with field-theory beta functions defined by a particular renormalization scheme?
4. What is the Hilbert space, observable algebra, and entropy interpretation for quantum gravity in asymptotically de Sitter spacetime, and can these data be realized by a concrete microscopic model?

The purpose of the exercise is to turn slogans into falsifiable or computable questions.

</details>

## Further reading

Foundational references:

- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200).
- E. Witten, [Anti de Sitter Space and Holography](https://arxiv.org/abs/hep-th/9802150).
- O. Aharony, S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111).

Bulk emergence, locality, and reconstruction:

- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, [Holography from Conformal Field Theory](https://arxiv.org/abs/0907.0151).
- D. Harlow, [TASI Lectures on the Emergence of Bulk Physics in AdS/CFT](https://arxiv.org/abs/1802.01040).
- A. Hamilton, D. Kabat, G. Lifschytz, and D. Lowe, [Local Bulk Operators in AdS/CFT](https://arxiv.org/abs/hep-th/0506118).
- A. Almheiri, X. Dong, and D. Harlow, [Bulk Locality and Quantum Error Correction in AdS/CFT](https://arxiv.org/abs/1411.7041).
- X. Dong, D. Harlow, and A. Wall, [Reconstruction of Bulk Operators within the Entanglement Wedge in Gauge-Gravity Duality](https://arxiv.org/abs/1601.05416).

Black holes, islands, and information:

- J. Maldacena, [Eternal Black Holes in Anti-de Sitter](https://arxiv.org/abs/hep-th/0106112).
- D. Harlow, [Jerusalem Lectures on Black Holes and Quantum Information](https://arxiv.org/abs/1409.1231).
- A. Lewkowycz and J. Maldacena, [Generalized Gravitational Entropy](https://arxiv.org/abs/1304.4926).
- T. Faulkner, A. Lewkowycz, and J. Maldacena, [Quantum Corrections to Holographic Entanglement Entropy](https://arxiv.org/abs/1307.2892).
- G. Penington, [Entanglement Wedge Reconstruction and the Information Paradox](https://arxiv.org/abs/1905.08255).
- A. Almheiri, N. Engelhardt, D. Marolf, and H. Maxfield, [The Entropy of Bulk Quantum Fields and the Entanglement Wedge of an Evaporating Black Hole](https://arxiv.org/abs/1905.08762).

Beyond AdS and speculative frontiers:

- J. Penedones, [Writing CFT Correlation Functions as AdS Scattering Amplitudes](https://arxiv.org/abs/1011.1485).
- A. Strominger, [The dS/CFT Correspondence](https://arxiv.org/abs/hep-th/0106113).
- E. Witten, [Quantum Gravity in de Sitter Space](https://arxiv.org/abs/hep-th/0106109).
- S. Pasterski, S.-H. Shao, and A. Strominger, [Flat Space Amplitudes and Conformal Symmetry of the Celestial Sphere](https://arxiv.org/abs/1701.00049).
- A. Brown, D. Roberts, L. Susskind, B. Swingle, and Y. Zhao, [Complexity Equals Action](https://arxiv.org/abs/1509.07876).
