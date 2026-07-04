---
title: "Scale Invariance versus Conformal Invariance"
description: "Explains the distinction between scale invariance and conformal invariance, the stress-tensor criterion, common examples, and why most unitary critical QFTs are treated as CFTs."
sidebar:
  label: "Scale vs Conformal"
  order: 1
level: Graduate
status: "Polished draft"
source: "Coleman 1985; Polchinski 1988; Riva–Cardy 2005; Nakayama 2013; Simmons-Duffin 2016; Poland–Rychkov–Vichi 2019"
topics:
  - scale invariance
  - conformal invariance
  - dilatations
  - special conformal transformations
  - stress tensor
  - virial current
  - trace anomaly
  - RG fixed points
canonicalTopics:
  - scale-versus-conformal-invariance
  - stress-tensor-trace
  - virial-current
  - cft-definition
researchStatus:
  established:
    - "Conformal invariance is stronger than scale invariance: it includes special conformal transformations and usually requires an improved traceless stress tensor."
    - "In two-dimensional unitary relativistic QFT, scale invariance implies conformal invariance under standard assumptions."
  active:
    - "In dimensions greater than two, the general nonperturbative equivalence between scale invariance and conformal invariance depends on assumptions and remains a subtle research topic."
---

## Summary

Scale invariance says that physics is unchanged when all lengths are multiplied by a common factor:

$$
x^\mu\mapsto \lambda x^\mu.
$$

Conformal invariance says more. It allows transformations that preserve angles but may rescale lengths by a position-dependent factor:

$$
\delta_{\rho\sigma}\frac{\partial x'^\rho}{\partial x^\mu}\frac{\partial x'^\sigma}{\partial x^\nu}
=\Omega(x)^2\delta_{\mu\nu}.
$$

Every conformal theory is scale invariant. The converse is not automatic. In a local QFT with a conserved stress tensor, the distinction is measured by the trace. Scale invariance allows

$$
T^\mu{}_{\mu}=\partial_\mu V^\mu,
$$

where $V^\mu$ is a virial current. Conformal invariance requires, roughly, that this trace can be removed by improving the stress tensor, so that

$$
T^\mu{}_{\mu}=0
$$

at separated points in flat space, up to anomalies and contact terms.

This distinction matters because CFT methods use the full conformal group. Scale invariance alone gives power laws and RG fixed-point intuition. Conformal invariance gives primary operators, descendants, Ward identities, strong constraints on two- and three-point functions, conformal blocks, and bootstrap equations.

:::note[Working rule]
In this volume, “CFT” means conformally invariant QFT, not merely scale-invariant QFT. When a physical fixed point is introduced from RG language, we state or assume the conditions under which scale invariance enhances to conformal invariance.
:::

## Prerequisites

You should know the [Conventions and Notation](/cft-bootstrap/conventions/) page, especially Euclidean signature and stress-tensor conventions. You should also know what a conserved current is, how Noether currents work, and why RG fixed points have no running dimensionless couplings.

Useful background from neighboring volumes includes Noether currents and stress tensors in [Foundations of QFT](/foundations/) and RG fixed points in [Renormalization, RG, and EFT](/renormalization-rg-eft/).

## Core idea

Scale transformations are global rescalings. They test whether the theory has a preferred length scale. Conformal transformations are local angle-preserving transformations. They test whether the theory is insensitive not only to the overall ruler but also to local changes of ruler that are equivalent to coordinate transformations.

For $d\geq 3$ in flat Euclidean space, the connected conformal group is finite-dimensional. Its generators are

$$
P_\mu,\qquad M_{\mu\nu},\qquad D,\qquad K_\mu,
$$

for translations, rotations, dilatations, and special conformal transformations. Scale invariance adds only $D$ to translations and rotations. Conformal invariance adds the $d$ generators $K_\mu$ as well.

The special conformal transformation is the new ingredient. Infinitesimally it acts like

