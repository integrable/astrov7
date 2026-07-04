---
title: "Polyakov Bootstrap"
description: "How crossing-symmetric exchange blocks and spurious-pole cancellation turn conformal bootstrap into analytic sum rules for CFT data."
sidebar:
  label: "Polyakov Bootstrap"
  order: 9
level: Advanced
status: "Polished draft"
source: "Polyakov; Gopakumar; Mazac; Paulos; Sleight; Taronna; analytic bootstrap and Mellin-space bootstrap literature."
topics:
  - Polyakov bootstrap
  - analytic conformal bootstrap
  - crossing symmetry
  - Mellin amplitudes
  - sum rules
canonicalTopics:
  - polyakov-bootstrap
  - crossing-symmetric-blocks
  - spurious-pole-cancellation
researchStatus:
  established:
    - "The Polyakov bootstrap reformulates crossing using crossing-symmetric exchange objects, leading to analytic sum rules from the cancellation of spurious singularities."
  active:
    - "Current research develops higher-dimensional Polyakov blocks, Mellin-space formulations, one-dimensional analytic functionals, spinning correlators, AdS contact ambiguities, and links to numerical bootstrap."
---

## Summary

The **Polyakov bootstrap** is a crossing-symmetric way to expand CFT four-point functions. Instead of expanding a correlator in conformal blocks of one OPE channel and then imposing crossing, it uses building blocks that are crossing symmetric from the start.

The usual conformal block expansion looks like

$$
\mathcal G(u,v)=\sum_{\mathcal O}a_{\mathcal O}G_{\Delta,\ell}^{(s)}(u,v),
$$

where the superscript reminds us that these are $s$-channel blocks. Crossing is then a separate constraint.

Polyakov's idea is to use crossing-symmetric exchange objects, schematically

$$
\mathcal P_{\Delta,\ell}(u,v),
$$

so that

$$
\mathcal G(u,v)=\sum_{\mathcal O}a_{\mathcal O}\mathcal P_{\Delta,\ell}(u,v)
$$

is crossing symmetric term by term, or at least organized in a crossing-symmetric basis after adding contact terms.

The price is that individual Polyakov blocks can contain **spurious singularities** that are not allowed in a physical correlator. Requiring those spurious pieces to cancel gives analytic bootstrap equations, often called Polyakov sum rules.

The slogan is

$$
\text{make crossing manifest, then cancel what should not be there}.
$$

## Prerequisites

Read [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/), [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/), [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/), and [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/) first.

You should know ordinary conformal blocks, crossing equations, Mellin pole language, and the idea that a physical correlator must have only the singularities allowed by the OPE.

## Core idea

The ordinary bootstrap starts with one-channel OPE expansions. For identical scalars, one may write

$$
\mathcal G(u,v)=\sum_{\mathcal O}a_{\mathcal O}G_{\Delta,\ell}(u,v),
$$

and impose crossing:

$$
v^{\Delta_\phi}\mathcal G(u,v)=u^{\Delta_\phi}\mathcal G(v,u).
$$

This makes OPE data visible but crossing nontrivial.

The Polyakov bootstrap reverses the emphasis. It builds correlators from objects that already know about crossing. This makes crossing easier but introduces new consistency conditions: the crossing-symmetric representation must not generate unphysical singularities.

The conceptual chain is

$$
\text{crossing-symmetric ansatz}
\quad\longrightarrow\quad
\text{spurious singularities}
\quad\longrightarrow\quad
\text{sum rules for CFT data}.
$$

This is why the Polyakov bootstrap sits naturally between conformal block bootstrap, Mellin amplitudes, and AdS Witten diagrams.

## Why ordinary blocks are not manifestly crossing symmetric

A conformal block is adapted to one OPE channel. The $s$-channel block captures the contribution of a primary and its descendants in the OPE

$$
\phi(x_1)\times\phi(x_2).
$$

It has the correct singular behavior as

$$
u\to0.
$$

