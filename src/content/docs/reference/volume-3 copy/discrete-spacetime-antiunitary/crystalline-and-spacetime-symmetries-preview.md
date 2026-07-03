---
title: "Crystalline and Spacetime Symmetries Preview"
description: "Introduces spacetime and crystalline symmetries in QFT, emphasizing coordinate action, field-index action, stress tensors, lattice momentum, defects, orientation reversal, and topological-phase caveats."
sidebar:
  label: "Crystalline Symmetries"
  order: 7
level: Advanced
status: "Polished draft"
source: "Weinberg Vol. I on Poincaré symmetry and projective representations; Coleman–Mandula theorem; condensed-matter field theory treatments of lattice and crystalline symmetry; modern crystalline-SPT literature."
topics:
  - spacetime symmetry
  - crystalline symmetry
  - space groups
  - translations
  - rotations
  - reflection symmetry
  - lattice momentum
  - stress tensor
  - defects
  - topological crystalline phases
canonicalTopics:
  - spacetime-symmetry
  - crystalline-symmetry
  - space-group
  - lattice-translation
  - point-group
  - stress-tensor-ward-identity
  - crystalline-defects
  - topological-crystalline-phase
researchStatus:
  established:
    - "Spacetime symmetries act on positions as well as field indices; continuous translations and Lorentz rotations lead to stress-tensor and angular-momentum Ward identities."
    - "Crystalline symmetries are discrete spatial symmetries, so they usually imply selection rules and defect data rather than local Noether currents."
  active:
    - "Crystalline symmetries remain active in QFT through crystalline SPT/SET phases, defect networks, fracton and subsystem structures, crystalline equivalence principles and their limitations, and anomalies involving orientation-reversing symmetries."
---

## Summary

Spacetime symmetries are symmetries that move the point where an operator lives. Internal symmetries act like

$$
\text{operator at }x\quad\longmapsto\quad\text{operator at the same }x,
$$

while spacetime symmetries act like

$$
\text{operator at }x\quad\longmapsto\quad\text{operator at }g\cdot x.
$$

This single difference changes almost everything. It changes the Ward identities, the meaning of charges, the definition of representations, the role of stress tensors, and the topology of possible background fields.

Crystalline symmetries are discrete spatial symmetries such as lattice translations, rotations, reflections, inversions, glide reflections, and screw rotations. They are ubiquitous in condensed matter and increasingly important in modern QFT because they organize lattice theories, topological crystalline phases, defects, anomalies, and continuum limits.

<figure class="doc-figure" style="--figure-width: 46rem;">

![Crystalline and spacetime symmetry map showing coordinate action, field-index action, lattice and point-group data, momentum selection rules, defects, topological phases, and orientation-reversing data.](/figures/symmetry-anomalies-topology/crystalline-spacetime-symmetry-map.svg)

<figcaption>

A spacetime or crystalline symmetry has two pieces of data: it moves the support of operators, $x\mapsto g\cdot x$, and it may rotate field indices by a matrix $D(g)$. For crystals, the group data include a translation lattice, a point group, and sometimes nonsymmorphic operations. Defects such as dislocations and disclinations are the geometric cousins of background gauge fields.

</figcaption>
</figure>

This page is a preview. It gives the vocabulary needed before later pages on spin structures, discrete anomalies, higher-form symmetries, topological response, matter phases, and symmetry TFT. The main lesson is simple:

$$
\text{spacetime symmetry is geometry, not just another internal group label.}
$$

## Prerequisites

Read [Internal Versus Spacetime Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/internal-versus-spacetime-symmetries/), [Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/parity/), [Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/time-reversal/), and [Reflection Positivity and Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/reflection-positivity-and-time-reversal/) first. The background-field chapter is also useful, especially [Background Fields Versus Dynamical Gauge Fields](/symmetry-anomalies-topology/background-fields-and-gauging/background-fields-versus-dynamical-gauge-fields/) and [Global Form of Symmetry Groups](/symmetry-anomalies-topology/background-fields-and-gauging/global-form-of-symmetry-groups/).

The mathematical prerequisites are basic group actions, lattices, quotient groups, and representations. No crystallography is assumed beyond the idea that a crystal has a discrete translation lattice.

## Core idea

An internal symmetry is usually encoded by a group $G$ acting on fields or operators at a fixed spacetime point. A spacetime symmetry is instead a group acting on spacetime itself.

