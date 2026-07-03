---
title: "Local Renormalization Group"
description: "A guide to the local renormalization group: spacetime-dependent couplings, Weyl transformations, trace identities, anomalies, Wess–Zumino consistency, and scheme geometry."
sidebar:
  label: "Local Renormalization Group"
  order: 40
level: Advanced
status: "Polished draft"
source: "Osborn 1991; Jack and Osborn; Shore; Coleman 1985, Dilatations; Zinn-Justin 2021; Schwimmer and Theisen."
topics:
  - local renormalization group
  - Weyl anomaly
  - trace anomaly
  - local couplings
  - Wess-Zumino consistency
  - scheme dependence
canonicalTopics:
  - local-renormalization-group
  - weyl-anomaly
  - trace-identity
  - coupling-space-geometry
researchStatus:
  established:
    - "The local RG packages ordinary RG flow, composite-operator renormalization, and trace anomalies into a Weyl variation of a generating functional with spacetime-dependent sources."
  active:
    - "Applications to scale versus conformal invariance, vector beta functions, boundaries, defects, irrelevant operators, and nonperturbative monotonicity theorems remain subtle and active."
---

## Summary

The **local renormalization group** is what you get when you stop treating the RG scale as a single global knob and instead ask how a quantum field theory responds to a **local Weyl rescaling** of the background geometry.

The ordinary RG says that renormalized couplings $g^i(\mu)$ change when the subtraction scale $\mu$ changes:

$$
\mu\frac{d g^i}{d\mu}=\beta^i(g).
$$

The local RG upgrades this to a statement about a generating functional with background fields:

$$
W[g_{\mu\nu}(x),g^i(x),A_\mu^a(x),\ldots].
$$

Here $g_{\mu\nu}$ is a background metric, $g^i(x)$ are spacetime-dependent sources for local operators $\mathcal O_i$, and $A_\mu^a$ are background gauge fields for global currents. A local Weyl transformation with parameter $\sigma(x)$ acts schematically as

$$
\Delta_\sigma W
=
\int d^d x\sqrt g\,\sigma(x)
\left(
2g_{\mu\nu}\frac{\delta W}{\delta g_{\mu\nu}}
-\beta^i\frac{\delta W}{\delta g^i}
+\cdots
\right)
=
\int d^d x\sqrt g\,\sigma(x)\mathcal A.
$$

The right-hand side $\mathcal A$ is the local Weyl anomaly. The dots include current sources, flavor rotations, improvement terms, and derivative-of-coupling terms. The local RG therefore contains the trace identity

$$
T^\mu{}_{\mu}
=
\beta^i[\mathcal O_i]
+\text{derivative terms}
+\text{curvature and source anomalies},
$$

with all terms interpreted as renormalized operator insertions.

<figure class="doc-figure" style="--figure-width: 58rem; --caption-width: 56rem;">

![Local RG map showing ordinary constant scale transformations upgraded to local Weyl transformations with local couplings, current sources, anomaly terms, and Wess-Zumino consistency.](/figures/renormalization-rg-eft/local-rg-weyl-consistency-map.svg)

<figcaption>

The local RG promotes constant scale transformations to local Weyl transformations of the source functional. Spacetime-dependent couplings expose contact terms and operator mixing; the local anomaly must satisfy Wess–Zumino consistency because Weyl transformations commute.

</figcaption>
</figure>

The payoff is conceptual and practical. Local RG explains why trace anomalies, beta functions, current mixing, contact terms, and monotonicity constraints are not separate bookkeeping accidents. They are different components of one source-dependent Ward identity.

## Prerequisites

You should know [Callan–Symanzik Equation](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/), [Beta Functions](/renormalization-rg-eft/renormalization-group-equations/beta-functions/), [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), [Renormalization Matrix](/renormalization-rg-eft/local-operators-and-ope/renormalization-matrix/), [OPE and Short-Distance Expansion](/renormalization-rg-eft/local-operators-and-ope/ope-and-short-distance-expansion/), and [Conformal Perturbation Theory Preview](/renormalization-rg-eft/local-operators-and-ope/conformal-perturbation-theory-preview/).

This page uses Euclidean background-field notation when discussing $W[g_{\mu\nu},g^i(x)]$. The physical Lorentzian trace identity is obtained by analytic continuation with the sign conventions stated on the relevant page. The RG convention remains the volume convention: $\beta^i=\mu\,dg^i/d\mu$ at fixed bare data.

