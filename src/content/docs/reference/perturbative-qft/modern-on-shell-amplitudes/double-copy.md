---
title: "Double Copy"
description: "How gravity amplitudes emerge from gauge-theory data through KLT relations, color-kinematics duality, and the BCJ double copy."
sidebar:
  label: "Double Copy"
  order: 9
level: Advanced
status: "Polished draft"
source: "Kawai, Lewellen, and Tye; Bern, Carrasco, and Johansson; Bern, Dennen, Huang, and Kiermaier; Elvang and Huang; Dixon; Zee Part N."
topics:
  - double copy
  - color-kinematics duality
  - BCJ relations
  - KLT relations
  - gravity amplitudes
canonicalTopics:
  - double-copy
  - color-kinematics-duality
  - bcj-double-copy
  - klt-relations
  - gravity-from-gauge-theory
researchStatus:
  established:
    - "KLT relations and tree-level color-kinematics double copy are standard results for broad classes of gauge and gravity amplitudes."
  active:
    - "Loop-level double-copy representations, classical double copy, curved-background extensions, EFT corrections, color-kinematics in general theories, and geometric origins remain active research directions."
---

## Summary

The double copy is the remarkable fact that many gravity amplitudes can be built from gauge-theory amplitude data. In its modern BCJ form, one first writes a gauge-theory amplitude as a sum over cubic graphs,

$$
\mathcal A_n^{\rm tree}
=
 g^{n-2}\sum_{\Gamma}
\frac{c_\Gamma n_\Gamma}{D_\Gamma},
$$

where $c_\Gamma$ are color factors, $n_\Gamma$ are kinematic numerators, and $D_\Gamma$ is the product of propagator denominators. If the numerators can be chosen to satisfy the same Jacobi relations as the color factors, then a gravity amplitude is obtained by replacing color with another copy of kinematics:

$$
\mathcal M_n^{\rm tree}
=
\left(\frac{\kappa}{2}\right)^{n-2}
\sum_{\Gamma}
\frac{n_\Gamma\widetilde n_\Gamma}{D_\Gamma},
$$

up to the usual overall $i$ and normalization conventions.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 55rem;">

![The double copy replaces color factors in a cubic gauge-theory representation by a second set of kinematic numerators](/figures/perturbative-qft/double-copy.svg)

<figcaption>

In a color-kinematics representation, gauge-theory numerators obey the same algebraic relations as color factors. The BCJ double copy replaces $c_\Gamma$ by a second numerator $\widetilde n_\Gamma$, producing a gravity integrand or amplitude with the same propagator graph basis.

</figcaption>
</figure>

The older KLT relations express closed-string tree amplitudes as products of open-string tree amplitudes. In the field-theory limit, they express gravity tree amplitudes as bilinear combinations of color-ordered gauge-theory tree amplitudes. The BCJ double copy is a graph-level refinement of this idea.

The double copy is not the statement that a graviton is literally two gluons inside spacetime. It is a statement about scattering amplitudes and, in extended forms, about integrands, classical solutions, radiation, and effective theories. It is powerful precisely because it turns the redundancy of gauge theory into an unexpected organizing principle for gravity.

## Prerequisites

You should know [Color Decomposition](/perturbative-qft/modern-on-shell-amplitudes/color-decomposition/), [Color-Ordered Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/color-ordered-amplitudes/), [BCFW Recursion](/perturbative-qft/modern-on-shell-amplitudes/bcfw-recursion/), [Generalized Unitarity](/perturbative-qft/modern-on-shell-amplitudes/generalized-unitarity/), [Soft Limits](/perturbative-qft/modern-on-shell-amplitudes/soft-limits/), [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/), and [Color Factors](/perturbative-qft/gauge-theory-perturbation-theory/color-factors/).

## Core idea

Non-Abelian gauge theory has two kinds of structure in its amplitudes:

```txt
color algebra      → structure constants, traces, Jacobi identities;
kinematic algebra  → momenta, polarizations, spinors, factorization data.
```

Color-kinematics duality says that amplitudes can often be represented so that these two structures obey parallel algebraic identities. Whenever a set of color factors satisfies a Jacobi relation,

$$
c_i+c_j+c_k=0,
$$

one can try to choose the corresponding kinematic numerators so that

$$
n_i+n_j+n_k=0.
$$

When such a representation exists, the color factor can be replaced by another kinematic numerator. Gauge theory then turns into gravity:

```txt
gauge theory: color × kinematics

double copy: kinematics × kinematics.
```

That slogan is a useful memory hook, but it hides a lot. The numerators are not unique, the graph basis is not unique, and the gravity theory produced depends on which two gauge-theory copies are used.

