---
title: "Orbifolds Preview"
description: "A preview of orbifold CFTs as gauging finite symmetries, with the compact-boson reflection orbifold as the basic example."
sidebar:
  label: "Orbifolds Preview"
  order: 11
level: Graduate
status: "Polished draft"
source: "Di Francesco, Mathieu, and Sénéchal 1997; Dixon, Harvey, Vafa, and Witten 1985–1986; Ginsparg 1988"
topics:
  - two-dimensional CFT
  - orbifold CFT
  - finite symmetry gauging
  - twisted sectors
  - modular invariance
  - compact boson
canonicalTopics:
  - orbifold-cft
  - finite-symmetry-gauging
  - twisted-sectors
researchStatus:
  established:
    - "For an anomaly-free finite symmetry of a two-dimensional CFT, the orbifold construction projects onto invariant states and adds twisted sectors so that the theory remains local and modular invariant."
    - "The circle-boson reflection orbifold is a standard c = 1 example with untwisted invariant operators and twist fields localized at fixed points."
  active:
    - "Modern work often reframes orbifolds in the language of topological defects, generalized symmetries, anomalies, and categorical structures."
---

## Summary

An orbifold CFT is obtained by **gauging a finite global symmetry** of a CFT. For a finite group $G$, the rough slogan is

$$
\text{orbifold} = \text{project to }G\text{-invariants} + \text{add }G\text{-twisted sectors}.
$$

The second term is the one people forget. If you only keep invariant operators and throw away non-invariant ones, the result is usually not a consistent CFT. Twisted sectors are required by locality, OPE closure, and modular invariance.

For the compact boson, the basic example is the reflection symmetry

$$
X\mapsto -X,
$$

which gives the circle orbifold

$$
S^1_R/\mathbb Z_2.
$$

Geometrically, the target circle is folded to an interval with two fixed points. In the CFT, those fixed points support twist fields. The resulting orbifold is not merely a scalar field living on an interval; it is a full two-dimensional CFT with untwisted invariant operators, twisted operators, and a modular-invariant torus partition function.

<figure class="doc-figure" style="--figure-width: 38rem;">

![Circle reflection orbifold and twisted sectors.](/figures/cft-bootstrap/orbifold-sector-sum.svg)

<figcaption>

The reflection orbifold of the compact boson identifies $X$ with $-X$. The quotient target has fixed points at $0$ and $\pi R$, and the CFT contains both projected untwisted states and twisted sectors associated with those fixed points.

</figcaption>
</figure>

## Prerequisites

You should know [Compact Boson](/cft-bootstrap/two-dimensional-cft/compact-boson/), especially the circle identification $X\sim X+2\pi R$, vertex operators $V_{n,m}$, and the torus partition function. You should also know [Free Boson CFT](/cft-bootstrap/two-dimensional-cft/free-boson-cft/), [Cylinder–Plane Map](/cft-bootstrap/two-dimensional-cft/cylinder-plane-map/), and [Operator Product Expansions in 2D](/cft-bootstrap/two-dimensional-cft/operator-product-expansions-in-2d/).

This page is a preview. It gives the physics and consistency logic, not the full classification of orbifold theories, discrete torsion, non-Abelian orbifolds, or modular tensor category language.

## Core idea

A finite global symmetry of a CFT can act on local operators, states, and twisted boundary conditions. Gauging that symmetry means that the symmetry is no longer a label distinguishing physical states. The new theory keeps only gauge-invariant states, but it must also sum over flat finite-group bundles.

On the torus, this means summing over twists around the two cycles. For an Abelian group, write $Z_{g,h}$ for the partition function with $g$-twisted boundary condition around one cycle and $h$-twisted boundary condition around the other. Then the orbifold partition function is schematically

$$
Z_{\mathrm{orb}}
=\frac{1}{|G|}\sum_{g,h\in G} Z_{g,h}
$$

when all elements commute. For a general finite group, the sum is over commuting pairs:

$$
Z_{\mathrm{orb}}
=\frac{1}{|G|}\sum_{\substack{g,h\in G\\ gh=hg}} Z_{g,h}.
$$

This formula is a compact way to say three things at once:

1. project onto invariant states,
2. include sectors twisted around the spatial circle,
3. make the answer invariant under modular transformations of the torus.

For $G=\mathbb Z_2=\{1,r\}$, the sum becomes

$$
Z_{\mathrm{orb}}
=\frac12\left(Z_{1,1}+Z_{1,r}+Z_{r,1}+Z_{r,r}\right).
$$

