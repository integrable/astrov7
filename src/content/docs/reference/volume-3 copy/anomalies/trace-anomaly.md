---
title: "Trace Anomaly"
description: "Explains the trace or Weyl anomaly, its relation to running couplings and curved-space response, and how it differs from gravitational anomalies."
sidebar:
  label: "Trace Anomaly"
  order: 10
level: Advanced
status: "Polished draft"
source: "Callan–Symanzik and Coleman–Jackiw scale-current viewpoints; Duff and Deser–Schwimmer Weyl-anomaly classifications; Srednicki, Schwartz, Coleman, Weinberg, and standard CFT references."
topics:
  - trace anomaly
  - Weyl anomaly
  - scale anomaly
  - beta function
  - stress tensor
  - conformal anomaly
  - curved background
  - central charge
canonicalTopics:
  - trace-anomaly
  - weyl-anomaly
  - conformal-anomaly
  - stress-tensor-trace
  - beta-function
researchStatus:
  established:
    - "The trace anomaly is the quantum failure of scale or local Weyl invariance, often controlled in flat space by beta functions and anomalous dimensions."
    - "In curved space, Weyl anomalies are local curvature and background-field terms in the trace Ward identity, with scheme-independent and scheme-dependent parts."
  active:
    - "Trace anomalies remain central in modern work on RG monotonicity, conformal manifolds, dilaton effective actions, entanglement, curved-space QFT, and anomaly inflow for scale or Weyl symmetry."
---

## Summary

The **trace anomaly** is the statement that the quantum stress tensor can have a nonzero trace even when the classical theory appears scale invariant or Weyl invariant.

In flat space, the diagnostic is usually

$$
T^\mu{}_{\mu}\ne0.
$$

For a renormalized theory with dimensionless couplings $\lambda^i$, a schematic and extremely useful form is

$$
T^\mu{}_{\mu}=\sum_i \beta^i(\lambda)\,\mathcal O_i
+\text{explicit breaking}
+\text{equation-of-motion and improvement terms}.
$$

The slogan is:

$$
\text{running couplings are the flat-space trace anomaly.}
$$

That slogan is not the whole story. In curved space, even a genuine conformal field theory with all beta functions zero may have a local Weyl anomaly,

$$
\langle T^\mu{}_{\mu}\rangle=\mathcal A_{\rm Weyl}[g,A,\ldots],
$$

built from curvature tensors and background-field strengths.

<figure class="doc-figure" style="--figure-width: 58rem;">

![Flowchart from classical scale or Weyl symmetry through regulator and subtraction scale to running couplings, curved-space Weyl terms, and the trace Ward identity.](/figures/symmetry-anomalies-topology/trace-anomaly-rg-map.svg)

<figcaption>

A trace anomaly has two common faces. In flat space it is tied to RG running, $T^\mu{}_{\mu}\sim\beta^i\mathcal O_i$. In curved space it also contains local Weyl-response terms such as $aE_4$, $cW^2$, $\nabla^2R$, and background-field contributions. It is not a diffeomorphism anomaly.

</figcaption>
</figure>

The trace anomaly is sometimes called the **scale anomaly**, **Weyl anomaly**, or **conformal anomaly**. These names overlap but are not identical. “Scale anomaly” emphasizes constant rescalings. “Weyl anomaly” emphasizes local rescalings of a background metric. “Conformal anomaly” is common but can be slightly misleading: in flat space, conformal symmetry may fail because the trace is nonzero; in curved space, the anomaly can survive even for a perfectly good CFT.

## Prerequisites

Read [What Is an Anomaly?](/symmetry-anomalies-topology/anomalies/what-is-an-anomaly/), [Regulator and Measure Viewpoints](/symmetry-anomalies-topology/anomalies/regulator-and-measure-viewpoints/), [Gravitational Anomalies](/symmetry-anomalies-topology/anomalies/gravitational-anomalies/), and [Mixed Anomalies](/symmetry-anomalies-topology/anomalies/mixed-anomalies/) first.

You should also know the stress-tensor convention

$$
\delta W[g]=\frac12\int d^dx\sqrt{|g|}\,\langle T^{\mu\nu}\rangle\delta g_{\mu\nu},
$$

and the background-field principle: a symmetry is tested by coupling to its source and asking whether the generating functional can be made invariant under source transformations.

## Core idea

A classical field theory may be invariant under scale transformations,

