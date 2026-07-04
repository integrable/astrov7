---
title: "Large-N and Factorization"
description: "Why large-N CFT correlators factorize, how generalized free fields and multi-trace operators emerge, and when this supports a weakly coupled AdS interpretation."
sidebar:
  label: "Large-N and Factorization"
  order: 2
level: Advanced
status: "Polished draft"
source: "Maldacena 1998; Witten 1998; Aharony et al. 2000; Heemskerk et al. 2009; large-N and holographic bootstrap literature."
topics:
  - large-N CFT
  - factorization
  - generalized free fields
  - double-trace operators
  - holographic CFT
canonicalTopics:
  - large-n-and-factorization
  - holographic-factorization
  - multi-trace-operators
researchStatus:
  established:
    - "Large-N factorization makes single-trace correlators generalized-free at leading order and organizes connected correlators as perturbative bulk interactions."
  active:
    - "Current research studies finite-N corrections, large-N mixing, sparse-spectrum criteria, vector versus matrix large-N limits, and bootstrap diagnostics for emergent bulk locality."
---

## Summary

**Large-$N$ factorization** is the CFT mechanism behind weakly coupled holography. In a suitable large-$N$ theory, normalized single-trace operators obey

$$
\langle \mathcal O_1\mathcal O_2\mathcal O_3\mathcal O_4\rangle
=
\langle \mathcal O_1\mathcal O_2\rangle\langle \mathcal O_3\mathcal O_4\rangle
+\text{permutations}
+O(N^{-p}).
$$

The leading term is generalized free field. The subleading connected term contains interactions.

This factorization explains why holographic CFTs have:

- single-trace operators behaving like one-particle bulk states;
- double-trace operators behaving like two-particle states;
- connected correlators behaving like AdS interaction amplitudes;
- anomalous double-trace dimensions behaving like binding energies;
- a perturbative expansion controlled by powers of $1/N$ or $1/C_T$.

The slogan is

$$
\text{factorization creates the bulk Fock space; connected correlators create interactions}.
$$

Large $N$ is necessary for a weakly coupled bulk, but it is not enough. A vector model can factorize at large $N$ without becoming Einstein gravity. For a local gravitational dual, one also needs sparseness and a gap to higher-spin single-trace operators.

## Prerequisites

Read [AdS/CFT Dictionary](/cft-bootstrap/holographic-cft/ads-cft-dictionary/), [Large-N CFTs](/cft-bootstrap/higher-dimensional-cft/large-n-cfts/), [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/), [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/), and [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/) first.

You should know the operator product expansion, primary operators, connected correlators, and the difference between single-trace and multi-trace language.

## Core idea

At large $N$, certain operators behave almost independently. Their connected correlators are suppressed, so the leading four-point function is built out of two-point functions. This is exactly the structure of generalized free field.

For a normalized single-trace scalar $\mathcal O$,

$$
\langle \mathcal O(x)\mathcal O(0)\rangle=\frac{1}{(x^2)^\Delta},
$$

and the leading four-point function is

$$
\mathcal G_{\rm GFF}(u,v)=1+u^\Delta+\left(\frac{u}{v}\right)^\Delta.
$$

The OPE of this leading correlator contains double-trace operators

$$
[\mathcal O\mathcal O]_{n,\ell}
$$

with dimensions

$$
\Delta_{n,\ell}^{(0)}=2\Delta+2n+\ell.
$$

At the next order, the connected correlator shifts these dimensions:

$$
\Delta_{n,\ell}=2\Delta+2n+\ell+N^{-p}\gamma_{n,\ell}^{(1)}+\cdots .
$$

This is the CFT version of turning on weak interactions among bulk particles.

## Connected versus disconnected correlators

For any random variables, connected correlators subtract products of lower-point correlators. In QFT, the connected four-point function is schematically

$$
\langle 1234\rangle_{\rm conn}
=
\langle 1234\rangle
-\langle 12\rangle\langle 34\rangle
-\langle 13\rangle\langle 24\rangle
-\langle 14\rangle\langle 23\rangle.
$$

Large-$N$ factorization says that the connected part is small:

$$
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle_{\rm conn}\sim N^{-p}.
$$

The exponent $p$ depends on normalization and on the kind of large-$N$ theory. In many matrix-like gauge theories with single-trace operators normalized to have order-one two-point functions,

