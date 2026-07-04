---
title: "Modular Theory and Tomita–Takesaki"
description: "Introduce cyclic separating vectors, Tomita operators, modular conjugations, modular flows, and their role in algebraic QFT."
sidebar:
  label: "Modular Theory"
  order: 8
level: Advanced
status: "Polished draft"
source: "Tomita–Takesaki modular theory; Bisognano–Wichmann theorem; Haag, Local Quantum Physics; Witten entanglement notes."
topics:
  - algebraic QFT
  - modular theory
  - Tomita–Takesaki theory
  - operator algebras
canonicalTopics:
  - tomita-takesaki-theory
  - modular-flow
  - bisognano-wichmann-theorem
researchStatus:
  established:
    - "Tomita–Takesaki theory is a standard theorem of von Neumann algebras and is a central tool in algebraic QFT."
  active:
    - "Explicit modular flows and modular Hamiltonians are known only in special QFT situations; their use in quantum information, holography, and constraints on QFT remains active."
---

## Summary

Tomita–Takesaki theory is the operator-algebraic mechanism that associates a canonical dynamics to a pair

$$
(\mathcal M,\Omega),
$$

where $\mathcal M$ is a von Neumann algebra and $\Omega$ is a cyclic and separating vector. The central construction begins with the antilinear operator

$$
S_0(A\Omega)=A^*\Omega,
\qquad A\in\mathcal M.
$$

After closure, its polar decomposition is

$$
S=J\Delta^{1/2},
$$

where $J$ is the **modular conjugation** and $\Delta$ is the **modular operator**. The Tomita–Takesaki theorem says

$$
J\mathcal M J=\mathcal M',
\qquad
\Delta^{it}\mathcal M\Delta^{-it}=\mathcal M
\quad (t\in\mathbb R).
$$

Thus a state and an algebra determine both a conjugation from the algebra to its commutant and a one-parameter automorphism group of the algebra.

In QFT this is powerful because the vacuum is cyclic and separating for local algebras under standard hypotheses. Therefore every local algebra $\mathcal A(\mathcal O)$ with the vacuum vector has modular objects. Usually they are abstract. In special cases they are geometric: for a Rindler wedge, the Bisognano–Wichmann theorem identifies the modular flow of the vacuum with Lorentz boosts and the modular conjugation with a CPT-like reflection.

Modular theory is now a common language for Haag duality, wedge localization, KMS equilibrium, the Unruh effect, local thermal behavior, type III algebras, relative entropy, and modern algebraic approaches to QFT entanglement.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A diagram showing a von Neumann algebra and cyclic separating vector leading to the Tomita operator, its polar decomposition into modular conjugation and modular operator, and then the two Tomita–Takesaki outputs: commutant duality and modular flow.](/figures/rigorous-qft/tomita-takesaki-modular-data.svg)

<figcaption>

Tomita–Takesaki modular data. A standard pair $(\mathcal M,\Omega)$ defines the Tomita operator $S$, whose polar decomposition gives $J$ and $\Delta$. The theorem sends $\mathcal M$ to its commutant by $J$ and produces the intrinsic modular flow $\sigma_t(A)=\Delta^{it}A\Delta^{-it}$.

</figcaption>
</figure>

## Prerequisites

You should know [States and GNS Representation](/rigorous-qft/algebraic-qft/states-and-gns-representation/), [Vacuum Representations](/rigorous-qft/algebraic-qft/vacuum-representations/), and [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/). The Wightman page [Vacuum and Cyclicity](/rigorous-qft/wightman-axiomatic-qft/vacuum-and-cyclicity/) explains the Reeh–Schlieder intuition behind cyclicity.

For full proofs one needs von Neumann algebras, unbounded operators, adjoints, closures, polar decomposition, and spectral calculus. This page states the main theorem and explains its QFT meaning.

## Core idea

In finite quantum mechanics, a state on a subsystem can be represented by a density matrix. Its logarithm gives a modular or entanglement Hamiltonian. In continuum QFT this picture usually fails for local regions: local algebras are typically type III von Neumann algebras, and there is no trace-class density matrix for the vacuum restricted to a sharp region.