$$
x^\mu\mapsto e^{-\sigma}x^\mu,
\qquad
\phi(x)\mapsto e^{\Delta\sigma}\phi(e^{\sigma}x),
$$

or, after coupling to a background metric, under local Weyl transformations,

$$
g_{\mu\nu}(x)\mapsto e^{2\sigma(x)}g_{\mu\nu}(x).
$$

The Noether current for scale transformations is the dilatation current,

$$
D^\mu=x_\nu T^{\mu\nu}+V^\mu,
$$

where $V^\mu$ is a possible virial current. Its divergence is

$$
\partial_\mu D^\mu=T^\mu{}_{\mu}+\partial_\mu V^\mu.
$$

If the stress tensor can be improved so that $V^\mu$ is removed, scale invariance implies

$$
T^\mu{}_{\mu}=0.
$$

Quantum mechanically, renormalization introduces a scale $\mu$. Dimensionless couplings become running couplings,

$$
\mu\frac{d\lambda^i}{d\mu}=\beta^i(\lambda),
$$

and the trace becomes the local operator that measures this running:

$$
T^\mu{}_{\mu}=\sum_i\beta^i\mathcal O_i+\text{other allowed terms}.
$$

The trace anomaly is therefore not a mysterious extra term glued onto the theory. It is the local Ward-identity form of the fact that the quantum theory knows about scales.

## Setup and conventions

We use the volume convention for the stress tensor,

$$
\delta W[g]=\frac12\int d^dx\sqrt{|g|}\,\langle T^{\mu\nu}\rangle\delta g_{\mu\nu}.
$$

For an infinitesimal Weyl transformation,

$$
\delta_\sigma g_{\mu\nu}=2\sigma g_{\mu\nu},
$$

so

$$
\delta_\sigma W[g]
=\int d^dx\sqrt{|g|}\,\sigma\,\langle T^\mu{}_{\mu}\rangle.
$$

A Weyl anomaly is a nonzero local expression

$$
\delta_\sigma W[g,A,\lambda]
=\int d^dx\sqrt{|g|}\,\sigma\,\mathcal A_{\rm Weyl}[g,A,\lambda].
$$

When the theory is written in terms of a renormalized Lagrangian

$$
\mathcal L=\sum_i\lambda^i\mathcal O_i,
$$

a compact flat-space trace formula is

$$
T^\mu{}_{\mu}=\sum_i\beta^i\mathcal O_i+\text{mass terms}+\text{improvement terms}.
$$

This formula is schematic because composite operators mix under renormalization. A precise formula requires a renormalization scheme and a basis of renormalized operators.

:::note[Convention-sensitive source note]
Trace-anomaly coefficients are especially sensitive to normalization choices. Compare whether the gauge kinetic term is written as $-\frac14F^a_{\mu\nu}F^{a\mu\nu}$ with $g$ in $F$, or as $-\frac{1}{4g^2}F^a_{\mu\nu}F^{a\mu\nu}$ with $g$ outside. Also compare Lorentzian versus Euclidean definitions of $W$, the sign of $T_{\mu\nu}$ from metric variation, and whether curvature tensors use the same sign convention.
:::

## Scale transformations and Weyl transformations

Scale invariance and Weyl invariance are related but not identical.

A **global scale transformation** rescales all lengths by a constant. In flat space this is generated by the dilatation charge. Its Ward identity is controlled by the divergence of $D^\mu$.

A **Weyl transformation** rescales the metric locally,

$$
g_{\mu\nu}(x)\to e^{2\sigma(x)}g_{\mu\nu}(x),
$$

while leaving coordinates fixed. It is a source transformation, not a coordinate transformation.

A **conformal transformation** in flat space is a coordinate transformation plus a compensating local rescaling that preserves the metric up to a Weyl factor.

The differences matter because a flat-space theory may be scale invariant without being obviously conformal if the virial current cannot be improved away. Also, a CFT in flat space may have

$$
T^\mu{}_{\mu}=0
$$

as an operator statement in flat space, while still having a nonzero Weyl anomaly on curved backgrounds.

The practical hierarchy is:

$$
\text{Weyl-invariant curved-space theory}
\Longrightarrow
\text{conformal flat-space theory}
\Longrightarrow
\text{scale-invariant flat-space theory},
$$

but the converses require assumptions.

## Flat-space trace anomaly from the RG

