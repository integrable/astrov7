---
title: "Why Holography?"
description: "Why AdS/CFT matters for quantum gravity, strongly coupled quantum field theory, black holes, and emergent spacetime."
sidebar:
  order: 10
---

The best way to learn AdS/CFT is not to begin with a dictionary table. A dictionary is useful only after one knows why such a dictionary should exist. The deeper question is this:

**Why should a quantum theory without gravity know everything about a gravitational spacetime in one higher dimension?**

At first sight, that sounds implausible. A quantum field theory appears to live on a fixed spacetime. A gravitational theory has a dynamical spacetime. A field theory has local operators such as $\mathcal O(x)$. A gravitational theory has geometry, horizons, causal structure, and black holes. Why should these be the same kind of object?

AdS/CFT says that, in special but extremely important examples, they are not merely related. They are two descriptions of the same quantum system.

The slogan is

$$
\text{quantum gravity in asymptotically AdS spacetime}
\quad
\longleftrightarrow
\quad
\text{large-}N\text{ quantum field theory on the boundary}.
$$

This page explains why this slogan is natural, why it is powerful, and why Anti-de Sitter space is the cleanest laboratory in which it becomes precise.

<figure class="doc-figure" style="--figure-width: 52rem;">

![A schematic map of holography: a boundary quantum field theory is equivalent to a bulk gravitational theory in asymptotically AdS spacetime.](/figures/course/holography-big-picture.svg)

<figcaption>

The same quantum system admits two descriptions. The boundary description is a large-$N$ quantum field theory with sources $J(x)$ and operators $\mathcal O(x)$. The bulk description is a gravitational theory in asymptotically AdS spacetime, where boundary values of fields act as sources and the radial direction is tied to field-theory scale.

</figcaption>
</figure>

## Three problems that become one

AdS/CFT became central because it connects three hard problems that, before holography, looked rather different.

First, **quantum gravity needs a nonperturbative definition**. General relativity is an excellent classical theory, but perturbative quantum gravity around a fixed background is not a complete ultraviolet description in four spacetime dimensions. The coupling $G_N$ has negative mass dimension, so higher-loop divergences require an infinite tower of counterterms unless some new structure enters. String theory improves the ultraviolet behavior, but then one still wants a nonperturbative definition: what is the Hilbert space, what are the exact observables, and what does it mean to sum over quantum geometries?

Second, **strongly coupled quantum field theory needs nonperturbative tools**. A gauge theory may be easy at weak coupling but hard at strong coupling. Perturbation theory in $g_{\mathrm{YM}}$ fails precisely where interesting phenomena such as confinement, transport, thermalization, and collective behavior often live. Lattice methods are powerful in Euclidean signature but are less direct for real-time dynamics, finite density, and questions involving analytic continuation.

Third, **black holes suggest that gravity counts degrees of freedom differently from ordinary local field theory**. A local quantum field theory with a fixed ultraviolet cutoff seems to assign degrees of freedom to volume. A black hole, however, carries an entropy proportional to the area of its horizon:

$$
S_{\mathrm{BH}}
=
\frac{A_{\mathrm{hor}}}{4G_N\hbar}
$$

in units with $c=k_B=1$. The entropy of the most gravitationally extreme object in a region scales like area, not volume. This is the original physical seed of the holographic principle.

AdS/CFT gives a precise answer in a controlled setting. The degrees of freedom of the gravitational theory are encoded in a non-gravitational quantum theory living on a lower-dimensional boundary. Conversely, the strongly coupled boundary theory can sometimes be solved by doing classical geometry in the bulk.

That is the magic trick. But it is not magic. It is a duality.

## Duality, not analogy

A duality is not a vague resemblance between two theories. It is an equivalence between two descriptions that use different variables.

A familiar example is electric-magnetic duality. In one description, electrically charged variables may be fundamental; in another, magnetically charged variables may be simpler. Neither description is “more real” in an absolute sense. Each is useful in a different regime.

