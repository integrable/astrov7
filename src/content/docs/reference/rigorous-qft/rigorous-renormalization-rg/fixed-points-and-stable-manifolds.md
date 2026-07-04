---
title: "Fixed Points and Stable Manifolds"
description: "Explains RG fixed points and stable manifolds as the dynamical-systems structure behind critical tuning, universality, and renormalized trajectories."
sidebar:
  label: "Fixed Points and Stable Manifolds"
  order: 5
level: Advanced
status: "Polished draft"
source: "Wilson–Kogut; Wegner; Polchinski; constructive RG and dynamical-systems literature"
topics:
  - RG fixed points
  - stable manifolds
  - critical surfaces
  - universality
  - rigorous RG
canonicalTopics:
  - rg-fixed-points
  - stable-manifolds
  - rigorous-renormalization
researchStatus:
  established:
    - "Fixed points and stable manifolds give the precise dynamical-systems language behind relevant directions, critical tuning, and universality whenever the RG map is controlled in a suitable function space."
  active:
    - "In realistic QFTs the hard part is not drawing the phase portrait, but proving the required finite- or infinite-dimensional estimates for the exact RG map."
---

## Summary

An RG fixed point is a theory, measure, effective interaction, or local net that is unchanged by a renormalization step, after the appropriate rescaling of lengths and fields. If $\mathcal R_b$ is an RG transformation with scale factor $b>1$, a fixed point is an object $g_*$ satisfying

$$
\mathcal R_b(g_*)=g_*.
$$

The stable manifold of $g_*$ is the set of initial theories whose repeated RG iterates approach $g_*$. It is the mathematical version of the critical surface. If $g$ lies on this surface, the large-distance limit is controlled by the fixed point; if $g$ has a component in a relevant direction, repeated coarse-graining drives it away unless that component is tuned.

In a finite-dimensional toy model, this is standard dynamical systems. In a rigorous RG construction, the same idea appears in a Banach space of effective interactions, often split into local coupling coordinates plus an irrelevant remainder:

$$
V_j=V_j^{\mathrm{loc}}+K_j.
$$

The stable-manifold language explains why the previous page's classification into relevant, irrelevant, and marginal directions is not just terminology. It is the local geometry of the RG flow.

## Prerequisites

Read [Renormalization as a Map of Measures](/rigorous-qft/rigorous-renormalization-rg/renormalization-as-map-of-measures/), [Wilsonian RG: Rigorous View](/rigorous-qft/rigorous-renormalization-rg/wilsonian-rg-rigorous-view/), [Scaling Limits](/rigorous-qft/rigorous-renormalization-rg/scaling-limits/), and [Relevant, Irrelevant, and Marginal Directions](/rigorous-qft/rigorous-renormalization-rg/relevant-irrelevant-and-marginal-directions/) first. You should also know why a continuum limit requires tuning in [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/).

## Core idea

The renormalization group turns the space of theories into a dynamical system. A single point in this space is not just one coupling constant. It may encode a full cutoff measure, an effective action, a polymer activity, a collection of Schwinger functions, or a local algebraic structure. But once an RG step is defined, the language of dynamical systems becomes unavoidable.

A fixed point is a scale-invariant object. A stable manifold is a collection of microscopic objects that forget enough of their microscopic detail to approach that scale-invariant object at long distances. An unstable direction is a perturbation that grows under coarse-graining. A center direction is marginal at linear order and must be analyzed by nonlinear terms.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Fixed point and stable manifold](/figures/rigorous-qft/fixed-point-stable-manifold.svg)

<figcaption>

The stable manifold $W^s(g_*)$ is the local critical surface: points on it flow toward the fixed point under coarse-graining. Relevant directions leave the fixed point unless tuned; marginal directions require nonlinear analysis.

</figcaption>
</figure>

The mental model is:

$$
\text{critical behavior}
=\text{approach to a fixed point along its stable manifold}.
$$

This is also the reason universality can be true. Many different microscopic theories can lie on, or be tuned onto, the same stable manifold. Their long-distance observables then share the same fixed-point data, even though their short-distance definitions differ.

## Setup and conventions