Consider a renormalized generating functional in flat space. It depends on momenta, couplings, and the renormalization scale,

$$
W=W[p,\lambda(\mu),\mu].
$$

Physical quantities cannot depend on the arbitrary choice of $\mu$. This gives the RG equation

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial\lambda^i}
+\text{field and source anomalous-dimension terms}
\right)W=0.
$$

A scale transformation changes all physical momenta. To compensate it, the couplings must run. The local form of this statement is the trace Ward identity,

$$
\langle T^\mu{}_{\mu}\rangle
=\sum_i\beta^i\langle\mathcal O_i\rangle+\text{contact terms}.
$$

For a correlation function of renormalized local operators,

$$
G_n(x_1,\ldots,x_n)=\langle\mathcal O_1(x_1)\cdots\mathcal O_n(x_n)\rangle,
$$

the integrated trace insertion generates the Callan–Symanzik equation. Roughly,

$$
\int d^dx\,\langle T^\mu{}_{\mu}(x)\mathcal O_1\cdots\mathcal O_n\rangle
$$

is the operator version of

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial\lambda^i}
+\sum_r\gamma_r
\right)G_n=0.
$$

The trace anomaly is therefore the local insertion behind the RG equation.

## Gauge-theory example

A classically massless Yang–Mills theory has no dimensionful parameter. Quantum mechanically the coupling runs. In the convention

$$
\mathcal L_{\rm YM}=-\frac{1}{4g^2}\operatorname{tr}F_{\mu\nu}F^{\mu\nu},
$$

with $F$ defined without an explicit $g$, the gauge contribution to the trace has the schematic form

$$
T^\mu{}_{\mu}
=\frac{\beta(g)}{2g^3}\operatorname{tr}F_{\rho\sigma}F^{\rho\sigma}+\cdots.
$$

If instead the Lagrangian is written as

$$
\mathcal L_{\rm YM}=-\frac14F^a_{\mu\nu}F^{a\mu\nu},
$$

with $g$ inside the nonabelian field strength, the same statement is often written as

$$
T^\mu{}_{\mu}
=\frac{\beta(g)}{2g}F^a_{\rho\sigma}F^{a\rho\sigma}+\cdots.
$$

These are the same physics after the field normalization is translated.

For QCD with quark masses, one also has explicit breaking:

$$
T^\mu{}_{\mu}
=\frac{\beta(g)}{2g}F^a_{\rho\sigma}F^{a\rho\sigma}
+\sum_q (1+\gamma_{m_q})m_q\bar q q+\text{scheme-dependent improvement terms}.
$$

Here $\gamma_{m_q}$ follows the common convention $\gamma_m=-\mu\,d\ln m/d\mu$; other sign conventions move the sign in this term. In the massless theory, the trace is still nonzero if $\beta(g)\ne0$. This is one way to say that dimensional transmutation has occurred: a dimensionless bare coupling has been traded for a physical scale such as $\Lambda_{\rm QCD}$.

## Explicit breaking versus anomalous breaking

The trace can be nonzero for several reasons. Do not put them all in the same mental bucket.

| Source of nonzero trace | Example | Meaning |
|---|---|---|
| Explicit relevant coupling | $m^2\phi^2$, $m\bar\psi\psi$ | the classical action already contains a scale |
| Running marginal coupling | $\beta(g)F^2$ | scale symmetry fails after renormalization |
| Improvement obstruction | virial-current term | scale and conformal questions depend on stress-tensor improvement |
| Curved-space Weyl anomaly | $aE_4-cW^2$ terms | local Weyl response of the generating functional |
| Contact term | coincident operator insertions | affects Ward identities at coincident points |

For a scalar theory, even the classical stress tensor has an ambiguity. One may improve it by adding

$$
\Delta T_{\mu\nu}
=(\partial_\mu\partial_\nu-\eta_{\mu\nu}\Box)B
$$

for a local scalar operator $B$. The trace changes by

$$
\Delta T^\mu{}_{\mu}=-(d-1)\Box B
$$

in flat $d$-dimensional space. This is why the phrase “the trace of the stress tensor” is incomplete until the improvement convention is stated.

## Curved-space Weyl anomaly

Now put the theory on a background metric. A local Weyl transformation gives

$$
\delta_\sigma W[g]
=\int d^dx\sqrt{|g|}\,\sigma\,\mathcal A_{\rm Weyl}.
$$