$$
\delta x^\mu = 2(b\cdot x)x^\mu-b^\mu x^2,
$$

where $b^\mu$ is a constant vector. A finite version can be written as

$$
x'^\mu=\frac{x^\mu-b^\mu x^2}{1-2b\cdot x+b^2x^2}.
$$

This transformation is not a translation, rotation, or global rescaling. It rescales distances by a factor depending on position. That extra freedom is what makes conformal symmetry so constraining.

A good mental picture is:

$$
\text{scale invariance}:
\text{one global zoom knob},
\qquad
\text{conformal invariance}:
\text{a locally varying zoom compatible with angles}.
$$

## Setup and conventions

This page uses flat Euclidean $\mathbb R^d$ unless stated otherwise. Correlators are Euclidean correlators at separated points. The stress tensor is symmetric and conserved,

$$
\partial^\mu T_{\mu\nu}=0,
$$

possibly after the usual Belinfante improvement when spin currents are present.

A scalar local operator $\mathcal O$ has scaling dimension $\Delta$ if under a dilatation it transforms as

$$
\mathcal O(x)\mapsto \lambda^{-\Delta}\mathcal O(\lambda^{-1}x),
$$

or equivalently, infinitesimally,

$$
[D,\mathcal O(x)]=\left(x^\mu\partial_\mu+\Delta\right)\mathcal O(x)
$$

in operator language, up to the conventional placement of factors of $i$ in Lorentzian signature.

A scalar primary operator in a conformal theory transforms covariantly under every conformal transformation:

$$
\mathcal O(x)\mapsto \Omega(x')^{\Delta}\mathcal O(x'),
$$

with the precise inverse-map convention fixed locally on the pages that use it. Spinning primaries carry an additional rotation matrix acting on spin indices.

Two warnings are worth making at the start.

First, scale invariance of a classical action is not the same as scale invariance of the quantum theory. Quantum renormalization may introduce running couplings or anomalies.

Second, scale invariance of flat-space separated-point correlators is not the same as Weyl invariance on arbitrary curved backgrounds. Curved-space trace anomalies are real and important, even for conformal theories.

## What scale invariance fixes

Suppose the vacuum is invariant under translations, rotations, and dilatations. Then the two-point function of scalar scaling operators must take a power-law form. Translation and rotation invariance give

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle=F_{ij}(\lvert x\rvert).
$$

Scale covariance gives

$$
F_{ij}(\lambda r)=\lambda^{-\Delta_i-\Delta_j}F_{ij}(r).
$$

If $\mathcal O_i$ and $\mathcal O_j$ are eigenoperators of $D$, this implies

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=\frac{C_{ij}}{\lvert x\rvert^{\Delta_i+\Delta_j}}.
$$

In a unitary conformal theory, operators of different scaling dimension are orthogonal, and an orthonormal scalar basis gives the sharper form

$$
\langle \mathcal O_i(x)\mathcal O_j(0)\rangle
=\frac{\delta_{ij}}{\lvert x\rvert^{2\Delta_i}}.
$$

Scale invariance also strongly suggests why critical phenomena have power laws. If there is no correlation length at the fixed point, then correlators cannot decay exponentially with a characteristic length. They must be built from powers and dimensionless functions.

But scale invariance alone is not enough to produce the full CFT formula book. For example, translation, rotation, and scale invariance do not by themselves fix the scalar three-point function to the conformal form. Three points in $d>1$ have dimensionless shape data after removing an overall scale. Conformal transformations remove that extra freedom.

## What conformal invariance adds

Conformal invariance fixes scalar two- and three-point functions almost completely. With the normalization conventions of this volume, scalar primaries satisfy

$$
\langle \mathcal O_i(x_1)\mathcal O_j(x_2)\rangle
=\frac{\delta_{ij}}{x_{12}^{2\Delta_i}},
$$

and

