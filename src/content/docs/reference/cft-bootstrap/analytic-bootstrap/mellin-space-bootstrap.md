---
title: "Mellin-Space Bootstrap"
description: "How Mellin amplitudes recast CFT correlators into variables resembling scattering amplitudes, especially for large-N and holographic CFTs."
sidebar:
  label: "Mellin-Space Bootstrap"
  order: 8
level: Advanced
status: "Polished draft"
source: "Mack; Penedones; Fitzpatrick, Kaplan, Penedones, Raju, and van Rees; Rastelli and Zhou; analytic bootstrap and AdS/CFT Mellin-amplitude literature."
topics:
  - Mellin amplitudes
  - analytic conformal bootstrap
  - holographic CFT
  - AdS amplitudes
  - crossing symmetry
canonicalTopics:
  - mellin-space-bootstrap
  - mellin-amplitudes
  - holographic-bootstrap
researchStatus:
  established:
    - "Mellin amplitudes provide a scattering-amplitude-like representation of CFT correlators, especially useful for large-N holographic CFTs and AdS effective field theory."
  active:
    - "Current research develops loop-level Mellin amplitudes, dispersion relations, spinning correlators, supersymmetric constraints, celestial connections, and numerical-analytic hybrids."
---

## Summary

The **Mellin-space bootstrap** rewrites CFT correlation functions using Mellin variables. In this representation, CFT correlators look strikingly similar to scattering amplitudes. Poles encode exchanged operator dimensions, residues encode OPE data, crossing becomes a symmetry of Mellin variables, and local AdS interactions become polynomial Mellin amplitudes.

For scalar correlators, the rough idea is

$$
\mathcal G(u,v)
\quad\longleftrightarrow\quad
M(s,t),
$$

where $u,v$ are conformal cross-ratios and $s,t$ are Mellin variables analogous to Mandelstam invariants. This analogy is especially sharp in holographic CFTs, where Mellin amplitudes are boundary avatars of AdS scattering amplitudes.

The basic dictionary is:

| CFT position-space object | Mellin-space analogue |
|---|---|
| conformal cross-ratios | exponential variables conjugate to Mellin variables |
| OPE expansion | pole expansion |
| exchanged primary | tower of Mellin poles |
| descendant contributions | residues fixed by conformal symmetry |
| crossing symmetry | permutation symmetry of Mellin amplitude |
| AdS contact interaction | polynomial Mellin amplitude |
| AdS exchange diagram | meromorphic Mellin amplitude |
| flat-space limit | high-energy limit of Mellin variables |

The slogan is

$$
\text{Mellin space is where CFT correlators imitate scattering amplitudes}.
$$

This page explains the representation, the pole structure, why it is useful for holographic bootstrap, and what can go wrong if the analogy with flat-space scattering is taken too literally.

## Prerequisites

Read [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/), [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/), [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/), and [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/) first.

You should know scalar four-point functions, cross-ratios,

$$
u=z\bar z,
\qquad
v=(1-z)(1-\bar z),
$$

OPE poles, conformal blocks, and the basic idea of AdS/CFT. Familiarity with ordinary scattering amplitudes helps, but Mellin space is a CFT representation, not a literal flat-space S-matrix.

## Core idea

CFT correlators have no ordinary momentum-conserving S-matrix in position space. Scale invariance removes the usual notion of asymptotic particle scattering. Mellin space partially restores an amplitude-like language by transforming powers of cross-ratios into complex Mellin variables.

A four-point function becomes a double inverse Mellin transform:

$$
\mathcal G(u,v)
=\int \frac{ds\,dt}{(2\pi i)^2}\;
 u^{s/2}v^{t/2}\,\Gamma\text{-factors}\,M(s,t),
$$

schematically. The exact powers and Gamma factors depend on conventions and external dimensions.

The Gamma factors are not decoration. They contain universal descendant and mean-field singularities. The Mellin amplitude $M(s,t)$ carries the dynamical data.

The conceptual chain is

