---
title: "Relevant, Irrelevant, and Marginal"
description: "Explains the Wilsonian classification of perturbations near an RG fixed point by scaling eigenvalues, including relevant tuning, irrelevant universality, and marginal nonlinear flow."
sidebar:
  label: "Relevant, Irrelevant, and Marginal"
  order: 5
level: Graduate
status: "Polished draft"
source: "Wilson and Kogut 1974; Zinn-Justin 2021; Weinberg Vol. II ch. 18; Schwartz ch. 23; Coleman, Dilatations; Burgess chs. 2–3; Altland and Simons ch. 6."
topics:
  - relevant operators
  - irrelevant operators
  - marginal operators
  - RG eigenvalues
  - scaling dimensions
  - critical surfaces
canonicalTopics:
  - relevant-operators
  - irrelevant-operators
  - marginal-operators
  - rg-eigenvalues
  - scaling-fields
researchStatus:
  established:
    - "The relevant, irrelevant, and marginal classification is the standard local classification of perturbations near an RG fixed point."
  active:
    - "Identifying the correct scaling operators can be subtle in strongly coupled theories, gauge theories, systems with dangerously irrelevant operators, defect sectors, nonlocal observables, or multiple competing fixed points."
---

## Summary

The words **relevant**, **irrelevant**, and **marginal** classify perturbations near a fixed point of the renormalization group.

Start with a fixed-point action $S_*$ and perturb it by local operators:

$$
S=S_*+\sum_a \lambda_a\int d^d x\,\mathcal O_a(x).
$$

If $\mathcal O_a$ is a scaling operator with dimension $\Delta_a$, define

$$
y_a=d-\Delta_a.
$$

In the Wilsonian IR-time convention of this chapter,

$$
\frac{d\lambda_a}{d\ell}=y_a\lambda_a+\cdots,
\qquad
\ell=\log\frac{\Lambda_0}{\Lambda}.
$$

Thus:

| Type | Condition | Toward the infrared |
|---|---:|---|
| relevant | $y_a>0$, or $\Delta_a<d$ | grows |
| irrelevant | $y_a<0$, or $\Delta_a>d$ | shrinks |
| marginal | $y_a=0$, or $\Delta_a=d$ | decided by nonlinear terms |

This classification is local in theory space. An operator is relevant or irrelevant **near a specified fixed point**, not absolutely forever and everywhere.

<figure class="doc-figure" style="--figure-width: 52rem; --caption-width: 55rem;">

![Theory space near a fixed point, showing an RG vector field, a critical surface, relevant, irrelevant, and marginal directions](/figures/renormalization-rg-eft/theory-space-linearization.svg)

<figcaption>

Relevant, irrelevant, and marginal are names for local scaling directions near a fixed point. Relevant perturbations move the trajectory away from the fixed point in the infrared, irrelevant perturbations decay into the critical surface, and marginal perturbations require nonlinear terms or exact arguments.

</figcaption>
</figure>

:::note[One sentence version]
Relevant perturbations must be tuned to reach a critical fixed point; irrelevant perturbations explain universality; marginal perturbations are where logarithms, fixed lines, and delicate dynamics like to hide.
:::

## Prerequisites

You should know [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/), [Momentum-Shell RG](/renormalization-rg-eft/wilsonian-renormalization/momentum-shell-rg/), and [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/).

For comparison with $\mu$-dependent language, review [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/) and [Scheme Dependence](/renormalization-rg-eft/renormalization-group-equations/scheme-dependence/). For operator language, the later chapter [Local Operators and OPE](/renormalization-rg-eft/local-operators-and-ope/) will make the connection to scaling operators and operator mixing more systematic.

## Core idea

Near a fixed point, the RG flow can be linearized. Let $\tilde g^i$ be dimensionless coordinates on theory space and let

$$
\tilde g^i=\tilde g_*^i+\delta\tilde g^i.
$$

The Wilsonian IR-time flow has the form

