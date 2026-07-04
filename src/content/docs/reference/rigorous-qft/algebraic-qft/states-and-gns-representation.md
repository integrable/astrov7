---
title: "States and GNS Representation"
description: "Explain algebraic states, the GNS construction, and how expectation values produce Hilbert-space representations of a local net."
sidebar:
  label: "States and GNS"
  order: 5
level: Graduate
status: "Polished draft"
source: "C*-algebraic states and GNS theorem; Haag, Local Quantum Physics; Araki, Mathematical Theory of Quantum Fields; Fewster–Rejzner AQFT introduction."
topics:
  - algebraic QFT
  - states
  - GNS representation
canonicalTopics:
  - algebraic-states
  - gns-representation
  - cyclic-representations
researchStatus:
  established:
    - "The GNS theorem is the standard bridge from abstract C*-algebras and states to cyclic Hilbert-space representations."
  active:
    - "In QFT, deciding which representations are physically admissible depends on locality, spectrum, phase, and sector selection criteria."
---

## Summary

In algebraic QFT a **state** is not first a vector in a pre-existing Hilbert space. It is an expectation-value functional on the algebra of observables. For a unital $C^*$-algebra $\mathcal A$, a state is a linear functional

$$
\omega:\mathcal A\to\mathbb C
$$

such that

$$
\omega(\mathbf 1)=1,
\qquad
\omega(A^*A)\ge 0
\quad (A\in\mathcal A).
$$

The **Gelfand–Naimark–Segal construction**, usually abbreviated **GNS**, says that every such state can be represented as a vector state in a canonical cyclic representation:

$$
\omega(A)=
\langle \Omega_\omega,
\pi_\omega(A)\Omega_\omega\rangle.
$$

Thus a choice of state produces a Hilbert space $\mathcal H_\omega$, a representation $\pi_\omega$ of the algebra by bounded operators, and a cyclic vector $\Omega_\omega$. In a local net, this turns the abstract algebras $\mathcal A(\mathcal O)$ into concrete local operator algebras

$$
\mathcal M_\omega(\mathcal O)
=\pi_\omega(\mathcal A(\mathcal O))''.
$$

The conceptual lesson is central to algebraic QFT: **the Hilbert space belongs to a representation, not to the bare observable algebra by itself**. Vacuum states, thermal states, charged sectors, and infinite-volume phases can lead to inequivalent representations.

<figure class="doc-figure" style="--figure-width: 44rem;">

![A flowchart of the GNS construction from a C-star algebra and a state through the null ideal, quotient, completion, representation, cyclic vector, and expectation values.](/figures/rigorous-qft/gns-quotient-construction.svg)

<figcaption>

The GNS construction turns a positive normalized expectation-value functional into a cyclic Hilbert-space representation. The quotient by $\mathcal N_\omega$ removes vectors of zero norm before completion.

</figcaption>
</figure>

## Prerequisites

You should know [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/), [Haag–Kastler Axioms](/rigorous-qft/algebraic-qft/haag-kastler-axioms/), and [Vacuum Representations](/rigorous-qft/algebraic-qft/vacuum-representations/). The Wightman pages [Hilbert Space and Fields](/rigorous-qft/wightman-axiomatic-qft/hilbert-space-and-fields/) and [Vacuum and Cyclicity](/rigorous-qft/wightman-axiomatic-qft/vacuum-and-cyclicity/) give the corresponding field-based viewpoint.

## Core idea

The usual Hilbert-space formulation of quantum theory starts with a Hilbert space $\mathcal H$ and represents observables as operators on it. A state is then a vector, density matrix, or more general positive normal functional. This is perfect for finite systems and for many calculations, but it hides a major feature of QFT: an infinite system may have many physically meaningful Hilbert-space representations that are not unitarily equivalent.

Algebraic QFT separates three layers that are often mixed together:

| Layer | Mathematical object | Physical role |
|---|---|---|
| Observable content | $C^*$-algebra $\mathcal A$ and local subalgebras $\mathcal A(\mathcal O)$ | Which measurements exist, and where they are localized. |
| State | Positive normalized functional $\omega$ | Expectation values and correlation data. |
| Representation | $(\mathcal H_\omega,\pi_\omega,\Omega_\omega)$ | A Hilbert-space realization adapted to that state. |

The GNS construction is the theorem that joins the second and third layers. It says that any abstract state can be realized by a vector in a Hilbert space, but the Hilbert space depends on the state.