$$
p=2.
$$

In vector models, the scaling can instead be order $1/N$. The exact power matters less than the structure: disconnected pieces dominate, connected pieces are perturbative.

## Generalized free field as leading order

A generalized free field is not necessarily a Lagrangian free field. It is an operator whose higher-point functions are determined by Wick-like factorization.

At leading large $N$, normalized single-trace operators behave this way. Their four-point function is crossing symmetric and has a consistent conformal block decomposition. The OPE contains double-trace families with mean-field dimensions and OPE coefficients.

This leading theory provides the bulk Fock space:

| GFF object | Bulk interpretation |
|---|---|
| identity | vacuum |
| single-trace primary $\mathcal O$ | one-particle state |
| double-trace $[\mathcal O\mathcal O]_{n,\ell}$ | two-particle state |
| triple-trace | three-particle state |
| GFF OPE coefficient | free multi-particle overlap |
| anomalous dimension zero | no interaction energy |

The connected $1/N$ corrections then add interactions to this Fock space.

## Multi-trace operators

Multi-trace operators are composites of single-trace operators. For scalar single-trace operators, a double-trace primary is schematically

$$
[\mathcal O_1\mathcal O_2]_{n,\ell}
\sim
\mathcal O_1\,\partial_{\mu_1}\cdots\partial_{\mu_\ell}(\partial^2)^n\mathcal O_2
-\text{descendants and traces}.
$$

Its leading large-$N$ dimension is

$$
\Delta_{n,\ell}^{(0)}=\Delta_1+\Delta_2+2n+\ell.
$$

Interactions shift it:

$$
\gamma_{n,\ell}=\Delta_{n,\ell}-\Delta_{n,\ell}^{(0)}.
$$

In AdS, this anomalous dimension is a binding energy. In CFT, it is a correction to the scaling dimension required by crossing.

Higher multi-trace operators behave similarly. A triple-trace operator is a three-particle state, and so on.

## OPE coefficient scaling

Large-$N$ factorization also controls OPE coefficients. With normalized single-trace operators, the two-point functions are order one:

$$
\langle \mathcal O_i\mathcal O_j\rangle\sim O(1).
$$

A typical three-point coefficient of single-trace operators scales as

$$
\lambda_{123}\sim N^{-p/2}
$$

in a convention where the connected four-point function scales as $N^{-p}$.

For matrix large-$N$ theories, this often means

$$
\lambda_{123}\sim \frac{1}{N}.
$$

This is why bulk cubic couplings are small at large $N$. The bulk theory is weakly interacting because boundary connected correlators are suppressed.

Precise powers depend on operator normalization, whether the theory is vector-like or matrix-like, and whether one uses $N$, $C_T$, or another large parameter.

## Central charge and Newton coupling

The stress-tensor two-point normalization $C_T$ is often the cleanest large parameter in a CFT. Holographically,

$$
C_T\sim \frac{R_{\rm AdS}^{d-1}}{G_N}
$$

up to dimension-dependent constants.

Thus large $C_T$ means small Newton coupling in AdS units. Quantum gravitational loops are suppressed by powers of

$$
G_N/R_{\rm AdS}^{d-1}\sim C_T^{-1}.
$$

In many holographic examples,

$$
C_T\sim N^2.
$$

Then the $1/N^2$ expansion is the bulk loop expansion. Tree-level Witten diagrams correspond to leading connected correlators; loop Witten diagrams correspond to further powers of $1/N^2$.

## Tree level and loops in AdS

The large-$N$ expansion organizes bulk perturbation theory.

| CFT order | Bulk interpretation |
|---|---|
| disconnected GFF | free multi-particle theory |
| leading connected $O(N^{-p})$ | tree-level Witten diagrams |
| next connected order | one-loop Witten diagrams |
| further orders | higher bulk loops |
| nonperturbative in $N$ | quantum gravity saddles, branes, black-hole microstructure |

At tree level, the connected four-point function is built from AdS contact and exchange diagrams. These determine the leading anomalous dimensions

$$
\gamma_{n,\ell}^{(1)}.
$$

At loop level, double discontinuities often contain products of tree-level data. This is the CFT analogue of unitarity cuts in scattering amplitudes.

## Factorization and cluster decomposition

Large-$N$ factorization resembles a strong form of statistical independence for normalized single-trace operators. It should not be confused with ordinary cluster decomposition.

