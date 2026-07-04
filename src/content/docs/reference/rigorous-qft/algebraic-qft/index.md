---
title: "Algebraic QFT"
description: "Chapter overview for local nets, Haag–Kastler axioms, states, sectors, and operator-algebraic structures in the Mathematical and Rigorous QFT volume."
sidebar:
  label: "Overview"
  order: 0
level: Graduate
status: "Polished draft"
source: "Haag–Kastler algebraic QFT; Haag, Local Quantum Physics; Araki, Mathematical Theory of Quantum Fields."
topics:
  - algebraic QFT
  - local observables
  - operator algebras
canonicalTopics:
  - algebraic-quantum-field-theory
  - local-nets
  - haag-kastler-axioms
researchStatus:
  established:
    - "Algebraic QFT is a standard rigorous framework for local relativistic quantum theory in terms of observable algebras."
  active:
    - "Constructing and classifying physically central interacting nets, especially in four dimensions and gauge theory, remains a major research direction."
---

Algebraic QFT is the chapter in the Mathematical and Rigorous QFT volume where observables, rather than fields or path integrals, become the primary objects. A theory is encoded by a compatible assignment of algebras to spacetime regions.

This chapter exists because many questions in QFT are local and representation-sensitive. Which measurements are available in a bounded region? What does spacelike separation mean algebraically? How can thermal states, charged sectors, gauge-invariant observables, or curved-spacetime theories be discussed without choosing one privileged Hilbert space from the start?

Read this chapter when you want the theorem-level language behind local quantum physics: nets, Haag–Kastler axioms, states, GNS representations, superselection sectors, modular theory, and locality properties such as Haag duality and the split property.

$$
\text{algebraic QFT} =
\text{spacetime regions organized by local observable algebras}.
$$

## Prerequisites

You should know [Conventions](/rigorous-qft/conventions/), [Why Fields Are Distributions](/rigorous-qft/operator-valued-distributions/why-fields-are-distributions/), and the basic Wightman conditions in [Wightman Axioms](/rigorous-qft/wightman-axiomatic-qft/wightman-axioms/). The first pages below are designed to be readable before a full course on operator algebras, but later pages will use $C^*$-algebras, von Neumann algebras, states, and representations more seriously.

## Reading path

Read these pages in order on a first pass.

