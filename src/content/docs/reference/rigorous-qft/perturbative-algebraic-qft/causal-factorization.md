---
title: "Causal Factorization"
description: "Explains the causal factorization axiom for time-ordered products and formal S-matrices in perturbative algebraic QFT."
sidebar:
  label: "Causal Factorization"
  order: 6
level: Advanced
status: "Polished draft"
source: "Bogoliubov–Shirkov; Epstein–Glaser; Brunetti–Fredenhagen–Dütsch; Rejzner pAQFT"
topics:
  - causal factorization
  - formal S-matrix
  - time-ordered products
  - perturbative algebraic QFT
canonicalTopics:
  - causal-factorization
  - causal-perturbation-theory
  - perturbative-algebraic-qft
researchStatus:
  established:
    - "Causal factorization is the structural axiom that lets perturbative algebraic QFT build time-ordered products and interacting observables locally from causal order."
  active:
    - "For gauge theories and curved backgrounds, causal factorization must be combined with BV-BRST identities, local covariance, microlocal spectrum conditions, and infrared control."
---

## Summary

Causal factorization is the rule that perturbative QFT should assemble local operations according to causal order. If one interaction is entirely later than another, the formal $S$-matrix for the combined interaction factors as the later piece followed by the earlier piece:

$$
\mathcal S(F+G)
=
\mathcal S(F)\star\mathcal S(G),
\qquad
F\succ G.
$$

Here $\star$ is the product in the free field algebra, and $F\succ G$ means that the support of $F$ is later than the support of $G$ in the causal order. This is the algebraic version of time ordering, but it is stronger than a mnemonic for putting operators in chronological order. It is the axiom that drives Epstein–Glaser induction.

For time-ordered products, the same idea says that if one block of insertions is later than another block, then the higher time-ordered product factors into lower ones:

$$
T_{I\cup J}((F_i)_{i\in I},(F_j)_{j\in J))
=
T_I((F_i)_{i\in I})\star T_J((F_j)_{j\in J}).
$$

The formula is schematic; the precise version includes graded signs for fermions and the condition that all supports in $I$ are later than all supports in $J$. Its power is that it determines time-ordered products away from coincident configurations. The remaining ultraviolet problem is then exactly the extension of distributions to diagonals.

## Prerequisites

Read [Perturbative QFT as Formal Power Series](/rigorous-qft/perturbative-algebraic-qft/perturbative-qft-as-formal-power-series/), [Causal Perturbation Theory](/rigorous-qft/perturbative-algebraic-qft/causal-perturbation-theory/), [Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/time-ordered-products/), and [Extension of Distributions](/rigorous-qft/perturbative-algebraic-qft/extension-of-distributions/). The causal-set language is closest to [Locality and Microcausality](/rigorous-qft/wightman-axiomatic-qft/locality-and-microcausality/) and [Haag–Kastler Axioms](/rigorous-qft/algebraic-qft/haag-kastler-axioms/), but here it is used perturbatively.

## Core idea

Ordinary Dyson perturbation theory begins with a time-ordering symbol. Causal perturbation theory reverses the logic. It asks for multilinear products and formal $S$-matrices whose behavior under causal separation is correct. Once that behavior is imposed, the products are fixed away from the diagonals and renormalization becomes a local extension problem.

Let $M$ be a globally hyperbolic spacetime. For compactly supported functionals $F$ and $G$, write

$$
F\succ G
$$

when no point of $\operatorname{supp}F$ lies in the causal past of a point of $\operatorname{supp}G$. Equivalently, any causal relation between the two supports points from $G$ toward $F$. In a Minkowski chart, this means that $F$ is later than $G$ whenever the two supports are causally comparable.

The causal factorization rule is then

$$
\mathcal S(F+G)
=
\mathcal S(F)\star\mathcal S(G),
\qquad
F\succ G.
$$

For three pieces, the more flexible form is

$$
\mathcal S(F+G+H)
=
\mathcal S(F+G)\star\mathcal S(G)^{-1}
\star\mathcal S(G+H),
\qquad
F\succ H.
$$

This version says that a middle interaction $G$ can overlap causally with both $F$ and $H$, while factorization still separates the parts that are ordered relative to each other.

<figure class="doc-figure" style="--figure-width: 50rem;">

![Causal factorization of formal S-matrices](/figures/rigorous-qft/causal-factorization-supports.svg)

<figcaption>

