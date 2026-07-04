---
title: "CFTs as RG Fixed Points"
description: "Explains why conformal field theories arise as fixed points of renormalization group flow, how scaling operators and critical exponents appear, and what this viewpoint does and does not prove."
sidebar:
  label: "CFTs as RG Fixed Points"
  order: 2
level: Graduate
status: "Polished draft"
source: "Wilson–Kogut 1974; Coleman 1985; Zinn-Justin 2021; Cardy 1996; Di Francesco–Mathieu–Sénéchal 1997; Poland–Rychkov–Vichi 2019"
topics:
  - conformal field theory
  - renormalization group
  - fixed points
  - critical phenomena
  - relevant operators
  - irrelevant operators
  - marginal operators
  - scaling operators
  - universality
canonicalTopics:
  - cfts-as-rg-fixed-points
  - rg-fixed-points
  - scaling-operators
  - relevant-irrelevant-marginal
  - universality-and-cft
researchStatus:
  established:
    - "RG fixed points provide the standard explanation for universal scale-invariant behavior at continuous phase transitions and in many continuum limits of QFT."
    - "Near a fixed point, local deformations are organized by scaling operators whose RG eigenvalues determine relevant, irrelevant, and marginal directions."
  active:
    - "The classification of all fixed points, the nonperturbative relation between scale and conformal invariance, and the structure of fixed points without Lagrangian descriptions remain active research areas."
---

## Summary

A conformal field theory often appears as the endpoint, starting point, or intermediate saddle of a renormalization group flow. The slogan is

$$
\text{CFT}=\text{a QFT at an RG fixed point, with conformal symmetry}.
$$

The RG viewpoint explains why CFTs are everywhere in critical phenomena and quantum field theory. A continuous phase transition has a diverging correlation length. Once the correlation length becomes infinite, the long-distance theory has no intrinsic length scale. The fixed point controlling that long-distance limit is described by scaling operators and universal data.

Near a fixed point, a theory is deformed by local operators:

$$
S=S_*+\sum_i g_i\int d^d x\,\mathcal O_i(x).
$$

The linearized RG flow is

$$
\frac{d g_i}{d\log b}=y_i g_i+O(g^2),
\qquad
y_i=d-\Delta_i,
$$

when $\mathcal O_i$ is a scalar scaling operator of dimension $\Delta_i$ and $b>1$ is a coarse-graining factor. Relevant deformations have $y_i>0$, irrelevant deformations have $y_i<0$, and marginal deformations have $y_i=0$ at linear order.

:::note[What this page does]
This page explains why RG fixed points naturally lead to CFT language. It does not claim that every scale-invariant fixed point is automatically conformal. The enhancement from scale invariance to conformal invariance is the subject of [Scale Invariance versus Conformal Invariance](/cft-bootstrap/what-is-a-cft/scale-invariance-versus-conformal-invariance/).
:::

## Prerequisites

You should know the [Conventions and Notation](/cft-bootstrap/conventions/) page and the distinction explained in [Scale Invariance versus Conformal Invariance](/cft-bootstrap/what-is-a-cft/scale-invariance-versus-conformal-invariance/). You should also be comfortable with local operators, correlation functions, Wilsonian coarse graining, and the idea that couplings run with scale.

Useful background from neighboring volumes includes fixed points, beta functions, relevant and irrelevant operators, and the Wilsonian picture in [Renormalization, RG, and EFT](/renormalization-rg-eft/). This page uses those ideas but keeps the emphasis on what becomes CFT data.

## Core idea

The renormalization group compares descriptions of the same physics at different length scales. Coarse grain by a factor $b>1$, integrate out short-distance details, then rescale coordinates so that the cutoff is restored. A fixed point is a theory that returns to itself under this operation.

In schematic notation,

$$
\text{microscopic theory}
\xrightarrow{\text{coarse grain}}
\text{effective theory at longer distances}.
$$

A fixed point satisfies

$$
\frac{d g_i}{d\log \mu}=\beta_i(g)=0
$$

for all physical dimensionless couplings. Here $\mu$ is an energy scale. Equivalently, under a change of length scale $b$, the theory looks the same after fields and operators are rescaled appropriately.

