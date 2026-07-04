---
title: "AdS/CFT Dictionary"
description: "The basic map between conformal field theory data and fields, states, interactions, and geometry in anti-de Sitter spacetime."
sidebar:
  label: "AdS/CFT Dictionary"
  order: 1
level: Advanced
status: "Polished draft"
source: "Maldacena 1998; Gubser, Klebanov, and Polyakov 1998; Witten 1998; standard holographic CFT and AdS/CFT reviews."
topics:
  - AdS/CFT
  - holographic CFT
  - operator dictionary
  - bulk fields
  - conformal boundary
canonicalTopics:
  - ads-cft-dictionary
  - holographic-dictionary
  - cft-bulk-map
researchStatus:
  established:
    - "The operator-field dictionary, source-response relation, and large-N interpretation of single-trace and double-trace data are standard pillars of AdS/CFT."
  active:
    - "Current research sharpens bulk reconstruction, finite-N corrections, quantum error correction, black-hole microstates, islands, and the emergence of locality from CFT data."
---

## Summary

The **AdS/CFT dictionary** translates between a conformal field theory in $d$ dimensions and a gravitational or string-theoretic theory on anti-de Sitter space in $d+1$ dimensions:

$$
\text{CFT}_d
\quad\Longleftrightarrow\quad
\text{quantum gravity on AdS}_{d+1}.
$$

The most basic entry says:

$$
\text{local primary operator }\mathcal O
\quad\Longleftrightarrow\quad
\text{bulk field }\Phi.
$$

The CFT operator dimension determines the bulk mass. OPE coefficients determine bulk interaction strengths. The stress tensor maps to the graviton. Global symmetry currents map to gauge fields. Large central charge means weak bulk gravity. Double-trace operators map to two-particle states in AdS.

The dictionary is not a metaphor. It is a precise equivalence in known examples, but most practical calculations use controlled limits: large $N$, large central charge, sparse spectra, semiclassical gravity, or low-energy AdS effective field theory.

The slogan is

$$
\text{bulk physics is encoded in CFT data}.
$$

This page gives the first map.

## Prerequisites

Read [Holographic CFT](/cft-bootstrap/holographic-cft/), [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/), [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/), [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/), and [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/) first.

You should know primary operators, two-point and three-point functions, OPE coefficients, stress tensors, conserved currents, and large-$N$ factorization.

## Core idea

AdS has a conformal boundary. A quantum gravity theory in the bulk defines boundary correlation functions. Conversely, a CFT can be used to reconstruct bulk observables, at least in appropriate regimes.

The basic relation is often written as a generating-functional equality:

$$
Z_{\rm bulk}[\phi_0]
=
\left\langle \exp\left(\int d^d x\,\phi_0(x)\mathcal O(x)\right)\right\rangle_{\rm CFT}.
$$

Here $\phi_0(x)$ is the boundary value of a bulk field $\Phi$, and it acts as a source for the CFT operator $\mathcal O$.

In the semiclassical bulk limit,

$$
Z_{\rm bulk}[\phi_0]\approx \exp\left(-S_{\rm bulk}^{\rm on-shell}[\phi_0]\right)
$$

in Euclidean signature. Differentiating with respect to $\phi_0$ gives CFT correlators.

Thus:

$$
\text{boundary source}\quad\leftrightarrow\quad\text{bulk boundary condition},
$$

and

$$
\text{CFT correlator}\quad\leftrightarrow\quad\text{bulk response}.
$$

## The first dictionary table

| CFT object | Bulk AdS object |
|---|---|
| spacetime dimension $d$ | bulk dimension $d+1$ |
| conformal group $SO(d,2)$ | AdS isometry group |
| primary operator $\mathcal O$ | bulk field $\Phi$ |
| dimension $\Delta$ | bulk mass $m$ |
| spin $\ell$ | bulk spin |
| source for $\mathcal O$ | boundary value of $\Phi$ |
| one-point function $\langle\mathcal O\rangle$ | normalizable response of $\Phi$ |
| OPE coefficient $\lambda_{ijk}$ | bulk cubic coupling |
| four-point function | AdS scattering process |
| stress tensor $T_{\mu\nu}$ | graviton $g_{MN}$ |
| global current $J_\mu$ | bulk gauge field $A_M$ |
| central charge $C_T$ | inverse Newton coupling |
| single-trace operator | one-particle bulk state |
| double-trace operator | two-particle bulk state |
| thermal state | thermal AdS or AdS black hole |
| entanglement entropy | extremal area plus bulk entropy |

