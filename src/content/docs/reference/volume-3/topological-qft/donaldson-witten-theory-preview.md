---
title: "Donaldson–Witten Theory: Preview"
description: "Introduces Donaldson–Witten theory as a four-dimensional cohomological TQFT obtained by twisting N=2 supersymmetric Yang–Mills theory, with localization onto instanton moduli spaces and Donaldson invariants."
sidebar:
  label: "Donaldson–Witten Preview"
  order: 7
level: Advanced
status: "Polished draft"
source: "Witten; Atiyah; Donaldson–Kronheimer; Nakahara; Frankel; Pestun et al.; standard cohomological TQFT references."
topics:
  - Donaldson–Witten theory
  - cohomological TQFT
  - topological twist
  - instanton moduli space
  - Donaldson invariants
  - descent observables
canonicalTopics:
  - donaldson-witten-theory
  - topological-yang-mills
  - cohomological-field-theory
  - instanton-moduli-space
  - donaldson-invariants
researchStatus:
  established:
    - "Donaldson–Witten theory is the standard four-dimensional cohomological TQFT whose path integral formally reproduces Donaldson polynomial invariants of smooth four-manifolds."
    - "Its localization equations are the anti-self-dual Yang–Mills equations, so the theory connects supersymmetric QFT, instanton moduli spaces, and smooth four-manifold topology."
  active:
    - "Modern developments relate this theory to Seiberg–Witten theory, geometric representation theory, categorification, boundaries, defects, and supersymmetric localization; this page is only a conceptual preview."
---

## Summary

**Donaldson–Witten theory** is a four-dimensional cohomological topological quantum field theory obtained by a topological twist of $\mathcal N=2$ supersymmetric Yang–Mills theory. Its correlation functions formally compute **Donaldson invariants**, smooth invariants of four-manifolds built from moduli spaces of anti-self-dual connections.

The central mechanism is the same one introduced on the [Cohomological TQFT](/symmetry-anomalies-topology/topological-qft/cohomological-tqft/) page. After twisting, one finds a scalar fermionic operator $Q$ satisfying

$$
Q^2=\text{gauge transformation}
$$

on gauge-invariant observables. The stress tensor is $Q$-exact, so correlation functions of $Q$-closed observables are insensitive to smooth metric variations, up to wall-crossing and compactness caveats. The path integral localizes to the anti-self-dual equations

$$
F_A^+=0.
$$

Thus the rough dictionary is

$$
\mathcal N=2\ \text{Yang–Mills}
\quad\xrightarrow{\text{twist}}\quad
\text{cohomological TQFT}
\quad\xrightarrow{\text{localization}}\quad
\text{instanton moduli space}
\quad\xrightarrow{\text{observables}}\quad
\text{Donaldson invariants}.
$$

<figure class="doc-figure" style="--figure-width: 50rem;">

![Donaldson–Witten theory schematic: N=2 Yang–Mills is twisted into a cohomological TQFT whose Q-fixed locus is the instanton moduli space and whose descent observables integrate cohomology classes over cycles.](/figures/symmetry-anomalies-topology/donaldson-witten-flow.svg)

<figcaption>

Donaldson–Witten theory is the prototype Witten-type TQFT: a physical supersymmetric gauge theory is twisted so that one supercharge becomes scalar, the path integral localizes to $F_A^+=0$, and descent observables produce intersection classes on instanton moduli space.

</figcaption>
</figure>

This page is a preview. It does not try to construct the full $\mathcal N=2$ supersymmetric Lagrangian, prove transversality of moduli spaces, or state the rigorous Donaldson theory. Its job is to explain why this theory is a landmark: it turns a quantum field theory into a machine for four-manifold topology.

## Prerequisites

You should know the pages on [Metric Independence](/symmetry-anomalies-topology/topological-qft/metric-independence/), [Cohomological TQFT](/symmetry-anomalies-topology/topological-qft/cohomological-tqft/), [Chern–Simons Theory](/symmetry-anomalies-topology/topological-qft/chern-simons-theory/), and [BF Theory](/symmetry-anomalies-topology/topological-qft/bf-theory/). You should also be comfortable with connections, curvature, Hodge decomposition, instantons, the self-dual/anti-self-dual split of two-forms, and the idea of a moduli space.

The needed four-dimensional geometry is this. On an oriented Riemannian four-manifold $M_4$, the Hodge star acts on two-forms with $*^2=1$, so

$$
\Omega^2(M_4)=\Omega^2_+(M_4)\oplus\Omega^2_-(M_4).
$$

For a connection $A$ with curvature $F_A$, write