Tomita–Takesaki theory replaces the missing density matrix by algebraic modular data. The pair

$$
(\mathcal M,\Omega)
$$

contains enough information to define a modular operator $\Delta$, a modular conjugation $J$, and a modular automorphism group

$$
\sigma_t(A)=\Delta^{it}A\Delta^{-it}.
$$

This is not an approximation. It is a theorem about von Neumann algebras. The surprise in QFT is that the hypotheses occur naturally: local algebras and the vacuum form standard pairs.

## Setup and conventions

Let $\mathcal H$ be a Hilbert space and let

$$
\mathcal M\subset B(\mathcal H)
$$

be a von Neumann algebra. Its commutant is

$$
\mathcal M'
=\{B\in B(\mathcal H): BA=AB
\text{ for all } A\in\mathcal M\}.
$$

A vector $\Omega\in\mathcal H$ is **cyclic** for $\mathcal M$ if

$$
\overline{\mathcal M\Omega}=\mathcal H.
$$

It is **separating** for $\mathcal M$ if

$$
A\Omega=0,
\quad A\in\mathcal M
\quad \Longrightarrow \quad A=0.
$$

A pair $(\mathcal M,\Omega)$ with $\Omega$ cyclic and separating is often called a **standard pair**.

In algebraic QFT, take

$$
\mathcal M=\mathcal A(\mathcal O)''
$$

in the vacuum representation and $\Omega$ the vacuum vector. Under standard locality and spectrum assumptions, Reeh–Schlieder gives cyclicity for bounded open regions. Locality plus cyclicity for the causal complement gives separatingness.

## The Tomita operator

For a standard pair $(\mathcal M,\Omega)$, define an antilinear operator on the dense domain $\mathcal M\Omega$ by

$$
S_0(A\Omega)=A^*\Omega.
$$

This is well-defined because $\Omega$ is separating. Indeed, if

$$
A\Omega=B\Omega,
$$

then $(A-B)\Omega=0$, hence $A=B$, and therefore $A^*\Omega=B^*\Omega$.

The operator $S_0$ is densely defined because $\Omega$ is cyclic. It is closable; denote its closure by $S$. Since $S$ is closed and antilinear, it has a polar decomposition

$$
S=J\Delta^{1/2}.
$$

Here:

| Object | Type | Meaning |
|---|---|---|
| $S$ | closed antilinear operator | Sends $A\Omega$ to $A^*\Omega$. |
| $\Delta$ | positive self-adjoint operator | Modular operator. |
| $J$ | antiunitary involution | Modular conjugation. |
| $\sigma_t$ | automorphism group | $\sigma_t(A)=\Delta^{it}A\Delta^{-it}$. |

The modular operator is generally unbounded. Its imaginary powers $\Delta^{it}$ are unitary by the spectral theorem.

## The Tomita–Takesaki theorem

**Theorem (Tomita–Takesaki).** Let $\mathcal M$ be a von Neumann algebra on $\mathcal H$, and let $\Omega$ be cyclic and separating for $\mathcal M$. Let

$$
S=J\Delta^{1/2}
$$

be the polar decomposition of the Tomita operator. Then

$$
J\mathcal M J=\mathcal M',
$$

and

$$
\sigma_t^\Omega(\mathcal M)=\mathcal M,
\qquad
\sigma_t^\Omega(A)
=\Delta^{it}A\Delta^{-it},
\quad t\in\mathbb R.
$$

Thus $\sigma_t^\Omega$ is a one-parameter group of $*$-automorphisms of $\mathcal M$.

This result has two QFT interpretations.

First, $J\mathcal M J=\mathcal M'$ is an abstract duality statement. In a local net, the commutant of a local algebra is closely related to observables localized outside the region. When Haag duality holds, modular conjugation is tied to spacetime complementarity.

Second, $\Delta^{it}$ gives an intrinsic time evolution associated to the pair $(\mathcal M,\Omega)$. It is not necessarily physical time translation. It is the modular flow of the state restricted to the algebra.

## Modular flow and the KMS condition

The modular automorphism group is