This distinction is not pedantry. The vacuum representation is the representation selected by a translation-invariant positive-energy vacuum state. A thermal representation is selected by a KMS state. A charged representation is selected by a state or sector carrying charge. In infinite-volume QFT these representations can be inequivalent, so there is no single Hilbert space that automatically contains every physically relevant situation as a vector.

## Setup and conventions

Let $\mathcal A$ be a unital $C^*$-algebra. The involution is written $A\mapsto A^*$, the norm is $\|A\|$, and the unit is $\mathbf 1$. In a local net, $\mathcal A$ is usually the **quasi-local algebra**, obtained as the norm closure of the algebra generated by all local algebras $\mathcal A(\mathcal O)$.

A representation of $\mathcal A$ on a Hilbert space $\mathcal H$ is a $*$-homomorphism

$$
\pi:\mathcal A\to B(\mathcal H).
$$

For a unital algebra, representations are usually taken to be unital:

$$
\pi(\mathbf 1)=I_{\mathcal H}.
$$

A vector $\Omega\in\mathcal H$ is cyclic for $\pi$ if

$$
\overline{\pi(\mathcal A)\Omega}=\mathcal H.
$$

Cyclicity says that the whole representation space is generated by applying observables to the chosen vector. In a local QFT vacuum representation, cyclicity of the vacuum for suitable local algebras is much stronger and becomes the Reeh–Schlieder property. Here we only need the basic algebraic notion.

## States as expectation-value functionals

A state $\omega$ on a unital $C^*$-algebra $\mathcal A$ is a linear functional satisfying

$$
\omega(\mathbf 1)=1,
\qquad
\omega(A^*A)\ge 0.
$$

From positivity one gets the Cauchy–Schwarz inequality

$$
|\omega(A^*B)|^2
\le
\omega(A^*A)\,\omega(B^*B),
$$

and in particular $\omega(A^*)=\overline{\omega(A)}$. Positivity is therefore the algebraic replacement for nonnegative probabilities and squared norms.

A few important kinds of states are worth separating.

| Kind of state | Meaning |
|---|---|
| Vector state | In a given representation, $\omega(A)=\langle\Psi,\pi(A)\Psi\rangle$ for a unit vector $\Psi$. |
| Normal state | In a von Neumann algebra representation, a state continuous in the appropriate ultraweak topology; on $B(\mathcal H)$ it is given by a density matrix. |
| Pure state | An extreme point of the convex set of states; it cannot be written as a nontrivial convex mixture of states. |
| Mixed state | A non-extreme state; operationally, it behaves like a probabilistic mixture of other states. |
| Factor state | A state whose GNS von Neumann algebra has trivial center. |

The last entry is especially important in QFT. Pure states are not always the most useful classification tool for infinite systems. Factor representations, primary states, and sectors often carry more stable physical information.

## The GNS theorem

**Theorem (GNS construction).** Let $\mathcal A$ be a unital $C^*$-algebra and let $\omega$ be a state on $\mathcal A$. Then there exists a Hilbert space $\mathcal H_\omega$, a representation $\pi_\omega:\mathcal A\to B(\mathcal H_\omega)$, and a cyclic unit vector $\Omega_\omega\in\mathcal H_\omega$ such that

$$
\omega(A)=
\langle \Omega_\omega,
\pi_\omega(A)\Omega_\omega\rangle
\qquad (A\in\mathcal A).
$$

The triple $(\mathcal H_\omega,\pi_\omega,\Omega_\omega)$ is unique up to unitary equivalence: if another cyclic triple has the same expectation values, there is a unitary map intertwining the two representations and sending one cyclic vector to the other.

The construction is explicit. Define the null space

$$
\mathcal N_\omega
=\{A\in\mathcal A:\omega(A^*A)=0\}.
$$

By Cauchy–Schwarz, $\mathcal N_\omega$ is a left ideal. Form the quotient vector space

$$
\mathcal D_\omega=\mathcal A/\mathcal N_\omega,
$$

and write the class of $A$ as $[A]$. Define

$$
\langle[A],[B]\rangle_\omega
=\omega(A^*B).
$$

This is well-defined and positive definite on the quotient. Complete $\mathcal D_\omega$ in this norm to obtain $\mathcal H_\omega$.

The representation is left multiplication:

$$
\pi_\omega(C)[A]=[CA].
$$

The cyclic vector is

$$
\Omega_\omega=[\mathbf 1].
$$