$$
\text{position-space correlator}
\quad\to\quad
\text{Mellin transform}
\quad\to\quad
\text{pole and residue data}
\quad\to\quad
\text{bootstrap constraints}.
$$

This turns OPE singularities into a meromorphic structure, much like how scattering amplitudes reveal particles through poles.

## Mellin representation for n-point functions

For scalar primary operators $\mathcal O_i$ of dimensions $\Delta_i$, an $n$-point correlator can be represented schematically as

$$
\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\rangle
=\int [d\delta_{ij}]\,M(\delta_{ij})
\prod_{i<j}\Gamma(\delta_{ij})(x_{ij}^2)^{-\delta_{ij}},
$$

with constraints

$$
\sum_{j\ne i}\delta_{ij}=\Delta_i.
$$

The variables $\delta_{ij}$ behave like pairwise products of fictitious momenta:

$$
\delta_{ij}\sim p_i\cdot p_j,
$$

subject to analogues of momentum conservation and mass-shell constraints. This is the origin of the scattering-amplitude analogy.

For four-point functions, there are two independent Mellin variables, commonly called

$$
s,\qquad t,
$$

with a third variable fixed by a constraint, analogous to

$$
s+t+u_M=\sum_i\Delta_i.
$$

Here $u_M$ is a Mellin variable, not the cross-ratio $u$. Do not let notation eat your lunch.

## Four-point scalar correlators

For identical scalar operators $\phi$ of dimension $\Delta_\phi$, write

$$
\langle\phi_1\phi_2\phi_3\phi_4\rangle
=\frac{1}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}}\mathcal G(u,v).
$$

A typical Mellin representation has the form

$$
\mathcal G(u,v)
=\int\frac{ds\,dt}{(2\pi i)^2}
\,u^{s/2}v^{t/2-\Delta_\phi}
\,\Gamma\text{-factors}(s,t)\,M(s,t),
$$

where the integration contours run parallel to the imaginary axes and separate families of poles.

Different authors shift $s,t$ by constants or use different powers of $u,v$. What is invariant is the structure:

1. Mellin variables are conjugate to logarithms of cross-ratios.
2. Gamma factors carry universal kinematic pole families.
3. The Mellin amplitude $M(s,t)$ carries dynamical singularities.
4. Crossing permutes the Mellin variables.

For learner purposes, this structure matters more than a memorized convention-specific formula.

## Poles and exchanged operators

In position space, an exchanged primary contributes a conformal block. In Mellin space, it produces poles. For an operator $\mathcal O$ of dimension $\Delta$ and spin $\ell$, the poles in a channel are located schematically at

$$
s=\Delta-\ell+2m,
\qquad
m=0,1,2,\ldots .
$$

The leading quantity

$$
\tau=\Delta-\ell
$$

is the twist. The integer $m$ labels descendant levels in the exchanged conformal multiplet.

The residues are polynomials in the other Mellin variable, often called Mack polynomials:

$$
\operatorname*{Res}_{s=\tau+2m}M(s,t)
\sim \lambda_{12\mathcal O}\lambda_{34\mathcal O}\,Q_{m,\ell}(t).
$$

This is the Mellin-space version of the OPE. Poles locate the exchanged operators. Residues encode OPE coefficients and spin structure.

## Crossing symmetry

Crossing symmetry says that the four-point function is invariant under exchanging operator insertions, with appropriate transformations of cross-ratios and tensor structures. In Mellin space, crossing acts as a permutation of Mellin variables and external labels.

For identical scalars, one expects a crossing-symmetric Mellin amplitude:

$$
M(s,t)=M(t,s)=M(s,u_M)=\cdots,
$$

schematically, with

$$
s+t+u_M=4\Delta_\phi.
$$

The precise permutation depends on the convention for $s,t,u_M$.

This is one of the reasons Mellin space is attractive. Crossing can look like the crossing symmetry of scattering amplitudes. The analogy is not perfect, because CFT correlators include Gamma factors, descendant towers, and no ordinary momentum-space delta function. Still, the symmetry becomes visually and algebraically natural.