$$
\sigma_t^\Omega(A)
=\Delta^{it}A\Delta^{-it}.
$$

The vector state

$$
\omega(A)=\langle\Omega,A\Omega\rangle
$$

is a KMS state at inverse temperature $1$ with respect to this modular flow. A convenient statement is: for suitable $A,B\in\mathcal M$, the function

$$
F_{A,B}(t)=\omega(A\sigma_t^\Omega(B))
$$

extends analytically to the strip

$$
0<\operatorname{Im} z<1
$$

and obeys the boundary relation

$$
F_{A,B}(t+i)=\omega(\sigma_t^\Omega(B)A).
$$

This is one reason modular theory is natural in equilibrium statistical mechanics and QFT. It identifies a state as thermal relative to its own modular dynamics.

The word **thermal** must be read carefully. The modular flow may be non-geometric and highly nonlocal. It is always an automorphism flow of the algebra, but it is not usually generated by an ordinary Hamiltonian density.

## Modular Hamiltonians

Physicists often write

$$
\Delta=e^{-K},
$$

where $K$ is the modular Hamiltonian. Equivalently,

$$
K=-\log\Delta.
$$

This notation is useful but dangerous. In finite-dimensional bipartite quantum mechanics, if

$$
\mathcal H=\mathcal H_L\otimes\mathcal H_R,
\qquad
\mathcal M=B(\mathcal H_L)\otimes 1,
$$

and $\Omega$ is a purification with reduced density matrices $\rho_L$ and $\rho_R$, then the modular operator is, on the support,

$$
\Delta=\rho_L\otimes\rho_R^{-1}.
$$

Thus

$$
K=-\log\rho_L\otimes 1
+1\otimes\log\rho_R.
$$

This finite-dimensional formula explains the name. But in QFT local algebras are typically type III, so $\rho_L$ does not exist as a trace-class density matrix for a sharp spatial region. The modular operator still exists because it is defined by the algebra and the cyclic separating vector, not by a density matrix.

This distinction is essential in rigorous discussions of entanglement. Entanglement in continuum QFT is primarily a property of algebras and states, not merely a tensor-factor density matrix.

## The Bisognano–Wichmann theorem

The most important geometric example is the right Rindler wedge in Minkowski spacetime,

$$
W_R=\{x\in\mathbb R^{1,d-1}: x^1>|x^0|\}.
$$

Let $\mathcal A(W_R)''$ be the wedge algebra in the vacuum representation. The Bisognano–Wichmann theorem identifies the modular objects of

$$
(\mathcal A(W_R)'',\Omega)
$$

with spacetime symmetries. With a conventional choice of boost orientation, the modular flow is the Lorentz boost preserving the wedge:

$$
\Delta_{W_R}^{it} A \Delta_{W_R}^{-it}
=
U(\Lambda_{W_R}(2\pi t))
A
U(\Lambda_{W_R}(2\pi t))^{-1},
$$

for $A$ localized in $W_R$. Some references use the opposite sign in the boost parameter; the invariant content is the factor $2\pi$ and the geometric boost action.

The corresponding modular conjugation is related to a CPT-type reflection that maps the right wedge to the left wedge. Consequently,

$$
J_{W_R}\mathcal A(W_R)''J_{W_R}
=\mathcal A(W_R)' .
$$

When wedge duality holds, the right-hand side is the algebra of the opposite wedge.

Physically, the theorem explains why the vacuum restricted to a Rindler wedge is thermal with respect to boost time. This is the algebraic core behind the Unruh effect.

## Local algebras and Reeh–Schlieder

Tomita–Takesaki theory enters QFT because local algebras with the vacuum are standard pairs.

For a typical bounded region $\mathcal O$, the Reeh–Schlieder theorem gives

$$
\overline{\mathcal A(\mathcal O)\Omega}=\mathcal H.
$$

