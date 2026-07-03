---
title: "Local Versus Extended Operators"
description: "Operator support, codimension, order and disorder definitions, topological defects, endpoints, linking, and fusion for defects and extended operators in QFT."
sidebar:
  label: "Local Versus Extended Operators"
  order: 1
level: Advanced
status: "Polished draft"
source: "Wilson; Polyakov Chs. 6–7; Srednicki §§82, 92–93; Gaiotto–Kapustin–Seiberg–Willett; standard CFT, TQFT, and gauge-theory defect references."
topics:
  - local operators
  - extended operators
  - defects
  - support dimension
  - codimension
  - disorder operators
  - topological defects
  - defect fusion
canonicalTopics:
  - local-operator
  - extended-operator
  - defect-operator
  - disorder-operator
  - topological-defect
  - defect-fusion
researchStatus:
  established:
    - "Local operators, line operators, surface operators, boundaries, interfaces, and disorder defects are standard operator-theoretic objects in modern QFT."
    - "The support dimension and transverse linking geometry of an operator are part of its physical data, not a decorative choice."
  active:
    - "Topological extended operators are central in current work on generalized symmetries, non-invertible symmetries, symmetry TFT, defect CFT, and extended TQFT."
---

## Summary

A local operator is inserted at a spacetime point. An extended operator is supported on a positive-dimensional submanifold: a line, surface, wall, boundary, interface, or a more general defect worldvolume. This sounds like a small change, but it is one of the sharpest upgrades in modern QFT.

A local operator probes fields at a point. An extended operator can probe holonomy, flux, monodromy, linking, charge screening, topology, boundary conditions, and symmetry action. Wilson lines detect gauge holonomy. ’t Hooft lines create magnetic singularities. Surface operators measure or impose flux. Twist operators create branch cuts. Topological walls can implement symmetries. Boundaries and interfaces can carry their own degrees of freedom.

The right organizing data for a defect is not just “the formula inserted into the path integral.” It is the tuple

$$
\mathcal D_\alpha(\Sigma_p)
\quad\text{with}\quad
\Sigma_p\subset M_d,
$$

where $\Sigma_p$ is the $p$-dimensional support in $d$-dimensional spacetime and $\alpha$ denotes labels such as representation, charge, monodromy, boundary condition, spin structure, framing, orientation, endpoint data, or topological sector.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Taxonomy of local and extended operators by support dimension, definition type, transverse linking data, and operator labels.](/figures/symmetry-anomalies-topology/local-extended-operator-taxonomy.svg)

<figcaption>

An extended operator is specified by its support $\Sigma_p$, its definition near the support, and its transverse linking data. A genuine extended operator is usually not a smeared local operator: it may involve holonomy, singular boundary conditions, monodromy, endpoints, or topological fusion rules.

</figcaption>
</figure>

## Prerequisites

You should know the basic language of [ordinary global symmetries](/symmetry-anomalies-topology/ordinary-global-symmetries/), [background fields and gauging](/symmetry-anomalies-topology/background-fields-and-gauging/), [gauge redundancy](/symmetry-anomalies-topology/gauge-redundancy-brst/), and [topological sectors](/symmetry-anomalies-topology/topological-sectors-solitonic-charges/). The most useful technical background is differential forms, Stokes’s theorem, homotopy groups, gauge holonomy, and the path-integral idea that an operator insertion can change either the integrand or the domain of integration.

You do not need the full theory of higher categories or extended TQFT for this page. The point here is the physics-level taxonomy that those languages later formalize.

## Setup and conventions

Let $M_d$ be a $d$-dimensional spacetime manifold. In Lorentzian QFT, $M_d$ has one time direction; in Euclidean QFT, it is usually a Riemannian manifold. A defect supported on an embedded or immersed $p$-dimensional submanifold $\Sigma_p\subset M_d$ will be denoted

$$
\mathcal D_\alpha(\Sigma_p).
$$

Here $\alpha$ is a placeholder for all additional labels. For example:

| Defect | Support | Typical labels |
|---|---:|---|
| Local operator $\mathcal O(x)$ | $p=0$ | spin, charge, scaling dimension, representation |
| Wilson line $W_R(C)$ | $p=1$ | representation $R$, orientation, framing, endpoints |
| ’t Hooft line $T_B(C)$ | $p=1$ | magnetic cocharacter $B$, global form, spin data |
| Surface operator $S(\Sigma_2)$ | $p=2$ | monodromy, flux, two-form charge, ramification data |
| Domain wall $\mathcal W(\Sigma_{d-1})$ | $p=d-1$ | phase labels, interface condition, symmetry element |
| Boundary condition $\mathcal B$ | $p=d-1$ as boundary | boundary degrees of freedom, anomaly inflow data |

The **codimension** of $\mathcal D(\Sigma_p)$ is

$$
\operatorname{codim}\Sigma_p=d-p.
$$

A small transverse sphere linking the defect has dimension

$$
S^{d-p-1}.
$$

This sphere is often where the most important data live. Around a line in four-dimensional spacetime, the linking sphere is $S^2$, so magnetic flux through $S^2$ can define an ’t Hooft line. Around a codimension-two defect, the linking sphere is $S^1$, so monodromy around the circle can define a twist or vortex defect. Around a local operator in $d$ dimensions, the linking sphere is $S^{d-1}$, which is why radial quantization surrounds local operators by spheres.

:::note[Convention-sensitive source note]
Some references count an operator by its **worldvolume dimension** $p$, while others count it by its **codimension** or by its spatial dimension at fixed time. This page uses $p$ for spacetime support dimension. Thus a line operator has $p=1$ in spacetime, even though at fixed time it may look like a pointlike heavy probe.
:::

## The path-integral viewpoint

A local operator insertion is often written schematically as

$$
\langle \mathcal O(x)\cdots\rangle
=\frac{1}{Z}\int \mathcal D\phi\,\mathcal O[\phi(x)]\cdots e^{iS[\phi]}.
$$

This formula suggests that every operator is just a function of fields. That is much too narrow. A general defect correlation function is better written as

$$
\langle \mathcal D_\alpha(\Sigma_p)\,\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle
=\frac{1}{Z}\int_{\mathcal C_\alpha(\Sigma_p)}\mathcal D\phi\,
\exp\!\left(iS[\phi]+iS_{\rm def}[\phi;\Sigma_p,\alpha]\right)
\prod_i \mathcal O_i(x_i).
$$

There are two different kinds of modification here.

First, the defect may add a term $S_{\rm def}$ to the action. For example, a charged relativistic particle moving along a worldline $C$ couples to a background gauge field by

$$
S_{\rm def}=q\int_C A.
$$

Second, the defect may change the allowed field configurations. This is the disorder-operator logic. For example, a magnetic line in four-dimensional gauge theory is not defined by multiplying the integrand by a local polynomial. It is defined by requiring a prescribed magnetic singularity around the line.

Both mechanisms are operator insertions. The first changes the weight. The second changes the integration domain.

## Local operators

Local operators are supported at a point. Examples include

$$
\phi(x),\qquad
\phi^2(x),\qquad
\bar\psi(x)\psi(x),\qquad
F_{\mu\nu}(x)F^{\mu\nu}(x),
$$

and more generally renormalized composite operators.

Local operators are the natural language of many foundational structures:

| Structure | Local-operator role |
|---|---|
| OPE | Products of nearby local operators expand into local operators. |
| RG | Scaling operators diagonalize linearized RG flow near fixed points. |
| Sources | A source $J(x)$ couples to $\mathcal O(x)$ by $\int d^d x\,J\mathcal O$. |
| Spectrum in CFT | Local operators correspond to states on $S^{d-1}$ under radial quantization. |
| Ward identities | Currents inserted near local operators generate symmetry transformations. |

