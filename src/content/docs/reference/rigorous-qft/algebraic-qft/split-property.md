---
title: "Split Property"
description: "Explain split inclusions of local algebras, type I intermediate factors, and the role of nuclearity in algebraic QFT."
sidebar:
  label: "Split Property"
  order: 9
level: Advanced
status: "Polished draft"
source: "Doplicher–Longo split inclusions; Buchholz–Wichmann nuclearity; Haag, Local Quantum Physics; Fewster split property review."
topics:
  - algebraic QFT
  - split property
  - local independence
  - nuclearity
canonicalTopics:
  - split-property
  - local-algebras
  - nuclearity-condition
researchStatus:
  established:
    - "The split property is a standard strengthening of causal independence for separated local algebras and follows from suitable nuclearity or phase-space conditions in many models."
  active:
    - "Proving split inclusions in interacting theories, gauge theories, curved spacetimes, and scaling limits remains a useful diagnostic of physical phase-space behavior."
---

## Summary

The **split property** says that two local algebras separated by a nonzero spacetime collar behave, for many purposes, as if they belonged to different tensor factors. In algebraic QFT it is not usually true that a sharp local algebra gives a tensor factorization of the Hilbert space. Local algebras in continuum QFT are typically type III von Neumann algebras, not algebras of the form $B(\mathcal H_{\mathrm{in}})$ inside a literal decomposition

$$
\mathcal H\simeq \mathcal H_{\mathrm{in}}\otimes
\mathcal H_{\mathrm{out}}.
$$

The split property replaces this false sharp factorization by a correct softened one. If

$$
\mathcal O_1\Subset \mathcal O_2
$$

are nested regions with positive separation between the inner region and the complement of the outer region, the inclusion

$$
\mathcal A(\mathcal O_1)''\subset \mathcal A(\mathcal O_2)''
$$

is **split** when there is a type I factor $\mathcal N$ such that

$$
\mathcal A(\mathcal O_1)''
\subset \mathcal N
\subset \mathcal A(\mathcal O_2)''.
$$

A type I factor is isomorphic to $B(\mathcal K)$ for some Hilbert space $\mathcal K$. Thus $\mathcal N$ supplies a tensor-product window between the inner observables and the outside observables. The collar is essential: the split property is a statement about separated regions, not a statement that the Hilbert space factorizes across a sharp entangling surface.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A diagram of nested spacetime regions O1 inside O2 and the corresponding split inclusion of von Neumann algebras A(O1) double prime inside a type I factor N inside A(O2) double prime.](/figures/rigorous-qft/split-property-inclusion.svg)

<figcaption>

The split property for nested regions. The spacetime collar between $\mathcal O_1$ and the causal complement of $\mathcal O_2$ permits an intermediate type I factor $\mathcal N$, giving a controlled tensor-product substitute for sharp local factorization.

</figcaption>
</figure>

## Prerequisites

You should know [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/), [Haag–Kastler Axioms](/rigorous-qft/algebraic-qft/haag-kastler-axioms/), [States and GNS Representation](/rigorous-qft/algebraic-qft/states-and-gns-representation/), and [Modular Theory and Tomita–Takesaki](/rigorous-qft/algebraic-qft/modular-theory-and-tomita-takesaki/). The page [Vacuum and Cyclicity](/rigorous-qft/wightman-axiomatic-qft/vacuum-and-cyclicity/) gives the Reeh–Schlieder background that explains why sharp local subspaces are much subtler than finite-dimensional subsystems.

The page uses standard operator-algebra language: von Neumann algebra, commutant, factor, type I factor, normal state, and tensor product. The main point is conceptual even if one has not yet studied the classification of von Neumann algebras.

## Core idea

In ordinary finite quantum mechanics, independent subsystems are described by a tensor product

$$
\mathcal H=\mathcal H_A\otimes \mathcal H_B,
$$

with observable algebras

$$
B(\mathcal H_A)\otimes \mathbf 1,
\qquad
\mathbf 1\otimes B(\mathcal H_B).
$$

It is tempting to import this picture directly into continuum QFT and write