For a local operator multiplet $\mathcal O_i(x)$, a schematic transformation law is

$$
U(g)\mathcal O_i(x)U(g)^{-1}
=\sum_j D_i{}^j(g)\mathcal O_j(g\cdot x).
$$

Here $g\cdot x$ is the transformed point, and $D(g)$ is the representation acting on spin, tensor, or internal indices. Different authors place inverses differently depending on whether the transformation is active or passive. The invariant content is that the operator's **support moves**.

For a scalar under a translation $a$,

$$
U(a)\phi(x)U(a)^{-1}=\phi(x+a).
$$

For a Lorentz transformation, a scalar obeys

$$
U(\Lambda)\phi(x)U(\Lambda)^{-1}=\phi(\Lambda x),
$$

while a vector obeys schematically

$$
U(\Lambda)V^\mu(x)U(\Lambda)^{-1}
=\Lambda^\mu{}_\nu V^\nu(\Lambda x),
$$

again up to the active/passive convention.

The field-index matrix $D(g)$ is not optional. A rotation does not only move a vector field to a rotated point; it also rotates its components.

:::note[Convention-sensitive source note]
Spacetime-symmetry formulas are a minefield of inverses. Some sources write $U(g)\mathcal O(x)U(g)^{-1}=D(g^{-1})\mathcal O(gx)$, others write the equivalent passive version with $g^{-1}x$. When comparing formulas, first ask: is $g$ acting actively on the physical configuration, passively on coordinates, or on test functions? Selection rules and Ward identities do not depend on this bookkeeping choice.
:::

## Continuous spacetime symmetries

In relativistic QFT on flat Minkowski spacetime, the standard continuous spacetime symmetry is the Poincaré group,

$$
\text{Poincaré}=\text{translations}\rtimes\text{Lorentz transformations}.
$$

Translations are generated by the momentum operators $P_\mu$:

$$
U(a)=e^{ia^\mu P_\mu}.
$$

Lorentz transformations are generated by angular momentum and boost generators $J_{\mu\nu}$.

The conserved current associated with translations is the stress tensor,

$$
\partial_\mu T^{\mu\nu}=0,
$$

when the theory is translationally invariant and there are no explicit spacetime-dependent sources. Lorentz invariance gives conservation of angular momentum current,

$$
M^{\lambda\mu\nu}=x^\mu T^{\lambda\nu}-x^\nu T^{\lambda\mu}+S^{\lambda\mu\nu},
$$

where $S^{\lambda\mu\nu}$ is the spin current. After improving the stress tensor, one often works with a symmetric stress tensor and absorbs the spin-current contribution.

The Ward identity for translations is the ancestor of many later formulas. In the presence of local operators,

$$
\partial_\mu\langle T^{\mu\nu}(x)\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
$$

is not simply zero as an ordinary function. It contains contact terms at $x=x_i$ that translate the insertions. These are spacetime-symmetry contact terms, not internal-charge contact terms.

## Internal versus spacetime groups

The difference between internal and spacetime symmetries is not just semantic.

For an internal symmetry generated by $Q^a$,

$$
[P_\mu,Q^a]=0
$$

in a relativistic theory with unbroken translations. This means internal charges do not move local operators through spacetime; they change labels at the same point.

For Lorentz generators,

$$
[J_{\mu\nu},P_\rho]
=i(\eta_{\nu\rho}P_\mu-\eta_{\mu\rho}P_\nu).
$$

Thus spacetime generators do not commute with translations. They transform momentum itself.

This algebraic fact is the beginning of the Coleman–Mandula story. Under assumptions involving a nontrivial analytic $S$-matrix, mass gap, and finitely many particle species below any mass, internal and spacetime symmetries cannot mix in arbitrary exotic ways. Supersymmetry evades the theorem by using fermionic generators; conformal symmetry changes the spacetime group; low-dimensional, topological, nonrelativistic, and non-particle settings can evade or modify the assumptions.

For this volume, the practical lesson is simpler:

$$
\text{do not treat spacetime symmetry as an ordinary onsite internal symmetry unless you have justified the reduction.}
$$

## Crystalline symmetry data

A crystal does not have the full continuous translation and rotation symmetry of Euclidean space. It has a discrete subgroup. In $d$ spatial dimensions, the translation lattice is