But local operators are not the whole operator algebra of a QFT. Gauge theory makes this unavoidable: a charged field $\psi(x)$ is not gauge invariant as a standalone local observable. It must either be part of a gauge-invariant local composite, or be attached to extended dressing data.

## Smeared operators versus genuine extended operators

A first example of an extended-looking operator is a smeared local operator,

$$
\mathcal O_f=\int_{M_d} d^d x\, f(x)\mathcal O(x).
$$

This is useful, especially because local quantum fields are distributions rather than honest functions. Smearing is not the same thing as introducing a new geometric operator. The support of $f$ matters analytically, but $\mathcal O_f$ is still built from local-operator data.

A genuine extended operator usually has additional structure that cannot be recovered by smearing local operators. Examples:

$$
W_R(C)=\operatorname{Tr}_R P\exp\!\left(i\int_C A\right)
$$

depends on parallel transport along a curve. A twist defect in a theory with a $G$ symmetry may require

$$
\phi(\theta+2\pi)=g\cdot \phi(\theta)
$$

around a linking circle. A magnetic line may require

$$
\int_{S^2} F=2\pi m
$$

on a small sphere linking the line. These are not smeared versions of local polynomials.

The quick diagnostic is this:

> If removing the submanifold $\Sigma_p$ changes the allowed topology, monodromy, holonomy, flux, boundary condition, or endpoint structure, the operator is genuinely extended.

## Support, codimension, and linking

The transverse space to a defect is often more important than the tangent space along it. Near a smooth point of $\Sigma_p$, spacetime locally looks like

$$
\mathbb R^p\times \mathbb R^{d-p}.
$$

Removing the defect leaves

$$
\mathbb R^p\times (\mathbb R^{d-p}\setminus\{0\}).
$$

The angular part of the transverse space is the linking sphere $S^{d-p-1}$. Defect data can be measured by integrals over this sphere or by monodromy along it.

Examples:

| Codimension | Linking sphere | Typical data |
|---:|---:|---|
| $1$ | $S^0$ | jump conditions, walls, interfaces |
| $2$ | $S^1$ | vortex winding, branch cuts, monodromy |
| $3$ | $S^2$ | magnetic charge, monopole flux, line defects in four dimensions |
| $4$ | $S^3$ | instanton number around pointlike events in four dimensions |

This is why the same physics can look different in different dimensions. A vortex is a codimension-two object. In two spatial dimensions it is a particlelike defect; in three spatial dimensions it is a stringlike defect; in spacetime language, its worldvolume dimension changes with time included.

## Order operators and disorder operators

An **order operator** is inserted as a function or functional of the fields. A local spin $\sigma(x)$ in the Ising model, a scalar composite $\phi^2(x)$, or a Wilson loop written as a holonomy are order-type insertions in this broad sense.

A **disorder operator** is defined by a modification of the allowed field configurations near its support. It tells the path integral how fields behave when one circles, links, or approaches the defect.

The distinction is clearest in two dimensions. In the Ising model, the spin operator $\sigma$ is an order operator, while the disorder operator $\mu$ creates a branch cut across which the Ising coupling or spin variable is twisted. In gauge theory, an ’t Hooft line is disorder-like because it imposes a monopole singularity around the line.

The order/disorder distinction is not absolute. Duality can exchange them. In many two-dimensional theories, an operator that is local in one duality frame is disorder-like in another. That is part of the point: “operator” is intrinsic, but “easy formula in terms of chosen fields” is not.

## Holonomy operators

Gauge fields make line operators unavoidable. A connection $A$ cannot usually be integrated to a gauge-invariant number along an open path. But parallel transport along a path $C$ is meaningful:

$$
U_R(C)=P\exp\!\left(i\int_C A_R\right).
$$

For a closed curve, the trace gives the Wilson loop

$$
W_R(C)=\operatorname{Tr}_R U_R(C).
$$

The label $R$ is not a decoration. It is part of the operator. In a nonabelian theory, different representations probe different center charges and different screening behavior. In a theory with gauge group $SU(N)/\mathbb Z_N$, not every representation of the Lie algebra $\mathfrak{su}(N)$ is an allowed Wilson-line label. The global form of the gauge group matters.

