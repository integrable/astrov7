---
title: "Spin–Statistics Theorem"
description: "States the Wightman spin–statistics theorem and explains why relativistic locality, positive energy, and Hilbert positivity fix the Bose or Fermi grading of finite-spin fields."
sidebar:
  label: "Spin–Statistics Theorem"
  order: 9
level: Graduate
status: "Polished draft"
source: "Pauli; Lüders–Zumino; Burgoyne; Streater–Wightman; Jost."
topics:
  - spin-statistics theorem
  - Wightman axioms
  - locality
  - Lorentz covariance
  - Hilbert positivity
canonicalTopics:
  - spin-statistics-theorem
  - wightman-axioms
  - relativistic-locality
researchStatus:
  established:
    - "In Wightman-type relativistic QFT with positive Hilbert space, positive energy, finite-component covariance, and locality, the local field grading is fixed by Lorentz spin: integer-spin fields are bosonic and half-integer-spin fields are fermionic."
  active:
    - "Variants in low dimensions, gauge-fixed indefinite-metric formalisms, algebraic superselection theory, and braided tensor categories require more refined statements than the elementary Bose/Fermi slogan."
---

## Summary

The spin–statistics theorem is the rigorous form of the rule

$$
\text{integer spin} \Rightarrow \text{Bose locality},
\qquad
\text{half-integer spin} \Rightarrow \text{Fermi locality}.
$$

In Wightman language, this is not merely a rule about free particles. It is a theorem about local relativistic fields on a positive Hilbert space. If a nonzero finite-component field transforms as an irreducible Lorentz representation $(j,k)$, then its local exchange sign is fixed by

$$
\epsilon_\phi=(-1)^{2(j+k)}.
$$

Thus scalar, vector, tensor, and field-strength fields commute at spacelike separation, while Weyl, Dirac, and other spinor fields anticommute at spacelike separation.

The theorem uses the same structural ingredients that make the Wightman framework powerful: Poincaré covariance, the spectral condition, locality, vacuum cyclicity, and positivity of the Hilbert-space inner product. If one drops positivity, as in gauge-fixed ghost formalisms, wrong-statistics auxiliary fields can appear without contradicting the theorem.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Logical structure of the spin–statistics theorem in Wightman QFT](/figures/rigorous-qft/spin-statistics-map.svg)

<figcaption>

The spin–statistics theorem combines covariance, positive energy, locality, and Hilbert positivity. Analyticity of Wightman functions turns spacelike exchange into a controlled continuation; the central Lorentz element corresponding to a $2\pi$ rotation supplies the spin sign, and positivity rules out the wrong local grading for nonzero finite-component fields.

</figcaption>
</figure>

## Prerequisites

You should know [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/), [Poincaré Covariance](/rigorous-qft/wightman-axiomatic-qft/poincare-covariance/), [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/), and [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/). The theorem is naturally stated using [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/) and the cyclic Hilbert-space picture from [Wightman Reconstruction Theorem](/rigorous-qft/wightman-axiomatic-qft/reconstruction-theorem/).

You do not need a full course in several-complex-variable analysis for this page, but you should know that the spectral condition implies analyticity of Wightman functions in tube domains.

## Logical status

| Item | Status |
|---|---|
| Type | Theorem. |
| Framework | Wightman-style relativistic QFT, stated here for finite-component fields in four-dimensional Minkowski spacetime. |
| Assumptions | Lorentz covariance, positive energy, local graded commutativity, vacuum cyclicity, and positive Hilbert-space metric. |
| Conclusion | The field grading must match the Lorentz spin parity: integer-spin fields are even and half-integer-spin fields are odd. |
| Main caveat | Gauge ghosts, anyons, braid statistics, and topological sectors change one or more hypotheses. |

## Core idea

Spin and statistics look unrelated in nonrelativistic quantum mechanics. Spin labels how a state transforms under rotations. Statistics labels how states or fields behave under exchange. Relativistic local QFT ties them together because exchange of spacelike separated field insertions can be compared, through analytic continuation and Lorentz covariance, with a rotation in the complexified Lorentz group.

The theorem is not simply

$$
\text{``wavefunctions must be symmetric or antisymmetric.''}
$$

The theorem is about **local field algebras**. A field is assigned a parity

$$
p_\phi\in\{0,1\},
$$

where $p_\phi=0$ means even, or bosonic, and $p_\phi=1$ means odd, or fermionic. Locality is then the graded relation

$$
\phi_i(f)\phi_j(g)
-
(-1)^{p_i p_j}\phi_j(g)\phi_i(f)=0
$$