## Setup and conventions

Use the scattering conventions fixed in this volume. We suppress overall momentum-conserving delta functions and convention-dependent factors of $i$ unless they are essential.

A tree-level Yang–Mills amplitude can be organized over cubic graphs. Quartic vertices are absorbed into cubic graphs by multiplying and dividing by appropriate propagator denominators. The result is a representation of the form

$$
\mathcal A_n^{\rm tree}
=
 g^{n-2}\sum_{\Gamma\in\text{cubic graphs}}
\frac{c_\Gamma n_\Gamma}{D_\Gamma}.
$$

Here

$$
D_\Gamma=\prod_{e\in\Gamma}P_e^2
$$

for massless tree graphs, with obvious modifications for massive internal lines.

The color factor $c_\Gamma$ is built from structure constants $f^{abc}$ or representation matrices. The numerator $n_\Gamma$ contains the kinematic dependence. Different numerator choices can give the same amplitude because terms can be reshuffled among graphs. This freedom is called generalized gauge freedom.

## KLT relations

The earliest version of the double-copy story comes from string theory. Kawai, Lewellen, and Tye found that closed-string tree amplitudes can be written as bilinear combinations of open-string tree amplitudes. Since closed strings contain gravitons and open strings contain gauge bosons, the field-theory limit gives relations between gravity and Yang–Mills tree amplitudes.

At four points, one common field-theory KLT relation is

$$
M_4^{\rm tree}(1,2,3,4)
=
-i s_{12}
A_4^{\rm tree}(1,2,3,4)
\widetilde A_4^{\rm tree}(1,2,4,3),
$$

where the exact sign and factor of $i$ depend on amplitude conventions.

At $n$ points, the schematic structure is

$$
M_n^{\rm tree}
=
\sum_{\alpha,\beta}
A_n^{\rm tree}(1,\alpha,n-1,n)
S[\alpha|\beta]
\widetilde A_n^{\rm tree}(1,n-1,\beta,n),
$$

where $S[\alpha|\beta]$ is the KLT momentum kernel and $\alpha,\beta$ run over permutations of $n-3$ labels.

KLT relations are true tree-level statements, but they do not display the local graph-by-graph structure of the amplitude. BCJ color-kinematics duality supplies that refinement.

## Color-kinematics duality

At four points, there are three cubic channels. Write

$$
\mathcal A_4
=
 g^2\left(
\frac{c_s n_s}{s}
+
\frac{c_t n_t}{t}
+
\frac{c_u n_u}{u}
\right).
$$

The color factors satisfy a Jacobi identity, for example

$$
c_s+c_t+c_u=0,
$$

with signs determined by the orientation convention for structure constants. Color-kinematics duality asks for numerators satisfying the parallel relation

$$
n_s+n_t+n_u=0.
$$

If this can be done, the gravity amplitude is

$$
\mathcal M_4
=
\left(\frac{\kappa}{2}\right)^2
\left(
\frac{n_s\widetilde n_s}{s}
+
\frac{n_t\widetilde n_t}{t}
+
\frac{n_u\widetilde n_u}{u}
\right).
$$

The relation is much more than a four-point trick. At higher multiplicity, every internal edge of a cubic graph participates in Jacobi triples. A color-kinematics representation requires all corresponding numerator triples to obey the same identities.

## Generalized gauge freedom

Kinematic numerators are not unique. A shift

$$
n_\Gamma\to n_\Gamma+\Delta_\Gamma
$$

is allowed if it leaves the full gauge amplitude unchanged:

$$
\sum_\Gamma\frac{c_\Gamma\Delta_\Gamma}{D_\Gamma}=0.
$$

This is not ordinary gauge fixing in the Lagrangian sense, though it is related in spirit. It is a freedom in how the same amplitude is represented across graph numerators.

Finding a color-kinematics representation is often the hard part. Ordinary Feynman-gauge numerators usually do not automatically satisfy BCJ Jacobi identities. One must perform algebraic rearrangements, choose clever gauges, use ansätze, exploit generalized unitarity cuts, or use recursive constructions.

The double copy is representation-dependent in this sense:

```txt
not every numerator representation double copies directly;
color-kinematics-satisfying representations are the useful ones.
```

At tree level, such representations are known quite broadly. At loop level, existence and construction are subtler.

## BCJ amplitude relations

Color-kinematics duality implies linear relations among color-ordered tree amplitudes. These are the BCJ relations. A basic example at four points is

$$
s_{12}A_4(1,2,3,4)
=
s_{13}A_4(1,3,2,4),
$$