Wilson lines are the next page because they are the cleanest first example of a genuine extended operator.

## Topological defects

A defect is **topological** if correlation functions do not change when the defect support is smoothly deformed, as long as it does not cross other insertions and no boundary subtleties are encountered.

For example, an ordinary global symmetry element $g\in G$ can be represented by a codimension-one topological defect $U_g(\Sigma_{d-1})$. Moving this defect through a local operator implements the symmetry action:

$$
U_g\,\mathcal O(x)\,U_g^{-1}=(g\cdot \mathcal O)(x).
$$

For a continuous ordinary symmetry with conserved current $j^\mu$, the charge on a Cauchy surface $\Sigma_{d-1}$ is

$$
Q(\Sigma)=\int_{\Sigma} d\Sigma_\mu\, j^\mu.
$$

Current conservation makes $Q(\Sigma)$ independent of smooth deformations of $\Sigma$ that do not cross charged insertions. The topological-defect viewpoint is the exponential version of this surface-independence statement.

For higher-form symmetries, the charged objects are themselves extended. A $q$-form symmetry has topological operators supported on codimension-$(q+1)$ submanifolds, and it acts on $q$-dimensional charged operators by linking. This is why the present chapter naturally leads into the chapter on Higher-Form and Generalized Symmetries.

## Endpoints and junctions

Extended operators may end, but not for free.

An open Wilson line in representation $R$ is not gauge invariant by itself. Its endpoints transform in $R$ and $R^*$, so they must be attached to charged endpoint operators or placed on a boundary condition that can absorb the charge. Schematically,

$$
\bar\psi(x_f)\,U_R(C_{x_i\to x_f})\,\psi(x_i)
$$

is gauge invariant when the endpoint fields transform correctly.

Similarly, a surface defect may end on a line defect, a line may end on a local operator, and domain walls can meet at junctions. The endpoint or junction is not an afterthought; it is part of the operator algebra. The allowed endpoints encode charge conservation, screening, anomaly inflow, and boundary degrees of freedom.

A useful principle is:

> A defect can end only on an object that carries the missing charge or cancels the missing boundary variation.

This statement appears in many disguises: Gauss law, one-form charge conservation, anomaly inflow, brane charge conservation, and boundary gauge invariance.

## Defect-local operators

A defect can carry its own local operators. If $\mathcal D(\Sigma_p)$ is present, one can insert operators $\widehat{\mathcal O}(y)$ with $y\in\Sigma_p$. These are called **defect-local operators**.

They are local from the point of view of the defect worldvolume, but not local in the ambient QFT without the defect. For a boundary condition in a $d$-dimensional QFT, boundary operators live in $(d-1)$ dimensions. For a line defect in four dimensions, line-local operators form a one-dimensional quantum system coupled to the bulk.

This is the beginning of defect CFT when the ambient theory and defect preserve conformal symmetry. It is also the practical language of impurity problems, boundary critical phenomena, Wilson-line insertions with fields living on the line, and interfaces between phases.

## Fusion

If two topological defects can be brought close together without encountering singular dependence on the separation, their product can be replaced by a new effective defect. This operation is called **fusion**.

For ordinary invertible symmetry defects,

$$
U_g(\Sigma)\,U_h(\Sigma) = U_{gh}(\Sigma).
$$

This is just group multiplication. But topological defects need not be invertible. Their fusion can take the form

$$
\mathcal D_a\times \mathcal D_b = \sum_c N_{ab}^{\;c}\,\mathcal D_c,
$$

with nonnegative integer multiplicities $N_{ab}^{\;c}$ in many finite semisimple examples. This is the doorway to non-invertible and categorical symmetry.

For non-topological defects, fusion is usually singular or scale-dependent. Bringing two Wilson lines together, for example, can require renormalization and can decompose according to representation theory, but it is not automatically a topological fusion rule.

## Locality with extended operators