whenever $\operatorname{supp}f$ and $\operatorname{supp}g$ are spacelike separated.

The spin–statistics theorem says that this parity is not freely adjustable. It must match the Lorentz transformation type of the field.

## Lorentz parity of a field

Finite-dimensional irreducible representations of the complexified proper Lorentz group are labeled by two half-integers:

$$
(j,k),
\qquad
j,k\in\frac12\mathbb Z_{\geq0}.
$$

Examples are:

| Field type | Lorentz type | Central sign | Local grading |
|---|---:|---:|---:|
| scalar $\phi$ | $(0,0)$ | $+1$ | bosonic |
| left Weyl spinor $\psi_\alpha$ | $(\frac12,0)$ | $-1$ | fermionic |
| right Weyl spinor $\overline\psi_{\dot\alpha}$ | $(0,\frac12)$ | $-1$ | fermionic |
| vector $A_\mu$ | $(\frac12,\frac12)$ | $+1$ | bosonic |
| self-dual field strength $F_{\alpha\beta}$ | $(1,0)$ | $+1$ | bosonic |

The relevant sign is the action of the central element $-1\in SL(2,\mathbb C)$:

$$
D_{(j,k)}(-1)=(-1)^{2(j+k)}.
$$

This sign is $+1$ for tensor representations and $-1$ for spinor representations. In physical language, it distinguishes integer-spin from half-integer-spin fields.

The theorem can therefore be summarized as

$$
(-1)^{p_\phi}=D_\phi(-1).
$$

Equivalently, the field parity $p_\phi$ must agree with the spinorial parity of the Lorentz representation.

## The theorem

A common Wightman-style statement is the following.

:::note[Spin–statistics theorem]
Let $\phi$ be a nonzero finite-component Wightman field on a positive Hilbert space. Suppose $\phi$ transforms covariantly under a finite-dimensional Lorentz representation $D_\phi$, satisfies the spectral condition, and is local or graded-local at spacelike separation.

Then the local grading of $\phi$ is fixed by the central Lorentz sign:

$$
(-1)^{p_\phi}=D_\phi(-1).
$$

For an irreducible Lorentz representation $(j,k)$, this means

$$
p_\phi
\equiv
2(j+k)
\pmod 2.
$$

Thus integer-spin fields are bosonic and half-integer-spin fields are fermionic. If the opposite grading is imposed under the Wightman hypotheses, the field is trivial in the physical Hilbert space.
:::

For a collection of fields, the statement is applied to each irreducible Lorentz-parity sector. Local products then use the graded commutator

$$
[\phi_i(f),\phi_j(g)]_{\mathrm{gr}}
=
\phi_i(f)\phi_j(g)
-
(-1)^{p_i p_j}\phi_j(g)\phi_i(f).
$$

If both fields are odd, this is an anticommutator. Otherwise it is a commutator.

## What assumptions do the work?

The theorem is sometimes described as a consequence of relativity alone. That is too vague. The Wightman proof uses a package of assumptions.

| Assumption | Role in the theorem |
|---|---|
| Poincaré covariance | Makes spin and Lorentz transformation type meaningful. |
| Finite-component field representation | Lets the central Lorentz sign $D(-1)$ be a fixed number on an irreducible sector. |
| Spectral condition | Gives analyticity of Wightman functions in forward tube domains. |
| Locality | Relates boundary values after spacelike exchange of field insertions. |
| Vacuum cyclicity | Lets statements about vacuum matrix elements determine field action on a dense domain. |
| Hilbert positivity | Rules out the wrong grading by turning analytic identities into norm constraints. |

Removing any of these assumptions changes the statement. For example, Faddeev–Popov ghosts are scalar fields with fermionic grading, but they are auxiliary fields in an indefinite or BRST state space, not Wightman fields on the physical positive Hilbert space.

## Proof idea

The full proof is a theorem of axiomatic QFT, not a one-line argument. The conceptual spine is as follows.

First, the spectral condition implies that Wightman functions are boundary values of analytic functions in tube domains. For an $n$-point function, translation invariance reduces the variables to differences, and positive energy places Fourier support in future cones. This is the analytic input.

Second, Lorentz covariance extends the analytic functions to larger domains after complexifying the Lorentz group. Special real boundary points in these domains, called Jost points, include configurations where adjacent points are mutually spacelike.

Third, locality gives an equality of boundary values at such spacelike configurations. For two fields, the local relation has the schematic form

$$
W_{\phi\chi}(x,y)
=
(-1)^{p_\phi p_\chi}
W_{\chi\phi}(y,x)
$$

at spacelike separation, with component indices suppressed.