Under the modular $S$ transformation, the two torus cycles are exchanged, so $Z_{1,r}$ is mapped to $Z_{r,1}$. If $Z_{r,1}$ is missing, modular invariance is already lost. That is the shortest argument for why twisted sectors are not optional.

## Setup and conventions

Let $\mathcal H$ be the Hilbert space of a CFT with a finite global symmetry group $G$. The untwisted projected Hilbert space is

$$
\mathcal H_{\mathrm{untwisted}}^G
=\{\,|\psi\rangle\in\mathcal H\mid g|\psi\rangle=|\psi\rangle\text{ for all }g\in G\,\}.
$$

The orbifold Hilbert space is larger than this:

$$
\mathcal H_{\mathrm{orb}}
=\bigoplus_{[g]}\mathcal H_g^{C(g)}.
$$

Here $\mathcal H_g$ is the sector with $g$-twisted boundary condition around the spatial circle,

$$
\Phi(\sigma+2\pi)=g\cdot\Phi(\sigma),
$$

$[g]$ denotes a conjugacy class, and $C(g)$ is the centralizer of $g$, the subgroup that preserves the $g$-twisted boundary condition. For Abelian $G$, each element is its own conjugacy class and $C(g)=G$.

This formula is the Hilbert-space counterpart of the torus sum over twisted sectors.

:::caution[Orbifolds require an anomaly-free symmetry]
A finite symmetry can be orbifolded only when it is gaugeable. In modern language, there must be no obstruction or ’t Hooft anomaly for gauging it. This page assumes the symmetry is gaugeable.
:::

## The reflection orbifold of the compact boson

Start with the compact boson

$$
X\sim X+2\pi R.
$$

It has a reflection symmetry

$$
r:X\mapsto -X.
$$

This symmetry sends

$$
V_{n,m}\longmapsto V_{-n,-m}.
$$

The untwisted invariant primaries are therefore symmetric combinations such as

$$
V_{n,m}^{+}=\frac{1}{\sqrt2}\left(V_{n,m}+V_{-n,-m}\right),
\qquad (n,m)\ne (0,0),
$$

together with invariant oscillator operators such as

$$
\partial X\bar\partial X.
$$

Odd operators such as $\partial X$ are projected out as local operators in the untwisted sector.

But the orbifold also contains twisted sectors. A reflection-twisted field satisfies, up to the circle identification,

$$
X(\sigma+2\pi)=-X(\sigma)+2\pi kR.
$$

The reflection has two fixed points on the target circle:

$$
X=0,
\qquad X=\pi R.
$$

Accordingly, the $S^1_R/\mathbb Z_2$ orbifold has two basic twist fields, often denoted

$$
\sigma_0,
\qquad \sigma_{\pi R}.
$$

They have weights

$$
h=\bar h=\frac{1}{16}
$$

in the standard compact-boson normalization. A chiral half-mode excitation shifts one side by $1/2$, so fields with

$$
h=\frac{9}{16},
\qquad
\bar h=\frac{1}{16}
$$

and the right-moving analog appear. The doubly excited twist field has $h=\bar h=9/16$.

The twist fields are not optional decorations. They are the local operators that create branch-cut boundary conditions for $X$.

## What twist fields do

A twist field forces $X$ to change sign when carried around it. More precisely, near a reflection twist field $\sigma_a$, the chiral derivative has a half-integer branch behavior:

$$
\partial X(z)\sigma_a(0)
\sim
z^{-1/2}\tau_a(0)+\cdots,
$$

where $\tau_a$ is an excited twist field. The square-root singularity says that after circling the twist insertion, $\partial X$ changes sign.

The twist field is therefore a local way of inserting a branch point. On a torus, the same physics appears as antiperiodic boundary conditions around cycles. On a surface with many twist fields, branch cuts can be drawn between them, but the cuts are bookkeeping devices; only their endpoints and monodromy data are physical.

## Orbifolding versus quotienting

The geometric quotient $S^1/\mathbb Z_2$ is an interval. That picture is helpful but incomplete.

A CFT orbifold is a quantum construction. It remembers:

- the invariant untwisted operators,
- the twisted sectors at fixed points,
- projection rules inside twisted sectors,
- modular invariance on the torus,
- OPE closure among untwisted and twisted operators.

The twist-field OPE is the cleanest way to see why the interval picture is not enough. For example,

$$
\sigma_a(z,\bar z)\sigma_b(0,0)
$$

can contain untwisted-sector operators whose allowed momentum and winding depend on the fixed points $a,b$. Thus the twisted sector talks to the original compact-boson lattice.

The geometry gives the nouns. The OPE gives the grammar.