This is why fixed points are natural homes for scaling operators. At a generic point along an RG flow, operators mix in a scale-dependent way. At a fixed point, the dilatation generator can be diagonalized. Local operators can be chosen so that

$$
\mathcal O_i(x)\mapsto b^{\Delta_i}\mathcal O_i(bx)
$$

or, equivalently,

$$
\mathcal O_i(bx)=b^{-\Delta_i}\mathcal O_i(x)
$$

inside correlation functions with the usual covariant transformation law. The numbers $\Delta_i$ are scaling dimensions. In a conformal fixed point, they become dimensions of conformal primary operators and their descendants.

## Setup and conventions

This page uses Euclidean $d$-dimensional notation. The coordinate dimension $d$ is the number of Euclidean coordinates, not necessarily four. The RG scale may be described either by an energy scale $\mu$ or by a length-rescaling factor $b$. Increasing $b$ means looking at longer distances; increasing $\mu$ means looking at shorter distances.

A local scalar deformation of a fixed point is written

$$
\delta S=g_i\int d^d x\,\mathcal O_i(x).
$$

If $\mathcal O_i$ has scaling dimension $\Delta_i$, then the coupling has mass dimension

$$
[g_i]=d-\Delta_i.
$$

The corresponding linearized RG eigenvalue is

$$
y_i=d-\Delta_i.
$$

The terminology is:

| Type of deformation | Condition | Long-distance effect |
|---|---:|---|
| Relevant | $y_i>0$, equivalently $\Delta_i<d$ | Grows under coarse graining; must usually be tuned to reach the fixed point. |
| Irrelevant | $y_i<0$, equivalently $\Delta_i>d$ | Dies away at long distances; explains universality. |
| Marginal | $y_i=0$, equivalently $\Delta_i=d$ | Requires higher-order analysis; can be marginally relevant, marginally irrelevant, or exactly marginal. |

For spinning operators, one must also track spin and tensor structure. Only scalar deformations can be added to the action without choosing background tensors, but spinning operators remain part of the CFT data.

## Fixed points and continuum limits

A lattice model has a microscopic spacing $a$. A continuum limit is obtained when one can send

$$
a\to 0
$$

while keeping physical long-distance quantities finite. This is only possible if the correlation length in lattice units diverges:

$$
\frac{\xi}{a}\to\infty.
$$

At a continuous phase transition, the physical correlation length behaves as

$$
\xi\sim |t|^{-\nu},
$$

where $t$ is a reduced temperature or another relevant tuning parameter. In lattice units, $\xi/a$ diverges as $t\to 0$. The long-distance theory therefore loses memory of the microscopic lattice spacing.

This is the practical meaning of a critical fixed point. It is the theory seen by probes whose wavelengths are much longer than the microscopic spacing but shorter than any finite correlation length. Exactly at criticality, no finite correlation length remains, and the fixed point controls arbitrarily long distances.

The continuum limit is not the same as forgetting the microscopic theory. The microscopic theory chooses a point in the space of couplings and therefore chooses which fixed point, if any, controls the long-distance physics. But once the fixed point is reached, many microscopic details become irrelevant.

This is universality:

$$
\text{many microscopic theories}
\longrightarrow
\text{one infrared fixed point}.
$$

Different magnets, fluids, lattice models, and quantum systems can share the same critical exponents and scaling functions because they flow to the same fixed point.

## Critical surfaces and tuning

Near a fixed point, the space of theories is divided into directions by RG eigenvalues. Relevant directions grow toward the infrared. Irrelevant directions shrink. The set of theories that flow into the fixed point in the infrared is called the critical surface or stable manifold.

If a fixed point has $n_{\rm rel}$ relevant scalar singlet directions, then reaching it usually requires tuning $n_{\rm rel}$ parameters. For an ordinary thermal critical point, one relevant singlet is often the temperature-like deformation, so one parameter must be tuned. A tricritical point has more relevant singlets and requires more tuning.

For example, near the Ising fixed point, the two most familiar relevant deformations are:

| Deformation | Physical meaning | Symmetry |
|---|---|---|
| $\epsilon$ | temperature-like perturbation | even under $\mathbb Z_2$ |
| $\sigma$ | magnetic-field perturbation | odd under $\mathbb Z_2$ |

