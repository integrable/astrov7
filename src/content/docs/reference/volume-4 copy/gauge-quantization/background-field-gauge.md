---
title: "Background-Field Gauge"
description: "Explains the background-field method for Yang–Mills theory, the background-covariant gauge condition, and why it streamlines gauge-theory renormalization."
sidebar:
  label: "Background-Field Gauge"
  order: 6
level: Graduate
status: "Polished draft"
source: "Srednicki §78; Weinberg Vol. II §§17.4–17.5; Schwartz Ch. 34; standard background-field method for Yang–Mills theory."
topics:
  - background-field method
  - background-field gauge
  - gauge fixing
  - effective action
  - Yang–Mills renormalization
  - beta functions
canonicalTopics:
  - background-field-gauge
  - background-field-method
  - gauge-fixed-effective-action
  - background-gauge-invariance
  - gauge-theory-renormalization
researchStatus:
  established:
    - "Background-field gauge is a standard perturbative method that preserves manifest gauge invariance with respect to a background connection and greatly simplifies the organization of gauge-theory counterterms."
  active:
    - "Background-field ideas remain important in effective actions, heat-kernel methods, curved-space QFT, lattice improvement, functional RG, and modern treatments of gauge theories with boundaries or nontrivial topology."
---

## Summary

Background-field gauge is a clever way to gauge-fix Yang–Mills theory without throwing away all visible gauge covariance. Instead of expanding directly around $A_\mu=0$, we split the gauge field into a background connection and a quantum fluctuation,

$$
A_\mu=\bar A_\mu+a_\mu.
$$

The quantum field $a_\mu$ is integrated over in the path integral. The background field $\bar A_\mu$ is kept as an external argument of the effective action. The gauge condition is chosen to be covariant with respect to the background connection:

$$
G^a[a;\bar A]=(\bar D^\mu a_\mu)^a=0.
$$

Here

$$
(\bar D_\mu X)^a
=\partial_\mu X^a-gf^{abc}\bar A_\mu^bX^c
$$

is the adjoint covariant derivative built from the background field.

The reward is that the effective action $\Gamma[\bar A]$ is invariant under background gauge transformations:

$$
\boxed{
\Gamma[\bar A^U]=\Gamma[\bar A].
}
$$

This is the whole trick. Ordinary covariant gauge fixing obscures gauge invariance and then BRST symmetry has to do a lot of bookkeeping. Background-field gauge keeps enough gauge covariance manifest that the divergent part of $\Gamma[\bar A]$ must be built from gauge-invariant operators such as $\bar F_{\mu\nu}^a\bar F^{a\mu\nu}$. That is why it is the cleanest route to the Yang–Mills beta function.

<figure class="doc-figure" style="--figure-width: 44rem;">

![Background-field gauge splits the gauge field into a background connection and a quantum fluctuation, fixes only the quantum gauge redundancy, and preserves background gauge invariance.](/figures/gauge-theories-standard-model/background-field-gauge-flow.svg)

<figcaption>

Background-field gauge separates two roles of the gauge field. The quantum redundancy is fixed by the background-covariant condition $\bar D^\mu a_\mu=0$, while background gauge covariance remains manifest. The resulting effective action $\Gamma[\bar A]$ obeys a background Ward identity, forcing its counterterms to be gauge-invariant functions of $\bar F_{\mu\nu}$.

</figcaption>
</figure>

## Prerequisites

You should have read [Gauge Fixing and Faddeev–Popov](/gauge-theories-standard-model/gauge-quantization/gauge-fixing-and-faddeev-popov/), [Ghosts and Gauge-Fixed Action](/gauge-theories-standard-model/gauge-quantization/ghosts-and-gauge-fixed-action/), [BRST Symmetry in Gauge Theory](/gauge-theories-standard-model/gauge-quantization/brst-symmetry-in-gauge-theory/), and [Covariant Gauges](/gauge-theories-standard-model/gauge-quantization/covariant-gauges/).

We use the volume convention

$$
D_\mu=\partial_\mu+igA_\mu^aT^a,
\qquad
(D_\mu X)^a=\partial_\mu X^a-gf^{abc}A_\mu^bX^c
$$

for an adjoint field $X^a$. The curvature is defined by

$$
[D_\mu,D_\nu]=igF_{\mu\nu}^aT^a,
$$

