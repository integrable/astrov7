---
title: "Modern On-Shell Amplitudes"
description: "Chapter overview for modern on-shell amplitudes in the Perturbative QFT and Scattering volume."
sidebar:
  label: "Overview"
  order: 0
level: Advanced
status: "Polished draft"
source: "Schwartz 2014, ch. 27; Dixon amplitude reviews; Elvang and Huang; SAGEX amplitude reviews."
topics:
  - scattering amplitudes
  - spinor helicity
  - color decomposition
  - on-shell recursion
  - generalized unitarity
  - double copy
canonicalTopics:
  - modern-on-shell-amplitudes
  - spinor-helicity-formalism
  - on-shell-recursion
  - generalized-unitarity
  - double-copy
researchStatus:
  established:
    - "Spinor-helicity methods, color decomposition, factorization, BCFW recursion, generalized unitarity, soft limits, and double-copy ideas are standard parts of the modern scattering-amplitudes toolkit."
  active:
    - "Positive geometry, celestial amplitudes, all-loop organization, curved-spacetime amplitudes, and nonperturbative S-matrix constraints remain active research directions."
---

Modern On-Shell Amplitudes is the chapter in the Perturbative QFT and Scattering volume where scattering amplitudes are studied as constrained physical objects. Instead of beginning every calculation with off-shell fields and gauge-fixed diagrams, the chapter asks what Lorentz symmetry, little-group covariance, locality, unitarity, factorization, and analyticity force the answer to be.

The chapter exists because amplitudes often know more structure than their Feynman-diagram derivation makes visible. A long sum of gauge-dependent diagrams can collapse into a short helicity expression; a loop integrand can be reconstructed from its cuts; a gravity amplitude can sometimes be organized as a double copy of gauge-theory data.

Read this chapter when you want a sharper coordinate system for scattering calculations, not a rejection of Lagrangians, LSZ, or ordinary perturbation theory.

$$
\text{amplitude}
\quad\Longleftrightarrow\quad
\text{symmetry}+\text{locality}+\text{factorization}+\text{unitarity}.
$$

## Prerequisites

You should know the qft.org [Perturbative QFT conventions](/perturbative-qft/conventions/), the [S-Matrix and T-Matrix](/perturbative-qft/from-correlators-to-s-matrix/s-matrix-and-t-matrix/), [Mandelstam Variables](/perturbative-qft/tree-level-scattering/mandelstam-variables/), and [Polarization Sums](/perturbative-qft/tree-level-scattering/polarization-sums/).

For gauge-theory amplitudes, review [Color Factors](/perturbative-qft/gauge-theory-perturbation-theory/color-factors/) and [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/). For loop amplitudes, review [Cutkosky Rules](/perturbative-qft/unitarity-analyticity-dispersion/cutkosky-rules/) and [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/).

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Spinor-Helicity Formalism](/perturbative-qft/modern-on-shell-amplitudes/spinor-helicity-formalism/) | The massless four-dimensional language in which momenta factor into spinors and helicity is tracked by little-group weight. |
| 2 | [Three-Point Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/three-point-amplitudes/) | The basic on-shell building blocks fixed by Lorentz symmetry, little-group scaling, and complex kinematics. |
| 3 | [Color Decomposition](/perturbative-qft/modern-on-shell-amplitudes/color-decomposition/) | The separation of gauge-group algebra from kinematic partial amplitudes. |
| 4 | [Color-Ordered Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/color-ordered-amplitudes/) | The planar ordered objects with cyclic symmetry, simpler pole structure, and stripped color factors. |
| 5 | [BCFW Recursion](/perturbative-qft/modern-on-shell-amplitudes/bcfw-recursion/) | The reconstruction of tree amplitudes from lower-point amplitudes using complex momentum shifts and factorization. |
| 6 | [Generalized Unitarity](/perturbative-qft/modern-on-shell-amplitudes/generalized-unitarity/) | The loop method that constrains integrands or coefficients from products of on-shell trees. |
| 7 | [On-Shell Diagrams Preview](/perturbative-qft/modern-on-shell-amplitudes/on-shell-diagrams-preview/) | A first look at graph-based on-shell building blocks, especially in planar supersymmetric gauge theory. |
| 8 | [Soft Limits](/perturbative-qft/modern-on-shell-amplitudes/soft-limits/) | The universal behavior of amplitudes when an external particle momentum becomes soft. |
| 9 | [Double Copy](/perturbative-qft/modern-on-shell-amplitudes/double-copy/) | The color–kinematics idea that relates gauge-theory and gravity amplitudes. |
| 10 | [Amplituhedron Preview](/perturbative-qft/modern-on-shell-amplitudes/amplituhedron-preview/) | A careful preview of positive geometry and canonical forms in planar $\mathcal N=4$ super-Yang–Mills amplitudes. |
| 11 | [Celestial Amplitudes Preview](/perturbative-qft/modern-on-shell-amplitudes/celestial-amplitudes-preview/) | A preview of rewriting flat-space scattering in a conformal basis on the celestial sphere. |