## Core idea

In ordinary renormalized perturbation theory, a source $g^i$ multiplying a local operator is usually constant:

$$
S\longrightarrow S+\int d^d x\,g^i\mathcal O_i.
$$

But if $g^i$ is only constant, functional derivatives with respect to it insert spacetime integrals of $\mathcal O_i$, not local operators. To keep track of local contact terms and operator mixing, one promotes the source to a function:

$$
S\longrightarrow
S+\int d^d x\sqrt g\,g^i(x)\mathcal O_i(x).
$$

Now the generating functional is a functional of sources. The local operator is recovered by differentiation:

$$
\langle \mathcal O_i(x)\rangle
=
\frac{1}{\sqrt g}\frac{\delta W}{\delta g^i(x)}.
$$

The stress tensor is obtained by varying the metric. With the Euclidean convention

$$
\langle T_{\mu\nu}(x)\rangle
=-\frac{2}{\sqrt g}\frac{\delta W}{\delta g^{\mu\nu}(x)},
$$

a local Weyl variation probes the trace $T^\mu{}_\mu$.

The local RG is the statement that a Weyl rescaling of the metric can be compensated by a corresponding transformation of all sources, up to a local anomaly. It is therefore the source-functional version of the phrase:

$$
\text{scale dependence is encoded in local operator insertions.}
$$

## Why local sources are necessary

If $g^i(x)$ varies in spacetime, renormalization permits counterterms that would be invisible for constant couplings. Examples include

$$
\int d^d x\sqrt g\,\chi_{ij}(g)\,\partial_\mu g^i\partial^\mu g^j,
$$

and curvature-source terms such as

$$
\int d^d x\sqrt g\,R\,L(g).
$$

These are not decorative. They are forced by short-distance singularities of operator insertions. For example, differentiating $W$ twice with respect to $g^i(x)$ and $g^j(y)$ inserts $\mathcal O_i(x)\mathcal O_j(y)$. The OPE as $x\to y$ can contain local singularities, and after integration these become source counterterms.

The local source method keeps four pieces of information visible:

| Object | What local RG tracks |
|---|---|
| Metric source | Stress tensor, improvement terms, curvature anomalies. |
| Scalar sources $g^i(x)$ | Composite operators, beta functions, operator mixing. |
| Background gauge fields $A_\mu^a$ | Currents, Ward identities, flavor rotations, vector beta functions. |
| Local counterterms | Scheme dependence, anomaly shifts, Wess–Zumino consistency. |

This is why local RG is a grown-up version of the Callan–Symanzik equation rather than a fancy rewriting of it.

## The Weyl generator

A local Weyl transformation rescales the metric:

$$
g_{\mu\nu}(x)\to e^{2\sigma(x)}g_{\mu\nu}(x).
$$

Infinitesimally,

$$
\delta_\sigma g_{\mu\nu}=2\sigma g_{\mu\nu}.
$$

Because increasing local length is opposite to increasing the UV subtraction scale $\mu$, the source variation includes the beta function. A schematic local RG generator is

$$
\Delta_\sigma
=
\int d^d x\sqrt g\,
\left[
2\sigma g_{\mu\nu}\frac{\delta}{\delta g_{\mu\nu}}
-\sigma\beta^i\frac{\delta}{\delta g^i}
+\cdots
\right].
$$

The ellipsis may include terms such as

$$
\partial_\mu\sigma\,\rho_i^a(g)\frac{\delta}{\delta A_\mu^a},
\qquad
\sigma\,\gamma_A{}^B J^A\frac{\delta}{\delta J^B},
$$

depending on which sources are present. The details are technical, but the principle is simple: every background source must transform in whatever way is required by renormalization and symmetry.

The local RG equation is then

$$
\Delta_\sigma W=\mathcal A_\sigma,
$$

where $\mathcal A_\sigma$ is a local functional of the sources and $\sigma$.

## The trace identity

Using

$$
\langle T_{\mu\nu}(x)\rangle
=-\frac{2}{\sqrt g}\frac{\delta W}{\delta g^{\mu\nu}(x)},
$$

the local RG equation gives the operator trace relation

$$
\langle T^\mu{}_{\mu}\rangle
=
\beta^i\langle [\mathcal O_i]\rangle
+\nabla_\mu\langle J^\mu_{\mathrm{vir}}\rangle
+\mathcal A[g_{\mu\nu},g^i(x),A_\mu,\ldots].
$$