## Contact diagrams

In AdS/CFT, a local contact interaction in the bulk contributes a Witten contact diagram to a boundary correlator. In Mellin space, such diagrams become polynomials.

For example, a simple non-derivative quartic interaction gives roughly

$$
M(s,t)=\text{constant}.
$$

Interactions with derivatives give polynomials in Mellin variables:

$$
M(s,t)=c_0+c_1s+c_2t+c_3s^2+\cdots .
$$

This is exactly what one wants from an amplitude-like representation. Locality in AdS becomes polynomial boundedness in Mellin space.

The degree of the polynomial is related to the number of derivatives in the bulk interaction. Thus Mellin amplitudes are useful for organizing AdS effective field theory:

$$
\text{bulk derivative expansion}
\quad\longleftrightarrow\quad
\text{polynomial Mellin expansion}.
$$

## Exchange diagrams

An AdS exchange diagram corresponds to a bulk field propagating between two pairs of boundary insertions. In Mellin space, exchange diagrams are meromorphic functions with poles corresponding to the exchanged operator and its descendants.

Schematically,

$$
M_{\rm exchange}(s,t)
=\sum_{m=0}^{\infty}\frac{R_m(t)}{s-(\Delta-\ell+2m)}
+\text{polynomial ambiguity}.
$$

The residues $R_m(t)$ are fixed by conformal symmetry and the exchanged spin. The polynomial ambiguity reflects the freedom to add contact terms.

This decomposition mirrors flat-space scattering:

$$
\text{exchange pole} + \text{contact ambiguity}.
$$

But in AdS/CFT, the infinite tower of poles comes from the conformal descendants of one primary, not from infinitely many independent particles.

## Large-N holographic CFTs

Mellin space is especially powerful for large-$N$ CFTs with sparse low-dimension single-trace spectra. At leading order, correlators are generalized free. Connected correlators are suppressed by powers of $1/N$:

$$
\mathcal G=\mathcal G_{\rm GFF}+\frac{1}{N^p}\mathcal G^{(1)}+\cdots .
$$

The correction $\mathcal G^{(1)}$ is described by tree-level AdS diagrams. Mellin amplitudes package these diagrams in a form close to ordinary amplitudes.

The dictionary is:

| Large-N CFT | AdS/Mellin meaning |
|---|---|
| single-trace operator | single-particle bulk field |
| double-trace operator | two-particle AdS state |
| connected four-point function | AdS interaction amplitude |
| anomalous double-trace dimensions | binding energies |
| contact Witten diagram | polynomial Mellin amplitude |
| exchange Witten diagram | meromorphic Mellin amplitude |
| higher-derivative bulk term | higher-degree polynomial |

This is why Mellin-space bootstrap is a standard language for holographic correlators.

## Flat-space limit

In a suitable large-radius or high-dimension limit, Mellin amplitudes are related to flat-space scattering amplitudes. Roughly, large Mellin variables probe high center-of-mass energy in AdS units.

The slogan is

$$
\text{large Mellin variables}
\quad\longrightarrow\quad
\text{flat-space Mandelstam invariants}.
$$

This relation lets one import intuition from scattering amplitudes into CFT and, conversely, derive bulk S-matrix information from boundary correlators.

The flat-space limit is not automatic. One must specify the holographic limit, AdS radius, normalization, and scaling of Mellin variables. But once these are controlled, Mellin space provides one of the cleanest bridges between CFT correlators and bulk scattering.

## Mellin bootstrap logic

A Mellin-space bootstrap problem typically imposes:

1. meromorphic pole structure from the OPE;
2. crossing symmetry under Mellin-variable permutations;
3. boundedness or polynomial growth conditions;
4. known single-trace exchanges or protected operators;
5. absence or control of spurious singularities;
6. unitarity and positivity constraints, often through OPE data;
7. large-$N$ or holographic power counting when relevant.

The goal is to determine or constrain $M(s,t)$.