After this path, you should be able to recognize when an amplitude problem is best attacked with spinors, recursion, cuts, color ordering, soft limits, or a frontier on-shell framework.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| Little-group covariance | A massless amplitude carries definite weights under rescalings of each external spinor. | Spinor-helicity expressions and three-point amplitudes. |
| Complex three-point kinematics | Complex momenta allow nonzero massless three-point seed amplitudes even when real kinematics are degenerate. | BCFW recursion and on-shell diagrams. |
| Factorization poles | Near a physical pole, an amplitude decomposes into lower-point amplitudes connected by an on-shell intermediate state. | Recursion, unitarity, analyticity, and bootstrap logic. |
| Color decomposition | Gauge-theory amplitudes can be expanded in color structures times color-stripped kinematic functions. | Color-ordered amplitudes and double copy. |
| Generalized unitarity | Loop information is constrained by putting selected internal propagators on shell. | Loop integrands, integral coefficients, and multi-loop calculations. |
| Soft universality | Soft photons, gluons, and gravitons probe charges, color, momentum, and asymptotic symmetries through universal factors. | Infrared physics and soft-theorem pages. |
| Double copy | In favorable representations, replacing color data by kinematic data maps gauge-theory structures toward gravity structures. | Gravity amplitudes and frontier amplitude programs. |
| Positive and celestial reformulations | Some amplitudes can be encoded as canonical forms or as conformal-basis data. | Amplituhedron and celestial-amplitudes previews. |

## Common confusions

**On shell does not mean anti-Lagrangian.** On-shell methods are usually justified by the same QFT principles that Lagrangians make manifest: locality, unitarity, symmetry, and analyticity. They reorganize information; they do not erase the need to know which theory is being studied.

**Complex momenta are not new physical particles.** Complex shifts and complex three-point amplitudes are analytic tools. Physical real-momentum amplitudes are recovered after the analytic construction is assembled.

**A color-ordered amplitude is not the full amplitude.** It is a kinematic coefficient in a color expansion. The full amplitude requires the appropriate color structures and, for non-planar or multi-trace sectors, more than one kind of ordering.

**BCFW recursion has assumptions.** The shifted amplitude must have suitable behavior at large complex shift, or boundary terms must be included. The recursion is powerful, not magical.

**The double copy is not ordinary squaring.** The slogan “gravity is gauge theory squared” is useful only after specifying the representation, numerator identities, external states, and scope of the statement.

## Boundaries

This chapter does:

- introduce spinor-helicity variables and little-group logic;
- explain color decomposition, color ordering, factorization, recursion, and generalized unitarity;
- connect soft limits and double-copy ideas to the broader amplitude landscape;
- provide careful previews of positive geometry and celestial amplitudes.

This chapter does not try to do:

- derive the S-matrix from correlation functions;
- teach ordinary Feynman rules from scratch;
- replace loop-integral reduction or master-integral technology;
- give a full treatment of twistor theory, positive Grassmannians, ambitwistor strings, or celestial holography.

Those topics belong in From Correlators to the S-Matrix, Diagrammatics and Feynman Rules, Loop Integral Technology, CFT and Bootstrap, Spacetime, Gravity, and Holography, and Research Frontiers and Open Problems.

## Where to go next

For a traditional calculation route, compare this chapter with the [Model Calculation Library](/perturbative-qft/model-calculation-library/). For loop reconstruction, continue with [Unitarity Cuts for Integrals](/perturbative-qft/loop-integral-technology/unitarity-cuts-for-integrals/) and [Master Integrals](/perturbative-qft/loop-integral-technology/master-integrals/).

For analytic constraints, continue with [Dispersion Relations](/perturbative-qft/unitarity-analyticity-dispersion/dispersion-relations/), [Partial-Wave Unitarity](/perturbative-qft/unitarity-analyticity-dispersion/partial-wave-unitarity/), and [Positivity Bounds Preview](/perturbative-qft/unitarity-analyticity-dispersion/positivity-bounds-preview/).

## References

### Standard first pass

- Schwartz, *Quantum Field Theory and the Standard Model*, especially the chapter on gluon scattering and spinor-helicity methods.
- Dixon, “Calculating Scattering Amplitudes Efficiently,” for a classic review of helicity, color decomposition, and amplitude technology.
- Elvang and Huang, *Scattering Amplitudes in Gauge Theory and Gravity*, for a systematic modern introduction.

### Deeper references

- Henn and Plefka, *Scattering Amplitudes in Gauge Theories*, for an amplitude-focused route through gauge theory and loop methods.
- Bern, Carrasco, Johansson, and collaborators, for color–kinematics duality and double-copy developments.
- Arkani-Hamed and collaborators, for on-shell diagrams, positive geometry, and the amplituhedron; Pasterski, Shao, Strominger, and collaborators, for celestial amplitudes.

## Version history

- **2026-06-14:** Initial polished chapter overview for Modern On-Shell Amplitudes in the Perturbative QFT and Scattering volume.
