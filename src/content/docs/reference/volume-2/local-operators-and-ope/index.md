---
title: "Local Operators and OPE"
description: "Chapter overview for engineering dimensions, anomalous dimensions, operator mixing, renormalization matrices, OPEs, redundant operators, and equation-of-motion operators."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Coleman 1985, Dilatations; Weinberg 1996, ch. 18; Zinn-Justin 2021; Cardy 1996; Collins 1984; Rychkov 2017."
topics:
  - local operators
  - composite operators
  - anomalous dimensions
  - operator mixing
  - operator product expansion
  - redundant operators
canonicalTopics:
  - local-operators
  - operator-product-expansion
  - anomalous-dimensions
  - operator-mixing
researchStatus:
  established:
    - "Local operators, composite-operator renormalization, operator mixing, anomalous-dimension matrices, and short-distance expansions are standard foundations of modern RG, EFT, and CFT."
  active:
    - "Operator bases, redundant operators, nonperturbative anomalous dimensions, conformal perturbation theory, and mixing in gauge theories and EFTs remain active in precision field theory and modern bootstrap work."
---

Local Operators and OPE is the chapter in the Renormalization, RG, and EFT volume where renormalization becomes a theory of **operator spaces**, not just a theory of Lagrangian parameters.

The reason this chapter exists is simple: fields are not the only quantities that renormalize. Products of fields at the same point are singular, composite operators mix with other operators carrying the same quantum numbers, and short-distance physics is encoded in the coefficients of local operators. This is the language that lets RG, EFT, CFT, lattice matching, anomalous dimensions, and operator bases talk to each other.

Read this chapter when you want to understand why an operator has an engineering dimension, how quantum corrections change that dimension, why operators mix, how anomalous-dimension matrices are defined, why the OPE is the systematic short-distance expansion of QFT, and why some operators are redundant because they can be removed by field redefinitions or equations of motion.

$$
\mathcal O_a(x)\mathcal O_b(0)
\sim
\sum_c C_{ab}{}^c(x,\mu,g)\,\mathcal O_c(0)
\qquad (x\to0).
$$

The equation is not a decorative CFT slogan. It is the local-operator version of Wilsonian thinking: at distances much larger than $|x|$, the detailed collision of two insertions is replaced by a sum of local operators allowed by symmetries.

## Prerequisites

You should know the scale conventions in [Conventions and Notation](/renormalization-rg-eft/conventions/), the meaning of [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), the geometry of [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/), and the classification in [Relevant, Irrelevant, and Marginal](/renormalization-rg-eft/wilsonian-renormalization/relevant-irrelevant-marginal/).

It is also useful to have read [Renormalization of Correlation Functions](/renormalization-rg-eft/regularization-counterterms/renormalization-of-correlation-functions/) and [Composite Operator Renormalization Preview](/renormalization-rg-eft/regularization-counterterms/composite-operator-renormalization-preview/). This chapter develops those previews into a reusable operator framework.

Readers headed toward CFT should keep [Scale Invariance](/renormalization-rg-eft/fixed-points-critical-phenomena/scale-invariance/) and [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/) nearby. Readers headed toward EFT should treat this chapter as the bridge to operator bases and Wilson coefficients.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Engineering Dimensions](/renormalization-rg-eft/local-operators-and-ope/engineering-dimensions/) | Classical mass dimensions of fields, couplings, and local operators from units and kinetic terms. |
| 2 | [Anomalous Dimensions of Operators](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimensions-of-operators/) | How renormalization changes scaling dimensions and why dimensions become dynamical data. |
| 3 | [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/) | Why operators with the same quantum numbers form vector spaces under renormalization. |
| 4 | [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/) | The matrix relation between bare and renormalized operator bases. |
| 5 | [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/) | RG flow of operator bases and Wilson coefficients, including sign conventions. |
| 6 | [OPE and Short-Distance Expansion](/renormalization-rg-eft/local-operators-and-ope/ope-and-short-distance-expansion/) | Products of nearby local operators replaced by a sum over local operators with coefficient functions. |
| 7 | [Conformal Perturbation Theory Preview](/renormalization-rg-eft/local-operators-and-ope/conformal-perturbation-theory-preview/) | How fixed points are perturbed by relevant or marginal operators and how OPE data control beta functions. |
| 8 | [Redundant Operators](/renormalization-rg-eft/local-operators-and-ope/redundant-operators/) | Operators removable by field redefinitions and why bases describe coordinates, not unique physics. |
| 9 | [Equations of Motion Operators](/renormalization-rg-eft/local-operators-and-ope/equations-of-motion-operators/) | How equation-of-motion operators enter correlation functions and simplify operator bases. |

After this path, you should be able to read an operator basis, identify which operators can mix, write the schematic renormalization matrix, interpret anomalous dimensions as matrix data, and recognize the OPE as the local short-distance expansion underlying both EFT matching and CFT bootstrap.

## Landmarks