Let $X$ be a space of cutoff theories. Depending on the framework, $X$ may be a finite-dimensional coordinate chart of couplings, a Banach space of effective interactions, a space of probability measures, or a space of local observables with scale-dependent structure. An RG step is a partially defined map

$$
\mathcal R:X\supset U\longrightarrow X.
$$

For a discrete Wilsonian RG, iteration means

$$
g_0\longmapsto g_1=\mathcal R(g_0)
\longmapsto g_2=\mathcal R(g_1)
\longmapsto \cdots .
$$

For an infinitesimal RG, one writes a flow

$$
\frac{dg}{d\ell}=\beta(g),
\qquad \ell=\log b.
$$

The finite-step and infinitesimal pictures are related only when enough regularity exists. Rigorous constructive RG often works with finite steps because each step has a concrete interpretation as Gaussian integration over one covariance shell followed by localization, rescaling, and estimates.

A fixed point is an element $g_*$ satisfying

$$
\mathcal R(g_*)=g_*.
$$

The local stable set is

$$
W^s_{\mathrm{loc}}(g_*)
=\{g\in U:\mathcal R^n(g)\in U
\text{ and }\mathcal R^n(g)\to g_*\}.
$$

In a Banach-space RG proof, convergence must be stated in a norm adapted to the scale decomposition. A weak slogan such as “the flow goes to the fixed point” is not a theorem until the topology and domain of the RG map are specified.

## Linearization and eigenspaces

Near a fixed point, write

$$
g=g_*+h.
$$

If $\mathcal R$ is differentiable at $g_*$, then

$$
\mathcal R(g_*+h)=g_*+Lh+N(h),
$$

where

$$
L=D\mathcal R\big|_{g_*},
\qquad
N(h)=O(\|h\|^2).
$$

The linearized map $L$ is the first approximation to the RG geometry. If $Lh_i=\lambda_i h_i$, then repeated iteration gives

$$
L^n h_i=\lambda_i^n h_i.
$$

For a finite RG scale factor $b$, it is common to write

$$
\lambda_i=b^{y_i}.
$$

The sign of $y_i$ gives the first-order classification:

| Direction | Linearized behavior | RG meaning |
|---|---|---|
| $|\lambda_i|<1$ | contracts | stable / irrelevant |
| $|\lambda_i|>1$ | expands | unstable / relevant |
| $|\lambda_i|=1$ | undecided | center / marginal |

The stable, unstable, and center subspaces are denoted schematically by

$$
E^s,
\qquad E^u,
\qquad E^c.
$$

In QFT applications these are rarely literal finite-dimensional vector spaces of all possible perturbations. More often, one has a finite-dimensional local part and an infinite-dimensional irrelevant remainder. The useful split is not simply “all functions of the field” versus “all couplings,” but a carefully chosen coordinate system in which the nonlocal remainder contracts.

## The stable-manifold theorem as an RG template

For a smooth map near a hyperbolic fixed point in finite dimensions, the stable-manifold theorem says that there is a local stable manifold tangent to $E^s$ at the fixed point:

$$
T_{g_*}W^s_{\mathrm{loc}}(g_*)=E^s.
$$

If the unstable subspace has dimension $r$, then the stable manifold has codimension $r$. This is the mathematical form of the statement that $r$ relevant parameters must be tuned to reach criticality.

In QFT language:

$$
\text{number of relevant directions}
=\text{number of tuning conditions}
$$

provided the fixed point is sufficiently controlled and there are no additional marginal complications.

For a scalar lattice model with a $\mathbb Z_2$ symmetry near the Gaussian fixed point, the main relevant coordinate is often the mass or temperature-like variable. To reach the critical surface, one tunes this coordinate as a function of the bare quartic coupling and cutoff. The stable manifold is not usually the hyperplane $m^2=0$; rather, it is a curved surface

$$
m_0^2=m_c^2(g_0,\Lambda)
$$

in bare parameter space. The curvature of this surface encodes counterterms.

## Critical surfaces and renormalized trajectories

There are two complementary ways to look at the same fixed point.