Causal factorization is the algebraic replacement for informal time ordering. If the support of $F$ is later than the support of $G$, the formal $S$-matrix factors as $\mathcal S(F+G)=\mathcal S(F)\star\mathcal S(G)$. The ultraviolet ambiguity only appears when supports collide or lose a separating causal order.

</figcaption>
</figure>

## Setup and conventions

In pAQFT, the formal $S$-matrix is built from renormalized time-ordered products:

$$
\mathcal S(V)
=
\exp_T\left(\frac{i}{\hbar}V\right)
=
\sum_{n=0}^\infty
\frac{i^n}{\hbar^n n!}
T_n(V^{\otimes n}).
$$

This is a formal power series, not generally a convergent exponential. The product $\star$ is the free algebra product determined by the chosen two-point structure. In flat vacuum language, it is the Wick product corrected by contractions; in curved spacetime, it is defined using a Hadamard two-point function or a suitable bidistribution.

The causal factorization axiom can be imposed either on $\mathcal S$ or on the $T_n$. These formulations are equivalent after expanding in powers of the interaction. The $S$-matrix form is compact; the $T_n$ form is the one used inductively.

For a finite set of labels $N=I\sqcup J$, suppose all supports in $I$ are later than all supports in $J$. Then

$$
T_N((F_k)_{k\in N})
=
T_I((F_i)_{i\in I})\star
T_J((F_j)_{j\in J}),
$$

with the conventional graded signs if fermionic fields are exchanged. This condition is imposed for separated supports. The construction still has to define what happens on the diagonals.

## Why this axiom determines the off-diagonal part

Consider $n$ insertions at pairwise distinct spacetime points. Away from all diagonals, one can cover configuration space by regions where at least one nontrivial causal separation exists. On such a region, causal factorization expresses $T_n$ in terms of lower-order time-ordered products.

For two insertions, the rule is familiar:

$$
T_2(F,G)
=
\begin{cases}
F\star G, & F\succ G,\\
G\star F, & G\succ F.
\end{cases}
$$

When the supports are spacelike separated, both orderings are allowed. Compatibility then requires locality of the free algebra:

$$
F\star G=G\star F
$$

for bosonic local observables with spacelike separated supports, with graded commutation for fermions.

For higher $n$, the same idea works by induction. Causal factorization does not need a global time coordinate. It only needs the causal relation of supports. This is why the method extends naturally to globally hyperbolic curved spacetimes.

## The Epstein–Glaser induction

At order $n$, assume that all $T_k$ for $k<n$ have already been constructed and satisfy the normalization conditions. Causal factorization then determines $T_n$ on the complement of the thin diagonal, and in practice on the complement of the relevant partial diagonals after subdivergences have been handled.

The remaining step is

$$
T_n\big|_{M^n\setminus\Delta_n}
\quad\leadsto\quad
T_n\text{ on }M^n.
$$

This is exactly the extension problem studied in [Extension of Distributions](/rigorous-qft/perturbative-algebraic-qft/extension-of-distributions/). Thus the logic is:

$$
\text{causal factorization}
\Longrightarrow
\text{off-diagonal time-ordered products}
\Longrightarrow
\text{local extension ambiguity}.
$$

This is why causal perturbation theory can avoid divergent intermediate integrals. It never defines the ill-behaved coincident product first and subtracts later. It defines the product where it is already meaningful, then classifies the possible extensions.

## Relative S-matrices and interacting fields

Causal factorization also gives the local construction of interacting observables. Given an interaction $V$, define the relative $S$-matrix

$$
\mathcal S_V(F)
=
\mathcal S(V)^{-1}\star\mathcal S(V+F).
$$

The interacting field associated to $F$ is obtained by the Bogoliubov formula

$$
R_V(F)
=
\left.\frac{\hbar}{i}
\frac{d}{d\lambda}
\mathcal S_V(\lambda F)
\right|_{\lambda=0}.
$$

Since $V$ is usually a spacetime-cutoff interaction, one must know whether changing $V$ far away changes the local observable. Causal factorization is the mechanism behind the answer: changes of the cutoff outside the relevant causal region produce equivalent local algebras. This is the perturbative algebraic replacement for taking a global adiabatic limit too early.

The result is local. One constructs interacting algebras in bounded regions and compares them as the cutoff is varied. Infrared questions are not hidden; they are separated from the ultraviolet construction.

## What causal factorization is not

Causal factorization is close to several familiar ideas, but it is not identical to them.