For holographic CFTs, one often makes an ansatz:

$$
M(s,t)=M_{\rm exchange}(s,t)+M_{\rm contact}(s,t),
$$

then fixes the contact terms using crossing, supersymmetry, OPE constraints, Regge behavior, or known protected data.

This is bootstrap in amplitude clothing. Same crossing beast, different hat.

## Relation to Polyakov bootstrap

Mellin space is closely related to the Polyakov bootstrap. Polyakov bootstrap uses crossing-symmetric exchange objects rather than ordinary single-channel conformal blocks. Mellin amplitudes naturally represent such crossing-symmetric exchange and contact structures.

In many settings, a Polyakov block can be represented by a Witten exchange diagram plus contact terms. Its Mellin amplitude has exchange poles and is arranged so that unphysical or spurious singularities cancel in the full correlator.

Thus Mellin space gives a natural language for:

$$
\text{crossing-symmetric building blocks}
\quad\text{and}\quad
\text{spurious-pole cancellation}.
$$

The next page, [Polyakov Bootstrap](/cft-bootstrap/analytic-bootstrap/polyakov-bootstrap/), develops this viewpoint directly.

## Relation to Lorentzian inversion

Mellin space and Lorentzian inversion are complementary. Lorentzian inversion reconstructs CFT data from double discontinuities. Mellin space packages correlators into meromorphic amplitude-like functions.

In large-$N$ holographic theories, both tools are often used together:

- Mellin amplitudes construct correlators from AdS diagrams.
- Double discontinuities isolate physical cuts and loop data.
- Inversion extracts double-trace anomalous dimensions and OPE coefficients.
- Regge behavior constrains polynomial ambiguities and contact terms.

The practical workflow can be:

$$
M(s,t)\quad\to\quad\mathcal G(u,v)\quad\to\quad\operatorname{dDisc}\mathcal G\quad\to\quad\text{CFT data}.
$$

Or, in reverse, known CFT data can constrain the Mellin amplitude.

## Supersymmetric examples

Mellin space is widely used in supersymmetric holographic CFTs. In such theories, protected operators and superconformal Ward identities strongly restrict correlators. The Mellin amplitude then encodes the remaining dynamical data.

Typical examples include correlators of half-BPS operators in theories related to:

- $\mathcal N=4$ super-Yang--Mills in four dimensions;
- six-dimensional $(2,0)$ theories;
- three-dimensional ABJM-like theories;
- other AdS compactifications with protected spectra.

Supersymmetry can reduce the problem to a smaller Mellin amplitude multiplied by known kinematic or R-symmetry structures. The remaining amplitude may be fixed by crossing, protected OPE data, and flat-space limits.

The details belong in the supersymmetric and holographic CFT chapters. Here the lesson is that Mellin space makes symmetry-constrained correlators look amplitude-like and manageable.

## Common pitfalls

**Do not confuse Mellin variables with cross-ratios.** Cross-ratios are $u,v$ or $z,\bar z$. Mellin variables are conjugate variables such as $s,t$.

**Do not ignore Gamma factors.** They carry universal pole families and affect the relation between Mellin poles and OPE data.

**Do not treat Mellin amplitudes as ordinary flat-space amplitudes.** The analogy is powerful but not literal. CFT descendants, AdS curvature, and conformal kinematics matter.

**Do not quote pole locations without stating conventions.** Some authors shift $s,t$ or use different Mellin variables.

**Do not forget polynomial ambiguities.** Exchange diagrams can be modified by contact terms, especially in holographic EFT.

**Do not assume polynomial growth without justification.** Growth conditions encode locality, Regge behavior, or EFT assumptions.

**Do not use Mellin space only for holography.** It is most famous there, but the representation is a general CFT tool when the Mellin transform exists and is useful.

## Relations to other pages

This page follows [Regge Limits and Chaos](/cft-bootstrap/analytic-bootstrap/regge-limits-and-chaos/) and prepares [Polyakov Bootstrap](/cft-bootstrap/analytic-bootstrap/polyakov-bootstrap/).