If the microscopic system preserves the $\mathbb Z_2$ spin-flip symmetry, the magnetic field is absent and only the temperature-like parameter must be tuned. If the symmetry is broken, the magnetic perturbation is allowed and must also be controlled.

This is why global symmetries matter. They are not just labels on operators. They decide which deformations are allowed by the microscopic problem and therefore which fixed points are reachable without extra tuning.

## Scaling operators and critical exponents

The RG eigenoperators near a fixed point are the scaling operators of the CFT. Their dimensions determine critical exponents.

Let $\epsilon$ be the leading relevant scalar singlet that tunes the distance from criticality. Its coupling $t$ has RG eigenvalue

$$
y_t=d-\Delta_\epsilon.
$$

Under coarse graining by $b$,

$$
t(b)=b^{y_t}t.
$$

The correlation length rescales as a length:

$$
\xi(t)=b^{-1}\xi(t(b)).
$$

Choose $b=|t|^{-1/y_t}$ so that $t(b)$ is order one. Then

$$
\xi(t)\sim |t|^{-1/y_t}.
$$

Therefore

$$
\nu=\frac1{y_t}=\frac1{d-\Delta_\epsilon}.
$$

Similarly, the two-point function of an order-parameter operator $\sigma$ at criticality behaves as

$$
\langle \sigma(x)\sigma(0)\rangle\sim \frac1{|x|^{2\Delta_\sigma}}.
$$

In the usual statistical-physics notation,

$$
2\Delta_\sigma=d-2+\eta,
$$

so

$$
\Delta_\sigma=\frac{d-2+\eta}{2}.
$$

These formulas are a bridge between RG language and CFT language:

$$
\text{critical exponents}
\quad\leftrightarrow\quad
\text{operator dimensions}.
$$

CFT goes further. It includes not only the exponents but also OPE coefficients, spin labels, current normalizations, stress-tensor data, and crossing constraints.

## The trace relation and beta functions

In a renormalized QFT, the trace of the stress tensor is controlled by the failure of the theory to be scale invariant. Schematically,

$$
T^\mu{}_{\mu}=\sum_i \beta^i(g)\mathcal O_i+\text{anomalies}+\partial_\mu V^\mu.
$$

This formula hides many technical details: operator mixing, scheme dependence, total derivatives, contact terms, improvement terms, and curved-space contributions. But it gives the right conceptual map.

Away from a fixed point, nonzero beta functions introduce a scale. At a fixed point,

$$
\beta^i(g_*)=0,
$$

so the separated-point flat-space trace is reduced to anomaly and virial-current issues. If the virial term can be removed by improvement and no relevant anomaly remains in flat space at separated points, the fixed point has a traceless stress tensor:

$$
T^\mu{}_{\mu}=0.
$$

Then the special-conformal currents are conserved, and the scale-invariant fixed point is a CFT.

This explains the common workflow:

$$
\beta(g_*)=0
\quad\Longrightarrow\quad
\text{scale invariance}
\quad\stackrel{\text{assumptions}}{\Longrightarrow}\quad
\text{conformal invariance}.
$$

The last arrow is important. It is powerful in many unitary relativistic examples, but it is not a license to ignore assumptions.

## Relevant deformations as departures from a CFT

A CFT is not usually the whole story of a physical system. It is a fixed point. To describe nearby massive or ordered phases, one perturbs it:

$$
S=S_*+g\int d^d x\,\mathcal O(x).
$$

If $\Delta<d$, then $g$ is relevant and defines a mass scale

$$
M\sim |g|^{1/(d-\Delta)}
$$

up to anomalous and nonlinear corrections. The perturbed theory is no longer conformal. It may flow to a massive phase, a symmetry-broken phase, a topological field theory, or another CFT.

This viewpoint is extremely useful because it separates two questions:

| Question | Fixed-point answer |
|---|---|
| What is universal at the critical point? | The CFT data of $S_*$. |
| What happens when the system is moved away from criticality? | The relevant deformation and the RG flow it triggers. |

For example, the critical Ising CFT does not contain a finite correlation length. The off-critical Ising model does. The finite correlation length appears after perturbing the CFT by the temperature operator.

## Irrelevant deformations and universality