## Modular invariance and twisted sums

For the $\mathbb Z_2$ reflection orbifold, write

$$
Z_{a,b},\qquad a,b\in\{1,r\},
$$

where $a$ is the spatial twist and $b$ is the temporal insertion. The orbifold partition function is

$$
Z_{\mathrm{orb}}
=\frac12\left(Z_{1,1}+Z_{1,r}+Z_{r,1}+Z_{r,r}\right).
$$

The terms have different Hilbert-space interpretations:

| Term | Meaning |
|---|---|
| $Z_{1,1}$ | Original compact-boson trace. |
| $Z_{1,r}$ | Trace in the original Hilbert space with $r$ inserted; implements projection. |
| $Z_{r,1}$ | Trace over the reflection-twisted Hilbert space. |
| $Z_{r,r}$ | Twisted Hilbert space with reflection inserted. |

The modular group permutes these sectors. In particular, $S$ exchanges spatial and temporal cycles, so

$$
S:Z_{1,r}\longleftrightarrow Z_{r,1}.
$$

A projected-only theory would keep $Z_{1,1}$ and $Z_{1,r}$ but omit $Z_{r,1}$ and $Z_{r,r}$. Such an object is not modular invariant and is not a complete local CFT.

## Relation to the c = 1 moduli space

The compact boson is one branch of the $c=1$ moduli space. The reflection orbifold is another branch. They meet and intersect at special radii where enhanced symmetry or extra identifications appear.

At a generic radius, the circle theory and its reflection orbifold are different CFTs with the same central charge. At special radii, the theories can be related to familiar rational CFTs or products of simpler models. For example, certain $c=1$ orbifolds are related to combinations of Ising models, and the self-dual circle theory is tied to $SU(2)_1$ current algebra.

This is one of the main lessons of the $c=1$ story: a moduli space of CFTs is not just a list of Lagrangians. It is a web of theories related by dualities, orbifolds, enhanced symmetry, and modular consistency.

## General finite-group orbifolds

For a general finite group $G$, the construction follows the same logic.

First, there are sectors $\mathcal H_g$ labelled by twists around the spatial circle:

$$
\Phi(\sigma+2\pi)=g\cdot\Phi(\sigma).
$$

Second, states in $\mathcal H_g$ are projected onto invariants under the centralizer $C(g)$.

Third, the torus partition function sums over commuting twists:

$$
Z_{\mathrm{orb}}
=\frac{1}{|G|}\sum_{\substack{g,h\in G\\gh=hg}}Z_{g,h}.
$$

The commuting condition is simply flatness of the finite-group bundle on the torus: going around the two cycles in different orders must give the same total monodromy.

Some orbifolds have additional choices called **discrete torsion**, which weights sectors by phases compatible with modular invariance and factorization. This page does not develop that refinement, but it is important in string theory and in the modern defect-language formulation of orbifolds.

## Common pitfalls

**Orbifolding is not symmetry breaking.** In symmetry breaking, one chooses a vacuum that is not invariant. In orbifolding, one gauges the symmetry and keeps gauge-invariant physics.

**The invariant subsector alone is not the orbifold.** Projection without twisted sectors is usually not modular invariant and not closed under the full CFT consistency conditions.

**Fixed points matter.** When the group action has fixed points, twisted sectors often contain localized twist fields. The target-space quotient can be singular even when the CFT is perfectly sensible.

**Not every finite symmetry can be orbifolded.** A finite symmetry with an anomaly cannot be gauged without adding extra structure or a higher-dimensional bulk.

**Orbifolds can create new local operators.** Twist fields are local operators of the orbifold even though they are not ordinary local functions of the original fields.

**The word “orbifold” has several dialects.** In geometry it means a quotient space with stabilizers. In CFT it means a quantum gauging procedure. In string theory it often means both at once.

## Relations to other pages

- [Compact Boson](/cft-bootstrap/two-dimensional-cft/compact-boson/) gives the circle theory being orbifolded here.
- [Free Fermion CFT](/cft-bootstrap/two-dimensional-cft/free-fermion-cft/) explains the Ising/free-fermion side of several $c=1$ identifications.
- [Holomorphic Factorization](/cft-bootstrap/two-dimensional-cft/holomorphic-factorization/) explains why full CFTs are sums of products of chiral data.
- [Modular Invariance](/cft-bootstrap/modular-bootstrap/modular-invariance/) will develop the torus constraints behind the twisted-sector sum.
- [Rational CFT](/cft-bootstrap/minimal-models-rational-cft/rational-cft/) will explain rational points and finite chiral operator content.
- [Generalized Symmetries](/symmetry-anomalies-topology/generalized-symmetries/) will give the modern symmetry-and-defect perspective on finite gauging.

