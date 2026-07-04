---
title: "Extension of Distributions"
description: "Explains the distribution-extension problem behind Epstein–Glaser renormalization and the finite local ambiguities it permits."
sidebar:
  label: "Extension of Distributions"
  order: 5
level: Advanced
status: "Polished draft"
source: "Steinmann scaling degree; Epstein–Glaser; Brunetti–Fredenhagen; Hollands–Wald"
topics:
  - distribution extension
  - scaling degree
  - local counterterms
  - Epstein–Glaser renormalization
canonicalTopics:
  - distribution-extension
  - scaling-degree
  - epstein-glaser-renormalization
researchStatus:
  established:
    - "Distribution extension with controlled scaling degree gives a precise mathematical form of the local counterterm freedom in perturbative renormalization."
  active:
    - "In curved spacetime and gauge theories, extension must be supplemented by local covariance, microlocal spectrum conditions, and often BV-BRST compatibility."
---

## Summary

A distribution can be perfectly well-defined away from a singular set and still fail to have a canonical value on that set. In perturbative QFT, this is exactly what happens when time-ordered products are first defined away from coincident spacetime points and then must be extended to the diagonals.

The basic problem is

$$
t_0\in \mathcal D'(X\setminus Y)
\quad\leadsto\quad
\widetilde t\in \mathcal D'(X),
$$

where $Y$ is a closed singular set, often a diagonal such as $x_1=x_2$. The extension must agree with $t_0$ on test functions supported away from $Y$.

The central theorem used in Epstein–Glaser renormalization says that an extension preserving a scaling-degree bound exists. When the singularity is mild enough, the extension is unique. When it is not unique, any two choices differ by a distribution supported on $Y$. For $Y$ a point, this means a finite sum of delta-function derivatives:

$$
\widetilde t'-\widetilde t
=
\sum_{|\alpha|\leq \omega}
 c_\alpha\,\partial^\alpha\delta.
$$

That formula is the local counterterm ambiguity in its most stripped-down mathematical form.

## Prerequisites

You should know [Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/), [Epstein–Glaser Renormalization](/rigorous-qft/perturbative-algebraic-qft/epstein-glaser-renormalization/), and [Time-Ordered Products](/rigorous-qft/perturbative-algebraic-qft/time-ordered-products/). The pages on [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/) and [Renormalization of Composite Fields](/rigorous-qft/rigorous-renormalization-rg/renormalization-of-composite-fields/) explain where these local ambiguities reappear in other languages.

## Core idea

A distribution is not a function with bad values at a few points. It is a continuous linear functional on test functions. Therefore, extending a distribution across a singular set is not the same as assigning pointwise values. It is the problem of defining its action on test functions whose support touches the singular set.

Let $j:X\setminus Y\hookrightarrow X$ be the inclusion. A distribution $\widetilde t\in\mathcal D'(X)$ is an extension of $t_0\in\mathcal D'(X\setminus Y)$ if

$$
\widetilde t(\varphi)=t_0(\varphi)
$$

for every test function $\varphi$ supported in $X\setminus Y$. Equivalently,

$$
\widetilde t|_{X\setminus Y}=t_0.
$$

If $\widetilde t$ and $\widetilde t'$ are two extensions, their difference vanishes away from $Y$:

$$
\operatorname{supp}(\widetilde t'-\widetilde t)\subseteq Y.
$$

Thus nonuniqueness is localized exactly on the singular set. In QFT, the singular set is a coincidence locus, so the ambiguity is local in spacetime.

<figure class="doc-figure" style="--figure-width: 51rem;">

![Distribution extension and local ambiguity](/figures/rigorous-qft/distribution-extension-local-ambiguity.svg)

<figcaption>

A distribution $t_0$ is fixed away from the diagonal. Extending it across the diagonal is the renormalization step. Scaling degree decides whether the extension is unique; if not, the ambiguity is supported on the diagonal and becomes a local counterterm.

</figcaption>
</figure>

## Setup and conventions

For the local model, take

$$
X=\mathbb R^N,
\qquad
Y=\{0\},
$$

and suppose

$$
t_0\in\mathcal D'(\mathbb R^N\setminus\{0\}).
$$

This is enough for many flat-space extension problems after translation invariance has reduced the total diagonal $x_1=\cdots=x_n$ to the origin in relative coordinates. For example, for $n$ insertions in $d$ spacetime dimensions, the relative coordinate dimension is

$$
N=d(n-1).
$$

For partial diagonals or curved spacetime, replace the origin by a submanifold. Locally, the extension problem is still controlled by the transverse directions to the submanifold. If $Y\subset X$ has codimension $N_\perp$, the role of $N$ is played by $N_\perp$.

The test-function space is $\mathcal D(X)=C_c^\infty(X)$ unless otherwise stated. Tempered distributions and Schwartz test functions are useful in translation-invariant Minkowski space, but the local extension theorem does not require global Fourier analysis.

## Scaling degree

Scaling degree measures how singular a distribution is under zooming into the singular set. For $t\in\mathcal D'(\mathbb R^N\setminus\{0\})$, define the scaled distribution $t_\lambda$ by

$$
\langle t_\lambda,\varphi\rangle
=
\lambda^{-N}
\langle t,\varphi(\lambda^{-1}\,\cdot)\rangle,
\qquad
\lambda>0.
$$

The scaling degree at the origin is

$$
\operatorname{sd}_0(t)
=
\inf\left\{
\delta\in\mathbb R\,\middle|\,
\lambda^\delta t_\lambda\to 0
\text{ in }\mathcal D'
\text{ as }\lambda\to0^+
\right\}.
$$

The singular order is

$$
\omega(t)=\operatorname{sd}_0(t)-N.
$$

The useful examples are:

| Distribution near $0\in\mathbb R^N$ | Scaling degree | Singular order |
|---|---:|---:|
| smooth function | $\leq 0$ | $<0$ |
| $|x|^{-a}$ with $a>0$ | $a$ | $a-N$ |
| $\delta(x)$ | $N$ | $0$ |
| $\partial^\alpha\delta(x)$ | $N+|\alpha|$ | $|\alpha|$ |

This table explains why delta derivatives are exactly the possible local ambiguities at fixed scaling degree.

## The extension theorem

The extension theorem used in Epstein–Glaser renormalization can be stated as follows.

:::note[Extension with fixed scaling degree]
Let $t_0\in\mathcal D'(\mathbb R^N\setminus\{0\})$ have finite scaling degree. Then there exists an extension $\widetilde t\in\mathcal D'(\mathbb R^N)$ satisfying

$$
\operatorname{sd}_0(\widetilde t)=\operatorname{sd}_0(t_0).
$$

If $\operatorname{sd}_0(t_0)<N$, the extension preserving this bound is unique. If $\operatorname{sd}_0(t_0)\geq N$, any two extensions preserving the same bound differ by

$$
\sum_{|\alpha|\leq \lfloor\omega\rfloor}
 c_\alpha\,\partial^\alpha\delta,
\qquad
\omega=\operatorname{sd}_0(t_0)-N.
$$
:::

The theorem is powerful because it gives both existence and the dimension of the renormalization ambiguity. It does not choose the constants $c_\alpha$. Those constants are fixed by normalization conditions, symmetries, experimental inputs, or a chosen renormalization prescription.

## How an extension is constructed

One concrete construction shows what is happening. Suppose $\omega\geq0$ is an integer bound on the singular order. Choose a compactly supported smooth function $w$ that is equal to $1$ in a neighborhood of $0$. Define a projection on test functions by subtracting the Taylor polynomial through degree $\omega$:

$$
(W_\omega f)(x)
=
f(x)
-
w(x)
\sum_{|\alpha|\leq\omega}
\frac{x^\alpha}{\alpha!}
(\partial^\alpha f)(0).
$$

Then $W_\omega f$ vanishes at the origin to sufficiently high order, so the pairing $t_0(W_\omega f)$ has a finite cutoff-independent limit. An extension may be written as

$$
\widetilde t(f)
=
t_0(W_\omega f)
+
\sum_{|\alpha|\leq\omega}
 c_\alpha(\partial^\alpha f)(0),
$$

with signs absorbed into the constants $c_\alpha$. Different choices of $w$ and $c_\alpha$ correspond to different renormalization prescriptions, but the freedom remains finite-dimensional.

This construction is not the only possible one. Its value is pedagogical: it makes visible that renormalization subtracts the part of the test function that probes the singular jet at the coincidence point.

## Examples

### Principal value of one over x

The distribution $1/x$ is defined on $\mathbb R\setminus\{0\}$ and has scaling degree $1$. Since $N=1$, the singular order is $0$, so an extension is not unique. Any two extensions differ by

$$
c\,\delta(x).
$$

The principal-value extension is fixed by imposing oddness:

$$
\operatorname{pv}\frac1x.
$$

Without that symmetry condition, adding $c\delta(x)$ is allowed by scaling degree.

### A logarithmic four-dimensional singularity

In four spacetime dimensions, the local singularity

$$
\frac{1}{(x^2-i0)^2}
$$

has scaling degree $4$ in $N=4$ relative coordinates. Hence the singular order is $0$, and the ambiguity is a multiple of $\delta(x)$:

$$
\widetilde t'
=
\widetilde t+c\,\delta(x).
$$

This is the position-space version of a logarithmic divergence. A scale can enter the chosen extension, and changing that scale shifts the local delta term.

### Higher singular order

If $t_0$ on $\mathbb R^4\setminus\{0\}$ has scaling degree $6$, then

$$
\omega=6-4=2.
$$

The local ambiguity is

$$
\sum_{|\alpha|\leq2}
c_\alpha\partial^\alpha\delta.
$$

Lorentz invariance, parity, internal symmetry, field equations, and Ward identities can remove many of these coefficients. Scaling degree alone only gives the allowed range.

## Extension to submanifolds and diagonals

For time-ordered products, the singular set is usually not just a point. In $M^n$, the total diagonal is

$$
\Delta_n=
\{(x_1,\ldots,x_n)\in M^n\mid x_1=\cdots=x_n\},
$$

and there are also partial diagonals such as $x_i=x_j$.

Locally near a diagonal, use coordinates

$$
(u,v),
\qquad
u\in Y,
\quad
v\in N_YX,
$$

where $u$ runs along the diagonal and $v$ is transverse to it. The extension problem scales the transverse variables $v$ while keeping $u$ fixed. If two extensions have the same transverse scaling-degree bound, their difference is supported on $Y$ and has the schematic form

$$
\sum_{|\alpha|\leq\omega}
 a_\alpha(u)\,\partial_v^\alpha\delta(v).
$$

In QFT, local covariance and the microlocal spectrum condition restrict the coefficients $a_\alpha(u)$ to local geometric expressions built from the fields, couplings, metric, curvature, and their derivatives, subject to dimension and symmetry constraints.

## Relation to counterterms

The finite local ambiguity is exactly what a counterterm is. A delta derivative supported on the diagonal becomes, after smearing, an integral over one spacetime point.

For instance, a two-point ambiguity of the form

$$
c\,\delta(x-y)
$$

turns a smeared bilocal expression into

$$
c\int d^dx\, f(x)g(x)\,\mathcal O(x),
$$

for the relevant local Wick polynomial or composite field $\mathcal O$. Derivatives of $\delta(x-y)$ become derivatives acting on test functions or, after integration by parts, derivatives of fields and couplings. This is why distribution extension produces local Lagrangian counterterms rather than nonlocal corrections.

The point is not that every local term must be present with a free coefficient. It is that the extension theorem identifies the maximal local freedom allowed by singularity degree. Normalization conditions, symmetries, and field identities then reduce it.

## Symmetry and covariance constraints

An arbitrary extension can destroy a symmetry. A useful renormalization scheme must choose extensions compatible with the structural requirements of the theory.

Typical constraints include:

| Constraint | Effect on extensions |
|---|---|
| Translation covariance | Forbids position-dependent coefficients in flat space. |
| Lorentz covariance | Allows only Lorentz-covariant delta derivatives and tensor structures. |
| Internal symmetry | Couples the allowed coefficients across different fields. |
| Scaling or almost homogeneous scaling | Controls logarithms and renormalization scales. |
| Field equations | Relates extensions involving equation-of-motion terms. |
| Ward identities | Can impose nontrivial compatibility conditions; anomalies are obstructions. |
| Local covariance | Replaces constant coefficients on curved spacetime by local geometric terms. |

In gauge theory, compatibility with BRST or BV identities is the delicate part. Failure to choose extensions satisfying the relevant identity is interpreted as an anomaly when the obstruction cannot be removed by local counterterms.

## Common pitfalls

**Assigning a value at the singular point.** A distribution extension is not a pointwise assignment. It defines the action on test functions that probe the singular set.

**Forgetting the scaling-degree bound.** Extensions always exist under broad conditions, but arbitrary extensions can worsen short-distance behavior. Epstein–Glaser renormalization restricts attention to extensions preserving the expected scaling degree.

**Calling every ambiguity arbitrary.** The ambiguity is finite-dimensional at each local extension step. Additional physical and structural conditions often reduce it further.

**Ignoring partial diagonals.** At higher orders, singularities occur when any subset of points coincides. Renormalization is an inductive extension over a stratified family of diagonals, not one final correction at the total diagonal only.

**Assuming covariance is automatic.** A local extension chosen in one coordinate chart need not be covariant. Curved-spacetime pAQFT imposes local covariance as a normalization condition, which restricts the allowed geometric counterterms.

## Relations to other pages

[Epstein–Glaser Renormalization](/rigorous-qft/perturbative-algebraic-qft/epstein-glaser-renormalization/) explains how this extension theorem enters the inductive construction of time-ordered products. [Causal Perturbation Theory](/rigorous-qft/perturbative-algebraic-qft/causal-perturbation-theory/) explains why the distributions are known away from diagonals before the extension step.

[Wavefront Sets](/rigorous-qft/microlocal-analysis-qft/wavefront-sets/) explains when distribution products are meaningful away from the diagonal. [Algebraic Renormalization in Curved Spacetime](/rigorous-qft/locally-covariant-qft/algebraic-renormalization-in-curved-spacetime/) explains how local covariance refines the extension problem. The later page on renormalization ambiguities will classify the allowed finite redefinitions more systematically.

## Research status

The extension-of-distributions viewpoint is established in perturbative algebraic QFT. It provides a clean ultraviolet construction for formal perturbation theory and gives precise control of local renormalization freedom.

The main active or delicate points are not the basic extension theorem itself. They are compatibility with gauge identities, local covariance, infrared limits, and the relation between perturbative formal series and nonperturbative theories. These issues are addressed by BV-BRST methods, locally covariant QFT, and constructive approaches rather than by the extension theorem alone.

## Exercises

### Exercise 1: Uniqueness below the dimension

Let $t_0(x)=|x|^{-a}$ on $\mathbb R^N\setminus\{0\}$ with $0<a<N$. Use scaling degree to decide whether the extension preserving scaling degree is unique.

<details><summary><strong>Solution</strong></summary>

The distribution has scaling degree $a$. Since $a<N$, the singular order is

$$
\omega=a-N<0.
$$

The extension preserving the scaling-degree bound is unique. There is no allowed delta-derivative ambiguity because even $\delta$ has scaling degree $N$, which would worsen the bound.

</details>

### Exercise 2: The ambiguity for one over x

Why does $1/x$ on $\mathbb R\setminus\{0\}$ admit a one-parameter family of extensions preserving scaling degree, and why does the principal value select one?

<details><summary><strong>Solution</strong></summary>

The scaling degree of $1/x$ is $1$, and $N=1$, so $\omega=0$. Two extensions can differ by $c\delta(x)$. The principal-value distribution is the odd extension. Since $\delta(x)$ is even, imposing oddness sets $c=0$.

</details>

### Exercise 3: Counterterms from diagonal support

Show schematically why a term $c\delta(x-y)$ in a two-point extension gives a local contribution after smearing.

<details><summary><strong>Solution</strong></summary>

Smearing against test functions gives

$$
\int d^dx\,d^dy\, f(x)g(y)c\delta(x-y)
=
c\int d^dx\, f(x)g(x).
$$

When field monomials are included, the same delta function collapses the bilocal expression to one spacetime integral of a local field polynomial. Derivatives of the delta function produce derivatives of test functions or fields, still locally.

</details>

### Exercise 4: Why delta derivatives are finite in number

If $t_0$ has scaling degree $N+3$ in $\mathbb R^N$, why are derivatives of $\delta$ of order $4$ not allowed in an extension preserving that bound?

<details><summary><strong>Solution</strong></summary>

A derivative $\partial^\alpha\delta$ has scaling degree $N+|\alpha|$. Preserving the bound $N+3$ allows only $|\alpha|\leq3$. A fourth derivative has scaling degree $N+4$ and would worsen the short-distance behavior.

</details>

## References

- O. Steinmann, *Perturbation Expansions in Axiomatic Field Theory*, Lecture Notes in Physics **11**, Springer, 1971. [doi:10.1007/BFb0025525](https://doi.org/10.1007/BFb0025525).
- H. Epstein and V. Glaser, “The Role of Locality in Perturbation Theory,” *Annales de l'Institut Henri Poincaré A* **19** (1973), 211–295. [Numdam](https://numdam.org/item/AIHPA_1973__19_3_211_0/).
- R. Brunetti and K. Fredenhagen, “Microlocal Analysis and Interacting Quantum Field Theories: Renormalization on Physical Backgrounds,” *Communications in Mathematical Physics* **208** (2000), 623–661. [arXiv:math-ph/9903028](https://arxiv.org/abs/math-ph/9903028), [doi:10.1007/s002200050004](https://doi.org/10.1007/s002200050004).
- S. Hollands and R. M. Wald, “Local Wick Polynomials and Time Ordered Products of Quantum Fields in Curved Spacetime,” *Communications in Mathematical Physics* **223** (2001), 289–326. [arXiv:gr-qc/0103074](https://arxiv.org/abs/gr-qc/0103074), [doi:10.1007/s002200100540](https://doi.org/10.1007/s002200100540).
- S. Hollands and R. M. Wald, “Existence of Local Covariant Time Ordered Products of Quantum Fields in Curved Spacetime,” *Communications in Mathematical Physics* **231** (2002), 309–345. [arXiv:gr-qc/0111108](https://arxiv.org/abs/gr-qc/0111108), [doi:10.1007/s00220-002-0719-y](https://doi.org/10.1007/s00220-002-0719-y).
- K. Rejzner, *Perturbative Algebraic Quantum Field Theory: An Introduction for Mathematicians*, Springer, 2016. [doi:10.1007/978-3-319-25901-7](https://doi.org/10.1007/978-3-319-25901-7).

## Version history

- **2026-07-01:** First polished draft.