Irrelevant operators explain why universality is possible. A microscopic action contains infinitely many allowed local terms. Most are irrelevant near a given fixed point. Under coarse graining, their couplings shrink:

$$
g_i(b)=b^{d-\Delta_i}g_i,
\qquad \Delta_i>d.
$$

Thus the long-distance behavior becomes insensitive to their microscopic values.

This does not mean irrelevant operators are useless. They control corrections to scaling. If the leading irrelevant scalar has dimension $\Delta_{\rm irr}>d$, then the leading correction exponent is often

$$
\omega=\Delta_{\rm irr}-d.
$$

A critical observable may behave schematically as

$$
A(t)=A_0 |t|^{-p}\left(1+c|t|^{\omega\nu}+\cdots\right).
$$

In precision bootstrap and numerical studies, leading irrelevant dimensions are not afterthoughts. They are essential for comparing finite-size data, Monte Carlo simulations, and experiments with CFT predictions.

## Marginal directions and conformal manifolds

A marginal scalar has $\Delta=d$. Linearized RG does not decide its fate. Higher-order terms in the beta function matter:

$$
\frac{dg}{d\log b}=a g^2+b_3 g^3+\cdots.
$$

Three outcomes are common:

| Type | Meaning |
|---|---|
| Marginally relevant | The coupling grows slowly and eventually drives the theory away from the fixed point. |
| Marginally irrelevant | The coupling shrinks slowly, often producing logarithmic corrections to scaling. |
| Exactly marginal | The coupling can be varied without leaving the fixed-point locus. |

Exactly marginal deformations generate a conformal manifold: a continuous family of CFTs. The compact boson in two dimensions is the standard elementary example. Supersymmetric CFTs provide many richer examples.

The existence of a marginal operator in the spectrum is therefore not enough to claim a conformal manifold. One must show that the beta function vanishes beyond linear order and that no obstruction appears.

## Examples

### Gaussian fixed point

The free massless scalar is the Gaussian fixed point. In $d$ dimensions,

$$
\Delta_\phi=\frac{d-2}{2}.
$$

The operator $\phi^2$ has dimension $d-2$ in the free theory and is relevant for $d>2$. It corresponds to the mass deformation. The operator $\phi^4$ has dimension $2(d-2)$ and coupling dimension

$$
d-2(d-2)=4-d.
$$

Thus $\phi^4$ is relevant below four dimensions, marginal in four dimensions, and irrelevant above four dimensions at the Gaussian fixed point. This simple counting already hints why $d=4$ is the upper critical dimension for the ordinary $\phi^4$ universality class.

### Wilson–Fisher fixed point

In $d=4-\epsilon$, the $\phi^4$ coupling can flow to a nontrivial fixed point. This is the Wilson–Fisher fixed point. For small $\epsilon$, it is accessible perturbatively. In $d=3$, it describes the universality class of the critical Ising model for one real scalar with $\mathbb Z_2$ symmetry, and the $O(N)$ vector universality classes for $N$ real scalars with $O(N)$ symmetry.

From the CFT viewpoint, the Wilson–Fisher fixed point is not merely a beta-function zero. It has operator dimensions, OPE coefficients, a stress tensor, symmetry currents, and crossing-symmetric correlation functions. The bootstrap targets precisely this fixed-point data.

### Gauge-theory fixed points

Gauge theories can have fixed points that are weakly coupled, strongly coupled, or known only indirectly. The Banks–Zaks fixed point is perturbative when the number of fermion flavors is close to the value where asymptotic freedom is lost. Other gauge-theory fixed points, such as many three-dimensional gauge-matter examples, are much more strongly coupled.

The RG language says these theories may sit at fixed points. The CFT language asks for their local operator spectrum, current normalizations, monopole or defect operators when relevant, and crossing constraints.

### Two-dimensional fixed points

Two-dimensional critical systems often flow to CFTs with infinite-dimensional local conformal symmetry. The Ising model, tricritical Ising model, three-state Potts model, compact boson, and WZW models are classic examples. In these cases the RG fixed-point idea is sharpened by Virasoro symmetry, modular invariance, and sometimes rational CFT structure.

## What the RG viewpoint does not determine