up to the convention for ordering and signs.

The practical consequence is that the number of independent color-ordered tree amplitudes is smaller than cyclicity, reflection, and Kleiss–Kuijf relations alone would suggest. A common basis has size

$$
(n-3)!.
$$

This is also the size of the KLT basis. The fact that the same basis size appears in KLT and BCJ is not accidental; both are different faces of the same hidden structure.

## Which gravity theory appears?

The output of a double copy depends on the two gauge-theory inputs. Some useful examples are:

| First copy | Second copy | Typical gravity output |
|---|---|---|
| pure Yang–Mills | pure Yang–Mills | gravity plus dilaton and two-form sectors |
| supersymmetric Yang–Mills | supersymmetric Yang–Mills | supergravity with corresponding supersymmetry |
| $\mathcal N=4$ super-Yang–Mills | $\mathcal N=4$ super-Yang–Mills | $\mathcal N=8$ supergravity |
| Yang–Mills with matter | Yang–Mills with matter | gravity coupled to matter, depending on representation choices |

The phrase “gravity” in amplitude discussions often includes more than pure Einstein gravity. A product of two gluon polarization vectors decomposes into symmetric traceless, antisymmetric, and trace pieces:

$$
\varepsilon_\mu\widetilde\varepsilon_\nu
\quad\leadsto\quad
\text{graviton}\oplus\text{two-form}\oplus\text{dilaton}.
$$

Projecting to pure gravity can require additional ingredients, such as ghost-like matter double copies, orbifold projections, or theory-specific constructions. Do not assume that Yang–Mills times Yang–Mills automatically means pure Einstein gravity and nothing else.

## Double copy and soft limits

The leading soft factors already hint at double copy. For a color-dressed soft gluon, the eikonal factor contains

$$
\mathbf T_i^a
\frac{p_i\cdot\varepsilon}{p_i\cdot q}.
$$

For a soft graviton, the corresponding factor contains

$$
\frac{p_i^\mu p_i^\nu\varepsilon_{\mu\nu}}{p_i\cdot q}.
$$

Very loosely, the replacement

$$
\mathbf T_i^a
\quad\longrightarrow\quad
p_i^\mu
$$

turns the gauge-theory eikonal numerator into the gravity one. This is the same pattern in miniature: color information is replaced by kinematic information.

This soft-limit analogy is not a proof of the double copy, but it is a good sanity check. Gravity carries energy-momentum in the way gauge theory carries charge.

## Loop-level double copy

At loop level, the same idea can be applied to integrands:

$$
\mathcal A_n^{(L)}
=
 g^{n-2+2L}
\sum_\Gamma\int\prod_{r=1}^L\frac{d^D\ell_r}{(2\pi)^D}
\frac{1}{S_\Gamma}
\frac{c_\Gamma n_\Gamma}{D_\Gamma}.
$$

If the loop integrand has numerators satisfying color-kinematics duality, then the candidate gravity integrand is

$$
\mathcal M_n^{(L)}
=
\left(\frac{\kappa}{2}\right)^{n-2+2L}
\sum_\Gamma\int\prod_{r=1}^L\frac{d^D\ell_r}{(2\pi)^D}
\frac{1}{S_\Gamma}
\frac{n_\Gamma\widetilde n_\Gamma}{D_\Gamma}.
$$

Here $S_\Gamma$ is the graph symmetry factor. This formula has produced many highly nontrivial multi-loop gravity results.

The loop-level story has caveats. Loop integrands are defined up to terms that integrate to zero, dimension-dependent identities, contact terms, and regulator effects. A representation that satisfies color-kinematics duality in strictly four dimensions may not be enough for a dimensionally regulated calculation. As always in loop physics, the denominator goblins bring friends.

## Relation to generalized unitarity

Generalized unitarity is one of the main ways to verify and construct double-copy integrands. The workflow is:

```txt
construct gauge-theory numerators
  → impose color-kinematics identities
  → double copy numerators
  → check gravity cuts against products of gravity trees.
```

On a unitarity cut, a loop integrand factorizes into products of tree amplitudes. If the tree-level double copy holds on each cut, then the loop-level double-copy integrand has strong evidence — and in many settings a proof strategy — for reproducing the gravity amplitude.

This is why double copy and generalized unitarity developed together. Unitarity cuts test whether a proposed gravity integrand has the right physical factorization without expanding every gravitational Feynman diagram. Anyone who has seen gravity Feynman rules appreciates this mercy.

## Classical double copy preview

The double copy also appears in classical problems. Certain gauge-theory solutions, radiation fields, and worldline observables have gravitational counterparts obtained by replacing color charges with kinematic data.