So the vacuum is cyclic for $\mathcal A(\mathcal O)$. If the causal complement $\mathcal O'$ is nonempty and the vacuum is cyclic for $\mathcal A(\mathcal O')$, then locality implies separatingness for $\mathcal A(\mathcal O)$: if $A\in\mathcal A(\mathcal O)$ and $A\Omega=0$, then for every $B\in\mathcal A(\mathcal O')$,

$$
A B\Omega = B A\Omega=0.
$$

Since $\mathcal A(\mathcal O')\Omega$ is dense, $A=0$.

Thus local QFT is filled with standard pairs. Each region and state can have modular data. Most of the time, however, this data is not known explicitly.

## Duality, complements, and modular conjugation

The identity

$$
J\mathcal M J=\mathcal M'
$$

is purely algebraic. In a local quantum field theory, the commutant $\mathcal A(\mathcal O)'$ contains every observable localized in $\mathcal O'$, by locality:

$$
\mathcal A(\mathcal O')
\subset
\mathcal A(\mathcal O)'.
$$

Haag duality is the stronger condition that, after taking the appropriate von Neumann closures,

$$
\mathcal A(\mathcal O')
=
\mathcal A(\mathcal O)'.
$$

When duality holds, modular conjugation has a direct spacetime interpretation: it exchanges a region's algebra with the algebra of its causal complement. When duality fails, $\mathcal M'$ is still mathematically well-defined, but it may contain more than the naively assigned complement algebra. This difference is important in gauge theories, sectors, and theories with topological operators.

## Why type III algebras matter

In many relativistic QFTs, local von Neumann algebras are expected, and often proved in models, to be type III factors. This has practical consequences.

There is no normal trace on a type III factor analogous to the matrix trace. There is no density matrix representing the vacuum restricted to a sharp local algebra. There are no minimal projections corresponding to finite-dimensional local subsystems. Entanglement entropy of a sharp region is therefore not literally the von Neumann entropy of a density matrix on a tensor factor.

Modular theory works precisely where the density-matrix picture breaks. It gives:

| Density-matrix intuition | Modular-theoretic replacement |
|---|---|
| Reduced density matrix $\rho_R$ | State $\omega$ restricted to a local algebra $\mathcal M$. |
| Entanglement Hamiltonian $-\log\rho_R$ | Modular Hamiltonian $K=-\log\Delta$. |
| Tensor-factor complement | Commutant $\mathcal M'$. |
| Thermal density matrix | KMS condition for modular flow. |
| Partial trace | Restriction of a state to a subalgebra. |

This is why modular theory appears in modern discussions of QFT entanglement, relative entropy, and algebraic quantum information.

## Relative modular theory

There is also a relative version involving two cyclic separating vectors or two faithful normal states. It defines a relative modular operator

$$
\Delta_{\Psi|\Omega},
$$

and leads to Araki relative entropy. In favorable notation, the relative entropy of $\Psi$ with respect to $\Omega$ for the algebra $\mathcal M$ is

$$
S_{\mathcal M}(\Psi\|\Omega)
= -\langle \Psi,
\log\Delta_{\Omega|\Psi}\,\Psi\rangle,
$$

with conventions varying between authors.

Relative modular theory is central in rigorous formulations of monotonicity of relative entropy under restriction to smaller algebras. This monotonicity is the algebraic version of data processing:

$$
\mathcal N\subset\mathcal M
\quad\Longrightarrow\quad
S_{\mathcal N}(\Psi\|\Omega)
\leq
S_{\mathcal M}(\Psi\|\Omega).
$$

This is one bridge from AQFT to modern quantum information and holography. A full treatment belongs to later pages; here the important point is that modular theory replaces reduced density matrices by objects defined directly for von Neumann algebras.

## Common pitfalls

**Modular flow is not usually physical time.** It is an intrinsic automorphism group determined by a state and an algebra. Only in special cases, such as wedges in the vacuum, is it a familiar spacetime symmetry.

**The modular Hamiltonian is not usually local.** For a Rindler wedge, it is a boost generator. For a ball in a conformal vacuum, it is also geometric after a conformal map. For generic regions and states, it is nonlocal and hard to write explicitly.

**The commutant is not automatically the causal complement algebra.** Locality gives inclusion. Haag duality gives equality. Gauge theories and topological sectors often force one to distinguish the two.

**Type III algebras are not a technical nuisance.** They encode the ultraviolet and locality structure of continuum QFT. They are the reason sharp-region entanglement is not ordinary finite-dimensional entanglement.

**Cyclic does not mean locally creatable in finite time.** Reeh–Schlieder cyclicity is a density statement involving unbounded energy operations and analytic consequences of the spectrum condition. It does not allow practical superluminal signaling.

**The symbol $K=-\log\Delta$ hides domain issues.** $K$ is generally unbounded. Formal manipulations with modular Hamiltonians must respect domains and operator topology.

**The temperature convention can shift.** The modular flow is normalized so the state is KMS at inverse temperature $1$. In the Rindler application, the factor $2\pi$ converts this convention to boost time and the usual Unruh normalization.

## Relations to other pages

The page [States and GNS Representation](/rigorous-qft/algebraic-qft/states-and-gns-representation/) explains how a state becomes a cyclic representation. Modular theory adds what happens when that cyclic vector is also separating for a von Neumann algebra.

The page [Vacuum Representations](/rigorous-qft/algebraic-qft/vacuum-representations/) supplies the vacuum Hilbert space in which local von Neumann algebras live. The page [Isotony, Locality, and Covariance](/rigorous-qft/algebraic-qft/isotony-locality-and-covariance/) explains why causal complements and commutants are related.

The page [DHR Theory Preview](/rigorous-qft/algebraic-qft/dhr-theory-preview/) uses locality and duality to organize charged sectors. Modular theory supplies a different but related duality engine through $J\mathcal M J=\mathcal M'$ and through wedge-localized geometric modular action.

## Research status

Tomita–Takesaki theory is a settled theorem of operator algebra. The Bisognano–Wichmann theorem is a foundational result connecting modular data to spacetime geometry for wedge algebras in relativistic QFT.

What remains active is not the abstract theorem, but its use. For generic regions, modular flows and modular Hamiltonians are difficult to describe. In conformal field theory and holography they connect to entanglement, relative entropy, energy conditions, and reconstruction questions. In algebraic QFT they continue to guide work on duality, nuclearity, split inclusions, local covariance, and the structure of local algebras.

A trustworthy rule is: modular theory is completely rigorous as operator-algebra mathematics, while explicit QFT identification of modular objects is model- and region-dependent.

## Exercises

### Exercise 1: why separating makes the Tomita operator well-defined

Let $\Omega$ be separating for $\mathcal M$. Show that the rule

$$
S_0(A\Omega)=A^*\Omega
$$

is well-defined on $\mathcal M\Omega$.

<details><summary><strong>Solution</strong></summary>

Suppose $A\Omega=B\Omega$. Then

$$
(A-B)\Omega=0.
$$

Since $\Omega$ is separating for $\mathcal M$, this implies $A-B=0$, hence $A=B$. Therefore

$$
A^*\Omega=B^*\Omega.
$$

So the value of $S_0$ depends only on the vector $A\Omega$, not on the chosen representative $A$.

</details>

### Exercise 2: locality gives separatingness from complement cyclicity

Let $\mathcal M=\mathcal A(\mathcal O)$ and suppose $\Omega$ is cyclic for $\mathcal A(\mathcal O')$. Assume locality, so every $A\in\mathcal A(\mathcal O)$ commutes with every $B\in\mathcal A(\mathcal O')$. Show that $\Omega$ is separating for $\mathcal A(\mathcal O)$.

<details><summary><strong>Solution</strong></summary>

Let $A\in\mathcal A(\mathcal O)$ and assume $A\Omega=0$. For every $B\in\mathcal A(\mathcal O')$,

$$
A B\Omega = B A\Omega=0,
$$

where locality was used in the first equality. Since $\Omega$ is cyclic for $\mathcal A(\mathcal O')$, the set $\mathcal A(\mathcal O')\Omega$ is dense in $\mathcal H$. Therefore $A$ vanishes on a dense subspace. Because $A$ is bounded, $A=0$. Thus $\Omega$ is separating for $\mathcal A(\mathcal O)$.

</details>

### Exercise 3: finite-dimensional modular operator

Let

$$
\mathcal H=\mathcal H_L\otimes\mathcal H_R,
\qquad
\mathcal M=B(\mathcal H_L)\otimes 1,
$$

and let

$$
\Omega=\sum_i \sqrt{p_i}\, e_i\otimes f_i,
\qquad p_i>0,
\qquad \sum_i p_i=1,
$$

with orthonormal bases $\{e_i\}$ and $\{f_i\}$. Show that, on matrix units, the modular flow acts as

$$
\sigma_t(E_{ij}\otimes 1)
=\left(\frac{p_i}{p_j}\right)^{it}
E_{ij}\otimes 1.
$$

<details><summary><strong>Solution</strong></summary>

The reduced density matrix on the left is

$$
\rho_L=\sum_i p_i |e_i\rangle\langle e_i|.
$$

For the algebra $B(\mathcal H_L)\otimes 1$, the modular automorphism is implemented on the left algebra by

$$
\sigma_t(A)=\rho_L^{it}A\rho_L^{-it}.
$$

For the matrix unit $E_{ij}=|e_i\rangle\langle e_j|$,

$$
\rho_L^{it}E_{ij}\rho_L^{-it}
=p_i^{it}p_j^{-it}E_{ij}
=\left(\frac{p_i}{p_j}\right)^{it}E_{ij}.
$$

This finite-dimensional formula is the density-matrix shadow of the general Tomita–Takesaki modular flow.

</details>

## References

### Modular theory and operator algebras

- M. Takesaki, *Tomita's Theory of Modular Hilbert Algebras and its Applications*, Lecture Notes in Mathematics **128**, Springer, 1970. [doi:10.1007/BFb0065832](https://doi.org/10.1007/BFb0065832).
- Rudolf Haag, *Local Quantum Physics: Fields, Particles, Algebras*, 2nd ed., Springer, 1996. [doi:10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- Huzihiro Araki, *Mathematical Theory of Quantum Fields*, Oxford University Press, 1999. Oxford Academic: [Mathematical Theory of Quantum Fields](https://academic.oup.com/book/54810).

### Modular theory in QFT

- Joseph J. Bisognano and Eyvind H. Wichmann, "On the duality condition for a Hermitian scalar field," *Journal of Mathematical Physics* **16** (1975), 985–1007. [doi:10.1063/1.522605](https://doi.org/10.1063/1.522605).
- Joseph J. Bisognano and Eyvind H. Wichmann, "On the duality condition for quantum fields," *Journal of Mathematical Physics* **17** (1976), 303–321. [doi:10.1063/1.522898](https://doi.org/10.1063/1.522898).
- H.-J. Borchers, "On revolutionizing quantum field theory with Tomita's modular theory," *Journal of Mathematical Physics* **41** (2000), 3604–3673. [doi:10.1063/1.533323](https://doi.org/10.1063/1.533323).
- Rudolf Haag, N. M. Hugenholtz, and M. Winnink, "On the equilibrium states in quantum statistical mechanics," *Communications in Mathematical Physics* **5** (1967), 215–236. [doi:10.1007/BF01646342](https://doi.org/10.1007/BF01646342).

### Entanglement and relative modular theory

- Edward Witten, "Notes on Some Entanglement Properties of Quantum Field Theory," *Reviews of Modern Physics* **90** (2018), 045003. [doi:10.1103/RevModPhys.90.045003](https://doi.org/10.1103/RevModPhys.90.045003), arXiv: [1803.04993](https://arxiv.org/abs/1803.04993).
- Nima Lashkari, "Constraining Quantum Fields using Modular Theory," arXiv: [1810.09306](https://arxiv.org/abs/1810.09306).
- Stefan Hollands and Ko Sanders, "Entanglement measures and their properties in quantum field theory," arXiv: [1702.04924](https://arxiv.org/abs/1702.04924).

## Version history

- 2026-06-29: First polished draft. Introduced standard pairs, Tomita operators, modular conjugation, modular flow, KMS interpretation, Bisognano–Wichmann theorem, type III caveats, relative modular theory, and exercises.