It also connects to [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/), [Holographic CFT](/cft-bootstrap/holographic-cft/), and [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/), because Mellin amplitudes are especially effective for perturbing generalized-free data in holographic theories.

For the Lorentzian reconstruction side, see [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/) and [Double Discontinuity](/cft-bootstrap/analytic-bootstrap/double-discontinuity/).

## Research status

Mellin amplitudes are established tools in analytic bootstrap and holographic CFT. Their pole structure, crossing behavior, and relation to AdS contact and exchange diagrams are standard.

Active research develops Mellin-space dispersion relations, loop-level holographic correlators, spinning and supersymmetric Mellin amplitudes, flat-space limits, celestial connections, and hybrid methods combining Mellin ansätze with numerical and Lorentzian inversion constraints.

## Exercises

### Exercise 1

What is the Mellin-space analogue of an exchanged primary operator?

<details><summary><strong>Solution</strong></summary>

An exchanged primary appears as a family of poles in a Mellin variable. For an operator of dimension $\Delta$ and spin $\ell$, the poles in a channel are schematically at

$$
s=\Delta-\ell+2m,
\qquad
m=0,1,2,\ldots .
$$

The residues are polynomials in the other Mellin variable and encode spin and OPE data.

</details>

### Exercise 2

Why do AdS contact interactions give polynomial Mellin amplitudes?

<details><summary><strong>Solution</strong></summary>

A local AdS contact interaction has no internal propagator, so it produces no exchange poles. Derivatives in the bulk interaction translate into powers of Mellin variables. Therefore a non-derivative contact term gives a constant Mellin amplitude, while higher-derivative contact terms give higher-degree polynomials.

</details>

### Exercise 3

What is the difference between a Mellin amplitude pole and a Gamma-function pole?

<details><summary><strong>Solution</strong></summary>

The Gamma factors in the Mellin representation contain universal kinematic pole families associated with descendants and mean-field structure. The Mellin amplitude $M(s,t)$ contains the dynamical pole structure associated with exchanged primaries and interactions. In practice, both affect the full correlator, so one must keep track of the chosen convention.

</details>

### Exercise 4

Why is Mellin space especially useful in large-$N$ holographic CFTs?

<details><summary><strong>Solution</strong></summary>

At large $N$, connected correlators are described by AdS Witten diagrams. In Mellin space, contact Witten diagrams become polynomials and exchange Witten diagrams become meromorphic functions with simple pole structures. This makes the correlator look like a scattering amplitude and organizes AdS effective field theory in a compact way.

</details>

### Exercise 5

Why should one not identify Mellin amplitudes with flat-space scattering amplitudes without qualification?

<details><summary><strong>Solution</strong></summary>

Mellin amplitudes are representations of CFT correlators in AdS-like kinematics. They include conformal descendant structure, Gamma factors, and curvature-scale effects. Flat-space scattering amplitudes emerge only in a controlled limit, with large Mellin variables and an appropriate holographic scaling. Outside that limit, the analogy is useful but not literal.

</details>

## References

- G. Mack, “D-dimensional conformal field theories with anomalous dimensions as dual resonance models,” *Bulg. J. Phys.* **36** (2009).
- J. Penedones, “Writing CFT correlation functions as AdS scattering amplitudes,” *Journal of High Energy Physics* **2011**.
- A. L. Fitzpatrick, J. Kaplan, J. Penedones, S. Raju, and B. C. van Rees, “A natural language for AdS/CFT correlators,” *Journal of High Energy Physics* **2011**.
- L. Rastelli and X. Zhou, “Mellin amplitudes for AdS5 × S5,” *Physical Review Letters* **118** (2017).
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019).

## Version history

- 2026-07-01: First polished draft. Added Mellin representation, pole/OPE dictionary, crossing, contact and exchange diagrams, large-$N$ holographic interpretation, flat-space limit, relation to Polyakov bootstrap and Lorentzian inversion, exercises, and references.
