---
title: "Symmetry Defects and Topological Operators"
description: "Explains how ordinary global symmetries can be represented by codimension-one topological operators, how these defects act on charged insertions, and why this viewpoint prepares the generalized-symmetry language."
sidebar:
  label: "Symmetry Defects"
  order: 6
level: Graduate
status: "Polished draft"
source: "Gaiotto–Kapustin–Seiberg–Willett; Coleman and Srednicki on charges and currents; standard topological-defect viewpoint in QFT and statistical mechanics."
topics:
  - symmetry defects
  - topological operators
  - Ward operators
  - charged insertions
  - selection rules
  - generalized symmetries
canonicalTopics:
  - symmetry-defect
  - topological-operator
  - invertible-defect
  - ward-operator
researchStatus:
  established:
    - "Ordinary global symmetries can be represented by invertible codimension-one topological operators whose crossing action reproduces the symmetry action on local operators."
    - "For continuous symmetries with conserved currents, the corresponding topological operators are exponentials of integrated charges."
  active:
    - "Modern generalized-symmetry research extends this viewpoint to higher-form, higher-group, non-invertible, categorical, and symmetry-TFT structures."
---

## Summary

An ordinary global symmetry can be described in two equivalent-looking but conceptually different ways.

The Hilbert-space language says that a symmetry element $g\in G$ is implemented by a unitary operator $U(g)$ acting on states and local operators.

The spacetime language says that the same symmetry can be inserted as a **codimension-one topological operator** $U_g(\Sigma)$ supported on a closed hypersurface $\Sigma$. The word *topological* means that $\Sigma$ can be smoothly deformed without changing correlation functions, as long as it does not cross charged insertions.

When the symmetry defect crosses a local operator, it acts by the symmetry representation:

$$
U_g(\Sigma)\,\mathcal O_i(x)
\quad\leadsto\quad
R(g)_i{}^j\mathcal O_j(x),
$$

where the arrow means equality inside correlation functions after moving the defect through the insertion. For a $U(1)$ charge-$q$ operator,

$$
\mathcal O_q\quad\mapsto\quad e^{iq\alpha}\mathcal O_q.
$$

This is the finite, geometric version of a Ward identity. Instead of writing an infinitesimal current conservation equation, one inserts a symmetry wall, slides it around, and records what it crosses.

<figure class="doc-figure" style="--figure-width: 48rem;">

![A symmetry defect surrounding a charged local operator can be deformed freely until it crosses the operator, at which point the operator transforms by its representation.](/figures/symmetry-anomalies-topology/ordinary-symmetry-defect-deformation.svg)

<figcaption>

An ordinary $0$-form symmetry element $g$ is represented by a codimension-one topological operator $U_g(\Sigma)$. The surface $\Sigma$ can be deformed freely away from insertions. Crossing a charged local operator $\mathcal O_i$ applies the representation matrix $R(g)_i{}^j$.

</figcaption>
</figure>

This viewpoint is not decorative. It is the bridge to higher-form symmetries, non-invertible symmetries, anomalies, twist defects, gauging, orbifolds, and symmetry TFT.

## Prerequisites

You should know [What Is a Symmetry?](/symmetry-anomalies-topology/ordinary-global-symmetries/what-is-a-symmetry/), [Symmetry Groups and Representations](/symmetry-anomalies-topology/ordinary-global-symmetries/symmetry-groups-and-representations/), and [Action on Fields and Operators](/symmetry-anomalies-topology/ordinary-global-symmetries/action-on-fields-and-operators/).

We use the convention

$$
U(\alpha)=e^{-i\alpha^aQ_a},
\qquad
U(\alpha)^\dagger\mathcal O_iU(\alpha)
=\mathcal O_i+i\alpha^a[Q_a,\mathcal O_i]+O(\alpha^2).
$$

The next page, [Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/), explains the canonical charge operator in detail. This page explains the same symmetry in spacetime-defect language.

## Core idea