$$
\Lambda=\left\{n^ia_i\mid n^i\in\mathbb Z\right\},
$$

where $a_i$ are primitive lattice vectors.

A space group $G_{\text{space}}$ fits into an exact sequence

$$
1\longrightarrow\Lambda\longrightarrow G_{\text{space}}
\longrightarrow P\longrightarrow1,
$$

where $P$ is the point group, the finite group of rotations, reflections, and inversions preserving the lattice up to translations.

If the sequence splits, the space group is symmorphic:

$$
G_{\text{space}}\simeq \Lambda\rtimes P.
$$

If it does not split, the crystal has nonsymmorphic operations such as glides and screws. A glide reflection is reflection plus a fractional translation. A screw rotation is rotation plus a fractional translation. These fractional translations can force protected band degeneracies and projective-looking representation data at special momenta.

This is already a warning: crystalline symmetry is not just a finite point group. The translation lattice and the extension data matter.

## Momentum and selection rules on a lattice

For a continuous translation symmetry, momentum is conserved as an ordinary vector. For a lattice translation symmetry, only crystal momentum is conserved, and it is defined modulo a reciprocal lattice vector.

If $a\in\Lambda$, then a momentum eigenstate obeys

$$
U(a)|\mathbf k,\alpha\rangle
=e^{i\mathbf k\cdot a}|\mathbf k,\alpha\rangle.
$$

The same phase is obtained for

$$
\mathbf k\sim\mathbf k+\mathbf G,
$$

where $\mathbf G$ belongs to the reciprocal lattice $\Lambda^*$ and satisfies

$$
\mathbf G\cdot a\in2\pi\mathbb Z
\qquad
\text{for all }a\in\Lambda.
$$

Therefore a lattice correlation function or scattering process obeys a selection rule of the form

$$
\mathbf k_1+\cdots+\mathbf k_n=\mathbf G
$$

rather than strict equality to zero. The nonzero reciprocal lattice vector represents Umklapp momentum transfer to the lattice.

This is one of the simplest places where replacing continuous spacetime symmetry by crystalline symmetry changes the physics without changing the local-looking operator algebra too dramatically.

## Noether currents and their absence

Continuous symmetries have local currents. Discrete symmetries usually do not.

Thus continuous translations give the stress tensor $T^{\mu\nu}$, and continuous rotations give angular momentum currents. But a lattice translation by one unit cell is discrete. It imposes selection rules, representation constraints, and background-defect data, but not a conserved Noether current localized in the same way.

This distinction matters when taking continuum limits. A lattice theory can flow to an infrared fixed point with emergent continuous rotation or Lorentz symmetry. At the microscopic level, only the crystalline subgroup is exact. At the fixed point, additional continuous spacetime symmetry may emerge because symmetry-breaking operators are irrelevant.

For example, a rotationally non-invariant lattice regulator can flow to a rotationally invariant continuum QFT. The exact microscopic symmetry is the lattice point group; the infrared symmetry can be larger.

The reverse can also happen: a continuum effective theory may accidentally look rotationally invariant at leading order, while irrelevant anisotropic operators remember the underlying crystal.

## Orientation reversal and antiunitarity

A spatial reflection is usually unitary in Lorentzian quantum mechanics: it reverses an odd number of spatial coordinates but does not reverse time. Time reversal is antiunitary because it reverses time evolution.

So why do crystalline papers sometimes say that orientation-reversing crystalline symmetries behave like antiunitary internal symmetries?

The reason is subtle and context-dependent. In Euclidean spacetime or in topological phases, orientation reversal of space can act on the path integral in a way analogous to complex conjugation, especially for topological actions whose integrals change sign under orientation reversal. In some classification frameworks, a crystalline symmetry operation that reverses orientation is mapped to an internal antiunitary symmetry in an auxiliary problem.

This is a powerful idea, but it is not a license to declare every mirror symmetry antiunitary in the microscopic Hilbert space. In ordinary Lorentzian Hamiltonian language, a spatial mirror is usually represented unitarily. The antiunitary replacement belongs to a Euclidean/topological classification dictionary and must be used with its hypotheses attached.

A good operational test is to ask:

$$
\text{does the symmetry reverse the physical time evolution operator }e^{-iHt}?
$$

If yes, antiunitarity is expected. If no, the microscopic Hilbert-space symmetry is usually unitary, although its Euclidean or topological avatar may involve orientation reversal and complex conjugation.