Cluster decomposition says that distant operators become uncorrelated in a vacuum with appropriate locality properties. Large-$N$ factorization says that connected correlators of certain operators are suppressed even at finite separations, once the correct large-$N$ normalization is used.

The distinction is:

$$
\text{cluster decomposition}:\quad \text{large distance},
$$

$$
\text{large-}N\text{ factorization}:\quad \text{large parameter}.
$$

Both are useful. They are not the same theorem.

## Matrix large N versus vector large N

Large $N$ comes in different species.

| Type | Typical singlet operators | Bulk tendency |
|---|---|---|
| matrix large $N$ | traces of matrices | stringy or gravitational AdS dual possible |
| vector large $N$ | bilinears of vectors | higher-spin-like dual common |
| tensor large $N$ | tensor invariants | model-dependent, often melonic dynamics |
| supersymmetric large $N$ | protected plus unprotected sectors | strong exact constraints possible |

Matrix large-$N$ gauge theories are the classic home of AdS/CFT. Vector models can also have AdS duals, but often with towers of light higher-spin fields rather than Einstein gravity.

Therefore:

$$
\text{large }N\not\Rightarrow\text{Einstein gravity}.
$$

Large $N$ gives weak coupling. Sparseness and a higher-spin gap decide what the weakly coupled bulk is.

## Sparseness and higher-spin gaps

For a local Einstein-like bulk effective field theory, one wants few light single-trace operators. In particular, one wants a large gap to higher-spin single-trace operators:

$$
\Delta_{\rm gap}\gg1.
$$

Why? Because light higher-spin fields strongly constrain interactions and usually signal stringy or higher-spin physics at low energies. A large higher-spin gap lets the bulk be described by a small number of low-spin fields over a wide energy range.

The practical criterion is:

$$
\text{large }C_T + \text{sparse low spectrum} + \text{higher-spin gap}
\quad\Rightarrow\quad
\text{semiclassical local AdS EFT}.
$$

This is not a theorem in one line, but it is the guiding principle behind holography from CFT data.

## Factorization and crossing

Factorization alone gives generalized free field at leading order. Crossing at subleading order is much more restrictive.

Write

$$
\mathcal G(u,v)=\mathcal G_{\rm GFF}(u,v)+N^{-p}\mathcal G^{(1)}(u,v)+\cdots .
$$

Then crossing requires

$$
\mathcal G^{(1)}(u,v)
$$

to be consistent with the shifts of double-trace dimensions and OPE coefficients in every channel.

This is the heart of large-$N$ analytic bootstrap. The connected correlator is not arbitrary. It must be a crossing-symmetric deformation of generalized free field.

In Mellin space, this deformation becomes a sum of exchange terms and contact polynomials. In Lorentzian inversion, it is reconstructed from double discontinuities plus possible contact ambiguities.

## Common pitfalls

**Do not say large $N$ means free theory.** It means certain normalized correlators factorize at leading order. Subleading connected correlators can encode strongly coupled dynamics.

**Do not assume $1/N^2$ in every theory.** Vector and matrix models have different counting.

**Do not confuse single-trace with single-particle outside its regime.** The language is sharpest in matrix-like large-$N$ holographic theories.

**Do not ignore multi-trace mixing.** Degenerate double-trace operators require anomalous-dimension matrices.

**Do not infer Einstein gravity from factorization alone.** Sparseness and a higher-spin gap are essential.

**Do not forget normalization.** OPE coefficient scaling depends on how operators are normalized.

**Do not treat generalized free field as a complete local QFT with finite stress-tensor data.** It is a consistent crossing solution and a leading large-$N$ limit, but finite-$N$ locality needs more structure.

## Relations to other pages

This page follows [AdS/CFT Dictionary](/cft-bootstrap/holographic-cft/ads-cft-dictionary/) and prepares [Witten Diagrams](/cft-bootstrap/holographic-cft/witten-diagrams/) and [Bulk Locality from CFT Data](/cft-bootstrap/holographic-cft/bulk-locality-from-cft-data/).

It connects back to [Large-N Analytic Bootstrap](/cft-bootstrap/analytic-bootstrap/large-n-analytic-bootstrap/), [Double-Twist Operators](/cft-bootstrap/analytic-bootstrap/double-twist-operators/), and [Generalized Free Fields](/cft-bootstrap/higher-dimensional-cft/generalized-free-fields/).