$$
\frac{d}{d\ell}\delta\tilde g^i
=M^i{}_j\delta\tilde g^j+O(\delta\tilde g^2),
$$

where

$$
M^i{}_j=\left.\frac{\partial\mathcal B^i}{\partial\tilde g^j}\right|_{\tilde g_*}.
$$

Diagonalizing $M$ gives scaling directions. If $v_a^i$ is an eigenvector with eigenvalue $y_a$, then

$$
\delta\tilde g_a(\ell)=e^{y_a\ell}\delta\tilde g_a(0)
$$

at linear order.

That is the classification. Positive $y_a$ grows as the cutoff is lowered: relevant. Negative $y_a$ decays: irrelevant. Zero $y_a$ requires the next terms in the beta function: marginal.

The operator version says the same thing. A perturbation

$$
\lambda_a\int d^d x\,\mathcal O_a(x)
$$

has coupling dimension

$$
[\lambda_a]=d-\Delta_a.
$$

The RG eigenvalue is

$$
y_a=d-\Delta_a.
$$

At the Gaussian fixed point this is engineering dimensional analysis. At an interacting fixed point, $\Delta_a$ includes anomalous dimensions.

## Setup and conventions

We use Wilsonian infrared time

$$
\ell=\log\frac{\Lambda_0}{\Lambda},
$$

so increasing $\ell$ means going toward longer distances. The classification on this page follows that direction.

If instead one uses the ultraviolet-oriented Callan–Symanzik convention

$$
\beta_g=\mu\frac{dg}{d\mu},
$$

then the sign of the flow reverses when $\mu$ is identified with a running cutoff:

$$
\frac{d}{d\ell}\sim -\mu\frac{d}{d\mu}.
$$

This is a sign convention, not a disagreement about physics.

For a scaling operator $\mathcal O_a$,

$$
\mathcal O_a(x)\to b^{-\Delta_a}\mathcal O_a(x/b)
$$

under a scale transformation by $b>1$. The integrated operator transforms as

$$
\int d^d x\,\mathcal O_a(x)
\to
b^{d-\Delta_a}\int d^d x\,\mathcal O_a(x).
$$

This gives the linear Wilsonian flow

$$
\frac{d\lambda_a}{d\ell}=(d-\Delta_a)\lambda_a+\text{nonlinear terms}.
$$

## Relevant perturbations

A relevant perturbation has

$$
y_a>0
\qquad\text{or}\qquad
\Delta_a<d.
$$

It grows toward the infrared. Therefore, a fixed point with relevant directions is unstable unless those directions are tuned.

This is the Wilsonian meaning of a critical point. To see universal fixed-point behavior, one must tune the relevant couplings to land on the critical surface. If there is one relevant direction, one parameter must be tuned. If there are two relevant directions, two parameters must be tuned.

The standard scalar example is the mass perturbation near the Gaussian fixed point:

$$
S=S_*+\frac12m^2\int d^d x\,\phi^2.
$$

At the Gaussian fixed point,

$$
[\phi]=\frac{d-2}{2},
\qquad
\Delta_{\phi^2}=d-2,
$$

so

$$
y_{\phi^2}=d-(d-2)=2.
$$

The mass term is relevant in any dimension at the Gaussian fixed point. This is why mass gaps and correlation lengths are sensitive to tuning near a critical point.

Relevant does not mean bad. Relevant parameters often encode the most important physical controls: mass, temperature, magnetic field, chemical potential, symmetry-breaking source, or deformation away from a CFT.

## Irrelevant perturbations

An irrelevant perturbation has

$$
y_a<0
\qquad\text{or}\qquad
\Delta_a>d.
$$

It shrinks toward the infrared. This is the mathematical core of universality: microscopic details often correspond to irrelevant perturbations, so their long-distance influence fades.

For example, at the Gaussian fixed point,

$$
\Delta_{\phi^6}=3(d-2),
$$

so

$$
y_{\phi^6}=d-3(d-2)=6-2d.
$$

In $d=4$, this gives

$$
y_{\phi^6}=-2.
$$