The anomaly must be local, because it is the short-distance residue of the regulated theory. It must also satisfy an abelian consistency condition: two Weyl transformations commute,

$$
[\delta_{\sigma_1},\delta_{\sigma_2}]W=0.
$$

This severely restricts possible terms.

In odd-dimensional unitary CFTs without boundaries, there is no local scalar density of the right Weyl variation to give the usual type-A or type-B Weyl anomaly. In even dimensions, there is.

### Two dimensions

For a two-dimensional CFT, the curved-space Weyl anomaly is proportional to the Ricci scalar:

$$
\langle T^\mu{}_{\mu}\rangle
=-\frac{c}{24\pi}R,
$$

up to the sign convention for the effective action and curvature. The coefficient $c$ is the central charge.

If the theory is chiral, there may also be a genuine gravitational anomaly proportional to $c_L-c_R$. The trace anomaly is controlled by $c_L+c_R$ in common conventions, while the diffeomorphism gravitational anomaly is controlled by $c_L-c_R$.

This gives a useful memory aid:

$$
\text{2D trace anomaly} \sim c_L+c_R,
\qquad
\text{2D gravitational anomaly} \sim c_L-c_R.
$$

### Four dimensions

For a four-dimensional CFT, the standard local form is

$$
\langle T^\mu{}_{\mu}\rangle
=\frac{1}{(4\pi)^2}
\left(
 c\,W_{\mu\nu\rho\sigma}W^{\mu\nu\rho\sigma}
-a\,E_4
+b\,\Box R
+\sum_I k_I\operatorname{tr}F^I_{\mu\nu}F^{I\mu\nu}
\right),
$$

where

$$
E_4=R_{\mu\nu\rho\sigma}R^{\mu\nu\rho\sigma}
-4R_{\mu\nu}R^{\mu\nu}
+R^2
$$

is the Euler density and $W_{\mu\nu\rho\sigma}$ is the Weyl tensor. The coefficient $a$ is the type-A anomaly coefficient. The coefficient $c$ is a type-B anomaly coefficient. The coefficient $b$ multiplying $\Box R$ is scheme dependent because it can be shifted by a local $R^2$ counterterm.

The background gauge-field term is present when the CFT has a global symmetry coupled to a background field. Its coefficient is related to the current two-point-function normalization.

## Type-A, type-B, and trivial Weyl anomalies

A useful classification separates Weyl anomalies into three kinds.

**Type-A anomalies** are related to Euler densities. In four dimensions the representative is $E_4$. Their Weyl variation is special and underlies many monotonicity statements, such as the two-dimensional $c$-theorem and the four-dimensional $a$-theorem.

**Type-B anomalies** are Weyl-invariant scalar densities. In four dimensions $W_{\mu\nu\rho\sigma}^2$ is the canonical example. Type-B anomaly coefficients are often tied to correlation-function normalizations.

**Trivial anomalies** are Weyl variations of local counterterms. They can be shifted by changing the renormalization scheme. The $\Box R$ term in four dimensions is the standard example.

This classification is not just taxonomy. It tells you which coefficients are robust data of the theory and which can move when local counterterms are changed.

## Relation to the anomaly polynomial story

The trace anomaly is not usually encoded by the same anomaly polynomial used for chiral gauge and gravitational anomalies. Gauge and gravitational anomalies are obstructions to gauge redundancies. The trace anomaly is an anomaly in scale or Weyl symmetry.

There is still a parallel structure:

$$
\text{background source}
\quad\Rightarrow\quad
\text{local anomalous variation}
\quad\Rightarrow\quad
\text{counterterm ambiguity}
\quad\Rightarrow\quad
\text{cohomology class}.
$$

For Weyl anomalies, the relevant cohomology is the local cohomology of Weyl transformations acting on background sources. For chiral anomalies, the relevant cohomology is the local gauge or BRST cohomology that appears in the descent formalism.

The two stories meet in important places. A theory may have both a trace anomaly and a gravitational anomaly. A curved-space CFT can have Weyl anomalies involving background gauge fields. A dilaton effective action can encode the difference between trace-anomaly coefficients along an RG flow.

## Dilaton viewpoint

Introduce a compensator field $\tau(x)$, often called the dilaton, which shifts under Weyl transformations:

$$
\tau(x)\mapsto \tau(x)+\sigma(x).
$$

Then the rescaled metric

$$
\widehat g_{\mu\nu}=e^{-2\tau}g_{\mu\nu}
$$