Fourth, analytic continuation compares this spacelike exchange with the Lorentz transformation associated with the central element $-1\in SL(2,\mathbb C)$. The field representation contributes the spinorial sign $D(-1)$.

Finally, consistency requires the exchange sign to agree with the Lorentz sign. If the signs disagree, positivity and cyclicity force the corresponding field-generated states to have zero norm; after quotienting null vectors, the field is trivial.

A useful slogan is:

$$
\text{local exchange}
\quad + \quad
\text{analytic Lorentz continuation}
\quad + \quad
\text{positive norm}
\quad\Longrightarrow\quad
\text{spin fixes grading}.
$$

## Free-field sanity checks

The theorem is general, but the familiar free fields show why the answer is physically reasonable.

For a real scalar field, imposing canonical commutation relations gives

$$
[\phi(x),\phi(y)]=i\Delta(x-y),
$$

and the Pauli–Jordan distribution $\Delta$ vanishes at spacelike separation. Thus scalar fields are locally bosonic.

For a Dirac field, the local relation is instead

$$
\{\psi_\alpha(x),\overline\psi_\beta(y)\}=S_{\alpha\beta}(x-y),
$$

with the relevant anticommutator vanishing at spacelike separation in the appropriate combinations. Fermionic anticommutation is what gives a positive-energy, positive-norm quantization.

If one quantizes the free scalar field with anticommutators, or the free Dirac field with commutators, pathologies appear: negative norms, energy problems, or a trivial local field. The Wightman theorem says that this is not an accident of free mode expansions. It is forced by locality, covariance, spectrum, and positivity.

## What statistics means here

In this page, "statistics" means the local exchange grading of fields. When a theory has particle states and a scattering interpretation, this field grading leads to the usual Bose or Fermi exchange behavior of multiparticle states. But the theorem itself is formulated at the level of fields and correlation functions, not as a postulate about nonrelativistic many-body wavefunctions.

This distinction matters because QFT has several notions of exchange:

| Setting | Exchange structure |
|---|---|
| Local fields in $3+1$ dimensions | Bose/Fermi grading under spacelike exchange. |
| Nonrelativistic identical particles | Symmetric or antisymmetric wavefunctions, imposed by representation theory of permutations. |
| Two spatial dimensions | Braid statistics and anyons can occur. |
| Algebraic QFT sectors | Statistics can be encoded by superselection categories. |
| Gauge-fixed perturbation theory | Auxiliary ghosts can have wrong spin-statistics because positivity is not physical. |

The spin–statistics theorem is the theorem-level bridge between the first two rows when a relativistic particle interpretation exists.

## Common pitfalls

**Thinking the theorem is only about free fields.** Pauli's original argument was close to free-field reasoning, but Wightman-style spin–statistics theorems apply to interacting fields under axiomatic assumptions.

**Forgetting positivity.** Scalar anticommuting ghosts do not refute the theorem. They are not physical positive-Hilbert-space Wightman fields.

**Confusing spin with Lorentz index count.** The clean invariant statement uses the central sign $D(-1)$ of the Lorentz representation. A vector has Lorentz indices but still has integer spin parity, so it is bosonic.

**Assuming spacelike correlations vanish.** The theorem concerns commutators or anticommutators, not the vanishing of Wightman two-point functions.

**Using the theorem unchanged in two spatial dimensions.** In $2+1$ dimensions, braid-group statistics and anyonic possibilities require a different framework.

**Treating supersymmetry as an exception.** Supersymmetry relates bosonic and fermionic fields, but it does not make a scalar fermionic or a spinor bosonic in the physical local operator algebra.

## Relations to other pages

[Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/) introduces the graded local relation used in the theorem. [Spectral Condition](/rigorous-qft/wightman-axiomatic-qft/spectral-condition/) explains the positive-energy hypothesis behind analyticity. [Wightman Functions](/rigorous-qft/wightman-axiomatic-qft/wightman-functions/) explains how locality and covariance appear as distributional identities.

[Wightman Reconstruction Theorem](/rigorous-qft/wightman-axiomatic-qft/reconstruction-theorem/) explains why positivity of Wightman functions is the same thing as Hilbert-space positivity after reconstruction. The later CPT theorem page will use closely related analytic machinery.

## Research status

**Established theorem.** In the Wightman framework for finite-component local fields in four-dimensional Minkowski spacetime, the spin–statistics connection is a standard theorem.

**Broader frameworks.** Algebraic QFT has spin–statistics theorems formulated in terms of superselection sectors and modular localization. These are deeper than the elementary field statement and are important when fields are not the intrinsic observables.