Then

$$
\langle\Omega_\omega,
\pi_\omega(A)\Omega_\omega\rangle
=\langle[\mathbf 1],[A]\rangle_\omega
=\omega(A).
$$

This proof also explains why the quotient is necessary. The expression $\omega(A^*A)$ may vanish for nonzero $A$, so $A$ must represent the zero vector in the Hilbert space associated with $\omega$.

## How local nets enter

Let

$$
\mathcal O\longmapsto\mathcal A(\mathcal O)
$$

be a Haag–Kastler net, and let $\mathcal A$ be its quasi-local $C^*$-algebra. A state $\omega$ on $\mathcal A$ restricts to each local algebra:

$$
\omega_\mathcal O
=\omega|_{\mathcal A(\mathcal O)}.
$$

The GNS representation gives concrete local algebras on $\mathcal H_\omega$:

$$
\pi_\omega(\mathcal A(\mathcal O))\subset B(\mathcal H_\omega).
$$

Because many local questions in QFT are naturally von Neumann algebraic, one then takes the double commutant

$$
\mathcal M_\omega(\mathcal O)
=\pi_\omega(\mathcal A(\mathcal O))''.
$$

This passage preserves the localization structure in the representation. For instance, if the abstract net is isotonic, then

$$
\mathcal O_1\subset\mathcal O_2
\quad\Longrightarrow\quad
\mathcal M_\omega(\mathcal O_1)
\subset
\mathcal M_\omega(\mathcal O_2).
$$

If the abstract net is local, then spacelike separated represented local algebras commute. In this way, the abstract local net becomes a concrete local net of von Neumann algebras in the chosen state representation.

## Implementing symmetries from invariant states

Suppose a group $G$ acts on $\mathcal A$ by automorphisms

$$
\alpha_g:\mathcal A\to\mathcal A.
$$

If the state is invariant,

$$
\omega(\alpha_g(A))=\omega(A),
$$

then $G$ is unitarily implemented in the GNS representation. On the dense subspace $\mathcal D_\omega$ define

$$
U_\omega(g)[A]=[\alpha_g(A)].
$$

This is isometric because

$$
\begin{aligned}
\langle[\alpha_g(A)],[\alpha_g(B)]\rangle_\omega
&=\omega(\alpha_g(A)^*\alpha_g(B))\\
&=\omega(\alpha_g(A^*B))\\
&=\omega(A^*B).
\end{aligned}
$$

So $U_\omega(g)$ extends to a unitary operator on $\mathcal H_\omega$, and

$$
U_\omega(g)\pi_\omega(A)U_\omega(g)^{-1}
=\pi_\omega(\alpha_g(A)).
$$

The cyclic vector is fixed:

$$
U_\omega(g)\Omega_\omega=\Omega_\omega.
$$

For Minkowski spacetime, this is how translation or Poincaré invariance of a vacuum state becomes unitary covariance of the vacuum representation. The spectral condition is not automatic from GNS; it is an additional positivity condition on the translation generators.

## Pure, irreducible, factor, and faithful representations

Several common words become precise in the GNS language.

A representation $\pi$ is **irreducible** if the only closed subspaces invariant under all $\pi(A)$ are $0$ and $\mathcal H$. Equivalently, its commutant is trivial:

$$
\pi(\mathcal A)'=\mathbb C I.
$$

For a $C^*$-algebra, a state is pure if and only if its GNS representation is irreducible.

A representation is a **factor representation** if

$$
\pi(\mathcal A)''\cap \pi(\mathcal A)'=\mathbb C I.
$$

The algebra $\pi(\mathcal A)''$ then has trivial center and is called a factor. In infinite systems, factor representations are often the right analog of thermodynamic phases or sectors, even when the state is not pure.

A representation is **faithful** if $\pi(A)=0$ implies $A=0$. GNS representations need not be faithful. If the state cannot detect some ideal of the algebra, that ideal is represented as zero. This is not a bug; it records which observables are operationally distinguishable in the state.

## Local density matrices and type III warnings

In finite-dimensional quantum mechanics, a state on $B(\mathcal H)$ is represented by a density matrix $\rho$:

$$
\omega(A)=\operatorname{Tr}(\rho A).
$$

This intuition is useful but dangerous in continuum QFT. Local von Neumann algebras in relativistic QFT are typically type III factors under standard phase-space and locality assumptions. Such algebras do not have a trace analogous to the matrix trace, and a local restriction of the vacuum should not be naively treated as a density matrix living inside the local algebra.