AdS/CFT is much more dramatic. One description has gravity and one more spatial-like direction. The other description has no dynamical gravity and lives on the boundary. The claim is not that the boundary theory approximates the bulk, or that the bulk is a visual metaphor for the boundary. The claim is that the two descriptions compute the same observables.

The practical form of the statement is the equality of generating functionals:

$$
Z_{\mathrm{CFT}}[J]
=
Z_{\mathrm{bulk}}[\phi \to J].
$$

Here $J$ is a source for a boundary operator $\mathcal O$, and $\phi$ is the dual bulk field whose boundary value is fixed by $J$. In the classical gravity limit, this becomes

$$
Z_{\mathrm{CFT}}[J]
\approx
\exp\!\left(-S_{\text{ren,on-shell}}[J]\right).
$$

The left-hand side is a quantum field theory object. The right-hand side is a gravitational on-shell action. This is the computational bridge that much of the course will build, regulate, and use.

## Why quantum gravity wanted holography

The black-hole entropy formula is one of the strongest clues that quantum gravity is not an ordinary local quantum field theory of gravitons.

Consider a region of characteristic size $R$. In nongravitational local QFT with a short-distance cutoff $a$, the number of independent cells scales roughly like

$$
\#\text{cells} \sim \left(\frac{R}{a}\right)^d
$$

for $d$ spatial dimensions. Entropy then naturally scales like volume.

Gravity changes this reasoning. If one puts too much energy into a region, the region collapses into a black hole. The maximum entropy of the region is then bounded by an area:

$$
S_{\max}
\lesssim
\frac{A}{4G_N\hbar}.
$$

This suggests that a complete quantum theory of gravity should not assign independent fundamental degrees of freedom to every bulk point in the naive way. Bulk locality, if it emerges, must be approximate and redundant.

AdS/CFT realizes this idea sharply. The fundamental nonperturbative description is a quantum theory on the boundary. The bulk radial direction, local bulk fields, and even parts of the bulk geometry emerge from the organization of boundary degrees of freedom.

This is not the same as saying that the bulk is fake. Effective fields inside AdS can be as real and predictive as phonons in a crystal or gluons in a perturbative description of QCD. The point is that their locality and gravitational dynamics are emergent properties of a deeper description.

## Why strongly coupled QFT wanted gravity

The other direction is equally important. Holography is not only a statement about quantum gravity; it is also a tool for quantum field theory.

Suppose a boundary theory is strongly coupled. A direct perturbative expansion in $g_{\mathrm{YM}}$ is not reliable. In certain large-$N$ CFTs, however, the dual bulk description becomes weakly coupled. In the best-controlled regime, the strongly coupled quantum field theory is described by classical gravity.

The inversion of difficulty is the useful part:

$$
\text{strongly coupled large-}N\text{ QFT}
\quad
\longleftrightarrow
\quad
\text{weakly coupled classical gravity}.
$$

This does not mean every strongly coupled system has a simple gravitational dual. It means that a special and important class of strongly coupled large-$N$ theories does. In those theories, hard field-theory questions become geometric questions.

For example:

| Field-theory question | Bulk question |
|---|---|
| What is the thermal entropy? | What is the area of the black-hole horizon? |
| What is the stress tensor? | What is the asymptotic behavior of the metric? |
| What is a retarded Green's function? | How does a wave fall into an AdS black brane? |
| What is the entanglement entropy of a region? | What is the area of an extremal surface? |
| What is an RG flow? | How does the geometry vary along the radial direction? |

This is why AdS/CFT is both a theory of quantum gravity and a method for studying strongly coupled quantum matter.

## Why large $N$ is the bridge

The appearance of gravity is not random. It is tied to large-$N$ gauge theory.

Let $N$ be the rank of a gauge group, for example $SU(N)$, and define the 't Hooft coupling