## Spin, Pin, and reflection data

Fermions force additional structure. On an oriented spacetime, spinors require a spin structure. If orientation-reversing symmetries such as reflections are present, one often needs Pin structures instead.

Roughly:

- Spin structures let spinors live consistently on oriented manifolds.
- Pin structures let spinors live consistently when reflections are allowed.
- Different Pin choices encode different possible squares of reflection or time-reversal-like operations on fermions.

This is why the square of a reflection symmetry is not always the naive identity on fermions. It may equal fermion parity,

$$
R^2=(-1)^F,
$$

or have another projective realization depending on dimension and convention.

These distinctions are invisible in purely bosonic point-particle drawings of crystals but become essential in fermionic QFT, topological superconductors, and anomaly classifications.

The later page [Spin Structures and Fermion Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/spin-structures-and-fermion-parity/) will make this precise. For now, remember the warning:

$$
\text{reflections acting on fermions require extra global data.}
$$

## Crystalline defects as background geometry

For internal symmetries, background fields are gauge fields. For spacetime and crystalline symmetries, background fields are geometric.

Continuous translations and rotations couple to the vielbein, metric, and spin connection. Curvature and torsion measure geometric defects. In a crystal, the analogous defects have physical names:

| Defect | Geometric meaning | Symmetry data |
|---|---|---|
| dislocation | missing or extra half-plane | translation holonomy, Burgers vector |
| disclination | angular wedge defect | rotation holonomy |
| domain wall | interface between symmetry-related regions | defect operator or wall data |
| mirror plane defect | fixed locus of reflection | orientation-reversing data |

A dislocation is a background for lattice translations in much the same way that a flux tube is a background for an internal $U(1)$ symmetry. If a particle encircles a dislocation, it can acquire a phase determined by its crystal momentum:

$$
\text{phase}=e^{i\mathbf k\cdot b},
$$

where $b$ is the Burgers vector.

This is the doorway to a more geometric view of crystalline symmetry: instead of only asking how operators transform in a perfect crystal, one asks how the theory behaves on manifolds or lattices with crystalline defects.

## Crystalline topological phases

Topological crystalline phases are phases protected or enriched by spatial symmetries. Unlike ordinary internal-symmetry SPT phases, their protecting symmetry moves points in space. This creates two competing instincts:

1. treat the spatial symmetry geometrically, using defects and lattice backgrounds;
2. map the problem to an internal-symmetry classification when possible.

A modern result known as the crystalline equivalence principle says, under important hypotheses, that certain topological crystalline phases in Euclidean space can be classified like internal-symmetry protected phases with the same group, with orientation-reversing spatial elements treated as antiunitary in the internal problem.

This is a beautiful shortcut, but it is not a universal theorem for all systems one might call “crystalline.” It is designed for particular topological phases and assumptions about crystalline topological liquids. Weak free-fermion phases, subsystem symmetries, gapless phases, fragile topology, disorder, and microscopic lattice constraints can require more care.

The safer conceptual statement is:

$$
\text{crystalline symmetry can sometimes be traded for internal symmetry after topology absorbs geometry.}
$$

The word “sometimes” is load-bearing. Tiny word, big bouncer energy.

## Spacetime symmetry breaking

Spacetime symmetries can be explicitly broken or spontaneously broken.

A crystal explicitly breaks continuous translations if it is introduced as a fixed external lattice potential. A physical solid formed by particles in empty space is better viewed as spontaneously breaking continuous translations and rotations down to a discrete space group. The associated Goldstone modes are phonons.

Spontaneous breaking of spacetime symmetries differs from internal symmetry breaking in several ways:

- broken generators do not always imply independent Goldstone modes;
- inverse Higgs constraints can relate candidate Goldstone fields;
- translations and rotations are linked by the spacetime algebra;
- the order parameter can be geometric, such as a density wave or lattice embedding.

This is why the Goldstone-counting story for internal symmetries is not enough for crystals, fluids, solids, and spacetime symmetry breaking. The SSB chapter gives the internal-symmetry baseline; later EFT pages will treat spacetime symmetry breaking more systematically.

## Crystalline symmetry and continuum QFT

A continuum QFT can interact with crystalline symmetry in three common ways.

First, the QFT may be a long-distance effective theory of a lattice model. Then crystalline symmetry is microscopic, and the continuum theory may have only the corresponding discrete rotations and translations exactly.