A symmetry defect is a controlled discontinuity.

Imagine cutting spacetime along a codimension-one hypersurface $\Sigma$. On one side of the cut, describe the fields or operators normally. When an object crosses the cut, glue it back by the symmetry transformation $g$. If $g$ is a genuine symmetry, the location of the cut should not matter. Moving the cut through empty spacetime changes no observable. Moving it through a charged insertion transforms that insertion.

This is why symmetry defects are topological. They are not physical membranes with tension. They are bookkeeping surfaces implementing a symmetry action.

The key data are:

| Data | Meaning |
|---|---|
| $U_g(\Sigma)$ | Defect operator supported on a closed codimension-one hypersurface. |
| Topological invariance | $U_g(\Sigma)$ can be deformed away from insertions. |
| Crossing rule | Moving $U_g$ through $\mathcal O_i$ gives $R(g)_i{}^j\mathcal O_j$. |
| Fusion | Parallel defects multiply as $U_gU_h=U_{gh}$. |
| Inverse | $U_g^{-1}=U_{g^{-1}}$. |
| Orientation | Reversing orientation exchanges $g$ with $g^{-1}$ in the usual convention. |

For ordinary global symmetries these defects are **invertible**. Later chapters relax this assumption. In a non-invertible symmetry, fusing defects can produce a sum of defects rather than a single inverse element. But ordinary symmetries are the clean starting case.

## Setup and conventions

Work in $d$ spacetime dimensions. A codimension-one hypersurface $\Sigma$ has dimension $d-1$. For an ordinary global symmetry group $G$, associate to each $g\in G$ a defect operator

$$
U_g(\Sigma).
$$

If $\Sigma$ is closed and does not pass through operator insertions, topological invariance means that