Locality for extended operators is subtler than locality for local fields. Two spacelike-separated local observables should commute, but extended operators can link even when their supports do not intersect. The correlator can depend on linking number, framing, or mutual electric/magnetic charges.

For example, in topological BF theory or Chern–Simons theory, the expectation value of line and surface operators can be a pure linking invariant. In four-dimensional gauge theory, Wilson and ’t Hooft lines may have nontrivial mutual locality conditions controlled by the Dirac pairing of their electric and magnetic charges.

So there are two notions to keep apart:

1. **Geometric disjointness:** the supports do not intersect.
2. **Operator mutual locality:** the insertions can be consistently ordered or moved around each other without extra phases, branch cuts, or singularities.

Extended operators are where these notions visibly diverge.

## Common pitfalls

**Mistaking support for dynamics.** A line operator is supported on a curve, but that does not mean the theory contains a dynamical string. It may be a nondynamical probe insertion.

**Calling every extended object a defect.** The word “defect” is broad, but one should still say whether it is an operator insertion, boundary condition, disorder singularity, dynamical soliton, topological wall, or interface between two QFTs.

**Ignoring the transverse sphere.** Many labels are not visible on $\Sigma_p$ itself. They are measured on the linking sphere $S^{d-p-1}$.

**Assuming a disorder operator has no formula.** Sometimes disorder operators have dual descriptions as ordinary fields or exponentials. “Disorder” describes how the operator is defined in a chosen variables, not an intrinsic lack of mathematics.

**Forgetting renormalization.** Extended operators have UV divergences associated with their length, area, cusps, self-intersections, and endpoints. The phrase “Wilson loop” usually means a renormalized operator, at least outside purely topological settings.

**Confusing topological with topologically charged.** A defect can carry a topological charge without being a topological operator. A domain wall with nonzero tension is not freely deformable just because it separates topological sectors.

## Relation to nearby pages

The next page, [Wilson Lines](/symmetry-anomalies-topology/defects-extended-operators/wilson-lines/), studies the canonical holonomy operator in gauge theory. [’t Hooft Lines](/symmetry-anomalies-topology/defects-extended-operators/thooft-lines/) then gives the magnetic disorder analogue. [Surface Operators](/symmetry-anomalies-topology/defects-extended-operators/surface-operators/) and [Disorder Operators](/symmetry-anomalies-topology/defects-extended-operators/disorder-operators/) expand the transverse-boundary-condition viewpoint. [Defect Fusion](/symmetry-anomalies-topology/defects-extended-operators/defect-fusion/) develops the topological-operator side of the story.

The later chapter on [Higher-Form and Generalized Symmetries](/symmetry-anomalies-topology/higher-form-generalized-symmetries/) uses extended operators as charged objects. The chapter on [Non-Invertible and Categorical Symmetries](/symmetry-anomalies-topology/non-invertible-categorical-symmetries/) uses topological defects and fusion as symmetry data.

## Research status

The basic taxonomy of local operators, Wilson lines, disorder operators, boundaries, and interfaces is established. What is still rapidly developing is the global organization of all these objects: higher-form symmetry, non-invertible symmetry, defect categories, anomaly inflow for defects, symmetry TFT, and extended TQFT.

A safe rule for research-facing pages is this: when a defect is topological and has a closed fusion algebra, it is not merely an observable. It is a piece of generalized symmetry data.

## Exercises

### Exercise 1: Linking spheres

Let $\Sigma_p\subset M_d$ be a smooth defect support. Show that the small sphere linking $\Sigma_p$ has dimension $d-p-1$. Identify the linking spheres for a local operator, a line operator, and a surface operator in four spacetime dimensions.

<details><summary><strong>Solution</strong></summary>

Near a smooth point of $\Sigma_p$, choose local coordinates so that

$$
M_d\simeq \mathbb R^p\times \mathbb R^{d-p},
\qquad
\Sigma_p\simeq \mathbb R^p\times\{0\}.
$$