Second, the QFT may have emergent continuous spacetime symmetry. The classic example is emergent Lorentz or rotational invariance at a critical point, where lattice anisotropies are irrelevant.

Third, the QFT may be placed on a background with defects or boundaries preserving only a crystalline subgroup. For example, a relativistic CFT with a planar boundary preserves only the subgroup of conformal transformations that preserve the boundary.

The practical rule is:

$$
\text{always distinguish exact microscopic symmetry from emergent infrared symmetry.}
$$

Many wrong arguments in condensed matter and high-energy theory come from silently promoting an emergent symmetry to an exact microscopic one.

## Common pitfalls

**Treating spatial reflection as automatically antiunitary.** Physical time reversal is antiunitary. A spatial mirror is usually unitary in Lorentzian Hilbert space. Orientation-reversing crystalline symmetries can behave like antiunitary internal symmetries in Euclidean/topological classification dictionaries, but that is an additional framework, not a universal microscopic fact.

**Forgetting that spacetime symmetries move operators.** A field transforming under a rotation does not only rotate its components; its argument also moves.

**Ignoring nonsymmorphic data.** A space group is not always just translations semidirect point group. Glides and screws can carry essential fractional translation data.

**Replacing lattice momentum by ordinary momentum.** Crystal momentum is defined modulo reciprocal lattice vectors. Umklapp processes are not violations of symmetry.

**Assuming every discrete symmetry has a Noether current.** Discrete translations and point-group symmetries impose selection rules and representation constraints, but not local Noether currents.

**Confusing emergent and exact symmetry.** A lattice model may have emergent Lorentz invariance in the infrared. That does not mean Lorentz symmetry is exact at the cutoff scale.

**Forgetting spin and Pin data.** Reflection actions on fermions are not fully specified by the point group alone. Global fermion-parity and Pin-structure data can matter.

## Relations to other pages

[Internal Versus Spacetime Symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/internal-versus-spacetime-symmetries/) gives the first distinction between fixed-point internal actions and coordinate-moving spacetime actions. This page extends that distinction to lattices and spatial groups.

[Parity](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/parity/) treats spatial inversion in relativistic field theory. Crystalline mirrors and inversions are discrete spatial symmetries of the same family, but with lattice and defect data added.

[Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/time-reversal/) and [Antiunitary Symmetries](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/antiunitary-symmetries/) explain why time reversal is antiunitary. That is essential before reading crystalline-equivalence statements that trade orientation-reversing spatial symmetries for antiunitary internal ones.

[Reflection Positivity and Time Reversal](/symmetry-anomalies-topology/discrete-spacetime-antiunitary/reflection-positivity-and-time-reversal/) explains the Euclidean reflection viewpoint, which is often the natural language for orientation-reversing crystalline and topological phases.

[Topological Terms](/symmetry-anomalies-topology/topological-terms/) and [Symmetry in Phases of Matter](/symmetry-anomalies-topology/symmetry-in-phases-of-matter/) are the natural later homes for crystalline topological response.

## Research status

The basic group theory of spacetime and crystalline symmetries is established. Space groups, point groups, reciprocal lattices, projective representations, and selection rules are classical material.

The QFT interpretation is still lively. Modern research studies crystalline SPT and SET phases, defect-network descriptions, crystalline equivalence principles, higher-order topological phases, subsystem and fracton-like structures, lattice anomalies, and orientation-reversing fermionic symmetries. The subject is mature enough to teach cleanly, but not so settled that every slogan should be trusted without hypotheses.

For this volume, the most important research-facing lesson is that spacetime symmetry cannot always be gauged or background-coupled like an internal symmetry. Sometimes it becomes geometry. Sometimes it becomes topology. Sometimes it becomes a defect network. And sometimes it refuses to be domesticated, which is rude but pedagogically useful.

## Exercises

### Exercise 1: Crystal-momentum selection rule

Let a lattice translation by $a\in\Lambda$ act on operators by

$$
U(a)\mathcal O_i(\mathbf k_i)U(a)^{-1}
=e^{i\mathbf k_i\cdot a}\mathcal O_i(\mathbf k_i).
$$

Show that a nonzero correlator

$$
\langle\mathcal O_1(\mathbf k_1)\cdots\mathcal O_n(\mathbf k_n)\rangle
$$