$$
\langle \mathcal O_i(x_1)\mathcal O_j(x_2)\mathcal O_k(x_3)\rangle
=
\frac{\lambda_{ijk}}
{x_{12}^{\Delta_i+\Delta_j-\Delta_k}
 x_{13}^{\Delta_i+\Delta_k-\Delta_j}
 x_{23}^{\Delta_j+\Delta_k-\Delta_i}}.
$$

Four-point functions are not fixed completely, but conformal symmetry reduces them to functions of cross-ratios. For identical scalar primaries $\phi$,

$$
\langle \phi(x_1)\phi(x_2)\phi(x_3)\phi(x_4)\rangle
=\frac{g(u,v)}{x_{12}^{2\Delta_\phi}x_{34}^{2\Delta_\phi}},
$$

where

$$
u=\frac{x_{12}^2x_{34}^2}{x_{13}^2x_{24}^2},
\qquad
v=\frac{x_{14}^2x_{23}^2}{x_{13}^2x_{24}^2}.
$$

Here $u$ and $v$ are the conformal cross-ratios. The function $g(u,v)$ is dynamical. The bootstrap asks which such functions can arise from a consistent OPE with positive norms.

The extra conformal generators also organize local operators into multiplets. A primary operator is annihilated by special conformal generators at the origin:

$$
[K_\mu,\mathcal O(0)]=0.
$$

Descendants are obtained by acting with translations:

$$
P_{\mu_1}\cdots P_{\mu_n}\mathcal O(0).
$$

This primary-descendant structure is what makes conformal blocks possible. A conformal block is the summed contribution of an entire conformal multiplet to a four-point function.

## Stress tensor and the virial current

The sharpest local test for the distinction uses the stress tensor. In a Poincaré-invariant or Euclidean-invariant local QFT, translations are generated by $T_{\mu\nu}$. If the theory is scale invariant, it has a conserved dilatation current. The most general flat-space form is

$$
D_\mu=x^\nu T_{\mu\nu}-V_\mu,
$$

where $V_\mu$ is the virial current. Conservation gives

$$
0=\partial^\mu D_\mu
=T^\mu{}_{\mu}-\partial^\mu V_\mu,
$$

so

$$
T^\mu{}_{\mu}=\partial^\mu V_\mu.
$$

If $V_\mu=0$, the stress tensor is already traceless and the theory is conformal. If $V_\mu$ is not zero but can be removed by an improvement of the stress tensor, the theory is still conformal. If the virial current cannot be removed, the theory may be scale invariant without being conformally invariant.

The improvement issue is not a technical nuisance. It is the hinge of the whole distinction.

A common scalar improvement has the form

$$
T'_{\mu\nu}=T_{\mu\nu}+\left(\delta_{\mu\nu}\partial^2-\partial_\mu\partial_\nu\right)L,
$$

where $L$ is a local scalar operator. This preserves conservation in flat space. Its trace changes by

$$
T'^\mu{}_{\mu}=T^\mu{}_{\mu}+(d-1)\partial^2L.
$$

Thus if the original trace is

$$
T^\mu{}_{\mu}=-(d-1)\partial^2L,
$$

then the improved stress tensor is traceless.

More general improvements can involve tensor operators and subtleties with global symmetries, gauge invariance, contact terms, and curved-space definitions. But the scalar formula captures the basic point: conformal invariance is tied to the existence of a conserved, symmetric, traceless stress tensor.

## Why the trace controls special conformal symmetry

Assume the stress tensor is symmetric, conserved, and traceless. Define the special-conformal current associated with a constant vector label $\rho$ by

$$
J^{(K_\rho)}_\mu=
\left(2x_\rho x^\nu-x^2\delta_\rho{}^\nu\right)T_{\mu\nu}.
$$

Taking the divergence and using $\partial^\mu T_{\mu\nu}=0$ gives

$$
\partial^\mu J^{(K_\rho)}_\mu=2x_\rho T^\mu{}_{\mu}.
$$