The $\phi^6$ interaction is irrelevant near the four-dimensional Gaussian fixed point. It can affect short-distance amplitudes or subleading corrections, but it does not define a new leading long-distance universality class in that neighborhood.

Irrelevant does not mean nonexistent. It means suppressed at long distances near a fixed point. In EFT, irrelevant operators are often the main characters: they encode finite-size, finite-resolution, heavy-particle, and high-scale corrections.

A typical EFT expansion is precisely an expansion in irrelevant operators:

$$
\mathcal L_{\mathrm{EFT}}
=\mathcal L_{\mathrm{leading}}
+\sum_i\frac{C_i}{M^{\Delta_i-d}}\mathcal O_i.
$$

For processes with characteristic scale $Q\ll M$, such terms are suppressed by powers of $Q/M$.

## Marginal perturbations

A marginal perturbation has

$$
y_a=0
\qquad\text{or}\qquad
\Delta_a=d
$$

at linear order. Linear analysis alone cannot decide its fate. One must examine nonlinear terms:

$$
\frac{d\lambda}{d\ell}=a\lambda^2+b\lambda^3+\cdots.
$$

There are three common possibilities.

| Type | Behavior | Typical interpretation |
|---|---|---|
| exactly marginal | beta function vanishes along a direction | line or manifold of fixed points |
| marginally irrelevant | flows slowly to zero in the IR | logarithmic corrections to scaling |
| marginally relevant | grows slowly in the IR | dimensional transmutation or gap generation |

Examples and previews:

- In four-dimensional scalar $\phi^4$ theory, the quartic coupling is marginal at tree level. Loop effects make it marginally irrelevant toward the infrared in perturbation theory.
- In asymptotically free non-Abelian gauge theory, the gauge coupling is marginal at tree level and marginally relevant toward the infrared.
- In two-dimensional CFT, exactly marginal operators can generate conformal manifolds when all higher-order obstructions vanish.
- In the Kosterlitz–Thouless transition, marginal directions lead to unusually slow flows and essential scaling.

Marginal is where students most often get tricked. Marginal at engineering level is only the first word, not the verdict.

## Scaling operators versus monomials

The clean classification applies to eigenoperators of the linearized RG, not necessarily to the monomials that first appear in a Lagrangian.

Near a fixed point, operators can mix:

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R}.
$$

The scaling operators are combinations that diagonalize the anomalous-dimension matrix or, equivalently, the stability matrix of the RG flow. A Lagrangian monomial such as $\phi^4$ may be close to an eigenoperator at the Gaussian fixed point, but at an interacting fixed point the true scaling operator is generally a mixture.

This is why the precise statement is:

$$
\text{relevant, irrelevant, and marginal classify RG eigenperturbations.}
$$

One may still speak loosely of a monomial being relevant when mixing is absent, negligible, triangular by symmetry, or clear from context. But the eigenoperator language is the safe version.

## Gaussian fixed point examples

At the Gaussian scalar fixed point,

$$
[\phi]=\frac{d-2}{2}.
$$

For $\mathbb Z_2$-even scalar operators without derivatives, the engineering dimensions are:

| Operator | Dimension $\Delta$ | RG eigenvalue $y=d-\Delta$ | Classification |
|---|---:|---:|---|
| $1$ | $0$ | $d$ | relevant vacuum-energy direction |
| $\phi^2$ | $d-2$ | $2$ | relevant |
| $\phi^4$ | $2d-4$ | $4-d$ | relevant for $d<4$, marginal for $d=4$, irrelevant for $d>4$ |
| $\phi^6$ | $3d-6$ | $6-2d$ | irrelevant for $d>3$, marginal for $d=3$ |
| $\phi^{2n}$ | $n(d-2)$ | $d-n(d-2)$ | depends on $d$ and $n$ |

The identity operator changes the vacuum energy. It is relevant by dimension counting, but in many flat-space scattering or connected-correlator calculations it decouples from normalized observables. In thermodynamics or gravity, it matters.

Derivative operators are classified the same way. For example,