| Idea | Relation to causal factorization |
|---|---|
| Microcausality | Microcausality says spacelike separated observables graded-commute. Causal factorization uses causal order to assemble time-ordered products. |
| Time ordering | Time ordering is the flat-spacetime mnemonic. Causal factorization is the coordinate-free structural axiom. |
| Cluster decomposition | Cluster decomposition concerns large-separation factorization of correlations. Causal factorization concerns exact algebraic factorization under causal ordering. |
| Unitarity | Formal unitarity imposes relations between time-ordered and anti-time-ordered products. It is a separate normalization condition. |
| Renormalization | Renormalization is the extension freedom left after causal factorization has fixed the off-diagonal products. |

Keeping these distinctions straight prevents many false proofs and false objections.

## Locality from causal factorization

Causal factorization encodes a strong form of locality. Suppose two interactions $V$ and $V'$ agree on a causal neighborhood relevant to an observable $F$. Their relative $S$-matrices may differ globally, but causal factorization constructs canonical identifications between the local interacting algebras they generate.

This is the heart of perturbative algebraic QFT. One does not define a single global interaction Hamiltonian and then hope it avoids Haag-type problems. One defines local interacting observables relative to compactly supported interactions and proves that the local algebra is independent, up to canonical equivalence, of irrelevant cutoff choices.

This local viewpoint also explains why causal factorization is compatible with curved spacetime. The statement only uses causal order and support, not Fourier transforms, vacuum states, or global energy positivity.

## Normalization conditions around causal factorization

Causal factorization is necessary but not the whole definition of time-ordered products. A useful system of $T_n$ also satisfies additional conditions, such as:

| Condition | Role |
|---|---|
| Symmetry | Permuting entries gives the same product, with graded signs for fermions. |
| Starting point | $T_0=1$ and $T_1(F)=F$ for the chosen Wick polynomial or local functional. |
| Causal factorization | Ordered separated supports factor into lower products. |
| Unitarity | The formal $S$-matrix has the expected inverse/adjoint relation. |
| Field independence | Functional differentiation interacts correctly with $T$. |
| Poincaré or local covariance | Products transform correctly under spacetime embeddings. |
| Scaling bounds | Short-distance behavior is controlled by power counting. |
| Ward or master identities | Symmetry and gauge identities are maintained when possible. |

The extension step must preserve these conditions. When they conflict, the obstruction is often interpreted as an anomaly.

## Common pitfalls

**Replacing causal order by a chosen time coordinate.** In Minkowski space, global time ordering is a useful shortcut. In curved spacetime and local algebraic formulations, the correct notion is causal order of supports.

**Assuming causal factorization defines coincident products.** It defines products away from the dangerous diagonals. Coincident configurations still require distribution extension and normalization choices.

**Confusing factorization with commutativity.** For timelike ordered supports, factorization fixes an order in the algebra. For spacelike separated supports, compatibility with locality gives graded commutativity for local observables.

**Treating the formal inverse as analytic.** The inverse $\mathcal S(V)^{-1}$ is a formal inverse in a power-series algebra. It does not assert convergence or a genuine unitary operator at finite coupling.

**Ignoring infrared cutoffs.** Causal factorization controls locality of compactly supported interactions. Removing cutoffs globally is a separate infrared question.

## Relations to other pages

[Causal Perturbation Theory](/rigorous-qft/perturbative-algebraic-qft/causal-perturbation-theory/) introduces the Epstein–Glaser construction using this axiom. [Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/time-ordered-products/) describes the multilinear maps whose factorization is required. [Extension of Distributions](/rigorous-qft/perturbative-algebraic-qft/extension-of-distributions/) explains the ultraviolet step left after causal factorization fixes the separated-point answer.

[Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/) and [Haag–Kastler Axioms](/rigorous-qft/algebraic-qft/haag-kastler-axioms/) provide the nonperturbative algebraic locality background. [Time-Slice Axiom](/rigorous-qft/locally-covariant-qft/time-slice-axiom/) explains the related idea that Cauchy data determine local dynamics. The later page on interacting fields as formal series will use relative $S$-matrices to define interacting observables.

## Research status

Causal factorization is a settled structural principle in causal perturbation theory and pAQFT. Together with scaling bounds and locality/covariance requirements, it gives a rigorous perturbative construction of interacting fields and local algebras as formal power series.

The frontier is not whether causal factorization is the right perturbative locality axiom. The harder questions are compatibility with gauge symmetry, classification of anomalies, control of the adiabatic limit, construction of states for interacting algebras, and nonperturbative completion. These lie at the interface with BV-BRST, locally covariant QFT, and constructive QFT.

