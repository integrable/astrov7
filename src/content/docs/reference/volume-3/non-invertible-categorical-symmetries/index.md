---
title: "Non-Invertible and Categorical Symmetries"
description: "Chapter overview for non-invertible symmetries, topological defects, fusion rules, duality defects, categorical symmetry, and their role in modern QFT."
sidebar:
  label: "Overview"
  order: 0
level: Research
status: "Polished draft"
source: "Shao TASI lectures; Schäfer-Nameki ICTP lectures; Gaiotto–Kapustin–Seiberg–Willett; 2D CFT and topological-defect literature."
topics:
  - non-invertible symmetry
  - categorical symmetry
  - topological defects
  - duality defects
  - fusion rules
  - generalized symmetry
canonicalTopics:
  - non-invertible-symmetry
  - categorical-symmetry
  - topological-defect
  - defect-fusion
  - duality-defect
researchStatus:
  established:
    - "In two-dimensional QFT and CFT, topological defects with non-group-like fusion are standard and provide canonical examples of non-invertible symmetry."
    - "The modern topological-defect viewpoint gives a common language for ordinary, higher-form, higher-group, and non-invertible symmetry."
  active:
    - "Non-invertible symmetries in dimensions higher than two, their representations, anomalies, gauging operations, symmetry TFT descriptions, and physical applications remain active research areas."
---

Non-Invertible and Categorical Symmetries is the chapter where the word “symmetry” stops meaning “group action” and starts meaning something more flexible: **topological operators with fusion**.

The previous chapters built a ladder:

$$
\text{ordinary symmetry}
\longrightarrow
\text{defects}
\longrightarrow
\text{higher-form symmetry}
\longrightarrow
\text{generalized symmetry}.
$$

This chapter climbs one more rung. In an ordinary invertible symmetry, topological symmetry operators fuse like group elements:

$$
U_g(\Sigma)U_h(\Sigma)=U_{gh}(\Sigma),
\qquad
U_g(\Sigma)U_{g^{-1}}(\Sigma)=1.
$$

A non-invertible symmetry is still topological and still constrains the QFT, but its symmetry operators need not have inverses. Fusion can branch:

$$
\mathcal N_a(\Sigma)\mathcal N_b(\Sigma)
=
\sum_c N_{ab}{}^c\,\mathcal N_c(\Sigma).
$$

The right-hand side is a **sum of sectors**, not a single group element. That branching is not a defect in the definition. It is the point.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A schematic roadmap from group-like symmetry defects to non-invertible fusion and categorical symmetry.](/figures/symmetry-anomalies-topology/noninvertible-chapter-map.svg)

<figcaption>

Ordinary group-like symmetries are the special case where every topological symmetry defect is invertible and fusion returns a single defect. Non-invertible symmetry allows fusion to branch into a sum of topological defects, leading naturally to categorical rather than group-theoretic language.

</figcaption>
</figure>

The chapter is advanced, but the first idea is wonderfully concrete:

$$
\text{invertible: can undo},\qquad
\text{non-invertible: cannot undo, but still topological}.
$$

## Prerequisites

You should know the earlier chapters on [Ordinary Global Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/), [Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/), and [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/). In particular, you should already be comfortable with the idea that a symmetry can be represented by a topological defect whose deformation leaves correlation functions invariant unless it crosses charged insertions.

The mathematical prerequisites are modest at first: groups, representations, tensor products, and basic operator algebra. Later pages use a little category language: objects, morphisms, fusion, simple objects, duals, and module categories. The chapter introduces only as much of that language as QFT needs.

The most important physics prerequisites are:

- topological defects and their fusion;
- symmetry defects for ordinary finite or compact groups;
- higher-form symmetry operators and linking;
- gauging as summing over background fields or defect networks;
- the distinction between an exact symmetry, a duality, and a gauge redundancy.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Invertible versus Non-Invertible Symmetry](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/invertible-versus-non-invertible-symmetry/) | The basic distinction: group-like topological defects have inverses; non-invertible defects fuse into sums or multiple sectors. |
| 2 | Topological Defects as Symmetries | The intrinsic definition of symmetry in terms of deformable operators, not field transformations. |
| 3 | Fusion Rules | How to read equations like $\mathcal N_a\mathcal N_b=\sum_cN_{ab}{}^c\mathcal N_c$, and what assumptions are hidden in this notation. |
| 4 | Duality Defects | Defects that implement dualities on one side and symmetry actions on another, including self-duality defects. |
| 5 | Kramers–Wannier Duality Defect | The canonical pedagogical example: the Ising duality line and its non-invertible fusion. |
| 6 | Categorical Symmetry | Why fusion categories, module categories, and categorical actions replace ordinary groups. |
| 7 | Non-Invertible Ward Identities: Preview | How topological deformation still constrains correlators even when no inverse operator exists. |
| 8 | Gauging and Orbifolding | How gauging ordinary symmetries can create non-invertible defects, and how orbifold logic fits the story. |
| 9 | Tambara–Yamagami Preview | A controlled family of fusion rules that packages many duality-defect examples. |
| 10 | Examples in Two-Dimensional QFT | Minimal models, WZW models, orbifolds, and statistical systems where non-invertible defects are explicit. |

After this path, read [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) to see how non-invertible symmetry data can be packaged by a one-higher-dimensional topological theory.

## Landmarks

| Landmark | Meaning | Why it matters |
|---|---|---|
| Topological defect | A defect whose correlators are invariant under smooth deformations avoiding insertions. | This is the modern carrier of symmetry. |
| Invertible defect | A defect $\mathcal D$ with another defect $\mathcal D^{-1}$ such that $\mathcal D\mathcal D^{-1}=1$. | Invertible defects recover group-like symmetry. |
| Non-invertible defect | A topological defect with no inverse under fusion. | The symmetry cannot be represented by a group action. |
| Fusion rule | The operation of bringing compatible topological defects together. | It replaces group multiplication. |
| Simple defect | An indecomposable defect, roughly a basic building block under direct sums. | Fusion rules are usually written in a basis of simple defects. |
| Quantum dimension | A positive number measuring the “size” of a topological defect in semisimple examples. | Invertible defects have quantum dimension $1$; non-invertible defects often have larger quantum dimension. |
| Duality defect | A defect associated with a duality or self-duality operation. | Canonical source of non-invertible symmetries. |
| Condensation defect | A defect produced by gauging or condensing a lower-dimensional symmetry algebra on a wall. | Major construction of non-invertible defects in modern QFT. |
| Categorical symmetry | Symmetry data organized by categories rather than groups. | The natural language for non-invertible fusion and actions. |
| Module category | A category on which a fusion category acts. | The replacement for an ordinary representation space. |

The main conceptual change is this:

$$
\text{ordinary representation theory}
\quad\leadsto\quad
\text{defect categories and their modules}.
$$

## Common confusions

**“Non-invertible means explicitly broken.”** No. A non-invertible symmetry can be exact. The defect is topological and imposes Ward-like constraints. It simply does not have an inverse under fusion.

**“Non-invertible means non-unitary.”** No. Many non-invertible symmetries appear in perfectly unitary theories. Non-invertibility is about fusion, not failure of Hilbert-space unitarity.

**“A non-invertible symmetry is just a badly chosen group.”** Usually no. If the fusion of simple topological defects gives a sum of defects, no relabeling turns it into ordinary group multiplication.

**“Fusion rules are OPE coefficients.”** They are related in spirit but not identical. Fusion rules describe the topological sector obtained by bringing extended defects together. Defect-local operator OPEs live on the resulting worldvolume and contain additional dynamical data.

**“Every duality is a symmetry.”** A duality may relate two different descriptions or two different theories. It becomes a symmetry defect of a single theory only when the relevant theory is self-dual or when the defect is allowed as an interface in an enlarged setup.

