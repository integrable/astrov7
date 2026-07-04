---
title: "Verlinde Formula Preview"
description: "How modular S data determine fusion coefficients in semisimple rational conformal field theory, with Ising and minimal-model examples."
sidebar:
  label: "Verlinde Formula"
  order: 10
level: Graduate
status: "Polished draft"
source: "Verlinde 1988; Moore and Seiberg; Di Francesco, Mathieu, and Senechal ch. 10; standard rational CFT literature."
topics:
  - Verlinde formula
  - rational CFT
  - fusion rules
  - modular data
  - characters
canonicalTopics:
  - verlinde-formula
  - modular-s-matrix
  - rational-cft-fusion
researchStatus:
  established:
    - "For semisimple rational CFTs, the Verlinde formula computes fusion coefficients from the modular S matrix of chiral characters."
  active:
    - "Logarithmic, nonsemisimple, spin, and defect-enriched theories require refined versions of the rational-CFT story."
---

## Summary

The **Verlinde formula** is the statement that, in a semisimple rational CFT, the fusion coefficients are determined by the modular $S$ matrix of chiral characters:

$$
N_{ij}{}^k
=\sum_\ell
\frac{S_{i\ell}S_{j\ell}S^*_{k\ell}}{S_{0\ell}}.
$$

Here $0$ denotes the vacuum representation, $i,j,k,\ell$ label irreducible chiral representations, and

$$
\chi_i(-1/\tau)=\sum_j S_{ij}\chi_j(\tau)
$$

is the modular $S$ transformation of characters.

The formula is striking because it relates two different geometries. Fusion is local operator algebra on the sphere. The $S$ matrix comes from changing cycles on the torus. The Verlinde formula says that, in rational CFT, these two kinds of consistency know about each other.

This page is a preview: it states the formula, explains how to use it, gives checks in the Ising model, and records the assumptions under which the statement is safe. A later theorem-first page can discuss modular tensor categories and the full Moore–Seiberg consistency equations.

## Prerequisites

Read [Rational CFT](/cft-bootstrap/minimal-models-rational-cft/rational-cft/), [Fusion Rules](/cft-bootstrap/minimal-models-rational-cft/fusion-rules/), [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), and [Modular Invariance](/cft-bootstrap/minimal-models-rational-cft/modular-invariance/) first.

You should know that a rational CFT has finitely many irreducible chiral representations with characters $\chi_i(\tau)$, and that their modular $S$ transformation is a finite matrix.

## Core idea

Fusion rules define matrices

$$
(N_i)_j{}^k=N_{ij}{}^k.
$$

The Verlinde formula says that all these fusion matrices are diagonalized by the same modular $S$ matrix. Equivalently,

$$
N_i=S D_i S^{-1},
$$

where $D_i$ is diagonal with entries

$$
(D_i)_\ell{}^\ell=\frac{S_{i\ell}}{S_{0\ell}}.
$$

Multiplying the matrices and reading off components gives

$$
N_{ij}{}^k
=\sum_\ell
\frac{S_{i\ell}S_{j\ell}S^*_{k\ell}}{S_{0\ell}}.
$$

The slogan is

$$
\text{modular }S\text{ matrix}
\quad\Longrightarrow\quad
\text{simultaneous diagonalization of fusion}
\quad\Longrightarrow\quad
\text{fusion coefficients}.
$$

## Setup and conventions

Let $\mathcal A$ be the chosen chiral algebra. Its irreducible representations are denoted

$$
\mathcal V_i,
\qquad i=0,1,\ldots,n-1,
$$

with $0$ the vacuum representation. The character is

$$
\chi_i(\tau)=\operatorname{Tr}_{\mathcal V_i}q^{L_0-c/24},
\qquad
q=e^{2\pi i\tau}.
$$

Assume the characters transform as

$$
\chi_i(-1/\tau)=\sum_j S_{ij}\chi_j(\tau),
$$

with $S$ unitary. The fusion product is

$$
\mathcal V_i\times\mathcal V_j
=\sum_k N_{ij}{}^k\mathcal V_k.
$$

Under the standard semisimple rational-CFT assumptions, the Verlinde formula computes the nonnegative integers $N_{ij}{}^k$ from $S$.

## Why it is plausible

The formula is not obvious from the definitions. A useful way to remember it is through torus one-point conformal blocks. Inserting a line or representation label $i$ along one torus cycle acts on the space of states. Changing the basis of cycles by the modular $S$ transformation diagonalizes that action.

This is why the eigenvalues of fusion by $i$ are

$$
\frac{S_{i\ell}}{S_{0\ell}}.
$$