$$
\lambda = g_{\mathrm{YM}}^2 N.
$$

In the 't Hooft large-$N$ limit, one takes

$$
N\to\infty,
\qquad
\lambda \;\text{fixed}.
$$

Perturbative diagrams of adjoint fields can be drawn using double-line notation. Their scaling is organized by topology:

$$
\mathcal A
=
\sum_{g=0}^{\infty} N^{2-2g} F_g(\lambda),
$$

where $g$ is the genus of the surface on which the diagram can be drawn. The leading terms are planar diagrams, and nonplanar diagrams are suppressed by powers of $1/N^2$.

This resembles the perturbative expansion of a closed string theory:

$$
\mathcal A_{\mathrm{string}}
=
\sum_{g=0}^{\infty} g_s^{2g-2}\,\mathcal F_g.
$$

The comparison suggests

$$
g_s \sim \frac{1}{N}
$$

up to convention-dependent powers and coupling factors. This is the first hint that large-$N$ gauge theories secretly contain string theories.

AdS/CFT makes the hint concrete. In the canonical example, the string theory is type IIB string theory on $\mathrm{AdS}_5\times S^5$, and the gauge theory is four-dimensional $\mathcal N=4$ super-Yang–Mills theory.

The emergence of classical gravity requires two simplifications:

$$
N \gg 1
\quad\text{and}\quad
\lambda \gg 1.
$$

Large $N$ suppresses quantum loops in the bulk. Large $\lambda$ makes the curvature radius large compared with the string length, suppressing stringy corrections. Thus classical gravity is a double limit of a more complete string/QFT duality.

## Why Anti-de Sitter space?

Holography is a broad idea, but AdS is where it is best understood. There are several reasons.

### AdS has a natural boundary

In Poincaré coordinates, empty $\mathrm{AdS}_{d+1}$ can be written as

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2 + \eta_{\mu\nu}dx^\mu dx^\nu
\right),
\qquad z>0.
$$

The boundary is at $z=0$. The metric diverges there, but after multiplying by the conformal factor $z^2/L^2$, one obtains the boundary metric $\eta_{\mu\nu}dx^\mu dx^\nu$. Thus the boundary geometry is defined only up to Weyl rescaling. This is exactly what one expects for a conformal field theory.

The boundary is not an ordinary wall at finite distance. It is a conformal boundary. Still, it is good enough to define boundary conditions, sources, conserved charges, and a precise variational problem.

### AdS has the right symmetry

The isometry group of $\mathrm{AdS}_{d+1}$ is

$$
SO(2,d),
$$

which is also the conformal group of $d$-dimensional Minkowski space. This is not a decorative coincidence. It is the simplest structural reason that gravity in AdS can be dual to a CFT.

At the level of symmetry, the match is

$$
\mathrm{Isom}(\mathrm{AdS}_{d+1})
=
\mathrm{Conf}(\mathbb R^{1,d-1}).
$$

The next pages will make this statement concrete.

### AdS behaves like a gravitational box

AdS has a timelike boundary. Light rays can reach the boundary and return in finite global time, so AdS behaves roughly like a reflecting box. This makes it possible to discuss equilibrium states, normal modes, and black holes in a controlled setting.

This is especially important for thermodynamics. Large AdS black holes can be in stable equilibrium with their radiation. That is very different from asymptotically flat Schwarzschild black holes, which have negative specific heat in the canonical ensemble.

### AdS appears from branes

The strongest reason is dynamical. AdS spaces arise as near-horizon geometries of branes in string theory. For $N$ coincident D3-branes, the near-horizon geometry is

$$
\mathrm{AdS}_5 \times S^5.
$$

The low-energy open-string degrees of freedom on the branes give $\mathcal N=4$ super-Yang–Mills theory. The low-energy closed-string description of the same branes gives the near-horizon gravitational background. The duality comes from identifying these two descriptions of the same underlying string-theoretic system.