requires $\sum_i\mathbf k_i$ to be a reciprocal lattice vector.

<details><summary><strong>Solution</strong></summary>

Translation invariance implies the correlator equals its translated version:

$$
\langle\mathcal O_1\cdots\mathcal O_n\rangle
=e^{ia\cdot\sum_i\mathbf k_i}
\langle\mathcal O_1\cdots\mathcal O_n\rangle
$$

for every $a\in\Lambda$. If the correlator is nonzero, then

$$
e^{ia\cdot\sum_i\mathbf k_i}=1
$$

for every lattice vector $a$. By definition, this means

$$
\sum_i\mathbf k_i\in\Lambda^*,
$$

where $\Lambda^*$ is the reciprocal lattice. Thus crystal momentum is conserved modulo a reciprocal lattice vector.

</details>

### Exercise 2: Why there is no Noether current for a one-site translation

Explain why a discrete lattice translation symmetry has no local Noether current, while an emergent continuous translation symmetry does.

<details><summary><strong>Solution</strong></summary>

Noether's theorem applies to continuous families of transformations depending on an infinitesimal parameter. A one-site lattice translation is a discrete operation; there is no infinitesimal parameter that can be localized as $a\to a(x)$ to extract a current.

If the long-distance theory has emergent continuous translations, then infinitesimal translations exist in the effective theory. Their Noether current is the stress tensor $T^{\mu\nu}$. This current belongs to the emergent continuum symmetry, not to the microscopic discrete translation alone.

</details>

### Exercise 3: Symmorphic versus nonsymmorphic

A two-dimensional operation sends

$$
(x,y)\mapsto(x+1/2,-y)
$$

in units where a lattice translation by $x\mapsto x+1$ is allowed. Is this a pure mirror? What happens when the operation is squared?

<details><summary><strong>Solution</strong></summary>

The operation is a glide reflection: a mirror $y\mapsto-y$ followed by a half-lattice translation in the $x$ direction. Squaring gives

$$
(x,y)\mapsto(x+1,y),
$$

which is a full lattice translation. Therefore this operation is not simply an order-two mirror. Its fractional translation data can affect representations, especially at crystal momenta where the translation phase is nontrivial.

</details>

### Exercise 4: Mirror versus time reversal

Why is a spatial mirror usually represented unitarily in Lorentzian Hilbert space, while time reversal is antiunitary?

<details><summary><strong>Solution</strong></summary>

A spatial mirror reverses one or more spatial coordinates but does not reverse the sign of physical time. It does not need to turn

$$
e^{-iHt}\quad\text{into}\quad e^{+iHt}.
$$

Therefore it can be represented by a unitary operator.

Time reversal does reverse time evolution. If $\mathsf T H\mathsf T^{-1}=H$, then to obtain

$$
\mathsf T e^{-iHt}\mathsf T^{-1}=e^{+iHt},
$$

one needs

$$
\mathsf T i\mathsf T^{-1}=-i.
$$

That is the defining anti-linearity of an antiunitary operator.

</details>

## References

- S. Weinberg, *The Quantum Theory of Fields*, Vol. I, especially the discussion of symmetries, Poincaré representations, inversions, and projective representations.
- S. Coleman and J. Mandula, “All Possible Symmetries of the S Matrix,” *Physical Review* **159** (1967).
- A. Altland and B. Simons, *Condensed Matter Field Theory*, especially the discussions of symmetry breaking, topological field theory, and gauge-theoretic viewpoints in matter systems.
- C. P. Burgess, *Introduction to Effective Field Theory*, especially nonlinear realization, spacetime symmetry breaking, and effective theories for many-body systems.
- R. Thorngren and D. V. Else, “Gauging Spatial Symmetries and the Classification of Topological Crystalline Phases,” arXiv:1612.00846.
- D. V. Else and R. Thorngren, “Crystalline Topological Phases as Defect Networks,” arXiv:1810.10539.
- K. Shiozaki, C. Z. Xiong, and K. Gomi, related work on crystalline symmetry, generalized homology, and fermionic crystalline phases.
- M. Barkeshli, P. Bonderson, M. Cheng, and Z. Wang, work on symmetry, defects, and topological phases with spatial symmetry.

## Version history

- 2026-06-17: Initial polished preview for the Discrete, Spacetime, and Antiunitary Symmetries chapter.