$$
\langle U_g(\Sigma)\,\mathcal X\rangle
=
\langle U_g(\Sigma')\,\mathcal X\rangle
$$

whenever $\Sigma$ and $\Sigma'$ are smoothly deformable into one another without crossing the insertions in $\mathcal X$.

For a continuous symmetry with conserved current $j_a^\mu$, the charge on an oriented hypersurface is

$$
Q_a(\Sigma)=\int_\Sigma d\Sigma_\mu\,j_a^\mu.
$$

Equivalently, if $J_a=*j_a$ is the Hodge-dual $(d-1)$-form current, then

$$
Q_a(\Sigma)=\int_\Sigma J_a.
$$

The finite symmetry defect near the identity is

$$
U_\alpha(\Sigma)=\exp\left(-i\alpha^aQ_a(\Sigma)\right).
$$

Current conservation is

$$
\partial_\mu j_a^\mu=0,
$$

or, in differential-form language,

$$
dJ_a=0.
$$

If $\Sigma$ and $\Sigma'$ bound a region $M$ with no insertions, Stokes' theorem gives

$$
Q_a(\Sigma)-Q_a(\Sigma')=\int_M dJ_a=0.
$$

That is the Noether-current origin of topological deformability.

:::note[Convention-sensitive source note]
The sign in $U_\alpha(\Sigma)=\exp(-i\alpha^aQ_a(\Sigma))$ follows the volume convention $U(\alpha)=e^{-i\alpha^aQ_a}$. Reversing the orientation of $\Sigma$ flips $Q_a(\Sigma)$. Sources using $U\mathcal O U^{-1}$ rather than $U^\dagger\mathcal O U$ will write the crossing rule with inverse representation matrices.
:::

## The crossing rule

Let $\mathcal O_i(x)$ be a local operator transforming in representation $R$. If a small symmetry sphere $S_x^{d-1}$ surrounds $x$, then inserting $U_g(S_x^{d-1})$ acts on the operator:

$$
U_g(S_x^{d-1})\,\mathcal O_i(x)
=R(g)_i{}^j\mathcal O_j(x),
$$

where the equality is understood inside correlation functions and with the same orientation convention as above.

For a $U(1)$ operator of charge $q$,

$$
U_\alpha(S_x^{d-1})\,\mathcal O_q(x)
=e^{iq\alpha}\mathcal O_q(x).
$$

For a finite $\mathbb Z_N$ symmetry with generator $r$, an operator of charge $k\in\mathbb Z_N$ obeys

$$
U_r(S_x^{d-1})\,\mathcal O_k(x)
=e^{2\pi i k/N}\mathcal O_k(x).
$$

For a nonabelian group, $R(g)$ is a matrix, and the defect can rotate an operator multiplet:

$$
U_g(S_x^{d-1})\,\mathcal O_i(x)
=R(g)_i{}^j\mathcal O_j(x).
$$

This crossing rule is often the most compact definition of the symmetry action. It does not require elementary fields. It only requires the operator content of the QFT.

## Ward identities as sliding identities

The usual Ward identity says that a conserved current can be moved through a correlation function, producing contact terms when it hits charged operators.

The defect version says the same thing more geometrically.

Place a defect $U_g(\Sigma)$ around several local operators. Slide $\Sigma$ outward until it encloses no insertions. If the vacuum and boundary conditions are invariant, the far-away defect can be removed. The only effect comes from the crossings. Therefore the product of representation matrices must leave the correlator invariant.

For a $U(1)$ symmetry,

$$
\langle\mathcal O_{q_1}(x_1)\cdots\mathcal O_{q_n}(x_n)\rangle
=e^{i\alpha(q_1+\cdots+q_n)}
\langle\mathcal O_{q_1}(x_1)\cdots\mathcal O_{q_n}(x_n)\rangle.
$$

If this holds for every $\alpha$, then

$$
\langle\mathcal O_{q_1}(x_1)\cdots\mathcal O_{q_n}(x_n)\rangle\ne0
\quad\Longrightarrow\quad
\sum_i q_i=0.
$$

For a nonabelian symmetry, the same sliding argument says that the correlator is an invariant tensor in the product of representations carried by the insertions. The defect language turns “charge conservation” into “topological invariance plus crossing rules.”

## Continuous symmetries from current flux

For continuous symmetries, symmetry defects near the identity are built from fluxes of the Noether current.

Take a spatial Cauchy surface $\Sigma_t$ in Lorentzian signature. Then

$$
Q_a(t)=\int_{\Sigma_t}d^{d-1}\mathbf x\,j_a^0(t,\mathbf x).
$$

More invariantly,

$$
Q_a(\Sigma)=\int_\Sigma d\Sigma_\mu\,j_a^\mu.
$$

If $\partial_\mu j_a^\mu=0$ and no charge leaks through the boundary at infinity, then $Q_a(\Sigma)$ depends only on the homology class of $\Sigma$ relative to insertions. A small sphere around a local operator measures how that operator transforms. A large sphere around the whole correlator measures the total charge.

This is why a conserved current is more than a local formula. It produces a topological operator:

$$
\exp\left(-i\alpha^a\int_\Sigma d\Sigma_\mu\,j_a^\mu\right).
$$

The topological property may fail if the current is not conserved, if there is an anomaly, if boundary conditions break the symmetry, or if the surface crosses a charged operator.

## Discrete symmetries do not need currents

A discrete symmetry usually has no infinitesimal current. There is no local Noether current whose integral gives the generator of a $\mathbb Z_2$ spin-flip symmetry.

But the defect still exists.

For example, in an Ising-like theory with spin-flip symmetry,

$$
\sigma\mapsto -\sigma,
\qquad
\varepsilon\mapsto \varepsilon,
$$

one can draw a codimension-one defect line or surface such that crossing it flips the sign of $\sigma$ and leaves even operators unchanged. Away from endpoints and charged insertions, this defect is topological when the symmetry is exact.

This is one of the reasons the defect viewpoint is powerful: it treats continuous and discrete symmetries uniformly. Continuous symmetries have currents near the identity. Discrete symmetries have defects but no infinitesimal current.

## Defects are not ordinary domain walls

A symmetry defect is sometimes drawn as a wall, but it is not usually a physical wall separating two different phases.

A physical domain wall is a dynamical or allowed boundary-condition object. It can have tension, localized degrees of freedom, scattering, and shape-dependent energy. Its position matters.

A symmetry defect is a topological insertion. Its position does not matter as long as it avoids charged insertions. It implements a change of variables across a cut.

The distinction is sharp:

| Object | Position dependence | Physical role |
|---|---|---|
| Symmetry defect | Topological; can slide | Implements a global symmetry action. |
| Physical domain wall | Generally geometric and energetic | Separates vacua or phases. |
| Boundary/interface | Usually has local data | Changes the theory or boundary condition. |
| Anomaly inflow wall | Topological or invertible in special cases | Encodes anomaly or SPT response. |

In spontaneously broken discrete symmetries, physical domain walls and symmetry defects can be related, but they are not the same object.

## Fusion and invertibility

If two parallel symmetry defects are placed on the same hypersurface, they fuse:

$$
U_g(\Sigma)U_h(\Sigma)=U_{gh}(\Sigma).
$$

The identity element gives the transparent defect:

$$
U_e(\Sigma)=1.
$$

Every ordinary symmetry defect has an inverse:

$$
U_g(\Sigma)^{-1}=U_{g^{-1}}(\Sigma).
$$

For nonabelian $G$, the order matters:

$$
U_gU_h\ne U_hU_g
$$

in general. The geometric order is controlled by how the defects are stacked or radially ordered.

This is exactly why ordinary global symmetries are called **invertible** symmetries in the modern language. Later, non-invertible defects obey fusion rules such as

$$
\mathcal N\times\mathcal N=1+\eta,
$$

or more complicated categorical generalizations. Ordinary group symmetries are the special case where fusion reproduces group multiplication and every defect has an inverse.

## Twisted sectors and background fields

Putting a symmetry defect along a nontrivial cycle is the same as imposing a twisted boundary condition.

For example, on a Euclidean spacetime with a circle direction, inserting a $g$-defect along a cut transverse to the circle means that fields are glued by $g$ after going around the circle:

$$
\Phi(\tau+\beta,\mathbf x)=g\cdot\Phi(\tau,\mathbf x).
$$

For $g=e^{i\alpha}$ in a $U(1)$ symmetry, this is the operator-path-integral version of inserting $e^{-i\alpha Q}$ in the trace:

$$
Z(\alpha)=\operatorname{Tr}_{\mathcal H}\left(e^{-\beta H}e^{-i\alpha Q}\right).
$$

For finite symmetries, summing over such twisted sectors is the beginning of gauging or orbifolding. For continuous symmetries, smooth background gauge fields generalize the same idea.

This is why the next chapter on background fields and gauging should feel like a continuation of this page, not a separate subject.

## Genuine operators and attached defects

A local operator is **genuine** if it can be inserted at a point without choosing extra lower-dimensional attachments. In ordinary scalar examples this sounds automatic. In gauge theories, dualities, and generalized symmetries, it is not.

A disorder operator may need a branch cut. A line operator may need a surface attached to it. A surface operator may need higher-dimensional data. The distinction between genuine and non-genuine operators is one of the central technical clarifications in modern generalized symmetry.

For ordinary global symmetry defects in this page, $U_g(\Sigma)$ itself is genuine as a closed topological operator. If it ends, the endpoint must be a defect-changing operator or a charged object. A symmetry wall cannot simply stop in empty spacetime.

The slogan is:

$$
\partial\Sigma=\varnothing
\quad\text{unless the boundary is explained by another operator.}
$$

## Examples

### Complex scalar with U(1) symmetry

Let a complex scalar carry charge $+1$:

$$
\phi\mapsto e^{i\alpha}\phi.
$$

The Noether current is convention-dependent in sign, but once the charge operator is normalized so that

$$
[Q,\phi]=\phi,
$$

then

$$
U_\alpha^\dagger\phi U_\alpha=e^{i\alpha}\phi.
$$

The symmetry defect is

$$
U_\alpha(\Sigma)=\exp\left(-i\alpha\int_\Sigma *j\right).
$$

Sliding it across $\phi$ multiplies the insertion by $e^{i\alpha}$; sliding it across $\phi^\dagger$ multiplies the insertion by $e^{-i\alpha}$.

### Ising spin-flip symmetry

In the Ising universality class at zero magnetic field, the $\mathbb Z_2$ symmetry acts as

$$
\sigma\mapsto -\sigma,
\qquad
\varepsilon\mapsto \varepsilon.
$$

The corresponding topological defect line changes the sign of every spin-field insertion it crosses. Correlators with an odd number of $\sigma$ insertions vanish because a defect can be moved from surrounding all insertions to nothing, producing a minus sign.

### Nonabelian flavor symmetry

Suppose local operators $\mathcal O_i$ form a multiplet of a nonabelian group $G$:

$$
U_g(S_x^{d-1})\mathcal O_i(x)=R(g)_i{}^j\mathcal O_j(x).
$$

A two-point function of operators in conjugate representations can be invariant because there is an invariant tensor pairing them. A correlator of operators whose tensor product contains no singlet vanishes.

The defect version and the representation version are the same statement in different clothing.

## Common pitfalls

**Thinking “topological” means the theory is a TQFT.** The full QFT need not be topological. Only the symmetry defect is topological.

**Confusing symmetry defects with physical domain walls.** A physical domain wall has dynamics and tension. A symmetry defect implements a gluing rule and can slide freely.

**Assuming every topological defect is an ordinary symmetry.** Ordinary symmetry defects are invertible and fuse by group multiplication. General topological defects may be non-invertible or may not act faithfully on all operators.

**Looking only for currents.** Continuous symmetries have Noether currents when the usual assumptions hold. Discrete symmetries do not, but they still have symmetry defects.

**Forgetting orientation.** Reversing the orientation of a symmetry defect replaces $g$ by $g^{-1}$ in the usual convention.

**Letting defects end without explanation.** A topological symmetry defect cannot have an arbitrary boundary. Its boundary must be an operator, another defect, or a specified boundary condition.

**Ignoring anomalies.** An anomalous symmetry can often be represented by topological operators only after including an inflow bulk or extra background data. Obstruction to consistent topological motion is one way anomalies show up.

## Relations to other pages

[Charges and Hilbert Space](/symmetry-anomalies-topology/ordinary-global-symmetries/charges-and-hilbert-space/) develops the canonical charge operator $Q$ and the sector decomposition of $\mathcal H$.

[Selection Rules](/symmetry-anomalies-topology/ordinary-global-symmetries/selection-rules/) turns the sliding-defect argument into practical correlator constraints.

The [Noether Currents and Ward Identities](/symmetry-anomalies-topology/noether-currents-ward-identities/) chapter derives the infinitesimal current identities that become topological defect motion after exponentiation.

The [Background Fields and Gauging](/symmetry-anomalies-topology/background-fields-and-gauging/) chapter explains how defects along nontrivial cycles become twisted sectors and background bundles.

The [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) chapter generalizes $U_g(\Sigma^{d-1})$ to symmetry operators supported on codimension $q+1$ manifolds.

The [Non-Invertible and Categorical Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/) chapter relaxes invertibility and replaces group multiplication by defect fusion rules.

## Research status

For ordinary global symmetries, the defect formulation is established and widely used in QFT, statistical mechanics, conformal field theory, and topological phases.

The active frontier is the expansion of the word “symmetry.” Higher-form symmetries are generated by topological operators of higher codimension. Non-invertible symmetries are generated by topological defects with fusion rules not given by a group. Symmetry TFT packages symmetry defects, charged operators, background fields, and anomalies into a bulk topological theory. The ordinary symmetry defect on this page is the minimal example of that larger story.

## Exercises

### Exercise 1: Topological invariance from current conservation

Let $J=*j$ be a conserved $(d-1)$-form current, so $dJ=0$. Suppose $\Sigma$ and $\Sigma'$ are homologous closed hypersurfaces bounding a region $M$ with no operator insertions. Show that

$$
\int_\Sigma J=\int_{\Sigma'}J.
$$

<details><summary><strong>Solution</strong></summary>

With orientations chosen so that $\partial M=\Sigma-\Sigma'$, Stokes' theorem gives

$$
\int_\Sigma J-\int_{\Sigma'}J
=\int_{\partial M}J
=\int_M dJ.
$$

Since $dJ=0$, the difference vanishes. Therefore the charge depends only on the homology class of the surface, as long as the deformation does not cross charged insertions or boundaries with flux.

</details>

### Exercise 2: Selection rule from a U(1) defect

Let $\mathcal O_{q_i}(x_i)$ carry $U(1)$ charge $q_i$. Use a large $U_\alpha$ defect enclosing all insertions to prove the neutrality condition for a nonzero correlator.

<details><summary><strong>Solution</strong></summary>

A large defect enclosing all insertions can be shrunk through the insertions, giving

$$
\langle\mathcal O_{q_1}\cdots\mathcal O_{q_n}\rangle
=e^{i\alpha\sum_i q_i}
\langle\mathcal O_{q_1}\cdots\mathcal O_{q_n}\rangle.
$$

Alternatively, the same large defect can be moved away and removed if the vacuum and boundary conditions are invariant. Therefore the correlator must equal itself times $e^{i\alpha\sum_iq_i}$ for every $\alpha$. If the correlator is nonzero, then $\sum_iq_i=0$.

</details>

### Exercise 3: Fusion for a finite symmetry

Let $G=\mathbb Z_N$ with generator $r$. Show that the corresponding symmetry defects obey

$$
U_{r^a}(\Sigma)U_{r^b}(\Sigma)=U_{r^{a+b}}(\Sigma),
$$

with $a+b$ understood modulo $N$.

<details><summary><strong>Solution</strong></summary>

Crossing both defects applies first $r^b$ and then $r^a$ to any charged operator, depending on the stacking convention. Since the group law is $r^ar^b=r^{a+b}$ and $r^N=e$, the combined defect has the same crossing action as $U_{r^{a+b}}$. Topological defects are determined by their action and fusion data, so the fusion law follows.

</details>

### Exercise 4: Why a symmetry defect cannot end in empty space

Explain why a codimension-one symmetry defect with a boundary would violate topological invariance unless the boundary is decorated by an operator or another defect.

<details><summary><strong>Solution</strong></summary>

A closed symmetry defect can be deformed without changing correlation functions because it represents a global symmetry action. If the defect ended in empty space, a small sphere linking its endpoint would detect a nontrivial crossing rule without any charged insertion to account for it. Moving the endpoint would create local changes in correlation functions, so the defect would no longer be topological. A boundary of the defect must therefore be a specified object: a charged operator, a defect-changing operator, a boundary condition, or another defect that absorbs the discontinuity.

</details>

## References

- Davide Gaiotto, Anton Kapustin, Nathan Seiberg, and Brian Willett, “Generalized Global Symmetries,” *JHEP* 02 (2015) 172.
- Sakura Schafer-Nameki, “ICTP Lectures on (Non-)Invertible Generalized Symmetries,” arXiv:2305.18296.
- Sidney Coleman, *Lectures of Sidney Coleman on Quantum Field Theory*, lectures on symmetries and conservation laws.
- Sidney Coleman, *Aspects of Symmetry*, especially lectures on unitary symmetry, soft pions, and topological conservation laws.
- Mark Srednicki, *Quantum Field Theory*, sections 22–24.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. I, chapters on symmetries and representations.

## Version history

- **2026-06-17:** First polished draft for the Ordinary Global Symmetries chapter.