| Step | Page | What it gives you |
|---:|---|---|
| 1 | [Local Nets of Algebras](/rigorous-qft/algebraic-qft/local-nets-of-algebras/) | The basic object $\mathcal O\mapsto\mathcal A(\mathcal O)$ and why local observables replace pointlike fields. |
| 2 | [Haag–Kastler Axioms](/rigorous-qft/algebraic-qft/haag-kastler-axioms/) | The standard structural assumptions: isotony, locality, covariance, vacuum, spectrum, and additivity variants. |
| 3 | [Isotony, Locality, and Covariance](/rigorous-qft/algebraic-qft/isotony-locality-and-covariance/) | The three core net axioms as precise algebraic versions of inclusion, causal commutation, and spacetime symmetry. |
| 4 | [Vacuum Representations](/rigorous-qft/algebraic-qft/vacuum-representations/) | How a vacuum state produces a Hilbert space, local von Neumann algebras, unitary covariance, and positive energy. |
| 5 | [States and GNS Representation](/rigorous-qft/algebraic-qft/states-and-gns-representation/) | The general theorem turning algebraic states into cyclic Hilbert-space representations. |
| 6 | [Superselection Sectors](/rigorous-qft/algebraic-qft/superselection-sectors/) | How inequivalent representations encode charges, sector labels, and the DHR localization criterion. |
| 7 | [DHR Theory Preview](/rigorous-qft/algebraic-qft/dhr-theory-preview/) | How localized transportable charges become endomorphisms, tensor categories, statistics, and reconstructed compact gauge symmetry. |
| 8 | [Modular Theory and Tomita–Takesaki](/rigorous-qft/algebraic-qft/modular-theory-and-tomita-takesaki/) | The modular operator-algebra machinery behind commutants, KMS structure, wedge boosts, and QFT entanglement. |
| 9 | [Split Property](/rigorous-qft/algebraic-qft/split-property/) | The type I interpolation condition that gives tensor-product-like independence for regions separated by a collar. |
| 10 | [Haag Duality](/rigorous-qft/algebraic-qft/haag-duality/) | The local completeness condition $\mathcal M(\mathcal O)=\mathcal M(\mathcal O')'$ and what its failures mean. |
| 11 | [Additivity and the Time-Slice Axiom](/rigorous-qft/algebraic-qft/additivity-and-time-slice-axiom/) | The local-generation and Cauchy-generation principles behind additive nets and algebraic dynamics. |

After this path, you should be able to explain what a local net is, state the core Haag–Kastler axioms, distinguish algebraic from field-based locality, describe how states generate Hilbert-space representations, state the basic idea of a superselection sector, recognize the DHR endomorphism picture, explain why modular theory is central to local algebras, distinguish split independence from locality, state Haag duality as a local completeness condition, distinguish additivity from isotony, and formulate the time-slice axiom as algebraic hyperbolic dynamics.

## Landmarks

| Landmark | Meaning | Where used next |
|---|---|---|
| $\mathcal O\mapsto\mathcal A(\mathcal O)$ | A spacetime region is assigned an algebra of observables localized there. | All later algebraic QFT pages. |
| Isotony | $\mathcal O_1\subset\mathcal O_2$ implies $\mathcal A(\mathcal O_1)\subset\mathcal A(\mathcal O_2)$. | Additivity, scaling limits, and local generation. |
| Locality | Spacelike separated local algebras commute. | Haag duality, split property, superselection sectors. |
| Covariance | Spacetime symmetries move regions and algebras together. | Vacuum representations and locally covariant QFT. |
| Quasi-local algebra | The $C^*$-completion generated by all local algebras. | States and GNS representations. |
| Vacuum representation | A Hilbert-space representation with invariant positive-energy vacuum. | Modular theory, particle interpretation, and scattering questions. |
| GNS construction | Every state on a $C^*$-algebra gives a cyclic representation realizing that state as a vector state. | Sector theory, KMS states, and representation comparisons. |
| Superselection sector | A physically admissible representation class not connected to another by observables. | DHR theory, charge localization, and gauge-group reconstruction. |
| DHR localization | A charge localized in $\mathcal O$ is indistinguishable from the vacuum on $\mathcal A(\mathcal O')$. | Localized endomorphisms and tensor categories of sectors. |
| Localized endomorphism | A DHR sector can often be represented by $\rho:\mathcal A\to\mathcal A$ acting trivially on the spacelike complement. | Fusion, statistics, and Doplicher–Roberts reconstruction. |
| Modular data | A standard pair $(\mathcal M,\Omega)$ gives $S=J\Delta^{1/2}$, $J\mathcal M J=\mathcal M'$, and $\sigma_t(A)=\Delta^{it}A\Delta^{-it}$. | Haag duality, KMS states, wedge boosts, and entanglement. |
| Split inclusion | $\mathcal M(\mathcal O_1)\subset\mathcal N\subset\mathcal M(\mathcal O_2)$ with $\mathcal N$ type I for $\mathcal O_1\Subset\mathcal O_2$. | Local independence, subsystem approximations, and nuclearity. |
| Haag duality | $\mathcal A(\mathcal O)=\mathcal A(\mathcal O')'$ in suitable situations. | Sector theory and completeness of local observables. |
| Dual net | $\mathcal M^d(\mathcal O)=\mathcal M(\mathcal O')'$. | Diagnosing missing observables, gauge constraints, and topological obstructions. |
| Additivity | $\mathcal A(\mathcal O)$ is generated by the algebras of a local cover of $\mathcal O$. | Local generation, continuum limits, and exclusion of hidden nonlocal observables. |
| Time-slice axiom | A Cauchy neighborhood $\mathcal N$ generates the algebra of its domain of dependence. | Locally covariant QFT, relative Cauchy evolution, and curved-spacetime dynamics. |

## Common confusions

**The net is not just the global algebra.** The global algebra without the localization map forgets which observables belong to which regions. Algebraic QFT is local because the region assignment is part of the data.

**Locality is weaker than Haag duality.** Locality says observables in spacelike separated regions commute. Haag duality says the algebra of a region is exactly the commutant of the algebra of its causal complement, which is a stronger completeness condition.

**Fields are not automatically observables.** Pointlike or gauge-dependent fields can help generate or describe a net, but the algebraic primitive is the observable algebra. This distinction is crucial in gauge theory and in theories with charged sectors.

**A vacuum representation is not the whole theory.** It is one physically important representation of the quasi-local algebra. Thermal states, charged sectors, and different phases may require inequivalent representations.

**A state is not automatically a vector in one universal Hilbert space.** The GNS construction turns a state into a vector in a representation built from that state. Different states can produce inequivalent representations.

**A superselection sector is not just a symmetry multiplet.** A sector records what the observable algebra can connect or cannot connect. In DHR theory this becomes a category of localized representations or endomorphisms.

**DHR theory does not cover every charge.** The original criterion requires bounded localization. Long-range electric charge, infraparticles, topological sectors, and low-dimensional braid sectors need modified selection criteria.

**Modular flow is not usually physical time.** It is an intrinsic automorphism group determined by an algebra and a state. Only in special cases, such as wedge algebras in the vacuum, is it a familiar spacetime symmetry.

**The split property is not sharp Hilbert-space factorization.** It gives a type I interpolation for nested regions with a collar. It does not say that $\mathcal H$ factorizes exactly across the boundary of a sharp region.

**Haag duality is not automatic from locality.** Locality gives $\mathcal M(\mathcal O)\subset\mathcal M(\mathcal O')'$. Haag duality is the stronger equality, and its failure can carry physical information.

**Additivity is not automatic from isotony.** Isotony says smaller regions give subalgebras of larger regions. Additivity says larger local algebras are generated by smaller ones.

**The time-slice axiom is not a finite measurement protocol.** It is an algebraic statement that Cauchy neighborhoods generate the algebra of a causal development. It does not say that finitely many measured numbers determine the future.

**The framework is not an existence proof.** The Haag–Kastler axioms provide a clean target for construction. They do not automatically construct the interacting continuum theory associated with an arbitrary Lagrangian.

## Boundaries

This chapter does:

- define local nets of observable algebras;
- state and explain the Haag–Kastler axioms;
- separate structural net axioms from representation-dependent assumptions;
- prepare the language of states, GNS representations, sectors, DHR endomorphisms, modular theory, split inclusions, Haag duality, dual nets, additivity, and time-slice dynamics;
- connect algebraic locality to Wightman locality and Euclidean reconstruction.

This chapter does not try to do:

- teach all of operator algebra theory from scratch;
- replace the Wightman or Osterwalder–Schrader frameworks;
- prove existence of four-dimensional interacting gauge-theory nets;
- give a full treatment of locally covariant QFT on curved spacetimes.

Those topics belong to later pages in this volume and, for mathematical prerequisites, to the Mathematical Toolkit volume.

## Where to go next

After this chapter, the natural next step is Locally Covariant QFT. The page [QFT as a Functor on Spacetimes](/rigorous-qft/locally-covariant-qft/qft-as-functor-on-spacetimes/) turns the fixed-spacetime net idea into a functorial assignment over globally hyperbolic spacetimes.

## References

### Standard first pass

- Rudolf Haag and Daniel Kastler, "An Algebraic Approach to Quantum Field Theory," *Journal of Mathematical Physics* **5** (1964), 848–861. [doi:10.1063/1.1704187](https://doi.org/10.1063/1.1704187).
- Rudolf Haag, *Local Quantum Physics: Fields, Particles, Algebras*, 2nd ed., Springer, 1996. [doi:10.1007/978-3-642-61458-3](https://doi.org/10.1007/978-3-642-61458-3).
- Huzihiro Araki, *Mathematical Theory of Quantum Fields*, Oxford University Press, 1999. Oxford Academic: [Mathematical Theory of Quantum Fields](https://academic.oup.com/book/54810).

### Deeper references

- Christopher J. Fewster and Kasia Rejzner, "Algebraic Quantum Field Theory – an introduction," arXiv: [1904.04051](https://arxiv.org/abs/1904.04051).
- Romeo Brunetti, Claudio Dappiaggi, Klaus Fredenhagen, and Jakob Yngvason, eds., *Advances in Algebraic Quantum Field Theory*, Springer, 2015. [doi:10.1007/978-3-319-21353-8](https://doi.org/10.1007/978-3-319-21353-8).
- Christopher J. Fewster and Rainer Verch, "Algebraic Quantum Field Theory in Curved Spacetimes," in *Advances in Algebraic Quantum Field Theory*, 2015. [doi:10.1007/978-3-319-21353-8_4](https://doi.org/10.1007/978-3-319-21353-8_4), arXiv: [1504.00586](https://arxiv.org/abs/1504.00586).
- Detlev Buchholz and Klaus Fredenhagen, "Algebraic Quantum Field Theory: Objectives, Methods, and Results," arXiv: [2305.12923](https://arxiv.org/abs/2305.12923).
- Sergio Doplicher, Rudolf Haag, and John E. Roberts, "Local observables and particle statistics I," *Communications in Mathematical Physics* **23** (1971), 199–230. [doi:10.1007/BF01877742](https://doi.org/10.1007/BF01877742).
- Sergio Doplicher, Rudolf Haag, and John E. Roberts, "Local observables and particle statistics II," *Communications in Mathematical Physics* **35** (1974), 49–85. [doi:10.1007/BF01646454](https://doi.org/10.1007/BF01646454).
- Sergio Doplicher and John E. Roberts, "Why there is a field algebra with a compact gauge group describing the superselection structure in particle physics," *Communications in Mathematical Physics* **131** (1990), 51–107. [doi:10.1007/BF02097680](https://doi.org/10.1007/BF02097680).
- M. Takesaki, *Tomita's Theory of Modular Hilbert Algebras and its Applications*, Lecture Notes in Mathematics **128**, Springer, 1970. [doi:10.1007/BFb0065832](https://doi.org/10.1007/BFb0065832).
- Joseph J. Bisognano and Eyvind H. Wichmann, "On the duality condition for a Hermitian scalar field," *Journal of Mathematical Physics* **16** (1975), 985–1007. [doi:10.1063/1.522605](https://doi.org/10.1063/1.522605).

## Version history

- **2026-06-29:** Updated reading path, landmarks, common confusions, and handoff after adding additivity and the time-slice axiom.
- **2026-06-29:** Updated reading path, landmarks, and common confusions after adding split property and Haag duality pages.
- **2026-06-29:** Updated reading path, landmarks, and common confusions after adding DHR theory and modular theory pages.
- **2026-06-28:** Updated reading path and landmarks after adding the pages on states/GNS representations and superselection sectors.
- **2026-06-28:** Updated reading path and landmarks after adding the pages on isotony/locality/covariance and vacuum representations.
- **2026-06-28:** Initial chapter overview created with the first two Algebraic QFT pages.