## Exercises

### Exercise 1: Two ordered supports

Let $F\succ G$. Expand the formal relation

$$
\mathcal S(F+G)=\mathcal S(F)\star\mathcal S(G)
$$

to second order and identify the corresponding condition on $T_2(F,G)$.

<details><summary><strong>Solution</strong></summary>

Using

$$
\mathcal S(F)=1+\frac{i}{\hbar}F
+\frac{1}{2}\left(\frac{i}{\hbar}\right)^2T_2(F,F)+\cdots,
$$

and the same for $G$, the mixed second-order term on the left is

$$
\left(\frac{i}{\hbar}\right)^2T_2(F,G).
$$

The mixed term on the right is

$$
\left(\frac{i}{\hbar}F\right)\star
\left(\frac{i}{\hbar}G\right)
=
\left(\frac{i}{\hbar}\right)^2F\star G.
$$

Therefore causal factorization implies $T_2(F,G)=F\star G$ when $F\succ G$.

</details>

### Exercise 2: Spacelike compatibility

Suppose $F$ and $G$ have spacelike separated supports. Why does causal factorization require compatibility with locality?

<details><summary><strong>Solution</strong></summary>

For spacelike separated supports, neither support is causally earlier than the other. Both orderings are admissible in the sense that no causal relation distinguishes them. Causal factorization would allow $T_2(F,G)=F\star G$ and also $T_2(F,G)=G\star F$. These are compatible only if local observables graded-commute at spacelike separation.

</details>

### Exercise 3: Why the diagonal remains

Why does causal factorization not solve the ultraviolet problem by itself?

<details><summary><strong>Solution</strong></summary>

Causal factorization expresses time-ordered products in terms of lower-order products when the supports are causally separated. At coincident points, there is no open causal separation that avoids singular products of distributions. The off-diagonal answer must still be extended to the diagonal, and that extension is the renormalization step.

</details>

### Exercise 4: Relative S-matrix as a formal object

Why is $\mathcal S(V)^{-1}$ in

$$
\mathcal S_V(F)=\mathcal S(V)^{-1}\star\mathcal S(V+F)
$$

not an analytic inverse of an operator at finite coupling?

<details><summary><strong>Solution</strong></summary>

The formal $S$-matrix is an element of a formal power-series algebra. Its constant term is $1$, so it has a unique formal inverse constructed order by order. This does not imply convergence of the series or the existence of a unitary operator for a nonzero numerical coupling.

</details>

## References

- N. N. Bogoliubov and D. V. Shirkov, *Introduction to the Theory of Quantized Fields*, Wiley, 1959; later editions by Interscience/Wiley.
- H. Epstein and V. Glaser, “The Role of Locality in Perturbation Theory,” *Annales de l'Institut Henri Poincaré A* **19** (1973), 211–295. [Numdam](https://numdam.org/item/AIHPA_1973__19_3_211_0/).
- R. Brunetti and K. Fredenhagen, “Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds,” *Communications in Mathematical Physics* **208** (2000), 623–661. [arXiv:math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), [doi:10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- M. Dütsch and K. Fredenhagen, “Causal Perturbation Theory in Terms of Retarded Products, and a Proof of the Action Ward Identity,” *Reviews in Mathematical Physics* **16** (2004), 1291–1348. [arXiv:hep-th/0403213](https://arxiv.org/abs/hep-th/0403213), [doi:10.1142/S0129055X04002266](https://doi.org/10.1142/S0129055X04002266).
- R. Brunetti, M. Dütsch, and K. Fredenhagen, “Perturbative Algebraic Quantum Field Theory and the Renormalization Groups,” *Advances in Theoretical and Mathematical Physics* **13** (2009), 1541–1599. [arXiv:0901.2038](https://arxiv.org/abs/0901.2038), [doi:10.4310/ATMP.2009.v13.n5.a7](https://doi.org/10.4310/ATMP.2009.v13.n5.a7).
- K. Fredenhagen and K. Rejzner, “Perturbative Algebraic Quantum Field Theory,” in *Mathematical Aspects of Quantum Field Theories* (2015). [arXiv:1208.1428](https://arxiv.org/abs/1208.1428).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory: An Introduction for Mathematicians*, Springer, 2016. [doi:10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).

## Version history

- **2026-07-01:** First polished draft.