$$
F_A^\pm=\frac12(F_A\pm *F_A).
$$

The anti-self-dual instanton equation is

$$
F_A^+=0.
$$

Some authors choose the opposite sign and call $F_A^-=0$ the instanton equation. That is an orientation convention.

## Core idea

Donaldson invariants originally arise from the geometry of the moduli space of anti-self-dual connections,

$$
\mathcal M_k
=
\{A\mid F_A^+=0,\ c_2(E)=k\}/\mathcal G,
$$

where $\mathcal G$ is the gauge group. The miraculous physical insight of Donaldson–Witten theory is that the same moduli-space intersection numbers can be produced by a twisted supersymmetric path integral.

The topological twist changes how fields transform under rotations. In ordinary $\mathcal N=2$ supersymmetric Yang–Mills theory, supercharges transform as spinors. After the twist, one linear combination becomes a scalar operator $Q$. This scalar $Q$ plays the role of a BRST-like differential.

Metric independence follows from the cohomological pattern

$$
T_{\mu\nu}=\{Q,G_{\mu\nu}\}
$$

schematically. If $\mathcal O_i$ are $Q$-closed and the measure has no anomaly, then

$$
\frac{\partial}{\partial g^{\mu\nu}}
\left\langle \mathcal O_1\cdots\mathcal O_n\right\rangle
=
\left\langle \{Q,\cdots\}\right\rangle=0.
$$

The path integral becomes a sophisticated localization integral. The $Q$-fixed equations include

$$
F_A^+=0,
$$

so the theory reduces to integration over instanton moduli space. Observables built by descent give cohomology classes on this moduli space, and their correlation functions become Donaldson polynomials.

## Setup and conventions

Let $G$ be a compact gauge group, often $SU(2)$ or $SO(3)$ in the classical Donaldson setting, and let $E\to M_4$ be a principal $G$-bundle. A connection $A$ has curvature

$$
F_A=dA+A\wedge A,
$$

where the product includes the Lie-algebra bracket.

The instanton number is normalized schematically by

$$
k
=
-\frac{1}{8\pi^2}\int_{M_4}\operatorname{tr}(F_A\wedge F_A),
$$

with the sign and trace normalization depending on the representation and orientation conventions. This page follows the same broad topological-term convention as the rest of the volume: when an exact numerical normalization matters, the page states the trace convention.

The instanton moduli space is formally the zero locus of the map

$$
A\longmapsto F_A^+
$$

modulo gauge transformations. Its expected dimension is given by an index theorem. For $G=SU(2)$ on a simply connected four-manifold, one common form is

$$
\dim \mathcal M_k
=
8k-3(1+b_2^+),
$$

under standard irreducibility and genericity assumptions. The exact formula depends on the gauge group, bundle, and topology of $M_4$.

:::note[Source note: preview-level formula]
Dimension formulas for instanton moduli spaces are index-theoretic statements. This preview gives the commonly quoted $SU(2)$ simply connected version only to orient the reader. Rigorous Donaldson theory requires careful treatment of reducible connections, orientations, compactification, transversality, and chamber dependence.
:::

## The topological twist

In four-dimensional Euclidean signature, the rotation group is locally

$$
Spin(4)\simeq SU(2)_+\times SU(2)_-.
$$

The $\mathcal N=2$ supersymmetric theory also has an $SU(2)_R$ R-symmetry. The Donaldson–Witten twist replaces one of the spin factors by a diagonal subgroup involving $SU(2)_R$. Symbolically,

$$
SU(2)_+^{\mathrm{twisted}}
=
\operatorname{diag}(SU(2)_+\times SU(2)_R).
$$

After this redefinition, some spinor fields become differential forms. Most importantly, one supercharge becomes a scalar $Q$. The theory can then be put on a general oriented Riemannian four-manifold, because $Q$ no longer depends on choosing a covariantly constant spinor.

The twisted field content can be organized schematically as:

| Twisted field | Geometric type | Role |
|---|---|---|
| $A$ | connection one-form | gauge field |
| $\psi$ | fermionic one-form | $Q$-partner of $A$ |
| $\chi^+$ | fermionic self-dual two-form | imposes $F_A^+=0$ |
| $\eta$ | fermionic scalar | gauge-fixing/cohomological partner |
| $\phi,\overline\phi$ | scalar adjoint fields | ghost-for-ghost style fields in the cohomological complex |

Different references use different names and signs. The invariant structure is that $Q$ acts like a differential on the space of fields and that $Q$-fixed configurations include anti-self-dual connections.

## Localization onto instantons