Therefore a traceless stress tensor gives conserved special-conformal currents. This is the local reason that tracelessness upgrades scale symmetry to conformal symmetry.

If the trace is only a total derivative, the special-conformal current is not automatically conserved. One must ask whether the total derivative can be absorbed into an improvement. That is the virial-current problem.

## Examples and non-examples

### Free massless scalar

The massless scalar field in $d$ dimensions has action

$$
S=\frac12\int d^d x\,\partial_\mu\phi\partial^\mu\phi.
$$

It is scale invariant with engineering dimension

$$
\Delta_\phi=\frac{d-2}{2}.
$$

The canonical stress tensor is not traceless for $d\neq 2$. On the equation of motion $\partial^2\phi=0$, its trace is proportional to $\partial^2\phi^2$. The improved stress tensor

$$
T^{\mathrm{conf}}_{\mu\nu}
=\partial_\mu\phi\partial_\nu\phi
-\frac12\delta_{\mu\nu}(\partial\phi)^2
+\xi\left(\delta_{\mu\nu}\partial^2-\partial_\mu\partial_\nu\right)\phi^2,
$$

with

$$
\xi=\frac{d-2}{4(d-1)},
$$

is traceless on shell. Thus the free massless scalar is conformal, not merely scale invariant.

### Maxwell theory

Free Maxwell theory has action

$$
S=\frac14\int d^d x\,F_{\mu\nu}F^{\mu\nu}.
$$

Classically it is scale invariant in any $d$ if the gauge field is assigned its engineering dimension. Its standard gauge-invariant stress tensor has trace

$$
T^\mu{}_{\mu}=\left(1-\frac d4\right)F_{\mu\nu}F^{\mu\nu}.
$$

This vanishes in $d=4$. In $d\neq 4$, the theory is a standard warning example: scale invariance does not automatically imply conformal invariance. There are subtleties in special dimensions and in gauge-dependent descriptions, but the lesson is robust: a dimensionless-looking action is not enough; the stress tensor knows the difference.

### Wilson–Fisher fixed points

The classical massless $\phi^4$ theory is scale invariant in four dimensions. Quantum mechanically, the coupling runs. In $d=4-\epsilon$, however, the beta function has a nontrivial fixed point for small positive $\epsilon$. That Wilson–Fisher fixed point is not just scale invariant; it is treated as a CFT. Its local operator dimensions and OPE coefficients are physical CFT data.

This example is conceptually important because it explains why the phrase “critical point” so often leads to CFT. RG says the infrared theory has no intrinsic length scale. Stress-tensor and unitarity arguments often then enhance the symmetry to conformal symmetry.

### Two-dimensional critical systems

In two Euclidean dimensions, conformal symmetry becomes much larger. Locally, conformal transformations are holomorphic maps

$$
z\mapsto f(z),
\qquad
\bar z\mapsto \bar f(\bar z).
$$

Quantum mechanically, the local conformal symmetry is represented by the Virasoro algebra, with central charge $c$. Under standard assumptions, two-dimensional unitary scale-invariant relativistic QFTs are conformally invariant. This is why two-dimensional critical systems can often be solved with Virasoro symmetry rather than merely analyzed with scaling exponents.

### Known counterexamples and loopholes

There are known examples and proposed examples of scale invariance without conformal invariance, but they usually evade one or more assumptions used in the most powerful enhancement arguments. The Riva–Cardy elasticity model is a famous physically motivated example. Maxwell theory away from four dimensions is another important warning sign. Nonunitary theories, theories without a discrete operator spectrum, theories with unusual virial currents, gauge subtleties, and theories with spontaneously broken scale invariance require care.

The practical lesson is not “scale always equals conformal.” The practical lesson is:

$$
\text{scale} + \text{locality} + \text{unitarity} + \text{stress-tensor assumptions}
\quad\text{often forces}\quad
\text{conformal}.
$$

The assumptions are physics, not decorative footnotes.

## Relation to RG fixed points