But the same block is not symmetric under exchanging points that swap OPE channels. Crossing relates the $s$-channel expansion to the $t$- and $u$-channel expansions:

$$
s\text{-channel OPE}=t\text{-channel OPE}=u\text{-channel OPE}.
$$

Therefore, in the ordinary bootstrap, crossing appears as a global constraint on an infinite sum of channel-specific blocks.

Polyakov blocks try to package the exchange of an operator together with its crossed images. They are more democratic. Very polite blocks. Occasionally too polite, hence the contact ambiguities.

## Polyakov blocks

A **Polyakov block** is a crossing-symmetric exchange object associated with a primary operator. In holographic or Mellin language, it is often represented by a sum of exchange Witten diagrams in all channels, plus contact terms chosen to satisfy desired boundedness or spurious-pole conditions.

Schematically,

$$
\mathcal P_{\Delta,\ell}
=\mathcal W_{\Delta,\ell}^{(s)}
+\mathcal W_{\Delta,\ell}^{(t)}
+\mathcal W_{\Delta,\ell}^{(u)}
+\mathcal C_{\Delta,\ell},
$$

where:

| Symbol | Meaning |
|---|---|
| $\mathcal W^{(s)}$ | exchange object in the $s$ channel |
| $\mathcal W^{(t)}$ | crossed exchange object in the $t$ channel |
| $\mathcal W^{(u)}$ | crossed exchange object in the $u$ channel |
| $\mathcal C$ | contact-term ambiguity or subtraction |

The exact definition depends on dimension, external operators, spin, and the desired Regge behavior.

Polyakov blocks are not unique until contact ambiguities are fixed. This is not a bug; it is the analytic-bootstrap version of choosing a basis.

## Spurious singularities

A physical correlator has OPE singularities dictated by physical operators. A crossing-symmetric exchange object may contain extra singularities that are artifacts of the representation. These are called **spurious singularities**.

In Mellin space, spurious singularities often appear as poles at locations associated with double-trace dimensions of mean-field theory. The physical correlator cannot have arbitrary uncanceled residues at these locations.

For identical scalar correlators, the mean-field double-twist locations are

$$
\Delta_{n,\ell}^{(0)}=2\Delta_\phi+2n+\ell.
$$

The Polyakov bootstrap requires cancellation of unphysical or overcounted contributions associated with such locations.

The resulting conditions become sum rules on the physical CFT data:

$$
\sum_{\mathcal O}a_{\mathcal O}\,\omega_{n,\ell}(\Delta_{\mathcal O},\ell_{\mathcal O})=0,
$$

schematically, where $\omega_{n,\ell}$ is a functional determined by the spurious-pole condition.

## Mellin-space formulation

Mellin space is a natural home for Polyakov bootstrap. Exchange Witten diagrams are meromorphic in Mellin variables, and contact terms are polynomial. Crossing-symmetric combinations are easy to write.

A schematic Mellin-space Polyakov ansatz is

$$
M(s,t)=\sum_{\mathcal O}a_{\mathcal O}M_{\Delta,\ell}^{\rm exch}(s,t)
+M_{\rm contact}(s,t),
$$

where each exchange contribution is symmetrized across channels.

The physical constraints are:

1. correct physical poles for exchanged primaries;
2. crossing symmetry;
3. cancellation of spurious poles;
4. acceptable Regge behavior;
5. compatibility with OPE data and unitarity.

In this language, the Polyakov bootstrap resembles an on-shell amplitude bootstrap: write the allowed meromorphic structure, impose symmetry and boundedness, then solve residue constraints.

## Relation to Witten diagrams

In AdS/CFT, Witten diagrams provide crossing-symmetric objects with clear bulk interpretations. Exchange Witten diagrams correspond to a bulk field exchanged between boundary insertions. Contact Witten diagrams correspond to local bulk interactions.

A Polyakov block can often be represented by an exchange Witten diagram dressed with contact terms. The contact terms are chosen to remove spurious behavior or satisfy Regge boundedness.

The analogy is:

| Polyakov bootstrap | AdS language |
|---|---|
| exchanged primary | bulk field exchange |
| Polyakov block | crossing-symmetrized exchange diagram plus contact terms |
| spurious pole | unphysical double-trace artifact |
| spurious-pole cancellation | bootstrap sum rule |
| contact ambiguity | local AdS counterterm or EFT interaction |
| Regge boundedness | high-energy bulk causality condition |

This is why Polyakov bootstrap is deeply connected to holographic bootstrap, even though the idea is more general than holography.

## Sum rules

The practical output of Polyakov bootstrap is a family of sum rules. Each spurious pole or unwanted singularity gives a condition. A typical schematic form is

$$
\sum_{\mathcal O}a_{\mathcal O}\,F_{n}(\Delta_{\mathcal O},\ell_{\mathcal O})=0,
$$

or, when double poles and single poles both matter,

$$
\sum_{\mathcal O}a_{\mathcal O}\,F_{n}(\Delta_{\mathcal O},\ell_{\mathcal O})=0,
\qquad
\sum_{\mathcal O}a_{\mathcal O}\,G_{n}(\Delta_{\mathcal O},\ell_{\mathcal O})=0.
$$

These functionals are analytic analogues of numerical bootstrap functionals. They test CFT data by applying crossing-symmetric consistency conditions.

In one-dimensional CFTs and related systems, such functionals can be made especially explicit and rigorous. In higher dimensions, the construction is richer and more technically involved.

The lesson is:

$$
\text{spurious-pole cancellation} = \text{analytic bootstrap equations}.
$$

## One-dimensional Polyakov bootstrap

The Polyakov bootstrap is particularly transparent in one-dimensional conformal field theory, or conformal quantum mechanics. There is only one cross-ratio, and crossing is simpler.

For identical scalars, a four-point function depends on one variable $z$. The ordinary conformal block expansion is one-dimensional, and analytic functionals can be constructed explicitly.

In this setting, the Polyakov bootstrap leads to functionals whose zeros and positivity properties resemble numerical bootstrap extremal functionals. It gives a clean laboratory for understanding:

- crossing-symmetric blocks;
- functional bases;
- extremal solutions;
- generalized free field data;
- spurious-pole cancellation;
- rigorous analytic bounds.

Many conceptual lessons from one-dimensional Polyakov bootstrap carry over to higher dimensions, though the technical machinery becomes much heavier.

## Higher-dimensional challenges

In higher dimensions, the Polyakov bootstrap is harder for several reasons:

| Challenge | Why it matters |
|---|---|
| spin | exchanged operators carry tensor structures |
| multiple cross-ratios | spurious singularities live in more variables |
| contact ambiguities | many polynomial or local terms are possible |
| Regge behavior | boundedness conditions depend on spin and channel |
| global symmetry | representation sectors multiply constraints |
| mixing | double-twist families can be degenerate |
| convergence | crossing-symmetric expansions need careful control |

These challenges are not reasons to avoid the method. They are the reason the method is interesting.

Modern work often combines Polyakov ideas with Mellin space, Lorentzian inversion, and numerical functionals to tame these complications.

## Contact-term ambiguity

Polyakov blocks are not unique because one can add crossing-symmetric contact terms without changing the physical exchange poles. In Mellin space, these are polynomial ambiguities:

$$
M_{\rm contact}(s,t)=\text{crossing-symmetric polynomial}.
$$

This ambiguity must be fixed by additional criteria, such as:

- Regge boundedness;
- locality or derivative-order assumptions;
- absence of certain spurious poles;
- supersymmetric Ward identities;
- known OPE data;
- flat-space limits;
- normalization conventions.

Contact ambiguity is the Polyakov-bootstrap version of scheme choice. It does not mean anything goes. It means one must state the basis and boundedness conditions clearly.

## Relation to numerical bootstrap

The Polyakov bootstrap and numerical bootstrap are cousins. Both produce linear constraints on CFT data. Numerical bootstrap functionals are usually constructed by optimizing finite derivative constraints. Polyakov functionals arise analytically from spurious-pole cancellation or crossing-symmetric expansions.

