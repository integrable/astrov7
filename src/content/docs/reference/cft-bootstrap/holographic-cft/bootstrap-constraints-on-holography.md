---
title: "Bootstrap Constraints on Holography"
description: "How crossing symmetry, unitarity, causality, Regge behavior, Mellin boundedness, entropy, and numerical bootstrap constrain which CFTs can have consistent AdS gravity duals."
sidebar:
  label: "Bootstrap Constraints on Holography"
  order: 12
level: Advanced
status: "Polished draft"
source: "Heemskerk et al.; Fitzpatrick et al.; Hofman and Maldacena; Camanho et al.; Caron-Huot; Poland, Rychkov, and Vichi; holographic bootstrap literature."
topics:
  - holographic bootstrap
  - AdS/CFT
  - crossing symmetry
  - causality
  - quantum gravity constraints
canonicalTopics:
  - bootstrap-constraints-on-holography
  - holographic-bootstrap-constraints
  - cft-constraints-on-quantum-gravity
researchStatus:
  established:
    - "Crossing symmetry, unitarity, causality, and Regge behavior impose strong constraints on large-N CFT data and the associated AdS effective field theories."
    - "Large central charge, sparse spectra, and higher-spin gaps are central conditions for semiclassical holography."
  active:
    - "Current research develops quantitative bounds on bulk EFT coefficients, higher-spin gaps, black-hole thresholds, wormholes, finite-N effects, and numerical bootstrap signatures of holographic CFTs."
---

## Summary

The **bootstrap constraints on holography** ask a sharp question:

> Which conformal field theories can behave like consistent quantum gravities in AdS?

The answer cannot be obtained by writing a plausible bulk Lagrangian alone. The boundary CFT must satisfy crossing symmetry, unitarity, positivity, causality, Regge boundedness, modular or thermal consistency, and the existence of a sensible spectrum of operators.

A candidate holographic CFT is constrained by several layers:

| CFT condition | Bulk interpretation |
|---|---|
| crossing symmetry | consistent interactions in all channels |
| unitarity and OPE positivity | positive Hilbert space and probabilities |
| large $C_T$ | weak bulk gravity |
| sparse single-trace spectrum | few light bulk fields |
| higher-spin gap | Einstein-like low-energy regime |
| Regge boundedness | causal high-energy scattering |
| Mellin boundedness | local AdS EFT below a cutoff |
| entanglement wedge consistency | quantum error-correcting bulk reconstruction |
| thermal consistency | black-hole thermodynamics and entropy |

The slogan is

$$
\text{not every AdS-looking EFT is allowed by CFT crossing}.
$$

This page closes the Holographic CFT chapter by explaining how bootstrap logic turns quantum-gravity consistency into constraints on CFT data.

## Prerequisites

Read [Stringy Corrections and Higher-Spin Gaps](/cft-bootstrap/holographic-cft/stringy-corrections-and-higher-spin-gaps/), [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/), [AdS Effective Field Theory](/cft-bootstrap/holographic-cft/ads-effective-field-theory/), [Mellin Amplitudes and Flat-Space Limits](/cft-bootstrap/holographic-cft/mellin-amplitudes-and-flat-space-limits/), and [Analytic-Numerical Bridges](/cft-bootstrap/analytic-bootstrap/analytic-numerical-bridges/) first.

You should know crossing equations, conformal blocks, large-$N$ factorization, Mellin amplitudes, Regge limits, conformal collider bounds, entanglement wedges, and the basic AdS/CFT dictionary.

## Core idea

A CFT is defined by its operator dimensions and OPE coefficients. Holography translates those data into bulk fields, masses, and interactions. Therefore constraints on CFT data become constraints on bulk quantum gravity.

The core bootstrap chain is

$$
\text{CFT data}
\longrightarrow
\text{crossing, unitarity, and causality}
\longrightarrow
\text{allowed correlators}
\longrightarrow
\text{allowed AdS EFTs}.
$$

A bulk action may look local, covariant, and respectable. But if the correlators it produces violate crossing, positivity, or Regge causality, it is not the low-energy limit of a consistent holographic CFT.

This is the boundary version of a swampland idea: some effective theories look reasonable locally but cannot be completed into quantum gravity.

## Crossing as bulk consistency

Crossing symmetry says that different OPE decompositions of the same correlator agree. For a four-point function, schematically,

$$
\sum_{\mathcal O}a_{\mathcal O}G_{\mathcal O}^{(s)}(u,v)
=
\sum_{\mathcal O}a_{\mathcal O}G_{\mathcal O}^{(t)}(u,v).
$$