The denominator appears because the vacuum representation supplies the normalization of the state associated with the cycle. This is also why quantum dimensions are

$$
d_i=\frac{S_{i0}}{S_{00}}.
$$

The full derivation belongs to the Moore–Seiberg consistency framework, where fusing and braiding moves of conformal blocks satisfy compatibility equations. The preview-level point is enough for calculations: once $S$ is known, fusion follows.

## Ising example

For the Ising CFT, use the basis

$$
(\mathbf 1,\epsilon,\sigma).
$$

The modular $S$ matrix is

$$
S=\frac12
\begin{pmatrix}
1&1&\sqrt2\\
1&1&-\sqrt2\\
\sqrt2&-\sqrt2&0
\end{pmatrix}.
$$

The quantum dimensions are

$$
d_i=\frac{S_{i0}}{S_{00}},
$$

so

$$
d_{\mathbf 1}=1,
\qquad
d_\epsilon=1,
\qquad
d_\sigma=\sqrt2.
$$

The field $\epsilon$ is a simple current because $d_\epsilon=1$. The field $\sigma$ is not: its quantum dimension is larger than one, and its self-fusion branches.

Using the Verlinde formula gives

$$
\epsilon\times\epsilon=\mathbf 1,
\qquad
\epsilon\times\sigma=\sigma,
\qquad
\sigma\times\sigma=\mathbf 1+\epsilon.
$$

The last rule is the classic Ising fusion rule. Here it follows from modular transformations of characters, not from a lattice argument.

## Minimal-model S matrix