is Weyl invariant. If a theory has a Weyl anomaly, one can write a Wess–Zumino action for $\tau$ whose Weyl variation reproduces the anomaly.

In flat space, this is a powerful way to package anomaly matching for RG flows. If a flow connects a UV CFT to an IR CFT, the difference of anomaly coefficients appears in the dilaton effective action. In two dimensions this is related to the $c$-theorem; in four dimensions it is central to the modern proof strategy for the $a$-theorem.

The conceptual point is simple: the anomaly cannot disappear along RG flow. It must be carried either by massless degrees of freedom in the IR or by a compensating Wess–Zumino term.

## Common pitfalls

**Confusing trace anomalies with gravitational anomalies.** A trace anomaly is a failure of Weyl invariance. A gravitational anomaly is a failure of diffeomorphism or local Lorentz invariance. Both involve $T_{\mu\nu}$, but only the latter obstructs coupling to background geometry as a gauge redundancy.

**Saying “a CFT has no trace anomaly.”** In flat space, the improved stress tensor of a CFT has vanishing trace away from contact terms. On curved backgrounds, even a CFT can have a Weyl anomaly.

**Forgetting improvement terms.** The stress tensor is not unique. Improvement terms can change the trace by total derivatives such as $\Box B$.

**Comparing beta-function formulas across gauge-field normalizations.** The expressions $\beta(g)F^2/(2g)$ and $\beta(g)F^2/(2g^3)$ can describe the same physics in different normalizations.

**Treating scheme-dependent curvature terms as universal.** Terms like $\Box R$ can often be shifted by local counterterms. Euler and Weyl-squared coefficients in a four-dimensional CFT are much more robust.

**Assuming scale invariance always equals conformal invariance.** In many unitary relativistic examples it does, under suitable assumptions, but the implication is subtle and not a definition.

## Relations to other pages

The trace anomaly is the anomaly-theory bridge to RG. It should be read alongside the Renormalization, RG, and EFT volume when those pages are available.

It also connects directly to [Gravitational Anomalies](/symmetry-anomalies-topology/anomalies/gravitational-anomalies/), because both use stress-tensor Ward identities but diagnose different symmetries. It connects to [Mixed Anomalies](/symmetry-anomalies-topology/anomalies/mixed-anomalies/) through background-field trace terms such as $F_{\mu\nu}F^{\mu\nu}$. It connects to [Contact Terms](/symmetry-anomalies-topology/noether-currents-ward-identities/contact-terms/) because trace Ward identities are full of coincident-point subtleties.

Later pages on anomaly polynomials and descent will treat chiral gauge and gravitational anomalies. Do not force the trace anomaly into that exact template; use the Weyl-cohomology template instead.

## Research status

The core facts are settled: renormalization can break classical scale invariance, the trace is governed by beta functions and explicit breaking terms, and curved-space CFTs can have local Weyl anomalies.

Active and sophisticated uses include RG monotonicity theorems, Weyl consistency conditions with spacetime-dependent couplings, defect and boundary Weyl anomalies, supersymmetric anomaly multiplets, entanglement entropy, hydrodynamics in curved backgrounds, and dilaton effective actions.

The relation between scale invariance and conformal invariance remains a subtle theorem-dependent subject. In many physically important relativistic unitary settings the expected implication holds, but the assumptions matter.

## Exercises

### Exercise 1: Weyl variation and the trace

Using

$$
\delta W[g]=\frac12\int d^dx\sqrt{|g|}\,\langle T^{\mu\nu}\rangle\delta g_{\mu\nu},
$$

show that an infinitesimal Weyl transformation $\delta_\sigma g_{\mu\nu}=2\sigma g_{\mu\nu}$ gives

$$
\delta_\sigma W[g]=\int d^dx\sqrt{|g|}\,\sigma\langle T^\mu{}_{\mu}\rangle.
$$

<details><summary><strong>Solution</strong></summary>

Substitute the Weyl variation into the definition:

$$
\delta_\sigma W[g]
=\frac12\int d^dx\sqrt{|g|}\,\langle T^{\mu\nu}\rangle(2\sigma g_{\mu\nu}).
$$

The factors of $2$ cancel, leaving

$$
\delta_\sigma W[g]
=\int d^dx\sqrt{|g|}\,\sigma\,g_{\mu\nu}\langle T^{\mu\nu}\rangle
=\int d^dx\sqrt{|g|}\,\sigma\langle T^\mu{}_{\mu}\rangle.
$$