so

$$
F_{\mu\nu}^a
=
\partial_\mu A_\nu^a-
\partial_\nu A_\mu^a
-gf^{abc}A_\mu^bA_\nu^c.
$$

## Core idea

Gauge fixing usually creates an awkward tension. We need gauge fixing to invert the kinetic operator, but the gauge-fixing term is not gauge invariant. In an ordinary Lorenz-type covariant gauge we add

$$
-\frac{1}{2\xi}(\partial^\mu A_\mu^a)^2,
$$

which makes the propagator well defined but hides the original gauge invariance of the Yang–Mills action. The final physics is still gauge invariant, but the intermediate Green functions are not.

Background-field gauge changes the bookkeeping. It introduces a background connection $\bar A_\mu$ and fixes only the gauge redundancy of the quantum fluctuation $a_\mu$. The gauge-fixing term is not invariant under arbitrary quantum gauge transformations, because it is meant to fix them. But it is invariant under background gauge transformations, under which $\bar A_\mu$ transforms as a connection and $a_\mu$ transforms homogeneously.

The method therefore separates two statements that are easy to blur:

| Statement | What happens in background-field gauge |
|---|---|
| Quantum gauge redundancy | Fixed by $G^a=(\bar D^\mu a_\mu)^a$. |
| Background gauge covariance | Kept manifest in $\Gamma[\bar A]$. |
| Propagators and vertices | Depend on the quantum gauge parameter $\xi$. |
| Effective-action counterterms | Must be invariant under background gauge transformations. |
| Physical predictions | Independent of the gauge-fixing choice when BRST symmetry is anomaly-free. |

So background-field gauge is not a new theory. It is a gauge-fixing scheme designed to make the symmetry constraints on renormalization obvious.

## Setup and conventions

Let the full gauge connection be

$$
A_\mu=A_\mu^aT^a,
$$

with Hermitian generators obeying

$$
[T^a,T^b]=if^{abc}T^c.
$$

We split

$$
A_\mu=\bar A_\mu+a_\mu,
$$

where $\bar A_\mu$ is arbitrary. It need not solve the classical equations of motion. It can be a slowly varying field, a constant field strength, an instanton background, a source for the effective action, or simply a formal device that will be set to zero after differentiating.

The background covariant derivative on adjoint fields is

$$
(\bar D_\mu X)^a
=\partial_\mu X^a-gf^{abc}\bar A_\mu^bX^c.
$$

The full covariant derivative is

$$
(D_\mu[A]X)^a
=\partial_\mu X^a-gf^{abc}(\bar A_\mu^b+a_\mu^b)X^c.
$$

The Yang–Mills action is still the original action evaluated on the sum:

$$
S_{\rm YM}[\bar A+a]
=
\int d^4x\,
\left[-\frac14F_{\mu\nu}^a[\bar A+a]F^{a\mu\nu}[\bar A+a]\right].
$$

The background-field path integral defines a functional of $\bar A$:

$$
\exp\{i\Gamma[\bar A]\}
=
\int\mathcal Da\,\mathcal D\bar c\,\mathcal Dc\,
\exp\left\{iS_{\rm BFG}[\bar A,a,\bar c,c]\right\},
$$

with sources and Legendre transforms included when one wants the full effective action rather than the one-loop version. For most uses in perturbative renormalization, this schematic expression is enough: integrate over quantum fluctuations, keep the background field as the object whose gauge-invariant effective action is being computed.

## Two transformations after the split

The split $A_\mu=\bar A_\mu+a_\mu$ creates two useful transformation laws.

First, there are **background gauge transformations**. These transform $\bar A_\mu$ like a connection and $a_\mu$ like an adjoint tensor:

$$
\bar A_\mu
\mapsto
U^{-1}\bar A_\mu U-\frac{i}{g}U^{-1}\partial_\mu U,
\qquad
 a_\mu\mapsto U^{-1}a_\mu U.
$$

The sum $\bar A_\mu+a_\mu$ therefore transforms like a genuine connection:

$$
\bar A_\mu+a_\mu
\mapsto
U^{-1}(\bar A_\mu+a_\mu)U-\frac{i}{g}U^{-1}\partial_\mu U.
$$

