---
title: "Higher-Dimensional CFT"
description: "Chapter overview for conformal field theory in dimensions greater than two, including conformal symmetry, spinning operators, conserved currents, stress tensors, unitarity bounds, and benchmark examples."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Poland, Rychkov, and Vichi 2019; Rychkov lectures; Simmons-Duffin TASI lectures; Osborn and Petkou; conformal bootstrap literature."
topics:
  - higher-dimensional CFT
  - conformal symmetry
  - spinning operators
  - conserved currents
  - conformal bootstrap
canonicalTopics:
  - higher-dimensional-cft
  - conformal-symmetry-in-d-dimensions
  - cft-data
researchStatus:
  established:
    - "Conformal symmetry in dimensions greater than two is finite-dimensional and strongly constrains local operators, correlation functions, OPEs, conserved currents, and stress tensors."
  active:
    - "Many higher-dimensional CFTs are strongly coupled and known only through bootstrap constraints, perturbative expansions, large-N limits, dualities, lattice data, or holography."
---

Higher-Dimensional CFT is the chapter where the conformal bootstrap becomes a genuinely nonperturbative language for quantum field theories in $d>2$. Two-dimensional CFT has Virasoro symmetry and many exactly solvable models. Higher-dimensional CFT has only the finite conformal group, but it still has enough structure to make strongly coupled fixed points sharply constrained.

This chapter exists to keep the CFT and Bootstrap volume from becoming too two-dimensional. It explains the objects that appear in real bootstrap problems: scalar and spinning primary operators, conserved currents, the stress tensor, unitarity bounds, conformal collider constraints, generalized free fields, large-$N$ CFTs, and benchmark models such as the three-dimensional Ising CFT and $O(N)$ models.

Read this chapter when you want to understand what survives beyond Virasoro symmetry. The answer is: quite a lot. Conformal kinematics fixes the form of two- and three-point functions up to finite CFT data, the OPE organizes local observables, unitarity imposes lower bounds on dimensions, and crossing symmetry turns consistency into equations.

$$
\text{higher-dimensional CFT}
=\text{finite conformal symmetry}+\text{operator algebra}+\text{unitarity}+\text{crossing}.
$$

## Prerequisites

You should know the [CFT and Bootstrap conventions](/cft-bootstrap/conventions/), the meaning of [conformal data](/cft-bootstrap/what-is-a-cft/conformal-data/), the basic [operator product expansion](/cft-bootstrap/operator-product-expansion/ope-basics/), and the logic of [crossing symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/).

Readers who want a first pass through conformal kinematics should review [Conformal Group in d Dimensions](/cft-bootstrap/conformal-symmetry/conformal-group-in-d-dimensions/) and [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/) before continuing.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Conformal Symmetry in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/conformal-symmetry-in-higher-dimensions/) | The finite conformal group, conformal algebra, conformal compactification, and the crucial contrast with two dimensions. |
| 2 | [Spinning Operators](/cft-bootstrap/higher-dimensional-cft/spinning-operators/) | How local operators transform under $SO(d)$ or Lorentz representations, and why tensor structures become unavoidable. |
| 3 | [Conserved Currents](/cft-bootstrap/higher-dimensional-cft/conserved-currents/) | How current conservation shortens conformal multiplets and fixes $\Delta=d-1$ for spin-one global symmetry currents. |
| 4 | [Stress Tensor in Higher Dimensions](/cft-bootstrap/higher-dimensional-cft/stress-tensor-in-higher-dimensions/) | The universal conserved spin-two operator, Ward identities, normalization, and the role of $C_T$. |
| 5 | [Unitarity Bounds in d Dimensions](/cft-bootstrap/higher-dimensional-cft/unitarity-bounds-in-d-dimensions/) | Lower bounds on scaling dimensions from positive norm descendants and the shortening that occurs at saturation. |
| 6 | [Conformal Collider Bounds](/cft-bootstrap/higher-dimensional-cft/conformal-collider-bounds/) | Positivity constraints from energy flux and their relation to causality and stress-tensor data. |
| 7 | [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/) | The simplest mean-field-like CFT data and the seed of large-$N$ double-trace spectra. |
| 8 | [Mean-Field Theory CFT](/cft-bootstrap/higher-dimensional-cft/mean-field-theory-cft/) | How disconnected correlators produce an exact crossing-symmetric spectrum of double-trace operators. |
| 9 | [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/) | Factorization, single-trace and double-trace language, and the bridge to holography. |
| 10 | [3D Ising CFT](/cft-bootstrap/higher-dimensional-cft/3d-ising-cft/) | The flagship nontrivial higher-dimensional CFT and benchmark for numerical bootstrap. |
| 11 | [O(N) Models](/cft-bootstrap/higher-dimensional-cft/o-n-models/) | Vector-model fixed points, global symmetry sectors, and the large-$N$ expansion. |
| 12 | [Gauge-Theory CFTs](/cft-bootstrap/higher-dimensional-cft/gauge-theory-cfts/) | Fixed points with gauge fields, conserved currents, monopole-like sectors, and non-Lagrangian caveats. |