In the bulk, this means that contact terms, exchange diagrams, and loop corrections must combine into a single correlator that has consistent expansions in every channel.

Crossing constrains:

- which single-trace exchanges can appear;
- how double-trace anomalous dimensions are organized;
- which contact terms are allowed;
- how loop-level cuts are completed by local counterterms;
- how global symmetry sectors talk to each other;
- how low-energy EFT data fit into a full spectrum.

The practical message is simple:

$$
\text{AdS diagrams are proposals; CFT crossing is the referee}.
$$

The referee is strict and has no chill.

## Unitarity and positivity

Unitarity gives positivity of norms and squared OPE coefficients. In an identical-scalar correlator, one has

$$
a_{\mathcal O}=\lambda_{\phi\phi\mathcal O}^2\ge0.
$$

This positivity is what makes numerical bootstrap possible and what gives analytic bootstrap its teeth.

In holography, positivity constrains bulk physics. Negative-norm states, wrong-sign kinetic terms, and nonunitary interactions show up as violations of CFT positivity.

Related positivity principles include:

| CFT positivity | Bulk meaning |
|---|---|
| OPE coefficient positivity | positive probabilities and spectral weights |
| averaged null energy | causal energy flux |
| double-discontinuity positivity | positive Lorentzian spectral data |
| relative entropy positivity | entanglement wedge consistency |
| modular Hamiltonian inequalities | gravitational energy constraints |

These are not separate miracles. They are different faces of Hilbert-space positivity.

## Large central charge and sparseness

Large $C_T$ suppresses bulk gravitational loops:

$$
C_T\sim \frac{R_{\rm AdS}^{d-1}}{G_N}.
$$

But large $C_T$ alone does not guarantee a simple gravitational dual. One also needs a sparse light single-trace spectrum and a large higher-spin gap.

The standard holographic target is:

$$
C_T\gg1,
\qquad
\text{few light single traces},
\qquad
\Delta_{\rm gap}^{\rm HS}\gg1.
$$

Numerical and analytic bootstrap can probe these assumptions by asking whether crossing allows a large central charge together with gaps in higher-spin sectors and controlled low-lying matter.

If the assumptions are inconsistent, the proposed bulk theory is ruled out. If they are allowed only in a small region, the CFT data are tightly constrained.

## Mellin bootstrap constraints

In Mellin space, local AdS EFT becomes amplitude-like. Contact terms are polynomials. Exchanges are meromorphic. Crossing is permutation symmetry. Locality becomes controlled growth.

A typical holographic Mellin ansatz is

$$
M(s,t)=M_{\rm exchange}(s,t)+M_{\rm contact}(s,t).
$$

Bootstrap constraints demand:

1. correct exchange poles;
2. crossing symmetry;
3. OPE consistency;
4. absence or cancellation of spurious singularities;
5. acceptable Regge behavior;
6. polynomial growth compatible with the assumed cutoff;
7. positivity of extracted CFT data.

This turns bulk EFT into a constrained amplitude problem.

The danger is that one can write many crossing-symmetric polynomials. The bootstrap asks which of them are compatible with unitarity, causality, and a finite higher-spin gap.

## Regge and causality constraints

The Lorentzian Regge limit is where many proposed bulk interactions get interrogated under bright lights.

Higher-derivative gravitational terms can modify high-energy scattering. If they produce bad Regge growth or time advances, they cannot be present without new states entering below the dangerous scale.

The schematic constraint is

$$
\text{large EFT correction}
\quad\Longrightarrow\quad
\text{small or finite gap to new higher-spin states}.
$$

Equivalently, if the higher-spin gap is very large, stress-tensor data must be close to the Einstein-gravity point.

In CFT terms, this is a constraint on stress-tensor correlators, conformal collider data, Lorentzian inversion, and the analytic behavior of correlators on nontrivial sheets.

Regge boundedness is not optional decoration. It decides whether the inversion formula has subtractions and whether the bulk high-energy scattering is causal.

## Conformal collider constraints

Conformal collider bounds require positive energy flux in states created by local operators. They constrain coefficients in three-point functions such as

$$
\langle TTT\rangle,
\qquad
\langle JJT\rangle,
\qquad
\langle \mathcal O\mathcal O T\rangle.
$$

Holographically, these bounds constrain higher-derivative gravitational and gauge-field couplings.

The logic is

$$
\text{positive boundary energy flux}
\longrightarrow
\text{bounds on CFT three-point data}
\longrightarrow
\text{bounds on bulk EFT coefficients}.
$$

In theories with a large higher-spin gap, the bounds can become especially restrictive. The allowed stress-tensor data may be forced close to Einstein gravity.