$$
\phi^2(\partial\phi)^2
$$

has engineering dimension

$$
\Delta_{\phi^2(\partial\phi)^2}
=2[\phi]+2([\partial]+[\phi])
=4[\phi]+2
=2(d-2)+2
=2d-2.
$$

Thus

$$
y=d-(2d-2)=2-d.
$$

In $d=4$ this is irrelevant with $y=-2$. Tiny arithmetic mistakes in power counting have a way of becoming big conceptual mistakes.

## Relation to power-counting renormalizability

Power-counting renormalizability is the Gaussian fixed point version of relevance classification.

Near the four-dimensional Gaussian fixed point:

| Old name | Wilsonian meaning near Gaussian fixed point |
|---|---|
| super-renormalizable | relevant coupling with positive mass dimension |
| renormalizable | marginal or relevant by engineering dimension |
| nonrenormalizable | irrelevant by engineering dimension |

The modern Wilsonian viewpoint changes the emotional temperature of these words. Nonrenormalizable does not mean useless. It means irrelevant near the Gaussian fixed point, hence suppressed at sufficiently low energy. This is exactly why EFT works.

The classification becomes more subtle near an interacting fixed point. A coupling that is irrelevant near the Gaussian fixed point may participate in an interacting fixed point, and anomalous dimensions can shift relevance. The fixed point comes first; the labels come after.

## Critical exponents

The relevant eigenvalues near a critical fixed point determine critical exponents. If the temperature-like perturbation has RG eigenvalue $y_t$, then the correlation length exponent is

$$
\nu=\frac{1}{y_t}.
$$

The heuristic derivation is short. Let $t$ be the reduced temperature and assume it flows as

$$
t(\ell)=e^{y_t\ell}t(0).
$$

The correlation length rescales as

$$
\xi(t)=e^\ell\xi(t(\ell)).
$$

Choose $\ell_*$ such that $t(\ell_*)\sim 1$, so

$$
e^{\ell_*}\sim |t|^{-1/y_t}.
$$

Since $\xi(t(\ell_*))$ is order one in cutoff units,

$$
\xi(t)\sim |t|^{-1/y_t}.
$$

Therefore $\nu=1/y_t$.

Other critical exponents are extracted from other relevant eigenvalues, anomalous dimensions, and scaling relations. The fixed-point spectrum is the universal data; microscopic couplings are coordinates used to reach it.

## Dangerous irrelevance

An irrelevant operator can sometimes be **dangerously irrelevant**. This means it flows to zero near the fixed point but still affects some observable through a singular dependence.

The classic example is the quartic coupling above the upper critical dimension in Landau–Ginzburg theory. At the Gaussian fixed point for $d>4$, $\phi^4$ is irrelevant. Yet in the ordered phase it stabilizes the potential:

$$
V(\phi)=\frac12 r\phi^2+\frac{u}{4!}\phi^4.
$$

Sending $u$ to zero too early can make the potential unstable or make order-parameter formulas singular. The operator is irrelevant for the fixed-point scaling in one sense, but dangerous for some observables.

The moral is not that irrelevant means secretly relevant. The moral is more precise: the scaling limit and the observable limit may not commute.

A later page on dangerously irrelevant operators will treat this carefully.

## Marginal examples in one equation

Consider a single marginal coupling with nonlinear flow

$$
\frac{d\lambda}{d\ell}=a\lambda^2+O(\lambda^3).
$$

For small positive $\lambda$:

| Sign of $a$ | IR behavior | Name |
|---:|---|---|
| $a<0$ | $\lambda(\ell)\to 0$ slowly | marginally irrelevant |
| $a>0$ | $\lambda(\ell)$ grows and perturbation theory eventually fails | marginally relevant |
| $a=0$ to all orders and nonperturbatively | fixed line or conformal manifold | exactly marginal |

Solving the leading equation gives

$$
\lambda(\ell)=\frac{\lambda_0}{1-a\lambda_0\ell}.
$$