The action of Donaldson–Witten theory has the schematic form

$$
S
=
\{Q,V\}
+
i\theta k.
$$

The $Q$-exact term can be rescaled without changing $Q$-closed correlators:

$$
S_t=t\{Q,V\}+i\theta k.
$$

Taking $t\to\infty$ localizes the path integral onto the minima of the bosonic part of $\{Q,V\}$. The dominant equation is

$$
F_A^+=0.
$$

This is the anti-self-dual Yang–Mills equation. Hence the infinite-dimensional path integral formally reduces to a finite-dimensional integral over $\mathcal M_k$.

The fermionic zero modes become differential forms on $\mathcal M_k$. The path integral over fermion zero modes computes intersection numbers. This is the cohomological-field-theory mechanism in its most famous four-dimensional form.

A useful mental model is:

$$
\int \mathcal D(\text{fields})\,e^{-S}\,(\text{observables})
\quad\leadsto\quad
\int_{\mathcal M_k}
(\text{cohomology classes}).
$$

The arrow hides the difficult analysis. It is a physical localization argument, not by itself a rigorous proof of compactness or transversality.

## Descent observables

Donaldson–Witten theory has a distinguished gauge-invariant scalar observable built from the adjoint scalar $\phi$,

$$
\mathcal O_0=\operatorname{tr}\phi^2.
$$

The cohomological descent procedure produces forms $\mathcal O_p$ satisfying

$$
d\mathcal O_p+\{Q,\mathcal O_{p+1}\}=0.
$$

Integrating $\mathcal O_p$ over a $p$-cycle $\gamma_p\subset M_4$ gives a $Q$-closed observable:

$$
I(\gamma_p)=\int_{\gamma_p}\mathcal O_p.
$$

Indeed,

$$
Q I(\gamma_p)
=
-\int_{\gamma_p}d\mathcal O_{p-1}
=
-\int_{\partial\gamma_p}\mathcal O_{p-1}=0
$$

when $\gamma_p$ is closed.

Correlation functions of these integrated observables become Donaldson invariants. For example, inserting observables associated to two-cycles $\Sigma_i$ produces intersection data on the instanton moduli space:

$$
\left\langle I(\Sigma_1)\cdots I(\Sigma_r)\right\rangle
=
\int_{\mathcal M_k}\mu(\Sigma_1)\wedge\cdots\wedge\mu(\Sigma_r),
$$

schematically. The classes $\mu(\Sigma_i)$ are the Donaldson $\mu$-map images of homology cycles.

:::note[Source note: descent versus de Rham]
The descent equation is not just the ordinary de Rham differential on spacetime. It relates spacetime exterior differentiation to the cohomological differential $Q$ acting on fields. This is why integrating over spacetime cycles produces $Q$-closed operators.
:::

## Donaldson invariants

Donaldson invariants distinguish smooth structures on four-manifolds. In the physics picture, they are correlation functions of topological observables in Donaldson–Witten theory.

The formal Donaldson generating function has the rough form

$$
\left\langle
\exp\left(\sum_i t_i I(\Sigma_i)+\lambda \mathcal O_0(x)\right)
\right\rangle.
$$

The coefficient of a monomial in $t_i$ and $\lambda$ corresponds to an intersection number on instanton moduli space, provided degrees match the dimension.

This was historically astonishing because it connected:

```txt
supersymmetric gauge theory
  → topological twist
  → instanton localization
  → smooth four-manifold invariants
```

The deeper moral is now standard: quantum field theory can produce invariants of manifolds by making metric dependence $Q$-exact and letting the path integral localize onto geometric moduli spaces.

## Metric dependence and wall crossing

Donaldson–Witten theory is topological in the cohomological sense: metric dependence is expected to be $Q$-exact. But “topological” does not mean every subtle dependence disappears.

There are two major caveats.

First, the space of solutions can fail to be compact. Compactification of instanton moduli space is part of the rigorous mathematical story.

Second, when $b_2^+(M_4)=1$, Donaldson invariants can depend on a chamber in the space of metrics. This is **wall crossing**. Physically, it occurs because changing the metric can cross loci where extra zero modes or reducible connections affect the path integral.

Thus the right statement is not “nothing can ever depend on the metric.” The right statement is:

$$
\text{metric variation is }Q\text{-exact unless boundary, zero-mode, or compactness effects contribute}.
$$

This is the same subtlety that appears throughout cohomological TQFT.

## Boundaries and Floer theory

On a four-manifold with boundary,

$$
\partial M_4=Y_3,
$$

