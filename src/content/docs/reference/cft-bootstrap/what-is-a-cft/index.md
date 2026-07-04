---
title: "What Is a CFT?"
description: "Chapter overview for the basic meaning of conformal field theory, scale invariance, RG fixed points, CFT data, local operators, and examples."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Di Francesco–Mathieu–Sénéchal 1997; Coleman 1985; Polchinski 1988; Nakayama 2013; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019"
topics:
  - conformal field theory
  - scale invariance
  - conformal invariance
  - RG fixed points
  - CFT data
  - local operators
  - reflection positivity
  - examples of CFTs
canonicalTopics:
  - what-is-a-cft
  - conformal-data
  - cfts-as-rg-fixed-points
  - scale-versus-conformal-invariance
researchStatus:
  established:
    - "CFTs are the standard description of quantum field theories at conformally invariant fixed points, and their local observables are organized by scaling dimensions, spin, and OPE coefficients."
    - "In many unitary relativistic examples of physical interest, scale-invariant fixed points are conformally invariant, though the precise theorem depends on assumptions."
  active:
    - "The boundary between scale invariance and conformal invariance, the classification of non-Lagrangian CFTs, and the space of consistent CFT data remain active conceptual and technical areas."
---

What Is a CFT? is the entry chapter for the CFT and Bootstrap volume. It explains what a conformal field theory is before the machinery of conformal algebras, radial quantization, conformal blocks, and bootstrap equations takes over.

A first working definition is:

$$
\text{CFT} = \text{a QFT whose local observables transform covariantly under conformal transformations}.
$$

A second, more bootstrap-friendly definition is:

$$
\text{CFT} = \text{a consistent spectrum of local operators and OPE coefficients}.
$$

The point of this chapter is to make these slogans precise enough to use. A CFT may come from a Lagrangian, from a lattice model at criticality, from a string worldsheet, from a supersymmetric construction, from holography, or from no known microscopic description. The common language is not the microscopic presentation. The common language is local operators, correlation functions, scaling dimensions, spin, OPE coefficients, and consistency.

## Prerequisites

You should know the site-wide [Conventions and Normalizations](/foundations/conventions-and-normalizations/) and the CFT-specific [Conventions and Notation](/cft-bootstrap/conventions/). You should also be comfortable with local operators, correlation functions, Noether currents, the stress tensor, and the idea that an RG flow can approach a fixed point.

Readers who are rusty on RG language should skim the fixed-point material in [Renormalization, RG, and EFT](/renormalization-rg-eft/). Readers who want a quick reminder of ordinary QFT correlators should revisit [Correlation Functions and Propagators](/foundations/correlators-and-propagators/).

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Scale Invariance versus Conformal Invariance](/cft-bootstrap/what-is-a-cft/scale-invariance-versus-conformal-invariance/) | The first conceptual distinction: dilatations remove a scale, while conformal transformations impose much stronger local constraints. |
| 2 | [CFTs as RG Fixed Points](/cft-bootstrap/what-is-a-cft/cfts-as-rg-fixed-points/) | Why critical theories and continuum limits are naturally described by fixed points of the renormalization group. |
| 3 | [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/) | The spectrum, spin labels, symmetry representations, and OPE coefficients that define the local operator algebra. |
| 4 | [Local Operators as Observables](/cft-bootstrap/what-is-a-cft/local-operators-as-observables/) | Why the local operator basis replaces particle states as the primary bookkeeping system of CFT. |
| 5 | [Unitarity and Reflection Positivity](/cft-bootstrap/what-is-a-cft/unitarity-and-reflection-positivity/) | The positivity assumptions that turn CFT into a Hilbert-space theory and make bootstrap inequalities possible. |
| 6 | [Euclidean and Lorentzian CFT](/cft-bootstrap/what-is-a-cft/euclidean-and-lorentzian-cft/) | The relation between Euclidean correlators, analytic continuation, causal ordering, and Lorentzian physics. |
| 7 | [Examples of CFTs](/cft-bootstrap/what-is-a-cft/examples-of-cfts/) | A map of free fields, minimal models, Wilson–Fisher fixed points, WZW models, gauge-theory fixed points, and holographic examples. |

After this path, you should be able to say what data a CFT contains, why conformal symmetry is stronger than ordinary scale invariance, and why a CFT can be meaningful even when no weakly coupled Lagrangian is known.

## Landmarks

The first landmark is the hierarchy

$$
\text{Poincaré or Euclidean symmetry}
\subset
\text{scale symmetry}
\subset
\text{conformal symmetry}.
$$

In Euclidean signature and $d\geq 3$, the connected conformal group is locally $SO(d+1,1)$. It contains translations, rotations, one dilatation, and $d$ special conformal transformations. In Lorentzian signature with $d$ spacetime dimensions, the corresponding group is locally $SO(d,2)$.

The second landmark is the stress-tensor criterion. Scale invariance gives a conserved dilatation current. In flat space this implies, schematically,

$$
T^\mu{}_{\mu}=\partial_\mu V^\mu,
$$

where $V^\mu$ is the virial current. Conformal invariance is obtained when the stress tensor can be improved so that

$$
T^\mu{}_{\mu}=0
$$

at separated points, up to anomalies or contact terms when those are relevant. This is one of the cleanest ways to see why conformal invariance is not just scale invariance with nicer typography.