This table is the skeleton. The rest of the page adds muscles, joints, and warning labels.

## Operator dimensions and bulk masses

For a scalar field in AdS$_{d+1}$ of radius $R$, the mass-dimension relation is

$$
m^2R^2=\Delta(\Delta-d).
$$

Equivalently,

$$
\Delta_\pm=\frac d2\pm\sqrt{\frac{d^2}{4}+m^2R^2}.
$$

Usually the operator dimension is

$$
\Delta=\Delta_+.
$$

In a special mass window above the Breitenlohner-Freedman bound, an alternative quantization using $\Delta_-$ may also be possible.

The important point is that the CFT scaling dimension is not merely a label. It is the bulk mass in AdS units.

For spinful fields, analogous relations exist, but their precise form depends on spin, gauge redundancies, and representation theory. Conserved currents and stress tensors are special because conservation fixes their dimensions.

## Near-boundary behavior

Choose a radial coordinate $z$ with the AdS boundary at

$$
z=0.
$$

A scalar bulk field behaves near the boundary as

$$
\Phi(z,x)\sim z^{d-\Delta}\phi_0(x)+z^\Delta A(x)+\cdots .
$$

The leading coefficient $\phi_0(x)$ is the source for $\mathcal O$. The subleading coefficient $A(x)$ is related to the expectation value

$$
\langle \mathcal O(x)\rangle_{\phi_0}.
$$

This is the **source-response** part of the dictionary. In words:

$$
\text{non-normalizable mode}=\text{source},
\qquad
\text{normalizable mode}=\text{state or response}.
$$

The exact powers and counterterms depend on conventions, integer-dimension coincidences, and holographic renormalization. The conceptual split is robust.

## States and radial quantization

In the CFT, radial quantization maps local operators to states on

$$
S^{d-1}.
$$

A primary operator $\mathcal O$ creates a state with energy

$$
E=\Delta/R_{S^{d-1}}.
$$

In global AdS, the Hamiltonian generating global time translations has the same spectrum. Thus the operator-state correspondence becomes the statement:

$$
\text{CFT operator dimension}\quad\leftrightarrow\quad\text{global AdS energy}.
$$

Single-particle bulk states correspond to single-trace primaries. Multi-particle bulk states correspond to multi-trace operators. This is why double-trace dimensions look like sums of single-trace dimensions plus orbital and radial excitation:

$$
\Delta_{n,\ell}\approx\Delta_1+\Delta_2+2n+\ell.
$$

Bulk binding energies appear as anomalous dimensions of double-trace operators.

## Single-trace and multi-trace operators

In matrix-like large-$N$ theories, a single-trace operator is schematically

$$
\mathcal O=\operatorname{Tr}(X_1X_2\cdots X_k).
$$

Holographically, such an operator creates a one-particle bulk excitation. A double-trace operator is schematically

$$
[\mathcal O_1\mathcal O_2]_{n,\ell},
$$

and creates a two-particle state.

The large-$N$ dictionary is:

| CFT operator type | Bulk state |
|---|---|
| identity | vacuum |
| single-trace | one particle |
| double-trace | two particles |
| triple-trace | three particles |
| stress tensor | graviton |
| conserved current | gauge boson |

This language is most literal in matrix large-$N$ theories. In vector models, the large-$N$ counting and bulk interpretation can be different. Not every large-$N$ theory is Einstein gravity wearing a CFT hat.

## Correlators and Witten diagrams

CFT correlators are computed in the bulk by Witten diagrams. These are like Feynman diagrams, but vertices are integrated over AdS and external legs end on the boundary.

| CFT correlator | Bulk computation |
|---|---|
| two-point function | bulk propagator normalization and mass |
| three-point function | cubic interaction vertex |
| four-point function | contact diagrams plus exchange diagrams |
| conformal block expansion | decomposition into exchanged AdS states |
| OPE limit | bulk short-distance or boundary-channel limit |

For example, a bulk cubic coupling

$$
g_{123}\Phi_1\Phi_2\Phi_3
$$

contributes to the CFT three-point coefficient

$$
\lambda_{123}.
$$

A bulk quartic contact term contributes to a connected four-point function and shifts double-trace anomalous dimensions.

The motto is:

$$
\text{bulk interactions} \quad\leftrightarrow\quad \text{CFT OPE data}.
$$

## Stress tensor and graviton