## Research status

The basic finite-group orbifold construction is settled and belongs to the standard toolkit of two-dimensional CFT and string theory. The $S^1/\mathbb Z_2$ compact-boson orbifold is one of the canonical examples.

The active frontier is conceptual unification. Orbifolds are now commonly phrased using topological defect lines, gauging of finite symmetries, anomalies, module categories, and generalized global symmetries. That language is more powerful, especially for non-invertible symmetries and rational CFT, but the compact-boson reflection orbifold remains the best place to learn the physics without getting mugged by notation in a dark alley.

## Exercises

### Exercise 1: Projection from a temporal insertion

Let $r^2=1$. Show that

$$
\frac12\operatorname{Tr}_{\mathcal H}\left((1+r)q^{L_0-c/24}\bar q^{\bar L_0-\bar c/24}\right)
$$

is the partition function of the $r$-invariant part of the untwisted Hilbert space.

<details><summary><strong>Solution</strong></summary>

The operator

$$
P_+=\frac12(1+r)
$$

is a projector because

$$
P_+^2=\frac14(1+2r+r^2)=\frac12(1+r)=P_+.
$$

If a state has $r$-eigenvalue $+1$, then $P_+$ acts as $1$. If it has $r$-eigenvalue $-1$, then $P_+$ acts as $0$. Therefore the trace with $P_+$ keeps precisely the invariant states. Equivalently,

$$
\frac12(Z_{1,1}+Z_{1,r})
$$

is the projected untwisted contribution.

</details>

### Exercise 2: Why a twisted sector is forced by modular S

For a $\mathbb Z_2$ orbifold, explain why keeping $Z_{1,r}$ but not $Z_{r,1}$ cannot be modular invariant.

<details><summary><strong>Solution</strong></summary>

The modular $S$ transformation exchanges the two torus cycles. A temporal insertion of $r$ with no spatial twist becomes a spatial twist with no temporal insertion:

$$
S:Z_{1,r}\mapsto Z_{r,1}.
$$

Therefore any modular-invariant sum containing $Z_{1,r}$ must also contain $Z_{r,1}$ with the matching coefficient. The term $Z_{r,1}$ is the trace over the $r$-twisted Hilbert space. Thus twisted sectors are required by modular invariance.

</details>

### Exercise 3: Fixed points of the reflection orbifold

For $X\sim X+2\pi R$ and $X\sim -X$, find the fixed points of the reflection action on the target circle.

<details><summary><strong>Solution</strong></summary>

A fixed point satisfies

$$
X=-X\quad \operatorname{mod} 2\pi R.
$$

Equivalently,

$$
2X=2\pi kR,
\qquad k\in\mathbb Z.
$$

Thus

$$
X=\pi kR.
$$

Modulo $2\pi R$, there are two inequivalent solutions:

$$
X=0,
\qquad X=\pi R.
$$

These are the two fixed points of $S^1_R/\mathbb Z_2$ and correspond to two basic twist fields.

</details>

### Exercise 4: Branch cut from the twist OPE

Suppose

$$
\partial X(z)\sigma(0)\sim z^{-1/2}\tau(0)+\cdots.
$$

What happens to $\partial X$ when it is analytically continued once around $\sigma$?

<details><summary><strong>Solution</strong></summary>

Taking $z\mapsto e^{2\pi i}z$ gives

$$
z^{-1/2}\mapsto e^{-\pi i}z^{-1/2}=-z^{-1/2}.
$$

Thus the leading term changes sign. This is the local operator statement that circling the twist insertion implements the reflection monodromy

$$
\partial X\mapsto -\partial X.
$$

</details>

## References

- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, especially the compactified boson, $\mathbb Z_2$ orbifold, modular invariance, and Ising bosonization material.
- L. Dixon, J. Harvey, C. Vafa, and E. Witten, classic papers on strings on orbifolds and twisted sectors.
- P. Ginsparg, *Applied Conformal Field Theory*, for a concise treatment of $c=1$ CFTs and orbifolds.
- P. Goddard, A. Kent, and D. Olive, work on coset constructions and related rational CFT structures.
- G. Moore and N. Seiberg, work on rational CFT consistency conditions, useful background for the modern view of orbifolds as part of the general sewing/modular-consistency problem.

## Version history

- 2026-06-28: First polished draft. Introduces finite symmetry gauging, projection, twisted sectors, modular-invariant torus sums, and the compact-boson reflection orbifold.
