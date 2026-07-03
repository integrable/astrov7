---
title: "Scheme Dependence"
description: "Explains renormalization schemes as coordinate choices on coupling space, how beta functions and anomalous dimensions transform, and which RG statements are physical."
sidebar:
  label: "Scheme Dependence"
  order: 7
level: Graduate
status: "Polished draft"
source: "Coleman, Dilatations and Asymptotic Freedom; Srednicki §§27–29; Schwartz ch. 23; Weinberg Vol. II ch. 18; Wilson and Kogut 1974; Zinn-Justin 2021."
topics:
  - renormalization schemes
  - scheme dependence
  - beta functions
  - anomalous dimensions
  - coupling redefinitions
  - universality
canonicalTopics:
  - scheme-dependence
  - renormalization-scheme
  - beta-function-covariance
  - universal-rg-data
researchStatus:
  established:
    - "Finite renormalization-scheme changes are changes of coordinates on the space of renormalized couplings and operator bases; physical observables are invariant when computed consistently."
  active:
    - "Scheme dependence remains practically important in precision perturbation theory, multi-scale EFT matching, lattice-continuum conversions, heavy-threshold decoupling, and attempts to infer physics from truncated RG flows."
---

## Summary

A **renormalization scheme** is a convention for assigning finite parts to renormalized parameters and renormalized operators. Changing scheme is not changing the physical theory. It is changing coordinates on the space of descriptions.

For renormalized couplings $g^i$, a finite scheme change has the form

$$
g^{\prime i}=f^i(g),
$$

where $f$ is locally invertible near the region of coupling space being used. The beta functions transform as a vector field:

$$
\beta^{\prime i}(g')
=
\frac{\partial f^i}{\partial g^j}\,\beta^j(g),
\qquad g'=f(g).
$$

This is the central formula of the page. It says that RG flow is a geometric object, while the components of that flow depend on the coordinates used to describe it.

The moral is not that beta functions are meaningless. The moral is sharper:

$$
\text{raw coordinates are scheme dependent; invariant RG statements are not.}
$$

The numerical value of a coupling, the location of a fixed point in coordinates, and higher perturbative beta-function coefficients can be scheme dependent. Physical observables, critical exponents at fixed points, scaling dimensions, and consistently defined scale ratios are not.

## Prerequisites

You should know [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Running Couplings](/renormalization-rg-eft/renormalization-group-equations/running-couplings/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), and [RG-Improved Perturbation Theory](/renormalization-rg-eft/renormalization-group-equations/rg-improved-perturbation-theory/).

It is also useful to have seen [Counterterm Schemes](/renormalization-rg-eft/renormalized-perturbation-theory/counterterm-schemes/), [On-Shell Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/on-shell-scheme/), [Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/), and [$\overline{\mathrm{MS}}$ Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/msbar-scheme/).

## Core idea

Renormalization has two logically separate jobs.

First, it removes regulator dependence from predictions by introducing local counterterms and defining renormalized quantities. Second, it chooses a convention for the finite pieces of those quantities. The second job is the scheme choice.

A scheme may define a coupling by subtracting only poles in dimensional regularization, by subtracting $1/\bar\epsilon$ combinations, by imposing a momentum-space condition at a Euclidean subtraction point, or by requiring that an on-shell amplitude take a measured value. All of these can describe the same physics, provided the parameters are converted correctly.

The clean way to think about this is geometric. The theory is not the list of numbers

$$
(g^1,g^2,\ldots).
$$

Those numbers are coordinates. A different scheme uses different coordinates

$$
(g^{\prime 1},g^{\prime 2},\ldots).
$$

The physical content is in invariant statements: the value of an observable, the existence of a fixed point under an invertible change of variables, the eigenvalues that govern linearized scaling near that fixed point, and ratios of dynamically generated scales after scheme conversion.

:::tip[Do not compare coordinates as if they were observables]
Saying that $g_{\overline{\mathrm{MS}}}(\mu)$ differs from a momentum-subtraction coupling at the same numerical $\mu$ is not a paradox. They are different coordinates on the same low-energy information. Compare predictions, or first convert the coordinates.
:::

## Setup and conventions

This volume defines beta functions by

$$
\beta^i(g)
\equiv
\left.\mu\frac{d g^i}{d\mu}\right|_{\text{bare parameters fixed}}.
$$

For a single coupling $g$, this reduces to

$$
\beta(g)=\mu\frac{dg}{d\mu}.
$$

A finite scheme change is an invertible redefinition

$$
g' = f(g).
$$

For several couplings,

$$
g^{\prime i}=f^i(g^1,g^2,\ldots).
$$

The scheme change may also involve masses and operator normalizations. For now we begin with dimensionless couplings. Masses and operators are discussed below.

A renormalized observable $F$ is a scalar under a change of scheme:

$$
F'(Q,\mu,g')=F(Q,\mu,g),
\qquad g'=f(g).
$$