The CFT stress tensor is dual to the bulk metric:

$$
T_{\mu\nu}\quad\leftrightarrow\quad g_{MN}.
$$

This is one of the most important entries in the dictionary. The stress tensor is conserved and has dimension

$$
\Delta_T=d,
\qquad
\ell_T=2.
$$

The bulk dual is a massless spin-two field: the graviton.

The normalization of the stress-tensor two-point function, often called $C_T$, controls the effective Newton coupling:

$$
C_T\sim \frac{R_{\rm AdS}^{d-1}}{G_N}
$$

up to dimension-dependent constants and conventions.

Large $C_T$ means weak bulk gravity. Finite $C_T$ means quantum gravity effects are not negligible.

## Currents and gauge fields

A conserved global symmetry current in the CFT maps to a bulk gauge field:

$$
J_\mu^a\quad\leftrightarrow\quad A_M^a.
$$

The current has

$$
\Delta_J=d-1,
\qquad
\ell_J=1.
$$

The corresponding bulk gauge invariance is not the same as a global symmetry in the bulk. Gauge redundancy in the bulk encodes a genuine global symmetry of the boundary CFT.

The current two-point normalization $C_J$ controls the bulk gauge coupling:

$$
C_J\sim \frac{R_{\rm AdS}^{d-3}}{g_{\rm bulk}^2}
$$

up to conventions.

Charged CFT operators create charged bulk particles. Boundary global symmetry representations become bulk gauge charges.

## RG scale and radial direction

The AdS radial direction is related to energy scale in the CFT. Near the boundary, one probes ultraviolet CFT physics. Deeper in the bulk, one probes longer-distance or lower-energy structure.

A rough slogan is

$$
\text{radial position in AdS}\quad\leftrightarrow\quad\text{energy scale in the CFT}.
$$

This is called the UV/IR relation. It is not a literal identification of one radial coordinate with one renormalization scale in every gauge choice, but it is one of the most useful intuitions in holography.

Renormalization in the bulk near the boundary becomes holographic renormalization in the CFT: one adds counterterms on cutoff surfaces and extracts finite correlation functions.

## Thermal states and black holes

A CFT at finite temperature lives on

$$
S^{d-1}\times S^1_\beta
$$

or on flat space with Euclidean time periodically identified. The holographic dual can be thermal AdS or an AdS black hole, depending on the ensemble and temperature.

The dictionary includes:

| CFT thermal object | Bulk object |
|---|---|
| thermal density matrix | Euclidean black-hole or thermal-AdS saddle |
| free energy | on-shell gravitational action |
| entropy | black-hole area plus corrections |
| heavy states | black-hole microstates or massive bulk states |
| OTOC growth | near-horizon shockwave scattering |

This is where holography becomes a theory of quantum black holes. But the CFT remains the exact definition in examples where the duality is established.

## Entanglement and geometry

For a boundary region $A$, holography relates entanglement entropy to a bulk extremal surface:

$$
S(A)=\frac{\operatorname{Area}(\gamma_A)}{4G_N}+S_{\rm bulk}+\cdots .
$$

At leading classical order, this is the Ryu-Takayanagi or Hubeny-Rangamani-Takayanagi prescription. Quantum corrections add bulk entanglement entropy and further terms.

This dictionary entry is conceptually different from the operator-field map. It says that spacetime geometry is encoded in patterns of quantum entanglement.

Later pages will treat this carefully. For now, remember:

$$
\text{geometry is not extra data; it is encoded in the CFT state}.
$$

## Common pitfalls

**Do not identify every CFT with a weakly curved bulk.** A generic CFT may have no simple local AdS description.

**Do not assume large $N$ is enough.** A sparse spectrum and a higher-spin gap are needed for Einstein-like locality.

**Do not confuse sources with states.** A boundary value of a bulk field is a source; a normalizable mode is related to a state or response.

**Do not treat Witten diagrams as ordinary flat-space diagrams.** They compute boundary correlators through AdS integrals.

**Do not ignore normalization conventions.** $C_T$, $C_J$, OPE coefficients, and bulk couplings all depend on conventions.

**Do not think gauge symmetry in the bulk is a global symmetry there.** It is a redundancy whose boundary imprint is a global current.

**Do not treat the radial coordinate as a gauge-invariant observable by itself.** The UV/IR relation is powerful but coordinate-dependent.

## Relations to other pages