This brane origin is the subject of the String Theory Origin unit. For now, the key point is that AdS/CFT was not guessed only from entropy slogans. It was discovered in a setting where string theory provides two controlled descriptions of one physical system.

## The radial direction as scale

One of the first conceptual surprises is that the extra bulk direction is related to energy scale in the boundary theory.

In Poincaré AdS,

$$
ds^2
=
\frac{L^2}{z^2}
\left(
 dz^2 + dx_\mu dx^\mu
\right).
$$

The coordinate $z$ has dimensions of length. Near $z=0$, one is close to the boundary. This region corresponds roughly to the ultraviolet of the boundary theory. Moving deeper into the bulk, toward larger $z$, corresponds roughly to moving toward the infrared.

A useful mnemonic is

$$
\mu \sim \frac{1}{z},
$$

where $\mu$ is a boundary energy scale. This relation is not a complete definition of holographic renormalization, but it captures the basic UV/IR connection:

$$
\text{near boundary}
\quad\longleftrightarrow\quad
\text{UV physics},
$$

$$
\text{deep interior}
\quad\longleftrightarrow\quad
\text{IR physics}.
$$

This is why RG flows in the field theory become radial evolution in the bulk, and why the asymptotic behavior of bulk fields encodes ultraviolet data such as sources, couplings, and operator dimensions.

## What holography computes

The central computational idea is simple to state.

Turn on a source $J(x)$ for a boundary operator $\mathcal O(x)$:

$$
Z_{\mathrm{CFT}}[J]
=
\left\langle
\exp\!\left(\int d^d x\, J(x)\mathcal O(x)\right)
\right\rangle.
$$

In the bulk, choose a field $\phi(z,x)$ whose boundary value is $J(x)$:

$$
\phi(z,x) \sim z^{d-\Delta}J(x)
\qquad
(z\to 0).
$$

Then solve the bulk equations of motion subject to that boundary condition. Insert the solution into the regulated and renormalized on-shell action. Functional derivatives with respect to $J$ give CFT correlators.

Schematically,

$$
\langle \mathcal O(x_1)\cdots \mathcal O(x_n)\rangle
=
\frac{\delta^n}{\delta J(x_1)\cdots \delta J(x_n)}
\log Z_{\mathrm{CFT}}[J]\bigg|_{J=0}.
$$

Using holography,

$$
\log Z_{\mathrm{CFT}}[J]
\approx
-S_{\text{ren,on-shell}}[J].
$$

This is the basic mechanism by which a geometric computation becomes a field-theory answer.

There are many refinements: Lorentzian signature requires real-time boundary conditions, gauge fields require careful treatment of constraints, the metric requires boundary terms, and fields near the Breitenlohner–Freedman bound may allow alternate quantization. These refinements are not technical annoyances; they are where the dictionary becomes precise.

## What makes the duality useful

AdS/CFT has several kinds of usefulness.

### It defines quantum gravity in AdS

A complete CFT is a nonperturbative quantum system. If the CFT has a gravitational dual, then the CFT defines the corresponding quantum gravity theory, including all finite-$N$ effects in principle.

This is conceptually powerful because the boundary theory does not require us to sum directly over arbitrary fluctuating geometries. The gravitational description emerges in a limit. The exact definition lives in ordinary quantum-mechanical language.

### It turns strong coupling into geometry

At large $N$ and strong 't Hooft coupling, some CFT observables can be computed by solving classical equations in one higher dimension. A difficult many-body quantum problem becomes a boundary-value problem in gravity.

For example, the entropy density of a thermal CFT with a planar black-brane dual is obtained from the horizon area. Transport coefficients are extracted from linearized perturbations of black-brane geometries. Entanglement entropies become areas of extremal surfaces.

### It geometrizes the renormalization group

The radial direction organizes scale dependence. Near-boundary expansions encode UV data. Interior boundary conditions encode IR physics. Domain-wall geometries describe RG flows triggered by relevant deformations.