Donaldson–Witten theory is no longer simply a number-valued invariant of $M_4$. The boundary Hilbert space is related to instanton Floer homology of $Y_3$.

This is a four-dimensional analogue of the relationship between Chern–Simons theory and conformal blocks or boundary current algebras. A TQFT on a manifold with boundary should assign states, not just numbers. Cutting and gluing four-manifolds then becomes a pairing of Floer-theoretic state spaces.

This boundary story is one reason Donaldson–Witten theory belongs near the [Extended TQFT Preview](/symmetry-anomalies-topology/topological-qft/extended-tqft-preview/) page. A fully local TQFT should know what it assigns not only to closed four-manifolds, but also to three-manifolds, surfaces, curves, and points.

## Relation to Seiberg–Witten theory

For many four-manifolds, Donaldson invariants can be expressed in terms of Seiberg–Witten invariants. Physically, this relation comes from the low-energy dynamics of $\mathcal N=2$ supersymmetric gauge theory. At special points on the Coulomb branch, the effective theory becomes abelian with light monopoles or dyons, and the relevant topological equations become Seiberg–Witten monopole equations rather than nonabelian instanton equations.

This is not merely a computational trick. It is one of the classic triumphs of QFT intuition in geometry: strong-coupling physics reorganizes a difficult nonabelian moduli problem into a more tractable abelian one.

This preview does not derive Seiberg–Witten theory. It only flags why Donaldson–Witten theory is a gateway topic: it is where supersymmetry, topology, moduli spaces, duality, and smooth four-manifold invariants first meet.

## What this page is not doing

This page is deliberately not a full introduction to $\mathcal N=2$ supersymmetry. It also does not define Donaldson invariants rigorously, prove compactness, construct orientations, treat reducible connections carefully, or explain gluing theorems.

The goal is to provide the QFT map:

$$
\text{twisted supersymmetric gauge theory}
\quad\Rightarrow\quad
\text{cohomological localization}
\quad\Rightarrow\quad
\text{four-manifold invariants}.
$$

For mathematical precision, use Donaldson–Kronheimer, Freed–Uhlenbeck, and standard gauge-theory references. For the physics derivation, use Witten’s original TQFT work and later Seiberg–Witten theory reviews.

## Common pitfalls

**“Donaldson–Witten theory is just ordinary Yang–Mills with $\theta$ term.”** No. It is a topologically twisted supersymmetric theory whose $Q$-exact action localizes to instantons. The topological Yang–Mills action in this context is cohomological, not merely the metric-independent $\int F\wedge F$ term.

**“Twisting changes the local dynamics by hand.”** The twist changes how fields transform under spacetime rotations by mixing rotations with R-symmetry. It does not arbitrarily invent the $Q$-complex; it repackages a supersymmetric theory so that a scalar supercharge survives on curved manifolds.

**“Metric independence means no caveats.”** Boundaries of moduli space, reducible connections, wall crossing, and anomalies can contribute. Cohomological metric independence is a powerful principle, not permission to ignore analysis.

**“The path integral proves Donaldson theory rigorously.”** The path integral gives a remarkable physical explanation and computational framework. Turning it into rigorous differential geometry requires additional mathematical work.

**“Donaldson invariants and Seiberg–Witten invariants are unrelated.”** They are deeply related through the low-energy structure of $\mathcal N=2$ gauge theory, though the precise relation depends on hypotheses and four-manifold data.

## Relations to other pages

[Metric Independence](/symmetry-anomalies-topology/topological-qft/metric-independence/) explains the stress-tensor criterion and the role of $Q$-exact metric dependence. [Cohomological TQFT](/symmetry-anomalies-topology/topological-qft/cohomological-tqft/) gives the general $Q$-cohomology and localization pattern. [Chern–Simons Theory](/symmetry-anomalies-topology/topological-qft/chern-simons-theory/) provides the three-dimensional cousin whose boundary and Floer-theoretic role appears in four-dimensional gauge theory.

The [Topological Sectors and Solitonic Charges](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/) chapter explains instanton number and topological sectors. The [Symmetry TFT and Anomaly Inflow](/symmetry-anomalies-topology/symmetry-tft-anomaly-inflow/) chapter explains how topological bulk theories encode anomaly and symmetry data. The supersymmetry volume develops the untwisted $\mathcal N=2$ gauge theory and Seiberg–Witten structure.

## Research status

Donaldson–Witten theory is established as a landmark bridge between physics and four-manifold topology. Its role as a cohomological TQFT and its formal localization onto instanton moduli spaces are standard.