First, the stable manifold contains microscopic theories that flow into the fixed point in the infrared. This is the critical surface. A point off the critical surface has a relevant component, such as a nonzero mass scale, and eventually flows away. In statistical mechanics this corresponds to finite correlation length.

Second, one can follow unstable directions away from the fixed point in the opposite direction. Such curves are often called renormalized trajectories. They describe continuum theories obtained by tuning into the fixed point in the ultraviolet and then flowing away along physical relevant parameters.

A schematic statement is

$$
\text{renormalized trajectory}
=\text{flow line with all irrelevant coordinates fixed by stability}.
$$

For example, in a renormalizable perturbative QFT, the bare irrelevant couplings are not arbitrary if one asks for a cutoff-independent continuum limit. They are fixed, order by order or nonperturbatively, as functions of the relevant and marginal physical parameters.

## Why the critical surface is not the same as a phase boundary

In elementary pictures, the critical surface is sometimes drawn as the boundary between phases. This can be useful, but it can mislead.

A phase boundary is a statement about macroscopic phases. A stable manifold is a statement about approach to a fixed point under a specified RG map. The two may coincide locally near an ordinary continuous phase transition, but they are not the same object. A first-order transition has a phase boundary without a critical fixed point. A crossover region can have a long flow near a fixed point without lying exactly on a critical surface. A theory can also pass near several fixed points, producing several approximate scaling regimes.

The stable-manifold viewpoint is therefore more precise than the phrase “the critical line.” It asks: which fixed point, which RG map, which coordinates, which topology, and which asymptotic region?

## Marginal directions and center manifolds

If a direction has $|\lambda|=1$, linearization does not decide stability. The nonlinear terms matter. Suppose an infinitesimal beta function has the form

$$
\frac{dg}{d\ell}=a g^2+O(g^3).
$$

Then the sign of $a$ and the direction of RG time determine whether $g$ is marginally relevant or marginally irrelevant. This is why the word marginal is incomplete unless one also says “exactly,” “marginally relevant,” “marginally irrelevant,” or “undecided at this order.”

The center-manifold theorem is the dynamical-systems analog of what physicists do with marginal couplings: reduce the problem to the nonlinearity on the center directions. In four-dimensional scalar $\phi^4$ theory, the quartic coupling is marginal at the Gaussian fixed point by engineering dimension, but the nonlinear beta function is decisive. In non-Abelian Yang–Mills theory, the sign is different and asymptotic freedom becomes possible.

For rigorous RG, marginal directions are hard because a linear contraction estimate is unavailable. One often needs carefully improved coordinates, logarithmic weights, or a flow analysis that proves slow decay such as

$$
g_j\sim \frac{1}{c j}
$$

rather than exponential contraction.

## Example: the Gaussian fixed point

Consider a scalar field in $d$ Euclidean dimensions. At the Gaussian fixed point, the engineering dimension of the field is

$$
\Delta_\phi^{(0)}=\frac{d-2}{2}.
$$

A monomial perturbation $\phi^n$ has coupling exponent

$$
y_n=d-n\frac{d-2}{2}.
$$

For the quartic perturbation,

$$
y_4=4-d.
$$

Thus:

| Dimension | Quartic direction at the Gaussian fixed point | Meaning |
|---:|---|---|
| $d<4$ | relevant | Interactions matter in the infrared near the Gaussian point. |
| $d=4$ | marginal at linear order | Nonlinear beta function and logarithms decide the flow. |
| $d>4$ | irrelevant | The Gaussian fixed point controls broad critical behavior. |

The mass term has exponent $y_2=2$, so it is relevant in all dimensions. This is why tuning the mass or temperature is unavoidable in scalar critical phenomena.

## Example: Wilson–Fisher fixed point

In $d=4-\epsilon$, the Gaussian fixed point has a weakly relevant quartic direction. Perturbation theory finds a nearby non-Gaussian fixed point at coupling of order $\epsilon$. In an appropriate coordinate system, this Wilson–Fisher fixed point has a small number of relevant directions and many irrelevant directions.