The brackets $[\mathcal O_i]$ remind us that these are renormalized composite operators. The current term is schematic: in theories with global symmetries, beta functions can mix with flavor rotations and divergences of currents.

In flat space with constant couplings and no virial-current subtleties, this reduces to the familiar separated-point statement

$$
T^\mu{}_{\mu}=\beta^i[\mathcal O_i].
$$

At an RG fixed point, $\beta^i=0$, but there can still be a curved-space Weyl anomaly. Thus flat-space scale invariance and curved-space Weyl invariance are related but not identical statements.

## The anomaly functional

The anomaly functional is local. At a fixed point in two dimensions, one has the familiar form

$$
\mathcal A_\sigma
=
\frac{c}{24\pi}
\int d^2x\sqrt g\,\sigma R
$$

up to convention choices. At a fixed point in four dimensions, the trace anomaly includes

$$
\langle T^\mu{}_\mu\rangle
=
\frac{1}{16\pi^2}
\left(
c\,W_{\mu\nu\rho\sigma}W^{\mu\nu\rho\sigma}
-a\,E_4
+b\,\Box R
\right).
$$

Here $W_{\mu\nu\rho\sigma}$ is the Weyl tensor and $E_4$ is the Euler density. The coefficient of $\Box R$ is scheme dependent because it can be shifted by a local $R^2$ counterterm. The coefficients $a$ and $c$ at a unitary CFT are physical CFT data.

Away from fixed points, and with local couplings, additional terms can appear:

$$
\chi_{ij}(g)\,\partial_\mu g^i\partial^\mu g^j,
\qquad
w_i(g)\,\partial_\mu g^i\partial^\mu R,
\qquad
\nabla_\mu\bigl(v_i(g)\partial^\mu g^i R\bigr),
$$

and many more terms depending on dimension and source content.

The important point is not the full catalog. The important point is that all such terms are constrained by locality, symmetries, dimensional analysis, and Wess–Zumino consistency.

## Wess–Zumino consistency

Local Weyl transformations commute:

$$
[\delta_\sigma,\delta_\tau]g_{\mu\nu}=0.
$$

Therefore the corresponding local RG transformations must satisfy

$$
[\Delta_\sigma,\Delta_\tau]W=0.
$$

If $\Delta_\sigma W=\mathcal A_\sigma$, this implies

$$
\Delta_\sigma\mathcal A_\tau
-\Delta_\tau\mathcal A_\sigma=0.
$$

This is the **Wess–Zumino consistency condition** for the Weyl anomaly.

The condition says that doing a Weyl transformation with parameter $\sigma(x)$ and then one with $\tau(x)$ must give the same answer as doing them in the opposite order. When expanded in independent combinations of $\sigma$, $\tau$, and their derivatives, it produces differential equations among anomaly coefficients, beta functions, and coupling-space tensors.

A famous schematic consequence in four dimensions is a gradient-like relation

$$
\partial_i\widetilde a
=
\chi_{ij}\beta^j
+\text{terms involving flavor rotations and scheme choices}.
$$

This is not a license to say that every RG flow is naively a gradient flow. It is a precise local consistency statement whose physical interpretation depends on assumptions about unitarity, scheme, flavor symmetries, and the positivity properties of $\chi_{ij}$.

## Coupling-space geometry

The local RG naturally turns coupling space into a geometric object. The source-derivative anomaly coefficient $\chi_{ij}(g)$ behaves like a metric-like tensor on coupling space. Finite local counterterms act like changes of coordinates or changes of connection. Flavor symmetries introduce gauge redundancy on coupling space.

This perspective is useful for conformal manifolds. If a CFT has exactly marginal couplings $\lambda^i$, then the generating functional depends on $\lambda^i(x)$, and contact terms encode the Zamolodchikov-type metric on the conformal manifold. In two-dimensional CFTs this structure is especially direct; in higher dimensions it is more delicate but still powerful.

It is also useful for distinguishing physical RG motion from redundant motion. If a beta function is just an infinitesimal field redefinition or flavor rotation, it should not be interpreted as a physical flow between inequivalent theories.

## Vector beta functions and flavor rotations

Suppose the theory has a global symmetry group $G_F$. Couplings may transform under $G_F$, and background gauge fields $A_\mu^a$ source the currents. Then a local Weyl transformation can induce a background flavor gauge transformation. The trace identity may contain