This is one reason entanglement in continuum QFT is subtle. The slogan “trace out the outside region” is often useful after introducing a cutoff or in special factorizable models, but the intrinsic algebraic object is a state restricted to a local algebra:

$$
\omega|_{\mathcal M(\mathcal O)}.
$$

The distinction matters for modular theory, the split property, local entropy, and gauge-theory edge-mode discussions.

## A useful dictionary

| Hilbert-space language | Algebraic language |
|---|---|
| Choose a Hilbert space first. | Choose an observable algebra and then a state. |
| State vector $\Psi$. | State functional $\omega(A)$. |
| Observables act on one fixed $\mathcal H$. | Each state gives a representation $\pi_\omega$. |
| Vacuum vector is assumed. | Vacuum state is a selected invariant positive-energy state. |
| Mixed state is a density matrix. | Mixed state is a non-extreme positive normalized functional. |
| Superselection often appears as block diagonal operators. | Sectors are inequivalent representations or localized endomorphisms. |

The two languages agree when a representation has already been chosen. The algebraic language is more flexible because it remembers that the representation itself is part of the physical data.

## Common pitfalls

**A state is not automatically a vector.** A state becomes a vector only after a representation has been constructed or chosen. The GNS vector $\Omega_\omega$ is canonical for the state, but it lives in $\mathcal H_\omega$, not in a universal Hilbert space shared by all states.

**GNS does not select the physical state.** The theorem works for every algebraic state. Additional physics is needed to identify vacuum states, thermal states, charged states, or Hadamard states.

**Unitary covariance requires invariance.** If $\omega$ is invariant under an automorphism group, the group is implemented by unitaries in the GNS representation. Without invariance, the automorphism may carry the GNS representation of $\omega$ to an inequivalent representation.

**A local state is not always a density matrix.** Density matrices are reliable for finite systems and for normal states on $B(\mathcal H)$. Local algebras in continuum QFT require the von Neumann algebraic language of normal states, modular theory, and often type III factors.

**Pure does not mean locally pure.** Even if the global vacuum state is pure on the quasi-local algebra, its restriction to a local algebra is highly mixed in the operational sense.

## Relations to other pages

[Vacuum Representations](/rigorous-qft/algebraic-qft/vacuum-representations/) uses the GNS construction for the special case of vacuum states. [Superselection Sectors](/rigorous-qft/algebraic-qft/superselection-sectors/) explains why inequivalent representations carry charge and sector data. Modular Theory and Tomita–Takesaki will use the pair $(\mathcal M,\Omega)$ produced by a representation to define modular conjugations and modular flows.

The Wightman page [Reconstruction Theorem](/rigorous-qft/wightman-axiomatic-qft/reconstruction-theorem/) is philosophically parallel: there, correlation functions reconstruct a Hilbert space and fields; here, a state on an algebra reconstructs a Hilbert space and representation.

## Research status

The GNS theorem itself is standard functional analysis. Its role in algebraic QFT is settled and foundational.

The research-sensitive part is not the theorem but the **choice and classification of physically relevant states and representations**. Vacuum selection, thermal KMS states, charged sectors, scaling-limit states, Hadamard states on curved spacetimes, and gauge-theory representations all require additional criteria. In this sense, GNS is the door from algebra to Hilbert space, but physics decides which doors matter.

## Exercises

### Exercise 1

Let $\omega$ be a state on a unital $C^*$-algebra $\mathcal A$. Prove the Cauchy–Schwarz inequality

$$
|\omega(A^*B)|^2
\le
\omega(A^*A)\omega(B^*B).
$$

<details><summary><strong>Solution</strong></summary>

If $\omega(A^*A)=0$, positivity of

$$
\omega((B+\lambda A)^*(B+\lambda A))
$$

for all $\lambda\in\mathbb C$ implies $\omega(A^*B)=0$, so the inequality is immediate. Otherwise set

$$
\lambda=-\frac{\omega(A^*B)}{\omega(A^*A)}.
$$

Positivity gives

$$
0\le
\omega((B+\lambda A)^*(B+\lambda A))
=\omega(B^*B)
-\frac{|\omega(A^*B)|^2}{\omega(A^*A)}.
$$

Multiplying by $\omega(A^*A)$ gives the result.

</details>

### Exercise 2

Let $\mathcal A=M_n(\mathbb C)$ and let $\psi\in\mathbb C^n$ be a unit vector. Define