$$
\mathcal H\stackrel{?}{=}
\mathcal H_{\mathcal O}\otimes \mathcal H_{\mathcal O'}.
$$

That formula is generally wrong for sharp continuum regions. It fails for the same physical reason that entanglement entropy across a sharp boundary is ultraviolet divergent: modes at arbitrarily short distances live near the boundary. Algebraically, the local von Neumann algebras are typically type III, and type III factors do not define ordinary density matrices or tensor factors in the finite-system sense.

The split property says that a tensor-product picture reappears after inserting a buffer. Instead of cutting exactly at the boundary of $\mathcal O_1$, one compares the observables in $\mathcal O_1$ with observables outside a slightly larger region $\mathcal O_2$. The collar

$$
\mathcal O_2\setminus \overline{\mathcal O_1}
$$

absorbs the ultraviolet correlations that would otherwise obstruct factorization.

This is one of the cleanest examples of a recurring theme in rigorous QFT:

$$
\text{sharp local tensor factorization is false,}
\qquad
\text{split factorization with a collar can be true.}
$$

## Setup and conventions

Work in a fixed vacuum representation of a Haag–Kastler net on Minkowski spacetime. Write

$$
\mathcal M(\mathcal O)
=\mathcal A(\mathcal O)''
\subset B(\mathcal H)
$$

for the von Neumann algebra generated by the local $C^*$-algebra in the representation. The double prime is important: the split property is normally stated for von Neumann algebras.

For two regions $\mathcal O_1$ and $\mathcal O_2$, the notation

$$
\mathcal O_1\Subset \mathcal O_2
$$

means that $\mathcal O_1$ is compactly contained in $\mathcal O_2$ in the appropriate causal sense. In Minkowski space, for double cones, one may think of $\overline{\mathcal O_1}$ as lying inside $\mathcal O_2$ with positive distance from the boundary. More invariantly, there is a nonzero spacetime collar between the inner region and the outside of the outer region.

By isotony,

$$
\mathcal O_1\subset \mathcal O_2
\quad\Longrightarrow\quad
\mathcal M(\mathcal O_1)\subset \mathcal M(\mathcal O_2).
$$

The split property is an additional property of this inclusion.

## Split inclusions

Let $\mathcal M_1\subset \mathcal M_2$ be an inclusion of von Neumann algebras on the same Hilbert space. The inclusion is called **split** if there exists a type I factor $\mathcal N$ satisfying

$$
\mathcal M_1\subset \mathcal N\subset \mathcal M_2.
$$

In a local net, the split property for double cones says that whenever

$$
\mathcal O_1\Subset \mathcal O_2,
$$

the inclusion

$$
\mathcal M(\mathcal O_1)
\subset
\mathcal M(\mathcal O_2)
$$

is split.

Equivalently, the local degrees of freedom in $\mathcal O_1$ can be separated from those outside $\mathcal O_2$ by a type I algebra sitting in the collar. A type I factor has the form

$$
\mathcal N\simeq B(\mathcal K),
$$

so it behaves like the algebra of all bounded operators on an ordinary Hilbert-space subsystem.

This does **not** say that $\mathcal M(\mathcal O_1)$ itself is type I. It usually is not. The point is that it can be embedded into a type I factor before reaching the larger local algebra.

## Tensor-product meaning

The split property has a useful tensor-product interpretation. In favorable standard situations, a split inclusion

$$
\mathcal M_1\subset \mathcal M_2
$$

implies that there is a unitary identification under which the algebra generated by $\mathcal M_1$ and $\mathcal M_2'$ looks like a tensor product:

$$
\mathcal M_1\vee \mathcal M_2'
\simeq
\mathcal M_1\ \overline\otimes\ \mathcal M_2'.
$$

Here $\vee$ denotes the von Neumann algebra generated by two commuting algebras, and $\overline\otimes$ is the von Neumann tensor product. In a local net, $\mathcal M(\mathcal O_2)'$ contains operators localized outside $\mathcal O_2$ when duality properties hold or when one works with the corresponding commutant algebra.

The interpretation is:

$$
\text{inner observables in }\mathcal O_1
\quad\text{and}\quad
\text{outer observables outside }\mathcal O_2
$$

can be treated as statistically independent subsystems, provided one leaves a collar between them.

This is stronger than ordinary locality. Locality says that spacelike separated algebras commute. Splitness says that their joint normal state space has the kind of independence familiar from tensor-product quantum mechanics.

## Product states and statistical independence

One important consequence is the existence of normal product states. Suppose $\omega_1$ is a normal state on $\mathcal M_1$ and $\omega_2$ is a normal state on $\mathcal M_2'$. Under splitness, there is a normal state $\omega$ on the generated algebra such that

$$
\omega(AB)=\omega_1(A)\,\omega_2(B),
\qquad
A\in\mathcal M_1,
\quad B\in\mathcal M_2'.
$$

This is not automatic from commutativity alone. In infinite systems, commuting algebras can be entangled in a way that prevents such normal product extensions. The split property rules out that pathology for observables separated by a buffer.

This is why the split property is often described as a strong form of causal or statistical independence. It says not only that experiments in separated regions are compatible, but also that independently prepared normal states can be combined.

## Why a collar is physically necessary

The collar is not a technical nuisance. It is the mathematical expression of ultraviolet physics.

In a lattice system with finitely many sites, a finite region and its complement give a literal tensor product. In the continuum, every boundary has modes at arbitrarily short wavelengths. If the cut is sharp, the vacuum contains arbitrarily high-energy correlations across it. This is reflected in several related facts:

| Finite lattice intuition | Continuum QFT reality |
|---|---|
| Finite local Hilbert factor. | Local algebras are typically type III. |
| Density matrix for every subsystem. | No trace-class local density matrix for a sharp region. |
| Entanglement entropy often finite. | Entanglement entropy across a sharp boundary is UV divergent. |
| Exact tensor product across a boundary. | Split tensor-product behavior requires a buffer. |

The split property says that the continuum is still compatible with subsystem reasoning, but only after one asks a physically softened question.

## Nuclearity and phase-space bounds

A major sufficient condition for the split property is a **nuclearity condition**. The idea is to measure how many local states of bounded energy can be produced from the vacuum by operators in a bounded region.

Let $H$ be the Hamiltonian, $\Omega$ the vacuum, and $\mathcal M(\mathcal O)$ a local von Neumann algebra. For $\beta>0$, define the map

$$
\Theta_{\beta,\mathcal O}:
\mathcal M(\mathcal O)\to\mathcal H,
\qquad
\Theta_{\beta,\mathcal O}(A)=e^{-\beta H}A\Omega.
$$

The factor $e^{-\beta H}$ suppresses high energies. A nuclearity condition asks that this map be nuclear, with suitable bounds on its nuclear norm. Roughly, the image of the unit ball of the local algebra should be small enough after energy damping to behave like a phase space with finite effective density of states.

The physical message is:

$$
\text{reasonable local energy-level density}
\quad\Longrightarrow\quad
\text{split property.}
$$

This is why the split property is not just an abstract algebraic condition. It encodes a physically meaningful phase-space constraint. The Buchholz–Wichmann nuclearity condition was designed precisely to exclude theories with too many local degrees of freedom at bounded energy.

## Relation to type III local algebras

At first sight, the split property may look like it contradicts the statement that local algebras are type III. It does not.

The typical picture is

$$
\mathcal M(\mathcal O_1)
\subset
\mathcal N
\subset
\mathcal M(\mathcal O_2),
$$

where

$$
\mathcal M(\mathcal O_1)
\quad\text{and}\quad
\mathcal M(\mathcal O_2)
$$

are type III factors, while $\mathcal N$ is type I. The type I factor is not itself assigned to a sharp spacetime region by the original net. It is an auxiliary algebra sitting between two local algebras. Its existence says that the inclusion has enough room to insert an ordinary quantum-mechanical subsystem.

A useful analogy is an ultraviolet regulator. The split inclusion does not say that the exact local theory becomes finite dimensional or type I. It says that if we keep a finite collar, the local and exterior algebras can be separated through a type I bridge.

## Consequences in AQFT

The split property has many equivalent or related consequences under standard hypotheses. The precise equivalences depend on technical assumptions, but the following are reliable guideposts.

| Consequence | Meaning |
|---|---|
| Normal product states | Independently chosen normal states on separated algebras can be combined. |
| Tensor-product representation | The generated algebra of inner and sufficiently outer observables behaves like a von Neumann tensor product. |
| Strong statistical independence | Locality is enhanced from commutativity to preparation independence. |
| Controlled subsystem approximation | Local physics can be approximated by ordinary tensor-factor reasoning when a collar is left. |
| Thermodynamic regularity | Nuclearity-style conditions connect splitness to acceptable local phase-space growth. |

The split property is also related to local preparability results: one can alter a state in an inner region without disturbing observables in a suitably separated outer region, within the limits set by the collar.

## A standard theorem pattern

A common theorem pattern in algebraic QFT is:

**Theorem pattern.** Suppose a Poincaré covariant vacuum net satisfies isotony, locality, spectrum condition, suitable additivity assumptions, and a phase-space nuclearity condition. Then for double cones $\mathcal O_1\Subset\mathcal O_2$, the inclusion

$$
\mathcal M(\mathcal O_1)
\subset
\mathcal M(\mathcal O_2)
$$

is split.

This statement is deliberately phrased as a pattern rather than a single universal theorem because the exact hypotheses vary between formulations: Buchholz–Wichmann nuclearity, modular nuclearity, compactness conditions, and curved-spacetime variants have different technical forms.

The important lesson is stable: splitness is usually proved from an energy or phase-space bound, not from locality alone.

## Example: what splitness looks like in finite systems

Let

$$
\mathcal H=\mathcal H_1\otimes\mathcal H_b\otimes\mathcal H_2,
$$

where $\mathcal H_b$ is a buffer Hilbert space. Define

$$
\mathcal M_1=B(\mathcal H_1)\otimes\mathbf 1_b\otimes\mathbf 1_2,
$$

and

$$
\mathcal M_2=B(\mathcal H_1\otimes\mathcal H_b)\otimes\mathbf 1_2.
$$

Then the inclusion $\mathcal M_1\subset\mathcal M_2$ is split. One can choose, for example,

$$
\mathcal N=B(\mathcal H_1)\otimes B(\mathcal H_b)\otimes\mathbf 1_2
=\mathcal M_2.
$$

This finite example is too simple because every algebra is type I. In continuum QFT, the analogy is not that the local algebras become finite tensor factors, but that a type I algebra can be inserted between two type III local algebras when a collar is present.

## Common pitfalls

**Pitfall 1: confusing splitness with locality.** Locality gives commutativity for spacelike separated observables. Splitness gives a tensor-product-like independence statement. It is stronger.

**Pitfall 2: removing the collar.** The split property is not the assertion that $\mathcal M(\mathcal O)$ and $\mathcal M(\mathcal O')$ factorize sharply. The buffer between $\mathcal O_1$ and the outside of $\mathcal O_2$ is essential.

**Pitfall 3: thinking the intermediate type I factor is canonical.** A split inclusion guarantees existence of at least one type I factor. There is generally no unique preferred choice without extra structure.

**Pitfall 4: treating type III as a pathology.** Type III local algebras are expected in continuum relativistic QFT. The split property is not a cure for type III behavior; it is a way to recover operational subsystem reasoning where it is physically justified.

**Pitfall 5: assuming every physically interesting net is known to be split.** Splitness is known in many models and follows from strong phase-space bounds, but it is still a property to prove. In difficult interacting and gauge-theoretic settings, it should be treated as a nontrivial assumption or theorem.

## Relations to other pages

The split property builds directly on [Isotony, Locality, and Covariance](/rigorous-qft/algebraic-qft/isotony-locality-and-covariance/): isotony gives the inclusion, locality gives commutation with outside observables, and splitness adds statistical independence.

It is closely tied to [Modular Theory and Tomita–Takesaki](/rigorous-qft/algebraic-qft/modular-theory-and-tomita-takesaki/), because modular nuclearity is one route to split inclusions, and split inclusions are often studied using modular data.

It also prepares [Haag Duality](/rigorous-qft/algebraic-qft/haag-duality/). Duality asks whether the algebra of a region is the full commutant of the algebra of its causal complement. Splitness asks whether separated inclusions have a type I interpolation. The two properties are logically different but frequently appear together in structural AQFT theorems.

## Research status

**Established.** The split property is a standard structural condition in algebraic QFT. It has precise formulations in terms of split inclusions of von Neumann algebras, and it follows from several nuclearity or compactness assumptions in important classes of models. It is central in making sense of local statistical independence despite type III local algebras.

**Active.** In hard interacting models, gauge theories, curved spacetimes, and scaling limits, the split property remains a meaningful condition to verify. Modern work often studies how splitness is transported between spacetimes, how it follows from modular nuclearity, and how it interacts with quantum energy inequalities, entanglement, and thermodynamic behavior.

**Open-ended physics lesson.** A physically acceptable continuum QFT should not have arbitrarily many locally creatable low-energy states. The split property is one rigorous way that this expectation becomes a theorem-level condition.

## Exercises

### Exercise 1

Explain why the split property is stronger than locality. Use the distinction between commutativity of algebras and existence of normal product states.

<details><summary><strong>Solution</strong></summary>

Locality says that if two regions are spacelike separated, then every observable in one local algebra commutes with every observable in the other. This makes the measurements compatible, but it does not by itself say that arbitrary normal states on the two algebras can be combined into a normal product state on the algebra they generate.

The split property gives tensor-product-like behavior for separated algebras with a collar. In particular, under standard hypotheses, normal product states exist on the generated algebra. Thus splitness is a stronger statistical independence statement, not merely a commutation statement.

</details>

### Exercise 2

Let $\mathcal M_1\subset\mathcal M_2$ be split. What role is played by the type I factor $\mathcal N$?

<details><summary><strong>Solution</strong></summary>

The type I factor $\mathcal N$ is an ordinary quantum-mechanical algebra inserted between $\mathcal M_1$ and $\mathcal M_2$:

$$
\mathcal M_1\subset\mathcal N\subset\mathcal M_2.
$$

Because $\mathcal N\simeq B(\mathcal K)$, it supplies a tensor-product window. It does not mean that $\mathcal M_1$ or $\mathcal M_2$ is type I; they may remain type III. The type I algebra is an interpolating algebra made possible by the spacetime collar.

</details>

### Exercise 3

Why is a nuclearity condition physically related to the split property?

<details><summary><strong>Solution</strong></summary>

A nuclearity condition controls the size of the set of vectors

$$
e^{-\beta H}A\Omega,
\qquad A\in\mathcal M(\mathcal O),
$$

as $A$ ranges over the local unit ball. The energy damping suppresses high-energy states. If the resulting map is nuclear with suitable bounds, the theory has a finite effective local phase-space density. Such control prevents too many independent local degrees of freedom from appearing at bounded energy, and this is strong enough in many settings to imply split inclusions for separated regions.

</details>

## References

### Standard first pass

- Rudolf Haag, *Local Quantum Physics: Fields, Particles, Algebras*, 2nd ed., Springer, 1996. [doi:10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- Huzihiro Araki, *Mathematical Theory of Quantum Fields*, Oxford University Press, 1999. Oxford Academic: [Mathematical Theory of Quantum Fields](https://academic.oup.com/book/54810).
- Christopher J. Fewster, "The split property for quantum field theories in flat and curved spacetimes," arXiv: [1601.06936](https://arxiv.org/abs/1601.06936).

### Original and deeper references

- Sergio Doplicher and Roberto Longo, "Standard and split inclusions of von Neumann algebras," *Inventiones Mathematicae* **75** (1984), 493–536. [doi:10.1007/BF01388641](https://doi.org/10.1007/BF01388641).
- Detlev Buchholz and Eyvind H. Wichmann, "Causal independence and the energy-level density of states in local quantum field theory," *Communications in Mathematical Physics* **106** (1986), 321–344. [doi:10.1007/BF01454978](https://doi.org/10.1007/BF01454978).
- Detlev Buchholz, Claudio D'Antoni, and Roberto Longo, "Nuclear maps and modular structures. II: Applications to quantum field theory," *Communications in Mathematical Physics* **129** (1990), 115–138. [doi:10.1007/BF02096782](https://doi.org/10.1007/BF02096782).
- Christopher J. Fewster, "The split property for locally covariant quantum field theories in curved spacetime," *Letters in Mathematical Physics* **105** (2015), 1633–1661. arXiv: [1501.02682](https://arxiv.org/abs/1501.02682).
- Stephen J. Summers, "Subsystems and independence in relativistic microscopic physics," *Studies in History and Philosophy of Modern Physics* **40** (2009), 133–141. arXiv: [0812.1517](https://arxiv.org/abs/0812.1517).

## Version history

- **2026-06-29:** Initial page on split inclusions, type I interpolation, statistical independence, and nuclearity.