The third landmark is the operator spectrum. Local operators can be chosen to diagonalize the dilatation operator:

$$
[D,\mathcal O_i(0)]=\Delta_i\mathcal O_i(0).
$$

The eigenvalue $\Delta_i$ is the scaling dimension. In a conformal theory, operators are further organized into primary operators and descendants. Primaries label conformal multiplets, and descendants are obtained by acting with translations.

The fourth landmark is CFT data:

$$
\left\{\Delta_i,\rho_i,\lambda_{ijk}\right\}.
$$

Here $\rho_i$ records spin and representation labels, while $\lambda_{ijk}$ are OPE coefficients in a chosen normalization. This data is not merely decoration. It is the input from which correlation functions are reconstructed through the OPE and conformal symmetry.

The fifth landmark is the bootstrap viewpoint. Four-point functions can be decomposed in more than one OPE channel. Consistency demands that all decompositions agree:

$$
\text{s-channel OPE} = \text{t-channel OPE}.
$$

This is crossing symmetry. Combined with unitarity and symmetry selection rules, it becomes a powerful nonperturbative constraint on possible CFT data.

## Common confusions

Do not identify “no mass parameter in a classical Lagrangian” with quantum conformal invariance. Running couplings, anomalies, relevant deformations, and virial currents can all change the conclusion.

Do not identify a scale-invariant solution with a scale-invariant theory. A theory may have a symmetry even when a particular state or background breaks it. Conversely, a special correlation function may have a power law without the full theory being conformal.

Do not treat “CFT” as synonymous with “two-dimensional CFT.” Two dimensions are special because local conformal transformations are infinite-dimensional and the stress tensor generates the Virasoro algebra. Higher-dimensional CFT is less algebraically rigid but still highly constrained.

Do not assume that every CFT has particles. A CFT on flat space usually has no mass gap and no ordinary asymptotic particle basis. In radial quantization, the cleaner Hilbert-space basis is made from local operators inserted at the origin.

Do not assume that every CFT has a Lagrangian. The bootstrap viewpoint is deliberately broader: a CFT is characterized by consistent operator data, whether or not a simple microscopic action is available.

Do not confuse conformal transformations with Weyl transformations. A conformal transformation is a coordinate transformation that rescales the metric by a position-dependent factor. A Weyl transformation changes the metric while keeping coordinates fixed. They are related, especially on curved backgrounds, but they are not the same operation.

## Boundaries

This chapter explains the entry-level meaning of conformal field theory. It does not yet derive the conformal algebra, classify representations, compute correlation functions, prove OPE convergence, build conformal blocks, or write numerical bootstrap programs. Those jobs belong to later chapters.

General RG flows and the epsilon expansion mainly belong to [Renormalization, RG, and EFT](/renormalization-rg-eft/). This chapter uses RG fixed points only to explain why CFTs arise. Detailed perturbative calculations near the Wilson–Fisher fixed point should live in the RG volume or in model calculation pages that explicitly connect the perturbative result to CFT data.

The full theory of critical phenomena in real materials belongs partly to statistical physics and matter chapters. This chapter keeps only the conformal part: what the fixed point knows about local scaling operators and universal correlation functions.

String worldsheet theory, AdS/CFT, supersymmetric localization, vertex operator algebras, tensor categories, and rigorous constructive field theory all touch CFT. They are not introduced here unless they clarify the basic definition of CFT data.

## Where to go next

After this chapter, go to [Conformal Symmetry](/cft-bootstrap/conformal-symmetry/) for the group, algebra, generators, and Ward identities. Then read [Operators, States, and Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/) to see why scaling dimensions become energies on the cylinder.

If your goal is the bootstrap, continue through [Correlation Functions](/cft-bootstrap/correlation-functions/), [Operator Product Expansion](/cft-bootstrap/operator-product-expansion/), [Conformal Blocks](/cft-bootstrap/conformal-blocks/), and [Crossing Symmetry and Bootstrap Logic](/cft-bootstrap/crossing-bootstrap-logic/). If your goal is two-dimensional CFT, branch after radial quantization into [Two-Dimensional CFT](/cft-bootstrap/two-dimensional-cft/) and [Virasoro Symmetry and Central Charge](/cft-bootstrap/virasoro-central-charge/).

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. The standard broad textbook for two-dimensional CFT, with background on QFT, statistical mechanics, global conformal invariance, Virasoro symmetry, minimal models, and modular invariance.
- S. Coleman, “Dilatations,” in *Aspects of Symmetry*, Cambridge University Press, 1985. A classic discussion of scale transformations, currents, anomalies, RG equations, and OPE ideas.
- J. Polchinski, “Scale and Conformal Invariance in Quantum Field Theory,” *Nuclear Physics B* **303** (1988). A foundational reference on when scale invariance enhances to conformal invariance.
- Y. Nakayama, “Scale Invariance vs Conformal Invariance,” arXiv:1302.0884. A broad review of the distinction, examples, assumptions, and open issues.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982. A clear modern entry point to higher-dimensional CFT and the bootstrap.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405. The main review of modern numerical bootstrap methods and applications.
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, Springer, 2017. A compact higher-dimensional CFT reference.

## Version history

- **2026-06-26:** Replaced the scaffold with a polished chapter overview, reading path, landmarks, common confusions, boundaries, and reference map.