The comparison is useful:

| Numerical bootstrap | Polyakov bootstrap |
|---|---|
| derivative functionals | analytic functionals from spurious-pole conditions |
| exclusion certificates | sum rules and sometimes bounds |
| finite cutoff | analytic construction with its own convergence assumptions |
| extremal functional zeros | zeros of analytic functionals |
| crossing imposed on block sums | crossing built into exchange objects |

In favorable cases, Polyakov functionals can explain why certain numerical functionals look the way they do. Conversely, numerical experiments can suggest analytic functional bases.

This is a very productive feedback loop. Tiny numerical goblin meets elegant analytic goblin. They compare notes.

## Relation to Lorentzian inversion

Lorentzian inversion reconstructs CFT data from double discontinuities. Polyakov bootstrap organizes correlators into crossing-symmetric exchange objects. These approaches are related because both use analyticity, crossing, and control of unphysical terms.

In some formulations, Polyakov sum rules can be understood through dispersion relations or inversion formulas with subtractions. The subtractions are related to contact terms and low-spin ambiguities.

The rough relation is:

$$
\text{Lorentzian inversion}
\quad\text{reconstructs data from physical cuts},
$$

while

$$
\text{Polyakov bootstrap}
\quad\text{builds crossing-symmetric correlators and cancels fake cuts or poles}.
$$

Both are ways of converting analytic structure into constraints on CFT data.

## Example: generalized free field

Generalized free field is the simplest test case. Its four-point function is

$$
\mathcal G_{\rm GFF}(u,v)
=1+u^{\Delta_\phi}+\left(\frac{u}{v}\right)^{\Delta_\phi}.
$$

It is crossing symmetric and has double-twist operators with dimensions

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell.
$$

A correct Polyakov-bootstrap formulation must reproduce this solution. The spurious-pole cancellation conditions are satisfied by the generalized-free OPE data.

This makes GFF a useful calibration point. If a proposed set of Polyakov blocks cannot reproduce generalized free field, something in the basis, normalization, or contact-term choice is wrong.

## Common pitfalls

**Do not confuse Polyakov blocks with ordinary conformal blocks.** Ordinary blocks are channel-specific. Polyakov blocks are crossing-symmetric exchange objects or symmetrized combinations.

**Do not forget contact ambiguities.** Crossing-symmetric exchange objects are not unique until boundedness or subtraction conditions are specified.

**Do not treat spurious poles as physical operators.** They are artifacts whose cancellation gives constraints.

**Do not assume the one-dimensional story transfers automatically to higher dimensions.** Higher-dimensional spin, tensor structures, and contact terms are harder.

**Do not ignore Regge behavior.** It often fixes or constrains the allowed Polyakov block basis.

**Do not use Mellin formulas without checking conventions.** Pole positions and residues shift with definitions of Mellin variables.

**Do not claim crossing is solved for free.** Polyakov bootstrap makes crossing manifest but replaces it with nontrivial analyticity and cancellation conditions.

## Relations to other pages

This page follows [Mellin-Space Bootstrap](/cft-bootstrap/analytic-bootstrap/mellin-space-bootstrap/) and prepares [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/) and [Analytic-Numerical Bridges](/cft-bootstrap/analytic-bootstrap/analytic-numerical-bridges/).

It also connects to [Lorentzian Inversion Formula](/cft-bootstrap/analytic-bootstrap/lorentzian-inversion-formula/) and [Double Discontinuity](/cft-bootstrap/analytic-bootstrap/double-discontinuity/) because Polyakov sum rules can be related to dispersion and inversion ideas.

For ordinary channel expansions, see [Conformal Blocks](/cft-bootstrap/conformal-blocks/) and [Crossing Symmetry](/cft-bootstrap/crossing-bootstrap-logic/crossing-symmetry/). For holographic interpretations, see [Holographic CFT](/cft-bootstrap/holographic-cft/).

## Research status