This gives a geometric language for ideas that are often abstract in field theory.

### It teaches us how spacetime can emerge

The bulk is not simply placed on top of the boundary theory. Its locality, dimensionality, and causal structure are encoded in the pattern of CFT states and correlators. Large-$N$ factorization gives approximate bulk particles. Entanglement helps organize bulk regions. Quantum error correction explains why bulk information can be redundantly represented in the boundary theory.

These are modern lessons, but their roots are already visible in the basic dictionary.

## What holography does not automatically say

The power of AdS/CFT comes with boundaries of applicability. A good foundations course should state them early.

### It does not say that every QFT has a simple gravity dual

A generic QFT is not expected to have a weakly curved Einstein gravity dual. A simple bulk description requires special properties, including large $N$, strong coupling, and a sparse spectrum of low-dimension single-trace operators.

When these conditions fail, a dual may still exist in a broad stringy or quantum-gravitational sense, but it will not be captured by a small set of classical bulk fields.

### It does not directly solve real-world QCD

Holographic models can imitate some features of QCD, such as confinement, chiral symmetry breaking, or transport behavior. But QCD is neither conformal nor supersymmetric, and its gauge group has $N=3$. Some holographic models are top-down string constructions; others are bottom-up effective models. They can be useful, but one must not confuse usefulness with exact equivalence.

### It is not yet a complete theory of cosmology

AdS has a negative cosmological constant and a timelike conformal boundary. Our observed universe is closer to de Sitter at large scales. Holography beyond AdS is an active research area, but the cleanest and best-understood dictionary is still AdS/CFT.

### It does not make bulk locality fundamental

Bulk locality is approximate. It is excellent in the classical gravity regime, but it is not expected to survive unchanged at finite $N$, at string scale, near singularities, or in regimes where quantum gravitational effects are large.

This is a feature, not a flaw. One of the central lessons of holography is that locality itself can be emergent.

## A first regime diagram in words

The canonical example has three useful levels.

At the most complete level,

$$
\mathcal N=4\;\text{SYM with gauge group }SU(N)
\quad
\longleftrightarrow
\quad
\text{type IIB string theory on }\mathrm{AdS}_5\times S^5.
$$

At large $N$ but not necessarily large $\lambda$, the bulk is a weakly interacting string theory on AdS:

$$
N\gg 1,
\quad
\lambda\;\text{arbitrary}
\quad
\longleftrightarrow
\quad
\text{classical string theory, generally stringy}.
$$

At large $N$ and large $\lambda$, the bulk reduces further to classical supergravity:

$$
N\gg 1,
\quad
\lambda\gg 1
\quad
\longleftrightarrow
\quad
\text{classical gravity on weakly curved AdS}.
$$

Most beginner computations in AdS/CFT take place in the last regime. But one should remember that this is a limit, not the definition of the duality.

## The minimal conceptual spine

The rest of the course develops the following chain of ideas.

First, large-$N$ gauge theory naturally organizes itself like a string theory:

$$
\text{large-}N\text{ expansion}
\quad
\sim
\quad
\text{string genus expansion}.
$$

Second, conformal symmetry naturally matches AdS isometries:

$$
\mathrm{Conf}(\mathbb R^{1,d-1})
\quad
\sim
\quad
\mathrm{Isom}(\mathrm{AdS}_{d+1}).
$$

Third, D-branes give two descriptions of one system:

$$
\text{open strings on branes}
\quad
\sim
\quad
\text{gauge theory},
$$

$$
\text{closed strings near branes}
\quad
\sim
\quad
\text{gravity on AdS}.
$$

Fourth, boundary values of bulk fields are sources for boundary operators:

$$
\phi_{(0)}(x)
\quad
\longleftrightarrow
\quad
J(x)\mathcal O(x).
$$