This equation does not mean the two perturbative formulas look identical term by term. It means they describe the same function after changing coordinates.

## Beta functions as vector fields

Start with the RG equation in one scheme:

$$
\frac{d g^i}{d\log\mu}=\beta^i(g).
$$

Differentiate the transformed coupling $g^{\prime i}=f^i(g)$ along the same RG trajectory:

$$
\frac{d g^{\prime i}}{d\log\mu}
=
\frac{\partial f^i}{\partial g^j}\frac{d g^j}{d\log\mu}
=
\frac{\partial f^i}{\partial g^j}\beta^j(g).
$$

Therefore

$$
\beta^{\prime i}(g')
=
\frac{\partial f^i}{\partial g^j}\beta^j(g),
\qquad g=f^{-1}(g').
$$

This is exactly how a vector field transforms under a change of coordinates. It is the same mathematical structure as changing coordinates on a manifold: the arrows are intrinsic, their components are not.

This point resolves a common contradiction. We often say that beta functions are scheme dependent. We also use beta functions to make physical claims. Both statements are true because the physical claims are not the coordinate components themselves. They are claims about the flow as a geometric object and about observables transported along it.

## One-coupling example

Consider a single marginal coupling with perturbative beta function

$$
\beta(g)=\beta_0 g^3+\beta_1 g^5+\beta_2 g^7+O(g^9).
$$

Let a new scheme define

$$
g'=g+a g^3+c g^5+O(g^7).
$$

Using

$$
\beta'(g')=\frac{dg'}{dg}\beta(g),
$$

and re-expanding in $g'$, one finds

$$
\beta'(g')
=
\beta_0 g'^3+\beta_1 g'^5+\beta_2' g'^7+O(g'^9),
$$

with

$$
\beta_2'
=
\beta_2-2a\beta_1+(2c-3a^2)\beta_0.
$$

Thus the first two coefficients are invariant under this ordinary analytic redefinition, while the third coefficient changes.

This is why one often says that the first two coefficients of a gauge-theory beta function are universal in mass-independent schemes. The phrase has assumptions packed into it: one coupling, analytic coupling redefinitions of the standard form, and a scheme class that does not introduce explicit mass thresholds into the beta function. Outside those assumptions, do not quote the slogan blindly.

For a coupling whose beta function begins as

$$
\beta(\lambda)=b_1\lambda^2+b_2\lambda^3+b_3\lambda^4+\cdots,
$$

as in many scalar-coupling conventions, the same lesson holds with the corresponding analytic redefinitions $\lambda'=\lambda+a\lambda^2+\cdots$: the leading coefficients allowed by the coordinate freedom are more universal than higher coefficients, but the precise statement depends on the normalization and on the class of schemes being compared.

## Fixed points

A fixed point satisfies

$$
\beta^i(g_*)=0.
$$

Under an invertible finite scheme change,

$$
\beta^{\prime i}(g'_*)
=
\frac{\partial f^i}{\partial g^j}\bigg|_{g_*}\beta^j(g_*)=0,
\qquad g'_*=f(g_*).
$$

So the existence of a fixed point is invariant under a regular invertible change of coordinates. Its coordinate location is not. The numbers $g_*^i$ and $g_*^{\prime i}$ need not be equal, and neither list is an observable.

The linearized RG flow near a fixed point is

$$
\frac{d\delta g^i}{d\log\mu}=B^i{}_j\delta g^j+O(\delta g^2),
\qquad
B^i{}_j=\left.\frac{\partial\beta^i}{\partial g^j}\right|_{g_*}.
$$

At the transformed fixed point, the matrix $B$ changes by a similarity transformation:

$$
B'=J B J^{-1},
\qquad
J^i{}_j=\left.\frac{\partial f^i}{\partial g^j}\right|_{g_*}.
$$

Therefore the eigenvalues of $B$ are invariant. These eigenvalues determine the RG scaling of perturbations around the fixed point. In statistical-physics language, after translating the sign convention for RG time, they determine relevant and irrelevant directions and critical exponents.

This is the practical reason critical exponents are meaningful even though beta-function components are scheme dependent.

:::caution[Truncated beta functions can invent or destroy fixed points]
The exact existence of a fixed point is invariant under a regular scheme change. A fixed point of a truncated beta function may not be. If a fixed point appears at coupling $g_*\sim 1$ in a low-order calculation, a scheme change can move it substantially or remove it from the region where the truncation is trustworthy.
:::

## Observables and finite redefinitions

Let an observable have a perturbative expansion

$$
F(Q)=g^2(\mu)+A g^4(\mu)+O(g^6).
$$

Suppose a second scheme defines

$$
g'=g+a g^3+O(g^5).
$$

Inverting gives

$$
g=g'-a g'^3+O(g'^5).
$$

Then

$$
g^2=g'^2-2a g'^4+O(g'^6),
$$

so the same observable is

$$
F(Q)=g'^2+(A-2a)g'^4+O(g'^6).
$$

The finite coefficient changed. The observable did not.

This example is deliberately small, but it is the whole story in miniature. A coefficient in a perturbative formula is not automatically physical. A coefficient attached to a convention-dependent coordinate can shift when the coordinate changes.

For real calculations, scheme conversion formulas are part of the result. If a paper quotes an $\overline{\mathrm{MS}}$ coupling, an on-shell mass, a momentum-subtraction coupling, or a lattice bare coupling, the scheme is not a footnote. It is part of the definition.

## Anomalous dimensions and operator bases

Composite operators introduce a second kind of scheme dependence: the choice of operator basis and finite operator normalization.

Let renormalized operators obey

$$
\mathcal O_{a,0}=Z_a{}^b\mathcal O_{b,R},
$$

and define the anomalous-dimension matrix by

$$
\gamma_a{}^b
=
(Z^{-1})_a{}^c
\left.\mu\frac{d Z_c{}^b}{d\mu}\right|_{\text{bare}}.
$$

With this convention,

$$
\left.\mu\frac{d}{d\mu}\mathcal O_{a,R}\right|_{\text{bare}}
=-\gamma_a{}^b\mathcal O_{b,R}.
$$

Now perform a finite basis change

$$
\mathcal O'_a=N_a{}^b(g)\mathcal O_b.
$$

The anomalous-dimension matrix transforms as

$$
\gamma'
=
N\gamma N^{-1}
-
\beta^i\frac{\partial N}{\partial g^i}N^{-1}.
$$

The second term appears because the basis itself can depend on running couplings. At a fixed point, where $\beta^i(g_*)=0$, the transformation reduces to a similarity transformation:

$$
\gamma'_*=N_*\gamma_*N_*^{-1}.
$$

Thus the eigenvalues associated with scaling operators at a fixed point are invariant, even though the components of $\gamma$ away from the fixed point are basis and scheme dependent.

For EFT Wilson coefficients the same logic appears in dual form. If the operator basis is changed, the coefficient vector changes inversely so that

$$
\sum_i C_i\mathcal O_i
$$

is unchanged. The anomalous-dimension matrix and Wilson coefficients both transform, but physical amplitudes do not.

## Mass-dependent and mass-independent schemes

A **mass-independent scheme** defines subtraction rules without explicit dependence on mass ratios such as $m/\mu$. Minimal subtraction and $\overline{\mathrm{MS}}$ are the standard examples. Their beta functions are simple and universal in many perturbative contexts, but heavy particles do not automatically disappear from the beta function when $\mu$ drops below their mass. Decoupling is implemented by matching to a lower-energy EFT at a threshold.

A **mass-dependent scheme** can define couplings through physical or momentum-subtraction conditions. Then beta functions may depend explicitly on ratios such as

$$
\frac{m}{\mu}.
$$

Such schemes can make decoupling more visible inside the running itself. The price is that beta functions become less universal and less compact.

Neither approach is morally superior. Mass-independent schemes are usually efficient for high-order perturbation theory and EFT matching. Mass-dependent schemes can be physically transparent for threshold behavior. Problems arise only when one mixes formulas from different schemes without conversion.

## What is invariant?

The following table is worth internalizing.

| Object | Scheme status | Comment |
|---|---|---|
| Numerical value of $g(\mu)$ | scheme dependent | a coordinate, not an observable |
| Higher beta-function coefficients | scheme dependent | after the universal coefficients allowed by assumptions |
| Fixed-point coordinate $g_*$ | scheme dependent | transformed by $g'_*=f(g_*)$ |
| Existence of a fixed point | invariant under regular invertible changes | not guaranteed by truncated perturbation theory |
| Linearized RG eigenvalues at a fixed point | invariant | determine scaling exponents after sign-convention translation |
| Scaling dimensions at a fixed point | invariant | eigenvalues of properly defined operator mixing |
| S-matrix elements and physical rates | invariant | after all conversions and matching are included |
| Wilson coefficients | scheme and basis dependent | coefficients are not observables by themselves |
| Products $C_i\mathcal O_i$ in observables | invariant | after operator-basis conversion |
| Dynamically generated scale normalization | scheme dependent | scale ratios are physical after consistent conversion |

The sentence "the beta function is scheme dependent" should therefore never be used as a conversation-ending shrug. It is an invitation to ask the better question: what invariant information is the calculation trying to extract?

## Scheme dependence at finite order

Exact physical observables are scheme independent. Truncated perturbative approximations are not.

Suppose an observable is known to order $g^4$. A scheme change reshuffles contributions between the coupling definition and the explicit coefficient. If every term through the same physical order is included, the two schemes agree up to the first neglected order. But because the series is truncated, the residual difference remains at higher order.

This residual scheme dependence is not a bug. It is one diagnostic of missing higher-order terms.

For example, a fixed-order prediction may depend on:

- the renormalization scale $\mu$;
- the subtraction scheme, such as MS versus $\overline{\mathrm{MS}}$;
- the definition of masses, such as pole mass versus running mass;
- the operator basis and evanescent-operator conventions in dimensional regularization;
- the threshold-matching prescription used to cross heavy-particle masses.

A careful calculation states these conventions and, when possible, estimates the effect of varying them within a reasonable range.

The dangerous move is to mistake convention dependence for physical uncertainty in the exact theory. The exact theory has no such ambiguity. The finite calculation does.

## Scheme dependence and naturalness

Scheme dependence is sometimes invoked carelessly in discussions of naturalness and power divergences. The fact that dimensional regularization hides power divergences does not mean that relevant operators have no physical sensitivity to heavy thresholds. Conversely, a hard cutoff displaying a term proportional to $\Lambda^2$ does not by itself prove the existence of a physical particle with mass $\Lambda$.

The invariant question is not "which divergent symbol appears in my favorite regulator?" The invariant question is how low-energy parameters respond to actual heavy states or UV boundary conditions.

For example, if a light scalar couples to a heavy scalar of mass $M$, matching at the scale $M$ can generate a finite threshold correction of order

$$
\delta m^2\sim \frac{\lambda}{16\pi^2}M^2,
$$

up to scheme-dependent constants. That threshold sensitivity is not removed by choosing a regulator in which quadratic divergences are absent. The local counterterm language and the Wilsonian matching language are two ways of describing the same physical issue.

This is one reason scheme dependence must be handled with adult supervision. It removes fake arguments. It does not remove real physics.

## Common pitfalls

**Comparing couplings without converting schemes.** A value quoted in $\overline{\mathrm{MS}}$ is not the same object as a momentum-subtraction coupling or an on-shell coupling. They can be related, but they should not be identified.

**Calling a beta-function coefficient physical without checking assumptions.** Universal coefficients are universal within a stated class of schemes and normalizations. The statement is not automatically true for every coupling variable one can invent.

**Treating a fixed-point coordinate as observable.** The coordinate $g_*$ depends on the scheme. Critical exponents and scaling dimensions are the invariant data.

**Overinterpreting a fixed point in a truncated beta function.** Scheme changes can move a strong-coupling fixed point around. If the fixed point is outside the controlled expansion, its coordinate existence in one truncation is not decisive evidence.

**Forgetting operator-basis dependence.** An anomalous-dimension matrix is tied to an operator basis. Wilson coefficients and operators must be transformed together.

**Using scheme dependence as an excuse for sloppiness.** Since observables are scheme independent, a scheme-dependent intermediate result is not wrong. But an unstated scheme is incomplete.

## Relations to other pages

[Counterterm Schemes](/renormalization-rg-eft/renormalized-perturbation-theory/counterterm-schemes/) explains finite subtraction choices from the perturbative-renormalization viewpoint. This page explains the RG consequence: schemes are coordinates on coupling space.

[Minimal Subtraction](/renormalization-rg-eft/renormalized-perturbation-theory/minimal-subtraction/) and [$\overline{\mathrm{MS}}$ Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/msbar-scheme/) give the most common mass-independent schemes. [On-Shell Scheme](/renormalization-rg-eft/renormalized-perturbation-theory/on-shell-scheme/) gives a physically normalized alternative.

[Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/) defines beta functions. [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/) explains field and operator scaling. [Dimensional Transmutation](/renormalization-rg-eft/renormalization-group-equations/dimensional-transmutation/) uses scheme conversion to explain why a dynamically generated scale has a convention-dependent normalization but physical scale ratios are meaningful.

Later, [Matching](/renormalization-rg-eft/effective-field-theory/matching/) and [Threshold Corrections](/renormalization-rg-eft/matching-running-decoupling/threshold-corrections/) will show how scheme dependence is handled when moving between theories with different degrees of freedom.

## Research status

The conceptual point is settled: renormalization schemes are conventions, finite scheme changes are reparameterizations, and physical observables are invariant under consistent conversion.

The practical frontier is not the principle but the execution. Precision QCD, electroweak calculations, flavor EFTs, SMEFT anomalous dimensions, lattice-to-continuum matching, threshold masses, evanescent operators, and multi-scale resummations all require careful scheme bookkeeping. In these contexts, scheme dependence is not philosophical fluff. It is where hidden mistakes like to breed.

## Exercises

### Exercise 1: Transforming the beta function

Let $g'=f(g)$ be an invertible finite scheme change for a single coupling. Starting from $dg/d\log\mu=\beta(g)$, derive

$$
\beta'(g')=\frac{df}{dg}\beta(g).
$$

<details><summary><strong>Solution</strong></summary>

Differentiate $g'=f(g)$ along the RG trajectory:

$$
\frac{dg'}{d\log\mu}
=\frac{df}{dg}\frac{dg}{d\log\mu}
=\frac{df}{dg}\beta(g).
$$

By definition, the left-hand side is $\beta'(g')$. Since $g=f^{-1}(g')$, the transformed beta function can be written entirely as a function of $g'$:

$$
\beta'(g')=\left.\frac{df}{dg}\beta(g)\right|_{g=f^{-1}(g')}.
$$

</details>

### Exercise 2: Universal first two coefficients

Let

$$
\beta(g)=\beta_0g^3+\beta_1g^5+\beta_2g^7+O(g^9)
$$

and

$$
g'=g+a g^3+c g^5+O(g^7).
$$

Show that the coefficients of $g'^3$ and $g'^5$ in $\beta'(g')$ are $\beta_0$ and $\beta_1$.

<details><summary><strong>Solution</strong></summary>

First compute

$$
\frac{dg'}{dg}=1+3ag^2+5cg^4+O(g^6).
$$

Therefore

$$
\beta'(g')
=\left(1+3ag^2+5cg^4+\cdots\right)
\left(\beta_0g^3+\beta_1g^5+\beta_2g^7+\cdots\right).
$$

Through $g^5$ this is

$$
\beta'(g')=\beta_0g^3+(\beta_1+3a\beta_0)g^5+O(g^7).
$$

Now invert the scheme change to the needed order:

$$
g=g'-a g'^3+O(g'^5).
$$

Then

$$
g^3=g'^3-3a g'^5+O(g'^7),
\qquad
 g^5=g'^5+O(g'^7).
$$

Substituting gives

$$
\beta'(g')
=\beta_0(g'^3-3a g'^5)
+(\beta_1+3a\beta_0)g'^5+O(g'^7)
=\beta_0g'^3+\beta_1g'^5+O(g'^7).
$$

The $a$-dependent terms cancel.

</details>

### Exercise 3: Linearized eigenvalues at a fixed point

For several couplings, let $g'=f(g)$ and suppose $g_*$ is a fixed point. Show that the linearized RG matrices obey

$$
B'=J B J^{-1},
\qquad
J^i{}_j=\left.\frac{\partial f^i}{\partial g^j}\right|_{g_*}.
$$

<details><summary><strong>Solution</strong></summary>

Near the fixed point,

$$
\delta g'^i=J^i{}_j\delta g^j+O(\delta g^2).
$$

The original linearized flow is

$$
\frac{d\delta g}{d\log\mu}=B\delta g.
$$

Multiplying by $J$ gives

$$
\frac{d\delta g'}{d\log\mu}=J B\delta g.
$$

Since $\delta g=J^{-1}\delta g'$ to linear order,

$$
\frac{d\delta g'}{d\log\mu}=J B J^{-1}\delta g'.
$$

Thus $B'=JBJ^{-1}$. Similar matrices have the same eigenvalues, so the linearized RG eigenvalues are invariant under regular finite scheme changes.

</details>

### Exercise 4: Scheme change of a perturbative observable

Suppose

$$
F=g^2+A g^4+O(g^6),
\qquad
 g'=g+a g^3+O(g^5).
$$

Write $F$ through order $g'^4$ in the primed scheme.

<details><summary><strong>Solution</strong></summary>

Invert the coupling redefinition:

$$
g=g'-a g'^3+O(g'^5).
$$

Then

$$
g^2=g'^2-2a g'^4+O(g'^6),
\qquad
 g^4=g'^4+O(g'^6).
$$

Therefore

$$
F=g'^2+(A-2a)g'^4+O(g'^6).
$$

The coefficient $A$ changes to $A'=A-2a$. The observable $F$ is unchanged; only its coordinate expansion changed.

</details>

## References

- Sidney Coleman, "Dilatations" and "Asymptotic Freedom" in *Aspects of Symmetry*, for the physics of scale transformations, anomalous dimensions, and RG equations.
- Mark Srednicki, *Quantum Field Theory*, especially the sections on other renormalization schemes, the renormalization group, and effective field theory.
- Matthew D. Schwartz, *Quantum Field Theory and the Standard Model*, chapter 23, for a modern discussion of running couplings and scheme choices in perturbative QFT.
- Steven Weinberg, *The Quantum Theory of Fields*, Vol. II, chapter 18, for renormalization group methods, scheme changes, fixed points, and mass effects.
- Kenneth G. Wilson and J. Kogut, "The Renormalization Group and the $\epsilon$ Expansion," *Physics Reports* **12** (1974) 75–200, for the Wilsonian perspective on fixed points, trajectories, and universality.
- Jean Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for detailed scheme-aware treatments of renormalization, RG equations, critical exponents, and operator mixing.

## Version history

- 2026-06-17: First polished draft. Added beta-function covariance, finite coupling redefinitions, fixed-point invariants, anomalous-dimension scheme dependence, mass-dependent schemes, practical truncation caveats, and exercises with solutions.