| Landmark | Meaning | Why it matters |
|---|---|---|
| Local operator | An insertion built from fields and derivatives at one spacetime point. | The basic observable and deformation in local QFT. |
| Composite operator | A local product such as $\phi^2$, $F_{\mu\nu}F^{\mu\nu}$, or $\bar\psi\gamma^\mu\psi$. | Requires its own renormalization beyond field and parameter renormalization. |
| Engineering dimension | Dimension obtained from units and the classical kinetic terms. | Gives the first power-counting classification. |
| Anomalous dimension | Quantum correction to scaling behavior. | Turns dimensions into dynamical data of a fixed point or RG trajectory. |
| Operator mixing | Renormalization maps one operator into a linear combination of operators with the same quantum numbers. | Makes operator renormalization a matrix problem. |
| Renormalization matrix | A matrix $Z_a{}^b$ relating bare and renormalized operator bases. | Organizes divergences and scheme dependence in composite operators. |
| Anomalous-dimension matrix | A matrix $\gamma_a{}^b$ governing RG flow of renormalized operators. | Determines scaling operators and running Wilson coefficients. |
| Scaling operator | An eigenoperator of the dilatation/RG action at a fixed point. | Has a definite scaling dimension and appears naturally in the OPE. |
| OPE coefficient | A coefficient $C_{ab}{}^c(x)$ in the expansion of $\mathcal O_a(x)\mathcal O_b(0)$. | Encodes local short-distance physics and becomes part of CFT data at fixed points. |
| Redundant operator | An operator removable by a field redefinition or change of coordinates on theory space. | Important for avoiding overcounting in EFT and RG. |
| Equation-of-motion operator | An operator proportional to the classical or quantum equations of motion, with contact-term caveats. | Often removable from on-shell bases but not invisible in all correlators. |

The central shift is from thinking of a QFT as a list of fields to thinking of it as a structured algebra of local operators, equipped with correlation functions, RG flow, and short-distance multiplication rules.

## Common confusions

**The field is not the only operator.** A scalar field $\phi$ is one local operator. The theory also contains $\phi^2$, $\phi^4$, $\partial_\mu\phi\partial^\mu\phi$, currents, the stress tensor, symmetry-breaking operators, and infinitely many higher-dimension operators.

**Engineering dimension is not the full scaling dimension.** Engineering dimensions are fixed by units. Scaling dimensions at an interacting fixed point include anomalous contributions.

**Operator mixing is not a computational annoyance.** It is the statement that local operators with the same symmetries form vector spaces. Choosing a basis is like choosing coordinates.

**A composite operator is not automatically finite because the Lagrangian was renormalized.** Insertions at a point create new short-distance singularities. Composite operators require their own renormalization.

**OPE does not mean ordinary Taylor expansion.** A Taylor expansion expands smooth functions. The OPE expands singular products of operators in a distributional and asymptotic sense, with coefficient functions that carry the short-distance singularities.

**Redundant does not mean zero.** A redundant operator can be removed from a chosen basis or from on-shell amplitudes, but it may still affect off-shell Green functions, contact terms, or the form of RG equations.

**Equation-of-motion operators require contact-term care.** They often vanish inside separated on-shell matrix elements, but insertions in correlation functions can produce contact terms when they collide with other operators.

## Boundaries

This chapter does:

- explain local operators as the basic objects acted on by RG;
- distinguish engineering dimensions from anomalous dimensions;
- develop operator mixing and matrix renormalization;
- define anomalous-dimension matrices and their relation to scaling operators;
- introduce the OPE as the local short-distance expansion;
- prepare the operator language needed for EFT bases, Wilson coefficients, CFT data, and conformal perturbation theory;
- explain why redundant and equation-of-motion operators are basis subtleties, not throwaway trivia.

This chapter does not try to do:

- develop full CFT representation theory, conformal blocks, or crossing equations, which belong in the CFT and Bootstrap volume;
- provide a complete SMEFT operator-basis database, which belongs in EFT and reference-library pages;
- replace detailed gauge-theory renormalization, BRST cohomology, or anomaly calculations;
- turn the OPE into a rigorous theorem in every QFT setting, which belongs in mathematical and rigorous QFT material;
- compute high-loop anomalous-dimension matrices for phenomenological applications.

## Where to go next

If you are following the Renormalization, RG, and EFT volume linearly, continue from this chapter to [Effective Field Theory](/renormalization-rg-eft/effective-field-theory/). The operator language here becomes the EFT language of Wilson coefficients, matching, running, field redefinitions, and basis choice.

For fixed-point physics, continue later to CFT and Bootstrap: there the local operators become conformal primaries and descendants, and the OPE coefficients become part of the intrinsic data defining a conformal field theory.

For practical perturbative calculations, return to renormalized Green functions, counterterms, and anomalous dimensions in the earlier chapters. For gauge theory and the Standard Model, operator mixing becomes essential in weak effective Hamiltonians, DGLAP evolution, SMEFT running, and anomaly constraints.

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200.
- Sidney Coleman, *Aspects of Symmetry*, especially "Dilatations," for scale transformations, anomalous dimensions, Callan–Symanzik equations, and OPE logic.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, especially the chapters on renormalization, composite operators, short-distance expansion, and critical behavior.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, especially the discussion of renormalization group methods and renormalized operators.
- John Collins, *Renormalization*, for a systematic treatment of composite-operator renormalization and operator mixing.
- John Cardy, *Scaling and Renormalization in Statistical Physics*, for operator scaling and critical phenomena.
- Slava Rychkov, *EPFL Lectures on Conformal Field Theory in D ≥ 3 Dimensions*, for the CFT interpretation of operators and OPE data.

## Version history

- 2026-06-17: First polished chapter overview using the revised `local-operators-and-ope` slug. Added reading path, landmarks, boundaries, references, and cross-links to RG, EFT, and CFT.