$$
\omega(A)=\langle\psi,A\psi\rangle.
$$

Show that the GNS Hilbert space is naturally isomorphic to $\mathbb C^n$ and that the GNS representation is the defining representation of $M_n(\mathbb C)$.

<details><summary><strong>Solution</strong></summary>

The null space is

$$
\mathcal N_\omega
=\{A\in M_n(\mathbb C):\langle A\psi,A\psi\rangle=0\}
=\{A:A\psi=0\}.
$$

Define

$$
U:[A]\mapsto A\psi.
$$

This is well-defined because $[A]=[B]$ means $(A-B)\psi=0$. It preserves the inner product:

$$
\langle[A],[B]\rangle_\omega
=\omega(A^*B)
=\langle A\psi,B\psi\rangle.
$$

It is onto because for any $v\in\mathbb C^n$ there is a matrix $A$ with $A\psi=v$. Under this unitary identification,

$$
U\pi_\omega(C)[A]
=U[CA]
=CA\psi
=C\,U[A],
$$

so $\pi_\omega$ is the defining representation.

</details>

### Exercise 3

Let $G$ act on $\mathcal A$ by automorphisms $\alpha_g$, and suppose $\omega\circ\alpha_g=\omega$. Show that

$$
U_g[A]=[\alpha_g(A)]
$$

is a well-defined unitary operator on $\mathcal H_\omega$ and that it implements the automorphism in the GNS representation.

<details><summary><strong>Solution</strong></summary>

If $A\in\mathcal N_\omega$, then

$$
\omega(\alpha_g(A)^*\alpha_g(A))
=\omega(\alpha_g(A^*A))
=\omega(A^*A)=0,
$$

so $\alpha_g(A)\in\mathcal N_\omega$. Therefore $U_g$ is well-defined on equivalence classes. It preserves the inner product because

$$
\begin{aligned}
\langle U_g[A],U_g[B]\rangle_\omega
&=\omega(\alpha_g(A)^*\alpha_g(B))\\
&=\omega(\alpha_g(A^*B))\\
&=\omega(A^*B).
\end{aligned}
$$

Hence it extends to a unitary operator. Finally,

$$
\begin{aligned}
U_g\pi_\omega(C)U_g^{-1}[A]
&=U_g\pi_\omega(C)[\alpha_{g^{-1}}(A)]\\
&=U_g[C\alpha_{g^{-1}}(A)]\\
&=[\alpha_g(C)A]\\
&=\pi_\omega(\alpha_g(C))[A].
\end{aligned}
$$

Thus $U_g\pi_\omega(C)U_g^{-1}=\pi_\omega(\alpha_g(C))$.

</details>

## References

### Standard first pass

- Rudolf Haag, *Local Quantum Physics: Fields, Particles, Algebras*, 2nd ed., Springer, 1996. [doi:10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- Huzihiro Araki, *Mathematical Theory of Quantum Fields*, Oxford University Press, 1999. Oxford Academic: [Mathematical Theory of Quantum Fields](https://academic.oup.com/book/54810).
- Christopher J. Fewster and Kasia Rejzner, "Algebraic Quantum Field Theory – an introduction," arXiv: [1904.04051](https://arxiv.org/abs/1904.04051).

### Functional-analytic background

- Israel M. Gelfand and Mark A. Naimark, "On the imbedding of normed rings into the ring of operators in Hilbert space," *Matematiceskij Sbornik* **54** (1943), 197–217. EuDML: [On the imbedding of normed rings](https://eudml.org/doc/65219).
- Irving E. Segal, "Irreducible representations of operator algebras," *Bulletin of the American Mathematical Society* **53** (1947), 73–88. [doi:10.1090/S0002-9904-1947-08742-5](https://doi.org/10.1090/S0002-9904-1947-08742-5).
- Ola Bratteli and Derek W. Robinson, *Operator Algebras and Quantum Statistical Mechanics 1*, 2nd ed., Springer, 1987. [doi:10.1007/978-3-662-02520-8](https://doi.org/10.1007/978-3-662-02520-8).
- Ola Bratteli and Derek W. Robinson, *Operator Algebras and Quantum Statistical Mechanics 2*, 2nd ed., Springer, 1997. [doi:10.1007/978-3-662-03444-6](https://doi.org/10.1007/978-3-662-03444-6).

## Version history

- **2026-06-28:** Initial polished draft.