After this path, you should be able to translate a higher-dimensional CFT problem into its basic operator data: representations, dimensions, OPE coefficients, Ward identities, and crossing constraints.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $SO(d+1,1)$ | Euclidean conformal group for $d>2$ on the conformal compactification. | Conformal transformations, embedding space, conformal blocks. |
| $[D,P_\mu]=P_\mu$ and $[D,K_\mu]=-K_\mu$ | Translations raise scaling dimension; special conformal generators lower it. | Primary and descendant representation theory. |
| $K_\mu|\mathcal O\rangle=0$ | Highest-weight condition for a primary state in radial quantization. | Conformal multiplets and unitarity bounds. |
| $\Delta\ge (d-2)/2$ for scalar primaries | Scalar unitarity bound in a unitary CFT. | Bootstrap assumptions and allowed spectra. |
| $\Delta\ge \ell+d-2$ for traceless symmetric spin $\ell\ge1$ | Higher-spin unitarity bound; saturation indicates conservation. | Conserved currents, stress tensors, higher-spin symmetry. |
| $\partial^\mu J_\mu=0$ | Shortening condition for a global symmetry current with $\Delta=d-1$. | Ward identities and current correlators. |
| $\partial^\mu T_{\mu\nu}=0$ and $T^\mu{}_{\mu}=0$ | Stress-tensor conservation and tracelessness in a flat-space CFT. | Central charge analogues, $C_T$, conformal collider bounds. |
| $\langle\phi\phi\phi\phi\rangle$ crossing | Associativity of the OPE in a four-point function. | Numerical and analytic bootstrap. |

These landmarks are the finite-dimensional replacement for the infinite Virasoro machinery of two-dimensional CFT.

## Common confusions

**Higher-dimensional CFT is not just 2D CFT with fewer formulas.** In $d>2$, conformal symmetry is finite-dimensional. There is no generic Virasoro algebra, no automatic holomorphic factorization, and no universal finite list of minimal models.

**Scale invariance and conformal invariance are related but not identical.** Many physically relevant unitary fixed points are conformal, but the logical implication requires assumptions. This chapter studies conformal fixed points after conformal symmetry has been established or assumed.

**Spinning operators are not optional decoration.** Scalars are the easiest entry point, but currents, stress tensors, fermions, and mixed-correlator bootstrap systems require tensor structures and spin representations.

**The central charge language changes.** In $d=2$, $c$ appears in the Virasoro algebra and the $TT$ OPE. In $d>2$, one usually tracks stress-tensor two- and three-point normalizations such as $C_T$ and collider parameters instead.

**Conserved currents are short multiplets.** Conservation is not merely a differential equation; in conformal representation theory it is a shortening condition at the unitarity bound.

**Generalized free fields are not ordinary free fields.** They have Wick-like correlators and crossing-symmetric double-trace spectra, but they generally do not have a local stress tensor by themselves.

**Numerical bootstrap results are conditional.** Bounds, islands, and extracted spectra depend on assumptions such as unitarity, global symmetry, operator gaps, truncation order, and numerical precision.

## Boundaries

This chapter focuses on local-operator CFT structure in $d>2$: conformal symmetry, representations, correlators, Ward identities, unitarity, and canonical examples.

It does not replace the earlier chapters on OPEs, conformal blocks, crossing, or bootstrap logic. Those chapters give the general machinery. This chapter specializes the machinery to the higher-dimensional theories where modern bootstrap applications often live.

It also does not try to cover every appearance of conformal symmetry in matter, holography, supersymmetry, or gauge theory. Those applications have their own chapters. Here they appear only when they clarify higher-dimensional CFT data.

Finally, this chapter is not a theorem-first treatment of conformal representation theory. It is a physics-facing guide to the structures used in calculations, bootstrap studies, and model identification.

## Where to go next

After this chapter, move to [Numerical Conformal Bootstrap](/cft-bootstrap/numerical-bootstrap/) if you want to turn crossing equations into rigorous-looking bounds and islands. Move to [Analytic Conformal Bootstrap](/cft-bootstrap/analytic-bootstrap/) if you want large-spin, lightcone, Lorentzian, and asymptotic methods.

For applications, go to [CFT in Statistical Physics and Matter](/cft-bootstrap/cft-in-statistical-physics-matter/) for critical phenomena, [Holographic CFT](/cft-bootstrap/holographic-cft/) for large-$N$ and AdS/CFT, or [Supersymmetric CFT](/cft-bootstrap/supersymmetric-cft/) for superconformal representation theory.

## References

- D. Poland, S. Rychkov, and A. Vichi, "The Conformal Bootstrap: Theory, Numerical Techniques, and Applications," *Reviews of Modern Physics* **91** (2019).
- S. Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, SpringerBriefs, 2016.
- D. Simmons-Duffin, "TASI Lectures on the Conformal Bootstrap," 2016.
- H. Osborn and A. Petkou, "Implications of conformal invariance in field theories for general dimensions," *Annals of Physics* **231** (1994).
- J. L. Cardy, *Scaling and Renormalization in Statistical Physics*, Cambridge University Press, 1996.
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997, for the two-dimensional contrast.

## Version history

- 2026-06-30: Replaced scaffold with a polished chapter overview. Added prerequisites, reading path, landmarks, confusions, boundaries, next routes, references, and version history.