Second, there are **quantum gauge transformations**. These hold $\bar A_\mu$ fixed and transform the full field $A_\mu=\bar A_\mu+a_\mu$. Infinitesimally,

$$
\delta_{\rm q}\bar A_\mu^a=0,
\qquad
\delta_{\rm q}a_\mu^a=(D_\mu[A]\alpha)^a.
$$

The quantum transformations are the redundant directions that must be gauge-fixed in the path integral. The background transformations are kept visible.

This distinction is bookkeeping, not new physics. The original theory had one gauge redundancy. The split lets us fix it while preserving a useful covariance property of the background functional.

## The background-covariant gauge condition

The background-field version of Lorenz gauge is

$$
G^a[a;\bar A]
=(\bar D^\mu a_\mu)^a.
$$

Under a background gauge transformation, $G^a$ transforms in the adjoint representation. Therefore the quadratic gauge-fixing term

$$
\mathcal L_{\rm gf}
=
-\frac{1}{2\xi}G^aG^a
=
-\frac{1}{2\xi}(\bar D^\mu a_\mu)^a(\bar D^\nu a_\nu)^a
$$

is invariant under background gauge transformations.

The Faddeev–Popov operator is obtained by varying $G^a$ under quantum gauge transformations:

$$
M^{ab}[\bar A,a]
=
\frac{\delta G^a[a^\alpha;\bar A]}{\delta\alpha^b}\bigg|_{\alpha=0}
=
\bar D^{\mu ac}D_\mu^{cb}[\bar A+a].
$$

Thus the ghost Lagrangian is

$$
\mathcal L_{\rm gh}
=
-\bar c^a\bar D^{\mu ac}D_\mu^{cb}[\bar A+a]c^b.
$$

The complete gauge-fixed background-field Lagrangian is

$$
\boxed{
\mathcal L_{\rm BFG}
=
-
\frac14F_{\mu\nu}^a[\bar A+a]F^{a\mu\nu}[\bar A+a]
-
\frac{1}{2\xi}(\bar D^\mu a_\mu)^a(\bar D^\nu a_\nu)^a
-
\bar c^a\bar D^{\mu ac}D_\mu^{cb}[\bar A+a]c^b.
}
$$

Matter fields can be included in the same way. One either splits matter fields into background and quantum parts, or sets the matter background to zero and integrates over matter quantum fluctuations in the presence of $\bar A_\mu$.

## What the gauge-fixed action buys you

The defining virtue of the construction is that $\mathcal L_{\rm BFG}$ is invariant under background gauge transformations if all quantum fields transform homogeneously in their representations:

$$
a_\mu\mapsto U^{-1}a_\mu U,
\qquad
c\mapsto U^{-1}cU,
\qquad
\bar c\mapsto U^{-1}\bar cU.
$$

Therefore the functional integral over $a,c,\bar c$ produces a background-gauge-invariant effective action:

$$
\Gamma[\bar A^U]=\Gamma[\bar A].
$$

This is a Ward identity for the background effective action. Infinitesimally it says, schematically,

$$
\bar D_\mu^{ab}\frac{\delta\Gamma}{\delta \bar A_\mu^b}=0.
$$

That identity is much simpler than the Slavnov–Taylor identities for ordinary gauge-fixed Green functions. It does not replace BRST symmetry; rather, it is a visible consequence of the special gauge choice.

## Quadratic operator and background Feynman gauge

For one-loop calculations, expand the action to quadratic order in the quantum field $a_\mu$. Up to integrations by parts and the usual $+i\epsilon$ prescription, the quadratic gauge-field term has the form

$$
\mathcal L_2
=
\frac12a_\mu^a
\left[
\eta^{\mu\nu}(\bar D^2)^{ab}
-
\left(1-\frac1\xi\right)(\bar D^\mu\bar D^\nu)^{ab}
-
2g f^{acb}\bar F^{c\mu\nu}
\right]
 a_\nu^b.
$$

The ghost quadratic term is

$$
\mathcal L_{{\rm gh},2}
=
-\bar c^a(\bar D^2)^{ab}c^b.
$$

The especially convenient choice is **background Feynman gauge**,

$$
\xi=1.
$$

Then the nonminimal $\bar D^\mu\bar D^\nu$ term disappears, and the gauge-field operator is of Laplace type plus a spin-curvature coupling:

$$
\Delta_{1,\mu\nu}^{ab}
\sim
\eta_{\mu\nu}(\bar D^2)^{ab}
-
2g f^{acb}\bar F_{\mu\nu}^c.
$$

The ghost operator is the scalar adjoint covariant Laplacian,

$$
\Delta_0^{ab}
\sim
(\bar D^2)^{ab}.
$$

This is why background-field gauge plays so well with heat-kernel methods and determinant calculations. The one-loop effective action has the schematic form

$$
\Gamma^{(1)}[\bar A]
=
\frac{i}{2}\operatorname{Tr}\log\Delta_1
-i\operatorname{Tr}\log\Delta_0
+\text{matter determinants},
$$

where the factor $1/2$ is for bosonic gauge fluctuations and the minus sign is the ghost sign. The divergent part must be a local background-gauge-invariant functional.

## Why this simplifies renormalization

In ordinary covariant gauges, the counterterm analysis is governed by BRST symmetry and Slavnov–Taylor identities. That is correct but technically heavy. In background-field gauge, the effective action $\Gamma[\bar A]$ is explicitly invariant under background gauge transformations, so the allowed divergent terms are highly constrained.

In four dimensions, the leading gauge-field counterterm has the form

$$
\Gamma_{\rm div}[\bar A]
\supset
C_{\rm div}
\int d^4x\,
\left(-\frac14\bar F_{\mu\nu}^a\bar F^{a\mu\nu}\right),
$$

plus gauge-invariant matter terms and possible higher-dimension terms if the theory is treated as an EFT. There is no separate arbitrary counterterm for every noncovariant tensor structure that appeared in intermediate propagators.

The background Ward identity also relates the renormalization of the background field to the renormalization of the gauge coupling. If

$$
\bar A_{0\mu}=Z_{\bar A}^{1/2}\bar A_\mu,
\qquad
 g_0=Z_g g,
$$

then background gauge invariance gives the important relation

$$
\boxed{
Z_g Z_{\bar A}^{1/2}=1.
}
$$

In words: once the background-field two-point function is renormalized, the gauge-coupling renormalization is fixed. This is the practical reason the background-field method is such an efficient beta-function machine.

## One-loop beta-function logic

For a simple gauge group with Dirac fermions and complex scalars in representations $R_f$ and $R_s$, the one-loop gauge beta function has the structure

$$
\beta(g)
\equiv
\mu\frac{dg}{d\mu}
=
-
\frac{g^3}{16\pi^2}
\left[
\frac{11}{3}C_A
-
\frac{4}{3}\sum_f T(R_f)
-
\frac{1}{3}\sum_s T(R_s)
\right]
+
O(g^5).
$$

Here $C_A$ is the quadratic Casimir of the adjoint representation and $T(R)$ is the Dynkin index,

$$
\operatorname{tr}_R(T^aT^b)=T(R)\delta^{ab}.
$$

This page is not deriving that coefficient yet; the later beta-function page does the calculation. The point here is the organization. In background-field gauge, the divergent part of the one-loop determinant is proportional to

$$
\int d^4x\,\bar F_{\mu\nu}^a\bar F^{a\mu\nu},
$$

so extracting the beta function is reduced to finding the coefficient of one background-gauge-invariant operator. The famous $11C_A/3$ comes from the competition between gauge-boson fluctuations and ghosts. Matter fields screen; pure Yang–Mills anti-screens.

## Background-field gauge versus ordinary gauges

The following comparison is a useful sanity check.

| Feature | Ordinary covariant gauge | Background-field gauge |
|---|---|---|
| Gauge condition | $\partial^\mu A_\mu^a=0$ | $(\bar D^\mu a_\mu)^a=0$ |
| Field integrated over | $A_\mu$ | $a_\mu$ |
| External gauge-covariant object | Not manifest | $\bar A_\mu$ |
| Effective action | Gauge-fixed Green functions obey Slavnov–Taylor identities | $\Gamma[\bar A]$ is background gauge invariant |
| Best use | General perturbative amplitudes | Counterterms, beta functions, effective actions |
| Physical content | Same theory | Same theory |

If the background is set to zero, $\bar A_\mu=0$, the gauge condition reduces to the usual Lorenz condition $\partial^\mu a_\mu^a=0$. But this limit hides the main point. The usefulness of the method comes from keeping $\bar A_\mu$ nonzero long enough to constrain the answer.