For later holographic applications, see [Mellin Amplitudes and Flat-Space Limits](/cft-bootstrap/holographic-cft/mellin-amplitudes-and-flat-space-limits/) and [Stringy Corrections and Higher-Spin Gaps](/cft-bootstrap/holographic-cft/stringy-corrections-and-higher-spin-gaps/).

## Research status

Large-$N$ factorization and its generalized-free leading behavior are established pillars of holographic CFT. The multi-trace interpretation of AdS multi-particle states is standard.

Active research focuses on the sharp conditions under which large-$N$ CFT data imply local bulk physics: sparseness, Regge behavior, finite-$N$ corrections, higher-spin gaps, mixing, loop-level reconstruction, and numerical bootstrap tests of holographic spectra.

## Exercises

### Exercise 1

What does large-$N$ factorization say about a normalized single-trace four-point function?

<details><summary><strong>Solution</strong></summary>

It says that the leading four-point function is a sum of products of two-point functions, while the connected part is suppressed:

$$
\langle \mathcal O\mathcal O\mathcal O\mathcal O\rangle
=\langle \mathcal O\mathcal O\rangle\langle \mathcal O\mathcal O\rangle
+\text{permutations}+O(N^{-p}).
$$

Thus the leading correlator is generalized free.

</details>

### Exercise 2

Why do double-trace operators appear at leading large $N$?

<details><summary><strong>Solution</strong></summary>

The leading generalized-free four-point function has an OPE decomposition containing composite primary operators built from two single-trace operators. For scalar operators, these have leading dimensions

$$
\Delta_{n,\ell}^{(0)}=\Delta_1+\Delta_2+2n+\ell.
$$

They are the CFT description of two-particle states in AdS.

</details>

### Exercise 3

What is the physical meaning of a double-trace anomalous dimension in AdS?

<details><summary><strong>Solution</strong></summary>

A double-trace anomalous dimension is the shift away from the noninteracting two-particle energy:

$$
\gamma_{n,\ell}=\Delta_{n,\ell}-\Delta_{n,\ell}^{(0)}.
$$

In AdS, it is interpreted as the interaction energy or binding energy of the two-particle state.

</details>

### Exercise 4

Why is large $N$ not sufficient for an Einstein gravity dual?

<details><summary><strong>Solution</strong></summary>

Large $N$ suppresses connected correlators and can give weak bulk coupling, but it does not determine the particle content. An Einstein-like bulk dual also requires a sparse low-dimension single-trace spectrum and a large gap to higher-spin single-trace operators. Without such a gap, the bulk may be higher-spin-like or stringy at low energies.

</details>

### Exercise 5

How is $C_T$ related to the bulk Newton constant?

<details><summary><strong>Solution</strong></summary>

The stress-tensor two-point normalization scales like

$$
C_T\sim \frac{R_{\rm AdS}^{d-1}}{G_N}
$$

up to dimension-dependent constants and conventions. Thus large $C_T$ corresponds to small bulk Newton coupling in AdS units and suppresses quantum-gravity loop effects.

</details>

## References

- J. Maldacena, “The Large N Limit of Superconformal Field Theories and Supergravity,” *Advances in Theoretical and Mathematical Physics* **2** (1998).
- E. Witten, “Anti de Sitter space and holography,” *Advances in Theoretical and Mathematical Physics* **2** (1998).
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, “Large N field theories, string theory and gravity,” *Physics Reports* **323** (2000).
- I. Heemskerk, J. Penedones, J. Polchinski, and J. Sully, “Holography from conformal field theory,” *Journal of High Energy Physics* **2009**.
- A. L. Fitzpatrick, J. Kaplan, J. Penedones, S. Raju, and B. C. van Rees, “A natural language for AdS/CFT correlators,” *Journal of High Energy Physics* **2011**.
- S. Caron-Huot, “Analyticity in spin in conformal theories,” *Journal of High Energy Physics* **2017**.

## Version history

- 2026-07-01: First polished draft. Added factorization definition, generalized-free leading behavior, multi-trace spectrum, OPE coefficient scaling, central-charge/Newton-coupling relation, tree and loop interpretation, matrix/vector distinction, sparseness and higher-spin-gap caveats, exercises, and references.