Fifth, the bulk on-shell action generates boundary correlators:

$$
S_{\text{ren,on-shell}}
\quad
\longrightarrow
\quad
\langle \mathcal O_1\cdots \mathcal O_n\rangle.
$$

Finally, black holes and extremal surfaces translate geometric quantities into thermal and information-theoretic quantities in the CFT:

$$
\text{horizon area}
\quad
\longleftrightarrow
\quad
\text{thermal entropy},
$$

$$
\text{extremal-surface area}
\quad
\longleftrightarrow
\quad
\text{entanglement entropy}.
$$

The course is built so that each page adds one piece to this spine.

## Dictionary checkpoint

At this stage, the following entries are only first approximations. They will become sharper later.

| Boundary concept | Bulk concept |
|---|---|
| large-$N$ expansion | weak bulk quantum-loop expansion |
| 't Hooft coupling $\lambda$ | curvature scale in string units |
| CFT spacetime | conformal boundary of AdS |
| RG scale | radial position |
| source $J(x)$ | boundary value of a bulk field |
| operator $\mathcal O(x)$ | bulk field excitation |
| thermal state | AdS black hole or black brane |
| entropy | area in Planck units |
| strongly coupled QFT computation | classical gravitational boundary-value problem |

The most important warning is that the right column is often an emergent, approximate description. The exact object, when the duality is known, is the full boundary quantum theory.

## Common confusions

### “Holography means the universe is literally a projection.”

The word “holography” is suggestive, but AdS/CFT is not the claim that our everyday world is an optical projection. It is a precise duality between quantum theories. The bulk gravitational description and the boundary field-theory description encode the same physics in different variables.

### “The boundary theory lives at the edge of the bulk like matter on a shell.”

The boundary is a conformal boundary, not a material surface sitting inside the bulk. Its metric is defined up to Weyl rescaling. The boundary QFT is not made of atoms attached to the edge of AdS; it is an independent quantum description of the same system.

### “The extra dimension is just hidden space.”

The AdS radial direction behaves geometrically in the bulk, but it is related to scale in the boundary theory. A local bulk point is not simply a boundary point plus one hidden coordinate. Bulk locality emerges through a subtle encoding in many boundary degrees of freedom.

### “Classical gravity proves the full duality.”

Classical gravity is evidence for, and a limit of, the duality. The full statement is stronger: it relates a complete quantum field theory to a complete quantum theory of strings/gravity. Many basic checks can be performed in the classical limit, but the exact duality includes finite-$N$ and stringy corrections.

### “If holography is powerful, bottom-up models must be exact.”

A bottom-up gravitational model can be useful without being known to come from a complete string compactification or a consistent CFT. Bottom-up models are effective laboratories. They should be judged by their assumptions, symmetries, regimes of control, and intended observables.

## Exercises

### Exercise 1: Area scaling versus volume scaling

Work in $d$ spatial dimensions. Suppose a nongravitational local QFT with cutoff $a$ assigns $O(1)$ degrees of freedom to each spatial cell of size $a^d$ inside a region of radius $R$. How does the number of cells scale with $R$? How does this compare with the entropy scaling of a black hole in the same number of spatial dimensions?

<details>
<summary><strong>Solution</strong></summary>

The number of QFT cells scales like the volume divided by the cell volume:

$$
\#\text{cells}
\sim
\frac{R^d}{a^d}
=
\left(\frac{R}{a}\right)^d.
$$

Thus the naive entropy of a local QFT with a fixed cutoff scales like volume.

A black hole in $d+1$ spacetime dimensions has horizon area scaling like

$$
A_{\mathrm{hor}} \sim R^{d-1},
$$

so its Bekenstein–Hawking entropy scales as

$$
S_{\mathrm{BH}}
\sim
\frac{R^{d-1}}{G_N\hbar}.
$$

The black-hole scaling is area-like rather than volume-like. This mismatch is one of the main motivations for the holographic principle.