The directions transverse to the defect form $\mathbb R^{d-p}$. Removing the origin in the transverse space and fixing a small radius gives

$$
S^{d-p-1}\subset \mathbb R^{d-p}.
$$

In $d=4$, a local operator has $p=0$ and linking sphere $S^3$; a line operator has $p=1$ and linking sphere $S^2$; a surface operator has $p=2$ and linking sphere $S^1$.

</details>

### Exercise 2: Why a codimension-two defect can have monodromy

Explain why codimension-two defects are naturally associated with monodromy data.

<details><summary><strong>Solution</strong></summary>

For a codimension-two defect, $d-p=2$, so the small linking sphere is

$$
S^{d-p-1}=S^1.
$$

A field configuration near the defect can be studied as one goes around this circle. It is therefore meaningful to impose a condition such as

$$
\phi(\theta+2\pi)=g\cdot \phi(\theta),
$$

where $g$ is a symmetry transformation. This is exactly monodromy data. Vortices, branch-point twist operators, and codimension-two surface operators use this geometry.

</details>

### Exercise 3: Open Wilson-line endpoint charge

Suppose a parallel transporter along a path from $x_i$ to $x_f$ transforms as

$$
U(C_{x_i\to x_f})\mapsto g(x_f)U(C_{x_i\to x_f})g(x_i)^{-1}.
$$

Show that $\bar\psi(x_f)U(C)\psi(x_i)$ can be gauge invariant if $\psi\mapsto g\psi$.

<details><summary><strong>Solution</strong></summary>

If $\psi(x_i)\mapsto g(x_i)\psi(x_i)$ and $\bar\psi(x_f)\mapsto \bar\psi(x_f)g(x_f)^{-1}$, then

$$
\bar\psi(x_f)U(C)\psi(x_i)
\mapsto
\bar\psi(x_f)g(x_f)^{-1}\,g(x_f)U(C)g(x_i)^{-1}\,g(x_i)\psi(x_i).
$$

The endpoint gauge transformations cancel, leaving

$$
\bar\psi(x_f)U(C)\psi(x_i).
$$

So the open Wilson line is not gauge invariant by itself, but it becomes gauge invariant when its endpoints are attached to charged operators with the correct transformation law.

</details>

### Exercise 4: Topological surface crossing

Let $U_g(\Sigma_{d-1})$ be a codimension-one topological operator for an ordinary symmetry element $g$. Explain why moving $U_g$ across a local operator $\mathcal O(x)$ should transform $\mathcal O(x)$ by $g$.

<details><summary><strong>Solution</strong></summary>

The topological surface $U_g(\Sigma_{d-1})$ can be deformed without changing the correlator as long as it does not cross charged insertions. If the deformation crosses $x$, the correlator can change only by the action of the symmetry on the operator at $x$. Therefore the crossing rule is

$$
U_g\text{ crossing }\mathcal O(x):\qquad
\mathcal O(x)\mapsto g\cdot\mathcal O(x).
$$

This is the defect version of the charge-commutator Ward identity. The surface is topological away from charged insertions, and charged insertions are precisely the places where crossing produces an action.

</details>

## References and further reading

- K. G. Wilson, lattice gauge theory and Wilson-loop diagnostics.
- A. M. Polyakov, *Gauge Fields and Strings*, especially the chapters on gauge-field topology and loop dynamics.
- M. Srednicki, *Quantum Field Theory*, especially the sections on Wilson loops, solitons, monopoles, instantons, and theta vacua.
- D. Gaiotto, A. Kapustin, N. Seiberg, and B. Willett, “Generalized Global Symmetries,” for the modern higher-form symmetry viewpoint.
- J. Fuchs, I. Runkel, C. Schweigert, and related work on defects in rational CFT.
- D. Gaiotto and collaborators on topological defects, generalized symmetries, and non-invertible symmetry.

## Version history

- 2026-06-19: First polished draft. Introduced the support/codimension/linking taxonomy, order-versus-disorder distinction, topological defects, endpoints, defect-local operators, and fusion.