</details>

### Exercise 2: Improvement changes the trace

Let

$$
\Delta T_{\mu\nu}=(\partial_\mu\partial_\nu-\eta_{\mu\nu}\Box)B
$$

in flat $d$-dimensional space. Compute $\Delta T^\mu{}_{\mu}$.

<details><summary><strong>Solution</strong></summary>

Contract with $\eta^{\mu\nu}$:

$$
\Delta T^\mu{}_{\mu}
=\eta^{\mu\nu}\partial_\mu\partial_\nu B
-\eta^{\mu\nu}\eta_{\mu\nu}\Box B.
$$

Since $\eta^{\mu\nu}\partial_\mu\partial_\nu=\Box$ and $\eta^{\mu\nu}\eta_{\mu\nu}=d$,

$$
\Delta T^\mu{}_{\mu}=(1-d)\Box B=-(d-1)\Box B.
$$

Thus improvement terms can change the trace by total-derivative local operators.

</details>

### Exercise 3: Why no pure local Weyl anomaly in odd dimensions?

Give the quick dimensional and cohomological reason why ordinary CFTs in odd spacetime dimensions have no bulk local Weyl anomaly on closed manifolds.

<details><summary><strong>Solution</strong></summary>

A local Weyl anomaly is an integral of a local scalar density of mass dimension $d$ whose Weyl variation satisfies the abelian consistency condition. In odd $d$, there is no Euler density of degree $d$, and the usual Weyl-invariant scalar densities built from curvature contractions have even mass dimension. On closed manifolds without boundaries, the local cohomology that gives the familiar type-A and type-B Weyl anomalies is absent.

This does not mean there are no finite universal quantities in odd-dimensional CFTs. It means they are not represented as a local bulk trace anomaly. Boundaries, defects, parity-odd structures, and background fields require separate analysis.

</details>

### Exercise 4: Gauge-field normalization

Suppose one writes a Yang–Mills action as

$$
\mathcal L=-\frac{1}{4g^2}F_{\mu\nu}F^{\mu\nu}.
$$

Explain why the trace anomaly is naturally proportional to $\beta(g)F^2/g^3$ in this normalization.

<details><summary><strong>Solution</strong></summary>

The coupling appears outside the kinetic operator. Differentiating the Lagrangian with respect to $g$ gives

$$
\frac{\partial\mathcal L}{\partial g}
=\frac{1}{2g^3}F_{\mu\nu}F^{\mu\nu}.
$$

The RG contribution to the trace is schematically

$$
T^\mu{}_{\mu}=\beta(g)\frac{\partial\mathcal L}{\partial g}+\cdots,
$$

so

$$
T^\mu{}_{\mu}=\frac{\beta(g)}{2g^3}F_{\mu\nu}F^{\mu\nu}+\cdots.
$$

If instead $g$ is absorbed into the gauge field strength, the same physics is written with a different power of $g$ in front.

</details>

## References

- S. Coleman and R. Jackiw, “Why Dilatation Generators Do Not Generate Dilatations?” *Annals of Physics* **67** (1971).
- S. Coleman, “Dilatations,” in *Aspects of Symmetry*.
- C. G. Callan, “Broken Scale Invariance in Scalar Field Theory,” *Physical Review D* **2** (1970).
- K. Symanzik, “Small Distance Behaviour in Field Theory and Power Counting,” *Communications in Mathematical Physics* **18** (1970).
- M. J. Duff, “Twenty Years of the Weyl Anomaly,” *Classical and Quantum Gravity* **11** (1994).
- S. Deser and A. Schwimmer, “Geometric Classification of Conformal Anomalies in Arbitrary Dimensions,” *Physics Letters B* **309** (1993).
- M. D. Schwartz, *Quantum Field Theory and the Standard Model*, Chapter 30 and related RG chapters.
- M. Srednicki, *Quantum Field Theory*, sections on anomalies, renormalization, and conserved currents.
- S. Weinberg, *The Quantum Theory of Fields*, Volumes I–II, sections on symmetries, renormalization, and anomalies.

## Version history

- 2026-06-18: First polished draft. Added flat-space RG trace formula, gauge-theory normalization caveat, curved-space Weyl anomaly, type-A/type-B/trivial classification, dilaton viewpoint, and exercises.