For Virasoro minimal models $\mathcal M(p,p')$, the primary labels are

$$
(r,s),
\qquad
1\le r\le p-1,
\qquad
1\le s\le p'-1,
$$

with

$$
(r,s)\sim(p-r,p'-s).
$$

There is an explicit modular $S$ matrix for the minimal-model characters. Its exact sign convention varies with the chosen representative labels and character phases, but it has the schematic form

$$
S_{(r,s),(r',s')}
\propto
\sin\left(\frac{\pi p'rr'}{p}\right)
\sin\left(\frac{\pi pss'}{p'}\right)
$$

up to a conventional sign and normalization.

Applying the Verlinde formula to this matrix reproduces the minimal-model fusion rule:

$$
(r,s)\times(r',s')
=\sum_{r''}\sum_{s''}(r'',s''),
$$

where $r''$ and $s''$ run through the truncated step-two ranges described in [Fusion Rules](/cft-bootstrap/minimal-models-rational-cft/fusion-rules/).

This is an important check: the same finite fusion algebra can be obtained from BPZ null-vector methods or from modular data.

## Diagonalizing fusion

The Verlinde formula implies that the columns of $S$ are simultaneous eigenvectors of all fusion matrices. More explicitly,

$$
N_i S_{\cdot\ell}
=\frac{S_{i\ell}}{S_{0\ell}}S_{\cdot\ell}.
$$

Here $S_{\cdot\ell}$ denotes the $\ell$th column of $S$. This equation is often the cleanest computational form.

For the Ising spin field, the fusion matrix is

$$
N_\sigma=
\begin{pmatrix}
0&0&1\\
0&0&1\\
1&1&0
\end{pmatrix}
$$

in the basis $(\mathbf 1,\epsilon,\sigma)$ if columns label the object being fused. Its eigenvalues are

$$
\sqrt2,\quad -\sqrt2,\quad 0,
$$

matching

$$
\frac{S_{\sigma\ell}}{S_{0\ell}}.
$$

This simultaneous diagonalization is one of the reasons rational CFT feels finite-dimensional despite having infinitely many descendant states.

## Assumptions and caveats

The standard Verlinde formula assumes a semisimple rational CFT. In practice, this means the category of chiral representations behaves like a finite semisimple tensor category with good modular data.

Important caveats:

| Setting | What changes |
|---|---|
| Logarithmic CFT | Modules can be indecomposable, and fusion need not be semisimple. |
| Nonunitary RCFT | The formula can still work, but positivity interpretations require care. |
| Fermionic or spin CFT | Modular transformations act on spin-structure sectors, not one bosonic partition function. |
| Extended chiral algebras | Rationality and fusion depend on the chosen algebra. |
| Non-diagonal modular invariants | Chiral fusion data do not by themselves determine the full left-right local spectrum. |

So the safe statement is not “all CFT fusion is determined by an $S$ matrix.” The safe statement is: in semisimple rational CFT, the modular $S$ matrix of irreducible characters determines the chiral fusion coefficients by the Verlinde formula.

## What the formula does not determine

The Verlinde formula determines fusion coefficients, not all CFT data.

It does not by itself determine:

| Missing data | Why it matters |
|---|---|
| OPE coefficients | Fusion says which channels exist, not their normalized coefficients. |
| Fusing matrices | Crossing needs associativity isomorphisms, not only channel counts. |
| Braiding phases | Locality and monodromy require braiding data. |
| Modular invariant $M_{ij}$ | A full local theory needs left-right pairing. |
| Correlator normalizations | Full local correlators need more than characters and fusion. |

The formula is therefore powerful but not magic. It is a central piece of rational CFT, not the entire theory.

## Common pitfalls

**Do not confuse $S$ in the Verlinde formula with the spacetime S-matrix.** The modular $S$ matrix acts on torus characters. It is unrelated to scattering amplitudes.

**Do not confuse fusion coefficients with OPE coefficients.** $N_{ij}{}^k$ is an integer. $C_{ij}{}^k$ is a normalization-dependent CFT datum.

**Do not forget the vacuum denominator.** The factor $S_{0\ell}$ is essential. Dropping it gives nonsense dimensions and usually non-integers.

**Do not apply the semisimple formula blindly to logarithmic CFT.** Nonsemisimple theories require refined character and pseudo-character technology.

**Do not assume a diagonal local theory.** Verlinde computes chiral fusion. The full local CFT still needs a modular invariant.

## Relations to other pages

This page completes the first pass through [Minimal Models and Rational CFT](/cft-bootstrap/minimal-models-rational-cft/). It depends directly on [Fusion Rules](/cft-bootstrap/minimal-models-rational-cft/fusion-rules/), [Characters](/cft-bootstrap/minimal-models-rational-cft/characters/), and [Modular Invariance](/cft-bootstrap/minimal-models-rational-cft/modular-invariance/).

The formula also prepares the Current Algebras and WZW Models chapter, where affine characters and modular data are central. Later boundary-CFT pages use the same $S$ matrix in Cardy’s construction of boundary states.

## Research status

The Verlinde formula is established in ordinary semisimple rational CFT and is one of the structural pillars of the subject. Its mathematical formulation is tied to modular tensor categories, vertex operator algebras, and the Moore–Seiberg consistency equations.

Active research extends the surrounding ideas to logarithmic CFT, nonsemisimple categories, fermionic phases, non-invertible symmetries, categorical defects, generalized orbifolds, and topological phases.

## Exercises

### Exercise 1

Use the Ising $S$ matrix to compute the quantum dimension of $\sigma$.

<details><summary><strong>Solution</strong></summary>

In the basis $(\mathbf 1,\epsilon,\sigma)$,

$$
S_{00}=\frac12,
\qquad
S_{\sigma0}=\frac{\sqrt2}{2}.
$$

Therefore

$$
d_\sigma=\frac{S_{\sigma0}}{S_{00}}=\sqrt2.
$$

</details>

### Exercise 2

Explain why $d_i=1$ suggests simple-current behavior in a unitary rational CFT.

<details><summary><strong>Solution</strong></summary>

The quantum dimension behaves multiplicatively under fusion:

$$
d_i d_j=\sum_k N_{ij}{}^k d_k.
$$

If $d_i=1$ and the theory is unitary, the right-hand side can only remain one term of total quantum dimension $d_j$ when fusion by $i$ permutes simple objects. Such an object is called a simple current.

This is an intuition, not a replacement for checking the actual fusion matrix.

</details>

### Exercise 3

What does the Verlinde formula determine, and what does it not determine?

<details><summary><strong>Solution</strong></summary>

It determines the fusion coefficients

$$
N_{ij}{}^k.
$$

These specify which chiral representation families can appear in fusion and with what multiplicity. The formula does not determine normalized OPE coefficients, fusing matrices, braiding matrices, or the modular invariant of a full local CFT. Those are additional data and consistency conditions.

</details>

## References

- E. Verlinde, “Fusion rules and modular transformations in 2D conformal field theory,” *Nuclear Physics B* **300** (1988).
- G. Moore and N. Seiberg, “Classical and quantum conformal field theory,” *Communications in Mathematical Physics* **123** (1989).
- P. Di Francesco, P. Mathieu, and D. Senechal, *Conformal Field Theory*, Springer, 1997.
- G. Segal, “The definition of conformal field theory,” in *Topology, Geometry and Quantum Field Theory*, Cambridge University Press.
- Y.-Z. Huang, *Two-Dimensional Conformal Geometry and Vertex Operator Algebras*, Birkhauser, 1997.

## Version history

- 2026-06-30: First polished draft. Added Verlinde formula statement, Ising check, minimal-model interpretation, assumptions, caveats, exercises, and references.