This is one of the cleanest examples of how a boundary positivity theorem becomes a quantum-gravity consistency condition.

## Lorentzian inversion constraints

The Lorentzian inversion formula reconstructs spin-dependent CFT data from double discontinuities. For holographic CFTs, this is a powerful way to constrain double-trace anomalous dimensions and OPE coefficients.

The inversion formula implies that crossed-channel data determine large-spin trajectories. Therefore a proposed bulk interaction must produce double-trace data with the correct analytic-in-spin behavior.

Useful checks include:

| Inversion output | Holographic interpretation |
|---|---|
| pole locations | operator dimensions |
| residues | OPE coefficients |
| large-spin tails | long-range AdS forces |
| low-spin ambiguities | contact terms or subtractions |
| dDisc positivity | physical intermediate data |
| Regge threshold | validity range of reconstruction |

A bulk EFT that gives erratic or nonanalytic high-spin CFT data is not a healthy holographic EFT.

## Entanglement constraints

Holographic CFTs have special entanglement structure. At large $N$, entanglement entropies are computed by extremal surfaces. Boundary subregions reconstruct entanglement wedges. Bulk reconstruction behaves like quantum error correction.

This imposes constraints beyond ordinary low-point correlators:

- entropy inequalities must hold;
- relative entropy must match between boundary and bulk plus area terms;
- entanglement wedge nesting must be consistent;
- modular flow should have a sensible bulk interpretation in appropriate regimes;
- island formulas must produce unitary Page-curve behavior when applicable.

These constraints are softer to state as algebraic bootstrap equations, but they are central to holography. A theory with local-looking correlators but impossible entanglement structure would not be a complete holographic CFT.

The bulk has to be a code, not just a collection of diagrams.

## Thermal and black-hole constraints

Holographic CFTs must also reproduce black-hole thermodynamics in the appropriate high-energy regime. A thermal partition function on a sphere can have a Hawking-Page transition. Heavy states should account for black-hole entropy. Thermal correlators should show decay, quasinormal behavior, hydrodynamics, or chaos depending on the regime.

Thermal consistency constrains:

| Thermal CFT object | Bulk expectation |
|---|---|
| partition function | thermal AdS or black-hole saddles |
| entropy | horizon area plus corrections |
| heavy-state density | black-hole microstate growth |
| OTOCs | Regge growth and chaos bounds |
| hydrodynamic poles | black-brane transport |
| Page curve | unitary evaporation in appropriate models |

These constraints are not usually encoded in one four-point crossing equation. They belong to the wider bootstrap of the whole CFT.

## Numerical bootstrap tests

Numerical bootstrap can test holographic assumptions by imposing gaps and central-charge conditions. For example, one can ask whether crossing allows:

- a large $C_T$;
- a unique stress tensor;
- no low-dimension higher-spin single-trace operators;
- sparse scalar spectra;
- large gaps in selected global-symmetry sectors;
- OPE coefficients compatible with weak bulk couplings.

Numerical output can include allowed regions, islands, lower bounds on $C_T$, upper bounds on gaps, and extremal spectra.

The numerical bootstrap is strongest for low-lying data. Analytic holographic bootstrap is strongest for asymptotic, large-spin, Regge, and large-$N$ structures. Together they can test whether a proposed holographic spectrum is plausible.

## Swampland-style lessons

It is tempting to write an AdS EFT and ask whether it could be quantum gravity. The CFT bootstrap changes the question:

$$
\text{Does there exist a unitary crossing-symmetric CFT with these data?}
$$

If not, the bulk theory is in the holographic swampland. This phrase is useful but should be used carefully. A failure of one bootstrap setup may reflect too-strong assumptions, finite-cutoff limitations, or missing sectors rather than a universal impossibility.

Still, the philosophy is powerful. Quantum gravity constraints can be studied through boundary consistency.

The boundary does not merely describe the bulk. It audits it.

## Common pitfalls

**Do not treat a local AdS Lagrangian as automatically consistent.** It must come from crossing-symmetric, unitary CFT data.

**Do not confuse large $C_T$ with a large higher-spin gap.** Weak gravity and Einstein-like locality are distinct conditions.

**Do not ignore low-spin ambiguities.** Contact terms and Regge subtractions can affect low-spin CFT data.

**Do not overstate numerical exclusions.** Finite derivative cutoffs and assumptions matter.

**Do not use positivity outside its hypotheses.** OPE positivity, ANEC, and dDisc positivity require appropriate unitarity and operator-ordering conditions.

**Do not assume every holographic constraint is visible in one correlator.** Entanglement, thermal physics, defects, and global symmetry sectors add more tests.