**Important qualifications.** Gauge fixing, BRST complexes, anyons in two spatial dimensions, nonlocal fields, infinite-component fields, and topological phases all require care. They usually modify at least one hypothesis: positivity, finite-component Lorentz covariance, ordinary spacelike locality, or the topology of exchange.

## Exercises

### Exercise 1: Lorentz parity table

Use

$$
D_{(j,k)}(-1)=(-1)^{2(j+k)}
$$

to determine the local grading of fields transforming as $(0,0)$, $(\frac12,0)$, $(\frac12,\frac12)$, $(1,0)$, and $(1,\frac12)$.

<details><summary><strong>Solution</strong></summary>

Compute $2(j+k)$ modulo $2$.

| Representation | $2(j+k)$ | Central sign | Grading |
|---|---:|---:|---|
| $(0,0)$ | $0$ | $+1$ | bosonic |
| $(\frac12,0)$ | $1$ | $-1$ | fermionic |
| $(\frac12,\frac12)$ | $2$ | $+1$ | bosonic |
| $(1,0)$ | $2$ | $+1$ | bosonic |
| $(1,\frac12)$ | $3$ | $-1$ | fermionic |

The last representation has half-integer spin parity and must be odd in a positive local Wightman theory.

</details>

### Exercise 2: Graded locality for two fields

Let $p_i,p_j\in\{0,1\}$. Show that

$$
\phi_i(f)\phi_j(g)
-
(-1)^{p_i p_j}\phi_j(g)\phi_i(f)=0
$$

is a commutator unless both fields are odd.

<details><summary><strong>Solution</strong></summary>

If at least one of $p_i,p_j$ is $0$, then $p_i p_j=0$, so $(-1)^{p_i p_j}=+1$. The relation is

$$
\phi_i(f)\phi_j(g)-\phi_j(g)\phi_i(f)=0,
$$

which is a commutator.

If both fields are odd, then $p_i=p_j=1$, so $(-1)^{p_i p_j}=-1$. The relation becomes

$$
\phi_i(f)\phi_j(g)+\phi_j(g)\phi_i(f)=0,
$$

which is an anticommutator.

</details>

### Exercise 3: Why ghosts are not counterexamples

Faddeev–Popov ghosts are Lorentz scalar fields but anticommute. Explain why this does not contradict the spin–statistics theorem.

<details><summary><strong>Solution</strong></summary>

The spin–statistics theorem assumes a physical positive Hilbert space of Wightman fields. Faddeev–Popov ghosts are auxiliary fields introduced in gauge fixing. They live in a BRST or indefinite-metric formalism and are not physical scalar fields acting on a positive Hilbert space of observable states.

The theorem can be applied after extracting the physical positive state space and physical local observables. Ghost fields themselves violate the hypotheses, so they are not counterexamples.

</details>

## References

### Standard first pass

- W. Pauli, "The Connection Between Spin and Statistics," *Physical Review* **58** (1940), 716–722. DOI: [10.1103/PhysRev.58.716](https://doi.org/10.1103/PhysRev.58.716).
- G. Lüders and B. Zumino, "Connection between Spin and Statistics," *Physical Review* **110** (1958), 1450–1453. DOI: [10.1103/PhysRev.110.1450](https://doi.org/10.1103/PhysRev.110.1450).
- N. Burgoyne, "On the Connection of Spin with Statistics," *Il Nuovo Cimento* **8** (1958), 607–609. DOI: [10.1007/BF02828775](https://doi.org/10.1007/BF02828775).
- R. F. Streater and A. S. Wightman, *PCT, Spin and Statistics, and All That*, Princeton University Press. DOI: [10.1515/9781400884230](https://doi.org/10.1515/9781400884230).

### Deeper references

- R. Jost, *The General Theory of Quantized Fields*, American Mathematical Society, 1965.
- R. F. Streater, "Local Fields with the Wrong Connection Between Spin and Statistics," *Communications in Mathematical Physics* **5** (1967), 88–96. DOI: [10.1007/BF01646839](https://doi.org/10.1007/BF01646839).
- D. Guido and R. Longo, "An Algebraic Spin and Statistics Theorem," *Communications in Mathematical Physics* **172** (1995), 517–533. DOI: [10.1007/BF02101806](https://doi.org/10.1007/BF02101806).
- I. Duck and E. C. G. Sudarshan, *Pauli and the Spin-Statistics Theorem*, World Scientific, 1997. DOI: [10.1142/3457](https://doi.org/10.1142/3457).

## Version history

- **2026-06-28:** Initial polished draft.