The RG fixed-point picture is powerful, but by itself it does not solve the CFT.

It does not determine the full operator spectrum. It may identify a few relevant operators and critical exponents, but a CFT contains infinitely many local operators.

It does not determine OPE coefficients. Critical exponents alone are not enough to reconstruct correlation functions.

It does not automatically prove conformal invariance. One still needs the assumptions discussed on the previous page.

It does not guarantee that a fixed point has a useful Lagrangian. The IR CFT can be non-Lagrangian even if the UV description is Lagrangian.

It does not make all microscopic questions irrelevant. Symmetries, anomalies, defects, boundary conditions, and allowed perturbations are inherited from the microscopic setup and can change which fixed point is reached.

This is why the modern bootstrap viewpoint is complementary to RG. RG explains how fixed points arise. Bootstrap asks which fixed-point data are consistent.

## Common pitfalls

**Mistake 1: “Fixed point” means “free theory.”** Free theories are fixed points, but many important fixed points are interacting.

**Mistake 2: “Relevant” means “important in the UV.”** Relevant and irrelevant are usually stated with respect to infrared coarse graining near a fixed point. A relevant perturbation grows at long distances.

**Mistake 3: “Irrelevant” means “physically meaningless.”** Irrelevant operators control corrections to scaling, lattice artifacts, and finite-size effects. They are often crucial in precision work.

**Mistake 4: “Marginal” means “exactly marginal.”** Marginality at linear order is only the beginning. Higher-order beta functions decide the fate unless protected by symmetry or other structure.

**Mistake 5: “The fixed point is independent of symmetry.”** Symmetry controls allowed perturbations and operator sectors. The same local fixed point can appear differently depending on which global symmetry is preserved or gauged.

**Mistake 6: “Critical exponents are the whole CFT.”** They are only part of the spectrum. CFT data also includes OPE coefficients, spin information, current and stress-tensor normalizations, and consistency relations.

## Relations to other pages

This page follows [Scale Invariance versus Conformal Invariance](/cft-bootstrap/what-is-a-cft/scale-invariance-versus-conformal-invariance/) and prepares [Conformal Data](/cft-bootstrap/what-is-a-cft/conformal-data/). The next page translates fixed-point language into the operator-data language used throughout conformal bootstrap.

The detailed derivation of the conformal group belongs to [Conformal Symmetry](/cft-bootstrap/conformal-symmetry/). The Hilbert-space meaning of scaling dimensions belongs to [Radial Quantization](/cft-bootstrap/operators-states-radial-quantization/radial-quantization/) and [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/).

The perturbative Wilson–Fisher calculation, epsilon expansion, and exact RG methods belong mainly to [Renormalization, RG, and EFT](/renormalization-rg-eft/). This page uses those methods only as motivation for CFT.

## Research status

The role of RG fixed points in critical phenomena and continuum QFT is established. The language of relevant, irrelevant, and marginal operators is standard and indispensable.

The classification of fixed points is not complete. In three and higher dimensions, many strongly coupled fixed points are known only through a combination of perturbation theory, lattice methods, dualities, large-$N$ expansions, supersymmetric tools, and bootstrap constraints. The space of consistent CFT data is much larger than the space currently controlled by Lagrangians.

The relation between scale and conformal invariance is highly developed but assumption-sensitive. This volume therefore treats “CFT” as a conformal fixed point and states assumptions when moving from RG fixed-point language to conformal symmetry.

## Exercises

### Exercise 1: Relevant, irrelevant, or marginal?

In $d=3$, classify scalar operators of dimensions $\Delta=1.2$, $\Delta=3$, and $\Delta=4.1$ as relevant, marginal, or irrelevant.

<details>
<summary><strong>Solution</strong></summary>

For a scalar deformation $\int d^d x\,g\mathcal O$, the RG eigenvalue is

$$
y=d-\Delta.
$$

In $d=3$:

- $\Delta=1.2$ gives $y=1.8>0$, so the deformation is relevant.
- $\Delta=3$ gives $y=0$, so it is marginal at linear order.
- $\Delta=4.1$ gives $y=-1.1<0$, so it is irrelevant.

</details>

### Exercise 2: Correlation-length exponent from a CFT dimension