## What the method does not say

Background-field gauge is powerful, but it is not magic.

It does not make every off-shell quantum Green function gauge independent. The effective action $\Gamma[\bar A]$ is background gauge invariant, but it can still depend on the quantum gauge parameter $\xi$ away from physical quantities or special constructions.

It does not remove the need for ghosts. In fact, the ghost operator is central:

$$
M=\bar D^\mu D_\mu[\bar A+a].
$$

It does not solve global gauge-fixing problems. The Gribov problem and nonperturbative gauge copies remain. Background-field gauge is a local perturbative tool unless extra nonperturbative structure is supplied.

It does not mean the background field is physically classical. The background is a source-like argument of the effective action. A stationary point of $\Gamma[\bar A]$ can describe a quantum-corrected classical field configuration, but an arbitrary $\bar A_\mu$ is just a useful bookkeeper.

## Common pitfalls

**Confusing background gauge transformations with quantum gauge transformations.** Background transformations are kept manifest. Quantum transformations are fixed. If those roles are mixed, the method looks paradoxical.

**Thinking $\bar A_\mu$ must solve the equations of motion.** It need not. The effective action is a functional of arbitrary background fields. Equations of motion come after varying $\Gamma[\bar A]$.

**Forgetting that ghosts still interact.** The background-covariant ghost operator contains both $\bar A_\mu$ and $a_\mu$. Ghosts contribute to the one-loop determinant and to perturbative diagrams.

**Assuming background gauge invariance means all quantities are physical.** Background-gauge-invariant off-shell functionals are useful, but physical observables require the usual care with gauge-invariant operators, S-matrix elements, or properly defined effective-action quantities.

**Using ordinary Ward identities where Slavnov–Taylor identities are needed.** The background effective action obeys simple background Ward identities. Ordinary quantum Green functions still obey BRST/Slavnov–Taylor identities.

**Losing the sign convention in $D_\mu$.** With the convention of this volume, adjoint derivatives act as $(D_\mu X)^a=\partial_\mu X^a-gf^{abc}A_\mu^bX^c$. If a source uses $D_\mu=\partial_\mu-igA_\mu^aT^a$, the sign of the non-Abelian term must be translated.

## Relations to other pages

This page completes the quantization chapter’s first pass. [Covariant Gauges](/gauge-theories-standard-model/gauge-quantization/covariant-gauges/) introduced the one-parameter gauge family for ordinary perturbative calculations. Background-field gauge is a special covariant family adapted to effective actions and renormalization.

The next chapter, [Renormalization of Gauge Theories](/gauge-theories-standard-model/gauge-renormalization/), uses this page as a bridge. The pages on gauge-invariant counterterms and the Yang–Mills beta function rely on the fact that background-field gauge makes the gauge-invariant structure of divergences visible.

For a deeper symmetry perspective, compare this page with BRST cohomology in the Symmetry, Anomalies, and Topology volume. For nonperturbative limitations, compare it with the Gribov-problem and confinement pages in the Nonperturbative QFT volume.

## Research status

The background-field method is established and widely used in perturbative gauge theory, effective actions, beta-function computations, and heat-kernel calculations. Its conceptual status is clean in perturbation theory: it is a gauge-fixing method that preserves background gauge covariance.

Active uses and refinements appear in functional RG, gauge theories on curved spaces, supersymmetric localization, higher-loop beta-function computations, effective field theory matching, and gauge theories with boundaries. The main caveat is nonperturbative: no local gauge condition, background-field or otherwise, globally solves the gauge-orbit problem in all Yang–Mills field space.

## Exercises

1. **Background covariance of the gauge condition.** Show that if $a_\mu\mapsto U^{-1}a_\mu U$ and $\bar D_\mu\mapsto U^{-1}\bar D_\mu U$, then $G=\bar D^\mu a_\mu$ transforms as $G\mapsto U^{-1}GU$.

<details><summary><strong>Solution</strong></summary>

Use the defining covariance of the background covariant derivative. For any adjoint field $X$ transforming as $X\mapsto U^{-1}XU$, one has

$$
\bar D_\mu^U X^U
=
U^{-1}(\bar D_\mu X)U.
$$

Setting $X=a_\mu$ and contracting the spacetime index gives