**Do not claim every allowed bootstrap point constructs a full CFT.** Allowed does not mean known to exist.

## Relations to other pages

This page closes the [Holographic CFT](/cft-bootstrap/holographic-cft/) chapter.

It synthesizes [AdS/CFT Dictionary](/cft-bootstrap/holographic-cft/ads-cft-dictionary/), [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/), [AdS Effective Field Theory](/cft-bootstrap/holographic-cft/ads-effective-field-theory/), [Stress Tensor, Graviton, and Causality](/cft-bootstrap/holographic-cft/stress-tensor-graviton-and-causality/), [Entanglement and the Ryu-Takayanagi Formula](/cft-bootstrap/holographic-cft/entanglement-and-rt/), [Black Holes and Thermal CFT](/cft-bootstrap/holographic-cft/black-holes-and-thermal-cft/), and [Stringy Corrections and Higher-Spin Gaps](/cft-bootstrap/holographic-cft/stringy-corrections-and-higher-spin-gaps/).

For method background, see [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/), [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/), [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/), and [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/).

## Research status

Bootstrap constraints on holography are a central part of modern CFT and quantum-gravity research. Many qualitative lessons are established: large $C_T$, sparseness, higher-spin gaps, Regge boundedness, and positivity are essential for semiclassical local AdS gravity.

Active research seeks sharper quantitative theorems and practical numerical constraints. Open directions include finite-gap bounds, black-hole thresholds, loop-level holographic bootstrap, modular and thermal constraints, entanglement wedge consistency, ensemble averaging, wormholes, and the relation between CFT bootstrap and quantum-gravity swampland programs.

## Exercises

### Exercise 1

Why is crossing symmetry a constraint on bulk EFT interactions?

<details><summary><strong>Solution</strong></summary>

A bulk EFT interaction computes a CFT correlator. That correlator must have consistent OPE decompositions in all channels. Crossing symmetry enforces equality of these decompositions. Therefore contact terms, exchange diagrams, and loop corrections must combine into CFT data that satisfy crossing.

</details>

### Exercise 2

What is the difference between large $C_T$ and a large higher-spin gap?

<details><summary><strong>Solution</strong></summary>

Large $C_T$ suppresses bulk gravitational loops and indicates weak gravity. A large higher-spin gap means high-spin single-trace operators are heavy, allowing an Einstein-like low-energy bulk. A CFT can have large $C_T$ without a large higher-spin gap, as in many vector-like large-$N$ theories.

</details>

### Exercise 3

How do conformal collider bounds constrain holography?

<details><summary><strong>Solution</strong></summary>

Conformal collider bounds require positive energy flux in states created by local operators. They constrain stress-tensor and current three-point coefficients. In a holographic dual, these coefficients correspond to gravitational and gauge-field EFT couplings, so the bounds restrict allowed higher-derivative bulk interactions.

</details>

### Exercise 4

Why does Regge behavior matter for the Lorentzian inversion formula?

<details><summary><strong>Solution</strong></summary>

The derivation of Lorentzian inversion uses contour deformation. If the correlator grows too quickly in the Regge limit, extra boundary terms or subtractions can appear. Thus Regge boundedness determines which spins are reconstructed directly and which low-spin data may remain ambiguous.

</details>

### Exercise 5

Why does allowed by numerics not automatically mean a CFT exists?

<details><summary><strong>Solution</strong></summary>

Numerical bootstrap usually proves exclusion: if no functional rules out a point at a finite cutoff, the point is allowed within that setup. This does not construct a full operator algebra or prove nonperturbative existence of a CFT. Existence requires stronger evidence or construction.

</details>

## References

- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, “Holography from conformal field theory,” *Journal of High Energy Physics* **2009**.
- A. L. Fitzpatrick, J. Kaplan, J. Penedones, S. Raju, and B. C. van Rees, “A natural language for AdS/CFT correlators,” *Journal of High Energy Physics* **2011**.
- D. M. Hofman and J. Maldacena, “Conformal collider physics: Energy and charge correlations,” *Journal of High Energy Physics* **2008**.
- X. O. Camanho, J. D. Edelstein, J. Maldacena, and A. Zhiboedov, “Causality constraints on corrections to the graviton three-point coupling,” *Journal of High Energy Physics* **2016**.
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).
- S. Rychkov and N. Su, “New Developments in the Numerical Conformal Bootstrap,” 2024.

## Version history

- 2026-07-02: First polished draft. Added crossing, unitarity, Mellin, Regge, collider, inversion, entanglement, thermal, numerical, and swampland-style constraints on holographic CFT data, with exercises and references.