At a fixed point of the renormalization group, dimensionless couplings stop running. In many perturbative schemes, the trace of the stress tensor has the schematic form

$$
T^\mu{}_{\mu}=\sum_i \beta^i(g)\mathcal O_i+\text{anomalies}+\partial_\mu V^\mu.
$$

At an ordinary fixed point, $\beta^i=0$, so the trace is reduced to anomalies and possible virial-current terms. In flat space at separated points, curvature anomalies disappear, and the central question becomes whether the virial term can be improved away.

This is why RG fixed points and CFTs are so closely related. The RG explains why scale invariance emerges. The stress tensor explains when the stronger conformal symmetry emerges.

There is one more subtlety. Some apparent “running” may be a motion along a redundant orbit generated by an internal symmetry. In that case the physical theory may still be scale invariant, and the correct fixed-point condition should be formulated modulo field redefinitions and symmetry rotations. This issue matters in advanced discussions of limit cycles and scale-versus-conformal proofs.

## How the distinction appears in correlators

Scale invariance fixes how correlators respond to a common rescaling:

$$
\left\langle \mathcal O_1(\lambda x_1)\cdots \mathcal O_n(\lambda x_n)\right\rangle
=
\lambda^{-\sum_i\Delta_i}
\left\langle \mathcal O_1(x_1)\cdots \mathcal O_n(x_n)\right\rangle.
$$

Conformal invariance imposes additional Ward identities from $K_\mu$. These identities remove extra functional freedom.

For scalar two-point functions, scale invariance already gets close to the conformal answer. For scalar three-point functions, conformal invariance is much stronger. For four-point functions, conformal invariance reduces the answer to a function of cross-ratios and makes the conformal-block expansion possible.

This is why the bootstrap is a conformal bootstrap, not merely a scale bootstrap. The machinery needs the representation theory of the full conformal group.

## Common pitfalls

**Mistake 1: “The Lagrangian has no mass, so the quantum theory is scale invariant.”** A classically dimensionless coupling may run. The scale anomaly is one of the central lessons of QFT.

**Mistake 2: “The two-point function is a power law, so the theory is conformal.”** A power law is evidence for scaling. Full conformal invariance requires the special-conformal Ward identities and the appropriate stress-tensor structure.

**Mistake 3: “The canonical stress tensor is not traceless, so the theory is not conformal.”** The canonical stress tensor may need improvement. The massless scalar is the standard example.

**Mistake 4: “Conformal invariance in flat space means no trace anomaly.”** Even a CFT can have trace anomalies on curved backgrounds or contact terms in stress-tensor correlators. Flat-space separated-point tracelessness is the cleaner statement used here.

**Mistake 5: “Every critical point is automatically a CFT.”** Many important critical points are CFTs, but the statement relies on assumptions such as locality, unitarity or reflection positivity, rotational invariance, and a suitable stress tensor. Disordered systems, long-range interactions, nonunitary statistical models, and nonequilibrium fixed points may need separate analysis.

**Mistake 6: “Scale invariance means continuous scale invariance.”** Some systems have only discrete scale invariance, leading to log-periodic behavior. That is not the same as having a conserved dilatation current.

## Relations to other pages

This page prepares the conceptual ground for [CFTs as RG Fixed Points](/cft-bootstrap/what-is-a-cft/cfts-as-rg-fixed-points/), where fixed-point language is developed more systematically.

The conformal transformations themselves are derived in [Conformal Transformations](/cft-bootstrap/conformal-symmetry/conformal-transformations/) and [Conformal Algebra](/cft-bootstrap/conformal-symmetry/conformal-algebra/). The stress-tensor Ward identities appear in [Conformal Ward Identities](/cft-bootstrap/conformal-symmetry/conformal-ward-identities/).