$$
G^U
=(\bar D^{U\mu}a_\mu^U)
=
U^{-1}(\bar D^\mu a_\mu)U
=U^{-1}GU.
$$

Therefore $G^aG^a$, equivalently $\operatorname{tr}G^2$, is invariant.

</details>

2. **Faddeev–Popov operator.** Starting from $G^a=(\bar D^\mu a_\mu)^a$ and the quantum transformation $\delta_{\rm q}a_\mu^a=(D_\mu[\bar A+a]\alpha)^a$, derive

$$
M^{ab}=\bar D^{\mu ac}D_\mu^{cb}[\bar A+a].
$$

<details><summary><strong>Solution</strong></summary>

Since the background field is fixed under quantum transformations,

$$
\delta_{\rm q}G^a
=
\bar D^{\mu ab}\delta_{\rm q}a_\mu^b.
$$

Using

$$
\delta_{\rm q}a_\mu^b
=
D_\mu^{bc}[\bar A+a]\alpha^c,
$$

we find

$$
\delta_{\rm q}G^a
=
\bar D^{\mu ab}D_\mu^{bc}[\bar A+a]\alpha^c.
$$

Thus

$$
M^{ac}
=
\frac{\delta G^a}{\delta\alpha^c}
=
\bar D^{\mu ab}D_\mu^{bc}[\bar A+a].
$$

Relabeling dummy indices gives the advertised formula.

</details>

3. **Why the counterterm is constrained.** In four-dimensional pure Yang–Mills theory, use dimensional analysis and background gauge invariance to argue that the logarithmic divergence in $\Gamma[\bar A]$ at order $\bar F^2$ must be proportional to $\int d^4x\,\bar F_{\mu\nu}^a\bar F^{a\mu\nu}$.

<details><summary><strong>Solution</strong></summary>

The divergent part of the effective action must be local. In four dimensions, $[d^4x]=-4$ and $[\bar F_{\mu\nu}]=2$, so a dimension-four gauge-field counterterm quadratic in the curvature has the form

$$
\int d^4x\,\bar F\bar F.
$$

Background gauge invariance requires color indices to be contracted invariantly. For a simple gauge group at this order, the invariant contraction is proportional to

$$
\bar F_{\mu\nu}^a\bar F^{a\mu\nu},
$$

up to the topological density $\bar F_{\mu\nu}^a\tilde{\bar F}^{a\mu\nu}$, which has different parity properties and is not generated as the ordinary kinetic counterterm in a parity-preserving Yang–Mills theory. Therefore the kinetic divergence has the stated form.

</details>

4. **Renormalization identity.** Explain why the combination $g\bar A_\mu$ suggests $Z_gZ_{\bar A}^{1/2}=1$ in background-field gauge.

<details><summary><strong>Solution</strong></summary>

The background covariant derivative contains the combination

$$
\bar D_\mu=\partial_\mu+ig\bar A_\mu^aT^a
$$

in the representation acting on matter, or the corresponding adjoint form. Background gauge transformations also contain $1/g$ in the inhomogeneous part of $\bar A_\mu^U$. For the renormalized background covariant derivative and transformation law to keep the same form after writing

$$
\bar A_{0\mu}=Z_{\bar A}^{1/2}\bar A_\mu,
\qquad
 g_0=Z_g g,
$$

the product $g_0\bar A_{0\mu}$ must renormalize like $g\bar A_\mu$. Hence

$$
Z_gZ_{\bar A}^{1/2}=1.
$$

This is the background-field Ward identity in its most useful renormalization form.

</details>

## References

- Srednicki, *Quantum Field Theory*, §78, for background-field gauge as a tool for non-Abelian gauge theory and beta-function calculations.
- Weinberg, *The Quantum Theory of Fields*, Vol. II, §§17.4–17.5, for background-field gauge and the one-loop calculation in background-field language.
- Schwartz, *Quantum Field Theory and the Standard Model*, Ch. 34, for background fields and effective-action methods.
- Abbott, “The Background Field Method Beyond One Loop,” for the classic perturbative formulation of the background-field method.
- DeWitt, *The Global Approach to Quantum Field Theory*, for the geometric background-field perspective.

## Version history

- **2026-06-18:** Initial polished draft for the Gauge Theories and the Standard Model volume.