$$
T^\mu{}_{\mu}
=
\beta^i\mathcal O_i
+\nabla_\mu J^\mu
+\cdots.
$$

The divergence of a current can often be moved into the beta function by changing coordinates on coupling space. This is the origin of the distinction between a raw beta function $\beta^i$ and a flavor-invariant beta function sometimes denoted $B^i$.

This distinction matters in discussions of scale versus conformal invariance. A theory whose apparent RG flow is a pure flavor rotation may look like a limit cycle in poorly chosen coordinates, while representing the same physical theory after quotienting by symmetry.

## Scheme dependence

A finite local counterterm changes the generating functional:

$$
W\to W+W_{\mathrm{local}}[g_{\mu\nu},g^i(x),A_\mu,\ldots].
$$

The anomaly changes by

$$
\mathcal A_\sigma\to
\mathcal A_\sigma+\Delta_\sigma W_{\mathrm{local}}.
$$

Therefore not every coefficient in the trace anomaly is physical. Local RG organizes this cleanly: anomaly terms that are Weyl variations of local counterterms are cohomologically trivial, while nontrivial anomaly terms cannot be removed.

This perspective is the source of the useful phrase: **scheme dependence is coordinate dependence on the space of sources**. It does not mean everything is arbitrary. It means invariant quantities must be identified after quotienting by local counterterms and source redefinitions.

## Recovering ordinary Callan–Symanzik equations

To recover the ordinary Callan–Symanzik equation, set

$$
g^i(x)=g^i,
\qquad
g_{\mu\nu}=\eta_{\mu\nu}.
$$

Then choose $\sigma(x)=\sigma_0$ constant. Source-derivative anomaly terms vanish, and the local RG becomes the global RG equation. Functional derivatives with respect to local sources then produce correlators with operator insertions, including the usual anomalous-dimension matrix.

For example, for renormalized scalar operators $\mathcal O_a$, one obtains a schematic separated-point equation

$$
\left(
\mu\frac{\partial}{\partial\mu}
+\beta^i\frac{\partial}{\partial g^i}
\right)
\langle \mathcal O_{a_1}(x_1)\cdots\mathcal O_{a_n}(x_n)\rangle
+
\sum_{r=1}^n
\gamma_{a_r}{}^b
\langle \mathcal O_{a_1}(x_1)\cdots\mathcal O_b(x_r)\cdots\mathcal O_{a_n}(x_n)\rangle
=0,
$$

away from contact terms and explicit scale insertions.

The ordinary equation is easier to use. The local equation explains why it is true and what happens when insertions collide.

## Common pitfalls

**Thinking local RG is just $\mu\to\mu(x)$.** The robust object is not a position-dependent subtraction scale by itself. It is the source functional with local couplings, metric, and background gauge fields.

**Dropping the anomaly because flat space is simple.** Curved-space anomalies constrain flat-space physics through contact terms and consistency conditions.

**Forgetting derivative-of-coupling counterterms.** Once $g^i$ depends on $x$, counterterms involving $\partial_\mu g^i$ are allowed and generally required. Ignoring them loses contact terms.

**Treating all anomaly coefficients as physical.** Some can be shifted by local counterterms. The invariant content is the anomaly cohomology plus consistency relations.

**Confusing a flavor rotation with physical RG flow.** Couplings can transform under global symmetries. Physical theory space is often a quotient by redundant transformations.

**Using local RG formulas without stating source conventions.** Signs in the trace identity depend on whether one varies $g_{\mu\nu}$ or $g^{\mu\nu}$ and on the sign used for source terms in $W$.

## Relations to other pages

The local RG refines [Callan–Symanzik Equation](/renormalization-rg-eft/renormalization-group-equations/callan-symanzik-equation/) by restoring the background sources that ordinary RG suppresses. It is closely tied to [Anomalous Dimensions](/renormalization-rg-eft/renormalization-group-equations/anomalous-dimensions/), [Operator Mixing](/renormalization-rg-eft/local-operators-and-ope/operator-mixing/), [Anomalous-Dimension Matrix](/renormalization-rg-eft/local-operators-and-ope/anomalous-dimension-matrix/), and [Conformal Perturbation Theory](/renormalization-rg-eft/advanced-rg-methods/conformal-perturbation-theory/).

It also prepares the curved-spacetime pages on stress-tensor renormalization and trace anomalies, as well as later pages on monotonicity theorems and scale versus conformal invariance.