The operator consequences of full conformal invariance appear in [Primary and Descendant Operators](/cft-bootstrap/operators-states-radial-quantization/primary-and-descendant-operators/), [State–Operator Correspondence](/cft-bootstrap/operators-states-radial-quantization/state-operator-correspondence/), and [Unitarity Bounds](/cft-bootstrap/operators-states-radial-quantization/unitarity-bounds/).

The correlation-function consequences appear in [Two-Point Functions](/cft-bootstrap/correlation-functions/two-point-functions/), [Three-Point Functions](/cft-bootstrap/correlation-functions/three-point-functions/), [Four-Point Functions](/cft-bootstrap/correlation-functions/four-point-functions/), and [Cross-Ratios](/cft-bootstrap/correlation-functions/cross-ratios/).

## Research status

The distinction between scale and conformal invariance is settled at the level needed for most CFT practice: conformal invariance is stronger, the stress tensor and virial current diagnose the difference, and full conformal symmetry is what powers the bootstrap.

The enhancement question is more subtle. In two dimensions, scale invariance implies conformal invariance under standard assumptions such as unitarity, Poincaré invariance, discreteness of the spectrum, and existence of a good stress tensor. In dimensions greater than two, there are strong perturbative arguments and broad evidence in physically important classes, but the most general nonperturbative theorem requires assumptions and care.

For this volume, the policy is practical and explicit. We call a theory a CFT only when conformal invariance is part of the structure. When a theory is introduced as an RG fixed point, the page should either state the enhancement assumptions or cite a source where conformal invariance is established.

## Exercises

### Exercise 1: Scale invariance of a scalar two-point function

Let $G(x)=\langle \mathcal O(x)\mathcal O(0)\rangle$ for a scalar scaling operator of dimension $\Delta$ in a translation- and rotation-invariant vacuum. Use scale invariance to show that

$$
G(x)=\frac{C}{\lvert x\rvert^{2\Delta}}.
$$

<details>
<summary><strong>Solution</strong></summary>

Translation and rotation invariance imply $G(x)=G(r)$ with $r=\lvert x\rvert$. Scale covariance of two identical operators gives

$$
G(\lambda r)=\lambda^{-2\Delta}G(r).
$$

Set $r=1$ and choose $\lambda=r$. Then

$$
G(r)=r^{-2\Delta}G(1).
$$

Writing $C=G(1)$ gives

$$
G(x)=\frac{C}{\lvert x\rvert^{2\Delta}}.
$$

</details>

### Exercise 2: Conservation of the special-conformal current

Assume $T_{\mu\nu}$ is symmetric, conserved, and traceless. Show that

$$
J^{(K_\rho)}_\mu=
\left(2x_\rho x^\nu-x^2\delta_\rho{}^\nu\right)T_{\mu\nu}
$$

is conserved.

<details>
<summary><strong>Solution</strong></summary>

Differentiate:

$$
\partial^\mu J^{(K_\rho)}_\mu
=\partial^\mu\left(2x_\rho x^\nu-x^2\delta_\rho{}^\nu\right)T_{\mu\nu}
+\left(2x_\rho x^\nu-x^2\delta_\rho{}^\nu\right)\partial^\mu T_{\mu\nu}.
$$

The second term vanishes by stress-tensor conservation. For the first term,

$$
\partial^\mu\left(2x_\rho x^\nu-x^2\delta_\rho{}^\nu\right)
=2\delta^\mu{}_{\rho}x^\nu+2x_\rho\delta^{\mu\nu}-2x^\mu\delta_\rho{}^\nu.
$$

Contracting with a symmetric $T_{\mu\nu}$, the first and third terms cancel, leaving

$$
\partial^\mu J^{(K_\rho)}_\mu=2x_\rho T^\mu{}_{\mu}=0.
$$

</details>

### Exercise 3: Improvement of the free scalar stress tensor

For the massless scalar in $d$ Euclidean dimensions, take

$$
T_{\mu\nu}=\partial_\mu\phi\partial_\nu\phi
-\frac12\delta_{\mu\nu}(\partial\phi)^2.
$$