The classical double copy includes examples such as:

| Gauge-side object | Gravity-side analogue |
|---|---|
| Coulomb-like field | Schwarzschild-like metric in suitable form |
| color charge | mass or momentum data |
| Yang–Mills radiation | gravitational radiation |
| worldline color dynamics | worldline gravitational dynamics |

This area is active and subtle. Classical double-copy maps can depend on gauge choices, coordinates, boundary conditions, sources, and whether the mapping is performed at the level of fields, equations, actions, or observables. The safest statement on this page is modest: the amplitude double copy has inspired powerful classical correspondences, but the classical dictionary is not one universal button labeled “square.”

## Common pitfalls

**Thinking the double copy is a slogan rather than a representation.** The BCJ double copy requires a suitable numerator representation. Random Feynman numerators usually do not work directly.

**Forgetting extra states.** Yang–Mills times Yang–Mills often gives gravity plus dilaton and two-form sectors. Pure gravity may require projections or modified matter content.

**Confusing KLT and BCJ.** KLT relates ordered tree amplitudes through a momentum kernel. BCJ double copy replaces color factors by kinematic numerators in a cubic-graph representation. They are related, but they are not the same formula.

**Assuming loop integrands are unique.** They are not. Loop integrands have generalized gauge freedom and regulator-dependent subtleties.

**Treating color-kinematics duality as manifest in the Lagrangian.** It is usually not manifest in standard Yang–Mills Feynman rules. Much of the art is finding variables where it becomes visible.

**Assuming every theory double copies to something simple.** Double-copy structures exist in many theories, but the output may be nonlocal-looking, higher-derivative, matter-coupled, or not yet understood.

## Relations to other pages

- [Color Decomposition](/perturbative-qft/modern-on-shell-amplitudes/color-decomposition/) separates gauge amplitudes into color tensors and kinematic partial amplitudes.
- [Color-Ordered Amplitudes](/perturbative-qft/modern-on-shell-amplitudes/color-ordered-amplitudes/) gives the ordered tree amplitudes that enter KLT relations.
- [Color Factors](/perturbative-qft/gauge-theory-perturbation-theory/color-factors/) collects the group-theory identities that color-kinematics numerators imitate.
- [BCFW Recursion](/perturbative-qft/modern-on-shell-amplitudes/bcfw-recursion/) gives a tree-level on-shell construction that exposes factorization.
- [Generalized Unitarity](/perturbative-qft/modern-on-shell-amplitudes/generalized-unitarity/) is the main loop-level tool for constructing and checking double-copy integrands.
- [Soft Limits](/perturbative-qft/modern-on-shell-amplitudes/soft-limits/) shows the eikonal version of the color-to-kinematics replacement.
- [Yang–Mills Feynman Rules](/perturbative-qft/gauge-theory-perturbation-theory/yang-mills-feynman-rules/) is the off-shell starting point that the on-shell double-copy representation reorganizes.

## Research status

- **Established:** KLT relations and tree-level BCJ double copy are standard amplitude technology.
- **Established with caveats:** Loop-level double-copy integrands are known in many important examples and have passed extensive unitarity checks, but finding suitable representations can be difficult and regulator-sensitive.
- **Active:** Multi-loop supergravity, finite-field reconstruction, color-kinematics for broader theories, classical double copy, curved-background extensions, EFT double copies, and the geometric origin of color-kinematics duality are active research areas.
- **Speculative or context-dependent:** Claims that every gravitational theory is simply the square of a gauge theory should be treated as research statements, not general theorems.

## Exercises

### Exercise 1: Four-point Jacobi mirror

Suppose the four-point cubic color factors satisfy

$$
c_s+c_t+c_u=0.
$$

Assume the kinematic numerators can be chosen so that

$$
n_s+n_t+n_u=0.
$$

Write the corresponding four-point double-copy gravity amplitude.

<details>
<summary><strong>Solution</strong></summary>

The gauge-theory amplitude has the cubic representation

$$
\mathcal A_4
=g^2\left(
\frac{c_s n_s}{s}
+
\frac{c_t n_t}{t}
+
\frac{c_u n_u}{u}
\right).
$$

The double-copy prescription replaces each color factor by a numerator from a second gauge-theory copy:

$$
c_s\to\widetilde n_s,
\qquad
c_t\to\widetilde n_t,
\qquad
c_u\to\widetilde n_u.
$$

Thus

$$
\mathcal M_4
=\left(\frac{\kappa}{2}\right)^2
\left(
\frac{n_s\widetilde n_s}{s}
+
\frac{n_t\widetilde n_t}{t}
+
\frac{n_u\widetilde n_u}{u}
\right),
$$