The important conceptual lesson is not the first coefficient of the beta function. It is the change of coordinates. At the interacting fixed point, the scaling operators are not simply the bare monomials $\phi^2$, $\phi^4$, and so on. They are eigenoperators of the linearized RG at that fixed point. Their dimensions include anomalous contributions.

From the stable-manifold viewpoint, universality near the Wilson–Fisher point means that many microscopic models can be tuned onto the same stable manifold and then approach the same fixed point. Their critical exponents and scaling functions are controlled by the same eigenvalues and eigenvectors of the linearized RG.

## What a rigorous proof must add

The phase portrait is not the proof. A rigorous RG proof must supply at least the following data.

| Ingredient | What must be proved |
|---|---|
| Space of interactions | A normed or topological space where the RG map is defined. |
| Exact RG step | A genuine integration/rescaling/localization map, not only a diagram. |
| Local coordinates | A controlled projection onto relevant, marginal, and selected local irrelevant terms. |
| Remainder norm | A norm in which nonlocal or irrelevant terms contract. |
| Stable surface | Existence and regularity of a tuned surface of initial conditions. |
| Uniform estimates | Bounds independent of volume and cutoff, strong enough for a limit. |
| Observables | Convergence of correlation functions, fields, or other observables. |

This is why constructive RG papers look more like analysis than like beta-function calculations. The beta function tracks a few coordinates. The proof controls the whole map.

## Common pitfalls

**Treating the drawing as the theorem.** A phase portrait helps, but it is not a proof of a fixed point or a stable manifold. The proof requires a specified space, map, norm, and estimates.

**Confusing relevant directions with physical importance.** Irrelevant operators can affect amplitudes, corrections to scaling, finite-size effects, and matching. “Irrelevant” means contracting near a fixed point, not uninteresting.

**Assuming the stable manifold is linear.** It is tangent to the stable subspace at the fixed point, but away from the fixed point it is generally curved. Counterterm tuning is often the curvature of this manifold in disguise.

**Forgetting marginal nonlinearities.** A marginal eigenvalue is only a first-order statement. The nonlinear beta function can turn it into a marginally relevant, marginally irrelevant, or exactly marginal direction.

**Using the wrong RG time direction.** Particle-physics beta functions are often written toward the ultraviolet; statistical-mechanics coarse-graining is usually toward the infrared. The words relevant and irrelevant must be interpreted with the chosen flow direction.

## Relations to other pages

- [Relevant, Irrelevant, and Marginal Directions](/rigorous-qft/rigorous-renormalization-rg/relevant-irrelevant-and-marginal-directions/) gives the linearized classification used here.
- [Scaling Limits](/rigorous-qft/rigorous-renormalization-rg/scaling-limits/) explains the limiting objects that stable-manifold tuning is meant to produce.
- [Rigorous φ⁴ Renormalization](/rigorous-qft/rigorous-renormalization-rg/rigorous-phi-four-renormalization/) applies this language to the scalar $\phi^4$ family.
- [Continuum Limit and Renormalization](/rigorous-qft/constructive-qft/continuum-limit-and-renormalization/) gives the constructive-QFT side of cutoff removal.
- [What Is Open in Four Dimensions](/rigorous-qft/constructive-qft/what-is-open-in-four-dimensions/) explains why stable-manifold pictures are much easier to draw than to prove in physically central four-dimensional theories.

## Research status

The dynamical-systems language of fixed points, relevant directions, and stable manifolds is standard and mathematically precise in finite dimensions. In many rigorous RG constructions, it becomes precise in infinite-dimensional spaces of effective interactions or polymer activities, but the details are model-dependent.

For scalar and statistical-mechanics models, there are rigorous RG methods that prove stability estimates, tune critical parameters, and derive logarithmic corrections at upper critical dimension. For many continuum QFTs of direct physical interest, especially non-Abelian gauge theories in four dimensions, the corresponding nonperturbative fixed-point and stable-manifold constructions remain major research problems.

The right status label is therefore: established framework, model-dependent theorem, not a universal black box.

## Exercises

### Exercise 1: Stable manifold in a two-coupling toy RG

Consider the finite-step RG map

$$
x'=\lambda x,
\qquad
y'=\mu y+a x^2,
$$