Use the equation of motion $\partial^2\phi=0$ to show that adding

$$
\xi\left(\delta_{\mu\nu}\partial^2-\partial_\mu\partial_\nu\right)\phi^2
$$

with $\xi=(d-2)/(4(d-1))$ makes the trace vanish.

<details>
<summary><strong>Solution</strong></summary>

The trace of the canonical tensor is

$$
T^\mu{}_{\mu}=\left(1-\frac d2\right)(\partial\phi)^2
=-\frac{d-2}{2}(\partial\phi)^2.
$$

On shell,

$$
\partial^2\phi^2=2(\partial\phi)^2+2\phi\partial^2\phi=2(\partial\phi)^2,
$$

so

$$
T^\mu{}_{\mu}=-\frac{d-2}{4}\partial^2\phi^2.
$$

The trace of the improvement term is

$$
\xi(d-1)\partial^2\phi^2.
$$

With

$$
\xi=\frac{d-2}{4(d-1)},
$$

this equals $(d-2)\partial^2\phi^2/4$, which cancels the canonical trace.

</details>

### Exercise 4: Why scale invariance does not fix the scalar three-point function

For three scalar operators in $d>1$, explain why translation, rotation, and scale invariance alone allow more functional freedom than conformal invariance.

<details>
<summary><strong>Solution</strong></summary>

Translation invariance lets the correlator depend only on relative separations. Rotation invariance lets it depend on the three distances $x_{12}$, $x_{13}$, and $x_{23}$. Scale invariance fixes only the overall homogeneity under

$$
x_{ij}\mapsto \lambda x_{ij}.
$$

After removing one overall scale, two independent dimensionless ratios remain. Therefore scale invariance alone can allow an arbitrary function of such ratios.

Conformal invariance includes special conformal transformations. For three distinct points, the conformal group has enough freedom to remove the remaining shape dependence, leaving only the standard three-point structure times one coefficient $\lambda_{ijk}$.

</details>

## References

- S. Coleman, “Dilatations,” in *Aspects of Symmetry*, Cambridge University Press, 1985. Classic physical discussion of scale currents, anomalies, RG equations, and OPE ideas.
- J. Polchinski, “Scale and Conformal Invariance in Quantum Field Theory,” *Nuclear Physics B* **303** (1988). Foundational analysis of the enhancement problem.
- V. Riva and J. Cardy, “Scale and Conformal Invariance in Field Theory: A Physical Counterexample,” *Physics Letters B* **622** (2005), arXiv:hep-th/0504197. A standard warning example.
- Y. Nakayama, “Scale Invariance vs Conformal Invariance,” arXiv:1302.0884. Broad review of examples, assumptions, and the state of the enhancement problem.
- M. A. Luty, J. Polchinski, and R. Rattazzi, “The a-Theorem and the Asymptotics of 4D Quantum Field Theory,” *Journal of High Energy Physics* **2013** (2013), arXiv:1204.5221. Perturbative four-dimensional perspective.
- A. Dymarsky, K. Farnsworth, Z. Komargodski, M. A. Luty, and V. Prilepina, “Scale Invariance, Conformality, and Generalized Free Fields,” arXiv:1402.6322. Addresses a loophole in four-dimensional arguments.
- A. Dymarsky and A. Zhiboedov, “Scale-Invariant Breaking of Conformal Symmetry,” arXiv:1505.01152. Discusses embedding scale-invariant subsectors into CFTs and related constraints.
- P. Di Francesco, P. Mathieu, and D. Sénéchal, *Conformal Field Theory*, Springer, 1997. Standard two-dimensional CFT textbook.
- D. Simmons-Duffin, “TASI Lectures on the Conformal Bootstrap,” arXiv:1602.07982. Modern higher-dimensional CFT introduction.

## Version history

- **2026-06-26:** Initial polished draft explaining the scale-versus-conformal distinction, stress-tensor criterion, examples, pitfalls, exercises, and reference map.