The Polyakov bootstrap is an established analytic reformulation of crossing based on crossing-symmetric exchange objects and cancellation of spurious singularities. It has especially sharp formulations in one-dimensional CFT and in Mellin-space/holographic contexts.

Active research develops higher-dimensional Polyakov blocks, spinning and supersymmetric generalizations, contact-term classification, dispersion-relation formulations, rigorous analytic functionals, and links to numerical bootstrap extremal functionals.

## Exercises

### Exercise 1

What is the main difference between an ordinary conformal block and a Polyakov block?

<details><summary><strong>Solution</strong></summary>

An ordinary conformal block is adapted to one OPE channel and represents the contribution of one primary and its descendants in that channel. It is not crossing symmetric by itself. A Polyakov block is a crossing-symmetric exchange object, often built from exchange diagrams in all channels plus contact terms. It makes crossing manifest but can introduce spurious singularities that must cancel in the full correlator.

</details>

### Exercise 2

Why do spurious poles lead to bootstrap equations?

<details><summary><strong>Solution</strong></summary>

A physical correlator can only have singularities allowed by the OPE. If a crossing-symmetric representation introduces spurious poles, their residues must cancel after summing over physical operators. Setting the spurious residues to zero gives equations of the schematic form

$$
\sum_{\mathcal O}a_{\mathcal O}F(\Delta_{\mathcal O},\ell_{\mathcal O})=0.
$$

These are Polyakov bootstrap sum rules.

</details>

### Exercise 3

Why are contact terms part of the Polyakov block story?

<details><summary><strong>Solution</strong></summary>

Crossing-symmetric exchange objects are not unique. One can add crossing-symmetric contact terms without changing the physical exchange poles. In Mellin space, these contact terms are crossing-symmetric polynomials. They are fixed by additional criteria such as Regge boundedness, locality assumptions, or cancellation of spurious singularities.

</details>

### Exercise 4

How does Mellin space help the Polyakov bootstrap?

<details><summary><strong>Solution</strong></summary>

In Mellin space, exchange contributions are meromorphic functions with pole structures corresponding to exchanged operators, while contact terms are polynomials. Crossing acts by permuting Mellin variables. This makes it natural to build crossing-symmetric exchange ansätze and impose spurious-pole cancellation as residue constraints.

</details>

### Exercise 5

Why is generalized free field a useful test case for Polyakov bootstrap?

<details><summary><strong>Solution</strong></summary>

Generalized free field has an exactly crossing-symmetric four-point function and known double-twist spectrum:

$$
\Delta_{n,\ell}=2\Delta_\phi+2n+\ell.
$$

A correct Polyakov-bootstrap formulation should reproduce this solution and satisfy the spurious-pole cancellation conditions with generalized-free OPE data. Failure to do so indicates a problem with basis, normalization, or contact-term choices.

</details>

## References

- A. M. Polyakov, “Nonhamiltonian approach to conformal quantum field theory,” *Zh. Eksp. Teor. Fiz.* **66** (1974).
- R. Gopakumar, A. Kaviraj, K. Sen, and A. Sinha, “Conformal bootstrap in Mellin space,” *Physical Review Letters* **118** (2017).
- M. F. Paulos, “Towards Feynman rules for Mellin amplitudes,” *Journal of High Energy Physics* **2011**.
- D. Mazac, “Analytic bounds and emergence of AdS2 physics from the conformal bootstrap,” *Journal of High Energy Physics* **2017**.
- C. Sleight and M. Taronna, “Spinning Witten diagrams,” *Journal of High Energy Physics* **2017**.
- J. Penedones, “Writing CFT correlation functions as AdS scattering amplitudes,” *Journal of High Energy Physics* **2011**.
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.

## Version history

- 2026-07-01: First polished draft. Added crossing-symmetric block idea, spurious-pole cancellation, Mellin and Witten-diagram formulations, contact-term ambiguity, one-dimensional and higher-dimensional comments, relation to numerical bootstrap and inversion, exercises, and references.