This slow $1/\ell$ behavior is why marginal couplings create logarithms instead of simple power laws.

## Practical diagnostic checklist

When classifying a perturbation, ask these questions in order.

1. **Which fixed point?** Relevance is local in theory space.
2. **Which RG time convention?** IR-time and UV-time signs differ.
3. **Which operator basis?** Monomials may mix; eigenoperators classify cleanly.
4. **Are there symmetries?** Symmetries block mixing and exclude perturbations.
5. **Are there redundancies?** Field redefinitions and equation-of-motion operators may not be physical directions.
6. **Is the perturbation marginal?** Then compute nonlinear terms or use an exact argument.
7. **Could it be dangerously irrelevant?** Check whether an observable depends singularly on a coupling that flows to zero.

This checklist prevents a surprising number of wrong statements.

## Common pitfalls

**Calling an operator relevant without naming the fixed point.** The same expression can have different scaling dimensions at different fixed points.

**Confusing engineering and scaling dimensions.** Engineering dimensions are enough at the Gaussian fixed point. Interacting fixed points require anomalous dimensions.

**Treating marginal as exactly marginal.** Marginal means undecided at linear order. Most marginal couplings run once nonlinear terms are included.

**Thinking irrelevant means unimportant.** Irrelevant operators control corrections to scaling, EFT errors, finite-size effects, and sometimes dangerously irrelevant physics.

**Forgetting operator mixing.** The eigenvectors of the RG stability matrix, not arbitrary monomials, define the clean classification.

**Mixing UV and IR sign conventions.** In this chapter $\ell$ flows toward the infrared. In many perturbative pages $\mu$ flows toward the ultraviolet.

**Ignoring redundant operators.** Some apparent directions in action space are just changes of variables.

## Relations to other pages

This page follows [Theory Space](/renormalization-rg-eft/wilsonian-renormalization/theory-space/) and prepares [Universality](/renormalization-rg-eft/wilsonian-renormalization/universality/), [Blocking and Coarse Graining](/renormalization-rg-eft/wilsonian-renormalization/blocking-and-coarse-graining/), and [Exact Renormalization Group](/renormalization-rg-eft/wilsonian-renormalization/exact-renormalization-group/).

It connects to [Power-Counting Renormalizability](/renormalization-rg-eft/regularization-counterterms/power-counting-renormalizability/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), [Fixed Points](/renormalization-rg-eft/fixed-points-critical-phenomena/fixed-points/), [Linearized RG Flow](/renormalization-rg-eft/fixed-points-critical-phenomena/linearized-rg-flow/), [Critical Exponents](/renormalization-rg-eft/fixed-points-critical-phenomena/critical-exponents/), and [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/).

## Research status

The relevant/irrelevant/marginal classification is settled as a local statement about RG fixed points. It is one of the central organizing principles of QFT, statistical mechanics, EFT, and critical phenomena.

Active research enters through hard cases: finding the fixed points, computing the scaling spectrum, dealing with strong coupling, identifying redundant directions, preserving gauge constraints, understanding dangerously irrelevant variables, and extending the classification to defects, boundaries, nonlocal operators, generalized symmetries, and non-Lagrangian theories.

## Exercises

### Exercise 1: Classify scalar monomials

At the Gaussian fixed point in $d=3$, classify $\phi^2$, $\phi^4$, $\phi^6$, and $\phi^8$ using $[\phi]=(d-2)/2$.

<details><summary><strong>Solution</strong></summary>

In $d=3$,

$$
[\phi]=\frac12.
$$

Thus

$$
\Delta_{\phi^{2n}}=n.
$$

The RG eigenvalue is

$$
y=d-\Delta=3-n.
$$

Therefore:

| Operator | $\Delta$ | $y$ | Classification |
|---|---:|---:|---|
| $\phi^2$ | $1$ | $2$ | relevant |
| $\phi^4$ | $2$ | $1$ | relevant |
| $\phi^6$ | $3$ | $0$ | marginal at tree level |
| $\phi^8$ | $4$ | $-1$ | irrelevant |