## Research status

The source-functional formulation of local RG and Wess–Zumino consistency is established. Its most standard applications are trace anomalies, Callan–Symanzik equations, operator mixing, conformal manifolds, and consistency constraints on RG flow.

Active work concerns the sharp relation between scale and conformal invariance, vector beta functions, boundary and defect local RG, irrelevant deformations, nonperturbative monotonicity, supersymmetric refinements, and holographic realizations.

## Exercises

### Exercise 1: Constant Weyl parameter

Start from the schematic local RG equation

$$
\Delta_\sigma W
=
\int d^d x\sqrt g\,\sigma(x)
\left(
2g_{\mu\nu}\frac{\delta W}{\delta g_{\mu\nu}}
-\beta^i\frac{\delta W}{\delta g^i}
\right)
=
\mathcal A_\sigma.
$$

Set $\sigma(x)=\sigma_0$, $g^i(x)=g^i$, and $g_{\mu\nu}=\eta_{\mu\nu}$. Explain why this reduces to the ordinary global scale/RG equation for separated flat-space correlators.

<details><summary><strong>Solution</strong></summary>

For constant $\sigma_0$, the Weyl transformation is a global rescaling of lengths. With constant couplings, derivative-of-coupling terms vanish. In flat space, curvature anomaly terms also vanish away from contact terms. The remaining equation says that the response to a global rescaling is compensated by the beta-function motion of the couplings. Differentiating with respect to sources for operators then gives the ordinary Callan–Symanzik equation for separated correlators, including anomalous-dimension terms from operator-source transformations.

</details>

### Exercise 2: Wess–Zumino consistency

Assume $\Delta_\sigma W=\mathcal A_\sigma$ and $[\Delta_\sigma,\Delta_\tau]W=0$. Show that

$$
\Delta_\sigma\mathcal A_\tau-\Delta_\tau\mathcal A_\sigma=0.
$$

<details><summary><strong>Solution</strong></summary>

Use the local RG equation twice:

$$
0=[\Delta_\sigma,\Delta_\tau]W
=\Delta_\sigma(\Delta_\tau W)-\Delta_\tau(\Delta_\sigma W).
$$

Since $\Delta_\tau W=\mathcal A_\tau$ and $\Delta_\sigma W=\mathcal A_\sigma$, this becomes

$$
0=\Delta_\sigma\mathcal A_\tau-\Delta_\tau\mathcal A_\sigma.
$$

This is the Wess–Zumino consistency condition for local Weyl anomalies.

</details>

### Exercise 3: Scheme shift of an anomaly

Let $W\to W+W_{\mathrm{local}}$, where $W_{\mathrm{local}}$ is a finite local functional of the background sources. Show that the anomaly shifts by $\Delta_\sigma W_{\mathrm{local}}$.

<details><summary><strong>Solution</strong></summary>

The transformed anomaly is defined by

$$
\Delta_\sigma(W+W_{\mathrm{local}})
=
\mathcal A'_\sigma.
$$

Using $\Delta_\sigma W=\mathcal A_\sigma$, we get

$$
\mathcal A'_\sigma
=
\mathcal A_\sigma+\Delta_\sigma W_{\mathrm{local}}.
$$

Thus any anomaly term that can be written as the local Weyl variation of a finite local counterterm is scheme dependent.

</details>

## References

- H. Osborn, "Weyl Consistency Conditions and a Local Renormalization Group Equation for General Renormalizable Field Theories," for the classic source-functional formulation.
- I. Jack and H. Osborn, papers on local RG, Weyl consistency, vector beta functions, and anomaly constraints.
- S. Coleman, *Aspects of Symmetry*, especially "Dilatations," for scale transformations, anomalous dimensions, and Callan–Symanzik equations.
- J. Zinn-Justin, *Quantum Field Theory and Critical Phenomena*, for RG, critical phenomena, anomalous dimensions, and field-theoretic scaling.
- R. J. Riegert, A. Schwimmer, S. Theisen, Z. Komargodski, and A. Schwimmer, for trace anomalies and monotonicity-theorem context.
- G. M. Shore, reviews and papers on local RG, scale versus conformal invariance, and Weyl consistency.

## Version history

- 2026-06-19: First polished draft. Introduced local couplings, source-functional Weyl transformations, trace anomalies, Wess–Zumino consistency, coupling-space geometry, vector beta functions, and scheme dependence.