</details>

### Exercise 2: Reading the large-$N$ expansion as a string expansion

Compare the large-$N$ gauge-theory expansion

$$
\mathcal A
=
\sum_{g=0}^{\infty}N^{2-2g}F_g(\lambda)
$$

with the closed-string genus expansion

$$
\mathcal A_{\mathrm{string}}
=
\sum_{g=0}^{\infty}g_s^{2g-2}\mathcal F_g.
$$

What is the suggested relation between the string coupling and $N$?

<details>
<summary><strong>Solution</strong></summary>

The powers match if

$$
g_s^{2g-2} \sim N^{2-2g}.
$$

This suggests

$$
g_s \sim \frac{1}{N}.
$$

In precise examples, the relation can involve convention-dependent factors and couplings. The central idea is that the $1/N$ expansion of a gauge theory behaves like the quantum-loop expansion of a closed string theory. Large $N$ therefore corresponds to weak string coupling and suppresses bulk quantum loops.

</details>

### Exercise 3: Why strong coupling helps gravity become classical

In the canonical AdS$_5$/CFT$_4$ example, the AdS radius $L$ and string length $\ell_s=\sqrt{\alpha'}$ obey schematically

$$
\frac{L^4}{\alpha'^2} \sim \lambda.
$$

What does the limit $\lambda\gg 1$ imply for the curvature of the bulk in string units?

<details>
<summary><strong>Solution</strong></summary>

The relation can be written as

$$
\left(\frac{L}{\ell_s}\right)^4 \sim \lambda.
$$

Thus $\lambda\gg 1$ implies

$$
L \gg \ell_s.
$$

The curvature radius is much larger than the string length, so the bulk geometry is weakly curved in string units. This suppresses higher-derivative $\alpha'$ corrections. Therefore strong 't Hooft coupling on the boundary is one of the conditions needed for the bulk to be well approximated by classical gravity rather than full string theory.

</details>

### Exercise 4: Why AdS rather than flat space?

List two reasons why AdS is a cleaner setting for holography than asymptotically flat spacetime.

<details>
<summary><strong>Solution</strong></summary>

Two important reasons are:

1. AdS has a timelike conformal boundary where one can impose boundary conditions and define sources for a boundary quantum field theory.
2. The AdS isometry group $SO(2,d)$ matches the conformal group of a $d$-dimensional CFT.

Another useful reason is that AdS acts like a gravitational box: signals can reach the boundary and return in finite global time, making thermal equilibrium and spectral questions more controlled.

</details>

## Further reading

The following references are landmarks, not prerequisites.

- G. 't Hooft, [Dimensional Reduction in Quantum Gravity](https://arxiv.org/abs/gr-qc/9310026). A foundational statement of the holographic principle from black-hole and entropy reasoning.
- L. Susskind, [The World as a Hologram](https://arxiv.org/abs/hep-th/9409089). A classic formulation of holography as a principle of quantum gravity.
- J. D. Bekenstein, [Black Holes and Entropy](https://doi.org/10.1103/PhysRevD.7.2333). The original black-hole entropy argument.
- S. W. Hawking, [Particle Creation by Black Holes](https://doi.org/10.1007/BF02345020). The calculation that fixes the black-hole temperature and entropy normalization.
- J. Maldacena, [The Large $N$ Limit of Superconformal Field Theories and Supergravity](https://arxiv.org/abs/hep-th/9711200). The original AdS/CFT proposal.
- O. Aharony, S. S. Gubser, J. Maldacena, H. Ooguri, and Y. Oz, [Large $N$ Field Theories, String Theory and Gravity](https://arxiv.org/abs/hep-th/9905111). A standard review of the correspondence and its evidence.

## Next step

The next page makes the slogan precise. We will separate three levels of the correspondence: the full string/QFT duality, the semiclassical gravity approximation, and the practical on-shell-action prescription used in computations.