Loop corrections decide the fate of the tree-level marginal $\phi^6$ perturbation.

</details>

### Exercise 2: Marginally irrelevant flow

Solve

$$
\frac{d\lambda}{d\ell}=-a\lambda^2,
\qquad a>0,
$$

with initial value $\lambda(0)=\lambda_0>0$. Show that $\lambda$ is marginally irrelevant.

<details><summary><strong>Solution</strong></summary>

Separate variables:

$$
\frac{d\lambda}{\lambda^2}=-a\,d\ell.
$$

Integrating gives

$$
-\frac{1}{\lambda(\ell)}=-a\ell-\frac{1}{\lambda_0}.
$$

Therefore

$$
\lambda(\ell)=\frac{\lambda_0}{1+a\lambda_0\ell}.
$$

As $\ell\to\infty$,

$$
\lambda(\ell)\sim \frac{1}{a\ell}\to0.
$$

It decays toward the infrared, but only logarithmically slowly. Hence it is marginally irrelevant.

</details>

### Exercise 3: Tuning relevant directions

A fixed point has three relevant directions and infinitely many irrelevant directions. How many independent microscopic parameters must be tuned to reach its critical surface?

<details><summary><strong>Solution</strong></summary>

Each relevant direction grows away from the fixed point in the infrared. To reach the critical surface, the components along all relevant directions must be set to the special values that flow into the fixed point. Therefore three independent tunings are required. The infinitely many irrelevant directions do not require tuning; they decay toward the fixed point.

</details>

### Exercise 4: An anomalous dimension changes relevance

Suppose an operator has engineering dimension $\Delta_{\mathrm{eng}}=d+0.1$ but anomalous dimension $\gamma=-0.3$ at an interacting fixed point. Is it relevant, irrelevant, or marginal?

<details><summary><strong>Solution</strong></summary>

The full scaling dimension is

$$
\Delta=\Delta_{\mathrm{eng}}+\gamma=d+0.1-0.3=d-0.2.
$$

Therefore

$$
y=d-\Delta=0.2>0.
$$

The perturbation is relevant at this interacting fixed point, even though engineering power counting would have called it irrelevant near the Gaussian fixed point.

</details>

### Exercise 5: Correlation-length exponent

Assume the temperature-like perturbation $t$ has Wilsonian IR-time flow

$$
\frac{dt}{d\ell}=y_t t.
$$

Use RG scaling to derive $\nu=1/y_t$.

<details><summary><strong>Solution</strong></summary>

The solution is

$$
t(\ell)=e^{y_t\ell}t(0).
$$

Choose $\ell_*$ such that $t(\ell_*)$ is order one. Then

$$
e^{\ell_*}\sim |t(0)|^{-1/y_t}.
$$

Under RG, lengths scale by $e^\ell$, so the correlation length behaves as

$$
\xi(t)\sim e^{\ell_*}\sim |t|^{-1/y_t}.
$$

By definition $\xi\sim |t|^{-\nu}$, hence

$$
\nu=\frac{1}{y_t}.
$$

</details>

## References

- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," for the classic RG classification of scaling directions.
- Sidney Coleman, "Dilatations," in *Aspects of Symmetry*, for scale transformations, anomalous dimensions, and the Callan–Symanzik viewpoint.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for scaling fields, relevant and irrelevant variables, and critical exponents.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for RG methods, fixed points, and critical phenomena.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter 23, for Wilsonian RG and relevance classification in QFT language.
- C. P. Burgess, *Introduction to Effective Field Theory*, chapters 2–3, for scaling, redundant interactions, and EFT power counting.
- Alexander Altland and Ben Simons, *Condensed Matter Field Theory*, chapter 6, for relevance, marginality, and RG in condensed-matter examples.

## Version history

- 2026-06-17: First polished draft. Classified relevant, irrelevant, and marginal directions using Wilsonian IR-time conventions, scaling dimensions, operator mixing, Gaussian examples, critical exponents, and dangerous irrelevance preview.