**“Categorical symmetry means we need category theory before physics.”** Not for the first pass. Start with topological defects and fusion. Category theory is the efficient language that appears once one asks for associativity, defect-changing operators, boundary conditions, and representations.

## Boundaries

This chapter is the canonical home of non-invertible and categorical symmetry as QFT symmetry structure. It does not replace surrounding chapters.

The [Defects and Extended Operators](/symmetry-anomalies-topology/defects-extended-operators/) chapter develops the basic operator vocabulary: supports, codimensions, Wilson lines, ’t Hooft lines, surface defects, twist operators, boundaries, interfaces, and defect fusion.

The [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) chapter treats invertible higher-form symmetries, higher-group symmetries, and subsystem previews. This chapter generalizes the fusion law beyond groups.

The [Low-Dimensional Symmetry Technology](/symmetry-anomalies-topology/low-dimensional-symmetry-technology/) chapter will treat bosonization, fermionization, orbifolds, and Kramers–Wannier duality as computational tools. This chapter emphasizes the abstract symmetry structure.

The [CFT and Bootstrap](/cft-bootstrap/) volume is the canonical home for full conformal-defect bootstrap, Virasoro minimal models, rational CFT, and modular tensor category technology when the goal is CFT itself.

The [Mathematical Toolkit](/math-toolkit/) is the home for category theory as mathematics. This chapter uses the categorical language only insofar as it clarifies QFT symmetry.

## Where to go next

For the shortest conceptual route, read [Invertible versus Non-Invertible Symmetry](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/invertible-versus-non-invertible-symmetry/), then Topological Defects as Symmetries, then Fusion Rules. That gives the working language.

For examples, jump from Fusion Rules to Kramers–Wannier Duality Defect and Examples in Two-Dimensional QFT. For modern research, continue to Gauging and Orbifolding, Categorical Symmetry, and then Symmetry TFT and Anomaly Inflow.

For readers coming from gauge theory and higher-form symmetry, the best route is:

$$
\text{defect fusion}
\longrightarrow
\text{gauging}
\longrightarrow
\text{condensation defects}
\longrightarrow
\text{non-invertible symmetry}.
$$

For readers coming from 2D CFT or statistical mechanics, the best route is:

$$
\text{Kramers–Wannier duality}
\longrightarrow
\text{duality defect}
\longrightarrow
\text{fusion category}.
$$

## References

### First-pass modern references

- Shu-Heng Shao, “What’s Done Cannot Be Undone: TASI Lectures on Non-Invertible Symmetries.” A highly readable physics-first entry point.
- Sakura Schäfer-Nameki, “ICTP Lectures on (Non-)Invertible Generalized Symmetries.” A broad modern introduction connecting invertible generalized symmetries, non-invertible defects, gauging constructions, and symmetry TFT.
- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries.” The standard starting point for the topological-operator viewpoint on generalized symmetries.

### Defects, CFT, and categorical structure

- John Fröhlich, Jürg Fuchs, Ingo Runkel, and Christoph Schweigert, papers on topological defects and rational CFT.
- Ingo Runkel, “Perturbed Defects and T-Systems in Conformal Field Theory,” for concrete defect-fusion technology.
- Petkova and Zuber, papers on generalized twisted partition functions and defect lines in rational CFT.
- Di Francesco, Mathieu, and Sénéchal, *Conformal Field Theory*, for the broader 2D CFT setting.

### Gauging, symmetry TFT, and modern constructions

- Anton Kapustin and Nathan Seiberg, “Coupling a QFT to a TQFT and Duality.”
- Lakshya Bhardwaj, Lea Bottini, Sakura Schäfer-Nameki, and collaborators, papers on generalized and non-invertible symmetries from gauging, condensation defects, and symmetry TFT.
- Recent reviews on non-invertible symmetries in dimensions greater than two, especially for gauge theories, duality defects, and generalized charges.

## Version history

- **2026-06-20:** Initial polished draft. Introduced the non-invertible/categorical symmetry chapter, reading path, landmarks, boundaries, and modern references.