up to the overall $i$ convention used for amplitudes.

</details>

### Exercise 2: Why quartic vertices can be hidden

Yang–Mills theory has a four-gluon contact vertex. Explain how a representation using only cubic graphs can still describe the full tree amplitude.

<details>
<summary><strong>Solution</strong></summary>

A contact term has no propagator denominator. To include it in a cubic graph basis, one can multiply and divide by a channel denominator. Schematically,

$$
C
=
\frac{sC}{s}
$$

for an $s$-channel cubic graph, or similarly for other channels. The contact contribution is then absorbed into the numerator of one or more cubic graphs.

This redistribution is not unique. Different ways of assigning contact terms to cubic graphs correspond to different numerator representations. Color-kinematics duality asks for a representation in which these redistributed numerators obey Jacobi relations mirroring the color factors.

</details>

### Exercise 3: Soft factors and the color-to-kinematics idea

Compare the leading soft gluon factor

$$
\sum_i\mathbf T_i^a\frac{p_i\cdot\varepsilon}{p_i\cdot q}
$$

with the leading soft graviton factor

$$
\sum_i\frac{p_i^\mu p_i^\nu\varepsilon_{\mu\nu}}{p_i\cdot q}.
$$

What replacement does this suggest?

<details>
<summary><strong>Solution</strong></summary>

The soft gluon factor contains a color charge $\mathbf T_i^a$ and one kinematic numerator $p_i\cdot\varepsilon$. The soft graviton factor contains two kinematic factors, since $\varepsilon_{\mu\nu}$ can be thought of as carrying two polarization indices.

The comparison suggests the replacement

$$
\mathbf T_i^a
\longrightarrow
p_i^\mu,
$$

so that color charge is replaced by kinematic momentum data. This is not a proof of the double copy, but it is the soft-limit version of the same color-to-kinematics pattern.

</details>

### Exercise 4: Extra states from polarization products

A product of two vector polarizations carries two Lorentz indices, $\varepsilon_\mu\widetilde\varepsilon_\nu$. Decompose it into symmetric traceless, antisymmetric, and trace pieces. What fields do these pieces suggest?

<details>
<summary><strong>Solution</strong></summary>

The tensor product decomposes as

$$
\varepsilon_\mu\widetilde\varepsilon_\nu
=
\left(\varepsilon_{(\mu}\widetilde\varepsilon_{\nu)}-\text{trace}\right)
+
\varepsilon_{[\mu}\widetilde\varepsilon_{\nu]}
+
\text{trace}.
$$

The symmetric traceless part has the index structure of a graviton. The antisymmetric part has the index structure of a two-form field. The trace is a scalar, usually called a dilaton in this context.

This is why a simple Yang–Mills times Yang–Mills double copy naturally produces gravity together with possible two-form and dilaton sectors unless they are projected out or canceled.

</details>

## References

- H. Kawai, D. C. Lewellen, and S.-H. H. Tye, “A Relation Between Tree Amplitudes of Closed and Open Strings,” *Nuclear Physics B* **269** (1986), for the original KLT relations.
- Z. Bern, J. J. M. Carrasco, and H. Johansson, “New Relations for Gauge-Theory Amplitudes,” *Physical Review D* **78** (2008), for BCJ amplitude relations.
- Z. Bern, J. J. M. Carrasco, and H. Johansson, “Perturbative Quantum Gravity as a Double Copy of Gauge Theory,” *Physical Review Letters* **105** (2010), for the loop-level double-copy proposal.
- Z. Bern, T. Dennen, Y.-t. Huang, and M. Kiermaier, “Gravity as the Square of Gauge Theory,” *Physical Review D* **82** (2010), for tree-level color-kinematics and gravity relations.
- H. Elvang and Y.-t. Huang, *Scattering Amplitudes in Gauge Theory and Gravity*, for spinor-helicity, KLT, and double-copy methods.
- L. J. Dixon, “A brief introduction to modern amplitude methods,” for a concise amplitude-focused overview.
- A. Zee, *Quantum Field Theory in a Nutshell*, Part N, for an accessible discussion of gluon scattering and the gravity-as-square idea.
- R. Monteiro, D. O'Connell, and C. D. White, “Black holes and the double copy,” *Journal of High Energy Physics* **12** (2014), for a classic classical-double-copy example.

## Version history

- **2026-06-13:** Initial QFT.org page on double copy, including KLT relations, color-kinematics duality, BCJ graph numerators, loop-level double copy, extra-state caveats, soft-limit intuition, and solved exercises.