where $0<\lambda<1<\mu$ and $a$ is a constant. Find a local stable manifold of the form $y=h(x)$ through the origin, up to order $x^2$.

<details>
<summary><strong>Solution</strong></summary>

The invariance equation for the graph $y=h(x)$ is

$$
h(\lambda x)=\mu h(x)+a x^2.
$$

Look for $h(x)=c x^2+O(x^3)$. Then

$$
c\lambda^2 x^2=\mu c x^2+a x^2+O(x^3).
$$

Thus

$$
c=\frac{a}{\lambda^2-\mu}.
$$

The stable manifold is curved unless $a=0$:

$$
y=\frac{a}{\lambda^2-\mu}x^2+O(x^3).
$$

This is the toy version of counterterm tuning. The relevant coordinate $y$ is not simply set to zero; it is set to a function of the irrelevant coordinate $x$.

</details>

### Exercise 2: Number of tunings near a hyperbolic fixed point

Suppose a hyperbolic RG fixed point has $r$ relevant directions and all other directions are irrelevant. What is the codimension of the local critical surface?

<details>
<summary><strong>Solution</strong></summary>

The local critical surface is the stable manifold. For a hyperbolic fixed point it is tangent to the stable subspace. If the unstable subspace has dimension $r$, then the stable subspace has codimension $r$, and so does the local stable manifold.

Thus $r$ independent conditions must be imposed to land on the stable manifold. In physics language, one must tune $r$ relevant parameters.

</details>

### Exercise 3: Marginal flow

Let

$$
\frac{dg}{d\ell}=-c g^2,
\qquad c>0.
$$

Solve the flow for $g(0)=g_0>0$. What does this say about the direction $g$ as $\ell\to\infty$?

<details>
<summary><strong>Solution</strong></summary>

Separate variables:

$$
\frac{dg}{g^2}=-c\,d\ell.
$$

This gives

$$
-\frac{1}{g(\ell)}=-c\ell-\frac{1}{g_0},
$$

or

$$
g(\ell)=\frac{g_0}{1+c g_0\ell}.
$$

Therefore $g(\ell)\to 0$ slowly, like $1/(c\ell)$. This is marginally irrelevant for the flow direction $\ell\to\infty$. The contraction is logarithmic, not exponential.

</details>

## References

### Standard first pass

- K. G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974) 75–200. [doi:10.1016/0370-1573(74)90023-4](https://doi.org/10.1016/0370-1573(74)90023-4).
- F. J. Wegner, “Corrections to Scaling Laws,” *Physical Review B* **5** (1972) 4529–4536. [doi:10.1103/PhysRevB.5.4529](https://doi.org/10.1103/PhysRevB.5.4529).
- J. Polchinski, “Renormalization and Effective Lagrangians,” *Nuclear Physics B* **231** (1984) 269–295. [doi:10.1016/0550-3213(84)90287-6](https://doi.org/10.1016/0550-3213(84)90287-6).
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, fifth edition, Oxford University Press, 2021. [doi:10.1093/oso/9780198834625.001.0001](https://doi.org/10.1093/oso/9780198834625.001.0001).

### Deeper references

- R. Bauerschmidt, D. C. Brydges, and G. Slade, *Introduction to a Renormalisation Group Method*. [arXiv:1907.05474](https://arxiv.org/abs/1907.05474).
- D. C. Brydges and G. Slade, “A Renormalisation Group Method. IV. Stability Analysis.” [arXiv:1403.7255](https://arxiv.org/abs/1403.7255).
- D. C. Brydges and G. Slade, “A Renormalisation Group Method. V. A Single Renormalisation Group Step.” [arXiv:1403.7256](https://arxiv.org/abs/1403.7256).
- M. Hirsch, C. Pugh, and M. Shub, *Invariant Manifolds*, Lecture Notes in Mathematics **583**, Springer, 1977.
- M. Shub, *Global Stability of Dynamical Systems*, Springer, 1987.
- O. J. Rosten, “Fundamentals of the Exact Renormalization Group.” [arXiv:1003.1366](https://arxiv.org/abs/1003.1366).

## Version history

- **2026-06-30:** Initial polished draft.