Let $\epsilon$ be the leading temperature-like scalar at a $d$-dimensional critical point. If $\Delta_\epsilon=d-1.4$, what is $\nu$?

<details>
<summary><strong>Solution</strong></summary>

The temperature coupling has RG eigenvalue

$$
y_t=d-\Delta_\epsilon.
$$

Here $\Delta_\epsilon=d-1.4$, so

$$
y_t=1.4.
$$

The correlation-length exponent is

$$
\nu=\frac1{y_t}=\frac1{1.4}=\frac57.
$$

</details>

### Exercise 3: Why irrelevant operators produce universality

Suppose two microscopic theories differ only by the coefficient of an operator $\mathcal O$ with $\Delta>d$ near an infrared fixed point. Explain why this difference disappears at long distances.

<details>
<summary><strong>Solution</strong></summary>

The coupling $g$ of $\mathcal O$ has RG eigenvalue

$$
y=d-\Delta<0.
$$

After coarse graining by $b>1$,

$$
g(b)=b^y g.
$$

Since $y<0$, $b^y\to 0$ as $b\to\infty$. Thus the difference between the two microscopic theories shrinks at long distances. They can flow to the same fixed point and share universal observables.

</details>

### Exercise 4: Upper critical dimension of φ⁴

At the Gaussian fixed point in $d$ dimensions, a free scalar has dimension $\Delta_\phi=(d-2)/2$. Find the dimension of $\phi^4$ and determine for which $d$ it is relevant, marginal, or irrelevant.

<details>
<summary><strong>Solution</strong></summary>

At the Gaussian fixed point,

$$
\Delta_{\phi^4}=4\Delta_\phi=2(d-2).
$$

The coupling to $\phi^4$ has eigenvalue

$$
y=d-2(d-2)=4-d.
$$

Therefore:

- for $d<4$, $y>0$ and $\phi^4$ is relevant;
- for $d=4$, $y=0$ and $\phi^4$ is marginal at linear order;
- for $d>4$, $y<0$ and $\phi^4$ is irrelevant.

Thus $d=4$ is the upper critical dimension for this interaction.

</details>

### Exercise 5: One-parameter tuning with Z₂ symmetry

A fixed point has one relevant scalar singlet, one relevant scalar charged under a $\mathbb Z_2$ symmetry, and all other symmetry-preserving scalar perturbations are irrelevant. How many parameters must be tuned to reach the fixed point if the microscopic theory preserves $\mathbb Z_2$? What if it does not?

<details>
<summary><strong>Solution</strong></summary>

If the microscopic theory preserves $\mathbb Z_2$, the charged relevant scalar cannot appear in the action. Only the relevant singlet must be tuned, so one parameter is required.

If the microscopic theory does not preserve $\mathbb Z_2$, the charged relevant scalar is allowed. Then both relevant directions must generally be tuned, so two parameters are required.

</details>

## References

- K. G. Wilson and J. Kogut, “The Renormalization Group and the $\epsilon$ Expansion,” *Physics Reports* **12** (1974). Classic review of RG fixed points, critical phenomena, and the connection to field theory.
- S. Coleman, “Dilatations,” in *Aspects of Symmetry*, Cambridge University Press, 1985. Classic discussion of scale transformations, RG equations, anomalous dimensions, and OPE ideas.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, 5th ed., Oxford University Press, 2021. Broad reference on QFT, RG, critical phenomena, and universal quantities.
- J. Cardy, *Scaling and Renormalization in Statistical Physics*, Cambridge University Press, 1996. Compact and conceptually clear treatment of scaling and RG in critical phenomena.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. Standard reference for the two-dimensional CFT realization of RG fixed-point ideas.
- D. Poland, S. Rychkov, and A. Vichi, “The Conformal Bootstrap: Theory, Numerical Techniques, and Applications,” *Reviews of Modern Physics* **91** (2019), arXiv:1805.04405. Modern bridge from CFT data to bootstrap constraints.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982. Clear introduction to higher-dimensional CFT and bootstrap language.

## Version history

- **2026-06-26:** Initial polished draft explaining CFTs as RG fixed points, scaling operators, relevant/irrelevant/marginal deformations, universality, trace relations, examples, pitfalls, and exercises.