Active and advanced directions include categorified Donaldson invariants, boundary and defect versions, relations to geometric Langlands, relations to Seiberg–Witten theory, refined invariants, equivariant and supersymmetric localization, and the role of topological twists in modern dualities.

## Exercises

### Exercise 1: Self-dual decomposition

Let $\omega$ be a two-form on an oriented Riemannian four-manifold. Define

$$
\omega^\pm=\frac12(\omega\pm *\omega).
$$

Show that $*\omega^\pm=\pm \omega^\pm$.

<details><summary><strong>Solution</strong></summary>

Using $*^2=1$ on two-forms in four Euclidean dimensions,

$$
*\omega^\pm
=
\frac12(*\omega\pm *^2\omega)
=
\frac12(*\omega\pm \omega).
$$

For the plus sign,

$$
*\omega^+=\frac12(*\omega+\omega)=\omega^+.
$$

For the minus sign,

$$
*\omega^-=\frac12(*\omega-\omega)=-\frac12(\omega-*\omega)=-\omega^-.
$$

</details>

### Exercise 2: Instantons minimize the Yang–Mills action

Use the identity

$$
\int \operatorname{tr}(F\wedge *F)
=
\int \operatorname{tr}(F^+\wedge *F^+)
+
\int \operatorname{tr}(F^-\wedge *F^-)
$$

to explain why fixing $\int\operatorname{tr}(F\wedge F)$ leads to a lower bound saturated by self-dual or anti-self-dual connections.

<details><summary><strong>Solution</strong></summary>

The decomposition $F=F^++F^-$ is orthogonal. Also,

$$
\int\operatorname{tr}(F\wedge F)
=
\int\operatorname{tr}(F^+\wedge *F^+)
-
\int\operatorname{tr}(F^-\wedge *F^-)
$$

up to trace-sign conventions. Thus the Yang–Mills norm is the sum of two nonnegative pieces, while the topological charge is their difference. For fixed topological charge, the norm is minimized when one of the two pieces vanishes. This gives $F^+=0$ or $F^-=0$, depending on orientation and sign convention.

</details>

### Exercise 3: Descent gives cycle observables

Suppose $d\mathcal O_p+\{Q,\mathcal O_{p+1}\}=0$. Show that

$$
I_{p+1}(\gamma)=\int_\gamma \mathcal O_{p+1}
$$

is $Q$-closed when $\gamma$ is a closed $(p+1)$-cycle.

<details><summary><strong>Solution</strong></summary>

From the descent equation,

$$
\{Q,\mathcal O_{p+1}\}=-d\mathcal O_p.
$$

Therefore

$$
QI_{p+1}(\gamma)
=
\int_\gamma \{Q,\mathcal O_{p+1}\}
=
-\int_\gamma d\mathcal O_p
=
-\int_{\partial\gamma}\mathcal O_p.
$$

If $\partial\gamma=0$, this vanishes. Thus $I_{p+1}(\gamma)$ is $Q$-closed.

</details>

### Exercise 4: Why a scalar supercharge matters

Why is it important that the twisted supercharge $Q$ is a scalar under the twisted rotation group?

<details><summary><strong>Solution</strong></summary>

A spinor supercharge cannot be defined globally on a generic curved four-manifold without additional structure such as a covariantly constant spinor. A scalar supercharge can be defined without choosing a preferred direction or spinor. This lets the twisted theory be placed on a broad class of oriented Riemannian four-manifolds and makes $Q$ usable as a cohomological differential.

</details>

## References

- E. Witten, “Topological Quantum Field Theory,” *Communications in Mathematical Physics* **117** (1988). The foundational physics construction of Donaldson–Witten theory.
- S. K. Donaldson and P. B. Kronheimer, *The Geometry of Four-Manifolds*. Standard mathematical reference for Donaldson invariants and instanton moduli spaces.
- M. F. Atiyah and L. Jeffrey, “Topological Lagrangians and Cohomology,” for the Mathai–Quillen interpretation.
- D. Birmingham, M. Blau, M. Rakowski, and G. Thompson, “Topological Field Theory,” for a broad review of cohomological TQFTs.
- M. Nakahara, *Geometry, Topology and Physics*, for instantons, characteristic classes, and gauge-theory topology.
- V. Pestun et al., “Localization Techniques in Quantum Field Theories,” for modern localization context.
- E. Witten, “Monopoles and Four-Manifolds,” for the Seiberg–Witten turn in four-dimensional topology.

## Version history

- **2026-06-23:** Initial polished preview. Added topological twist, localization to $F_A^+=0$, descent observables, Donaldson invariant dictionary, wall-crossing caveats, and Seiberg–Witten relation.