This page starts the [Holographic CFT](/cft-bootstrap/holographic-cft/) chapter. It prepares [Large-N and Factorization](/cft-bootstrap/holographic-cft/large-n-and-factorization/), [Witten Diagrams](/cft-bootstrap/holographic-cft/witten-diagrams/), and [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/).

It connects back to [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/), [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/), and [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/).

For stress-tensor and current background, see [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/) and [Conserved Currents](/cft-bootstrap/higher-dimensional-cft/conserved-currents/).

## Research status

The basic AdS/CFT dictionary is established and is the foundation of holographic CFT. The operator-field map, source-response relation, stress-tensor/graviton correspondence, and large-$N$ multi-trace interpretation are standard.

Active research concerns the hardest parts of the dictionary: bulk reconstruction beyond perturbation theory, finite-$N$ quantum gravity, black-hole microstates, entanglement wedges, islands, emergence of locality, and precise bootstrap criteria for when a CFT admits a semiclassical bulk dual.

## Exercises

### Exercise 1

For a scalar primary of dimension $\Delta$ in a $d$-dimensional CFT, what is the mass of the dual scalar field in AdS units?

<details><summary><strong>Solution</strong></summary>

The scalar mass-dimension relation is

$$
m^2R^2=\Delta(\Delta-d).
$$

Thus the CFT scaling dimension determines the bulk mass in units of the AdS radius.

</details>

### Exercise 2

What is the bulk dual of the CFT stress tensor?

<details><summary><strong>Solution</strong></summary>

The CFT stress tensor $T_{\mu\nu}$ is dual to the bulk metric $g_{MN}$, whose fluctuation is the graviton. The stress tensor has spin two and protected dimension $d$, matching a massless spin-two field in AdS.

</details>

### Exercise 3

Explain the difference between the source and response terms in the near-boundary expansion of a scalar field.

<details><summary><strong>Solution</strong></summary>

Near the boundary,

$$
\Phi(z,x)\sim z^{d-\Delta}\phi_0(x)+z^\Delta A(x)+\cdots .
$$

The coefficient $\phi_0(x)$ is the source coupled to the CFT operator $\mathcal O$. The coefficient $A(x)$ is related to the expectation value $\langle\mathcal O\rangle$ in the presence of that source, after holographic renormalization.

</details>

### Exercise 4

Why do double-trace operators correspond to two-particle states in AdS?

<details><summary><strong>Solution</strong></summary>

In large-$N$ CFTs, single-trace operators create one-particle bulk states. A double-trace operator schematically built from two single-trace operators creates a state with two such excitations. Its leading dimension is approximately the sum of the single-particle energies plus radial and orbital excitation,

$$
\Delta_{n,\ell}\approx\Delta_1+\Delta_2+2n+\ell.
$$

The anomalous dimension is the interaction energy of the two-particle state.

</details>

### Exercise 5

Why is a sparse spectrum important for an Einstein-like bulk dual?

<details><summary><strong>Solution</strong></summary>

A sparse spectrum means there are few light single-trace operators besides the stress tensor and other expected low-spin fields. A large gap to higher-spin single-trace operators suppresses stringy or higher-spin effects at low energies. This allows the bulk to be approximated by local Einstein-like effective field theory rather than by a strongly stringy or higher-spin theory.

</details>

## References

- J. Maldacena, “The Large N Limit of Superconformal Field Theories and Supergravity,” *Advances in Theoretical and Mathematical Physics* **2** (1998).
- S. S. Gubser, I. R. Klebanov, and A. M. Polyakov, “Gauge theory correlators from non-critical string theory,” *Physics Letters B* **428** (1998).
- E. Witten, “Anti de Sitter space and holography,” *Advances in Theoretical and Mathematical Physics* **2** (1998).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, “Large N field theories, string theory and gravity,” *Physics Reports* **323** (2000).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, “Holography from conformal field theory,” *Journal of High Energy Physics* **2009**.
- J. Penedones, “Writing CFT correlation functions as AdS scattering amplitudes,” *Journal of High Energy Physics* **2011**.
- S. Ryu and T. Takayanagi, “Holographic derivation of entanglement entropy from AdS/CFT,” *Physical Review Letters* **96** (2006).

## Version history

- 2026-07-01: First polished draft. Added the basic operator-field dictionary, source-response relation, mass-dimension formula, single-trace and multi-trace interpretation, Witten-diagram map, stress tensor and current entries, thermal and entanglement dictionary, pitfalls, exercises, and references.
